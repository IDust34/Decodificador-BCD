# Decodificador-BCD
BCd decodificador
--Decodificador BCD a display de 7 segmentos--

--Librerias--
library ieee;
use ieee.std_logic_1164.all;
--Entradas y salidas--
entity Decodificador_7_Display is
port
	(
		BCD:	in	bit_vector (0 to 3);
		Segmentos:	out	bit_vector (0 to 6)
	);
end Decodificador_7_Display;
--Funcionamiento--
architecture Decodificador_7_Display of Decodificador_7_Display is
begin
process (BCD) begin
	Case BCD is
		When "0000" => Segmentos <= "0000001";
		When "0001" => Segmentos <= "1001111";
		When "0010" => Segmentos <= "0010010";
		When "0011" => Segmentos <= "0000110";
		When "0100" => Segmentos <= "1001100";
		When "0101" => Segmentos <= "0100100";
		When "0110" => Segmentos <= "0100000";
		When "0111" => Segmentos <= "0001110";
		When "1000" => Segmentos <= "0000000";
		When "1001" => Segmentos <= "0000100";
		When others => Segmentos <= "1111111";
	end case;
end process;
end Decodificador_7_Display;
