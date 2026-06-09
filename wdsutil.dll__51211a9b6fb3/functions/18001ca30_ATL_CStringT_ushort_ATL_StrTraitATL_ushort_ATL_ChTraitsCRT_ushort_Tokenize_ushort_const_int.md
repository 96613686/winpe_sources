# ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Tokenize(ushort const *,int &)

- ea: `0x18001ca30`
- end: `0x18001cbc9`
- name: `?Tokenize@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBA?AV12@PEBGAEAH@Z`
- size: `409`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x18001486c`
- `0x18001e334`

## callees

- `0x1800085b8`
- `0x1800143b8`
- `0x1800185cc`
- `0x18001ca30`
- `0x180034010`

## import_xrefs

- `msvcrt!wcsspn` at `0x18001ca75`
- `msvcrt!wcsspn` at `0x18001ca75`
- `msvcrt!wcscspn` at `0x18001ca9b`
- `msvcrt!wcscspn` at `0x18001ca9b`

## pseudocode

```c
_QWORD *__fastcall ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Tokenize(
        __int64 *a1,
        _QWORD *a2,
        __int64 a3,
        int *a4)
{
  unsigned __int64 v7; // rsi
  unsigned __int64 v8; // rbp
  int v9; // r15d
  const wchar_t *v10; // rcx
  int v11; // eax
  int v12; // edx
  int v13; // ebx
  __int64 v14; // rdx
  __int64 v15; // r8
  int v16; // eax
  unsigned int v17; // esi
  __int64 v18; // rax
  __int64 v19; // rcx
  __int64 v20; // rax
  __int64 v22; // rcx
  __int64 v23; // rcx

  if ( *a4 < 0 )
    goto LABEL_27;
  v7 = *a1 + 2LL * *a4;
  v8 = *a1 + 2LL * *(int *)(*a1 - 16);
  if ( v7 >= v8
    || (v9 = wcsspn((const wchar_t *)(*a1 + 2LL * *a4), L";"),
        v10 = (const wchar_t *)(v7 + 2LL * v9),
        (unsigned __int64)v10 >= v8) )
  {
    *a4 = -1;
    v22 = *(_QWORD *)(*a1 - 24);
    if ( !v22 || (v23 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v22 + 32LL))(v22)) == 0 )
    {
      v23 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[4])(&ATL::g_strmgr);
      if ( !v23 )
        ATL::AtlThrowImpl(-2147467259);
    }
    v18 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v23 + 24LL))(v23);
    goto LABEL_16;
  }
  v11 = wcscspn(v10, L";");
  v12 = v9 + *a4;
  *a4 = v12 + v11 + 1;
  v13 = 0;
  if ( v12 >= 0 )
    v13 = v12;
  v14 = 0;
  if ( v11 >= 0 )
    v14 = (unsigned int)v11;
  if ( 0x7FFFFFFF - v13 < (int)v14 )
LABEL_27:
    ATL::AtlThrowImpl(-2147024809);
  v15 = *a1;
  v16 = *(_DWORD *)(*a1 - 16);
  if ( v13 + (int)v14 > v16 )
    v14 = (unsigned int)(v16 - v13);
  v17 = 0;
  if ( v13 <= v16 )
    v17 = v14;
  if ( !v13 && v17 == v16 )
  {
    v18 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v15 - 24);
LABEL_16:
    *a2 = v18 + 24;
    return a2;
  }
  v19 = *(_QWORD *)(v15 - 24);
  if ( !v19 || (v20 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v19 + 32LL))(v19, v14)) == 0 )
    v20 = ((__int64 (__fastcall *)(void ***, __int64))ATL::g_strmgr[4])(&ATL::g_strmgr, v14);
  ATL::CSimpleStringT<unsigned short,0>::CSimpleStringT<unsigned short,0>(a2, *a1 + 2LL * v13, v17, v20);
  return a2;
}

```

## disassembly

```asm
0x18001ca30  push    rbx
0x18001ca32  push    rbp
0x18001ca33  push    rsi
0x18001ca34  push    rdi
0x18001ca35  push    r14
0x18001ca37  push    r15
0x18001ca39  sub     rsp, 28h
0x18001ca3d  cmp     dword ptr [r9], 0
0x18001ca41  mov     rbx, r9
0x18001ca44  mov     rdi, rdx
0x18001ca47  mov     r14, rcx
0x18001ca4a  jl      loc_18001CBBE
0x18001ca50  mov     r8, [rcx]
0x18001ca53  movsxd  rax, dword ptr [r9]
0x18001ca56  lea     rsi, [r8+rax*2]
0x18001ca5a  movsxd  rax, dword ptr [r8-10h]
0x18001ca5e  lea     rbp, [r8+rax*2]
0x18001ca62  cmp     rsi, rbp
0x18001ca65  jnb     loc_18001CB5D
0x18001ca6b  lea     rdx, Control; ";"
0x18001ca72  mov     rcx, rsi; String
0x18001ca75  call    cs:__imp_wcsspn
0x18001ca7c  nop     dword ptr [rax+rax+00h]
0x18001ca81  movsxd  rcx, eax
0x18001ca84  mov     r15, rax
0x18001ca87  lea     rcx, [rsi+rcx*2]; String
0x18001ca8b  cmp     rcx, rbp
0x18001ca8e  jnb     loc_18001CB5D
0x18001ca94  lea     rdx, Control; ";"
0x18001ca9b  call    cs:__imp_wcscspn
0x18001caa2  nop     dword ptr [rax+rax+00h]
0x18001caa7  mov     edx, [rbx]
0x18001caa9  add     edx, r15d
0x18001caac  lea     ecx, [rax+1]
0x18001caaf  add     ecx, edx
0x18001cab1  mov     [rbx], ecx
0x18001cab3  xor     ebx, ebx
0x18001cab5  test    edx, edx
0x18001cab7  cmovns  ebx, edx
0x18001caba  xor     edx, edx
0x18001cabc  test    eax, eax
0x18001cabe  cmovns  edx, eax
0x18001cac1  mov     eax, 7FFFFFFFh
0x18001cac6  sub     eax, ebx
0x18001cac8  cmp     eax, edx
0x18001caca  jl      loc_18001CBBE
0x18001cad0  mov     r8, [r14]
0x18001cad3  lea     ecx, [rbx+rdx]
0x18001cad6  mov     eax, [r8-10h]
0x18001cada  cmp     ecx, eax
0x18001cadc  jle     short loc_18001CAE2
0x18001cade  mov     edx, eax
0x18001cae0  sub     edx, ebx
0x18001cae2  xor     esi, esi
0x18001cae4  cmp     ebx, eax
0x18001cae6  cmovle  esi, edx
0x18001cae9  test    ebx, ebx
0x18001caeb  jnz     short loc_18001CB03
0x18001caed  cmp     esi, eax
0x18001caef  jnz     short loc_18001CB03
0x18001caf1  lea     rcx, [r8-18h]
0x18001caf5  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x18001cafa  add     rax, 18h
0x18001cafe  mov     [rdi], rax
0x18001cb01  jmp     short loc_18001CB4C
0x18001cb03  mov     rcx, [r8-18h]
0x18001cb07  test    rcx, rcx
0x18001cb0a  jz      short loc_18001CB1D
0x18001cb0c  mov     rax, [rcx]
0x18001cb0f  mov     rax, [rax+20h]
0x18001cb13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cb18  test    rax, rax
0x18001cb1b  jnz     short loc_18001CB34
0x18001cb1d  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18001cb24  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18001cb2b  mov     rax, [rax+20h]
0x18001cb2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cb34  mov     rcx, [r14]
0x18001cb37  mov     r9, rax
0x18001cb3a  movsxd  rdx, ebx
0x18001cb3d  mov     r8d, esi
0x18001cb40  lea     rdx, [rcx+rdx*2]
0x18001cb44  mov     rcx, rdi
0x18001cb47  call    ??0?$CSimpleStringT@G$0A@@ATL@@QEAA@PEBGHPEAUIAtlStringMgr@1@@Z; ATL::CSimpleStringT<ushort,0>::CSimpleStringT<ushort,0>(ushort const *,int,ATL::IAtlStringMgr *)
0x18001cb4c  mov     rax, rdi
0x18001cb4f  add     rsp, 28h
0x18001cb53  pop     r15
0x18001cb55  pop     r14
0x18001cb57  pop     rdi
0x18001cb58  pop     rsi
0x18001cb59  pop     rbp
0x18001cb5a  pop     rbx
0x18001cb5b  retn
0x18001cb5d  mov     dword ptr [rbx], 0FFFFFFFFh
0x18001cb63  mov     rax, [r14]
0x18001cb66  mov     rcx, [rax-18h]
0x18001cb6a  test    rcx, rcx
0x18001cb6d  jz      short loc_18001CB83
0x18001cb6f  mov     rax, [rcx]
0x18001cb72  mov     rax, [rax+20h]
0x18001cb76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cb7b  mov     rcx, rax
0x18001cb7e  test    rax, rax
0x18001cb81  jnz     short loc_18001CBA2
0x18001cb83  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18001cb8a  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18001cb91  mov     rax, [rax+20h]
0x18001cb95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cb9a  mov     rcx, rax
0x18001cb9d  test    rax, rax
0x18001cba0  jz      short loc_18001CBB3
0x18001cba2  mov     rax, [rcx]
0x18001cba5  mov     rax, [rax+18h]
0x18001cba9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cbae  jmp     loc_18001CAFA
0x18001cbb3  mov     ecx, 80004005h; int
0x18001cbb8  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18001cbbe  mov     ecx, 80070057h; int
0x18001cbc3  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
