# CreateEventWithUserSecurity(ushort const *)

- ea: `0x18002167c`
- end: `0x1800217fb`
- name: `?CreateEventWithUserSecurity@@YAPEAXPEBG@Z`
- size: `383`
- prototype: `void *__fastcall(LPCWSTR lpName)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800211c0`

## callees

- `0x18002167c`
- `0x180035830`
- `0x1800364ac`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800217d1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800217da`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800217d1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800217da`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800216e4`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800216e4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800216a3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800216d3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800216a3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800216d3`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x1800216ac`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x1800216ac`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800217c3`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800217c3`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180021712`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180021712`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800216bc`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800216bc`
- `ntdll!RtlCreateAcl` at `0x18002174e`
- `ntdll!RtlCreateAcl` at `0x18002174e`
- `ntdll!RtlAddAccessAllowedAce` at `0x180021769`
- `ntdll!RtlAddAccessAllowedAce` at `0x180021769`
- `ntdll!RtlCreateSecurityDescriptor` at `0x18002177b`
- `ntdll!RtlCreateSecurityDescriptor` at `0x18002177b`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x180021793`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x180021793`

## pseudocode

```c
HANDLE __fastcall CreateEventWithUserSecurity(LPCWSTR lpName)
{
  HANDLE v2; // rbx
  HANDLE CurrentProcess; // rax
  DWORD ProcessId; // eax
  HANDLE v5; // rdi
  HANDLE v6; // rax
  void *TokenHandle; // [rsp+30h] [rbp-D0h] BYREF
  struct _SECURITY_ATTRIBUTES EventAttributes; // [rsp+38h] [rbp-C8h] BYREF
  DWORD ReturnLength; // [rsp+50h] [rbp-B0h] BYREF
  _OWORD SecurityDescriptor[2]; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v12; // [rsp+78h] [rbp-88h]
  struct _ACL Acl; // [rsp+80h] [rbp-80h] BYREF
  PSID TokenInformation[20]; // [rsp+D0h] [rbp-30h] BYREF

  v2 = 0;
  CurrentProcess = GetCurrentProcess();
  ProcessId = GetProcessId(CurrentProcess);
  v5 = OpenProcess(0x400u, 0, ProcessId);
  if ( v5 )
  {
    TokenHandle = 0;
    v6 = GetCurrentProcess();
    if ( OpenProcessToken(v6, 8u, &TokenHandle) )
    {
      ReturnLength = 0;
      if ( GetTokenInformation(TokenHandle, TokenUser, TokenInformation, 0xA0u, &ReturnLength) )
      {
        memset_0(&Acl, 0, 0x50u);
        v12 = 0;
        memset(SecurityDescriptor, 0, sizeof(SecurityDescriptor));
        if ( !RtlCreateAcl(&Acl, 0x50u, 2u)
          && !RtlAddAccessAllowedAce(&Acl, 2u, 0x10000000u, TokenInformation[0])
          && !RtlCreateSecurityDescriptor(SecurityDescriptor, 1u)
          && !RtlSetDaclSecurityDescriptor(SecurityDescriptor, 1u, &Acl, 0) )
        {
          *(_QWORD *)&EventAttributes.nLength = 24;
          EventAttributes.lpSecurityDescriptor = SecurityDescriptor;
          *(_QWORD *)&EventAttributes.bInheritHandle = 0;
          v2 = CreateEventW(&EventAttributes, 1, 0, lpName);
        }
      }
      CloseHandle(TokenHandle);
    }
    CloseHandle(v5);
  }
  return v2;
}

```

## disassembly

```asm
0x18002167c  push    rbp
0x18002167e  push    rbx
0x18002167f  push    rsi
0x180021680  push    rdi
0x180021681  lea     rbp, [rsp-88h]
0x180021689  sub     rsp, 188h
0x180021690  mov     rax, cs:__security_cookie
0x180021697  xor     rax, rsp
0x18002169a  mov     [rbp+0A0h+var_30], rax
0x18002169e  mov     rsi, rcx
0x1800216a1  xor     ebx, ebx
0x1800216a3  call    cs:__imp_GetCurrentProcess
0x1800216a9  mov     rcx, rax; Process
0x1800216ac  call    cs:__imp_GetProcessId
0x1800216b2  xor     edx, edx; bInheritHandle
0x1800216b4  mov     ecx, 400h; dwDesiredAccess
0x1800216b9  mov     r8d, eax; dwProcessId
0x1800216bc  call    cs:__imp_OpenProcess
0x1800216c2  mov     rdi, rax
0x1800216c5  test    rax, rax
0x1800216c8  jz      loc_1800217E0
0x1800216ce  mov     [rsp+1A0h+TokenHandle], rbx
0x1800216d3  call    cs:__imp_GetCurrentProcess
0x1800216d9  mov     rcx, rax; ProcessHandle
0x1800216dc  lea     r8, [rsp+1A0h+TokenHandle]; TokenHandle
0x1800216e1  lea     edx, [rbx+8]; DesiredAccess
0x1800216e4  call    cs:__imp_OpenProcessToken
0x1800216ea  test    eax, eax
0x1800216ec  jz      loc_1800217D7
0x1800216f2  mov     rcx, [rsp+1A0h+TokenHandle]; TokenHandle
0x1800216f7  lea     rax, [rsp+1A0h+var_150]
0x1800216fc  mov     r9d, 0A0h; TokenInformationLength
0x180021702  mov     [rsp+1A0h+ReturnLength], rax; ReturnLength
0x180021707  lea     r8, [rbp+0A0h+TokenInformation]; TokenInformation
0x18002170b  mov     [rsp+1A0h+var_150], ebx
0x18002170f  lea     edx, [rbx+1]; TokenInformationClass
0x180021712  call    cs:__imp_GetTokenInformation
0x180021718  test    eax, eax
0x18002171a  jz      loc_1800217CC
0x180021720  xor     edx, edx; Val
0x180021722  lea     r8d, [rbx+50h]; Size
0x180021726  lea     rcx, [rbp+0A0h+Acl]; void *
0x18002172a  call    memset_0
0x18002172f  xorps   xmm0, xmm0
0x180021732  lea     edx, [rbx+50h]; AclSize
0x180021735  xor     eax, eax
0x180021737  lea     r8d, [rbx+2]; AclRevision
0x18002173b  lea     rcx, [rbp+0A0h+Acl]; Acl
0x18002173f  mov     [rsp+1A0h+var_128], rax
0x180021744  movups  [rsp+1A0h+SecurityDescriptor], xmm0
0x180021749  movups  [rsp+1A0h+var_138], xmm0
0x18002174e  call    cs:__imp_RtlCreateAcl
0x180021754  test    eax, eax
0x180021756  jnz     short loc_1800217CC
0x180021758  mov     r9, [rbp+0A0h+TokenInformation]; Sid
0x18002175c  lea     edx, [rbx+2]; Revision
0x18002175f  mov     r8d, 10000000h; AccessMask
0x180021765  lea     rcx, [rbp+0A0h+Acl]; Acl
0x180021769  call    cs:__imp_RtlAddAccessAllowedAce
0x18002176f  test    eax, eax
0x180021771  jnz     short loc_1800217CC
0x180021773  lea     edx, [rbx+1]; Revision
0x180021776  lea     rcx, [rsp+1A0h+SecurityDescriptor]; SecurityDescriptor
0x18002177b  call    cs:__imp_RtlCreateSecurityDescriptor
0x180021781  test    eax, eax
0x180021783  jnz     short loc_1800217CC
0x180021785  xor     r9d, r9d; DaclDefaulted
0x180021788  lea     r8, [rbp+0A0h+Acl]; Dacl
0x18002178c  mov     dl, 1; DaclPresent
0x18002178e  lea     rcx, [rsp+1A0h+SecurityDescriptor]; SecurityDescriptor
0x180021793  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x180021799  test    eax, eax
0x18002179b  jnz     short loc_1800217CC
0x18002179d  lea     rax, [rsp+1A0h+SecurityDescriptor]
0x1800217a2  mov     qword ptr [rsp+1A0h+EventAttributes.nLength], 18h
0x1800217ab  mov     r9, rsi; lpName
0x1800217ae  mov     [rsp+1A0h+EventAttributes.lpSecurityDescriptor], rax
0x1800217b3  xor     r8d, r8d; bInitialState
0x1800217b6  mov     qword ptr [rsp+1A0h+EventAttributes.bInheritHandle], rbx
0x1800217bb  lea     edx, [rbx+1]; bManualReset
0x1800217be  lea     rcx, [rsp+1A0h+EventAttributes]; lpEventAttributes
0x1800217c3  call    cs:__imp_CreateEventW
0x1800217c9  mov     rbx, rax
0x1800217cc  mov     rcx, [rsp+1A0h+TokenHandle]; hObject
0x1800217d1  call    cs:__imp_CloseHandle
0x1800217d7  mov     rcx, rdi; hObject
0x1800217da  call    cs:__imp_CloseHandle
0x1800217e0  mov     rax, rbx
0x1800217e3  mov     rcx, [rbp+0A0h+var_30]
0x1800217e7  xor     rcx, rsp; StackCookie
0x1800217ea  call    __security_check_cookie
0x1800217ef  add     rsp, 188h
0x1800217f6  pop     rdi
0x1800217f7  pop     rsi
0x1800217f8  pop     rbx
0x1800217f9  pop     rbp
0x1800217fa  retn
```
