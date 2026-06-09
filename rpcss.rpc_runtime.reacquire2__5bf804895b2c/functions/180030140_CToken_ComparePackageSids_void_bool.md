# CToken::ComparePackageSids(void *,bool)

- ea: `0x180030140`
- end: `0x180030393`
- name: `?ComparePackageSids@CToken@@QEAAJPEAX_N@Z`
- size: `595`
- prototype: `int(CToken *__hidden this, void *, bool)`
- caller_count: `3`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18002aa10`
- `0x18002f160`
- `0x18002ffe4`

## callees

- `0x18001c624`
- `0x1800210f8`
- `0x180030140`
- `0x180093f20`
- `0x1800b7ac0`

## import_xrefs

- `ntdll!RtlFreeSid` at `0x180030312`
- `ntdll!RtlFreeSid` at `0x180030312`
- `ntdll!RtlGetAppContainerSidType` at `0x180030263`
- `ntdll!RtlGetAppContainerSidType` at `0x180030263`
- `ntdll!RtlEqualSid` at `0x18003032a`
- `ntdll!RtlEqualSid` at `0x18003032a`
- `ntdll!RtlGetAppContainerParent` at `0x1800302da`
- `ntdll!RtlGetAppContainerParent` at `0x1800302da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800301dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003021b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800301dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003021b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800301ae`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800301ae`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180030347`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180030347`

## string_xrefs

- `0x18003020b`: `onecore\com\combase\rpcss\objex\token.cxx`
- `0x18003027b`: `onecore\com\combase\rpcss\objex\token.cxx`
- `0x1800302a1`: `onecore\com\combase\rpcss\objex\token.cxx`
- `0x1800302f2`: `onecore\com\combase\rpcss\objex\token.cxx`
- `0x1800301f3`: `GetTokenPackageSid`

## pseudocode

```c
int __fastcall CToken::ComparePackageSids(CToken *this, void *a2, char a3)
{
  void *v3; // rcx
  int result; // eax
  bool v7; // zf
  PSID v8; // rcx
  int AppContainerSidType; // eax
  int v10; // eax
  int v11; // ebx
  int AppContainerParent; // eax
  int v13; // ebx
  PDWORD ReturnLength; // [rsp+20h] [rbp-98h]
  int ReturnLengtha; // [rsp+20h] [rbp-98h]
  PSID Sid[2]; // [rsp+40h] [rbp-78h] BYREF
  PSID pSid1[2]; // [rsp+50h] [rbp-68h] BYREF
  __int128 v18; // [rsp+60h] [rbp-58h]
  __int128 v19; // [rsp+70h] [rbp-48h]
  _BYTE v20[28]; // [rsp+80h] [rbp-38h] BYREF
  int v21; // [rsp+9Ch] [rbp-1Ch]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]

  v3 = (void *)*((_QWORD *)this + 9);
  v21 = 0;
  *(_OWORD *)pSid1 = 0;
  v18 = 0;
  LODWORD(Sid[0]) = 0;
  v19 = 0;
  memset(v20, 0, sizeof(v20));
  if ( GetTokenInformation(v3, TokenAppContainerSid, pSid1, 0x4Cu, (PDWORD)Sid) )
    goto LABEL_9;
  if ( dword_1801574B8 || gfEnableTracing && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    GetLastError();
    LODWORD(ReturnLength) = 0;
    ComTraceMessage(
      0xFFFFFFFFLL,
      "onecore\\com\\combase\\rpcss\\objex\\token.cxx",
      "GetTokenPackageSid",
      112,
      ReturnLength,
      L"%!WINERROR!");
  }
  result = GetLastError();
  v7 = result == 0;
  if ( result > 0 )
  {
    result = (unsigned __int16)result | 0x80070000;
    v7 = result == 0;
  }
  if ( v7 )
  {
LABEL_9:
    v8 = pSid1[0];
    if ( pSid1[0] )
    {
      if ( a2 )
      {
        if ( !a3 )
          return !EqualSid(v8, a2);
        LODWORD(Sid[0]) = 0;
        AppContainerSidType = RtlGetAppContainerSidType(pSid1[0], Sid);
        if ( AppContainerSidType < 0 )
        {
          v10 = wil::details::in1diag3::Return_NtStatus(
                  retaddr,
                  (void *)0x9C0,
                  (unsigned int)"onecore\\com\\combase\\rpcss\\objex\\token.cxx",
                  (const char *)(unsigned int)AppContainerSidType,
                  (int)ReturnLength);
          v11 = v10;
          if ( v10 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x981,
              (unsigned int)"onecore\\com\\combase\\rpcss\\objex\\token.cxx",
              (const char *)(unsigned int)v10,
              ReturnLengtha);
            return v11;
          }
          goto LABEL_22;
        }
        if ( LODWORD(Sid[0]) != 1 )
        {
LABEL_22:
          v8 = pSid1[0];
          return !EqualSid(v8, a2);
        }
        Sid[0] = 0;
        AppContainerParent = RtlGetAppContainerParent(pSid1[0], Sid);
        if ( AppContainerParent >= 0 )
          v13 = RtlEqualSid(Sid[0], a2) == 0;
        else
          v13 = wil::details::in1diag3::Return_NtStatus(
                  retaddr,
                  (void *)0x986,
                  (unsigned int)"onecore\\com\\combase\\rpcss\\objex\\token.cxx",
                  (const char *)(unsigned int)AppContainerParent,
                  (int)ReturnLength);
        if ( Sid[0] )
          RtlFreeSid(Sid[0]);
        return v13;
      }
      else
      {
        return 1;
      }
    }
    else
    {
      return a2 != 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180030140  mov     r11, rsp
0x180030143  mov     [r11+18h], rbx
0x180030147  mov     [r11+20h], rsi
0x18003014b  push    rdi
0x18003014c  sub     rsp, 0B0h
0x180030153  mov     rax, cs:__security_cookie
0x18003015a  xor     rax, rsp
0x18003015d  mov     [rsp+0B8h+var_18], rax
0x180030165  mov     rcx, [rcx+48h]; TokenHandle
0x180030169  lea     rax, [r11-78h]
0x18003016d  xorps   xmm0, xmm0
0x180030170  mov     [rsp+0B8h+ReturnLength], rax; ReturnLength
0x180030175  xor     esi, esi
0x180030177  movzx   ebx, r8b
0x18003017b  mov     [r11-1Ch], esi
0x18003017f  lea     r8, [r11-68h]; TokenInformation
0x180030183  movups  xmmword ptr [rsp+0B8h+pSid1], xmm0
0x180030188  mov     rdi, rdx
0x18003018b  mov     r9d, 4Ch ; 'L'; TokenInformationLength
0x180030191  movups  [rsp+0B8h+var_58], xmm0
0x180030196  mov     edx, 1Fh; TokenInformationClass
0x18003019b  mov     dword ptr [rsp+0B8h+Sid], esi
0x18003019f  movups  [rsp+0B8h+var_48], xmm0
0x1800301a4  movups  xmmword ptr [r11-38h], xmm0
0x1800301a9  movups  xmmword ptr [r11-2Ch], xmm0
0x1800301ae  call    cs:__imp_GetTokenInformation
0x1800301b5  nop     dword ptr [rax+rax+00h]
0x1800301ba  test    eax, eax
0x1800301bc  jnz     short loc_18003023B
0x1800301be  mov     eax, cs:dword_1801574B8
0x1800301c4  test    eax, eax
0x1800301c6  jnz     short loc_1800301DD
0x1800301c8  cmp     cs:?gfEnableTracing@@3HA, esi; int gfEnableTracing
0x1800301ce  jz      short loc_18003021B
0x1800301d0  mov     rax, cs:WPP_GLOBAL_Control
0x1800301d7  test    byte ptr [rax+1Ch], 1
0x1800301db  jz      short loc_18003021B
0x1800301dd  call    cs:__imp_GetLastError
0x1800301e4  nop     dword ptr [rax+rax+00h]
0x1800301e9  mov     [rsp+0B8h+var_88], eax
0x1800301ed  mov     r9d, 70h ; 'p'
0x1800301f3  lea     r8, aGettokenpackag; "GetTokenPackageSid"
0x1800301fa  mov     ecx, 0FFFFFFFFh
0x1800301ff  lea     rax, aWinerror; "%!WINERROR!"
0x180030206  mov     [rsp+0B8h+var_90], rax
0x18003020b  lea     rdx, aOnecoreComComb_100; "onecore\\com\\combase\\rpcss\\objex\\to"...
0x180030212  mov     dword ptr [rsp+0B8h+ReturnLength], esi; int
0x180030216  call    ?ComTraceMessage@@YAXJPEBD0HW4TraceLevel@@PEBGZZ; ComTraceMessage(long,char const *,char const *,int,TraceLevel,ushort const *,...)
0x18003021b  call    cs:__imp_GetLastError
0x180030222  nop     dword ptr [rax+rax+00h]
0x180030227  test    eax, eax
0x180030229  jle     short loc_180030235
0x18003022b  movzx   eax, ax
0x18003022e  or      eax, 80070000h
0x180030233  test    eax, eax
0x180030235  jnz     loc_18003036D
0x18003023b  mov     rcx, [rsp+0B8h+pSid1]
0x180030240  test    rcx, rcx
0x180030243  jz      loc_180030365
0x180030249  test    rdi, rdi
0x18003024c  jz      loc_18003035E
0x180030252  test    bl, bl
0x180030254  jz      loc_180030344
0x18003025a  lea     rdx, [rsp+0B8h+Sid]
0x18003025f  mov     dword ptr [rsp+0B8h+Sid], esi
0x180030263  call    cs:__imp_RtlGetAppContainerSidType
0x18003026a  nop     dword ptr [rax+rax+00h]
0x18003026f  test    eax, eax
0x180030271  jns     short loc_1800302BC
0x180030273  mov     rcx, [rsp+0B8h]; this
0x18003027b  lea     r8, aOnecoreComComb_100; "onecore\\com\\combase\\rpcss\\objex\\to"...
0x180030282  mov     r9d, eax; char *
0x180030285  mov     edx, 9C0h; void *
0x18003028a  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18003028f  mov     ebx, eax
0x180030291  test    eax, eax
0x180030293  jns     loc_18003033F
0x180030299  mov     rcx, [rsp+0B8h]; this
0x1800302a1  lea     r8, aOnecoreComComb_100; "onecore\\com\\combase\\rpcss\\objex\\to"...
0x1800302a8  mov     r9d, eax; char *
0x1800302ab  mov     edx, 981h; void *
0x1800302b0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800302b5  mov     eax, ebx
0x1800302b7  jmp     loc_18003036D
0x1800302bc  xor     al, al
0x1800302be  cmp     dword ptr [rsp+0B8h+Sid], 1
0x1800302c3  jnz     short loc_1800302C7
0x1800302c5  mov     al, 1
0x1800302c7  test    al, al
0x1800302c9  jz      short loc_18003033F
0x1800302cb  mov     rcx, [rsp+0B8h+pSid1]
0x1800302d0  lea     rdx, [rsp+0B8h+Sid]
0x1800302d5  mov     [rsp+0B8h+Sid], rsi
0x1800302da  call    cs:__imp_RtlGetAppContainerParent
0x1800302e1  nop     dword ptr [rax+rax+00h]
0x1800302e6  test    eax, eax
0x1800302e8  jns     short loc_180030322
0x1800302ea  mov     rcx, [rsp+0B8h]; this
0x1800302f2  lea     r8, aOnecoreComComb_100; "onecore\\com\\combase\\rpcss\\objex\\to"...
0x1800302f9  mov     r9d, eax; char *
0x1800302fc  mov     edx, 986h; void *
0x180030301  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180030306  mov     ebx, eax
0x180030308  mov     rcx, [rsp+0B8h+Sid]; Sid
0x18003030d  test    rcx, rcx
0x180030310  jz      short loc_18003031E
0x180030312  call    cs:__imp_RtlFreeSid
0x180030319  nop     dword ptr [rax+rax+00h]
0x18003031e  mov     eax, ebx
0x180030320  jmp     short loc_18003036D
0x180030322  mov     rcx, [rsp+0B8h+Sid]; Sid1
0x180030327  mov     rdx, rdi; Sid2
0x18003032a  call    cs:__imp_RtlEqualSid
0x180030331  nop     dword ptr [rax+rax+00h]
0x180030336  test    al, al
0x180030338  mov     ebx, esi
0x18003033a  setz    bl
0x18003033d  jmp     short loc_180030308
0x18003033f  mov     rcx, [rsp+0B8h+pSid1]; pSid1
0x180030344  mov     rdx, rdi; pSid2
0x180030347  call    cs:__imp_EqualSid
0x18003034e  nop     dword ptr [rax+rax+00h]
0x180030353  test    eax, eax
0x180030355  mov     ecx, esi
0x180030357  setz    cl
0x18003035a  mov     eax, ecx
0x18003035c  jmp     short loc_18003036D
0x18003035e  mov     eax, 1
0x180030363  jmp     short loc_18003036D
0x180030365  cmp     rcx, rdi
0x180030368  mov     eax, esi
0x18003036a  setnz   al
0x18003036d  mov     rcx, [rsp+0B8h+var_18]
0x180030375  xor     rcx, rsp; StackCookie
0x180030378  call    __security_check_cookie
0x18003037d  lea     r11, [rsp+0B8h+var_8]
0x180030385  mov     rbx, [r11+20h]
0x180030389  mov     rsi, [r11+28h]
0x18003038d  mov     rsp, r11
0x180030390  pop     rdi
0x180030391  retn
```
