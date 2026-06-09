# Windows::Internal::Notifications::Utilities::InsertBoolIntoPropertySet(Windows::Foundation::Collections::IPropertySet *,ushort const *,bool)

- ea: `0x180010800`
- end: `0x180010a4b`
- name: `?InsertBoolIntoPropertySet@Utilities@Notifications@Internal@Windows@@SAXPEAUIPropertySet@Collections@Foundation@4@PEBG_N@Z`
- size: `587`
- prototype: `void __fastcall(struct Windows::Foundation::Collections::IPropertySet *, const unsigned __int16 *, bool)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180010770`

## callees

- `0x180010800`
- `0x18001b848`
- `0x18001ff00`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800109dc`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180010a2f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800109dc`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180010a2f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180010845`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180010924`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180010845`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180010924`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001087f`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001087f`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
void __fastcall Windows::Internal::Notifications::Utilities::InsertBoolIntoPropertySet(
        struct Windows::Foundation::Collections::IPropertySet *a1,
        const unsigned __int16 *a2)
{
  HRESULT v3; // eax
  int ActivationFactory; // eax
  __int64 v5; // rdx
  wil::details::in1diag3 *v6; // rcx
  int v7; // eax
  int v8; // eax
  _QWORD *v9; // rdi
  __int64 v10; // rsi
  __int64 v11; // r14
  HRESULT v12; // eax
  int v13; // eax
  wil::details::in1diag3 *v14; // rcx
  _QWORD *v15; // rcx
  __int64 v16; // rcx
  __int64 v17; // rcx
  int v18; // [rsp+20h] [rbp-39h]
  _BYTE v19[8]; // [rsp+30h] [rbp-29h] BYREF
  __int64 v20; // [rsp+38h] [rbp-21h] BYREF
  _QWORD *v21; // [rsp+40h] [rbp-19h] BYREF
  _QWORD v22[2]; // [rsp+48h] [rbp-11h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+58h] [rbp-1h] BYREF
  HSTRING string; // [rsp+70h] [rbp+17h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]

  v20 = 0;
  string = 0;
  v3 = WindowsCreateStringReference(L"Windows.Foundation.PropertyValue", 0x20u, &hstringHeader, &string);
  if ( v3 < 0 )
  {
    RaiseException(v3, 1u, 0, 0);
LABEL_17:
    wil::details::in1diag3::Throw_Hr(
      v6,
      (void *)0x11,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\src\\Utilities.h",
      (const char *)(unsigned int)ActivationFactory,
      v18);
  }
  ActivationFactory = RoGetActivationFactory(string, &GUID_629bdbc8_d932_4ff4_96b9_8d96c5c1e858, &v20);
  v6 = retaddr;
  if ( ActivationFactory < 0 )
    goto LABEL_17;
  v22[0] = 0;
  LOBYTE(v5) = 1;
  v7 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD *))(*(_QWORD *)v20 + 136LL))(v20, v5, v22);
  if ( v7 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x14,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\src\\Utilities.h",
      (const char *)(unsigned int)v7,
      v18);
  v22[1] = a1;
  if ( a1 )
    (*(void (__fastcall **)(struct Windows::Foundation::Collections::IPropertySet *))(*(_QWORD *)a1 + 8LL))(a1);
  v21 = 0;
  v8 = (**(__int64 (__fastcall ***)(struct Windows::Foundation::Collections::IPropertySet *, GUID *, _QWORD **))a1)(
         a1,
         &GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca,
         &v21);
  if ( v8 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x18,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\src\\Utilities.h",
      (const char *)(unsigned int)v8,
      v18);
  v19[0] = 0;
  v9 = v21;
  v10 = *v21;
  string = 0;
  v11 = v22[0];
  v12 = WindowsCreateStringReference(L"ActivatableAboveLock", 0x14u, &hstringHeader, &string);
  if ( v12 < 0 )
  {
    RaiseException(v12, 1u, 0, 0);
LABEL_21:
    wil::details::in1diag3::Throw_Hr(
      v14,
      (void *)0x1C,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\src\\Utilities.h",
      (const char *)(unsigned int)v13,
      v18);
  }
  v13 = (*(__int64 (__fastcall **)(_QWORD *, HSTRING, __int64, _BYTE *))(v10 + 80))(v9, string, v11, v19);
  v14 = retaddr;
  if ( v13 < 0 )
    goto LABEL_21;
  v15 = v21;
  if ( v21 )
  {
    v21 = 0;
    (*(void (__fastcall **)(_QWORD *))(*v15 + 16LL))(v15);
  }
  (*(void (__fastcall **)(struct Windows::Foundation::Collections::IPropertySet *))(*(_QWORD *)a1 + 16LL))(a1);
  v16 = v22[0];
  if ( v22[0] )
  {
    v22[0] = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
  }
  v17 = v20;
  if ( v20 )
  {
    v20 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
  }
}

```

## disassembly

```asm
0x180010800  push    rbp
0x180010802  push    rbx
0x180010803  push    rsi
0x180010804  push    rdi
0x180010805  push    r14
0x180010807  push    r15
0x180010809  lea     rbp, [rsp-2Fh]
0x18001080e  sub     rsp, 88h
0x180010815  mov     rax, cs:__security_cookie
0x18001081c  xor     rax, rsp
0x18001081f  mov     [rbp+57h+var_38], rax
0x180010823  mov     rbx, rcx
0x180010826  xor     r15d, r15d
0x180010829  mov     [rbp+57h+var_78], r15
0x18001082d  mov     [rbp+57h+string], r15
0x180010831  lea     r9, [rbp+57h+string]; string
0x180010835  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x180010839  mov     edx, 20h ; ' '; length
0x18001083e  lea     rcx, ?RuntimeClass_Windows_Foundation_PropertyValue@@3QBGB; "Windows.Foundation.PropertyValue"
0x180010845  call    cs:__imp_WindowsCreateStringReference
0x18001084b  test    eax, eax
0x18001084d  js      loc_1800109CF
0x180010853  mov     rdi, [rbp+57h+string]
0x180010857  mov     rcx, [rbp+57h+var_78]
0x18001085b  test    rcx, rcx
0x18001085e  jz      short loc_180010871
0x180010860  mov     [rbp+57h+var_78], r15
0x180010864  mov     rax, [rcx]
0x180010867  mov     rax, [rax+10h]
0x18001086b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010870  nop
0x180010871  lea     r8, [rbp+57h+var_78]
0x180010875  lea     rdx, _GUID_629bdbc8_d932_4ff4_96b9_8d96c5c1e858
0x18001087c  mov     rcx, rdi
0x18001087f  call    cs:__imp_RoGetActivationFactory
0x180010885  mov     rcx, [rbp+5Fh]
0x180010889  test    eax, eax
0x18001088b  js      loc_1800109E3
0x180010891  mov     [rbp+57h+var_68], r15
0x180010895  mov     rcx, [rbp+57h+var_78]
0x180010899  mov     rax, [rcx]
0x18001089c  lea     r8, [rbp+57h+var_68]
0x1800108a0  mov     dl, 1
0x1800108a2  mov     rax, [rax+88h]
0x1800108a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800108ae  mov     rcx, [rbp+5Fh]; this
0x1800108b2  test    eax, eax
0x1800108b4  js      loc_1800109F8
0x1800108ba  mov     [rbp+57h+var_60], rbx
0x1800108be  test    rbx, rbx
0x1800108c1  jz      short loc_1800108D3
0x1800108c3  mov     rax, [rbx]
0x1800108c6  mov     rcx, rbx
0x1800108c9  mov     rax, [rax+8]
0x1800108cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800108d2  nop
0x1800108d3  mov     [rbp+57h+var_70], r15
0x1800108d7  mov     rax, [rbx]
0x1800108da  lea     r8, [rbp+57h+var_70]
0x1800108de  lea     rdx, _GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca
0x1800108e5  mov     rcx, rbx
0x1800108e8  mov     rax, [rax]
0x1800108eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800108f0  nop
0x1800108f1  mov     rcx, [rbp+5Fh]; this
0x1800108f5  test    eax, eax
0x1800108f7  js      loc_180010A0D
0x1800108fd  mov     [rbp+57h+var_80], 0
0x180010901  mov     rdi, [rbp+57h+var_70]
0x180010905  mov     rsi, [rdi]
0x180010908  mov     [rbp+57h+string], r15
0x18001090c  mov     r14, [rbp+57h+var_68]
0x180010910  lea     r9, [rbp+57h+string]; string
0x180010914  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x180010918  mov     edx, 14h; length
0x18001091d  lea     rcx, aActivatableabo; "ActivatableAboveLock"
0x180010924  call    cs:__imp_WindowsCreateStringReference
0x18001092a  test    eax, eax
0x18001092c  js      loc_180010A22
0x180010932  lea     r9, [rbp+57h+var_80]
0x180010936  mov     r8, r14
0x180010939  mov     rdx, [rbp+57h+string]
0x18001093d  mov     rcx, rdi
0x180010940  mov     rax, [rsi+50h]
0x180010944  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010949  mov     rcx, [rbp+5Fh]
0x18001094d  test    eax, eax
0x18001094f  js      loc_180010A36
0x180010955  mov     rcx, [rbp+57h+var_70]
0x180010959  test    rcx, rcx
0x18001095c  jz      short loc_18001096F
0x18001095e  mov     [rbp+57h+var_70], r15
0x180010962  mov     rax, [rcx]
0x180010965  mov     rax, [rax+10h]
0x180010969  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001096e  nop
0x18001096f  mov     rax, [rbx]
0x180010972  mov     rcx, rbx
0x180010975  mov     rax, [rax+10h]
0x180010979  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001097e  nop
0x18001097f  mov     rcx, [rbp+57h+var_68]
0x180010983  test    rcx, rcx
0x180010986  jz      short loc_180010999
0x180010988  mov     [rbp+57h+var_68], r15
0x18001098c  mov     rax, [rcx]
0x18001098f  mov     rax, [rax+10h]
0x180010993  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010998  nop
0x180010999  mov     rcx, [rbp+57h+var_78]
0x18001099d  test    rcx, rcx
0x1800109a0  jz      short loc_1800109B3
0x1800109a2  mov     [rbp+57h+var_78], r15
0x1800109a6  mov     rax, [rcx]
0x1800109a9  mov     rax, [rax+10h]
0x1800109ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800109b2  nop
0x1800109b3  mov     rcx, [rbp+57h+var_38]
0x1800109b7  xor     rcx, rsp; StackCookie
0x1800109ba  call    __security_check_cookie
0x1800109bf  add     rsp, 88h
0x1800109c6  pop     r15
0x1800109c8  pop     r14
0x1800109ca  pop     rdi
0x1800109cb  pop     rsi
0x1800109cc  pop     rbx
0x1800109cd  pop     rbp
0x1800109ce  retn
0x1800109cf  xor     r9d, r9d; lpArguments
0x1800109d2  xor     r8d, r8d; nNumberOfArguments
0x1800109d5  mov     edx, 1; dwExceptionFlags
0x1800109da  mov     ecx, eax; dwExceptionCode
0x1800109dc  call    cs:__imp_RaiseException
0x1800109e2  nop
0x1800109e3  mov     r9d, eax; char *
0x1800109e6  lea     r8, aOnecoreuapBase_9; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800109ed  mov     edx, 11h; void *
0x1800109f2  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800109f8  mov     r9d, eax; char *
0x1800109fb  lea     r8, aOnecoreuapBase_9; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180010a02  mov     edx, 14h; void *
0x180010a07  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180010a0d  mov     r9d, eax; char *
0x180010a10  lea     r8, aOnecoreuapBase_9; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180010a17  mov     edx, 18h; void *
0x180010a1c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180010a22  xor     r9d, r9d; lpArguments
0x180010a25  xor     r8d, r8d; nNumberOfArguments
0x180010a28  mov     edx, 1; dwExceptionFlags
0x180010a2d  mov     ecx, eax; dwExceptionCode
0x180010a2f  call    cs:__imp_RaiseException
0x180010a35  nop
0x180010a36  mov     r9d, eax; char *
0x180010a39  lea     r8, aOnecoreuapBase_9; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180010a40  mov     edx, 1Ch; void *
0x180010a45  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
