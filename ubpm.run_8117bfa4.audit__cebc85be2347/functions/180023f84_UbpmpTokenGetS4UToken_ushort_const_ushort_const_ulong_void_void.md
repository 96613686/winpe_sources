# UbpmpTokenGetS4UToken(ushort const *,ushort const *,ulong,void * *,void * *)

- ea: `0x180023f84`
- end: `0x1800245a2`
- name: `?UbpmpTokenGetS4UToken@@YAKPEBG0KPEAPEAX1@Z`
- size: `1566`
- prototype: `unsigned int __usercall@<eax>(const unsigned __int16 *Src@<rcx>, const unsigned __int16 *@<rdx>, SECURITY_LOGON_TYPE LogonType@<r8d>, void **@<r9>, void **)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180023b50`

## callees

- `0x18000fbf0`
- `0x1800150c0`
- `0x180023f84`
- `0x18003edd8`
- `0x18003fee8`
- `0x180040222`
- `0x180040260`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800243de`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800244a8`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800243de`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800244a8`
- `ntdll!NtAllocateLocallyUniqueId` at `0x1800242bc`
- `ntdll!NtAllocateLocallyUniqueId` at `0x1800242bc`
- `ntdll!RtlNtStatusToDosError` at `0x180024053`
- `ntdll!RtlNtStatusToDosError` at `0x1800240da`
- `ntdll!RtlNtStatusToDosError` at `0x1800242ce`
- `ntdll!RtlNtStatusToDosError` at `0x18002438a`
- `ntdll!RtlNtStatusToDosError` at `0x180024053`
- `ntdll!RtlNtStatusToDosError` at `0x1800240da`
- `ntdll!RtlNtStatusToDosError` at `0x1800242ce`
- `ntdll!RtlNtStatusToDosError` at `0x18002438a`
- `ntdll!RtlInitString` at `0x1800240b0`
- `ntdll!RtlInitString` at `0x18002411e`
- `ntdll!RtlInitString` at `0x1800240b0`
- `ntdll!RtlInitString` at `0x18002411e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024202`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800243f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024403`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024456`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800244b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024202`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800243f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024403`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024456`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800244b8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024548`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024548`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024531`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024531`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180024442`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180024442`
- `SspiCli!LsaLookupAuthenticationPackage` at `0x1800240c8`
- `SspiCli!LsaLookupAuthenticationPackage` at `0x1800240c8`
- `SspiCli!LsaLogonUser` at `0x180024365`
- `SspiCli!LsaLogonUser` at `0x180024365`
- `SspiCli!LsaConnectUntrusted` at `0x180024041`
- `SspiCli!LsaConnectUntrusted` at `0x180024041`
- `SspiCli!LsaFreeReturnBuffer` at `0x18002455d`
- `SspiCli!LsaFreeReturnBuffer` at `0x18002455d`
- `SspiCli!LsaDeregisterLogonProcess` at `0x180024573`
- `SspiCli!LsaDeregisterLogonProcess` at `0x180024573`

## pseudocode

```c
__int64 __fastcall UbpmpTokenGetS4UToken(
        const unsigned __int16 *Src,
        __int64 a2,
        __int64 LogonType,
        void **a4,
        void **a5)
{
  SECURITY_LOGON_TYPE v6; // r15d
  const unsigned __int16 *v7; // rdi
  HLOCAL v8; // r12
  _QWORD *AuthenticationInformation; // r14
  int v10; // eax
  ULONG LastError; // ebx
  _QWORD *v12; // rcx
  int v13; // edx
  int v14; // eax
  unsigned __int64 v15; // rax
  _QWORD *v16; // rcx
  __int64 v17; // rdx
  unsigned __int64 v18; // rcx
  __int64 v19; // rbx
  ULONG v20; // eax
  ULONG AuthenticationInformationLength; // r13d
  _QWORD *v22; // rax
  char *v23; // rbx
  __int16 v24; // ax
  __int16 v25; // ax
  int v26; // eax
  int v27; // eax
  HANDLE v28; // rax
  DWORD ReturnLength; // [rsp+70h] [rbp-90h] BYREF
  HANDLE TokenHandle; // [rsp+78h] [rbp-88h] BYREF
  ULONG AuthenticationPackage; // [rsp+80h] [rbp-80h] BYREF
  int SubStatus; // [rsp+84h] [rbp-7Ch] BYREF
  void *LsaHandle; // [rsp+88h] [rbp-78h] BYREF
  unsigned int v35; // [rsp+90h] [rbp-70h]
  int v36; // [rsp+94h] [rbp-6Ch]
  int v37; // [rsp+98h] [rbp-68h]
  ULONG ProfileBufferLength; // [rsp+9Ch] [rbp-64h] BYREF
  PVOID Buffer; // [rsp+A0h] [rbp-60h] BYREF
  struct _LUID LogonId; // [rsp+A8h] [rbp-58h] BYREF
  void **v41; // [rsp+B0h] [rbp-50h]
  void **v42; // [rsp+B8h] [rbp-48h]
  _STRING DestinationString; // [rsp+C0h] [rbp-40h] BYREF
  struct _STRING v44; // [rsp+D0h] [rbp-30h] BYREF
  LUID LocallyUniqueId[2]; // [rsp+E0h] [rbp-20h] BYREF
  struct _QUOTA_LIMITS Quotas; // [rsp+F0h] [rbp-10h] BYREF

  AuthenticationPackage = 0;
  TokenHandle = (HANDLE)-1LL;
  v42 = a5;
  v41 = a4;
  v6 = (int)LogonType;
  LsaHandle = (void *)-1LL;
  v7 = (const unsigned __int16 *)a2;
  ReturnLength = 0;
  v8 = 0;
  Buffer = 0;
  AuthenticationInformation = 0;
  LogonId = 0;
  SubStatus = 0;
  ProfileBufferLength = 0;
  DestinationString = 0;
  v44 = 0;
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
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v13 = 32;
LABEL_9:
      WPP_SF_SSdL(v12[2], v13, LogonType, (_DWORD)Src, (__int64)v7, v6, LastError);
      goto LABEL_64;
    }
    goto LABEL_64;
  }
  RtlInitString(&DestinationString, "Negotiate");
  v14 = LsaLookupAuthenticationPackage(LsaHandle, (PLSA_STRING)&DestinationString, &AuthenticationPackage);
  if ( v14 < 0 )
  {
    LastError = RtlNtStatusToDosError(v14);
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v13 = 33;
      goto LABEL_9;
    }
    goto LABEL_64;
  }
  RtlInitString(&v44, "AuthzApi");
  v15 = -1;
  do
    ++v15;
  while ( Src[v15] );
  a2 = 0xFFFF;
  if ( v15 > 0xFFFF )
  {
    LastError = 87;
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_64;
    v17 = 34;
    goto LABEL_20;
  }
  v18 = -1;
  do
    ++v18;
  while ( v7[v18] );
  if ( v18 > 0xFFFF )
  {
    LastError = 87;
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_64;
    v17 = 35;
LABEL_20:
    WPP_SF_L(v16[2], v17, WPP_134408c016563692a0776b6ad2359b4f_Traceguids, 87);
    goto LABEL_64;
  }
  v36 = (unsigned __int16)v15;
  v19 = (unsigned int)(unsigned __int16)v15 + 1;
  v20 = 2 * v19 + 40;
  if ( (unsigned int)(2 * v19) >= 0xFFFFFFD8
    || (v37 = (unsigned __int16)v18,
        v35 = (unsigned __int16)v18 + 1,
        AuthenticationInformationLength = v20 + 2 * v35,
        AuthenticationInformationLength < v20) )
  {
LABEL_28:
    LastError = 534;
    goto LABEL_64;
  }
  v22 = UbpmAlloc(AuthenticationInformationLength);
  AuthenticationInformation = v22;
  if ( !v22 )
  {
    LastError = GetLastError();
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v13 = 36;
      goto LABEL_9;
    }
    goto LABEL_64;
  }
  *v22 = 12;
  memcpy_0(v22 + 5, Src, 2 * v19);
  v23 = (char *)AuthenticationInformation + 2 * v19 + 40;
  memcpy_0(v23, v7, 2LL * v35);
  v24 = 2 * v36;
  if ( (unsigned int)(2 * v36) > 0xFFFF )
  {
    *((_WORD *)AuthenticationInformation + 4) = -1;
    goto LABEL_28;
  }
  *((_WORD *)AuthenticationInformation + 4) = v24;
  *((_WORD *)AuthenticationInformation + 5) = v24;
  AuthenticationInformation[2] = AuthenticationInformation + 5;
  v25 = 2 * v37;
  if ( (unsigned int)(2 * v37) > 0xFFFF )
  {
    *((_WORD *)AuthenticationInformation + 12) = -1;
    goto LABEL_28;
  }
  *((_WORD *)AuthenticationInformation + 12) = v25;
  *((_WORD *)AuthenticationInformation + 13) = v25;
  AuthenticationInformation[4] = v23;
  LocallyUniqueId[0] = (LUID)0x2020204D5042552ELL;
  v26 = NtAllocateLocallyUniqueId(&LocallyUniqueId[1]);
  if ( v26 >= 0 )
  {
    v27 = LsaLogonUser(
            LsaHandle,
            (PLSA_STRING)&v44,
            v6,
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
    if ( v27 >= 0 )
    {
      if ( !GetTokenInformation(TokenHandle, TokenLogonSid, 0, 0, &ReturnLength) )
      {
        if ( GetLastError() != 122 )
        {
          LastError = GetLastError();
          v12 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v13 = 39;
            goto LABEL_9;
          }
          goto LABEL_64;
        }
        v8 = LocalAlloc(0, ReturnLength);
        if ( !v8 )
        {
          LastError = GetLastError();
          v12 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v13 = 40;
            goto LABEL_9;
          }
          goto LABEL_64;
        }
      }
      if ( GetTokenInformation(TokenHandle, TokenLogonSid, v8, ReturnLength, &ReturnLength) )
      {
        v28 = TokenHandle;
        LastError = 0;
        TokenHandle = (HANDLE)-1LL;
        *v41 = v28;
        *v42 = v8;
        v8 = 0;
      }
      else
      {
        LastError = GetLastError();
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v13 = 41;
          goto LABEL_9;
        }
      }
      goto LABEL_64;
    }
    if ( v27 == -1073741715 && SubStatus == -1073741730 )
      v27 = -1073741730;
    LastError = RtlNtStatusToDosError(v27);
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v13 = 38;
      goto LABEL_9;
    }
  }
  else
  {
    LastError = RtlNtStatusToDosError(v26);
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v13 = 37;
      goto LABEL_9;
    }
  }
LABEL_64:
  UBPM_MIDL_user_free(AuthenticationInformation, a2, LogonType, a4);
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
0x180023f84  push    rbp
0x180023f86  push    rbx
0x180023f87  push    rsi
0x180023f88  push    rdi
0x180023f89  push    r12
0x180023f8b  push    r13
0x180023f8d  push    r14
0x180023f8f  push    r15
0x180023f91  lea     rbp, [rsp-38h]
0x180023f96  sub     rsp, 138h
0x180023f9d  mov     rax, cs:__security_cookie
0x180023fa4  xor     rax, rsp
0x180023fa7  mov     [rbp+70h+var_50], rax
0x180023fab  xor     r13d, r13d
0x180023fae  xorps   xmm0, xmm0
0x180023fb1  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180023fb5  mov     [rbp+70h+AuthenticationPackage], r13d
0x180023fb9  mov     rsi, rcx
0x180023fbc  mov     [rsp+170h+TokenHandle], rbx
0x180023fc1  mov     rcx, [rbp+70h+arg_20]
0x180023fc8  mov     rax, r9
0x180023fcb  mov     [rbp+70h+var_B8], rcx
0x180023fcf  xorps   xmm1, xmm1
0x180023fd2  mov     [rbp+70h+var_C0], rax
0x180023fd6  mov     r15d, r8d
0x180023fd9  mov     [rbp+70h+LsaHandle], rbx
0x180023fdd  mov     rdi, rdx
0x180023fe0  mov     [rsp+170h+ReturnLength], r13d
0x180023fe5  mov     r12d, r13d
0x180023fe8  mov     [rbp+70h+Buffer], r13
0x180023fec  mov     r14d, r13d
0x180023fef  mov     qword ptr [rbp+70h+var_C8.LowPart], r13
0x180023ff3  mov     [rbp+70h+var_EC], r13d
0x180023ff7  mov     [rbp+70h+var_D4], r13d
0x180023ffb  movups  xmmword ptr [rbp+70h+DestinationString.Length], xmm0
0x180023fff  movups  xmmword ptr [rbp+70h+var_A0.Length], xmm1
0x180024003  movups  xmmword ptr [rbp+70h+LocallyUniqueId.LowPart], xmm0
0x180024007  movups  xmmword ptr [rbp+70h+var_80.PagedPoolLimit], xmm0
0x18002400b  movups  xmmword ptr [rbp+70h+var_80.MinimumWorkingSetSize], xmm0
0x18002400f  movups  xmmword ptr [rbp+70h+var_80.PagefileLimit], xmm0
0x180024013  test    rsi, rsi
0x180024016  jz      loc_180024521
0x18002401c  test    rdx, rdx
0x18002401f  jz      loc_180024521
0x180024025  test    rax, rax
0x180024028  jz      loc_180024521
0x18002402e  test    rcx, rcx
0x180024031  jz      loc_180024521
0x180024037  mov     [r9], rbx
0x18002403a  mov     [rcx], r13
0x18002403d  lea     rcx, [rbp+70h+LsaHandle]; LsaHandle
0x180024041  call    cs:__imp_LsaConnectUntrusted
0x180024048  nop     dword ptr [rax+rax+00h]
0x18002404d  test    eax, eax
0x18002404f  jns     short loc_1800240A5
0x180024051  mov     ecx, eax; Status
0x180024053  call    cs:__imp_RtlNtStatusToDosError
0x18002405a  nop     dword ptr [rax+rax+00h]
0x18002405f  mov     ebx, eax
0x180024061  mov     rcx, cs:WPP_GLOBAL_Control
0x180024068  lea     rax, WPP_GLOBAL_Control
0x18002406f  cmp     rcx, rax
0x180024072  jz      loc_180024526
0x180024078  test    byte ptr [rcx+1Ch], 1
0x18002407c  jz      loc_180024526
0x180024082  lea     edx, [r13+20h]
0x180024086  mov     rcx, [rcx+10h]
0x18002408a  mov     r9, rsi
0x18002408d  mov     dword ptr [rsp+170h+LocalGroups], ebx
0x180024091  mov     [rsp+170h+AuthenticationInformationLength], r15d
0x180024096  mov     [rsp+170h+AuthenticationInformation], rdi
0x18002409b  call    WPP_SF_SSdL
0x1800240a0  jmp     loc_180024526
0x1800240a5  lea     rdx, SourceString; "Negotiate"
0x1800240ac  lea     rcx, [rbp+70h+DestinationString]; DestinationString
0x1800240b0  call    cs:__imp_RtlInitString
0x1800240b7  nop     dword ptr [rax+rax+00h]
0x1800240bc  mov     rcx, [rbp+70h+LsaHandle]; LsaHandle
0x1800240c0  lea     r8, [rbp+70h+AuthenticationPackage]; AuthenticationPackage
0x1800240c4  lea     rdx, [rbp+70h+DestinationString]; PackageName
0x1800240c8  call    cs:__imp_LsaLookupAuthenticationPackage
0x1800240cf  nop     dword ptr [rax+rax+00h]
0x1800240d4  test    eax, eax
0x1800240d6  jns     short loc_180024113
0x1800240d8  mov     ecx, eax; Status
0x1800240da  call    cs:__imp_RtlNtStatusToDosError
0x1800240e1  nop     dword ptr [rax+rax+00h]
0x1800240e6  mov     ebx, eax
0x1800240e8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800240ef  lea     rax, WPP_GLOBAL_Control
0x1800240f6  cmp     rcx, rax
0x1800240f9  jz      loc_180024526
0x1800240ff  test    byte ptr [rcx+1Ch], 1
0x180024103  jz      loc_180024526
0x180024109  mov     edx, 21h ; '!'
0x18002410e  jmp     loc_180024086
0x180024113  lea     rdx, aAuthzapi; "AuthzApi"
0x18002411a  lea     rcx, [rbp+70h+var_A0]; DestinationString
0x18002411e  call    cs:__imp_RtlInitString
0x180024125  nop     dword ptr [rax+rax+00h]
0x18002412a  mov     rax, rbx
0x18002412d  inc     rax
0x180024130  cmp     [rsi+rax*2], r13w
0x180024135  jnz     short loc_18002412D
0x180024137  mov     edx, 0FFFFh
0x18002413c  cmp     rax, rdx
0x18002413f  jbe     short loc_180024182
0x180024141  mov     ebx, 57h ; 'W'
0x180024146  mov     rcx, cs:WPP_GLOBAL_Control
0x18002414d  lea     rax, WPP_GLOBAL_Control
0x180024154  cmp     rcx, rax
0x180024157  jz      loc_180024526
0x18002415d  test    byte ptr [rcx+1Ch], 1
0x180024161  jz      loc_180024526
0x180024167  lea     edx, [rbx-35h]
0x18002416a  mov     rcx, [rcx+10h]
0x18002416e  lea     r8, WPP_134408c016563692a0776b6ad2359b4f_Traceguids
0x180024175  mov     r9d, ebx
0x180024178  call    WPP_SF_L
0x18002417d  jmp     loc_180024526
0x180024182  mov     rcx, rbx
0x180024185  inc     rcx
0x180024188  cmp     [rdi+rcx*2], r13w
0x18002418d  jnz     short loc_180024185
0x18002418f  cmp     rcx, rdx
0x180024192  jbe     short loc_1800241BF
0x180024194  mov     ebx, 57h ; 'W'
0x180024199  mov     rcx, cs:WPP_GLOBAL_Control
0x1800241a0  lea     rax, WPP_GLOBAL_Control
0x1800241a7  cmp     rcx, rax
0x1800241aa  jz      loc_180024526
0x1800241b0  test    byte ptr [rcx+1Ch], 1
0x1800241b4  jz      loc_180024526
0x1800241ba  lea     edx, [rbx-34h]
0x1800241bd  jmp     short loc_18002416A
0x1800241bf  movzx   eax, ax
0x1800241c2  mov     [rbp+70h+var_DC], eax
0x1800241c5  lea     ebx, [rax+1]
0x1800241c8  lea     eax, ds:28h[rbx*2]
0x1800241cf  cmp     eax, 28h ; '('
0x1800241d2  jnb     short loc_1800241DE
0x1800241d4  mov     ebx, 216h
0x1800241d9  jmp     loc_180024526
0x1800241de  movzx   ecx, cx
0x1800241e1  mov     [rbp+70h+var_D8], ecx
0x1800241e4  inc     ecx
0x1800241e6  mov     [rbp+70h+var_E0], ecx
0x1800241e9  lea     r13d, [rax+rcx*2]
0x1800241ed  cmp     r13d, eax
0x1800241f0  jb      short loc_1800241D4
0x1800241f2  mov     ecx, r13d; Size
0x1800241f5  call    ?UbpmAlloc@@YAPEAXK@Z; UbpmAlloc(ulong)
0x1800241fa  mov     r14, rax
0x1800241fd  test    rax, rax
0x180024200  jnz     short loc_18002423A
0x180024202  call    cs:__imp_GetLastError
0x180024209  nop     dword ptr [rax+rax+00h]
0x18002420e  mov     ebx, eax
0x180024210  mov     rcx, cs:WPP_GLOBAL_Control
0x180024217  lea     rax, WPP_GLOBAL_Control
0x18002421e  cmp     rcx, rax
0x180024221  jz      loc_180024526
0x180024227  test    byte ptr [rcx+1Ch], 1
0x18002422b  jz      loc_180024526
0x180024231  lea     edx, [r14+24h]
0x180024235  jmp     loc_180024086
0x18002423a  lea     rcx, [rax+28h]; void *
0x18002423e  mov     qword ptr [rax], 0Ch
0x180024245  lea     r8, [rbx+rbx]; Size
0x180024249  mov     rdx, rsi; Src
0x18002424c  call    memcpy_0
0x180024251  mov     r8d, [rbp+70h+var_E0]
0x180024255  add     rbx, 14h
0x180024259  add     r8, r8; Size
0x18002425c  mov     rdx, rdi; Src
0x18002425f  lea     rbx, [r14+rbx*2]
0x180024263  mov     rcx, rbx; void *
0x180024266  call    memcpy_0
0x18002426b  mov     eax, [rbp+70h+var_DC]
0x18002426e  mov     ecx, 0FFFFh
0x180024273  add     eax, eax
0x180024275  cmp     eax, ecx
0x180024277  ja      loc_180024517
0x18002427d  mov     [r14+8], ax
0x180024282  mov     [r14+0Ah], ax
0x180024287  lea     rax, [r14+28h]
0x18002428b  mov     [r14+10h], rax
0x18002428f  mov     eax, [rbp+70h+var_D8]
0x180024292  add     eax, eax
0x180024294  cmp     eax, ecx
0x180024296  ja      loc_18002450D
0x18002429c  mov     [r14+18h], ax
0x1800242a1  lea     rcx, [rbp+70h+LocallyUniqueId.LowPart+8]; LocallyUniqueId
0x1800242a5  mov     [r14+1Ah], ax
0x1800242aa  mov     rax, 2020204D5042552Eh
0x1800242b4  mov     [r14+20h], rbx
0x1800242b8  mov     qword ptr [rbp+70h+LocallyUniqueId.LowPart], rax
0x1800242bc  call    cs:__imp_NtAllocateLocallyUniqueId
0x1800242c3  nop     dword ptr [rax+rax+00h]
0x1800242c8  test    eax, eax
0x1800242ca  jns     short loc_180024307
0x1800242cc  mov     ecx, eax; Status
0x1800242ce  call    cs:__imp_RtlNtStatusToDosError
0x1800242d5  nop     dword ptr [rax+rax+00h]
0x1800242da  mov     ebx, eax
0x1800242dc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800242e3  lea     rax, WPP_GLOBAL_Control
0x1800242ea  cmp     rcx, rax
0x1800242ed  jz      loc_180024526
0x1800242f3  test    byte ptr [rcx+1Ch], 1
0x1800242f7  jz      loc_180024526
0x1800242fd  mov     edx, 25h ; '%'
0x180024302  jmp     loc_180024086
0x180024307  mov     r9d, [rbp+70h+AuthenticationPackage]; AuthenticationPackage
0x18002430b  lea     rax, [rbp+70h+var_EC]
0x18002430f  mov     rcx, [rbp+70h+LsaHandle]; LsaHandle
0x180024313  lea     rdx, [rbp+70h+var_A0]; OriginName
0x180024317  mov     [rsp+170h+SubStatus], rax; SubStatus
0x18002431c  mov     r8d, r15d; LogonType
0x18002431f  lea     rax, [rbp+70h+var_80]
0x180024323  mov     [rsp+170h+Quotas], rax; Quotas
0x180024328  lea     rax, [rsp+170h+TokenHandle]
0x18002432d  mov     [rsp+170h+Token], rax; Token
0x180024332  lea     rax, [rbp+70h+var_C8]
0x180024336  mov     [rsp+170h+LogonId], rax; LogonId
0x18002433b  lea     rax, [rbp+70h+var_D4]
0x18002433f  mov     [rsp+170h+ProfileBufferLength], rax; ProfileBufferLength
0x180024344  lea     rax, [rbp+70h+Buffer]
0x180024348  mov     [rsp+170h+ProfileBuffer], rax; ProfileBuffer
0x18002434d  lea     rax, [rbp+70h+LocallyUniqueId]
0x180024351  mov     [rsp+170h+SourceContext], rax; SourceContext
0x180024356  mov     [rsp+170h+LocalGroups], r12; LocalGroups
0x18002435b  mov     [rsp+170h+AuthenticationInformationLength], r13d; AuthenticationInformationLength
0x180024360  mov     [rsp+170h+AuthenticationInformation], r14; AuthenticationInformation
0x180024365  call    cs:__imp_LsaLogonUser
0x18002436c  nop     dword ptr [rax+rax+00h]
0x180024371  xor     r13d, r13d
0x180024374  test    eax, eax
0x180024376  jns     short loc_1800243C3
0x180024378  cmp     eax, 0C000006Dh
0x18002437d  jnz     short loc_180024388
0x18002437f  lea     ecx, [rax-0Fh]
0x180024382  cmp     [rbp+70h+var_EC], ecx
0x180024385  cmovz   eax, ecx
0x180024388  mov     ecx, eax; Status
0x18002438a  call    cs:__imp_RtlNtStatusToDosError
0x180024391  nop     dword ptr [rax+rax+00h]
0x180024396  mov     ebx, eax
0x180024398  mov     rcx, cs:WPP_GLOBAL_Control
0x18002439f  lea     rax, WPP_GLOBAL_Control
0x1800243a6  cmp     rcx, rax
0x1800243a9  jz      loc_180024526
0x1800243af  test    byte ptr [rcx+1Ch], 1
0x1800243b3  jz      loc_180024526
0x1800243b9  mov     edx, 26h ; '&'
0x1800243be  jmp     loc_180024086
0x1800243c3  mov     rcx, [rsp+170h+TokenHandle]; TokenHandle
0x1800243c8  lea     rax, [rsp+170h+ReturnLength]
0x1800243cd  xor     r9d, r9d; TokenInformationLength
0x1800243d0  mov     [rsp+170h+AuthenticationInformation], rax; ReturnLength
0x1800243d5  xor     r8d, r8d; TokenInformation
0x1800243d8  lea     ebx, [r9+1Ch]
0x1800243dc  mov     edx, ebx; TokenInformationClass
0x1800243de  call    cs:__imp_GetTokenInformation
0x1800243e5  nop     dword ptr [rax+rax+00h]
0x1800243ea  test    eax, eax
0x1800243ec  jnz     loc_18002448F
0x1800243f2  call    cs:__imp_GetLastError
0x1800243f9  nop     dword ptr [rax+rax+00h]
0x1800243fe  cmp     eax, 7Ah ; 'z'
0x180024401  jz      short loc_18002443C
0x180024403  call    cs:__imp_GetLastError
0x18002440a  nop     dword ptr [rax+rax+00h]
0x18002440f  mov     ebx, eax
0x180024411  mov     rcx, cs:WPP_GLOBAL_Control
0x180024418  lea     rax, WPP_GLOBAL_Control
0x18002441f  cmp     rcx, rax
0x180024422  jz      loc_180024526
0x180024428  test    byte ptr [rcx+1Ch], 1
0x18002442c  jz      loc_180024526
0x180024432  mov     edx, 27h ; '''
0x180024437  jmp     loc_180024086
0x18002443c  mov     edx, [rsp+170h+ReturnLength]; uBytes
0x180024440  xor     ecx, ecx; uFlags
0x180024442  call    cs:__imp_LocalAlloc
0x180024449  nop     dword ptr [rax+rax+00h]
0x18002444e  mov     r12, rax
0x180024451  test    rax, rax
0x180024454  jnz     short loc_18002448F
0x180024456  call    cs:__imp_GetLastError
0x18002445d  nop     dword ptr [rax+rax+00h]
0x180024462  mov     ebx, eax
0x180024464  mov     rcx, cs:WPP_GLOBAL_Control
0x18002446b  lea     rax, WPP_GLOBAL_Control
0x180024472  cmp     rcx, rax
0x180024475  jz      loc_180024526
0x18002447b  test    byte ptr [rcx+1Ch], 1
0x18002447f  jz      loc_180024526
0x180024485  lea     edx, [r12+28h]
0x18002448a  jmp     loc_180024086
  ... truncated ...
```
