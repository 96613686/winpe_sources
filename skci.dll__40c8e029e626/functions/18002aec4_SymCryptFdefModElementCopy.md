# SymCryptFdefModElementCopy

- ea: `0x18002aec4`
- end: `0x18002aee2`
- name: `SymCryptFdefModElementCopy`
- size: `30`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: ``

## callers

- `0x180024be8`
- `0x180029704`
- `0x18002b020`
- `0x18002cac8`
- `0x18002cc18`
- `0x18002f7ec`
- `0x1800323d0`

## callees

- `0x18002aec4`
- `0x18003392c`

## pseudocode

```c
void *__fastcall SymCryptFdefModElementCopy(__int64 a1, const void *a2, void *a3)
{
  void *result; // rax

  result = a3;
  if ( a2 != a3 )
    return memcpy_0(a3, a2, *(unsigned int *)(a1 + 16));
  return result;
}

```

## disassembly

```asm
0x18002aec4  sub     rsp, 28h
0x18002aec8  mov     rax, r8
0x18002aecb  cmp     rdx, r8
0x18002aece  jz      short loc_18002AEDC
0x18002aed0  mov     r8d, [rcx+10h]; MaxCount
0x18002aed4  mov     rcx, rax; void *
0x18002aed7  call    memcpy_0
0x18002aedc  add     rsp, 28h
0x18002aee0  retn
```
