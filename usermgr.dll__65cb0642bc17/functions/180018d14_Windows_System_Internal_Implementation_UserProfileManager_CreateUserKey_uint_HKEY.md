# Windows::System::Internal::Implementation::UserProfileManager::CreateUserKey(uint,HKEY__ * *)

- ea: `0x180018d14`
- end: `0x180018f95`
- name: `?CreateUserKey@UserProfileManager@Implementation@Internal@System@Windows@@SAJIPEAPEAUHKEY__@@@Z`
- size: `641`
- prototype: `__int64 __fastcall(unsigned int Value, HKEY *)`
- caller_count: `8`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18004b4e4`
- `0x18004c71c`
- `0x18004c910`
- `0x180060e10`
- `0x1800633c8`
- `0x1800c21d0`
- `0x1800c2ae0`
- `0x1800e07e9`

## callees

- `0x18000acdc`
- `0x18000ce48`
- `0x180018d14`
- `0x180034454`
- `0x1800344b8`
- `0x18004e508`
- `0x1800de450`
- `0x1800ec010`

## import_xrefs

- `msvcrt!_ui64tow_s` at `0x180018e09`
- `msvcrt!_ui64tow_s` at `0x180018e09`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180018e32`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180018e97`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180018f59`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180018f69`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180018e32`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180018e97`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180018f59`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180018f69`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180018ef0`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180018ef0`

## string_xrefs

- `0x180018d58`: `onecore\ds\security\umstartup\usermgr\lib\knownusermanager.cpp`
- `0x180018d7d`: `onecore\ds\security\umstartup\usermgr\lib\knownusermanager.cpp`
- `0x180018e6f`: `onecore\ds\security\umstartup\usermgr\lib\knownusermanager.cpp`
- `0x180018f05`: `onecore\ds\security\umstartup\usermgr\lib\knownusermanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall Windows::System::Internal::Implementation::UserProfileManager::CreateUserKey(
        unsigned int Value,
        HKEY *a2)
{
  unsigned __int64 v3; // rsi
  void (__fastcall *v4)(void *, __int64 *); // rbx
  __int64 (*v5)(void); // r14
  HKEY v6; // rbx
  unsigned int v7; // eax
  HKEY v8; // rbx
  unsigned int v9; // eax
  HKEY v10; // rcx
  __int64 v11; // rdx
  wil *v13; // rcx
  unsigned int v14; // eax
  DWORD dwOptions; // [rsp+20h] [rbp-A8h]
  DWORD dwOptionsa; // [rsp+20h] [rbp-A8h]
  DWORD dwOptionsb; // [rsp+20h] [rbp-A8h]
  HKEY phkResult; // [rsp+50h] [rbp-78h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-70h]
  DWORD dwDisposition; // [rsp+60h] [rbp-68h] BYREF
  __int64 v21; // [rsp+68h] [rbp-60h] BYREF
  _BYTE v22[8]; // [rsp+70h] [rbp-58h] BYREF
  HKEY *p_phkResult; // [rsp+78h] [rbp-50h]
  char v24; // [rsp+80h] [rbp-48h]
  wchar_t Buffer[12]; // [rsp+88h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+0h]

  v3 = Value;
  if ( Value - 16 > 0xFFFF0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x219,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\knownusermanager.cpp",
      (const char *)0x80070057LL,
      dwOptionsa);
  if ( !a2 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x21A,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\knownusermanager.cpp",
      (const char *)0x80004003LL,
      dwOptionsa);
  *a2 = 0;
  dwDisposition = 0;
  phkResult = 0;
  hKey = 0;
  v21 = 0;
  v4 = *(void (__fastcall **)(void *, __int64 *))(Windows::System::Internal::Adapters::g_AdapterCollection + 72LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v21);
  v4(&Windows::System::Internal::Adapters::g_AdapterCollection, &v21);
  p_phkResult = &phkResult;
  v24 = 1;
  _ui64tow_s(v3, Buffer, 0xBu, 10);
  v5 = *(__int64 (**)(void))(*(_QWORD *)v21 + 24LL);
  v6 = hKey;
  if ( hKey )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)v22);
    RegCloseKey(v6);
    wil::last_error_context::~last_error_context((wil::last_error_context *)v22);
  }
  hKey = 0;
  try
  {
    v7 = v5();
    if ( v7 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x22D,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\knownusermanager.cpp",
        (const char *)v7,
        dwOptionsa);
    v8 = phkResult;
    if ( phkResult )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)v22);
      RegCloseKey(v8);
      wil::last_error_context::~last_error_context((wil::last_error_context *)v22);
    }
    phkResult = 0;
    v9 = RegCreateKeyExW(hKey, Buffer, 0, 0, 0, 0x2001Fu, 0, &phkResult, &dwDisposition);
    if ( v9 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x22E,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\knownusermanager.cpp",
        (const char *)v9,
        dwOptionsb);
    *a2 = phkResult;
    v10 = 0;
    phkResult = 0;
  }
  catch ( ... )
  {
    v13 = (wil *)hKey;
    if ( hKey )
    {
      if ( dwDisposition == 1 )
        RegDeleteKeyW(hKey, Buffer);
    }
    v14 = wil::ResultFromCaughtException(v13);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x239,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\knownusermanager.cpp",
      (const char *)v14,
      dwOptions);
  }
  v11 = v21;
  if ( v21 )
  {
    v21 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
    v10 = phkResult;
  }
  if ( hKey )
  {
    RegCloseKey(hKey);
    v10 = phkResult;
  }
  if ( v10 )
    RegCloseKey(v10);
  return 0;
}

```

## disassembly

```asm
0x180018d14  mov     [rsp+arg_10], rbx
0x180018d19  push    rsi
0x180018d1a  push    rdi
0x180018d1b  push    r14
0x180018d1d  sub     rsp, 0B0h
0x180018d24  mov     rax, cs:__security_cookie
0x180018d2b  xor     rax, rsp
0x180018d2e  mov     [rsp+0C8h+var_28], rax
0x180018d36  mov     rdi, rdx
0x180018d39  mov     esi, ecx
0x180018d3b  lea     eax, [rsi-10h]
0x180018d3e  cmp     eax, 0FFFF0h
0x180018d43  setbe   al
0x180018d46  mov     rcx, [rsp+0C8h]; this
0x180018d4e  test    al, al
0x180018d50  jnz     short loc_180018D6A
0x180018d52  mov     r9d, 80070057h; char *
0x180018d58  lea     r8, aOnecoreDsSecur_60; "onecore\\ds\\security\\umstartup\\userm"...
0x180018d5f  mov     edx, 219h; void *
0x180018d64  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180018d6a  mov     rcx, [rsp+0C8h]; this
0x180018d72  test    rdi, rdi
0x180018d75  jnz     short loc_180018D8F
0x180018d77  mov     r9d, 80004003h; char *
0x180018d7d  lea     r8, aOnecoreDsSecur_60; "onecore\\ds\\security\\umstartup\\userm"...
0x180018d84  mov     edx, 21Ah; void *
0x180018d89  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180018d8f  mov     qword ptr [rdx], 0
0x180018d96  mov     [rsp+0C8h+dwDisposition], 0
0x180018d9e  mov     [rsp+0C8h+var_78], 0
0x180018da7  mov     [rsp+0C8h+hKey], 0
0x180018db0  mov     [rsp+0C8h+var_60], 0
0x180018db9  mov     rax, cs:?g_AdapterCollection@Adapters@Internal@System@Windows@@3VAdapterCollection@1234@A; Windows::System::Internal::Adapters::AdapterCollection Windows::System::Internal::Adapters::g_AdapterCollection
0x180018dc0  mov     rbx, [rax+48h]
0x180018dc4  lea     rcx, [rsp+0C8h+var_60]
0x180018dc9  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180018dce  lea     rdx, [rsp+0C8h+var_60]
0x180018dd3  lea     rcx, ?g_AdapterCollection@Adapters@Internal@System@Windows@@3VAdapterCollection@1234@A; Windows::System::Internal::Adapters::AdapterCollection Windows::System::Internal::Adapters::g_AdapterCollection
0x180018dda  mov     rax, rbx
0x180018ddd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018de2  lea     rax, [rsp+0C8h+var_78]
0x180018de7  mov     [rsp+0C8h+var_50], rax
0x180018dec  mov     [rsp+0C8h+var_48], 1
0x180018df4  mov     rcx, rsi; Value
0x180018df7  mov     r9d, 0Ah; Radix
0x180018dfd  lea     r8d, [r9+1]; BufferCount
0x180018e01  lea     rdx, [rsp+0C8h+Buffer]; Buffer
0x180018e09  call    cs:__imp__ui64tow_s
0x180018e0f  mov     rsi, [rsp+0C8h+var_60]
0x180018e14  mov     rax, [rsi]
0x180018e17  mov     r14, [rax+18h]
0x180018e1b  mov     rbx, [rsp+0C8h+hKey]
0x180018e20  test    rbx, rbx
0x180018e23  jz      short loc_180018E42
0x180018e25  lea     rcx, [rsp+0C8h+var_58]; this
0x180018e2a  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180018e2f  mov     rcx, rbx; hKey
0x180018e32  call    cs:__imp_RegCloseKey
0x180018e38  lea     rcx, [rsp+0C8h+var_58]; this
0x180018e3d  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180018e42  mov     [rsp+0C8h+hKey], 0
0x180018e4b  lea     r8, [rsp+0C8h+hKey]
0x180018e50  mov     edx, 20006h
0x180018e55  mov     rcx, rsi
0x180018e58  mov     rax, r14
0x180018e5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018e60  mov     rcx, [rsp+0C8h]; this
0x180018e68  test    eax, eax
0x180018e6a  jz      short loc_180018E80
0x180018e6c  mov     r9d, eax; char *
0x180018e6f  lea     r8, aOnecoreDsSecur_60; "onecore\\ds\\security\\umstartup\\userm"...
0x180018e76  mov     edx, 22Dh; void *
0x180018e7b  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180018e80  mov     rbx, [rsp+0C8h+var_78]
0x180018e85  test    rbx, rbx
0x180018e88  jz      short loc_180018EA7
0x180018e8a  lea     rcx, [rsp+0C8h+var_58]; this
0x180018e8f  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180018e94  mov     rcx, rbx; hKey
0x180018e97  call    cs:__imp_RegCloseKey
0x180018e9d  lea     rcx, [rsp+0C8h+var_58]; this
0x180018ea2  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180018ea7  mov     [rsp+0C8h+var_78], 0
0x180018eb0  lea     rax, [rsp+0C8h+dwDisposition]
0x180018eb5  mov     [rsp+0C8h+lpdwDisposition], rax; lpdwDisposition
0x180018eba  lea     rax, [rsp+0C8h+var_78]
0x180018ebf  mov     [rsp+0C8h+phkResult], rax; phkResult
0x180018ec4  mov     [rsp+0C8h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180018ecd  mov     [rsp+0C8h+samDesired], 2001Fh; samDesired
0x180018ed5  mov     [rsp+0C8h+dwOptions], 0; unsigned int
0x180018edd  xor     r9d, r9d; lpClass
0x180018ee0  xor     r8d, r8d; Reserved
0x180018ee3  lea     rdx, [rsp+0C8h+Buffer]; lpSubKey
0x180018eeb  mov     rcx, [rsp+0C8h+hKey]; hKey
0x180018ef0  call    cs:__imp_RegCreateKeyExW
0x180018ef6  mov     rcx, [rsp+0C8h]; this
0x180018efe  test    eax, eax
0x180018f00  jz      short loc_180018F16
0x180018f02  mov     r9d, eax; char *
0x180018f05  lea     r8, aOnecoreDsSecur_60; "onecore\\ds\\security\\umstartup\\userm"...
0x180018f0c  mov     edx, 22Eh; void *
0x180018f11  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180018f16  mov     rax, [rsp+0C8h+var_78]
0x180018f1b  mov     [rdi], rax
0x180018f1e  xor     ecx, ecx
0x180018f20  mov     [rsp+0C8h+var_78], rcx
0x180018f25  mov     rdx, [rsp+0C8h+var_60]
0x180018f2a  test    rdx, rdx
0x180018f2d  jz      short loc_180018F4C
0x180018f2f  mov     [rsp+0C8h+var_60], 0
0x180018f38  mov     rax, [rdx]
0x180018f3b  mov     rcx, rdx
0x180018f3e  mov     rax, [rax+10h]
0x180018f42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018f47  mov     rcx, [rsp+0C8h+var_78]
0x180018f4c  mov     rax, [rsp+0C8h+hKey]
0x180018f51  test    rax, rax
0x180018f54  jz      short loc_180018F64
0x180018f56  mov     rcx, rax; hKey
0x180018f59  call    cs:__imp_RegCloseKey
0x180018f5f  mov     rcx, [rsp+0C8h+var_78]; hKey
0x180018f64  test    rcx, rcx
0x180018f67  jz      short loc_180018F6F
0x180018f69  call    cs:__imp_RegCloseKey
0x180018f6f  xor     eax, eax
0x180018f71  mov     rcx, [rsp+0C8h+var_28]
0x180018f79  xor     rcx, rsp; StackCookie
0x180018f7c  call    __security_check_cookie
0x180018f81  mov     rbx, [rsp+0C8h+arg_10]
0x180018f89  add     rsp, 0B0h
0x180018f90  pop     r14
0x180018f92  pop     rdi
0x180018f93  pop     rsi
0x180018f94  retn
```
