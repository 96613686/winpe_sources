# CHungApp::ShortTerminationTimeoutCallback(_TP_CALLBACK_INSTANCE *,_TP_WAIT *,int)

- ea: `0x18002917c`
- end: `0x180029276`
- name: `?ShortTerminationTimeoutCallback@CHungApp@@AEAAXPEAU_TP_CALLBACK_INSTANCE@@PEAU_TP_WAIT@@H@Z`
- size: `250`
- prototype: `void __fastcall(CHungApp *__hidden this, PTP_CALLBACK_INSTANCE pci, struct _TP_WAIT *, int)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x1800297d0`

## callees

- `0x180011ef8`
- `0x18002917c`
- `0x180029cac`
- `0x180029e88`
- `0x18002b168`
- `0x18002b4ec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180029196`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180029196`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800291b2`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18002925a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800291b2`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18002925a`
- `api-ms-win-core-threadpool-l1-2-0!LeaveCriticalSectionWhenCallbackReturns` at `0x180029266`
- `api-ms-win-core-threadpool-l1-2-0!LeaveCriticalSectionWhenCallbackReturns` at `0x180029266`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CHungApp::ShortTerminationTimeoutCallback(
        struct _RTL_CRITICAL_SECTION *this,
        PTP_CALLBACK_INSTANCE pci,
        struct _TP_WAIT *a3,
        int a4)
{
  CHungApp *v7; // rbx
  struct _TP_WAIT *v8; // rcx
  char v9; // al
  int v10; // eax
  struct _TP_WAIT *v11; // rcx
  void *v12; // rdx
  struct _RTL_CRITICAL_SECTION *v13; // [rsp+20h] [rbp-38h] BYREF
  char v14; // [rsp+28h] [rbp-30h]

  v7 = (CHungApp *)this;
  v13 = this;
  EnterCriticalSection(this);
  v14 = 1;
  v8 = (struct _TP_WAIT *)*((_QWORD *)v7 + 301);
  if ( v8 )
    SetThreadpoolWait(v8, 0, 0);
  if ( *((_DWORD *)v7 + 12) && !*((_DWORD *)v7 + 613) )
  {
    if ( a4 )
    {
      v10 = CHungApp::_LaunchKernelHangReporting(v7);
      if ( v10 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          13,
          &WPP_28e55efa1b5d3afdb4532fbb5bd9be34_Traceguids,
          (unsigned int)v10);
      v11 = (struct _TP_WAIT *)*((_QWORD *)v7 + 302);
      if ( v11 )
      {
        v12 = (void *)*((_QWORD *)v7 + 148);
        if ( (unsigned __int64)v12 + 1 > 1 )
          SetThreadpoolWait(v11, v12, &CHungApp::ms_longTerminationTimeoutFT);
      }
    }
    else
    {
      v9 = CHungApp::_CalcTerminationTime(v7);
      CHungApp::_WriteHangEvent(v7, v9);
      CHungApp::_Cleanup((__int64)v7, (__int64)&v13, a3);
      v7 = (CHungApp *)v13;
    }
  }
  LeaveCriticalSectionWhenCallbackReturns(pci, (PCRITICAL_SECTION)v7);
}

```

## disassembly

```asm
0x18002917c  push    rbx
0x18002917e  push    rbp
0x18002917f  push    rsi
0x180029180  push    rdi
0x180029181  sub     rsp, 38h
0x180029185  mov     edi, r9d
0x180029188  mov     rsi, r8
0x18002918b  mov     rbp, rdx
0x18002918e  mov     rbx, rcx
0x180029191  mov     [rsp+58h+var_38], rcx
0x180029196  call    cs:__imp_EnterCriticalSection
0x18002919c  mov     [rsp+58h+var_30], 1
0x1800291a1  mov     rcx, [rbx+968h]; pwa
0x1800291a8  test    rcx, rcx
0x1800291ab  jz      short loc_1800291B8
0x1800291ad  xor     r8d, r8d; pftTimeout
0x1800291b0  xor     edx, edx; h
0x1800291b2  call    cs:__imp_SetThreadpoolWait
0x1800291b8  cmp     dword ptr [rbx+30h], 0
0x1800291bc  jz      loc_180029260
0x1800291c2  cmp     dword ptr [rbx+994h], 0
0x1800291c9  jnz     loc_180029260
0x1800291cf  mov     rcx, rbx; this
0x1800291d2  test    edi, edi
0x1800291d4  jnz     short loc_1800291FC
0x1800291d6  call    ?_CalcTerminationTime@CHungApp@@AEAAKXZ; CHungApp::_CalcTerminationTime(void)
0x1800291db  mov     edx, eax; unsigned int
0x1800291dd  mov     rcx, rbx; this
0x1800291e0  call    ?_WriteHangEvent@CHungApp@@AEAAJK@Z; CHungApp::_WriteHangEvent(ulong)
0x1800291e5  mov     r8, rsi
0x1800291e8  lea     rdx, [rsp+58h+var_38]
0x1800291ed  mov     rcx, rbx
0x1800291f0  call    ?_Cleanup@CHungApp@@AEAAXAEAV?$unique_lock@Vrecursive_mutex@utl@@@utl@@PEAU_TP_WAIT@@@Z; CHungApp::_Cleanup(utl::unique_lock<utl::recursive_mutex> &,_TP_WAIT *)
0x1800291f5  mov     rbx, [rsp+58h+var_38]
0x1800291fa  jmp     short loc_180029260
0x1800291fc  call    ?_LaunchKernelHangReporting@CHungApp@@AEAAJXZ; CHungApp::_LaunchKernelHangReporting(void)
0x180029201  test    eax, eax
0x180029203  jns     short loc_180029236
0x180029205  lea     rdx, WPP_GLOBAL_Control
0x18002920c  mov     rcx, cs:WPP_GLOBAL_Control
0x180029213  cmp     rcx, rdx
0x180029216  jz      short loc_180029236
0x180029218  test    byte ptr [rcx+1Ch], 1
0x18002921c  jz      short loc_180029236
0x18002921e  mov     edx, 0Dh
0x180029223  mov     r9d, eax
0x180029226  lea     r8, WPP_28e55efa1b5d3afdb4532fbb5bd9be34_Traceguids
0x18002922d  mov     rcx, [rcx+10h]
0x180029231  call    WPP_SF_d
0x180029236  mov     rcx, [rbx+970h]; pwa
0x18002923d  test    rcx, rcx
0x180029240  jz      short loc_180029260
0x180029242  mov     rdx, [rbx+4A0h]; h
0x180029249  lea     rax, [rdx+1]
0x18002924d  cmp     rax, 1
0x180029251  jbe     short loc_180029260
0x180029253  lea     r8, ?ms_longTerminationTimeoutFT@CHungApp@@0U_FILETIME@@A; pftTimeout
0x18002925a  call    cs:__imp_SetThreadpoolWait
0x180029260  mov     rdx, rbx; pcs
0x180029263  mov     rcx, rbp; pci
0x180029266  call    cs:__imp_LeaveCriticalSectionWhenCallbackReturns
0x18002926c  nop
0x18002926d  add     rsp, 38h
0x180029271  pop     rdi
0x180029272  pop     rsi
0x180029273  pop     rbp
0x180029274  pop     rbx
0x180029275  retn
```
