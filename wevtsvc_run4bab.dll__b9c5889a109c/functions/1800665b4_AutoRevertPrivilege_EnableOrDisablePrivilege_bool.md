# AutoRevertPrivilege::EnableOrDisablePrivilege(bool)

- ea: `0x1800665b4`
- end: `0x18006662b`
- name: `?EnableOrDisablePrivilege@AutoRevertPrivilege@@AEAA_N_N@Z`
- size: `119`
- prototype: `bool __fastcall(AutoRevertPrivilege *__hidden this, bool)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180017e94`
- `0x180066510`

## callees

- `0x1800665b4`
- `0x18009aee0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006661b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006661b`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x1800665ff`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x1800665ff`

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
0x1800665b4  mov     r11, rsp
0x1800665b7  sub     rsp, 58h
0x1800665bb  mov     rax, cs:__security_cookie
0x1800665c2  xor     rax, rsp
0x1800665c5  mov     [rsp+58h+var_18], rax
0x1800665ca  movzx   eax, dl
0x1800665cd  lea     r8, [r11-28h]; NewState
0x1800665d1  add     eax, eax
0x1800665d3  mov     [rsp+58h+var_28], 1
0x1800665db  mov     [rsp+58h+var_1C], eax
0x1800665df  xor     r9d, r9d; BufferLength
0x1800665e2  mov     rax, [rcx+8]
0x1800665e6  xor     edx, edx; DisableAllPrivileges
0x1800665e8  mov     rcx, [rcx]; TokenHandle
0x1800665eb  mov     qword ptr [r11-30h], 0
0x1800665f3  mov     [r11-24h], rax
0x1800665f7  mov     qword ptr [r11-38h], 0
0x1800665ff  call    cs:__imp_AdjustTokenPrivileges
0x180066605  test    eax, eax
0x180066607  jnz     short loc_18006661B
0x180066609  mov     rcx, [rsp+58h+var_18]
0x18006660e  xor     rcx, rsp; StackCookie
0x180066611  call    __security_check_cookie
0x180066616  add     rsp, 58h
0x18006661a  retn
0x18006661b  call    cs:__imp_GetLastError
0x180066621  cmp     eax, 514h
0x180066626  setnz   al
0x180066629  jmp     short loc_180066609
```
