# ULongLongMult

- ea: `0x18002dbd0`
- end: `0x18002dbf8`
- name: `ULongLongMult`
- size: `40`
- prototype: `HRESULT __stdcall(ULONGLONG ullMultiplicand, ULONGLONG ullMultiplier, ULONGLONG *pullResult)`
- caller_count: `11`
- callee_count: `1`
- tags: ``

## callers

- `0x180001024`
- `0x18000129c`
- `0x1800110d0`
- `0x180028980`
- `0x18002af00`
- `0x18002c5c4`
- `0x18002c8f8`
- `0x1800309d0`
- `0x1800314f0`
- `0x180039770`
- `0x18003fd44`

## callees

- `0x18002dbd0`

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
0x18002dbd0  mov     rax, rdx
0x18002dbd3  mov     [rsp+arg_18], 0
0x18002dbdc  mul     rcx
0x18002dbdf  mov     rcx, rax
0x18002dbe2  test    rdx, rdx
0x18002dbe5  jnz     short loc_18002DBED
0x18002dbe7  xor     eax, eax
0x18002dbe9  mov     [r8], rcx
0x18002dbec  retn
0x18002dbed  mov     eax, 80070216h
0x18002dbf2  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18002dbf6  jmp     short loc_18002DBE9
```
