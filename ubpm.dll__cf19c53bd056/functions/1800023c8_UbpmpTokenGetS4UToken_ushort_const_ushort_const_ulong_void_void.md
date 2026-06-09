# UbpmpTokenGetS4UToken(ushort const *,ushort const *,ulong,void * *,void * *)

- ea: `0x1800023c8`
- end: `0x18000295e`
- name: `?UbpmpTokenGetS4UToken@@YAKPEBG0KPEAPEAX1@Z`
- size: `1430`
- prototype: `__int64 __fastcall(const unsigned __int16 *Src, const unsigned __int16 *, __int32 LogonType, void **, void **)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180001fb0`

## callees

- `0x1800023c8`
- `0x18000f9a0`
- `0x180019d90`
- `0x18003c454`
- `0x18003d4ac`
- `0x18003d7d2`
- `0x18003d810`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800027dd`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180002889`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800027dd`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180002889`
- `ntdll!NtAllocateLocallyUniqueId` at `0x1800026d3`
- `ntdll!NtAllocateLocallyUniqueId` at `0x1800026d3`
- `ntdll!RtlNtStatusToDosError` at `0x180002491`
- `ntdll!RtlNtStatusToDosError` at `0x180002506`
- `ntdll!RtlNtStatusToDosError` at `0x1800026df`
- `ntdll!RtlNtStatusToDosError` at `0x18000278f`
- `ntdll!RtlNtStatusToDosError` at `0x180002491`
- `ntdll!RtlNtStatusToDosError` at `0x180002506`
- `ntdll!RtlNtStatusToDosError` at `0x1800026df`
- `ntdll!RtlNtStatusToDosError` at `0x18000278f`
- `ntdll!RtlInitString` at `0x1800024e8`
- `ntdll!RtlInitString` at `0x180002541`
- `ntdll!RtlInitString` at `0x1800024e8`
- `ntdll!RtlInitString` at `0x180002541`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000261f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800027eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800027f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000283d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002893`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000261f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800027eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800027f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000283d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002893`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002917`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002917`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002906`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002906`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000282f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000282f`
- `SspiCli!LsaLookupAuthenticationPackage` at `0x1800024fa`
- `SspiCli!LsaLookupAuthenticationPackage` at `0x1800024fa`
- `SspiCli!LsaLogonUser` at `0x180002770`
- `SspiCli!LsaLogonUser` at `0x180002770`
- `SspiCli!LsaConnectUntrusted` at `0x180002485`
- `SspiCli!LsaConnectUntrusted` at `0x180002485`
- `SspiCli!LsaFreeReturnBuffer` at `0x180002926`
- `SspiCli!LsaFreeReturnBuffer` at `0x180002926`
- `SspiCli!LsaDeregisterLogonProcess` at `0x180002936`
- `SspiCli!LsaDeregisterLogonProcess` at `0x180002936`

## pseudocode

```c
__int64 __fastcall UbpmpTokenGetS4UToken(
        const unsigned __int16 *Src,
        const unsigned __int16 *a2,
        __int32 LogonType,
        void **a4,
        void **a5)
{
  HLOCAL v8; // r12
  _QWORD *AuthenticationInformation; // r14
  int v10; // eax
  ULONG LastError; // ebx
  int v12; // r8d
  _QWORD *v13; // rcx
  int v14; // edx
  int v15; // eax
  unsigned __int64 v16; // rax
  _QWORD *v17; // rcx
  __int64 v18; // rdx
  unsigned __int64 v19; // rcx
  __int64 v20; // rbx
  ULONG v21; // eax
  ULONG AuthenticationInformationLength; // r13d
  _QWORD *v23; // rax
  char *v24; // rbx
  __int16 v25; // ax
  __int16 v26; // ax
  int v27; // eax
  int v28; // eax
  HANDLE v29; // rax
  DWORD ReturnLength; // [rsp+70h] [rbp-90h] BYREF
  HANDLE TokenHandle; // [rsp+78h] [rbp-88h] BYREF
  ULONG AuthenticationPackage; // [rsp+80h] [rbp-80h] BYREF
  int SubStatus; // [rsp+84h] [rbp-7Ch] BYREF
  void *LsaHandle; // [rsp+88h] [rbp-78h] BYREF
  unsigned int v36; // [rsp+90h] [rbp-70h]
  int v37; // [rsp+94h] [rbp-6Ch]
  int v38; // [rsp+98h] [rbp-68h]
  ULONG ProfileBufferLength; // [rsp+9Ch] [rbp-64h] BYREF
  PVOID Buffer; // [rsp+A0h] [rbp-60h] BYREF
  struct _LUID LogonId; // [rsp+A8h] [rbp-58h] BYREF
  void **v42; // [rsp+B0h] [rbp-50h]
  void **v43; // [rsp+B8h] [rbp-48h]
  _STRING DestinationString; // [rsp+C0h] [rbp-40h] BYREF
  struct _STRING v45; // [rsp+D0h] [rbp-30h] BYREF
  LUID LocallyUniqueId[2]; // [rsp+E0h] [rbp-20h] BYREF
  struct _QUOTA_LIMITS Quotas; // [rsp+F0h] [rbp-10h] BYREF

  AuthenticationPackage = 0;
  TokenHandle = (HANDLE)-1LL;
  v43 = a5;
  v42 = a4;
  LsaHandle = (void *)-1LL;
  ReturnLength = 0;
  v8 = 0;
  Buffer = 0;
  AuthenticationInformation = 0;
  LogonId = 0;
  SubStatus = 0;
  ProfileBufferLength = 0;
  DestinationString = 0;
  v45 = 0;
  *(_OWORD *)&LocallyUniqueId[0].LowPart = 0;
  memset(&Quotas, 0, sizeof(Quotas));
  if ( !Src || !a2 || !a4 || !a5 )
  {
    LastError = 87;
    goto LABEL_64;
  }
  *a4 = (void *)-1LL;
  *a5 = 0;
  v10 = LsaConnectUntrusted(&LsaHandle);
  if ( v10 < 0 )
  {
    LastError = RtlNtStatusToDosError(v10);
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v14 = 32;
LABEL_9:
      WPP_SF_SSdL(v13[2], v14, v12, (_DWORD)Src, (__int64)a2, LogonType, LastError);
      goto LABEL_64;
    }
    goto LABEL_64;
  }
  RtlInitString(&DestinationString, "Negotiate");
  v15 = LsaLookupAuthenticationPackage(LsaHandle, (PLSA_STRING)&DestinationString, &AuthenticationPackage);
  if ( v15 < 0 )
  {
    LastError = RtlNtStatusToDosError(v15);
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v14 = 33;
      goto LABEL_9;
    }
    goto LABEL_64;
  }
  RtlInitString(&v45, "AuthzApi");
  v16 = -1;
  do
    ++v16;
  while ( Src[v16] );
  if ( v16 > 0xFFFF )
  {
    LastError = 87;
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_64;
    v18 = 34;
    goto LABEL_20;
  }
  v19 = -1;
  do
    ++v19;
  while ( a2[v19] );
  if ( v19 > 0xFFFF )
  {
    LastError = 87;
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_64;
    v18 = 35;
LABEL_20:
    WPP_SF_L(v17[2], v18, WPP_134408c016563692a0776b6ad2359b4f_Traceguids, 87);
    goto LABEL_64;
  }
  v37 = (unsigned __int16)v16;
  v20 = (unsigned int)(unsigned __int16)v16 + 1;
  v21 = 2 * v20 + 40;
  if ( (unsigned int)(2 * v20) >= 0xFFFFFFD8
    || (v38 = (unsigned __int16)v19,
        v36 = (unsigned __int16)v19 + 1,
        AuthenticationInformationLength = v21 + 2 * v36,
        AuthenticationInformationLength < v21) )
  {
LABEL_28:
    LastError = 534;
    goto LABEL_64;
  }
  v23 = UbpmAlloc(AuthenticationInformationLength);
  AuthenticationInformation = v23;
  if ( !v23 )
  {
    LastError = GetLastError();
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v14 = 36;
      goto LABEL_9;
    }
    goto LABEL_64;
  }
  *v23 = 12;
  memcpy_0(v23 + 5, Src, 2 * v20);
  v24 = (char *)AuthenticationInformation + 2 * v20 + 40;
  memcpy_0(v24, a2, 2LL * v36);
  v25 = 2 * v37;
  if ( (unsigned int)(2 * v37) > 0xFFFF )
  {
    *((_WORD *)AuthenticationInformation + 4) = -1;
    goto LABEL_28;
  }
  *((_WORD *)AuthenticationInformation + 4) = v25;
  *((_WORD *)AuthenticationInformation + 5) = v25;
  AuthenticationInformation[2] = AuthenticationInformation + 5;
  v26 = 2 * v38;
  if ( (unsigned int)(2 * v38) > 0xFFFF )
  {
    *((_WORD *)AuthenticationInformation + 12) = -1;
    goto LABEL_28;
  }
  *((_WORD *)AuthenticationInformation + 12) = v26;
  *((_WORD *)AuthenticationInformation + 13) = v26;
  AuthenticationInformation[4] = v24;
  LocallyUniqueId[0] = (LUID)0x2020204D5042552ELL;
  v27 = NtAllocateLocallyUniqueId(&LocallyUniqueId[1]);
  if ( v27 >= 0 )
  {
    v28 = LsaLogonUser(
            LsaHandle,
            (PLSA_STRING)&v45,
            (SECURITY_LOGON_TYPE)LogonType,
            AuthenticationPackage,
            AuthenticationInformation,
            AuthenticationInformationLength,
            0,
            (PTOKEN_SOURCE)LocallyUniqueId,
            &Buffer,
            &ProfileBufferLength,
            &LogonId,
            &TokenHandle,
            &Quotas,
            &SubStatus);
    if ( v28 >= 0 )
    {
      if ( !GetTokenInformation(TokenHandle, TokenLogonSid, 0, 0, &ReturnLength) )
      {
        if ( GetLastError() != 122 )
        {
          LastError = GetLastError();
          v13 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v14 = 39;
            goto LABEL_9;
          }
          goto LABEL_64;
        }
        v8 = LocalAlloc(0, ReturnLength);
        if ( !v8 )
        {
          LastError = GetLastError();
          v13 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v14 = 40;
            goto LABEL_9;
          }
          goto LABEL_64;
        }
      }
      if ( GetTokenInformation(TokenHandle, TokenLogonSid, v8, ReturnLength, &ReturnLength) )
      {
        v29 = TokenHandle;
        LastError = 0;
        TokenHandle = (HANDLE)-1LL;
        *v42 = v29;
        *v43 = v8;
        v8 = 0;
      }
      else
      {
        LastError = GetLastError();
        v13 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v14 = 41;
          goto LABEL_9;
        }
      }
      goto LABEL_64;
    }
    if ( v28 == -1073741715 && SubStatus == -1073741730 )
      v28 = -1073741730;
    LastError = RtlNtStatusToDosError(v28);
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v14 = 38;
      goto LABEL_9;
    }
  }
  else
  {
    LastError = RtlNtStatusToDosError(v27);
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v14 = 37;
      goto LABEL_9;
    }
  }
LABEL_64:
  UBPM_MIDL_user_free(AuthenticationInformation);
  LocalFree(v8);
  if ( TokenHandle != (HANDLE)-1LL )
    CloseHandle(TokenHandle);
  if ( Buffer )
    LsaFreeReturnBuffer(Buffer);
  if ( LsaHandle != (void *)-1LL )
    LsaDeregisterLogonProcess(LsaHandle);
  return LastError;
}

```

## disassembly

```asm
0x1800023c8  push    rbp
0x1800023ca  push    rbx
0x1800023cb  push    rsi
0x1800023cc  push    rdi
0x1800023cd  push    r12
0x1800023cf  push    r13
0x1800023d1  push    r14
0x1800023d3  push    r15
0x1800023d5  lea     rbp, [rsp-38h]
0x1800023da  sub     rsp, 138h
0x1800023e1  mov     rax, cs:__security_cookie
0x1800023e8  xor     rax, rsp
0x1800023eb  mov     [rbp+70h+var_50], rax
0x1800023ef  xor     r13d, r13d
0x1800023f2  xorps   xmm0, xmm0
0x1800023f5  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800023f9  mov     [rbp+70h+AuthenticationPackage], r13d
0x1800023fd  mov     rsi, rcx
0x180002400  mov     [rsp+170h+TokenHandle], rbx
0x180002405  mov     rcx, [rbp+70h+arg_20]
0x18000240c  mov     rax, r9
0x18000240f  mov     [rbp+70h+var_B8], rcx
0x180002413  xorps   xmm1, xmm1
0x180002416  mov     [rbp+70h+var_C0], rax
0x18000241a  mov     r15d, r8d
0x18000241d  mov     [rbp+70h+LsaHandle], rbx
0x180002421  mov     rdi, rdx
0x180002424  mov     [rsp+170h+ReturnLength], r13d
0x180002429  mov     r12d, r13d
0x18000242c  mov     [rbp+70h+Buffer], r13
0x180002430  mov     r14d, r13d
0x180002433  mov     qword ptr [rbp+70h+var_C8.LowPart], r13
0x180002437  mov     [rbp+70h+var_EC], r13d
0x18000243b  mov     [rbp+70h+var_D4], r13d
0x18000243f  movups  xmmword ptr [rbp+70h+DestinationString.Length], xmm0
0x180002443  movups  xmmword ptr [rbp+70h+var_A0.Length], xmm1
0x180002447  movups  xmmword ptr [rbp+70h+LocallyUniqueId.LowPart], xmm0
0x18000244b  movups  xmmword ptr [rbp+70h+var_80.PagedPoolLimit], xmm0
0x18000244f  movups  xmmword ptr [rbp+70h+var_80.MinimumWorkingSetSize], xmm0
0x180002453  movups  xmmword ptr [rbp+70h+var_80.PagefileLimit], xmm0
0x180002457  test    rsi, rsi
0x18000245a  jz      loc_1800028F6
0x180002460  test    rdx, rdx
0x180002463  jz      loc_1800028F6
0x180002469  test    rax, rax
0x18000246c  jz      loc_1800028F6
0x180002472  test    rcx, rcx
0x180002475  jz      loc_1800028F6
0x18000247b  mov     [r9], rbx
0x18000247e  mov     [rcx], r13
0x180002481  lea     rcx, [rbp+70h+LsaHandle]; LsaHandle
0x180002485  call    cs:__imp_LsaConnectUntrusted
0x18000248b  test    eax, eax
0x18000248d  jns     short loc_1800024DD
0x18000248f  mov     ecx, eax; Status
0x180002491  call    cs:__imp_RtlNtStatusToDosError
0x180002497  mov     ebx, eax
0x180002499  mov     rcx, cs:WPP_GLOBAL_Control
0x1800024a0  lea     rax, WPP_GLOBAL_Control
0x1800024a7  cmp     rcx, rax
0x1800024aa  jz      loc_1800028FB
0x1800024b0  test    byte ptr [rcx+1Ch], 1
0x1800024b4  jz      loc_1800028FB
0x1800024ba  lea     edx, [r13+20h]
0x1800024be  mov     rcx, [rcx+10h]
0x1800024c2  mov     r9, rsi
0x1800024c5  mov     dword ptr [rsp+170h+LocalGroups], ebx
0x1800024c9  mov     [rsp+170h+AuthenticationInformationLength], r15d
0x1800024ce  mov     [rsp+170h+AuthenticationInformation], rdi
0x1800024d3  call    WPP_SF_SSdL
0x1800024d8  jmp     loc_1800028FB
0x1800024dd  lea     rdx, SourceString; "Negotiate"
0x1800024e4  lea     rcx, [rbp+70h+DestinationString]; DestinationString
0x1800024e8  call    cs:__imp_RtlInitString
0x1800024ee  mov     rcx, [rbp+70h+LsaHandle]; LsaHandle
0x1800024f2  lea     r8, [rbp+70h+AuthenticationPackage]; AuthenticationPackage
0x1800024f6  lea     rdx, [rbp+70h+DestinationString]; PackageName
0x1800024fa  call    cs:__imp_LsaLookupAuthenticationPackage
0x180002500  test    eax, eax
0x180002502  jns     short loc_180002536
0x180002504  mov     ecx, eax; Status
0x180002506  call    cs:__imp_RtlNtStatusToDosError
0x18000250c  mov     ebx, eax
0x18000250e  mov     rcx, cs:WPP_GLOBAL_Control
0x180002515  lea     rax, WPP_GLOBAL_Control
0x18000251c  cmp     rcx, rax
0x18000251f  jz      loc_1800028FB
0x180002525  test    byte ptr [rcx+1Ch], 1
0x180002529  jz      loc_1800028FB
0x18000252f  mov     edx, 21h ; '!'
0x180002534  jmp     short loc_1800024BE
0x180002536  lea     rdx, aAuthzapi; "AuthzApi"
0x18000253d  lea     rcx, [rbp+70h+var_A0]; DestinationString
0x180002541  call    cs:__imp_RtlInitString
0x180002547  mov     rax, rbx
0x18000254a  inc     rax
0x18000254d  cmp     [rsi+rax*2], r13w
0x180002552  jnz     short loc_18000254A
0x180002554  mov     edx, 0FFFFh
0x180002559  cmp     rax, rdx
0x18000255c  jbe     short loc_18000259F
0x18000255e  mov     ebx, 57h ; 'W'
0x180002563  mov     rcx, cs:WPP_GLOBAL_Control
0x18000256a  lea     rax, WPP_GLOBAL_Control
0x180002571  cmp     rcx, rax
0x180002574  jz      loc_1800028FB
0x18000257a  test    byte ptr [rcx+1Ch], 1
0x18000257e  jz      loc_1800028FB
0x180002584  lea     edx, [rbx-35h]
0x180002587  mov     rcx, [rcx+10h]
0x18000258b  lea     r8, WPP_134408c016563692a0776b6ad2359b4f_Traceguids
0x180002592  mov     r9d, ebx
0x180002595  call    WPP_SF_L
0x18000259a  jmp     loc_1800028FB
0x18000259f  mov     rcx, rbx
0x1800025a2  inc     rcx
0x1800025a5  cmp     [rdi+rcx*2], r13w
0x1800025aa  jnz     short loc_1800025A2
0x1800025ac  cmp     rcx, rdx
0x1800025af  jbe     short loc_1800025DC
0x1800025b1  mov     ebx, 57h ; 'W'
0x1800025b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800025bd  lea     rax, WPP_GLOBAL_Control
0x1800025c4  cmp     rcx, rax
0x1800025c7  jz      loc_1800028FB
0x1800025cd  test    byte ptr [rcx+1Ch], 1
0x1800025d1  jz      loc_1800028FB
0x1800025d7  lea     edx, [rbx-34h]
0x1800025da  jmp     short loc_180002587
0x1800025dc  movzx   eax, ax
0x1800025df  mov     [rbp+70h+var_DC], eax
0x1800025e2  lea     ebx, [rax+1]
0x1800025e5  lea     eax, ds:28h[rbx*2]
0x1800025ec  cmp     eax, 28h ; '('
0x1800025ef  jnb     short loc_1800025FB
0x1800025f1  mov     ebx, 216h
0x1800025f6  jmp     loc_1800028FB
0x1800025fb  movzx   ecx, cx
0x1800025fe  mov     [rbp+70h+var_D8], ecx
0x180002601  inc     ecx
0x180002603  mov     [rbp+70h+var_E0], ecx
0x180002606  lea     r13d, [rax+rcx*2]
0x18000260a  cmp     r13d, eax
0x18000260d  jb      short loc_1800025F1
0x18000260f  mov     ecx, r13d; Size
0x180002612  call    ?UbpmAlloc@@YAPEAXK@Z; UbpmAlloc(ulong)
0x180002617  mov     r14, rax
0x18000261a  test    rax, rax
0x18000261d  jnz     short loc_180002651
0x18000261f  call    cs:__imp_GetLastError
0x180002625  mov     ebx, eax
0x180002627  mov     rcx, cs:WPP_GLOBAL_Control
0x18000262e  lea     rax, WPP_GLOBAL_Control
0x180002635  cmp     rcx, rax
0x180002638  jz      loc_1800028FB
0x18000263e  test    byte ptr [rcx+1Ch], 1
0x180002642  jz      loc_1800028FB
0x180002648  lea     edx, [r14+24h]
0x18000264c  jmp     loc_1800024BE
0x180002651  lea     rcx, [rax+28h]; void *
0x180002655  mov     qword ptr [rax], 0Ch
0x18000265c  lea     r8, [rbx+rbx]; Size
0x180002660  mov     rdx, rsi; Src
0x180002663  call    memcpy_0
0x180002668  mov     r8d, [rbp+70h+var_E0]
0x18000266c  add     rbx, 14h
0x180002670  add     r8, r8; Size
0x180002673  mov     rdx, rdi; Src
0x180002676  lea     rbx, [r14+rbx*2]
0x18000267a  mov     rcx, rbx; void *
0x18000267d  call    memcpy_0
0x180002682  mov     eax, [rbp+70h+var_DC]
0x180002685  mov     ecx, 0FFFFh
0x18000268a  add     eax, eax
0x18000268c  cmp     eax, ecx
0x18000268e  ja      loc_1800028EC
0x180002694  mov     [r14+8], ax
0x180002699  mov     [r14+0Ah], ax
0x18000269e  lea     rax, [r14+28h]
0x1800026a2  mov     [r14+10h], rax
0x1800026a6  mov     eax, [rbp+70h+var_D8]
0x1800026a9  add     eax, eax
0x1800026ab  cmp     eax, ecx
0x1800026ad  ja      loc_1800028E2
0x1800026b3  mov     [r14+18h], ax
0x1800026b8  lea     rcx, [rbp+70h+LocallyUniqueId.LowPart+8]; LocallyUniqueId
0x1800026bc  mov     [r14+1Ah], ax
0x1800026c1  mov     rax, 2020204D5042552Eh
0x1800026cb  mov     [r14+20h], rbx
0x1800026cf  mov     qword ptr [rbp+70h+LocallyUniqueId.LowPart], rax
0x1800026d3  call    cs:__imp_NtAllocateLocallyUniqueId
0x1800026d9  test    eax, eax
0x1800026db  jns     short loc_180002712
0x1800026dd  mov     ecx, eax; Status
0x1800026df  call    cs:__imp_RtlNtStatusToDosError
0x1800026e5  mov     ebx, eax
0x1800026e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800026ee  lea     rax, WPP_GLOBAL_Control
0x1800026f5  cmp     rcx, rax
0x1800026f8  jz      loc_1800028FB
0x1800026fe  test    byte ptr [rcx+1Ch], 1
0x180002702  jz      loc_1800028FB
0x180002708  mov     edx, 25h ; '%'
0x18000270d  jmp     loc_1800024BE
0x180002712  mov     r9d, [rbp+70h+AuthenticationPackage]; AuthenticationPackage
0x180002716  lea     rax, [rbp+70h+var_EC]
0x18000271a  mov     rcx, [rbp+70h+LsaHandle]; LsaHandle
0x18000271e  lea     rdx, [rbp+70h+var_A0]; OriginName
0x180002722  mov     [rsp+170h+SubStatus], rax; SubStatus
0x180002727  mov     r8d, r15d; LogonType
0x18000272a  lea     rax, [rbp+70h+var_80]
0x18000272e  mov     [rsp+170h+Quotas], rax; Quotas
0x180002733  lea     rax, [rsp+170h+TokenHandle]
0x180002738  mov     [rsp+170h+Token], rax; Token
0x18000273d  lea     rax, [rbp+70h+var_C8]
0x180002741  mov     [rsp+170h+LogonId], rax; LogonId
0x180002746  lea     rax, [rbp+70h+var_D4]
0x18000274a  mov     [rsp+170h+ProfileBufferLength], rax; ProfileBufferLength
0x18000274f  lea     rax, [rbp+70h+Buffer]
0x180002753  mov     [rsp+170h+ProfileBuffer], rax; ProfileBuffer
0x180002758  lea     rax, [rbp+70h+LocallyUniqueId]
0x18000275c  mov     [rsp+170h+SourceContext], rax; SourceContext
0x180002761  mov     [rsp+170h+LocalGroups], r12; LocalGroups
0x180002766  mov     [rsp+170h+AuthenticationInformationLength], r13d; AuthenticationInformationLength
0x18000276b  mov     [rsp+170h+AuthenticationInformation], r14; AuthenticationInformation
0x180002770  call    cs:__imp_LsaLogonUser
0x180002776  xor     r13d, r13d
0x180002779  test    eax, eax
0x18000277b  jns     short loc_1800027C2
0x18000277d  cmp     eax, 0C000006Dh
0x180002782  jnz     short loc_18000278D
0x180002784  lea     ecx, [rax-0Fh]
0x180002787  cmp     [rbp+70h+var_EC], ecx
0x18000278a  cmovz   eax, ecx
0x18000278d  mov     ecx, eax; Status
0x18000278f  call    cs:__imp_RtlNtStatusToDosError
0x180002795  mov     ebx, eax
0x180002797  mov     rcx, cs:WPP_GLOBAL_Control
0x18000279e  lea     rax, WPP_GLOBAL_Control
0x1800027a5  cmp     rcx, rax
0x1800027a8  jz      loc_1800028FB
0x1800027ae  test    byte ptr [rcx+1Ch], 1
0x1800027b2  jz      loc_1800028FB
0x1800027b8  mov     edx, 26h ; '&'
0x1800027bd  jmp     loc_1800024BE
0x1800027c2  mov     rcx, [rsp+170h+TokenHandle]; TokenHandle
0x1800027c7  lea     rax, [rsp+170h+ReturnLength]
0x1800027cc  xor     r9d, r9d; TokenInformationLength
0x1800027cf  mov     [rsp+170h+AuthenticationInformation], rax; ReturnLength
0x1800027d4  xor     r8d, r8d; TokenInformation
0x1800027d7  lea     ebx, [r9+1Ch]
0x1800027db  mov     edx, ebx; TokenInformationClass
0x1800027dd  call    cs:__imp_GetTokenInformation
0x1800027e3  test    eax, eax
0x1800027e5  jnz     loc_180002870
0x1800027eb  call    cs:__imp_GetLastError
0x1800027f1  cmp     eax, 7Ah ; 'z'
0x1800027f4  jz      short loc_180002829
0x1800027f6  call    cs:__imp_GetLastError
0x1800027fc  mov     ebx, eax
0x1800027fe  mov     rcx, cs:WPP_GLOBAL_Control
0x180002805  lea     rax, WPP_GLOBAL_Control
0x18000280c  cmp     rcx, rax
0x18000280f  jz      loc_1800028FB
0x180002815  test    byte ptr [rcx+1Ch], 1
0x180002819  jz      loc_1800028FB
0x18000281f  mov     edx, 27h ; '''
0x180002824  jmp     loc_1800024BE
0x180002829  mov     edx, [rsp+170h+ReturnLength]; uBytes
0x18000282d  xor     ecx, ecx; uFlags
0x18000282f  call    cs:__imp_LocalAlloc
0x180002835  mov     r12, rax
0x180002838  test    rax, rax
0x18000283b  jnz     short loc_180002870
0x18000283d  call    cs:__imp_GetLastError
0x180002843  mov     ebx, eax
0x180002845  mov     rcx, cs:WPP_GLOBAL_Control
0x18000284c  lea     rax, WPP_GLOBAL_Control
0x180002853  cmp     rcx, rax
0x180002856  jz      loc_1800028FB
0x18000285c  test    byte ptr [rcx+1Ch], 1
0x180002860  jz      loc_1800028FB
0x180002866  lea     edx, [r12+28h]
0x18000286b  jmp     loc_1800024BE
0x180002870  mov     r9d, [rsp+170h+ReturnLength]; TokenInformationLength
0x180002875  lea     rax, [rsp+170h+ReturnLength]
0x18000287a  mov     rcx, [rsp+170h+TokenHandle]; TokenHandle
0x18000287f  mov     r8, r12; TokenInformation
0x180002882  mov     edx, ebx; TokenInformationClass
0x180002884  mov     [rsp+170h+AuthenticationInformation], rax; ReturnLength
0x180002889  call    cs:__imp_GetTokenInformation
0x18000288f  test    eax, eax
0x180002891  jnz     short loc_1800028BE
0x180002893  call    cs:__imp_GetLastError
0x180002899  mov     ebx, eax
0x18000289b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800028a2  lea     rax, WPP_GLOBAL_Control
0x1800028a9  cmp     rcx, rax
0x1800028ac  jz      short loc_1800028FB
0x1800028ae  test    byte ptr [rcx+1Ch], 1
  ... truncated ...
```
