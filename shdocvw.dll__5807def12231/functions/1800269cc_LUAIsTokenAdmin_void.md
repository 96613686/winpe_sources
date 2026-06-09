# _LUAIsTokenAdmin(void *)

- ea: `0x1800269cc`
- end: `0x180026a67`
- name: `?_LUAIsTokenAdmin@@YAHPEAX@Z`
- size: `155`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180026b58`
- `0x180026c68`

## callees

- `0x180008320`
- `0x1800269cc`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026a45`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026a45`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180026a3a`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180026a3a`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180026a21`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180026a21`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x180026a00`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x180026a00`

## pseudocode

```c
__int64 __fastcall _LUAIsTokenAdmin(void *a1)
{
  WINBOOL IsMember; // [rsp+20h] [rbp-78h] BYREF
  DWORD cbSid; // [rsp+24h] [rbp-74h] BYREF
  void *DuplicateTokenHandle; // [rsp+28h] [rbp-70h] BYREF
  _BYTE pSid[80]; // [rsp+30h] [rbp-68h] BYREF

  IsMember = 0;
  DuplicateTokenHandle = 0;
  if ( DuplicateToken(a1, SecurityIdentification, &DuplicateTokenHandle) )
  {
    cbSid = 68;
    if ( CreateWellKnownSid(WinBuiltinAdministratorsSid, 0, pSid, &cbSid) )
      CheckTokenMembership(DuplicateTokenHandle, pSid, &IsMember);
    CloseHandle(DuplicateTokenHandle);
  }
  return (unsigned int)IsMember;
}

```

## disassembly

```asm
0x1800269cc  sub     rsp, 98h
0x1800269d3  mov     rax, cs:__security_cookie
0x1800269da  xor     rax, rsp
0x1800269dd  mov     [rsp+98h+var_18], rax
0x1800269e5  lea     r8, [rsp+98h+DuplicateTokenHandle]; DuplicateTokenHandle
0x1800269ea  mov     [rsp+98h+IsMember], 0
0x1800269f2  mov     edx, 1; ImpersonationLevel
0x1800269f7  mov     [rsp+98h+DuplicateTokenHandle], 0
0x180026a00  call    cs:__imp_DuplicateToken
0x180026a06  test    eax, eax
0x180026a08  jz      short loc_180026A4B
0x180026a0a  xor     edx, edx; DomainSid
0x180026a0c  mov     [rsp+98h+cbSid], 44h ; 'D'
0x180026a14  lea     r9, [rsp+98h+cbSid]; cbSid
0x180026a19  lea     r8, [rsp+98h+pSid]; pSid
0x180026a1e  lea     ecx, [rdx+1Ah]; WellKnownSidType
0x180026a21  call    cs:__imp_CreateWellKnownSid
0x180026a27  test    eax, eax
0x180026a29  jz      short loc_180026A40
0x180026a2b  mov     rcx, [rsp+98h+DuplicateTokenHandle]; TokenHandle
0x180026a30  lea     r8, [rsp+98h+IsMember]; IsMember
0x180026a35  lea     rdx, [rsp+98h+pSid]; SidToCheck
0x180026a3a  call    cs:__imp_CheckTokenMembership
0x180026a40  mov     rcx, [rsp+98h+DuplicateTokenHandle]; hObject
0x180026a45  call    cs:__imp_CloseHandle
0x180026a4b  mov     eax, [rsp+98h+IsMember]
0x180026a4f  mov     rcx, [rsp+98h+var_18]
0x180026a57  xor     rcx, rsp; StackCookie
0x180026a5a  call    __security_check_cookie
0x180026a5f  add     rsp, 98h
0x180026a66  retn
```
