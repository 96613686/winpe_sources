# CPreflistFolder::InvokeCommand(CUICommand *,IShellItemArray *,IBindCtx *)

- ea: `0x18000fdf0`
- end: `0x1800102b2`
- name: `?InvokeCommand@CPreflistFolder@@UEAAJPEAVCUICommand@@PEAUIShellItemArray@@PEAUIBindCtx@@@Z`
- size: `1218`
- prototype: `int(CPreflistFolder *__hidden this, struct CUICommand *, struct IShellItemArray *, struct IBindCtx *)`
- caller_count: `0`
- callee_count: `20`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180003458`
- `0x1800036ac`
- `0x18000cf1c`
- `0x18000cfd4`
- `0x18000d158`
- `0x18000d264`
- `0x18000d290`
- `0x18000d2e4`
- `0x18000dd14`
- `0x18000df24`
- `0x18000f080`
- `0x18000fb60`
- `0x18000fc60`
- `0x18000fdf0`
- `0x180026024`
- `0x18002749c`
- `0x180027594`
- `0x18002d7f6`
- `0x18002d840`
- `0x180030010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800101ac`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800101ac`
- `ntdll!WinSqmSetDWORD` at `0x18000ff39`
- `ntdll!WinSqmSetDWORD` at `0x18000ffb1`
- `ntdll!WinSqmSetDWORD` at `0x18000ff39`
- `ntdll!WinSqmSetDWORD` at `0x18000ffb1`
- `ntdll!WinSqmIncrementDWORD` at `0x18000fe9e`
- `ntdll!WinSqmIncrementDWORD` at `0x18000fef9`
- `ntdll!WinSqmIncrementDWORD` at `0x18000fe9e`
- `ntdll!WinSqmIncrementDWORD` at `0x18000fef9`
- `SHELL32!ShellExecuteW` at `0x1800100ba`
- `SHELL32!ShellExecuteW` at `0x1800100ba`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall CPreflistFolder::InvokeCommand(
        HWND *this,
        struct CUICommand *a2,
        struct IShellItemArray *a3,
        struct IBindCtx *a4)
{
  HWND v7; // rcx
  HRESULT v8; // ebx
  __int64 v9; // r8
  __int64 v10; // rax
  WTL::CString *v11; // rcx
  __int64 v12; // rbx
  __int64 v13; // rdi
  LPVOID ppv; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v16; // [rsp+38h] [rbp-C8h] BYREF
  struct _GUID v17; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v18; // [rsp+50h] [rbp-B0h]
  int v19; // [rsp+58h] [rbp-A8h]
  LPCWSTR lpFile; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v21[8]; // [rsp+68h] [rbp-98h] BYREF
  _QWORD v22[7]; // [rsp+70h] [rbp-90h] BYREF
  int v23; // [rsp+A8h] [rbp-58h]
  __int16 v24; // [rsp+B0h] [rbp-50h]
  __int64 v25; // [rsp+B8h] [rbp-48h]
  __int128 Buf1; // [rsp+C0h] [rbp-40h] BYREF
  void **v27; // [rsp+D0h] [rbp-30h] BYREF
  struct _GUID v28; // [rsp+D8h] [rbp-28h]
  char v29; // [rsp+E8h] [rbp-18h] BYREF
  struct _GUID Buf2; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v31[96]; // [rsp+100h] [rbp+0h] BYREF

  CPreflistFolder::InitializeDataSource((CPreflistFolder *)(this - 8));
  Buf1 = 0;
  (*(void (__fastcall **)(struct CUICommand *, __int128 *))(*(_QWORD *)a2 + 48LL))(a2, &Buf1);
  CProfile::CProfile((CProfile *)v31);
  CPreflistFolder::GetFirstProfile(a3, (struct CProfile *)v31);
  if ( !memcmp_0(&Buf1, qword_180035408, 0x10u) )
    goto LABEL_29;
  if ( !memcmp_0(&Buf1, &xmmword_1800353F8, 0x10u) )
  {
    WinSqmIncrementDWORD(0, 6203, 1);
    (*(void (__fastcall **)(__int64, void ***))(*(_QWORD *)CSingletonPtr<CWlanProfileStore>::s_pInstance + 80LL))(
      CSingletonPtr<CWlanProfileStore>::s_pInstance,
      &v27);
    v17 = v28;
    v8 = RunInfraWizard(v7, &v17);
LABEL_15:
    v27 = &CAdapter::`vftable';
    v11 = (WTL::CString *)&v29;
LABEL_22:
    WTL::CString::~CString(v11);
    goto LABEL_30;
  }
  if ( memcmp_0(&Buf1, &xmmword_1800353E8, 0x10u) )
  {
    if ( !memcmp_0(&Buf1, &xmmword_1800353D8, 0x10u) )
    {
      WinSqmSetDWORD(0, 6201, 1);
      v9 = (*(unsigned int (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)CSingletonPtr<CWlanProfileStore>::s_pInstance
                                                            + 64LL))(
             CSingletonPtr<CWlanProfileStore>::s_pInstance,
             v31)
         - 1;
    }
    else
    {
      if ( memcmp_0(&Buf1, &xmmword_1800353C8, 0x10u) )
      {
        if ( !memcmp_0(&Buf1, &xmmword_1800353A8, 0x10u) )
        {
          (*(void (__fastcall **)(__int64, void ***))(*(_QWORD *)CSingletonPtr<CWlanProfileStore>::s_pInstance + 80LL))(
            CSingletonPtr<CWlanProfileStore>::s_pInstance,
            &v27);
          Buf2 = v28;
          ppv = (LPVOID)WTL::_atltmpPchNil;
          v8 = GuidToString(&Buf2, (struct WTL::CString *)&ppv);
          if ( v8 >= 0 )
          {
            WTL::CString::CString((WTL::CString *)&v16, L"shell:::{7007acc7-3202-11d1-aad2-00805fc1270e}");
            v10 = WTL::operator+((WTL::CString *)&v17);
            WTL::operator+(v21, v10, &ppv);
            WTL::operator+((WTL::CString *)&lpFile);
            WTL::CString::~CString((WTL::CString *)v21);
            WTL::CString::~CString((WTL::CString *)&v17);
            v8 = ShellExecuteW(this[12], L"properties", lpFile, 0, 0, 1) == 0 ? 0x80004005 : 0;
            WTL::CString::~CString((WTL::CString *)&lpFile);
            WTL::CString::~CString((WTL::CString *)&v16);
          }
          WTL::CString::~CString((WTL::CString *)&ppv);
          goto LABEL_15;
        }
        if ( !memcmp_0(&Buf1, &xmmword_180035398, 0x10u) )
        {
          v22[1] = 0;
          v22[5] = 0;
          v22[6] = 0;
          v23 = 0;
          v22[0] = &CSwitchDlg::`vftable';
          v25 = 0;
          v24 = 1;
          ATL::CDialogImpl<CSwitchDlg,ATL::CWindow>::DoModal(v22, this[12]);
          v8 = 0;
          CSwitchDlg::~CSwitchDlg((CSwitchDlg *)v22);
          goto LABEL_30;
        }
        if ( !memcmp_0(&Buf1, &xmmword_180035388, 0x10u) )
        {
          WTL::CString::CString((WTL::CString *)&v16, L"Microsoft.NetworkAndSharingCenter");
          ppv = 0;
          v8 = CoCreateInstance(
                 &GUID_06622d85_6856_4460_8de1_a81921b41c4b,
                 0,
                 0x17u,
                 &GUID_d11ad862_66de_4df4_bf6c_1f5621996af1,
                 &ppv);
          if ( v8 >= 0 )
            v8 = (*(__int64 (__fastcall **)(LPVOID, __int64, _QWORD, HWND))(*(_QWORD *)ppv + 24LL))(
                   ppv,
                   v16,
                   0,
                   this[9]);
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppv);
          v11 = (WTL::CString *)&v16;
          goto LABEL_22;
        }
        *(_QWORD *)&v17.Data1 = 0;
        *(_QWORD *)v17.Data4 = 0;
        v18 = 0;
        v19 = 0;
        (*(void (__fastcall **)(__int64, struct _GUID *))(*(_QWORD *)CSingletonPtr<CWlanProfileStore>::s_pInstance + 72LL))(
          CSingletonPtr<CWlanProfileStore>::s_pInstance,
          &v17);
        v12 = 0;
        if ( *(_QWORD *)v17.Data4 )
        {
          while ( 1 )
          {
            v13 = ATL::CAtlArray<CAdapter,ATL::CElementTraits<CAdapter>>::GetAt(&v17, v12);
            Buf2 = *(struct _GUID *)(v13 + 8);
            if ( !memcmp_0(&Buf1, &Buf2, 0x10u) )
              break;
            if ( (unsigned __int64)++v12 >= *(_QWORD *)v17.Data4 )
              goto LABEL_28;
          }
          (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)CSingletonPtr<CWlanProfileStore>::s_pInstance + 88LL))(
            CSingletonPtr<CWlanProfileStore>::s_pInstance,
            v13);
        }
LABEL_28:
        ATL::CAtlArray<CAdapter,ATL::CElementTraits<CAdapter>>::~CAtlArray<CAdapter,ATL::CElementTraits<CAdapter>>(&v17);
LABEL_29:
        v8 = 0;
        goto LABEL_30;
      }
      WinSqmSetDWORD(0, 6201, 1);
      v9 = (*(unsigned int (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)CSingletonPtr<CWlanProfileStore>::s_pInstance
                                                            + 64LL))(
             CSingletonPtr<CWlanProfileStore>::s_pInstance,
             v31)
         + 1;
    }
    (*(void (__fastcall **)(__int64, _BYTE *, __int64))(*(_QWORD *)CSingletonPtr<CWlanProfileStore>::s_pInstance + 160LL))(
      CSingletonPtr<CWlanProfileStore>::s_pInstance,
      v31,
      v9);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)CSingletonPtr<CWlanProfileStore>::s_pInstance + 184LL))(CSingletonPtr<CWlanProfileStore>::s_pInstance);
    goto LABEL_29;
  }
  WinSqmIncrementDWORD(0, 6202, 1);
  v8 = DeleteProfileWithUI(this[12], (char *)this + 84, v31);
LABEL_30:
  CProfile::~CProfile((CProfile *)v31);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18000fdf0  mov     [rsp-8+arg_18], rbx
0x18000fdf5  push    rbp
0x18000fdf6  push    rsi
0x18000fdf7  push    rdi
0x18000fdf8  push    r14
0x18000fdfa  push    r15
0x18000fdfc  lea     rbp, [rsp-70h]
0x18000fe01  sub     rsp, 170h
0x18000fe08  mov     rax, cs:__security_cookie
0x18000fe0f  xor     rax, rsp
0x18000fe12  mov     [rbp+90h+var_30], rax
0x18000fe16  mov     rdi, r8
0x18000fe19  mov     rbx, rdx
0x18000fe1c  mov     rsi, rcx
0x18000fe1f  add     rcx, 0FFFFFFFFFFFFFFC0h; this
0x18000fe23  call    ?InitializeDataSource@CPreflistFolder@@IEAAXXZ; CPreflistFolder::InitializeDataSource(void)
0x18000fe28  xorps   xmm0, xmm0
0x18000fe2b  movups  [rbp+90h+Buf1], xmm0
0x18000fe2f  mov     rax, [rbx]
0x18000fe32  lea     rdx, [rbp+90h+Buf1]
0x18000fe36  mov     rcx, rbx
0x18000fe39  mov     rax, [rax+30h]
0x18000fe3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fe42  lea     rcx, [rbp+90h+var_90]; this
0x18000fe46  call    ??0CProfile@@QEAA@XZ; CProfile::CProfile(void)
0x18000fe4b  nop
0x18000fe4c  lea     rdx, [rbp+90h+var_90]; struct CProfile *
0x18000fe50  mov     rcx, rdi; struct IShellItemArray *
0x18000fe53  call    ?GetFirstProfile@CPreflistFolder@@CAJPEAUIShellItemArray@@AEAVCProfile@@@Z; CPreflistFolder::GetFirstProfile(IShellItemArray *,CProfile &)
0x18000fe58  mov     r15d, 10h
0x18000fe5e  mov     r8d, r15d; Size
0x18000fe61  lea     rdx, qword_180035408; Buf2
0x18000fe68  lea     rcx, [rbp+90h+Buf1]; Buf1
0x18000fe6c  call    memcmp_0
0x18000fe71  xor     r14d, r14d
0x18000fe74  test    eax, eax
0x18000fe76  jz      loc_180010281
0x18000fe7c  mov     r8d, r15d; Size
0x18000fe7f  lea     rdx, xmmword_1800353F8; Buf2
0x18000fe86  lea     rcx, [rbp+90h+Buf1]; Buf1
0x18000fe8a  call    memcmp_0
0x18000fe8f  test    eax, eax
0x18000fe91  jnz     short loc_18000FED7
0x18000fe93  mov     edx, 183Bh
0x18000fe98  xor     ecx, ecx
0x18000fe9a  lea     r8d, [r15-0Fh]
0x18000fe9e  call    cs:__imp_WinSqmIncrementDWORD
0x18000fea4  mov     rcx, cs:?s_pInstance@?$CSingletonPtr@VCWlanProfileStore@@@@0PEAVCWlanProfileStore@@EA; CWlanProfileStore * CSingletonPtr<CWlanProfileStore>::s_pInstance
0x18000feab  mov     rax, [rcx]
0x18000feae  lea     rdx, [rbp+90h+var_C0]
0x18000feb2  mov     rax, [rax+50h]
0x18000feb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000febb  nop
0x18000febc  movups  xmm0, [rbp+90h+var_B8]
0x18000fec0  movdqu  xmmword ptr [rsp+190h+var_150.Data1], xmm0
0x18000fec6  lea     rdx, [rsp+190h+var_150]; struct _GUID *
0x18000fecb  call    ?RunInfraWizard@@YAJPEAUHWND__@@PEAU_GUID@@@Z; RunInfraWizard(HWND__ *,_GUID *)
0x18000fed0  mov     ebx, eax
0x18000fed2  jmp     loc_1800100EE
0x18000fed7  mov     r8, r15; Size
0x18000feda  lea     rdx, xmmword_1800353E8; Buf2
0x18000fee1  lea     rcx, [rbp+90h+Buf1]; Buf1
0x18000fee5  call    memcmp_0
0x18000feea  test    eax, eax
0x18000feec  jnz     short loc_18000FF17
0x18000feee  mov     edx, 183Ah
0x18000fef3  xor     ecx, ecx
0x18000fef5  lea     r8d, [rax+1]
0x18000fef9  call    cs:__imp_WinSqmIncrementDWORD
0x18000feff  lea     rdx, [rsi+54h]
0x18000ff03  lea     r8, [rbp+90h+var_90]
0x18000ff07  mov     rcx, [rsi+60h]
0x18000ff0b  call    ?DeleteProfileWithUI@@YAJPEAUHWND__@@AEAV?$CSingletonPtr@VCWlanProfileStore@@@@AEAVCProfile@@@Z; DeleteProfileWithUI(HWND__ *,CSingletonPtr<CWlanProfileStore> &,CProfile &)
0x18000ff10  mov     ebx, eax
0x18000ff12  jmp     loc_180010284
0x18000ff17  mov     r8, r15; Size
0x18000ff1a  lea     rdx, xmmword_1800353D8; Buf2
0x18000ff21  lea     rcx, [rbp+90h+Buf1]; Buf1
0x18000ff25  call    memcmp_0
0x18000ff2a  test    eax, eax
0x18000ff2c  jnz     short loc_18000FF8F
0x18000ff2e  mov     edx, 1839h
0x18000ff33  xor     ecx, ecx
0x18000ff35  lea     r8d, [rax+1]
0x18000ff39  call    cs:__imp_WinSqmSetDWORD
0x18000ff3f  mov     rcx, cs:?s_pInstance@?$CSingletonPtr@VCWlanProfileStore@@@@0PEAVCWlanProfileStore@@EA; CWlanProfileStore * CSingletonPtr<CWlanProfileStore>::s_pInstance
0x18000ff46  mov     rax, [rcx]
0x18000ff49  lea     rdx, [rbp+90h+var_90]
0x18000ff4d  mov     rax, [rax+40h]
0x18000ff51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ff56  lea     r8d, [rax-1]
0x18000ff5a  mov     rcx, cs:?s_pInstance@?$CSingletonPtr@VCWlanProfileStore@@@@0PEAVCWlanProfileStore@@EA; CWlanProfileStore * CSingletonPtr<CWlanProfileStore>::s_pInstance
0x18000ff61  mov     rdx, [rcx]
0x18000ff64  mov     rax, [rdx+0A0h]
0x18000ff6b  lea     rdx, [rbp+90h+var_90]
0x18000ff6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ff74  mov     rcx, cs:?s_pInstance@?$CSingletonPtr@VCWlanProfileStore@@@@0PEAVCWlanProfileStore@@EA; CWlanProfileStore * CSingletonPtr<CWlanProfileStore>::s_pInstance
0x18000ff7b  mov     rax, [rcx]
0x18000ff7e  mov     rax, [rax+0B8h]
0x18000ff85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ff8a  jmp     loc_180010281
0x18000ff8f  mov     r8, r15; Size
0x18000ff92  lea     rdx, xmmword_1800353C8; Buf2
0x18000ff99  lea     rcx, [rbp+90h+Buf1]; Buf1
0x18000ff9d  call    memcmp_0
0x18000ffa2  test    eax, eax
0x18000ffa4  jnz     short loc_18000FFD4
0x18000ffa6  mov     edx, 1839h
0x18000ffab  xor     ecx, ecx
0x18000ffad  lea     r8d, [rax+1]
0x18000ffb1  call    cs:__imp_WinSqmSetDWORD
0x18000ffb7  mov     rcx, cs:?s_pInstance@?$CSingletonPtr@VCWlanProfileStore@@@@0PEAVCWlanProfileStore@@EA; CWlanProfileStore * CSingletonPtr<CWlanProfileStore>::s_pInstance
0x18000ffbe  mov     rax, [rcx]
0x18000ffc1  lea     rdx, [rbp+90h+var_90]
0x18000ffc5  mov     rax, [rax+40h]
0x18000ffc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ffce  lea     r8d, [rax+1]
0x18000ffd2  jmp     short loc_18000FF5A
0x18000ffd4  mov     r8, r15; Size
0x18000ffd7  lea     rdx, xmmword_1800353A8; Buf2
0x18000ffde  lea     rcx, [rbp+90h+Buf1]; Buf1
0x18000ffe2  call    memcmp_0
0x18000ffe7  test    eax, eax
0x18000ffe9  jnz     loc_180010102
0x18000ffef  mov     rcx, cs:?s_pInstance@?$CSingletonPtr@VCWlanProfileStore@@@@0PEAVCWlanProfileStore@@EA; CWlanProfileStore * CSingletonPtr<CWlanProfileStore>::s_pInstance
0x18000fff6  mov     rax, [rcx]
0x18000fff9  lea     rdx, [rbp+90h+var_C0]
0x18000fffd  mov     rax, [rax+50h]
0x180010001  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010006  nop
0x180010007  movups  xmm0, [rbp+90h+var_B8]
0x18001000b  movdqu  [rbp+90h+Buf2], xmm0
0x180010010  mov     rax, cs:?_atltmpPchNil@WTL@@3PEBGEB; ushort const * const WTL::_atltmpPchNil
0x180010017  mov     [rsp+190h+ppv], rax
0x18001001c  lea     rdx, [rsp+190h+ppv]; struct WTL::CString *
0x180010021  lea     rcx, [rbp+90h+Buf2]; struct _GUID *
0x180010025  call    ?GuidToString@@YAJAEBU_GUID@@AEAVCString@WTL@@@Z; GuidToString(_GUID const &,WTL::CString &)
0x18001002a  mov     ebx, eax
0x18001002c  test    eax, eax
0x18001002e  js      loc_1800100E3
0x180010034  lea     rdx, aShell7007acc73; "shell:::{7007acc7-3202-11d1-aad2-00805f"...
0x18001003b  lea     rcx, [rsp+190h+var_158]; this
0x180010040  call    ??0CString@WTL@@QEAA@PEBG@Z; WTL::CString::CString(ushort const *)
0x180010045  nop
0x180010046  lea     r8, asc_180035290; "\\::{"
0x18001004d  lea     rdx, [rsp+190h+var_158]
0x180010052  lea     rcx, [rsp+190h+var_150]; this
0x180010057  call    ??HWTL@@YA?AVCString@0@AEBV10@PEBG@Z; WTL::operator+(WTL::CString const &,ushort const *)
0x18001005c  nop
0x18001005d  lea     r8, [rsp+190h+ppv]
0x180010062  mov     rdx, rax
0x180010065  lea     rcx, [rsp+190h+var_128]
0x18001006a  call    ??HWTL@@YA?AVCString@0@AEBV10@0@Z; WTL::operator+(WTL::CString const &,WTL::CString const &)
0x18001006f  nop
0x180010070  lea     r8, asc_18003505C; "}"
0x180010077  mov     rdx, rax
0x18001007a  lea     rcx, [rsp+190h+lpFile]; this
0x18001007f  call    ??HWTL@@YA?AVCString@0@AEBV10@PEBG@Z; WTL::operator+(WTL::CString const &,ushort const *)
0x180010084  nop
0x180010085  lea     rcx, [rsp+190h+var_128]; this
0x18001008a  call    ??1CString@WTL@@QEAA@XZ; WTL::CString::~CString(void)
0x18001008f  nop
0x180010090  lea     rcx, [rsp+190h+var_150]; this
0x180010095  call    ??1CString@WTL@@QEAA@XZ; WTL::CString::~CString(void)
0x18001009a  mov     [rsp+190h+nShowCmd], 1; nShowCmd
0x1800100a2  mov     [rsp+190h+lpDirectory], r14; lpDirectory
0x1800100a7  xor     r9d, r9d; lpParameters
0x1800100aa  mov     r8, [rsp+190h+lpFile]; lpFile
0x1800100af  lea     rdx, aProperties; "properties"
0x1800100b6  mov     rcx, [rsi+60h]; hwnd
0x1800100ba  call    cs:__imp_ShellExecuteW
0x1800100c0  neg     rax
0x1800100c3  sbb     ebx, ebx
0x1800100c5  not     ebx
0x1800100c7  and     ebx, 80004005h
0x1800100cd  lea     rcx, [rsp+190h+lpFile]; this
0x1800100d2  call    ??1CString@WTL@@QEAA@XZ; WTL::CString::~CString(void)
0x1800100d7  nop
0x1800100d8  lea     rcx, [rsp+190h+var_158]; this
0x1800100dd  call    ??1CString@WTL@@QEAA@XZ; WTL::CString::~CString(void)
0x1800100e2  nop
0x1800100e3  lea     rcx, [rsp+190h+ppv]; this
0x1800100e8  call    ??1CString@WTL@@QEAA@XZ; WTL::CString::~CString(void)
0x1800100ed  nop
0x1800100ee  lea     rax, ??_7CAdapter@@6B@; const CAdapter::`vftable'
0x1800100f5  mov     [rbp+90h+var_C0], rax
0x1800100f9  lea     rcx, [rbp+90h+var_A8]
0x1800100fd  jmp     loc_1800101E7
0x180010102  mov     r8, r15; Size
0x180010105  lea     rdx, xmmword_180035398; Buf2
0x18001010c  lea     rcx, [rbp+90h+Buf1]; Buf1
0x180010110  call    memcmp_0
0x180010115  test    eax, eax
0x180010117  jnz     short loc_180010160
0x180010119  mov     [rsp+190h+var_118], r14
0x18001011e  mov     [rbp+90h+var_F8], r14
0x180010122  mov     [rbp+90h+var_F0], r14
0x180010126  mov     [rbp+90h+var_E8], r14d
0x18001012a  lea     rax, ??_7CSwitchDlg@@6B@; const CSwitchDlg::`vftable'
0x180010131  mov     [rsp+190h+var_120], rax
0x180010136  mov     [rbp+90h+var_D8], r14
0x18001013a  mov     [rbp+90h+var_E0], 1
0x180010140  mov     rdx, [rsi+60h]
0x180010144  lea     rcx, [rsp+190h+var_120]
0x180010149  call    ?DoModal@?$CDialogImpl@VCSwitchDlg@@VCWindow@ATL@@@ATL@@QEAA_JPEAUHWND__@@_J@Z; ATL::CDialogImpl<CSwitchDlg,ATL::CWindow>::DoModal(HWND__ *,__int64)
0x18001014e  mov     ebx, r14d
0x180010151  lea     rcx, [rsp+190h+var_120]; this
0x180010156  call    ??1CSwitchDlg@@UEAA@XZ; CSwitchDlg::~CSwitchDlg(void)
0x18001015b  jmp     loc_180010284
0x180010160  mov     r8, r15; Size
0x180010163  lea     rdx, xmmword_180035388; Buf2
0x18001016a  lea     rcx, [rbp+90h+Buf1]; Buf1
0x18001016e  call    memcmp_0
0x180010173  test    eax, eax
0x180010175  jnz     short loc_1800101F1
0x180010177  lea     rdx, aMicrosoftNetwo; "Microsoft.NetworkAndSharingCenter"
0x18001017e  lea     rcx, [rsp+190h+var_158]; this
0x180010183  call    ??0CString@WTL@@QEAA@PEBG@Z; WTL::CString::CString(ushort const *)
0x180010188  nop
0x180010189  mov     [rsp+190h+ppv], r14
0x18001018e  lea     rax, [rsp+190h+ppv]
0x180010193  mov     [rsp+190h+lpDirectory], rax; ppv
0x180010198  lea     r9, _GUID_d11ad862_66de_4df4_bf6c_1f5621996af1; riid
0x18001019f  xor     edx, edx; pUnkOuter
0x1800101a1  lea     r8d, [rdx+17h]; dwClsContext
0x1800101a5  lea     rcx, _GUID_06622d85_6856_4460_8de1_a81921b41c4b; rclsid
0x1800101ac  call    cs:__imp_CoCreateInstance
0x1800101b2  mov     ebx, eax
0x1800101b4  test    eax, eax
0x1800101b6  js      short loc_1800101D7
0x1800101b8  mov     rcx, [rsp+190h+ppv]
0x1800101bd  mov     rax, [rcx]
0x1800101c0  mov     r9, [rsi+48h]
0x1800101c4  xor     r8d, r8d
0x1800101c7  mov     rdx, [rsp+190h+var_158]
0x1800101cc  mov     rax, [rax+18h]
0x1800101d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800101d5  mov     ebx, eax
0x1800101d7  lea     rcx, [rsp+190h+ppv]
0x1800101dc  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800101e1  nop
0x1800101e2  lea     rcx, [rsp+190h+var_158]; this
0x1800101e7  call    ??1CString@WTL@@QEAA@XZ; WTL::CString::~CString(void)
0x1800101ec  jmp     loc_180010284
0x1800101f1  mov     qword ptr [rsp+190h+var_150.Data1], r14
0x1800101f6  mov     qword ptr [rsp+190h+var_150.Data4], r14
0x1800101fb  mov     [rsp+190h+var_140], r14
0x180010200  mov     [rsp+190h+var_138], r14d
0x180010205  mov     rcx, cs:?s_pInstance@?$CSingletonPtr@VCWlanProfileStore@@@@0PEAVCWlanProfileStore@@EA; CWlanProfileStore * CSingletonPtr<CWlanProfileStore>::s_pInstance
0x18001020c  mov     rax, [rcx]
0x18001020f  lea     rdx, [rsp+190h+var_150]
0x180010214  mov     rax, [rax+48h]
0x180010218  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001021d  mov     rbx, r14
0x180010220  cmp     qword ptr [rsp+190h+var_150.Data4], r14
0x180010225  jbe     short loc_180010277
0x180010227  mov     rdx, rbx
0x18001022a  lea     rcx, [rsp+190h+var_150]
0x18001022f  call    ?GetAt@?$CAtlArray@VCAdapter@@V?$CElementTraits@VCAdapter@@@ATL@@@ATL@@QEBAAEBVCAdapter@@_K@Z; ATL::CAtlArray<CAdapter,ATL::CElementTraits<CAdapter>>::GetAt(unsigned __int64)
0x180010234  mov     rdi, rax
0x180010237  movups  xmm0, xmmword ptr [rax+8]
0x18001023b  movdqu  [rbp+90h+Buf2], xmm0
0x180010240  mov     r8, r15; Size
0x180010243  lea     rdx, [rbp+90h+Buf2]; Buf2
0x180010247  lea     rcx, [rbp+90h+Buf1]; Buf1
0x18001024b  call    memcmp_0
0x180010250  test    eax, eax
0x180010252  jz      short loc_180010260
0x180010254  inc     rbx
0x180010257  cmp     rbx, qword ptr [rsp+190h+var_150.Data4]
0x18001025c  jb      short loc_180010227
0x18001025e  jmp     short loc_180010277
0x180010260  mov     rcx, cs:?s_pInstance@?$CSingletonPtr@VCWlanProfileStore@@@@0PEAVCWlanProfileStore@@EA; CWlanProfileStore * CSingletonPtr<CWlanProfileStore>::s_pInstance
0x180010267  mov     rax, [rcx]
0x18001026a  mov     rdx, rdi
0x18001026d  mov     rax, [rax+58h]
0x180010271  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010276  nop
0x180010277  lea     rcx, [rsp+190h+var_150]
0x18001027c  call    ??1?$CAtlArray@VCAdapter@@V?$CElementTraits@VCAdapter@@@ATL@@@ATL@@QEAA@XZ; ATL::CAtlArray<CAdapter,ATL::CElementTraits<CAdapter>>::~CAtlArray<CAdapter,ATL::CElementTraits<CAdapter>>(void)
0x180010281  mov     ebx, r14d
0x180010284  lea     rcx, [rbp+90h+var_90]; this
0x180010288  call    ??1CProfile@@UEAA@XZ; CProfile::~CProfile(void)
0x18001028d  mov     eax, ebx
0x18001028f  mov     rcx, [rbp+90h+var_30]
0x180010293  xor     rcx, rsp; StackCookie
0x180010296  call    __security_check_cookie
0x18001029b  mov     rbx, [rsp+190h+arg_18]
0x1800102a3  add     rsp, 170h
0x1800102aa  pop     r15
0x1800102ac  pop     r14
0x1800102ae  pop     rdi
0x1800102af  pop     rsi
0x1800102b0  pop     rbp
0x1800102b1  retn
```
