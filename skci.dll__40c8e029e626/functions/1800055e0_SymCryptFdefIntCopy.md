# SymCryptFdefIntCopy

- ea: `0x1800055e0`
- end: `0x180005607`
- name: `SymCryptFdefIntCopy`
- size: `39`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x180024be8`
- `0x180025888`
- `0x180029fa0`
- `0x18002a4b0`
- `0x18002b020`

## callees

- `0x1800055e0`
- `0x18003392c`

## pseudocode

```c
void *__fastcall SymCryptFdefIntCopy(_DWORD *a1, _DWORD *a2)
{
  void *result; // rax

  result = a2;
  if ( a1 != a2 )
    return memcpy_0(a2 + 8, a1 + 8, (unsigned int)(a2[1] << 6));
  return result;
}

```

## disassembly

```asm
0x1800055e0  sub     rsp, 28h
0x1800055e4  mov     rax, rdx
0x1800055e7  cmp     rcx, rdx
0x1800055ea  jz      short loc_180005601
0x1800055ec  mov     r8d, [rdx+4]
0x1800055f0  lea     rdx, [rcx+20h]; Src
0x1800055f4  shl     r8d, 6; MaxCount
0x1800055f8  lea     rcx, [rax+20h]; void *
0x1800055fc  call    memcpy_0
0x180005601  add     rsp, 28h
0x180005605  retn
```
