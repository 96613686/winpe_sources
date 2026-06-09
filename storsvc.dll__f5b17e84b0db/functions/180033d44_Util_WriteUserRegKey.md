# Util::WriteUserRegKey

- ea: `0x180033d44`
- end: `0x180033eb5`
- name: `Util::WriteUserRegKey`
- size: `369`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, service_task`

## callers

- `0x180032088`

## callees

- `0x1800108f4`
- `0x180010d24`
- `0x180012734`
- `0x180019210`
- `0x180019d4c`
- `0x180019db4`
- `0x18001dcf4`
- `0x180033d44`
- `0x18003e95c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033e27`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033e27`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180033de2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180033de2`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180033df8`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180033df8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180033d7c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180033d7c`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180033e74`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180033e74`
- `RPCRT4!RpcRevertToSelf` at `0x180033e89`
- `RPCRT4!RpcRevertToSelf` at `0x180033e89`
- `RPCRT4!RpcImpersonateClient` at `0x180033e04`
- `RPCRT4!RpcImpersonateClient` at `0x180033e04`

## string_xrefs

- `0x180033db8`: `onecore\drivers\storage\storsvc\service\storagepolicy.cpp`
- `0x180033e38`: `onecore\drivers\storage\storsvc\service\storagepolicy.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall Util::WriteUserRegKey(__int64 a1, __int64 a2, const WCHAR *a3, __int64 a4, LPCVOID a5)
{
  int v6; // eax
  unsigned int v7; // ebx
  HANDLE CurrentThread; // rax
  RPC_STATUS v9; // eax
  DWORD LastError; // eax
  LSTATUS v11; // eax
  unsigned int lpData; // [rsp+20h] [rbp-20h]
  void *TokenHandle; // [rsp+30h] [rbp-10h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+8h]
  __int64 v17; // [rsp+58h] [rbp+18h]

  v17 = a2;
  hKey = 0;
  v6 = OpenStorageRegKey(HKEY_CURRENT_USER, (wchar_t *)L"OptimizeStorage", &hKey);
  v7 = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x793,
      (unsigned int)"onecore\\drivers\\storage\\storsvc\\service\\storagepolicy.cpp",
      (const char *)(unsigned int)v6,
      lpData);
    goto LABEL_13;
  }
  TokenHandle = 0;
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    &TokenHandle,
    0);
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0xCu, 1, &TokenHandle) )
  {
    LastError = GetLastError();
    if ( LastError )
    {
      v7 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x7A0,
             (unsigned int)"onecore\\drivers\\storage\\storsvc\\service\\storagepolicy.cpp",
             (const char *)LastError,
             lpData);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
      goto LABEL_13;
    }
  }
  else
  {
    v9 = RpcImpersonateClient(0);
    v7 = v9;
    if ( v9 )
    {
      if ( v9 > 0 )
        v7 = (unsigned __int16)v9 | 0x80070000;
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
      goto LABEL_13;
    }
  }
  v11 = RegSetKeyValueW(hKey, 0, a3, 4u, a5, 4u);
  v7 = v11;
  if ( v11 > 0 )
    v7 = (unsigned __int16)v11 | 0x80070000;
  RpcRevertToSelf();
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
LABEL_13:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return v7;
}

```

## disassembly

```asm
0x180033d44  mov     [rsp-8+arg_0], rbx
0x180033d49  mov     [rsp-8+arg_10], rdi
0x180033d4e  mov     [rsp-8+arg_8], rdx
0x180033d53  push    rbp
0x180033d54  mov     rbp, rsp
0x180033d57  sub     rsp, 40h
0x180033d5b  mov     rdi, r8
0x180033d5e  mov     [rbp+hKey], 0
0x180033d66  mov     rbx, [rbp+hKey]
0x180033d6a  test    rbx, rbx
0x180033d6d  jz      short loc_180033D8C
0x180033d6f  lea     rcx, [rbp+arg_8]; this
0x180033d73  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180033d78  nop
0x180033d79  mov     rcx, rbx; hKey
0x180033d7c  call    cs:__imp_RegCloseKey
0x180033d82  nop
0x180033d83  lea     rcx, [rbp+arg_8]; this
0x180033d87  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180033d8c  mov     [rbp+hKey], 0
0x180033d94  lea     r8, [rbp+hKey]; phkResult
0x180033d98  lea     rdx, aOptimizestorag; "OptimizeStorage"
0x180033d9f  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180033da6  call    ?OpenStorageRegKey@@YAJPEAUHKEY__@@PEBGPEAPEAU1@@Z; OpenStorageRegKey(HKEY__ *,ushort const *,HKEY__ * *)
0x180033dab  mov     ebx, eax
0x180033dad  test    eax, eax
0x180033daf  jns     short loc_180033DCF
0x180033db1  mov     rcx, [rbp+8]; this
0x180033db5  mov     r9d, eax; char *
0x180033db8  lea     r8, aOnecoreDrivers_25; "onecore\\drivers\\storage\\storsvc\\ser"...
0x180033dbf  mov     edx, 793h; void *
0x180033dc4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180033dc9  nop
0x180033dca  jmp     loc_180033E9A
0x180033dcf  mov     [rbp+TokenHandle], 0
0x180033dd7  xor     edx, edx
0x180033dd9  lea     rcx, [rbp+TokenHandle]
0x180033ddd  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180033de2  call    cs:__imp_GetCurrentThread
0x180033de8  lea     r9, [rbp+TokenHandle]; TokenHandle
0x180033dec  mov     edx, 0Ch; DesiredAccess
0x180033df1  lea     r8d, [rdx-0Bh]; OpenAsSelf
0x180033df5  mov     rcx, rax; ThreadHandle
0x180033df8  call    cs:__imp_OpenThreadToken
0x180033dfe  test    eax, eax
0x180033e00  jnz     short loc_180033E27
0x180033e02  xor     ecx, ecx; BindingHandle
0x180033e04  call    cs:__imp_RpcImpersonateClient
0x180033e0a  mov     ebx, eax
0x180033e0c  test    eax, eax
0x180033e0e  jz      short loc_180033E57
0x180033e10  jle     short loc_180033E1B
0x180033e12  movzx   ebx, ax
0x180033e15  or      ebx, 80070000h
0x180033e1b  lea     rcx, [rbp+TokenHandle]
0x180033e1f  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180033e24  nop
0x180033e25  jmp     short loc_180033E9A
0x180033e27  call    cs:__imp_GetLastError
0x180033e2d  test    eax, eax
0x180033e2f  jz      short loc_180033E57
0x180033e31  mov     rcx, [rbp+8]; this
0x180033e35  mov     r9d, eax; char *
0x180033e38  lea     r8, aOnecoreDrivers_25; "onecore\\drivers\\storage\\storsvc\\ser"...
0x180033e3f  mov     edx, 7A0h; void *
0x180033e44  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180033e49  mov     ebx, eax
0x180033e4b  lea     rcx, [rbp+TokenHandle]
0x180033e4f  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180033e54  nop
0x180033e55  jmp     short loc_180033E9A
0x180033e57  mov     r9d, 4; dwType
0x180033e5d  mov     [rsp+40h+cbData], r9d; cbData
0x180033e62  mov     rax, [rbp+arg_20]
0x180033e66  mov     [rsp+40h+lpData], rax; lpData
0x180033e6b  mov     r8, rdi; lpValueName
0x180033e6e  xor     edx, edx; lpSubKey
0x180033e70  mov     rcx, [rbp+hKey]; hKey
0x180033e74  call    cs:__imp_RegSetKeyValueW
0x180033e7a  mov     ebx, eax
0x180033e7c  test    eax, eax
0x180033e7e  jle     short loc_180033E89
0x180033e80  movzx   ebx, ax
0x180033e83  or      ebx, 80070000h
0x180033e89  call    cs:__imp_RpcRevertToSelf
0x180033e8f  nop
0x180033e90  lea     rcx, [rbp+TokenHandle]
0x180033e94  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180033e99  nop
0x180033e9a  lea     rcx, [rbp+hKey]
0x180033e9e  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180033ea3  mov     eax, ebx
0x180033ea5  mov     rbx, [rsp+40h+arg_0]
0x180033eaa  mov     rdi, [rsp+40h+arg_10]
0x180033eaf  add     rsp, 40h
0x180033eb3  pop     rbp
0x180033eb4  retn
```
