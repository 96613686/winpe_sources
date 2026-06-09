# WrpSetPrivilegesByName

- ea: `0x180007424`
- end: `0x180007561`
- name: `WrpSetPrivilegesByName`
- size: `317`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800038e0`

## callees

- `0x180007424`
- `0x18001b7b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800074ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800074ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000752e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800074ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800074ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000752e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007515`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007515`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800074a4`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800074a4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180007492`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180007492`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x1800074e4`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x1800074e4`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x180007466`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x180007466`

## pseudocode

```c
__int64 WrpSetPrivilegesByName()
{
  __int64 v0; // rdi
  HANDLE CurrentProcess; // rax
  signed int v2; // eax
  unsigned int v3; // ebx
  signed int LastError; // eax
  signed int v5; // eax
  void *TokenHandle; // [rsp+30h] [rbp-30h] BYREF
  _LUID Luid; // [rsp+38h] [rbp-28h] BYREF
  struct _TOKEN_PRIVILEGES NewState; // [rsp+40h] [rbp-20h] BYREF

  Luid = 0;
  NewState = 0;
  v0 = 0;
  while ( LookupPrivilegeValueW(0, (LPCWSTR)(&PRIVILEGES_BACKUP_RESTORE)[v0], &Luid) )
  {
    NewState.Privileges[0].Luid = Luid;
    NewState.PrivilegeCount = 1;
    NewState.Privileges[0].Attributes = 2;
    TokenHandle = 0;
    CurrentProcess = GetCurrentProcess();
    if ( OpenProcessToken(CurrentProcess, 0x20028u, &TokenHandle) )
    {
      if ( AdjustTokenPrivileges(TokenHandle, 0, &NewState, 0, 0, 0) )
      {
        v3 = 0;
      }
      else
      {
        LastError = GetLastError();
        v3 = LastError;
        if ( LastError > 0 )
          v3 = (unsigned __int16)LastError | 0x80070000;
      }
      if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        CloseHandle(TokenHandle);
    }
    else
    {
      v2 = GetLastError();
      v3 = v2;
      if ( v2 > 0 )
        v3 = (unsigned __int16)v2 | 0x80070000;
    }
    if ( (v3 & 0x80000000) != 0 )
      return v3;
    v0 = (unsigned int)(v0 + 1);
    if ( (unsigned int)v0 >= 2 )
      return 0;
  }
  v5 = GetLastError();
  v3 = v5;
  if ( v5 > 0 )
    return (unsigned __int16)v5 | 0x80070000;
  return v3;
}

```

## disassembly

```asm
0x180007424  mov     [rsp-8+arg_0], rbx
0x180007429  mov     [rsp-8+arg_8], rdi
0x18000742e  push    rbp
0x18000742f  mov     rbp, rsp
0x180007432  sub     rsp, 60h
0x180007436  mov     rax, cs:__security_cookie
0x18000743d  xor     rax, rsp
0x180007440  mov     [rbp+var_10], rax
0x180007444  xorps   xmm0, xmm0
0x180007447  mov     qword ptr [rbp+Luid.LowPart], 0
0x18000744f  movups  xmmword ptr [rbp+NewState.PrivilegeCount], xmm0
0x180007453  xor     edi, edi
0x180007455  lea     rax, ?PRIVILEGES_BACKUP_RESTORE@@3PAPEBGA; ushort const * near * PRIVILEGES_BACKUP_RESTORE
0x18000745c  xor     ecx, ecx; lpSystemName
0x18000745e  mov     rdx, [rax+rdi*8]; lpName
0x180007462  lea     r8, [rbp+Luid]; lpLuid
0x180007466  call    cs:__imp_LookupPrivilegeValueW
0x18000746c  test    eax, eax
0x18000746e  jz      loc_18000752E
0x180007474  mov     rax, qword ptr [rbp+Luid.LowPart]
0x180007478  mov     qword ptr [rbp+NewState.Privileges.Luid.LowPart], rax
0x18000747c  mov     [rbp+NewState.PrivilegeCount], 1
0x180007483  mov     [rbp+NewState.Privileges.Attributes], 2
0x18000748a  mov     [rbp+TokenHandle], 0
0x180007492  call    cs:__imp_GetCurrentProcess
0x180007498  lea     r8, [rbp+TokenHandle]; TokenHandle
0x18000749c  mov     edx, 20028h; DesiredAccess
0x1800074a1  mov     rcx, rax; ProcessHandle
0x1800074a4  call    cs:__imp_OpenProcessToken
0x1800074aa  test    eax, eax
0x1800074ac  jnz     short loc_1800074C5
0x1800074ae  call    cs:__imp_GetLastError
0x1800074b4  mov     ebx, eax
0x1800074b6  test    eax, eax
0x1800074b8  jle     short loc_18000751B
0x1800074ba  movzx   ebx, ax
0x1800074bd  or      ebx, 80070000h
0x1800074c3  jmp     short loc_18000751B
0x1800074c5  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1800074c9  lea     r8, [rbp+NewState]; NewState
0x1800074cd  mov     [rsp+60h+ReturnLength], 0; ReturnLength
0x1800074d6  xor     r9d, r9d; BufferLength
0x1800074d9  xor     edx, edx; DisableAllPrivileges
0x1800074db  mov     [rsp+60h+PreviousState], 0; PreviousState
0x1800074e4  call    cs:__imp_AdjustTokenPrivileges
0x1800074ea  test    eax, eax
0x1800074ec  jnz     short loc_180007505
0x1800074ee  call    cs:__imp_GetLastError
0x1800074f4  mov     ebx, eax
0x1800074f6  test    eax, eax
0x1800074f8  jle     short loc_180007507
0x1800074fa  movzx   ebx, ax
0x1800074fd  or      ebx, 80070000h
0x180007503  jmp     short loc_180007507
0x180007505  xor     ebx, ebx
0x180007507  mov     rcx, [rbp+TokenHandle]; hObject
0x18000750b  lea     rax, [rcx-1]
0x18000750f  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180007513  ja      short loc_18000751B
0x180007515  call    cs:__imp_CloseHandle
0x18000751b  test    ebx, ebx
0x18000751d  js      short loc_180007543
0x18000751f  inc     edi
0x180007521  cmp     edi, 2
0x180007524  jb      loc_180007455
0x18000752a  xor     ebx, ebx
0x18000752c  jmp     short loc_180007543
0x18000752e  call    cs:__imp_GetLastError
0x180007534  mov     ebx, eax
0x180007536  test    eax, eax
0x180007538  jle     short loc_180007543
0x18000753a  movzx   ebx, ax
0x18000753d  or      ebx, 80070000h
0x180007543  mov     eax, ebx
0x180007545  mov     rcx, [rbp+var_10]
0x180007549  xor     rcx, rsp; StackCookie
0x18000754c  call    __security_check_cookie
0x180007551  mov     rbx, [rsp+60h+arg_0]
0x180007556  mov     rdi, [rsp+60h+arg_8]
0x18000755b  add     rsp, 60h
0x18000755f  pop     rbp
0x180007560  retn
```
