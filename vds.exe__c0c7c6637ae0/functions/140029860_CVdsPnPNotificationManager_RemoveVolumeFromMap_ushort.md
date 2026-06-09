# CVdsPnPNotificationManager::RemoveVolumeFromMap(ushort *)

- ea: `0x140029860`
- end: `0x1400299a7`
- name: `?RemoveVolumeFromMap@CVdsPnPNotificationManager@@AEAAXPEAG@Z`
- size: `327`
- prototype: `void(CVdsPnPNotificationManager *__hidden this, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, service_task`

## callers

- `0x1400504f4`

## callees

- `0x140029860`
- `0x14003c084`

## import_xrefs

- `USER32!UnregisterDeviceNotification` at `0x140029939`
- `USER32!UnregisterDeviceNotification` at `0x140029939`
- `msvcrt!_wcsicmp` at `0x1400298d0`
- `msvcrt!_wcsicmp` at `0x1400298d0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14002998b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14002998b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140029896`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140029896`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400298f7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400298f7`
- `vdsutil!?Remove@CRtlMap@@QEAAHAEAVCRtlEntry@@@Z` at `0x140029946`
- `vdsutil!?Remove@CRtlMap@@QEAAHAEAVCRtlEntry@@@Z` at `0x140029946`
- `vdsutil!VdsHeapFree` at `0x140029905`
- `vdsutil!VdsHeapFree` at `0x140029905`
- `vdsutil!VdsTraceEx` at `0x140029967`
- `vdsutil!VdsTraceEx` at `0x140029981`
- `vdsutil!VdsTraceEx` at `0x140029967`
- `vdsutil!VdsTraceEx` at `0x140029981`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140029884`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140029884`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140029996`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140029996`
- `vdsutil!?Next@CRtlMapIter@@QEAAAEAV1@XZ` at `0x1400298de`
- `vdsutil!?Next@CRtlMapIter@@QEAAAEAV1@XZ` at `0x1400298de`
- `vdsutil!?Begin@CRtlMap@@QEAA?AVCRtlMapIter@@XZ` at `0x1400298ab`
- `vdsutil!?Begin@CRtlMap@@QEAA?AVCRtlMapIter@@XZ` at `0x1400298ab`

## string_xrefs

- `0x140029972`: `RemoveVolumeFromMap: volume not found: %S`
- `0x140029874`: `CVdsPnPNotificationManager::RemoveVolumeFromMap()`
- `0x140029958`: `CVdsPnPNotificationManager::RemoveVolumeFromMap, 1, hr=%lX`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CVdsPnPNotificationManager::RemoveVolumeFromMap(CVdsPnPNotificationManager *this, unsigned __int16 *a2)
{
  struct _RTL_CRITICAL_SECTION *v4; // rdi
  CRtlMap *v5; // r14
  const wchar_t *v6; // rbx
  HANDLE ProcessHeap; // rax
  const wchar_t **v8; // rax
  wchar_t *v9; // rcx
  int v10; // eax
  _BYTE v11[16]; // [rsp+28h] [rbp-28h] BYREF
  __int64 v12; // [rsp+38h] [rbp-18h] BYREF
  const wchar_t **v13; // [rsp+40h] [rbp-10h]

  CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v11, 0x5Eu, "CVdsPnPNotificationManager::RemoveVolumeFromMap()");
  v4 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 8);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  v5 = (CVdsPnPNotificationManager *)((char *)this + 160);
  CRtlMap::Begin((char *)this + 160, &v12);
  while ( 1 )
  {
    if ( !v12 || !v13 )
    {
      VdsTraceEx(94, 1, "RemoveVolumeFromMap: volume not found: %S", a2);
      goto LABEL_17;
    }
    if ( !_wcsicmp(v13[6], a2) )
      break;
    CRtlMapIter::Next((CRtlMapIter *)&v12);
  }
  if ( v13 )
    v6 = v13[6];
  else
    v6 = 0;
  ProcessHeap = GetProcessHeap();
  VdsHeapFree(ProcessHeap, 0, v6);
  v8 = v13;
  if ( v13 )
    v8 = v13 + 4;
  v8[1] = 0;
  v8[2] = 0;
  if ( v13 )
    v9 = (wchar_t *)v13[2];
  else
    v9 = 0;
  UnregisterDeviceNotification(v9);
  CRtlMap::Remove(v5, (struct CRtlEntry *)v13);
  v10 = CVdsService::RemoveObsoleteDevNodes();
  if ( v10 < 0 )
    VdsTraceEx(94, 1, "CVdsPnPNotificationManager::RemoveVolumeFromMap, 1, hr=%lX", v10);
LABEL_17:
  LeaveCriticalSection(v4);
  CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v11);
}

```

## disassembly

```asm
0x140029860  push    rbp
0x140029862  push    rbx
0x140029863  push    rsi
0x140029864  push    rdi
0x140029865  push    r14
0x140029867  mov     rbp, rsp
0x14002986a  sub     rsp, 50h
0x14002986e  mov     rsi, rdx
0x140029871  mov     rbx, rcx
0x140029874  lea     r8, aCvdspnpnotific_24; "CVdsPnPNotificationManager::RemoveVolum"...
0x14002987b  mov     edx, 5Eh ; '^'
0x140029880  lea     rcx, [rbp+var_28]
0x140029884  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x14002988a  nop
0x14002988b  lea     rdi, [rbx+8]
0x14002988f  mov     [rbp+var_30], rdi
0x140029893  mov     rcx, rdi; lpCriticalSection
0x140029896  call    cs:__imp_EnterCriticalSection
0x14002989c  nop
0x14002989d  lea     r14, [rbx+0A0h]
0x1400298a4  lea     rdx, [rbp+var_18]
0x1400298a8  mov     rcx, r14
0x1400298ab  call    cs:__imp_?Begin@CRtlMap@@QEAA?AVCRtlMapIter@@XZ; CRtlMap::Begin(void)
0x1400298b1  cmp     [rbp+var_18], 0
0x1400298b6  jz      loc_14002996F
0x1400298bc  mov     rcx, [rbp+var_10]
0x1400298c0  test    rcx, rcx
0x1400298c3  jz      loc_14002996F
0x1400298c9  mov     rdx, rsi; String2
0x1400298cc  mov     rcx, [rcx+30h]; String1
0x1400298d0  call    cs:__imp__wcsicmp
0x1400298d6  test    eax, eax
0x1400298d8  jz      short loc_1400298E6
0x1400298da  lea     rcx, [rbp+var_18]
0x1400298de  call    cs:__imp_?Next@CRtlMapIter@@QEAAAEAV1@XZ; CRtlMapIter::Next(void)
0x1400298e4  jmp     short loc_1400298B1
0x1400298e6  mov     rax, [rbp+var_10]
0x1400298ea  test    rax, rax
0x1400298ed  jz      short loc_1400298F5
0x1400298ef  mov     rbx, [rax+30h]
0x1400298f3  jmp     short loc_1400298F7
0x1400298f5  xor     ebx, ebx
0x1400298f7  call    cs:__imp_GetProcessHeap
0x1400298fd  mov     r8, rbx
0x140029900  xor     edx, edx
0x140029902  mov     rcx, rax
0x140029905  call    cs:__imp_VdsHeapFree
0x14002990b  mov     rax, [rbp+var_10]
0x14002990f  test    rax, rax
0x140029912  jz      short loc_140029918
0x140029914  add     rax, 20h ; ' '
0x140029918  mov     qword ptr [rax+8], 0
0x140029920  mov     qword ptr [rax+10h], 0
0x140029928  mov     rax, [rbp+var_10]
0x14002992c  test    rax, rax
0x14002992f  jz      short loc_140029937
0x140029931  mov     rcx, [rax+10h]
0x140029935  jmp     short loc_140029939
0x140029937  xor     ecx, ecx; Handle
0x140029939  call    cs:__imp_UnregisterDeviceNotification
0x14002993f  mov     rdx, [rbp+var_10]
0x140029943  mov     rcx, r14
0x140029946  call    cs:__imp_?Remove@CRtlMap@@QEAAHAEAVCRtlEntry@@@Z; CRtlMap::Remove(CRtlEntry &)
0x14002994c  call    ?RemoveObsoleteDevNodes@CVdsService@@SAJXZ; CVdsService::RemoveObsoleteDevNodes(void)
0x140029951  test    eax, eax
0x140029953  jns     short loc_140029988
0x140029955  mov     r9d, eax
0x140029958  lea     r8, aCvdspnpnotific_10; "CVdsPnPNotificationManager::RemoveVolum"...
0x14002995f  mov     edx, 1
0x140029964  lea     ecx, [rdx+5Dh]
0x140029967  call    cs:__imp_VdsTraceEx
0x14002996d  jmp     short loc_140029988
0x14002996f  mov     r9, rsi
0x140029972  lea     r8, aRemovevolumefr; "RemoveVolumeFromMap: volume not found: "...
0x140029979  mov     edx, 1
0x14002997e  lea     ecx, [rdx+5Dh]
0x140029981  call    cs:__imp_VdsTraceEx
0x140029987  nop
0x140029988  mov     rcx, rdi; lpCriticalSection
0x14002998b  call    cs:__imp_LeaveCriticalSection
0x140029991  nop
0x140029992  lea     rcx, [rbp+var_28]
0x140029996  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x14002999c  add     rsp, 50h
0x1400299a0  pop     r14
0x1400299a2  pop     rdi
0x1400299a3  pop     rsi
0x1400299a4  pop     rbx
0x1400299a5  pop     rbp
0x1400299a6  retn
```
