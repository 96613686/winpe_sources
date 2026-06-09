# NThreadingLibrary::TWorkCrew::CancelWorkThread(_TP_CALLBACK_INSTANCE *,void *,_TP_WAIT *,long)

- ea: `0x140013640`
- end: `0x140013868`
- name: `?CancelWorkThread@TWorkCrew@NThreadingLibrary@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z`
- size: `552`
- prototype: `void __fastcall(struct _TP_CALLBACK_INSTANCE *, void *, struct _TP_WAIT *, int)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400131c4`
- `0x140013b24`

## callees

- `0x140013640`
- `0x140013adc`
- `0x140016010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140013680`
- `KERNEL32!GetCurrentThreadId` at `0x1400137ed`
- `KERNEL32!GetCurrentThreadId` at `0x140013680`
- `KERNEL32!GetCurrentThreadId` at `0x1400137ed`
- `KERNEL32!EnterCriticalSection` at `0x140013670`
- `KERNEL32!EnterCriticalSection` at `0x1400137e3`
- `KERNEL32!EnterCriticalSection` at `0x140013670`
- `KERNEL32!EnterCriticalSection` at `0x1400137e3`
- `KERNEL32!LeaveCriticalSection` at `0x1400136ba`
- `KERNEL32!LeaveCriticalSection` at `0x140013827`
- `KERNEL32!LeaveCriticalSection` at `0x1400136ba`
- `KERNEL32!LeaveCriticalSection` at `0x140013827`
- `KERNEL32!SetThreadpoolTimer` at `0x140013741`
- `KERNEL32!SetThreadpoolTimer` at `0x140013741`
- `ntdll!TpCallbackMayRunLong` at `0x14001383e`
- `ntdll!TpCallbackMayRunLong` at `0x14001383e`
- `ntdll!TpSetWait` at `0x14001376e`
- `ntdll!TpSetWait` at `0x140013855`
- `ntdll!TpSetWait` at `0x14001376e`
- `ntdll!TpSetWait` at `0x140013855`
- `ntdll!TpWaitForWork` at `0x140013799`
- `ntdll!TpWaitForWork` at `0x140013799`
- `ntdll!TpReleaseWork` at `0x1400137a3`
- `ntdll!TpReleaseWork` at `0x1400137a3`
- `ntdll!TpWaitForWait` at `0x14001377b`
- `ntdll!TpWaitForWait` at `0x14001377b`
- `ntdll!TpReleaseWait` at `0x140013785`
- `ntdll!TpReleaseWait` at `0x140013785`
- `ntdll!TpWaitForTimer` at `0x14001374e`
- `ntdll!TpWaitForTimer` at `0x14001374e`
- `ntdll!TpReleaseTimer` at `0x140013758`
- `ntdll!TpReleaseTimer` at `0x140013758`
- `ntdll!TpWaitForIoCompletion` at `0x14001371a`
- `ntdll!TpWaitForIoCompletion` at `0x14001371a`
- `ntdll!TpReleaseIoCompletion` at `0x140013724`
- `ntdll!TpReleaseIoCompletion` at `0x140013724`
- `ntdll!TpWaitForAlpcCompletion` at `0x1400136f5`
- `ntdll!TpWaitForAlpcCompletion` at `0x1400136f5`
- `ntdll!TpReleaseAlpcCompletion` at `0x1400136ff`
- `ntdll!TpReleaseAlpcCompletion` at `0x1400136ff`

## pseudocode

```c
void __fastcall NThreadingLibrary::TWorkCrew::CancelWorkThread(
        struct _TP_CALLBACK_INSTANCE *a1,
        struct _RTL_CRITICAL_SECTION *a2,
        struct _TP_WAIT *a3)
{
  struct _RTL_CRITICAL_SECTION *v5; // rbx
  __int64 v6; // rcx
  struct _TP_TIMER *v7; // rcx
  __int64 v8; // rcx
  __int64 v9; // rcx
  signed __int32 v10; // edx
  __int64 v11; // rdi

  if ( !a2 || LODWORD(a2->SpinCount) != 2003985271 )
    goto LABEL_33;
  v5 = a2 + 1;
  EnterCriticalSection(a2 + 1);
  ++HIDWORD(v5[1].DebugInfo);
  LODWORD(v5[1].DebugInfo) = GetCurrentThreadId();
  if ( LODWORD(a2[4].SpinCount) )
    goto LABEL_30;
  LODWORD(a2[4].SpinCount) = 1;
  while ( 1 )
  {
    v11 = NCoreLibrary::TList<NThreadingLibrary::TWorkItem>::RemoveAtHead(&a2[3].OwningThread);
    if ( !v11 )
      break;
    if ( !--HIDWORD(v5[1].DebugInfo) )
      LODWORD(v5[1].DebugInfo) = 0;
    LeaveCriticalSection(v5);
    switch ( *(_DWORD *)(v11 + 88) )
    {
      case 1:
        v9 = *(_QWORD *)(v11 + 96);
        if ( v9 )
        {
          TpWaitForWork(v9, 1);
          TpReleaseWork(*(_QWORD *)(v11 + 96));
          goto LABEL_22;
        }
        break;
      case 2:
        v8 = *(_QWORD *)(v11 + 96);
        if ( v8 )
        {
          TpSetWait(v8, 0, 0);
          TpWaitForWait(*(_QWORD *)(v11 + 96), 1);
          TpReleaseWait(*(_QWORD *)(v11 + 96));
          goto LABEL_22;
        }
        break;
      case 3:
        v7 = *(struct _TP_TIMER **)(v11 + 96);
        if ( v7 )
        {
          SetThreadpoolTimer(v7, 0, 0, 0);
          TpWaitForTimer(*(_QWORD *)(v11 + 96), 1);
          TpReleaseTimer(*(_QWORD *)(v11 + 96));
          goto LABEL_22;
        }
        break;
      case 4:
        v6 = *(_QWORD *)(v11 + 96);
        if ( v6 )
        {
          TpWaitForIoCompletion(v6, 1);
          TpReleaseIoCompletion(*(_QWORD *)(v11 + 96));
          goto LABEL_22;
        }
        break;
      default:
        if ( *(_DWORD *)(v11 + 88) == 5 && *(_QWORD *)(v11 + 96) )
        {
          TpWaitForAlpcCompletion();
          TpReleaseAlpcCompletion(*(_QWORD *)(v11 + 96));
LABEL_22:
          *(_QWORD *)(v11 + 96) = 0;
          goto LABEL_24;
        }
        break;
    }
    do
LABEL_24:
      v10 = *(_DWORD *)(v11 + 8);
    while ( v10 != 0x7FFFFFFF && v10 != _InterlockedCompareExchange((volatile signed __int32 *)(v11 + 8), v10 - 1, v10) );
    if ( v10 == 1 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 8LL))(v11);
    EnterCriticalSection(v5);
    ++HIDWORD(v5[1].DebugInfo);
    LODWORD(v5[1].DebugInfo) = GetCurrentThreadId();
  }
  LODWORD(a2[4].SpinCount) = 0;
LABEL_30:
  if ( HIDWORD(v5[1].DebugInfo)-- == 1 )
    LODWORD(v5[1].DebugInfo) = 0;
  LeaveCriticalSection(v5);
LABEL_33:
  if ( a1 )
  {
    if ( !LODWORD(a2[4].OwningThread) )
    {
      TpCallbackMayRunLong(a1, a2, a3);
      TpSetWait(a2[5].OwningThread, a2[4].LockSemaphore, 0);
    }
  }
}

```

## disassembly

```asm
0x140013640  push    rbx
0x140013642  push    rbp
0x140013643  push    rsi
0x140013644  push    rdi
0x140013645  push    r12
0x140013647  push    r14
0x140013649  sub     rsp, 28h
0x14001364d  mov     rsi, rdx
0x140013650  mov     rbp, rcx
0x140013653  test    rdx, rdx
0x140013656  jz      loc_14001382D
0x14001365c  cmp     dword ptr [rdx+20h], 77726377h
0x140013663  jnz     loc_14001382D
0x140013669  lea     rbx, [rdx+28h]
0x14001366d  mov     rcx, rbx; lpCriticalSection
0x140013670  call    cs:__imp_EnterCriticalSection
0x140013676  mov     r12d, 1
0x14001367c  add     [rbx+2Ch], r12d
0x140013680  call    cs:__imp_GetCurrentThreadId
0x140013686  mov     [rbx+28h], eax
0x140013689  cmp     dword ptr [rsi+0C0h], 0
0x140013690  jnz     loc_140013814
0x140013696  mov     [rsi+0C0h], r12d
0x14001369d  lea     r14, [rsi+88h]
0x1400136a4  jmp     loc_1400137F6
0x1400136a9  sub     [rbx+2Ch], r12d
0x1400136ad  mov     eax, [rbx+2Ch]
0x1400136b0  test    eax, eax
0x1400136b2  jnz     short loc_1400136B7
0x1400136b4  mov     [rbx+28h], eax
0x1400136b7  mov     rcx, rbx; lpCriticalSection
0x1400136ba  call    cs:__imp_LeaveCriticalSection
0x1400136c0  mov     ecx, [rdi+58h]
0x1400136c3  sub     ecx, r12d
0x1400136c6  jz      loc_14001378D
0x1400136cc  sub     ecx, r12d
0x1400136cf  jz      loc_140013760
0x1400136d5  sub     ecx, r12d
0x1400136d8  jz      short loc_14001372C
0x1400136da  sub     ecx, r12d
0x1400136dd  jz      short loc_14001370A
0x1400136df  cmp     ecx, r12d
0x1400136e2  jnz     loc_1400137BF
0x1400136e8  mov     rcx, [rdi+60h]
0x1400136ec  test    rcx, rcx
0x1400136ef  jz      loc_1400137BF
0x1400136f5  call    cs:__imp_TpWaitForAlpcCompletion
0x1400136fb  mov     rcx, [rdi+60h]
0x1400136ff  call    cs:__imp_TpReleaseAlpcCompletion
0x140013705  jmp     loc_1400137A9
0x14001370a  mov     rcx, [rdi+60h]
0x14001370e  test    rcx, rcx
0x140013711  jz      loc_1400137BF
0x140013717  mov     edx, r12d
0x14001371a  call    cs:__imp_TpWaitForIoCompletion
0x140013720  mov     rcx, [rdi+60h]
0x140013724  call    cs:__imp_TpReleaseIoCompletion
0x14001372a  jmp     short loc_1400137A9
0x14001372c  mov     rcx, [rdi+60h]; pti
0x140013730  test    rcx, rcx
0x140013733  jz      loc_1400137BF
0x140013739  xor     r9d, r9d; msWindowLength
0x14001373c  xor     r8d, r8d; msPeriod
0x14001373f  xor     edx, edx; pftDueTime
0x140013741  call    cs:__imp_SetThreadpoolTimer
0x140013747  mov     rcx, [rdi+60h]
0x14001374b  mov     edx, r12d
0x14001374e  call    cs:__imp_TpWaitForTimer
0x140013754  mov     rcx, [rdi+60h]
0x140013758  call    cs:__imp_TpReleaseTimer
0x14001375e  jmp     short loc_1400137A9
0x140013760  mov     rcx, [rdi+60h]
0x140013764  test    rcx, rcx
0x140013767  jz      short loc_1400137BF
0x140013769  xor     r8d, r8d
0x14001376c  xor     edx, edx
0x14001376e  call    cs:__imp_TpSetWait
0x140013774  mov     rcx, [rdi+60h]
0x140013778  mov     edx, r12d
0x14001377b  call    cs:__imp_TpWaitForWait
0x140013781  mov     rcx, [rdi+60h]
0x140013785  call    cs:__imp_TpReleaseWait
0x14001378b  jmp     short loc_1400137A9
0x14001378d  mov     rcx, [rdi+60h]
0x140013791  test    rcx, rcx
0x140013794  jz      short loc_1400137BF
0x140013796  mov     edx, r12d
0x140013799  call    cs:__imp_TpWaitForWork
0x14001379f  mov     rcx, [rdi+60h]
0x1400137a3  call    cs:__imp_TpReleaseWork
0x1400137a9  mov     qword ptr [rdi+60h], 0
0x1400137b1  jmp     short loc_1400137BF
0x1400137b3  lea     ecx, [rdx-1]
0x1400137b6  mov     eax, edx
0x1400137b8  lock cmpxchg [rdi+8], ecx
0x1400137bd  jz      short loc_1400137CA
0x1400137bf  mov     edx, [rdi+8]
0x1400137c2  cmp     edx, 7FFFFFFFh
0x1400137c8  jnz     short loc_1400137B3
0x1400137ca  lea     eax, [rdx-1]
0x1400137cd  test    eax, eax
0x1400137cf  jnz     short loc_1400137E0
0x1400137d1  mov     rax, [rdi]
0x1400137d4  mov     rcx, rdi
0x1400137d7  mov     rax, [rax+8]
0x1400137db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400137e0  mov     rcx, rbx; lpCriticalSection
0x1400137e3  call    cs:__imp_EnterCriticalSection
0x1400137e9  add     [rbx+2Ch], r12d
0x1400137ed  call    cs:__imp_GetCurrentThreadId
0x1400137f3  mov     [rbx+28h], eax
0x1400137f6  mov     rcx, r14
0x1400137f9  call    ?RemoveAtHead@?$TList@VTWorkItem@NThreadingLibrary@@@NCoreLibrary@@QEAAPEAVTWorkItem@NThreadingLibrary@@XZ; NCoreLibrary::TList<NThreadingLibrary::TWorkItem>::RemoveAtHead(void)
0x1400137fe  mov     rdi, rax
0x140013801  test    rax, rax
0x140013804  jnz     loc_1400136A9
0x14001380a  mov     dword ptr [rsi+0C0h], 0
0x140013814  add     dword ptr [rbx+2Ch], 0FFFFFFFFh
0x140013818  mov     eax, [rbx+2Ch]
0x14001381b  jnz     short loc_140013824
0x14001381d  mov     dword ptr [rbx+28h], 0
0x140013824  mov     rcx, rbx; lpCriticalSection
0x140013827  call    cs:__imp_LeaveCriticalSection
0x14001382d  test    rbp, rbp
0x140013830  jz      short loc_14001385B
0x140013832  cmp     dword ptr [rsi+0B0h], 0
0x140013839  jnz     short loc_14001385B
0x14001383b  mov     rcx, rbp
0x14001383e  call    cs:__imp_TpCallbackMayRunLong
0x140013844  mov     rdx, [rsi+0B8h]
0x14001384b  xor     r8d, r8d
0x14001384e  mov     rcx, [rsi+0D8h]
0x140013855  call    cs:__imp_TpSetWait
0x14001385b  add     rsp, 28h
0x14001385f  pop     r14
0x140013861  pop     r12
0x140013863  pop     rdi
0x140013864  pop     rsi
0x140013865  pop     rbp
0x140013866  pop     rbx
0x140013867  retn
```
