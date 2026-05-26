export default function EmployeePortalDemo() {
  const users = [
    {
      id: 1,
      name: 'Carlos Ramírez',
      email: 'carlos@empresa.com',
      role: 'Empleado',
      status: 'Activo',
    },
    {
      id: 2,
      name: 'Laura Gómez',
      email: 'laura@empresa.com',
      role: 'Administrador',
      status: 'Activo',
    },
    {
      id: 3,
      name: 'Miguel Torres',
      email: 'miguel@empresa.com',
      role: 'Empleado',
      status: 'Inactivo',
    },
  ];

  return (
    <div className="min-h-screen bg-gray-100 p-6">
      <div className="max-w-6xl mx-auto grid grid-cols-1 lg:grid-cols-3 gap-6">
        {/* Login */}
        <div className="bg-white rounded-3xl shadow-lg p-6">
          <h1 className="text-3xl font-bold mb-2">Portal Empresarial</h1>
          <p className="text-gray-500 mb-6">
            Acceso privado para empleados.
          </p>

          <div className="space-y-4">
            <input
              type="email"
              placeholder="Correo corporativo"
              className="w-full border rounded-2xl px-4 py-3"
            />

            <input
              type="password"
              placeholder="Contraseña"
              className="w-full border rounded-2xl px-4 py-3"
            />

            <button className="w-full bg-black text-white py-3 rounded-2xl font-semibold hover:opacity-90 transition">
              Ingresar
            </button>
          </div>

          <div className="mt-8 border-t pt-6">
            <h2 className="font-semibold text-lg mb-4">Crear usuario</h2>

            <div className="space-y-3">
              <input
                type="text"
                placeholder="Nombre completo"
                className="w-full border rounded-2xl px-4 py-3"
              />

              <input
                type="email"
                placeholder="Correo"
                className="w-full border rounded-2xl px-4 py-3"
              />

              <select className="w-full border rounded-2xl px-4 py-3">
                <option>Empleado</option>
                <option>Administrador</option>
              </select>

              <button className="w-full bg-blue-600 text-white py-3 rounded-2xl font-semibold hover:opacity-90 transition">
                Registrar usuario
              </button>
            </div>
          </div>
        </div>

        {/* Private Menu */}
        <div className="bg-white rounded-3xl shadow-lg p-6 lg:col-span-2">
          <div className="flex items-center justify-between mb-6">
            <div>
              <h2 className="text-2xl font-bold">Menú Privado</h2>
              <p className="text-gray-500">
                Contenido accesible únicamente para empleados autorizados.
              </p>
            </div>

            <div className="bg-green-100 text-green-700 px-4 py-2 rounded-full text-sm font-medium">
              Sesión activa
            </div>
          </div>

          {/* Menu Cards */}
          <div className="grid grid-cols-1 md:grid-cols-3 gap-4 mb-8">
            <div className="bg-gray-50 rounded-2xl p-5 border hover:shadow-md transition cursor-pointer">
              <h3 className="font-bold text-lg mb-2">Documentos</h3>
              <p className="text-gray-500 text-sm">
                Acceso a archivos internos de la empresa.
              </p>
            </div>

            <div className="bg-gray-50 rounded-2xl p-5 border hover:shadow-md transition cursor-pointer">
              <h3 className="font-bold text-lg mb-2">Recursos Humanos</h3>
              <p className="text-gray-500 text-sm">
                Información de empleados y procesos internos.
              </p>
            </div>

            <div className="bg-gray-50 rounded-2xl p-5 border hover:shadow-md transition cursor-pointer">
              <h3 className="font-bold text-lg mb-2">Reportes</h3>
              <p className="text-gray-500 text-sm">
                Métricas y reportes administrativos.
              </p>
            </div>
          </div>

          {/* Users Table */}
          <div>
            <div className="flex items-center justify-between mb-4">
              <h3 className="text-xl font-bold">Administración de usuarios</h3>

              <button className="bg-red-600 text-white px-4 py-2 rounded-xl text-sm font-medium hover:opacity-90 transition">
                Cerrar sesión
              </button>
            </div>

            <div className="overflow-x-auto">
              <table className="w-full border-collapse">
                <thead>
                  <tr className="bg-gray-100 text-left">
                    <th className="p-3 rounded-l-2xl">Nombre</th>
                    <th className="p-3">Correo</th>
                    <th className="p-3">Rol</th>
                    <th className="p-3">Estado</th>
                    <th className="p-3 rounded-r-2xl">Acciones</th>
                  </tr>
                </thead>

                <tbody>
                  {users.map((user) => (
                    <tr key={user.id} className="border-b">
                      <td className="p-3 font-medium">{user.name}</td>
                      <td className="p-3 text-gray-600">{user.email}</td>
                      <td className="p-3">{user.role}</td>
                      <td className="p-3">
                        <span
                          className={`px-3 py-1 rounded-full text-sm ${
                            user.status === 'Activo'
                              ? 'bg-green-100 text-green-700'
                              : 'bg-gray-200 text-gray-600'
                          }`}
                        >
                          {user.status}
                        </span>
                      </td>

                      <td className="p-3 flex gap-2">
                        <button className="bg-yellow-100 text-yellow-700 px-3 py-1 rounded-lg text-sm hover:opacity-90 transition">
                          Editar
                        </button>

                        <button className="bg-red-100 text-red-700 px-3 py-1 rounded-lg text-sm hover:opacity-90 transition">
                          Eliminar
                        </button>
                      </td>
                    </tr>
                  ))}
                </tbody>
              </table>
            </div>
          </div>
        </div>
      </div>

      {/* Footer */}
      <div className="max-w-6xl mx-auto mt-6 text-center text-sm text-gray-500">
        Primera versión funcional del sistema de acceso empresarial.
      </div>
    </div>
  );
}
