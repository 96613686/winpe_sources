# px_ipps_createTabDftDir_32f

- ea: `0x180050b60`
- end: `0x180050bc2`
- name: `px_ipps_createTabDftDir_32f`
- size: `98`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x18001c9d0`
- `0x18001cbe0`
- `0x1800556c4`

## callees

- `0x18001f910`
- `0x180050b60`

## pseudocode

```c
__int64 __fastcall px_ipps_createTabDftDir_32f(int a1, __int64 *a2, int a3)
{
  __int64 v3; // rdi
  __int64 result; // rax
  __int64 v7; // r9
  __int64 v8; // r10
  __int64 v9; // rax

  v3 = a1;
  result = px_ippsMalloc_8u((unsigned int)(8 * a1));
  v7 = 0;
  v8 = result;
  if ( result )
  {
    if ( (int)v3 > 0 )
    {
      do
      {
        v9 = *a2;
        a2 += a3 / (int)v3;
        *(_QWORD *)(v8 + 8 * v7++) = v9;
      }
      while ( v7 < v3 );
    }
    return v8;
  }
  return result;
}

```

## disassembly

```asm
0x180050b60  mov     [rsp+arg_0], rbx
0x180050b65  mov     [rsp+arg_8], rsi
0x180050b6a  push    rdi
0x180050b6b  sub     rsp, 20h
0x180050b6f  movsxd  rdi, ecx
0x180050b72  mov     esi, r8d
0x180050b75  mov     rbx, rdx
0x180050b78  mov     ecx, edi
0x180050b7a  shl     ecx, 3
0x180050b7d  call    px_ippsMalloc_8u
0x180050b82  xor     r9d, r9d
0x180050b85  mov     r10, rax
0x180050b88  test    rax, rax
0x180050b8b  jz      short loc_180050BB2
0x180050b8d  test    edi, edi
0x180050b8f  jle     short loc_180050BAF
0x180050b91  mov     eax, esi
0x180050b93  cdq
0x180050b94  idiv    edi
0x180050b96  movsxd  rcx, eax
0x180050b99  shl     rcx, 3
0x180050b9d  mov     rax, [rbx]
0x180050ba0  add     rbx, rcx
0x180050ba3  mov     [r10+r9*8], rax
0x180050ba7  inc     r9
0x180050baa  cmp     r9, rdi
0x180050bad  jl      short loc_180050B9D
0x180050baf  mov     rax, r10
0x180050bb2  mov     rbx, [rsp+28h+arg_0]
0x180050bb7  mov     rsi, [rsp+28h+arg_8]
0x180050bbc  add     rsp, 20h
0x180050bc0  pop     rdi
0x180050bc1  retn
```
