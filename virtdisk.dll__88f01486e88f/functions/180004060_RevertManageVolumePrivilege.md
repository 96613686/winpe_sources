# RevertManageVolumePrivilege

- ea: `0x180004060`
- end: `0x180004103`
- name: `RevertManageVolumePrivilege`
- size: `163`
- prototype: `BOOL __fastcall(__int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800025c0`
- `0x180003930`
- `0x180009b90`

## callees

- `0x180004060`
- `0x180005730`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800040d1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800040d1`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x1800040c2`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x1800040c2`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800040e3`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800040e3`

## pseudocode

```c
BOOL __fastcall RevertManageVolumePrivilege(__int64 a1)
{
  HANDLE v2; // rcx
  BOOL result; // eax
  struct _TOKEN_PRIVILEGES NewState; // [rsp+30h] [rbp-28h] BYREF

  v2 = *(HANDLE *)a1;
  NewState = 0;
  if ( v2 )
  {
    if ( *(_BYTE *)(a1 + 9) && !*(_BYTE *)(a1 + 8) )
    {
      NewState.PrivilegeCount = 1;
      *(_QWORD *)&NewState.Privileges[0].Luid.HighPart = 0;
      NewState.Privileges[0].Luid.LowPart = 28;
      AdjustTokenPrivileges(v2, 0, &NewState, 0x10u, 0, 0);
    }
    result = CloseHandle(*(HANDLE *)a1);
  }
  if ( *(_BYTE *)(a1 + 8) )
    return RevertToSelf();
  return result;
}

```

## disassembly

```asm
0x180004060  push    rbx
0x180004062  sub     rsp, 50h
0x180004066  mov     rax, cs:__security_cookie
0x18000406d  xor     rax, rsp
0x180004070  mov     [rsp+58h+var_18], rax
0x180004075  mov     rbx, rcx
0x180004078  xorps   xmm0, xmm0
0x18000407b  mov     rcx, [rcx]; TokenHandle
0x18000407e  movups  xmmword ptr [rsp+58h+NewState.PrivilegeCount], xmm0
0x180004083  test    rcx, rcx
0x180004086  jz      short loc_1800040DD
0x180004088  cmp     byte ptr [rbx+9], 0
0x18000408c  jz      short loc_1800040CE
0x18000408e  cmp     byte ptr [rbx+8], 0
0x180004092  jnz     short loc_1800040CE
0x180004094  xor     eax, eax
0x180004096  mov     [rsp+58h+NewState.PrivilegeCount], 1
0x18000409e  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x1800040a3  lea     r8, [rsp+58h+NewState]; NewState
0x1800040a8  mov     r9d, 10h; BufferLength
0x1800040ae  mov     [rsp+58h+PreviousState], rax; PreviousState
0x1800040b3  xor     edx, edx; DisableAllPrivileges
0x1800040b5  mov     qword ptr [rsp+58h+NewState.Privileges.Luid.HighPart], rax
0x1800040ba  mov     [rsp+58h+NewState.Privileges.Luid.LowPart], 1Ch
0x1800040c2  call    cs:__imp_AdjustTokenPrivileges
0x1800040c9  nop     dword ptr [rax+rax+00h]
0x1800040ce  mov     rcx, [rbx]; hObject
0x1800040d1  call    cs:__imp_CloseHandle
0x1800040d8  nop     dword ptr [rax+rax+00h]
0x1800040dd  cmp     byte ptr [rbx+8], 0
0x1800040e1  jz      short loc_1800040EF
0x1800040e3  call    cs:__imp_RevertToSelf
0x1800040ea  nop     dword ptr [rax+rax+00h]
0x1800040ef  mov     rcx, [rsp+58h+var_18]
0x1800040f4  xor     rcx, rsp; StackCookie
0x1800040f7  call    __security_check_cookie
0x1800040fc  add     rsp, 50h
0x180004100  pop     rbx
0x180004101  retn
```
