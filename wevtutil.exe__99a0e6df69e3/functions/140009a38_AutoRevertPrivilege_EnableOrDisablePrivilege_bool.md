# AutoRevertPrivilege::EnableOrDisablePrivilege(bool)

- ea: `0x140009a38`
- end: `0x140009aad`
- name: `?EnableOrDisablePrivilege@AutoRevertPrivilege@@AEAA_N_N@Z`
- size: `117`
- prototype: `bool __fastcall(AutoRevertPrivilege *__hidden this, bool)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140009ae4`
- `0x14002f47c`

## callees

- `0x140009a38`
- `0x140021b00`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140009a8d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140009a8d`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x140009a83`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x140009a83`

## pseudocode

```c
bool __fastcall AutoRevertPrivilege::EnableOrDisablePrivilege(AutoRevertPrivilege *this, unsigned __int8 a2)
{
  LUID v2; // rax
  void *v3; // rcx
  BOOL v4; // eax
  struct _TOKEN_PRIVILEGES v6; // [rsp+30h] [rbp-28h] BYREF

  v6.PrivilegeCount = 1;
  v6.Privileges[0].Attributes = 2 * a2;
  v2 = (LUID)*((_QWORD *)this + 1);
  v3 = *(void **)this;
  v6.Privileges[0].Luid = v2;
  v4 = AdjustTokenPrivileges(v3, 0, &v6, 0, 0, 0);
  if ( v4 )
    LOBYTE(v4) = GetLastError() != 1300;
  return v4;
}

```

## disassembly

```asm
0x140009a38  mov     r11, rsp
0x140009a3b  sub     rsp, 58h
0x140009a3f  mov     rax, cs:__security_cookie
0x140009a46  xor     rax, rsp
0x140009a49  mov     [rsp+58h+var_18], rax
0x140009a4e  movzx   eax, dl
0x140009a51  lea     r8, [r11-28h]; NewState
0x140009a55  add     eax, eax
0x140009a57  mov     [rsp+58h+var_28], 1
0x140009a5f  mov     [rsp+58h+var_1C], eax
0x140009a63  xor     r9d, r9d; BufferLength
0x140009a66  mov     rax, [rcx+8]
0x140009a6a  xor     edx, edx; DisableAllPrivileges
0x140009a6c  mov     rcx, [rcx]; TokenHandle
0x140009a6f  mov     qword ptr [r11-30h], 0
0x140009a77  mov     [r11-24h], rax
0x140009a7b  mov     qword ptr [r11-38h], 0
0x140009a83  call    cs:__imp_AdjustTokenPrivileges
0x140009a89  test    eax, eax
0x140009a8b  jz      short loc_140009A9B
0x140009a8d  call    cs:__imp_GetLastError
0x140009a93  cmp     eax, 514h
0x140009a98  setnz   al
0x140009a9b  mov     rcx, [rsp+58h+var_18]
0x140009aa0  xor     rcx, rsp; StackCookie
0x140009aa3  call    __security_check_cookie
0x140009aa8  add     rsp, 58h
0x140009aac  retn
```
