# _CheckAdmin(void *)

- ea: `0x18006b04c`
- end: `0x18006b15e`
- name: `?_CheckAdmin@@YAJPEAX@Z`
- size: `274`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18006b46c`

## callees

- `0x18006a608`
- `0x18006b04c`
- `0x1800772c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006b093`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006b0fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006b093`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006b0fc`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18006b089`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18006b089`
- `ADVAPI32!CheckTokenMembership` at `0x18006b0f2`
- `ADVAPI32!CheckTokenMembership` at `0x18006b0f2`

## string_xrefs

- `0x18006b0c8`: `onecore\ds\security\eas\policyengine\common.cpp`
- `0x18006b0b4`: `CreateWellKnownSid`

## pseudocode

```c
__int64 __fastcall _CheckAdmin(HANDLE TokenHandle)
{
  signed int v2; // eax
  unsigned int v3; // ebx
  signed int LastError; // eax
  int v6; // [rsp+20h] [rbp-98h]
  int v7; // [rsp+20h] [rbp-98h]
  WINBOOL IsMember; // [rsp+40h] [rbp-78h] BYREF
  DWORD cbSid[3]; // [rsp+44h] [rbp-74h] BYREF
  _BYTE pSid[80]; // [rsp+50h] [rbp-68h] BYREF

  IsMember = 0;
  cbSid[0] = 68;
  if ( CreateWellKnownSid(WinBuiltinAdministratorsSid, 0, pSid, cbSid) )
  {
    if ( CheckTokenMembership(TokenHandle, pSid, &IsMember) )
    {
      return IsMember == 0 ? 0xC0000022 : 0;
    }
    else
    {
      LastError = GetLastError();
      v3 = LastError;
      if ( LastError > 0 )
        v3 = (unsigned __int16)LastError | 0xC0070000;
      v7 = 888;
      DbgPrintfW(
        1u,
        L"(0x%08x) %ws:%u : %ws:%ws\n",
        v3,
        L"onecore\\ds\\security\\eas\\policyengine\\common.cpp",
        v7,
        "_CheckAdmin",
        &Class);
    }
  }
  else
  {
    v2 = GetLastError();
    v3 = v2;
    if ( v2 > 0 )
      v3 = (unsigned __int16)v2 | 0xC0070000;
    v6 = 877;
    DbgPrintfW(
      1u,
      L"(0x%08x) %ws:%u : %ws:%ws\n",
      v3,
      L"onecore\\ds\\security\\eas\\policyengine\\common.cpp",
      v6,
      L"CreateWellKnownSid",
      &Class);
  }
  return v3;
}

```

## disassembly

```asm
0x18006b04c  push    rbx
0x18006b04e  sub     rsp, 0B0h
0x18006b055  mov     rax, cs:__security_cookie
0x18006b05c  xor     rax, rsp
0x18006b05f  mov     [rsp+0B8h+var_18], rax
0x18006b067  xor     edx, edx; DomainSid
0x18006b069  mov     [rsp+0B8h+IsMember], 0
0x18006b071  mov     rbx, rcx
0x18006b074  mov     [rsp+0B8h+cbSid], 44h ; 'D'
0x18006b07c  lea     r9, [rsp+0B8h+cbSid]; cbSid
0x18006b081  lea     r8, [rsp+0B8h+pSid]; pSid
0x18006b086  lea     ecx, [rdx+1Ah]; WellKnownSidType
0x18006b089  call    cs:__imp_CreateWellKnownSid
0x18006b08f  test    eax, eax
0x18006b091  jnz     short loc_18006B0E5
0x18006b093  call    cs:__imp_GetLastError
0x18006b099  mov     ebx, eax
0x18006b09b  test    eax, eax
0x18006b09d  jle     short loc_18006B0A8
0x18006b09f  movzx   ebx, ax
0x18006b0a2  or      ebx, 0C0070000h
0x18006b0a8  lea     rax, Class
0x18006b0af  mov     [rsp+0B8h+var_88], rax
0x18006b0b4  lea     rax, aCreatewellknow; "CreateWellKnownSid"
0x18006b0bb  mov     [rsp+0B8h+var_90], rax
0x18006b0c0  mov     [rsp+0B8h+var_98], 36Dh
0x18006b0c8  lea     r9, aOnecoreDsSecur_0; "onecore\\ds\\security\\eas\\policyengin"...
0x18006b0cf  mov     r8d, ebx
0x18006b0d2  lea     rdx, a0x08xWsUWsWs; "(0x%08x) %ws:%u : %ws:%ws\n"
0x18006b0d9  mov     ecx, 1; unsigned int
0x18006b0de  call    ?DbgPrintfW@@YAXKPEBGZZ; DbgPrintfW(ulong,ushort const *,...)
0x18006b0e3  jmp     short loc_18006B143
0x18006b0e5  lea     r8, [rsp+0B8h+IsMember]; IsMember
0x18006b0ea  mov     rcx, rbx; TokenHandle
0x18006b0ed  lea     rdx, [rsp+0B8h+pSid]; SidToCheck
0x18006b0f2  call    cs:__imp_CheckTokenMembership
0x18006b0f8  test    eax, eax
0x18006b0fa  jnz     short loc_18006B133
0x18006b0fc  call    cs:__imp_GetLastError
0x18006b102  mov     ebx, eax
0x18006b104  test    eax, eax
0x18006b106  jle     short loc_18006B111
0x18006b108  movzx   ebx, ax
0x18006b10b  or      ebx, 0C0070000h
0x18006b111  lea     rax, Class
0x18006b118  mov     [rsp+0B8h+var_88], rax
0x18006b11d  lea     rax, aCheckadmin; "_CheckAdmin"
0x18006b124  mov     [rsp+0B8h+var_90], rax
0x18006b129  mov     [rsp+0B8h+var_98], 378h
0x18006b131  jmp     short loc_18006B0C8
0x18006b133  mov     eax, [rsp+0B8h+IsMember]
0x18006b137  neg     eax
0x18006b139  sbb     ebx, ebx
0x18006b13b  not     ebx
0x18006b13d  and     ebx, 0C0000022h
0x18006b143  mov     eax, ebx
0x18006b145  mov     rcx, [rsp+0B8h+var_18]
0x18006b14d  xor     rcx, rsp; StackCookie
0x18006b150  call    __security_check_cookie
0x18006b155  add     rsp, 0B0h
0x18006b15c  pop     rbx
0x18006b15d  retn
```
