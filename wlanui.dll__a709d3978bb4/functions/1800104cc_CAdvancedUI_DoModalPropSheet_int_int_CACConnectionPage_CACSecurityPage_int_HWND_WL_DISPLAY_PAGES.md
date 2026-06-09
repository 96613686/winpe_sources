# CAdvancedUI::_DoModalPropSheet(int,int,CACConnectionPage *,CACSecurityPage *,int,HWND__ *,_WL_DISPLAY_PAGES)

- ea: `0x1800104cc`
- end: `0x1800106eb`
- name: `?_DoModalPropSheet@CAdvancedUI@@AEAAHHHPEAVCACConnectionPage@@PEAVCACSecurityPage@@HPEAUHWND__@@W4_WL_DISPLAY_PAGES@@@Z`
- size: `543`
- prototype: `int(CAdvancedUI *__hidden this, int, int, struct CACConnectionPage *, struct CACSecurityPage *, int, HWND, enum _WL_DISPLAY_PAGES)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18000fe78`

## callees

- `0x1800068e8`
- `0x18000901c`
- `0x18000fa44`
- `0x1800104cc`
- `0x180014e90`
- `0x18001bf0a`
- `0x18001d010`

## pseudocode

```c
__int64 __fastcall CAdvancedUI::_DoModalPropSheet(
        const WCHAR *this,
        int a2,
        int a3,
        struct CACConnectionPage *a4,
        struct CACSecurityPage *a5,
        int a6,
        HWND a7,
        enum _WL_DISPLAY_PAGES a8)
{
  volatile signed __int32 *v11; // rax
  volatile signed __int32 *v12; // rbx
  unsigned int v13; // r8d
  const unsigned __int16 *v14; // r9
  unsigned int v15; // r8d
  const unsigned __int16 *v16; // r9
  void (*v17)(void); // rax
  __int64 v19; // rcx
  __int64 v20; // rcx
  __int64 v21; // r8
  __int64 v22; // rax
  const WCHAR *v23; // rbx
  unsigned int v24; // edi
  const unsigned __int16 *v25; // [rsp+20h] [rbp-89h]
  const unsigned __int16 *v26; // [rsp+20h] [rbp-89h]
  const unsigned __int16 *v27; // [rsp+28h] [rbp-81h]
  const unsigned __int16 *v28; // [rsp+28h] [rbp-81h]
  HINSTANCE v29; // [rsp+30h] [rbp-79h]
  HINSTANCE v30; // [rsp+30h] [rbp-79h]
  unsigned int (*v31)(HWND, unsigned int, struct _PROPSHEETPAGEW *); // [rsp+38h] [rbp-71h]
  unsigned int (*v32)(HWND, unsigned int, struct _PROPSHEETPAGEW *); // [rsp+38h] [rbp-71h]
  __int128 v33; // [rsp+40h] [rbp-69h] BYREF
  PROPSHEETHEADERW_V2 v34; // [rsp+50h] [rbp-59h] BYREF
  const WCHAR *v35; // [rsp+F0h] [rbp+47h] BYREF

  v35 = this;
  memset_0(&v34, 0, sizeof(v34));
  v33 = 0;
  v11 = (volatile signed __int32 *)((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr);
  v12 = v11 + 6;
  v35 = (const WCHAR *)(v11 + 6);
  if ( a4 && a5 )
  {
    memset_0(&v34, 0, sizeof(v34));
    v33 = 0u;
    *(_QWORD *)&v33 = CPropSheetPage::CreatePage(a4, (unsigned int)(a2 != 0) + 101, v13, v14, v25, v27, v29, v31);
    if ( !(_QWORD)v33 )
    {
      if ( _InterlockedExchangeAdd(v12 - 2, 0xFFFFFFFF) <= 1 )
      {
        v17 = *(void (**)(void))(**((_QWORD **)v12 - 3) + 8LL);
LABEL_9:
        v17();
        return 0xFFFFFFFFLL;
      }
      return 0xFFFFFFFFLL;
    }
    *((_QWORD *)&v33 + 1) = CPropSheetPage::CreatePage(a5, 0x67u, v15, v16, v26, v28, v30, v32);
    if ( !*((_QWORD *)&v33 + 1) )
    {
      if ( _InterlockedExchangeAdd(v12 - 2, 0xFFFFFFFF) <= 1 )
      {
        v17 = *(void (**)(void))(**((_QWORD **)v12 - 3) + 8LL);
        goto LABEL_9;
      }
      return 0xFFFFFFFFLL;
    }
    v19 = *((_QWORD *)a4 + 18);
    v34.hwndParent = a7;
    v34.hInstance = hInstance;
    v34.ppsp = (LPCPROPSHEETPAGEW)&v33;
    v34.dwSize = 72;
    v34.nStartPage = a8 != WLConnectionPage;
    v34.dwFlags = 33554560;
    v34.nPages = 2;
    v20 = v19 + 24;
    if ( !v20 && !*((_QWORD *)a4 + 17) )
      goto LABEL_32;
    v21 = *((_QWORD *)a4 + 17);
    v22 = -1;
    do
      ++v22;
    while ( *(_WORD *)(v21 + 2 * v22) );
    if ( (unsigned int)v22 <= 0x20 )
    {
      if ( v20 )
        v21 = v20;
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::FormatMessageW(
        &v35,
        17302,
        v21);
    }
    else
    {
LABEL_32:
      if ( !(unsigned int)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::LoadStringW(
                            &v35,
                            17301) )
      {
        v23 = v35;
        v24 = -1;
LABEL_22:
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v23 - 2, 0xFFFFFFFF) <= 1 )
          (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v23 - 3) + 8LL))(*((_QWORD *)v23 - 3));
        return v24;
      }
    }
    v23 = v35;
    v34.pszCaption = v35;
    if ( a3 )
    {
      v34.dwFlags |= 0x100u;
      v34.pfnCallback = SetDialogElevationRequired;
    }
    v24 = PropertySheetW(&v34);
    goto LABEL_22;
  }
  if ( _InterlockedExchangeAdd(v11 + 4, 0xFFFFFFFF) <= 1 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v11 + 8LL))(*(_QWORD *)v11);
  return 87;
}

```

## disassembly

```asm
0x1800104cc  mov     [rsp-8+arg_0], rcx
0x1800104d1  push    rbp
0x1800104d2  push    rbx
0x1800104d3  push    rdi
0x1800104d4  push    r12
0x1800104d6  push    r14
0x1800104d8  push    r15
0x1800104da  lea     rbp, [rsp-0Fh]
0x1800104df  sub     rsp, 0B8h
0x1800104e6  mov     r14d, edx
0x1800104e9  lea     rcx, [rbp+37h+var_90]; void *
0x1800104ed  xor     edx, edx; Val
0x1800104ef  mov     r15d, r8d
0x1800104f2  mov     rdi, r9
0x1800104f5  lea     r8d, [rdx+60h]; Size
0x1800104f9  call    memset_0
0x1800104fe  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180010505  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18001050c  xorps   xmm0, xmm0
0x18001050f  movups  [rbp+37h+var_A0], xmm0
0x180010513  mov     rax, [rax+18h]
0x180010517  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001051c  xor     r12d, r12d
0x18001051f  lea     rbx, [rax+18h]
0x180010523  mov     [rbp+37h+arg_0], rbx
0x180010527  test    rdi, rdi
0x18001052a  jz      loc_1800106B5
0x180010530  cmp     [rbp+37h+arg_20], r12
0x180010534  jz      loc_1800106B5
0x18001053a  xor     edx, edx; Val
0x18001053c  lea     r8d, [r12+60h]; Size
0x180010541  lea     rcx, [rbp+37h+var_90]; void *
0x180010545  call    memset_0
0x18001054a  xor     eax, eax
0x18001054c  mov     rcx, rdi; this
0x18001054f  neg     r14d
0x180010552  mov     qword ptr [rbp+37h+var_A0], rax
0x180010556  mov     qword ptr [rbp+37h+var_A0+8], rax
0x18001055a  sbb     edx, edx
0x18001055c  neg     edx
0x18001055e  add     edx, 65h ; 'e'; unsigned int
0x180010561  call    ?CreatePage@CPropSheetPage@@QEAAPEAU_PSP@@IKPEBG00PEAUHINSTANCE__@@P6AIPEAUHWND__@@IPEAU_PROPSHEETPAGEW@@@Z@Z; CPropSheetPage::CreatePage(uint,ulong,ushort const *,ushort const *,ushort const *,HINSTANCE__ *,uint (*)(HWND__ *,uint,_PROPSHEETPAGEW *))
0x180010566  mov     qword ptr [rbp+37h+var_A0], rax
0x18001056a  test    rax, rax
0x18001056d  jnz     short loc_18001058C
0x18001056f  lea     rdx, [rbx-18h]
0x180010573  or      eax, 0FFFFFFFFh
0x180010576  lock xadd [rdx+10h], eax
0x18001057b  sub     eax, 1
0x18001057e  jg      short loc_1800105C3
0x180010580  mov     rcx, [rdx]
0x180010583  mov     rax, [rcx]
0x180010586  mov     rax, [rax+8]
0x18001058a  jmp     short loc_1800105BE
0x18001058c  mov     rcx, [rbp+37h+arg_20]; this
0x180010590  mov     edx, 67h ; 'g'; unsigned int
0x180010595  call    ?CreatePage@CPropSheetPage@@QEAAPEAU_PSP@@IKPEBG00PEAUHINSTANCE__@@P6AIPEAUHWND__@@IPEAU_PROPSHEETPAGEW@@@Z@Z; CPropSheetPage::CreatePage(uint,ulong,ushort const *,ushort const *,ushort const *,HINSTANCE__ *,uint (*)(HWND__ *,uint,_PROPSHEETPAGEW *))
0x18001059a  mov     qword ptr [rbp+37h+var_A0+8], rax
0x18001059e  test    rax, rax
0x1800105a1  jnz     short loc_1800105CB
0x1800105a3  lea     rdx, [rbx-18h]
0x1800105a7  or      ecx, 0FFFFFFFFh
0x1800105aa  lock xadd [rdx+10h], ecx
0x1800105af  sub     ecx, 1
0x1800105b2  jg      short loc_1800105C3
0x1800105b4  mov     rcx, [rdx]
0x1800105b7  mov     r8, [rcx]
0x1800105ba  mov     rax, [r8+8]
0x1800105be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800105c3  or      eax, 0FFFFFFFFh
0x1800105c6  jmp     loc_1800106DA
0x1800105cb  mov     rax, [rbp+37h+arg_30]
0x1800105cf  cmp     [rbp+37h+arg_38], r12d
0x1800105d3  mov     rcx, [rdi+90h]
0x1800105da  mov     [rbp+37h+var_90.hwndParent], rax
0x1800105de  mov     rax, cs:hInstance
0x1800105e5  mov     [rbp+37h+var_90.hInstance], rax
0x1800105e9  lea     rax, [rbp+37h+var_A0]
0x1800105ed  mov     qword ptr [rbp+37h+var_90.38h], rax
0x1800105f1  mov     eax, r12d
0x1800105f4  setnz   al
0x1800105f7  mov     [rbp+37h+var_90.dwSize], 48h ; 'H'
0x1800105fe  mov     dword ptr [rbp+37h+var_90.30h], eax
0x180010601  mov     [rbp+37h+var_90.dwFlags], 2000080h
0x180010608  mov     [rbp+37h+var_90.nPages], 2
0x18001060f  add     rcx, 18h
0x180010613  jnz     short loc_18001061E
0x180010615  cmp     [rdi+88h], r12
0x18001061c  jz      short loc_18001069A
0x18001061e  mov     r8, [rdi+88h]
0x180010625  or      rax, 0FFFFFFFFFFFFFFFFh
0x180010629  inc     rax
0x18001062c  cmp     [r8+rax*2], r12w
0x180010631  jnz     short loc_180010629
0x180010633  cmp     eax, 20h ; ' '
0x180010636  ja      short loc_18001069A
0x180010638  test    rcx, rcx
0x18001063b  mov     edx, 4396h
0x180010640  cmovnz  r8, rcx
0x180010644  lea     rcx, [rbp+37h+arg_0]
0x180010648  call    ?FormatMessageW@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXIZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::FormatMessageW(uint,...)
0x18001064d  mov     rbx, [rbp+37h+arg_0]
0x180010651  mov     [rbp+37h+var_90.pszCaption], rbx
0x180010655  test    r15d, r15d
0x180010658  jz      short loc_18001066A
0x18001065a  bts     [rbp+37h+var_90.dwFlags], 8
0x18001065f  lea     rax, ?SetDialogElevationRequired@@YAHPEAUHWND__@@I_J@Z; SetDialogElevationRequired(HWND__ *,uint,__int64)
0x180010666  mov     [rbp+37h+var_90.pfnCallback], rax
0x18001066a  lea     rcx, [rbp+37h+var_90]; LPCPROPSHEETHEADERW
0x18001066e  call    PropertySheetW
0x180010673  mov     rdi, rax
0x180010676  lea     rdx, [rbx-18h]
0x18001067a  or      ecx, 0FFFFFFFFh
0x18001067d  lock xadd [rdx+10h], ecx
0x180010682  sub     ecx, 1
0x180010685  jg      short loc_180010696
0x180010687  mov     rcx, [rdx]
0x18001068a  mov     r8, [rcx]
0x18001068d  mov     rax, [r8+8]
0x180010691  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010696  mov     eax, edi
0x180010698  jmp     short loc_1800106DA
0x18001069a  mov     edx, 4395h
0x18001069f  lea     rcx, [rbp+37h+arg_0]
0x1800106a3  call    ?LoadStringW@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAHI@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::LoadStringW(uint)
0x1800106a8  test    eax, eax
0x1800106aa  jnz     short loc_18001064D
0x1800106ac  mov     rbx, [rbp+37h+arg_0]
0x1800106b0  or      edi, 0FFFFFFFFh
0x1800106b3  jmp     short loc_180010676
0x1800106b5  lea     rdx, [rbx-18h]
0x1800106b9  or      eax, 0FFFFFFFFh
0x1800106bc  lock xadd [rdx+10h], eax
0x1800106c1  sub     eax, 1
0x1800106c4  jg      short loc_1800106D5
0x1800106c6  mov     rcx, [rdx]
0x1800106c9  mov     rax, [rcx]
0x1800106cc  mov     rax, [rax+8]
0x1800106d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800106d5  mov     eax, 57h ; 'W'
0x1800106da  add     rsp, 0B8h
0x1800106e1  pop     r15
0x1800106e3  pop     r14
0x1800106e5  pop     r12
0x1800106e7  pop     rdi
0x1800106e8  pop     rbx
0x1800106e9  pop     rbp
0x1800106ea  retn
```
