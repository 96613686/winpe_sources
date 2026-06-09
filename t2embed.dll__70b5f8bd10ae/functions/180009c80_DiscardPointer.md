# DiscardPointer

- ea: `0x180009c80`
- end: `0x180009d36`
- name: `DiscardPointer`
- size: `182`
- prototype: ``
- caller_count: `20`
- callee_count: `2`
- tags: ``

## callers

- `0x180001f60`
- `0x1800059a0`
- `0x180006548`
- `0x180006a2c`
- `0x1800088a0`
- `0x180009a50`
- `0x180009d40`
- `0x18000a650`
- `0x18000b8f0`
- `0x18000db44`
- `0x18000dca8`
- `0x18000ddd4`
- `0x18000de70`
- `0x18000e12c`
- `0x18000e2d4`
- `0x18000e5e4`
- `0x18000e734`
- `0x18000eb94`
- `0x18001a414`
- `0x18001ce2c`

## callees

- `0x180009c80`
- `0x18002b010`

## import_xrefs

- `msvcrt!longjmp` at `0x180009d2f`
- `msvcrt!longjmp` at `0x180009d2f`

## pseudocode

```c
void __fastcall DiscardPointer(__int64 *a1, __int64 a2, int a3)
{
  int v4; // ebx
  __int64 v5; // rbp
  __int64 v6; // rsi
  __int64 v7; // rax

  if ( a2 )
  {
    v4 = *((_DWORD *)a1 + 3);
    v5 = *a1;
    do
    {
      if ( --v4 < 0 )
        longjmp((_JBTYPE *)a1 + 3, 3358);
      v6 = v5 + 16LL * v4;
    }
    while ( *(_QWORD *)v6 != a2 );
    if ( a3 )
      ((void (__fastcall *)(__int64))a1[5])(a2);
    v7 = *((int *)a1 + 3);
    if ( (int)v7 + ~v4 > 0 )
    {
      *(_QWORD *)v6 = *(_QWORD *)(v5 + 16 * v7 - 16);
      *(_DWORD *)(v6 + 8) = *(_DWORD *)(v5 + 16LL * *((int *)a1 + 3) - 8);
      *(_QWORD *)(v5 + 16LL * *((int *)a1 + 3) - 16) = 0;
      *(_DWORD *)(v5 + 16LL * *((int *)a1 + 3) - 8) = 0;
    }
    else
    {
      *(_QWORD *)v6 = 0;
      *(_DWORD *)(v6 + 8) = 0;
    }
    --*((_DWORD *)a1 + 3);
  }
}

```

## disassembly

```asm
0x180009c80  test    rdx, rdx
0x180009c83  jz      short locret_180009CF3
0x180009c85  push    rdi
0x180009c86  sub     rsp, 20h
0x180009c8a  mov     [rsp+28h+arg_0], rbx
0x180009c8f  mov     rdi, rcx
0x180009c92  mov     ebx, [rcx+0Ch]
0x180009c95  mov     [rsp+28h+arg_8], rbp
0x180009c9a  mov     rbp, [rcx]
0x180009c9d  mov     [rsp+28h+arg_10], rsi
0x180009ca2  dec     ebx
0x180009ca4  test    ebx, ebx
0x180009ca6  js      short loc_180009D26
0x180009ca8  movsxd  rsi, ebx
0x180009cab  shl     rsi, 4
0x180009caf  add     rsi, rbp
0x180009cb2  cmp     [rsi], rdx
0x180009cb5  jnz     short loc_180009CA2
0x180009cb7  test    r8d, r8d
0x180009cba  jz      short loc_180009CC8
0x180009cbc  mov     rax, [rdi+28h]
0x180009cc0  mov     rcx, rdx
0x180009cc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009cc8  movsxd  rax, dword ptr [rdi+0Ch]
0x180009ccc  not     ebx
0x180009cce  add     ebx, eax
0x180009cd0  xor     ecx, ecx
0x180009cd2  test    ebx, ebx
0x180009cd4  jg      short loc_180009CF4
0x180009cd6  mov     [rsi], rcx
0x180009cd9  mov     [rsi+8], ecx
0x180009cdc  dec     dword ptr [rdi+0Ch]
0x180009cdf  mov     rsi, [rsp+28h+arg_10]
0x180009ce4  mov     rbx, [rsp+28h+arg_0]
0x180009ce9  mov     rbp, [rsp+28h+arg_8]
0x180009cee  add     rsp, 20h
0x180009cf2  pop     rdi
0x180009cf3  retn
0x180009cf4  add     rax, rax
0x180009cf7  mov     rax, [rbp+rax*8-10h]
0x180009cfc  mov     [rsi], rax
0x180009cff  movsxd  rax, dword ptr [rdi+0Ch]
0x180009d03  add     rax, rax
0x180009d06  mov     eax, [rbp+rax*8-8]
0x180009d0a  mov     [rsi+8], eax
0x180009d0d  movsxd  rax, dword ptr [rdi+0Ch]
0x180009d11  add     rax, rax
0x180009d14  mov     [rbp+rax*8-10h], rcx
0x180009d19  movsxd  rax, dword ptr [rdi+0Ch]
0x180009d1d  add     rax, rax
0x180009d20  mov     [rbp+rax*8-8], ecx
0x180009d24  jmp     short loc_180009CDC
0x180009d26  add     rcx, 30h ; '0'; Buf
0x180009d2a  mov     edx, 0D1Eh; Value
0x180009d2f  call    cs:__imp_longjmp
```
