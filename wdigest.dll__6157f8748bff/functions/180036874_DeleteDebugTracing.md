# _DeleteDebugTracing

- ea: `0x180036874`
- end: `0x1800369d4`
- name: `_DeleteDebugTracing`
- size: `352`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800272f0`

## callees

- `0x180035fc8`
- `0x180036360`
- `0x180036874`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800368b5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800368b5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800369ab`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800369ab`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x180036958`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x180036958`
- `api-ms-win-core-threadpool-legacy-l1-1-0!ChangeTimerQueueTimer` at `0x18003699a`
- `api-ms-win-core-threadpool-legacy-l1-1-0!ChangeTimerQueueTimer` at `0x18003699a`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x1800368fc`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x1800368fc`

## pseudocode

```c
void DeleteDebugTracing()
{
  struct _DBG_TRACE_CONTROL_BLOCK *v0; // rdi
  struct _RTL_CRITICAL_SECTION *SharedMem; // rax
  struct _RTL_CRITICAL_SECTION *v2; // rbx
  __int64 v3; // rcx
  struct _DBG_TRACE_CONTROL_BLOCK **v4; // rax
  HANDLE LockSemaphore; // rax
  int SpinCount; // ecx
  PRTL_CRITICAL_SECTION_DEBUG DebugInfo; // r8
  int v8; // eax
  void (__stdcall *v9)(PVOID, BOOLEAN); // r8
  unsigned int OwningThread_high; // esi
  void *v11; // rdx

  if ( (NtCurrentPeb()->BitField & 2) == 0 )
  {
    v0 = DigestGlobalTraceControlBlock;
    if ( DigestGlobalTraceControlBlock )
    {
      SharedMem = (struct _RTL_CRITICAL_SECTION *)_DbgpOpenOrCreateSharedMem();
      v2 = SharedMem;
      if ( SharedMem )
      {
        EnterCriticalSection(SharedMem + 2);
        v3 = *(_QWORD *)v0;
        if ( *(struct _DBG_TRACE_CONTROL_BLOCK **)(*(_QWORD *)v0 + 8LL) != v0
          || (v4 = (struct _DBG_TRACE_CONTROL_BLOCK **)*((_QWORD *)v0 + 1), *v4 != v0) )
        {
          __fastfail(3u);
        }
        *v4 = (struct _DBG_TRACE_CONTROL_BLOCK *)v3;
        *(_QWORD *)(v3 + 8) = v4;
        --LODWORD(v2->SpinCount);
        LockSemaphore = v2[1].LockSemaphore;
        SpinCount = v2->SpinCount;
        if ( LockSemaphore == *((HANDLE *)v0 + 18) )
        {
          DeleteTimerQueueTimer(0, (HANDLE)v2[1].SpinCount, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
          v2[1].SpinCount = 0;
          v2[1].LockSemaphore = 0;
          DebugInfo = v2[1].DebugInfo;
          if ( DebugInfo != (PRTL_CRITICAL_SECTION_DEBUG)&v2[1] )
          {
            v8 = LODWORD(v2->SpinCount) + 6;
            HIDWORD(v2[1].OwningThread) = 10 * v8;
            v9 = *(void (__stdcall **)(PVOID, BOOLEAN))&DebugInfo[3].Type;
            v2[1].LockSemaphore = v9;
            if ( !CreateTimerQueueTimer((PHANDLE)&v2[1].SpinCount, 0, v9, v2, 10000 * v8, 10000 * v8, 0) )
              v2[1].LockSemaphore = 0;
          }
        }
        else if ( LockSemaphore )
        {
          OwningThread_high = HIDWORD(v2[1].OwningThread);
          if ( OwningThread_high > 10 * SpinCount + 120 )
          {
            v11 = (void *)v2[1].SpinCount;
            HIDWORD(v2[1].OwningThread) = 10 * SpinCount + 60;
            if ( !ChangeTimerQueueTimer(0, v11, 10000 * (SpinCount + 6), 10000 * (SpinCount + 6)) )
              HIDWORD(v2[1].OwningThread) = OwningThread_high;
          }
        }
        LeaveCriticalSection(v2 + 2);
        _DbgpDeleteTraceControl(v0);
        DigestGlobalTraceControlBlock = 0;
      }
    }
  }
}

```

## disassembly

```asm
0x180036874  push    rbx
0x180036876  push    rbp
0x180036877  push    rsi
0x180036878  push    rdi
0x180036879  sub     rsp, 48h
0x18003687d  mov     rax, gs:60h
0x180036886  test    byte ptr [rax+3], 2
0x18003688a  jnz     loc_1800369C4
0x180036890  mov     rdi, cs:DigestGlobalTraceControlBlock
0x180036897  test    rdi, rdi
0x18003689a  jz      loc_1800369C4
0x1800368a0  call    ?_DbgpOpenOrCreateSharedMem@@YAPEAU_DBG_TCB_HEADER@@XZ; _DbgpOpenOrCreateSharedMem(void)
0x1800368a5  mov     rbx, rax
0x1800368a8  test    rax, rax
0x1800368ab  jz      loc_1800369C4
0x1800368b1  lea     rcx, [rax+50h]; lpCriticalSection
0x1800368b5  call    cs:__imp_EnterCriticalSection
0x1800368bb  mov     rcx, [rdi]
0x1800368be  cmp     [rcx+8], rdi
0x1800368c2  jnz     loc_1800369CD
0x1800368c8  mov     rax, [rdi+8]
0x1800368cc  cmp     [rax], rdi
0x1800368cf  jnz     loc_1800369CD
0x1800368d5  mov     [rax], rcx
0x1800368d8  mov     [rcx+8], rax
0x1800368dc  dec     dword ptr [rbx+20h]
0x1800368df  mov     rax, [rbx+40h]
0x1800368e3  mov     ecx, [rbx+20h]
0x1800368e6  cmp     rax, [rdi+90h]
0x1800368ed  jnz     short loc_18003696C
0x1800368ef  lea     rsi, [rbx+48h]
0x1800368f3  or      r8, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x1800368f7  mov     rdx, [rsi]; Timer
0x1800368fa  xor     ecx, ecx; TimerQueue
0x1800368fc  call    cs:__imp_DeleteTimerQueueTimer
0x180036902  lea     rax, [rbx+28h]
0x180036906  mov     qword ptr [rsi], 0
0x18003690d  mov     qword ptr [rbx+40h], 0
0x180036915  mov     r8, [rax]
0x180036918  cmp     r8, rax
0x18003691b  jz      loc_1800369A7
0x180036921  mov     eax, [rbx+20h]
0x180036924  mov     r9, rbx; Parameter
0x180036927  add     eax, 6
0x18003692a  mov     [rsp+68h+Flags], 0; Flags
0x180036932  xor     edx, edx; TimerQueue
0x180036934  lea     ecx, [rax+rax*4]
0x180036937  add     ecx, ecx
0x180036939  imul    eax, ecx, 3E8h
0x18003693f  mov     [rbx+3Ch], ecx
0x180036942  mov     rcx, rsi; phNewTimer
0x180036945  mov     r8, [r8+90h]; Callback
0x18003694c  mov     [rbx+40h], r8
0x180036950  mov     [rsp+68h+Period], eax; Period
0x180036954  mov     [rsp+68h+DueTime], eax; DueTime
0x180036958  call    cs:__imp_CreateTimerQueueTimer
0x18003695e  test    eax, eax
0x180036960  jnz     short loc_1800369A7
0x180036962  mov     qword ptr [rbx+40h], 0
0x18003696a  jmp     short loc_1800369A7
0x18003696c  test    rax, rax
0x18003696f  jz      short loc_1800369A7
0x180036971  mov     esi, [rbx+3Ch]
0x180036974  lea     eax, [rcx+rcx*4]
0x180036977  lea     edx, [rax+rax]
0x18003697a  lea     eax, [rdx+78h]
0x18003697d  cmp     esi, eax
0x18003697f  jbe     short loc_1800369A7
0x180036981  lea     eax, [rdx+3Ch]
0x180036984  mov     rdx, [rbx+48h]; Timer
0x180036988  mov     [rbx+3Ch], eax
0x18003698b  lea     eax, [rcx+6]
0x18003698e  imul    r8d, eax, 2710h; DueTime
0x180036995  xor     ecx, ecx; TimerQueue
0x180036997  mov     r9d, r8d; Period
0x18003699a  call    cs:__imp_ChangeTimerQueueTimer
0x1800369a0  test    eax, eax
0x1800369a2  jnz     short loc_1800369A7
0x1800369a4  mov     [rbx+3Ch], esi
0x1800369a7  lea     rcx, [rbx+50h]; lpCriticalSection
0x1800369ab  call    cs:__imp_LeaveCriticalSection
0x1800369b1  mov     rcx, rdi; struct _DBG_TRACE_CONTROL_BLOCK *
0x1800369b4  call    ?_DbgpDeleteTraceControl@@YAXPEAU_DBG_TRACE_CONTROL_BLOCK@@@Z; _DbgpDeleteTraceControl(_DBG_TRACE_CONTROL_BLOCK *)
0x1800369b9  mov     cs:DigestGlobalTraceControlBlock, 0
0x1800369c4  add     rsp, 48h
0x1800369c8  pop     rdi
0x1800369c9  pop     rsi
0x1800369ca  pop     rbp
0x1800369cb  pop     rbx
0x1800369cc  retn
0x1800369cd  mov     ecx, 3
0x1800369d2  int     29h; Win8: RtlFailFast(ecx)
```
