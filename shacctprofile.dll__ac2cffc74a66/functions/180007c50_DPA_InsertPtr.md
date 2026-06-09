# DPA_InsertPtr

- ea: `0x180007c50`
- end: `0x180007cdf`
- name: `DPA_InsertPtr`
- size: `143`
- prototype: `int __stdcall(HDPA hdpa, int i, void *p)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180006c70`
- `0x18000731c`

## callees

- `0x180007bb4`
- `0x180007c50`
- `0x18000973c`

## pseudocode

```c
int __stdcall DPA_InsertPtr(HDPA hdpa, int i, void *p)
{
  int v4; // edi
  unsigned int v6; // eax
  unsigned int v7; // edx
  int result; // eax

  v4 = i;
  if ( !hdpa || i < 0 )
    return -1;
  v6 = *(_DWORD *)hdpa;
  if ( i > *(_DWORD *)hdpa )
    v4 = *(_DWORD *)hdpa;
  v7 = v6 + 1;
  if ( v6 + 1 < v6 || *((int *)hdpa + 6) < 0 || v7 > *((_DWORD *)hdpa + 6) && !DPA_Grow(hdpa, v7) )
    return -1;
  if ( v4 < *(_DWORD *)hdpa )
    memmove_0(
      (void *)(*((_QWORD *)hdpa + 1) + 8LL * (v4 + 1)),
      (const void *)(*((_QWORD *)hdpa + 1) + 8LL * v4),
      8LL * (*(_DWORD *)hdpa - v4));
  result = v4;
  *(_QWORD *)(*((_QWORD *)hdpa + 1) + 8LL * v4) = p;
  ++*(_DWORD *)hdpa;
  return result;
}

```

## disassembly

```asm
0x180007c50  mov     [rsp+arg_0], rbx
0x180007c55  mov     [rsp+arg_8], rsi
0x180007c5a  push    rdi
0x180007c5b  sub     rsp, 20h
0x180007c5f  mov     rsi, r8
0x180007c62  mov     edi, edx
0x180007c64  mov     rbx, rcx
0x180007c67  test    rcx, rcx
0x180007c6a  jz      short loc_180007CCC
0x180007c6c  test    edx, edx
0x180007c6e  js      short loc_180007CCC
0x180007c70  mov     eax, [rcx]
0x180007c72  cmp     edx, eax
0x180007c74  cmovg   edi, eax
0x180007c77  lea     edx, [rax+1]; cp
0x180007c7a  cmp     edx, eax
0x180007c7c  jb      short loc_180007CCC
0x180007c7e  cmp     dword ptr [rcx+18h], 0
0x180007c82  jl      short loc_180007CCC
0x180007c84  cmp     edx, [rcx+18h]
0x180007c87  jbe     short loc_180007C92
0x180007c89  call    DPA_Grow
0x180007c8e  test    eax, eax
0x180007c90  jz      short loc_180007CCC
0x180007c92  mov     eax, [rbx]
0x180007c94  cmp     edi, eax
0x180007c96  jge     short loc_180007CBB
0x180007c98  mov     r9, [rbx+8]
0x180007c9c  sub     eax, edi
0x180007c9e  movsxd  r8, eax
0x180007ca1  movsxd  rax, edi
0x180007ca4  shl     r8, 3; Size
0x180007ca8  lea     rdx, [r9+rax*8]; Src
0x180007cac  lea     eax, [rdi+1]
0x180007caf  movsxd  rcx, eax
0x180007cb2  lea     rcx, [r9+rcx*8]; void *
0x180007cb6  call    memmove_0
0x180007cbb  mov     rcx, [rbx+8]
0x180007cbf  mov     eax, edi
0x180007cc1  movsxd  rdx, edi
0x180007cc4  mov     [rcx+rdx*8], rsi
0x180007cc8  inc     dword ptr [rbx]
0x180007cca  jmp     short loc_180007CCF
0x180007ccc  or      eax, 0FFFFFFFFh
0x180007ccf  mov     rbx, [rsp+28h+arg_0]
0x180007cd4  mov     rsi, [rsp+28h+arg_8]
0x180007cd9  add     rsp, 20h
0x180007cdd  pop     rdi
0x180007cde  retn
```
