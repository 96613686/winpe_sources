# CVdsPnPNotificationManager::InitializeAuxThread(CVdsPnPNotificationManager *)

- ea: `0x1400501a0`
- end: `0x14005026a`
- name: `?InitializeAuxThread@CVdsPnPNotificationManager@@CAKPEAV1@@Z`
- size: `202`
- prototype: `unsigned int __fastcall(struct CVdsPnPNotificationManager *lpParameter)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140050270`

## callees

- `0x1400501a0`

## import_xrefs

- `USER32!PostThreadMessageW` at `0x140050222`
- `USER32!PostThreadMessageW` at `0x140050222`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400501f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140050236`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400501f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140050236`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1400501e3`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1400501e3`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x14005020b`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x14005020b`
- `vdsutil!VdsTraceEx` at `0x14005024d`
- `vdsutil!VdsTraceEx` at `0x14005024d`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x1400501ba`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x1400501ba`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14005025c`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14005025c`

## string_xrefs

- `0x1400501a9`: `CVdsPnPNotificationManager::InitializeAuxThread()`
- `0x1400501fb`: `VDS(0X0204000F): CreateThread failed: %X`
- `0x14005023c`: `VDS(0X02040010): PostThreadMessage failed: %X`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CVdsPnPNotificationManager::InitializeAuxThread(struct CVdsPnPNotificationManager *lpParameter)
{
  DWORD LastError; // eax
  const char *v3; // r8
  int v4; // ebx
  DWORD v5; // ebx
  _BYTE v7[24]; // [rsp+30h] [rbp-18h] BYREF

  CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v7, 0x5Eu, "CVdsPnPNotificationManager::InitializeAuxThread()");
  CVdsPnPNotificationManager::m_hAuxThread = CreateThread(
                                               0,
                                               0,
                                               (LPTHREAD_START_ROUTINE)CVdsPnPNotificationManager::AuxThread,
                                               lpParameter,
                                               0,
                                               &CVdsPnPNotificationManager::m_dwAuxThreadId);
  if ( CVdsPnPNotificationManager::m_hAuxThread )
  {
    v4 = 0;
    while ( 1 )
    {
      Sleep(0x1F4u);
      if ( PostThreadMessageW(CVdsPnPNotificationManager::m_dwAuxThreadId, 0x400u, 0, 0) )
        break;
      if ( ++v4 > 600 )
      {
        LastError = GetLastError();
        v3 = "VDS(0X02040010): PostThreadMessage failed: %X";
        goto LABEL_7;
      }
    }
    v5 = 0;
  }
  else
  {
    LastError = GetLastError();
    v3 = "VDS(0X0204000F): CreateThread failed: %X";
LABEL_7:
    v5 = LastError;
    VdsTraceEx(94, 0, v3, LastError);
  }
  CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v7);
  return v5;
}

```

## disassembly

```asm
0x1400501a0  push    rbx
0x1400501a2  sub     rsp, 40h
0x1400501a6  mov     rbx, rcx
0x1400501a9  lea     r8, aCvdspnpnotific_22; "CVdsPnPNotificationManager::InitializeA"...
0x1400501b0  mov     edx, 5Eh ; '^'
0x1400501b5  lea     rcx, [rsp+48h+var_18]
0x1400501ba  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x1400501c0  nop
0x1400501c1  lea     rax, ?m_dwAuxThreadId@CVdsPnPNotificationManager@@0KA; ulong CVdsPnPNotificationManager::m_dwAuxThreadId
0x1400501c8  mov     [rsp+48h+lpThreadId], rax; lpThreadId
0x1400501cd  mov     [rsp+48h+dwCreationFlags], 0; dwCreationFlags
0x1400501d5  mov     r9, rbx; lpParameter
0x1400501d8  lea     r8, ?AuxThread@CVdsPnPNotificationManager@@CAKPEAX@Z; lpStartAddress
0x1400501df  xor     edx, edx; dwStackSize
0x1400501e1  xor     ecx, ecx; lpThreadAttributes
0x1400501e3  call    cs:__imp_CreateThread
0x1400501e9  mov     cs:?m_hAuxThread@CVdsPnPNotificationManager@@0PEAXEA, rax; void * CVdsPnPNotificationManager::m_hAuxThread
0x1400501f0  test    rax, rax
0x1400501f3  jnz     short loc_140050204
0x1400501f5  call    cs:__imp_GetLastError
0x1400501fb  lea     r8, aVds0x0204000fC; "VDS(0X0204000F): CreateThread failed: %"...
0x140050202  jmp     short loc_140050243
0x140050204  xor     ebx, ebx
0x140050206  mov     ecx, 1F4h; dwMilliseconds
0x14005020b  call    cs:__imp_Sleep
0x140050211  xor     r9d, r9d; lParam
0x140050214  xor     r8d, r8d; wParam
0x140050217  mov     edx, 400h; Msg
0x14005021c  mov     ecx, cs:?m_dwAuxThreadId@CVdsPnPNotificationManager@@0KA; idThread
0x140050222  call    cs:__imp_PostThreadMessageW
0x140050228  test    eax, eax
0x14005022a  jnz     short loc_140050255
0x14005022c  inc     ebx
0x14005022e  cmp     ebx, 258h
0x140050234  jle     short loc_140050206
0x140050236  call    cs:__imp_GetLastError
0x14005023c  lea     r8, aVds0x02040010P; "VDS(0X02040010): PostThreadMessage fail"...
0x140050243  mov     r9d, eax
0x140050246  mov     ebx, eax
0x140050248  xor     edx, edx
0x14005024a  lea     ecx, [rdx+5Eh]
0x14005024d  call    cs:__imp_VdsTraceEx
0x140050253  jmp     short loc_140050257
0x140050255  xor     ebx, ebx
0x140050257  lea     rcx, [rsp+48h+var_18]
0x14005025c  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x140050262  mov     eax, ebx
0x140050264  add     rsp, 40h
0x140050268  pop     rbx
0x140050269  retn
```
