# SdpIsSystem(int *)

- ea: `0x140005eb8`
- end: `0x140005fe6`
- name: `?SdpIsSystem@@YAJPEAH@Z`
- size: `302`
- prototype: `__int64 __fastcall(int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x1400055d8`

## callees

- `0x140005964`
- `0x140005eb8`
- `0x140007770`

## import_xrefs

- `ADVAPI32!AllocateAndInitializeSid` at `0x140005f3e`
- `ADVAPI32!AllocateAndInitializeSid` at `0x140005f3e`
- `ADVAPI32!FreeSid` at `0x140005fa2`
- `ADVAPI32!FreeSid` at `0x140005fa2`
- `ADVAPI32!CheckTokenMembership` at `0x140005f88`
- `ADVAPI32!CheckTokenMembership` at `0x140005f88`
- `KERNEL32!GetLastError` at `0x140005f48`
- `KERNEL32!GetLastError` at `0x140005fc2`
- `KERNEL32!GetLastError` at `0x140005f48`
- `KERNEL32!GetLastError` at `0x140005fc2`

## pseudocode

```c
__int64 __fastcall SdpIsSystem(int *a1)
{
  signed int v2; // ebx
  int v3; // r8d
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
    SdpDebugTrace((unsigned int)a1, L"SdpIsSystem", v3, v2);
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
0x140005eb8  push    rbp
0x140005eba  push    rbx
0x140005ebb  push    rsi
0x140005ebc  push    rdi
0x140005ebd  lea     rbp, [rsp-3Fh]
0x140005ec2  sub     rsp, 88h
0x140005ec9  mov     rax, cs:__security_cookie
0x140005ed0  xor     rax, rsp
0x140005ed3  mov     [rbp+57h+var_28], rax
0x140005ed7  xor     esi, esi
0x140005ed9  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x140005edf  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], esi
0x140005ee2  mov     rdi, rcx
0x140005ee5  mov     [rbp+57h+SidToCheck], rsi
0x140005ee9  mov     [rbp+57h+IsMember], esi
0x140005eec  test    rcx, rcx
0x140005eef  jnz     short loc_140005F10
0x140005ef1  mov     ebx, 80070057h
0x140005ef6  mov     r8d, 8A4h; int
0x140005efc  mov     r9d, ebx; int
0x140005eff  lea     rdx, aSdpissystem; "SdpIsSystem"
0x140005f06  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x140005f0b  jmp     loc_140005F99
0x140005f10  lea     rax, [rbp+57h+SidToCheck]
0x140005f14  xor     r9d, r9d; nSubAuthority1
0x140005f17  mov     [rsp+0A0h+pSid], rax; pSid
0x140005f1c  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x140005f20  mov     [rsp+0A0h+nSubAuthority7], esi; nSubAuthority7
0x140005f24  mov     dl, 1; nSubAuthorityCount
0x140005f26  mov     [rsp+0A0h+nSubAuthority6], esi; nSubAuthority6
0x140005f2a  mov     [rsp+0A0h+nSubAuthority5], esi; nSubAuthority5
0x140005f2e  lea     r8d, [r9+12h]; nSubAuthority0
0x140005f32  mov     [rsp+0A0h+nSubAuthority4], esi; nSubAuthority4
0x140005f36  mov     [rsp+0A0h+nSubAuthority3], esi; nSubAuthority3
0x140005f3a  mov     [rsp+0A0h+nSubAuthority2], esi; nSubAuthority2
0x140005f3e  call    cs:__imp_AllocateAndInitializeSid
0x140005f44  test    eax, eax
0x140005f46  jnz     short loc_140005F69
0x140005f48  call    cs:__imp_GetLastError
0x140005f4e  mov     ebx, eax
0x140005f50  test    eax, eax
0x140005f52  jle     short loc_140005F5D
0x140005f54  movzx   ebx, ax
0x140005f57  or      ebx, 80070000h
0x140005f5d  test    ebx, ebx
0x140005f5f  jns     short loc_140005F69
0x140005f61  mov     r8d, 8B1h
0x140005f67  jmp     short loc_140005EFC
0x140005f69  mov     rdx, [rbp+57h+SidToCheck]; SidToCheck
0x140005f6d  test    rdx, rdx
0x140005f70  jnz     short loc_140005F82
0x140005f72  mov     ebx, 8007000Eh
0x140005f77  mov     r8d, 8B2h
0x140005f7d  jmp     loc_140005EFC
0x140005f82  lea     r8, [rbp+57h+IsMember]; IsMember
0x140005f86  xor     ecx, ecx; TokenHandle
0x140005f88  call    cs:__imp_CheckTokenMembership
0x140005f8e  test    eax, eax
0x140005f90  jz      short loc_140005FC2
0x140005f92  mov     ebx, esi
0x140005f94  mov     ecx, [rbp+57h+IsMember]
0x140005f97  mov     [rdi], ecx
0x140005f99  mov     rcx, [rbp+57h+SidToCheck]; pSid
0x140005f9d  test    rcx, rcx
0x140005fa0  jz      short loc_140005FA8
0x140005fa2  call    cs:__imp_FreeSid
0x140005fa8  mov     eax, ebx
0x140005faa  mov     rcx, [rbp+57h+var_28]
0x140005fae  xor     rcx, rsp; StackCookie
0x140005fb1  call    __security_check_cookie
0x140005fb6  add     rsp, 88h
0x140005fbd  pop     rdi
0x140005fbe  pop     rsi
0x140005fbf  pop     rbx
0x140005fc0  pop     rbp
0x140005fc1  retn
0x140005fc2  call    cs:__imp_GetLastError
0x140005fc8  mov     ebx, eax
0x140005fca  test    eax, eax
0x140005fcc  jle     short loc_140005FD7
0x140005fce  movzx   ebx, ax
0x140005fd1  or      ebx, 80070000h
0x140005fd7  test    ebx, ebx
0x140005fd9  jns     short loc_140005F94
0x140005fdb  mov     r8d, 8BAh
0x140005fe1  jmp     loc_140005EFC
```
