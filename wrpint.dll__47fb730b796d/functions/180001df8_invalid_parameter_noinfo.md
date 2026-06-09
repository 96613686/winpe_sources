# _invalid_parameter_noinfo

- ea: `0x180001df8`
- end: `0x180001e19`
- name: `_invalid_parameter_noinfo`
- size: `33`
- prototype: `void __cdecl()`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x18000c518`
- `0x18000dbb4`
- `0x18000dcb0`
- `0x18000e378`
- `0x18000f4a0`
- `0x18000fe1c`
- `0x180011764`

## callees

- `0x180001e20`

## pseudocode

```c
void __cdecl __noreturn invalid_parameter_noinfo()
{
  invoke_watson(0, 0, 0, 0, 0);
}

```

## disassembly

```asm
0x180001df8  sub     rsp, 38h
0x180001dfc  xor     r9d, r9d; LineNo
0x180001dff  mov     [rsp+38h+Reserved], 0; Reserved
0x180001e08  xor     r8d, r8d; FileName
0x180001e0b  xor     edx, edx; FunctionName
0x180001e0d  xor     ecx, ecx; Expression
0x180001e0f  call    _invoke_watson
0x180001e14  add     rsp, 38h
0x180001e18  retn
```
