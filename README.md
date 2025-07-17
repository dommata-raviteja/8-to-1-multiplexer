# 8-to-1-multiplexer
Verilog  HDL code and  Testbench For 8:1 Multiplexer
// 8:1 Multiplexer Module
module mux8to1 (
    input  wire [7:0] data_in,    // 8-bit input data lines
    input  wire [2:0] sel,        // 3-bit select line
    output wire       out        // Output line
);

    // Select the output based on select lines
    assign out = data_in[sel];

endmodule

`timescale 1ns / 1ps

module tb_mux8to1;

    reg [7:0] in;      // 8 input lines
    reg [2:0] sel;     // 3-bit select line
    wire out;          // Output from MUX

    // Instantiate the DUT (Device Under Test)
    mux8to1 uut (
        .in(in),
        .sel(sel),
        .out(out)
    );

    initial begin
        $display("Time\tSel\tInput\t\tOut");
        $monitor("%0dns\t%0d\t%b\t%b", $time, sel, in, out);

        // Initialize input
        in = 8'b00000000;

        // Apply different inputs and select lines
        in = 8'b10101010;  // Alternating 1s and 0s

        // Test all select combinations
        sel = 3'b000; #10;
        sel = 3'b001; #10;
        sel = 3'b010; #10;
        sel = 3'b011; #10;
        sel = 3'b100; #10;
        sel = 3'b101; #10;
        sel = 3'b110; #10;
        sel = 3'b111; #10;

        $finish;
    end

endmodule

