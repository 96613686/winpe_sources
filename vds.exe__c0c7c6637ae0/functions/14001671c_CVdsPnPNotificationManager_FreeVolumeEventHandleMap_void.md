# CVdsPnPNotificationManager::FreeVolumeEventHandleMap(void)

- ea: `0x14001671c`
- end: `0x140016827`
- name: `?FreeVolumeEventHandleMap@CVdsPnPNotificationManager@@AEAAXXZ`
- size: `267`
- prototype: `void __fastcall(CVdsPnPNotificationManager *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14000f4e0`

## callees

- `0x14001671c`

## import_xrefs

- `USER32!UnregisterDeviceNotification` at `0x140016784`
- `USER32!UnregisterDeviceNotification` at `0x140016784`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140016805`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140016805`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140016752`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140016752`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400167b1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400167b1`
- `vdsutil!?RemoveAll@CRtlMap@@QEAAXH@Z` at `0x1400167fb`
- `vdsutil!?RemoveAll@CRtlMap@@QEAAXH@Z` at `0x1400167fb`
- `vdsutil!VdsHeapFree` at `0x1400167bf`
- `vdsutil!VdsHeapFree` at `0x1400167bf`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14001673f`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14001673f`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140016811`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140016811`
- `vdsutil!?Next@CRtlMapIter@@QEAAAEAV1@XZ` at `0x1400167e8`
- `vdsutil!?Next@CRtlMapIter@@QEAAAEAV1@XZ` at `0x1400167e8`
- `vdsutil!?Begin@CRtlMap@@QEAA?AVCRtlMapIter@@XZ` at `0x140016768`
- `vdsutil!?Begin@CRtlMap@@QEAA?AVCRtlMapIter@@XZ` at `0x140016768`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CVdsPnPNotificationManager::FreeVolumeEventHandleMap(CVdsPnPNotificationManager *this)
{
  struct _RTL_CRITICAL_SECTION *v2; // rdi
  CRtlMap *v3; // rsi
  __int64 v4; // rax
  __int64 v5; // rbx
  HANDLE ProcessHeap; // rax
  __int64 v7; // rax
  _BYTE v8[16]; // [rsp+28h] [rbp-30h] BYREF
  __int64 v9; // [rsp+38h] [rbp-20h] BYREF
  __int64 v10; // [rsp+40h] [rbp-18h]

  CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v8, 0x5Eu, "CVdsPnPNotificationManager::FreeVolumeEventHandleMap()");
  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 8);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  v3 = (CVdsPnPNotificationManager *)((char *)this + 160);
  CRtlMap::Begin((char *)this + 160, &v9);
  while ( v9 && v10 )
  {
    UnregisterDeviceNotification(*(HDEVNOTIFY *)(v10 + 16));
    v4 = v10;
    *(_QWORD *)(v10 + 8) = 0;
    *(_QWORD *)(v4 + 16) = 0;
    if ( v10 )
      v5 = *(_QWORD *)(v10 + 48);
    else
      v5 = 0;
    ProcessHeap = GetProcessHeap();
    VdsHeapFree(ProcessHeap, 0, v5);
    v7 = v10;
    if ( v10 )
      v7 = v10 + 32;
    *(_QWORD *)(v7 + 8) = 0;
    *(_QWORD *)(v7 + 16) = 0;
    CRtlMapIter::Next((CRtlMapIter *)&v9);
  }
  CRtlMap::RemoveAll(v3, 1);
  LeaveCriticalSection(v2);
  CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v8);
}

```

## disassembly

```asm
0x14001671c  mov     [rsp+arg_0], rbx
0x140016721  mov     [rsp+arg_8], rsi
0x140016726  push    rdi
0x140016727  sub     rsp, 50h
0x14001672b  mov     rbx, rcx
0x14001672e  lea     r8, aCvdspnpnotific_4; "CVdsPnPNotificationManager::FreeVolumeE"...
0x140016735  mov     edx, 5Eh ; '^'
0x14001673a  lea     rcx, [rsp+58h+var_30]
0x14001673f  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x140016745  nop
0x140016746  lea     rdi, [rbx+8]
0x14001674a  mov     [rsp+58h+var_38], rdi
0x14001674f  mov     rcx, rdi; lpCriticalSection
0x140016752  call    cs:__imp_EnterCriticalSection
0x140016758  nop
0x140016759  lea     rsi, [rbx+0A0h]
0x140016760  lea     rdx, [rsp+58h+var_20]
0x140016765  mov     rcx, rsi
0x140016768  call    cs:__imp_?Begin@CRtlMap@@QEAA?AVCRtlMapIter@@XZ; CRtlMap::Begin(void)
0x14001676e  cmp     [rsp+58h+var_20], 0
0x140016774  jz      short loc_1400167F3
0x140016776  mov     rcx, [rsp+58h+var_18]
0x14001677b  test    rcx, rcx
0x14001677e  jz      short loc_1400167F3
0x140016780  mov     rcx, [rcx+10h]; Handle
0x140016784  call    cs:__imp_UnregisterDeviceNotification
0x14001678a  mov     rax, [rsp+58h+var_18]
0x14001678f  mov     qword ptr [rax+8], 0
0x140016797  mov     qword ptr [rax+10h], 0
0x14001679f  mov     rax, [rsp+58h+var_18]
0x1400167a4  test    rax, rax
0x1400167a7  jz      short loc_1400167AF
0x1400167a9  mov     rbx, [rax+30h]
0x1400167ad  jmp     short loc_1400167B1
0x1400167af  xor     ebx, ebx
0x1400167b1  call    cs:__imp_GetProcessHeap
0x1400167b7  mov     r8, rbx
0x1400167ba  xor     edx, edx
0x1400167bc  mov     rcx, rax
0x1400167bf  call    cs:__imp_VdsHeapFree
0x1400167c5  mov     rax, [rsp+58h+var_18]
0x1400167ca  test    rax, rax
0x1400167cd  jz      short loc_1400167D3
0x1400167cf  add     rax, 20h ; ' '
0x1400167d3  mov     qword ptr [rax+8], 0
0x1400167db  mov     qword ptr [rax+10h], 0
0x1400167e3  lea     rcx, [rsp+58h+var_20]
0x1400167e8  call    cs:__imp_?Next@CRtlMapIter@@QEAAAEAV1@XZ; CRtlMapIter::Next(void)
0x1400167ee  jmp     loc_14001676E
0x1400167f3  mov     edx, 1
0x1400167f8  mov     rcx, rsi
0x1400167fb  call    cs:__imp_?RemoveAll@CRtlMap@@QEAAXH@Z; CRtlMap::RemoveAll(int)
0x140016801  nop
0x140016802  mov     rcx, rdi; lpCriticalSection
0x140016805  call    cs:__imp_LeaveCriticalSection
0x14001680b  nop
0x14001680c  lea     rcx, [rsp+58h+var_30]
0x140016811  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x140016817  mov     rbx, [rsp+58h+arg_0]
0x14001681c  mov     rsi, [rsp+58h+arg_8]
0x140016821  add     rsp, 50h
0x140016825  pop     rdi
0x140016826  retn
```
