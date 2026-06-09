# ATL::CAtlArray<IdentityToken,ATL::CElementTraits<IdentityToken>>::GrowBuffer(unsigned __int64)

- ea: `0x180012340`
- end: `0x18001240c`
- name: `?GrowBuffer@?$CAtlArray@UIdentityToken@@V?$CElementTraits@UIdentityToken@@@ATL@@@ATL@@AEAA_N_K@Z`
- size: `204`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180012288`
- `0x18003c6c0`

## callees

- `0x180012340`
- `0x180015788`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!memmove_s` at `0x1800123dd`
- `api-ms-win-crt-string-l1-1-0!memmove_s` at `0x1800123dd`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x18001237b`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x1800123b6`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x18001237b`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x1800123b6`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800123ed`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800123ed`

## pseudocode

```c
char __fastcall ATL::CAtlArray<IdentityToken,ATL::CElementTraits<IdentityToken>>::GrowBuffer(__int64 a1, size_t a2)
{
  unsigned __int64 v4; // rdx
  size_t v5; // rcx
  void *v6; // rax
  void *v7; // rsi
  errno_t v9; // eax

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
      v7 = calloc(a2, 0x48u);
      if ( !v7 )
        return 0;
      v9 = memmove_s(v7, 72LL * *(_QWORD *)(a1 + 8), *(const void *const *)a1, 72LL * *(_QWORD *)(a1 + 8));
      ATL::AtlCrtErrorCheck(v9);
      free(*(void **)a1);
      *(_QWORD *)a1 = v7;
    }
    else
    {
      if ( v5 > a2 )
        a2 = v5;
      v6 = calloc(a2, 0x48u);
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
0x180012340  mov     [rsp+arg_0], rbx
0x180012345  mov     [rsp+arg_8], rsi
0x18001234a  push    rdi
0x18001234b  sub     rsp, 20h
0x18001234f  mov     rdi, rdx
0x180012352  mov     rbx, rcx
0x180012355  mov     rdx, [rcx+10h]
0x180012359  cmp     rdi, rdx
0x18001235c  jbe     loc_1800123FA
0x180012362  cmp     qword ptr [rbx], 0
0x180012366  movsxd  rcx, dword ptr [rcx+18h]
0x18001236a  jnz     short loc_18001238B
0x18001236c  cmp     rcx, rdi
0x18001236f  mov     edx, 48h ; 'H'; Size
0x180012374  cmova   rdi, rcx
0x180012378  mov     rcx, rdi; Count
0x18001237b  call    cs:__imp_calloc
0x180012381  mov     [rbx], rax
0x180012384  test    rax, rax
0x180012387  jnz     short loc_1800123F6
0x180012389  jmp     short loc_1800123C4
0x18001238b  test    rcx, rcx
0x18001238e  jnz     short loc_1800123A3
0x180012390  mov     rcx, rdx
0x180012393  mov     rax, rdi
0x180012396  shr     rcx, 1
0x180012399  sub     rax, rdx
0x18001239c  cmp     rax, rcx
0x18001239f  cmova   rcx, rax
0x1800123a3  lea     rax, [rdx+rcx]
0x1800123a7  mov     edx, 48h ; 'H'; Size
0x1800123ac  cmp     rdi, rax
0x1800123af  cmovb   rdi, rax
0x1800123b3  mov     rcx, rdi; Count
0x1800123b6  call    cs:__imp_calloc
0x1800123bc  mov     rsi, rax
0x1800123bf  test    rax, rax
0x1800123c2  jnz     short loc_1800123C8
0x1800123c4  xor     al, al
0x1800123c6  jmp     short loc_1800123FC
0x1800123c8  mov     rax, [rbx+8]
0x1800123cc  mov     rcx, rsi; Destination
0x1800123cf  mov     r8, [rbx]; Source
0x1800123d2  lea     rdx, [rax+rax*8]
0x1800123d6  shl     rdx, 3; DestinationSize
0x1800123da  mov     r9, rdx; SourceSize
0x1800123dd  call    cs:__imp_memmove_s
0x1800123e3  mov     ecx, eax; int
0x1800123e5  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x1800123ea  mov     rcx, [rbx]; Block
0x1800123ed  call    cs:__imp_free
0x1800123f3  mov     [rbx], rsi
0x1800123f6  mov     [rbx+10h], rdi
0x1800123fa  mov     al, 1
0x1800123fc  mov     rbx, [rsp+28h+arg_0]
0x180012401  mov     rsi, [rsp+28h+arg_8]
0x180012406  add     rsp, 20h
0x18001240a  pop     rdi
0x18001240b  retn
```
