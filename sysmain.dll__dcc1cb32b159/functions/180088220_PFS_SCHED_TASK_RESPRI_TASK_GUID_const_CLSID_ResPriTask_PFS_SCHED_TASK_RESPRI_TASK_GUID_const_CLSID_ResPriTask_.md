# PFS_SCHED_TASK<RESPRI_TASK,&_GUID const CLSID_ResPriTask>::~PFS_SCHED_TASK<RESPRI_TASK,&_GUID const CLSID_ResPriTask>(void)

- ea: `0x180088220`
- end: `0x180088300`
- name: `??1?$PFS_SCHED_TASK@VRESPRI_TASK@@$1?CLSID_ResPriTask@@3U_GUID@@B@@UEAA@XZ`
- size: `224`
- prototype: `void __fastcall(__int64)`
- caller_count: `5`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180088330`
- `0x180088350`
- `0x180088410`
- `0x180088450`
- `0x180088490`

## callees

- `0x18006ff04`
- `0x180088220`
- `0x1800b7010`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x180088295`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180088295`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800882d3`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800882d3`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18008827f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18008827f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800882f3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008823c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180088263`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180088275`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008823c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180088263`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180088275`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800882bb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800882bb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800882a9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800882a9`

## pseudocode

```c
void __fastcall PFS_SCHED_TASK<RESPRI_TASK,&_GUID const CLSID_ResPriTask>::~PFS_SCHED_TASK<RESPRI_TASK,&_GUID const CLSID_ResPriTask>(
        __int64 a1)
{
  void *v2; // rcx
  __int64 v3; // rcx
  void *v4; // rcx
  void *v5; // rcx
  HANDLE ProcessHeap; // rax

  *(_QWORD *)a1 = &PFS_SCHED_TASK<HBDRV_TASK,&_GUID const CLSID_HbDrvTask>::`vftable';
  v2 = *(void **)(a1 + 120);
  if ( v2 )
    CloseHandle(v2);
  v3 = *(_QWORD *)(a1 + 104);
  if ( v3 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  v4 = *(void **)(a1 + 136);
  if ( v4 )
    CloseHandle(v4);
  v5 = *(void **)(a1 + 144);
  if ( v5 )
    CloseHandle(v5);
  DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 64));
  if ( *(_DWORD *)(a1 + 132) )
  {
    RtlAcquireSRWLockExclusive(&PfSvcGlobalsLock);
    if ( !--PfSvcGlobalsRefCount )
    {
      PfSvGlobalsCleanup();
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, *(LPVOID *)&PfSvcGlobals);
      *(_QWORD *)&PfSvcGlobals = 0;
    }
    RtlReleaseSRWLockExclusive(&PfSvcGlobalsLock);
  }
  _InterlockedDecrement((volatile signed __int32 *)&LivingComObjectCount);
  if ( *(_BYTE *)(a1 + 56) )
  {
    *(_BYTE *)(a1 + 56) = 0;
    DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 16));
  }
}

```

## disassembly

```asm
0x180088220  push    rbx
0x180088222  sub     rsp, 20h
0x180088226  lea     rax, ??_7?$PFS_SCHED_TASK@VHBDRV_TASK@@$1?CLSID_HbDrvTask@@3U_GUID@@B@@6B@; const PFS_SCHED_TASK<HBDRV_TASK,&_GUID const CLSID_HbDrvTask>::`vftable'
0x18008822d  mov     rbx, rcx
0x180088230  mov     [rcx], rax
0x180088233  mov     rcx, [rcx+78h]; hObject
0x180088237  test    rcx, rcx
0x18008823a  jz      short loc_180088242
0x18008823c  call    cs:__imp_CloseHandle
0x180088242  mov     rcx, [rbx+68h]
0x180088246  test    rcx, rcx
0x180088249  jz      short loc_180088257
0x18008824b  mov     rax, [rcx]
0x18008824e  mov     rax, [rax+10h]
0x180088252  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180088257  mov     rcx, [rbx+88h]; hObject
0x18008825e  test    rcx, rcx
0x180088261  jz      short loc_180088269
0x180088263  call    cs:__imp_CloseHandle
0x180088269  mov     rcx, [rbx+90h]; hObject
0x180088270  test    rcx, rcx
0x180088273  jz      short loc_18008827B
0x180088275  call    cs:__imp_CloseHandle
0x18008827b  lea     rcx, [rbx+40h]; lpCriticalSection
0x18008827f  call    cs:__imp_DeleteCriticalSection
0x180088285  cmp     dword ptr [rbx+84h], 0
0x18008828c  jz      short loc_1800882D9
0x18008828e  lea     rcx, PfSvcGlobalsLock
0x180088295  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18008829b  add     cs:PfSvcGlobalsRefCount, 0FFFFFFFFh
0x1800882a2  jnz     short loc_1800882CC
0x1800882a4  call    PfSvGlobalsCleanup
0x1800882a9  call    cs:__imp_GetProcessHeap
0x1800882af  mov     r8, cs:PfSvcGlobals; lpMem
0x1800882b6  xor     edx, edx; dwFlags
0x1800882b8  mov     rcx, rax; hHeap
0x1800882bb  call    cs:__imp_HeapFree
0x1800882c1  mov     cs:PfSvcGlobals, 0
0x1800882cc  lea     rcx, PfSvcGlobalsLock
0x1800882d3  call    cs:__imp_RtlReleaseSRWLockExclusive
0x1800882d9  lock dec cs:?LivingComObjectCount@@3KA; ulong LivingComObjectCount
0x1800882e0  lea     rcx, [rbx+10h]
0x1800882e4  cmp     byte ptr [rcx+28h], 0
0x1800882e8  jz      short loc_1800882FA
0x1800882ea  mov     byte ptr [rcx+28h], 0
0x1800882ee  add     rsp, 20h
0x1800882f2  pop     rbx
0x1800882f3  jmp     cs:__imp_DeleteCriticalSection
0x1800882fa  add     rsp, 20h
0x1800882fe  pop     rbx
0x1800882ff  retn
```
