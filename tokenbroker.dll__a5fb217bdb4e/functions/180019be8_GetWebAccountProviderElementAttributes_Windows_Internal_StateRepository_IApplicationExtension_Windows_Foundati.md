# _GetWebAccountProviderElementAttributes(Windows::Internal::StateRepository::IApplicationExtension *,Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> * *)

- ea: `0x180019be8`
- end: `0x180019f04`
- name: `?_GetWebAccountProviderElementAttributes@@YAJPEAUIApplicationExtension@StateRepository@Internal@Windows@@PEAPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@4@@Z`
- size: `796`
- prototype: ``
- caller_count: `4`
- callee_count: `7`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180011400`
- `0x180019a2c`
- `0x180065764`
- `0x18009e208`

## callees

- `0x180007350`
- `0x18000bd40`
- `0x180019be8`
- `0x180019f0c`
- `0x18005e730`
- `0x18008e690`
- `0x18011b010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180019e7d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180019e7d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180019cfe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180019cfe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019e66`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019ee7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019eef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019e66`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019ee7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019eef`
- `ext-ms-onecore-appmodel-staterepository-internal-l1-1-3!SRDictionaryToPropertySet` at `0x180019c84`
- `ext-ms-onecore-appmodel-staterepository-internal-l1-1-3!SRDictionaryToPropertySet` at `0x180019c84`

## string_xrefs

- `0x180019e8f`: `onecore\ds\security\tokenbroker\broker\lib\wamproviderregistration.cpp`
- `0x180019eb9`: `onecore\ds\security\tokenbroker\broker\lib\wamproviderregistration.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall _GetWebAccountProviderElementAttributes(__int64 *a1, HSTRING *a2)
{
  __int64 v3; // rax
  int v4; // ebx
  void *v5; // rcx
  int v6; // eax
  __int64 (__fastcall ***v7)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v8)(_QWORD, GUID *, __int64 *); // rdi
  int Inspectable; // edi
  __int64 v10; // rbx
  __int64 (__fastcall *v11)(__int64, HSTRING, struct IInspectable **); // rdi
  struct IInspectable *v12; // rbx
  HRESULT (__stdcall *QueryInterface)(IInspectable *, const IID *const, void **); // rdi
  HSTRING v14; // rcx
  struct IInspectable *v15; // rcx
  __int64 v16; // rcx
  __int64 (__fastcall ***v17)(_QWORD, _QWORD, _QWORD); // rcx
  void *v18; // rcx
  void *v20; // rcx
  __int64 (__fastcall ***v21)(_QWORD, _QWORD, _QWORD); // rcx
  LPVOID pv; // [rsp+20h] [rbp-29h] BYREF
  __int64 (__fastcall ***v23)(_QWORD, GUID *, __int64 *); // [rsp+28h] [rbp-21h] BYREF
  unsigned int v24; // [rsp+30h] [rbp-19h] BYREF
  __int64 v25; // [rsp+38h] [rbp-11h] BYREF
  struct IInspectable *p_p_pv; // [rsp+40h] [rbp-9h] BYREF
  struct IInspectable *v27; // [rsp+48h] [rbp-1h] BYREF
  LPVOID *p_pv; // [rsp+50h] [rbp+7h] BYREF
  void *v29; // [rsp+58h] [rbp+Fh] BYREF
  char v30; // [rsp+60h] [rbp+17h]
  HSTRING string; // [rsp+68h] [rbp+1Fh] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+70h] [rbp+27h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+5Fh]

  v24 = 0;
  pv = 0;
  v3 = *a1;
  p_pv = &pv;
  v29 = 0;
  v30 = 1;
  v4 = (*(__int64 (__fastcall **)(__int64 *, unsigned int *, void **))(v3 + 512))(a1, &v24, &v29);
  if ( v30 )
  {
    v5 = *p_pv;
    *p_pv = v29;
    if ( v5 )
      CoTaskMemFree(v5);
  }
  if ( v4 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x41,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\wamproviderregistration.cpp",
      (const char *)(unsigned int)v4,
      (int)pv);
  }
  else
  {
    v23 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v23);
    v6 = SRDictionaryToPropertySet(v24, pv, &v23);
    v4 = v6;
    if ( v6 >= 0 )
    {
      v25 = 0;
      v7 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v23;
      v8 = **v23;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v25);
      Inspectable = v8(v7, &GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca, &v25);
      if ( Inspectable >= 0 )
      {
        p_pv = 0;
        LODWORD(v29) = 0;
        v10 = v25;
        v11 = *(__int64 (__fastcall **)(__int64, HSTRING, struct IInspectable **))(*(_QWORD *)v25 + 48LL);
        p_p_pv = (struct IInspectable *)&p_pv;
        v27 = 0;
        if ( WindowsCreateStringReference(L"WebAccountProvider", 0x12u, &hstringHeader, &string) < 0 )
          RaiseException(0xC000000D, 1u, 0, 0);
        Inspectable = v11(v10, string, &v27);
        RoVariant::Attach((RoVariant *)p_p_pv, v27);
        if ( Inspectable >= 0 )
        {
          p_p_pv = 0;
          string = (HSTRING)p_pv;
          LODWORD(hstringHeader.Reserved.Reserved1) = (_DWORD)v29;
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&p_p_pv);
          Inspectable = RoVariant::Accessor::GetInspectable((RoVariant::Accessor *)&string, &p_p_pv);
          if ( Inspectable >= 0 )
          {
            string = 0;
            v12 = p_p_pv;
            QueryInterface = p_p_pv->lpVtbl->QueryInterface;
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&string);
            Inspectable = ((__int64 (__fastcall *)(struct IInspectable *, GUID *, HSTRING *))QueryInterface)(
                            v12,
                            &GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca,
                            &string);
            if ( Inspectable < 0 )
            {
              v14 = string;
            }
            else
            {
              v14 = 0;
              *a2 = string;
            }
            if ( v14 )
            {
              string = 0;
              (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v14 + 16LL))(v14);
            }
          }
          v15 = p_p_pv;
          if ( p_p_pv )
          {
            p_p_pv = 0;
            ((void (__fastcall *)(struct IInspectable *))v15->lpVtbl->Release)(v15);
          }
        }
        if ( p_pv && (((_DWORD)v29 - 3) & 0xFFFFFFFB) == 0 )
          (*((void (**)(void))*p_pv + 2))();
      }
      v16 = v25;
      if ( v25 )
      {
        v25 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
      }
      v17 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v23;
      if ( v23 )
      {
        v23 = 0;
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v17)[2])(v17);
      }
      v18 = pv;
      pv = 0;
      if ( v18 )
        CoTaskMemFree(v18);
      return (unsigned int)Inspectable;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x43,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\wamproviderregistration.cpp",
      (const char *)(unsigned int)v6,
      (int)pv);
    v21 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v23;
    if ( v23 )
    {
      v23 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v21)[2])(v21);
    }
  }
  v20 = pv;
  pv = 0;
  if ( v20 )
    CoTaskMemFree(v20);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180019be8  mov     [rsp-8+arg_10], rbx
0x180019bed  mov     [rsp-8+arg_18], rsi
0x180019bf2  push    rbp
0x180019bf3  push    rdi
0x180019bf4  push    r14
0x180019bf6  lea     rbp, [rsp-47h]
0x180019bfb  sub     rsp, 90h
0x180019c02  mov     rax, cs:__security_cookie
0x180019c09  xor     rax, rsp
0x180019c0c  mov     [rbp+57h+var_18], rax
0x180019c10  mov     rsi, rdx
0x180019c13  xor     r14d, r14d
0x180019c16  mov     [rbp+57h+var_70], r14d
0x180019c1a  mov     [rbp+57h+pv], r14
0x180019c1e  mov     rax, [rcx]
0x180019c21  lea     rdx, [rbp+57h+pv]
0x180019c25  mov     [rbp+57h+var_50], rdx
0x180019c29  mov     [rbp+57h+var_48], r14
0x180019c2d  mov     [rbp+57h+var_40], 1
0x180019c31  lea     r8, [rbp+57h+var_48]
0x180019c35  lea     rdx, [rbp+57h+var_70]
0x180019c39  mov     rax, [rax+200h]
0x180019c40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019c45  mov     ebx, eax
0x180019c47  cmp     [rbp+57h+var_40], r14b
0x180019c4b  jz      short loc_180019C64
0x180019c4d  mov     r8, [rbp+57h+var_50]
0x180019c51  mov     rcx, [r8]; pv
0x180019c54  mov     rdx, [rbp+57h+var_48]
0x180019c58  mov     [r8], rdx
0x180019c5b  test    rcx, rcx
0x180019c5e  jnz     loc_180019EEF
0x180019c64  test    ebx, ebx
0x180019c66  js      loc_180019E88
0x180019c6c  mov     [rbp+57h+var_78], r14
0x180019c70  lea     rcx, [rbp+57h+var_78]
0x180019c74  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180019c79  lea     r8, [rbp+57h+var_78]
0x180019c7d  mov     rdx, [rbp+57h+pv]
0x180019c81  mov     ecx, [rbp+57h+var_70]
0x180019c84  call    cs:__imp_SRDictionaryToPropertySet
0x180019c8a  mov     ebx, eax
0x180019c8c  test    eax, eax
0x180019c8e  js      loc_180019EB2
0x180019c94  mov     [rbp+57h+var_68], r14
0x180019c98  mov     rbx, [rbp+57h+var_78]
0x180019c9c  mov     rax, [rbx]
0x180019c9f  mov     rdi, [rax]
0x180019ca2  lea     rcx, [rbp+57h+var_68]
0x180019ca6  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180019cab  lea     r8, [rbp+57h+var_68]
0x180019caf  lea     rdx, _GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca
0x180019cb6  mov     rcx, rbx
0x180019cb9  mov     rax, rdi
0x180019cbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019cc1  mov     edi, eax
0x180019cc3  test    eax, eax
0x180019cc5  js      loc_180019DFF
0x180019ccb  mov     [rbp+57h+var_50], r14
0x180019ccf  mov     dword ptr [rbp+57h+var_48], r14d
0x180019cd3  mov     rbx, [rbp+57h+var_68]
0x180019cd7  mov     rax, [rbx]
0x180019cda  mov     rdi, [rax+30h]
0x180019cde  lea     rax, [rbp+57h+var_50]
0x180019ce2  mov     [rbp+57h+var_60], rax
0x180019ce6  mov     [rbp+57h+var_58], r14
0x180019cea  lea     r9, [rbp+57h+string]; string
0x180019cee  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x180019cf2  mov     edx, 12h; length
0x180019cf7  lea     rcx, aWebaccountprov; "WebAccountProvider"
0x180019cfe  call    cs:__imp_WindowsCreateStringReference
0x180019d04  test    eax, eax
0x180019d06  js      loc_180019E6E
0x180019d0c  lea     r8, [rbp+57h+var_58]
0x180019d10  mov     rdx, [rbp+57h+string]
0x180019d14  mov     rcx, rbx
0x180019d17  mov     rax, rdi
0x180019d1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019d1f  mov     edi, eax
0x180019d21  mov     ebx, eax
0x180019d23  shr     ebx, 1Fh
0x180019d26  mov     rdx, [rbp+57h+var_58]; struct IInspectable *
0x180019d2a  mov     rcx, [rbp+57h+var_60]; this
0x180019d2e  call    ?Attach@RoVariant@@QEAAXPEAUIInspectable@@@Z; RoVariant::Attach(IInspectable *)
0x180019d33  nop
0x180019d34  xor     bl, 1
0x180019d37  jz      loc_180019DDC
0x180019d3d  mov     [rbp+57h+var_60], r14
0x180019d41  mov     rax, [rbp+57h+var_50]
0x180019d45  mov     [rbp+57h+string], rax
0x180019d49  mov     eax, dword ptr [rbp+57h+var_48]
0x180019d4c  mov     dword ptr [rbp+57h+hstringHeader.Reserved], eax
0x180019d4f  lea     rcx, [rbp+57h+var_60]
0x180019d53  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180019d58  lea     rdx, [rbp+57h+var_60]; struct IInspectable **
0x180019d5c  lea     rcx, [rbp+57h+string]; this
0x180019d60  call    ?GetInspectable@Accessor@RoVariant@@QEBAJPEAPEAUIInspectable@@@Z; RoVariant::Accessor::GetInspectable(IInspectable * *)
0x180019d65  mov     edi, eax
0x180019d67  test    eax, eax
0x180019d69  js      short loc_180019DC2
0x180019d6b  mov     [rbp+57h+string], r14
0x180019d6f  mov     rbx, [rbp+57h+var_60]
0x180019d73  mov     rax, [rbx]
0x180019d76  mov     rdi, [rax]
0x180019d79  lea     rcx, [rbp+57h+string]
0x180019d7d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180019d82  lea     r8, [rbp+57h+string]
0x180019d86  lea     rdx, _GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca
0x180019d8d  mov     rcx, rbx
0x180019d90  mov     rax, rdi
0x180019d93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019d98  mov     edi, eax
0x180019d9a  test    eax, eax
0x180019d9c  js      loc_180019EFA
0x180019da2  mov     rax, [rbp+57h+string]
0x180019da6  mov     rcx, r14
0x180019da9  mov     [rsi], rax
0x180019dac  test    rcx, rcx
0x180019daf  jz      short loc_180019DC2
0x180019db1  mov     [rbp+57h+string], r14
0x180019db5  mov     rax, [rcx]
0x180019db8  mov     rax, [rax+10h]
0x180019dbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019dc1  nop
0x180019dc2  mov     rcx, [rbp+57h+var_60]
0x180019dc6  test    rcx, rcx
0x180019dc9  jz      short loc_180019DDC
0x180019dcb  mov     [rbp+57h+var_60], r14
0x180019dcf  mov     rax, [rcx]
0x180019dd2  mov     rax, [rax+10h]
0x180019dd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019ddb  nop
0x180019ddc  mov     rcx, [rbp+57h+var_50]
0x180019de0  test    rcx, rcx
0x180019de3  jz      short loc_180019DFF
0x180019de5  mov     eax, dword ptr [rbp+57h+var_48]
0x180019de8  add     eax, 0FFFFFFFDh
0x180019deb  test    eax, 0FFFFFFFBh
0x180019df0  jnz     short loc_180019DFF
0x180019df2  mov     rax, [rcx]
0x180019df5  mov     rax, [rax+10h]
0x180019df9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019dfe  nop
0x180019dff  mov     rcx, [rbp+57h+var_68]
0x180019e03  test    rcx, rcx
0x180019e06  jz      short loc_180019E19
0x180019e08  mov     [rbp+57h+var_68], r14
0x180019e0c  mov     rax, [rcx]
0x180019e0f  mov     rax, [rax+10h]
0x180019e13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019e18  nop
0x180019e19  mov     rcx, [rbp+57h+var_78]
0x180019e1d  test    rcx, rcx
0x180019e20  jz      short loc_180019E33
0x180019e22  mov     [rbp+57h+var_78], r14
0x180019e26  mov     rax, [rcx]
0x180019e29  mov     rax, [rax+10h]
0x180019e2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019e32  nop
0x180019e33  mov     rcx, [rbp+57h+pv]; pv
0x180019e37  mov     [rbp+57h+pv], r14
0x180019e3b  test    rcx, rcx
0x180019e3e  jnz     short loc_180019E66
0x180019e40  mov     eax, edi
0x180019e42  mov     rcx, [rbp+57h+var_18]
0x180019e46  xor     rcx, rsp; StackCookie
0x180019e49  call    __security_check_cookie
0x180019e4e  lea     r11, [rsp+0A0h+var_10]
0x180019e56  mov     rbx, [r11+30h]
0x180019e5a  mov     rsi, [r11+38h]
0x180019e5e  mov     rsp, r11
0x180019e61  pop     r14
0x180019e63  pop     rdi
0x180019e64  pop     rbp
0x180019e65  retn
0x180019e66  call    cs:__imp_CoTaskMemFree
0x180019e6c  jmp     short loc_180019E40
0x180019e6e  xor     r9d, r9d; lpArguments
0x180019e71  xor     r8d, r8d; nNumberOfArguments
0x180019e74  lea     edx, [r9+1]; dwExceptionFlags
0x180019e78  mov     ecx, 0C000000Dh; dwExceptionCode
0x180019e7d  call    cs:__imp_RaiseException
0x180019e83  jmp     loc_180019D0C
0x180019e88  mov     rcx, [rbp+5Fh]; this
0x180019e8c  mov     r9d, ebx; char *
0x180019e8f  lea     r8, aOnecoreDsSecur_16; "onecore\\ds\\security\\tokenbroker\\bro"...
0x180019e96  mov     edx, 41h ; 'A'; void *
0x180019e9b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019ea0  nop
0x180019ea1  mov     rcx, [rbp+57h+pv]; pv
0x180019ea5  mov     [rbp+57h+pv], r14
0x180019ea9  test    rcx, rcx
0x180019eac  jnz     short loc_180019EE7
0x180019eae  mov     eax, ebx
0x180019eb0  jmp     short loc_180019E42
0x180019eb2  mov     rcx, [rbp+5Fh]; this
0x180019eb6  mov     r9d, ebx; char *
0x180019eb9  lea     r8, aOnecoreDsSecur_16; "onecore\\ds\\security\\tokenbroker\\bro"...
0x180019ec0  mov     edx, 43h ; 'C'; void *
0x180019ec5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019eca  nop
0x180019ecb  mov     rcx, [rbp+57h+var_78]
0x180019ecf  test    rcx, rcx
0x180019ed2  jz      short loc_180019EE5
0x180019ed4  mov     [rbp+57h+var_78], r14
0x180019ed8  mov     rax, [rcx]
0x180019edb  mov     rax, [rax+10h]
0x180019edf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019ee4  nop
0x180019ee5  jmp     short loc_180019EA1
0x180019ee7  call    cs:__imp_CoTaskMemFree
0x180019eed  jmp     short loc_180019EAE
0x180019eef  call    cs:__imp_CoTaskMemFree
0x180019ef5  jmp     loc_180019C64
0x180019efa  mov     rcx, [rbp+57h+string]
0x180019efe  jmp     loc_180019DAC
```
