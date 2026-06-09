# NThreadingLibrary::TWorkCrew::tpTimerCallback(_TP_CALLBACK_INSTANCE *,void *,_TP_TIMER *)

- ea: `0x140013d00`
- end: `0x140013dd6`
- name: `?tpTimerCallback@TWorkCrew@NThreadingLibrary@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z`
- size: `214`
- prototype: `static void(struct _TP_CALLBACK_INSTANCE *, void *, struct _TP_TIMER *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1400139b0`
- `0x140013d00`
- `0x140016010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140013d33`
- `KERNEL32!GetCurrentThreadId` at `0x140013d7c`
- `KERNEL32!GetCurrentThreadId` at `0x140013d33`
- `KERNEL32!GetCurrentThreadId` at `0x140013d7c`
- `KERNEL32!EnterCriticalSection` at `0x140013d2a`
- `KERNEL32!EnterCriticalSection` at `0x140013d73`
- `KERNEL32!EnterCriticalSection` at `0x140013d2a`
- `KERNEL32!EnterCriticalSection` at `0x140013d73`
- `KERNEL32!LeaveCriticalSection` at `0x140013d5a`
- `KERNEL32!LeaveCriticalSection` at `0x140013dc6`
- `KERNEL32!LeaveCriticalSection` at `0x140013d5a`
- `KERNEL32!LeaveCriticalSection` at `0x140013dc6`
- `KERNEL32!SetThreadpoolTimer` at `0x140013da3`
- `KERNEL32!SetThreadpoolTimer` at `0x140013da3`

## pseudocode

```c
void __fastcall NThreadingLibrary::TWorkCrew::tpTimerCallback(
        struct _TP_CALLBACK_INSTANCE *a1,
        void *a2,
        struct _TP_TIMER *a3)
{
  __int64 v4; // rbx
  __int64 v5; // rsi

  if ( a2 && *((_DWORD *)a2 + 16) == 1953063799 )
  {
    v4 = *((_QWORD *)a2 + 10);
    EnterCriticalSection((LPCRITICAL_SECTION)(v4 + 40));
    ++*(_DWORD *)(v4 + 84);
    *(_DWORD *)(v4 + 80) = GetCurrentThreadId();
    if ( !*((_DWORD *)a2 + 17) )
    {
      v5 = *((_QWORD *)a2 + 10);
      if ( (*(_DWORD *)(v5 + 84))-- == 1 )
        *(_DWORD *)(v5 + 80) = 0;
      LeaveCriticalSection((LPCRITICAL_SECTION)(v5 + 40));
      (*(void (__fastcall **)(void *))(*(_QWORD *)a2 + 24LL))(a2);
      EnterCriticalSection((LPCRITICAL_SECTION)(v5 + 40));
      ++*(_DWORD *)(v5 + 84);
      *(_DWORD *)(v5 + 80) = GetCurrentThreadId();
      if ( !*((_DWORD *)a2 + 17) && !*((_DWORD *)a2 + 28) && *((_DWORD *)a2 + 30) )
      {
        SetThreadpoolTimer(*((PTP_TIMER *)a2 + 12), 0, 0, 0);
        NThreadingLibrary::TWorkCrew::MoveWorkItemToCancelQueue(
          *((NThreadingLibrary::TWorkCrew **)a2 + 10),
          (struct NThreadingLibrary::TWorkItem *)a2);
      }
    }
    if ( !--*(_DWORD *)(v4 + 84) )
      *(_DWORD *)(v4 + 80) = 0;
    LeaveCriticalSection((LPCRITICAL_SECTION)(v4 + 40));
  }
}

```

## disassembly

```asm
0x140013d00  test    rdx, rdx
0x140013d03  jz      locret_140013DD5
0x140013d09  push    rbx
0x140013d0a  push    rsi
0x140013d0b  push    rdi
0x140013d0c  push    r14
0x140013d0e  sub     rsp, 28h
0x140013d12  cmp     dword ptr [rdx+40h], 74696377h
0x140013d19  mov     rdi, rdx
0x140013d1c  jnz     loc_140013DCC
0x140013d22  mov     rbx, [rdx+50h]
0x140013d26  lea     rcx, [rbx+28h]; lpCriticalSection
0x140013d2a  call    cs:__imp_EnterCriticalSection
0x140013d30  inc     dword ptr [rbx+54h]
0x140013d33  call    cs:__imp_GetCurrentThreadId
0x140013d39  mov     [rbx+50h], eax
0x140013d3c  cmp     dword ptr [rdi+44h], 0
0x140013d40  jnz     short loc_140013DB5
0x140013d42  mov     rsi, [rdi+50h]
0x140013d46  add     dword ptr [rsi+54h], 0FFFFFFFFh
0x140013d4a  mov     eax, [rsi+54h]
0x140013d4d  jnz     short loc_140013D56
0x140013d4f  mov     dword ptr [rsi+50h], 0
0x140013d56  lea     rcx, [rsi+28h]; lpCriticalSection
0x140013d5a  call    cs:__imp_LeaveCriticalSection
0x140013d60  mov     rax, [rdi]
0x140013d63  mov     rcx, rdi
0x140013d66  mov     rax, [rax+18h]
0x140013d6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140013d6f  lea     rcx, [rsi+28h]; lpCriticalSection
0x140013d73  call    cs:__imp_EnterCriticalSection
0x140013d79  inc     dword ptr [rsi+54h]
0x140013d7c  call    cs:__imp_GetCurrentThreadId
0x140013d82  mov     [rsi+50h], eax
0x140013d85  cmp     dword ptr [rdi+44h], 0
0x140013d89  jnz     short loc_140013DB5
0x140013d8b  cmp     dword ptr [rdi+70h], 0
0x140013d8f  jnz     short loc_140013DB5
0x140013d91  cmp     dword ptr [rdi+78h], 0
0x140013d95  jz      short loc_140013DB5
0x140013d97  mov     rcx, [rdi+60h]; pti
0x140013d9b  xor     r9d, r9d; msWindowLength
0x140013d9e  xor     r8d, r8d; msPeriod
0x140013da1  xor     edx, edx; pftDueTime
0x140013da3  call    cs:__imp_SetThreadpoolTimer
0x140013da9  mov     rcx, [rdi+50h]; this
0x140013dad  mov     rdx, rdi; struct NThreadingLibrary::TWorkItem *
0x140013db0  call    ?MoveWorkItemToCancelQueue@TWorkCrew@NThreadingLibrary@@AEAAJPEAVTWorkItem@2@@Z; NThreadingLibrary::TWorkCrew::MoveWorkItemToCancelQueue(NThreadingLibrary::TWorkItem *)
0x140013db5  dec     dword ptr [rbx+54h]
0x140013db8  mov     eax, [rbx+54h]
0x140013dbb  test    eax, eax
0x140013dbd  jnz     short loc_140013DC2
0x140013dbf  mov     [rbx+50h], eax
0x140013dc2  lea     rcx, [rbx+28h]; lpCriticalSection
0x140013dc6  call    cs:__imp_LeaveCriticalSection
0x140013dcc  add     rsp, 28h
0x140013dd0  pop     r14
0x140013dd2  pop     rdi
0x140013dd3  pop     rsi
0x140013dd4  pop     rbx
0x140013dd5  retn
```
