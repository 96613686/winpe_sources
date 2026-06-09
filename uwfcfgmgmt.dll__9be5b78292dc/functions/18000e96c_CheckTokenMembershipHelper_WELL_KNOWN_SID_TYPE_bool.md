# CheckTokenMembershipHelper(WELL_KNOWN_SID_TYPE,bool *)

- ea: `0x18000e96c`
- end: `0x18000ea0d`
- name: `?CheckTokenMembershipHelper@@YAJW4WELL_KNOWN_SID_TYPE@@PEA_N@Z`
- size: `161`
- prototype: `signed int __fastcall(enum WELL_KNOWN_SID_TYPE, bool *)`
- caller_count: `7`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180008170`
- `0x180008300`
- `0x18000bfa0`
- `0x180010580`
- `0x1800139f0`
- `0x180013be0`
- `0x1800163b0`

## callees

- `0x18000e96c`
- `0x18001b020`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e9bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e9bf`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18000e9b5`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18000e9b5`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18000e9df`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18000e9df`

## pseudocode

```c
signed int __fastcall CheckTokenMembershipHelper(enum WELL_KNOWN_SID_TYPE a1, bool *a2)
{
  signed int result; // eax
  WINBOOL IsMember; // [rsp+20h] [rbp-78h] BYREF
  DWORD cbSid[3]; // [rsp+24h] [rbp-74h] BYREF
  _BYTE pSid[80]; // [rsp+30h] [rbp-68h] BYREF

  IsMember = 0;
  cbSid[0] = 68;
  if ( !a2 )
    return -2147467261;
  if ( CreateWellKnownSid(WinBuiltinAdministratorsSid, 0, pSid, cbSid) && CheckTokenMembership(0, pSid, &IsMember) )
  {
    result = 0;
    *a2 = IsMember != 0;
  }
  else
  {
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x18000e96c  push    rbx
0x18000e96e  sub     rsp, 90h
0x18000e975  mov     rax, cs:__security_cookie
0x18000e97c  xor     rax, rsp
0x18000e97f  mov     [rsp+98h+var_18], rax
0x18000e987  mov     [rsp+98h+IsMember], 0
0x18000e98f  mov     rbx, rdx
0x18000e992  mov     [rsp+98h+cbSid], 44h ; 'D'
0x18000e99a  test    rdx, rdx
0x18000e99d  jnz     short loc_18000E9A6
0x18000e99f  mov     eax, 80004003h
0x18000e9a4  jmp     short loc_18000E9F4
0x18000e9a6  xor     edx, edx; DomainSid
0x18000e9a8  lea     r9, [rsp+98h+cbSid]; cbSid
0x18000e9ad  lea     r8, [rsp+98h+pSid]; pSid
0x18000e9b2  lea     ecx, [rdx+1Ah]; WellKnownSidType
0x18000e9b5  call    cs:__imp_CreateWellKnownSid
0x18000e9bb  test    eax, eax
0x18000e9bd  jnz     short loc_18000E9D3
0x18000e9bf  call    cs:__imp_GetLastError
0x18000e9c5  test    eax, eax
0x18000e9c7  jle     short loc_18000E9F4
0x18000e9c9  movzx   eax, ax
0x18000e9cc  or      eax, 80070000h
0x18000e9d1  jmp     short loc_18000E9F4
0x18000e9d3  lea     r8, [rsp+98h+IsMember]; IsMember
0x18000e9d8  xor     ecx, ecx; TokenHandle
0x18000e9da  lea     rdx, [rsp+98h+pSid]; SidToCheck
0x18000e9df  call    cs:__imp_CheckTokenMembership
0x18000e9e5  test    eax, eax
0x18000e9e7  jz      short loc_18000E9BF
0x18000e9e9  xor     eax, eax
0x18000e9eb  cmp     [rsp+98h+IsMember], eax
0x18000e9ef  setnz   cl
0x18000e9f2  mov     [rbx], cl
0x18000e9f4  mov     rcx, [rsp+98h+var_18]
0x18000e9fc  xor     rcx, rsp; StackCookie
0x18000e9ff  call    __security_check_cookie
0x18000ea04  add     rsp, 90h
0x18000ea0b  pop     rbx
0x18000ea0c  retn
```
