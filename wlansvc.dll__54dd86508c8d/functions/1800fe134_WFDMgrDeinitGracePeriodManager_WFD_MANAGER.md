# WFDMgrDeinitGracePeriodManager(_WFD_MANAGER *)

- ea: `0x1800fe134`
- end: `0x1800fe2ce`
- name: `?WFDMgrDeinitGracePeriodManager@@YAKPEAU_WFD_MANAGER@@@Z`
- size: `410`
- prototype: `unsigned int __fastcall(struct _WFD_MANAGER *)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x1800fa78c`
- `0x180187c78`

## callees

- `0x18000aa0c`
- `0x180011530`
- `0x1800fe134`
- `0x1800fe2d4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800fe241`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800fe28b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800fe241`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800fe28b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800fe206`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800fe263`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800fe206`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800fe263`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800fe251`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800fe251`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800fe25a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800fe25a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800fe22a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800fe22a`

## pseudocode

```c
__int64 __fastcall WFDMgrDeinitGracePeriodManager(struct _RTL_CRITICAL_SECTION *a1)
{
  PVOID *v2; // rcx
  unsigned int v3; // edi
  struct _TP_TIMER *v4; // rsi
  struct _TP_TIMER *SpinCount; // rcx
  struct _WFD_SESSION_GRACE_PERIOD_INFO **i; // rsi

  v2 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 1246, &WPP_770d2a6ca85f3f6f822445dd5e88f798_Traceguids);
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !a1 )
  {
    if ( v2 != &WPP_GLOBAL_Control && *((_BYTE *)v2 + 105) && (*((_BYTE *)v2 + 108) & 1) != 0 )
    {
      WPP_SF_(v2[12], 1247, &WPP_770d2a6ca85f3f6f822445dd5e88f798_Traceguids);
      v2 = (PVOID *)WPP_GLOBAL_Control;
    }
    v3 = 87;
    goto LABEL_25;
  }
  v3 = 0;
  if ( HIDWORD(a1[19].OwningThread) )
  {
    v4 = 0;
    EnterCriticalSection(a1 + 6);
    SpinCount = (struct _TP_TIMER *)a1[18].SpinCount;
    LODWORD(a1[19].OwningThread) = 1;
    if ( SpinCount )
    {
      SetThreadpoolTimer(SpinCount, 0, 0, 0);
      v4 = (struct _TP_TIMER *)a1[18].SpinCount;
      a1[18].SpinCount = 0;
    }
    LeaveCriticalSection(a1 + 6);
    if ( v4 )
    {
      WaitForThreadpoolTimerCallbacks(v4, 0);
      CloseThreadpoolTimer(v4);
    }
    EnterCriticalSection(a1 + 6);
    for ( i = (struct _WFD_SESSION_GRACE_PERIOD_INFO **)&a1[18].OwningThread;
          *i != (struct _WFD_SESSION_GRACE_PERIOD_INFO *)i;
          WFDMgrRemoveAndDestroyGracePeriodInfo((struct _WFD_MANAGER *)a1, *i) )
    {
      ;
    }
    HIDWORD(a1[19].OwningThread) = 0;
    LeaveCriticalSection(a1 + 6);
    goto LABEL_24;
  }
  if ( v2 == &WPP_GLOBAL_Control )
    return v3;
  if ( *((_BYTE *)v2 + 105) >= 3u && (*((_BYTE *)v2 + 108) & 1) != 0 )
  {
    WPP_SF_(v2[12], 1248, &WPP_770d2a6ca85f3f6f822445dd5e88f798_Traceguids);
LABEL_24:
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_25:
  if ( v2 != &WPP_GLOBAL_Control && *((_BYTE *)v2 + 105) >= 4u && (*((_BYTE *)v2 + 108) & 1) != 0 )
    WPP_SF_d(v2[12], 1249, &WPP_770d2a6ca85f3f6f822445dd5e88f798_Traceguids, v3);
  return v3;
}

```

## disassembly

```asm
0x1800fe134  push    rbx
0x1800fe136  push    rbp
0x1800fe137  push    rsi
0x1800fe138  push    rdi
0x1800fe139  push    r12
0x1800fe13b  sub     rsp, 20h
0x1800fe13f  mov     rbx, rcx
0x1800fe142  mov     rcx, cs:WPP_GLOBAL_Control
0x1800fe149  lea     r12, WPP_GLOBAL_Control
0x1800fe150  cmp     rcx, r12
0x1800fe153  jz      short loc_1800FE17D
0x1800fe155  cmp     byte ptr [rcx+69h], 4
0x1800fe159  jb      short loc_1800FE17D
0x1800fe15b  test    byte ptr [rcx+6Ch], 1
0x1800fe15f  jz      short loc_1800FE17D
0x1800fe161  mov     rcx, [rcx+60h]
0x1800fe165  lea     r8, WPP_770d2a6ca85f3f6f822445dd5e88f798_Traceguids
0x1800fe16c  mov     edx, 4DEh
0x1800fe171  call    WPP_SF_
0x1800fe176  mov     rcx, cs:WPP_GLOBAL_Control
0x1800fe17d  test    rbx, rbx
0x1800fe180  jnz     short loc_1800FE1B9
0x1800fe182  cmp     rcx, r12
0x1800fe185  jz      short loc_1800FE1AF
0x1800fe187  cmp     byte ptr [rcx+69h], 1
0x1800fe18b  jb      short loc_1800FE1AF
0x1800fe18d  test    byte ptr [rcx+6Ch], 1
0x1800fe191  jz      short loc_1800FE1AF
0x1800fe193  mov     rcx, [rcx+60h]
0x1800fe197  lea     r8, WPP_770d2a6ca85f3f6f822445dd5e88f798_Traceguids
0x1800fe19e  mov     edx, 4DFh
0x1800fe1a3  call    WPP_SF_
0x1800fe1a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800fe1af  mov     edi, 57h ; 'W'
0x1800fe1b4  jmp     loc_1800FE298
0x1800fe1b9  xor     edi, edi
0x1800fe1bb  cmp     [rbx+30Ch], edi
0x1800fe1c1  jnz     short loc_1800FE1FA
0x1800fe1c3  cmp     rcx, r12
0x1800fe1c6  jz      loc_1800FE2C1
0x1800fe1cc  cmp     byte ptr [rcx+69h], 3
0x1800fe1d0  jb      loc_1800FE298
0x1800fe1d6  test    byte ptr [rcx+6Ch], 1
0x1800fe1da  jz      loc_1800FE298
0x1800fe1e0  mov     rcx, [rcx+60h]
0x1800fe1e4  lea     r8, WPP_770d2a6ca85f3f6f822445dd5e88f798_Traceguids
0x1800fe1eb  mov     edx, 4E0h
0x1800fe1f0  call    WPP_SF_
0x1800fe1f5  jmp     loc_1800FE291
0x1800fe1fa  lea     rbp, [rbx+0F0h]
0x1800fe201  xor     esi, esi
0x1800fe203  mov     rcx, rbp; lpCriticalSection
0x1800fe206  call    cs:__imp_EnterCriticalSection
0x1800fe20c  mov     rcx, [rbx+2F0h]; pti
0x1800fe213  mov     dword ptr [rbx+308h], 1
0x1800fe21d  test    rcx, rcx
0x1800fe220  jz      short loc_1800FE23E
0x1800fe222  xor     r9d, r9d; msWindowLength
0x1800fe225  xor     r8d, r8d; msPeriod
0x1800fe228  xor     edx, edx; pftDueTime
0x1800fe22a  call    cs:__imp_SetThreadpoolTimer
0x1800fe230  mov     rsi, [rbx+2F0h]
0x1800fe237  mov     [rbx+2F0h], rdi
0x1800fe23e  mov     rcx, rbp; lpCriticalSection
0x1800fe241  call    cs:__imp_LeaveCriticalSection
0x1800fe247  test    rsi, rsi
0x1800fe24a  jz      short loc_1800FE260
0x1800fe24c  xor     edx, edx; fCancelPendingCallbacks
0x1800fe24e  mov     rcx, rsi; pti
0x1800fe251  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800fe257  mov     rcx, rsi; pti
0x1800fe25a  call    cs:__imp_CloseThreadpoolTimer
0x1800fe260  mov     rcx, rbp; lpCriticalSection
0x1800fe263  call    cs:__imp_EnterCriticalSection
0x1800fe269  lea     rsi, [rbx+2E0h]
0x1800fe270  cmp     [rsi], rsi
0x1800fe273  jz      short loc_1800FE282
0x1800fe275  mov     rdx, [rsi]; struct _WFD_SESSION_GRACE_PERIOD_INFO *
0x1800fe278  mov     rcx, rbx; struct _WFD_MANAGER *
0x1800fe27b  call    ?WFDMgrRemoveAndDestroyGracePeriodInfo@@YAKPEAU_WFD_MANAGER@@PEAU_WFD_SESSION_GRACE_PERIOD_INFO@@@Z; WFDMgrRemoveAndDestroyGracePeriodInfo(_WFD_MANAGER *,_WFD_SESSION_GRACE_PERIOD_INFO *)
0x1800fe280  jmp     short loc_1800FE270
0x1800fe282  mov     rcx, rbp; lpCriticalSection
0x1800fe285  mov     [rbx+30Ch], edi
0x1800fe28b  call    cs:__imp_LeaveCriticalSection
0x1800fe291  mov     rcx, cs:WPP_GLOBAL_Control
0x1800fe298  cmp     rcx, r12
0x1800fe29b  jz      short loc_1800FE2C1
0x1800fe29d  cmp     byte ptr [rcx+69h], 4
0x1800fe2a1  jb      short loc_1800FE2C1
0x1800fe2a3  test    byte ptr [rcx+6Ch], 1
0x1800fe2a7  jz      short loc_1800FE2C1
0x1800fe2a9  mov     rcx, [rcx+60h]
0x1800fe2ad  lea     r8, WPP_770d2a6ca85f3f6f822445dd5e88f798_Traceguids
0x1800fe2b4  mov     edx, 4E1h
0x1800fe2b9  mov     r9d, edi
0x1800fe2bc  call    WPP_SF_d
0x1800fe2c1  mov     eax, edi
0x1800fe2c3  add     rsp, 20h
0x1800fe2c7  pop     r12
0x1800fe2c9  pop     rdi
0x1800fe2ca  pop     rsi
0x1800fe2cb  pop     rbp
0x1800fe2cc  pop     rbx
0x1800fe2cd  retn
```
