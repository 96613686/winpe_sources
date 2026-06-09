# EnablePrivilege

- ea: `0x18003f2b0`
- end: `0x18003f3b8`
- name: `EnablePrivilege`
- size: `264`
- prototype: `__int64 __fastcall(__int64, DWORD, DWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x18003f958`

## callees

- `0x180001600`
- `0x18003f2b0`

## import_xrefs

- `KERNEL32!GetCurrentProcess` at `0x18003f2f4`
- `KERNEL32!GetCurrentProcess` at `0x18003f2f4`
- `KERNEL32!CloseHandle` at `0x18003f332`
- `KERNEL32!CloseHandle` at `0x18003f383`
- `KERNEL32!CloseHandle` at `0x18003f332`
- `KERNEL32!CloseHandle` at `0x18003f383`
- `ADVAPI32!OpenProcessToken` at `0x18003f306`
- `ADVAPI32!OpenProcessToken` at `0x18003f306`
- `ADVAPI32!AdjustTokenPrivileges` at `0x18003f377`
- `ADVAPI32!AdjustTokenPrivileges` at `0x18003f377`
- `ADVAPI32!LookupPrivilegeValueW` at `0x18003f324`
- `ADVAPI32!LookupPrivilegeValueW` at `0x18003f324`

## string_xrefs

- `0x18003f31d`: `SeBackupPrivilege`

## pseudocode

```c
__int64 __fastcall EnablePrivilege(__int64 a1, DWORD a2, DWORD *a3)
{
  HANDLE CurrentProcess; // rax
  unsigned int v7; // edi
  HANDLE TokenHandle; // [rsp+30h] [rbp-48h] BYREF
  DWORD ReturnLength; // [rsp+38h] [rbp-40h] BYREF
  struct _LUID Luid; // [rsp+40h] [rbp-38h] BYREF
  struct _TOKEN_PRIVILEGES NewState; // [rsp+48h] [rbp-30h] BYREF
  struct _TOKEN_PRIVILEGES PreviousState; // [rsp+58h] [rbp-20h] BYREF

  TokenHandle = 0;
  Luid = 0;
  NewState = 0;
  PreviousState = 0;
  ReturnLength = 0;
  CurrentProcess = GetCurrentProcess();
  if ( !OpenProcessToken(CurrentProcess, 0x28u, &TokenHandle) )
    return 0;
  if ( !LookupPrivilegeValueW(0, L"SeBackupPrivilege", &Luid) )
  {
    CloseHandle(TokenHandle);
    return 0;
  }
  NewState.Privileges[0].Luid = Luid;
  NewState.PrivilegeCount = 1;
  NewState.Privileges[0].Attributes = a2 != 0 ? 2 : 0;
  v7 = AdjustTokenPrivileges(TokenHandle, 0, &NewState, 0x10u, &PreviousState, &ReturnLength);
  CloseHandle(TokenHandle);
  if ( v7 )
  {
    if ( PreviousState.PrivilegeCount )
      *a3 = (PreviousState.Privileges[0].Attributes >> 1) & 1;
    else
      *a3 = a2;
  }
  return v7;
}

```

## disassembly

```asm
0x18003f2b0  push    rbp
0x18003f2b2  push    rbx
0x18003f2b3  push    rsi
0x18003f2b4  push    rdi
0x18003f2b5  mov     rbp, rsp
0x18003f2b8  sub     rsp, 78h
0x18003f2bc  mov     rax, cs:__security_cookie
0x18003f2c3  xor     rax, rsp
0x18003f2c6  mov     [rbp+var_10], rax
0x18003f2ca  xorps   xmm0, xmm0
0x18003f2cd  mov     [rbp+TokenHandle], 0
0x18003f2d5  xorps   xmm1, xmm1
0x18003f2d8  mov     qword ptr [rbp+Luid.LowPart], 0
0x18003f2e0  movups  xmmword ptr [rbp+NewState.PrivilegeCount], xmm0
0x18003f2e4  mov     rbx, r8
0x18003f2e7  mov     esi, edx
0x18003f2e9  movups  xmmword ptr [rbp+var_20.PrivilegeCount], xmm1
0x18003f2ed  mov     [rbp+var_40], 0
0x18003f2f4  call    cs:__imp_GetCurrentProcess
0x18003f2fa  lea     r8, [rbp+TokenHandle]; TokenHandle
0x18003f2fe  mov     edx, 28h ; '('; DesiredAccess
0x18003f303  mov     rcx, rax; ProcessHandle
0x18003f306  call    cs:__imp_OpenProcessToken
0x18003f30c  test    eax, eax
0x18003f30e  jnz     short loc_18003F317
0x18003f310  xor     eax, eax
0x18003f312  jmp     loc_18003F3A3
0x18003f317  lea     r8, [rbp+Luid]; lpLuid
0x18003f31b  xor     ecx, ecx; lpSystemName
0x18003f31d  lea     rdx, aSebackupprivil; "SeBackupPrivilege"
0x18003f324  call    cs:__imp_LookupPrivilegeValueW
0x18003f32a  test    eax, eax
0x18003f32c  jnz     short loc_18003F33A
0x18003f32e  mov     rcx, [rbp+TokenHandle]; hObject
0x18003f332  call    cs:__imp_CloseHandle
0x18003f338  jmp     short loc_18003F310
0x18003f33a  mov     rax, qword ptr [rbp+Luid.LowPart]
0x18003f33e  lea     r8, [rbp+NewState]; NewState
0x18003f342  mov     qword ptr [rbp+NewState.Privileges.Luid.LowPart], rax
0x18003f346  mov     r9d, 10h; BufferLength
0x18003f34c  mov     eax, esi
0x18003f34e  mov     [rbp+NewState.PrivilegeCount], 1
0x18003f355  neg     eax
0x18003f357  lea     rax, [rbp+var_40]
0x18003f35b  sbb     ecx, ecx
0x18003f35d  mov     [rsp+78h+ReturnLength], rax; ReturnLength
0x18003f362  and     ecx, 2
0x18003f365  lea     rax, [rbp+var_20]
0x18003f369  mov     [rbp+NewState.Privileges.Attributes], ecx
0x18003f36c  xor     edx, edx; DisableAllPrivileges
0x18003f36e  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18003f372  mov     [rsp+78h+PreviousState], rax; PreviousState
0x18003f377  call    cs:__imp_AdjustTokenPrivileges
0x18003f37d  mov     rcx, [rbp+TokenHandle]; hObject
0x18003f381  mov     edi, eax
0x18003f383  call    cs:__imp_CloseHandle
0x18003f389  test    edi, edi
0x18003f38b  jz      short loc_18003F3A1
0x18003f38d  cmp     [rbp+var_20.PrivilegeCount], 0
0x18003f391  jnz     short loc_18003F397
0x18003f393  mov     [rbx], esi
0x18003f395  jmp     short loc_18003F3A1
0x18003f397  mov     eax, [rbp+var_20.Privileges.Attributes]
0x18003f39a  shr     eax, 1
0x18003f39c  and     eax, 1
0x18003f39f  mov     [rbx], eax
0x18003f3a1  mov     eax, edi
0x18003f3a3  mov     rcx, [rbp+var_10]
0x18003f3a7  xor     rcx, rsp; StackCookie
0x18003f3aa  call    __security_check_cookie
0x18003f3af  add     rsp, 78h
0x18003f3b3  pop     rdi
0x18003f3b4  pop     rsi
0x18003f3b5  pop     rbx
0x18003f3b6  pop     rbp
0x18003f3b7  retn
```
