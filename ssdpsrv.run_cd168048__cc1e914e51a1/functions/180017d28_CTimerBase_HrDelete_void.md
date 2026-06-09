# CTimerBase::HrDelete(void *)

- ea: `0x180017d28`
- end: `0x180017e61`
- name: `?HrDelete@CTimerBase@@QEAAJPEAX@Z`
- size: `313`
- prototype: `int(CTimerBase *__hidden this, void *)`
- caller_count: `8`
- callee_count: `3`
- tags: ``

## callers

- `0x18000bd3c`
- `0x180014b40`
- `0x180016570`
- `0x18001784c`
- `0x180017ec0`
- `0x180017fd0`
- `0x180018020`
- `0x18001a920`

## callees

- `0x18000683c`
- `0x180017d28`
- `0x1800271fc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180017dc9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180017dd8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180017dc9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180017dd8`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180017dff`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180017dff`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180017d46`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180017d8c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180017d46`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180017d8c`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x180017d71`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x180017d71`

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
        --LOWORD(qword_180044C58[2 * *(__int16 *)p_SpinCount]);
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
0x180017d28  push    rbx
0x180017d2a  push    rbp
0x180017d2b  push    rsi
0x180017d2c  push    rdi
0x180017d2d  push    r14
0x180017d2f  sub     rsp, 20h
0x180017d33  lea     rbp, [rcx+28h]
0x180017d37  mov     rdi, rcx
0x180017d3a  xor     r14d, r14d
0x180017d3d  mov     rcx, rbp; lpCriticalSection
0x180017d40  mov     rsi, rdx
0x180017d43  mov     ebx, r14d
0x180017d46  call    cs:__imp_EnterCriticalSection
0x180017d4d  nop     dword ptr [rax+rax+00h]
0x180017d52  mov     rdx, [rdi+8]; Timer
0x180017d56  mov     dword ptr [rdi+50h], 1
0x180017d5d  mov     [rdi+8], r14
0x180017d61  test    rdx, rdx
0x180017d64  jz      loc_180017DF2
0x180017d6a  mov     rcx, [rdi+10h]; TimerQueue
0x180017d6e  mov     r8, rsi; CompletionEvent
0x180017d71  call    cs:__imp_DeleteTimerQueueTimer
0x180017d78  nop     dword ptr [rax+rax+00h]
0x180017d7d  test    eax, eax
0x180017d7f  jz      loc_180017E0D
0x180017d85  lea     rcx, CriticalSection; lpCriticalSection
0x180017d8c  call    cs:__imp_EnterCriticalSection
0x180017d93  nop     dword ptr [rax+rax+00h]
0x180017d98  add     rdi, 20h ; ' '
0x180017d9c  jz      short loc_180017DC2
0x180017d9e  cmp     [rdi], r14w
0x180017da2  jl      short loc_180017DC2
0x180017da4  movsx   rax, word ptr [rdi]
0x180017da8  lea     r8, qword_180044C58
0x180017daf  shl     rax, 4
0x180017db3  mov     edx, 0FFFFh
0x180017db8  add     [rax+r8], dx
0x180017dbd  mov     word ptr [rdi], 0FFFFh
0x180017dc2  lea     rcx, CriticalSection; lpCriticalSection
0x180017dc9  call    cs:__imp_LeaveCriticalSection
0x180017dd0  nop     dword ptr [rax+rax+00h]
0x180017dd5  mov     rcx, rbp; lpCriticalSection
0x180017dd8  call    cs:__imp_LeaveCriticalSection
0x180017ddf  nop     dword ptr [rax+rax+00h]
0x180017de4  mov     eax, ebx
0x180017de6  add     rsp, 20h
0x180017dea  pop     r14
0x180017dec  pop     rdi
0x180017ded  pop     rsi
0x180017dee  pop     rbp
0x180017def  pop     rbx
0x180017df0  retn
0x180017df2  lea     rdx, [rsi-1]
0x180017df6  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180017dfa  ja      short loc_180017DD5
0x180017dfc  mov     rcx, rsi; hEvent
0x180017dff  call    cs:__imp_SetEvent
0x180017e06  nop     dword ptr [rax+rax+00h]
0x180017e0b  jmp     short loc_180017DD5
0x180017e0d  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x180017e12  mov     ebx, eax
0x180017e14  cmp     eax, 800703E5h
0x180017e19  jnz     short loc_180017E23
0x180017e1b  mov     ebx, r14d
0x180017e1e  jmp     loc_180017D85
0x180017e23  test    ebx, ebx
0x180017e25  jz      loc_180017D85
0x180017e2b  mov     rcx, cs:WPP_GLOBAL_Control
0x180017e32  lea     rax, WPP_GLOBAL_Control
0x180017e39  cmp     rcx, rax
0x180017e3c  jz      short loc_180017DD5
0x180017e3e  test    byte ptr [rcx+1Ch], 1
0x180017e42  jz      short loc_180017DD5
0x180017e44  mov     rcx, [rcx+10h]
0x180017e48  lea     r8, WPP_3ebb8ef5cef634d4e8096079a4452eca_Traceguids
0x180017e4f  mov     edx, 14h
0x180017e54  mov     r9d, ebx
0x180017e57  call    WPP_SF_d
0x180017e5c  jmp     loc_180017DD5
```
