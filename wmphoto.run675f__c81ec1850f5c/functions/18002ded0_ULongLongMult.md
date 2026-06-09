# ULongLongMult

- ea: `0x18002ded0`
- end: `0x18002def9`
- name: `ULongLongMult`
- size: `41`
- prototype: `HRESULT __stdcall(ULONGLONG ullMultiplicand, ULONGLONG ullMultiplier, ULONGLONG *pullResult)`
- caller_count: `11`
- callee_count: `1`
- tags: ``

## callers

- `0x180001024`
- `0x1800012bc`
- `0x18001128c`
- `0x180028940`
- `0x18002b180`
- `0x18002c864`
- `0x18002cbb0`
- `0x180030e10`
- `0x180031850`
- `0x180039e90`
- `0x18004051c`

## callees

- `0x18002ded0`

## pseudocode

```c
HRESULT __stdcall ULongLongMult(ULONGLONG ullMultiplicand, ULONGLONG ullMultiplier, ULONGLONG *pullResult)
{
  ULONGLONG v4; // rcx
  HRESULT result; // eax

  v4 = ullMultiplicand * ullMultiplier;
  if ( is_mul_ok(ullMultiplicand, ullMultiplier) )
  {
    result = 0;
  }
  else
  {
    result = -2147024362;
    v4 = -1;
  }
  *pullResult = v4;
  return result;
}

```

## disassembly

```asm
0x18002ded0  mov     rax, rdx
0x18002ded3  mov     [rsp+arg_18], 0
0x18002dedc  mul     rcx
0x18002dedf  mov     rcx, rax
0x18002dee2  test    rdx, rdx
0x18002dee5  jnz     short loc_18002DEEE
0x18002dee7  xor     eax, eax
0x18002dee9  mov     [r8], rcx
0x18002deec  retn
0x18002deee  mov     eax, 80070216h
0x18002def3  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18002def7  jmp     short loc_18002DEE9
```
