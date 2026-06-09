# BoundSubscription::OnRetryComplete(void)

- ea: `0x18000ea28`
- end: `0x18000eaea`
- name: `?OnRetryComplete@BoundSubscription@@AEAAXXZ`
- size: `194`
- prototype: `void __fastcall(BoundSubscription *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000fc00`

## callees

- `0x18000c724`
- `0x18000ea28`
- `0x180011878`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ea41`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ea41`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000eae3`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x18000eab5`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x18000eab5`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall BoundSubscription::OnRetryComplete(BoundSubscription *this)
{
  struct _RTL_CRITICAL_SECTION *v2; // rdi
  _QWORD *v3; // r8
  _QWORD *v4; // r9

  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 16);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  if ( *((_DWORD *)this + 14) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      v3 = (_QWORD *)((char *)this + 72);
      if ( *((_QWORD *)this + 12) >= 8u )
        v3 = (_QWORD *)*v3;
      v4 = (_QWORD *)(*((_QWORD *)this + 8) + 56LL);
      if ( *(_QWORD *)(*((_QWORD *)this + 8) + 80LL) >= 8u )
        v4 = (_QWORD *)*v4;
      WPP_SF_SSq(*((_QWORD *)WPP_GLOBAL_Control + 2), 59, (_DWORD)v3, (_DWORD)v4, (__int64)v3, (char)this);
    }
    DeleteTimerQueueTimer(0, *((HANDLE *)this + 30), 0);
    *((_QWORD *)this + 30) = 0;
    *((_DWORD *)this + 14) = 0;
    BoundSubscription::EnterSubscribingState(this);
  }
  LeaveCriticalSection(v2);
}

```

## disassembly

```asm
0x18000ea28  mov     [rsp+arg_8], rbx
0x18000ea2d  push    rdi
0x18000ea2e  sub     rsp, 30h
0x18000ea32  mov     rbx, rcx
0x18000ea35  lea     rdi, [rcx+10h]
0x18000ea39  mov     [rsp+38h+arg_0], rdi
0x18000ea3e  mov     rcx, rdi; lpCriticalSection
0x18000ea41  call    cs:__imp_EnterCriticalSection
0x18000ea47  nop
0x18000ea48  cmp     dword ptr [rbx+38h], 0
0x18000ea4c  jz      loc_18000EAD6
0x18000ea52  lea     rax, WPP_GLOBAL_Control
0x18000ea59  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ea60  cmp     rcx, rax
0x18000ea63  jz      short loc_18000EAA9
0x18000ea65  test    byte ptr [rcx+1Ch], 10h
0x18000ea69  jz      short loc_18000EAA9
0x18000ea6b  cmp     byte ptr [rcx+19h], 5
0x18000ea6f  jb      short loc_18000EAA9
0x18000ea71  lea     r8, [rbx+48h]
0x18000ea75  cmp     qword ptr [r8+18h], 8
0x18000ea7a  jb      short loc_18000EA7F
0x18000ea7c  mov     r8, [r8]
0x18000ea7f  mov     r9, [rbx+40h]
0x18000ea83  add     r9, 38h ; '8'
0x18000ea87  cmp     qword ptr [r9+18h], 8
0x18000ea8c  jb      short loc_18000EA91
0x18000ea8e  mov     r9, [r9]
0x18000ea91  mov     edx, 3Bh ; ';'
0x18000ea96  mov     [rsp+38h+var_10], rbx
0x18000ea9b  mov     [rsp+38h+var_18], r8
0x18000eaa0  mov     rcx, [rcx+10h]
0x18000eaa4  call    WPP_SF_SSq
0x18000eaa9  xor     r8d, r8d; CompletionEvent
0x18000eaac  mov     rdx, [rbx+0F0h]; Timer
0x18000eab3  xor     ecx, ecx; TimerQueue
0x18000eab5  call    cs:__imp_DeleteTimerQueueTimer
0x18000eabb  mov     qword ptr [rbx+0F0h], 0
0x18000eac6  mov     dword ptr [rbx+38h], 0
0x18000eacd  mov     rcx, rbx; this
0x18000ead0  call    ?EnterSubscribingState@BoundSubscription@@AEAAXXZ; BoundSubscription::EnterSubscribingState(void)
0x18000ead5  nop
0x18000ead6  mov     rcx, rdi
0x18000ead9  mov     rbx, [rsp+38h+arg_8]
0x18000eade  add     rsp, 30h
0x18000eae2  pop     rdi
0x18000eae3  jmp     cs:__imp_LeaveCriticalSection
```
