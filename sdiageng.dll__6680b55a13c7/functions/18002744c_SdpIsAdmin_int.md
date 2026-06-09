# SdpIsAdmin(int *)

- ea: `0x18002744c`
- end: `0x180027584`
- name: `?SdpIsAdmin@@YAJPEAH@Z`
- size: `312`
- prototype: `__int64 __fastcall(int *)`
- caller_count: `4`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x18000c3fc`
- `0x18001e194`
- `0x180020fc0`
- `0x180026bf4`

## callees

- `0x180026fa0`
- `0x18002744c`
- `0x1800298c0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800274e6`
- `KERNEL32!GetLastError` at `0x180027560`
- `KERNEL32!GetLastError` at `0x1800274e6`
- `KERNEL32!GetLastError` at `0x180027560`
- `ADVAPI32!AllocateAndInitializeSid` at `0x1800274dc`
- `ADVAPI32!AllocateAndInitializeSid` at `0x1800274dc`
- `ADVAPI32!FreeSid` at `0x180027540`
- `ADVAPI32!FreeSid` at `0x180027540`
- `ADVAPI32!CheckTokenMembership` at `0x180027526`
- `ADVAPI32!CheckTokenMembership` at `0x180027526`

## pseudocode

```c
__int64 __fastcall SdpIsAdmin(int *a1)
{
  signed int v2; // ebx
  unsigned int v3; // r8d
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
    SdpDebugTrace(1u, L"SdpIsAdmin", v3, v2);
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
0x18002744c  push    rbp
0x18002744e  push    rbx
0x18002744f  push    rsi
0x180027450  push    rdi
0x180027451  lea     rbp, [rsp-3Fh]
0x180027456  sub     rsp, 88h
0x18002745d  mov     rax, cs:__security_cookie
0x180027464  xor     rax, rsp
0x180027467  mov     [rbp+57h+var_28], rax
0x18002746b  xor     esi, esi
0x18002746d  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x180027473  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], esi
0x180027476  mov     rdi, rcx
0x180027479  mov     [rbp+57h+SidToCheck], rsi
0x18002747d  mov     [rbp+57h+IsMember], esi
0x180027480  test    rcx, rcx
0x180027483  jnz     short loc_1800274A9
0x180027485  mov     ebx, 80070057h
0x18002748a  mov     r8d, 861h; int
0x180027490  mov     r9d, ebx; int
0x180027493  lea     rdx, aSdpisadmin; "SdpIsAdmin"
0x18002749a  mov     ecx, 1; Level
0x18002749f  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x1800274a4  jmp     loc_180027537
0x1800274a9  lea     rax, [rbp+57h+SidToCheck]
0x1800274ad  mov     r9d, 220h; nSubAuthority1
0x1800274b3  mov     [rsp+0A0h+pSid], rax; pSid
0x1800274b8  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x1800274bc  mov     [rsp+0A0h+nSubAuthority7], esi; nSubAuthority7
0x1800274c0  mov     r8d, 20h ; ' '; nSubAuthority0
0x1800274c6  mov     [rsp+0A0h+nSubAuthority6], esi; nSubAuthority6
0x1800274ca  mov     dl, 2; nSubAuthorityCount
0x1800274cc  mov     [rsp+0A0h+nSubAuthority5], esi; nSubAuthority5
0x1800274d0  mov     [rsp+0A0h+nSubAuthority4], esi; nSubAuthority4
0x1800274d4  mov     [rsp+0A0h+nSubAuthority3], esi; nSubAuthority3
0x1800274d8  mov     [rsp+0A0h+nSubAuthority2], esi; nSubAuthority2
0x1800274dc  call    cs:__imp_AllocateAndInitializeSid
0x1800274e2  test    eax, eax
0x1800274e4  jnz     short loc_180027507
0x1800274e6  call    cs:__imp_GetLastError
0x1800274ec  mov     ebx, eax
0x1800274ee  test    eax, eax
0x1800274f0  jle     short loc_1800274FB
0x1800274f2  movzx   ebx, ax
0x1800274f5  or      ebx, 80070000h
0x1800274fb  test    ebx, ebx
0x1800274fd  jns     short loc_180027507
0x1800274ff  mov     r8d, 86Eh
0x180027505  jmp     short loc_180027490
0x180027507  mov     rdx, [rbp+57h+SidToCheck]; SidToCheck
0x18002750b  test    rdx, rdx
0x18002750e  jnz     short loc_180027520
0x180027510  mov     ebx, 8007000Eh
0x180027515  mov     r8d, 86Fh
0x18002751b  jmp     loc_180027490
0x180027520  lea     r8, [rbp+57h+IsMember]; IsMember
0x180027524  xor     ecx, ecx; TokenHandle
0x180027526  call    cs:__imp_CheckTokenMembership
0x18002752c  test    eax, eax
0x18002752e  jz      short loc_180027560
0x180027530  mov     ebx, esi
0x180027532  mov     ecx, [rbp+57h+IsMember]
0x180027535  mov     [rdi], ecx
0x180027537  mov     rcx, [rbp+57h+SidToCheck]; pSid
0x18002753b  test    rcx, rcx
0x18002753e  jz      short loc_180027546
0x180027540  call    cs:__imp_FreeSid
0x180027546  mov     eax, ebx
0x180027548  mov     rcx, [rbp+57h+var_28]
0x18002754c  xor     rcx, rsp; StackCookie
0x18002754f  call    __security_check_cookie
0x180027554  add     rsp, 88h
0x18002755b  pop     rdi
0x18002755c  pop     rsi
0x18002755d  pop     rbx
0x18002755e  pop     rbp
0x18002755f  retn
0x180027560  call    cs:__imp_GetLastError
0x180027566  mov     ebx, eax
0x180027568  test    eax, eax
0x18002756a  jle     short loc_180027575
0x18002756c  movzx   ebx, ax
0x18002756f  or      ebx, 80070000h
0x180027575  test    ebx, ebx
0x180027577  jns     short loc_180027532
0x180027579  mov     r8d, 877h
0x18002757f  jmp     loc_180027490
```
