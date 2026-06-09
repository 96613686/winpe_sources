# _BioCredMgrLogonIdentifiedUser(void *,ulong,_WINBIO_IDENTITY *,unsigned __int64,_SYSTEMTIME *)

- ea: `0x180060a78`
- end: `0x180060dbf`
- name: `?_BioCredMgrLogonIdentifiedUser@@YAJPEAXKPEAU_WINBIO_IDENTITY@@_KPEAU_SYSTEMTIME@@@Z`
- size: `839`
- prototype: `__int64 __fastcall(void *, unsigned int, struct _WINBIO_IDENTITY *, unsigned __int64, SYSTEMTIME *lpSystemTime)`
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180061900`

## callees

- `0x180011d24`
- `0x180025d94`
- `0x180026b28`
- `0x180027438`
- `0x1800275b4`
- `0x180040600`
- `0x180059038`
- `0x180060a78`
- `0x180060dc8`
- `0x180068f60`
- `0x18006fac4`
- `0x1800bb61c`
- `0x1800bbb1c`
- `0x1800bbb84`
- `0x1800bbcec`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180060cb6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180060cb6`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x180060ca7`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x180060ca7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180060b9a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180060bb8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180060c7b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180060cd0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180060d38`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180060d61`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180060b9a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180060bb8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180060c7b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180060cd0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180060d38`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180060d61`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180060c46`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180060c46`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180060c0d`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180060c0d`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180060af4`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180060af4`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180060c6c`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180060c6c`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180060c56`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180060c56`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSDisconnectSession` at `0x180060d22`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSDisconnectSession` at `0x180060d22`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall _BioCredMgrLogonIdentifiedUser(
        void *a1,
        DWORD a2,
        struct _WINBIO_IDENTITY *a3,
        unsigned __int64 a4,
        SYSTEMTIME *lpSystemTime)
{
  signed int v10; // ebx
  CUserContext *v11; // rcx
  struct _FILETIME v12; // rbx
  CFUSManager *v13; // rcx
  signed int LastError; // eax
  HLOCAL hMem; // [rsp+30h] [rbp-D0h] BYREF
  DWORD pSessionId; // [rsp+38h] [rbp-C8h] BYREF
  struct _FILETIME FileTime; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v18; // [rsp+48h] [rbp-B8h] BYREF
  int v19; // [rsp+58h] [rbp-A8h]
  struct _FILETIME SystemTimeAsFileTime; // [rsp+60h] [rbp-A0h] BYREF
  HLOCAL *p_hMem; // [rsp+68h] [rbp-98h]
  _BYTE v22[96]; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v23[26]; // [rsp+D0h] [rbp-30h] BYREF

  if ( !a1 )
    return 2147942487LL;
  CActivityMonitor::NotifyClientArrival(0xC0FFFFFF);
  if ( a3 && lpSystemTime && a3->Type == 3 && IsValidSid(a3->Value.AccountSid.Data) )
  {
    BioPolicy::Refresh((BioPolicy *)v22);
    if ( v22[8 * (int)BioPolicy::Values::make_index(7)] )
    {
      v10 = -2146861001;
LABEL_32:
      CActivityMonitor::NotifyClientDeparture(0xC0FFFFFF);
      return (unsigned int)v10;
    }
    if ( (unsigned int)IsSASRequired(a2) )
    {
      v10 = -2146861003;
      goto LABEL_32;
    }
    v18 = 0;
    v19 = 0;
    if ( CUserContext::OpenContext((CUserContext *)&v18, a1) < 0 )
    {
LABEL_12:
      CUserContext::~CUserContext((CUserContext *)&v18);
      v10 = -2146861053;
      goto LABEL_32;
    }
    hMem = 0;
    p_hMem = &hMem;
    if ( (int)CUserContext::GetUserSid((CUserContext *)&v18, &hMem) < 0 )
    {
      LocalFree(hMem);
      hMem = 0;
      goto LABEL_12;
    }
    if ( !CUserContext::IsCredProvEnabled(v11, a3->Value.AccountSid.Data) )
    {
      LocalFree(hMem);
      hMem = 0;
      CUserContext::~CUserContext((CUserContext *)&v18);
      v10 = -2146861008;
      goto LABEL_32;
    }
    if ( (unsigned int)CUserContext::IsLowIntegrity((CUserContext *)&v18)
      || (unsigned int)CUserContext::IsAppContainer((CUserContext *)&v18)
      || (SystemTimeAsFileTime = 0,
          FileTime = 0,
          SystemTimeToFileTime(lpSystemTime, &FileTime),
          v12 = FileTime,
          BioPolicy::Refresh((BioPolicy *)v23),
          FileTime = (struct _FILETIME)(*(_QWORD *)&v12 + 10000000LL * v23[2 * (int)BioPolicy::Values::make_index(4)]),
          GetSystemTimeAsFileTime(&SystemTimeAsFileTime),
          CompareFileTime(&FileTime, &SystemTimeAsFileTime) < 0) )
    {
      LocalFree(hMem);
      hMem = 0;
      CUserContext::~CUserContext((CUserContext *)&v18);
      v10 = -2147024891;
      goto LABEL_32;
    }
    if ( EqualSid(hMem, a3->Value.AccountSid.Data) )
    {
      LocalFree(hMem);
      hMem = 0;
      CUserContext::~CUserContext((CUserContext *)&v18);
      v10 = 1;
      goto LABEL_32;
    }
    pSessionId = 0;
    if ( ProcessIdToSessionId(a2, &pSessionId) )
    {
      if ( !g_FUS_Manager )
        MicrosoftTelemetryAssertTriggeredNoArgs(v13);
      v10 = CFUSManager::StoreFUSTarget(v13, a2, a3, a4, &FileTime);
      if ( v10 < 0 )
        goto LABEL_25;
      if ( WTSDisconnectSession(0, pSessionId, 1) )
      {
        LocalFree(hMem);
        hMem = 0;
        CUserContext::~CUserContext((CUserContext *)&v18);
        CActivityMonitor::NotifyClientDeparture(0xC0FFFFFF);
        return 0;
      }
    }
    MicrosoftTelemetryAssertTriggeredNoArgs(v13);
    LastError = GetLastError();
    v10 = LastError;
    if ( LastError > 0 )
      v10 = (unsigned __int16)LastError | 0x80070000;
LABEL_25:
    LocalFree(hMem);
    hMem = 0;
    CUserContext::~CUserContext((CUserContext *)&v18);
    goto LABEL_32;
  }
  CActivityMonitor::NotifyClientDeparture(0xC0FFFFFF);
  return 2147942405LL;
}

```

## disassembly

```asm
0x180060a78  mov     [rsp-8+arg_0], rbx
0x180060a7d  push    rbp
0x180060a7e  push    rsi
0x180060a7f  push    rdi
0x180060a80  push    r12
0x180060a82  push    r13
0x180060a84  push    r14
0x180060a86  push    r15
0x180060a88  lea     rbp, [rsp-40h]
0x180060a8d  sub     rsp, 140h
0x180060a94  mov     rax, cs:__security_cookie
0x180060a9b  xor     rax, rsp
0x180060a9e  mov     [rbp+70h+var_38], rax
0x180060aa2  mov     r12, r9
0x180060aa5  mov     rdi, r8
0x180060aa8  mov     r14d, edx
0x180060aab  mov     rbx, rcx
0x180060aae  mov     r15, [rbp+70h+lpSystemTime]
0x180060ab5  xor     r13d, r13d
0x180060ab8  test    rcx, rcx
0x180060abb  jnz     short loc_180060AC7
0x180060abd  mov     eax, 80070057h
0x180060ac2  jmp     loc_180060D98
0x180060ac7  mov     ecx, 0C0FFFFFFh; unsigned int
0x180060acc  call    ?NotifyClientArrival@CActivityMonitor@@SAXI@Z; CActivityMonitor::NotifyClientArrival(uint)
0x180060ad1  nop
0x180060ad2  test    rdi, rdi
0x180060ad5  jz      loc_180060D89
0x180060adb  test    r15, r15
0x180060ade  jz      loc_180060D89
0x180060ae4  cmp     dword ptr [rdi], 3
0x180060ae7  jnz     loc_180060D89
0x180060aed  lea     rsi, [rdi+8]
0x180060af1  mov     rcx, rsi; pSid
0x180060af4  call    cs:__imp_IsValidSid
0x180060afa  test    eax, eax
0x180060afc  jz      loc_180060D89
0x180060b02  lea     rcx, [rsp+170h+var_100]; this
0x180060b07  call    ?Refresh@BioPolicy@@QEAAJXZ; BioPolicy::Refresh(void)
0x180060b0c  mov     ecx, 7
0x180060b11  call    ?make_index@Values@BioPolicy@@SAHW4type@12@@Z; BioPolicy::Values::make_index(BioPolicy::Values::type)
0x180060b16  movsxd  rcx, eax
0x180060b19  cmp     [rsp+rcx*8+170h+var_100], r13b
0x180060b1e  jz      short loc_180060B2A
0x180060b20  mov     ebx, 80098037h
0x180060b25  jmp     loc_180060D7B
0x180060b2a  mov     ecx, r14d; dwProcessId
0x180060b2d  call    ?IsSASRequired@@YAHK@Z; IsSASRequired(ulong)
0x180060b32  test    eax, eax
0x180060b34  jz      short loc_180060B40
0x180060b36  mov     ebx, 80098035h
0x180060b3b  jmp     loc_180060D7B
0x180060b40  xorps   xmm0, xmm0
0x180060b43  movdqu  [rsp+170h+var_128], xmm0
0x180060b49  mov     [rsp+170h+var_118], r13d
0x180060b4e  mov     rdx, rbx; void *
0x180060b51  lea     rcx, [rsp+170h+var_128]; this
0x180060b56  call    ?OpenContext@CUserContext@@QEAAJPEAX@Z; CUserContext::OpenContext(void *)
0x180060b5b  test    eax, eax
0x180060b5d  jns     short loc_180060B73
0x180060b5f  lea     rcx, [rsp+170h+var_128]; this
0x180060b64  call    ??1CUserContext@@QEAA@XZ; CUserContext::~CUserContext(void)
0x180060b69  mov     ebx, 80098003h
0x180060b6e  jmp     loc_180060D7B
0x180060b73  mov     [rsp+170h+hMem], r13
0x180060b78  lea     rax, [rsp+170h+hMem]
0x180060b7d  mov     [rsp+170h+var_108], rax
0x180060b82  lea     rdx, [rsp+170h+hMem]; void **
0x180060b87  lea     rcx, [rsp+170h+var_128]; this
0x180060b8c  call    ?GetUserSid@CUserContext@@QEBAJPEAPEAX@Z; CUserContext::GetUserSid(void * *)
0x180060b91  test    eax, eax
0x180060b93  jns     short loc_180060BA7
0x180060b95  mov     rcx, [rsp+170h+hMem]; hMem
0x180060b9a  call    cs:__imp_LocalFree
0x180060ba0  mov     [rsp+170h+hMem], r13
0x180060ba5  jmp     short loc_180060B5F
0x180060ba7  mov     rdx, rsi; void *
0x180060baa  call    ?IsCredProvEnabled@CUserContext@@QEBAHPEAX@Z; CUserContext::IsCredProvEnabled(void *)
0x180060baf  test    eax, eax
0x180060bb1  jnz     short loc_180060BD7
0x180060bb3  mov     rcx, [rsp+170h+hMem]; hMem
0x180060bb8  call    cs:__imp_LocalFree
0x180060bbe  mov     [rsp+170h+hMem], r13
0x180060bc3  lea     rcx, [rsp+170h+var_128]; this
0x180060bc8  call    ??1CUserContext@@QEAA@XZ; CUserContext::~CUserContext(void)
0x180060bcd  mov     ebx, 80098030h
0x180060bd2  jmp     loc_180060D7B
0x180060bd7  lea     rcx, [rsp+170h+var_128]; this
0x180060bdc  call    ?IsLowIntegrity@CUserContext@@QEBAHXZ; CUserContext::IsLowIntegrity(void)
0x180060be1  test    eax, eax
0x180060be3  jnz     loc_180060D5C
0x180060be9  lea     rcx, [rsp+170h+var_128]; this
0x180060bee  call    ?IsAppContainer@CUserContext@@QEBAHXZ; CUserContext::IsAppContainer(void)
0x180060bf3  test    eax, eax
0x180060bf5  jnz     loc_180060D5C
0x180060bfb  mov     qword ptr [rsp+170h+SystemTimeAsFileTime.dwLowDateTime], r13
0x180060c00  mov     qword ptr [rsp+170h+FileTime.dwLowDateTime], r13
0x180060c05  lea     rdx, [rsp+170h+FileTime]; lpFileTime
0x180060c0a  mov     rcx, r15; lpSystemTime
0x180060c0d  call    cs:__imp_SystemTimeToFileTime
0x180060c13  mov     rbx, qword ptr [rsp+170h+FileTime.dwLowDateTime]
0x180060c18  lea     rcx, [rbp+70h+var_A0]; this
0x180060c1c  call    ?Refresh@BioPolicy@@QEAAJXZ; BioPolicy::Refresh(void)
0x180060c21  mov     ecx, 4
0x180060c26  call    ?make_index@Values@BioPolicy@@SAHW4type@12@@Z; BioPolicy::Values::make_index(BioPolicy::Values::type)
0x180060c2b  movsxd  rcx, eax
0x180060c2e  mov     eax, [rbp+rcx*8+70h+var_A0]
0x180060c32  imul    rcx, rax, 989680h
0x180060c39  add     rcx, rbx
0x180060c3c  mov     qword ptr [rsp+170h+FileTime.dwLowDateTime], rcx
0x180060c41  lea     rcx, [rsp+170h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180060c46  call    cs:__imp_GetSystemTimeAsFileTime
0x180060c4c  lea     rdx, [rsp+170h+SystemTimeAsFileTime]; lpFileTime2
0x180060c51  lea     rcx, [rsp+170h+FileTime]; lpFileTime1
0x180060c56  call    cs:__imp_CompareFileTime
0x180060c5c  test    eax, eax
0x180060c5e  js      loc_180060D5C
0x180060c64  mov     rdx, rsi; pSid2
0x180060c67  mov     rcx, [rsp+170h+hMem]; pSid1
0x180060c6c  call    cs:__imp_EqualSid
0x180060c72  test    eax, eax
0x180060c74  jz      short loc_180060C9A
0x180060c76  mov     rcx, [rsp+170h+hMem]; hMem
0x180060c7b  call    cs:__imp_LocalFree
0x180060c81  mov     [rsp+170h+hMem], r13
0x180060c86  lea     rcx, [rsp+170h+var_128]; this
0x180060c8b  call    ??1CUserContext@@QEAA@XZ; CUserContext::~CUserContext(void)
0x180060c90  mov     ebx, 1
0x180060c95  jmp     loc_180060D7B
0x180060c9a  mov     [rsp+170h+pSessionId], r13d
0x180060c9f  lea     rdx, [rsp+170h+pSessionId]; pSessionId
0x180060ca4  mov     ecx, r14d; dwProcessId
0x180060ca7  call    cs:__imp_ProcessIdToSessionId
0x180060cad  test    eax, eax
0x180060caf  jnz     short loc_180060CEA
0x180060cb1  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180060cb6  call    cs:__imp_GetLastError
0x180060cbc  test    eax, eax
0x180060cbe  mov     ebx, eax
0x180060cc0  jle     short loc_180060CCB
0x180060cc2  movzx   ebx, ax
0x180060cc5  or      ebx, 80070000h
0x180060ccb  mov     rcx, [rsp+170h+hMem]; hMem
0x180060cd0  call    cs:__imp_LocalFree
0x180060cd6  mov     [rsp+170h+hMem], r13
0x180060cdb  lea     rcx, [rsp+170h+var_128]; this
0x180060ce0  call    ??1CUserContext@@QEAA@XZ; CUserContext::~CUserContext(void)
0x180060ce5  jmp     loc_180060D7B
0x180060cea  cmp     cs:?g_FUS_Manager@@3PEAVCFUSManager@@EA, r13; CFUSManager * g_FUS_Manager
0x180060cf1  jnz     short loc_180060CF8
0x180060cf3  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180060cf8  lea     rax, [rsp+170h+FileTime]
0x180060cfd  mov     [rsp+170h+var_150], rax; struct _FILETIME *
0x180060d02  mov     r9, r12; unsigned __int64
0x180060d05  mov     r8, rdi; struct _WINBIO_IDENTITY *
0x180060d08  mov     edx, r14d; unsigned int
0x180060d0b  call    ?StoreFUSTarget@CFUSManager@@QEAAJKPEAU_WINBIO_IDENTITY@@_KPEAU_FILETIME@@@Z; CFUSManager::StoreFUSTarget(ulong,_WINBIO_IDENTITY *,unsigned __int64,_FILETIME *)
0x180060d10  mov     ebx, eax
0x180060d12  test    eax, eax
0x180060d14  js      short loc_180060CCB
0x180060d16  mov     r8d, 1; bWait
0x180060d1c  mov     edx, [rsp+170h+pSessionId]; SessionId
0x180060d20  xor     ecx, ecx; hServer
0x180060d22  call    cs:__imp_WTSDisconnectSession
0x180060d28  test    eax, eax
0x180060d2a  jnz     short loc_180060D33
0x180060d2c  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180060d31  jmp     short loc_180060CB6
0x180060d33  mov     rcx, [rsp+170h+hMem]; hMem
0x180060d38  call    cs:__imp_LocalFree
0x180060d3e  mov     [rsp+170h+hMem], r13
0x180060d43  lea     rcx, [rsp+170h+var_128]; this
0x180060d48  call    ??1CUserContext@@QEAA@XZ; CUserContext::~CUserContext(void)
0x180060d4d  nop
0x180060d4e  mov     ecx, 0C0FFFFFFh; unsigned int
0x180060d53  call    ?NotifyClientDeparture@CActivityMonitor@@SAXI@Z; CActivityMonitor::NotifyClientDeparture(uint)
0x180060d58  xor     eax, eax
0x180060d5a  jmp     short loc_180060D98
0x180060d5c  mov     rcx, [rsp+170h+hMem]; hMem
0x180060d61  call    cs:__imp_LocalFree
0x180060d67  mov     [rsp+170h+hMem], r13
0x180060d6c  lea     rcx, [rsp+170h+var_128]; this
0x180060d71  call    ??1CUserContext@@QEAA@XZ; CUserContext::~CUserContext(void)
0x180060d76  mov     ebx, 80070005h
0x180060d7b  mov     ecx, 0C0FFFFFFh; unsigned int
0x180060d80  call    ?NotifyClientDeparture@CActivityMonitor@@SAXI@Z; CActivityMonitor::NotifyClientDeparture(uint)
0x180060d85  mov     eax, ebx
0x180060d87  jmp     short loc_180060D98
0x180060d89  mov     ecx, 0C0FFFFFFh; unsigned int
0x180060d8e  call    ?NotifyClientDeparture@CActivityMonitor@@SAXI@Z; CActivityMonitor::NotifyClientDeparture(uint)
0x180060d93  mov     eax, 80070005h
0x180060d98  mov     rcx, [rbp+70h+var_38]
0x180060d9c  xor     rcx, rsp; StackCookie
0x180060d9f  call    __security_check_cookie
0x180060da4  mov     rbx, [rsp+170h+arg_0]
0x180060dac  add     rsp, 140h
0x180060db3  pop     r15
0x180060db5  pop     r14
0x180060db7  pop     r13
0x180060db9  pop     r12
0x180060dbb  pop     rdi
0x180060dbc  pop     rsi
0x180060dbd  pop     rbp
0x180060dbe  retn
```
