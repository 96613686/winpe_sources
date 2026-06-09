# CSpLocalSettingsDataKey::EnumKeys(ulong,ushort * *)

- ea: `0x180263a30`
- end: `0x180263d5b`
- name: `?EnumKeys@CSpLocalSettingsDataKey@@UEAAJKPEAPEAG@Z`
- size: `811`
- prototype: `__int64 __fastcall(CSpLocalSettingsDataKey *__hidden this, unsigned int, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000a590`
- `0x180011cb0`
- `0x180021944`
- `0x180023c6c`
- `0x180026508`
- `0x180263a30`
- `0x18028b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180263a57`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180263a57`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180263c3a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180263ce8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180263d15`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180263c3a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180263ce8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180263d15`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180263c7d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180263c7d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CSpLocalSettingsDataKey::EnumKeys(RTL_SRWLOCK *this, unsigned int a2, unsigned __int16 **a3)
{
  RTL_SRWLOCK *v6; // rbx
  RTL_SRWLOCK *v7; // r14
  RTL_SRWLOCK *v8; // rsi
  PVOID Ptr; // rdi
  __int64 (__fastcall *v10)(PVOID, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)); // rbx
  int v11; // eax
  unsigned int v12; // ebx
  __int64 (__fastcall ***v13)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v14)(_QWORD, GUID *, __int64 *); // rdi
  int v15; // eax
  __int64 v16; // rdx
  __int64 v17; // rdi
  __int64 (__fastcall *v18)(__int64, RTL_SRWLOCK *); // rbx
  int v19; // eax
  __int64 v20; // rdx
  PVOID v21; // rdi
  __int64 (__fastcall *v22)(PVOID, __int64 *); // rbx
  int v23; // eax
  __int64 v24; // rdi
  __int64 (__fastcall *v25)(__int64, HSTRING *); // rbx
  int v26; // eax
  const unsigned __int16 *StringRawBuffer; // rax
  int appended; // eax
  __int64 v29; // rdx
  unsigned __int16 *v30; // rax
  __int64 v32; // [rsp+20h] [rbp-30h] BYREF
  __int64 v33; // [rsp+28h] [rbp-28h] BYREF
  unsigned __int16 *v34; // [rsp+30h] [rbp-20h] BYREF
  __int64 (__fastcall ***v35)(_QWORD, GUID *, __int64 *); // [rsp+38h] [rbp-18h] BYREF
  _QWORD v36[2]; // [rsp+40h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+38h]
  char v38; // [rsp+90h] [rbp+40h] BYREF
  HSTRING string; // [rsp+A8h] [rbp+58h] BYREF

  v6 = this + 13;
  AcquireSRWLockExclusive(this + 13);
  v36[0] = v6;
  v7 = this + 12;
  v8 = this + 14;
  if ( !this[12].Ptr || a2 < LODWORD(v8->Ptr) )
  {
    LODWORD(v8->Ptr) = 0;
    v35 = 0;
    Ptr = this[8].Ptr;
    v10 = *(__int64 (__fastcall **)(PVOID, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)))(*(_QWORD *)Ptr + 72LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v35);
    v11 = v10(Ptr, &v35);
    v12 = v11;
    if ( v11 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xEF,
        (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\customdatakeys\\localsettings_datakey.cpp",
        (const char *)(unsigned int)v11,
        v32);
LABEL_10:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v35);
LABEL_32:
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(v36);
      return v12;
    }
    v33 = 0;
    v13 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v35;
    v14 = **v35;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v33);
    v15 = v14(v13, &GUID_a785be1d_159e_53ad_9553_598b03dca048, &v33);
    v12 = v15;
    if ( v15 < 0 )
    {
      v16 = 242;
LABEL_9:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v16,
        (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\customdatakeys\\localsettings_datakey.cpp",
        (const char *)(unsigned int)v15,
        v32);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v33);
      goto LABEL_10;
    }
    v17 = v33;
    v18 = *(__int64 (__fastcall **)(__int64, RTL_SRWLOCK *))(*(_QWORD *)v33 + 48LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v7);
    v15 = v18(v17, v7);
    v12 = v15;
    if ( v15 < 0 )
    {
      v16 = 243;
      goto LABEL_9;
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v33);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v35);
  }
  v38 = 0;
  v19 = (*(__int64 (__fastcall **)(PVOID, char *))(*(_QWORD *)v7->Ptr + 56LL))(v7->Ptr, &v38);
  v12 = v19;
  if ( v19 < 0 )
  {
    v20 = 247;
LABEL_14:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v20,
      (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\customdatakeys\\localsettings_datakey.cpp",
      (const char *)(unsigned int)v19,
      v32);
    goto LABEL_32;
  }
  while ( LODWORD(v8->Ptr) < a2 )
  {
    if ( !v38 )
      goto LABEL_34;
    v19 = (*(__int64 (__fastcall **)(PVOID, char *))(*(_QWORD *)v7->Ptr + 64LL))(v7->Ptr, &v38);
    v12 = v19;
    if ( v19 < 0 )
    {
      v20 = 250;
      goto LABEL_14;
    }
    ++LODWORD(v8->Ptr);
  }
  if ( v38 )
  {
    v32 = 0;
    v21 = v7->Ptr;
    v22 = *(__int64 (__fastcall **)(PVOID, __int64 *))(*(_QWORD *)v7->Ptr + 48LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v32);
    v23 = v22(v21, &v32);
    v12 = v23;
    if ( v23 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x100,
        (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\customdatakeys\\localsettings_datakey.cpp",
        (const char *)(unsigned int)v23,
        v32);
LABEL_31:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v32);
      goto LABEL_32;
    }
    string = 0;
    v24 = v32;
    v25 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v32 + 48LL);
    WindowsDeleteString(0);
    string = 0;
    v26 = v25(v24, &string);
    v12 = v26;
    if ( v26 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x103,
        (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\customdatakeys\\localsettings_datakey.cpp",
        (const char *)(unsigned int)v26,
        v32);
LABEL_30:
      WindowsDeleteString(string);
      string = 0;
      goto LABEL_31;
    }
    v34 = 0;
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    appended = CSpDynamicString::AppendHR((CSpDynamicString *)&v34, StringRawBuffer);
    v12 = appended;
    if ( appended < 0 )
    {
      v29 = 262;
LABEL_29:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v29,
        (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\customdatakeys\\localsettings_datakey.cpp",
        (const char *)(unsigned int)appended,
        v32);
      SPPIPEINFO::~SPPIPEINFO((SPPIPEINFO *)&v34);
      goto LABEL_30;
    }
    v30 = v34;
    v34 = 0;
    *a3 = v30;
    ++LODWORD(v8->Ptr);
    appended = (*(__int64 (__fastcall **)(PVOID, char *))(*(_QWORD *)v7->Ptr + 64LL))(v7->Ptr, &v38);
    v12 = appended;
    if ( appended < 0 )
    {
      v29 = 267;
      goto LABEL_29;
    }
    SPPIPEINFO::~SPPIPEINFO((SPPIPEINFO *)&v34);
    WindowsDeleteString(string);
    string = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v32);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(v36);
    return 0;
  }
  else
  {
LABEL_34:
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(v36);
    return 2147766329LL;
  }
}

```

## disassembly

```asm
0x180263a30  mov     [rsp-38h+arg_8], rbx
0x180263a35  push    rbp
0x180263a36  push    rsi
0x180263a37  push    rdi
0x180263a38  push    r12
0x180263a3a  push    r13
0x180263a3c  push    r14
0x180263a3e  push    r15
0x180263a40  mov     rbp, rsp
0x180263a43  sub     rsp, 50h
0x180263a47  mov     r12, r8
0x180263a4a  mov     r15d, edx
0x180263a4d  mov     rdi, rcx
0x180263a50  lea     rbx, [rcx+68h]
0x180263a54  mov     rcx, rbx; SRWLock
0x180263a57  call    cs:__imp_AcquireSRWLockExclusive
0x180263a5d  mov     [rbp+var_10], rbx
0x180263a61  lea     r14, [rdi+60h]
0x180263a65  xor     r13d, r13d
0x180263a68  lea     rsi, [rdi+70h]
0x180263a6c  cmp     [r14], r13
0x180263a6f  jz      short loc_180263A7A
0x180263a71  cmp     r15d, [rsi]
0x180263a74  jnb     loc_180263B69
0x180263a7a  mov     [rsi], r13d
0x180263a7d  mov     [rbp+var_18], r13
0x180263a81  mov     rdi, [rdi+40h]
0x180263a85  mov     rax, [rdi]
0x180263a88  mov     rbx, [rax+48h]
0x180263a8c  lea     rcx, [rbp+var_18]
0x180263a90  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180263a95  lea     rdx, [rbp+var_18]
0x180263a99  mov     rcx, rdi
0x180263a9c  mov     rax, rbx
0x180263a9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180263aa4  mov     ebx, eax
0x180263aa6  test    eax, eax
0x180263aa8  jns     short loc_180263AC7
0x180263aaa  mov     rcx, [rbp+38h]; this
0x180263aae  mov     r9d, eax; char *
0x180263ab1  lea     r8, aOnecoreuapEndu_314; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x180263ab8  mov     edx, 0EFh; void *
0x180263abd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180263ac2  jmp     loc_180263B49
0x180263ac7  mov     [rbp+var_28], r13
0x180263acb  mov     rbx, [rbp+var_18]
0x180263acf  mov     rax, [rbx]
0x180263ad2  mov     rdi, [rax]
0x180263ad5  lea     rcx, [rbp+var_28]
0x180263ad9  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180263ade  lea     r8, [rbp+var_28]
0x180263ae2  lea     rdx, _GUID_a785be1d_159e_53ad_9553_598b03dca048
0x180263ae9  mov     rcx, rbx
0x180263aec  mov     rax, rdi
0x180263aef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180263af4  mov     ebx, eax
0x180263af6  test    eax, eax
0x180263af8  jns     short loc_180263B01
0x180263afa  mov     edx, 0F2h
0x180263aff  jmp     short loc_180263B2D
0x180263b01  mov     rdi, [rbp+var_28]
0x180263b05  mov     rax, [rdi]
0x180263b08  mov     rbx, [rax+30h]
0x180263b0c  mov     rcx, r14
0x180263b0f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180263b14  mov     rdx, r14
0x180263b17  mov     rcx, rdi
0x180263b1a  mov     rax, rbx
0x180263b1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180263b22  mov     ebx, eax
0x180263b24  test    eax, eax
0x180263b26  jns     short loc_180263B57
0x180263b28  mov     edx, 0F3h; void *
0x180263b2d  mov     r9d, eax; char *
0x180263b30  lea     r8, aOnecoreuapEndu_314; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x180263b37  mov     rcx, [rbp+38h]; this
0x180263b3b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180263b40  lea     rcx, [rbp+var_28]
0x180263b44  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180263b49  lea     rcx, [rbp+var_18]
0x180263b4d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180263b52  jmp     loc_180263CFB
0x180263b57  lea     rcx, [rbp+var_28]
0x180263b5b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180263b60  lea     rcx, [rbp+var_18]
0x180263b64  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180263b69  mov     [rbp+arg_0], r13b
0x180263b6d  mov     rcx, [r14]
0x180263b70  mov     rax, [rcx]
0x180263b73  lea     rdx, [rbp+arg_0]
0x180263b77  mov     rax, [rax+38h]
0x180263b7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180263b80  mov     ebx, eax
0x180263b82  test    eax, eax
0x180263b84  jns     short loc_180263BA3
0x180263b86  mov     edx, 0F7h; void *
0x180263b8b  lea     r8, aOnecoreuapEndu_314; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x180263b92  mov     r9d, eax; char *
0x180263b95  mov     rcx, [rbp+38h]; this
0x180263b99  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180263b9e  jmp     loc_180263CFB
0x180263ba3  cmp     [rsi], r15d
0x180263ba6  jnb     short loc_180263BD6
0x180263ba8  cmp     [rbp+arg_0], r13b
0x180263bac  jz      loc_180263D35
0x180263bb2  mov     rcx, [r14]
0x180263bb5  mov     rax, [rcx]
0x180263bb8  lea     rdx, [rbp+arg_0]
0x180263bbc  mov     rax, [rax+40h]
0x180263bc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180263bc5  mov     ebx, eax
0x180263bc7  test    eax, eax
0x180263bc9  js      short loc_180263BCF
0x180263bcb  inc     dword ptr [rsi]
0x180263bcd  jmp     short loc_180263BA3
0x180263bcf  mov     edx, 0FAh
0x180263bd4  jmp     short loc_180263B8B
0x180263bd6  cmp     [rbp+arg_0], r13b
0x180263bda  jz      loc_180263D35
0x180263be0  mov     [rbp+var_30], r13
0x180263be4  mov     rdi, [r14]
0x180263be7  mov     rax, [rdi]
0x180263bea  mov     rbx, [rax+30h]
0x180263bee  lea     rcx, [rbp+var_30]
0x180263bf2  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180263bf7  lea     rdx, [rbp+var_30]
0x180263bfb  mov     rcx, rdi
0x180263bfe  mov     rax, rbx
0x180263c01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180263c06  mov     ebx, eax
0x180263c08  test    eax, eax
0x180263c0a  jns     short loc_180263C29
0x180263c0c  mov     rcx, [rbp+38h]; this
0x180263c10  mov     r9d, eax; char *
0x180263c13  lea     r8, aOnecoreuapEndu_314; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x180263c1a  mov     edx, 100h; void *
0x180263c1f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180263c24  jmp     loc_180263CF2
0x180263c29  mov     [rbp+string], r13
0x180263c2d  mov     rdi, [rbp+var_30]
0x180263c31  mov     rax, [rdi]
0x180263c34  mov     rbx, [rax+30h]
0x180263c38  xor     ecx, ecx; string
0x180263c3a  call    cs:__imp_WindowsDeleteString
0x180263c40  mov     [rbp+string], r13
0x180263c44  lea     rdx, [rbp+string]
0x180263c48  mov     rcx, rdi
0x180263c4b  mov     rax, rbx
0x180263c4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180263c53  mov     ebx, eax
0x180263c55  test    eax, eax
0x180263c57  jns     short loc_180263C73
0x180263c59  mov     rcx, [rbp+38h]; this
0x180263c5d  mov     r9d, eax; char *
0x180263c60  lea     r8, aOnecoreuapEndu_314; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x180263c67  mov     edx, 103h; void *
0x180263c6c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180263c71  jmp     short loc_180263CE4
0x180263c73  mov     [rbp+var_20], r13
0x180263c77  xor     edx, edx; length
0x180263c79  mov     rcx, [rbp+string]; string
0x180263c7d  call    cs:__imp_WindowsGetStringRawBuffer
0x180263c83  mov     rdx, rax; Src
0x180263c86  lea     rcx, [rbp+var_20]; this
0x180263c8a  call    ?AppendHR@CSpDynamicString@@QEAAJPEBG@Z; CSpDynamicString::AppendHR(ushort const *)
0x180263c8f  mov     ebx, eax
0x180263c91  test    eax, eax
0x180263c93  jns     short loc_180263C9C
0x180263c95  mov     edx, 106h
0x180263c9a  jmp     short loc_180263CC8
0x180263c9c  mov     rax, [rbp+var_20]
0x180263ca0  mov     [rbp+var_20], r13
0x180263ca4  mov     [r12], rax
0x180263ca8  inc     dword ptr [rsi]
0x180263caa  mov     rcx, [r14]
0x180263cad  mov     rax, [rcx]
0x180263cb0  lea     rdx, [rbp+arg_0]
0x180263cb4  mov     rax, [rax+40h]
0x180263cb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180263cbd  mov     ebx, eax
0x180263cbf  test    eax, eax
0x180263cc1  jns     short loc_180263D08
0x180263cc3  mov     edx, 10Bh; void *
0x180263cc8  mov     r9d, eax; char *
0x180263ccb  lea     r8, aOnecoreuapEndu_314; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x180263cd2  mov     rcx, [rbp+38h]; this
0x180263cd6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180263cdb  lea     rcx, [rbp+var_20]; this
0x180263cdf  call    ??1SPPIPEINFO@@QEAA@XZ; SPPIPEINFO::~SPPIPEINFO(void)
0x180263ce4  mov     rcx, [rbp+string]; string
0x180263ce8  call    cs:__imp_WindowsDeleteString
0x180263cee  mov     [rbp+string], r13
0x180263cf2  lea     rcx, [rbp+var_30]
0x180263cf6  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180263cfb  lea     rcx, [rbp+var_10]
0x180263cff  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x180263d04  mov     eax, ebx
0x180263d06  jmp     short loc_180263D43
0x180263d08  lea     rcx, [rbp+var_20]; this
0x180263d0c  call    ??1SPPIPEINFO@@QEAA@XZ; SPPIPEINFO::~SPPIPEINFO(void)
0x180263d11  mov     rcx, [rbp+string]; string
0x180263d15  call    cs:__imp_WindowsDeleteString
0x180263d1b  mov     [rbp+string], r13
0x180263d1f  lea     rcx, [rbp+var_30]
0x180263d23  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180263d28  lea     rcx, [rbp+var_10]
0x180263d2c  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x180263d31  xor     eax, eax
0x180263d33  jmp     short loc_180263D43
0x180263d35  lea     rcx, [rbp+var_10]
0x180263d39  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x180263d3e  mov     eax, 80045039h
0x180263d43  mov     rbx, [rsp+50h+arg_8]
0x180263d4b  add     rsp, 50h
0x180263d4f  pop     r15
0x180263d51  pop     r14
0x180263d53  pop     r13
0x180263d55  pop     r12
0x180263d57  pop     rdi
0x180263d58  pop     rsi
0x180263d59  pop     rbp
0x180263d5a  retn
```
