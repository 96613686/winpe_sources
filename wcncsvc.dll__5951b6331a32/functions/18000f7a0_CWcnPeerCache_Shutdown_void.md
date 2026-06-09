# CWcnPeerCache::Shutdown(void)

- ea: `0x18000f7a0`
- end: `0x18000f8d5`
- name: `?Shutdown@CWcnPeerCache@@QEAAXXZ`
- size: `309`
- prototype: `void __fastcall(CWcnPeerCache *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180003b98`

## callees

- `0x180004fb8`
- `0x18000e5e0`
- `0x18000f7a0`
- `0x180053004`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000f82f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000f82f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000f83e`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000f83e`

## pseudocode

```c
void __fastcall CWcnPeerCache::Shutdown(CWcnPeerCache *this)
{
  _BYTE *v2; // r10
  const char *Indent; // rax
  __int64 v4; // r10
  const char *v5; // rax
  __int64 v6; // r10
  struct _TP_TIMER *v7; // rcx
  const char *v8; // rax
  __int64 v9; // r10
  const char *v10; // rax
  __int64 v11; // r10

  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
    {
      Indent = GetIndent(1);
      WPP_SF_s(*(_QWORD *)(v4 + 16), 97, WPP_f34e634574083547aa3a426270948a29_Traceguids, Indent);
      v2 = WPP_GLOBAL_Control;
    }
    if ( v2 != (_BYTE *)&WPP_GLOBAL_Control && v2[25] >= 6u )
    {
      v5 = GetIndent(1);
      WPP_SF_s(*(_QWORD *)(v6 + 16), 99, WPP_f34e634574083547aa3a426270948a29_Traceguids, v5);
    }
  }
  v7 = (struct _TP_TIMER *)*((_QWORD *)this + 14);
  if ( v7 )
  {
    SetThreadpoolTimer(v7, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(*((PTP_TIMER *)this + 14), 1);
    *((_BYTE *)this + 120) = 0;
  }
  CWcnPeerCache::CancelAllSessionsInner(this, 0);
  CWcnPeerCache::CancelAllSessionsInner(this, 1);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    v8 = GetIndent(-1);
    WPP_SF_s(*(_QWORD *)(v9 + 16), 100, WPP_f34e634574083547aa3a426270948a29_Traceguids, v8);
  }
  *((_QWORD *)this + 14) = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    v10 = GetIndent(-1);
    WPP_SF_s(*(_QWORD *)(v11 + 16), 98, WPP_f34e634574083547aa3a426270948a29_Traceguids, v10);
  }
}

```

## disassembly

```asm
0x18000f7a0  mov     [rsp+arg_0], rbx
0x18000f7a5  push    rsi
0x18000f7a6  sub     rsp, 20h
0x18000f7aa  mov     rbx, rcx
0x18000f7ad  mov     r10, cs:WPP_GLOBAL_Control
0x18000f7b4  lea     rsi, WPP_GLOBAL_Control
0x18000f7bb  cmp     r10, rsi
0x18000f7be  jz      short loc_18000F81E
0x18000f7c0  cmp     byte ptr [r10+19h], 6
0x18000f7c5  jb      short loc_18000F7F0
0x18000f7c7  mov     ecx, 1; int
0x18000f7cc  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18000f7d1  mov     rcx, [r10+10h]
0x18000f7d5  lea     r8, WPP_f34e634574083547aa3a426270948a29_Traceguids
0x18000f7dc  mov     edx, 61h ; 'a'
0x18000f7e1  mov     r9, rax
0x18000f7e4  call    WPP_SF_s
0x18000f7e9  mov     r10, cs:WPP_GLOBAL_Control
0x18000f7f0  cmp     r10, rsi
0x18000f7f3  jz      short loc_18000F81E
0x18000f7f5  cmp     byte ptr [r10+19h], 6
0x18000f7fa  jb      short loc_18000F81E
0x18000f7fc  mov     ecx, 1; int
0x18000f801  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18000f806  mov     rcx, [r10+10h]
0x18000f80a  lea     r8, WPP_f34e634574083547aa3a426270948a29_Traceguids
0x18000f811  mov     edx, 63h ; 'c'
0x18000f816  mov     r9, rax
0x18000f819  call    WPP_SF_s
0x18000f81e  mov     rcx, [rbx+70h]; pti
0x18000f822  test    rcx, rcx
0x18000f825  jz      short loc_18000F848
0x18000f827  xor     r9d, r9d; msWindowLength
0x18000f82a  xor     r8d, r8d; msPeriod
0x18000f82d  xor     edx, edx; pftDueTime
0x18000f82f  call    cs:__imp_SetThreadpoolTimer
0x18000f835  mov     rcx, [rbx+70h]; pti
0x18000f839  mov     edx, 1; fCancelPendingCallbacks
0x18000f83e  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000f844  mov     byte ptr [rbx+78h], 0
0x18000f848  xor     edx, edx; bool
0x18000f84a  mov     rcx, rbx; this
0x18000f84d  call    ?CancelAllSessionsInner@CWcnPeerCache@@AEAAX_N@Z; CWcnPeerCache::CancelAllSessionsInner(bool)
0x18000f852  mov     dl, 1; bool
0x18000f854  mov     rcx, rbx; this
0x18000f857  call    ?CancelAllSessionsInner@CWcnPeerCache@@AEAAX_N@Z; CWcnPeerCache::CancelAllSessionsInner(bool)
0x18000f85c  mov     r10, cs:WPP_GLOBAL_Control
0x18000f863  cmp     r10, rsi
0x18000f866  jz      short loc_18000F88F
0x18000f868  cmp     byte ptr [r10+19h], 6
0x18000f86d  jb      short loc_18000F88F
0x18000f86f  or      ecx, 0FFFFFFFFh; int
0x18000f872  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18000f877  mov     rcx, [r10+10h]
0x18000f87b  lea     r8, WPP_f34e634574083547aa3a426270948a29_Traceguids
0x18000f882  mov     edx, 64h ; 'd'
0x18000f887  mov     r9, rax
0x18000f88a  call    WPP_SF_s
0x18000f88f  mov     qword ptr [rbx+70h], 0
0x18000f897  mov     r10, cs:WPP_GLOBAL_Control
0x18000f89e  cmp     r10, rsi
0x18000f8a1  jz      short loc_18000F8CA
0x18000f8a3  cmp     byte ptr [r10+19h], 6
0x18000f8a8  jb      short loc_18000F8CA
0x18000f8aa  or      ecx, 0FFFFFFFFh; int
0x18000f8ad  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18000f8b2  mov     rcx, [r10+10h]
0x18000f8b6  lea     r8, WPP_f34e634574083547aa3a426270948a29_Traceguids
0x18000f8bd  mov     edx, 62h ; 'b'
0x18000f8c2  mov     r9, rax
0x18000f8c5  call    WPP_SF_s
0x18000f8ca  mov     rbx, [rsp+28h+arg_0]
0x18000f8cf  add     rsp, 20h
0x18000f8d3  pop     rsi
0x18000f8d4  retn
```
