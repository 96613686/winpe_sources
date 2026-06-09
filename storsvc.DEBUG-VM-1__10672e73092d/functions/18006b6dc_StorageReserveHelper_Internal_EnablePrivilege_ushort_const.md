# StorageReserveHelper::Internal::EnablePrivilege(ushort const *)

- ea: `0x18006b6dc`
- end: `0x18006b7a5`
- name: `?EnablePrivilege@Internal@StorageReserveHelper@@YA_NPEBG@Z`
- size: `201`
- prototype: `bool __fastcall(StorageReserveHelper::Internal *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18006a970`

## callees

- `0x18000d030`
- `0x180019d4c`
- `0x18001dcf4`
- `0x18006b6dc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18006b70c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18006b70c`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18006b71c`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18006b71c`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18006b775`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18006b775`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x18006b73e`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x18006b73e`

## string_xrefs

- `0x18006b735`: `SeManageVolumePrivilege`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
bool __fastcall StorageReserveHelper::Internal::EnablePrivilege(
        StorageReserveHelper::Internal *this,
        const unsigned __int16 *a2)
{
  BOOL v2; // ebx
  HANDLE CurrentProcess; // rax
  void *TokenHandle; // [rsp+30h] [rbp-30h] BYREF
  struct _LUID Luid; // [rsp+38h] [rbp-28h] BYREF
  struct _TOKEN_PRIVILEGES NewState; // [rsp+40h] [rbp-20h] BYREF

  TokenHandle = 0;
  v2 = 0;
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    &TokenHandle,
    0);
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 0x20u, &TokenHandle) )
  {
    NewState = 0;
    Luid = 0;
    if ( LookupPrivilegeValueW(0, L"SeManageVolumePrivilege", &Luid) )
    {
      NewState.PrivilegeCount = 1;
      NewState.Privileges[0].Luid = Luid;
      NewState.Privileges[0].Attributes = 2;
      v2 = AdjustTokenPrivileges(TokenHandle, 0, &NewState, 0, 0, 0);
    }
  }
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
  return v2;
}

```

## disassembly

```asm
0x18006b6dc  mov     [rsp-8+arg_0], rbx
0x18006b6e1  push    rbp
0x18006b6e2  mov     rbp, rsp
0x18006b6e5  sub     rsp, 60h
0x18006b6e9  mov     rax, cs:__security_cookie
0x18006b6f0  xor     rax, rsp
0x18006b6f3  mov     [rbp+var_10], rax
0x18006b6f7  mov     [rbp+TokenHandle], 0
0x18006b6ff  xor     ebx, ebx
0x18006b701  xor     edx, edx
0x18006b703  lea     rcx, [rbp+TokenHandle]
0x18006b707  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18006b70c  call    cs:__imp_GetCurrentProcess
0x18006b712  lea     r8, [rbp+TokenHandle]; TokenHandle
0x18006b716  lea     edx, [rbx+20h]; DesiredAccess
0x18006b719  mov     rcx, rax; ProcessHandle
0x18006b71c  call    cs:__imp_OpenProcessToken
0x18006b722  test    eax, eax
0x18006b724  jz      short loc_18006B77D
0x18006b726  xorps   xmm0, xmm0
0x18006b729  movups  xmmword ptr [rbp+NewState.PrivilegeCount], xmm0
0x18006b72d  mov     qword ptr [rbp+Luid.LowPart], rbx
0x18006b731  lea     r8, [rbp+Luid]; lpLuid
0x18006b735  lea     rdx, Name; "SeManageVolumePrivilege"
0x18006b73c  xor     ecx, ecx; lpSystemName
0x18006b73e  call    cs:__imp_LookupPrivilegeValueW
0x18006b744  test    eax, eax
0x18006b746  jz      short loc_18006B77D
0x18006b748  mov     [rbp+NewState.PrivilegeCount], 1
0x18006b74f  mov     rax, qword ptr [rbp+Luid.LowPart]
0x18006b753  mov     qword ptr [rbp+NewState.Privileges.Luid.LowPart], rax
0x18006b757  mov     [rbp+NewState.Privileges.Attributes], 2
0x18006b75e  mov     [rsp+60h+ReturnLength], rbx; ReturnLength
0x18006b763  mov     [rsp+60h+PreviousState], rbx; PreviousState
0x18006b768  xor     r9d, r9d; BufferLength
0x18006b76b  lea     r8, [rbp+NewState]; NewState
0x18006b76f  xor     edx, edx; DisableAllPrivileges
0x18006b771  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18006b775  call    cs:__imp_AdjustTokenPrivileges
0x18006b77b  mov     ebx, eax
0x18006b77d  cmp     ebx, 1
0x18006b780  setz    bl
0x18006b783  lea     rcx, [rbp+TokenHandle]
0x18006b787  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18006b78c  mov     al, bl
0x18006b78e  mov     rcx, [rbp+var_10]
0x18006b792  xor     rcx, rsp; StackCookie
0x18006b795  call    __security_check_cookie
0x18006b79a  mov     rbx, [rsp+60h+arg_0]
0x18006b79f  add     rsp, 60h
0x18006b7a3  pop     rbp
0x18006b7a4  retn
```
