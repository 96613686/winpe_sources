# NThreadingLibrary::TWorkCrew::CancelWorkThread(_TP_CALLBACK_INSTANCE *,void *,_TP_WAIT *,long)

- ea: `0x14000bf00`
- end: `0x14000c19f`
- name: `?CancelWorkThread@TWorkCrew@NThreadingLibrary@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z`
- size: `671`
- prototype: `void __fastcall(struct _TP_CALLBACK_INSTANCE *, void *, struct _TP_WAIT *, int)`
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140055ff8`
- `0x1400568c8`

## callees

- `0x14000bf00`
- `0x1400565a4`
- `0x140056600`
- `0x140056658`
- `0x1400566b4`
- `0x140056728`
- `0x140081010`

## import_xrefs

- `ntdll!TpSetWait` at `0x14000c0f5`
- `ntdll!TpSetWait` at `0x14000c0f5`
- `ntdll!TpCallbackMayRunLong` at `0x14000c0d8`
- `ntdll!TpCallbackMayRunLong` at `0x14000c0d8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14000bfd6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14000c0ad`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14000bfd6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14000c0ad`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14000bf3a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14000c03d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14000bf3a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14000c03d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000bf49`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000c04c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000bf49`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000c04c`

## pseudocode

```c
void __fastcall NThreadingLibrary::TWorkCrew::CancelWorkThread(
        struct _TP_CALLBACK_INSTANCE *a1,
        struct _RTL_CRITICAL_SECTION *a2,
        struct _TP_WAIT *a3)
{
  _QWORD *p_Type; // rdx
  _QWORD *v6; // r14
  NThreadingLibrary::TWorkCrew *v7; // rcx
  signed __int32 i; // edx
  _QWORD *v9; // rdx

  if ( a2 && LODWORD(a2->SpinCount) == 2003985271 )
  {
    EnterCriticalSection(a2 + 1);
    ++HIDWORD(a2[2].DebugInfo);
    LODWORD(a2[2].DebugInfo) = GetCurrentThreadId();
    if ( !LODWORD(a2[4].SpinCount) )
    {
      LODWORD(a2[4].SpinCount) = 1;
      p_Type = &a2[4].DebugInfo->Type;
      *(_QWORD *)(p_Type[2] + 24LL) = p_Type[3];
      *(_QWORD *)(p_Type[3] + 16LL) = p_Type[2];
      p_Type[2] = p_Type;
      p_Type[3] = p_Type;
      if ( p_Type != &a2[3].LockSemaphore )
      {
        v6 = p_Type - 4;
        if ( !p_Type )
          v6 = 0;
        while ( v6 )
        {
          if ( !--HIDWORD(a2[2].DebugInfo) )
            LODWORD(a2[2].DebugInfo) = 0;
          LeaveCriticalSection(a2 + 1);
          switch ( *((_DWORD *)v6 + 22) )
          {
            case 1:
              NThreadingLibrary::TWorkCrew::CancelQueuedItem(
                (NThreadingLibrary::TWorkCrew *)(unsigned int)(*((_DWORD *)v6 + 22) - 1),
                (struct NThreadingLibrary::TQueuedItem *)v6);
              break;
            case 2:
              NThreadingLibrary::TWorkCrew::CancelWaitItem(
                (NThreadingLibrary::TWorkCrew *)(unsigned int)(*((_DWORD *)v6 + 22) - 2),
                (struct NThreadingLibrary::TWaitItem *)v6);
              break;
            case 3:
              NThreadingLibrary::TWorkCrew::CancelTimerItem(
                (NThreadingLibrary::TWorkCrew *)(unsigned int)(*((_DWORD *)v6 + 22) - 3),
                (struct NThreadingLibrary::TTimerItem *)v6);
              break;
            default:
              v7 = (NThreadingLibrary::TWorkCrew *)(unsigned int)(*((_DWORD *)v6 + 22) - 4);
              if ( *((_DWORD *)v6 + 22) == 4 )
              {
                NThreadingLibrary::TWorkCrew::CancelIOItem(v7, (struct NThreadingLibrary::TIOItem *)v6);
              }
              else if ( *((_DWORD *)v6 + 22) == 5 )
              {
                NThreadingLibrary::TWorkCrew::CancelLpcItem(v7, (struct NThreadingLibrary::TLpcItem *)v6);
              }
              break;
          }
          for ( i = *((_DWORD *)v6 + 2); i != 0x7FFFFFFF; i = *((_DWORD *)v6 + 2) )
          {
            if ( i == _InterlockedCompareExchange((volatile signed __int32 *)v6 + 2, i - 1, i) )
              break;
          }
          if ( i == 1 )
            (*(void (__fastcall **)(_QWORD *))(*v6 + 8LL))(v6);
          EnterCriticalSection(a2 + 1);
          ++HIDWORD(a2[2].DebugInfo);
          LODWORD(a2[2].DebugInfo) = GetCurrentThreadId();
          v9 = &a2[4].DebugInfo->Type;
          *(_QWORD *)(v9[2] + 24LL) = v9[3];
          *(_QWORD *)(v9[3] + 16LL) = v9[2];
          v9[2] = v9;
          v9[3] = v9;
          if ( v9 == &a2[3].LockSemaphore )
            break;
          v6 = v9 - 4;
          if ( !v9 )
            v6 = 0;
        }
      }
      LODWORD(a2[4].SpinCount) = 0;
    }
    if ( HIDWORD(a2[2].DebugInfo)-- == 1 )
      LODWORD(a2[2].DebugInfo) = 0;
    LeaveCriticalSection(a2 + 1);
  }
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
0x14000bf00  push    rsi
0x14000bf02  push    rdi
0x14000bf03  sub     rsp, 28h
0x14000bf07  mov     rdi, rdx
0x14000bf0a  mov     rsi, rcx
0x14000bf0d  test    rdx, rdx
0x14000bf10  jz      short loc_14000BF1B
0x14000bf12  cmp     dword ptr [rdx+20h], 77726377h
0x14000bf19  jz      short loc_14000BF2C
0x14000bf1b  test    rsi, rsi
0x14000bf1e  jnz     loc_14000C0C8
0x14000bf24  add     rsp, 28h
0x14000bf28  pop     rdi
0x14000bf29  pop     rsi
0x14000bf2a  retn
0x14000bf2c  mov     [rsp+38h+arg_0], rbx
0x14000bf31  lea     rcx, [rdx+28h]; lpCriticalSection
0x14000bf35  mov     [rsp+38h+var_18], r15
0x14000bf3a  call    cs:__imp_EnterCriticalSection
0x14000bf41  nop     dword ptr [rax+rax+00h]
0x14000bf46  inc     dword ptr [rdi+54h]
0x14000bf49  call    cs:__imp_GetCurrentThreadId
0x14000bf50  nop     dword ptr [rax+rax+00h]
0x14000bf55  xor     r15d, r15d
0x14000bf58  mov     [rdi+50h], eax
0x14000bf5b  cmp     [rdi+0C0h], r15d
0x14000bf62  jnz     loc_14000C09C
0x14000bf68  mov     dword ptr [rdi+0C0h], 1
0x14000bf72  mov     [rsp+38h+arg_8], rbp
0x14000bf77  lea     rbp, [rdi+90h]
0x14000bf7e  mov     rdx, [rbp+10h]
0x14000bf82  mov     rcx, [rdx+10h]
0x14000bf86  mov     rax, [rdx+18h]
0x14000bf8a  mov     [rcx+18h], rax
0x14000bf8e  mov     rcx, [rdx+18h]
0x14000bf92  mov     rax, [rdx+10h]
0x14000bf96  mov     [rcx+10h], rax
0x14000bf9a  mov     [rdx+10h], rdx
0x14000bf9e  mov     [rdx+18h], rdx
0x14000bfa2  cmp     rdx, rbp
0x14000bfa5  jz      loc_14000C090
0x14000bfab  mov     [rsp+38h+arg_10], r14
0x14000bfb0  test    rdx, rdx
0x14000bfb3  lea     r14, [rdx-20h]
0x14000bfb7  cmovz   r14, r15
0x14000bfbb  test    r14, r14
0x14000bfbe  jz      loc_14000C08B
0x14000bfc4  dec     dword ptr [rdi+54h]
0x14000bfc7  mov     eax, [rdi+54h]
0x14000bfca  test    eax, eax
0x14000bfcc  jz      loc_14000C14C
0x14000bfd2  lea     rcx, [rdi+28h]; lpCriticalSection
0x14000bfd6  call    cs:__imp_LeaveCriticalSection
0x14000bfdd  nop     dword ptr [rax+rax+00h]
0x14000bfe2  mov     ecx, [r14+58h]
0x14000bfe6  sub     ecx, 1; this
0x14000bfe9  jz      loc_14000C189
0x14000bfef  sub     ecx, 1; this
0x14000bff2  jz      loc_14000C17C
0x14000bff8  sub     ecx, 1; this
0x14000bffb  jz      loc_14000C16F
0x14000c001  sub     ecx, 1; this
0x14000c004  jz      loc_14000C162
0x14000c00a  cmp     ecx, 1
0x14000c00d  jz      loc_14000C155
0x14000c013  mov     edx, [r14+8]
0x14000c017  cmp     edx, 7FFFFFFFh
0x14000c01d  jnz     loc_14000C110
0x14000c023  lea     eax, [rdx-1]
0x14000c026  test    eax, eax
0x14000c028  jnz     short loc_14000C039
0x14000c02a  mov     rax, [r14]
0x14000c02d  mov     rcx, r14
0x14000c030  mov     rax, [rax+8]
0x14000c034  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c039  lea     rcx, [rdi+28h]; lpCriticalSection
0x14000c03d  call    cs:__imp_EnterCriticalSection
0x14000c044  nop     dword ptr [rax+rax+00h]
0x14000c049  inc     dword ptr [rdi+54h]
0x14000c04c  call    cs:__imp_GetCurrentThreadId
0x14000c053  nop     dword ptr [rax+rax+00h]
0x14000c058  mov     [rdi+50h], eax
0x14000c05b  mov     rdx, [rdi+0A0h]
0x14000c062  mov     rcx, [rdx+10h]
0x14000c066  mov     rax, [rdx+18h]
0x14000c06a  mov     [rcx+18h], rax
0x14000c06e  mov     rcx, [rdx+18h]
0x14000c072  mov     rax, [rdx+10h]
0x14000c076  mov     [rcx+10h], rax
0x14000c07a  mov     [rdx+10h], rdx
0x14000c07e  mov     [rdx+18h], rdx
0x14000c082  cmp     rdx, rbp
0x14000c085  jnz     loc_14000C133
0x14000c08b  mov     r14, [rsp+38h+arg_10]
0x14000c090  mov     rbp, [rsp+38h+arg_8]
0x14000c095  mov     [rdi+0C0h], r15d
0x14000c09c  add     dword ptr [rdi+54h], 0FFFFFFFFh
0x14000c0a0  mov     eax, [rdi+54h]
0x14000c0a3  jz      loc_14000C196
0x14000c0a9  lea     rcx, [rdi+28h]; lpCriticalSection
0x14000c0ad  call    cs:__imp_LeaveCriticalSection
0x14000c0b4  nop     dword ptr [rax+rax+00h]
0x14000c0b9  mov     r15, [rsp+38h+var_18]
0x14000c0be  mov     rbx, [rsp+38h+arg_0]
0x14000c0c3  jmp     loc_14000BF1B
0x14000c0c8  cmp     dword ptr [rdi+0B0h], 0
0x14000c0cf  jnz     loc_14000BF24
0x14000c0d5  mov     rcx, rsi
0x14000c0d8  call    cs:__imp_TpCallbackMayRunLong
0x14000c0df  nop     dword ptr [rax+rax+00h]
0x14000c0e4  mov     rdx, [rdi+0B8h]
0x14000c0eb  xor     r8d, r8d
0x14000c0ee  mov     rcx, [rdi+0D8h]
0x14000c0f5  call    cs:__imp_TpSetWait
0x14000c0fc  nop     dword ptr [rax+rax+00h]
0x14000c101  jmp     loc_14000BF24
0x14000c110  lea     ecx, [rdx-1]
0x14000c113  mov     eax, edx
0x14000c115  lock cmpxchg [r14+8], ecx
0x14000c11b  jz      loc_14000C023
0x14000c121  mov     edx, [r14+8]
0x14000c125  cmp     edx, 7FFFFFFFh
0x14000c12b  jz      loc_14000C023
0x14000c131  jmp     short loc_14000C110
0x14000c133  test    rdx, rdx
0x14000c136  lea     r14, [rdx-20h]
0x14000c13a  cmovz   r14, r15
0x14000c13e  test    r14, r14
0x14000c141  jz      loc_14000C08B
0x14000c147  jmp     loc_14000BFC4
0x14000c14c  mov     [rdi+50h], r15d
0x14000c150  jmp     loc_14000BFD2
0x14000c155  mov     rdx, r14; struct NThreadingLibrary::TLpcItem *
0x14000c158  call    ?CancelLpcItem@TWorkCrew@NThreadingLibrary@@AEAAJPEAVTLpcItem@2@@Z; NThreadingLibrary::TWorkCrew::CancelLpcItem(NThreadingLibrary::TLpcItem *)
0x14000c15d  jmp     loc_14000C013
0x14000c162  mov     rdx, r14; struct NThreadingLibrary::TIOItem *
0x14000c165  call    ?CancelIOItem@TWorkCrew@NThreadingLibrary@@AEAAJPEAVTIOItem@2@@Z; NThreadingLibrary::TWorkCrew::CancelIOItem(NThreadingLibrary::TIOItem *)
0x14000c16a  jmp     loc_14000C013
0x14000c16f  mov     rdx, r14; struct NThreadingLibrary::TTimerItem *
0x14000c172  call    ?CancelTimerItem@TWorkCrew@NThreadingLibrary@@AEAAJPEAVTTimerItem@2@@Z; NThreadingLibrary::TWorkCrew::CancelTimerItem(NThreadingLibrary::TTimerItem *)
0x14000c177  jmp     loc_14000C013
0x14000c17c  mov     rdx, r14; struct NThreadingLibrary::TWaitItem *
0x14000c17f  call    ?CancelWaitItem@TWorkCrew@NThreadingLibrary@@AEAAJPEAVTWaitItem@2@@Z; NThreadingLibrary::TWorkCrew::CancelWaitItem(NThreadingLibrary::TWaitItem *)
0x14000c184  jmp     loc_14000C013
0x14000c189  mov     rdx, r14; struct NThreadingLibrary::TQueuedItem *
0x14000c18c  call    ?CancelQueuedItem@TWorkCrew@NThreadingLibrary@@AEAAJPEAVTQueuedItem@2@@Z; NThreadingLibrary::TWorkCrew::CancelQueuedItem(NThreadingLibrary::TQueuedItem *)
0x14000c191  jmp     loc_14000C013
0x14000c196  mov     [rdi+50h], r15d
0x14000c19a  jmp     loc_14000C0A9
```
