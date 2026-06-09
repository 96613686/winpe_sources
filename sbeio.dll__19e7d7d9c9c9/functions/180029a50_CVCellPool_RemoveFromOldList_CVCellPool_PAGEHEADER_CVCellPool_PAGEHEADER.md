# CVCellPool::_RemoveFromOldList(CVCellPool::PAGEHEADER * &,CVCellPool::PAGEHEADER * &)

- ea: `0x180029a50`
- end: `0x180029a83`
- name: `?_RemoveFromOldList@CVCellPool@@AEAAXAEAPEAUPAGEHEADER@1@0@Z`
- size: `51`
- prototype: `void __fastcall(CVCellPool *__hidden this, struct CVCellPool::PAGEHEADER **, struct CVCellPool::PAGEHEADER **)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180010900`
- `0x180010a80`
- `0x1800297d8`
- `0x1800299b4`

## callees

- `0x180029a50`

## pseudocode

```c
void __fastcall CVCellPool::_RemoveFromOldList(
        CVCellPool *this,
        struct CVCellPool::PAGEHEADER **a2,
        struct CVCellPool::PAGEHEADER **a3)
{
  char *v3; // r9
  char *v4; // rcx
  __int64 v5; // rdx

  v3 = (char *)*a3;
  v4 = (char *)*a3 + 24;
  if ( *a3 == *a2 )
    *a2 = *(struct CVCellPool::PAGEHEADER **)v4;
  v5 = *((_QWORD *)v3 + 4);
  if ( v5 )
    *(_QWORD *)(v5 + 24) = *(_QWORD *)v4;
  if ( *(_QWORD *)v4 )
    *(_QWORD *)(*(_QWORD *)v4 + 32LL) = *((_QWORD *)v3 + 4);
}

```

## disassembly

```asm
0x180029a50  mov     r9, [r8]
0x180029a53  lea     rcx, [r9+18h]
0x180029a57  cmp     r9, [rdx]
0x180029a5a  jnz     short loc_180029A62
0x180029a5c  mov     rax, [rcx]
0x180029a5f  mov     [rdx], rax
0x180029a62  mov     rdx, [r9+20h]
0x180029a66  test    rdx, rdx
0x180029a69  jz      short loc_180029A72
0x180029a6b  mov     rax, [rcx]
0x180029a6e  mov     [rdx+18h], rax
0x180029a72  mov     rdx, [rcx]
0x180029a75  test    rdx, rdx
0x180029a78  jz      short locret_180029A82
0x180029a7a  mov     rax, [r9+20h]
0x180029a7e  mov     [rdx+20h], rax
0x180029a82  retn
```
