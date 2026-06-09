# CTimerBase::HrResetTimer(ulong)

- ea: `0x180007360`
- end: `0x180007706`
- name: `?HrResetTimer@CTimerBase@@QEAAJK@Z`
- size: `934`
- prototype: `__int64 __fastcall(char *Parameter, DWORD DueTime)`
- caller_count: `5`
- callee_count: `5`
- tags: ``

## callers

- `0x180005740`
- `0x180007bec`
- `0x18000c968`
- `0x180020fd8`
- `0x18002fcb8`

## callees

- `0x18000554c`
- `0x180007360`
- `0x18001afe4`
- `0x1800255a8`
- `0x180028000`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800073fa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007404`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800074db`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000752e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007679`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800073fa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007404`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800074db`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000752e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007679`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000737b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800073cd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007417`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007589`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000737b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800073cd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007417`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007589`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x18000750d`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x18000750d`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x1800073b4`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x1800073b4`

## pseudocode

```c
__int64 __fastcall CTimerBase::HrResetTimer(char *Parameter, DWORD DueTime)
{
  void *v4; // rdx
  __int16 *v5; // rsi
  __int64 v6; // rax
  unsigned int v7; // esi
  unsigned int Win32Error; // eax
  LPCSTR v9; // rcx
  bool v10; // zf
  __int64 v12; // rbp
  __int16 *v13; // r15
  __int16 v14; // cx
  __int16 v15; // r9
  __int16 i; // r8
  __int64 v17; // rdx
  __int64 v18; // rax
  void *v19; // rbp

  EnterCriticalSection((LPCRITICAL_SECTION)Parameter + 1);
  v4 = (void *)*((_QWORD *)Parameter + 1);
  *((_DWORD *)Parameter + 20) = 1;
  *((_QWORD *)Parameter + 1) = 0;
  if ( v4 )
  {
    if ( DeleteTimerQueueTimer(*((HANDLE *)Parameter + 2), v4, (HANDLE)0xFFFFFFFFFFFFFFFFLL)
      || (Win32Error = HrFromLastWin32Error(), Win32Error == -2147023899)
      || !Win32Error )
    {
      v5 = (__int16 *)(Parameter + 32);
      EnterCriticalSection(&CriticalSection);
      if ( Parameter != (char *)-32LL )
      {
        v6 = *v5;
        if ( (v6 & 0x8000u) == 0LL )
        {
          --LOWORD(CTimerQueue::s_instance[2 * v6 + 1]);
          *v5 = -1;
        }
      }
      LeaveCriticalSection(&CriticalSection);
    }
    else if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 1) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_3ebb8ef5cef634d4e8096079a4452eca_Traceguids, Win32Error);
    }
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)Parameter + 1);
  *((_DWORD *)Parameter + 20) = 0;
  v7 = -2147467259;
  EnterCriticalSection((LPCRITICAL_SECTION)Parameter + 1);
  if ( *((_DWORD *)Parameter + 20) )
  {
LABEL_8:
    if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_3ebb8ef5cef634d4e8096079a4452eca_Traceguids, v7);
    goto LABEL_22;
  }
  v12 = *((_QWORD *)Parameter + 3);
  v13 = (__int16 *)(Parameter + 32);
  EnterCriticalSection(&CriticalSection);
  if ( Parameter != (char *)-32LL )
  {
    v14 = word_180042650;
    v15 = 0;
    *v13 = -1;
    for ( i = 0; i < 100; ++i )
    {
      if ( !v7 )
        goto LABEL_39;
      v17 = CTimerQueue::s_instance[2 * v14];
      if ( v17 && v17 != v12 && LOWORD(CTimerQueue::s_instance[2 * v14 + 1]) != 10 )
      {
        v15 = v14;
        v7 = 0;
      }
      v14 = (__int16)(v14 + 1) % 100;
      word_180042650 = v14;
    }
    if ( !v7 )
    {
LABEL_39:
      v18 = 2LL * v15;
      v19 = (void *)CTimerQueue::s_instance[v18];
      *v13 = v15;
      ++LOWORD(CTimerQueue::s_instance[v18 + 1]);
      LeaveCriticalSection(&CriticalSection);
      *((_QWORD *)Parameter + 2) = v19;
      *((_QWORD *)Parameter + 3) = v19;
      if ( CreateTimerQueueTimer((PHANDLE)Parameter + 1, v19, CTimerBase::Callback, Parameter, DueTime, 0, 0) )
      {
        _InterlockedIncrement(&dword_1800414DC);
      }
      else
      {
        v7 = HrFromLastWin32Error();
        if ( v7 == -2147023899 )
        {
          v7 = 0;
          _InterlockedIncrement(&dword_1800414DC);
          goto LABEL_22;
        }
        if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 1) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_3ebb8ef5cef634d4e8096079a4452eca_Traceguids, v7);
        CTimerQueue::ReleaseHandle((CTimerQueue *)CTimerQueue::s_instance, (__int16 *)Parameter + 16);
      }
      v10 = v7 == 0;
      goto LABEL_21;
    }
    goto LABEL_32;
  }
  v7 = -2147467261;
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control )
  {
    if ( (WPP_GLOBAL_Control[28] & 1) == 0 )
      goto LABEL_33;
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_3ebb8ef5cef634d4e8096079a4452eca_Traceguids);
LABEL_32:
    v9 = WPP_GLOBAL_Control;
LABEL_33:
    if ( v9 != (LPCSTR)&WPP_GLOBAL_Control && (v9[28] & 1) != 0 )
      WPP_SF_d(*((_QWORD *)v9 + 2), 16, WPP_3ebb8ef5cef634d4e8096079a4452eca_Traceguids, v7);
  }
  LeaveCriticalSection(&CriticalSection);
  v10 = v7 == 0;
LABEL_21:
  if ( !v10 )
    goto LABEL_8;
LABEL_22:
  LeaveCriticalSection((LPCRITICAL_SECTION)Parameter + 1);
  if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 8) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_3ebb8ef5cef634d4e8096079a4452eca_Traceguids, v7);
  return v7;
}

```

## disassembly

```asm
0x180007360  push    rbx
0x180007362  push    rbp
0x180007363  push    rsi
0x180007364  push    rdi
0x180007365  push    r12
0x180007367  push    r13
0x180007369  push    r14
0x18000736b  push    r15
0x18000736d  sub     rsp, 48h
0x180007371  mov     rdi, rcx
0x180007374  mov     r12d, edx
0x180007377  add     rcx, 28h ; '('; lpCriticalSection
0x18000737b  call    cs:__imp_EnterCriticalSection
0x180007381  mov     rdx, [rdi+8]; Timer
0x180007385  lea     r15, ?s_instance@CTimerQueue@@0V1@A; CTimerQueue CTimerQueue::s_instance
0x18000738c  xor     r13d, r13d
0x18000738f  mov     dword ptr [rdi+50h], 1
0x180007396  mov     [rdi+8], r13
0x18000739a  mov     rbp, 0FFFFFFFFFFFFFFFFh
0x1800073a1  lea     rsi, WPP_GLOBAL_Control
0x1800073a8  test    rdx, rdx
0x1800073ab  jz      short loc_180007400
0x1800073ad  mov     rcx, [rdi+10h]; TimerQueue
0x1800073b1  mov     r8, rbp; CompletionEvent
0x1800073b4  call    cs:__imp_DeleteTimerQueueTimer
0x1800073ba  test    eax, eax
0x1800073bc  jz      loc_180007466
0x1800073c2  lea     rcx, CriticalSection; lpCriticalSection
0x1800073c9  lea     rsi, [rdi+20h]
0x1800073cd  call    cs:__imp_EnterCriticalSection
0x1800073d3  test    rsi, rsi
0x1800073d6  jz      short loc_1800073F3
0x1800073d8  movsx   rax, word ptr [rsi]
0x1800073dc  test    ax, ax
0x1800073df  js      short loc_1800073F3
0x1800073e1  shl     rax, 4
0x1800073e5  mov     ecx, 0FFFFh
0x1800073ea  add     [rax+r15+8], cx
0x1800073f0  mov     [rsi], bp
0x1800073f3  lea     rcx, CriticalSection; lpCriticalSection
0x1800073fa  call    cs:__imp_LeaveCriticalSection
0x180007400  lea     rcx, [rdi+28h]; lpCriticalSection
0x180007404  call    cs:__imp_LeaveCriticalSection
0x18000740a  lea     rcx, [rdi+28h]; lpCriticalSection
0x18000740e  mov     [rdi+50h], r13d
0x180007412  mov     esi, 80004005h
0x180007417  call    cs:__imp_EnterCriticalSection
0x18000741d  mov     eax, [rdi+50h]
0x180007420  test    eax, eax
0x180007422  jz      loc_18000757A
0x180007428  mov     rcx, cs:WPP_GLOBAL_Control
0x18000742f  lea     rax, WPP_GLOBAL_Control
0x180007436  cmp     rcx, rax
0x180007439  jz      loc_18000752A
0x18000743f  test    byte ptr [rcx+1Ch], 1
0x180007443  jz      loc_18000752A
0x180007449  mov     rcx, [rcx+10h]
0x18000744d  lea     r8, WPP_3ebb8ef5cef634d4e8096079a4452eca_Traceguids
0x180007454  mov     edx, 12h
0x180007459  mov     r9d, esi
0x18000745c  call    WPP_SF_d
0x180007461  jmp     loc_18000752A
0x180007466  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x18000746b  cmp     eax, 800703E5h
0x180007470  jz      loc_1800073C2
0x180007476  test    eax, eax
0x180007478  jz      loc_1800073C2
0x18000747e  mov     rcx, cs:WPP_GLOBAL_Control
0x180007485  cmp     rcx, rsi
0x180007488  jz      loc_180007400
0x18000748e  test    byte ptr [rcx+1Ch], 1
0x180007492  jz      loc_180007400
0x180007498  mov     rcx, [rcx+10h]
0x18000749c  lea     r8, WPP_3ebb8ef5cef634d4e8096079a4452eca_Traceguids
0x1800074a3  mov     edx, 14h
0x1800074a8  mov     r9d, eax
0x1800074ab  call    WPP_SF_d
0x1800074b0  jmp     loc_180007400
0x1800074b5  mov     rbp, r13
0x1800074b8  mov     esi, 80004003h
0x1800074bd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800074c4  lea     rax, WPP_GLOBAL_Control
0x1800074cb  cmp     rcx, rax
0x1800074ce  jnz     loc_180007684
0x1800074d4  lea     rcx, CriticalSection; lpCriticalSection
0x1800074db  call    cs:__imp_LeaveCriticalSection
0x1800074e1  test    esi, esi
0x1800074e3  js      short loc_180007524
0x1800074e5  mov     [rsp+88h+Flags], r13d; Flags
0x1800074ea  lea     r8, ?Callback@CTimerBase@@CAXPEAXE@Z; Callback
0x1800074f1  mov     [rsp+88h+Period], r13d; Period
0x1800074f6  lea     rcx, [rdi+8]; phNewTimer
0x1800074fa  mov     r9, rdi; Parameter
0x1800074fd  mov     [rsp+88h+DueTime], r12d; DueTime
0x180007502  mov     rdx, rbp; TimerQueue
0x180007505  mov     [rdi+10h], rbp
0x180007509  mov     [rdi+18h], rbp
0x18000750d  call    cs:__imp_CreateTimerQueueTimer
0x180007513  test    eax, eax
0x180007515  jz      loc_1800076A4
0x18000751b  lock inc cs:dword_1800414DC
0x180007522  test    esi, esi
0x180007524  jnz     loc_180007428
0x18000752a  lea     rcx, [rdi+28h]; lpCriticalSection
0x18000752e  call    cs:__imp_LeaveCriticalSection
0x180007534  mov     rcx, cs:WPP_GLOBAL_Control
0x18000753b  lea     rax, WPP_GLOBAL_Control
0x180007542  cmp     rcx, rax
0x180007545  jnz     short loc_18000755A
0x180007547  mov     eax, esi
0x180007549  add     rsp, 48h
0x18000754d  pop     r15
0x18000754f  pop     r14
0x180007551  pop     r13
0x180007553  pop     r12
0x180007555  pop     rdi
0x180007556  pop     rsi
0x180007557  pop     rbp
0x180007558  pop     rbx
0x180007559  retn
0x18000755a  test    byte ptr [rcx+1Ch], 8
0x18000755e  jz      short loc_180007547
0x180007560  mov     rcx, [rcx+10h]
0x180007564  lea     r8, WPP_3ebb8ef5cef634d4e8096079a4452eca_Traceguids
0x18000756b  mov     edx, 15h
0x180007570  mov     r9d, esi
0x180007573  call    WPP_SF_d
0x180007578  jmp     short loc_180007547
0x18000757a  mov     rbp, [rdi+18h]
0x18000757e  lea     rcx, CriticalSection; lpCriticalSection
0x180007585  lea     r15, [rdi+20h]
0x180007589  call    cs:__imp_EnterCriticalSection
0x18000758f  test    r15, r15
0x180007592  jz      loc_1800074B5
0x180007598  movzx   ecx, cs:word_180042650
0x18000759f  lea     r10, ?s_instance@CTimerQueue@@0V1@A; CTimerQueue CTimerQueue::s_instance
0x1800075a6  mov     r9d, r13d
0x1800075a9  mov     word ptr [r15], 0FFFFh
0x1800075af  mov     r8d, r13d
0x1800075b2  mov     r11d, 0Ah
0x1800075b8  test    esi, esi
0x1800075ba  jz      loc_18000765C
0x1800075c0  movsx   rax, cx
0x1800075c4  add     rax, rax
0x1800075c7  mov     rdx, [r10+rax*8]
0x1800075cb  test    rdx, rdx
0x1800075ce  jnz     short loc_180007643
0x1800075d0  inc     cx
0x1800075d3  mov     eax, 51EB851Fh
0x1800075d8  movsx   ecx, cx
0x1800075db  inc     r8w
0x1800075df  imul    ecx
0x1800075e1  sar     edx, 5
0x1800075e4  mov     eax, edx
0x1800075e6  shr     eax, 1Fh
0x1800075e9  add     edx, eax
0x1800075eb  imul    eax, edx, 64h ; 'd'
0x1800075ee  sub     ecx, eax
0x1800075f0  mov     cs:word_180042650, cx
0x1800075f7  cmp     r8w, 64h ; 'd'
0x1800075fc  jl      short loc_1800075B8
0x1800075fe  mov     rbp, r13
0x180007601  test    esi, esi
0x180007603  jz      short loc_18000765C
0x180007605  mov     rcx, cs:WPP_GLOBAL_Control
0x18000760c  lea     rax, WPP_GLOBAL_Control
0x180007613  cmp     rcx, rax
0x180007616  jz      loc_1800074D4
0x18000761c  test    byte ptr [rcx+1Ch], 1
0x180007620  jz      loc_1800074D4
0x180007626  mov     rcx, [rcx+10h]
0x18000762a  lea     r8, WPP_3ebb8ef5cef634d4e8096079a4452eca_Traceguids
0x180007631  mov     edx, 10h
0x180007636  mov     r9d, esi
0x180007639  call    WPP_SF_d
0x18000763e  jmp     loc_1800074D4
0x180007643  cmp     rdx, rbp
0x180007646  jz      short loc_1800075D0
0x180007648  cmp     r11w, [r10+rax*8+8]
0x18000764e  jz      short loc_1800075D0
0x180007650  movzx   r9d, cx
0x180007654  mov     esi, r13d
0x180007657  jmp     loc_1800075D0
0x18000765c  movsx   rax, r9w
0x180007660  lea     rcx, CriticalSection; lpCriticalSection
0x180007667  shl     rax, 4
0x18000766b  mov     rbp, [rax+r10]
0x18000766f  mov     [r15], r9w
0x180007673  inc     word ptr [rax+r10+8]
0x180007679  call    cs:__imp_LeaveCriticalSection
0x18000767f  jmp     loc_1800074E5
0x180007684  test    byte ptr [rcx+1Ch], 1
0x180007688  jz      short loc_180007613
0x18000768a  mov     rcx, [rcx+10h]
0x18000768e  lea     r8, WPP_3ebb8ef5cef634d4e8096079a4452eca_Traceguids
0x180007695  mov     edx, 0Fh
0x18000769a  call    WPP_SF_
0x18000769f  jmp     loc_180007605
0x1800076a4  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x1800076a9  mov     esi, eax
0x1800076ab  cmp     eax, 800703E5h
0x1800076b0  jnz     short loc_1800076C1
0x1800076b2  mov     esi, r13d
0x1800076b5  lock inc cs:dword_1800414DC
0x1800076bc  jmp     loc_18000752A
0x1800076c1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800076c8  lea     rax, WPP_GLOBAL_Control
0x1800076cf  cmp     rcx, rax
0x1800076d2  jz      short loc_1800076F2
0x1800076d4  test    byte ptr [rcx+1Ch], 1
0x1800076d8  jz      short loc_1800076F2
0x1800076da  mov     rcx, [rcx+10h]
0x1800076de  lea     r8, WPP_3ebb8ef5cef634d4e8096079a4452eca_Traceguids
0x1800076e5  mov     edx, 11h
0x1800076ea  mov     r9d, esi
0x1800076ed  call    WPP_SF_d
0x1800076f2  mov     rdx, r15; __int16 *
0x1800076f5  lea     rcx, ?s_instance@CTimerQueue@@0V1@A; this
0x1800076fc  call    ?ReleaseHandle@CTimerQueue@@QEAAXPEAF@Z; CTimerQueue::ReleaseHandle(short *)
0x180007701  jmp     loc_180007522
```
