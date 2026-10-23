# Ariel Eduardo Borbon Izaguirre 252116


¿por qué se usa un contexto y no props para la sesión?
porque el usuario es un estado global que tenemos en todos lados, no en un solo componente, si usaramos un prop tuvieramos que andar malabarenado los datos del usuario por muchos componentes, con el contexto nos ahorramos eso


¿qué pasa si un componente usa la sesión fuera del proveedor?
si se quiere usar el useContext en una ruta afuera de ProveedorSesion, react no va a encontrarlo y devolvera el valor default (null), aunque en nuestro caso apareceria "useSession() Tiene que usarse dentro del componente principal (ProveedorSesion)"


¿dónde se guarda el token y qué riesgo tiene ese lugar?
el token se guarda de manera local en el LocalStorage, el cual se puede ver directo si no esta encriptado, y un riesgo seria el XSS donde si un atacante le mete codigo JS a la App de alguna manera, podria leer LocalStorage, robandose el JWT del usuario y robarle la identidad a un usuario