<script>
    import image from "./../assets/summa-fed.jpg";
    import products from "../products";

    var query = window.matchMedia("(min-width: 723px)");

    let isDesktop = query.matches;
    const checkIsDesktop = (e) => {
        isDesktop = e.matches;
        console.log(e.matches);
    };

    query.addListener(checkIsDesktop);
</script>

{#each products as item}
    <div class="card-product">
        <div class="product-image">
            <img src={image} alt="" />
        </div>
        <div class="card-body">
            <div class="product-name">
                <span>{item.name}</span>
            </div>
            <div class="product-price">
                <small class="price"
                    >Antes ${new Intl.NumberFormat().format(item.price)}</small
                >
                <span class="final-price"
                    >${new Intl.NumberFormat().format(item.final_price)}</span
                >
            </div>
            <div class="actions">
                <button>{isDesktop ? "Ver detalles" : "Comprar"}</button>
            </div>
        </div>
    </div>
{/each}

<style>
    .card-product {
        display: block;
        flex-grow: 0;
        flex-shrink: 1;
        flex-basis: auto;
        align-self: auto;
        order: 0;
        background-color: #ffffff;
        width: 100%;
        flex: 1 21%;
    }

    .product-image img {
        width: 100%;
    }

    .card-product .card-body {
        padding: 16px;
        display: flex;
        flex-direction: column;
        gap: 16px;
    }

    .card-product .card-body .product-name {
        color: #141414;
    }
    .card-product .card-body .product-price {
        display: flex;
        flex-direction: column;
        gap: 5px;
    }

    .card-product .card-body .product-price .price {
        color: #747474;
    }
    .card-product .card-body .product-price .final-price {
        font-weight: 700;
        font-size: 20px;
    }

    .card-product .card-body .actions button {
        background-color: #4dbd3d;
        border: 0;
        outline: none;
        color: #ffffff;
        text-transform: uppercase;
        padding: 10px 15px;
        width: 100%;
        border-radius: 22px;
        font-weight: 600;
        transition: all 1s;
    }

    @media (min-width: 723px) {
        .card-product {
            display: block;
            flex-grow: 0;
            flex-shrink: 1;
            flex: 1 21%;
            order: 0;
            width: 100%;
            max-width: inherit;
            transition: all 1s;
        }
        .card-product:hover {
            -webkit-box-shadow: 0px 3px 41px -20px rgba(0, 0, 0, 0.75);
            -moz-box-shadow: 0px 3px 41px -20px rgba(0, 0, 0, 0.75);
            box-shadow: 0px 3px 41px -20px rgba(0, 0, 0, 0.75);
            cursor: pointer;
        }

        .card-product .card-body .actions button {
            padding: 12px 15px;
        }
        .card-product .card-body .actions button:hover {
            opacity: 0.7;
        }
    }
</style>
