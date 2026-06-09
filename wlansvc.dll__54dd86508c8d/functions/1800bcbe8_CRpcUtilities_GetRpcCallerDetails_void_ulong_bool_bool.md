# CRpcUtilities::GetRpcCallerDetails(void *,ulong *,bool *,bool *)

- ea: `0x1800bcbe8`
- end: `0x1800bce96`
- name: `?GetRpcCallerDetails@CRpcUtilities@@SAXPEAXPEAKPEA_N2@Z`
- size: `686`
- prototype: `void __fastcall(RPC_BINDING_HANDLE ClientBinding, unsigned int *, bool *, bool *)`
- caller_count: `3`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1801ebd58`
- `0x1801ec6e0`
- `0x1801ed160`

## callees

- `0x18000aa0c`
- `0x180011530`
- `0x180073c18`
- `0x1800bcbe8`
- `0x1800bd620`
- `0x180106340`
- `0x180107330`
- `0x180214a34`
- `0x180214dec`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bcd48`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bcda0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bce12`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bcd48`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bcda0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bce12`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800bcd96`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800bcd96`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x1800bcc73`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x1800bcc73`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800bcd39`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800bcd39`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800bce08`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800bce08`

## string_xrefs

- `0x1800bce24`: `GetTokenInformation failed`
- `0x1800bcd5a`: `OpenProcess failed`
- `0x1800bcdb2`: `OpenProcessToken failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=21
void __fastcall CRpcUtilities::GetRpcCallerDetails(
        RPC_BINDING_HANDLE ClientBinding,
        unsigned int *a2,
        bool *a3,
        bool *a4)
{
  unsigned int v8; // eax
  int v9; // eax
  DWORD v10; // r8d
  HANDLE v11; // rax
  signed int LastError; // eax
  signed int v13; // eax
  signed int v14; // eax
  DWORD dwProcessId; // [rsp+30h] [rbp-79h] BYREF
  int TokenInformation; // [rsp+34h] [rbp-75h] BYREF
  void *TokenHandle; // [rsp+38h] [rbp-71h] BYREF
  DWORD ReturnLength; // [rsp+40h] [rbp-69h] BYREF
  HANDLE v19; // [rsp+48h] [rbp-61h] BYREF
  _DWORD RpcCallAttributes[2]; // [rsp+50h] [rbp-59h] BYREF
  _BYTE v21[56]; // [rsp+58h] [rbp-51h] BYREF
  unsigned __int64 v22; // [rsp+90h] [rbp-19h]

  if ( !ClientBinding
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 2u
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 13, WPP_6cb57578a11d39b1330a34758a21b766_Traceguids);
  }
  memset_0(v21, 0, 0x68u);
  RpcCallAttributes[0] = 2;
  RpcCallAttributes[1] = 16;
  v8 = RpcServerInqCallAttributesW(ClientBinding, RpcCallAttributes);
  if ( v8 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 105)
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 14, WPP_6cb57578a11d39b1330a34758a21b766_Traceguids, v8);
    }
    WFDSvc::CWFDSvcException::Throw(
      -2147024122,
      "CRpcUtilities::GetRpcCallerDetails",
      "onecoreuap\\net\\wlan\\autocfg\\wlansvcext\\util\\src\\wfdrpcutil.cpp",
      0x72u,
      L"RpcServerInqCallAttributesW failed");
  }
  dwProcessId = 0;
  v9 = ULongLongToULong(v22, &dwProcessId);
  if ( v9 < 0 )
    WFDSvc::CWFDSvcException::Throw(
      v9,
      "CRpcUtilities::GetRpcCallerDetails",
      "onecoreuap\\net\\wlan\\autocfg\\wlansvcext\\util\\src\\wfdrpcutil.cpp",
      0x79u,
      L"Cast failed");
  v10 = dwProcessId;
  if ( a2 )
    *a2 = dwProcessId;
  if ( a3 || a4 )
  {
    v11 = OpenProcess(0x1000u, 0, v10);
    v19 = v11;
    if ( !v11 )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      WFDSvc::CWFDSvcException::Throw(
        LastError,
        "CRpcUtilities::GetRpcCallerDetails",
        "onecoreuap\\net\\wlan\\autocfg\\wlansvcext\\util\\src\\wfdrpcutil.cpp",
        0x87u,
        L"OpenProcess failed");
    }
    TokenHandle = 0;
    if ( !OpenProcessToken(v11, 8u, &TokenHandle) )
    {
      v13 = GetLastError();
      if ( v13 > 0 )
        v13 = (unsigned __int16)v13 | 0x80070000;
      WFDSvc::CWFDSvcException::Throw(
        v13,
        "CRpcUtilities::GetRpcCallerDetails",
        "onecoreuap\\net\\wlan\\autocfg\\wlansvcext\\util\\src\\wfdrpcutil.cpp",
        0x8Fu,
        L"OpenProcessToken failed");
    }
    if ( a3 )
    {
      TokenInformation = 0;
      ReturnLength = 0;
      if ( !GetTokenInformation(TokenHandle, TokenIsAppContainer, &TokenInformation, 4u, &ReturnLength) )
      {
        v14 = GetLastError();
        if ( v14 > 0 )
          v14 = (unsigned __int16)v14 | 0x80070000;
        WFDSvc::CWFDSvcException::Throw(
          v14,
          "CRpcUtilities::GetRpcCallerDetails",
          "onecoreuap\\net\\wlan\\autocfg\\wlansvcext\\util\\src\\wfdrpcutil.cpp",
          0x9Fu,
          L"GetTokenInformation failed");
      }
      *a3 = TokenInformation != 0;
    }
    if ( a4 )
      CRpcUtilities::CheckCallerUIModel((const struct COsHandle *)&TokenHandle, a4);
    COsHandle::~COsHandle((COsHandle *)&TokenHandle);
    COsHandle::~COsHandle((COsHandle *)&v19);
  }
}

```

## disassembly

```asm
0x1800bcbe8  push    rbp
0x1800bcbea  push    rbx
0x1800bcbeb  push    rsi
0x1800bcbec  push    rdi
0x1800bcbed  push    r13
0x1800bcbef  push    r14
0x1800bcbf1  lea     rbp, [rsp-2Fh]
0x1800bcbf6  sub     rsp, 0D8h
0x1800bcbfd  mov     rax, cs:__security_cookie
0x1800bcc04  xor     rax, rsp
0x1800bcc07  mov     [rbp+57h+var_40], rax
0x1800bcc0b  mov     rbx, r9
0x1800bcc0e  mov     rdi, r8
0x1800bcc11  mov     rsi, rdx
0x1800bcc14  mov     r14, rcx
0x1800bcc17  lea     r13, WPP_GLOBAL_Control
0x1800bcc1e  test    rcx, rcx
0x1800bcc21  jnz     short loc_1800BCC4F
0x1800bcc23  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bcc2a  cmp     rcx, r13
0x1800bcc2d  jz      short loc_1800BCC4F
0x1800bcc2f  cmp     byte ptr [rcx+69h], 2
0x1800bcc33  jb      short loc_1800BCC4F
0x1800bcc35  test    byte ptr [rcx+6Ch], 1
0x1800bcc39  jz      short loc_1800BCC4F
0x1800bcc3b  lea     edx, [r14+0Dh]
0x1800bcc3f  lea     r8, WPP_6cb57578a11d39b1330a34758a21b766_Traceguids
0x1800bcc46  mov     rcx, [rcx+60h]
0x1800bcc4a  call    WPP_SF_
0x1800bcc4f  xor     edx, edx; Val
0x1800bcc51  lea     r8d, [rdx+68h]; Size
0x1800bcc55  lea     rcx, [rbp+57h+var_A8]; void *
0x1800bcc59  call    memset_0
0x1800bcc5e  mov     [rbp+57h+RpcCallAttributes], 2
0x1800bcc65  mov     [rbp+57h+var_AC], 10h
0x1800bcc6c  lea     rdx, [rbp+57h+RpcCallAttributes]; RpcCallAttributes
0x1800bcc70  mov     rcx, r14; ClientBinding
0x1800bcc73  call    cs:__imp_RpcServerInqCallAttributesW
0x1800bcc79  test    eax, eax
0x1800bcc7b  jz      short loc_1800BCCD8
0x1800bcc7d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bcc84  cmp     rcx, r13
0x1800bcc87  jz      short loc_1800BCCAD
0x1800bcc89  cmp     byte ptr [rcx+69h], 1
0x1800bcc8d  jb      short loc_1800BCCAD
0x1800bcc8f  test    byte ptr [rcx+6Ch], 1
0x1800bcc93  jz      short loc_1800BCCAD
0x1800bcc95  mov     edx, 0Eh
0x1800bcc9a  mov     r9d, eax
0x1800bcc9d  lea     r8, WPP_6cb57578a11d39b1330a34758a21b766_Traceguids
0x1800bcca4  mov     rcx, [rcx+60h]
0x1800bcca8  call    WPP_SF_d
0x1800bccad  lea     rax, aRpcserverinqca; "RpcServerInqCallAttributesW failed"
0x1800bccb4  mov     [rsp+100h+ReturnLength], rax; unsigned __int16 *
0x1800bccb9  mov     r9d, 72h ; 'r'; unsigned int
0x1800bccbf  lea     r8, aOnecoreuapNetW_20; "onecoreuap\\net\\wlan\\autocfg\\wlansvc"...
0x1800bccc6  lea     rdx, aCrpcutilitiesG; "CRpcUtilities::GetRpcCallerDetails"
0x1800bcccd  mov     ecx, 80070306h; int
0x1800bccd2  call    ?Throw@CWFDSvcException@WFDSvc@@SAXJPEBD0KPEBG@Z; WFDSvc::CWFDSvcException::Throw(long,char const *,char const *,ulong,ushort const *)
0x1800bccd8  mov     [rbp+57h+dwProcessId], 0
0x1800bccdf  lea     rdx, [rbp+57h+dwProcessId]; unsigned int *
0x1800bcce3  mov     rcx, [rbp+57h+var_70]; unsigned __int64
0x1800bcce7  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x1800bccec  test    eax, eax
0x1800bccee  jns     short loc_1800BCD18
0x1800bccf0  lea     rcx, aCastFailed; "Cast failed"
0x1800bccf7  mov     [rsp+100h+ReturnLength], rcx; unsigned __int16 *
0x1800bccfc  mov     r9d, 79h ; 'y'; unsigned int
0x1800bcd02  lea     r8, aOnecoreuapNetW_20; "onecoreuap\\net\\wlan\\autocfg\\wlansvc"...
0x1800bcd09  lea     rdx, aCrpcutilitiesG; "CRpcUtilities::GetRpcCallerDetails"
0x1800bcd10  mov     ecx, eax; int
0x1800bcd12  call    ?Throw@CWFDSvcException@WFDSvc@@SAXJPEBD0KPEBG@Z; WFDSvc::CWFDSvcException::Throw(long,char const *,char const *,ulong,ushort const *)
0x1800bcd18  mov     r8d, [rbp+57h+dwProcessId]; dwProcessId
0x1800bcd1c  test    rsi, rsi
0x1800bcd1f  jz      short loc_1800BCD24
0x1800bcd21  mov     [rsi], r8d
0x1800bcd24  test    rdi, rdi
0x1800bcd27  jnz     short loc_1800BCD32
0x1800bcd29  test    rbx, rbx
0x1800bcd2c  jz      loc_1800BCE7A
0x1800bcd32  xor     edx, edx; bInheritHandle
0x1800bcd34  mov     ecx, 1000h; dwDesiredAccess
0x1800bcd39  call    cs:__imp_OpenProcess
0x1800bcd3f  mov     [rbp+57h+var_B8], rax
0x1800bcd43  test    rax, rax
0x1800bcd46  jnz     short loc_1800BCD82
0x1800bcd48  call    cs:__imp_GetLastError
0x1800bcd4e  test    eax, eax
0x1800bcd50  jle     short loc_1800BCD5A
0x1800bcd52  movzx   eax, ax
0x1800bcd55  or      eax, 80070000h
0x1800bcd5a  lea     rcx, aOpenprocessFai; "OpenProcess failed"
0x1800bcd61  mov     [rsp+100h+ReturnLength], rcx; unsigned __int16 *
0x1800bcd66  mov     r9d, 87h; unsigned int
0x1800bcd6c  lea     r8, aOnecoreuapNetW_20; "onecoreuap\\net\\wlan\\autocfg\\wlansvc"...
0x1800bcd73  lea     rdx, aCrpcutilitiesG; "CRpcUtilities::GetRpcCallerDetails"
0x1800bcd7a  mov     ecx, eax; int
0x1800bcd7c  call    ?Throw@CWFDSvcException@WFDSvc@@SAXJPEBD0KPEBG@Z; WFDSvc::CWFDSvcException::Throw(long,char const *,char const *,ulong,ushort const *)
0x1800bcd82  mov     [rbp+57h+TokenHandle], 0
0x1800bcd8a  lea     r8, [rbp+57h+TokenHandle]; TokenHandle
0x1800bcd8e  mov     edx, 8; DesiredAccess
0x1800bcd93  mov     rcx, rax; ProcessHandle
0x1800bcd96  call    cs:__imp_OpenProcessToken
0x1800bcd9c  test    eax, eax
0x1800bcd9e  jnz     short loc_1800BCDDA
0x1800bcda0  call    cs:__imp_GetLastError
0x1800bcda6  test    eax, eax
0x1800bcda8  jle     short loc_1800BCDB2
0x1800bcdaa  movzx   eax, ax
0x1800bcdad  or      eax, 80070000h
0x1800bcdb2  lea     rcx, aOpenprocesstok; "OpenProcessToken failed"
0x1800bcdb9  mov     [rsp+100h+ReturnLength], rcx; unsigned __int16 *
0x1800bcdbe  mov     r9d, 8Fh; unsigned int
0x1800bcdc4  lea     r8, aOnecoreuapNetW_20; "onecoreuap\\net\\wlan\\autocfg\\wlansvc"...
0x1800bcdcb  lea     rdx, aCrpcutilitiesG; "CRpcUtilities::GetRpcCallerDetails"
0x1800bcdd2  mov     ecx, eax; int
0x1800bcdd4  call    ?Throw@CWFDSvcException@WFDSvc@@SAXJPEBD0KPEBG@Z; WFDSvc::CWFDSvcException::Throw(long,char const *,char const *,ulong,ushort const *)
0x1800bcdda  test    rdi, rdi
0x1800bcddd  jz      short loc_1800BCE55
0x1800bcddf  mov     [rbp+57h+TokenInformation], 0
0x1800bcde6  mov     [rbp+57h+var_C0], 0
0x1800bcded  lea     rax, [rbp+57h+var_C0]
0x1800bcdf1  mov     [rsp+100h+ReturnLength], rax; ReturnLength
0x1800bcdf6  mov     r9d, 4; TokenInformationLength
0x1800bcdfc  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x1800bce00  lea     edx, [r9+19h]; TokenInformationClass
0x1800bce04  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x1800bce08  call    cs:__imp_GetTokenInformation
0x1800bce0e  test    eax, eax
0x1800bce10  jnz     short loc_1800BCE4C
0x1800bce12  call    cs:__imp_GetLastError
0x1800bce18  test    eax, eax
0x1800bce1a  jle     short loc_1800BCE24
0x1800bce1c  movzx   eax, ax
0x1800bce1f  or      eax, 80070000h
0x1800bce24  lea     rcx, aGettokeninform; "GetTokenInformation failed"
0x1800bce2b  mov     [rsp+100h+ReturnLength], rcx; unsigned __int16 *
0x1800bce30  mov     r9d, 9Fh; unsigned int
0x1800bce36  lea     r8, aOnecoreuapNetW_20; "onecoreuap\\net\\wlan\\autocfg\\wlansvc"...
0x1800bce3d  lea     rdx, aCrpcutilitiesG; "CRpcUtilities::GetRpcCallerDetails"
0x1800bce44  mov     ecx, eax; int
0x1800bce46  call    ?Throw@CWFDSvcException@WFDSvc@@SAXJPEBD0KPEBG@Z; WFDSvc::CWFDSvcException::Throw(long,char const *,char const *,ulong,ushort const *)
0x1800bce4c  cmp     [rbp+57h+TokenInformation], 0
0x1800bce50  setnbe  al
0x1800bce53  mov     [rdi], al
0x1800bce55  test    rbx, rbx
0x1800bce58  jz      short loc_1800BCE67
0x1800bce5a  mov     rdx, rbx; bool *
0x1800bce5d  lea     rcx, [rbp+57h+TokenHandle]; struct COsHandle *
0x1800bce61  call    ?CheckCallerUIModel@CRpcUtilities@@CAXAEBVCOsHandle@@PEA_N@Z; CRpcUtilities::CheckCallerUIModel(COsHandle const &,bool *)
0x1800bce66  nop
0x1800bce67  lea     rcx, [rbp+57h+TokenHandle]; this
0x1800bce6b  call    ??1COsHandle@@QEAA@XZ; COsHandle::~COsHandle(void)
0x1800bce70  nop
0x1800bce71  lea     rcx, [rbp+57h+var_B8]; this
0x1800bce75  call    ??1COsHandle@@QEAA@XZ; COsHandle::~COsHandle(void)
0x1800bce7a  mov     rcx, [rbp+57h+var_40]
0x1800bce7e  xor     rcx, rsp; StackCookie
0x1800bce81  call    __security_check_cookie
0x1800bce86  add     rsp, 0D8h
0x1800bce8d  pop     r14
0x1800bce8f  pop     r13
0x1800bce91  pop     rdi
0x1800bce92  pop     rsi
0x1800bce93  pop     rbx
0x1800bce94  pop     rbp
0x1800bce95  retn
```
