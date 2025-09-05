# Smarttraderacademy
App para hacer trading con ayuda de ia 
import React, { useState } from 'react';
import { DollarSign, Users, TrendingUp, Mail, Settings, BarChart3, Target, Plus, Search, Eye, Edit, Trash2, Download, Bell, RefreshCw } from 'lucide-react';

const AdminDashboard = () => {
  const [activeTab, setActiveTab] = useState('overview');

  return (
    <div className="max-w-7xl mx-auto bg-gray-50 min-h-screen">
      {/* Header */}
      <div className="bg-gradient-to-r from-indigo-600 to-purple-600 text-white p-6 shadow-lg">
        <div className="flex justify-between items-center">
          <div>
            <h1 className="text-3xl font-bold mb-2">🚀 SmartTrader Academy</h1>
            <p className="text-lg opacity-90">Admin Dashboard - Control Total</p>
          </div>
          <div className="text-right">
            <div className="text-2xl font-bold">$15,680</div>
            <div className="text-sm opacity-90">Revenue este mes</div>
          </div>
        </div>
      </div>

      {/* Navigation Tabs */}
      <div className="bg-white shadow-sm border-b">
        <div className="flex space-x-0">
          {[
            { key: 'overview', label: '📊 Dashboard', icon: BarChart3 },
            { key: 'users', label: '👥 Usuarios', icon: Users },
            { key: 'email', label: '📧 Email Marketing', icon: Mail },
            { key: 'settings', label: '⚙️ Configuración', icon: Settings }
          ].map(({ key, label, icon: Icon }) => (
            <button
              key={key}
              onClick={() => setActiveTab(key)}
              className={`flex items-center px-6 py-4 border-b-2 font-medium text-sm ${
                activeTab === key 
                  ? 'border-indigo-500 text-indigo-600 bg-indigo-50' 
                  : 'border-transparent text-gray-500 hover:text-gray-700 hover:border-gray-300'
              }`}
            >
              <Icon size={18} className="mr-2" />
              {label}
            </button>
          ))}
        </div>
      </div>

      {/* Content */}
      <div className="p-6">
        {activeTab === 'overview' && (
          <div className="space-y-6">
            {/* Stats Cards */}
            <div className="grid grid-cols-1 md:grid-cols-4 gap-6">
              <div className="bg-white p-6 rounded-lg shadow border">
                <div className="flex items-center">
                  <div className="flex-shrink-0">
                    <DollarSign className="h-8 w-8 text-green-500" />
                  </div>
                  <div className="ml-5 w-0 flex-1">
                    <dl>
                      <dt className="text-sm font-medium text-gray-500 truncate">Revenue Mensual</dt>
                      <dd className="text-2xl font-bold text-gray-900">$15,680</dd>
                    </dl>
                  </div>
                </div>
                <div className="mt-2">
                  <div className="flex items-center text-sm text-green-600">
                    <TrendingUp className="h-4 w-4" />
                    <span className="ml-1">+127% vs mes anterior</span>
                  </div>
                </div>
              </div>

              <div className="bg-white p-6 rounded-lg shadow border">
                <div className="flex items-center">
                  <div className="flex-shrink-0">
                    <Users className="h-8 w-8 text-blue-500" />
                  </div>
                  <div className="ml-5 w-0 flex-1">
                    <dl>
                      <dt className="text-sm font-medium text-gray-500 truncate">Usuarios Totales</dt>
                      <dd className="text-2xl font-bold text-gray-900">2,847</dd>
                    </dl>
                  </div>
                </div>
                <div className="mt-2">
                  <div className="text-sm text-gray-600">
                    847 Premium • 340 Trial
                  </div>
                </div>
              </div>

              <div className="bg-white p-6 rounded-lg shadow border">
                <div className="flex items-center">
                  <div className="flex-shrink-0">
                    <Target className="h-8 w-8 text-purple-500" />
                  </div>
                  <div className="ml-5 w-0 flex-1">
                    <dl>
                      <dt className="text-sm font-medium text-gray-500 truncate">Conversión Rate</dt>
                      <dd className="text-2xl font-bold text-gray-900">67.8%</dd>
                    </dl>
                  </div>
                </div>
                <div className="mt-2">
                  <div className="text-sm text-green-600">
                    Industria promedio: 15%
                  </div>
                </div>
              </div>

              <div className="bg-white p-6 rounded-lg shadow border">
                <div className="flex items-center">
                  <div className="flex-shrink-0">
                    <BarChart3 className="h-8 w-8 text-orange-500" />
                  </div>
                  <div className="ml-5 w-0 flex-1">
                    <dl>
                      <dt className="text-sm font-medium text-gray-500 truncate">LTV Promedio</dt>
                      <dd className="text-2xl font-bold text-gray-900">$127</dd>
                    </dl>
                  </div>
                </div>
                <div className="mt-2">
                  <div className="text-sm text-gray-600">
                    CAC: $12 • ROI: 10.6x
                  </div>
                </div>
              </div>
            </div>

            {/* Real-time Activity */}
            <div className="bg-white shadow rounded-lg">
              <div className="px-6 py-4 border-b border-gray-200">
                <h3 className="text-lg font-medium text-gray-900">📈 Actividad en Tiempo Real</h3>
              </div>
              <div className="p-6">
                <div className="grid grid-cols-2 md:grid-cols-4 gap-4">
                  <div className="text-center">
                    <div className="text-3xl font-bold text-green-600">156</div>
                    <div className="text-sm text-gray-500">Usuarios Online</div>
                  </div>
                  <div className="text-center">
                    <div className="text-3xl font-bold text-blue-600">89</div>
                    <div className="text-sm text-gray-500">Signups Hoy</div>
                  </div>
                  <div className="text-center">
                    <div className="text-3xl font-bold text-purple-600">23</div>
                    <div className="text-sm text-gray-500">Conversiones Hoy</div>
                  </div>
                  <div className="text-center">
                    <div className="text-3xl font-bold text-orange-600">94.2%</div>
                    <div className="text-sm text-gray-500">Uptime Sistema</div>
                  </div>
                </div>
              </div>
            </div>

            {/* Top Referrers */}
            <div className="bg-white shadow rounded-lg">
              <div className="px-6 py-4 border-b border-gray-200">
                <h3 className="text-lg font-medium text-gray-900">🏆 Top Referrers del Mes</h3>
              </div>
              <div className="p-6">
                <div className="space-y-4">
                  {[
                    { name: '@CryptoInfluencer', referrals: 127, earnings: 2540 },
                    { name: '@TradingGuru_ES', referrals: 89, earnings: 1780 },
                    { name: '@BitcoinMaria', referrals: 76, earnings: 1520 }
                  ].map((user, index) => (
                    <div key={index} className="flex items-center justify-between py-3 border-b border-gray-100 last:border-b-0">
                      <div className="flex items-center">
                        <div className="w-10 h-10 bg-gradient-to-r from-blue-500 to-purple-500 rounded-full flex items-center justify-center text-white font-bold text-sm mr-4">
                          #{index + 1}
                        </div>
                        <div>
                          <div className="font-medium text-gray-900">{user.name}</div>
                          <div className="text-sm text-gray-500">{user.referrals} referidos exitosos</div>
                        </div>
                      </div>
                      <div className="text-right">
                        <div className="font-bold text-green-600">${user.earnings}</div>
                        <div className="text-sm text-gray-500">ganancia total</div>
                      </div>
                    </div>
                  ))}
                </div>
              </div>
            </div>
          </div>
        )}

        {activeTab === 'users' && (
          <div className="space-y-6">
            <div className="bg-white shadow rounded-lg">
              <div className="px-6 py-4 border-b border-gray-200 flex justify-between items-center">
                <h3 className="text-lg font-medium text-gray-900">👥 Gestión de Usuarios</h3>
                <div className="flex space-x-3">
                  <button className="bg-blue-600 text-white px-4 py-2 rounded-md text-sm font-medium hover:bg-blue-700">
                    <Plus className="h-4 w-4 inline mr-1" />
                    Nuevo Usuario
                  </button>
                  <button className="bg-gray-100 text-gray-700 px-4 py-2 rounded-md text-sm font-medium hover:bg-gray-200">
                    <Download className="h-4 w-4 inline mr-1" />
                    Exportar
                  </button>
                </div>
              </div>
              <div className="overflow-hidden">
                <table className="min-w-full divide-y divide-gray-200">
                  <thead className="bg-gray-50">
                    <tr>
                      <th className="px-6 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider">Usuario</th>
                      <th className="px-6 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider">Plan</th>
                      <th className="px-6 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider">Revenue</th>
                      <th className="px-6 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider">Estado</th>
                      <th className="px-6 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider">Acciones</th>
                    </tr>
                  </thead>
                  <tbody className="bg-white divide-y divide-gray-200">
                    {[
                      { name: 'María González', email: 'maria@email.com', plan: 'Pro', revenue: 156, status: 'active' },
                      { name: 'Carlos Silva', email: 'carlos@email.com', plan: 'Básico', revenue: 89, status: 'active' },
                      { name: 'Ana Rodríguez', email: 'ana@email.com', plan: 'Trial', revenue: 0, status: 'trial' },
                      { name: 'José Martín', email: 'jose@email.com', plan: 'Pro', revenue: 234, status: 'active' }
                    ].map((user, index) => (
                      <tr key={index} className="hover:bg-gray-50">
                        <td className="px-6 py-4 whitespace-nowrap">
                          <div className="flex items-center">
                            <div className="flex-shrink-0 h-10 w-10">
                              <div className="h-10 w-10 rounded-full bg-gradient-to-r from-blue-400 to-purple-500 flex items-center justify-center text-white font-medium text-sm">
                                {user.name.split(' ').map(n => n[0]).join('')}
                              </div>
                            </div>
                            <div className="ml-4">
                              <div className="text-sm font-medium text-gray-900">{user.name}</div>
                              <div className="text-sm text-gray-500">{user.email}</div>
                            </div>
                          </div>
                        </td>
                        <td className="px-6 py-4 whitespace-nowrap">
                          <span className={`inline-flex px-2 py-1 text-xs font-semibold rounded-full ${
                            user.plan === 'Pro' ? 'bg-purple-100 text-purple-800' :
                            user.plan === 'Básico' ? 'bg-blue-100 text-blue-800' :
                            'bg-gray-100 text-gray-800'
                          }`}>
                            {user.plan}
                          </span>
                        </td>
                        <td className="px-6 py-4 whitespace-nowrap text-sm text-gray-900">
                          ${user.revenue}
                        </td>
                        <td className="px-6 py-4 whitespace-nowrap">
                          <span className={`inline-flex px-2 py-1 text-xs font-semibold rounded-full ${
                            user.status === 'active' ? 'bg-green-100 text-green-800' : 'bg-yellow-100 text-yellow-800'
                          }`}>
                            {user.status === 'active' ? 'Activo' : 'Trial'}
                          </span>
                        </td>
                        <td className="px-6 py-4 whitespace-nowrap text-sm font-medium">
                          <div className="flex space-x-2">
                            <button className="text-indigo-600 hover:text-indigo-900">
                              <Eye className="h-4 w-4" />
                            </button>
                            <button className="text-green-600 hover:text-green-900">
                              <Edit className="h-4 w-4" />
                            </button>
                            <button className="text-red-600 hover:text-red-900">
                              <Trash2 className="h-4 w-4" />
                            </button>
                          </div>
                        </td>
                      </tr>
                    ))}
                  </tbody>
                </table>
              </div>
            </div>
          </div>
        )}

        {activeTab === 'email' && (
          <div className="space-y-6">
            <div className="bg-white shadow rounded-lg">
              <div className="px-6 py-4 border-b border-gray-200">
                <h3 className="text-lg font-medium text-gray-900">📧 Performance de Campañas Email</h3>
              </div>
              <div className="p-6">
                <div className="space-y-4">
                  {[
                    { name: 'Trial Ending Reminder', sent: 340, opened: 89.2, revenue: 1380 },
                    { name: 'New Feature: Claude Pro', sent: 2140, opened: 78.5, revenue: 2560 },
                    { name: 'Weekend Trading Signals', sent: 847, opened: 92.1, revenue: 5240 }
                  ].map((campaign, index) => (
                    <div key={index} className="border rounded-lg p-4 hover:bg-gray-50">
                      <div className="flex justify-between items-center">
                        <div>
                          <h4 className="font-medium text-gray-900">{campaign.name}</h4>
                          <div className="text-sm text-gray-500 mt-1">
                            Enviados: {campaign.sent.toLocaleString()} | Abiertos: {campaign.opened}%
                          </div>
                        </div>
                        <div className="text-right">
                          <div className="font-bold text-green-600">${campaign.revenue.toLocaleString()}</div>
                          <div className="text-sm text-gray-500">Revenue generado</div>
                        </div>
                      </div>
                    </div>
                  ))}
                </div>
              </div>
            </div>
          </div>
        )}

        {activeTab === 'settings' && (
          <div className="space-y-6">
            <div className="bg-white shadow rounded-lg">
              <div className="px-6 py-4 border-b border-gray-200">
                <h3 className="text-lg font-medium text-gray-900">⚙️ Configuración de la App</h3>
              </div>
              <div className="p-6 space-y-6">
                <div className="grid grid-cols-1 md:grid-cols-2 gap-6">
                  <div>
                    <label className="block text-sm font-medium text-gray-700 mb-2">Precio Plan Básico ($)</label>
                    <input 
                      type="number" 
                      defaultValue="2.99" 
                      className="w-full px-3 py-2 border border-gray-300 rounded-md focus:outline-none focus:ring-2 focus:ring-indigo-500"
                    />
                  </div>
                  <div>
                    <label className="block text-sm font-medium text-gray-700 mb-2">Precio Plan Pro ($)</label>
                    <input 
                      type="number" 
                      defaultValue="4.99" 
                      className="w-full px-3 py-2 border border-gray-300 rounded-md focus:outline-none focus:ring-2 focus:ring-indigo-500"
                    />
                  </div>
                </div>

                <div>
                  <label className="block text-sm font-medium text-gray-700 mb-2">Mensaje de Bienvenida de Claude</label>
                  <textarea 
                    rows={4}
                    className="w-full px-3 py-2 border border-gray-300 rounded-md focus:outline-none focus:ring-2 focus:ring-indigo-500"
                    defaultValue="¡Hola! Soy Claude, tu profesor personal de trading. Estoy aquí para enseñarte a invertir de forma inteligente y segura. ¿Empezamos?"
                  />
                </div>

                <div className="pt-4">
                  <button className="bg-green-600 text-white px-6 py-2 rounded-md hover:bg-green-700 font-medium">
                    Guardar Cambios
                  </button>
                </div>
              </div>
            </div>
          </div>
        )}
      </div>

      {/* Footer */}
      <div className="bg-white border-t mt-12">
        <div className="text-center py-6 text-sm text-gray-500">
          SmartTrader Academy Admin Panel • Powered by Claude.ai
        </div>
      </div>
    </div>
  );
};

export default AdminDashboard;
