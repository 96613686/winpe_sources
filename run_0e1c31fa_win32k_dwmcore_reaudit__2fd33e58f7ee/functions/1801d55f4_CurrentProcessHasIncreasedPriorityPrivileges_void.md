# CurrentProcessHasIncreasedPriorityPrivileges(void)

- ea: `0x1801d55f4`
- end: `0x1801d56d2`
- name: `?CurrentProcessHasIncreasedPriorityPrivileges@@YA_NXZ`
- size: `222`
- prototype: `bool(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18027e574`

## callees

- `0x1801d55f4`
- `0x180228490`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1801d5658`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1801d5658`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1801d5646`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1801d5646`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801d569a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801d569a`
- `api-ms-win-security-base-l1-1-0!PrivilegeCheck` at `0x1801d568e`
- `api-ms-win-security-base-l1-1-0!PrivilegeCheck` at `0x1801d568e`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x1801d5630`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x1801d5630`

## string_xrefs

- `0x1801d5620`: `SeIncreaseBasePriorityPrivilege`

## pseudocode

```c
char CurrentProcessHasIncreasedPriorityPrivileges(void)
{
  HANDLE CurrentProcess; // rax
  char v1; // di
  BOOL v2; // ebx
  WINBOOL pfResult; // [rsp+20h] [rbp-40h] BYREF
  void *TokenHandle; // [rsp+28h] [rbp-38h] BYREF
  _LUID Luid; // [rsp+30h] [rbp-30h] BYREF
  DWORD v7; // [rsp+38h] [rbp-28h]
  _PRIVILEGE_SET RequiredPrivileges; // [rsp+40h] [rbp-20h] BYREF

  Luid = 0;
  v7 = 2;
  if ( !LookupPrivilegeValueW(0, L"SeIncreaseBasePriorityPrivilege", &Luid) )
    return 0;
  TokenHandle = 0;
  CurrentProcess = GetCurrentProcess();
  if ( !OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
    return 0;
  RequiredPrivileges.Privilege[0].Luid = Luid;
  v1 = 1;
  RequiredPrivileges.Privilege[0].Attributes = v7;
  RequiredPrivileges.PrivilegeCount = 1;
  RequiredPrivileges.Control = 1;
  pfResult = 0;
  v2 = PrivilegeCheck(TokenHandle, &RequiredPrivileges, &pfResult);
  CloseHandle(TokenHandle);
  if ( !v2 || !pfResult )
    return 0;
  return v1;
}

```

## disassembly

```asm
0x1801d55f4  mov     [rsp-8+arg_0], rbx
0x1801d55f9  mov     [rsp-8+arg_8], rdi
0x1801d55fe  push    rbp
0x1801d55ff  mov     rbp, rsp
0x1801d5602  sub     rsp, 60h
0x1801d5606  mov     rax, cs:__security_cookie
0x1801d560d  xor     rax, rsp
0x1801d5610  mov     [rbp+var_8], rax
0x1801d5614  lea     r8, [rbp+Luid]; lpLuid
0x1801d5618  mov     qword ptr [rbp+Luid.LowPart], 0
0x1801d5620  lea     rdx, Name; "SeIncreaseBasePriorityPrivilege"
0x1801d5627  mov     [rbp+var_28], 2
0x1801d562e  xor     ecx, ecx; lpSystemName
0x1801d5630  call    cs:__imp_LookupPrivilegeValueW
0x1801d5636  test    eax, eax
0x1801d5638  jz      loc_1801D56CE
0x1801d563e  mov     [rbp+TokenHandle], 0
0x1801d5646  call    cs:__imp_GetCurrentProcess
0x1801d564c  lea     r8, [rbp+TokenHandle]; TokenHandle
0x1801d5650  mov     edx, 8; DesiredAccess
0x1801d5655  mov     rcx, rax; ProcessHandle
0x1801d5658  call    cs:__imp_OpenProcessToken
0x1801d565e  test    eax, eax
0x1801d5660  jz      short loc_1801D56CE
0x1801d5662  mov     rax, qword ptr [rbp+Luid.LowPart]
0x1801d5666  lea     r8, [rbp+pfResult]; pfResult
0x1801d566a  mov     rcx, [rbp+TokenHandle]; ClientToken
0x1801d566e  lea     rdx, [rbp+RequiredPrivileges]; RequiredPrivileges
0x1801d5672  mov     qword ptr [rbp+RequiredPrivileges.Privilege.Luid.LowPart], rax
0x1801d5676  mov     edi, 1
0x1801d567b  mov     eax, [rbp+var_28]
0x1801d567e  mov     [rbp+RequiredPrivileges.Privilege.Attributes], eax
0x1801d5681  mov     [rbp+RequiredPrivileges.PrivilegeCount], edi
0x1801d5684  mov     [rbp+RequiredPrivileges.Control], edi
0x1801d5687  mov     [rbp+pfResult], 0
0x1801d568e  call    cs:__imp_PrivilegeCheck
0x1801d5694  mov     rcx, [rbp+TokenHandle]; hObject
0x1801d5698  mov     ebx, eax
0x1801d569a  call    cs:__imp_CloseHandle
0x1801d56a0  test    ebx, ebx
0x1801d56a2  jz      short loc_1801D56C9
0x1801d56a4  cmp     [rbp+pfResult], 0
0x1801d56a8  jz      short loc_1801D56C9
0x1801d56aa  mov     al, dil
0x1801d56ad  mov     rcx, [rbp+var_8]
0x1801d56b1  xor     rcx, rsp; StackCookie
0x1801d56b4  call    __security_check_cookie
0x1801d56b9  mov     rbx, [rsp+60h+arg_0]
0x1801d56be  mov     rdi, [rsp+60h+arg_8]
0x1801d56c3  add     rsp, 60h
0x1801d56c7  pop     rbp
0x1801d56c8  retn
0x1801d56c9  xor     dil, dil
0x1801d56cc  jmp     short loc_1801D56AA
0x1801d56ce  xor     al, al
0x1801d56d0  jmp     short loc_1801D56AD
```
