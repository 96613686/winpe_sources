# CGlobalRefCount::AnyReferences(void)

- ea: `0x18000bdf0`
- end: `0x18000bfd1`
- name: `?AnyReferences@CGlobalRefCount@@QEAAJXZ`
- size: `481`
- prototype: `__int64 __fastcall(CGlobalRefCount *__hidden this)`
- caller_count: `5`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000b33c`
- `0x18000b3f0`
- `0x18000cb84`
- `0x180020bd8`
- `0x180029500`

## callees

- `0x18000b3c0`
- `0x18000bdf0`
- `0x180035830`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000bf69`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000bf72`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000bf8e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000bf69`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000bf72`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000bf8e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bf7d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bf7d`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000be71`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000be71`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000be2a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000be5e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000be2a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000be5e`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18000be33`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18000be33`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x18000bf5b`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x18000bf5b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000bea1`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000bea1`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18000be43`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18000be43`
- `ntdll!RtlCreateAcl` at `0x18000bee6`
- `ntdll!RtlCreateAcl` at `0x18000bee6`
- `ntdll!RtlAddAccessAllowedAce` at `0x18000bf03`
- `ntdll!RtlAddAccessAllowedAce` at `0x18000bf03`
- `ntdll!RtlCreateSecurityDescriptor` at `0x18000bf17`
- `ntdll!RtlCreateSecurityDescriptor` at `0x18000bf17`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x18000bf2f`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x18000bf2f`

## pseudocode

```c
__int64 __fastcall CGlobalRefCount::AnyReferences(CGlobalRefCount *this)
{
  const WCHAR *v1; // r14
  HANDLE CurrentProcess; // rax
  DWORD ProcessId; // eax
  HANDLE v4; // rsi
  unsigned int v5; // ebx
  HANDLE v6; // rdi
  HANDLE v7; // rax
  void *TokenHandle; // [rsp+38h] [rbp-D0h] BYREF
  struct _SECURITY_ATTRIBUTES MutexAttributes; // [rsp+40h] [rbp-C8h] BYREF
  _BYTE ReturnLength[48]; // [rsp+58h] [rbp-B0h] BYREF
  struct _ACL Acl[2]; // [rsp+88h] [rbp-80h] BYREF
  __int128 v13; // [rsp+98h] [rbp-70h]
  __int128 v14; // [rsp+A8h] [rbp-60h]
  __int128 v15; // [rsp+B8h] [rbp-50h]
  __int128 v16; // [rsp+C8h] [rbp-40h]
  PSID TokenInformation[20]; // [rsp+D8h] [rbp-30h] BYREF

  if ( *((_DWORD *)this + 4) )
    return 0;
  v1 = *(const WCHAR **)this;
  CurrentProcess = GetCurrentProcess();
  ProcessId = GetProcessId(CurrentProcess);
  v4 = OpenProcess(0x400u, 0, ProcessId);
  if ( !v4 )
    return ResultFromKnownLastError();
  v5 = 0;
  v6 = 0;
  TokenHandle = 0;
  v7 = GetCurrentProcess();
  if ( OpenProcessToken(v7, 8u, &TokenHandle) )
  {
    *(_DWORD *)ReturnLength = 0;
    if ( GetTokenInformation(TokenHandle, TokenUser, TokenInformation, 0xA0u, (PDWORD)ReturnLength) )
    {
      *(_OWORD *)&Acl[0].AclRevision = 0;
      v13 = 0;
      v14 = 0;
      v15 = 0;
      v16 = 0;
      memset(&ReturnLength[8], 0, 40);
      if ( !RtlCreateAcl(Acl, 0x50u, 2u)
        && !RtlAddAccessAllowedAce(Acl, 2u, 0x10000000u, TokenInformation[0])
        && !RtlCreateSecurityDescriptor(&ReturnLength[8], 1u)
        && !RtlSetDaclSecurityDescriptor(&ReturnLength[8], 1u, Acl, 0) )
      {
        *(_QWORD *)&MutexAttributes.nLength = 24;
        MutexAttributes.lpSecurityDescriptor = &ReturnLength[8];
        *(_QWORD *)&MutexAttributes.bInheritHandle = 0;
        v6 = CreateMutexW(&MutexAttributes, 0, v1);
      }
    }
    CloseHandle(TokenHandle);
  }
  CloseHandle(v4);
  if ( !v6 )
    return ResultFromKnownLastError();
  LOBYTE(v5) = GetLastError() != 183;
  CloseHandle(v6);
  return v5;
}

```

## disassembly

```asm
0x18000bdf0  mov     r11, rsp
0x18000bdf3  push    rbp
0x18000bdf4  push    rbx
0x18000bdf5  lea     rbp, [r11-98h]
0x18000bdfc  sub     rsp, 188h
0x18000be03  mov     rax, cs:__security_cookie
0x18000be0a  xor     rax, rsp
0x18000be0d  mov     [rbp+90h+var_20], rax
0x18000be11  cmp     dword ptr [rcx+10h], 0
0x18000be15  jnz     loc_18000BFCB
0x18000be1b  mov     [r11+10h], rsi
0x18000be1f  mov     [r11+18h], rdi
0x18000be23  mov     [r11-18h], r14
0x18000be27  mov     r14, [rcx]
0x18000be2a  call    cs:__imp_GetCurrentProcess
0x18000be30  mov     rcx, rax; Process
0x18000be33  call    cs:__imp_GetProcessId
0x18000be39  xor     edx, edx; bInheritHandle
0x18000be3b  mov     ecx, 400h; dwDesiredAccess
0x18000be40  mov     r8d, eax; dwProcessId
0x18000be43  call    cs:__imp_OpenProcess
0x18000be49  mov     rsi, rax
0x18000be4c  test    rax, rax
0x18000be4f  jz      loc_18000BFC4
0x18000be55  xor     ebx, ebx
0x18000be57  mov     edi, ebx
0x18000be59  mov     [rsp+190h+TokenHandle], rbx
0x18000be5e  call    cs:__imp_GetCurrentProcess
0x18000be64  lea     r8, [rsp+190h+TokenHandle]; TokenHandle
0x18000be69  mov     edx, 8; DesiredAccess
0x18000be6e  mov     rcx, rax; ProcessHandle
0x18000be71  call    cs:__imp_OpenProcessToken
0x18000be77  test    eax, eax
0x18000be79  jz      loc_18000BF6F
0x18000be7f  mov     rcx, [rsp+190h+TokenHandle]; TokenHandle
0x18000be84  lea     rax, [rsp+190h+ReturnLength]
0x18000be89  mov     r9d, 0A0h; TokenInformationLength
0x18000be8f  mov     [rsp+20h], rax; ReturnLength
0x18000be94  lea     r8, [rbp+90h+TokenInformation]; TokenInformation
0x18000be98  mov     [rsp+190h+ReturnLength], ebx
0x18000be9c  mov     edx, 1; TokenInformationClass
0x18000bea1  call    cs:__imp_GetTokenInformation
0x18000bea7  test    eax, eax
0x18000bea9  jz      loc_18000BF64
0x18000beaf  xorps   xmm0, xmm0
0x18000beb2  lea     rcx, [rbp+90h+Acl]; Acl
0x18000beb6  xor     eax, eax
0x18000beb8  mov     edx, 50h ; 'P'; AclSize
0x18000bebd  mov     r8d, 2; AclRevision
0x18000bec3  mov     [rsp+190h+var_118], rax
0x18000bec8  movups  xmmword ptr [rbp+90h+Acl.AclRevision], xmm0
0x18000becc  movups  [rbp+90h+var_100], xmm0
0x18000bed0  movups  [rbp+90h+var_F0], xmm0
0x18000bed4  movups  [rbp+90h+var_E0], xmm0
0x18000bed8  movups  [rbp+90h+var_D0], xmm0
0x18000bedc  movups  xmmword ptr [rsp+190h+ReturnLength+8], xmm0
0x18000bee1  movups  [rsp+190h+var_130+8], xmm0
0x18000bee6  call    cs:__imp_RtlCreateAcl
0x18000beec  test    eax, eax
0x18000beee  jnz     short loc_18000BF64
0x18000bef0  mov     r9, [rbp+90h+TokenInformation]; Sid
0x18000bef4  lea     rcx, [rbp+90h+Acl]; Acl
0x18000bef8  mov     edx, 2; Revision
0x18000befd  mov     r8d, 10000000h; AccessMask
0x18000bf03  call    cs:__imp_RtlAddAccessAllowedAce
0x18000bf09  test    eax, eax
0x18000bf0b  jnz     short loc_18000BF64
0x18000bf0d  mov     edx, 1; Revision
0x18000bf12  lea     rcx, [rsp+190h+ReturnLength+8]; SecurityDescriptor
0x18000bf17  call    cs:__imp_RtlCreateSecurityDescriptor
0x18000bf1d  test    eax, eax
0x18000bf1f  jnz     short loc_18000BF64
0x18000bf21  xor     r9d, r9d; DaclDefaulted
0x18000bf24  lea     r8, [rbp+90h+Acl]; Dacl
0x18000bf28  mov     dl, 1; DaclPresent
0x18000bf2a  lea     rcx, [rsp+190h+ReturnLength+8]; SecurityDescriptor
0x18000bf2f  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x18000bf35  test    eax, eax
0x18000bf37  jnz     short loc_18000BF64
0x18000bf39  lea     rax, [rsp+190h+ReturnLength+8]
0x18000bf3e  mov     qword ptr [rsp+190h+MutexAttributes.nLength], 18h
0x18000bf47  mov     r8, r14; lpName
0x18000bf4a  mov     [rsp+190h+MutexAttributes.lpSecurityDescriptor], rax
0x18000bf4f  xor     edx, edx; bInitialOwner
0x18000bf51  mov     qword ptr [rsp+190h+MutexAttributes.bInheritHandle], rbx
0x18000bf56  lea     rcx, [rsp+190h+MutexAttributes]; lpMutexAttributes
0x18000bf5b  call    cs:__imp_CreateMutexW
0x18000bf61  mov     rdi, rax
0x18000bf64  mov     rcx, [rsp+190h+TokenHandle]; hObject
0x18000bf69  call    cs:__imp_CloseHandle
0x18000bf6f  mov     rcx, rsi; hObject
0x18000bf72  call    cs:__imp_CloseHandle
0x18000bf78  test    rdi, rdi
0x18000bf7b  jz      short loc_18000BFC4
0x18000bf7d  call    cs:__imp_GetLastError
0x18000bf83  cmp     eax, 0B7h
0x18000bf88  mov     rcx, rdi; hObject
0x18000bf8b  setnz   bl
0x18000bf8e  call    cs:__imp_CloseHandle
0x18000bf94  mov     eax, ebx
0x18000bf96  mov     rdi, [rsp+190h+arg_10]
0x18000bf9e  mov     rsi, [rsp+190h+arg_8]
0x18000bfa6  mov     r14, [rsp+180h]
0x18000bfae  mov     rcx, [rbp+90h+var_20]
0x18000bfb2  xor     rcx, rsp; StackCookie
0x18000bfb5  call    __security_check_cookie
0x18000bfba  add     rsp, 188h
0x18000bfc1  pop     rbx
0x18000bfc2  pop     rbp
0x18000bfc3  retn
0x18000bfc4  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18000bfc9  jmp     short loc_18000BF96
0x18000bfcb  xor     ebx, ebx
0x18000bfcd  mov     eax, ebx
0x18000bfcf  jmp     short loc_18000BFAE
```
