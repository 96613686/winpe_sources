# CTimerBase::HrDelete(void *)

- ea: `0x180015720`
- end: `0x180015829`
- name: `?HrDelete@CTimerBase@@QEAAJPEAX@Z`
- size: `265`
- prototype: `__int64 __fastcall(struct _RTL_CRITICAL_SECTION *this, char *)`
- caller_count: `8`
- callee_count: `3`
- tags: ``

## callers

- `0x18000a590`
- `0x180013a70`
- `0x180014048`
- `0x18001528c`
- `0x18001587c`
- `0x180015980`
- `0x1800159d0`
- `0x1800196cc`

## callees

- `0x18000554c`
- `0x180015720`
- `0x1800255a8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800157a7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800157b0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800157a7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800157b0`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800157d0`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800157d0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001573e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180015770`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001573e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180015770`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x18001575f`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x18001575f`

## pseudocode

```c
__int64 __fastcall CTimerBase::HrDelete(struct _RTL_CRITICAL_SECTION *this, char *a2)
{
  struct _RTL_CRITICAL_SECTION *v2; // rbp
  unsigned int Win32Error; // ebx
  void *v6; // rdx
  ULONG_PTR *p_SpinCount; // rdi

  v2 = this + 1;
  Win32Error = 0;
  EnterCriticalSection(this + 1);
  v6 = *(void **)&this->LockCount;
  LODWORD(this[2].DebugInfo) = 1;
  *(_QWORD *)&this->LockCount = 0;
  if ( v6 )
  {
    if ( DeleteTimerQueueTimer(this->OwningThread, v6, a2) )
      goto LABEL_3;
    Win32Error = HrFromLastWin32Error();
    if ( Win32Error == -2147023899 )
    {
      Win32Error = 0;
      goto LABEL_3;
    }
    if ( !Win32Error )
    {
LABEL_3:
      EnterCriticalSection(&CriticalSection);
      p_SpinCount = &this->SpinCount;
      if ( p_SpinCount && *(__int16 *)p_SpinCount >= 0 )
      {
        --LOWORD(qword_180041B58[2 * *(__int16 *)p_SpinCount]);
        *(_WORD *)p_SpinCount = -1;
      }
      LeaveCriticalSection(&CriticalSection);
      goto LABEL_7;
    }
    if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_3ebb8ef5cef634d4e8096079a4452eca_Traceguids, Win32Error);
  }
  else if ( (unsigned __int64)(a2 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    SetEvent(a2);
  }
LABEL_7:
  LeaveCriticalSection(v2);
  return Win32Error;
}

```

## disassembly

```asm
0x180015720  push    rbx
0x180015722  push    rbp
0x180015723  push    rsi
0x180015724  push    rdi
0x180015725  push    r14
0x180015727  sub     rsp, 20h
0x18001572b  lea     rbp, [rcx+28h]
0x18001572f  mov     rdi, rcx
0x180015732  xor     r14d, r14d
0x180015735  mov     rcx, rbp; lpCriticalSection
0x180015738  mov     rsi, rdx
0x18001573b  mov     ebx, r14d
0x18001573e  call    cs:__imp_EnterCriticalSection
0x180015744  mov     rdx, [rdi+8]; Timer
0x180015748  mov     dword ptr [rdi+50h], 1
0x18001574f  mov     [rdi+8], r14
0x180015753  test    rdx, rdx
0x180015756  jz      short loc_1800157C3
0x180015758  mov     rcx, [rdi+10h]; TimerQueue
0x18001575c  mov     r8, rsi; CompletionEvent
0x18001575f  call    cs:__imp_DeleteTimerQueueTimer
0x180015765  test    eax, eax
0x180015767  jz      short loc_1800157D8
0x180015769  lea     rcx, CriticalSection; lpCriticalSection
0x180015770  call    cs:__imp_EnterCriticalSection
0x180015776  add     rdi, 20h ; ' '
0x18001577a  jz      short loc_1800157A0
0x18001577c  cmp     [rdi], r14w
0x180015780  jl      short loc_1800157A0
0x180015782  movsx   rax, word ptr [rdi]
0x180015786  lea     r8, qword_180041B58
0x18001578d  shl     rax, 4
0x180015791  mov     edx, 0FFFFh
0x180015796  add     [rax+r8], dx
0x18001579b  mov     word ptr [rdi], 0FFFFh
0x1800157a0  lea     rcx, CriticalSection; lpCriticalSection
0x1800157a7  call    cs:__imp_LeaveCriticalSection
0x1800157ad  mov     rcx, rbp; lpCriticalSection
0x1800157b0  call    cs:__imp_LeaveCriticalSection
0x1800157b6  mov     eax, ebx
0x1800157b8  add     rsp, 20h
0x1800157bc  pop     r14
0x1800157be  pop     rdi
0x1800157bf  pop     rsi
0x1800157c0  pop     rbp
0x1800157c1  pop     rbx
0x1800157c2  retn
0x1800157c3  lea     rdx, [rsi-1]
0x1800157c7  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x1800157cb  ja      short loc_1800157AD
0x1800157cd  mov     rcx, rsi; hEvent
0x1800157d0  call    cs:__imp_SetEvent
0x1800157d6  jmp     short loc_1800157AD
0x1800157d8  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x1800157dd  mov     ebx, eax
0x1800157df  cmp     eax, 800703E5h
0x1800157e4  jnz     short loc_1800157EE
0x1800157e6  mov     ebx, r14d
0x1800157e9  jmp     loc_180015769
0x1800157ee  test    ebx, ebx
0x1800157f0  jz      loc_180015769
0x1800157f6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800157fd  lea     rax, WPP_GLOBAL_Control
0x180015804  cmp     rcx, rax
0x180015807  jz      short loc_1800157AD
0x180015809  test    byte ptr [rcx+1Ch], 1
0x18001580d  jz      short loc_1800157AD
0x18001580f  mov     rcx, [rcx+10h]
0x180015813  lea     r8, WPP_3ebb8ef5cef634d4e8096079a4452eca_Traceguids
0x18001581a  mov     edx, 14h
0x18001581f  mov     r9d, ebx
0x180015822  call    WPP_SF_d
0x180015827  jmp     short loc_1800157AD
```
