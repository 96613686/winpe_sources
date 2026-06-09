# winrt::WindowsUdk::System::implementation::GetOutlookMapiNamespace(IDispatch * *)

- ea: `0x18031c6fc`
- end: `0x18031c966`
- name: `?GetOutlookMapiNamespace@implementation@System@WindowsUdk@winrt@@YAJPEAPEAUIDispatch@@@Z`
- size: `618`
- prototype: `__int64 __fastcall(winrt::WindowsUdk::System::implementation *__hidden this, struct IDispatch **)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x18031ca0c`
- `0x18031ce20`

## callees

- `0x18002e634`
- `0x1800e34bc`
- `0x18015cb00`
- `0x18031c6fc`
- `0x1804a2010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18031c81a`
- `OLEAUT32!__imp_SysAllocString` at `0x18031c81a`
- `OLEAUT32!__imp_VariantInit` at `0x18031c803`
- `OLEAUT32!__imp_VariantInit` at `0x18031c870`
- `OLEAUT32!__imp_VariantInit` at `0x18031c803`
- `OLEAUT32!__imp_VariantInit` at `0x18031c870`
- `OLEAUT32!__imp_VariantClear` at `0x18031c849`
- `OLEAUT32!__imp_VariantClear` at `0x18031c8e4`
- `OLEAUT32!__imp_VariantClear` at `0x18031c92f`
- `OLEAUT32!__imp_VariantClear` at `0x18031c93a`
- `OLEAUT32!__imp_VariantClear` at `0x18031c849`
- `OLEAUT32!__imp_VariantClear` at `0x18031c8e4`
- `OLEAUT32!__imp_VariantClear` at `0x18031c92f`
- `OLEAUT32!__imp_VariantClear` at `0x18031c93a`
- `api-ms-win-core-com-l1-1-0!CLSIDFromProgID` at `0x18031c738`
- `api-ms-win-core-com-l1-1-0!CLSIDFromProgID` at `0x18031c738`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18031c783`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18031c783`

## string_xrefs

- `0x18031c74b`: `shellcommon\undockeddevkit\libs\windowsudk.system\launcher.cpp`
- `0x18031c7e7`: `shellcommon\undockeddevkit\libs\windowsudk.system\launcher.cpp`
- `0x18031c835`: `shellcommon\undockeddevkit\libs\windowsudk.system\launcher.cpp`
- `0x18031c8d3`: `shellcommon\undockeddevkit\libs\windowsudk.system\launcher.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall winrt::WindowsUdk::System::implementation::GetOutlookMapiNamespace(
        winrt::WindowsUdk::System::implementation *this,
        struct IDispatch **a2)
{
  HRESULT v3; // eax
  unsigned int v4; // ebx
  HRESULT v5; // eax
  __int64 v6; // rdx
  int v7; // eax
  __int64 v8; // rdx
  __int64 v9; // r9
  int ppv; // [rsp+20h] [rbp-79h]
  int ppva; // [rsp+20h] [rbp-79h]
  LPVOID v13; // [rsp+58h] [rbp-41h] BYREF
  VARIANTARG pvarg; // [rsp+60h] [rbp-39h] BYREF
  VARIANTARG v15; // [rsp+78h] [rbp-21h] BYREF
  _QWORD v16[4]; // [rsp+90h] [rbp-9h] BYREF
  GUID clsid; // [rsp+B0h] [rbp+17h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]

  *(_QWORD *)this = 0;
  clsid = 0;
  v3 = CLSIDFromProgID(L"Outlook.Application", &clsid);
  v4 = v3;
  if ( v3 >= 0 )
  {
    v13 = 0;
    v5 = CoCreateInstance(&clsid, 0, 4u, &GUID_00020400_0000_0000_c000_000000000046, &v13);
    v4 = v5;
    if ( v5 < 0 )
    {
      v6 = 81;
LABEL_7:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v6,
        (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.system\\launcher.cpp",
        (const char *)(unsigned int)v5,
        ppva);
LABEL_20:
      wil::com_ptr_t<Windows::Internal::Sustainability::IGridIntensityData,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Sustainability::IGridIntensityData,wil::err_exception_policy>(&v13);
      return v4;
    }
    v16[0] = L"GetNamespace";
    ppva = 1024;
    v5 = (*(__int64 (__fastcall **)(LPVOID, GUID *, _QWORD *, __int64))(*(_QWORD *)v13 + 40LL))(v13, &GUID_NULL, v16, 1);
    v4 = v5;
    if ( v5 < 0 )
    {
      v6 = 85;
      goto LABEL_7;
    }
    VariantInit(&pvarg);
    pvarg.vt = 8;
    pvarg.llVal = (LONGLONG)SysAllocString(L"MAPI");
    if ( !pvarg.llVal )
    {
      v4 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5A,
        (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.system\\launcher.cpp",
        (const char *)0x8007000ELL,
        1024);
LABEL_10:
      VariantClear(&pvarg);
      goto LABEL_20;
    }
    v16[2] = 0;
    v16[3] = 1;
    v16[1] = &pvarg;
    VariantInit(&v15);
    LOWORD(ppva) = 1;
    v7 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, GUID *, __int64))(*(_QWORD *)v13 + 48LL))(v13, 0, &GUID_NULL, 2048);
    v4 = v7;
    if ( v7 >= 0 )
    {
      if ( v15.vt != 9 )
      {
        v4 = -2147467259;
        v9 = 2147500037LL;
        v8 = 98;
        goto LABEL_14;
      }
      v7 = (**(__int64 (__fastcall ***)(LONGLONG, GUID *, winrt::WindowsUdk::System::implementation *))v15.llVal)(
             v15.llVal,
             &GUID_00020400_0000_0000_c000_000000000046,
             this);
      v4 = v7;
      if ( v7 >= 0 )
      {
        VariantClear(&v15);
        VariantClear(&pvarg);
        v4 = 0;
        goto LABEL_20;
      }
      v8 = 99;
    }
    else
    {
      v8 = 97;
    }
    v9 = (unsigned int)v7;
LABEL_14:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.system\\launcher.cpp",
      (const char *)v9,
      ppva);
    VariantClear(&v15);
    goto LABEL_10;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x4E,
    (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.system\\launcher.cpp",
    (const char *)(unsigned int)v3,
    ppv);
  return v4;
}

```

## disassembly

```asm
0x18031c6fc  push    rbp
0x18031c6fe  push    rbx
0x18031c6ff  push    rdi
0x18031c700  push    r14
0x18031c702  lea     rbp, [rsp-3Fh]
0x18031c707  sub     rsp, 0D8h
0x18031c70e  mov     rax, cs:__security_cookie
0x18031c715  xor     rax, rsp
0x18031c718  mov     [rbp+57h+var_30], rax
0x18031c71c  mov     rdi, rcx
0x18031c71f  mov     qword ptr [rcx], 0
0x18031c726  xorps   xmm0, xmm0
0x18031c729  movups  xmmword ptr [rbp+57h+clsid.Data1], xmm0
0x18031c72d  lea     rdx, [rbp+57h+clsid]; lpclsid
0x18031c731  lea     rcx, szProgID; "Outlook.Application"
0x18031c738  call    cs:__imp_CLSIDFromProgID
0x18031c73e  mov     ebx, eax
0x18031c740  test    eax, eax
0x18031c742  jns     short loc_18031C761
0x18031c744  mov     rcx, [rbp+5Fh]; this
0x18031c748  mov     r9d, eax; char *
0x18031c74b  lea     r8, aShellcommonUnd_134; "shellcommon\\undockeddevkit\\libs\\wind"...
0x18031c752  mov     edx, 4Eh ; 'N'; void *
0x18031c757  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18031c75c  jmp     loc_18031C94B
0x18031c761  mov     [rbp+57h+var_98], 0
0x18031c769  lea     rax, [rbp+57h+var_98]
0x18031c76d  mov     [rsp+0F0h+ppv], rax; ppv
0x18031c772  lea     r9, _GUID_00020400_0000_0000_c000_000000000046; riid
0x18031c779  xor     edx, edx; pUnkOuter
0x18031c77b  lea     r8d, [rdx+4]; dwClsContext
0x18031c77f  lea     rcx, [rbp+57h+clsid]; rclsid
0x18031c783  call    cs:__imp_CoCreateInstance
0x18031c789  mov     ebx, eax
0x18031c78b  test    eax, eax
0x18031c78d  jns     short loc_18031C796
0x18031c78f  mov     edx, 51h ; 'Q'
0x18031c794  jmp     short loc_18031C7E7
0x18031c796  mov     [rbp+57h+var_A0], 0
0x18031c79d  lea     rax, aGetnamespace; "GetNamespace"
0x18031c7a4  mov     [rbp+57h+var_60], rax
0x18031c7a8  mov     rcx, [rbp+57h+var_98]
0x18031c7ac  mov     rax, [rcx]
0x18031c7af  lea     rdx, [rbp+57h+var_A0]
0x18031c7b3  mov     [rsp+0F0h+var_C8], rdx
0x18031c7b8  mov     dword ptr [rsp+0F0h+ppv], 400h; int
0x18031c7c0  mov     r14d, 1
0x18031c7c6  mov     r9d, r14d
0x18031c7c9  lea     r8, [rbp+57h+var_60]
0x18031c7cd  lea     rdx, GUID_NULL
0x18031c7d4  mov     rax, [rax+28h]
0x18031c7d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18031c7dd  mov     ebx, eax
0x18031c7df  test    eax, eax
0x18031c7e1  jns     short loc_18031C7FF
0x18031c7e3  lea     edx, [r14+54h]; void *
0x18031c7e7  lea     r8, aShellcommonUnd_134; "shellcommon\\undockeddevkit\\libs\\wind"...
0x18031c7ee  mov     r9d, eax; char *
0x18031c7f1  mov     rcx, [rbp+5Fh]; this
0x18031c7f5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18031c7fa  jmp     loc_18031C942
0x18031c7ff  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18031c803  call    cs:__imp_VariantInit
0x18031c809  nop
0x18031c80a  mov     eax, 8
0x18031c80f  mov     word ptr [rbp+57h+pvarg], ax
0x18031c813  lea     rcx, psz; "MAPI"
0x18031c81a  call    cs:__imp_SysAllocString
0x18031c820  mov     qword ptr [rbp+57h+pvarg+8], rax
0x18031c824  test    rax, rax
0x18031c827  jnz     short loc_18031C854
0x18031c829  mov     rcx, [rbp+5Fh]; this
0x18031c82d  mov     ebx, 8007000Eh
0x18031c832  mov     r9d, ebx; char *
0x18031c835  lea     r8, aShellcommonUnd_134; "shellcommon\\undockeddevkit\\libs\\wind"...
0x18031c83c  lea     edx, [rax+5Ah]; void *
0x18031c83f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18031c844  nop
0x18031c845  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18031c849  call    cs:__imp_VariantClear
0x18031c84f  jmp     loc_18031C942
0x18031c854  mov     [rbp+57h+var_50], 0
0x18031c85c  mov     [rbp+57h+var_48], 1
0x18031c864  lea     rax, [rbp+57h+pvarg]
0x18031c868  mov     [rbp+57h+var_58], rax
0x18031c86c  lea     rcx, [rbp+57h+var_78]; pvarg
0x18031c870  call    cs:__imp_VariantInit
0x18031c876  nop
0x18031c877  mov     rcx, [rbp+57h+var_98]
0x18031c87b  mov     rax, [rcx]
0x18031c87e  mov     [rsp+0F0h+var_B0], 0
0x18031c887  mov     [rsp+0F0h+var_B8], 0
0x18031c890  lea     rdx, [rbp+57h+var_78]
0x18031c894  mov     [rsp+0F0h+var_C0], rdx
0x18031c899  lea     rdx, [rbp+57h+var_58]
0x18031c89d  mov     [rsp+0F0h+var_C8], rdx
0x18031c8a2  mov     word ptr [rsp+0F0h+ppv], r14w; int
0x18031c8a8  mov     r9d, 800h
0x18031c8ae  lea     r8, GUID_NULL
0x18031c8b5  mov     edx, [rbp+57h+var_A0]
0x18031c8b8  mov     rax, [rax+30h]
0x18031c8bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18031c8c1  mov     ebx, eax
0x18031c8c3  test    eax, eax
0x18031c8c5  jns     short loc_18031C8EF
0x18031c8c7  mov     edx, 61h ; 'a'; void *
0x18031c8cc  mov     r9d, eax; char *
0x18031c8cf  mov     rcx, [rbp+5Fh]; this
0x18031c8d3  lea     r8, aShellcommonUnd_134; "shellcommon\\undockeddevkit\\libs\\wind"...
0x18031c8da  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18031c8df  nop
0x18031c8e0  lea     rcx, [rbp+57h+var_78]; pvarg
0x18031c8e4  call    cs:__imp_VariantClear
0x18031c8ea  jmp     loc_18031C845
0x18031c8ef  cmp     word ptr [rbp+57h+var_78], 9
0x18031c8f4  jz      short loc_18031C905
0x18031c8f6  mov     ebx, 80004005h
0x18031c8fb  mov     r9d, ebx
0x18031c8fe  mov     edx, 62h ; 'b'
0x18031c903  jmp     short loc_18031C8CF
0x18031c905  mov     rcx, qword ptr [rbp+57h+var_78+8]
0x18031c909  mov     rax, [rcx]
0x18031c90c  mov     r8, rdi
0x18031c90f  lea     rdx, _GUID_00020400_0000_0000_c000_000000000046
0x18031c916  mov     rax, [rax]
0x18031c919  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18031c91e  mov     ebx, eax
0x18031c920  test    eax, eax
0x18031c922  jns     short loc_18031C92B
0x18031c924  mov     edx, 63h ; 'c'
0x18031c929  jmp     short loc_18031C8CC
0x18031c92b  lea     rcx, [rbp+57h+var_78]; pvarg
0x18031c92f  call    cs:__imp_VariantClear
0x18031c935  nop
0x18031c936  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18031c93a  call    cs:__imp_VariantClear
0x18031c940  xor     ebx, ebx
0x18031c942  lea     rcx, [rbp+57h+var_98]
0x18031c946  call    ??1?$com_ptr_t@UIGridIntensityData@Sustainability@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::Sustainability::IGridIntensityData,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Sustainability::IGridIntensityData,wil::err_exception_policy>(void)
0x18031c94b  mov     eax, ebx
0x18031c94d  mov     rcx, [rbp+57h+var_30]
0x18031c951  xor     rcx, rsp; StackCookie
0x18031c954  call    __security_check_cookie
0x18031c959  add     rsp, 0D8h
0x18031c960  pop     r14
0x18031c962  pop     rdi
0x18031c963  pop     rbx
0x18031c964  pop     rbp
0x18031c965  retn
```
