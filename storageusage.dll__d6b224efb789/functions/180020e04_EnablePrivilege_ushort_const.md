# EnablePrivilege(ushort const *)

- ea: `0x180020e04`
- end: `0x180020f8f`
- name: `?EnablePrivilege@@YAHPEBG@Z`
- size: `395`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800222a8`

## callees

- `0x1800050f0`
- `0x180020e04`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x180020e8f`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x180020f0e`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x180020e8f`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x180020f0e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180020f59`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180020f62`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18002bb2b`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18002bb35`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180020f59`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180020f62`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18002bb2b`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18002bb35`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180020ea7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180020ea7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020efc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020efc`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x180020eec`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x180020f3f`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x180020eec`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x180020f3f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180020e4c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180020e4c`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180020e5d`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180020e5d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020f50`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002bb21`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020f50`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002bb21`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x180020e81`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x180020e81`

## string_xrefs

- `0x180020e78`: `SeBackupPrivilege`

## pseudocode

```c
BOOL __fastcall EnablePrivilege(const unsigned __int16 *a1)
{
  struct _TOKEN_PRIVILEGES *v1; // rbx
  BOOL v2; // esi
  HANDLE CurrentProcess; // rax
  BOOL result; // eax
  struct _TOKEN_PRIVILEGES *v5; // rax
  struct _TOKEN_PRIVILEGES *v6; // rdi
  DWORD BufferLength; // [rsp+30h] [rbp-448h] BYREF
  void *TokenHandle; // [rsp+38h] [rbp-440h] BYREF
  BOOL v9; // [rsp+40h] [rbp-438h]
  _LUID Luid; // [rsp+48h] [rbp-430h] BYREF
  struct _TOKEN_PRIVILEGES *v11; // [rsp+50h] [rbp-428h]
  struct _TOKEN_PRIVILEGES *v12; // [rsp+58h] [rbp-420h]
  struct _TOKEN_PRIVILEGES PreviousState; // [rsp+60h] [rbp-418h] BYREF

  TokenHandle = 0;
  v11 = 0;
  v1 = 0;
  v12 = 0;
  BufferLength = 0;
  v2 = 0;
  Luid = 0;
  CurrentProcess = GetCurrentProcess();
  result = OpenProcessToken(CurrentProcess, 0x28u, &TokenHandle);
  if ( result )
  {
    BufferLength = 0;
    LookupPrivilegeValueW(0, L"SeBackupPrivilege", &Luid);
    v5 = (struct _TOKEN_PRIVILEGES *)calloc(1u, 0x10u);
    v6 = v5;
    v11 = v5;
    if ( !v5 )
      goto LABEL_3;
    v5->PrivilegeCount = 1;
    v5->Privileges[0].Luid = Luid;
    v5->Privileges[0].Attributes = 2;
    v2 = AdjustTokenPrivileges(TokenHandle, 0, v5, 0x400u, &PreviousState, &BufferLength);
    v9 = v2;
    if ( v2 || GetLastError() != 122 )
      goto LABEL_8;
    v1 = (struct _TOKEN_PRIVILEGES *)calloc(1u, BufferLength);
    v12 = v1;
    if ( v1 )
    {
      v2 = AdjustTokenPrivileges(TokenHandle, 0, v6, BufferLength, v1, &BufferLength);
      v9 = v2;
    }
    else
    {
LABEL_3:
      SetLastError(8u);
    }
LABEL_8:
    CloseHandle(TokenHandle);
    free(v6);
    free(v1);
    return v2;
  }
  return result;
}

```

## disassembly

```asm
0x180020e04  mov     [rsp+arg_0], rbx
0x180020e09  mov     [rsp+arg_8], rsi
0x180020e0e  push    rdi
0x180020e0f  sub     rsp, 470h
0x180020e16  mov     rax, cs:__security_cookie
0x180020e1d  xor     rax, rsp
0x180020e20  mov     [rsp+478h+var_18], rax
0x180020e28  mov     [rsp+478h+TokenHandle], 0
0x180020e31  mov     [rsp+478h+var_428], 0
0x180020e3a  xor     ebx, ebx
0x180020e3c  mov     [rsp+478h+var_420], rbx
0x180020e41  mov     [rsp+478h+BufferLength], ebx
0x180020e45  xor     esi, esi
0x180020e47  mov     qword ptr [rsp+478h+Luid.LowPart], rbx
0x180020e4c  call    cs:__imp_GetCurrentProcess
0x180020e52  mov     rcx, rax; ProcessHandle
0x180020e55  lea     r8, [rsp+478h+TokenHandle]; TokenHandle
0x180020e5a  lea     edx, [rbx+28h]; DesiredAccess
0x180020e5d  call    cs:__imp_OpenProcessToken
0x180020e63  test    eax, eax
0x180020e65  jz      loc_180020F6A
0x180020e6b  mov     [rsp+478h+BufferLength], 0
0x180020e73  lea     r8, [rsp+478h+Luid]; lpLuid
0x180020e78  lea     rdx, Name; "SeBackupPrivilege"
0x180020e7f  xor     ecx, ecx; lpSystemName
0x180020e81  call    cs:__imp_LookupPrivilegeValueW
0x180020e87  mov     edx, 10h; Size
0x180020e8c  lea     ecx, [rdx-0Fh]; Count
0x180020e8f  call    cs:__imp_calloc
0x180020e95  mov     rdi, rax
0x180020e98  mov     [rsp+478h+var_428], rax
0x180020e9d  test    rax, rax
0x180020ea0  jnz     short loc_180020EB2
0x180020ea2  mov     ecx, 8; dwErrCode
0x180020ea7  call    cs:__imp_SetLastError
0x180020ead  jmp     loc_180020F4B
0x180020eb2  mov     dword ptr [rax], 1
0x180020eb8  mov     rax, qword ptr [rsp+478h+Luid.LowPart]
0x180020ebd  mov     [rdi+4], rax
0x180020ec1  mov     dword ptr [rdi+0Ch], 2
0x180020ec8  lea     rax, [rsp+478h+BufferLength]
0x180020ecd  mov     [rsp+478h+ReturnLength], rax; ReturnLength
0x180020ed2  lea     rax, [rsp+478h+var_418]
0x180020ed7  mov     [rsp+478h+PreviousState], rax; PreviousState
0x180020edc  mov     r9d, 400h; BufferLength
0x180020ee2  mov     r8, rdi; NewState
0x180020ee5  xor     edx, edx; DisableAllPrivileges
0x180020ee7  mov     rcx, [rsp+478h+TokenHandle]; TokenHandle
0x180020eec  call    cs:__imp_AdjustTokenPrivileges
0x180020ef2  mov     esi, eax
0x180020ef4  mov     [rsp+478h+var_438], eax
0x180020ef8  test    eax, eax
0x180020efa  jnz     short loc_180020F4B
0x180020efc  call    cs:__imp_GetLastError
0x180020f02  cmp     eax, 7Ah ; 'z'
0x180020f05  jnz     short loc_180020F4B
0x180020f07  mov     edx, [rsp+478h+BufferLength]; Size
0x180020f0b  lea     ecx, [rsi+1]; Count
0x180020f0e  call    cs:__imp_calloc
0x180020f14  mov     rbx, rax
0x180020f17  mov     [rsp+478h+var_420], rax
0x180020f1c  test    rax, rax
0x180020f1f  jz      short loc_180020EA2
0x180020f21  lea     rax, [rsp+478h+BufferLength]
0x180020f26  mov     [rsp+478h+ReturnLength], rax; ReturnLength
0x180020f2b  mov     [rsp+478h+PreviousState], rbx; PreviousState
0x180020f30  mov     r9d, [rsp+478h+BufferLength]; BufferLength
0x180020f35  mov     r8, rdi; NewState
0x180020f38  xor     edx, edx; DisableAllPrivileges
0x180020f3a  mov     rcx, [rsp+478h+TokenHandle]; TokenHandle
0x180020f3f  call    cs:__imp_AdjustTokenPrivileges
0x180020f45  mov     esi, eax
0x180020f47  mov     [rsp+478h+var_438], eax
0x180020f4b  mov     rcx, [rsp+478h+TokenHandle]; hObject
0x180020f50  call    cs:__imp_CloseHandle
0x180020f56  mov     rcx, rdi; Block
0x180020f59  call    cs:__imp_free
0x180020f5f  mov     rcx, rbx; Block
0x180020f62  call    cs:__imp_free
0x180020f68  mov     eax, esi
0x180020f6a  mov     rcx, [rsp+478h+var_18]
0x180020f72  xor     rcx, rsp; StackCookie
0x180020f75  call    __security_check_cookie
0x180020f7a  lea     r11, [rsp+478h+var_8]
0x180020f82  mov     rbx, [r11+10h]
0x180020f86  mov     rsi, [r11+18h]
0x180020f8a  mov     rsp, r11
0x180020f8d  pop     rdi
0x180020f8e  retn
0x18002bb14  push    rbp
0x18002bb16  sub     rsp, 30h
0x18002bb1a  mov     rbp, rdx
0x18002bb1d  mov     rcx, [rbp+38h]; hObject
0x18002bb21  call    cs:__imp_CloseHandle
0x18002bb27  mov     rcx, [rbp+50h]; Block
0x18002bb2b  call    cs:__imp_free
0x18002bb31  mov     rcx, [rbp+58h]; Block
0x18002bb35  call    cs:__imp_free
0x18002bb3b  nop
0x18002bb3c  add     rsp, 30h
0x18002bb40  pop     rbp
0x18002bb41  retn
```
