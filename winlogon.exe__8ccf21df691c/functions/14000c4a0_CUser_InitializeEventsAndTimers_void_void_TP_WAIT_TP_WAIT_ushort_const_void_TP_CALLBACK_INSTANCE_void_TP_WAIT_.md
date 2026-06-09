# CUser::InitializeEventsAndTimers(void * *,void * *,_TP_WAIT * *,_TP_WAIT * *,ushort const *,void (*)(_TP_CALLBACK_INSTANCE *,void *,_TP_WAIT *,long))

- ea: `0x14000c4a0`
- end: `0x14000cb46`
- name: `?InitializeEventsAndTimers@CUser@@AEAAXPEAPEAX0PEAPEAU_TP_WAIT@@1PEBGP6AXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU2@J@Z@Z`
- size: `1702`
- prototype: `void __fastcall(CUser *__hidden this, void **, void **, struct _TP_WAIT **, struct _TP_WAIT **, const unsigned __int16 *, void (*)(struct _TP_CALLBACK_INSTANCE *, void *, struct _TP_WAIT *, int))`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x14000c020`

## callees

- `0x1400057f4`
- `0x14000c4a0`
- `0x14000d4e0`
- `0x14000d570`
- `0x14000f510`
- `0x140041c34`
- `0x140053720`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14000c67e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14000c7ea`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14000c67e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14000c7ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000c687`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000c7f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000c84f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000c873`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000c93b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000ca13`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000ca55`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000c687`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000c7f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000c84f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000c873`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000c93b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000ca13`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000ca55`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000c5a0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000c5a0`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14000c57f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14000c57f`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x14000c865`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x14000c865`
- `ntdll!TpAllocWait` at `0x14000c707`
- `ntdll!TpAllocWait` at `0x14000c8a0`
- `ntdll!TpAllocWait` at `0x14000c707`
- `ntdll!TpAllocWait` at `0x14000c8a0`
- `ntdll!NtQueryInformationToken` at `0x14000c552`
- `ntdll!NtQueryInformationToken` at `0x14000c552`

## pseudocode

```c
void __fastcall CUser::InitializeEventsAndTimers(
        CUser *this,
        void **a2,
        void **a3,
        struct _TP_WAIT **a4,
        struct _TP_WAIT **a5,
        const unsigned __int16 *a6,
        void (*a7)(struct _TP_CALLBACK_INSTANCE *, void *, struct _TP_WAIT *, int))
{
  ULONG v7; // r12d
  void (*v8)(struct _TP_CALLBACK_INSTANCE *, void *, struct _TP_WAIT *, int); // r15
  void *v13; // rcx
  int v14; // ebx
  int v15; // eax
  void *SecurityDescriptor; // r15
  __int64 v17; // r9
  HANDLE v18; // r14
  DWORD v19; // eax
  CUser *v20; // rcx
  signed int v21; // eax
  void *v22; // rsi
  HANDLE v23; // rbx
  DWORD v24; // eax
  DWORD v25; // r14d
  CUser *v26; // rcx
  CUser *v27; // rcx
  __int64 v28; // rdx
  ULONG LastError; // eax
  DWORD v30; // eax
  DWORD v31; // eax
  PULONG ReturnLength; // [rsp+20h] [rbp-E0h]
  PULONG ReturnLengtha; // [rsp+20h] [rbp-E0h]
  __int64 v34; // [rsp+30h] [rbp-D0h] BYREF
  HANDLE TokenInformation; // [rsp+38h] [rbp-C8h] BYREF
  struct _SECURITY_ATTRIBUTES EventAttributes; // [rsp+40h] [rbp-C0h] BYREF
  const unsigned __int16 *v37; // [rsp+58h] [rbp-A8h]
  __int64 v38; // [rsp+60h] [rbp-A0h]
  void (*v39)(struct _TP_CALLBACK_INSTANCE *, void *, struct _TP_WAIT *, int); // [rsp+68h] [rbp-98h]
  struct _TP_WAIT **v40; // [rsp+70h] [rbp-90h]
  _BYTE v41[36]; // [rsp+78h] [rbp-88h] BYREF
  __int128 v42; // [rsp+9Ch] [rbp-64h]
  int v43; // [rsp+ACh] [rbp-54h]
  WCHAR Name[512]; // [rsp+B0h] [rbp-50h] BYREF

  v7 = 0;
  v8 = a7;
  v40 = a5;
  v37 = a6;
  v39 = a7;
  v43 = 0;
  TokenInformation = 0;
  v13 = (void *)*((_QWORD *)this + 17);
  v14 = 0;
  v38 = 0;
  memset(v41, 0, sizeof(v41));
  v34 = 0;
  v42 = 0;
  v15 = NtQueryInformationToken(v13, TokenLinkedToken, &TokenInformation, 8u, (PULONG)&v34 + 1);
  if ( v15 < 0 )
  {
    LastError = RtlNtStatusToDosErrorNoTeb(v15);
  }
  else
  {
    if ( GetTokenInformation(TokenInformation, TokenStatistics, v41, 0x38u, (PDWORD)&v34) )
    {
      v14 = *(_DWORD *)&v41[8];
      v38 = *(_QWORD *)&v41[8];
      goto LABEL_4;
    }
    LastError = GetLastError();
  }
  v7 = LastError;
LABEL_4:
  if ( TokenInformation )
    CloseHandle(TokenInformation);
  if ( *a2 )
  {
LABEL_20:
    if ( !*a4 )
    {
      if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 132, WPP_586e3f58e70b3bd7f4fb97bd2f93cbf8_Traceguids);
      }
      v21 = TpAllocWait(a4, v8, 0, 0);
      if ( v21 < 0 )
      {
        v27 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v28 = 133;
          goto LABEL_47;
        }
      }
      else if ( !v7 )
      {
        v21 = TpAllocWait(v40, v8, 0, 0);
        if ( v21 < 0 )
        {
          v27 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v28 = 134;
            goto LABEL_47;
          }
        }
      }
    }
    return;
  }
  if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 129, WPP_586e3f58e70b3bd7f4fb97bd2f93cbf8_Traceguids);
  }
  *(_DWORD *)&v41[8] = 2031619;
  *(_QWORD *)v41 = g_pSidSystem;
  *(_QWORD *)&v41[16] = g_pSidService;
  memset(&EventAttributes, 0, sizeof(EventAttributes));
  v41[12] = 0;
  *(_DWORD *)&v41[24] = 2031619;
  v41[28] = 0;
  SecurityDescriptor = CreateSecurityDescriptor((__int64)v41, 2u);
  if ( !SecurityDescriptor
    && WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v30 = GetLastError();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 92, WPP_6767f1e3976c37dffaa064fbfa18a65b_Traceguids, v30);
  }
  v17 = *((unsigned int *)this + 33);
  LODWORD(ReturnLength) = *((_DWORD *)this + 32);
  EventAttributes.nLength = 24;
  EventAttributes.lpSecurityDescriptor = SecurityDescriptor;
  EventAttributes.bInheritHandle = 0;
  StringCchPrintfW(Name, 0x200u, L"Global\\%08x%08x_%s", v17, ReturnLength, v37, v34);
  v18 = CreateEventW(&EventAttributes, 0, 0, Name);
  v19 = GetLastError();
  LODWORD(v34) = v19;
  if ( v18 )
    goto LABEL_13;
  v20 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 93, WPP_6767f1e3976c37dffaa064fbfa18a65b_Traceguids, v19);
    v19 = v34;
LABEL_13:
    v20 = WPP_GLOBAL_Control;
  }
  if ( v19 == 183
    && v20 != (CUser *)&WPP_GLOBAL_Control
    && (*((_BYTE *)v20 + 28) & 1) != 0
    && *((_BYTE *)v20 + 25) >= 2u )
  {
    WPP_SF_(*((_QWORD *)v20 + 2), 94, WPP_6767f1e3976c37dffaa064fbfa18a65b_Traceguids);
  }
  if ( SecurityDescriptor )
    DeleteSecurityDescriptor(SecurityDescriptor);
  *a2 = v18;
  if ( !v18 )
  {
    if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v21 = GetLastError();
      v27 = WPP_GLOBAL_Control;
      v28 = 130;
      goto LABEL_47;
    }
    return;
  }
  if ( v7 )
    goto LABEL_19;
  *(_DWORD *)&v41[8] = 2031619;
  *(_QWORD *)v41 = g_pSidSystem;
  *(_QWORD *)&v41[16] = g_pSidService;
  memset(&EventAttributes, 0, sizeof(EventAttributes));
  v41[12] = 0;
  *(_DWORD *)&v41[24] = 2031619;
  v41[28] = 0;
  v22 = CreateSecurityDescriptor((__int64)v41, 2u);
  if ( !v22
    && WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v31 = GetLastError();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 92, WPP_6767f1e3976c37dffaa064fbfa18a65b_Traceguids, v31);
  }
  LODWORD(ReturnLengtha) = v14;
  EventAttributes.nLength = 24;
  EventAttributes.lpSecurityDescriptor = v22;
  EventAttributes.bInheritHandle = 0;
  StringCchPrintfW(Name, 0x200u, L"Global\\%08x%08x_%s", HIDWORD(v38), ReturnLengtha, v37);
  v23 = CreateEventW(&EventAttributes, 0, 0, Name);
  v24 = GetLastError();
  v25 = v24;
  if ( v23 )
    goto LABEL_30;
  v26 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 93, WPP_6767f1e3976c37dffaa064fbfa18a65b_Traceguids, v24);
LABEL_30:
    v26 = WPP_GLOBAL_Control;
  }
  if ( v25 == 183
    && v26 != (CUser *)&WPP_GLOBAL_Control
    && (*((_BYTE *)v26 + 28) & 1) != 0
    && *((_BYTE *)v26 + 25) >= 2u )
  {
    WPP_SF_(*((_QWORD *)v26 + 2), 94, WPP_6767f1e3976c37dffaa064fbfa18a65b_Traceguids);
  }
  if ( v22 )
    DeleteSecurityDescriptor(v22);
  *a3 = v23;
  if ( v23 )
  {
LABEL_19:
    v8 = v39;
    goto LABEL_20;
  }
  if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v21 = GetLastError();
    v27 = WPP_GLOBAL_Control;
    v28 = 131;
LABEL_47:
    WPP_SF_d(*((_QWORD *)v27 + 2), v28, WPP_586e3f58e70b3bd7f4fb97bd2f93cbf8_Traceguids, (unsigned int)v21);
  }
}

```

## disassembly

```asm
0x14000c4a0  push    rbp
0x14000c4a2  push    rbx
0x14000c4a3  push    rsi
0x14000c4a4  push    rdi
0x14000c4a5  push    r12
0x14000c4a7  push    r13
0x14000c4a9  push    r14
0x14000c4ab  push    r15
0x14000c4ad  lea     rbp, [rsp-3C8h]
0x14000c4b5  sub     rsp, 4C8h
0x14000c4bc  mov     rax, cs:__security_cookie
0x14000c4c3  xor     rax, rsp
0x14000c4c6  mov     [rbp+400h+var_50], rax
0x14000c4cd  mov     rax, [rbp+400h+arg_20]
0x14000c4d4  xor     r12d, r12d
0x14000c4d7  mov     r15, [rbp+400h+arg_30]
0x14000c4de  xorps   xmm0, xmm0
0x14000c4e1  mov     [rsp+500h+var_490], rax
0x14000c4e6  mov     rdi, r9
0x14000c4e9  mov     rax, [rbp+400h+arg_28]
0x14000c4f0  mov     r13, r8
0x14000c4f3  mov     [rsp+500h+var_4A8], rax
0x14000c4f8  lea     r8, [rsp+500h+TokenInformation]; TokenInformation
0x14000c4fd  xor     eax, eax
0x14000c4ff  mov     [rsp+500h+var_498], r15
0x14000c504  mov     [rbp+400h+var_454], eax
0x14000c507  mov     rsi, rdx
0x14000c50a  lea     rax, [rsp+500h+var_4CC]
0x14000c50f  mov     [rsp+500h+TokenInformation], r12
0x14000c514  mov     r14, rcx
0x14000c517  mov     [rsp+500h+ReturnLength], rax; ReturnLength
0x14000c51c  mov     rcx, [rcx+88h]; TokenHandle
0x14000c523  mov     ebx, r12d
0x14000c526  mov     r9d, 8; TokenInformationLength
0x14000c52c  mov     [rsp+500h+var_4A0], rbx
0x14000c531  mov     edx, 13h; TokenInformationClass
0x14000c536  mov     [rsp+500h+var_4CC], r12d
0x14000c53b  mov     dword ptr [rsp+500h+var_488], r12d
0x14000c540  movups  xmmword ptr [rsp+500h+var_488+4], xmm0
0x14000c545  mov     [rsp+500h+var_4D0], r12d
0x14000c54a  movups  [rbp+400h+var_474], xmm0
0x14000c54e  movups  [rbp+400h+var_464], xmm0
0x14000c552  call    cs:__imp_NtQueryInformationToken
0x14000c558  test    eax, eax
0x14000c55a  js      loc_14000C863
0x14000c560  mov     rcx, [rsp+500h+TokenInformation]; TokenHandle
0x14000c565  lea     rax, [rsp+500h+var_4D0]
0x14000c56a  mov     r9d, 38h ; '8'; TokenInformationLength
0x14000c570  mov     [rsp+500h+ReturnLength], rax; ReturnLength
0x14000c575  lea     r8, [rsp+500h+var_488]; TokenInformation
0x14000c57a  mov     edx, 0Ah; TokenInformationClass
0x14000c57f  call    cs:__imp_GetTokenInformation
0x14000c585  test    eax, eax
0x14000c587  jz      loc_14000C873
0x14000c58d  mov     rbx, qword ptr [rbp+400h+var_480]
0x14000c591  mov     [rsp+500h+var_4A0], rbx
0x14000c596  mov     rcx, [rsp+500h+TokenInformation]; hObject
0x14000c59b  test    rcx, rcx
0x14000c59e  jz      short loc_14000C5A6
0x14000c5a0  call    cs:__imp_CloseHandle
0x14000c5a6  cmp     qword ptr [rsi], 0
0x14000c5aa  lea     rax, WPP_GLOBAL_Control
0x14000c5b1  jnz     loc_14000C6D9
0x14000c5b7  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c5be  cmp     rcx, rax
0x14000c5c1  jz      short loc_14000C5D3
0x14000c5c3  test    byte ptr [rcx+1Ch], 20h
0x14000c5c7  jz      short loc_14000C5D3
0x14000c5c9  cmp     byte ptr [rcx+19h], 4
0x14000c5cd  jnb     loc_14000C8F6
0x14000c5d3  xor     eax, eax
0x14000c5d5  mov     [rbp+400h+var_480], 1F0003h
0x14000c5dc  mov     qword ptr [rsp+500h+EventAttributes.bInheritHandle], rax
0x14000c5e1  lea     rcx, [rsp+500h+var_488]
0x14000c5e6  mov     rax, cs:g_pSidSystem
0x14000c5ed  xorps   xmm0, xmm0
0x14000c5f0  mov     [rsp+500h+var_488], rax
0x14000c5f5  mov     edx, 2
0x14000c5fa  mov     rax, cs:g_pSidService
0x14000c601  mov     [rbp-78h], rax
0x14000c605  movups  xmmword ptr [rsp+500h+EventAttributes.nLength], xmm0
0x14000c60a  mov     [rbp+400h+var_47C], 0
0x14000c60e  mov     dword ptr [rbp+400h+var_474+4], 1F0003h
0x14000c615  mov     byte ptr [rbp+400h+var_474+8], 0
0x14000c619  call    CreateSecurityDescriptor
0x14000c61e  mov     r15, rax
0x14000c621  test    rax, rax
0x14000c624  jz      loc_14000C910
0x14000c62a  mov     rax, [rsp+500h+var_4A8]
0x14000c62f  lea     r8, aGlobal08x08xS; "Global\\%08x%08x_%s"
0x14000c636  mov     r9d, [r14+84h]
0x14000c63d  lea     rcx, [rbp+400h+Name]; unsigned __int16 *
0x14000c641  mov     [rsp+500h+var_4D8], rax
0x14000c646  mov     edx, 200h; unsigned __int64
0x14000c64b  mov     eax, [r14+80h]
0x14000c652  mov     dword ptr [rsp+500h+ReturnLength], eax
0x14000c656  mov     [rsp+500h+EventAttributes.nLength], 18h
0x14000c65e  mov     [rsp+500h+EventAttributes.lpSecurityDescriptor], r15
0x14000c663  mov     [rsp+500h+EventAttributes.bInheritHandle], 0
0x14000c66b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14000c670  lea     r9, [rbp+400h+Name]; lpName
0x14000c674  xor     r8d, r8d; bInitialState
0x14000c677  xor     edx, edx; bManualReset
0x14000c679  lea     rcx, [rsp+500h+EventAttributes]; lpEventAttributes
0x14000c67e  call    cs:__imp_CreateEventW
0x14000c684  mov     r14, rax
0x14000c687  call    cs:__imp_GetLastError
0x14000c68d  mov     [rsp+500h+var_4D0], eax
0x14000c691  test    r14, r14
0x14000c694  jz      loc_14000C965
0x14000c69a  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c6a1  lea     rdx, WPP_GLOBAL_Control
0x14000c6a8  cmp     eax, 0B7h
0x14000c6ad  jz      loc_14000C9B1
0x14000c6b3  test    r15, r15
0x14000c6b6  jnz     loc_14000C87B
0x14000c6bc  mov     [rsi], r14
0x14000c6bf  test    r14, r14
0x14000c6c2  jz      loc_14000C9E8
0x14000c6c8  test    r12d, r12d
0x14000c6cb  jz      short loc_14000C741
0x14000c6cd  mov     r15, [rsp+500h+var_498]
0x14000c6d2  lea     rax, WPP_GLOBAL_Control
0x14000c6d9  cmp     qword ptr [rdi], 0
0x14000c6dd  jnz     short loc_14000C71E
0x14000c6df  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c6e6  cmp     rcx, rax
0x14000c6e9  jz      short loc_14000C6FB
0x14000c6eb  test    byte ptr [rcx+1Ch], 20h
0x14000c6ef  jz      short loc_14000C6FB
0x14000c6f1  cmp     byte ptr [rcx+19h], 4
0x14000c6f5  jnb     loc_14000CAF7
0x14000c6fb  xor     r9d, r9d
0x14000c6fe  xor     r8d, r8d
0x14000c701  mov     rdx, r15
0x14000c704  mov     rcx, rdi
0x14000c707  call    cs:__imp_TpAllocWait
0x14000c70d  test    eax, eax
0x14000c70f  js      loc_14000CB11
0x14000c715  test    r12d, r12d
0x14000c718  jz      loc_14000C892
0x14000c71e  mov     rcx, [rbp+400h+var_50]
0x14000c725  xor     rcx, rsp; StackCookie
0x14000c728  call    __security_check_cookie
0x14000c72d  add     rsp, 4C8h
0x14000c734  pop     r15
0x14000c736  pop     r14
0x14000c738  pop     r13
0x14000c73a  pop     r12
0x14000c73c  pop     rdi
0x14000c73d  pop     rsi
0x14000c73e  pop     rbx
0x14000c73f  pop     rbp
0x14000c740  retn
0x14000c741  xor     eax, eax
0x14000c743  mov     [rbp+400h+var_480], 1F0003h
0x14000c74a  mov     qword ptr [rsp+500h+EventAttributes.bInheritHandle], rax
0x14000c74f  lea     rcx, [rsp+500h+var_488]
0x14000c754  mov     rax, cs:g_pSidSystem
0x14000c75b  xorps   xmm0, xmm0
0x14000c75e  mov     [rsp+500h+var_488], rax
0x14000c763  mov     edx, 2
0x14000c768  mov     rax, cs:g_pSidService
0x14000c76f  mov     [rbp-78h], rax
0x14000c773  movups  xmmword ptr [rsp+500h+EventAttributes.nLength], xmm0
0x14000c778  mov     [rbp+400h+var_47C], 0
0x14000c77c  mov     dword ptr [rbp+400h+var_474+4], 1F0003h
0x14000c783  mov     byte ptr [rbp+400h+var_474+8], 0
0x14000c787  call    CreateSecurityDescriptor
0x14000c78c  mov     rsi, rax
0x14000c78f  test    rax, rax
0x14000c792  jz      loc_14000CA2A
0x14000c798  lea     r15, WPP_GLOBAL_Control
0x14000c79f  mov     rax, [rsp+500h+var_4A8]
0x14000c7a4  lea     r8, aGlobal08x08xS; "Global\\%08x%08x_%s"
0x14000c7ab  mov     r9d, dword ptr [rsp+500h+var_4A0+4]
0x14000c7b0  lea     rcx, [rbp+400h+Name]; unsigned __int16 *
0x14000c7b4  mov     [rsp+500h+var_4D8], rax
0x14000c7b9  mov     edx, 200h; unsigned __int64
0x14000c7be  mov     dword ptr [rsp+500h+ReturnLength], ebx
0x14000c7c2  mov     [rsp+500h+EventAttributes.nLength], 18h
0x14000c7ca  mov     [rsp+500h+EventAttributes.lpSecurityDescriptor], rsi
0x14000c7cf  mov     [rsp+500h+EventAttributes.bInheritHandle], 0
0x14000c7d7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14000c7dc  lea     r9, [rbp+400h+Name]; lpName
0x14000c7e0  xor     r8d, r8d; bInitialState
0x14000c7e3  xor     edx, edx; bManualReset
0x14000c7e5  lea     rcx, [rsp+500h+EventAttributes]; lpEventAttributes
0x14000c7ea  call    cs:__imp_CreateEventW
0x14000c7f0  mov     rbx, rax
0x14000c7f3  call    cs:__imp_GetLastError
0x14000c7f9  mov     r14d, eax
0x14000c7fc  test    rbx, rbx
0x14000c7ff  jz      loc_14000CA7F
0x14000c805  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c80c  cmp     r14d, 0B7h
0x14000c813  jz      loc_14000CAC0
0x14000c819  test    rsi, rsi
0x14000c81c  jnz     short loc_14000C888
0x14000c81e  mov     [r13+0], rbx
0x14000c822  test    rbx, rbx
0x14000c825  jnz     loc_14000C6CD
0x14000c82b  mov     rax, cs:WPP_GLOBAL_Control
0x14000c832  cmp     rax, r15
0x14000c835  jz      loc_14000C71E
0x14000c83b  test    byte ptr [rax+1Ch], 20h
0x14000c83f  jz      loc_14000C71E
0x14000c845  cmp     byte ptr [rax+19h], 2
0x14000c849  jb      loc_14000C71E
0x14000c84f  call    cs:__imp_GetLastError
0x14000c855  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c85c  mov     edx, 83h
0x14000c861  jmp     short loc_14000C8DE
0x14000c863  mov     ecx, eax; Status
0x14000c865  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x14000c86b  mov     r12d, eax
0x14000c86e  jmp     loc_14000C596
0x14000c873  call    cs:__imp_GetLastError
0x14000c879  jmp     short loc_14000C86B
0x14000c87b  mov     rcx, r15; lpMem
0x14000c87e  call    DeleteSecurityDescriptor
0x14000c883  jmp     loc_14000C6BC
0x14000c888  mov     rcx, rsi; lpMem
0x14000c88b  call    DeleteSecurityDescriptor
0x14000c890  jmp     short loc_14000C81E
0x14000c892  mov     rcx, [rsp+500h+var_490]
0x14000c897  xor     r9d, r9d
0x14000c89a  xor     r8d, r8d
0x14000c89d  mov     rdx, r15
0x14000c8a0  call    cs:__imp_TpAllocWait
0x14000c8a6  test    eax, eax
0x14000c8a8  jns     loc_14000C71E
0x14000c8ae  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c8b5  lea     rdx, WPP_GLOBAL_Control
0x14000c8bc  cmp     rcx, rdx
0x14000c8bf  jz      loc_14000C71E
0x14000c8c5  test    byte ptr [rcx+1Ch], 20h
0x14000c8c9  jz      loc_14000C71E
0x14000c8cf  cmp     byte ptr [rcx+19h], 2
0x14000c8d3  jb      loc_14000C71E
0x14000c8d9  mov     edx, 86h
0x14000c8de  mov     rcx, [rcx+10h]
0x14000c8e2  lea     r8, WPP_586e3f58e70b3bd7f4fb97bd2f93cbf8_Traceguids
0x14000c8e9  mov     r9d, eax
0x14000c8ec  call    WPP_SF_d
0x14000c8f1  jmp     loc_14000C71E
0x14000c8f6  mov     rcx, [rcx+10h]
0x14000c8fa  lea     r8, WPP_586e3f58e70b3bd7f4fb97bd2f93cbf8_Traceguids
0x14000c901  mov     edx, 81h
0x14000c906  call    WPP_SF_
0x14000c90b  jmp     loc_14000C5D3
0x14000c910  mov     rax, cs:WPP_GLOBAL_Control
0x14000c917  lea     rdx, WPP_GLOBAL_Control
0x14000c91e  cmp     rax, rdx
0x14000c921  jz      loc_14000C62A
0x14000c927  test    byte ptr [rax+1Ch], 1
0x14000c92b  jz      loc_14000C62A
0x14000c931  cmp     byte ptr [rax+19h], 2
0x14000c935  jb      loc_14000C62A
0x14000c93b  call    cs:__imp_GetLastError
0x14000c941  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c948  lea     r8, WPP_6767f1e3976c37dffaa064fbfa18a65b_Traceguids
0x14000c94f  mov     edx, 5Ch ; '\'
0x14000c954  mov     r9d, eax
0x14000c957  mov     rcx, [rcx+10h]
0x14000c95b  call    WPP_SF_d
0x14000c960  jmp     loc_14000C62A
0x14000c965  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c96c  lea     rdx, WPP_GLOBAL_Control
0x14000c973  cmp     rcx, rdx
0x14000c976  jz      loc_14000C6A8
0x14000c97c  test    byte ptr [rcx+1Ch], 1
0x14000c980  jz      loc_14000C6A8
0x14000c986  cmp     byte ptr [rcx+19h], 2
0x14000c98a  jb      loc_14000C6A8
0x14000c990  mov     rcx, [rcx+10h]
0x14000c994  lea     r8, WPP_6767f1e3976c37dffaa064fbfa18a65b_Traceguids
0x14000c99b  mov     edx, 5Dh ; ']'
0x14000c9a0  mov     r9d, eax
0x14000c9a3  call    WPP_SF_d
0x14000c9a8  mov     eax, [rsp+500h+var_4D0]
0x14000c9ac  jmp     loc_14000C69A
0x14000c9b1  cmp     rcx, rdx
0x14000c9b4  jz      loc_14000C6B3
0x14000c9ba  test    byte ptr [rcx+1Ch], 1
0x14000c9be  jz      loc_14000C6B3
0x14000c9c4  cmp     byte ptr [rcx+19h], 2
0x14000c9c8  jb      loc_14000C6B3
0x14000c9ce  mov     rcx, [rcx+10h]
0x14000c9d2  lea     r8, WPP_6767f1e3976c37dffaa064fbfa18a65b_Traceguids
0x14000c9d9  mov     edx, 5Eh ; '^'
0x14000c9de  call    WPP_SF_
0x14000c9e3  jmp     loc_14000C6B3
0x14000c9e8  mov     rax, cs:WPP_GLOBAL_Control
0x14000c9ef  lea     rdx, WPP_GLOBAL_Control
0x14000c9f6  cmp     rax, rdx
0x14000c9f9  jz      loc_14000C71E
0x14000c9ff  test    byte ptr [rax+1Ch], 20h
0x14000ca03  jz      loc_14000C71E
0x14000ca09  cmp     byte ptr [rax+19h], 2
  ... truncated ...
```
