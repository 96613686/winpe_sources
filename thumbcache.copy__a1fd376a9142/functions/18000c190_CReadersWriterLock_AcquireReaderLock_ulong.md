# CReadersWriterLock::AcquireReaderLock(ulong)

- ea: `0x18000c190`
- end: `0x18000c3c2`
- name: `?AcquireReaderLock@CReadersWriterLock@@QEAAJK@Z`
- size: `562`
- prototype: `__int64 __fastcall(CReadersWriterLock *__hidden this, unsigned int)`
- caller_count: `9`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000af30`
- `0x18000b5c0`
- `0x18000cac0`
- `0x1800108b4`
- `0x180010ba0`
- `0x180010e00`
- `0x180025a00`
- `0x18002a88c`
- `0x1800435b4`

## callees

- `0x18000b3c0`
- `0x18000c190`
- `0x180035830`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c33e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c347`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c33e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c347`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000c245`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000c245`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000c202`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000c232`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000c202`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000c232`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18000c20b`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18000c20b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000c1b7`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000c1b7`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000c371`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000c371`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x18000c330`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x18000c330`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000c276`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000c276`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18000c21b`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18000c21b`
- `ntdll!RtlCreateAcl` at `0x18000c2bb`
- `ntdll!RtlCreateAcl` at `0x18000c2bb`
- `ntdll!RtlAddAccessAllowedAce` at `0x18000c2d8`
- `ntdll!RtlAddAccessAllowedAce` at `0x18000c2d8`
- `ntdll!RtlCreateSecurityDescriptor` at `0x18000c2ec`
- `ntdll!RtlCreateSecurityDescriptor` at `0x18000c2ec`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x18000c304`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x18000c304`

## pseudocode

```c
__int64 __fastcall CReadersWriterLock::AcquireReaderLock(CReadersWriterLock *this, DWORD a2)
{
  DWORD v3; // eax
  const WCHAR *v4; // r14
  HANDLE v5; // rdi
  HANDLE CurrentProcess; // rax
  DWORD ProcessId; // eax
  HANDLE v8; // rsi
  HANDLE v9; // rax
  int Error; // edi
  __int64 result; // rax
  void *TokenHandle; // [rsp+30h] [rbp-D0h] BYREF
  struct _SECURITY_ATTRIBUTES MutexAttributes; // [rsp+38h] [rbp-C8h] BYREF
  DWORD ReturnLength; // [rsp+50h] [rbp-B0h] BYREF
  _OWORD SecurityDescriptor[2]; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v16; // [rsp+78h] [rbp-88h]
  struct _ACL Acl[2]; // [rsp+80h] [rbp-80h] BYREF
  __int128 v18; // [rsp+90h] [rbp-70h]
  __int128 v19; // [rsp+A0h] [rbp-60h]
  __int128 v20; // [rsp+B0h] [rbp-50h]
  __int128 v21; // [rsp+C0h] [rbp-40h]
  PSID TokenInformation[20]; // [rsp+D0h] [rbp-30h] BYREF

  v3 = WaitForSingleObject(*((HANDLE *)this + 1), a2);
  if ( v3 == 258 )
    return 2147942658LL;
  if ( v3 != -1 || (result = ResultFromKnownLastError(), (int)result >= 0) )
  {
    v4 = (const WCHAR *)*((_QWORD *)this + 3);
    v5 = 0;
    *((_DWORD *)this + 10) = 1;
    CurrentProcess = GetCurrentProcess();
    ProcessId = GetProcessId(CurrentProcess);
    v8 = OpenProcess(0x400u, 0, ProcessId);
    if ( v8 )
    {
      TokenHandle = 0;
      v9 = GetCurrentProcess();
      if ( OpenProcessToken(v9, 8u, &TokenHandle) )
      {
        ReturnLength = 0;
        if ( GetTokenInformation(TokenHandle, TokenUser, TokenInformation, 0xA0u, &ReturnLength) )
        {
          v16 = 0;
          *(_OWORD *)&Acl[0].AclRevision = 0;
          v18 = 0;
          v19 = 0;
          v20 = 0;
          v21 = 0;
          memset(SecurityDescriptor, 0, sizeof(SecurityDescriptor));
          if ( !RtlCreateAcl(Acl, 0x50u, 2u)
            && !RtlAddAccessAllowedAce(Acl, 2u, 0x10000000u, TokenInformation[0])
            && !RtlCreateSecurityDescriptor(SecurityDescriptor, 1u)
            && !RtlSetDaclSecurityDescriptor(SecurityDescriptor, 1u, Acl, 0) )
          {
            *(_QWORD *)&MutexAttributes.nLength = 24;
            MutexAttributes.lpSecurityDescriptor = SecurityDescriptor;
            *(_QWORD *)&MutexAttributes.bInheritHandle = 0;
            v5 = CreateMutexW(&MutexAttributes, 0, v4);
          }
        }
        CloseHandle(TokenHandle);
      }
      CloseHandle(v8);
    }
    *((_QWORD *)this + 4) = v5;
    if ( v5 )
    {
      Error = 0;
    }
    else
    {
      Error = ResultFromKnownLastError();
      if ( Error < 0 )
        goto LABEL_16;
    }
    _InterlockedIncrement((volatile signed __int32 *)this + 13);
LABEL_16:
    ReleaseMutex(*((HANDLE *)this + 1));
    return (unsigned int)Error;
  }
  return result;
}

```

## disassembly

```asm
0x18000c190  push    rbp
0x18000c192  push    rbx
0x18000c193  lea     rbp, [rsp-98h]
0x18000c19b  sub     rsp, 198h
0x18000c1a2  mov     rax, cs:__security_cookie
0x18000c1a9  xor     rax, rsp
0x18000c1ac  mov     [rbp+0A0h+var_30], rax
0x18000c1b0  mov     rbx, rcx
0x18000c1b3  mov     rcx, [rcx+8]; hHandle
0x18000c1b7  call    cs:__imp_WaitForSingleObject
0x18000c1bd  cmp     eax, 102h
0x18000c1c2  jz      loc_18000C3AE
0x18000c1c8  cmp     eax, 0FFFFFFFFh
0x18000c1cb  jz      loc_18000C39F
0x18000c1d1  mov     [rsp+1A0h+arg_10], rsi
0x18000c1d9  mov     [rsp+1A0h+var_10], rdi
0x18000c1e1  mov     [rsp+1A0h+var_18], r14
0x18000c1e9  mov     r14, [rbx+18h]
0x18000c1ed  mov     [rsp+1A0h+var_20], r15
0x18000c1f5  xor     r15d, r15d
0x18000c1f8  mov     edi, r15d
0x18000c1fb  mov     dword ptr [rbx+28h], 1
0x18000c202  call    cs:__imp_GetCurrentProcess
0x18000c208  mov     rcx, rax; Process
0x18000c20b  call    cs:__imp_GetProcessId
0x18000c211  xor     edx, edx; bInheritHandle
0x18000c213  mov     ecx, 400h; dwDesiredAccess
0x18000c218  mov     r8d, eax; dwProcessId
0x18000c21b  call    cs:__imp_OpenProcess
0x18000c221  mov     rsi, rax
0x18000c224  test    rax, rax
0x18000c227  jz      loc_18000C34D
0x18000c22d  mov     [rsp+1A0h+TokenHandle], r15
0x18000c232  call    cs:__imp_GetCurrentProcess
0x18000c238  lea     r8, [rsp+1A0h+TokenHandle]; TokenHandle
0x18000c23d  mov     edx, 8; DesiredAccess
0x18000c242  mov     rcx, rax; ProcessHandle
0x18000c245  call    cs:__imp_OpenProcessToken
0x18000c24b  test    eax, eax
0x18000c24d  jz      loc_18000C344
0x18000c253  mov     rcx, [rsp+1A0h+TokenHandle]; TokenHandle
0x18000c258  lea     rax, [rsp+1A0h+var_150]
0x18000c25d  mov     r9d, 0A0h; TokenInformationLength
0x18000c263  mov     [rsp+1A0h+ReturnLength], rax; ReturnLength
0x18000c268  lea     r8, [rbp+0A0h+TokenInformation]; TokenInformation
0x18000c26c  mov     [rsp+1A0h+var_150], r15d
0x18000c271  mov     edx, 1; TokenInformationClass
0x18000c276  call    cs:__imp_GetTokenInformation
0x18000c27c  test    eax, eax
0x18000c27e  jz      loc_18000C339
0x18000c284  xorps   xmm0, xmm0
0x18000c287  lea     rcx, [rbp+0A0h+Acl]; Acl
0x18000c28b  xor     eax, eax
0x18000c28d  mov     edx, 50h ; 'P'; AclSize
0x18000c292  mov     r8d, 2; AclRevision
0x18000c298  mov     [rsp+1A0h+var_128], rax
0x18000c29d  movups  xmmword ptr [rbp+0A0h+Acl.AclRevision], xmm0
0x18000c2a1  movups  [rbp+0A0h+var_110], xmm0
0x18000c2a5  movups  [rbp+0A0h+var_100], xmm0
0x18000c2a9  movups  [rbp+0A0h+var_F0], xmm0
0x18000c2ad  movups  [rbp+0A0h+var_E0], xmm0
0x18000c2b1  movups  [rsp+1A0h+SecurityDescriptor], xmm0
0x18000c2b6  movups  [rsp+1A0h+var_138], xmm0
0x18000c2bb  call    cs:__imp_RtlCreateAcl
0x18000c2c1  test    eax, eax
0x18000c2c3  jnz     short loc_18000C339
0x18000c2c5  mov     r9, [rbp+0A0h+TokenInformation]; Sid
0x18000c2c9  lea     rcx, [rbp+0A0h+Acl]; Acl
0x18000c2cd  mov     edx, 2; Revision
0x18000c2d2  mov     r8d, 10000000h; AccessMask
0x18000c2d8  call    cs:__imp_RtlAddAccessAllowedAce
0x18000c2de  test    eax, eax
0x18000c2e0  jnz     short loc_18000C339
0x18000c2e2  mov     edx, 1; Revision
0x18000c2e7  lea     rcx, [rsp+1A0h+SecurityDescriptor]; SecurityDescriptor
0x18000c2ec  call    cs:__imp_RtlCreateSecurityDescriptor
0x18000c2f2  test    eax, eax
0x18000c2f4  jnz     short loc_18000C339
0x18000c2f6  xor     r9d, r9d; DaclDefaulted
0x18000c2f9  lea     r8, [rbp+0A0h+Acl]; Dacl
0x18000c2fd  mov     dl, 1; DaclPresent
0x18000c2ff  lea     rcx, [rsp+1A0h+SecurityDescriptor]; SecurityDescriptor
0x18000c304  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x18000c30a  test    eax, eax
0x18000c30c  jnz     short loc_18000C339
0x18000c30e  lea     rax, [rsp+1A0h+SecurityDescriptor]
0x18000c313  mov     qword ptr [rsp+1A0h+MutexAttributes.nLength], 18h
0x18000c31c  mov     r8, r14; lpName
0x18000c31f  mov     [rsp+1A0h+MutexAttributes.lpSecurityDescriptor], rax
0x18000c324  xor     edx, edx; bInitialOwner
0x18000c326  mov     qword ptr [rsp+1A0h+MutexAttributes.bInheritHandle], r15
0x18000c32b  lea     rcx, [rsp+1A0h+MutexAttributes]; lpMutexAttributes
0x18000c330  call    cs:__imp_CreateMutexW
0x18000c336  mov     rdi, rax
0x18000c339  mov     rcx, [rsp+1A0h+TokenHandle]; hObject
0x18000c33e  call    cs:__imp_CloseHandle
0x18000c344  mov     rcx, rsi; hObject
0x18000c347  call    cs:__imp_CloseHandle
0x18000c34d  mov     r14, [rsp+1A0h+var_18]
0x18000c355  mov     rsi, [rsp+1A0h+arg_10]
0x18000c35d  mov     [rbx+20h], rdi
0x18000c361  test    rdi, rdi
0x18000c364  jz      short loc_18000C3B5
0x18000c366  mov     edi, r15d
0x18000c369  lock inc dword ptr [rbx+34h]
0x18000c36d  mov     rcx, [rbx+8]; hMutex
0x18000c371  call    cs:__imp_ReleaseMutex
0x18000c377  mov     r15, [rsp+1A0h+var_20]
0x18000c37f  mov     eax, edi
0x18000c381  mov     rdi, [rsp+1A0h+var_10]
0x18000c389  mov     rcx, [rbp+0A0h+var_30]
0x18000c38d  xor     rcx, rsp; StackCookie
0x18000c390  call    __security_check_cookie
0x18000c395  add     rsp, 198h
0x18000c39c  pop     rbx
0x18000c39d  pop     rbp
0x18000c39e  retn
0x18000c39f  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18000c3a4  test    eax, eax
0x18000c3a6  jns     loc_18000C1D1
0x18000c3ac  jmp     short loc_18000C389
0x18000c3ae  mov     eax, 80070102h
0x18000c3b3  jmp     short loc_18000C389
0x18000c3b5  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18000c3ba  mov     edi, eax
0x18000c3bc  test    eax, eax
0x18000c3be  js      short loc_18000C36D
0x18000c3c0  jmp     short loc_18000C369
```
