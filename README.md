# typewriter.js
Add a typewriter effect to your text

Para lograr el efecto de máquina de escribir (typewrite) primero se debe incluir el JS en el HTML.

					<script src="typewriter.js"></script>
			
Luego añadir el siguiente CSS, el cual le da el estilo al texto con la clase typewrite, y se customiza el cursor parpadeante con la clase typewrite:after

				<style type="text/css">
					.typewrite{
						font-size: 20px;
						font-weight: 300;
					}

					.typewrite:after {
						content: ''; /* Sin contenido despues del cursor */ 
						display: inline-block;
						position: relative;
						top: 0px;
						width: 3px; /* ancho del cursor */
						height: 20px; /* altura del cursor */
						background: red; /* color del cursor */
						opacity: 0; 
						-webkit-animation: showBlink steps(1) 1s infinite; /* animacion (showBlink) */
						animation: showBlink steps(1) 1s infinite;					
					}

					/* showBlink keyframes */
					@-webkit-keyframes showBlink {
					  0%   { opacity: 1; }
					  50%  { opacity: 0; }
					  100% { opacity: 1; }
					}
					@keyframes showBlink {
					  0%   { opacity: 1; }
					  50%  { opacity: 0; }
					  100% { opacity: 1; }
					}
				</style>
			
Finalmente debes crear un <span class="typewrite">, que contenga dos atributos. El primero es data-period, que dicta cuantos milisegundos dura el texto antes de ser borrado y reemplazado. El segundo atributo es data-type, el cual contiene una lista de valores, los cuales seran animados uno tras otro, en el mismo orden.

				<span class="typewrite" data-period="3000" data-type='[ "ESTE", "EJEMPLO", "UTILIZA" , "TYPEWRITER" ] '>
					HOLA
				</span>							
			
Puedes revisar el código fuente de esta página para ver como funciona
