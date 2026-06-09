# SdpIsSystem(int *)

- ea: `0x18002778c`
- end: `0x1800278cb`
- name: `?SdpIsSystem@@YAJPEAH@Z`
- size: `319`
- prototype: `__int64 __fastcall(int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x180026bf4`

## callees

- `0x180026fa0`
- `0x18002778c`
- `0x1800298c0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18002782b`
- `KERNEL32!GetLastError` at `0x1800278a7`
- `KERNEL32!GetLastError` at `0x18002782b`
- `KERNEL32!GetLastError` at `0x1800278a7`
- `ADVAPI32!AllocateAndInitializeSid` at `0x180027821`
- `ADVAPI32!AllocateAndInitializeSid` at `0x180027821`
- `ADVAPI32!FreeSid` at `0x180027886`
- `ADVAPI32!FreeSid` at `0x180027886`
- `ADVAPI32!CheckTokenMembership` at `0x18002786b`
- `ADVAPI32!CheckTokenMembership` at `0x18002786b`

## pseudocode

```c
__int64 __fastcall SdpIsSystem(int *a1)
{
  signed int v2; // ebx
  unsigned int v3; // r8d
  signed int LastError; // eax
  signed int v6; // eax
  WINBOOL IsMember; // [rsp+60h] [rbp+17h] BYREF
  PSID SidToCheck; // [rsp+68h] [rbp+1Fh] BYREF
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+70h] [rbp+27h] BYREF

  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  SidToCheck = 0;
  IsMember = 0;
  if ( !a1 )
  {
    v2 = -2147024809;
    v3 = 2212;
LABEL_3:
    SdpDebugTrace(1u, L"SdpIsSystem", v3, v2);
    goto LABEL_14;
  }
  if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, &SidToCheck) )
  {
    LastError = GetLastError();
    v2 = LastError;
    if ( LastError > 0 )
      v2 = (unsigned __int16)LastError | 0x80070000;
    if ( v2 < 0 )
    {
      v3 = 2225;
      goto LABEL_3;
    }
  }
  if ( !SidToCheck )
  {
    v2 = -2147024882;
    v3 = 2226;
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
      v3 = 2234;
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
0x18002778c  push    rbp
0x18002778e  push    rbx
0x18002778f  push    rsi
0x180027790  push    r14
0x180027792  lea     rbp, [rsp-3Fh]
0x180027797  sub     rsp, 88h
0x18002779e  mov     rax, cs:__security_cookie
0x1800277a5  xor     rax, rsp
0x1800277a8  mov     [rbp+57h+var_28], rax
0x1800277ac  xor     r14d, r14d
0x1800277af  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x1800277b5  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], r14d
0x1800277b9  mov     rsi, rcx
0x1800277bc  mov     [rbp+57h+SidToCheck], r14
0x1800277c0  mov     [rbp+57h+IsMember], r14d
0x1800277c4  test    rcx, rcx
0x1800277c7  jnz     short loc_1800277ED
0x1800277c9  mov     ebx, 80070057h
0x1800277ce  mov     r8d, 8A4h; int
0x1800277d4  mov     r9d, ebx; int
0x1800277d7  lea     rdx, aSdpissystem; "SdpIsSystem"
0x1800277de  mov     ecx, 1; Level
0x1800277e3  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x1800277e8  jmp     loc_18002787D
0x1800277ed  lea     rax, [rbp+57h+SidToCheck]
0x1800277f1  xor     r9d, r9d; nSubAuthority1
0x1800277f4  mov     [rsp+0A0h+pSid], rax; pSid
0x1800277f9  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x1800277fd  mov     [rsp+0A0h+nSubAuthority7], r14d; nSubAuthority7
0x180027802  mov     dl, 1; nSubAuthorityCount
0x180027804  mov     [rsp+0A0h+nSubAuthority6], r14d; nSubAuthority6
0x180027809  mov     [rsp+0A0h+nSubAuthority5], r14d; nSubAuthority5
0x18002780e  lea     r8d, [r9+12h]; nSubAuthority0
0x180027812  mov     [rsp+0A0h+nSubAuthority4], r14d; nSubAuthority4
0x180027817  mov     [rsp+0A0h+nSubAuthority3], r14d; nSubAuthority3
0x18002781c  mov     [rsp+0A0h+nSubAuthority2], r14d; nSubAuthority2
0x180027821  call    cs:__imp_AllocateAndInitializeSid
0x180027827  test    eax, eax
0x180027829  jnz     short loc_18002784C
0x18002782b  call    cs:__imp_GetLastError
0x180027831  mov     ebx, eax
0x180027833  test    eax, eax
0x180027835  jle     short loc_180027840
0x180027837  movzx   ebx, ax
0x18002783a  or      ebx, 80070000h
0x180027840  test    ebx, ebx
0x180027842  jns     short loc_18002784C
0x180027844  mov     r8d, 8B1h
0x18002784a  jmp     short loc_1800277D4
0x18002784c  mov     rdx, [rbp+57h+SidToCheck]; SidToCheck
0x180027850  test    rdx, rdx
0x180027853  jnz     short loc_180027865
0x180027855  mov     ebx, 8007000Eh
0x18002785a  mov     r8d, 8B2h
0x180027860  jmp     loc_1800277D4
0x180027865  lea     r8, [rbp+57h+IsMember]; IsMember
0x180027869  xor     ecx, ecx; TokenHandle
0x18002786b  call    cs:__imp_CheckTokenMembership
0x180027871  test    eax, eax
0x180027873  jz      short loc_1800278A7
0x180027875  mov     ebx, r14d
0x180027878  mov     ecx, [rbp+57h+IsMember]
0x18002787b  mov     [rsi], ecx
0x18002787d  mov     rcx, [rbp+57h+SidToCheck]; pSid
0x180027881  test    rcx, rcx
0x180027884  jz      short loc_18002788C
0x180027886  call    cs:__imp_FreeSid
0x18002788c  mov     eax, ebx
0x18002788e  mov     rcx, [rbp+57h+var_28]
0x180027892  xor     rcx, rsp; StackCookie
0x180027895  call    __security_check_cookie
0x18002789a  add     rsp, 88h
0x1800278a1  pop     r14
0x1800278a3  pop     rsi
0x1800278a4  pop     rbx
0x1800278a5  pop     rbp
0x1800278a6  retn
0x1800278a7  call    cs:__imp_GetLastError
0x1800278ad  mov     ebx, eax
0x1800278af  test    eax, eax
0x1800278b1  jle     short loc_1800278BC
0x1800278b3  movzx   ebx, ax
0x1800278b6  or      ebx, 80070000h
0x1800278bc  test    ebx, ebx
0x1800278be  jns     short loc_180027878
0x1800278c0  mov     r8d, 8BAh
0x1800278c6  jmp     loc_1800277D4
```
