useRef

useRef allows us to get direct access to a JSX element.
The useRef returns a mutable ref object. This object has a property called .current.

For example, if we wanted to write some code that focuses a search
input when the users use the key combination Control + K.

import { useWindowEvent } from "@mantine/hooks";
import { useRef } from "react";

function Header() {

const inputRef = useRef();

useWindowEvent("keydown", (event) => {
if (event.code === "KeyK" && event.ctrlKey) {
event.preventDefault();
inputRef.current.focus();
}
});

return <input ref={inputRef} />

}
