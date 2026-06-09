# CNetworkAddresses::RunPublisher(void)

- ea: `0x1800e7660`
- end: `0x1800e7891`
- name: `?RunPublisher@CNetworkAddresses@@SAJXZ`
- size: `561`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800e6f98`

## callees

- `0x18000c050`
- `0x18001a9c0`
- `0x18001ad00`
- `0x180039d60`
- `0x18003c814`
- `0x1800e7660`
- `0x180110b60`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e7731`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e778b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e77c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e7808`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e783b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e7731`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e778b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e77c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e7808`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e783b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800e7719`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800e7779`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800e77b6`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800e77f6`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800e7719`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800e7779`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800e77b6`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800e77f6`

## string_xrefs

- `0x1800e76a0`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\networkaddresses.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 CNetworkAddresses::RunPublisher(void)
{
  signed int LastError; // eax
  unsigned int v1; // r8d
  void *v2; // rdx
  unsigned int (*v3)(void *); // rcx
  int v4; // r8d
  unsigned int v5; // ebx
  char *v7; // [rsp+20h] [rbp-40h]
  _BYTE v8[16]; // [rsp+30h] [rbp-30h] BYREF
  _QWORD v9[4]; // [rsp+40h] [rbp-20h] BYREF
  int v10; // [rsp+80h] [rbp+20h] BYREF

  v10 = 0;
  v9[0] = "CNetworkAddresses::RunPublisher";
  v9[1] = &v10;
  v9[2] = 0;
  v9[3] = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\networkaddresses.cpp",
    "CNetworkAddresses::RunPublisher",
    (const char *)0x2E,
    0,
    (const unsigned __int16 *)v7);
  if ( CNetworkAddresses::m_fInitialized )
  {
    if ( CNetworkAddresses::m_fRunning )
      goto LABEL_33;
    CComCritSecLockWTry<CComAutoCriticalSectionWTry>::CComCritSecLockWTry<CComAutoCriticalSectionWTry>(
      (__int64)v8,
      (struct _RTL_CRITICAL_SECTION *)CNetworkAddresses::m_csPublisher,
      1);
    if ( !CNetworkAddresses::m_fRunning )
    {
      CNetworkAddresses::m_hStopPublisher = CreateEventW(0, 1, 0, 0);
      if ( CNetworkAddresses::m_hStopPublisher )
        goto LABEL_11;
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      v10 = LastError;
      if ( LastError >= 0 )
      {
LABEL_11:
        CNetworkAddresses::m_hNewRequest = CreateEventW(0, 1, 0, 0);
        if ( CNetworkAddresses::m_hNewRequest )
          goto LABEL_16;
        LastError = GetLastError();
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        v10 = LastError;
        if ( LastError >= 0 )
        {
LABEL_16:
          CNetworkAddresses::m_hRequest = CreateEventW(0, 1, 0, 0);
          if ( CNetworkAddresses::m_hRequest )
            goto LABEL_21;
          LastError = GetLastError();
          if ( LastError > 0 )
            LastError = (unsigned __int16)LastError | 0x80070000;
          v10 = LastError;
          if ( LastError >= 0 )
          {
LABEL_21:
            CNetworkAddresses::m_hWaitEvent = CreateEventW(0, 1, 0, 0);
            if ( CNetworkAddresses::m_hWaitEvent )
              goto LABEL_26;
            LastError = GetLastError();
            if ( LastError > 0 )
              LastError = (unsigned __int16)LastError | 0x80070000;
            v10 = LastError;
            if ( LastError >= 0 )
            {
LABEL_26:
              CNetworkAddresses::m_hPublisherThread = IDCRLCreateThread(v3, v2, v4);
              if ( CNetworkAddresses::m_hPublisherThread )
                goto LABEL_31;
              LastError = GetLastError();
              if ( LastError > 0 )
                LastError = (unsigned __int16)LastError | 0x80070000;
              v10 = LastError;
              if ( LastError >= 0 )
              {
LABEL_31:
                CNetworkAddresses::m_fRunning = 1;
                goto LABEL_32;
              }
              v1 = 64;
            }
            else
            {
              v1 = 62;
            }
          }
          else
          {
            v1 = 60;
          }
        }
        else
        {
          v1 = 58;
        }
      }
      else
      {
        v1 = 56;
      }
      Telemetry::IfFailExit(
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\networkaddresses.cpp",
        "CNetworkAddresses::RunPublisher",
        v1,
        LastError,
        "hr = HRESULT_FROM_WIN32(GetLastError())");
    }
LABEL_32:
    CComCritSecLockWTry<CComAutoCriticalSectionWTry>::~CComCritSecLockWTry<CComAutoCriticalSectionWTry>((__int64)v8);
    goto LABEL_33;
  }
  v10 = -2147418113;
  Telemetry::IfFailExit(
    "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\networkaddresses.cpp",
    "CNetworkAddresses::RunPublisher",
    0x30u,
    -2147418113,
    "m_fInitialized");
LABEL_33:
  v5 = v10;
  CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v9);
  return v5;
}

```

## disassembly

```asm
0x1800e7660  mov     [rsp-18h+arg_8], rbx
0x1800e7665  mov     [rsp-18h+arg_10], rdi
0x1800e766a  push    rbp
0x1800e766b  push    r14
0x1800e766d  push    r15
0x1800e766f  mov     rbp, rsp
0x1800e7672  sub     rsp, 60h
0x1800e7676  xor     ebx, ebx
0x1800e7678  mov     [rbp+arg_0], ebx
0x1800e767b  lea     rdi, aCnetworkaddres_12; "CNetworkAddresses::RunPublisher"
0x1800e7682  mov     [rbp+var_20], rdi
0x1800e7686  lea     rax, [rbp+arg_0]
0x1800e768a  mov     [rbp+var_18], rax
0x1800e768e  mov     [rbp+var_10], rbx
0x1800e7692  mov     [rbp+var_8], rbx
0x1800e7696  xor     r9d, r9d; unsigned int
0x1800e7699  lea     r8d, [rbx+2Eh]; char *
0x1800e769d  mov     rdx, rdi; char *
0x1800e76a0  lea     r14, aOnecoreuapDsEx_88; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x1800e76a7  mov     rcx, r14; this
0x1800e76aa  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x1800e76af  nop
0x1800e76b0  cmp     cs:?m_fInitialized@CNetworkAddresses@@0EA, bl; uchar CNetworkAddresses::m_fInitialized
0x1800e76b6  jnz     short loc_1800E76E2
0x1800e76b8  mov     r9d, 8000FFFFh; int
0x1800e76be  mov     [rbp+arg_0], r9d
0x1800e76c2  lea     rax, aMFinitialized; "m_fInitialized"
0x1800e76c9  mov     [rsp+60h+var_40], rax; char *
0x1800e76ce  lea     r8d, [rbx+30h]; unsigned int
0x1800e76d2  mov     rdx, rdi; char *
0x1800e76d5  mov     rcx, r14; char *
0x1800e76d8  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x1800e76dd  jmp     loc_1800E786D
0x1800e76e2  cmp     cs:?m_fRunning@CNetworkAddresses@@0EA, bl; uchar CNetworkAddresses::m_fRunning
0x1800e76e8  jnz     loc_1800E786D
0x1800e76ee  mov     r8b, 1
0x1800e76f1  lea     rdx, ?m_csPublisher@CNetworkAddresses@@0VCThreadProtected@@A; CThreadProtected CNetworkAddresses::m_csPublisher
0x1800e76f8  lea     rcx, [rbp+var_30]
0x1800e76fc  call    ??0?$CComCritSecLockWTry@VCComAutoCriticalSectionWTry@@@@QEAA@AEAVCComAutoCriticalSectionWTry@@_N@Z; CComCritSecLockWTry<CComAutoCriticalSectionWTry>::CComCritSecLockWTry<CComAutoCriticalSectionWTry>(CComAutoCriticalSectionWTry &,bool)
0x1800e7701  cmp     cs:?m_fRunning@CNetworkAddresses@@0EA, bl; uchar CNetworkAddresses::m_fRunning
0x1800e7707  jnz     loc_1800E7864
0x1800e770d  xor     r9d, r9d; lpName
0x1800e7710  xor     r8d, r8d; bInitialState
0x1800e7713  lea     edx, [r9+1]; bManualReset
0x1800e7717  xor     ecx, ecx; lpEventAttributes
0x1800e7719  call    cs:__imp_CreateEventW
0x1800e771f  mov     cs:?m_hStopPublisher@CNetworkAddresses@@0PEAXEA, rax; void * CNetworkAddresses::m_hStopPublisher
0x1800e7726  mov     r15d, 80070000h
0x1800e772c  test    rax, rax
0x1800e772f  jnz     short loc_1800E776D
0x1800e7731  call    cs:__imp_GetLastError
0x1800e7737  test    eax, eax
0x1800e7739  jle     short loc_1800E7741
0x1800e773b  movzx   eax, ax
0x1800e773e  or      eax, r15d
0x1800e7741  mov     [rbp+arg_0], eax
0x1800e7744  test    eax, eax
0x1800e7746  jns     short loc_1800E776D
0x1800e7748  mov     r8d, 38h ; '8'; unsigned int
0x1800e774e  lea     rcx, aHrHresultFromW_10; "hr = HRESULT_FROM_WIN32(GetLastError())"
0x1800e7755  mov     [rsp+60h+var_40], rcx; char *
0x1800e775a  mov     r9d, eax; int
0x1800e775d  mov     rdx, rdi; char *
0x1800e7760  mov     rcx, r14; char *
0x1800e7763  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x1800e7768  jmp     loc_1800E7864
0x1800e776d  xor     r9d, r9d; lpName
0x1800e7770  xor     r8d, r8d; bInitialState
0x1800e7773  lea     edx, [r9+1]; bManualReset
0x1800e7777  xor     ecx, ecx; lpEventAttributes
0x1800e7779  call    cs:__imp_CreateEventW
0x1800e777f  mov     cs:?m_hNewRequest@CNetworkAddresses@@0PEAXEA, rax; void * CNetworkAddresses::m_hNewRequest
0x1800e7786  test    rax, rax
0x1800e7789  jnz     short loc_1800E77AA
0x1800e778b  call    cs:__imp_GetLastError
0x1800e7791  test    eax, eax
0x1800e7793  jle     short loc_1800E779B
0x1800e7795  movzx   eax, ax
0x1800e7798  or      eax, r15d
0x1800e779b  mov     [rbp+arg_0], eax
0x1800e779e  test    eax, eax
0x1800e77a0  jns     short loc_1800E77AA
0x1800e77a2  mov     r8d, 3Ah ; ':'
0x1800e77a8  jmp     short loc_1800E774E
0x1800e77aa  xor     r9d, r9d; lpName
0x1800e77ad  xor     r8d, r8d; bInitialState
0x1800e77b0  lea     edx, [r9+1]; bManualReset
0x1800e77b4  xor     ecx, ecx; lpEventAttributes
0x1800e77b6  call    cs:__imp_CreateEventW
0x1800e77bc  mov     cs:?m_hRequest@CNetworkAddresses@@0PEAXEA, rax; void * CNetworkAddresses::m_hRequest
0x1800e77c3  test    rax, rax
0x1800e77c6  jnz     short loc_1800E77EA
0x1800e77c8  call    cs:__imp_GetLastError
0x1800e77ce  test    eax, eax
0x1800e77d0  jle     short loc_1800E77D8
0x1800e77d2  movzx   eax, ax
0x1800e77d5  or      eax, r15d
0x1800e77d8  mov     [rbp+arg_0], eax
0x1800e77db  test    eax, eax
0x1800e77dd  jns     short loc_1800E77EA
0x1800e77df  mov     r8d, 3Ch ; '<'
0x1800e77e5  jmp     loc_1800E774E
0x1800e77ea  xor     r9d, r9d; lpName
0x1800e77ed  xor     r8d, r8d; bInitialState
0x1800e77f0  lea     edx, [r9+1]; bManualReset
0x1800e77f4  xor     ecx, ecx; lpEventAttributes
0x1800e77f6  call    cs:__imp_CreateEventW
0x1800e77fc  mov     cs:?m_hWaitEvent@CNetworkAddresses@@0PEAXEA, rax; void * CNetworkAddresses::m_hWaitEvent
0x1800e7803  test    rax, rax
0x1800e7806  jnz     short loc_1800E782A
0x1800e7808  call    cs:__imp_GetLastError
0x1800e780e  test    eax, eax
0x1800e7810  jle     short loc_1800E7818
0x1800e7812  movzx   eax, ax
0x1800e7815  or      eax, r15d
0x1800e7818  mov     [rbp+arg_0], eax
0x1800e781b  test    eax, eax
0x1800e781d  jns     short loc_1800E782A
0x1800e781f  mov     r8d, 3Eh ; '>'
0x1800e7825  jmp     loc_1800E774E
0x1800e782a  call    ?IDCRLCreateThread@@YAPEAXP6AKPEAX@Z0H@Z; IDCRLCreateThread(ulong (*)(void *),void *,int)
0x1800e782f  mov     cs:?m_hPublisherThread@CNetworkAddresses@@0PEAXEA, rax; void * CNetworkAddresses::m_hPublisherThread
0x1800e7836  test    rax, rax
0x1800e7839  jnz     short loc_1800E785D
0x1800e783b  call    cs:__imp_GetLastError
0x1800e7841  test    eax, eax
0x1800e7843  jle     short loc_1800E784B
0x1800e7845  movzx   eax, ax
0x1800e7848  or      eax, r15d
0x1800e784b  mov     [rbp+arg_0], eax
0x1800e784e  test    eax, eax
0x1800e7850  jns     short loc_1800E785D
0x1800e7852  mov     r8d, 40h ; '@'
0x1800e7858  jmp     loc_1800E774E
0x1800e785d  mov     cs:?m_fRunning@CNetworkAddresses@@0EA, 1; uchar CNetworkAddresses::m_fRunning
0x1800e7864  lea     rcx, [rbp+var_30]
0x1800e7868  call    ??1?$CComCritSecLockWTry@VCComAutoCriticalSectionWTry@@@@QEAA@XZ; CComCritSecLockWTry<CComAutoCriticalSectionWTry>::~CComCritSecLockWTry<CComAutoCriticalSectionWTry>(void)
0x1800e786d  mov     ebx, [rbp+arg_0]
0x1800e7870  lea     rcx, [rbp+var_20]
0x1800e7874  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x1800e7879  mov     eax, ebx
0x1800e787b  lea     r11, [rsp+60h+var_s0]
0x1800e7880  mov     rbx, [r11+28h]
0x1800e7884  mov     rdi, [r11+30h]
0x1800e7888  mov     rsp, r11
0x1800e788b  pop     r15
0x1800e788d  pop     r14
0x1800e788f  pop     rbp
0x1800e7890  retn
```
