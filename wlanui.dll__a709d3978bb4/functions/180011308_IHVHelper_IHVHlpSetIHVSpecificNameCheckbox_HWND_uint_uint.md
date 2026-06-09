# IHVHelper::IHVHlpSetIHVSpecificNameCheckbox(HWND__ *,uint,uint)

- ea: `0x180011308`
- end: `0x18001157b`
- name: `?IHVHlpSetIHVSpecificNameCheckbox@IHVHelper@@QEAAJPEAUHWND__@@II@Z`
- size: `627`
- prototype: `int(IHVHelper *__hidden this, HWND, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x18000e31c`

## callees

- `0x180003870`
- `0x180006e30`
- `0x180008150`
- `0x18000901c`
- `0x180010d8c`
- `0x180011308`
- `0x180011584`
- `0x18001d010`

## import_xrefs

- `msvcrt!memmove_s` at `0x180011446`
- `msvcrt!memmove_s` at `0x180011446`
- `USER32!SetWindowTextW` at `0x1800114c6`
- `USER32!SetWindowTextW` at `0x1800114c6`
- `USER32!GetDlgItem` at `0x1800114b6`
- `USER32!GetDlgItem` at `0x1800114b6`
- `OLEAUT32!__imp_SysFreeString` at `0x1800114d5`
- `OLEAUT32!__imp_SysFreeString` at `0x1800114d5`

## pseudocode

```c
__int64 __fastcall IHVHelper::IHVHlpSetIHVSpecificNameCheckbox(IHVHelper *this, HWND a2)
{
  const WCHAR *v4; // rbx
  __int64 v5; // rax
  bool v6; // zf
  __int64 v7; // rdi
  int v8; // r14d
  int v9; // ebx
  int v10; // esi
  errno_t v11; // eax
  int v12; // ebx
  HWND DlgItem; // rax
  _QWORD *v14; // rdx
  __int64 v16; // [rsp+20h] [rbp-28h] BYREF
  BSTR bstrString; // [rsp+28h] [rbp-20h] BYREF
  __int64 v18; // [rsp+30h] [rbp-18h] BYREF
  LPCWSTR lpString[2]; // [rsp+38h] [rbp-10h] BYREF

  bstrString = 0;
  v18 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  v4 = (const WCHAR *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
  lpString[0] = v4;
  v5 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr);
  v6 = *((_QWORD *)this + 2) == 0;
  v7 = v5 + 24;
  v16 = v5 + 24;
  if ( v6 )
  {
    v8 = -2147418113;
    goto LABEL_25;
  }
  if ( !(unsigned int)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::LoadStringW(
                        &v18,
                        17107) )
  {
    v8 = -2147467259;
    goto LABEL_25;
  }
  v8 = (*(__int64 (__fastcall **)(_QWORD, BSTR *))(**((_QWORD **)this + 2) + 24LL))(*((_QWORD *)this + 2), &bstrString);
  if ( v8 >= 0 )
  {
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(
      &v16,
      bstrString);
    v7 = v16;
    v9 = *(_DWORD *)(v16 - 16);
    if ( v9 <= 25 )
    {
LABEL_24:
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
        lpString,
        v18,
        v7);
      DlgItem = GetDlgItem(a2, 15075);
      v4 = lpString[0];
      SetWindowTextW(DlgItem, lpString[0]);
      goto LABEL_25;
    }
    v10 = v9 - 22;
    if ( v9 - 22 >= 0 )
    {
      if ( 0x7FFFFFFF - v10 < 23 )
        goto LABEL_35;
    }
    else
    {
      v10 = 0;
    }
    if ( v10 + 23 > v9 )
      v10 = v9 - 23;
    if ( v10 <= 0 )
      goto LABEL_23;
    if ( *(int *)(v16 - 8) > 1 )
    {
      ATL::CSimpleStringT<unsigned short,0>::Fork(&v16, (unsigned int)v9);
      v7 = v16;
    }
    v11 = memmove_s(
            (void *const)(v7 + 46),
            2LL * (v9 - v10 - 22),
            (const void *const)(v7 + 2 * (v10 + 23LL)),
            2LL * (v9 - v10 - 22));
    if ( v11 )
    {
      if ( v11 == 12 )
        ATL::AtlThrowImpl(-2147024882);
      if ( v11 == 22 || v11 == 34 )
        goto LABEL_35;
      if ( v11 != 80 )
        ATL::AtlThrowImpl(-2147467259);
    }
    v12 = v9 - v10;
    if ( v12 >= 0 && v12 <= *(_DWORD *)(v7 - 12) )
    {
      *(_DWORD *)(v7 - 16) = v12;
      *(_WORD *)(v7 + 2LL * v12) = 0;
LABEL_23:
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Insert(&v16);
      v7 = v16;
      goto LABEL_24;
    }
LABEL_35:
    ATL::AtlThrowImpl(-2147024809);
  }
LABEL_25:
  if ( bstrString )
  {
    SysFreeString(bstrString);
    bstrString = 0;
  }
  if ( _InterlockedDecrement((volatile signed __int32 *)(v7 - 24 + 16)) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v7 - 24) + 8LL))(*(_QWORD *)(v7 - 24));
  if ( _InterlockedDecrement((volatile signed __int32 *)v4 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v4 - 3) + 8LL))(*((_QWORD *)v4 - 3));
  v14 = (_QWORD *)(v18 - 24);
  if ( _InterlockedDecrement((volatile signed __int32 *)(v18 - 24 + 16)) <= 0 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v14 + 8LL))(*v14);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180011308  push    rbp
0x18001130a  push    rbx
0x18001130b  push    rsi
0x18001130c  push    rdi
0x18001130d  push    r14
0x18001130f  push    r15
0x180011311  mov     rbp, rsp
0x180011314  sub     rsp, 48h
0x180011318  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18001131f  lea     rdi, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180011326  mov     rsi, rcx
0x180011329  mov     [rbp+bstrString], 0
0x180011331  mov     rcx, rdi
0x180011334  mov     r15, rdx
0x180011337  mov     rax, [rax+18h]
0x18001133b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011340  add     rax, 18h
0x180011344  mov     rcx, rdi
0x180011347  mov     [rbp+var_18], rax
0x18001134b  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180011352  mov     rax, [rax+18h]
0x180011356  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001135b  mov     rcx, rdi
0x18001135e  lea     rbx, [rax+18h]
0x180011362  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180011369  mov     [rbp+lpString], rbx
0x18001136d  mov     rax, [rax+18h]
0x180011371  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011376  cmp     qword ptr [rsi+10h], 0
0x18001137b  lea     rdi, [rax+18h]
0x18001137f  mov     [rbp+var_28], rdi
0x180011383  jnz     short loc_180011390
0x180011385  mov     r14d, 8000FFFFh
0x18001138b  jmp     loc_1800114CC
0x180011390  mov     edx, 42D3h
0x180011395  lea     rcx, [rbp+var_18]
0x180011399  call    ?LoadStringW@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAHI@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::LoadStringW(uint)
0x18001139e  test    eax, eax
0x1800113a0  jnz     short loc_1800113AD
0x1800113a2  mov     r14d, 80004005h
0x1800113a8  jmp     loc_1800114CC
0x1800113ad  mov     rcx, [rsi+10h]
0x1800113b1  lea     rdx, [rbp+bstrString]
0x1800113b5  mov     rax, [rcx]
0x1800113b8  mov     rax, [rax+18h]
0x1800113bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800113c1  mov     r14d, eax
0x1800113c4  test    eax, eax
0x1800113c6  js      loc_1800114CC
0x1800113cc  mov     rdx, [rbp+bstrString]
0x1800113d0  lea     rcx, [rbp+var_28]
0x1800113d4  call    ??4?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator=(ushort const *)
0x1800113d9  mov     rdi, [rbp+var_28]
0x1800113dd  mov     ebx, [rdi-10h]
0x1800113e0  cmp     ebx, 19h
0x1800113e3  jle     loc_18001149E
0x1800113e9  lea     esi, [rbx-16h]
0x1800113ec  test    esi, esi
0x1800113ee  jns     short loc_1800113F4
0x1800113f0  xor     esi, esi
0x1800113f2  jmp     short loc_180011404
0x1800113f4  mov     eax, 7FFFFFFFh
0x1800113f9  sub     eax, esi
0x1800113fb  cmp     eax, 17h
0x1800113fe  jl      loc_180011565
0x180011404  lea     eax, [rsi+17h]
0x180011407  cmp     eax, ebx
0x180011409  jle     short loc_18001140E
0x18001140b  lea     esi, [rbx-17h]
0x18001140e  test    esi, esi
0x180011410  jle     short loc_180011491
0x180011412  cmp     dword ptr [rdi-8], 1
0x180011416  jle     short loc_180011427
0x180011418  mov     edx, ebx
0x18001141a  lea     rcx, [rbp+var_28]
0x18001141e  call    ?Fork@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::Fork(int)
0x180011423  mov     rdi, [rbp+var_28]
0x180011427  mov     eax, ebx
0x180011429  lea     rcx, [rdi+2Eh]; Destination
0x18001142d  sub     eax, esi
0x18001142f  sub     eax, 16h
0x180011432  movsxd  rdx, eax
0x180011435  add     rdx, rdx; DestinationSize
0x180011438  movsxd  rax, esi
0x18001143b  add     rax, 17h
0x18001143f  mov     r9, rdx; SourceSize
0x180011442  lea     r8, [rdi+rax*2]; Source
0x180011446  call    cs:__imp_memmove_s
0x18001144c  test    eax, eax
0x18001144e  jz      short loc_180011474
0x180011450  cmp     eax, 0Ch
0x180011453  jz      loc_18001155A
0x180011459  cmp     eax, 16h
0x18001145c  jz      loc_180011565
0x180011462  cmp     eax, 22h ; '"'
0x180011465  jz      loc_180011565
0x18001146b  cmp     eax, 50h ; 'P'
0x18001146e  jnz     loc_180011570
0x180011474  sub     ebx, esi
0x180011476  js      loc_180011565
0x18001147c  cmp     ebx, [rdi-0Ch]
0x18001147f  jg      loc_180011565
0x180011485  movsxd  rcx, ebx
0x180011488  xor     eax, eax
0x18001148a  mov     [rdi-10h], ebx
0x18001148d  mov     [rdi+rcx*2], ax
0x180011491  lea     rcx, [rbp+var_28]
0x180011495  call    ?Insert@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAHHPEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Insert(int,ushort const *)
0x18001149a  mov     rdi, [rbp+var_28]
0x18001149e  mov     rdx, [rbp+var_18]
0x1800114a2  lea     rcx, [rbp+lpString]
0x1800114a6  mov     r8, rdi
0x1800114a9  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x1800114ae  mov     edx, 3AE3h; nIDDlgItem
0x1800114b3  mov     rcx, r15; hDlg
0x1800114b6  call    cs:__imp_GetDlgItem
0x1800114bc  mov     rbx, [rbp+lpString]
0x1800114c0  mov     rcx, rax; hWnd
0x1800114c3  mov     rdx, rbx; lpString
0x1800114c6  call    cs:__imp_SetWindowTextW
0x1800114cc  mov     rcx, [rbp+bstrString]; bstrString
0x1800114d0  test    rcx, rcx
0x1800114d3  jz      short loc_1800114E3
0x1800114d5  call    cs:__imp_SysFreeString
0x1800114db  mov     [rbp+bstrString], 0
0x1800114e3  lea     rdx, [rdi-18h]
0x1800114e7  or      edi, 0FFFFFFFFh
0x1800114ea  mov     eax, edi
0x1800114ec  lock xadd [rdx+10h], eax
0x1800114f1  add     eax, edi
0x1800114f3  test    eax, eax
0x1800114f5  jg      short loc_180011506
0x1800114f7  mov     rcx, [rdx]
0x1800114fa  mov     rax, [rcx]
0x1800114fd  mov     rax, [rax+8]
0x180011501  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011506  lea     rdx, [rbx-18h]
0x18001150a  mov     eax, edi
0x18001150c  lock xadd [rdx+10h], eax
0x180011511  add     eax, edi
0x180011513  test    eax, eax
0x180011515  jg      short loc_180011526
0x180011517  mov     rcx, [rdx]
0x18001151a  mov     rax, [rcx]
0x18001151d  mov     rax, [rax+8]
0x180011521  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011526  mov     rdx, [rbp+var_18]
0x18001152a  mov     eax, edi
0x18001152c  add     rdx, 0FFFFFFFFFFFFFFE8h
0x180011530  lock xadd [rdx+10h], eax
0x180011535  add     eax, edi
0x180011537  test    eax, eax
0x180011539  jg      short loc_18001154A
0x18001153b  mov     rcx, [rdx]
0x18001153e  mov     rax, [rcx]
0x180011541  mov     rax, [rax+8]
0x180011545  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001154a  mov     eax, r14d
0x18001154d  add     rsp, 48h
0x180011551  pop     r15
0x180011553  pop     r14
0x180011555  pop     rdi
0x180011556  pop     rsi
0x180011557  pop     rbx
0x180011558  pop     rbp
0x180011559  retn
0x18001155a  mov     ecx, 8007000Eh; int
0x18001155f  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180011565  mov     ecx, 80070057h; int
0x18001156a  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180011570  mov     ecx, 80004005h; int
0x180011575  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
