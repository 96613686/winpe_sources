# _RNvNtNtCs9MWeMO1rkJG_4core9panicking11panic_const23panic_const_div_by_zero

- ea: `0x140018780`
- end: `0x140018799`
- name: `_RNvNtNtCs9MWeMO1rkJG_4core9panicking11panic_const23panic_const_div_by_zero`
- size: `25`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14000fe20`
- `0x140011120`

## callees

- `0x140018650`

## string_xrefs

- `0x140018787`: `attempt to divide by zerouser-provided comparison function does not correctly implement a total orderD:\os\tools\Rust\vpack\rust.tools.es\lib\rustlib\src\rust\library\core\src\slice\sort\shared\smallsort.rs`

## pseudocode

```c
void __fastcall __noreturn RNvNtNtCs9MWeMO1rkJG_4core9panicking11panic_const23panic_const_div_by_zero(__int64 a1)
{
  RNvNtCs9MWeMO1rkJG_4core9panicking9panic_fmt(
    "attempt to divide by zerouser-provided comparison function does not correctly implement a total orderD:\\os\\tools\\"
    "Rust\\vpack\\rust.tools.es\\lib\\rustlib\\src\\rust\\library\\core\\src\\slice\\sort\\shared\\smallsort.rs",
    51,
    a1);
}

```

## disassembly

```asm
0x140018780  sub     rsp, 28h
0x140018784  mov     r8, rcx
0x140018787  lea     rcx, aAttemptToDivid; "attempt to divide by zerouser-provided "...
0x14001878e  mov     edx, 33h ; '3'
0x140018793  call    _RNvNtCs9MWeMO1rkJG_4core9panicking9panic_fmt
```
