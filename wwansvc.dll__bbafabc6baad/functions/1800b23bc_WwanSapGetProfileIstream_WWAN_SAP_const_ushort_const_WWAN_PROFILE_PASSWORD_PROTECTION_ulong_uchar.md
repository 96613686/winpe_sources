# WwanSapGetProfileIstream(WWAN_SAP const *,ushort const *,WWAN_PROFILE_PASSWORD_PROTECTION,ulong *,uchar * *)

- ea: `0x1800b23bc`
- end: `0x1800b253d`
- name: `?WwanSapGetProfileIstream@@YAKPEBUWWAN_SAP@@PEBGW4WWAN_PROFILE_PASSWORD_PROTECTION@@PEAKPEAPEAE@Z`
- size: `385`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, installer_update`

## callers

- `0x1800acba0`

## callees

- `0x180008abc`
- `0x180010e94`
- `0x1800119bc`
- `0x180012300`
- `0x1800135e0`
- `0x18005bb50`
- `0x18007289c`
- `0x18007cb94`
- `0x1800893b4`
- `0x1800b23bc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800b24f5`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800b24f5`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800b23ee`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800b23ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b240f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b24ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b240f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b24ff`

## string_xrefs

- `0x1800b2424`: `onecoreuap\net\wwan\service\sessionmanager\wwansap.c`
- `0x1800b2514`: `onecoreuap\net\wwan\service\sessionmanager\wwansap.c`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 WwanSapGetProfileIstream(void *a1, MessageParams *a2, int a3, MessageParams *a4, ...)
{
  MessageParams *v5; // r15
  HANDLE EventW; // rax
  MessageParams *v8; // rbx
  DWORD LastError; // eax
  MessageParams *v10; // rsi
  unsigned int v11; // edx
  unsigned int v12; // ebx
  DWORD v13; // eax
  HANDLE hHandle; // [rsp+60h] [rbp+40h] BYREF
  MessageParams *v16; // [rsp+68h] [rbp+48h] BYREF
  unsigned int v17; // [rsp+70h] [rbp+50h] BYREF
  va_list va; // [rsp+80h] [rbp+60h] BYREF

  va_start(va, a4);
  hHandle = a1;
  v5 = (MessageParams *)a3;
  v17 = 0;
  EventW = CreateEventW(0, 1, 0, 0);
  std::unique_ptr<_WWAN_SET_LTE_ATTACH>::unique_ptr<_WWAN_SET_LTE_ATTACH>((__int64)&hHandle, (__int64)EventW);
  v8 = (MessageParams *)hHandle;
  if ( (unsigned __int64)hHandle + 1 <= 1 )
  {
    LastError = GetLastError();
    __FatalError(
      "onecoreuap\\net\\wwan\\service\\sessionmanager\\wwansap.c",
      0x503u,
      "Failure while creating an Event",
      LastError);
  }
  v16 = (MessageParams *)operator new(0x48u);
  v10 = MessageParams::MessageParams(v16);
  v16 = v8;
  std::vector<void *>::push_back((char *)v10 + 48, &v16);
  v16 = (MessageParams *)&v17;
  std::vector<void *>::push_back((char *)v10 + 48, &v16);
  v16 = a2;
  std::vector<void *>::push_back((char *)v10 + 48, &v16);
  v16 = v5;
  std::vector<void *>::push_back((char *)v10 + 48, &v16);
  v16 = a4;
  std::vector<void *>::push_back((char *)v10 + 48, &v16);
  std::vector<void *>::push_back((char *)v10 + 48, (__int64 *)va);
  if ( (unsigned int)MessageDispatcher::_EnQueueWwanRPCMessage(18, v10) )
  {
    if ( v10 )
      MessageParams::`scalar deleting destructor'(v10, v11);
    WwanLog::Error("WwanSapGetProfileIstream", 0, L"Notification dispatcher: Failed to Queue Message");
    v12 = 31;
  }
  else
  {
    if ( WaitForSingleObject(v8, 0xFFFFFFFF) )
    {
      v13 = GetLastError();
      __FatalError("onecoreuap\\net\\wwan\\service\\sessionmanager\\wwansap.c", 0x518u, "WaitForSingleObject", v13);
    }
    v12 = v17;
  }
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&hHandle);
  return v12;
}

```

## disassembly

```asm
0x1800b23bc  mov     [rsp-38h+hHandle], rcx
0x1800b23c1  push    rbp
0x1800b23c2  push    rbx
0x1800b23c3  push    rsi
0x1800b23c4  push    rdi
0x1800b23c5  push    r12
0x1800b23c7  push    r14
0x1800b23c9  push    r15
0x1800b23cb  mov     rbp, rsp
0x1800b23ce  sub     rsp, 20h
0x1800b23d2  mov     r14, r9
0x1800b23d5  movsxd  r15, r8d
0x1800b23d8  mov     r12, rdx
0x1800b23db  mov     [rbp+arg_10], 0
0x1800b23e2  xor     r9d, r9d; lpName
0x1800b23e5  xor     r8d, r8d; bInitialState
0x1800b23e8  lea     edx, [r9+1]; bManualReset
0x1800b23ec  xor     ecx, ecx; lpEventAttributes
0x1800b23ee  call    cs:__imp_CreateEventW
0x1800b23f4  mov     rdx, rax
0x1800b23f7  lea     rcx, [rbp+hHandle]
0x1800b23fb  call    ??$?0U?$default_delete@U_WWAN_SET_LTE_ATTACH@@@std@@$0A@@?$unique_ptr@U_WWAN_SET_LTE_ATTACH@@U?$default_delete@U_WWAN_SET_LTE_ATTACH@@@std@@@std@@QEAA@PEAU_WWAN_SET_LTE_ATTACH@@@Z; std::unique_ptr<_WWAN_SET_LTE_ATTACH>::unique_ptr<_WWAN_SET_LTE_ATTACH>(_WWAN_SET_LTE_ATTACH *)
0x1800b2400  nop
0x1800b2401  mov     rbx, [rbp+hHandle]
0x1800b2405  lea     rax, [rbx+1]
0x1800b2409  cmp     rax, 1
0x1800b240d  ja      short loc_1800B2430
0x1800b240f  call    cs:__imp_GetLastError
0x1800b2415  mov     r9d, eax; unsigned int
0x1800b2418  lea     r8, aFailureWhileCr; "Failure while creating an Event"
0x1800b241f  mov     edx, 503h; unsigned int
0x1800b2424  lea     rcx, aOnecoreuapNetW_10; "onecoreuap\\net\\wwan\\service\\session"...
0x1800b242b  call    ?__FatalError@@YAXPEBDK0K@Z; __FatalError(char const *,ulong,char const *,ulong)
0x1800b2430  mov     ecx, 48h ; 'H'; Size
0x1800b2435  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800b243a  mov     [rbp+arg_8], rax
0x1800b243e  mov     rcx, rax; this
0x1800b2441  call    ??0MessageParams@@QEAA@XZ; MessageParams::MessageParams(void)
0x1800b2446  mov     rsi, rax
0x1800b2449  lea     rdi, [rax+30h]
0x1800b244d  mov     [rbp+arg_8], rbx
0x1800b2451  lea     rdx, [rbp+arg_8]
0x1800b2455  mov     rcx, rdi
0x1800b2458  call    ?push_back@?$vector@PEAXV?$allocator@PEAX@std@@@std@@QEAAX$$QEAPEAX@Z; std::vector<void *>::push_back(void * &&)
0x1800b245d  lea     rax, [rbp+arg_10]
0x1800b2461  mov     [rbp+arg_8], rax
0x1800b2465  lea     rdx, [rbp+arg_8]
0x1800b2469  mov     rcx, rdi
0x1800b246c  call    ?push_back@?$vector@PEAXV?$allocator@PEAX@std@@@std@@QEAAX$$QEAPEAX@Z; std::vector<void *>::push_back(void * &&)
0x1800b2471  mov     [rbp+arg_8], r12
0x1800b2475  lea     rdx, [rbp+arg_8]
0x1800b2479  mov     rcx, rdi
0x1800b247c  call    ?push_back@?$vector@PEAXV?$allocator@PEAX@std@@@std@@QEAAX$$QEAPEAX@Z; std::vector<void *>::push_back(void * &&)
0x1800b2481  mov     [rbp+arg_8], r15
0x1800b2485  lea     rdx, [rbp+arg_8]
0x1800b2489  mov     rcx, rdi
0x1800b248c  call    ?push_back@?$vector@PEAXV?$allocator@PEAX@std@@@std@@QEAAX$$QEAPEAX@Z; std::vector<void *>::push_back(void * &&)
0x1800b2491  mov     [rbp+arg_8], r14
0x1800b2495  lea     rdx, [rbp+arg_8]
0x1800b2499  mov     rcx, rdi
0x1800b249c  call    ?push_back@?$vector@PEAXV?$allocator@PEAX@std@@@std@@QEAAX$$QEAPEAX@Z; std::vector<void *>::push_back(void * &&)
0x1800b24a1  mov     rax, [rbp+arg_20]
0x1800b24a5  mov     [rbp+arg_20], rax
0x1800b24a9  lea     rdx, [rbp+arg_20]
0x1800b24ad  mov     rcx, rdi
0x1800b24b0  call    ?push_back@?$vector@PEAXV?$allocator@PEAX@std@@@std@@QEAAX$$QEAPEAX@Z; std::vector<void *>::push_back(void * &&)
0x1800b24b5  mov     rdx, rsi
0x1800b24b8  mov     ecx, 12h
0x1800b24bd  call    ?_EnQueueWwanRPCMessage@MessageDispatcher@@SAKW4_OpRPCCode@@PEAUMessageParams@@@Z; MessageDispatcher::_EnQueueWwanRPCMessage(_OpRPCCode,MessageParams *)
0x1800b24c2  test    eax, eax
0x1800b24c4  jz      short loc_1800B24EF
0x1800b24c6  test    rsi, rsi
0x1800b24c9  jz      short loc_1800B24D3
0x1800b24cb  mov     rcx, rsi; this
0x1800b24ce  call    ??_GMessageParams@@QEAAPEAXI@Z; MessageParams::`scalar deleting destructor'(uint)
0x1800b24d3  lea     r8, aNotificationDi_8; "Notification dispatcher: Failed to Queu"...
0x1800b24da  xor     edx, edx; struct _GUID *
0x1800b24dc  lea     rcx, aWwansapgetprof_0; "WwanSapGetProfileIstream"
0x1800b24e3  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800b24e8  mov     ebx, 1Fh
0x1800b24ed  jmp     short loc_1800B2523
0x1800b24ef  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800b24f2  mov     rcx, rbx; hHandle
0x1800b24f5  call    cs:__imp_WaitForSingleObject
0x1800b24fb  test    eax, eax
0x1800b24fd  jz      short loc_1800B2520
0x1800b24ff  call    cs:__imp_GetLastError
0x1800b2505  mov     r9d, eax; unsigned int
0x1800b2508  lea     r8, aWaitforsingleo; "WaitForSingleObject"
0x1800b250f  mov     edx, 518h; unsigned int
0x1800b2514  lea     rcx, aOnecoreuapNetW_10; "onecoreuap\\net\\wwan\\service\\session"...
0x1800b251b  call    ?__FatalError@@YAXPEBDK0K@Z; __FatalError(char const *,ulong,char const *,ulong)
0x1800b2520  mov     ebx, [rbp+arg_10]
0x1800b2523  lea     rcx, [rbp+hHandle]
0x1800b2527  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x1800b252c  mov     eax, ebx
0x1800b252e  add     rsp, 20h
0x1800b2532  pop     r15
0x1800b2534  pop     r14
0x1800b2536  pop     r12
0x1800b2538  pop     rdi
0x1800b2539  pop     rsi
0x1800b253a  pop     rbx
0x1800b253b  pop     rbp
0x1800b253c  retn
```
