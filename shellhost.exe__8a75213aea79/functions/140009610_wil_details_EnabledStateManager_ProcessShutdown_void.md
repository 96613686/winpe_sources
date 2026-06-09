# wil::details::EnabledStateManager::ProcessShutdown(void)

- ea: `0x140009610`
- end: `0x140009860`
- name: `?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ`
- size: `592`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x14000b1a0`
- `0x140065890`

## callees

- `0x140009610`
- `0x14000f7e0`
- `0x14004a384`
- `0x140067010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000964b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000964b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140009800`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140009800`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000983b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000983b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000980b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000980b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140009833`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140009833`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000981e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000981e`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14000982a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14000982a`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall wil::details::EnabledStateManager::ProcessShutdown(RTL_SRWLOCK *this)
{
  struct _TP_TIMER *Ptr; // rsi
  RTL_SRWLOCK *v3; // rbp
  _QWORD *v4; // rbx
  _BYTE *v5; // rdi
  __int64 v6; // r8
  int v7; // r10d
  unsigned __int32 v8; // ecx
  unsigned __int32 v9; // eax
  char *v10; // rdx
  unsigned __int64 v11; // r8
  __int64 v12; // rdx
  void (__fastcall *v13)(_QWORD, __int64, _QWORD, _QWORD); // rax
  DWORD LastError; // ebx
  _DWORD v15[2]; // [rsp+38h] [rbp-80h] BYREF
  char v16; // [rsp+40h] [rbp-78h] BYREF

  LODWORD(this->Ptr) = 0;
  Ptr = (struct _TP_TIMER *)this[2].Ptr;
  this[2].Ptr = 0;
  v3 = this + 1;
  AcquireSRWLockExclusive(this + 1);
  v4 = this[4].Ptr;
  v5 = this[5].Ptr;
  if ( (unsigned __int64)(v5 - (_BYTE *)v4) >= 0x10 )
  {
    while ( v4 != (_QWORD *)v5 )
    {
      v6 = v4[1];
      v7 = *(_DWORD *)v4;
      _m_prefetchw((const void *)v6);
      v8 = _InterlockedAnd((volatile signed __int32 *)v6, 0xFFC0401E);
      if ( ((v8 >> 1) & 0xF) != 0 )
      {
        _m_prefetchw((const void *)(v6 + 4));
        v9 = (v8 >> 1) & 0xF & ~_InterlockedOr((volatile signed __int32 *)(v6 + 4), (v8 >> 1) & 0xF);
      }
      else
      {
        v9 = 0;
      }
      if ( (v9 & 1) != 0 )
      {
        v15[0] = v7;
        v15[1] = 65538;
        v10 = &v16;
      }
      else
      {
        v10 = (char *)v15;
      }
      if ( (v9 & 2) != 0 )
      {
        *(_DWORD *)v10 = v7;
        *((_DWORD *)v10 + 1) = 65542;
        v10 += 8;
      }
      if ( (v9 & 4) != 0 )
      {
        *(_DWORD *)v10 = v7;
        *((_DWORD *)v10 + 1) = 65539;
        v10 += 8;
      }
      if ( v9 >= 8 )
      {
        *(_DWORD *)v10 = v7;
        *((_DWORD *)v10 + 1) = 65543;
        v10 += 8;
      }
      v11 = v8 >> 5;
      if ( (v11 & 0x1FF) != 0 )
      {
        *(_DWORD *)v10 = v7;
        *((_WORD *)v10 + 2) = 4 * ((v8 >> 14) & 1);
        LOWORD(v11) = v11 & 0x1FF;
        *((_WORD *)v10 + 3) = v11;
        v10 += 8;
      }
      if ( ((v8 >> 15) & 0x7F) != 0 )
      {
        *(_DWORD *)v10 = v7;
        *((_WORD *)v10 + 2) = 4 * ((v8 >> 22) & 1) + 1;
        *((_WORD *)v10 + 3) = (v8 >> 15) & 0x7F;
        v10 += 8;
      }
      v12 = (v10 - (char *)v15) >> 3;
      if ( v12 > 0 )
        wil::details::WilApi_RecordFeatureUsageReports(
          (wil::details *)v15,
          (struct __WIL_RTL_FEATURE_USAGE_DATA *)v12,
          v11);
      v4 += 2;
    }
    this[5].Ptr = this[4].Ptr;
    v13 = (void (__fastcall *)(_QWORD, __int64, _QWORD, _QWORD))g_wil_details_internalRecordFeatureUsage;
    v3 = this + 1;
    if ( g_wil_details_internalRecordFeatureUsage
      || (v13 = (void (__fastcall *)(_QWORD, __int64, _QWORD, _QWORD))g_wil_details_apiRecordFeatureUsage) != 0 )
    {
      v13(0, 254, 0, 0);
    }
  }
  if ( v3 )
    ReleaseSRWLockExclusive(v3);
  if ( Ptr )
  {
    LastError = GetLastError();
    SetThreadpoolTimer(Ptr, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(Ptr, 1);
    CloseThreadpoolTimer(Ptr);
    SetLastError(LastError);
  }
}

```

## disassembly

```asm
0x140009610  push    rbx
0x140009612  push    rbp
0x140009613  push    rsi
0x140009614  push    rdi
0x140009615  push    r12
0x140009617  push    r13
0x140009619  push    r14
0x14000961b  push    r15
0x14000961d  sub     rsp, 78h
0x140009621  mov     rax, cs:__security_cookie
0x140009628  xor     rax, rsp
0x14000962b  mov     [rsp+0B8h+var_50], rax
0x140009630  mov     r14, rcx
0x140009633  xor     eax, eax
0x140009635  mov     [rcx], eax
0x140009637  mov     rsi, [rcx+10h]
0x14000963b  mov     [rsp+0B8h+var_88], rsi
0x140009640  mov     [rcx+10h], rax
0x140009644  lea     rbp, [rcx+8]
0x140009648  mov     rcx, rbp; SRWLock
0x14000964b  call    cs:__imp_AcquireSRWLockExclusive
0x140009651  nop
0x140009652  mov     rbx, [r14+20h]
0x140009656  mov     rdi, [r14+28h]
0x14000965a  mov     rax, rdi
0x14000965d  sub     rax, rbx
0x140009660  mov     r15d, 1
0x140009666  cmp     rax, 10h
0x14000966a  jb      loc_1400097F8
0x140009670  mov     r11d, 6
0x140009676  mov     r12d, 1FFh
0x14000967c  nop     dword ptr [rax+00h]
0x140009680  cmp     rbx, rdi
0x140009683  jz      loc_1400097BC
0x140009689  mov     r8, [rbx+8]
0x14000968d  mov     r10d, [rbx]
0x140009690  prefetchw byte ptr [r8]
0x140009694  mov     eax, [r8]
0x140009697  nop     word ptr [rax+rax+00000000h]
0x1400096a0  mov     ecx, eax
0x1400096a2  and     ecx, 0FFC0401Eh
0x1400096a8  lock cmpxchg [r8], ecx
0x1400096ad  jnz     short loc_1400096A0
0x1400096af  mov     ecx, eax
0x1400096b1  mov     r9d, eax
0x1400096b4  shr     r9d, 1
0x1400096b7  and     r9d, 0Fh
0x1400096bb  jz      short loc_1400096E4
0x1400096bd  prefetchw byte ptr [r8+4]
0x1400096c2  mov     eax, [r8+4]
0x1400096c6  nop     word ptr [rax+rax+00000000h]
0x1400096d0  mov     edx, eax
0x1400096d2  or      edx, r9d
0x1400096d5  lock cmpxchg [r8+4], edx
0x1400096db  jnz     short loc_1400096D0
0x1400096dd  not     eax
0x1400096df  and     eax, r9d
0x1400096e2  jmp     short loc_1400096E7
0x1400096e4  mov     eax, r9d
0x1400096e7  test    al, 1
0x1400096e9  jz      short loc_1400096FF
0x1400096eb  mov     [rsp+0B8h+var_80], r10d
0x1400096f0  mov     [rsp+0B8h+var_7C], 10002h
0x1400096f8  lea     rdx, [rsp+0B8h+var_78]
0x1400096fd  jmp     short loc_140009704
0x1400096ff  lea     rdx, [rsp+0B8h+var_80]
0x140009704  test    al, 2
0x140009706  jz      short loc_140009716
0x140009708  mov     [rdx], r10d
0x14000970b  mov     dword ptr [rdx+4], 10006h
0x140009712  add     rdx, 8
0x140009716  test    al, 4
0x140009718  jz      short loc_140009728
0x14000971a  mov     [rdx], r10d
0x14000971d  mov     dword ptr [rdx+4], 10003h
0x140009724  add     rdx, 8
0x140009728  cmp     eax, 8
0x14000972b  jb      short loc_14000973B
0x14000972d  mov     [rdx], r10d
0x140009730  mov     dword ptr [rdx+4], 10007h
0x140009737  add     rdx, 8
0x14000973b  mov     r8d, ecx
0x14000973e  shr     r8d, 5
0x140009742  test    r12d, r8d
0x140009745  jz      short loc_140009768
0x140009747  mov     [rdx], r10d
0x14000974a  mov     eax, ecx
0x14000974c  shr     eax, 0Eh
0x14000974f  and     ax, 1
0x140009753  shl     ax, 2
0x140009757  mov     [rdx+4], ax
0x14000975b  and     r8w, r12w; unsigned __int64
0x14000975f  mov     [rdx+6], r8w
0x140009764  add     rdx, 8
0x140009768  mov     eax, ecx
0x14000976a  shr     eax, 0Fh
0x14000976d  test    al, 7Fh
0x14000976f  jz      short loc_140009792
0x140009771  mov     [rdx], r10d
0x140009774  shr     ecx, 16h
0x140009777  and     cx, 1
0x14000977b  shl     cx, 2
0x14000977f  inc     cx
0x140009782  mov     [rdx+4], cx
0x140009786  and     ax, 7Fh
0x14000978a  mov     [rdx+6], ax
0x14000978e  add     rdx, 8
0x140009792  lea     rax, [rsp+0B8h+var_80]
0x140009797  sub     rdx, rax
0x14000979a  sar     rdx, 3; struct __WIL_RTL_FEATURE_USAGE_DATA *
0x14000979e  test    rdx, rdx
0x1400097a1  jle     short loc_1400097B3
0x1400097a3  lea     rcx, [rsp+0B8h+var_80]; this
0x1400097a8  call    ?WilApi_RecordFeatureUsageReports@details@wil@@YAXPEAU__WIL_RTL_FEATURE_USAGE_DATA@@_K@Z; wil::details::WilApi_RecordFeatureUsageReports(__WIL_RTL_FEATURE_USAGE_DATA *,unsigned __int64)
0x1400097ad  mov     r11d, 6
0x1400097b3  add     rbx, 10h
0x1400097b7  jmp     loc_140009680
0x1400097bc  mov     rax, [r14+20h]
0x1400097c0  mov     [r14+28h], rax
0x1400097c4  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x1400097cb  test    rax, rax
0x1400097ce  mov     rsi, [rsp+0B8h+var_88]
0x1400097d3  lea     rbp, [r14+8]
0x1400097d7  jnz     short loc_1400097E5
0x1400097d9  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x1400097e0  test    rax, rax
0x1400097e3  jz      short loc_1400097F8
0x1400097e5  xor     r9d, r9d
0x1400097e8  xor     r8d, r8d
0x1400097eb  mov     edx, 0FEh
0x1400097f0  xor     ecx, ecx
0x1400097f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400097f7  nop
0x1400097f8  test    rbp, rbp
0x1400097fb  jz      short loc_140009806
0x1400097fd  mov     rcx, rbp; SRWLock
0x140009800  call    cs:__imp_ReleaseSRWLockExclusive
0x140009806  test    rsi, rsi
0x140009809  jz      short loc_140009842
0x14000980b  call    cs:__imp_GetLastError
0x140009811  mov     ebx, eax
0x140009813  xor     r9d, r9d; msWindowLength
0x140009816  xor     r8d, r8d; msPeriod
0x140009819  xor     edx, edx; pftDueTime
0x14000981b  mov     rcx, rsi; pti
0x14000981e  call    cs:__imp_SetThreadpoolTimer
0x140009824  mov     edx, r15d; fCancelPendingCallbacks
0x140009827  mov     rcx, rsi; pti
0x14000982a  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140009830  mov     rcx, rsi; pti
0x140009833  call    cs:__imp_CloseThreadpoolTimer
0x140009839  mov     ecx, ebx; dwErrCode
0x14000983b  call    cs:__imp_SetLastError
0x140009841  nop
0x140009842  mov     rcx, [rsp+0B8h+var_50]
0x140009847  xor     rcx, rsp; StackCookie
0x14000984a  call    __security_check_cookie
0x14000984f  add     rsp, 78h
0x140009853  pop     r15
0x140009855  pop     r14
0x140009857  pop     r13
0x140009859  pop     r12
0x14000985b  pop     rdi
0x14000985c  pop     rsi
0x14000985d  pop     rbp
0x14000985e  pop     rbx
0x14000985f  retn
```
