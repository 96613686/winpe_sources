# ATL::CAtlArray<IdentityProperty,ATL::CElementTraits<IdentityProperty>>::GrowBuffer(unsigned __int64)

- ea: `0x180012964`
- end: `0x180012a2c`
- name: `?GrowBuffer@?$CAtlArray@UIdentityProperty@@V?$CElementTraits@UIdentityProperty@@@ATL@@@ATL@@AEAA_N_K@Z`
- size: `200`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800128b8`
- `0x18003c650`

## callees

- `0x180012964`
- `0x180015788`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!memmove_s` at `0x1800129fd`
- `api-ms-win-crt-string-l1-1-0!memmove_s` at `0x1800129fd`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x18001299f`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x1800129da`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x18001299f`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x1800129da`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180012a0d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180012a0d`

## pseudocode

```c
char __fastcall ATL::CAtlArray<IdentityProperty,ATL::CElementTraits<IdentityProperty>>::GrowBuffer(
        __int64 a1,
        size_t a2)
{
  unsigned __int64 v4; // rdx
  size_t v5; // rcx
  void *v6; // rax
  void *v7; // rax
  void *v8; // rsi
  errno_t v10; // eax

  v4 = *(_QWORD *)(a1 + 16);
  if ( a2 > v4 )
  {
    v5 = *(int *)(a1 + 24);
    if ( *(_QWORD *)a1 )
    {
      if ( !v5 )
      {
        v5 = v4 >> 1;
        if ( a2 - v4 > v4 >> 1 )
          v5 = a2 - v4;
      }
      if ( a2 < v4 + v5 )
        a2 = v4 + v5;
      v7 = calloc(a2, 0x10u);
      v8 = v7;
      if ( !v7 )
        return 0;
      v10 = memmove_s(v7, 16LL * *(_QWORD *)(a1 + 8), *(const void *const *)a1, 16LL * *(_QWORD *)(a1 + 8));
      ATL::AtlCrtErrorCheck(v10);
      free(*(void **)a1);
      *(_QWORD *)a1 = v8;
    }
    else
    {
      if ( v5 > a2 )
        a2 = v5;
      v6 = calloc(a2, 0x10u);
      *(_QWORD *)a1 = v6;
      if ( !v6 )
        return 0;
    }
    *(_QWORD *)(a1 + 16) = a2;
  }
  return 1;
}

```

## disassembly

```asm
0x180012964  mov     [rsp+arg_0], rbx
0x180012969  mov     [rsp+arg_8], rsi
0x18001296e  push    rdi
0x18001296f  sub     rsp, 20h
0x180012973  mov     rdi, rdx
0x180012976  mov     rbx, rcx
0x180012979  mov     rdx, [rcx+10h]
0x18001297d  cmp     rdi, rdx
0x180012980  jbe     loc_180012A1A
0x180012986  cmp     qword ptr [rbx], 0
0x18001298a  movsxd  rcx, dword ptr [rcx+18h]
0x18001298e  jnz     short loc_1800129AF
0x180012990  cmp     rcx, rdi
0x180012993  mov     edx, 10h; Size
0x180012998  cmova   rdi, rcx
0x18001299c  mov     rcx, rdi; Count
0x18001299f  call    cs:__imp_calloc
0x1800129a5  mov     [rbx], rax
0x1800129a8  test    rax, rax
0x1800129ab  jnz     short loc_180012A16
0x1800129ad  jmp     short loc_1800129E8
0x1800129af  test    rcx, rcx
0x1800129b2  jnz     short loc_1800129C7
0x1800129b4  mov     rcx, rdx
0x1800129b7  mov     rax, rdi
0x1800129ba  shr     rcx, 1
0x1800129bd  sub     rax, rdx
0x1800129c0  cmp     rax, rcx
0x1800129c3  cmova   rcx, rax
0x1800129c7  lea     rax, [rdx+rcx]
0x1800129cb  mov     edx, 10h; Size
0x1800129d0  cmp     rdi, rax
0x1800129d3  cmovb   rdi, rax
0x1800129d7  mov     rcx, rdi; Count
0x1800129da  call    cs:__imp_calloc
0x1800129e0  mov     rsi, rax
0x1800129e3  test    rax, rax
0x1800129e6  jnz     short loc_1800129EC
0x1800129e8  xor     al, al
0x1800129ea  jmp     short loc_180012A1C
0x1800129ec  mov     rdx, [rbx+8]
0x1800129f0  mov     rcx, rsi; Destination
0x1800129f3  mov     r8, [rbx]; Source
0x1800129f6  shl     rdx, 4; DestinationSize
0x1800129fa  mov     r9, rdx; SourceSize
0x1800129fd  call    cs:__imp_memmove_s
0x180012a03  mov     ecx, eax; int
0x180012a05  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180012a0a  mov     rcx, [rbx]; Block
0x180012a0d  call    cs:__imp_free
0x180012a13  mov     [rbx], rsi
0x180012a16  mov     [rbx+10h], rdi
0x180012a1a  mov     al, 1
0x180012a1c  mov     rbx, [rsp+28h+arg_0]
0x180012a21  mov     rsi, [rsp+28h+arg_8]
0x180012a26  add     rsp, 20h
0x180012a2a  pop     rdi
0x180012a2b  retn
```
