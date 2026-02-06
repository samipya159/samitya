import { useState } from "react";

export const App = () => {
  const [formVal, setFormVal] = useState({
    name: "",
    email: "",
    desc: "",
  });

  return (
    <div>
      <form
        onSubmit={(e) => {
          e.preventDefault();
          console.log(formVal);
        }}
      >
        <input
          type="text"
          placeholder="Enter your name"
          value={formVal.name}
          onChange={(e) =>
            setFormVal((prev) => {
              return { ...prev, name: e.target.value };
            })
          }
        />
        <br />
        <br />

        <input
          type="email"
          placeholder="Enter your email"
          value={formVal.email}
          onChange={(e) =>
            setFormVal((prev) => {
              return { ...prev, email: e.target.value };
            })
          }
        />
        <br />
        <br />
        <textarea
          value={formVal.desc}
          onChange={(e) =>
            setFormVal((prev) => {
              return { ...prev, desc: e.target.value };
            })
          }
        />
        <br />
        <br />
        <button>Submit</button>
      </form>
    </div>
  );
};
