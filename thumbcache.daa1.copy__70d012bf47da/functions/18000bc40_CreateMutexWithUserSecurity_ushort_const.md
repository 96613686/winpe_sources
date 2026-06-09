# CreateMutexWithUserSecurity(ushort const *)

- ea: `0x18000bc40`
- end: `0x18000bde3`
- name: `?CreateMutexWithUserSecurity@@YAPEAXPEBG@Z`
- size: `419`
- prototype: `void *__fastcall(LPCWSTR lpName)`
- caller_count: `4`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180009c70`
- `0x18000b9b0`
- `0x180015d40`
- `0x1800211c0`

## callees

- `0x18000bc40`
- `0x180035830`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000bdad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000bdb6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000bdad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000bdb6`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000bcb4`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000bcb4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000bc71`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000bca1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000bc71`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000bca1`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18000bc7a`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18000bc7a`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x18000bd9f`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x18000bd9f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000bce5`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000bce5`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18000bc8a`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18000bc8a`
- `ntdll!RtlCreateAcl` at `0x18000bd2a`
- `ntdll!RtlCreateAcl` at `0x18000bd2a`
- `ntdll!RtlAddAccessAllowedAce` at `0x18000bd47`
- `ntdll!RtlAddAccessAllowedAce` at `0x18000bd47`
- `ntdll!RtlCreateSecurityDescriptor` at `0x18000bd5b`
- `ntdll!RtlCreateSecurityDescriptor` at `0x18000bd5b`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x18000bd73`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x18000bd73`

## pseudocode

```c
HANDLE __fastcall CreateMutexWithUserSecurity(LPCWSTR lpName)
{
  HANDLE v2; // rdi
  HANDLE CurrentProcess; // rax
  DWORD ProcessId; // eax
  HANDLE v5; // rbx
  HANDLE v6; // rax
  void *TokenHandle; // [rsp+30h] [rbp-D0h] BYREF
  struct _SECURITY_ATTRIBUTES MutexAttributes; // [rsp+38h] [rbp-C8h] BYREF
  DWORD ReturnLength; // [rsp+50h] [rbp-B0h] BYREF
  _OWORD SecurityDescriptor[2]; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v12; // [rsp+78h] [rbp-88h]
  struct _ACL Acl[2]; // [rsp+80h] [rbp-80h] BYREF
  __int128 v14; // [rsp+90h] [rbp-70h]
  __int128 v15; // [rsp+A0h] [rbp-60h]
  __int128 v16; // [rsp+B0h] [rbp-50h]
  __int128 v17; // [rsp+C0h] [rbp-40h]
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
        v12 = 0;
        *(_OWORD *)&Acl[0].AclRevision = 0;
        v14 = 0;
        v15 = 0;
        v16 = 0;
        v17 = 0;
        memset(SecurityDescriptor, 0, sizeof(SecurityDescriptor));
        if ( !RtlCreateAcl(Acl, 0x50u, 2u)
          && !RtlAddAccessAllowedAce(Acl, 2u, 0x10000000u, TokenInformation[0])
          && !RtlCreateSecurityDescriptor(SecurityDescriptor, 1u)
          && !RtlSetDaclSecurityDescriptor(SecurityDescriptor, 1u, Acl, 0) )
        {
          *(_QWORD *)&MutexAttributes.nLength = 24;
          MutexAttributes.lpSecurityDescriptor = SecurityDescriptor;
          *(_QWORD *)&MutexAttributes.bInheritHandle = 0;
          v2 = CreateMutexW(&MutexAttributes, 0, lpName);
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
0x18000bc40  mov     [rsp-8+arg_8], rbx
0x18000bc45  mov     [rsp-8+arg_10], rsi
0x18000bc4a  push    rbp
0x18000bc4b  push    rdi
0x18000bc4c  push    r14
0x18000bc4e  lea     rbp, [rsp-80h]
0x18000bc53  sub     rsp, 180h
0x18000bc5a  mov     rax, cs:__security_cookie
0x18000bc61  xor     rax, rsp
0x18000bc64  mov     [rbp+90h+var_20], rax
0x18000bc68  xor     r14d, r14d
0x18000bc6b  mov     rsi, rcx
0x18000bc6e  mov     edi, r14d
0x18000bc71  call    cs:__imp_GetCurrentProcess
0x18000bc77  mov     rcx, rax; Process
0x18000bc7a  call    cs:__imp_GetProcessId
0x18000bc80  xor     edx, edx; bInheritHandle
0x18000bc82  mov     ecx, 400h; dwDesiredAccess
0x18000bc87  mov     r8d, eax; dwProcessId
0x18000bc8a  call    cs:__imp_OpenProcess
0x18000bc90  mov     rbx, rax
0x18000bc93  test    rax, rax
0x18000bc96  jz      loc_18000BDBC
0x18000bc9c  mov     [rsp+190h+TokenHandle], r14
0x18000bca1  call    cs:__imp_GetCurrentProcess
0x18000bca7  lea     r8, [rsp+190h+TokenHandle]; TokenHandle
0x18000bcac  mov     edx, 8; DesiredAccess
0x18000bcb1  mov     rcx, rax; ProcessHandle
0x18000bcb4  call    cs:__imp_OpenProcessToken
0x18000bcba  test    eax, eax
0x18000bcbc  jz      loc_18000BDB3
0x18000bcc2  mov     rcx, [rsp+190h+TokenHandle]; TokenHandle
0x18000bcc7  lea     rax, [rsp+190h+var_140]
0x18000bccc  mov     r9d, 0A0h; TokenInformationLength
0x18000bcd2  mov     [rsp+190h+ReturnLength], rax; ReturnLength
0x18000bcd7  lea     r8, [rbp+90h+TokenInformation]; TokenInformation
0x18000bcdb  mov     [rsp+190h+var_140], r14d
0x18000bce0  mov     edx, 1; TokenInformationClass
0x18000bce5  call    cs:__imp_GetTokenInformation
0x18000bceb  test    eax, eax
0x18000bced  jz      loc_18000BDA8
0x18000bcf3  xorps   xmm0, xmm0
0x18000bcf6  lea     rcx, [rbp+90h+Acl]; Acl
0x18000bcfa  xor     eax, eax
0x18000bcfc  mov     edx, 50h ; 'P'; AclSize
0x18000bd01  mov     r8d, 2; AclRevision
0x18000bd07  mov     [rsp+190h+var_118], rax
0x18000bd0c  movups  xmmword ptr [rbp+90h+Acl.AclRevision], xmm0
0x18000bd10  movups  [rbp+90h+var_100], xmm0
0x18000bd14  movups  [rbp+90h+var_F0], xmm0
0x18000bd18  movups  [rbp+90h+var_E0], xmm0
0x18000bd1c  movups  [rbp+90h+var_D0], xmm0
0x18000bd20  movups  [rsp+190h+SecurityDescriptor], xmm0
0x18000bd25  movups  [rsp+190h+var_128], xmm0
0x18000bd2a  call    cs:__imp_RtlCreateAcl
0x18000bd30  test    eax, eax
0x18000bd32  jnz     short loc_18000BDA8
0x18000bd34  mov     r9, [rbp+90h+TokenInformation]; Sid
0x18000bd38  lea     rcx, [rbp+90h+Acl]; Acl
0x18000bd3c  mov     edx, 2; Revision
0x18000bd41  mov     r8d, 10000000h; AccessMask
0x18000bd47  call    cs:__imp_RtlAddAccessAllowedAce
0x18000bd4d  test    eax, eax
0x18000bd4f  jnz     short loc_18000BDA8
0x18000bd51  mov     edx, 1; Revision
0x18000bd56  lea     rcx, [rsp+190h+SecurityDescriptor]; SecurityDescriptor
0x18000bd5b  call    cs:__imp_RtlCreateSecurityDescriptor
0x18000bd61  test    eax, eax
0x18000bd63  jnz     short loc_18000BDA8
0x18000bd65  xor     r9d, r9d; DaclDefaulted
0x18000bd68  lea     r8, [rbp+90h+Acl]; Dacl
0x18000bd6c  mov     dl, 1; DaclPresent
0x18000bd6e  lea     rcx, [rsp+190h+SecurityDescriptor]; SecurityDescriptor
0x18000bd73  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x18000bd79  test    eax, eax
0x18000bd7b  jnz     short loc_18000BDA8
0x18000bd7d  lea     rax, [rsp+190h+SecurityDescriptor]
0x18000bd82  mov     qword ptr [rsp+190h+MutexAttributes.nLength], 18h
0x18000bd8b  mov     r8, rsi; lpName
0x18000bd8e  mov     [rsp+190h+MutexAttributes.lpSecurityDescriptor], rax
0x18000bd93  xor     edx, edx; bInitialOwner
0x18000bd95  mov     qword ptr [rsp+190h+MutexAttributes.bInheritHandle], r14
0x18000bd9a  lea     rcx, [rsp+190h+MutexAttributes]; lpMutexAttributes
0x18000bd9f  call    cs:__imp_CreateMutexW
0x18000bda5  mov     rdi, rax
0x18000bda8  mov     rcx, [rsp+190h+TokenHandle]; hObject
0x18000bdad  call    cs:__imp_CloseHandle
0x18000bdb3  mov     rcx, rbx; hObject
0x18000bdb6  call    cs:__imp_CloseHandle
0x18000bdbc  mov     rax, rdi
0x18000bdbf  mov     rcx, [rbp+90h+var_20]
0x18000bdc3  xor     rcx, rsp; StackCookie
0x18000bdc6  call    __security_check_cookie
0x18000bdcb  lea     r11, [rsp+190h+var_10]
0x18000bdd3  mov     rbx, [r11+28h]
0x18000bdd7  mov     rsi, [r11+30h]
0x18000bddb  mov     rsp, r11
0x18000bdde  pop     r14
0x18000bde0  pop     rdi
0x18000bde1  pop     rbp
0x18000bde2  retn
```
