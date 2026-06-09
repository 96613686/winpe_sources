# LogonUserWrap

- ea: `0x180002110`
- end: `0x180002564`
- name: `LogonUserWrap`
- size: `1108`
- prototype: `__int64 __fastcall(wchar_t *Str, int *, __int16 *, SECURITY_LOGON_TYPE, int, void *, void **, wchar_t **)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180001470`

## callees

- `0x180002110`
- `0x180003e10`
- `0x180003fec`
- `0x180004530`
- `0x180004720`

## import_xrefs

- `api-ms-win-core-crt-l1-1-0!wcschr` at `0x1800021fc`
- `api-ms-win-core-crt-l1-1-0!wcschr` at `0x1800021fc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800022f3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002331`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000246f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800024d3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800024ec`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002521`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800022f3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002331`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000246f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800024d3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800024ec`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002521`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180002301`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180002342`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000247e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180002301`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180002342`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000247e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800024e1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800024fa`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000252f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800024e1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800024fa`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000252f`
- `ntdll!RtlInitString` at `0x18000221f`
- `ntdll!RtlInitString` at `0x18000221f`
- `ntdll!RtlLengthRequiredSid` at `0x1800022eb`
- `ntdll!RtlLengthRequiredSid` at `0x1800022eb`
- `ntdll!RtlSubAuthoritySid` at `0x180002328`
- `ntdll!RtlSubAuthoritySid` at `0x180002328`
- `ntdll!RtlNtStatusToDosError` at `0x180002262`
- `ntdll!RtlNtStatusToDosError` at `0x1800024b4`
- `ntdll!RtlNtStatusToDosError` at `0x180002262`
- `ntdll!RtlNtStatusToDosError` at `0x1800024b4`
- `ntdll!RtlInitializeSid` at `0x18000231d`
- `ntdll!RtlInitializeSid` at `0x18000231d`
- `SspiCli!LsaFreeReturnBuffer` at `0x180002516`
- `SspiCli!LsaFreeReturnBuffer` at `0x180002516`
- `SspiCli!SeciAllocateAndSetIPAddress` at `0x1800023d2`
- `SspiCli!SeciAllocateAndSetIPAddress` at `0x1800023d2`
- `SspiCli!LsaLogonUser` at `0x180002442`
- `SspiCli!LsaLogonUser` at `0x180002442`
- `SspiCli!SeciFreeCallContext` at `0x18000253b`
- `SspiCli!SeciFreeCallContext` at `0x18000253b`
- `CRYPTBASE!SystemFunction041` at `0x180002256`
- `CRYPTBASE!SystemFunction041` at `0x180002256`

## pseudocode

```c
__int64 __fastcall LogonUserWrap(
        wchar_t *Str,
        int *a2,
        __int16 *a3,
        SECURITY_LOGON_TYPE a4,
        int a5,
        void *a6,
        void **a7,
        wchar_t **a8)
{
  int *v8; // r15
  int *v9; // rbx
  unsigned __int16 *v10; // rdi
  void *v11; // r13
  const wchar_t *v12; // r9
  int *v13; // rcx
  int v14; // esi
  wchar_t *v15; // r12
  unsigned __int16 v16; // r14
  const char *v17; // rsi
  __int64 v18; // rdi
  int v19; // eax
  ULONG v20; // eax
  struct _TOKEN_GROUPS *LocalGroups; // r15
  __int64 v22; // rcx
  unsigned int AuthInfo; // r14d
  ULONG v24; // ebx
  HANDLE ProcessHeap; // rax
  void *v26; // rax
  HANDLE v27; // rax
  struct _TOKEN_GROUPS *v28; // rax
  __int64 v29; // rax
  struct _TOKEN_SOURCE *p_SourceContext; // rcx
  __int64 v31; // rdx
  struct _TOKEN_SOURCE *v32; // rax
  int v33; // eax
  STRSAFE_LPCWSTR *v34; // rdi
  SIZE_T v35; // rbx
  HANDLE v36; // rax
  wchar_t *v37; // rax
  int v38; // eax
  HANDLE v39; // rax
  HANDLE v40; // rax
  HANDLE v41; // rax
  unsigned int v43; // [rsp+70h] [rbp-90h]
  ULONG AuthenticationInformationLength; // [rsp+74h] [rbp-8Ch] BYREF
  ULONG AuthenticationPackage; // [rsp+78h] [rbp-88h] BYREF
  int SubStatus; // [rsp+7Ch] [rbp-84h] BYREF
  int v47; // [rsp+80h] [rbp-80h] BYREF
  ULONG ProfileBufferLength; // [rsp+84h] [rbp-7Ch] BYREF
  SECURITY_LOGON_TYPE LogonType; // [rsp+88h] [rbp-78h]
  PVOID AuthenticationInformation; // [rsp+90h] [rbp-70h] BYREF
  PVOID Buffer; // [rsp+98h] [rbp-68h] BYREF
  int *v52; // [rsp+A0h] [rbp-60h]
  const wchar_t *v53; // [rsp+A8h] [rbp-58h]
  PHANDLE Token; // [rsp+B0h] [rbp-50h]
  struct _LUID LogonId; // [rsp+B8h] [rbp-48h] BYREF
  wchar_t **v56; // [rsp+C0h] [rbp-40h]
  _STRING DestinationString; // [rsp+C8h] [rbp-38h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+D8h] [rbp-28h] BYREF
  _OWORD v59[2]; // [rsp+E0h] [rbp-20h] BYREF
  struct _TOKEN_SOURCE SourceContext; // [rsp+100h] [rbp+0h] BYREF
  struct _QUOTA_LIMITS Quotas; // [rsp+110h] [rbp+10h] BYREF

  v8 = &dword_180006E14;
  v9 = (int *)*((_QWORD *)a3 + 1);
  v10 = (unsigned __int16 *)(a3 + 1);
  v11 = 0;
  LogonType = a4;
  Token = a7;
  v12 = (const wchar_t *)&dword_180006E14;
  v56 = a8;
  if ( Str )
    v12 = Str;
  v43 = 0;
  *(_DWORD *)IdentifierAuthority.Value = 0;
  v13 = &dword_180006E14;
  *(_WORD *)&IdentifierAuthority.Value[4] = 512;
  if ( a2 )
    v13 = a2;
  AuthenticationPackage = 0;
  v52 = v13;
  v14 = 0;
  AuthenticationInformation = 0;
  v15 = 0;
  AuthenticationInformationLength = 0;
  Buffer = 0;
  ProfileBufferLength = 0;
  LogonId = 0;
  SubStatus = 0;
  v47 = 0;
  v53 = v12;
  memset(v59, 0, 28);
  DestinationString = 0;
  SourceContext = 0;
  memset(&Quotas, 0, sizeof(Quotas));
  if ( v9 )
  {
    v16 = *a3;
    v8 = v9;
  }
  else
  {
    *v10 = 1;
    v9 = &dword_180006E14;
    v16 = 0;
  }
  if ( !*(_WORD *)v13 )
  {
    if ( !wcschr(v12, 0x40u) )
      v14 = 1;
    v43 = v14;
  }
  v17 = "seclogon";
  RtlInitString(&DestinationString, "seclogon");
  if ( v16 >= *v10 )
    goto LABEL_47;
  if ( !v16 )
  {
LABEL_18:
    v18 = 2LL * v16;
    *(_WORD *)((char *)v8 + v18) = 0;
    goto LABEL_19;
  }
  v18 = 2LL * v16;
  if ( (v18 & 7) != 0 )
  {
LABEL_47:
    v20 = 87;
    goto LABEL_48;
  }
  v19 = SystemFunction041(v8, 2 * v16, 2u);
  if ( v19 >= 0 )
    goto LABEL_18;
  v20 = RtlNtStatusToDosError(v19);
  if ( v20 )
  {
LABEL_48:
    AuthInfo = v20;
    goto LABEL_49;
  }
LABEL_19:
  LocalGroups = 0;
  AuthInfo = MakeAuthInfo(
               v43,
               v53,
               v52,
               v9,
               &AuthenticationPackage,
               &AuthenticationInformation,
               &AuthenticationInformationLength);
  if ( !AuthInfo )
  {
    for ( ; v18; --v18 )
    {
      *(_BYTE *)v9 = 0;
      v9 = (int *)((char *)v9 + 1);
    }
    AuthInfo = 8;
    if ( a6 )
    {
      v24 = RtlLengthRequiredSid(1u);
      ProcessHeap = GetProcessHeap();
      v26 = HeapAlloc(ProcessHeap, 0, v24);
      v11 = v26;
      if ( !v26 )
        goto LABEL_41;
      RtlInitializeSid(v26, &IdentifierAuthority, 1u);
      *RtlSubAuthoritySid(v11, 0) = 0;
      v27 = GetProcessHeap();
      v28 = (struct _TOKEN_GROUPS *)HeapAlloc(v27, 0, 0x28u);
      LocalGroups = v28;
      if ( !v28 )
        goto LABEL_41;
      v28->GroupCount = 2;
      v28->Groups[0].Sid = a6;
      v28->Groups[0].Attributes = -1073741817;
      *(_QWORD *)&v28[1].GroupCount = v11;
      LODWORD(v28[1].Groups[0].Sid) = 7;
    }
    v29 = 2147483646;
    p_SourceContext = &SourceContext;
    v31 = 8;
    do
    {
      if ( !v29 )
        break;
      if ( !*v17 )
        break;
      p_SourceContext->SourceName[0] = *v17++;
      p_SourceContext = (struct _TOKEN_SOURCE *)((char *)p_SourceContext + 1);
      --v29;
      --v31;
    }
    while ( v31 );
    *(_QWORD *)&v59[0] = 23;
    v32 = (struct _TOKEN_SOURCE *)((char *)p_SourceContext - 1);
    DWORD2(v59[1]) = 0;
    if ( v31 )
      v32 = p_SourceContext;
    *(_OWORD *)((char *)v59 + 8) = 0;
    BYTE7(v59[1]) = 1;
    v32->SourceName[0] = 0;
    SeciAllocateAndSetIPAddress(v59, 28, &v47);
    v33 = LsaLogonUser(
            *(&hServiceStatus + 1),
            (PLSA_STRING)&DestinationString,
            LogonType,
            AuthenticationPackage,
            AuthenticationInformation,
            AuthenticationInformationLength,
            LocalGroups,
            &SourceContext,
            &Buffer,
            &ProfileBufferLength,
            &LogonId,
            Token,
            &Quotas,
            &SubStatus);
    if ( v33 < 0 || (v33 = SubStatus, SubStatus < 0) )
    {
      v38 = RtlNtStatusToDosError(v33);
      goto LABEL_40;
    }
    v34 = (STRSAFE_LPCWSTR *)Buffer;
    if ( !Buffer || !*((_QWORD *)Buffer + 14) )
      goto LABEL_38;
    v35 = 2LL * *((unsigned __int16 *)Buffer + 52) + 2;
    v36 = GetProcessHeap();
    v37 = (wchar_t *)HeapAlloc(v36, 8u, v35);
    v15 = v37;
    if ( v37 )
    {
      v38 = StringCchCopyW(v37, *((unsigned __int16 *)v34 + 52) + 1LL, v34[14]);
      if ( v38 >= 0 )
      {
LABEL_38:
        *v56 = v15;
        v15 = 0;
        AuthInfo = 0;
        goto LABEL_41;
      }
LABEL_40:
      AuthInfo = v38;
    }
  }
LABEL_41:
  if ( AuthenticationInformation )
    DestroyAuthInfo(v22, AuthenticationInformation);
  if ( v11 )
  {
    v39 = GetProcessHeap();
    HeapFree(v39, 0, v11);
  }
  if ( LocalGroups )
  {
    v40 = GetProcessHeap();
    HeapFree(v40, 0, LocalGroups);
  }
LABEL_49:
  if ( Buffer )
    LsaFreeReturnBuffer(Buffer);
  if ( v15 )
  {
    v41 = GetProcessHeap();
    HeapFree(v41, 0, v15);
  }
  if ( v47 )
    SeciFreeCallContext();
  return AuthInfo;
}

```

## disassembly

```asm
0x180002110  push    rbp
0x180002112  push    rbx
0x180002113  push    rsi
0x180002114  push    rdi
0x180002115  push    r12
0x180002117  push    r13
0x180002119  push    r14
0x18000211b  push    r15
0x18000211d  lea     rbp, [rsp-58h]
0x180002122  sub     rsp, 158h
0x180002129  mov     rax, cs:__security_cookie
0x180002130  xor     rax, rsp
0x180002133  mov     [rbp+90h+var_50], rax
0x180002137  mov     rax, [rbp+90h+arg_30]
0x18000213e  lea     r15, dword_180006E14
0x180002145  mov     rbx, [r8+8]
0x180002149  lea     rdi, [r8+2]
0x18000214d  xor     r13d, r13d
0x180002150  mov     [rbp+90h+LogonType], r9d
0x180002154  xorps   xmm0, xmm0
0x180002157  mov     [rbp+90h+var_E0], rax
0x18000215b  mov     rax, [rbp+90h+arg_38]
0x180002162  test    rcx, rcx
0x180002165  mov     r9, r15
0x180002168  mov     [rbp+90h+var_D0], rax
0x18000216c  cmovnz  r9, rcx
0x180002170  mov     [rsp+190h+var_120], r13d
0x180002175  test    rdx, rdx
0x180002178  mov     dword ptr [rbp+90h+IdentifierAuthority.Value], r13d
0x18000217c  mov     rcx, r15
0x18000217f  mov     word ptr [rbp+90h+IdentifierAuthority.Value+4], 200h
0x180002185  cmovnz  rcx, rdx
0x180002189  mov     [rsp+190h+AuthenticationPackage], r13d
0x18000218e  mov     [rbp+90h+var_F0], rcx
0x180002192  mov     esi, r13d
0x180002195  mov     [rbp+90h+var_100], r13
0x180002199  mov     r12d, r13d
0x18000219c  mov     [rsp+190h+var_11C], r13d
0x1800021a1  mov     [rbp+90h+Buffer], r13
0x1800021a5  mov     [rbp+90h+var_10C], r13d
0x1800021a9  mov     qword ptr [rbp+90h+var_D8.LowPart], r13
0x1800021ad  mov     [rsp+190h+var_114], r13d
0x1800021b2  mov     [rbp+90h+var_110], r13d
0x1800021b6  mov     [rbp+90h+var_E8], r9
0x1800021ba  movups  [rbp+90h+var_B0], xmm0
0x1800021be  movups  xmmword ptr [rbp+90h+DestinationString.Length], xmm0
0x1800021c2  movups  xmmword ptr [rbp+90h+var_90.SourceName], xmm0
0x1800021c6  movups  xmmword ptr [rbp+90h+var_80.PagedPoolLimit], xmm0
0x1800021ca  movups  xmmword ptr [rbp+90h+var_80.MinimumWorkingSetSize], xmm0
0x1800021ce  movups  xmmword ptr [rbp+90h+var_80.PagefileLimit], xmm0
0x1800021d2  movups  [rbp+90h+var_B0+0Ch], xmm0
0x1800021d6  test    rbx, rbx
0x1800021d9  jnz     short loc_1800021E8
0x1800021db  mov     word ptr [rdi], 1
0x1800021e0  mov     rbx, r15
0x1800021e3  mov     r14d, r13d
0x1800021e6  jmp     short loc_1800021EF
0x1800021e8  movzx   r14d, word ptr [r8]
0x1800021ec  mov     r15, rbx
0x1800021ef  cmp     r13w, [rcx]
0x1800021f3  jnz     short loc_180002211
0x1800021f5  mov     dx, 40h ; '@'; Ch
0x1800021f9  mov     rcx, r9; Str
0x1800021fc  call    cs:__imp_wcschr
0x180002202  test    rax, rax
0x180002205  mov     eax, 1
0x18000220a  cmovz   esi, eax
0x18000220d  mov     [rsp+190h+var_120], esi
0x180002211  lea     rsi, SourceString; "seclogon"
0x180002218  mov     rdx, rsi; SourceString
0x18000221b  lea     rcx, [rbp+90h+DestinationString]; DestinationString
0x18000221f  call    cs:__imp_RtlInitString
0x180002225  cmp     r14w, [rdi]
0x180002229  jnb     loc_180002502
0x18000222f  cmp     r13w, r14w
0x180002233  jz      short loc_180002272
0x180002235  movzx   eax, r14w
0x180002239  lea     rdi, [rax+rax]
0x18000223d  test    dil, 7
0x180002241  jnz     loc_180002502
0x180002247  movzx   edx, r14w
0x18000224b  mov     r8d, 2; OptionFlags
0x180002251  add     edx, edx; MemorySize
0x180002253  mov     rcx, r15; Memory
0x180002256  call    cs:__imp_SystemFunction041
0x18000225c  test    eax, eax
0x18000225e  jns     short loc_180002272
0x180002260  mov     ecx, eax; Status
0x180002262  call    cs:__imp_RtlNtStatusToDosError
0x180002268  test    eax, eax
0x18000226a  jnz     loc_180002507
0x180002270  jmp     short loc_18000227F
0x180002272  movzx   eax, r14w
0x180002276  lea     rdi, [rax+rax]
0x18000227a  mov     [rdi+r15], r13w
0x18000227f  xor     r15d, r15d
0x180002282  mov     r8, [rbp+90h+var_F0]
0x180002286  lea     rax, [rsp+190h+var_11C]
0x18000228b  mov     rdx, [rbp+90h+var_E8]
0x18000228f  mov     r9, rbx
0x180002292  mov     ecx, [rsp+190h+var_120]
0x180002296  mov     [rsp+190h+LocalGroups], rax
0x18000229b  lea     rax, [rbp+90h+var_100]
0x18000229f  mov     qword ptr [rsp+190h+AuthenticationInformationLength], rax
0x1800022a4  lea     rax, [rsp+190h+AuthenticationPackage]
0x1800022a9  mov     [rsp+190h+AuthenticationInformation], rax
0x1800022ae  call    MakeAuthInfo
0x1800022b3  mov     r14d, eax
0x1800022b6  test    eax, eax
0x1800022b8  jnz     loc_1800024BD
0x1800022be  test    rdi, rdi
0x1800022c1  jz      short loc_1800022D0
0x1800022c3  mov     [rbx], r12b
0x1800022c6  lea     rbx, [rbx+1]
0x1800022ca  sub     rdi, 1
0x1800022ce  jnz     short loc_1800022C3
0x1800022d0  mov     rdi, [rbp+90h+arg_28]
0x1800022d7  mov     r14d, 8
0x1800022dd  test    rdi, rdi
0x1800022e0  jz      loc_180002370
0x1800022e6  mov     ecx, 1; SubAuthorityCount
0x1800022eb  call    cs:__imp_RtlLengthRequiredSid
0x1800022f1  mov     ebx, eax
0x1800022f3  call    cs:__imp_GetProcessHeap
0x1800022f9  mov     r8d, ebx; dwBytes
0x1800022fc  xor     edx, edx; dwFlags
0x1800022fe  mov     rcx, rax; hHeap
0x180002301  call    cs:__imp_HeapAlloc
0x180002307  mov     r13, rax
0x18000230a  test    rax, rax
0x18000230d  jz      loc_1800024BD
0x180002313  mov     r8b, 1; SubAuthorityCount
0x180002316  lea     rdx, [rbp+90h+IdentifierAuthority]; IdentifierAuthority
0x18000231a  mov     rcx, rax; Sid
0x18000231d  call    cs:__imp_RtlInitializeSid
0x180002323  xor     edx, edx; SubAuthority
0x180002325  mov     rcx, r13; Sid
0x180002328  call    cs:__imp_RtlSubAuthoritySid
0x18000232e  mov     [rax], r12d
0x180002331  call    cs:__imp_GetProcessHeap
0x180002337  xor     edx, edx; dwFlags
0x180002339  mov     r8d, 28h ; '('; dwBytes
0x18000233f  mov     rcx, rax; hHeap
0x180002342  call    cs:__imp_HeapAlloc
0x180002348  mov     r15, rax
0x18000234b  test    rax, rax
0x18000234e  jz      loc_1800024BD
0x180002354  mov     dword ptr [rax], 2
0x18000235a  mov     [rax+8], rdi
0x18000235e  mov     dword ptr [rax+10h], 0C0000007h
0x180002365  mov     [rax+18h], r13
0x180002369  mov     dword ptr [rax+20h], 7
0x180002370  mov     eax, 7FFFFFFEh
0x180002375  lea     rcx, [rbp+90h+var_90]
0x180002379  mov     rdx, r14
0x18000237c  nop     dword ptr [rax+00h]
0x180002380  test    rax, rax
0x180002383  jz      short loc_1800023A0
0x180002385  movzx   r8d, byte ptr [rsi]
0x180002389  test    r8b, r8b
0x18000238c  jz      short loc_1800023A0
0x18000238e  mov     [rcx], r8b
0x180002391  inc     rsi
0x180002394  inc     rcx
0x180002397  dec     rax
0x18000239a  sub     rdx, 1
0x18000239e  jnz     short loc_180002380
0x1800023a0  test    rdx, rdx
0x1800023a3  mov     qword ptr [rbp+90h+var_B0], 17h
0x1800023ab  lea     rax, [rcx-1]
0x1800023af  mov     [rbp+90h+var_98], r12d
0x1800023b3  cmovnz  rax, rcx
0x1800023b7  lea     r8, [rbp+90h+var_110]
0x1800023bb  xorps   xmm0, xmm0
0x1800023be  lea     rcx, [rbp+90h+var_B0]
0x1800023c2  movups  [rbp+90h+var_B0+8], xmm0
0x1800023c6  mov     edx, 1Ch
0x1800023cb  mov     [rbp+90h+var_99], 1
0x1800023cf  mov     [rax], r12b
0x1800023d2  call    cs:__imp_SeciAllocateAndSetIPAddress
0x1800023d8  mov     r9d, [rsp+190h+AuthenticationPackage]; AuthenticationPackage
0x1800023dd  lea     rax, [rsp+190h+var_114]
0x1800023e2  mov     r8d, [rbp+90h+LogonType]; LogonType
0x1800023e6  lea     rdx, [rbp+90h+DestinationString]; OriginName
0x1800023ea  mov     rcx, qword ptr cs:hServiceStatus+8; LsaHandle
0x1800023f1  mov     [rsp+190h+SubStatus], rax; SubStatus
0x1800023f6  lea     rax, [rbp+90h+var_80]
0x1800023fa  mov     [rsp+190h+Quotas], rax; Quotas
0x1800023ff  mov     rax, [rbp+90h+var_E0]
0x180002403  mov     [rsp+190h+Token], rax; Token
0x180002408  lea     rax, [rbp+90h+var_D8]
0x18000240c  mov     [rsp+190h+LogonId], rax; LogonId
0x180002411  lea     rax, [rbp+90h+var_10C]
0x180002415  mov     [rsp+190h+ProfileBufferLength], rax; ProfileBufferLength
0x18000241a  lea     rax, [rbp+90h+Buffer]
0x18000241e  mov     [rsp+190h+ProfileBuffer], rax; ProfileBuffer
0x180002423  lea     rax, [rbp+90h+var_90]
0x180002427  mov     [rsp+190h+SourceContext], rax; SourceContext
0x18000242c  mov     eax, [rsp+190h+var_11C]
0x180002430  mov     [rsp+190h+LocalGroups], r15; LocalGroups
0x180002435  mov     [rsp+190h+AuthenticationInformationLength], eax; AuthenticationInformationLength
0x180002439  mov     rax, [rbp+90h+var_100]
0x18000243d  mov     [rsp+190h+AuthenticationInformation], rax; AuthenticationInformation
0x180002442  call    cs:__imp_LsaLogonUser
0x180002448  test    eax, eax
0x18000244a  js      short loc_1800024B2
0x18000244c  mov     eax, [rsp+190h+var_114]
0x180002450  test    eax, eax
0x180002452  js      short loc_1800024B2
0x180002454  mov     rdi, [rbp+90h+Buffer]
0x180002458  test    rdi, rdi
0x18000245b  jz      short loc_1800024A3
0x18000245d  cmp     [rdi+70h], r12
0x180002461  jz      short loc_1800024A3
0x180002463  movzx   eax, word ptr [rdi+68h]
0x180002467  lea     rbx, ds:2[rax*2]
0x18000246f  call    cs:__imp_GetProcessHeap
0x180002475  mov     r8, rbx; dwBytes
0x180002478  mov     edx, r14d; dwFlags
0x18000247b  mov     rcx, rax; hHeap
0x18000247e  call    cs:__imp_HeapAlloc
0x180002484  mov     r12, rax
0x180002487  test    rax, rax
0x18000248a  jz      short loc_1800024BD
0x18000248c  movzx   edx, word ptr [rdi+68h]
0x180002490  mov     rcx, rax; pszDest
0x180002493  mov     r8, [rdi+70h]; pszSrc
0x180002497  inc     rdx; cchDest
0x18000249a  call    StringCchCopyW
0x18000249f  test    eax, eax
0x1800024a1  js      short loc_1800024BA
0x1800024a3  mov     rax, [rbp+90h+var_D0]
0x1800024a7  mov     [rax], r12
0x1800024aa  xor     r12d, r12d
0x1800024ad  xor     r14d, r14d
0x1800024b0  jmp     short loc_1800024BD
0x1800024b2  mov     ecx, eax; Status
0x1800024b4  call    cs:__imp_RtlNtStatusToDosError
0x1800024ba  mov     r14d, eax
0x1800024bd  mov     rax, [rbp+90h+var_100]
0x1800024c1  test    rax, rax
0x1800024c4  jz      short loc_1800024CE
0x1800024c6  mov     rdx, rax
0x1800024c9  call    DestroyAuthInfo
0x1800024ce  test    r13, r13
0x1800024d1  jz      short loc_1800024E7
0x1800024d3  call    cs:__imp_GetProcessHeap
0x1800024d9  mov     r8, r13; lpMem
0x1800024dc  xor     edx, edx; dwFlags
0x1800024de  mov     rcx, rax; hHeap
0x1800024e1  call    cs:__imp_HeapFree
0x1800024e7  test    r15, r15
0x1800024ea  jz      short loc_18000250A
0x1800024ec  call    cs:__imp_GetProcessHeap
0x1800024f2  mov     r8, r15; lpMem
0x1800024f5  xor     edx, edx; dwFlags
0x1800024f7  mov     rcx, rax; hHeap
0x1800024fa  call    cs:__imp_HeapFree
0x180002500  jmp     short loc_18000250A
0x180002502  mov     eax, 57h ; 'W'
0x180002507  mov     r14d, eax
0x18000250a  mov     rdi, [rbp+90h+Buffer]
0x18000250e  test    rdi, rdi
0x180002511  jz      short loc_18000251C
0x180002513  mov     rcx, rdi; Buffer
0x180002516  call    cs:__imp_LsaFreeReturnBuffer
0x18000251c  test    r12, r12
0x18000251f  jz      short loc_180002535
0x180002521  call    cs:__imp_GetProcessHeap
0x180002527  mov     r8, r12; lpMem
0x18000252a  xor     edx, edx; dwFlags
0x18000252c  mov     rcx, rax; hHeap
0x18000252f  call    cs:__imp_HeapFree
0x180002535  cmp     [rbp+90h+var_110], 0
0x180002539  jz      short loc_180002541
0x18000253b  call    cs:__imp_SeciFreeCallContext
0x180002541  mov     eax, r14d
0x180002544  mov     rcx, [rbp+90h+var_50]
0x180002548  xor     rcx, rsp; StackCookie
0x18000254b  call    __security_check_cookie
0x180002550  add     rsp, 158h
0x180002557  pop     r15
0x180002559  pop     r14
0x18000255b  pop     r13
0x18000255d  pop     r12
0x18000255f  pop     rdi
0x180002560  pop     rsi
0x180002561  pop     rbx
0x180002562  pop     rbp
0x180002563  retn
```
