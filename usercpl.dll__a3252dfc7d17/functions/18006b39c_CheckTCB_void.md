# _CheckTCB(void *)

- ea: `0x18006b39c`
- end: `0x18006b464`
- name: `?_CheckTCB@@YAJPEAX@Z`
- size: `200`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18006b46c`

## callees

- `0x18006a608`
- `0x18006b39c`
- `0x1800772c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006b3df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006b3e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006b3f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006b3df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006b3e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006b3f3`
- `ADVAPI32!PrivilegeCheck` at `0x18006b3d5`
- `ADVAPI32!PrivilegeCheck` at `0x18006b3d5`

## string_xrefs

- `0x18006b411`: `onecore\ds\security\eas\policyengine\common.cpp`
- `0x18006b418`: `PrivilegeCheck`

## pseudocode

```c
__int64 __fastcall _CheckTCB(void *a1)
{
  unsigned int LastError; // ebx
  int v3; // [rsp+20h] [rbp-58h]
  WINBOOL v4; // [rsp+40h] [rbp-38h] BYREF
  struct _PRIVILEGE_SET v5; // [rsp+48h] [rbp-30h] BYREF

  *(_QWORD *)&v5.PrivilegeCount = 1;
  v5.Privilege[0].Luid = (LUID)7LL;
  v4 = 0;
  v5.Privilege[0].Attributes = 0;
  if ( PrivilegeCheck(a1, &v5, &v4) )
  {
    return v4 == 0 ? 0xC0000022 : 0;
  }
  else
  {
    if ( (int)GetLastError() > 0 )
      LastError = (unsigned __int16)GetLastError() | 0xC0070000;
    else
      LastError = GetLastError();
    v3 = 840;
    DbgPrintfW(
      1u,
      L"(0x%08x) %ws:%u : %ws:%ws\n",
      LastError,
      L"onecore\\ds\\security\\eas\\policyengine\\common.cpp",
      v3,
      L"PrivilegeCheck",
      &Class);
  }
  return LastError;
}

```

## disassembly

```asm
0x18006b39c  mov     r11, rsp
0x18006b39f  push    rbx
0x18006b3a0  sub     rsp, 70h
0x18006b3a4  mov     rax, cs:__security_cookie
0x18006b3ab  xor     rax, rsp
0x18006b3ae  mov     [rsp+78h+var_18], rax
0x18006b3b3  xor     ebx, ebx
0x18006b3b5  mov     qword ptr [r11-30h], 1
0x18006b3bd  mov     qword ptr [r11-28h], 7
0x18006b3c5  lea     r8, [r11-38h]; pfResult
0x18006b3c9  lea     rdx, [r11-30h]; RequiredPrivileges
0x18006b3cd  mov     [rsp+78h+var_38], ebx
0x18006b3d1  mov     [rsp+78h+var_20], ebx
0x18006b3d5  call    cs:__imp_PrivilegeCheck
0x18006b3db  test    eax, eax
0x18006b3dd  jnz     short loc_18006B43F
0x18006b3df  call    cs:__imp_GetLastError
0x18006b3e5  test    eax, eax
0x18006b3e7  jg      short loc_18006B3F3
0x18006b3e9  call    cs:__imp_GetLastError
0x18006b3ef  mov     ebx, eax
0x18006b3f1  jmp     short loc_18006B402
0x18006b3f3  call    cs:__imp_GetLastError
0x18006b3f9  movzx   ebx, ax
0x18006b3fc  or      ebx, 0C0070000h
0x18006b402  lea     rax, Class
0x18006b409  mov     r8d, ebx
0x18006b40c  mov     [rsp+78h+var_48], rax
0x18006b411  lea     r9, aOnecoreDsSecur_0; "onecore\\ds\\security\\eas\\policyengin"...
0x18006b418  lea     rax, aPrivilegecheck; "PrivilegeCheck"
0x18006b41f  mov     ecx, 1; unsigned int
0x18006b424  mov     [rsp+78h+var_50], rax
0x18006b429  lea     rdx, a0x08xWsUWsWs; "(0x%08x) %ws:%u : %ws:%ws\n"
0x18006b430  mov     [rsp+78h+var_58], 348h
0x18006b438  call    ?DbgPrintfW@@YAXKPEBGZZ; DbgPrintfW(ulong,ushort const *,...)
0x18006b43d  jmp     short loc_18006B44F
0x18006b43f  mov     eax, [rsp+78h+var_38]
0x18006b443  neg     eax
0x18006b445  sbb     ebx, ebx
0x18006b447  not     ebx
0x18006b449  and     ebx, 0C0000022h
0x18006b44f  mov     eax, ebx
0x18006b451  mov     rcx, [rsp+78h+var_18]
0x18006b456  xor     rcx, rsp; StackCookie
0x18006b459  call    __security_check_cookie
0x18006b45e  add     rsp, 70h
0x18006b462  pop     rbx
0x18006b463  retn
```
