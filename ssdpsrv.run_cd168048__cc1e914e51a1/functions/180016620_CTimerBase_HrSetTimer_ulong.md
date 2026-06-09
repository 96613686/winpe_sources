# CTimerBase::HrSetTimer(ulong)

- ea: `0x180016620`
- end: `0x1800168c8`
- name: `?HrSetTimer@CTimerBase@@QEAAJK@Z`
- size: `680`
- prototype: `__int64 __fastcall(PVOID Parameter, DWORD DueTime)`
- caller_count: `7`
- callee_count: `5`
- tags: ``

## callers

- `0x1800148c4`
- `0x180014b40`
- `0x180015168`
- `0x180016570`
- `0x1800177a0`
- `0x18001ddf4`
- `0x18001f2e0`

## callees

- `0x18000683c`
- `0x180016620`
- `0x18001c3b0`
- `0x1800271fc`
- `0x180029df0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800166b1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180016710`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001683c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800166b1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180016710`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001683c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180016640`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001673f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180016640`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001673f`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x1800166e9`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x1800166e9`

## pseudocode

```c
__int64 __fastcall CTimerBase::HrSetTimer(char *Parameter, DWORD DueTime)
{
  unsigned int v4; // esi
  LPCSTR v5; // rcx
  bool v6; // zf
  __int64 v8; // r12
  __int16 *v9; // r13
  __int16 v10; // cx
  __int16 v11; // r9
  __int16 i; // r8
  __int64 v13; // rdx
  __int64 v14; // rax
  void *v15; // r12
  unsigned int Win32Error; // eax

  v4 = -2147467259;
  EnterCriticalSection((LPCRITICAL_SECTION)Parameter + 1);
  if ( *((_DWORD *)Parameter + 20) )
  {
LABEL_2:
    if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_3ebb8ef5cef634d4e8096079a4452eca_Traceguids, v4);
    goto LABEL_11;
  }
  v8 = *((_QWORD *)Parameter + 3);
  v9 = (__int16 *)(Parameter + 32);
  EnterCriticalSection(&CriticalSection);
  if ( Parameter != (char *)-32LL )
  {
    v10 = word_180045738;
    v11 = 0;
    *v9 = -1;
    for ( i = 0; i < 100; ++i )
    {
      if ( !v4 )
        goto LABEL_25;
      v13 = CTimerQueue::s_instance[2 * v10];
      if ( v13 && v13 != v8 && LOWORD(CTimerQueue::s_instance[2 * v10 + 1]) != 10 )
      {
        v11 = v10;
        v4 = 0;
      }
      v10 = (__int16)(v10 + 1) % 100;
      word_180045738 = v10;
    }
    if ( !v4 )
    {
LABEL_25:
      v14 = 2LL * v11;
      v15 = (void *)CTimerQueue::s_instance[v14];
      *v9 = v11;
      ++LOWORD(CTimerQueue::s_instance[v14 + 1]);
      LeaveCriticalSection(&CriticalSection);
      *((_QWORD *)Parameter + 2) = v15;
      *((_QWORD *)Parameter + 3) = v15;
      if ( CreateTimerQueueTimer((PHANDLE)Parameter + 1, v15, CTimerBase::Callback, Parameter, DueTime, 0, 0) )
      {
        _InterlockedIncrement(&dword_1800445DC);
      }
      else
      {
        Win32Error = HrFromLastWin32Error();
        v4 = Win32Error;
        if ( Win32Error == -2147023899 )
        {
          v4 = 0;
          _InterlockedIncrement(&dword_1800445DC);
          goto LABEL_11;
        }
        if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 1) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_3ebb8ef5cef634d4e8096079a4452eca_Traceguids, Win32Error);
        CTimerQueue::ReleaseHandle((CTimerQueue *)CTimerQueue::s_instance, (__int16 *)Parameter + 16);
      }
      v6 = v4 == 0;
      goto LABEL_10;
    }
    goto LABEL_18;
  }
  v4 = -2147467261;
  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control )
  {
    if ( (WPP_GLOBAL_Control[28] & 1) == 0 )
      goto LABEL_19;
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_3ebb8ef5cef634d4e8096079a4452eca_Traceguids);
LABEL_18:
    v5 = WPP_GLOBAL_Control;
LABEL_19:
    if ( v5 != (LPCSTR)&WPP_GLOBAL_Control && (v5[28] & 1) != 0 )
      WPP_SF_d(*((_QWORD *)v5 + 2), 16, WPP_3ebb8ef5cef634d4e8096079a4452eca_Traceguids, v4);
  }
  LeaveCriticalSection(&CriticalSection);
  v6 = v4 == 0;
LABEL_10:
  if ( !v6 )
    goto LABEL_2;
LABEL_11:
  LeaveCriticalSection((LPCRITICAL_SECTION)Parameter + 1);
  return v4;
}

```

## disassembly

```asm
0x180016620  push    rbx
0x180016622  push    rbp
0x180016623  push    rsi
0x180016624  push    rdi
0x180016625  push    r12
0x180016627  push    r13
0x180016629  push    r14
0x18001662b  push    r15
0x18001662d  sub     rsp, 48h
0x180016631  mov     rdi, rcx
0x180016634  mov     r14d, edx
0x180016637  add     rcx, 28h ; '('; lpCriticalSection
0x18001663b  mov     esi, 80004005h
0x180016640  call    cs:__imp_EnterCriticalSection
0x180016647  nop     dword ptr [rax+rax+00h]
0x18001664c  mov     eax, [rdi+50h]
0x18001664f  test    eax, eax
0x180016651  jz      loc_180016730
0x180016657  lea     rbp, WPP_GLOBAL_Control
0x18001665e  mov     rcx, cs:WPP_GLOBAL_Control
0x180016665  cmp     rcx, rbp
0x180016668  jz      loc_18001670C
0x18001666e  test    byte ptr [rcx+1Ch], 1
0x180016672  jz      loc_18001670C
0x180016678  mov     rcx, [rcx+10h]
0x18001667c  lea     r8, WPP_3ebb8ef5cef634d4e8096079a4452eca_Traceguids
0x180016683  mov     edx, 12h
0x180016688  mov     r9d, esi
0x18001668b  call    WPP_SF_d
0x180016690  jmp     short loc_18001670C
0x180016692  mov     r12, r15
0x180016695  mov     esi, 80004003h
0x18001669a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800166a1  cmp     rcx, rbp
0x1800166a4  jnz     loc_18001684D
0x1800166aa  lea     rcx, CriticalSection; lpCriticalSection
0x1800166b1  call    cs:__imp_LeaveCriticalSection
0x1800166b8  nop     dword ptr [rax+rax+00h]
0x1800166bd  test    esi, esi
0x1800166bf  js      short loc_180016706
0x1800166c1  mov     [rsp+88h+Flags], r15d; Flags
0x1800166c6  lea     rcx, [rdi+8]; phNewTimer
0x1800166ca  mov     [rsp+88h+Period], r15d; Period
0x1800166cf  lea     r8, ?Callback@CTimerBase@@CAXPEAXE@Z; Callback
0x1800166d6  mov     r9, rdi; Parameter
0x1800166d9  mov     [rsp+88h+DueTime], r14d; DueTime
0x1800166de  mov     rdx, r12; TimerQueue
0x1800166e1  mov     [rdi+10h], r12
0x1800166e5  mov     [rdi+18h], r12
0x1800166e9  call    cs:__imp_CreateTimerQueueTimer
0x1800166f0  nop     dword ptr [rax+rax+00h]
0x1800166f5  test    eax, eax
0x1800166f7  jz      loc_18001686D
0x1800166fd  lock inc cs:dword_1800445DC
0x180016704  test    esi, esi
0x180016706  jnz     loc_18001665E
0x18001670c  lea     rcx, [rdi+28h]; lpCriticalSection
0x180016710  call    cs:__imp_LeaveCriticalSection
0x180016717  nop     dword ptr [rax+rax+00h]
0x18001671c  mov     eax, esi
0x18001671e  add     rsp, 48h
0x180016722  pop     r15
0x180016724  pop     r14
0x180016726  pop     r13
0x180016728  pop     r12
0x18001672a  pop     rdi
0x18001672b  pop     rsi
0x18001672c  pop     rbp
0x18001672d  pop     rbx
0x18001672e  retn
0x180016730  mov     r12, [rdi+18h]
0x180016734  lea     rcx, CriticalSection; lpCriticalSection
0x18001673b  lea     r13, [rdi+20h]
0x18001673f  call    cs:__imp_EnterCriticalSection
0x180016746  nop     dword ptr [rax+rax+00h]
0x18001674b  xor     r15d, r15d
0x18001674e  lea     rbp, WPP_GLOBAL_Control
0x180016755  lea     r10, ?s_instance@CTimerQueue@@0V1@A; CTimerQueue CTimerQueue::s_instance
0x18001675c  test    r13, r13
0x18001675f  jz      loc_180016692
0x180016765  movzx   ecx, cs:word_180045738
0x18001676c  movzx   r9d, r15w
0x180016770  mov     word ptr [r13+0], 0FFFFh
0x180016777  movzx   r8d, r15w
0x18001677b  mov     r11d, 0Ah
0x180016781  test    esi, esi
0x180016783  jz      loc_18001681E
0x180016789  movsx   rax, cx
0x18001678d  add     rax, rax
0x180016790  mov     rdx, [r10+rax*8]
0x180016794  test    rdx, rdx
0x180016797  jnz     short loc_180016805
0x180016799  inc     cx
0x18001679c  mov     eax, 51EB851Fh
0x1800167a1  movsx   ecx, cx
0x1800167a4  inc     r8w
0x1800167a8  imul    ecx
0x1800167aa  sar     edx, 5
0x1800167ad  mov     eax, edx
0x1800167af  shr     eax, 1Fh
0x1800167b2  add     edx, eax
0x1800167b4  imul    eax, edx, 64h ; 'd'
0x1800167b7  sub     ecx, eax
0x1800167b9  mov     cs:word_180045738, cx
0x1800167c0  cmp     r8w, 64h ; 'd'
0x1800167c5  jl      short loc_180016781
0x1800167c7  mov     r12, r15
0x1800167ca  test    esi, esi
0x1800167cc  jz      short loc_18001681E
0x1800167ce  mov     rcx, cs:WPP_GLOBAL_Control
0x1800167d5  cmp     rcx, rbp
0x1800167d8  jz      loc_1800166AA
0x1800167de  test    byte ptr [rcx+1Ch], 1
0x1800167e2  jz      loc_1800166AA
0x1800167e8  mov     rcx, [rcx+10h]
0x1800167ec  lea     r8, WPP_3ebb8ef5cef634d4e8096079a4452eca_Traceguids
0x1800167f3  mov     edx, 10h
0x1800167f8  mov     r9d, esi
0x1800167fb  call    WPP_SF_d
0x180016800  jmp     loc_1800166AA
0x180016805  cmp     rdx, r12
0x180016808  jz      short loc_180016799
0x18001680a  cmp     r11w, [r10+rax*8+8]
0x180016810  jz      short loc_180016799
0x180016812  movzx   r9d, cx
0x180016816  mov     esi, r15d
0x180016819  jmp     loc_180016799
0x18001681e  movsx   rax, r9w
0x180016822  lea     rcx, CriticalSection; lpCriticalSection
0x180016829  shl     rax, 4
0x18001682d  mov     r12, [rax+r10]
0x180016831  mov     [r13+0], r9w
0x180016836  inc     word ptr [rax+r10+8]
0x18001683c  call    cs:__imp_LeaveCriticalSection
0x180016843  nop     dword ptr [rax+rax+00h]
0x180016848  jmp     loc_1800166C1
0x18001684d  test    byte ptr [rcx+1Ch], 1
0x180016851  jz      short loc_1800167D5
0x180016853  mov     rcx, [rcx+10h]
0x180016857  lea     r8, WPP_3ebb8ef5cef634d4e8096079a4452eca_Traceguids
0x18001685e  mov     edx, 0Fh
0x180016863  call    WPP_SF_
0x180016868  jmp     loc_1800167CE
0x18001686d  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x180016872  mov     esi, eax
0x180016874  cmp     eax, 800703E5h
0x180016879  jnz     short loc_18001688A
0x18001687b  mov     esi, r15d
0x18001687e  lock inc cs:dword_1800445DC
0x180016885  jmp     loc_18001670C
0x18001688a  mov     rcx, cs:WPP_GLOBAL_Control
0x180016891  cmp     rcx, rbp
0x180016894  jz      short loc_1800168B4
0x180016896  test    byte ptr [rcx+1Ch], 1
0x18001689a  jz      short loc_1800168B4
0x18001689c  mov     rcx, [rcx+10h]
0x1800168a0  lea     r8, WPP_3ebb8ef5cef634d4e8096079a4452eca_Traceguids
0x1800168a7  mov     edx, 11h
0x1800168ac  mov     r9d, eax
0x1800168af  call    WPP_SF_d
0x1800168b4  mov     rdx, r13; __int16 *
0x1800168b7  lea     rcx, ?s_instance@CTimerQueue@@0V1@A; this
0x1800168be  call    ?ReleaseHandle@CTimerQueue@@QEAAXPEAF@Z; CTimerQueue::ReleaseHandle(short *)
0x1800168c3  jmp     loc_180016704
```
