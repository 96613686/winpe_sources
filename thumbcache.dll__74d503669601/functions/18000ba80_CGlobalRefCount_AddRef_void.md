# CGlobalRefCount::AddRef(void)

- ea: `0x18000ba80`
- end: `0x18000bc33`
- name: `?AddRef@CGlobalRefCount@@QEAAJXZ`
- size: `435`
- prototype: `__int64 __fastcall(CGlobalRefCount *__hidden this)`
- caller_count: `7`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000af30`
- `0x18000b120`
- `0x18000b3f0`
- `0x18000b520`
- `0x18000b5c0`
- `0x18000c77c`
- `0x180013d80`

## callees

- `0x18000b3c0`
- `0x18000ba80`
- `0x180035830`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000bbf5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000bbfe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000bbf5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000bbfe`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000bafc`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000bafc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000bab9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000bae9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000bab9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000bae9`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18000bac2`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18000bac2`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x18000bbe7`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x18000bbe7`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000bb2d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000bb2d`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18000bad2`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18000bad2`
- `ntdll!RtlCreateAcl` at `0x18000bb72`
- `ntdll!RtlCreateAcl` at `0x18000bb72`
- `ntdll!RtlAddAccessAllowedAce` at `0x18000bb8f`
- `ntdll!RtlAddAccessAllowedAce` at `0x18000bb8f`
- `ntdll!RtlCreateSecurityDescriptor` at `0x18000bba3`
- `ntdll!RtlCreateSecurityDescriptor` at `0x18000bba3`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x18000bbbb`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x18000bbbb`

## pseudocode

```c
__int64 __fastcall CGlobalRefCount::AddRef(const WCHAR **this)
{
  const WCHAR *v1; // r14
  const WCHAR *v2; // rdi
  HANDLE CurrentProcess; // rax
  DWORD ProcessId; // eax
  HANDLE v6; // rsi
  HANDLE v7; // rax
  void *TokenHandle; // [rsp+30h] [rbp-D0h] BYREF
  _SECURITY_ATTRIBUTES MutexAttributes; // [rsp+38h] [rbp-C8h] BYREF
  DWORD ReturnLength; // [rsp+50h] [rbp-B0h] BYREF
  _OWORD SecurityDescriptor[2]; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v13; // [rsp+78h] [rbp-88h]
  _ACL Acl[2]; // [rsp+80h] [rbp-80h] BYREF
  __int128 v15; // [rsp+90h] [rbp-70h]
  __int128 v16; // [rsp+A0h] [rbp-60h]
  __int128 v17; // [rsp+B0h] [rbp-50h]
  __int128 v18; // [rsp+C0h] [rbp-40h]
  PSID TokenInformation[20]; // [rsp+D0h] [rbp-30h] BYREF

  v1 = *this;
  v2 = 0;
  *((_DWORD *)this + 4) = 1;
  CurrentProcess = GetCurrentProcess();
  ProcessId = GetProcessId(CurrentProcess);
  v6 = OpenProcess(0x400u, 0, ProcessId);
  if ( v6 )
  {
    TokenHandle = 0;
    v7 = GetCurrentProcess();
    if ( OpenProcessToken(v7, 8u, &TokenHandle) )
    {
      ReturnLength = 0;
      if ( GetTokenInformation(TokenHandle, TokenUser, TokenInformation, 0xA0u, &ReturnLength) )
      {
        v13 = 0;
        *(_OWORD *)&Acl[0].AclRevision = 0;
        v15 = 0;
        v16 = 0;
        v17 = 0;
        v18 = 0;
        memset(SecurityDescriptor, 0, sizeof(SecurityDescriptor));
        if ( !RtlCreateAcl(Acl, 0x50u, 2u)
          && !RtlAddAccessAllowedAce(Acl, 2u, 0x10000000u, TokenInformation[0])
          && !RtlCreateSecurityDescriptor(SecurityDescriptor, 1u)
          && !RtlSetDaclSecurityDescriptor(SecurityDescriptor, 1u, Acl, 0) )
        {
          *(_QWORD *)&MutexAttributes.nLength = 24;
          MutexAttributes.lpSecurityDescriptor = SecurityDescriptor;
          *(_QWORD *)&MutexAttributes.bInheritHandle = 0;
          v2 = (const WCHAR *)CreateMutexW(&MutexAttributes, 0, v1);
        }
      }
      CloseHandle(TokenHandle);
    }
    CloseHandle(v6);
  }
  this[1] = v2;
  if ( v2 )
    return 0;
  else
    return ResultFromKnownLastError();
}

```

## disassembly

```asm
0x18000ba80  push    rbp
0x18000ba82  push    rbx
0x18000ba83  push    rsi
0x18000ba84  push    rdi
0x18000ba85  push    r14
0x18000ba87  push    r15
0x18000ba89  lea     rbp, [rsp-88h]
0x18000ba91  sub     rsp, 188h
0x18000ba98  mov     rax, cs:__security_cookie
0x18000ba9f  xor     rax, rsp
0x18000baa2  mov     [rbp+0B0h+var_40], rax
0x18000baa6  mov     r14, [rcx]
0x18000baa9  xor     r15d, r15d
0x18000baac  mov     edi, r15d
0x18000baaf  mov     dword ptr [rcx+10h], 1
0x18000bab6  mov     rbx, rcx
0x18000bab9  call    cs:__imp_GetCurrentProcess
0x18000babf  mov     rcx, rax; Process
0x18000bac2  call    cs:__imp_GetProcessId
0x18000bac8  xor     edx, edx; bInheritHandle
0x18000baca  mov     ecx, 400h; dwDesiredAccess
0x18000bacf  mov     r8d, eax; dwProcessId
0x18000bad2  call    cs:__imp_OpenProcess
0x18000bad8  mov     rsi, rax
0x18000badb  test    rax, rax
0x18000bade  jz      loc_18000BC04
0x18000bae4  mov     [rsp+1B0h+TokenHandle], r15
0x18000bae9  call    cs:__imp_GetCurrentProcess
0x18000baef  lea     r8, [rsp+1B0h+TokenHandle]; TokenHandle
0x18000baf4  mov     edx, 8; DesiredAccess
0x18000baf9  mov     rcx, rax; ProcessHandle
0x18000bafc  call    cs:__imp_OpenProcessToken
0x18000bb02  test    eax, eax
0x18000bb04  jz      loc_18000BBFB
0x18000bb0a  mov     rcx, [rsp+1B0h+TokenHandle]; TokenHandle
0x18000bb0f  lea     rax, [rsp+1B0h+var_160]
0x18000bb14  mov     r9d, 0A0h; TokenInformationLength
0x18000bb1a  mov     [rsp+1B0h+ReturnLength], rax; ReturnLength
0x18000bb1f  lea     r8, [rbp+0B0h+TokenInformation]; TokenInformation
0x18000bb23  mov     [rsp+1B0h+var_160], r15d
0x18000bb28  mov     edx, 1; TokenInformationClass
0x18000bb2d  call    cs:__imp_GetTokenInformation
0x18000bb33  test    eax, eax
0x18000bb35  jz      loc_18000BBF0
0x18000bb3b  xorps   xmm0, xmm0
0x18000bb3e  lea     rcx, [rbp+0B0h+Acl]; Acl
0x18000bb42  xor     eax, eax
0x18000bb44  mov     edx, 50h ; 'P'; AclSize
0x18000bb49  mov     r8d, 2; AclRevision
0x18000bb4f  mov     [rsp+1B0h+var_138], rax
0x18000bb54  movups  xmmword ptr [rbp+0B0h+Acl.AclRevision], xmm0
0x18000bb58  movups  [rbp+0B0h+var_120], xmm0
0x18000bb5c  movups  [rbp+0B0h+var_110], xmm0
0x18000bb60  movups  [rbp+0B0h+var_100], xmm0
0x18000bb64  movups  [rbp+0B0h+var_F0], xmm0
0x18000bb68  movups  [rsp+1B0h+SecurityDescriptor], xmm0
0x18000bb6d  movups  [rsp+1B0h+var_148], xmm0
0x18000bb72  call    cs:__imp_RtlCreateAcl
0x18000bb78  test    eax, eax
0x18000bb7a  jnz     short loc_18000BBF0
0x18000bb7c  mov     r9, [rbp+0B0h+TokenInformation]; Sid
0x18000bb80  lea     rcx, [rbp+0B0h+Acl]; Acl
0x18000bb84  mov     edx, 2; Revision
0x18000bb89  mov     r8d, 10000000h; AccessMask
0x18000bb8f  call    cs:__imp_RtlAddAccessAllowedAce
0x18000bb95  test    eax, eax
0x18000bb97  jnz     short loc_18000BBF0
0x18000bb99  mov     edx, 1; Revision
0x18000bb9e  lea     rcx, [rsp+1B0h+SecurityDescriptor]; SecurityDescriptor
0x18000bba3  call    cs:__imp_RtlCreateSecurityDescriptor
0x18000bba9  test    eax, eax
0x18000bbab  jnz     short loc_18000BBF0
0x18000bbad  xor     r9d, r9d; DaclDefaulted
0x18000bbb0  lea     r8, [rbp+0B0h+Acl]; Dacl
0x18000bbb4  mov     dl, 1; DaclPresent
0x18000bbb6  lea     rcx, [rsp+1B0h+SecurityDescriptor]; SecurityDescriptor
0x18000bbbb  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x18000bbc1  test    eax, eax
0x18000bbc3  jnz     short loc_18000BBF0
0x18000bbc5  lea     rax, [rsp+1B0h+SecurityDescriptor]
0x18000bbca  mov     qword ptr [rsp+1B0h+MutexAttributes.nLength], 18h
0x18000bbd3  mov     r8, r14; lpName
0x18000bbd6  mov     [rsp+1B0h+MutexAttributes.lpSecurityDescriptor], rax
0x18000bbdb  xor     edx, edx; bInitialOwner
0x18000bbdd  mov     qword ptr [rsp+1B0h+MutexAttributes.bInheritHandle], r15
0x18000bbe2  lea     rcx, [rsp+1B0h+MutexAttributes]; lpMutexAttributes
0x18000bbe7  call    cs:__imp_CreateMutexW
0x18000bbed  mov     rdi, rax
0x18000bbf0  mov     rcx, [rsp+1B0h+TokenHandle]; hObject
0x18000bbf5  call    cs:__imp_CloseHandle
0x18000bbfb  mov     rcx, rsi; hObject
0x18000bbfe  call    cs:__imp_CloseHandle
0x18000bc04  mov     [rbx+8], rdi
0x18000bc08  test    rdi, rdi
0x18000bc0b  jz      short loc_18000BC2C
0x18000bc0d  mov     eax, r15d
0x18000bc10  mov     rcx, [rbp+0B0h+var_40]
0x18000bc14  xor     rcx, rsp; StackCookie
0x18000bc17  call    __security_check_cookie
0x18000bc1c  add     rsp, 188h
0x18000bc23  pop     r15
0x18000bc25  pop     r14
0x18000bc27  pop     rdi
0x18000bc28  pop     rsi
0x18000bc29  pop     rbx
0x18000bc2a  pop     rbp
0x18000bc2b  retn
0x18000bc2c  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18000bc31  jmp     short loc_18000BC10
```
