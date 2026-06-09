# CTimerBase::HrResetTimer(ulong)

- ea: `0x180008800`
- end: `0x180008be9`
- name: `?HrResetTimer@CTimerBase@@QEAAJK@Z`
- size: `1001`
- prototype: `__int64 __fastcall(PVOID Parameter, DWORD DueTime)`
- caller_count: `5`
- callee_count: `5`
- tags: ``

## callers

- `0x180006a60`
- `0x18000962c`
- `0x1800228dc`
- `0x180023eb8`
- `0x180031fbc`

## callees

- `0x18000683c`
- `0x180008800`
- `0x18001c3b0`
- `0x1800271fc`
- `0x180029df0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800088ac`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800088bc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000899f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800089fe`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008b56`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800088ac`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800088bc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000899f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800089fe`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008b56`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000881b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008879`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800088d5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008a60`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000881b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008879`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800088d5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008a60`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x1800089d7`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x1800089d7`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x18000885a`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x18000885a`

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
    v14 = word_180045738;
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
      word_180045738 = v14;
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
        _InterlockedIncrement(&dword_1800445DC);
      }
      else
      {
        v7 = HrFromLastWin32Error();
        if ( v7 == -2147023899 )
        {
          v7 = 0;
          _InterlockedIncrement(&dword_1800445DC);
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
0x180008800  push    rbx
0x180008802  push    rbp
0x180008803  push    rsi
0x180008804  push    rdi
0x180008805  push    r12
0x180008807  push    r13
0x180008809  push    r14
0x18000880b  push    r15
0x18000880d  sub     rsp, 48h
0x180008811  mov     rdi, rcx
0x180008814  mov     r12d, edx
0x180008817  add     rcx, 28h ; '('; lpCriticalSection
0x18000881b  call    cs:__imp_EnterCriticalSection
0x180008822  nop     dword ptr [rax+rax+00h]
0x180008827  mov     rdx, [rdi+8]; Timer
0x18000882b  lea     r15, ?s_instance@CTimerQueue@@0V1@A; CTimerQueue CTimerQueue::s_instance
0x180008832  xor     r13d, r13d
0x180008835  mov     dword ptr [rdi+50h], 1
0x18000883c  mov     [rdi+8], r13
0x180008840  mov     rbp, 0FFFFFFFFFFFFFFFFh
0x180008847  lea     rsi, WPP_GLOBAL_Control
0x18000884e  test    rdx, rdx
0x180008851  jz      short loc_1800088B8
0x180008853  mov     rcx, [rdi+10h]; TimerQueue
0x180008857  mov     r8, rbp; CompletionEvent
0x18000885a  call    cs:__imp_DeleteTimerQueueTimer
0x180008861  nop     dword ptr [rax+rax+00h]
0x180008866  test    eax, eax
0x180008868  jz      loc_18000892A
0x18000886e  lea     rcx, CriticalSection; lpCriticalSection
0x180008875  lea     rsi, [rdi+20h]
0x180008879  call    cs:__imp_EnterCriticalSection
0x180008880  nop     dword ptr [rax+rax+00h]
0x180008885  test    rsi, rsi
0x180008888  jz      short loc_1800088A5
0x18000888a  movsx   rax, word ptr [rsi]
0x18000888e  test    ax, ax
0x180008891  js      short loc_1800088A5
0x180008893  shl     rax, 4
0x180008897  mov     ecx, 0FFFFh
0x18000889c  add     [rax+r15+8], cx
0x1800088a2  mov     [rsi], bp
0x1800088a5  lea     rcx, CriticalSection; lpCriticalSection
0x1800088ac  call    cs:__imp_LeaveCriticalSection
0x1800088b3  nop     dword ptr [rax+rax+00h]
0x1800088b8  lea     rcx, [rdi+28h]; lpCriticalSection
0x1800088bc  call    cs:__imp_LeaveCriticalSection
0x1800088c3  nop     dword ptr [rax+rax+00h]
0x1800088c8  lea     rcx, [rdi+28h]; lpCriticalSection
0x1800088cc  mov     [rdi+50h], r13d
0x1800088d0  mov     esi, 80004005h
0x1800088d5  call    cs:__imp_EnterCriticalSection
0x1800088dc  nop     dword ptr [rax+rax+00h]
0x1800088e1  mov     eax, [rdi+50h]
0x1800088e4  test    eax, eax
0x1800088e6  jz      loc_180008A51
0x1800088ec  mov     rcx, cs:WPP_GLOBAL_Control
0x1800088f3  lea     rax, WPP_GLOBAL_Control
0x1800088fa  cmp     rcx, rax
0x1800088fd  jz      loc_1800089FA
0x180008903  test    byte ptr [rcx+1Ch], 1
0x180008907  jz      loc_1800089FA
0x18000890d  mov     rcx, [rcx+10h]
0x180008911  lea     r8, WPP_3ebb8ef5cef634d4e8096079a4452eca_Traceguids
0x180008918  mov     edx, 12h
0x18000891d  mov     r9d, esi
0x180008920  call    WPP_SF_d
0x180008925  jmp     loc_1800089FA
0x18000892a  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x18000892f  cmp     eax, 800703E5h
0x180008934  jz      loc_18000886E
0x18000893a  test    eax, eax
0x18000893c  jz      loc_18000886E
0x180008942  mov     rcx, cs:WPP_GLOBAL_Control
0x180008949  cmp     rcx, rsi
0x18000894c  jz      loc_1800088B8
0x180008952  test    byte ptr [rcx+1Ch], 1
0x180008956  jz      loc_1800088B8
0x18000895c  mov     rcx, [rcx+10h]
0x180008960  lea     r8, WPP_3ebb8ef5cef634d4e8096079a4452eca_Traceguids
0x180008967  mov     edx, 14h
0x18000896c  mov     r9d, eax
0x18000896f  call    WPP_SF_d
0x180008974  jmp     loc_1800088B8
0x180008979  mov     rbp, r13
0x18000897c  mov     esi, 80004003h
0x180008981  mov     rcx, cs:WPP_GLOBAL_Control
0x180008988  lea     rax, WPP_GLOBAL_Control
0x18000898f  cmp     rcx, rax
0x180008992  jnz     loc_180008B67
0x180008998  lea     rcx, CriticalSection; lpCriticalSection
0x18000899f  call    cs:__imp_LeaveCriticalSection
0x1800089a6  nop     dword ptr [rax+rax+00h]
0x1800089ab  test    esi, esi
0x1800089ad  js      short loc_1800089F4
0x1800089af  mov     [rsp+88h+Flags], r13d; Flags
0x1800089b4  lea     r8, ?Callback@CTimerBase@@CAXPEAXE@Z; Callback
0x1800089bb  mov     [rsp+88h+Period], r13d; Period
0x1800089c0  lea     rcx, [rdi+8]; phNewTimer
0x1800089c4  mov     r9, rdi; Parameter
0x1800089c7  mov     [rsp+88h+DueTime], r12d; DueTime
0x1800089cc  mov     rdx, rbp; TimerQueue
0x1800089cf  mov     [rdi+10h], rbp
0x1800089d3  mov     [rdi+18h], rbp
0x1800089d7  call    cs:__imp_CreateTimerQueueTimer
0x1800089de  nop     dword ptr [rax+rax+00h]
0x1800089e3  test    eax, eax
0x1800089e5  jz      loc_180008B87
0x1800089eb  lock inc cs:dword_1800445DC
0x1800089f2  test    esi, esi
0x1800089f4  jnz     loc_1800088EC
0x1800089fa  lea     rcx, [rdi+28h]; lpCriticalSection
0x1800089fe  call    cs:__imp_LeaveCriticalSection
0x180008a05  nop     dword ptr [rax+rax+00h]
0x180008a0a  mov     rcx, cs:WPP_GLOBAL_Control
0x180008a11  lea     rax, WPP_GLOBAL_Control
0x180008a18  cmp     rcx, rax
0x180008a1b  jnz     short loc_180008A31
0x180008a1d  mov     eax, esi
0x180008a1f  add     rsp, 48h
0x180008a23  pop     r15
0x180008a25  pop     r14
0x180008a27  pop     r13
0x180008a29  pop     r12
0x180008a2b  pop     rdi
0x180008a2c  pop     rsi
0x180008a2d  pop     rbp
0x180008a2e  pop     rbx
0x180008a2f  retn
0x180008a31  test    byte ptr [rcx+1Ch], 8
0x180008a35  jz      short loc_180008A1D
0x180008a37  mov     rcx, [rcx+10h]
0x180008a3b  lea     r8, WPP_3ebb8ef5cef634d4e8096079a4452eca_Traceguids
0x180008a42  mov     edx, 15h
0x180008a47  mov     r9d, esi
0x180008a4a  call    WPP_SF_d
0x180008a4f  jmp     short loc_180008A1D
0x180008a51  mov     rbp, [rdi+18h]
0x180008a55  lea     rcx, CriticalSection; lpCriticalSection
0x180008a5c  lea     r15, [rdi+20h]
0x180008a60  call    cs:__imp_EnterCriticalSection
0x180008a67  nop     dword ptr [rax+rax+00h]
0x180008a6c  test    r15, r15
0x180008a6f  jz      loc_180008979
0x180008a75  movzx   ecx, cs:word_180045738
0x180008a7c  lea     r10, ?s_instance@CTimerQueue@@0V1@A; CTimerQueue CTimerQueue::s_instance
0x180008a83  mov     r9d, r13d
0x180008a86  mov     word ptr [r15], 0FFFFh
0x180008a8c  mov     r8d, r13d
0x180008a8f  mov     r11d, 0Ah
0x180008a95  test    esi, esi
0x180008a97  jz      loc_180008B39
0x180008a9d  movsx   rax, cx
0x180008aa1  add     rax, rax
0x180008aa4  mov     rdx, [r10+rax*8]
0x180008aa8  test    rdx, rdx
0x180008aab  jnz     short loc_180008B20
0x180008aad  inc     cx
0x180008ab0  mov     eax, 51EB851Fh
0x180008ab5  movsx   ecx, cx
0x180008ab8  inc     r8w
0x180008abc  imul    ecx
0x180008abe  sar     edx, 5
0x180008ac1  mov     eax, edx
0x180008ac3  shr     eax, 1Fh
0x180008ac6  add     edx, eax
0x180008ac8  imul    eax, edx, 64h ; 'd'
0x180008acb  sub     ecx, eax
0x180008acd  mov     cs:word_180045738, cx
0x180008ad4  cmp     r8w, 64h ; 'd'
0x180008ad9  jl      short loc_180008A95
0x180008adb  mov     rbp, r13
0x180008ade  test    esi, esi
0x180008ae0  jz      short loc_180008B39
0x180008ae2  mov     rcx, cs:WPP_GLOBAL_Control
0x180008ae9  lea     rax, WPP_GLOBAL_Control
0x180008af0  cmp     rcx, rax
0x180008af3  jz      loc_180008998
0x180008af9  test    byte ptr [rcx+1Ch], 1
0x180008afd  jz      loc_180008998
0x180008b03  mov     rcx, [rcx+10h]
0x180008b07  lea     r8, WPP_3ebb8ef5cef634d4e8096079a4452eca_Traceguids
0x180008b0e  mov     edx, 10h
0x180008b13  mov     r9d, esi
0x180008b16  call    WPP_SF_d
0x180008b1b  jmp     loc_180008998
0x180008b20  cmp     rdx, rbp
0x180008b23  jz      short loc_180008AAD
0x180008b25  cmp     r11w, [r10+rax*8+8]
0x180008b2b  jz      short loc_180008AAD
0x180008b2d  movzx   r9d, cx
0x180008b31  mov     esi, r13d
0x180008b34  jmp     loc_180008AAD
0x180008b39  movsx   rax, r9w
0x180008b3d  lea     rcx, CriticalSection; lpCriticalSection
0x180008b44  shl     rax, 4
0x180008b48  mov     rbp, [rax+r10]
0x180008b4c  mov     [r15], r9w
0x180008b50  inc     word ptr [rax+r10+8]
0x180008b56  call    cs:__imp_LeaveCriticalSection
0x180008b5d  nop     dword ptr [rax+rax+00h]
0x180008b62  jmp     loc_1800089AF
0x180008b67  test    byte ptr [rcx+1Ch], 1
0x180008b6b  jz      short loc_180008AF0
0x180008b6d  mov     rcx, [rcx+10h]
0x180008b71  lea     r8, WPP_3ebb8ef5cef634d4e8096079a4452eca_Traceguids
0x180008b78  mov     edx, 0Fh
0x180008b7d  call    WPP_SF_
0x180008b82  jmp     loc_180008AE2
0x180008b87  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x180008b8c  mov     esi, eax
0x180008b8e  cmp     eax, 800703E5h
0x180008b93  jnz     short loc_180008BA4
0x180008b95  mov     esi, r13d
0x180008b98  lock inc cs:dword_1800445DC
0x180008b9f  jmp     loc_1800089FA
0x180008ba4  mov     rcx, cs:WPP_GLOBAL_Control
0x180008bab  lea     rax, WPP_GLOBAL_Control
0x180008bb2  cmp     rcx, rax
0x180008bb5  jz      short loc_180008BD5
0x180008bb7  test    byte ptr [rcx+1Ch], 1
0x180008bbb  jz      short loc_180008BD5
0x180008bbd  mov     rcx, [rcx+10h]
0x180008bc1  lea     r8, WPP_3ebb8ef5cef634d4e8096079a4452eca_Traceguids
0x180008bc8  mov     edx, 11h
0x180008bcd  mov     r9d, esi
0x180008bd0  call    WPP_SF_d
0x180008bd5  mov     rdx, r15; __int16 *
0x180008bd8  lea     rcx, ?s_instance@CTimerQueue@@0V1@A; this
0x180008bdf  call    ?ReleaseHandle@CTimerQueue@@QEAAXPEAF@Z; CTimerQueue::ReleaseHandle(short *)
0x180008be4  jmp     loc_1800089F2
```
