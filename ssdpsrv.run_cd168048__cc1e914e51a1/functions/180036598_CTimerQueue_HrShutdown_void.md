# CTimerQueue::HrShutdown(void *)

- ea: `0x180036598`
- end: `0x1800366f0`
- name: `?HrShutdown@CTimerQueue@@QEAAJPEAX@Z`
- size: `344`
- prototype: `__int64 __fastcall(CTimerQueue *__hidden this, void *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18002f900`

## callees

- `0x18000683c`
- `0x1800271fc`
- `0x180036598`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180036602`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800366a6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180036602`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800366a6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800365b2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800365b2`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueEx` at `0x180036649`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueEx` at `0x180036649`

## pseudocode

```c
__int64 __fastcall CTimerQueue::HrShutdown(struct _RTL_CRITICAL_SECTION *this, void *a2)
{
  struct _RTL_CRITICAL_SECTION *v2; // rbx
  unsigned int v4; // esi
  __int64 i; // rbp
  void *v6; // rcx
  unsigned int Win32Error; // eax

  v2 = this + 40;
  EnterCriticalSection(this + 40);
  if ( !LODWORD(this[41].DebugInfo) )
  {
    v4 = -2147418113;
    if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_3ebb8ef5cef634d4e8096079a4452eca_Traceguids, 2147549183LL);
    LeaveCriticalSection(v2);
LABEL_16:
    if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_3ebb8ef5cef634d4e8096079a4452eca_Traceguids, v4);
    return v4;
  }
  v4 = 0;
  if ( !--LODWORD(this[41].DebugInfo) )
  {
    for ( i = 0; i != 100; ++i )
    {
      v6 = (void *)*((_QWORD *)&this->DebugInfo + 2 * i);
      if ( v6 )
      {
        if ( !DeleteTimerQueueEx(v6, (HANDLE)0xFFFFFFFFFFFFFFFFLL) )
        {
          Win32Error = HrFromLastWin32Error();
          v4 = Win32Error;
          if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 1) != 0 )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              13,
              WPP_3ebb8ef5cef634d4e8096079a4452eca_Traceguids,
              Win32Error);
        }
        *((_QWORD *)&this->DebugInfo + 2 * i) = 0;
        *((_WORD *)&this->LockCount + 8 * i) = 0;
      }
    }
  }
  LeaveCriticalSection(v2);
  if ( v4 )
    goto LABEL_16;
  return v4;
}

```

## disassembly

```asm
0x180036598  push    rbx
0x18003659a  push    rbp
0x18003659b  push    rsi
0x18003659c  push    rdi
0x18003659d  push    r14
0x18003659f  push    r15
0x1800365a1  sub     rsp, 28h
0x1800365a5  lea     rbx, [rcx+640h]
0x1800365ac  mov     rdi, rcx
0x1800365af  mov     rcx, rbx; lpCriticalSection
0x1800365b2  call    cs:__imp_EnterCriticalSection
0x1800365b9  nop     dword ptr [rax+rax+00h]
0x1800365be  mov     eax, [rdi+668h]
0x1800365c4  test    eax, eax
0x1800365c6  jnz     short loc_180036613
0x1800365c8  mov     esi, 8000FFFFh
0x1800365cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800365d4  lea     r15, WPP_GLOBAL_Control
0x1800365db  cmp     rcx, r15
0x1800365de  jz      short loc_1800365FF
0x1800365e0  test    byte ptr [rcx+1Ch], 1
0x1800365e4  jz      short loc_1800365FF
0x1800365e6  mov     rcx, [rcx+10h]
0x1800365ea  lea     edx, [rax+0Ch]
0x1800365ed  mov     r9d, 8000FFFFh
0x1800365f3  lea     r8, WPP_3ebb8ef5cef634d4e8096079a4452eca_Traceguids
0x1800365fa  call    WPP_SF_d
0x1800365ff  mov     rcx, rbx; lpCriticalSection
0x180036602  call    cs:__imp_LeaveCriticalSection
0x180036609  nop     dword ptr [rax+rax+00h]
0x18003660e  jmp     loc_1800366B6
0x180036613  mov     eax, [rdi+668h]
0x180036619  lea     r15, WPP_GLOBAL_Control
0x180036620  dec     eax
0x180036622  xor     esi, esi
0x180036624  mov     [rdi+668h], eax
0x18003662a  mov     eax, [rdi+668h]
0x180036630  test    eax, eax
0x180036632  jnz     short loc_1800366A3
0x180036634  xor     ebp, ebp
0x180036636  mov     r14, rbp
0x180036639  add     r14, r14
0x18003663c  mov     rcx, [rdi+r14*8]; TimerQueue
0x180036640  test    rcx, rcx
0x180036643  jz      short loc_18003669A
0x180036645  or      rdx, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x180036649  call    cs:__imp_DeleteTimerQueueEx
0x180036650  nop     dword ptr [rax+rax+00h]
0x180036655  test    eax, eax
0x180036657  jnz     short loc_18003668A
0x180036659  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x18003665e  mov     esi, eax
0x180036660  mov     rcx, cs:WPP_GLOBAL_Control
0x180036667  cmp     rcx, r15
0x18003666a  jz      short loc_18003668A
0x18003666c  test    byte ptr [rcx+1Ch], 1
0x180036670  jz      short loc_18003668A
0x180036672  mov     rcx, [rcx+10h]
0x180036676  lea     r8, WPP_3ebb8ef5cef634d4e8096079a4452eca_Traceguids
0x18003667d  mov     edx, 0Dh
0x180036682  mov     r9d, eax
0x180036685  call    WPP_SF_d
0x18003668a  xor     eax, eax
0x18003668c  mov     qword ptr [rdi+r14*8], 0
0x180036694  mov     [rdi+r14*8+8], ax
0x18003669a  inc     rbp
0x18003669d  cmp     rbp, 64h ; 'd'
0x1800366a1  jnz     short loc_180036636
0x1800366a3  mov     rcx, rbx; lpCriticalSection
0x1800366a6  call    cs:__imp_LeaveCriticalSection
0x1800366ad  nop     dword ptr [rax+rax+00h]
0x1800366b2  test    esi, esi
0x1800366b4  jz      short loc_1800366E0
0x1800366b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800366bd  cmp     rcx, r15
0x1800366c0  jz      short loc_1800366E0
0x1800366c2  test    byte ptr [rcx+1Ch], 1
0x1800366c6  jz      short loc_1800366E0
0x1800366c8  mov     rcx, [rcx+10h]
0x1800366cc  lea     r8, WPP_3ebb8ef5cef634d4e8096079a4452eca_Traceguids
0x1800366d3  mov     edx, 0Eh
0x1800366d8  mov     r9d, esi
0x1800366db  call    WPP_SF_d
0x1800366e0  mov     eax, esi
0x1800366e2  add     rsp, 28h
0x1800366e6  pop     r15
0x1800366e8  pop     r14
0x1800366ea  pop     rdi
0x1800366eb  pop     rsi
0x1800366ec  pop     rbp
0x1800366ed  pop     rbx
0x1800366ee  retn
```
