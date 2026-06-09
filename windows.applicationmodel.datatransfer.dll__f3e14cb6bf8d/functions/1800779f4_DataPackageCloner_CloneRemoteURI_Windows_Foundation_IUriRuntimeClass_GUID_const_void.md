# DataPackageCloner::CloneRemoteURI(Windows::Foundation::IUriRuntimeClass *,_GUID const &,void * *)

- ea: `0x1800779f4`
- end: `0x180077cbb`
- name: `?CloneRemoteURI@DataPackageCloner@@AEAAJPEAUIUriRuntimeClass@Foundation@Windows@@AEBU_GUID@@PEAPEAX@Z`
- size: `711`
- prototype: `__int64 __fastcall(DataPackageCloner *__hidden this, struct Windows::Foundation::IUriRuntimeClass *, const struct _GUID *, void **)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180076aac`
- `0x180079938`

## callees

- `0x180002ad0`
- `0x180043b6c`
- `0x180048954`
- `0x1800779f4`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180077a36`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180077c58`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180077c90`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180077a36`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180077c58`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180077c90`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180077acd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180077acd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x180077a66`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x180077a66`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x180077b8d`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x180077b8d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180077b7b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180077b7b`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180077b07`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180077b07`

## string_xrefs

- `0x180077ac6`: `Windows.Foundation.Uri`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall DataPackageCloner::CloneRemoteURI(
        DataPackageCloner *this,
        struct Windows::Foundation::IUriRuntimeClass *a2,
        const struct _GUID *a3,
        void **a4)
{
  __int64 (__fastcall *v8)(struct Windows::Foundation::IUriRuntimeClass *, HSTRING *); // rbx
  int v9; // eax
  unsigned int v10; // ebx
  unsigned __int64 v11; // r9
  __int64 v12; // rdx
  UINT32 StringLen; // eax
  unsigned __int64 v14; // rdx
  HSTRING v15; // rdi
  HRESULT v16; // eax
  int v17; // edx
  unsigned int v18; // r8d
  int ActivationFactory; // eax
  __int64 v20; // rcx
  unsigned int StringW; // eax
  __int64 v22; // rcx
  __int64 (__fastcall ***v23)(_QWORD, const struct _GUID *, void **); // rcx
  int v24; // eax
  __int64 (__fastcall ***v25)(_QWORD, const struct _GUID *, void **); // rcx
  __int64 (__fastcall ***v26)(_QWORD, const struct _GUID *, void **); // rcx
  __int64 v28; // [rsp+20h] [rbp-50h] BYREF
  __int64 (__fastcall ***v29)(_QWORD, const struct _GUID *, void **); // [rsp+28h] [rbp-48h] BYREF
  HSTRING string; // [rsp+30h] [rbp-40h] BYREF
  WCHAR Buffer[4]; // [rsp+38h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+40h] [rbp-30h] BYREF
  HSTRING v33; // [rsp+58h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+38h]

  *a4 = 0;
  string = 0;
  v8 = *(__int64 (__fastcall **)(struct Windows::Foundation::IUriRuntimeClass *, HSTRING *))(*(_QWORD *)a2 + 128LL);
  WindowsDeleteString(0);
  string = 0;
  v9 = v8(a2, &string);
  v10 = v9;
  if ( v9 < 0 )
  {
    v11 = (unsigned int)v9;
    v12 = 256;
LABEL_31:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecoreuap\\shell\\datatransfer\\lib\\datapackagecloner.cpp",
      (const char *)v11,
      v28);
LABEL_32:
    WindowsDeleteString(string);
    return v10;
  }
  StringLen = WindowsGetStringLen(string);
  if ( !is_mul_ok(2u, StringLen + 1) )
  {
    v10 = -2147024362;
    v12 = 260;
    goto LABEL_30;
  }
  v14 = *((_QWORD *)this + 3) + 2 * (StringLen + 1);
  if ( v14 < *((_QWORD *)this + 3) )
  {
    v10 = -2147024882;
    goto LABEL_28;
  }
  *((_QWORD *)this + 3) = v14;
  v10 = *((_QWORD *)this + 4) < v14 ? 0x8007000E : 0;
  if ( v14 > *((_QWORD *)this + 4) )
  {
LABEL_28:
    v12 = 261;
LABEL_30:
    v11 = v10;
    goto LABEL_31;
  }
  v15 = string;
  v29 = 0;
  v28 = 0;
  v33 = 0;
  v16 = WindowsCreateStringReference(L"Windows.Foundation.Uri", 0x16u, &hstringHeader, &v33);
  if ( v16 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v16, v17, v18);
    JUMPOUT(0x180077CBALL);
  }
  ActivationFactory = RoGetActivationFactory(v33, &GUID_44a9796f_723e_4fdf_a218_033e75b0c084, &v28);
  v10 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB5,
      (unsigned int)"onecoreuap\\shell\\datatransfer\\lib\\datapackagecloner.cpp",
      (const char *)(unsigned int)ActivationFactory,
      v28);
    v20 = v28;
    if ( v28 )
    {
      v28 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
    }
LABEL_17:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x108,
      (unsigned int)"onecoreuap\\shell\\datatransfer\\lib\\datapackagecloner.cpp",
      (const char *)v10,
      v28);
    v23 = v29;
    if ( v29 )
    {
      v29 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, const struct _GUID *, void **)))(*v23)[2])(v23);
    }
    goto LABEL_32;
  }
  v10 = (*(__int64 (__fastcall **)(__int64, HSTRING, _QWORD))(*(_QWORD *)v28 + 48LL))(v28, v15, &v29);
  if ( (v10 & 0x80000000) != 0 )
  {
    *(_QWORD *)Buffer = 0;
    StringW = LoadStringW(&_ImageBase, 8u, Buffer, 0);
    if ( StringW )
      RoOriginateErrorW(v10, StringW, *(_QWORD *)Buffer);
  }
  v22 = v28;
  if ( v28 )
  {
    v28 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
  }
  if ( (v10 & 0x80000000) != 0 )
    goto LABEL_17;
  v24 = (**v29)(v29, a3, a4);
  v10 = v24;
  if ( v24 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x109,
      (unsigned int)"onecoreuap\\shell\\datatransfer\\lib\\datapackagecloner.cpp",
      (const char *)(unsigned int)v24,
      v28);
    v25 = v29;
    if ( v29 )
    {
      v29 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, const struct _GUID *, void **)))(*v25)[2])(v25);
    }
    goto LABEL_32;
  }
  v26 = v29;
  if ( v29 )
  {
    v29 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, const struct _GUID *, void **)))(*v26)[2])(v26);
  }
  WindowsDeleteString(string);
  return 0;
}

```

## disassembly

```asm
0x1800779f4  push    rbp
0x1800779f6  push    rbx
0x1800779f7  push    rsi
0x1800779f8  push    rdi
0x1800779f9  push    r12
0x1800779fb  push    r14
0x1800779fd  push    r15
0x1800779ff  mov     rbp, rsp
0x180077a02  sub     rsp, 70h
0x180077a06  mov     rax, cs:__security_cookie
0x180077a0d  xor     rax, rsp
0x180077a10  mov     [rbp+var_10], rax
0x180077a14  mov     r14, r9
0x180077a17  mov     r15, r8
0x180077a1a  mov     rdi, rdx
0x180077a1d  mov     rsi, rcx
0x180077a20  xor     r12d, r12d
0x180077a23  mov     [r9], r12
0x180077a26  mov     [rbp+string], r12
0x180077a2a  mov     rax, [rdx]
0x180077a2d  mov     rbx, [rax+80h]
0x180077a34  xor     ecx, ecx; string
0x180077a36  call    cs:__imp_WindowsDeleteString
0x180077a3c  mov     [rbp+string], r12
0x180077a40  lea     rdx, [rbp+string]
0x180077a44  mov     rcx, rdi
0x180077a47  mov     rax, rbx
0x180077a4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077a4f  mov     ebx, eax
0x180077a51  test    eax, eax
0x180077a53  jns     short loc_180077A62
0x180077a55  mov     r9d, eax
0x180077a58  mov     edx, 100h
0x180077a5d  jmp     loc_180077C7B
0x180077a62  mov     rcx, [rbp+string]; string
0x180077a66  call    cs:__imp_WindowsGetStringLen
0x180077a6c  lea     ecx, [rax+1]
0x180077a6f  add     rcx, rcx
0x180077a72  mov     rax, rcx
0x180077a75  shr     rax, 20h
0x180077a79  test    eax, eax
0x180077a7b  jnz     loc_180077C6E
0x180077a81  mov     edx, ecx
0x180077a83  add     rdx, [rsi+18h]
0x180077a87  cmp     rdx, [rsi+18h]
0x180077a8b  jb      loc_180077C62
0x180077a91  mov     [rsi+18h], rdx
0x180077a95  cmp     [rsi+20h], rdx
0x180077a99  sbb     ebx, ebx
0x180077a9b  and     ebx, 8007000Eh
0x180077aa1  cmp     rdx, [rsi+20h]
0x180077aa5  ja      loc_180077C67
0x180077aab  mov     rdi, [rbp+string]
0x180077aaf  mov     [rbp+var_48], r12
0x180077ab3  mov     [rbp+var_50], r12
0x180077ab7  mov     [rbp+var_18], r12
0x180077abb  lea     r9, [rbp+var_18]; string
0x180077abf  lea     r8, [rbp+hstringHeader]; hstringHeader
0x180077ac3  lea     edx, [rax+16h]; length
0x180077ac6  lea     rcx, ?RuntimeClass_Windows_Foundation_Uri@@3QBGB; "Windows.Foundation.Uri"
0x180077acd  call    cs:__imp_WindowsCreateStringReference
0x180077ad3  test    eax, eax
0x180077ad5  js      loc_180077CB3
0x180077adb  mov     rbx, [rbp+var_18]
0x180077adf  mov     rcx, [rbp+var_50]
0x180077ae3  test    rcx, rcx
0x180077ae6  jz      short loc_180077AF9
0x180077ae8  mov     [rbp+var_50], r12
0x180077aec  mov     rax, [rcx]
0x180077aef  mov     rax, [rax+10h]
0x180077af3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077af8  nop
0x180077af9  lea     r8, [rbp+var_50]
0x180077afd  lea     rdx, _GUID_44a9796f_723e_4fdf_a218_033e75b0c084
0x180077b04  mov     rcx, rbx
0x180077b07  call    cs:__imp_RoGetActivationFactory
0x180077b0d  mov     ebx, eax
0x180077b0f  test    eax, eax
0x180077b11  jns     short loc_180077B48
0x180077b13  mov     rcx, [rbp+38h]; this
0x180077b17  mov     r9d, eax; char *
0x180077b1a  lea     r8, aOnecoreuapShel_4; "onecoreuap\\shell\\datatransfer\\lib\\d"...
0x180077b21  mov     edx, 0B5h; void *
0x180077b26  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180077b2b  nop
0x180077b2c  mov     rcx, [rbp+var_50]
0x180077b30  test    rcx, rcx
0x180077b33  jz      short loc_180077B46
0x180077b35  mov     [rbp+var_50], r12
0x180077b39  mov     rax, [rcx]
0x180077b3c  mov     rax, [rax+10h]
0x180077b40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077b45  nop
0x180077b46  jmp     short loc_180077BB2
0x180077b48  mov     rcx, [rbp+var_50]
0x180077b4c  mov     rax, [rcx]
0x180077b4f  lea     r8, [rbp+var_48]
0x180077b53  mov     rdx, rdi
0x180077b56  mov     rax, [rax+30h]
0x180077b5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077b5f  mov     ebx, eax
0x180077b61  test    eax, eax
0x180077b63  jns     short loc_180077B94
0x180077b65  mov     qword ptr [rbp+Buffer], r12
0x180077b69  xor     r9d, r9d; cchBufferMax
0x180077b6c  lea     r8, [rbp+Buffer]; lpBuffer
0x180077b70  lea     edx, [r9+8]; uID
0x180077b74  lea     rcx, __ImageBase; hInstance
0x180077b7b  call    cs:__imp_LoadStringW
0x180077b81  test    eax, eax
0x180077b83  jz      short loc_180077B94
0x180077b85  mov     r8, qword ptr [rbp+Buffer]
0x180077b89  mov     edx, eax
0x180077b8b  mov     ecx, ebx
0x180077b8d  call    cs:__imp_RoOriginateErrorW
0x180077b93  nop
0x180077b94  mov     rcx, [rbp+var_50]
0x180077b98  test    rcx, rcx
0x180077b9b  jz      short loc_180077BAE
0x180077b9d  mov     [rbp+var_50], r12
0x180077ba1  mov     rax, [rcx]
0x180077ba4  mov     rax, [rax+10h]
0x180077ba8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077bad  nop
0x180077bae  test    ebx, ebx
0x180077bb0  jns     short loc_180077BEA
0x180077bb2  mov     rcx, [rbp+38h]; this
0x180077bb6  mov     r9d, ebx; char *
0x180077bb9  lea     r8, aOnecoreuapShel_4; "onecoreuap\\shell\\datatransfer\\lib\\d"...
0x180077bc0  mov     edx, 108h; void *
0x180077bc5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180077bca  nop
0x180077bcb  mov     rcx, [rbp+var_48]
0x180077bcf  test    rcx, rcx
0x180077bd2  jz      short loc_180077BE5
0x180077bd4  mov     [rbp+var_48], r12
0x180077bd8  mov     rax, [rcx]
0x180077bdb  mov     rax, [rax+10h]
0x180077bdf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077be4  nop
0x180077be5  jmp     loc_180077C8C
0x180077bea  mov     rcx, [rbp+var_48]
0x180077bee  mov     rax, [rcx]
0x180077bf1  mov     r8, r14
0x180077bf4  mov     rdx, r15
0x180077bf7  mov     rax, [rax]
0x180077bfa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077bff  mov     ebx, eax
0x180077c01  test    eax, eax
0x180077c03  jns     short loc_180077C3A
0x180077c05  mov     rcx, [rbp+38h]; this
0x180077c09  mov     r9d, eax; char *
0x180077c0c  lea     r8, aOnecoreuapShel_4; "onecoreuap\\shell\\datatransfer\\lib\\d"...
0x180077c13  mov     edx, 109h; void *
0x180077c18  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180077c1d  nop
0x180077c1e  mov     rcx, [rbp+var_48]
0x180077c22  test    rcx, rcx
0x180077c25  jz      short loc_180077C38
0x180077c27  mov     [rbp+var_48], r12
0x180077c2b  mov     rax, [rcx]
0x180077c2e  mov     rax, [rax+10h]
0x180077c32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077c37  nop
0x180077c38  jmp     short loc_180077C8C
0x180077c3a  mov     rcx, [rbp+var_48]
0x180077c3e  test    rcx, rcx
0x180077c41  jz      short loc_180077C54
0x180077c43  mov     [rbp+var_48], r12
0x180077c47  mov     rax, [rcx]
0x180077c4a  mov     rax, [rax+10h]
0x180077c4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077c53  nop
0x180077c54  mov     rcx, [rbp+string]; string
0x180077c58  call    cs:__imp_WindowsDeleteString
0x180077c5e  xor     eax, eax
0x180077c60  jmp     short loc_180077C98
0x180077c62  mov     ebx, 8007000Eh
0x180077c67  mov     edx, 105h
0x180077c6c  jmp     short loc_180077C78
0x180077c6e  mov     ebx, 80070216h
0x180077c73  mov     edx, 104h; void *
0x180077c78  mov     r9d, ebx; char *
0x180077c7b  lea     r8, aOnecoreuapShel_4; "onecoreuap\\shell\\datatransfer\\lib\\d"...
0x180077c82  mov     rcx, [rbp+38h]; this
0x180077c86  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180077c8b  nop
0x180077c8c  mov     rcx, [rbp+string]; string
0x180077c90  call    cs:__imp_WindowsDeleteString
0x180077c96  mov     eax, ebx
0x180077c98  mov     rcx, [rbp+var_10]
0x180077c9c  xor     rcx, rsp; StackCookie
0x180077c9f  call    __security_check_cookie
0x180077ca4  add     rsp, 70h
0x180077ca8  pop     r15
0x180077caa  pop     r14
0x180077cac  pop     r12
0x180077cae  pop     rdi
0x180077caf  pop     rsi
0x180077cb0  pop     rbx
0x180077cb1  pop     rbp
0x180077cb2  retn
0x180077cb3  mov     ecx, eax; this
0x180077cb5  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
