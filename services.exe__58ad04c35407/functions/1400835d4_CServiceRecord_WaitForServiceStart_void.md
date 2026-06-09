# CServiceRecord::WaitForServiceStart(void)

- ea: `0x1400835d4`
- end: `0x140083870`
- name: `?WaitForServiceStart@CServiceRecord@@QEAAKXZ`
- size: `668`
- prototype: `unsigned int __fastcall(CServiceRecord *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x14002ab00`

## callees

- `0x140003e54`
- `0x1400188fc`
- `0x14001c87c`
- `0x140020d84`
- `0x1400835d4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x14008379d`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x14008379d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140083613`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140083613`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140083621`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400837ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140083621`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400837ad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14008385e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14008385e`
- `ntdll!RtlFreeHeap` at `0x14008366f`
- `ntdll!RtlFreeHeap` at `0x14008366f`
- `ntdll!RtlAllocateHeap` at `0x14008369d`
- `ntdll!RtlAllocateHeap` at `0x14008369d`

## pseudocode

```c
__int64 __fastcall CServiceRecord::WaitForServiceStart(CServiceRecord *this)
{
  DWORD LastError; // edi
  CServiceRecord *v3; // rbx
  HANDLE EventW; // rbp
  CServiceRecord *Heap; // rax
  CServiceRecord **v7; // rcx
  DWORD v8; // eax
  CServiceRecord *v9; // rcx
  CServiceRecord **v10; // rax
  HANDLE Handles; // [rsp+30h] [rbp-28h] BYREF
  HANDLE v12; // [rsp+38h] [rbp-20h]
  char v13; // [rsp+68h] [rbp+10h] BYREF

  LastError = 0;
  Handles = g_hAutoStartPhase1Event;
  v12 = 0;
  v3 = 0;
  if ( _InterlockedCompareExchange((volatile signed __int32 *)&g_dwRunningAutostartPhase1Loop, 0, 0) )
  {
    EventW = CreateEventW(0, 0, 0, 0);
    if ( EventW )
    {
      Heap = (CServiceRecord *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x18u);
      v3 = Heap;
      if ( Heap )
      {
        *((_QWORD *)Heap + 2) = EventW;
        v12 = EventW;
        *((_QWORD *)Heap + 1) = Heap;
        *(_QWORD *)Heap = Heap;
        CScmLock::LockAutoExclusive((char *)this + 312, &v13);
        if ( *((_DWORD *)this + 21) == 4 )
        {
          LastError = 1056;
          if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
            && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 4) != 0 )
          {
            WPP_SF_S(
              WPP_GLOBAL_Control->StubInfo,
              104,
              WPP_91aecf8c7c2c39cfbebddfe21418e6fb_Traceguids,
              *((_QWORD *)this + 7));
          }
        }
        else
        {
          v7 = (CServiceRecord **)*((_QWORD *)this + 24);
          if ( *v7 != (CServiceRecord *)((char *)this + 184) )
            goto LABEL_29;
          *((_QWORD *)v3 + 1) = v7;
          *(_QWORD *)v3 = (char *)this + 184;
          *v7 = v3;
          *((_QWORD *)this + 24) = v3;
          CScmSyncLockExclusive::InternalUnlock((CScmSyncLockExclusive *)&v13);
          v8 = WaitForMultipleObjectsEx(2u, &Handles, 0, 0xFFFFFFFF, 0);
          if ( v8 == 1 )
          {
            LastError = 1056;
            if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
              && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 4) != 0 )
            {
              WPP_SF_S(
                WPP_GLOBAL_Control->StubInfo,
                105,
                WPP_91aecf8c7c2c39cfbebddfe21418e6fb_Traceguids,
                *((_QWORD *)this + 7));
            }
          }
          else if ( v8 == -1 )
          {
            LastError = GetLastError();
            if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
              && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
            {
              WPP_SF_Sd(
                WPP_GLOBAL_Control->StubInfo,
                106,
                (unsigned int)WPP_91aecf8c7c2c39cfbebddfe21418e6fb_Traceguids,
                *((_QWORD *)this + 7),
                LastError);
            }
          }
          CScmLock::LockAutoExclusive((char *)this + 312, &v13);
          v9 = *(CServiceRecord **)v3;
          if ( *(CServiceRecord **)(*(_QWORD *)v3 + 8LL) != v3
            || (v10 = (CServiceRecord **)*((_QWORD *)v3 + 1), *v10 != v3) )
          {
LABEL_29:
            __fastfail(3u);
          }
          *v10 = v9;
          *((_QWORD *)v9 + 1) = v10;
          *((_QWORD *)v3 + 1) = v3;
          *(_QWORD *)v3 = v3;
        }
        CScmSyncLockExclusive::InternalUnlock((CScmSyncLockExclusive *)&v13);
      }
      else
      {
        LastError = 8;
        if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
          && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
        {
          WPP_SF_Sd(
            WPP_GLOBAL_Control->StubInfo,
            103,
            (unsigned int)WPP_91aecf8c7c2c39cfbebddfe21418e6fb_Traceguids,
            *((_QWORD *)this + 7),
            8);
        }
      }
      CloseHandle(EventW);
    }
    else
    {
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
        WPP_SF_Sd(
          WPP_GLOBAL_Control->StubInfo,
          102,
          (unsigned int)WPP_91aecf8c7c2c39cfbebddfe21418e6fb_Traceguids,
          *((_QWORD *)this + 7),
          LastError);
    }
  }
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v3);
  return LastError;
}

```

## disassembly

```asm
0x1400835d4  mov     r11, rsp
0x1400835d7  mov     [r11+8], rbx
0x1400835db  mov     [r11+18h], rbp
0x1400835df  push    rsi
0x1400835e0  push    rdi
0x1400835e1  push    r14
0x1400835e3  sub     rsp, 40h
0x1400835e7  mov     rax, cs:?g_hAutoStartPhase1Event@@3PEAXEA; void * g_hAutoStartPhase1Event
0x1400835ee  xor     edi, edi
0x1400835f0  mov     [r11-28h], rax
0x1400835f4  mov     rsi, rcx
0x1400835f7  xor     eax, eax
0x1400835f9  mov     [r11-20h], rdi
0x1400835fd  mov     ebx, edi
0x1400835ff  mov     edx, edi; bManualReset
0x140083601  lock cmpxchg cs:?g_dwRunningAutostartPhase1Loop@@3KC, edx; ulong volatile g_dwRunningAutostartPhase1Loop
0x140083609  jz      short loc_14008365D
0x14008360b  xor     r9d, r9d; lpName
0x14008360e  xor     r8d, r8d; bInitialState
0x140083611  xor     ecx, ecx; lpEventAttributes
0x140083613  call    cs:__imp_CreateEventW
0x140083619  mov     rbp, rax
0x14008361c  test    rax, rax
0x14008361f  jnz     short loc_14008368A
0x140083621  call    cs:__imp_GetLastError
0x140083627  mov     edi, eax
0x140083629  mov     rcx, cs:WPP_GLOBAL_Control
0x140083630  lea     rax, WPP_GLOBAL_Control
0x140083637  cmp     rcx, rax
0x14008363a  jz      short loc_14008365D
0x14008363c  test    byte ptr [rcx+1Ch], 1
0x140083640  jz      short loc_14008365D
0x140083642  mov     r9, [rsi+38h]
0x140083646  lea     edx, [rbx+66h]
0x140083649  mov     rcx, [rcx+10h]
0x14008364d  lea     r8, WPP_91aecf8c7c2c39cfbebddfe21418e6fb_Traceguids
0x140083654  mov     [rsp+58h+bAlertable], edi
0x140083658  call    WPP_SF_Sd
0x14008365d  mov     rcx, gs:60h
0x140083666  mov     r8, rbx; P
0x140083669  xor     edx, edx; Flags
0x14008366b  mov     rcx, [rcx+30h]; HeapHandle
0x14008366f  call    cs:__imp_RtlFreeHeap
0x140083675  mov     rbx, [rsp+58h+arg_0]
0x14008367a  mov     eax, edi
0x14008367c  mov     rbp, [rsp+58h+arg_10]
0x140083681  add     rsp, 40h
0x140083685  pop     r14
0x140083687  pop     rdi
0x140083688  pop     rsi
0x140083689  retn
0x14008368a  mov     rcx, gs:60h
0x140083693  xor     edx, edx; Flags
0x140083695  mov     rcx, [rcx+30h]; HeapHandle
0x140083699  lea     r8d, [rdx+18h]; Size
0x14008369d  call    cs:__imp_RtlAllocateHeap
0x1400836a3  mov     rbx, rax
0x1400836a6  test    rax, rax
0x1400836a9  jnz     short loc_1400836EF
0x1400836ab  lea     edi, [rax+8]
0x1400836ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1400836b5  lea     rax, WPP_GLOBAL_Control
0x1400836bc  cmp     rcx, rax
0x1400836bf  jz      loc_14008385B
0x1400836c5  test    byte ptr [rcx+1Ch], 1
0x1400836c9  jz      loc_14008385B
0x1400836cf  mov     r9, [rsi+38h]
0x1400836d3  lea     edx, [rbx+67h]
0x1400836d6  mov     rcx, [rcx+10h]
0x1400836da  lea     r8, WPP_91aecf8c7c2c39cfbebddfe21418e6fb_Traceguids
0x1400836e1  mov     [rsp+58h+bAlertable], edi
0x1400836e5  call    WPP_SF_Sd
0x1400836ea  jmp     loc_14008385B
0x1400836ef  mov     [rax+10h], rbp
0x1400836f3  lea     r14, [rsi+138h]
0x1400836fa  mov     [rsp+58h+var_20], rbp
0x1400836ff  lea     rdx, [rsp+58h+arg_8]
0x140083704  mov     rcx, r14
0x140083707  mov     [rax+8], rbx
0x14008370b  mov     [rax], rbx
0x14008370e  call    ?LockAutoExclusive@CScmLock@@QEAA?AVCScmSyncLockExclusive@@XZ; CScmLock::LockAutoExclusive(void)
0x140083713  cmp     dword ptr [rsi+54h], 4
0x140083717  jnz     short loc_14008375D
0x140083719  mov     edi, 420h
0x14008371e  mov     rcx, cs:WPP_GLOBAL_Control
0x140083725  lea     rax, WPP_GLOBAL_Control
0x14008372c  cmp     rcx, rax
0x14008372f  jz      loc_140083851
0x140083735  test    byte ptr [rcx+1Ch], 4
0x140083739  jz      loc_140083851
0x14008373f  mov     r9, [rsi+38h]
0x140083743  lea     r8, WPP_91aecf8c7c2c39cfbebddfe21418e6fb_Traceguids
0x14008374a  mov     rcx, [rcx+10h]
0x14008374e  mov     edx, 68h ; 'h'
0x140083753  call    WPP_SF_S
0x140083758  jmp     loc_140083851
0x14008375d  lea     rax, [rsi+0B8h]
0x140083764  mov     rcx, [rax+8]
0x140083768  cmp     [rcx], rax
0x14008376b  jnz     loc_140083869
0x140083771  mov     [rbx+8], rcx
0x140083775  mov     [rbx], rax
0x140083778  mov     [rcx], rbx
0x14008377b  lea     rcx, [rsp+58h+arg_8]; this
0x140083780  mov     [rax+8], rbx
0x140083784  call    ?InternalUnlock@CScmSyncLockExclusive@@IEAAXXZ; CScmSyncLockExclusive::InternalUnlock(void)
0x140083789  xor     r8d, r8d; bWaitAll
0x14008378c  mov     [rsp+58h+bAlertable], edi; bAlertable
0x140083790  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x140083794  lea     rdx, [rsp+58h+Handles]; lpHandles
0x140083799  lea     ecx, [r8+2]; nCount
0x14008379d  call    cs:__imp_WaitForMultipleObjectsEx
0x1400837a3  cmp     eax, 1
0x1400837a6  jz      short loc_1400837ED
0x1400837a8  cmp     eax, 0FFFFFFFFh
0x1400837ab  jnz     short loc_140083824
0x1400837ad  call    cs:__imp_GetLastError
0x1400837b3  mov     edi, eax
0x1400837b5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400837bc  lea     rax, WPP_GLOBAL_Control
0x1400837c3  cmp     rcx, rax
0x1400837c6  jz      short loc_140083824
0x1400837c8  test    byte ptr [rcx+1Ch], 1
0x1400837cc  jz      short loc_140083824
0x1400837ce  mov     r9, [rsi+38h]
0x1400837d2  lea     r8, WPP_91aecf8c7c2c39cfbebddfe21418e6fb_Traceguids
0x1400837d9  mov     rcx, [rcx+10h]
0x1400837dd  mov     edx, 6Ah ; 'j'
0x1400837e2  mov     [rsp+58h+bAlertable], edi
0x1400837e6  call    WPP_SF_Sd
0x1400837eb  jmp     short loc_140083824
0x1400837ed  mov     edi, 420h
0x1400837f2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400837f9  lea     rax, WPP_GLOBAL_Control
0x140083800  cmp     rcx, rax
0x140083803  jz      short loc_140083824
0x140083805  test    byte ptr [rcx+1Ch], 4
0x140083809  jz      short loc_140083824
0x14008380b  mov     r9, [rsi+38h]
0x14008380f  lea     r8, WPP_91aecf8c7c2c39cfbebddfe21418e6fb_Traceguids
0x140083816  mov     rcx, [rcx+10h]
0x14008381a  mov     edx, 69h ; 'i'
0x14008381f  call    WPP_SF_S
0x140083824  lea     rdx, [rsp+58h+arg_8]
0x140083829  mov     rcx, r14
0x14008382c  call    ?LockAutoExclusive@CScmLock@@QEAA?AVCScmSyncLockExclusive@@XZ; CScmLock::LockAutoExclusive(void)
0x140083831  mov     rcx, [rbx]
0x140083834  cmp     [rcx+8], rbx
0x140083838  jnz     short loc_140083869
0x14008383a  mov     rax, [rbx+8]
0x14008383e  cmp     [rax], rbx
0x140083841  jnz     short loc_140083869
0x140083843  mov     [rax], rcx
0x140083846  mov     [rcx+8], rax
0x14008384a  mov     [rbx+8], rbx
0x14008384e  mov     [rbx], rbx
0x140083851  lea     rcx, [rsp+58h+arg_8]; this
0x140083856  call    ?InternalUnlock@CScmSyncLockExclusive@@IEAAXXZ; CScmSyncLockExclusive::InternalUnlock(void)
0x14008385b  mov     rcx, rbp; hObject
0x14008385e  call    cs:__imp_CloseHandle
0x140083864  jmp     loc_14008365D
0x140083869  mov     ecx, 3
0x14008386e  int     29h; Win8: RtlFailFast(ecx)
```
