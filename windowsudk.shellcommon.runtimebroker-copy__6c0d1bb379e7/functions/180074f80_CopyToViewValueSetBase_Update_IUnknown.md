# CopyToViewValueSetBase::Update(IUnknown *)

- ea: `0x180074f80`
- end: `0x180075271`
- name: `?Update@CopyToViewValueSetBase@@UEAAJPEAUIUnknown@@@Z`
- size: `753`
- prototype: `__int64 __fastcall(CopyToViewValueSetBase *__hidden this, struct IUnknown *)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x18002e634`
- `0x180044668`
- `0x180074f50`
- `0x180074f80`
- `0x180075278`
- `0x180075318`
- `0x1800e34bc`
- `0x1804a2010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180075025`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800750b6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180075165`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800751d1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180075232`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180075025`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800750b6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180075165`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800751d1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180075232`

## string_xrefs

- `0x18007511d`: `shellcommon\internal\composable\inc\CopyToViewValueSet.h`
- `0x180075150`: `shellcommon\internal\composable\inc\CopyToViewValueSet.h`
- `0x1800751a5`: `shellcommon\internal\composable\inc\CopyToViewValueSet.h`
- `0x180075214`: `shellcommon\internal\composable\inc\CopyToViewValueSet.h`
- `0x180075252`: `shellcommon\internal\composable\inc\CopyToViewValueSet.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CopyToViewValueSetBase::Update(CopyToViewValueSetBase *this, struct IUnknown *a2)
{
  struct IUnknownVtbl *lpVtbl; // rax
  int v4; // eax
  unsigned int v5; // ebx
  __int64 *v6; // rsi
  int v7; // edx
  __int64 v8; // rdi
  __int64 (__fastcall *v9)(__int64, HSTRING *); // rbx
  int v10; // eax
  int v11; // eax
  int v12; // eax
  int v14; // [rsp+20h] [rbp-50h]
  __int64 v15; // [rsp+30h] [rbp-40h] BYREF
  __int64 v16; // [rsp+38h] [rbp-38h] BYREF
  __int64 *v17; // [rsp+40h] [rbp-30h] BYREF
  int v18; // [rsp+48h] [rbp-28h]
  __int64 v19; // [rsp+50h] [rbp-20h] BYREF
  _BYTE v20[24]; // [rsp+58h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+18h]
  char v22; // [rsp+98h] [rbp+28h] BYREF
  char *v23; // [rsp+A0h] [rbp+30h] BYREF
  HSTRING string; // [rsp+A8h] [rbp+38h] BYREF

  lpVtbl = a2->lpVtbl;
  v15 = 0;
  v4 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int64 *))lpVtbl->QueryInterface)(
         a2,
         &GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca,
         &v15);
  v5 = v4;
  if ( v4 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x49,
      (unsigned int)"shellcommon\\internal\\composable\\inc\\CopyToViewValueSet.h",
      (const char *)(unsigned int)v4,
      v14);
    if ( v15 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
    return v5;
  }
  else
  {
    LODWORD(v23) = 0;
    wil::iterable_range_nothrow<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>::iterable_range_nothrow<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>(
      &v19,
      *((_QWORD *)this + 7),
      &v23);
    v6 = &v19;
    v17 = &v19;
    v7 = (v19 != 0) - 1;
    v18 = v7;
    while ( v7 != -1 && *(int *)v6[2] >= 0 )
    {
      string = 0;
      v8 = v6[1];
      v9 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v8 + 48LL);
      WindowsDeleteString(0);
      string = 0;
      v10 = v9(v8, &string);
      v5 = v10;
      if ( v10 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x4F,
          (unsigned int)"shellcommon\\internal\\composable\\inc\\CopyToViewValueSet.h",
          (const char *)(unsigned int)v10,
          v14);
        WindowsDeleteString(string);
        string = 0;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v20);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v19);
        if ( v15 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
        return v5;
      }
      v16 = 0;
      v11 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v6[1] + 56LL))(v6[1], &v16);
      v5 = v11;
      if ( v11 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x51,
          (unsigned int)"shellcommon\\internal\\composable\\inc\\CopyToViewValueSet.h",
          (const char *)(unsigned int)v11,
          v14);
        wil::com_ptr_t<Windows::Internal::Sustainability::IGridIntensityData,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Sustainability::IGridIntensityData,wil::err_exception_policy>(&v16);
        WindowsDeleteString(string);
        string = 0;
        wil::iterable_range_nothrow<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>::~iterable_range_nothrow<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>(&v19);
LABEL_28:
        wil::com_ptr_t<Windows::Internal::Sustainability::IGridIntensityData,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Sustainability::IGridIntensityData,wil::err_exception_policy>(&v15);
        return v5;
      }
      v22 = 0;
      v12 = (*(__int64 (__fastcall **)(__int64, HSTRING, __int64, char *))(*(_QWORD *)v15 + 80LL))(
              v15,
              string,
              v16,
              &v22);
      v5 = v12;
      if ( v12 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x54,
          (unsigned int)"shellcommon\\internal\\composable\\inc\\CopyToViewValueSet.h",
          (const char *)(unsigned int)v12,
          v14);
        if ( v16 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
        WindowsDeleteString(string);
        string = 0;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v20);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v19);
        if ( v15 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
        return v5;
      }
      if ( v16 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
      WindowsDeleteString(string);
      wil::iterable_range_nothrow<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>::iterable_iterator_nothrow::operator++(&v17);
      v7 = v18;
      v6 = v17;
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v20);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v19);
    v5 = (unsigned int)v23;
    if ( (int)v23 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x56,
        (unsigned int)"shellcommon\\internal\\composable\\inc\\CopyToViewValueSet.h",
        (const char *)(unsigned int)v23,
        v14);
      goto LABEL_28;
    }
    if ( v15 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
    return 0;
  }
}

```

## disassembly

```asm
0x180074f80  mov     [rsp-18h+arg_0], rbx
0x180074f85  push    rbp
0x180074f86  push    rsi
0x180074f87  push    rdi
0x180074f88  mov     rbp, rsp
0x180074f8b  sub     rsp, 70h
0x180074f8f  mov     r9, rdx
0x180074f92  mov     rdi, rcx
0x180074f95  mov     rax, [rdx]
0x180074f98  mov     [rbp+var_40], 0
0x180074fa0  lea     r8, [rbp+var_40]
0x180074fa4  lea     rdx, _GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca
0x180074fab  mov     rcx, r9
0x180074fae  mov     rax, [rax]
0x180074fb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180074fb6  mov     ebx, eax
0x180074fb8  test    eax, eax
0x180074fba  js      loc_180075116
0x180074fc0  mov     dword ptr [rbp+arg_10], 0
0x180074fc7  lea     r8, [rbp+arg_10]
0x180074fcb  mov     rdx, [rdi+38h]
0x180074fcf  lea     rcx, [rbp+var_20]
0x180074fd3  call    ??0?$iterable_range_nothrow@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@wil@@QEAA@PEAU?$IIterable@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@Collections@Foundation@Windows@@PEAJ@Z; wil::iterable_range_nothrow<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>::iterable_range_nothrow<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>(Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *> *,long *)
0x180074fd8  mov     rax, [rbp+var_20]
0x180074fdc  neg     rax
0x180074fdf  sbb     ecx, ecx
0x180074fe1  neg     ecx
0x180074fe3  dec     ecx
0x180074fe5  lea     rsi, [rbp+var_20]
0x180074fe9  mov     [rbp+var_30], rsi
0x180074fed  xor     edx, edx
0x180074fef  cmp     ecx, 0FFFFFFFFh
0x180074ff2  setnz   dl
0x180074ff5  dec     edx
0x180074ff7  mov     [rbp+var_28], edx
0x180074ffa  mov     rax, [rsi+10h]
0x180074ffe  cmp     edx, 0FFFFFFFFh
0x180075001  jz      loc_1800750D1
0x180075007  cmp     dword ptr [rax], 0
0x18007500a  jl      loc_1800750D1
0x180075010  mov     [rbp+string], 0
0x180075018  mov     rdi, [rsi+8]
0x18007501c  mov     rax, [rdi]
0x18007501f  mov     rbx, [rax+30h]
0x180075023  xor     ecx, ecx; string
0x180075025  call    cs:__imp_WindowsDeleteString
0x18007502b  mov     [rbp+string], 0
0x180075033  lea     rdx, [rbp+string]
0x180075037  mov     rcx, rdi
0x18007503a  mov     rax, rbx
0x18007503d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075042  mov     ebx, eax
0x180075044  test    eax, eax
0x180075046  js      loc_180075149
0x18007504c  mov     [rbp+var_38], 0
0x180075054  mov     rcx, [rsi+8]
0x180075058  mov     rax, [rcx]
0x18007505b  lea     rdx, [rbp+var_38]
0x18007505f  mov     rax, [rax+38h]
0x180075063  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075068  mov     ebx, eax
0x18007506a  test    eax, eax
0x18007506c  js      loc_18007520D
0x180075072  mov     [rbp+arg_8], 0
0x180075076  mov     rcx, [rbp+var_40]
0x18007507a  mov     rax, [rcx]
0x18007507d  lea     r9, [rbp+arg_8]
0x180075081  mov     r8, [rbp+var_38]
0x180075085  mov     rdx, [rbp+string]
0x180075089  mov     rax, [rax+50h]
0x18007508d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075092  mov     ebx, eax
0x180075094  test    eax, eax
0x180075096  js      loc_18007519E
0x18007509c  mov     rcx, [rbp+var_38]
0x1800750a0  test    rcx, rcx
0x1800750a3  jz      short loc_1800750B2
0x1800750a5  mov     rax, [rcx]
0x1800750a8  mov     rax, [rax+10h]
0x1800750ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800750b1  nop
0x1800750b2  mov     rcx, [rbp+string]; string
0x1800750b6  call    cs:__imp_WindowsDeleteString
0x1800750bc  lea     rcx, [rbp+var_30]
0x1800750c0  call    ??Eiterable_iterator_nothrow@?$iterable_range_nothrow@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@wil@@QEAAAEAV012@XZ; wil::iterable_range_nothrow<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>::iterable_iterator_nothrow::operator++(void)
0x1800750c5  mov     edx, [rbp+var_28]
0x1800750c8  mov     rsi, [rbp+var_30]
0x1800750cc  jmp     loc_180074FFA
0x1800750d1  lea     rcx, [rbp+var_18]
0x1800750d5  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800750da  lea     rcx, [rbp+var_20]
0x1800750de  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800750e3  mov     ebx, dword ptr [rbp+arg_10]
0x1800750e6  test    ebx, ebx
0x1800750e8  js      loc_18007524B
0x1800750ee  mov     rcx, [rbp+var_40]
0x1800750f2  test    rcx, rcx
0x1800750f5  jz      short loc_180075104
0x1800750f7  mov     rax, [rcx]
0x1800750fa  mov     rax, [rax+10h]
0x1800750fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075103  nop
0x180075104  xor     eax, eax
0x180075106  mov     rbx, [rsp+70h+arg_0]
0x18007510e  add     rsp, 70h
0x180075112  pop     rdi
0x180075113  pop     rsi
0x180075114  pop     rbp
0x180075115  retn
0x180075116  mov     rcx, [rbp+18h]; this
0x18007511a  mov     r9d, ebx; char *
0x18007511d  lea     r8, aShellcommonInt_4; "shellcommon\\internal\\composable\\inc"...
0x180075124  mov     edx, 49h ; 'I'; void *
0x180075129  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007512e  nop
0x18007512f  mov     rcx, [rbp+var_40]
0x180075133  test    rcx, rcx
0x180075136  jz      short loc_180075145
0x180075138  mov     rax, [rcx]
0x18007513b  mov     rax, [rax+10h]
0x18007513f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075144  nop
0x180075145  mov     eax, ebx
0x180075147  jmp     short loc_180075106
0x180075149  mov     rcx, [rbp+18h]; this
0x18007514d  mov     r9d, ebx; char *
0x180075150  lea     r8, aShellcommonInt_4; "shellcommon\\internal\\composable\\inc"...
0x180075157  mov     edx, 4Fh ; 'O'; void *
0x18007515c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180075161  mov     rcx, [rbp+string]; string
0x180075165  call    cs:__imp_WindowsDeleteString
0x18007516b  mov     [rbp+string], 0
0x180075173  lea     rcx, [rbp+var_18]
0x180075177  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18007517c  lea     rcx, [rbp+var_20]
0x180075180  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180075185  nop
0x180075186  mov     rcx, [rbp+var_40]
0x18007518a  test    rcx, rcx
0x18007518d  jz      short loc_18007519C
0x18007518f  mov     rax, [rcx]
0x180075192  mov     rax, [rax+10h]
0x180075196  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007519b  nop
0x18007519c  jmp     short loc_180075145
0x18007519e  mov     rcx, [rbp+18h]; this
0x1800751a2  mov     r9d, ebx; char *
0x1800751a5  lea     r8, aShellcommonInt_4; "shellcommon\\internal\\composable\\inc"...
0x1800751ac  mov     edx, 54h ; 'T'; void *
0x1800751b1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800751b6  nop
0x1800751b7  mov     rcx, [rbp+var_38]
0x1800751bb  test    rcx, rcx
0x1800751be  jz      short loc_1800751CD
0x1800751c0  mov     rax, [rcx]
0x1800751c3  mov     rax, [rax+10h]
0x1800751c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800751cc  nop
0x1800751cd  mov     rcx, [rbp+string]; string
0x1800751d1  call    cs:__imp_WindowsDeleteString
0x1800751d7  mov     [rbp+string], 0
0x1800751df  lea     rcx, [rbp+var_18]
0x1800751e3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800751e8  lea     rcx, [rbp+var_20]
0x1800751ec  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800751f1  nop
0x1800751f2  mov     rcx, [rbp+var_40]
0x1800751f6  test    rcx, rcx
0x1800751f9  jz      short loc_180075208
0x1800751fb  mov     rax, [rcx]
0x1800751fe  mov     rax, [rax+10h]
0x180075202  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075207  nop
0x180075208  jmp     loc_180075145
0x18007520d  mov     rcx, [rbp+18h]; this
0x180075211  mov     r9d, eax; char *
0x180075214  lea     r8, aShellcommonInt_4; "shellcommon\\internal\\composable\\inc"...
0x18007521b  mov     edx, 51h ; 'Q'; void *
0x180075220  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180075225  lea     rcx, [rbp+var_38]
0x180075229  call    ??1?$com_ptr_t@UIGridIntensityData@Sustainability@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::Sustainability::IGridIntensityData,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Sustainability::IGridIntensityData,wil::err_exception_policy>(void)
0x18007522e  mov     rcx, [rbp+string]; string
0x180075232  call    cs:__imp_WindowsDeleteString
0x180075238  mov     [rbp+string], 0
0x180075240  lea     rcx, [rbp+var_20]
0x180075244  call    ??1?$iterable_range_nothrow@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@wil@@QEAA@XZ; wil::iterable_range_nothrow<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>::~iterable_range_nothrow<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>(void)
0x180075249  jmp     short loc_180075263
0x18007524b  mov     rcx, [rbp+18h]; this
0x18007524f  mov     r9d, ebx; char *
0x180075252  lea     r8, aShellcommonInt_4; "shellcommon\\internal\\composable\\inc"...
0x180075259  mov     edx, 56h ; 'V'; void *
0x18007525e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180075263  lea     rcx, [rbp+var_40]
0x180075267  call    ??1?$com_ptr_t@UIGridIntensityData@Sustainability@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::Sustainability::IGridIntensityData,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Sustainability::IGridIntensityData,wil::err_exception_policy>(void)
0x18007526c  jmp     loc_180075145
```
