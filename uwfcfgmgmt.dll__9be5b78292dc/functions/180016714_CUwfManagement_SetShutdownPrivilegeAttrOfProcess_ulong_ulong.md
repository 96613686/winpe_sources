# CUwfManagement::SetShutdownPrivilegeAttrOfProcess(ulong,ulong &)

- ea: `0x180016714`
- end: `0x180016831`
- name: `?SetShutdownPrivilegeAttrOfProcess@CUwfManagement@@AEAAJKAEAK@Z`
- size: `285`
- prototype: `__int64 __fastcall(CUwfManagement *this, LONG, LONG *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180016840`

## callees

- `0x180016714`
- `0x18001b020`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016772`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800167da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016772`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800167da`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180016756`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180016756`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180016768`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180016768`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001680b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001680b`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x1800167d0`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x1800167d0`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x18001679a`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x18001679a`

## string_xrefs

- `0x180016793`: `SeShutdownPrivilege`

## pseudocode

```c
__int64 __fastcall CUwfManagement::SetShutdownPrivilegeAttrOfProcess(CUwfManagement *this, LONG a2, LONG *a3)
{
  HANDLE CurrentProcess; // rax
  signed int v6; // eax
  unsigned int v7; // ebx
  signed int LastError; // eax
  DWORD ReturnLength; // [rsp+30h] [rbp-40h] BYREF
  void *TokenHandle; // [rsp+38h] [rbp-38h] BYREF
  struct _LUID Luid[2]; // [rsp+40h] [rbp-30h] BYREF
  struct _TOKEN_PRIVILEGES PreviousState; // [rsp+50h] [rbp-20h] BYREF

  TokenHandle = 0;
  ReturnLength = 0;
  *(_OWORD *)&Luid[0].LowPart = 0;
  PreviousState = 0;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 0x28u, &TokenHandle)
    && LookupPrivilegeValueW(0, L"SeShutdownPrivilege", (PLUID)&Luid[0].HighPart)
    && (Luid[0].LowPart = 1,
        Luid[1].HighPart = a2,
        AdjustTokenPrivileges(TokenHandle, 0, (PTOKEN_PRIVILEGES)Luid, 0x10u, &PreviousState, &ReturnLength)) )
  {
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError > 0 )
      v7 = (unsigned __int16)LastError | 0x80070000;
    *a3 = Luid[1].HighPart;
    if ( v7 == -2147023596 )
      v7 = -2147024891;
  }
  else
  {
    v6 = GetLastError();
    v7 = v6;
    if ( v6 > 0 )
      v7 = (unsigned __int16)v6 | 0x80070000;
  }
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return v7;
}

```

## disassembly

```asm
0x180016714  mov     [rsp-8+arg_0], rbx
0x180016719  mov     [rsp-8+arg_8], rdi
0x18001671e  push    rbp
0x18001671f  mov     rbp, rsp
0x180016722  sub     rsp, 70h
0x180016726  mov     rax, cs:__security_cookie
0x18001672d  xor     rax, rsp
0x180016730  mov     [rbp+var_10], rax
0x180016734  xorps   xmm0, xmm0
0x180016737  mov     [rbp+TokenHandle], 0
0x18001673f  xorps   xmm1, xmm1
0x180016742  mov     [rbp+var_40], 0
0x180016749  movups  xmmword ptr [rbp+Luid.LowPart], xmm0
0x18001674d  mov     rdi, r8
0x180016750  mov     ebx, edx
0x180016752  movups  xmmword ptr [rbp+var_20.PrivilegeCount], xmm1
0x180016756  call    cs:__imp_GetCurrentProcess
0x18001675c  lea     r8, [rbp+TokenHandle]; TokenHandle
0x180016760  mov     edx, 28h ; '('; DesiredAccess
0x180016765  mov     rcx, rax; ProcessHandle
0x180016768  call    cs:__imp_OpenProcessToken
0x18001676e  test    eax, eax
0x180016770  jnz     short loc_18001678D
0x180016772  call    cs:__imp_GetLastError
0x180016778  mov     ebx, eax
0x18001677a  test    eax, eax
0x18001677c  jle     loc_180016802
0x180016782  movzx   ebx, ax
0x180016785  or      ebx, 80070000h
0x18001678b  jmp     short loc_180016802
0x18001678d  lea     r8, [rbp+Luid.HighPart]; lpLuid
0x180016791  xor     ecx, ecx; lpSystemName
0x180016793  lea     rdx, aSeshutdownpriv; "SeShutdownPrivilege"
0x18001679a  call    cs:__imp_LookupPrivilegeValueW
0x1800167a0  test    eax, eax
0x1800167a2  jz      short loc_180016772
0x1800167a4  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1800167a8  lea     rax, [rbp+var_40]
0x1800167ac  mov     [rsp+70h+ReturnLength], rax; ReturnLength
0x1800167b1  lea     r8, [rbp+Luid]; NewState
0x1800167b5  lea     rax, [rbp+var_20]
0x1800167b9  mov     [rbp+Luid.LowPart], 1
0x1800167c0  mov     r9d, 10h; BufferLength
0x1800167c6  mov     [rsp+70h+PreviousState], rax; PreviousState
0x1800167cb  xor     edx, edx; DisableAllPrivileges
0x1800167cd  mov     [rbp+Luid.HighPart+8], ebx
0x1800167d0  call    cs:__imp_AdjustTokenPrivileges
0x1800167d6  test    eax, eax
0x1800167d8  jz      short loc_180016772
0x1800167da  call    cs:__imp_GetLastError
0x1800167e0  mov     ebx, eax
0x1800167e2  test    eax, eax
0x1800167e4  jle     short loc_1800167EF
0x1800167e6  movzx   ebx, ax
0x1800167e9  or      ebx, 80070000h
0x1800167ef  mov     ecx, [rbp+Luid.HighPart+8]
0x1800167f2  cmp     ebx, 80070514h
0x1800167f8  mov     eax, 80070005h
0x1800167fd  mov     [rdi], ecx
0x1800167ff  cmovz   ebx, eax
0x180016802  mov     rcx, [rbp+TokenHandle]; hObject
0x180016806  test    rcx, rcx
0x180016809  jz      short loc_180016811
0x18001680b  call    cs:__imp_CloseHandle
0x180016811  mov     eax, ebx
0x180016813  mov     rcx, [rbp+var_10]
0x180016817  xor     rcx, rsp; StackCookie
0x18001681a  call    __security_check_cookie
0x18001681f  lea     r11, [rsp+70h+var_s0]
0x180016824  mov     rbx, [r11+10h]
0x180016828  mov     rdi, [r11+18h]
0x18001682c  mov     rsp, r11
0x18001682f  pop     rbp
0x180016830  retn
```
