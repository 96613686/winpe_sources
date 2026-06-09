# CToken::ComparePackageSids(void *,bool)

- ea: `0x180025d00`
- end: `0x180025f22`
- name: `?ComparePackageSids@CToken@@QEAAJPEAX_N@Z`
- size: `546`
- prototype: `int(CToken *__hidden this, void *, bool)`
- caller_count: `3`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180024e48`
- `0x180025bac`
- `0x180031ae0`

## callees

- `0x180018344`
- `0x180025d00`
- `0x18002ba28`
- `0x18008cd90`
- `0x1800b27e0`

## import_xrefs

- `ntdll!RtlFreeSid` at `0x180025eb4`
- `ntdll!RtlFreeSid` at `0x180025eb4`
- `ntdll!RtlGetAppContainerSidType` at `0x180025e11`
- `ntdll!RtlGetAppContainerSidType` at `0x180025e11`
- `ntdll!RtlEqualSid` at `0x180025ec6`
- `ntdll!RtlEqualSid` at `0x180025ec6`
- `ntdll!RtlGetAppContainerParent` at `0x180025e82`
- `ntdll!RtlGetAppContainerParent` at `0x180025e82`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025d97`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025dcf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025d97`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025dcf`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180025d6e`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180025d6e`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180025edd`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180025edd`

## string_xrefs

- `0x180025dbf`: `onecore\com\combase\rpcss\objex\token.cxx`
- `0x180025e23`: `onecore\com\combase\rpcss\objex\token.cxx`
- `0x180025e49`: `onecore\com\combase\rpcss\objex\token.cxx`
- `0x180025e94`: `onecore\com\combase\rpcss\objex\token.cxx`
- `0x180025da7`: `GetTokenPackageSid`

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
  int ReturnLength; // [rsp+20h] [rbp-98h]
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
  if ( dword_18014E4B8 || gfEnableTracing && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    GetLastError();
    ReturnLength = 0;
    ComTraceMessage(0xFFFFFFFFLL, "onecore\\com\\combase\\rpcss\\objex\\token.cxx", "GetTokenPackageSid", 112);
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
                  ReturnLength);
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
                  ReturnLength);
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
0x180025d00  mov     r11, rsp
0x180025d03  mov     [r11+18h], rbx
0x180025d07  mov     [r11+20h], rsi
0x180025d0b  push    rdi
0x180025d0c  sub     rsp, 0B0h
0x180025d13  mov     rax, cs:__security_cookie
0x180025d1a  xor     rax, rsp
0x180025d1d  mov     [rsp+0B8h+var_18], rax
0x180025d25  mov     rcx, [rcx+48h]; TokenHandle
0x180025d29  lea     rax, [r11-78h]
0x180025d2d  xorps   xmm0, xmm0
0x180025d30  mov     [rsp+0B8h+ReturnLength], rax; ReturnLength
0x180025d35  xor     esi, esi
0x180025d37  movzx   ebx, r8b
0x180025d3b  mov     [r11-1Ch], esi
0x180025d3f  lea     r8, [r11-68h]; TokenInformation
0x180025d43  movups  xmmword ptr [rsp+0B8h+pSid1], xmm0
0x180025d48  mov     rdi, rdx
0x180025d4b  mov     r9d, 4Ch ; 'L'; TokenInformationLength
0x180025d51  movups  [rsp+0B8h+var_58], xmm0
0x180025d56  mov     edx, 1Fh; TokenInformationClass
0x180025d5b  mov     dword ptr [rsp+0B8h+Sid], esi
0x180025d5f  movups  [rsp+0B8h+var_48], xmm0
0x180025d64  movups  xmmword ptr [r11-38h], xmm0
0x180025d69  movups  xmmword ptr [r11-2Ch], xmm0
0x180025d6e  call    cs:__imp_GetTokenInformation
0x180025d74  test    eax, eax
0x180025d76  jnz     short loc_180025DE9
0x180025d78  mov     eax, cs:dword_18014E4B8
0x180025d7e  test    eax, eax
0x180025d80  jnz     short loc_180025D97
0x180025d82  cmp     cs:?gfEnableTracing@@3HA, esi; int gfEnableTracing
0x180025d88  jz      short loc_180025DCF
0x180025d8a  mov     rax, cs:WPP_GLOBAL_Control
0x180025d91  test    byte ptr [rax+1Ch], 1
0x180025d95  jz      short loc_180025DCF
0x180025d97  call    cs:__imp_GetLastError
0x180025d9d  mov     [rsp+0B8h+var_88], eax
0x180025da1  mov     r9d, 70h ; 'p'
0x180025da7  lea     r8, aGettokenpackag; "GetTokenPackageSid"
0x180025dae  mov     ecx, 0FFFFFFFFh
0x180025db3  lea     rax, aWinerror; "%!WINERROR!"
0x180025dba  mov     [rsp+0B8h+var_90], rax
0x180025dbf  lea     rdx, aOnecoreComComb_100; "onecore\\com\\combase\\rpcss\\objex\\to"...
0x180025dc6  mov     dword ptr [rsp+0B8h+ReturnLength], esi; int
0x180025dca  call    ?ComTraceMessage@@YAXJPEBD0HW4TraceLevel@@PEBGZZ; ComTraceMessage(long,char const *,char const *,int,TraceLevel,ushort const *,...)
0x180025dcf  call    cs:__imp_GetLastError
0x180025dd5  test    eax, eax
0x180025dd7  jle     short loc_180025DE3
0x180025dd9  movzx   eax, ax
0x180025ddc  or      eax, 80070000h
0x180025de1  test    eax, eax
0x180025de3  jnz     loc_180025EFD
0x180025de9  mov     rcx, [rsp+0B8h+pSid1]
0x180025dee  test    rcx, rcx
0x180025df1  jz      loc_180025EF5
0x180025df7  test    rdi, rdi
0x180025dfa  jz      loc_180025EEE
0x180025e00  test    bl, bl
0x180025e02  jz      loc_180025EDA
0x180025e08  lea     rdx, [rsp+0B8h+Sid]
0x180025e0d  mov     dword ptr [rsp+0B8h+Sid], esi
0x180025e11  call    cs:__imp_RtlGetAppContainerSidType
0x180025e17  test    eax, eax
0x180025e19  jns     short loc_180025E64
0x180025e1b  mov     rcx, [rsp+0B8h]; this
0x180025e23  lea     r8, aOnecoreComComb_100; "onecore\\com\\combase\\rpcss\\objex\\to"...
0x180025e2a  mov     r9d, eax; char *
0x180025e2d  mov     edx, 9C0h; void *
0x180025e32  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180025e37  mov     ebx, eax
0x180025e39  test    eax, eax
0x180025e3b  jns     loc_180025ED5
0x180025e41  mov     rcx, [rsp+0B8h]; this
0x180025e49  lea     r8, aOnecoreComComb_100; "onecore\\com\\combase\\rpcss\\objex\\to"...
0x180025e50  mov     r9d, eax; char *
0x180025e53  mov     edx, 981h; void *
0x180025e58  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180025e5d  mov     eax, ebx
0x180025e5f  jmp     loc_180025EFD
0x180025e64  xor     al, al
0x180025e66  cmp     dword ptr [rsp+0B8h+Sid], 1
0x180025e6b  jnz     short loc_180025E6F
0x180025e6d  mov     al, 1
0x180025e6f  test    al, al
0x180025e71  jz      short loc_180025ED5
0x180025e73  mov     rcx, [rsp+0B8h+pSid1]
0x180025e78  lea     rdx, [rsp+0B8h+Sid]
0x180025e7d  mov     [rsp+0B8h+Sid], rsi
0x180025e82  call    cs:__imp_RtlGetAppContainerParent
0x180025e88  test    eax, eax
0x180025e8a  jns     short loc_180025EBE
0x180025e8c  mov     rcx, [rsp+0B8h]; this
0x180025e94  lea     r8, aOnecoreComComb_100; "onecore\\com\\combase\\rpcss\\objex\\to"...
0x180025e9b  mov     r9d, eax; char *
0x180025e9e  mov     edx, 986h; void *
0x180025ea3  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180025ea8  mov     ebx, eax
0x180025eaa  mov     rcx, [rsp+0B8h+Sid]; Sid
0x180025eaf  test    rcx, rcx
0x180025eb2  jz      short loc_180025EBA
0x180025eb4  call    cs:__imp_RtlFreeSid
0x180025eba  mov     eax, ebx
0x180025ebc  jmp     short loc_180025EFD
0x180025ebe  mov     rcx, [rsp+0B8h+Sid]; Sid1
0x180025ec3  mov     rdx, rdi; Sid2
0x180025ec6  call    cs:__imp_RtlEqualSid
0x180025ecc  test    al, al
0x180025ece  mov     ebx, esi
0x180025ed0  setz    bl
0x180025ed3  jmp     short loc_180025EAA
0x180025ed5  mov     rcx, [rsp+0B8h+pSid1]; pSid1
0x180025eda  mov     rdx, rdi; pSid2
0x180025edd  call    cs:__imp_EqualSid
0x180025ee3  test    eax, eax
0x180025ee5  mov     ecx, esi
0x180025ee7  setz    cl
0x180025eea  mov     eax, ecx
0x180025eec  jmp     short loc_180025EFD
0x180025eee  mov     eax, 1
0x180025ef3  jmp     short loc_180025EFD
0x180025ef5  cmp     rcx, rdi
0x180025ef8  mov     eax, esi
0x180025efa  setnz   al
0x180025efd  mov     rcx, [rsp+0B8h+var_18]
0x180025f05  xor     rcx, rsp; StackCookie
0x180025f08  call    __security_check_cookie
0x180025f0d  lea     r11, [rsp+0B8h+var_8]
0x180025f15  mov     rbx, [r11+20h]
0x180025f19  mov     rsi, [r11+28h]
0x180025f1d  mov     rsp, r11
0x180025f20  pop     rdi
0x180025f21  retn
```
