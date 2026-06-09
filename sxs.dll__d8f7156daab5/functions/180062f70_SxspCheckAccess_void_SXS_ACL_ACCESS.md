# SxspCheckAccess(void *,SXS_ACL_ACCESS *)

- ea: `0x180062f70`
- end: `0x18006306e`
- name: `?SxspCheckAccess@@YAJPEAXPEAUSXS_ACL_ACCESS@@@Z`
- size: `254`
- prototype: `__int64 __fastcall(void *, struct SXS_ACL_ACCESS *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180063074`

## callees

- `0x180062f70`
- `0x18006a110`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180062ffd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180062ffd`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180062fed`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180062fed`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180063026`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180063026`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180063049`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180063049`

## pseudocode

```c
__int64 __fastcall SxspCheckAccess(void *a1, struct SXS_ACL_ACCESS *a2)
{
  bool v2; // zf
  unsigned int v3; // ebx
  signed int LastError; // eax
  PSID SidToCheck; // [rsp+60h] [rbp-28h] BYREF
  WINBOOL IsMember; // [rsp+68h] [rbp-20h] BYREF

  v2 = *((_QWORD *)a2 + 1) == 0;
  SidToCheck = 0;
  IsMember = 0;
  if ( v2 )
  {
    if ( AllocateAndInitializeSid(
           (PSID_IDENTIFIER_AUTHORITY)((char *)a2 + 16),
           *((_BYTE *)a2 + 22),
           *((_DWORD *)a2 + 6),
           *((_DWORD *)a2 + 7),
           *((_DWORD *)a2 + 8),
           *((_DWORD *)a2 + 9),
           *((_DWORD *)a2 + 10),
           *((_DWORD *)a2 + 11),
           *((_DWORD *)a2 + 12),
           *((_DWORD *)a2 + 13),
           &SidToCheck)
      && CheckTokenMembership(0, SidToCheck, &IsMember) )
    {
      v3 = IsMember == 0;
    }
    else
    {
      LastError = GetLastError();
      v3 = LastError;
      if ( LastError > 0 )
        v3 = (unsigned __int16)LastError | 0x80070000;
    }
    if ( SidToCheck )
      FreeSid(SidToCheck);
  }
  else
  {
    return (unsigned int)-2147467263;
  }
  return v3;
}

```

## disassembly

```asm
0x180062f70  push    rbx
0x180062f72  sub     rsp, 80h
0x180062f79  mov     rax, cs:__security_cookie
0x180062f80  xor     rax, rsp
0x180062f83  mov     [rsp+88h+var_18], rax
0x180062f88  cmp     qword ptr [rdx+8], 0
0x180062f8d  mov     [rsp+88h+SidToCheck], 0
0x180062f96  mov     [rsp+88h+IsMember], 0
0x180062f9e  jz      short loc_180062FAA
0x180062fa0  mov     ebx, 80004001h
0x180062fa5  jmp     loc_180063055
0x180062faa  mov     r9d, [rdx+1Ch]; nSubAuthority1
0x180062fae  lea     rax, [rsp+88h+SidToCheck]
0x180062fb3  mov     r8d, [rdx+18h]; nSubAuthority0
0x180062fb7  lea     rcx, [rdx+10h]; pIdentifierAuthority
0x180062fbb  mov     [rsp+88h+pSid], rax; pSid
0x180062fc0  mov     eax, [rdx+34h]
0x180062fc3  mov     [rsp+88h+nSubAuthority7], eax; nSubAuthority7
0x180062fc7  mov     eax, [rdx+30h]
0x180062fca  mov     [rsp+88h+nSubAuthority6], eax; nSubAuthority6
0x180062fce  mov     eax, [rdx+2Ch]
0x180062fd1  mov     [rsp+88h+nSubAuthority5], eax; nSubAuthority5
0x180062fd5  mov     eax, [rdx+28h]
0x180062fd8  mov     [rsp+88h+nSubAuthority4], eax; nSubAuthority4
0x180062fdc  mov     eax, [rdx+24h]
0x180062fdf  mov     [rsp+88h+nSubAuthority3], eax; nSubAuthority3
0x180062fe3  mov     eax, [rdx+20h]
0x180062fe6  mov     dl, [rdx+16h]; nSubAuthorityCount
0x180062fe9  mov     [rsp+88h+nSubAuthority2], eax; nSubAuthority2
0x180062fed  call    cs:__imp_AllocateAndInitializeSid
0x180062ff4  nop     dword ptr [rax+rax+00h]
0x180062ff9  test    eax, eax
0x180062ffb  jnz     short loc_18006301A
0x180062ffd  call    cs:__imp_GetLastError
0x180063004  nop     dword ptr [rax+rax+00h]
0x180063009  mov     ebx, eax
0x18006300b  test    eax, eax
0x18006300d  jle     short loc_18006303F
0x18006300f  movzx   ebx, ax
0x180063012  or      ebx, 80070000h
0x180063018  jmp     short loc_18006303F
0x18006301a  mov     rdx, [rsp+88h+SidToCheck]; SidToCheck
0x18006301f  lea     r8, [rsp+88h+IsMember]; IsMember
0x180063024  xor     ecx, ecx; TokenHandle
0x180063026  call    cs:__imp_CheckTokenMembership
0x18006302d  nop     dword ptr [rax+rax+00h]
0x180063032  test    eax, eax
0x180063034  jz      short loc_180062FFD
0x180063036  xor     ebx, ebx
0x180063038  cmp     [rsp+88h+IsMember], ebx
0x18006303c  setz    bl
0x18006303f  mov     rcx, [rsp+88h+SidToCheck]; pSid
0x180063044  test    rcx, rcx
0x180063047  jz      short loc_180063055
0x180063049  call    cs:__imp_FreeSid
0x180063050  nop     dword ptr [rax+rax+00h]
0x180063055  mov     eax, ebx
0x180063057  mov     rcx, [rsp+88h+var_18]
0x18006305c  xor     rcx, rsp; StackCookie
0x18006305f  call    __security_check_cookie
0x180063064  add     rsp, 80h
0x18006306b  pop     rbx
0x18006306c  retn
```
