# CTimerQueue::HrInitialize(void)

- ea: `0x18000cd48`
- end: `0x18000ce50`
- name: `?HrInitialize@CTimerQueue@@QEAAJXZ`
- size: `264`
- prototype: `__int64 __fastcall(CTimerQueue *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000c078`

## callees

- `0x18000683c`
- `0x18000cd48`
- `0x1800271fc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000cd8a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ce34`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000cd8a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ce34`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000cd62`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000cd62`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueue` at `0x18000cda8`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueue` at `0x18000cda8`

## pseudocode

```c
__int64 __fastcall CTimerQueue::HrInitialize(struct _RTL_CRITICAL_SECTION *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rbx
  unsigned int v4; // esi
  __int64 i; // rbp
  HANDLE TimerQueue; // rax
  __int64 v7; // r14
  unsigned int Win32Error; // eax

  v1 = this + 40;
  EnterCriticalSection(this + 40);
  if ( (int)++LODWORD(this[41].DebugInfo) <= 1 )
  {
    v4 = 0;
    for ( i = 0; i != 100; ++i )
    {
      TimerQueue = CreateTimerQueue();
      v7 = 2 * i;
      *((_QWORD *)&this->DebugInfo + 2 * i) = TimerQueue;
      if ( !TimerQueue )
      {
        Win32Error = HrFromLastWin32Error();
        v4 = Win32Error;
        if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 1) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_3ebb8ef5cef634d4e8096079a4452eca_Traceguids, Win32Error);
      }
      *((_WORD *)&this->LockCount + 4 * v7) = 0;
    }
    if ( v4 && WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_3ebb8ef5cef634d4e8096079a4452eca_Traceguids, v4);
    LeaveCriticalSection(v1);
    return v4;
  }
  else
  {
    LeaveCriticalSection(v1);
    return 0;
  }
}

```

## disassembly

```asm
0x18000cd48  push    rbx
0x18000cd4a  push    rbp
0x18000cd4b  push    rsi
0x18000cd4c  push    rdi
0x18000cd4d  push    r14
0x18000cd4f  push    r15
0x18000cd51  sub     rsp, 28h
0x18000cd55  lea     rbx, [rcx+640h]
0x18000cd5c  mov     rdi, rcx
0x18000cd5f  mov     rcx, rbx; lpCriticalSection
0x18000cd62  call    cs:__imp_EnterCriticalSection
0x18000cd69  nop     dword ptr [rax+rax+00h]
0x18000cd6e  mov     eax, [rdi+668h]
0x18000cd74  inc     eax
0x18000cd76  mov     [rdi+668h], eax
0x18000cd7c  mov     eax, [rdi+668h]
0x18000cd82  cmp     eax, 1
0x18000cd85  jle     short loc_18000CD9D
0x18000cd87  mov     rcx, rbx; lpCriticalSection
0x18000cd8a  call    cs:__imp_LeaveCriticalSection
0x18000cd91  nop     dword ptr [rax+rax+00h]
0x18000cd96  xor     eax, eax
0x18000cd98  jmp     loc_18000CE42
0x18000cd9d  xor     esi, esi
0x18000cd9f  lea     r15, WPP_GLOBAL_Control
0x18000cda6  xor     ebp, ebp
0x18000cda8  call    cs:__imp_CreateTimerQueue
0x18000cdaf  nop     dword ptr [rax+rax+00h]
0x18000cdb4  mov     r14, rbp
0x18000cdb7  add     r14, r14
0x18000cdba  mov     [rdi+r14*8], rax
0x18000cdbe  test    rax, rax
0x18000cdc1  jnz     short loc_18000CDF4
0x18000cdc3  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x18000cdc8  mov     esi, eax
0x18000cdca  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cdd1  cmp     rcx, r15
0x18000cdd4  jz      short loc_18000CDF4
0x18000cdd6  test    byte ptr [rcx+1Ch], 1
0x18000cdda  jz      short loc_18000CDF4
0x18000cddc  mov     rcx, [rcx+10h]
0x18000cde0  lea     r8, WPP_3ebb8ef5cef634d4e8096079a4452eca_Traceguids
0x18000cde7  mov     edx, 0Ah
0x18000cdec  mov     r9d, eax
0x18000cdef  call    WPP_SF_d
0x18000cdf4  xor     eax, eax
0x18000cdf6  inc     rbp
0x18000cdf9  mov     [rdi+r14*8+8], ax
0x18000cdff  cmp     rbp, 64h ; 'd'
0x18000ce03  jnz     short loc_18000CDA8
0x18000ce05  test    esi, esi
0x18000ce07  jz      short loc_18000CE31
0x18000ce09  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ce10  cmp     rcx, r15
0x18000ce13  jz      short loc_18000CE31
0x18000ce15  test    byte ptr [rcx+1Ch], 1
0x18000ce19  jz      short loc_18000CE31
0x18000ce1b  mov     rcx, [rcx+10h]
0x18000ce1f  lea     edx, [rax+0Bh]
0x18000ce22  mov     r9d, esi
0x18000ce25  lea     r8, WPP_3ebb8ef5cef634d4e8096079a4452eca_Traceguids
0x18000ce2c  call    WPP_SF_d
0x18000ce31  mov     rcx, rbx; lpCriticalSection
0x18000ce34  call    cs:__imp_LeaveCriticalSection
0x18000ce3b  nop     dword ptr [rax+rax+00h]
0x18000ce40  mov     eax, esi
0x18000ce42  add     rsp, 28h
0x18000ce46  pop     r15
0x18000ce48  pop     r14
0x18000ce4a  pop     rdi
0x18000ce4b  pop     rsi
0x18000ce4c  pop     rbp
0x18000ce4d  pop     rbx
0x18000ce4e  retn
```
