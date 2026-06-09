# CheckAdminMembershipFromLUAToken

- ea: `0x14008ee4c`
- end: `0x14008ef43`
- name: `CheckAdminMembershipFromLUAToken`
- size: `247`
- prototype: `__int64 __fastcall(HANDLE ExistingTokenHandle)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14009040c`

## callees

- `0x1400057f4`
- `0x1400437c0`
- `0x140053720`
- `0x14008ee4c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14008eef3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14008eef3`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x14008ee93`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x14008ee93`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x14008eec7`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x14008eec7`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x14008eeb1`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x14008eeb1`

## pseudocode

```c
__int64 __fastcall CheckAdminMembershipFromLUAToken(HANDLE ExistingTokenHandle)
{
  DWORD LastError; // eax
  unsigned int v3; // ebx
  WINBOOL IsMember; // [rsp+20h] [rbp-29h] BYREF
  void *DuplicateTokenHandle; // [rsp+28h] [rbp-21h] BYREF
  DWORD cbSid[4]; // [rsp+30h] [rbp-19h] BYREF
  _BYTE pSid[80]; // [rsp+40h] [rbp-9h] BYREF

  IsMember = 0;
  DuplicateTokenHandle = 0;
  CAutoPtr<void *,&void HandleClose(void *)>::Free(&DuplicateTokenHandle);
  if ( DuplicateToken(ExistingTokenHandle, SecurityIdentification, &DuplicateTokenHandle) )
  {
    cbSid[0] = 68;
    if ( CreateWellKnownSid(WinBuiltinAdministratorsSid, 0, pSid, cbSid) )
    {
      if ( !CheckTokenMembership(DuplicateTokenHandle, pSid, &IsMember)
        && WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        LastError = GetLastError();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_8d12472ee3e0397472f1167aeb1d1409_Traceguids, LastError);
      }
    }
  }
  v3 = IsMember;
  CAutoPtr<void *,&void HandleClose(void *)>::Free(&DuplicateTokenHandle);
  return v3;
}

```

## disassembly

```asm
0x14008ee4c  mov     [rsp-8+arg_8], rbx
0x14008ee51  push    rbp
0x14008ee52  lea     rbp, [rsp-57h]
0x14008ee57  sub     rsp, 0A0h
0x14008ee5e  mov     rax, cs:__security_cookie
0x14008ee65  xor     rax, rsp
0x14008ee68  mov     [rbp+57h+var_10], rax
0x14008ee6c  mov     rbx, rcx
0x14008ee6f  mov     [rbp+57h+IsMember], 0
0x14008ee76  lea     rcx, [rbp+57h+DuplicateTokenHandle]
0x14008ee7a  mov     [rbp+57h+DuplicateTokenHandle], 0
0x14008ee82  call    ?Free@?$CAutoPtr@PEAX$1?HandleClose@@YAXPEAX@Z@@AEAAXXZ; CAutoPtr<void *,&HandleClose(void *)>::Free(void)
0x14008ee87  lea     r8, [rbp+57h+DuplicateTokenHandle]; DuplicateTokenHandle
0x14008ee8b  mov     edx, 1; ImpersonationLevel
0x14008ee90  mov     rcx, rbx; ExistingTokenHandle
0x14008ee93  call    cs:__imp_DuplicateToken
0x14008ee99  test    eax, eax
0x14008ee9b  jz      short loc_14008EF18
0x14008ee9d  xor     edx, edx; DomainSid
0x14008ee9f  mov     [rbp+57h+cbSid], 44h ; 'D'
0x14008eea6  lea     r9, [rbp+57h+cbSid]; cbSid
0x14008eeaa  lea     r8, [rbp+57h+pSid]; pSid
0x14008eeae  lea     ecx, [rdx+1Ah]; WellKnownSidType
0x14008eeb1  call    cs:__imp_CreateWellKnownSid
0x14008eeb7  test    eax, eax
0x14008eeb9  jz      short loc_14008EF18
0x14008eebb  mov     rcx, [rbp+57h+DuplicateTokenHandle]; TokenHandle
0x14008eebf  lea     r8, [rbp+57h+IsMember]; IsMember
0x14008eec3  lea     rdx, [rbp+57h+pSid]; SidToCheck
0x14008eec7  call    cs:__imp_CheckTokenMembership
0x14008eecd  test    eax, eax
0x14008eecf  jnz     short loc_14008EF18
0x14008eed1  mov     rax, cs:WPP_GLOBAL_Control
0x14008eed8  lea     rcx, WPP_GLOBAL_Control
0x14008eedf  cmp     rax, rcx
0x14008eee2  jz      short loc_14008EF18
0x14008eee4  test    dword ptr [rax+1Ch], 1000h
0x14008eeeb  jz      short loc_14008EF18
0x14008eeed  cmp     byte ptr [rax+19h], 2
0x14008eef1  jb      short loc_14008EF18
0x14008eef3  call    cs:__imp_GetLastError
0x14008eef9  mov     rcx, cs:WPP_GLOBAL_Control
0x14008ef00  lea     r8, WPP_8d12472ee3e0397472f1167aeb1d1409_Traceguids
0x14008ef07  mov     edx, 11h
0x14008ef0c  mov     r9d, eax
0x14008ef0f  mov     rcx, [rcx+10h]
0x14008ef13  call    WPP_SF_d
0x14008ef18  mov     ebx, [rbp+57h+IsMember]
0x14008ef1b  lea     rcx, [rbp+57h+DuplicateTokenHandle]
0x14008ef1f  call    ?Free@?$CAutoPtr@PEAX$1?HandleClose@@YAXPEAX@Z@@AEAAXXZ; CAutoPtr<void *,&HandleClose(void *)>::Free(void)
0x14008ef24  mov     eax, ebx
0x14008ef26  mov     rcx, [rbp+57h+var_10]
0x14008ef2a  xor     rcx, rsp; StackCookie
0x14008ef2d  call    __security_check_cookie
0x14008ef32  mov     rbx, [rsp+0A0h+arg_8]
0x14008ef3a  add     rsp, 0A0h
0x14008ef41  pop     rbp
0x14008ef42  retn
```
