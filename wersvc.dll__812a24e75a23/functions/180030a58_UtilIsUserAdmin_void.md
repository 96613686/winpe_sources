# UtilIsUserAdmin(void *)

- ea: `0x180030a58`
- end: `0x180030bba`
- name: `?UtilIsUserAdmin@@YAHPEAX@Z`
- size: `354`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002ff0c`

## callees

- `0x1800029d0`
- `0x180007cf8`
- `0x18002f348`
- `0x180030a58`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180030ad0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180030ad0`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180030ae1`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180030ae1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030ab9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030ab9`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180030b3f`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180030b3f`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180030b57`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180030b57`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x180030aaf`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x180030aaf`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180030b72`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180030b72`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180030b86`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180030b9a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180030b86`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180030b9a`

## pseudocode

```c
_BOOL8 __fastcall UtilIsUserAdmin(HANDLE TokenHandle)
{
  HANDLE v1; // rbx
  BOOL v2; // edi
  void **v3; // rax
  int *v4; // r9
  void **v5; // rbx
  HANDLE CurrentProcess; // rax
  BOOL v7; // ebx
  PSID SidToCheck; // [rsp+60h] [rbp+7h] BYREF
  int v10; // [rsp+68h] [rbp+Fh] BYREF
  WINBOOL IsMember; // [rsp+6Ch] [rbp+13h] BYREF
  HANDLE hObject; // [rsp+70h] [rbp+17h] BYREF
  HANDLE TokenHandlea; // [rsp+78h] [rbp+1Fh] BYREF
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+80h] [rbp+27h] BYREF

  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  IsMember = 0;
  v1 = TokenHandle;
  v10 = 0;
  v2 = 0;
  LODWORD(SidToCheck) = 0;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  TokenHandlea = 0;
  hObject = 0;
  if ( TokenHandle )
  {
    v3 = tlx::replace<tlx::file_handle_traits>(&TokenHandlea);
    if ( !DuplicateToken(v1, SecurityImpersonation, v3) )
    {
LABEL_3:
      GetLastError();
      goto LABEL_14;
    }
  }
  else
  {
    v5 = tlx::replace<tlx::file_handle_traits>(&hObject);
    CurrentProcess = GetCurrentProcess();
    if ( !OpenProcessToken(CurrentProcess, 8u, v5) )
      goto LABEL_3;
    v1 = hObject;
  }
  if ( !(unsigned int)_werDetail::UtilLUAIsElevatedToken(v1, &v10, (int *)&SidToCheck, v4)
    && (v10 || (_DWORD)SidToCheck) )
  {
    SidToCheck = 0;
    v7 = AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, &SidToCheck);
    if ( v7 )
    {
      v2 = CheckTokenMembership(TokenHandlea, SidToCheck, &IsMember) && v7;
      if ( IsMember )
        v2 = 0;
    }
    if ( SidToCheck )
      FreeSid(SidToCheck);
  }
LABEL_14:
  if ( (unsigned __int64)hObject + 1 > 1 )
    CloseHandle(hObject);
  if ( (unsigned __int64)TokenHandlea + 1 > 1 )
    CloseHandle(TokenHandlea);
  return v2;
}

```

## disassembly

```asm
0x180030a58  push    rbp
0x180030a5a  push    rbx
0x180030a5b  push    rsi
0x180030a5c  push    rdi
0x180030a5d  lea     rbp, [rsp-3Fh]
0x180030a62  sub     rsp, 98h
0x180030a69  mov     rax, cs:__security_cookie
0x180030a70  xor     rax, rsp
0x180030a73  mov     [rbp+57h+var_28], rax
0x180030a77  xor     esi, esi
0x180030a79  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x180030a7f  mov     [rbp+57h+IsMember], esi
0x180030a82  mov     rbx, rcx
0x180030a85  mov     [rbp+57h+var_48], esi
0x180030a88  mov     edi, esi
0x180030a8a  mov     dword ptr [rbp+57h+SidToCheck], esi
0x180030a8d  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], esi
0x180030a90  mov     [rbp+57h+TokenHandle], rsi
0x180030a94  mov     [rbp+57h+hObject], rsi
0x180030a98  test    rcx, rcx
0x180030a9b  jz      short loc_180030AC4
0x180030a9d  lea     rcx, [rbp+57h+TokenHandle]
0x180030aa1  call    ??$replace@Ufile_handle_traits@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@Ufile_handle_traits@tlx@@@0@@Z; tlx::replace<tlx::file_handle_traits>(tlx::unique_any<tlx::file_handle_traits> &)
0x180030aa6  mov     r8, rax; DuplicateTokenHandle
0x180030aa9  lea     edx, [rsi+2]; ImpersonationLevel
0x180030aac  mov     rcx, rbx; ExistingTokenHandle
0x180030aaf  call    cs:__imp_DuplicateToken
0x180030ab5  test    eax, eax
0x180030ab7  jnz     short loc_180030AEF
0x180030ab9  call    cs:__imp_GetLastError
0x180030abf  jmp     loc_180030B78
0x180030ac4  lea     rcx, [rbp+57h+hObject]
0x180030ac8  call    ??$replace@Ufile_handle_traits@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@Ufile_handle_traits@tlx@@@0@@Z; tlx::replace<tlx::file_handle_traits>(tlx::unique_any<tlx::file_handle_traits> &)
0x180030acd  mov     rbx, rax
0x180030ad0  call    cs:__imp_GetCurrentProcess
0x180030ad6  mov     r8, rbx; TokenHandle
0x180030ad9  mov     edx, 8; DesiredAccess
0x180030ade  mov     rcx, rax; ProcessHandle
0x180030ae1  call    cs:__imp_OpenProcessToken
0x180030ae7  test    eax, eax
0x180030ae9  jz      short loc_180030AB9
0x180030aeb  mov     rbx, [rbp+57h+hObject]
0x180030aef  lea     r8, [rbp+57h+SidToCheck]; int *
0x180030af3  mov     rcx, rbx; TokenHandle
0x180030af6  lea     rdx, [rbp+57h+var_48]; void *
0x180030afa  call    ?UtilLUAIsElevatedToken@_werDetail@@YAJPEAXPEAH1@Z; _werDetail::UtilLUAIsElevatedToken(void *,int *,int *)
0x180030aff  test    eax, eax
0x180030b01  jnz     short loc_180030B78
0x180030b03  cmp     [rbp+57h+var_48], esi
0x180030b06  jnz     short loc_180030B0D
0x180030b08  cmp     dword ptr [rbp+57h+SidToCheck], esi
0x180030b0b  jz      short loc_180030B78
0x180030b0d  lea     rax, [rbp+57h+SidToCheck]
0x180030b11  mov     [rbp+57h+SidToCheck], rsi
0x180030b15  mov     [rsp+0B0h+pSid], rax; pSid
0x180030b1a  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x180030b1e  mov     [rsp+0B0h+nSubAuthority7], esi; nSubAuthority7
0x180030b22  xor     r9d, r9d; nSubAuthority1
0x180030b25  mov     [rsp+0B0h+nSubAuthority6], esi; nSubAuthority6
0x180030b29  mov     dl, 1; nSubAuthorityCount
0x180030b2b  mov     [rsp+0B0h+nSubAuthority5], esi; nSubAuthority5
0x180030b2f  mov     [rsp+0B0h+nSubAuthority4], esi; nSubAuthority4
0x180030b33  mov     [rsp+0B0h+nSubAuthority3], esi; nSubAuthority3
0x180030b37  lea     r8d, [r9+12h]; nSubAuthority0
0x180030b3b  mov     [rsp+0B0h+nSubAuthority2], esi; nSubAuthority2
0x180030b3f  call    cs:__imp_AllocateAndInitializeSid
0x180030b45  mov     ebx, eax
0x180030b47  test    eax, eax
0x180030b49  jz      short loc_180030B69
0x180030b4b  mov     rdx, [rbp+57h+SidToCheck]; SidToCheck
0x180030b4f  lea     r8, [rbp+57h+IsMember]; IsMember
0x180030b53  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x180030b57  call    cs:__imp_CheckTokenMembership
0x180030b5d  neg     eax
0x180030b5f  sbb     edi, edi
0x180030b61  and     edi, ebx
0x180030b63  cmp     [rbp+57h+IsMember], esi
0x180030b66  cmovnz  edi, esi
0x180030b69  mov     rcx, [rbp+57h+SidToCheck]; pSid
0x180030b6d  test    rcx, rcx
0x180030b70  jz      short loc_180030B78
0x180030b72  call    cs:__imp_FreeSid
0x180030b78  mov     rcx, [rbp+57h+hObject]; hObject
0x180030b7c  lea     rax, [rcx+1]
0x180030b80  cmp     rax, 1
0x180030b84  jbe     short loc_180030B8C
0x180030b86  call    cs:__imp_CloseHandle
0x180030b8c  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x180030b90  lea     rdx, [rcx+1]
0x180030b94  cmp     rdx, 1
0x180030b98  jbe     short loc_180030BA0
0x180030b9a  call    cs:__imp_CloseHandle
0x180030ba0  mov     eax, edi
0x180030ba2  mov     rcx, [rbp+57h+var_28]
0x180030ba6  xor     rcx, rsp; StackCookie
0x180030ba9  call    __security_check_cookie
0x180030bae  add     rsp, 98h
0x180030bb5  pop     rdi
0x180030bb6  pop     rsi
0x180030bb7  pop     rbx
0x180030bb8  pop     rbp
0x180030bb9  retn
```
