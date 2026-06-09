# CTimerQueue::HrShutdown(void *)

- ea: `0x180033af8`
- end: `0x180033c37`
- name: `?HrShutdown@CTimerQueue@@QEAAJPEAX@Z`
- size: `319`
- prototype: `__int64 __fastcall(struct _RTL_CRITICAL_SECTION *this, void *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18002d870`

## callees

- `0x18000554c`
- `0x1800255a8`
- `0x180033af8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180033b5c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180033bf4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180033b5c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180033bf4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180033b12`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180033b12`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueEx` at `0x180033b9d`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueEx` at `0x180033b9d`

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
0x180033af8  push    rbx
0x180033afa  push    rbp
0x180033afb  push    rsi
0x180033afc  push    rdi
0x180033afd  push    r14
0x180033aff  push    r15
0x180033b01  sub     rsp, 28h
0x180033b05  lea     rbx, [rcx+640h]
0x180033b0c  mov     rdi, rcx
0x180033b0f  mov     rcx, rbx; lpCriticalSection
0x180033b12  call    cs:__imp_EnterCriticalSection
0x180033b18  mov     eax, [rdi+668h]
0x180033b1e  test    eax, eax
0x180033b20  jnz     short loc_180033B67
0x180033b22  mov     esi, 8000FFFFh
0x180033b27  mov     rcx, cs:WPP_GLOBAL_Control
0x180033b2e  lea     r15, WPP_GLOBAL_Control
0x180033b35  cmp     rcx, r15
0x180033b38  jz      short loc_180033B59
0x180033b3a  test    byte ptr [rcx+1Ch], 1
0x180033b3e  jz      short loc_180033B59
0x180033b40  mov     rcx, [rcx+10h]
0x180033b44  lea     edx, [rax+0Ch]
0x180033b47  mov     r9d, 8000FFFFh
0x180033b4d  lea     r8, WPP_3ebb8ef5cef634d4e8096079a4452eca_Traceguids
0x180033b54  call    WPP_SF_d
0x180033b59  mov     rcx, rbx; lpCriticalSection
0x180033b5c  call    cs:__imp_LeaveCriticalSection
0x180033b62  jmp     loc_180033BFE
0x180033b67  mov     eax, [rdi+668h]
0x180033b6d  lea     r15, WPP_GLOBAL_Control
0x180033b74  dec     eax
0x180033b76  xor     esi, esi
0x180033b78  mov     [rdi+668h], eax
0x180033b7e  mov     eax, [rdi+668h]
0x180033b84  test    eax, eax
0x180033b86  jnz     short loc_180033BF1
0x180033b88  xor     ebp, ebp
0x180033b8a  mov     r14, rbp
0x180033b8d  add     r14, r14
0x180033b90  mov     rcx, [rdi+r14*8]; TimerQueue
0x180033b94  test    rcx, rcx
0x180033b97  jz      short loc_180033BE8
0x180033b99  or      rdx, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x180033b9d  call    cs:__imp_DeleteTimerQueueEx
0x180033ba3  test    eax, eax
0x180033ba5  jnz     short loc_180033BD8
0x180033ba7  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x180033bac  mov     esi, eax
0x180033bae  mov     rcx, cs:WPP_GLOBAL_Control
0x180033bb5  cmp     rcx, r15
0x180033bb8  jz      short loc_180033BD8
0x180033bba  test    byte ptr [rcx+1Ch], 1
0x180033bbe  jz      short loc_180033BD8
0x180033bc0  mov     rcx, [rcx+10h]
0x180033bc4  lea     r8, WPP_3ebb8ef5cef634d4e8096079a4452eca_Traceguids
0x180033bcb  mov     edx, 0Dh
0x180033bd0  mov     r9d, eax
0x180033bd3  call    WPP_SF_d
0x180033bd8  xor     eax, eax
0x180033bda  mov     qword ptr [rdi+r14*8], 0
0x180033be2  mov     [rdi+r14*8+8], ax
0x180033be8  inc     rbp
0x180033beb  cmp     rbp, 64h ; 'd'
0x180033bef  jnz     short loc_180033B8A
0x180033bf1  mov     rcx, rbx; lpCriticalSection
0x180033bf4  call    cs:__imp_LeaveCriticalSection
0x180033bfa  test    esi, esi
0x180033bfc  jz      short loc_180033C28
0x180033bfe  mov     rcx, cs:WPP_GLOBAL_Control
0x180033c05  cmp     rcx, r15
0x180033c08  jz      short loc_180033C28
0x180033c0a  test    byte ptr [rcx+1Ch], 1
0x180033c0e  jz      short loc_180033C28
0x180033c10  mov     rcx, [rcx+10h]
0x180033c14  lea     r8, WPP_3ebb8ef5cef634d4e8096079a4452eca_Traceguids
0x180033c1b  mov     edx, 0Eh
0x180033c20  mov     r9d, esi
0x180033c23  call    WPP_SF_d
0x180033c28  mov     eax, esi
0x180033c2a  add     rsp, 28h
0x180033c2e  pop     r15
0x180033c30  pop     r14
0x180033c32  pop     rdi
0x180033c33  pop     rsi
0x180033c34  pop     rbp
0x180033c35  pop     rbx
0x180033c36  retn
```
