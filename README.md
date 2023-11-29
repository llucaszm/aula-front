import { useState } from 'react';                                
import { FormLogin, FormCadastro } from './components';

export default function App() {
  const [tipoForm, setTipoForm] = useState(null);

  const handleButtonClick = (tipo) => {
    setTipoForm(tipo);
  };

  return (
    <div className="App container-fluid">
      <h1 className="mb-4">e-comércio - N2 Q8</h1>
      <div className="btn-group" role="group">
        <button
          type="button"
          className="btn btn-primary"
          onClick={() => handleButtonClick('cadastro')}
        >
          Cadastre-se
        </button>
        <button
          type="button"
          className="btn btn-success"
          onClick={() => handleButtonClick('login')}
        >
          Login
        </button>
      </div>
      <div style={{ marginTop: 16 }}>
        {tipoForm === 'cadastro' ? (
          <FormCadastro />
        ) : tipoForm === 'login' ? (
          <FormLogin />
        ) : (
          <p style={{ marginTop: 12, fontSize: 12 }}>
            Selecione uma ação acima
          </p>
        )}
      </div>
    </div>
  );
}
