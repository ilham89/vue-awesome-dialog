<script>
import { defineComponent } from "vue-demi";

export default /*#__PURE__*/ defineComponent({
    name: "VueAwesomeDialog", // vue component name
    emits: ["close", "save"],
    setup(_, { emit }) {
        const close = () => {
            emit("close");
        };
        const save = () => {
            emit("save");
        };
        return {
            close,
            save,
        };
    },
});
</script>

<template>
    <transition name="modal-fade">
        <div class="modal-backdrop">
            <div
                class="modal"
                role="dialog"
                aria-labelledby="modalTitle"
                aria-describedby="modalDescription"
            >
                <header class="modal-header" id="modalTitle">
                    <slot name="header"> Default Title! </slot>
                    <button
                        type="button"
                        class="btn-close"
                        @click="close"
                        aria-label="Close modal"
                    >
                        x
                    </button>
                </header>
                <section class="modal-body" id="modalDescription">
                    <slot name="body"> This is the default body! </slot>
                </section>
                <footer class="modal-footer">
                    <div class="action-footer">
                        <button
                            type="button"
                            class="btn-green"
                            @click="close"
                            aria-label="Close modal"
                        >
                            Discard
                        </button>
                        <button
                            type="button"
                            class="btn-green btn-save"
                            @click="save"
                            aria-label="Close modal"
                        >
                            Save
                        </button>
                    </div>
                </footer>
            </div>
        </div>
    </transition>
</template>

<style scoped>
.modal-backdrop {
    position: fixed;
    top: 0;
    bottom: 0;
    left: 0;
    right: 0;
    background-color: rgba(0, 0, 0, 0.3);
    display: flex;
    justify-content: center;
    align-items: center;
}
.modal {
    background: #ffffff;
    border-radius: 0.5em;
    box-shadow: 0 10px 20px rgba(black, 0.2);
    overflow-x: auto;
    display: flex;
    flex-direction: column;
    max-width: 80%;
    max-height: 80%;
    -ms-overflow-style: none;
    scrollbar-width: none;
}
.modal::-webkit-scrollbar {
    display: none;
}
.modal-header {
    padding: 15px;
    display: flex;
    position: sticky;
    top: 0;
    background-color: white;
    z-index: 10;
}
.modal-footer {
    padding: 15px;
    display: flex;
}
.modal-header {
    /* position: relative; */
    border-bottom: 1px solid #eeeeee;
    color: #1ecd97;
    justify-content: space-between;
}
.modal-footer {
    border-top: 1px solid #eeeeee;
    flex-direction: column;
    position: sticky;
    bottom: 0;
    background: white;
    z-index: 10;
}
.modal-body {
    position: relative;
    padding: 20px 10px;
}
.btn-close {
    position: absolute;
    top: 0;
    right: 0;
    border: none;
    font-size: 20px;
    padding: 10px;
    cursor: pointer;
    font-weight: bold;
    color: #1ecd97;
    background: transparent;
}
.btn-green {
    outline: none;
    height: 40px;
    text-align: center;
    border-radius: 10px;
    background: #fff;
    border: 2px solid #1ecd97;
    color: #1ecd97;
    letter-spacing: 1px;
    text-shadow: 0;
    font-size: 12px;
    font-weight: bold;
    cursor: pointer;
    transition: all 0.25s ease;
    padding: 8px 12px;
}
.btn-save {
    color: white;
    background: #1ecd97;
    margin-left: 16px;
}
.btn-green:hover {
    background: #f6f5f5;
}
.btn-save:hover {
    color: white;
    background: #02a873;
    border: 2px solid #02a873;
}
.action-footer {
    display: flex;
    justify-content: end;
}
.modal-fade-enter,
.modal-fade-leave-to {
    opacity: 0;
}
.modal-fade-enter-active,
.modal-fade-leave-active {
    transition: opacity 0.5s ease;
}
</style>