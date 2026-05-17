import streamlit as st
import random
import time

st.set_page_config(page_title="Ecuaciones de primer grado", page_icon="🧮")

st.title("🧮 Juego de ecuaciones de primer grado")
st.write("Resuelve la ecuación y verifica tu respuesta.")

def nueva_ecuacion():
    x = random.randint(-10, 10)
    a = random.randint(1, 9)
    b = random.randint(-20, 20)
    c = a * x + b

    return a, b, c, x

if "ecuacion" not in st.session_state:
    st.session_state.ecuacion = nueva_ecuacion()

a, b, c, solucion = st.session_state.ecuacion

signo = "+" if b >= 0 else "-"
st.subheader(f"Resuelve: {a}x {signo} {abs(b)} = {c}")

respuesta = st.number_input("Escribe el valor de x:", step=1)

col1, col2 = st.columns(2)

with col1:
    if st.button("Verificar respuesta"):
        with st.spinner("Revisando tu respuesta..."):
            time.sleep(1)

        if respuesta == solucion:
            st.success("🎉 ¡Correcto! Muy bien.")
            st.balloons()
        else:
            st.error("❌ Incorrecto. Intenta nuevamente.")
            st.snow()

with col2:
    if st.button("Nueva ecuación"):
        st.session_state.ecuacion = nueva_ecuacion()
        st.rerun()

st.info("Presiona 'Nueva ecuación' para practicar otra.")
