# winrt::WindowsUdk::System::implementation::LaunchEmailInOutlook(wil::com_ptr_t<IDispatch,wil::err_exception_policy> const &,winrt::hstring const &)

- ea: `0x18031ca48`
- end: `0x18031ce0c`
- name: `?LaunchEmailInOutlook@implementation@System@WindowsUdk@winrt@@YAJAEBV?$com_ptr_t@UIDispatch@@Uerr_exception_policy@wil@@@wil@@AEBUhstring@4@@Z`
- size: `964`
- prototype: `__int64 __fastcall(_QWORD *, winrt::hstring *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x18031ce20`

## callees

- `0x180025348`
- `0x18002e634`
- `0x1800483f4`
- `0x1800e34bc`
- `0x18031ca48`
- `0x1804a2010`

## import_xrefs

- `combase!__imp_CoAllowSetForegroundWindow` at `0x18031ccec`
- `combase!__imp_CoAllowSetForegroundWindow` at `0x18031ccec`
- `OLEAUT32!__imp_SysAllocString` at `0x18031caef`
- `OLEAUT32!__imp_SysAllocString` at `0x18031caef`
- `OLEAUT32!__imp_VariantInit` at `0x18031cad4`
- `OLEAUT32!__imp_VariantInit` at `0x18031cb41`
- `OLEAUT32!__imp_VariantInit` at `0x18031cd59`
- `OLEAUT32!__imp_VariantInit` at `0x18031cad4`
- `OLEAUT32!__imp_VariantInit` at `0x18031cb41`
- `OLEAUT32!__imp_VariantInit` at `0x18031cd59`
- `OLEAUT32!__imp_VariantClear` at `0x18031cb1e`
- `OLEAUT32!__imp_VariantClear` at `0x18031cbae`
- `OLEAUT32!__imp_VariantClear` at `0x18031cbf0`
- `OLEAUT32!__imp_VariantClear` at `0x18031cbfb`
- `OLEAUT32!__imp_VariantClear` at `0x18031cdc1`
- `OLEAUT32!__imp_VariantClear` at `0x18031cdd7`
- `OLEAUT32!__imp_VariantClear` at `0x18031cb1e`
- `OLEAUT32!__imp_VariantClear` at `0x18031cbae`
- `OLEAUT32!__imp_VariantClear` at `0x18031cbf0`
- `OLEAUT32!__imp_VariantClear` at `0x18031cbfb`
- `OLEAUT32!__imp_VariantClear` at `0x18031cdc1`
- `OLEAUT32!__imp_VariantClear` at `0x18031cdd7`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18031cc86`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18031cc86`

## string_xrefs

- `0x18031cabb`: `shellcommon\undockeddevkit\libs\windowsudk.system\launcher.cpp`
- `0x18031cb0a`: `shellcommon\undockeddevkit\libs\windowsudk.system\launcher.cpp`
- `0x18031cb99`: `shellcommon\undockeddevkit\libs\windowsudk.system\launcher.cpp`
- `0x18031cc4b`: `shellcommon\undockeddevkit\libs\windowsudk.system\launcher.cpp`
- `0x18031cc97`: `shellcommon\undockeddevkit\libs\windowsudk.system\launcher.cpp`
- `0x18031ccfd`: `shellcommon\undockeddevkit\libs\windowsudk.system\launcher.cpp`
- `0x18031cd33`: `shellcommon\undockeddevkit\libs\windowsudk.system\launcher.cpp`
- `0x18031cdab`: `shellcommon\undockeddevkit\libs\windowsudk.system\launcher.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall winrt::WindowsUdk::System::implementation::LaunchEmailInOutlook(_QWORD *a1, winrt::hstring *a2)
{
  int v4; // eax
  unsigned int v5; // ebx
  const OLECHAR *v6; // rax
  int v7; // eax
  __int64 v8; // r9
  __int64 v9; // rdx
  LONGLONG llVal; // rbx
  int v11; // eax
  unsigned int v12; // edi
  HRESULT v13; // eax
  __int64 v14; // rax
  int v15; // eax
  wil::details::in1diag3 *v16; // rcx
  __int64 v17; // rdx
  HRESULT v18; // eax
  int v19; // eax
  int ppv; // [rsp+20h] [rbp-99h]
  int ppva; // [rsp+20h] [rbp-99h]
  LPVOID v23; // [rsp+50h] [rbp-69h] BYREF
  LONGLONG v24; // [rsp+58h] [rbp-61h] BYREF
  VARIANTARG pvarg; // [rsp+60h] [rbp-59h] BYREF
  VARIANTARG v26; // [rsp+78h] [rbp-41h] BYREF
  const wchar_t *v27; // [rsp+90h] [rbp-29h] BYREF
  _QWORD v28[4]; // [rsp+98h] [rbp-21h] BYREF
  __int128 v29; // [rsp+B8h] [rbp-1h]
  __int64 v30; // [rsp+C8h] [rbp+Fh]
  VARIANTARG v31; // [rsp+D0h] [rbp+17h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]
  IUnknown *pUnk; // [rsp+138h] [rbp+7Fh] BYREF

  v24 = 0;
  v27 = L"GetItemFromID";
  HIWORD(ppv) = 0;
  v4 = (*(__int64 (__fastcall **)(_QWORD, GUID *, const wchar_t **, __int64))(*(_QWORD *)*a1 + 40LL))(
         *a1,
         &GUID_NULL,
         &v27,
         1);
  v5 = v4;
  if ( v4 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x74,
      (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.system\\launcher.cpp",
      (const char *)(unsigned int)v4,
      1024);
    goto LABEL_28;
  }
  VariantInit(&pvarg);
  pvarg.vt = 8;
  v6 = winrt::hstring::c_str(a2);
  pvarg.llVal = (LONGLONG)SysAllocString(v6);
  if ( !pvarg.llVal )
  {
    v5 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x79,
      (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.system\\launcher.cpp",
      (const char *)0x8007000ELL,
      1024);
LABEL_5:
    VariantClear(&pvarg);
    goto LABEL_28;
  }
  v28[2] = 0;
  v28[3] = 1;
  v28[1] = &pvarg;
  VariantInit(&v26);
  LOWORD(ppv) = 1;
  v7 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, GUID *, __int64))(*(_QWORD *)*a1 + 48LL))(*a1, 0, &GUID_NULL, 2048);
  v5 = v7;
  if ( v7 < 0 )
  {
    v8 = (unsigned int)v7;
    v9 = 128;
LABEL_8:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.system\\launcher.cpp",
      (const char *)v8,
      ppv);
    VariantClear(&v26);
    goto LABEL_5;
  }
  if ( v26.vt != 9 )
  {
    v5 = -2147467259;
    v8 = 2147500037LL;
    v9 = 129;
    goto LABEL_8;
  }
  llVal = v26.llVal;
  v24 = v26.llVal;
  if ( v26.llVal )
    (*(void (__fastcall **)(LONGLONG))(*v26.pllVal + 8))(v26.llVal);
  VariantClear(&v26);
  VariantClear(&pvarg);
  v28[0] = L"Display";
  v11 = (*(__int64 (__fastcall **)(LONGLONG, GUID *, _QWORD *, __int64))(*(_QWORD *)llVal + 40LL))(
          llVal,
          &GUID_NULL,
          v28,
          1);
  v12 = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x88,
      (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.system\\launcher.cpp",
      (const char *)(unsigned int)v11,
      1024);
    v5 = v12;
    goto LABEL_28;
  }
  v23 = 0;
  v13 = CoCreateInstance(&CLSID_ImmersiveShell, 0, 0x404u, &GUID_6d5140c1_7436_11ce_8034_00aa006009fa, &v23);
  if ( v13 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x8B,
      (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.system\\launcher.cpp",
      (const char *)(unsigned int)v13,
      ppva);
    goto LABEL_25;
  }
  pUnk = 0;
  v14 = *(_QWORD *)v23;
  pUnk = 0;
  v15 = (*(__int64 (__fastcall **)(LPVOID, GUID *, GUID *, IUnknown **))(v14 + 24))(
          v23,
          &IID_IImmersiveApplicationManager,
          &GUID_bf63999f_7411_40da_861c_df72c0ffee84,
          &pUnk);
  v16 = retaddr;
  if ( v15 >= 0 )
  {
    v18 = CoAllowSetForegroundWindow(pUnk, 0);
    if ( v18 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x90,
        (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.system\\launcher.cpp",
        (const char *)(unsigned int)v18,
        ppva);
    v15 = ((__int64 (__fastcall *)(IUnknown *, _QWORD, __int64))pUnk->lpVtbl[4].QueryInterface)(pUnk, 0, 1);
    v16 = retaddr;
    if ( v15 >= 0 )
      goto LABEL_24;
    v17 = 145;
  }
  else
  {
    v17 = 142;
  }
  wil::details::in1diag3::_Log_Hr(
    v16,
    (void *)v17,
    (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.system\\launcher.cpp",
    (const char *)(unsigned int)v15,
    ppva);
LABEL_24:
  wil::com_ptr_t<Windows::Internal::Sustainability::IGridIntensityData,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Sustainability::IGridIntensityData,wil::err_exception_policy>(&pUnk);
LABEL_25:
  v29 = 0;
  v30 = 0;
  VariantInit(&v31);
  LOWORD(ppva) = 1;
  v19 = (*(__int64 (__fastcall **)(LONGLONG, _QWORD, GUID *, __int64))(*(_QWORD *)llVal + 48LL))(
          llVal,
          0,
          &GUID_NULL,
          2048);
  v5 = v19;
  if ( v19 >= 0 )
  {
    VariantClear(&v31);
    wil::com_ptr_t<Windows::Internal::Sustainability::IGridIntensityData,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Sustainability::IGridIntensityData,wil::err_exception_policy>(&v23);
    v5 = 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x97,
      (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.system\\launcher.cpp",
      (const char *)(unsigned int)v19,
      ppva);
    VariantClear(&v31);
    wil::com_ptr_t<Windows::Internal::Sustainability::IGridIntensityData,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Sustainability::IGridIntensityData,wil::err_exception_policy>(&v23);
  }
LABEL_28:
  wil::com_ptr_t<Windows::Internal::Sustainability::IGridIntensityData,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Sustainability::IGridIntensityData,wil::err_exception_policy>(&v24);
  return v5;
}

```

## disassembly

```asm
0x18031ca48  mov     [rsp-8+arg_8], rbx
0x18031ca4d  push    rbp
0x18031ca4e  push    rsi
0x18031ca4f  push    rdi
0x18031ca50  push    r14
0x18031ca52  push    r15
0x18031ca54  lea     rbp, [rsp-37h]
0x18031ca59  sub     rsp, 0F0h
0x18031ca60  mov     rdi, rdx
0x18031ca63  mov     rsi, rcx
0x18031ca66  xor     r14d, r14d
0x18031ca69  mov     [rbp+57h+var_B8], r14
0x18031ca6d  mov     [rbp+57h+arg_0], r14d
0x18031ca71  lea     rax, aGetitemfromid; "GetItemFromID"
0x18031ca78  mov     [rbp+57h+var_80], rax
0x18031ca7c  mov     rcx, [rcx]
0x18031ca7f  mov     rax, [rcx]
0x18031ca82  lea     rdx, [rbp+57h+arg_0]
0x18031ca86  mov     [rsp+110h+var_E8], rdx
0x18031ca8b  mov     dword ptr [rsp+110h+ppv], 400h; int
0x18031ca93  lea     r15d, [r14+1]
0x18031ca97  mov     r9d, r15d
0x18031ca9a  lea     r8, [rbp+57h+var_80]
0x18031ca9e  lea     rdx, GUID_NULL
0x18031caa5  mov     rax, [rax+28h]
0x18031caa9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18031caae  mov     ebx, eax
0x18031cab0  test    eax, eax
0x18031cab2  jns     short loc_18031CAD0
0x18031cab4  mov     rcx, [rbp+5Fh]; this
0x18031cab8  mov     r9d, eax; char *
0x18031cabb  lea     r8, aShellcommonUnd_134; "shellcommon\\undockeddevkit\\libs\\wind"...
0x18031cac2  lea     edx, [r14+74h]; void *
0x18031cac6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18031cacb  jmp     loc_18031CDEA
0x18031cad0  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18031cad4  call    cs:__imp_VariantInit
0x18031cada  nop
0x18031cadb  mov     eax, 8
0x18031cae0  mov     word ptr [rbp+57h+pvarg], ax
0x18031cae4  mov     rcx, rdi; this
0x18031cae7  call    ?c_str@hstring@winrt@@QEBAPEB_WXZ; winrt::hstring::c_str(void)
0x18031caec  mov     rcx, rax; psz
0x18031caef  call    cs:__imp_SysAllocString
0x18031caf5  mov     qword ptr [rbp+57h+pvarg+8], rax
0x18031caf9  test    rax, rax
0x18031cafc  jnz     short loc_18031CB29
0x18031cafe  mov     rcx, [rbp+5Fh]; this
0x18031cb02  mov     ebx, 8007000Eh
0x18031cb07  mov     r9d, ebx; char *
0x18031cb0a  lea     r8, aShellcommonUnd_134; "shellcommon\\undockeddevkit\\libs\\wind"...
0x18031cb11  lea     edx, [rax+79h]; void *
0x18031cb14  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18031cb19  nop
0x18031cb1a  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18031cb1e  call    cs:__imp_VariantClear
0x18031cb24  jmp     loc_18031CDEA
0x18031cb29  mov     [rbp+57h+var_68], r14
0x18031cb2d  mov     [rbp+57h+var_60], 1
0x18031cb35  lea     rax, [rbp+57h+pvarg]
0x18031cb39  mov     [rbp+57h+var_70], rax
0x18031cb3d  lea     rcx, [rbp+57h+var_98]; pvarg
0x18031cb41  call    cs:__imp_VariantInit
0x18031cb47  nop
0x18031cb48  mov     rcx, [rsi]
0x18031cb4b  mov     rax, [rcx]
0x18031cb4e  mov     [rsp+110h+var_D0], r14
0x18031cb53  mov     [rsp+110h+var_D8], r14
0x18031cb58  lea     rdx, [rbp+57h+var_98]
0x18031cb5c  mov     [rsp+110h+var_E0], rdx
0x18031cb61  lea     rdx, [rbp+57h+var_70]
0x18031cb65  mov     [rsp+110h+var_E8], rdx
0x18031cb6a  mov     word ptr [rsp+110h+ppv], r15w; int
0x18031cb70  mov     esi, 800h
0x18031cb75  mov     r9d, esi
0x18031cb78  lea     r8, GUID_NULL
0x18031cb7f  mov     edx, [rbp+57h+arg_0]
0x18031cb82  mov     rax, [rax+30h]
0x18031cb86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18031cb8b  mov     ebx, eax
0x18031cb8d  test    eax, eax
0x18031cb8f  jns     short loc_18031CBB9
0x18031cb91  mov     r9d, eax; char *
0x18031cb94  mov     edx, 80h; void *
0x18031cb99  lea     r8, aShellcommonUnd_134; "shellcommon\\undockeddevkit\\libs\\wind"...
0x18031cba0  mov     rcx, [rbp+5Fh]; this
0x18031cba4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18031cba9  nop
0x18031cbaa  lea     rcx, [rbp+57h+var_98]; pvarg
0x18031cbae  call    cs:__imp_VariantClear
0x18031cbb4  jmp     loc_18031CB1A
0x18031cbb9  cmp     word ptr [rbp+57h+var_98], 9
0x18031cbbe  jz      short loc_18031CBCF
0x18031cbc0  mov     ebx, 80004005h
0x18031cbc5  mov     r9d, ebx
0x18031cbc8  mov     edx, 81h
0x18031cbcd  jmp     short loc_18031CB99
0x18031cbcf  mov     rbx, qword ptr [rbp+57h+var_98+8]
0x18031cbd3  mov     [rbp+57h+var_B8], rbx
0x18031cbd7  test    rbx, rbx
0x18031cbda  jz      short loc_18031CBEC
0x18031cbdc  mov     rax, [rbx]
0x18031cbdf  mov     rcx, rbx
0x18031cbe2  mov     rax, [rax+8]
0x18031cbe6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18031cbeb  nop
0x18031cbec  lea     rcx, [rbp+57h+var_98]; pvarg
0x18031cbf0  call    cs:__imp_VariantClear
0x18031cbf6  nop
0x18031cbf7  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18031cbfb  call    cs:__imp_VariantClear
0x18031cc01  mov     [rbp+57h+arg_10], r14d
0x18031cc05  lea     rax, aDisplay; "Display"
0x18031cc0c  mov     [rbp+57h+var_78], rax
0x18031cc10  mov     rax, [rbx]
0x18031cc13  lea     rcx, [rbp+57h+arg_10]
0x18031cc17  mov     [rsp+110h+var_E8], rcx
0x18031cc1c  mov     dword ptr [rsp+110h+ppv], 400h; int
0x18031cc24  mov     r9d, r15d
0x18031cc27  lea     r8, [rbp+57h+var_78]
0x18031cc2b  lea     rdx, GUID_NULL
0x18031cc32  mov     rcx, rbx
0x18031cc35  mov     rax, [rax+28h]
0x18031cc39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18031cc3e  mov     edi, eax
0x18031cc40  test    eax, eax
0x18031cc42  jns     short loc_18031CC63
0x18031cc44  mov     rcx, [rbp+5Fh]; this
0x18031cc48  mov     r9d, eax; char *
0x18031cc4b  lea     r8, aShellcommonUnd_134; "shellcommon\\undockeddevkit\\libs\\wind"...
0x18031cc52  mov     edx, 88h; void *
0x18031cc57  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18031cc5c  mov     ebx, edi
0x18031cc5e  jmp     loc_18031CDEA
0x18031cc63  mov     [rbp+57h+var_C0], r14
0x18031cc67  lea     rax, [rbp+57h+var_C0]
0x18031cc6b  mov     [rsp+110h+ppv], rax; int
0x18031cc70  lea     r9, _GUID_6d5140c1_7436_11ce_8034_00aa006009fa; riid
0x18031cc77  xor     edx, edx; pUnkOuter
0x18031cc79  mov     r8d, 404h; dwClsContext
0x18031cc7f  lea     rcx, CLSID_ImmersiveShell; rclsid
0x18031cc86  call    cs:__imp_CoCreateInstance
0x18031cc8c  mov     rcx, [rbp+5Fh]; this
0x18031cc90  test    eax, eax
0x18031cc92  jns     short loc_18031CCAD
0x18031cc94  mov     r9d, eax; char *
0x18031cc97  lea     r8, aShellcommonUnd_134; "shellcommon\\undockeddevkit\\libs\\wind"...
0x18031cc9e  mov     edx, 8Bh; void *
0x18031cca3  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18031cca8  jmp     loc_18031CD49
0x18031ccad  mov     [rbp+57h+pUnk], r14
0x18031ccb1  mov     rcx, [rbp+57h+var_C0]
0x18031ccb5  mov     rax, [rcx]
0x18031ccb8  mov     [rbp+57h+pUnk], r14
0x18031ccbc  lea     r9, [rbp+57h+pUnk]
0x18031ccc0  lea     r8, _GUID_bf63999f_7411_40da_861c_df72c0ffee84
0x18031ccc7  lea     rdx, IID_IImmersiveApplicationManager
0x18031ccce  mov     rax, [rax+18h]
0x18031ccd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18031ccd7  mov     rcx, [rbp+5Fh]
0x18031ccdb  test    eax, eax
0x18031ccdd  jns     short loc_18031CCE6
0x18031ccdf  mov     edx, 8Eh
0x18031cce4  jmp     short loc_18031CD30
0x18031cce6  xor     edx, edx; lpvReserved
0x18031cce8  mov     rcx, [rbp+57h+pUnk]; pUnk
0x18031ccec  call    cs:__imp_CoAllowSetForegroundWindow
0x18031ccf2  mov     rcx, [rbp+5Fh]; this
0x18031ccf6  test    eax, eax
0x18031ccf8  jns     short loc_18031CD0E
0x18031ccfa  mov     r9d, eax; char *
0x18031ccfd  lea     r8, aShellcommonUnd_134; "shellcommon\\undockeddevkit\\libs\\wind"...
0x18031cd04  mov     edx, 90h; void *
0x18031cd09  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18031cd0e  mov     rcx, [rbp+57h+pUnk]
0x18031cd12  mov     rax, [rcx]
0x18031cd15  mov     r8d, r15d
0x18031cd18  xor     edx, edx
0x18031cd1a  mov     rax, [rax+60h]
0x18031cd1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18031cd23  mov     rcx, [rbp+5Fh]; this
0x18031cd27  test    eax, eax
0x18031cd29  jns     short loc_18031CD40
0x18031cd2b  mov     edx, 91h; void *
0x18031cd30  mov     r9d, eax; char *
0x18031cd33  lea     r8, aShellcommonUnd_134; "shellcommon\\undockeddevkit\\libs\\wind"...
0x18031cd3a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18031cd3f  nop
0x18031cd40  lea     rcx, [rbp+57h+pUnk]
0x18031cd44  call    ??1?$com_ptr_t@UIGridIntensityData@Sustainability@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::Sustainability::IGridIntensityData,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Sustainability::IGridIntensityData,wil::err_exception_policy>(void)
0x18031cd49  xorps   xmm0, xmm0
0x18031cd4c  movdqu  [rbp+57h+var_58], xmm0
0x18031cd51  mov     [rbp+57h+var_48], r14
0x18031cd55  lea     rcx, [rbp+57h+var_40]; pvarg
0x18031cd59  call    cs:__imp_VariantInit
0x18031cd5f  nop
0x18031cd60  mov     rax, [rbx]
0x18031cd63  mov     [rsp+110h+var_D0], r14
0x18031cd68  mov     [rsp+110h+var_D8], r14
0x18031cd6d  lea     rcx, [rbp+57h+var_40]
0x18031cd71  mov     [rsp+110h+var_E0], rcx
0x18031cd76  lea     rcx, [rbp+57h+var_58]
0x18031cd7a  mov     [rsp+110h+var_E8], rcx
0x18031cd7f  mov     word ptr [rsp+110h+ppv], r15w; int
0x18031cd85  mov     r9d, esi
0x18031cd88  lea     r8, GUID_NULL
0x18031cd8f  mov     edx, [rbp+57h+arg_10]
0x18031cd92  mov     rcx, rbx
0x18031cd95  mov     rax, [rax+30h]
0x18031cd99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18031cd9e  mov     ebx, eax
0x18031cda0  test    eax, eax
0x18031cda2  jns     short loc_18031CDD3
0x18031cda4  mov     rcx, [rbp+5Fh]; this
0x18031cda8  mov     r9d, eax; char *
0x18031cdab  lea     r8, aShellcommonUnd_134; "shellcommon\\undockeddevkit\\libs\\wind"...
0x18031cdb2  mov     edx, 97h; void *
0x18031cdb7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18031cdbc  nop
0x18031cdbd  lea     rcx, [rbp+57h+var_40]; pvarg
0x18031cdc1  call    cs:__imp_VariantClear
0x18031cdc7  nop
0x18031cdc8  lea     rcx, [rbp+57h+var_C0]
0x18031cdcc  call    ??1?$com_ptr_t@UIGridIntensityData@Sustainability@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::Sustainability::IGridIntensityData,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Sustainability::IGridIntensityData,wil::err_exception_policy>(void)
0x18031cdd1  jmp     short loc_18031CDEA
0x18031cdd3  lea     rcx, [rbp+57h+var_40]; pvarg
0x18031cdd7  call    cs:__imp_VariantClear
0x18031cddd  nop
0x18031cdde  lea     rcx, [rbp+57h+var_C0]
0x18031cde2  call    ??1?$com_ptr_t@UIGridIntensityData@Sustainability@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::Sustainability::IGridIntensityData,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Sustainability::IGridIntensityData,wil::err_exception_policy>(void)
0x18031cde7  mov     ebx, r14d
0x18031cdea  lea     rcx, [rbp+57h+var_B8]
0x18031cdee  call    ??1?$com_ptr_t@UIGridIntensityData@Sustainability@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::Sustainability::IGridIntensityData,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Sustainability::IGridIntensityData,wil::err_exception_policy>(void)
0x18031cdf3  mov     eax, ebx
0x18031cdf5  mov     rbx, [rsp+110h+arg_8]
0x18031cdfd  add     rsp, 0F0h
0x18031ce04  pop     r15
0x18031ce06  pop     r14
0x18031ce08  pop     rdi
0x18031ce09  pop     rsi
0x18031ce0a  pop     rbp
0x18031ce0b  retn
```
