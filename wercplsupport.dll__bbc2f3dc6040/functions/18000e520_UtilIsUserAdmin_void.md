# UtilIsUserAdmin(void *)

- ea: `0x18000e520`
- end: `0x18000e63f`
- name: `?UtilIsUserAdmin@@YAHPEAX@Z`
- size: `287`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000e700`

## callees

- `0x180002a48`
- `0x18000e520`
- `0x18000e648`
- `0x1800121b0`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18000e5da`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18000e5da`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18000e5f0`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18000e5f0`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18000e60b`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18000e60b`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000e574`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000e574`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000e565`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000e565`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e57e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e57e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e61f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e61f`

## pseudocode

```c
_BOOL8 __fastcall UtilIsUserAdmin(void *a1)
{
  BOOL v1; // edi
  void **v2; // rbx
  HANDLE CurrentProcess; // rax
  int *v4; // r9
  BOOL v5; // ebx
  PSID SidToCheck; // [rsp+60h] [rbp+7h] BYREF
  int v8; // [rsp+68h] [rbp+Fh] BYREF
  WINBOOL IsMember; // [rsp+6Ch] [rbp+13h] BYREF
  HANDLE hObject; // [rsp+70h] [rbp+17h] BYREF
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+78h] [rbp+1Fh] BYREF

  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  IsMember = 0;
  v1 = 0;
  v8 = 0;
  LODWORD(SidToCheck) = 0;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  hObject = 0;
  v2 = (void **)tlx::replace<tlx::file_handle_traits>(&hObject);
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 8u, v2) )
  {
    if ( !(unsigned int)_werDetail::UtilLUAIsElevatedToken(hObject, &v8, (int *)&SidToCheck, v4)
      && (v8 || (_DWORD)SidToCheck) )
    {
      SidToCheck = 0;
      v5 = AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, &SidToCheck);
      if ( v5 )
      {
        v1 = CheckTokenMembership(0, SidToCheck, &IsMember) && v5;
        if ( IsMember )
          v1 = 0;
      }
      if ( SidToCheck )
        FreeSid(SidToCheck);
    }
  }
  else
  {
    GetLastError();
  }
  if ( (unsigned __int64)hObject + 1 > 1 )
    CloseHandle(hObject);
  return v1;
}

```

## disassembly

```asm
0x18000e520  push    rbp
0x18000e522  push    rbx
0x18000e523  push    rsi
0x18000e524  push    rdi
0x18000e525  lea     rbp, [rsp-3Fh]
0x18000e52a  sub     rsp, 98h
0x18000e531  mov     rax, cs:__security_cookie
0x18000e538  xor     rax, rsp
0x18000e53b  mov     [rbp+57h+var_30], rax
0x18000e53f  xor     esi, esi
0x18000e541  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x18000e547  lea     rcx, [rbp+57h+hObject]
0x18000e54b  mov     [rbp+57h+IsMember], esi
0x18000e54e  mov     edi, esi
0x18000e550  mov     [rbp+57h+var_48], esi
0x18000e553  mov     dword ptr [rbp+57h+SidToCheck], esi
0x18000e556  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], esi
0x18000e559  mov     [rbp+57h+hObject], rsi
0x18000e55d  call    ??$replace@Ufile_handle_traits@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@Ufile_handle_traits@tlx@@@0@@Z; tlx::replace<tlx::file_handle_traits>(tlx::unique_any<tlx::file_handle_traits> &)
0x18000e562  mov     rbx, rax
0x18000e565  call    cs:__imp_GetCurrentProcess
0x18000e56b  mov     r8, rbx; TokenHandle
0x18000e56e  lea     edx, [rsi+8]; DesiredAccess
0x18000e571  mov     rcx, rax; ProcessHandle
0x18000e574  call    cs:__imp_OpenProcessToken
0x18000e57a  test    eax, eax
0x18000e57c  jnz     short loc_18000E589
0x18000e57e  call    cs:__imp_GetLastError
0x18000e584  jmp     loc_18000E611
0x18000e589  mov     rcx, [rbp+57h+hObject]; TokenHandle
0x18000e58d  lea     r8, [rbp+57h+SidToCheck]; int *
0x18000e591  lea     rdx, [rbp+57h+var_48]; void *
0x18000e595  call    ?UtilLUAIsElevatedToken@_werDetail@@YAJPEAXPEAH1@Z; _werDetail::UtilLUAIsElevatedToken(void *,int *,int *)
0x18000e59a  test    eax, eax
0x18000e59c  jnz     short loc_18000E611
0x18000e59e  cmp     [rbp+57h+var_48], esi
0x18000e5a1  jnz     short loc_18000E5A8
0x18000e5a3  cmp     dword ptr [rbp+57h+SidToCheck], esi
0x18000e5a6  jz      short loc_18000E611
0x18000e5a8  lea     rax, [rbp+57h+SidToCheck]
0x18000e5ac  mov     [rbp+57h+SidToCheck], rsi
0x18000e5b0  mov     [rsp+0B0h+pSid], rax; pSid
0x18000e5b5  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x18000e5b9  mov     [rsp+0B0h+nSubAuthority7], esi; nSubAuthority7
0x18000e5bd  xor     r9d, r9d; nSubAuthority1
0x18000e5c0  mov     [rsp+0B0h+nSubAuthority6], esi; nSubAuthority6
0x18000e5c4  mov     dl, 1; nSubAuthorityCount
0x18000e5c6  mov     [rsp+0B0h+nSubAuthority5], esi; nSubAuthority5
0x18000e5ca  mov     [rsp+0B0h+nSubAuthority4], esi; nSubAuthority4
0x18000e5ce  mov     [rsp+0B0h+nSubAuthority3], esi; nSubAuthority3
0x18000e5d2  lea     r8d, [r9+12h]; nSubAuthority0
0x18000e5d6  mov     [rsp+0B0h+nSubAuthority2], esi; nSubAuthority2
0x18000e5da  call    cs:__imp_AllocateAndInitializeSid
0x18000e5e0  mov     ebx, eax
0x18000e5e2  test    eax, eax
0x18000e5e4  jz      short loc_18000E602
0x18000e5e6  mov     rdx, [rbp+57h+SidToCheck]; SidToCheck
0x18000e5ea  lea     r8, [rbp+57h+IsMember]; IsMember
0x18000e5ee  xor     ecx, ecx; TokenHandle
0x18000e5f0  call    cs:__imp_CheckTokenMembership
0x18000e5f6  neg     eax
0x18000e5f8  sbb     edi, edi
0x18000e5fa  and     edi, ebx
0x18000e5fc  cmp     [rbp+57h+IsMember], esi
0x18000e5ff  cmovnz  edi, esi
0x18000e602  mov     rcx, [rbp+57h+SidToCheck]; pSid
0x18000e606  test    rcx, rcx
0x18000e609  jz      short loc_18000E611
0x18000e60b  call    cs:__imp_FreeSid
0x18000e611  mov     rcx, [rbp+57h+hObject]; hObject
0x18000e615  lea     rdx, [rcx+1]
0x18000e619  cmp     rdx, 1
0x18000e61d  jbe     short loc_18000E625
0x18000e61f  call    cs:__imp_CloseHandle
0x18000e625  mov     eax, edi
0x18000e627  mov     rcx, [rbp+57h+var_30]
0x18000e62b  xor     rcx, rsp; StackCookie
0x18000e62e  call    __security_check_cookie
0x18000e633  add     rsp, 98h
0x18000e63a  pop     rdi
0x18000e63b  pop     rsi
0x18000e63c  pop     rbx
0x18000e63d  pop     rbp
0x18000e63e  retn
```
