# ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator=(ushort const *)

- ea: `0x180003358`
- end: `0x180003485`
- name: `??4?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@PEBG@Z`
- size: `301`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800048cc`

## callees

- `0x180003358`
- `0x1800041f8`
- `0x18000ae24`
- `0x180014010`

## import_xrefs

- `msvcrt!memmove_s` at `0x1800033d2`
- `msvcrt!memmove_s` at `0x1800033d2`
- `msvcrt!memcpy_s` at `0x1800033e3`
- `msvcrt!memcpy_s` at `0x1800033e3`

## pseudocode

```c
char **__fastcall ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(
        char **a1,
        char *a2)
{
  __int64 v4; // rbx
  unsigned __int64 v5; // rbp
  unsigned __int64 v6; // r15
  char *v7; // rcx
  rsize_t v8; // r9
  char *v9; // rax
  char *v10; // rdx
  __int64 v11; // rbx

  if ( a2 )
  {
    v4 = -1;
    do
      ++v4;
    while ( *(_WORD *)&a2[2 * v4] );
    if ( (_DWORD)v4 )
    {
      v5 = (a2 - *a1) >> 1;
      v6 = *((unsigned int *)*a1 - 4);
      if ( (int)((*((_DWORD *)*a1 - 3) - v4) | (1 - *((_DWORD *)*a1 - 2))) < 0 )
        ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(a1, (unsigned int)v4);
      v7 = *a1;
      v8 = 2LL * (int)v4;
      if ( v5 > v6 )
        memcpy_s(v7, v8, a2, v8);
      else
        memmove_s(v7, v8, &v7[2 * v5], v8);
      if ( (int)v4 >= 0 && (int)v4 <= *((_DWORD *)*a1 - 3) )
      {
        *((_DWORD *)*a1 - 4) = v4;
        *(_WORD *)&(*a1)[2 * (int)v4] = 0;
        return a1;
      }
LABEL_21:
      ATL::AtlThrowImpl(-2147024809);
    }
  }
  v9 = *a1;
  v10 = *a1 - 24;
  if ( !*((_DWORD *)v10 + 2) )
    return a1;
  if ( *((int *)v10 + 4) < 0 )
  {
    if ( *((int *)v9 - 3) >= 0 )
    {
      *((_DWORD *)v9 - 4) = 0;
      *(_WORD *)*a1 = 0;
      return a1;
    }
    goto LABEL_21;
  }
  v11 = *(_QWORD *)v10;
  if ( _InterlockedDecrement((volatile signed __int32 *)v10 + 4) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v10 + 8LL))(*(_QWORD *)v10);
  *a1 = (char *)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v11 + 24LL))(v11) + 24);
  return a1;
}

```

## disassembly

```asm
0x180003358  push    rbx
0x18000335a  push    rbp
0x18000335b  push    rsi
0x18000335c  push    rdi
0x18000335d  push    r12
0x18000335f  push    r14
0x180003361  push    r15
0x180003363  sub     rsp, 20h
0x180003367  mov     rdi, rcx
0x18000336a  xor     r12d, r12d
0x18000336d  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180003371  mov     r14, rdx
0x180003374  test    rdx, rdx
0x180003377  jz      loc_18000340C
0x18000337d  mov     rbx, rcx
0x180003380  inc     rbx
0x180003383  cmp     [rdx+rbx*2], r12w
0x180003388  jnz     short loc_180003380
0x18000338a  test    ebx, ebx
0x18000338c  jz      short loc_18000340C
0x18000338e  mov     rax, [rdi]
0x180003391  mov     rbp, r14
0x180003394  sub     rbp, rax
0x180003397  mov     ecx, 1
0x18000339c  sar     rbp, 1
0x18000339f  sub     ecx, [rax-8]
0x1800033a2  mov     r15d, [rax-10h]
0x1800033a6  mov     eax, [rax-0Ch]
0x1800033a9  sub     eax, ebx
0x1800033ab  or      ecx, eax
0x1800033ad  jge     short loc_1800033B9
0x1800033af  mov     edx, ebx
0x1800033b1  mov     rcx, rdi
0x1800033b4  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x1800033b9  mov     rcx, [rdi]; Destination
0x1800033bc  movsxd  rax, ebx
0x1800033bf  lea     rsi, [rax+rax]
0x1800033c3  mov     r9, rsi; SourceSize
0x1800033c6  mov     rdx, rsi; DestinationSize
0x1800033c9  cmp     rbp, r15
0x1800033cc  ja      short loc_1800033E0
0x1800033ce  lea     r8, [rcx+rbp*2]; Source
0x1800033d2  call    cs:__imp_memmove_s
0x1800033d9  nop     dword ptr [rax+rax+00h]
0x1800033de  jmp     short loc_1800033EF
0x1800033e0  mov     r8, r14; Source
0x1800033e3  call    cs:__imp_memcpy_s
0x1800033ea  nop     dword ptr [rax+rax+00h]
0x1800033ef  test    ebx, ebx
0x1800033f1  js      loc_18000347A
0x1800033f7  mov     rax, [rdi]
0x1800033fa  cmp     ebx, [rax-0Ch]
0x1800033fd  jg      short loc_18000347A
0x1800033ff  mov     [rax-10h], ebx
0x180003402  mov     rcx, [rdi]
0x180003405  mov     [rsi+rcx], r12w
0x18000340a  jmp     short loc_180003467
0x18000340c  mov     rax, [rdi]
0x18000340f  lea     rdx, [rax-18h]
0x180003413  cmp     [rdx+8], r12d
0x180003417  jz      short loc_180003467
0x180003419  cmp     [rdx+10h], r12d
0x18000341d  jge     short loc_180003432
0x18000341f  cmp     [rax-0Ch], r12d
0x180003423  jl      short loc_18000347A
0x180003425  mov     [rax-10h], r12d
0x180003429  mov     rcx, [rdi]
0x18000342c  mov     [rcx], r12w
0x180003430  jmp     short loc_180003467
0x180003432  mov     rbx, [rdx]
0x180003435  mov     eax, ecx
0x180003437  lock xadd [rdx+10h], eax
0x18000343c  add     eax, ecx
0x18000343e  test    eax, eax
0x180003440  jg      short loc_180003451
0x180003442  mov     rcx, [rdx]
0x180003445  mov     rax, [rcx]
0x180003448  mov     rax, [rax+8]
0x18000344c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003451  mov     rax, [rbx]
0x180003454  mov     rcx, rbx
0x180003457  mov     rax, [rax+18h]
0x18000345b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003460  add     rax, 18h
0x180003464  mov     [rdi], rax
0x180003467  mov     rax, rdi
0x18000346a  add     rsp, 20h
0x18000346e  pop     r15
0x180003470  pop     r14
0x180003472  pop     r12
0x180003474  pop     rdi
0x180003475  pop     rsi
0x180003476  pop     rbp
0x180003477  pop     rbx
0x180003478  retn
0x18000347a  mov     ecx, 80070057h; int
0x18000347f  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
