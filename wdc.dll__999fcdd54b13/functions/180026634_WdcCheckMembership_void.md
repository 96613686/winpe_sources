# WdcCheckMembership(void)

- ea: `0x180026634`
- end: `0x1800267f7`
- name: `?WdcCheckMembership@@YAJXZ`
- size: `451`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x1800663c0`

## callees

- `0x18000b854`
- `0x180026634`
- `0x18003a3c0`

## import_xrefs

- `ADVAPI32!AllocateAndInitializeSid` at `0x18002669a`
- `ADVAPI32!AllocateAndInitializeSid` at `0x18002673a`
- `ADVAPI32!AllocateAndInitializeSid` at `0x18002669a`
- `ADVAPI32!AllocateAndInitializeSid` at `0x18002673a`
- `ADVAPI32!CheckTokenMembership` at `0x1800266d2`
- `ADVAPI32!CheckTokenMembership` at `0x180026765`
- `ADVAPI32!CheckTokenMembership` at `0x1800266d2`
- `ADVAPI32!CheckTokenMembership` at `0x180026765`
- `ADVAPI32!FreeSid` at `0x1800267c8`
- `ADVAPI32!FreeSid` at `0x1800267d7`
- `ADVAPI32!FreeSid` at `0x1800267c8`
- `ADVAPI32!FreeSid` at `0x1800267d7`
- `KERNEL32!GetLastError` at `0x1800266a9`
- `KERNEL32!GetLastError` at `0x1800266dc`
- `KERNEL32!GetLastError` at `0x180026744`
- `KERNEL32!GetLastError` at `0x180026773`
- `KERNEL32!GetLastError` at `0x1800266a9`
- `KERNEL32!GetLastError` at `0x1800266dc`
- `KERNEL32!GetLastError` at `0x180026744`
- `KERNEL32!GetLastError` at `0x180026773`

## pseudocode

```c
__int64 WdcCheckMembership(void)
{
  signed int LastError; // eax
  signed int v1; // ebx
  signed int v2; // eax
  signed int v3; // eax
  signed int v4; // eax
  __int64 nSubAuthority2; // [rsp+20h] [rbp-39h]
  WINBOOL IsMember; // [rsp+60h] [rbp+7h] BYREF
  PSID pSid; // [rsp+68h] [rbp+Fh] BYREF
  PSID SidToCheck; // [rsp+70h] [rbp+17h] BYREF
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+78h] [rbp+1Fh] BYREF

  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  IsMember = 0;
  SidToCheck = 0;
  pSid = 0;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, &SidToCheck) )
  {
    LastError = GetLastError();
    v1 = LastError;
    if ( !LastError )
      goto LABEL_27;
    if ( LastError > 0 )
      v1 = (unsigned __int16)LastError | 0x80070000;
    if ( v1 < 0 )
      goto LABEL_28;
  }
  if ( !CheckTokenMembership(0, SidToCheck, &IsMember) )
  {
    v2 = GetLastError();
    v1 = v2;
    if ( !v2 )
      goto LABEL_27;
    if ( v2 > 0 )
      v1 = (unsigned __int16)v2 | 0x80070000;
    if ( v1 < 0 )
      goto LABEL_28;
  }
  if ( IsMember )
  {
    v1 = 0;
    goto LABEL_29;
  }
  if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, 0x22Fu, 0, 0, 0, 0, 0, 0, &pSid) )
  {
    v3 = GetLastError();
    v1 = v3;
    if ( !v3 )
      goto LABEL_27;
    if ( v3 > 0 )
      v1 = (unsigned __int16)v3 | 0x80070000;
    if ( v1 < 0 )
      goto LABEL_28;
  }
  if ( !CheckTokenMembership(0, pSid, &IsMember) )
  {
    v4 = GetLastError();
    v1 = v4;
    if ( v4 )
    {
      if ( v4 > 0 )
        v1 = (unsigned __int16)v4 | 0x80070000;
      if ( v1 >= 0 )
        goto LABEL_24;
LABEL_28:
      LODWORD(nSubAuthority2) = v1;
      WdcDebugMessage(
        "base\\diagnosis\\pdui\\perfmon\\mmc\\utils.cpp",
        "WdcCheckMembership",
        0,
        L"FAILURE: 0x%08x",
        nSubAuthority2);
      goto LABEL_29;
    }
LABEL_27:
    v1 = -2147467259;
    goto LABEL_28;
  }
  v1 = 0;
LABEL_24:
  if ( !IsMember )
    v1 = 1;
LABEL_29:
  if ( pSid )
    FreeSid(pSid);
  if ( SidToCheck )
    FreeSid(SidToCheck);
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x180026634  push    rbp
0x180026636  push    rbx
0x180026637  push    rsi
0x180026638  push    rdi
0x180026639  lea     rbp, [rsp-3Fh]
0x18002663e  sub     rsp, 98h
0x180026645  mov     rax, cs:__security_cookie
0x18002664c  xor     rax, rsp
0x18002664f  mov     [rbp+57h+var_30], rax
0x180026653  xor     edi, edi
0x180026655  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x18002665b  lea     rax, [rbp+57h+SidToCheck]
0x18002665f  mov     [rbp+57h+IsMember], edi
0x180026662  mov     [rsp+0B0h+pSid], rax; pSid
0x180026667  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x18002666b  mov     [rsp+0B0h+nSubAuthority7], edi; nSubAuthority7
0x18002666f  mov     r9d, 220h; nSubAuthority1
0x180026675  mov     [rsp+0B0h+nSubAuthority6], edi; nSubAuthority6
0x180026679  lea     r8d, [rdi+20h]; nSubAuthority0
0x18002667d  mov     [rsp+0B0h+nSubAuthority5], edi; nSubAuthority5
0x180026681  mov     dl, 2; nSubAuthorityCount
0x180026683  mov     [rsp+0B0h+nSubAuthority4], edi; nSubAuthority4
0x180026687  mov     [rsp+0B0h+nSubAuthority3], edi; nSubAuthority3
0x18002668b  mov     dword ptr [rsp+0B0h+nSubAuthority2], edi; nSubAuthority2
0x18002668f  mov     [rbp+57h+SidToCheck], rdi
0x180026693  mov     [rbp+57h+var_48], rdi
0x180026697  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], edi
0x18002669a  call    cs:__imp_AllocateAndInitializeSid
0x1800266a0  mov     esi, 80070000h
0x1800266a5  test    eax, eax
0x1800266a7  jnz     short loc_1800266C8
0x1800266a9  call    cs:__imp_GetLastError
0x1800266af  mov     ebx, eax
0x1800266b1  test    eax, eax
0x1800266b3  jz      loc_180026797
0x1800266b9  jle     short loc_1800266C0
0x1800266bb  movzx   ebx, ax
0x1800266be  or      ebx, esi
0x1800266c0  test    ebx, ebx
0x1800266c2  js      loc_18002679C
0x1800266c8  mov     rdx, [rbp+57h+SidToCheck]; SidToCheck
0x1800266cc  lea     r8, [rbp+57h+IsMember]; IsMember
0x1800266d0  xor     ecx, ecx; TokenHandle
0x1800266d2  call    cs:__imp_CheckTokenMembership
0x1800266d8  test    eax, eax
0x1800266da  jnz     short loc_1800266FB
0x1800266dc  call    cs:__imp_GetLastError
0x1800266e2  mov     ebx, eax
0x1800266e4  test    eax, eax
0x1800266e6  jz      loc_180026797
0x1800266ec  jle     short loc_1800266F3
0x1800266ee  movzx   ebx, ax
0x1800266f1  or      ebx, esi
0x1800266f3  test    ebx, ebx
0x1800266f5  js      loc_18002679C
0x1800266fb  cmp     [rbp+57h+IsMember], edi
0x1800266fe  jz      short loc_180026707
0x180026700  mov     ebx, edi
0x180026702  jmp     loc_1800267BF
0x180026707  lea     rax, [rbp+57h+var_48]
0x18002670b  mov     r9d, 22Fh; nSubAuthority1
0x180026711  mov     [rsp+0B0h+pSid], rax; pSid
0x180026716  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x18002671a  mov     [rsp+0B0h+nSubAuthority7], edi; nSubAuthority7
0x18002671e  mov     r8d, 20h ; ' '; nSubAuthority0
0x180026724  mov     [rsp+0B0h+nSubAuthority6], edi; nSubAuthority6
0x180026728  mov     dl, 2; nSubAuthorityCount
0x18002672a  mov     [rsp+0B0h+nSubAuthority5], edi; nSubAuthority5
0x18002672e  mov     [rsp+0B0h+nSubAuthority4], edi; nSubAuthority4
0x180026732  mov     [rsp+0B0h+nSubAuthority3], edi; nSubAuthority3
0x180026736  mov     dword ptr [rsp+0B0h+nSubAuthority2], edi; nSubAuthority2
0x18002673a  call    cs:__imp_AllocateAndInitializeSid
0x180026740  test    eax, eax
0x180026742  jnz     short loc_18002675B
0x180026744  call    cs:__imp_GetLastError
0x18002674a  mov     ebx, eax
0x18002674c  test    eax, eax
0x18002674e  jz      short loc_180026797
0x180026750  jle     short loc_180026757
0x180026752  movzx   ebx, ax
0x180026755  or      ebx, esi
0x180026757  test    ebx, ebx
0x180026759  js      short loc_18002679C
0x18002675b  mov     rdx, [rbp+57h+var_48]; SidToCheck
0x18002675f  lea     r8, [rbp+57h+IsMember]; IsMember
0x180026763  xor     ecx, ecx; TokenHandle
0x180026765  call    cs:__imp_CheckTokenMembership
0x18002676b  test    eax, eax
0x18002676d  jz      short loc_180026773
0x18002676f  mov     ebx, edi
0x180026771  jmp     short loc_18002678A
0x180026773  call    cs:__imp_GetLastError
0x180026779  mov     ebx, eax
0x18002677b  test    eax, eax
0x18002677d  jz      short loc_180026797
0x18002677f  jle     short loc_180026786
0x180026781  movzx   ebx, ax
0x180026784  or      ebx, esi
0x180026786  test    ebx, ebx
0x180026788  js      short loc_18002679C
0x18002678a  cmp     [rbp+57h+IsMember], edi
0x18002678d  mov     eax, 1
0x180026792  cmovz   ebx, eax
0x180026795  jmp     short loc_1800267BF
0x180026797  mov     ebx, 80004005h
0x18002679c  mov     eax, ebx
0x18002679e  mov     dword ptr [rsp+0B0h+nSubAuthority2], ebx
0x1800267a2  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x1800267a9  xor     r8d, r8d; int
0x1800267ac  lea     rdx, aWdccheckmember; "WdcCheckMembership"
0x1800267b3  lea     rcx, aBaseDiagnosisP_13; "base\\diagnosis\\pdui\\perfmon\\mmc\\ut"...
0x1800267ba  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x1800267bf  mov     rcx, [rbp+57h+var_48]; pSid
0x1800267c3  test    rcx, rcx
0x1800267c6  jz      short loc_1800267CE
0x1800267c8  call    cs:__imp_FreeSid
0x1800267ce  mov     rcx, [rbp+57h+SidToCheck]; pSid
0x1800267d2  test    rcx, rcx
0x1800267d5  jz      short loc_1800267DD
0x1800267d7  call    cs:__imp_FreeSid
0x1800267dd  mov     eax, ebx
0x1800267df  mov     rcx, [rbp+57h+var_30]
0x1800267e3  xor     rcx, rsp; StackCookie
0x1800267e6  call    __security_check_cookie
0x1800267eb  add     rsp, 98h
0x1800267f2  pop     rdi
0x1800267f3  pop     rsi
0x1800267f4  pop     rbx
0x1800267f5  pop     rbp
0x1800267f6  retn
```
