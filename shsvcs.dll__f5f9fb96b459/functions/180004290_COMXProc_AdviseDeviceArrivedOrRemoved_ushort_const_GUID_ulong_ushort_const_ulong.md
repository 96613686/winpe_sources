# COMXProc::AdviseDeviceArrivedOrRemoved(ushort const *,_GUID *,ulong,ushort const *,ulong)

- ea: `0x180004290`
- end: `0x1800043f1`
- name: `?AdviseDeviceArrivedOrRemoved@COMXProc@@YAJPEBGPEAU_GUID@@K0K@Z`
- size: `353`
- prototype: `__int64 __fastcall(COMXProc *this, struct _GUID *, struct _GUID *, PCNZWCH lpString1, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800036e0`

## callees

- `0x180004290`
- `0x1800137e0`
- `0x180017070`
- `0x18001b404`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000434b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000434b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004361`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000436f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004361`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000436f`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000431e`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000431e`

## pseudocode

```c
__int64 __fastcall COMXProc::AdviseDeviceArrivedOrRemoved(
        COMXProc *this,
        struct _GUID *a2,
        struct _GUID *a3,
        PCNZWCH lpString1,
        const unsigned __int16 *a5)
{
  unsigned int v7; // ebp
  void *v9; // rbx
  int v10; // eax
  unsigned int v11; // r12d
  int v12; // esi

  v7 = (unsigned int)a3;
  v9 = operator new(0x30u);
  if ( !v9 )
    return 2147942414LL;
  *((_QWORD *)v9 + 1) = 1;
  *((_DWORD *)v9 + 5) = 0;
  *((_QWORD *)v9 + 4) = 0;
  *((_QWORD *)v9 + 3) = 0;
  *((_QWORD *)v9 + 5) = 0;
  *(_QWORD *)v9 = &COMXProc::CThreadTaskDeviceEvent::`vftable';
  *((_DWORD *)v9 + 4) = -2147418113;
  v10 = CompareStringW(0x7Fu, 1u, lpString1, -1, L"DeviceArrival", -1);
  v11 = 32;
  v12 = -2147467259;
  if ( v10 != 2 )
    v11 = 128;
  if ( XProcHelpers::g_fInitialized )
  {
    EnterCriticalSection(&stru_18003E3B8);
    if ( XProcHelpers::g_fShuttingDown )
    {
      LeaveCriticalSection(&stru_18003E3B8);
    }
    else
    {
      ++XProcHelpers::g_cActiveThread;
      LeaveCriticalSection(&stru_18003E3B8);
      *((_DWORD *)v9 + 8) = 1;
      v12 = COMXProc::CThreadTaskDeviceEvent::Init(
              (COMXProc::CThreadTaskDeviceEvent *)v9,
              (const unsigned __int16 *)this,
              a2,
              v7,
              v11,
              (unsigned int)a5);
      if ( v12 >= 0 )
        v12 = CThreadTask::Run(v9);
    }
  }
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v9 + 2, 0xFFFFFFFF) == 1 )
    (**(void (__fastcall ***)(void *, __int64))v9)(v9, 1);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180004290  mov     [rsp+arg_10], rbx
0x180004295  mov     [rsp+arg_18], rbp
0x18000429a  push    rsi
0x18000429b  push    r14
0x18000429d  push    r15
0x18000429f  sub     rsp, 40h
0x1800042a3  mov     r15, rcx
0x1800042a6  mov     rsi, r9
0x1800042a9  mov     ecx, 30h ; '0'; Size
0x1800042ae  mov     ebp, r8d
0x1800042b1  mov     r14, rdx
0x1800042b4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800042b9  mov     rbx, rax
0x1800042bc  test    rax, rax
0x1800042bf  jz      loc_1800043D8
0x1800042c5  xor     eax, eax
0x1800042c7  mov     [rsp+58h+arg_0], rdi
0x1800042cc  mov     qword ptr [rbx+8], 1
0x1800042d4  mov     edi, 0FFFFFFFFh
0x1800042d9  mov     [rsp+58h+arg_8], r12
0x1800042de  mov     r9d, edi; cchCount1
0x1800042e1  mov     [rbx+14h], eax
0x1800042e4  mov     r8, rsi; lpString1
0x1800042e7  mov     [rbx+20h], rax
0x1800042eb  mov     edx, 1; dwCmpFlags
0x1800042f0  mov     [rbx+18h], rax
0x1800042f4  mov     ecx, 7Fh; Locale
0x1800042f9  mov     [rbx+28h], rax
0x1800042fd  lea     rax, ??_7CThreadTaskDeviceEvent@COMXProc@@6B@; const COMXProc::CThreadTaskDeviceEvent::`vftable'
0x180004304  mov     [rbx], rax
0x180004307  lea     rax, aDevicearrival; "DeviceArrival"
0x18000430e  mov     [rsp+58h+cchCount2], edi; cchCount2
0x180004312  mov     [rsp+58h+lpString2], rax; lpString2
0x180004317  mov     dword ptr [rbx+10h], 8000FFFFh
0x18000431e  call    cs:__imp_CompareStringW
0x180004324  mov     ecx, 80h
0x180004329  mov     r12d, 20h ; ' '
0x18000432f  cmp     eax, 2
0x180004332  mov     esi, 80004005h
0x180004337  cmovnz  r12d, ecx
0x18000433b  cmp     cs:?g_fInitialized@XProcHelpers@@3HA, 0; int XProcHelpers::g_fInitialized
0x180004342  jz      short loc_1800043AD
0x180004344  lea     rcx, stru_18003E3B8; lpCriticalSection
0x18000434b  call    cs:__imp_EnterCriticalSection
0x180004351  cmp     cs:?g_fShuttingDown@XProcHelpers@@3HA, 0; int XProcHelpers::g_fShuttingDown
0x180004358  lea     rcx, stru_18003E3B8; lpCriticalSection
0x18000435f  jz      short loc_180004369
0x180004361  call    cs:__imp_LeaveCriticalSection
0x180004367  jmp     short loc_1800043AD
0x180004369  inc     cs:?g_cActiveThread@XProcHelpers@@3KA; ulong XProcHelpers::g_cActiveThread
0x18000436f  call    cs:__imp_LeaveCriticalSection
0x180004375  mov     eax, dword ptr [rsp+58h+arg_20]
0x18000437c  mov     r9d, ebp; unsigned int
0x18000437f  mov     [rsp+58h+cchCount2], eax; unsigned int
0x180004383  mov     r8, r14; struct _GUID *
0x180004386  mov     rdx, r15; unsigned __int16 *
0x180004389  mov     dword ptr [rsp+58h+lpString2], r12d; unsigned int
0x18000438e  mov     rcx, rbx; this
0x180004391  mov     dword ptr [rbx+20h], 1
0x180004398  call    ?Init@CThreadTaskDeviceEvent@COMXProc@@QEAAJPEBGPEAU_GUID@@KKK@Z; COMXProc::CThreadTaskDeviceEvent::Init(ushort const *,_GUID *,ulong,ulong,ulong)
0x18000439d  mov     esi, eax
0x18000439f  test    eax, eax
0x1800043a1  js      short loc_1800043AD
0x1800043a3  mov     rcx, rbx; Context
0x1800043a6  call    ?Run@CThreadTask@@QEAAJXZ; CThreadTask::Run(void)
0x1800043ab  mov     esi, eax
0x1800043ad  lock xadd [rbx+8], edi
0x1800043b2  mov     r12, [rsp+58h+arg_8]
0x1800043b7  cmp     edi, 1
0x1800043ba  mov     rdi, [rsp+58h+arg_0]
0x1800043bf  jnz     short loc_1800043D4
0x1800043c1  mov     rax, [rbx]
0x1800043c4  mov     edx, 1
0x1800043c9  mov     rcx, rbx
0x1800043cc  mov     rax, [rax]
0x1800043cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800043d4  mov     eax, esi
0x1800043d6  jmp     short loc_1800043DD
0x1800043d8  mov     eax, 8007000Eh
0x1800043dd  mov     rbx, [rsp+58h+arg_10]
0x1800043e2  mov     rbp, [rsp+58h+arg_18]
0x1800043e7  add     rsp, 40h
0x1800043eb  pop     r15
0x1800043ed  pop     r14
0x1800043ef  pop     rsi
0x1800043f0  retn
```
