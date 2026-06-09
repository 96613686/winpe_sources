# BoundSubscription::InternalDeactivate(bool)

- ea: `0x18000dda4`
- end: `0x18000df8f`
- name: `?InternalDeactivate@BoundSubscription@@QEAAX_N@Z`
- size: `491`
- prototype: `void __fastcall(BoundSubscription *this, unsigned __int8)`
- caller_count: `6`
- callee_count: `3`
- tags: ``

## callers

- `0x180008094`
- `0x18000b890`
- `0x18000e010`
- `0x180021a22`
- `0x180021ca5`
- `0x180021e97`

## callees

- `0x18000dda4`
- `0x1800103b8`
- `0x180011afc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000de3e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000dec2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000de3e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000dec2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000de8f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000de8f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000df88`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x18000deb9`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x18000deb9`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x18000dea5`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x18000dea5`
- `WsmSvc!WSManCloseSubscriptionHandle` at `0x18000df49`
- `WsmSvc!WSManCloseSubscriptionHandle` at `0x18000df49`
- `WsmSvc!WSManCloseEnumeratorHandle` at `0x18000df62`
- `WsmSvc!WSManCloseEnumeratorHandle` at `0x18000df62`
- `WsmSvc!WSManCloseSessionHandle` at `0x18000de57`
- `WsmSvc!WSManCloseSessionHandle` at `0x18000de57`

## pseudocode

```c
void __fastcall BoundSubscription::InternalDeactivate(BoundSubscription *this, unsigned __int8 a2)
{
  __int64 v2; // r15
  _QWORD *v4; // rdx
  _QWORD *v5; // rax
  void *v6; // r12
  void *v7; // rsi
  __int64 v8; // r15
  _QWORD *v9; // rsi
  const unsigned __int16 *v10; // r9
  const unsigned __int16 *v11; // rdx
  const unsigned __int16 *v12; // rcx
  __int64 v13; // rcx

  v2 = a2;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    v4 = (_QWORD *)((char *)this + 72);
    if ( *((_QWORD *)this + 12) >= 8u )
      v4 = (_QWORD *)*v4;
    v5 = (_QWORD *)(*((_QWORD *)this + 8) + 56LL);
    if ( *(_QWORD *)(*((_QWORD *)this + 8) + 80LL) >= 8u )
      v5 = (_QWORD *)*v5;
    WPP_SF_sdSSq(*((_QWORD *)WPP_GLOBAL_Control + 2), *((_DWORD *)this + 14), (__int64)v5, (__int64)v4, (char)this);
  }
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  *((_DWORD *)this + 14) = 0;
  if ( *((_QWORD *)this + 36) )
  {
    WSManCloseSessionHandle();
    *((_QWORD *)this + 36) = 0;
  }
  v6 = (void *)*((_QWORD *)this + 28);
  v7 = (void *)*((_QWORD *)this + 30);
  *((_QWORD *)this + 28) = 0;
  *((_QWORD *)this + 30) = 0;
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  v8 = v2 ^ 1;
  if ( v6 )
    UnregisterWaitEx(v6, (HANDLE)(v8 - 1));
  if ( v7 )
    DeleteTimerQueueTimer(0, v7, (HANDLE)(v8 - 1));
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  v9 = (_QWORD *)((char *)this + 296);
  if ( *((_QWORD *)this + 37) )
  {
    v10 = (const unsigned __int16 *)((char *)this + 184);
    if ( *((_QWORD *)this + 26) >= 8u )
      v10 = *(const unsigned __int16 **)v10;
    v11 = (const unsigned __int16 *)((char *)this + 72);
    if ( *((_QWORD *)this + 12) >= 8u )
      v11 = *(const unsigned __int16 **)v11;
    v12 = (const unsigned __int16 *)(*((_QWORD *)this + 8) + 56LL);
    if ( *(_QWORD *)(*((_QWORD *)this + 8) + 80LL) >= 8u )
      v12 = *(const unsigned __int16 **)v12;
    WriteSavedRunTimeStatus(v12, v11, *((_DWORD *)this + 45), v10, *((_QWORD *)this + 27), 0);
    WSManCloseSubscriptionHandle(*v9);
    *v9 = 0;
  }
  v13 = *((_QWORD *)this + 44);
  if ( v13 )
    WSManCloseEnumeratorHandle(v13);
  *(_OWORD *)((char *)this + 328) = 0;
  *(_OWORD *)((char *)this + 344) = 0;
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
}

```

## disassembly

```asm
0x18000dda4  mov     [rsp+arg_0], rcx
0x18000dda9  push    rbx
0x18000ddaa  push    rsi
0x18000ddab  push    r12
0x18000ddad  push    r14
0x18000ddaf  push    r15
0x18000ddb1  sub     rsp, 50h
0x18000ddb5  movzx   r15d, dl
0x18000ddb9  mov     rbx, rcx
0x18000ddbc  lea     rax, WPP_GLOBAL_Control
0x18000ddc3  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ddca  cmp     rcx, rax
0x18000ddcd  jz      short loc_18000DE2F
0x18000ddcf  test    byte ptr [rcx+1Ch], 10h
0x18000ddd3  jz      short loc_18000DE2F
0x18000ddd5  cmp     byte ptr [rcx+19h], 5
0x18000ddd9  jb      short loc_18000DE2F
0x18000dddb  lea     rdx, [rbx+48h]
0x18000dddf  cmp     qword ptr [rdx+18h], 8
0x18000dde4  jb      short loc_18000DDE9
0x18000dde6  mov     rdx, [rdx]
0x18000dde9  mov     rax, [rbx+40h]
0x18000dded  add     rax, 38h ; '8'
0x18000ddf1  cmp     qword ptr [rax+18h], 8
0x18000ddf6  jb      short loc_18000DDFB
0x18000ddf8  mov     rax, [rax]
0x18000ddfb  lea     r8, aFalse; "false"
0x18000de02  lea     r9, aTrue; "true"
0x18000de09  test    r15b, r15b
0x18000de0c  cmovz   r9, r8
0x18000de10  mov     qword ptr [rsp+78h+var_40], rbx; char
0x18000de15  mov     [rsp+78h+var_48], rdx; __int64
0x18000de1a  mov     qword ptr [rsp+78h+var_50], rax; __int64
0x18000de1f  mov     eax, [rbx+38h]
0x18000de22  mov     dword ptr [rsp+78h+var_58], eax; char
0x18000de26  mov     rcx, [rcx+10h]; LoggerHandle
0x18000de2a  call    WPP_SF_sdSSq
0x18000de2f  lea     r14, [rbx+10h]
0x18000de33  mov     [rsp+78h+arg_10], r14
0x18000de3b  mov     rcx, r14; lpCriticalSection
0x18000de3e  call    cs:__imp_EnterCriticalSection
0x18000de44  mov     dword ptr [rbx+38h], 0
0x18000de4b  mov     rcx, [rbx+120h]
0x18000de52  test    rcx, rcx
0x18000de55  jz      short loc_18000DE68
0x18000de57  call    cs:__imp_WSManCloseSessionHandle
0x18000de5d  mov     qword ptr [rbx+120h], 0
0x18000de68  mov     r12, [rbx+0E0h]
0x18000de6f  mov     rsi, [rbx+0F0h]
0x18000de76  mov     qword ptr [rbx+0E0h], 0
0x18000de81  mov     qword ptr [rbx+0F0h], 0
0x18000de8c  mov     rcx, r14; lpCriticalSection
0x18000de8f  call    cs:__imp_LeaveCriticalSection
0x18000de95  xor     r15, 1
0x18000de99  test    r12, r12
0x18000de9c  jz      short loc_18000DEAB
0x18000de9e  lea     rdx, [r15-1]; CompletionEvent
0x18000dea2  mov     rcx, r12; WaitHandle
0x18000dea5  call    cs:__imp_UnregisterWaitEx
0x18000deab  test    rsi, rsi
0x18000deae  jz      short loc_18000DEBF
0x18000deb0  lea     r8, [r15-1]; CompletionEvent
0x18000deb4  mov     rdx, rsi; Timer
0x18000deb7  xor     ecx, ecx; TimerQueue
0x18000deb9  call    cs:__imp_DeleteTimerQueueTimer
0x18000debf  mov     rcx, r14; lpCriticalSection
0x18000dec2  call    cs:__imp_EnterCriticalSection
0x18000dec8  lea     rsi, [rbx+128h]
0x18000decf  mov     [rsp+78h+arg_18], rsi
0x18000ded7  cmp     qword ptr [rsi], 0
0x18000dedb  jz      short loc_18000DF56
0x18000dedd  mov     r8, [rbx+0D8h]
0x18000dee4  lea     r9, [rbx+0B8h]
0x18000deeb  cmp     qword ptr [r9+18h], 8
0x18000def0  jb      short loc_18000DEF5
0x18000def2  mov     r9, [r9]; unsigned __int16 *
0x18000def5  lea     rdx, [rbx+48h]
0x18000def9  cmp     qword ptr [rdx+18h], 8
0x18000defe  jb      short loc_18000DF03
0x18000df00  mov     rdx, [rdx]; unsigned __int16 *
0x18000df03  mov     rcx, [rbx+40h]
0x18000df07  add     rcx, 38h ; '8'
0x18000df0b  cmp     qword ptr [rcx+18h], 8
0x18000df10  jb      short loc_18000DF15
0x18000df12  mov     rcx, [rcx]; unsigned __int16 *
0x18000df15  mov     [rsp+78h+var_50], 0; bool
0x18000df1a  mov     qword ptr [rsp+78h+var_58], r8; unsigned __int64
0x18000df1f  mov     r8d, [rbx+0B4h]; unsigned int
0x18000df26  call    ?WriteSavedRunTimeStatus@@YAXPEBG0K0_K_N@Z; WriteSavedRunTimeStatus(ushort const *,ushort const *,ulong,ushort const *,unsigned __int64,bool)
0x18000df2b  nop
0x18000df2c  jmp     short loc_18000DF46
0x18000df2e  mov     rbx, [rsp+78h+arg_0]
0x18000df36  mov     r14, [rsp+78h+arg_10]
0x18000df3e  mov     rsi, [rsp+78h+arg_18]
0x18000df46  mov     rcx, [rsi]
0x18000df49  call    cs:__imp_WSManCloseSubscriptionHandle
0x18000df4f  mov     qword ptr [rsi], 0
0x18000df56  mov     rcx, [rbx+160h]
0x18000df5d  test    rcx, rcx
0x18000df60  jz      short loc_18000DF68
0x18000df62  call    cs:__imp_WSManCloseEnumeratorHandle
0x18000df68  xorps   xmm0, xmm0
0x18000df6b  movups  xmmword ptr [rbx+148h], xmm0
0x18000df72  movups  xmmword ptr [rbx+158h], xmm0
0x18000df79  mov     rcx, r14
0x18000df7c  add     rsp, 50h
0x18000df80  pop     r15
0x18000df82  pop     r14
0x18000df84  pop     r12
0x18000df86  pop     rsi
0x18000df87  pop     rbx
0x18000df88  jmp     cs:__imp_LeaveCriticalSection
```
