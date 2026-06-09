# CSpLocalSettingsDataKey::EnumValues(ulong,ushort * *)

- ea: `0x180263d70`
- end: `0x18026403f`
- name: `?EnumValues@CSpLocalSettingsDataKey@@UEAAJKPEAPEAG@Z`
- size: `719`
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
- `0x180263d70`
- `0x18028b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180263d97`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180263d97`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180263f1e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180263fcc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180263ff9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180263f1e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180263fcc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180263ff9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180263f61`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180263f61`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CSpLocalSettingsDataKey::EnumValues(RTL_SRWLOCK *this, unsigned int a2, unsigned __int16 **a3)
{
  RTL_SRWLOCK *v6; // rbx
  RTL_SRWLOCK *v7; // r14
  unsigned int *v8; // rsi
  __int64 (__fastcall ***Ptr)(_QWORD, GUID *, __int64 *); // rdi
  __int64 (__fastcall *v10)(_QWORD, GUID *, __int64 *); // rbx
  int v11; // eax
  unsigned int v12; // ebx
  __int64 v13; // rdx
  __int64 v14; // rdi
  __int64 (__fastcall *v15)(__int64, RTL_SRWLOCK *); // rbx
  int v16; // eax
  __int64 v17; // rdx
  PVOID v18; // rdi
  __int64 (__fastcall *v19)(PVOID, __int64 *); // rbx
  int v20; // eax
  __int64 v21; // rdi
  __int64 (__fastcall *v22)(__int64, HSTRING *); // rbx
  int v23; // eax
  const unsigned __int16 *StringRawBuffer; // rax
  int appended; // eax
  __int64 v26; // rdx
  unsigned __int16 *v27; // rax
  __int64 v29; // [rsp+20h] [rbp-20h] BYREF
  unsigned __int16 *v30; // [rsp+28h] [rbp-18h] BYREF
  __int64 v31; // [rsp+30h] [rbp-10h] BYREF
  RTL_SRWLOCK *v32; // [rsp+38h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+38h]
  char v34; // [rsp+80h] [rbp+40h] BYREF
  HSTRING string; // [rsp+98h] [rbp+58h] BYREF

  v6 = this + 13;
  AcquireSRWLockExclusive(this + 13);
  v32 = v6;
  v7 = this + 11;
  v8 = (unsigned int *)&this[14].Ptr + 1;
  if ( !this[11].Ptr || a2 < *v8 )
  {
    *v8 = 0;
    v31 = 0;
    Ptr = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))this[9].Ptr;
    v10 = **Ptr;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v31);
    v11 = v10(Ptr, &GUID_fe2f3d47_5d47_5499_8374_430c7cda0204, &v31);
    v12 = v11;
    if ( v11 < 0 )
    {
      v13 = 281;
LABEL_7:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v13,
        (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\customdatakeys\\localsettings_datakey.cpp",
        (const char *)(unsigned int)v11,
        v29);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v31);
LABEL_29:
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v32);
      return v12;
    }
    v14 = v31;
    v15 = *(__int64 (__fastcall **)(__int64, RTL_SRWLOCK *))(*(_QWORD *)v31 + 48LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v7);
    v11 = v15(v14, v7);
    v12 = v11;
    if ( v11 < 0 )
    {
      v13 = 282;
      goto LABEL_7;
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v31);
  }
  v34 = 0;
  v16 = (*(__int64 (__fastcall **)(PVOID, char *))(*(_QWORD *)v7->Ptr + 56LL))(v7->Ptr, &v34);
  v12 = v16;
  if ( v16 < 0 )
  {
    v17 = 286;
LABEL_11:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v17,
      (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\customdatakeys\\localsettings_datakey.cpp",
      (const char *)(unsigned int)v16,
      v29);
    goto LABEL_29;
  }
  while ( *v8 < a2 )
  {
    if ( !v34 )
      goto LABEL_31;
    v16 = (*(__int64 (__fastcall **)(PVOID, char *))(*(_QWORD *)v7->Ptr + 64LL))(v7->Ptr, &v34);
    v12 = v16;
    if ( v16 < 0 )
    {
      v17 = 289;
      goto LABEL_11;
    }
    ++*v8;
  }
  if ( v34 )
  {
    v29 = 0;
    v18 = v7->Ptr;
    v19 = *(__int64 (__fastcall **)(PVOID, __int64 *))(*(_QWORD *)v7->Ptr + 48LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v29);
    v20 = v19(v18, &v29);
    v12 = v20;
    if ( v20 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x127,
        (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\customdatakeys\\localsettings_datakey.cpp",
        (const char *)(unsigned int)v20,
        v29);
LABEL_28:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v29);
      goto LABEL_29;
    }
    string = 0;
    v21 = v29;
    v22 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v29 + 48LL);
    WindowsDeleteString(0);
    string = 0;
    v23 = v22(v21, &string);
    v12 = v23;
    if ( v23 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x12A,
        (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\customdatakeys\\localsettings_datakey.cpp",
        (const char *)(unsigned int)v23,
        v29);
LABEL_27:
      WindowsDeleteString(string);
      string = 0;
      goto LABEL_28;
    }
    v30 = 0;
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    appended = CSpDynamicString::AppendHR((CSpDynamicString *)&v30, StringRawBuffer);
    v12 = appended;
    if ( appended < 0 )
    {
      v26 = 301;
LABEL_26:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v26,
        (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\customdatakeys\\localsettings_datakey.cpp",
        (const char *)(unsigned int)appended,
        v29);
      SPPIPEINFO::~SPPIPEINFO((SPPIPEINFO *)&v30);
      goto LABEL_27;
    }
    v27 = v30;
    v30 = 0;
    *a3 = v27;
    ++*v8;
    appended = (*(__int64 (__fastcall **)(PVOID, char *))(*(_QWORD *)v7->Ptr + 64LL))(v7->Ptr, &v34);
    v12 = appended;
    if ( appended < 0 )
    {
      v26 = 305;
      goto LABEL_26;
    }
    SPPIPEINFO::~SPPIPEINFO((SPPIPEINFO *)&v30);
    WindowsDeleteString(string);
    string = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v29);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v32);
    return 0;
  }
  else
  {
LABEL_31:
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v32);
    return 2147766329LL;
  }
}

```

## disassembly

```asm
0x180263d70  mov     [rsp-38h+arg_8], rbx
0x180263d75  push    rbp
0x180263d76  push    rsi
0x180263d77  push    rdi
0x180263d78  push    r12
0x180263d7a  push    r13
0x180263d7c  push    r14
0x180263d7e  push    r15
0x180263d80  mov     rbp, rsp
0x180263d83  sub     rsp, 40h
0x180263d87  mov     r12, r8
0x180263d8a  mov     r15d, edx
0x180263d8d  mov     rdi, rcx
0x180263d90  lea     rbx, [rcx+68h]
0x180263d94  mov     rcx, rbx; SRWLock
0x180263d97  call    cs:__imp_AcquireSRWLockExclusive
0x180263d9d  mov     [rbp+var_8], rbx
0x180263da1  lea     r14, [rdi+58h]
0x180263da5  xor     r13d, r13d
0x180263da8  lea     rsi, [rdi+74h]
0x180263dac  cmp     [r14], r13
0x180263daf  jz      short loc_180263DBA
0x180263db1  cmp     r15d, [rsi]
0x180263db4  jnb     loc_180263E4D
0x180263dba  mov     [rsi], r13d
0x180263dbd  mov     [rbp+var_10], r13
0x180263dc1  mov     rdi, [rdi+48h]
0x180263dc5  mov     rax, [rdi]
0x180263dc8  mov     rbx, [rax]
0x180263dcb  lea     rcx, [rbp+var_10]
0x180263dcf  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180263dd4  lea     r8, [rbp+var_10]
0x180263dd8  lea     rdx, _GUID_fe2f3d47_5d47_5499_8374_430c7cda0204
0x180263ddf  mov     rcx, rdi
0x180263de2  mov     rax, rbx
0x180263de5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180263dea  mov     ebx, eax
0x180263dec  test    eax, eax
0x180263dee  jns     short loc_180263DF7
0x180263df0  mov     edx, 119h
0x180263df5  jmp     short loc_180263E23
0x180263df7  mov     rdi, [rbp+var_10]
0x180263dfb  mov     rax, [rdi]
0x180263dfe  mov     rbx, [rax+30h]
0x180263e02  mov     rcx, r14
0x180263e05  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180263e0a  mov     rdx, r14
0x180263e0d  mov     rcx, rdi
0x180263e10  mov     rax, rbx
0x180263e13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180263e18  mov     ebx, eax
0x180263e1a  test    eax, eax
0x180263e1c  jns     short loc_180263E44
0x180263e1e  mov     edx, 11Ah; void *
0x180263e23  mov     r9d, eax; char *
0x180263e26  lea     r8, aOnecoreuapEndu_314; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x180263e2d  mov     rcx, [rbp+38h]; this
0x180263e31  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180263e36  lea     rcx, [rbp+var_10]
0x180263e3a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180263e3f  jmp     loc_180263FDF
0x180263e44  lea     rcx, [rbp+var_10]
0x180263e48  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180263e4d  mov     [rbp+arg_0], r13b
0x180263e51  mov     rcx, [r14]
0x180263e54  mov     rax, [rcx]
0x180263e57  lea     rdx, [rbp+arg_0]
0x180263e5b  mov     rax, [rax+38h]
0x180263e5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180263e64  mov     ebx, eax
0x180263e66  test    eax, eax
0x180263e68  jns     short loc_180263E87
0x180263e6a  mov     edx, 11Eh; void *
0x180263e6f  lea     r8, aOnecoreuapEndu_314; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x180263e76  mov     r9d, eax; char *
0x180263e79  mov     rcx, [rbp+38h]; this
0x180263e7d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180263e82  jmp     loc_180263FDF
0x180263e87  cmp     [rsi], r15d
0x180263e8a  jnb     short loc_180263EBA
0x180263e8c  cmp     [rbp+arg_0], r13b
0x180263e90  jz      loc_180264019
0x180263e96  mov     rcx, [r14]
0x180263e99  mov     rax, [rcx]
0x180263e9c  lea     rdx, [rbp+arg_0]
0x180263ea0  mov     rax, [rax+40h]
0x180263ea4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180263ea9  mov     ebx, eax
0x180263eab  test    eax, eax
0x180263ead  js      short loc_180263EB3
0x180263eaf  inc     dword ptr [rsi]
0x180263eb1  jmp     short loc_180263E87
0x180263eb3  mov     edx, 121h
0x180263eb8  jmp     short loc_180263E6F
0x180263eba  cmp     [rbp+arg_0], r13b
0x180263ebe  jz      loc_180264019
0x180263ec4  mov     [rbp+var_20], r13
0x180263ec8  mov     rdi, [r14]
0x180263ecb  mov     rax, [rdi]
0x180263ece  mov     rbx, [rax+30h]
0x180263ed2  lea     rcx, [rbp+var_20]
0x180263ed6  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180263edb  lea     rdx, [rbp+var_20]
0x180263edf  mov     rcx, rdi
0x180263ee2  mov     rax, rbx
0x180263ee5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180263eea  mov     ebx, eax
0x180263eec  test    eax, eax
0x180263eee  jns     short loc_180263F0D
0x180263ef0  mov     rcx, [rbp+38h]; this
0x180263ef4  mov     r9d, eax; char *
0x180263ef7  lea     r8, aOnecoreuapEndu_314; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x180263efe  mov     edx, 127h; void *
0x180263f03  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180263f08  jmp     loc_180263FD6
0x180263f0d  mov     [rbp+string], r13
0x180263f11  mov     rdi, [rbp+var_20]
0x180263f15  mov     rax, [rdi]
0x180263f18  mov     rbx, [rax+30h]
0x180263f1c  xor     ecx, ecx; string
0x180263f1e  call    cs:__imp_WindowsDeleteString
0x180263f24  mov     [rbp+string], r13
0x180263f28  lea     rdx, [rbp+string]
0x180263f2c  mov     rcx, rdi
0x180263f2f  mov     rax, rbx
0x180263f32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180263f37  mov     ebx, eax
0x180263f39  test    eax, eax
0x180263f3b  jns     short loc_180263F57
0x180263f3d  mov     rcx, [rbp+38h]; this
0x180263f41  mov     r9d, eax; char *
0x180263f44  lea     r8, aOnecoreuapEndu_314; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x180263f4b  mov     edx, 12Ah; void *
0x180263f50  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180263f55  jmp     short loc_180263FC8
0x180263f57  mov     [rbp+var_18], r13
0x180263f5b  xor     edx, edx; length
0x180263f5d  mov     rcx, [rbp+string]; string
0x180263f61  call    cs:__imp_WindowsGetStringRawBuffer
0x180263f67  mov     rdx, rax; Src
0x180263f6a  lea     rcx, [rbp+var_18]; this
0x180263f6e  call    ?AppendHR@CSpDynamicString@@QEAAJPEBG@Z; CSpDynamicString::AppendHR(ushort const *)
0x180263f73  mov     ebx, eax
0x180263f75  test    eax, eax
0x180263f77  jns     short loc_180263F80
0x180263f79  mov     edx, 12Dh
0x180263f7e  jmp     short loc_180263FAC
0x180263f80  mov     rax, [rbp+var_18]
0x180263f84  mov     [rbp+var_18], r13
0x180263f88  mov     [r12], rax
0x180263f8c  inc     dword ptr [rsi]
0x180263f8e  mov     rcx, [r14]
0x180263f91  mov     rax, [rcx]
0x180263f94  lea     rdx, [rbp+arg_0]
0x180263f98  mov     rax, [rax+40h]
0x180263f9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180263fa1  mov     ebx, eax
0x180263fa3  test    eax, eax
0x180263fa5  jns     short loc_180263FEC
0x180263fa7  mov     edx, 131h; void *
0x180263fac  mov     r9d, eax; char *
0x180263faf  lea     r8, aOnecoreuapEndu_314; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x180263fb6  mov     rcx, [rbp+38h]; this
0x180263fba  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180263fbf  lea     rcx, [rbp+var_18]; this
0x180263fc3  call    ??1SPPIPEINFO@@QEAA@XZ; SPPIPEINFO::~SPPIPEINFO(void)
0x180263fc8  mov     rcx, [rbp+string]; string
0x180263fcc  call    cs:__imp_WindowsDeleteString
0x180263fd2  mov     [rbp+string], r13
0x180263fd6  lea     rcx, [rbp+var_20]
0x180263fda  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180263fdf  lea     rcx, [rbp+var_8]
0x180263fe3  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x180263fe8  mov     eax, ebx
0x180263fea  jmp     short loc_180264027
0x180263fec  lea     rcx, [rbp+var_18]; this
0x180263ff0  call    ??1SPPIPEINFO@@QEAA@XZ; SPPIPEINFO::~SPPIPEINFO(void)
0x180263ff5  mov     rcx, [rbp+string]; string
0x180263ff9  call    cs:__imp_WindowsDeleteString
0x180263fff  mov     [rbp+string], r13
0x180264003  lea     rcx, [rbp+var_20]
0x180264007  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18026400c  lea     rcx, [rbp+var_8]
0x180264010  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x180264015  xor     eax, eax
0x180264017  jmp     short loc_180264027
0x180264019  lea     rcx, [rbp+var_8]
0x18026401d  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x180264022  mov     eax, 80045039h
0x180264027  mov     rbx, [rsp+40h+arg_8]
0x18026402f  add     rsp, 40h
0x180264033  pop     r15
0x180264035  pop     r14
0x180264037  pop     r13
0x180264039  pop     r12
0x18026403b  pop     rdi
0x18026403c  pop     rsi
0x18026403d  pop     rbp
0x18026403e  retn
```
