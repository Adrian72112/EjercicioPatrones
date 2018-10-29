# Ejercicios de DIP, ISP, SRP
## Ejercicio 1 

**DIP:** No se cumple. Las clases de alto nivel no deben depender de clases de bajo nivel; ambas deben depender de abstracciones. AnalizarDatos crea un objecto BaseDeDatos, un cambio en la clase BaseDeDatos podria corromper el comportamieno de AnalizarDatos

**ISP:** Si se cumple. Ambas clases AnalizarDatos y BaseDeDatos no son forzados a depender de tipos que no usan.

**SRP:** No se cumple, AnalizarDatos tiene más de una responsabilidad. La de validar condicion por ejemplo. Se puede encapsular. 


## Ejercicio 2
## Ejercicio 3 

```cs

interface IData
{
    DataBaseObject[] ListarDatos();
}
//Objeto que representa un dato de la base de datos.
class DataBaseObject
{
    public string Descripcion { get; }
}

//Base de datos.
class BaseDeDatos : IData
{
    public DataBaseObject ObtenerDato(string clave)
    {
        //Devuelve el dato correspondiente a la clave
    }
    public void GrabarDato(string clave, DataBaseObject dato)
    {
        //Graba el dato en la base de datos, bajo la clave dada
    }
    public String[] ListarClaves()
    {
        //Devuelve un String[] con todas las claves
    }
    public String[] ListarDescripcionDatos()
    {
        //Devuelve un String[] con la descripción de todas los 
        //datos almacenados en  la base
    }
    public DataBaseObject[] ListarDatos()
    {
//Devuelve un DataBaseObject[] con todos los datos almacenados en la base
    }
}
class AnlizadorDatos
{
    private IData baseDatos{get; set;};

    public void Analizar()
    {
        foreach (DataBaseObject DBObj in baseDatos.ListarDatos())
        {
            Verificar(DBObj)    
        }
    }
    public void Verificar(DataBaseObject DBobj)
    {
        string msg;
        Validar.CumpleCondicion(DBObj,out msg)
        Mensaje(msg);
    }
    public void Mensaje(string msg)
    { /*Mensaje predeterminado*/ }
}

static class Validar()
{
    static void CumpleCondicion(DataBaseObject DBObj,out string mensaje)
    {
        //Evaluar y devolver 
    }
}

```