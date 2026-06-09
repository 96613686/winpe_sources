# CreateDrvInstAlertEvents

- ea: `0x1800020e0`
- end: `0x1800024c7`
- name: `CreateDrvInstAlertEvents`
- size: `999`
- prototype: `_BOOL8()`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18000cf30`

## callees

- `0x1800020e0`
- `0x1800040f0`
- `0x180011964`
- `0x18001893e`
- `0x180018970`

## import_xrefs

- `msvcrt!_itow_s` at `0x1800022e2`
- `msvcrt!_itow_s` at `0x1800022e2`
- `ntdll!RtlRandomEx` at `0x18000229e`
- `ntdll!RtlRandomEx` at `0x18000229e`
- `ntdll!RtlCreateServiceSid` at `0x18000216a`
- `ntdll!RtlCreateServiceSid` at `0x18000216a`
- `ntdll!RtlInitUnicodeString` at `0x180002145`
- `ntdll!RtlInitUnicodeString` at `0x180002145`
- `ntdll!RtlNtStatusToDosError` at `0x180002179`
- `ntdll!RtlNtStatusToDosError` at `0x180002179`
- `ntdll!RtlFreeHeap` at `0x18000248d`
- `ntdll!RtlFreeHeap` at `0x18000248d`
- `ntdll!RtlAllocateHeap` at `0x1800021cd`
- `ntdll!RtlAllocateHeap` at `0x1800021cd`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180002363`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180002428`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180002363`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180002428`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180002378`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800023bb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000243d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000247b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000249d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180002378`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800023bb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000243d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000247b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000249d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800021f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000236e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002382`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002433`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002447`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800021f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000236e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002382`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002433`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002447`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000212f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000212f`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180002199`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800021a5`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180002199`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800021a5`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x1800021ea`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x1800021ea`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x18000221b`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x180002246`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x18000221b`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x180002246`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x18000225a`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x18000225a`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180002274`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180002274`

## string_xrefs

- `0x180002135`: `DeviceInstall`

## pseudocode

```c
_BOOL8 CreateDrvInstAlertEvents()
{
  int v0; // eax
  DWORD LastError; // ebx
  DWORD LengthSid; // edi
  DWORD v3; // edi
  struct _ACL *Heap; // rax
  struct _ACL *v5; // rsi
  ULONG v6; // eax
  _QWORD *v7; // rcx
  __int64 v8; // rdx
  HANDLE v9; // rax
  DWORD v10; // ebx
  HANDLE v11; // rax
  DWORD v12; // edi
  ULONG ServiceSidLength; // [rsp+30h] [rbp-D0h] BYREF
  ULONG Seed; // [rsp+34h] [rbp-CCh] BYREF
  _SECURITY_ATTRIBUTES EventAttributes; // [rsp+38h] [rbp-C8h] BYREF
  _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-B0h] BYREF
  _OWORD pSecurityDescriptor[2]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v19; // [rsp+80h] [rbp-80h]
  _BYTE ServiceSid[80]; // [rsp+90h] [rbp-70h] BYREF
  WCHAR Name[264]; // [rsp+E0h] [rbp-20h] BYREF

  ServiceSidLength = 68;
  DestinationString = 0;
  v19 = 0;
  memset(pSecurityDescriptor, 0, sizeof(pSecurityDescriptor));
  memset(&EventAttributes, 0, 20);
  Seed = GetTickCount();
  RtlInitUnicodeString(&DestinationString, L"DeviceInstall");
  memset_0(ServiceSid, 0, 0x44u);
  v0 = RtlCreateServiceSid(&DestinationString, ServiceSid, &ServiceSidLength);
  if ( v0 < 0 )
  {
    LastError = RtlNtStatusToDosError(v0);
    goto LABEL_33;
  }
  LengthSid = GetLengthSid(*(PSID *)(PnpSvchostGlobalData + 32));
  LastError = 8;
  v3 = GetLengthSid(ServiceSid) + 24 + LengthSid;
  if ( v3 <= 0xF42400 )
  {
    Heap = (struct _ACL *)RtlAllocateHeap(PnpHeapHandle, 8u, v3);
    v5 = Heap;
    if ( Heap )
    {
      if ( !InitializeAcl(Heap, v3, 2u)
        || !AddAccessAllowedAceEx(v5, 2u, 0, 0x1F0003u, ServiceSid)
        || !AddAccessAllowedAceEx(v5, 2u, 0, 0x100000u, *(PSID *)(PnpSvchostGlobalData + 32))
        || !InitializeSecurityDescriptor(pSecurityDescriptor, 1u)
        || !SetSecurityDescriptorDacl(pSecurityDescriptor, 1, v5, 0) )
      {
        LastError = GetLastError();
LABEL_32:
        RtlFreeHeap(PnpHeapHandle, 0, v5);
        goto LABEL_33;
      }
      EventAttributes.nLength = 24;
      EventAttributes.lpSecurityDescriptor = pSecurityDescriptor;
      EventAttributes.bInheritHandle = 0;
      v6 = RtlRandomEx(&Seed);
      *(_QWORD *)&PnpServiceEventIdentifier = 0;
      word_180023958 = 0;
      _itow_s(v6 % 0xFFFF, &PnpServiceEventIdentifier, 5u, 16);
      if ( (int)RtlStringCchPrintfW(Name, 260, L"Global\\DrvInst_Shutdown_Pending_%ws", &PnpServiceEventIdentifier) < 0 )
      {
        LastError = 1359;
        v7 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_32;
        v8 = 13;
        goto LABEL_15;
      }
      PnpServiceShutdownPendingEvent = 0;
      v9 = CreateEventW(&EventAttributes, 1, 0, Name);
      if ( v9 )
      {
        PnpServiceShutdownPendingEvent = v9;
        SetLastError(0);
      }
      else
      {
        v10 = GetLastError();
        SetLastError(v10);
        if ( v10 )
        {
          LastError = GetLastError();
          v7 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            goto LABEL_32;
          v8 = 14;
LABEL_15:
          WPP_SF_d(v7[2], v8, WPP_0e80b14c55a13f72cdcecc79ffb17787_Traceguids, LastError);
          goto LABEL_32;
        }
      }
      if ( (int)RtlStringCchPrintfW(Name, 260, L"Global\\DrvInst_Abort_%ws", &PnpServiceEventIdentifier) >= 0 )
      {
        PnpServiceShutdownAbortEvent = 0;
        LastError = 0;
        v11 = CreateEventW(&EventAttributes, 1, 0, Name);
        if ( v11 )
        {
          PnpServiceShutdownAbortEvent = v11;
          SetLastError(0);
          goto LABEL_32;
        }
        v12 = GetLastError();
        SetLastError(v12);
        if ( !v12 )
          goto LABEL_32;
        LastError = GetLastError();
        v7 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_32;
        v8 = 16;
      }
      else
      {
        LastError = 1359;
        v7 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_32;
        v8 = 15;
      }
      goto LABEL_15;
    }
  }
LABEL_33:
  SetLastError(LastError);
  return LastError == 0;
}

```

## disassembly

```asm
0x1800020e0  push    rbp
0x1800020e2  push    rbx
0x1800020e3  push    rsi
0x1800020e4  push    r14
0x1800020e6  lea     rbp, [rsp-208h]
0x1800020ee  sub     rsp, 308h
0x1800020f5  mov     rax, cs:__security_cookie
0x1800020fc  xor     rax, rsp
0x1800020ff  mov     [rbp+220h+var_30], rax
0x180002106  xorps   xmm0, xmm0
0x180002109  mov     [rsp+320h+ServiceSidLength], 44h ; 'D'
0x180002111  xor     eax, eax
0x180002113  movups  xmmword ptr [rsp+320h+DestinationString.Length], xmm0
0x180002118  mov     [rbp+220h+var_2A0], rax
0x18000211c  movups  [rsp+320h+pSecurityDescriptor], xmm0
0x180002121  mov     [rsp+320h+EventAttributes.bInheritHandle], eax
0x180002125  movups  [rsp+320h+var_2B0], xmm0
0x18000212a  movups  xmmword ptr [rsp+320h+EventAttributes.nLength], xmm0
0x18000212f  call    cs:__imp_GetTickCount
0x180002135  lea     rdx, ServiceName; "DeviceInstall"
0x18000213c  mov     [rsp+320h+Seed], eax
0x180002140  lea     rcx, [rsp+320h+DestinationString]; DestinationString
0x180002145  call    cs:__imp_RtlInitUnicodeString
0x18000214b  xor     edx, edx; Val
0x18000214d  lea     rcx, [rbp+220h+ServiceSid]; void *
0x180002151  mov     r8d, 44h ; 'D'; Size
0x180002157  call    memset_0
0x18000215c  lea     r8, [rsp+320h+ServiceSidLength]; ServiceSidLength
0x180002161  lea     rdx, [rbp+220h+ServiceSid]; ServiceSid
0x180002165  lea     rcx, [rsp+320h+DestinationString]; ServiceName
0x18000216a  call    cs:__imp_RtlCreateServiceSid
0x180002170  xor     r14d, r14d
0x180002173  test    eax, eax
0x180002175  jns     short loc_180002186
0x180002177  mov     ecx, eax; Status
0x180002179  call    cs:__imp_RtlNtStatusToDosError
0x18000217f  mov     ebx, eax
0x180002181  jmp     loc_18000249B
0x180002186  mov     rcx, cs:PnpSvchostGlobalData
0x18000218d  mov     [rsp+320h+arg_0], rdi
0x180002195  mov     rcx, [rcx+20h]; pSid
0x180002199  call    cs:__imp_GetLengthSid
0x18000219f  lea     rcx, [rbp+220h+ServiceSid]; pSid
0x1800021a3  mov     edi, eax
0x1800021a5  call    cs:__imp_GetLengthSid
0x1800021ab  add     eax, 18h
0x1800021ae  mov     ebx, 8
0x1800021b3  add     edi, eax
0x1800021b5  cmp     edi, 0F42400h
0x1800021bb  ja      loc_180002493
0x1800021c1  mov     rcx, cs:PnpHeapHandle; HeapHandle
0x1800021c8  mov     edx, ebx; Flags
0x1800021ca  mov     r8d, edi; Size
0x1800021cd  call    cs:__imp_RtlAllocateHeap
0x1800021d3  mov     rsi, rax
0x1800021d6  test    rax, rax
0x1800021d9  jz      loc_180002493
0x1800021df  mov     r8d, 2; dwAclRevision
0x1800021e5  mov     edx, edi; nAclLength
0x1800021e7  mov     rcx, rax; pAcl
0x1800021ea  call    cs:__imp_InitializeAcl
0x1800021f0  test    eax, eax
0x1800021f2  jnz     short loc_180002201
0x1800021f4  call    cs:__imp_GetLastError
0x1800021fa  mov     ebx, eax
0x1800021fc  jmp     loc_180002481
0x180002201  lea     rax, [rbp+220h+ServiceSid]
0x180002205  mov     r9d, 1F0003h; AccessMask
0x18000220b  xor     r8d, r8d; AceFlags
0x18000220e  mov     [rsp+320h+pSid], rax; pSid
0x180002213  mov     edx, 2; dwAceRevision
0x180002218  mov     rcx, rsi; pAcl
0x18000221b  call    cs:__imp_AddAccessAllowedAceEx
0x180002221  test    eax, eax
0x180002223  jz      short loc_1800021F4
0x180002225  mov     rax, cs:PnpSvchostGlobalData
0x18000222c  mov     r9d, 100000h; AccessMask
0x180002232  xor     r8d, r8d; AceFlags
0x180002235  mov     edx, 2; dwAceRevision
0x18000223a  mov     rcx, [rax+20h]
0x18000223e  mov     [rsp+320h+pSid], rcx; pSid
0x180002243  mov     rcx, rsi; pAcl
0x180002246  call    cs:__imp_AddAccessAllowedAceEx
0x18000224c  test    eax, eax
0x18000224e  jz      short loc_1800021F4
0x180002250  mov     edx, 1; dwRevision
0x180002255  lea     rcx, [rsp+320h+pSecurityDescriptor]; pSecurityDescriptor
0x18000225a  call    cs:__imp_InitializeSecurityDescriptor
0x180002260  test    eax, eax
0x180002262  jz      short loc_1800021F4
0x180002264  xor     r9d, r9d; bDaclDefaulted
0x180002267  lea     rcx, [rsp+320h+pSecurityDescriptor]; pSecurityDescriptor
0x18000226c  mov     r8, rsi; pDacl
0x18000226f  mov     edx, 1; bDaclPresent
0x180002274  call    cs:__imp_SetSecurityDescriptorDacl
0x18000227a  test    eax, eax
0x18000227c  jz      loc_1800021F4
0x180002282  lea     rax, [rsp+320h+pSecurityDescriptor]
0x180002287  mov     [rsp+320h+EventAttributes.nLength], 18h
0x18000228f  lea     rcx, [rsp+320h+Seed]; Seed
0x180002294  mov     [rsp+320h+EventAttributes.lpSecurityDescriptor], rax
0x180002299  mov     [rsp+320h+EventAttributes.bInheritHandle], r14d
0x18000229e  call    cs:__imp_RtlRandomEx
0x1800022a4  mov     r8d, eax
0x1800022a7  mov     r9d, 10h; Radix
0x1800022ad  mov     eax, 80008001h
0x1800022b2  mul     r8d
0x1800022b5  xor     eax, eax
0x1800022b7  shr     edx, 0Fh
0x1800022ba  imul    ecx, edx, 0FFFFh
0x1800022c0  lea     rdx, PnpServiceEventIdentifier; Buffer
0x1800022c7  mov     cs:PnpServiceEventIdentifier, rax
0x1800022ce  mov     cs:word_180023958, ax
0x1800022d5  sub     r8d, ecx
0x1800022d8  movzx   ecx, r8w; Value
0x1800022dc  mov     r8d, 5; BufferCount
0x1800022e2  call    cs:__imp__itow_s
0x1800022e8  lea     r9, PnpServiceEventIdentifier
0x1800022ef  mov     edx, 104h
0x1800022f4  lea     r8, aGlobalDrvinstS; "Global\\DrvInst_Shutdown_Pending_%ws"
0x1800022fb  lea     rcx, [rbp+220h+Name]
0x1800022ff  call    RtlStringCchPrintfW
0x180002304  test    eax, eax
0x180002306  jns     short loc_18000234B
0x180002308  mov     ebx, 54Fh
0x18000230d  mov     rcx, cs:WPP_GLOBAL_Control
0x180002314  lea     rax, WPP_GLOBAL_Control
0x18000231b  cmp     rcx, rax
0x18000231e  jz      loc_180002481
0x180002324  test    byte ptr [rcx+1Ch], 1
0x180002328  jz      loc_180002481
0x18000232e  mov     edx, 0Dh
0x180002333  mov     rcx, [rcx+10h]
0x180002337  lea     r8, WPP_0e80b14c55a13f72cdcecc79ffb17787_Traceguids
0x18000233e  mov     r9d, ebx
0x180002341  call    WPP_SF_d
0x180002346  jmp     loc_180002481
0x18000234b  lea     r9, [rbp+220h+Name]; lpName
0x18000234f  mov     cs:PnpServiceShutdownPendingEvent, r14
0x180002356  xor     r8d, r8d; bInitialState
0x180002359  lea     rcx, [rsp+320h+EventAttributes]; lpEventAttributes
0x18000235e  mov     edx, 1; bManualReset
0x180002363  call    cs:__imp_CreateEventW
0x180002369  test    rax, rax
0x18000236c  jnz     short loc_1800023B2
0x18000236e  call    cs:__imp_GetLastError
0x180002374  mov     ebx, eax
0x180002376  mov     ecx, eax; dwErrCode
0x180002378  call    cs:__imp_SetLastError
0x18000237e  test    ebx, ebx
0x180002380  jz      short loc_1800023C1
0x180002382  call    cs:__imp_GetLastError
0x180002388  mov     ebx, eax
0x18000238a  mov     rcx, cs:WPP_GLOBAL_Control
0x180002391  lea     rax, WPP_GLOBAL_Control
0x180002398  cmp     rcx, rax
0x18000239b  jz      loc_180002481
0x1800023a1  test    byte ptr [rcx+1Ch], 1
0x1800023a5  jz      loc_180002481
0x1800023ab  mov     edx, 0Eh
0x1800023b0  jmp     short loc_180002333
0x1800023b2  xor     ecx, ecx; dwErrCode
0x1800023b4  mov     cs:PnpServiceShutdownPendingEvent, rax
0x1800023bb  call    cs:__imp_SetLastError
0x1800023c1  lea     r9, PnpServiceEventIdentifier
0x1800023c8  mov     edx, 104h
0x1800023cd  lea     r8, aGlobalDrvinstA; "Global\\DrvInst_Abort_%ws"
0x1800023d4  lea     rcx, [rbp+220h+Name]
0x1800023d8  call    RtlStringCchPrintfW
0x1800023dd  test    eax, eax
0x1800023df  jns     short loc_18000240D
0x1800023e1  mov     ebx, 54Fh
0x1800023e6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800023ed  lea     rax, WPP_GLOBAL_Control
0x1800023f4  cmp     rcx, rax
0x1800023f7  jz      loc_180002481
0x1800023fd  test    byte ptr [rcx+1Ch], 1
0x180002401  jz      short loc_180002481
0x180002403  mov     edx, 0Fh
0x180002408  jmp     loc_180002333
0x18000240d  lea     r9, [rbp+220h+Name]; lpName
0x180002411  mov     cs:PnpServiceShutdownAbortEvent, r14
0x180002418  xor     r8d, r8d; bInitialState
0x18000241b  lea     rcx, [rsp+320h+EventAttributes]; lpEventAttributes
0x180002420  mov     edx, 1; bManualReset
0x180002425  mov     ebx, r14d
0x180002428  call    cs:__imp_CreateEventW
0x18000242e  test    rax, rax
0x180002431  jnz     short loc_180002472
0x180002433  call    cs:__imp_GetLastError
0x180002439  mov     edi, eax
0x18000243b  mov     ecx, eax; dwErrCode
0x18000243d  call    cs:__imp_SetLastError
0x180002443  test    edi, edi
0x180002445  jz      short loc_180002481
0x180002447  call    cs:__imp_GetLastError
0x18000244d  mov     ebx, eax
0x18000244f  mov     rcx, cs:WPP_GLOBAL_Control
0x180002456  lea     rax, WPP_GLOBAL_Control
0x18000245d  cmp     rcx, rax
0x180002460  jz      short loc_180002481
0x180002462  test    byte ptr [rcx+1Ch], 1
0x180002466  jz      short loc_180002481
0x180002468  mov     edx, 10h
0x18000246d  jmp     loc_180002333
0x180002472  xor     ecx, ecx; dwErrCode
0x180002474  mov     cs:PnpServiceShutdownAbortEvent, rax
0x18000247b  call    cs:__imp_SetLastError
0x180002481  mov     rcx, cs:PnpHeapHandle; HeapHandle
0x180002488  mov     r8, rsi; P
0x18000248b  xor     edx, edx; Flags
0x18000248d  call    cs:__imp_RtlFreeHeap
0x180002493  mov     rdi, [rsp+320h+arg_0]
0x18000249b  mov     ecx, ebx; dwErrCode
0x18000249d  call    cs:__imp_SetLastError
0x1800024a3  test    ebx, ebx
0x1800024a5  mov     eax, r14d
0x1800024a8  setz    al
0x1800024ab  mov     rcx, [rbp+220h+var_30]
0x1800024b2  xor     rcx, rsp; StackCookie
0x1800024b5  call    __security_check_cookie
0x1800024ba  add     rsp, 308h
0x1800024c1  pop     r14
0x1800024c3  pop     rsi
0x1800024c4  pop     rbx
0x1800024c5  pop     rbp
0x1800024c6  retn
```
