# SdpIsAdmin(int *)

- ea: `0x140005d7c`
- end: `0x140005eaf`
- name: `?SdpIsAdmin@@YAJPEAH@Z`
- size: `307`
- prototype: `__int64 __fastcall(int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x1400055d8`

## callees

- `0x140005964`
- `0x140005d7c`
- `0x140007770`

## import_xrefs

- `ADVAPI32!AllocateAndInitializeSid` at `0x140005e07`
- `ADVAPI32!AllocateAndInitializeSid` at `0x140005e07`
- `ADVAPI32!FreeSid` at `0x140005e6b`
- `ADVAPI32!FreeSid` at `0x140005e6b`
- `ADVAPI32!CheckTokenMembership` at `0x140005e51`
- `ADVAPI32!CheckTokenMembership` at `0x140005e51`
- `KERNEL32!GetLastError` at `0x140005e11`
- `KERNEL32!GetLastError` at `0x140005e8b`
- `KERNEL32!GetLastError` at `0x140005e11`
- `KERNEL32!GetLastError` at `0x140005e8b`

## pseudocode

```c
__int64 __fastcall SdpIsAdmin(int *a1)
{
  signed int v2; // ebx
  int v3; // r8d
  signed int LastError; // eax
  signed int v6; // eax
  WINBOOL IsMember; // [rsp+60h] [rbp+17h] BYREF
  PSID SidToCheck; // [rsp+68h] [rbp+1Fh] BYREF
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+70h] [rbp+27h] BYREF

  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  SidToCheck = 0;
  IsMember = 0;
  if ( !a1 )
  {
    v2 = -2147024809;
    v3 = 2145;
LABEL_3:
    SdpDebugTrace((unsigned int)a1, L"SdpIsAdmin", v3, v2);
    goto LABEL_14;
  }
  if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, &SidToCheck) )
  {
    LastError = GetLastError();
    v2 = LastError;
    if ( LastError > 0 )
      v2 = (unsigned __int16)LastError | 0x80070000;
    if ( v2 < 0 )
    {
      v3 = 2158;
      goto LABEL_3;
    }
  }
  if ( !SidToCheck )
  {
    v2 = -2147024882;
    v3 = 2159;
    goto LABEL_3;
  }
  if ( CheckTokenMembership(0, SidToCheck, &IsMember) )
  {
    v2 = 0;
  }
  else
  {
    v6 = GetLastError();
    v2 = v6;
    if ( v6 > 0 )
      v2 = (unsigned __int16)v6 | 0x80070000;
    if ( v2 < 0 )
    {
      v3 = 2167;
      goto LABEL_3;
    }
  }
  *a1 = IsMember;
LABEL_14:
  if ( SidToCheck )
    FreeSid(SidToCheck);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x140005d7c  push    rbp
0x140005d7e  push    rbx
0x140005d7f  push    rsi
0x140005d80  push    rdi
0x140005d81  lea     rbp, [rsp-3Fh]
0x140005d86  sub     rsp, 88h
0x140005d8d  mov     rax, cs:__security_cookie
0x140005d94  xor     rax, rsp
0x140005d97  mov     [rbp+57h+var_28], rax
0x140005d9b  xor     esi, esi
0x140005d9d  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x140005da3  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], esi
0x140005da6  mov     rdi, rcx
0x140005da9  mov     [rbp+57h+SidToCheck], rsi
0x140005dad  mov     [rbp+57h+IsMember], esi
0x140005db0  test    rcx, rcx
0x140005db3  jnz     short loc_140005DD4
0x140005db5  mov     ebx, 80070057h
0x140005dba  mov     r8d, 861h; int
0x140005dc0  mov     r9d, ebx; int
0x140005dc3  lea     rdx, aSdpisadmin; "SdpIsAdmin"
0x140005dca  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x140005dcf  jmp     loc_140005E62
0x140005dd4  lea     rax, [rbp+57h+SidToCheck]
0x140005dd8  mov     r9d, 220h; nSubAuthority1
0x140005dde  mov     [rsp+0A0h+pSid], rax; pSid
0x140005de3  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x140005de7  mov     [rsp+0A0h+nSubAuthority7], esi; nSubAuthority7
0x140005deb  mov     r8d, 20h ; ' '; nSubAuthority0
0x140005df1  mov     [rsp+0A0h+nSubAuthority6], esi; nSubAuthority6
0x140005df5  mov     dl, 2; nSubAuthorityCount
0x140005df7  mov     [rsp+0A0h+nSubAuthority5], esi; nSubAuthority5
0x140005dfb  mov     [rsp+0A0h+nSubAuthority4], esi; nSubAuthority4
0x140005dff  mov     [rsp+0A0h+nSubAuthority3], esi; nSubAuthority3
0x140005e03  mov     [rsp+0A0h+nSubAuthority2], esi; nSubAuthority2
0x140005e07  call    cs:__imp_AllocateAndInitializeSid
0x140005e0d  test    eax, eax
0x140005e0f  jnz     short loc_140005E32
0x140005e11  call    cs:__imp_GetLastError
0x140005e17  mov     ebx, eax
0x140005e19  test    eax, eax
0x140005e1b  jle     short loc_140005E26
0x140005e1d  movzx   ebx, ax
0x140005e20  or      ebx, 80070000h
0x140005e26  test    ebx, ebx
0x140005e28  jns     short loc_140005E32
0x140005e2a  mov     r8d, 86Eh
0x140005e30  jmp     short loc_140005DC0
0x140005e32  mov     rdx, [rbp+57h+SidToCheck]; SidToCheck
0x140005e36  test    rdx, rdx
0x140005e39  jnz     short loc_140005E4B
0x140005e3b  mov     ebx, 8007000Eh
0x140005e40  mov     r8d, 86Fh
0x140005e46  jmp     loc_140005DC0
0x140005e4b  lea     r8, [rbp+57h+IsMember]; IsMember
0x140005e4f  xor     ecx, ecx; TokenHandle
0x140005e51  call    cs:__imp_CheckTokenMembership
0x140005e57  test    eax, eax
0x140005e59  jz      short loc_140005E8B
0x140005e5b  mov     ebx, esi
0x140005e5d  mov     ecx, [rbp+57h+IsMember]
0x140005e60  mov     [rdi], ecx
0x140005e62  mov     rcx, [rbp+57h+SidToCheck]; pSid
0x140005e66  test    rcx, rcx
0x140005e69  jz      short loc_140005E71
0x140005e6b  call    cs:__imp_FreeSid
0x140005e71  mov     eax, ebx
0x140005e73  mov     rcx, [rbp+57h+var_28]
0x140005e77  xor     rcx, rsp; StackCookie
0x140005e7a  call    __security_check_cookie
0x140005e7f  add     rsp, 88h
0x140005e86  pop     rdi
0x140005e87  pop     rsi
0x140005e88  pop     rbx
0x140005e89  pop     rbp
0x140005e8a  retn
0x140005e8b  call    cs:__imp_GetLastError
0x140005e91  mov     ebx, eax
0x140005e93  test    eax, eax
0x140005e95  jle     short loc_140005EA0
0x140005e97  movzx   ebx, ax
0x140005e9a  or      ebx, 80070000h
0x140005ea0  test    ebx, ebx
0x140005ea2  jns     short loc_140005E5D
0x140005ea4  mov     r8d, 877h
0x140005eaa  jmp     loc_140005DC0
```
