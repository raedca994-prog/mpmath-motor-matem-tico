# mpmath-motor-matem-tico
 Fórmula explícita de Riemann-von Mangoldt para psi(x) usando ceros de zeta
def psi_riemann_explicita(x: float, num_ceros: int = 50):
suma_ceros = mp.mpc(0)
for n in range(1, num_ceros + 1):
# Obtiene el n-ésimo cero no trivial: rho = 0.5 + i * gamma_n
rho = mp.zetazero(n)
# Cada cero aporta rho y su conjugado (parte real * 2)
termino = (x ** rho) / rho
suma_ceros += 2 * mp.re(termino)
Resultados reales de la prueba en vivo:
Cota de Schoenfeld (x = 1.000.000): 78.498 primos reales, estimación Li(x) = 78.627,55, error real 129,55 frente al margen máximo teórico 549,70 (cumple la cota: true).
Fórmula explícita de Riemann-von Mangoldt (x = 20, 100 ceros de Zeta): psi(20) ≈ 19,2092.
