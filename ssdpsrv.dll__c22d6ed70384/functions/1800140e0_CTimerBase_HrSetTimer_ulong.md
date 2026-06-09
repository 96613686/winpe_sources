# CTimerBase::HrSetTimer(ulong)

- ea: `0x1800140e0`
- end: `0x180014363`
- name: `?HrSetTimer@CTimerBase@@QEAAJK@Z`
- size: `643`
- prototype: `__int64 __fastcall(char *Parameter, DWORD DueTime)`
- caller_count: `7`
- callee_count: `5`
- tags: ``

## callers

- `0x1800015cc`
- `0x180013924`
- `0x180013a70`
- `0x180014048`
- `0x1800151ec`
- `0x18001c974`
- `0x18001de28`

## callees

- `0x18000554c`
- `0x1800140e0`
- `0x18001afe4`
- `0x1800255a8`
- `0x180028000`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001416b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800141be`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800142dd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001416b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800141be`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800142dd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180014100`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800141e6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180014100`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800141e6`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x18001419d`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x18001419d`

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
    v10 = word_180042650;
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
      word_180042650 = v10;
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
        _InterlockedIncrement(&dword_1800414DC);
      }
      else
      {
        Win32Error = HrFromLastWin32Error();
        v4 = Win32Error;
        if ( Win32Error == -2147023899 )
        {
          v4 = 0;
          _InterlockedIncrement(&dword_1800414DC);
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
0x1800140e0  push    rbx
0x1800140e2  push    rbp
0x1800140e3  push    rsi
0x1800140e4  push    rdi
0x1800140e5  push    r12
0x1800140e7  push    r13
0x1800140e9  push    r14
0x1800140eb  push    r15
0x1800140ed  sub     rsp, 48h
0x1800140f1  mov     rdi, rcx
0x1800140f4  mov     r14d, edx
0x1800140f7  add     rcx, 28h ; '('; lpCriticalSection
0x1800140fb  mov     esi, 80004005h
0x180014100  call    cs:__imp_EnterCriticalSection
0x180014106  mov     eax, [rdi+50h]
0x180014109  test    eax, eax
0x18001410b  jz      loc_1800141D7
0x180014111  lea     rbp, WPP_GLOBAL_Control
0x180014118  mov     rcx, cs:WPP_GLOBAL_Control
0x18001411f  cmp     rcx, rbp
0x180014122  jz      loc_1800141BA
0x180014128  test    byte ptr [rcx+1Ch], 1
0x18001412c  jz      loc_1800141BA
0x180014132  mov     rcx, [rcx+10h]
0x180014136  lea     r8, WPP_3ebb8ef5cef634d4e8096079a4452eca_Traceguids
0x18001413d  mov     edx, 12h
0x180014142  mov     r9d, esi
0x180014145  call    WPP_SF_d
0x18001414a  jmp     short loc_1800141BA
0x18001414c  mov     r12, r15
0x18001414f  mov     esi, 80004003h
0x180014154  mov     rcx, cs:WPP_GLOBAL_Control
0x18001415b  cmp     rcx, rbp
0x18001415e  jnz     loc_1800142E8
0x180014164  lea     rcx, CriticalSection; lpCriticalSection
0x18001416b  call    cs:__imp_LeaveCriticalSection
0x180014171  test    esi, esi
0x180014173  js      short loc_1800141B4
0x180014175  mov     [rsp+88h+Flags], r15d; Flags
0x18001417a  lea     rcx, [rdi+8]; phNewTimer
0x18001417e  mov     [rsp+88h+Period], r15d; Period
0x180014183  lea     r8, ?Callback@CTimerBase@@CAXPEAXE@Z; Callback
0x18001418a  mov     r9, rdi; Parameter
0x18001418d  mov     [rsp+88h+DueTime], r14d; DueTime
0x180014192  mov     rdx, r12; TimerQueue
0x180014195  mov     [rdi+10h], r12
0x180014199  mov     [rdi+18h], r12
0x18001419d  call    cs:__imp_CreateTimerQueueTimer
0x1800141a3  test    eax, eax
0x1800141a5  jz      loc_180014308
0x1800141ab  lock inc cs:dword_1800414DC
0x1800141b2  test    esi, esi
0x1800141b4  jnz     loc_180014118
0x1800141ba  lea     rcx, [rdi+28h]; lpCriticalSection
0x1800141be  call    cs:__imp_LeaveCriticalSection
0x1800141c4  mov     eax, esi
0x1800141c6  add     rsp, 48h
0x1800141ca  pop     r15
0x1800141cc  pop     r14
0x1800141ce  pop     r13
0x1800141d0  pop     r12
0x1800141d2  pop     rdi
0x1800141d3  pop     rsi
0x1800141d4  pop     rbp
0x1800141d5  pop     rbx
0x1800141d6  retn
0x1800141d7  mov     r12, [rdi+18h]
0x1800141db  lea     rcx, CriticalSection; lpCriticalSection
0x1800141e2  lea     r13, [rdi+20h]
0x1800141e6  call    cs:__imp_EnterCriticalSection
0x1800141ec  xor     r15d, r15d
0x1800141ef  lea     rbp, WPP_GLOBAL_Control
0x1800141f6  lea     r10, ?s_instance@CTimerQueue@@0V1@A; CTimerQueue CTimerQueue::s_instance
0x1800141fd  test    r13, r13
0x180014200  jz      loc_18001414C
0x180014206  movzx   ecx, cs:word_180042650
0x18001420d  movzx   r9d, r15w
0x180014211  mov     word ptr [r13+0], 0FFFFh
0x180014218  movzx   r8d, r15w
0x18001421c  mov     r11d, 0Ah
0x180014222  test    esi, esi
0x180014224  jz      loc_1800142BF
0x18001422a  movsx   rax, cx
0x18001422e  add     rax, rax
0x180014231  mov     rdx, [r10+rax*8]
0x180014235  test    rdx, rdx
0x180014238  jnz     short loc_1800142A6
0x18001423a  inc     cx
0x18001423d  mov     eax, 51EB851Fh
0x180014242  movsx   ecx, cx
0x180014245  inc     r8w
0x180014249  imul    ecx
0x18001424b  sar     edx, 5
0x18001424e  mov     eax, edx
0x180014250  shr     eax, 1Fh
0x180014253  add     edx, eax
0x180014255  imul    eax, edx, 64h ; 'd'
0x180014258  sub     ecx, eax
0x18001425a  mov     cs:word_180042650, cx
0x180014261  cmp     r8w, 64h ; 'd'
0x180014266  jl      short loc_180014222
0x180014268  mov     r12, r15
0x18001426b  test    esi, esi
0x18001426d  jz      short loc_1800142BF
0x18001426f  mov     rcx, cs:WPP_GLOBAL_Control
0x180014276  cmp     rcx, rbp
0x180014279  jz      loc_180014164
0x18001427f  test    byte ptr [rcx+1Ch], 1
0x180014283  jz      loc_180014164
0x180014289  mov     rcx, [rcx+10h]
0x18001428d  lea     r8, WPP_3ebb8ef5cef634d4e8096079a4452eca_Traceguids
0x180014294  mov     edx, 10h
0x180014299  mov     r9d, esi
0x18001429c  call    WPP_SF_d
0x1800142a1  jmp     loc_180014164
0x1800142a6  cmp     rdx, r12
0x1800142a9  jz      short loc_18001423A
0x1800142ab  cmp     r11w, [r10+rax*8+8]
0x1800142b1  jz      short loc_18001423A
0x1800142b3  movzx   r9d, cx
0x1800142b7  mov     esi, r15d
0x1800142ba  jmp     loc_18001423A
0x1800142bf  movsx   rax, r9w
0x1800142c3  lea     rcx, CriticalSection; lpCriticalSection
0x1800142ca  shl     rax, 4
0x1800142ce  mov     r12, [rax+r10]
0x1800142d2  mov     [r13+0], r9w
0x1800142d7  inc     word ptr [rax+r10+8]
0x1800142dd  call    cs:__imp_LeaveCriticalSection
0x1800142e3  jmp     loc_180014175
0x1800142e8  test    byte ptr [rcx+1Ch], 1
0x1800142ec  jz      short loc_180014276
0x1800142ee  mov     rcx, [rcx+10h]
0x1800142f2  lea     r8, WPP_3ebb8ef5cef634d4e8096079a4452eca_Traceguids
0x1800142f9  mov     edx, 0Fh
0x1800142fe  call    WPP_SF_
0x180014303  jmp     loc_18001426F
0x180014308  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x18001430d  mov     esi, eax
0x18001430f  cmp     eax, 800703E5h
0x180014314  jnz     short loc_180014325
0x180014316  mov     esi, r15d
0x180014319  lock inc cs:dword_1800414DC
0x180014320  jmp     loc_1800141BA
0x180014325  mov     rcx, cs:WPP_GLOBAL_Control
0x18001432c  cmp     rcx, rbp
0x18001432f  jz      short loc_18001434F
0x180014331  test    byte ptr [rcx+1Ch], 1
0x180014335  jz      short loc_18001434F
0x180014337  mov     rcx, [rcx+10h]
0x18001433b  lea     r8, WPP_3ebb8ef5cef634d4e8096079a4452eca_Traceguids
0x180014342  mov     edx, 11h
0x180014347  mov     r9d, eax
0x18001434a  call    WPP_SF_d
0x18001434f  mov     rdx, r13; __int16 *
0x180014352  lea     rcx, ?s_instance@CTimerQueue@@0V1@A; this
0x180014359  call    ?ReleaseHandle@CTimerQueue@@QEAAXPEAF@Z; CTimerQueue::ReleaseHandle(short *)
0x18001435e  jmp     loc_1800141B2
```
