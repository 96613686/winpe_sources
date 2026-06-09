# SOS_OS::SetPrivilege(void *,wchar_t const *,int)

- ea: `0x1004b9460`
- end: `0x1004b94fc`
- name: `?SetPrivilege@SOS_OS@@SA?AW4SOS_RESULT@@PEAXPEB_WH@Z`
- size: `156`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation`

## callees

- `0x100403070`
- `0x1004b9460`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1004b94d5`
- `KERNEL32!GetLastError` at `0x1004b94d5`
- `ADVAPI32!AdjustTokenPrivileges` at `0x1004b94cf`
- `ADVAPI32!AdjustTokenPrivileges` at `0x1004b94cf`
- `ADVAPI32!LookupPrivilegeValueW` at `0x1004b9486`
- `ADVAPI32!LookupPrivilegeValueW` at `0x1004b9486`

## pseudocode

```c
DWORD __fastcall SOS_OS::SetPrivilege(void *a1, const WCHAR *a2, int a3)
{
  DWORD result; // eax
  struct _LUID Luid; // [rsp+30h] [rbp-28h] BYREF
  struct _TOKEN_PRIVILEGES NewState; // [rsp+38h] [rbp-20h] BYREF

  if ( !LookupPrivilegeValueW(0, a2, &Luid) )
    return 0x80000000;
  NewState.Privileges[0].Luid = Luid;
  NewState.PrivilegeCount = 1;
  NewState.Privileges[0].Attributes = a3 != 0 ? 2 : 0;
  AdjustTokenPrivileges(a1, 0, &NewState, 0x10u, 0, 0);
  result = GetLastError();
  if ( result )
    return 0x80000000;
  return result;
}

```

## disassembly

```asm
0x1004b9460  mov     [rsp+arg_10], rbx
0x1004b9465  push    rdi
0x1004b9466  sub     rsp, 50h
0x1004b946a  mov     rax, cs:__security_cookie
0x1004b9471  xor     rax, rsp
0x1004b9474  mov     [rsp+58h+var_10], rax
0x1004b9479  mov     ebx, r8d
0x1004b947c  mov     rdi, rcx
0x1004b947f  lea     r8, [rsp+58h+Luid]; lpLuid
0x1004b9484  xor     ecx, ecx; lpSystemName
0x1004b9486  call    cs:__imp_LookupPrivilegeValueW
0x1004b948c  test    eax, eax
0x1004b948e  jz      short loc_1004B94DF
0x1004b9490  mov     rax, qword ptr [rsp+58h+Luid.LowPart]
0x1004b9495  lea     r8, [rsp+58h+NewState]; NewState
0x1004b949a  mov     qword ptr [rsp+58h+NewState.Privileges.Luid.LowPart], rax
0x1004b949f  neg     ebx
0x1004b94a1  mov     [rsp+58h+ReturnLength], 0; ReturnLength
0x1004b94aa  mov     r9d, 10h; BufferLength
0x1004b94b0  sbb     eax, eax
0x1004b94b2  mov     [rsp+58h+NewState.PrivilegeCount], 1
0x1004b94ba  and     eax, 2
0x1004b94bd  mov     [rsp+58h+PreviousState], 0; PreviousState
0x1004b94c6  xor     edx, edx; DisableAllPrivileges
0x1004b94c8  mov     [rsp+58h+NewState.Privileges.Attributes], eax
0x1004b94cc  mov     rcx, rdi; TokenHandle
0x1004b94cf  call    cs:__imp_AdjustTokenPrivileges
0x1004b94d5  call    cs:__imp_GetLastError
0x1004b94db  test    eax, eax
0x1004b94dd  jz      short loc_1004B94E4
0x1004b94df  mov     eax, 80000000h
0x1004b94e4  mov     rcx, [rsp+58h+var_10]
0x1004b94e9  xor     rcx, rsp; StackCookie
0x1004b94ec  call    __security_check_cookie
0x1004b94f1  mov     rbx, [rsp+58h+arg_10]
0x1004b94f6  add     rsp, 50h
0x1004b94fa  pop     rdi
0x1004b94fb  retn
```
