# CHungApp::HangrepExitedCallback(_TP_CALLBACK_INSTANCE *,_TP_WAIT *)

- ea: `0x18002710c`
- end: `0x180027257`
- name: `?HangrepExitedCallback@CHungApp@@AEAAXPEAU_TP_CALLBACK_INSTANCE@@PEAU_TP_WAIT@@@Z`
- size: `331`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this, PTP_CALLBACK_INSTANCE pci, struct _TP_WAIT *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180029310`

## callees

- `0x180006a80`
- `0x180006aa8`
- `0x180011ef8`
- `0x18002710c`
- `0x180029e88`
- `0x18002b424`
- `0x18002b4ec`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x18002715a`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x18002715a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002712c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002712c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180027225`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180027225`
- `api-ms-win-core-threadpool-l1-2-0!LeaveCriticalSectionWhenCallbackReturns` at `0x180027246`
- `api-ms-win-core-threadpool-l1-2-0!LeaveCriticalSectionWhenCallbackReturns` at `0x180027246`

## pseudocode

```c
void __fastcall CHungApp::HangrepExitedCallback(
        struct _RTL_CRITICAL_SECTION *this,
        PTP_CALLBACK_INSTANCE pci,
        struct _TP_WAIT *a3)
{
  CHungApp *v5; // rbx
  HANDLE *v6; // rcx
  struct _TP_WAIT *v7; // rcx
  struct _RTL_CRITICAL_SECTION *v8; // [rsp+20h] [rbp-38h] BYREF
  char v9; // [rsp+28h] [rbp-30h]
  DWORD ExitCode; // [rsp+60h] [rbp+8h] BYREF

  v5 = (CHungApp *)this;
  ExitCode = -1;
  v8 = this;
  EnterCriticalSection(this);
  v9 = 1;
  if ( *((_DWORD *)v5 + 613) || !*((_DWORD *)v5 + 12) )
    goto LABEL_20;
  if ( !GetExitCodeProcess(*((HANDLE *)v5 + 296), &ExitCode) )
  {
    ExitCode = -1;
    goto LABEL_8;
  }
  v6 = (HANDLE *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
    {
LABEL_9:
      if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 8) != 0 )
        WPP_SF_S(v6[2], 11, WPP_28e55efa1b5d3afdb4532fbb5bd9be34_Traceguids, (char *)v5 + 1192);
      goto LABEL_12;
    }
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_28e55efa1b5d3afdb4532fbb5bd9be34_Traceguids, ExitCode);
LABEL_8:
    v6 = (HANDLE *)WPP_GLOBAL_Control;
    goto LABEL_9;
  }
LABEL_12:
  CHungApp::_WriteHangEvent(v5, -1);
  if ( *((_DWORD *)v5 + 82) )
  {
    CHungApp::_TerminateProcessCallback(v5);
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_28e55efa1b5d3afdb4532fbb5bd9be34_Traceguids);
    v7 = (struct _TP_WAIT *)*((_QWORD *)v5 + 300);
    if ( v7 )
      SetThreadpoolWait(v7, 0, 0);
    CHungApp::_Cleanup((__int64)v5, (__int64)&v8, a3);
    v5 = (CHungApp *)v8;
  }
LABEL_20:
  LeaveCriticalSectionWhenCallbackReturns(pci, (PCRITICAL_SECTION)v5);
}

```

## disassembly

```asm
0x18002710c  push    rbx
0x18002710e  push    rsi
0x18002710f  push    rdi
0x180027110  push    r15
0x180027112  sub     rsp, 38h
0x180027116  mov     rsi, r8
0x180027119  mov     rdi, rdx
0x18002711c  mov     rbx, rcx
0x18002711f  mov     [rsp+58h+ExitCode], 0FFFFFFFFh
0x180027127  mov     [rsp+58h+var_38], rcx
0x18002712c  call    cs:__imp_EnterCriticalSection
0x180027132  mov     [rsp+58h+var_30], 1
0x180027137  cmp     dword ptr [rbx+994h], 0
0x18002713e  jnz     loc_180027240
0x180027144  cmp     dword ptr [rbx+30h], 0
0x180027148  jz      loc_180027240
0x18002714e  lea     rdx, [rsp+58h+ExitCode]; lpExitCode
0x180027153  mov     rcx, [rbx+940h]; hProcess
0x18002715a  call    cs:__imp_GetExitCodeProcess
0x180027160  lea     r15, WPP_GLOBAL_Control
0x180027167  test    eax, eax
0x180027169  jz      short loc_180027199
0x18002716b  mov     rcx, cs:WPP_GLOBAL_Control
0x180027172  cmp     rcx, r15
0x180027175  jz      short loc_1800271CF
0x180027177  test    byte ptr [rcx+1Ch], 4
0x18002717b  jz      short loc_1800271A8
0x18002717d  mov     edx, 0Ah
0x180027182  mov     r9d, [rsp+58h+ExitCode]
0x180027187  lea     r8, WPP_28e55efa1b5d3afdb4532fbb5bd9be34_Traceguids
0x18002718e  mov     rcx, [rcx+10h]
0x180027192  call    WPP_SF_d
0x180027197  jmp     short loc_1800271A1
0x180027199  mov     [rsp+58h+ExitCode], 0FFFFFFFFh
0x1800271a1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800271a8  cmp     rcx, r15
0x1800271ab  jz      short loc_1800271CF
0x1800271ad  test    byte ptr [rcx+1Ch], 8
0x1800271b1  jz      short loc_1800271CF
0x1800271b3  lea     r9, [rbx+4A8h]
0x1800271ba  mov     edx, 0Bh
0x1800271bf  lea     r8, WPP_28e55efa1b5d3afdb4532fbb5bd9be34_Traceguids
0x1800271c6  mov     rcx, [rcx+10h]
0x1800271ca  call    WPP_SF_S
0x1800271cf  or      edx, 0FFFFFFFFh; unsigned int
0x1800271d2  mov     rcx, rbx; this
0x1800271d5  call    ?_WriteHangEvent@CHungApp@@AEAAJK@Z; CHungApp::_WriteHangEvent(ulong)
0x1800271da  cmp     dword ptr [rbx+148h], 0
0x1800271e1  jz      short loc_1800271ED
0x1800271e3  mov     rcx, rbx; this
0x1800271e6  call    ?_TerminateProcessCallback@CHungApp@@AEAAXXZ; CHungApp::_TerminateProcessCallback(void)
0x1800271eb  jmp     short loc_180027240
0x1800271ed  mov     rcx, cs:WPP_GLOBAL_Control
0x1800271f4  cmp     rcx, r15
0x1800271f7  jz      short loc_180027214
0x1800271f9  test    byte ptr [rcx+1Ch], 4
0x1800271fd  jz      short loc_180027214
0x1800271ff  mov     edx, 0Ch
0x180027204  lea     r8, WPP_28e55efa1b5d3afdb4532fbb5bd9be34_Traceguids
0x18002720b  mov     rcx, [rcx+10h]
0x18002720f  call    WPP_SF_
0x180027214  mov     rcx, [rbx+960h]; pwa
0x18002721b  test    rcx, rcx
0x18002721e  jz      short loc_18002722B
0x180027220  xor     r8d, r8d; pftTimeout
0x180027223  xor     edx, edx; h
0x180027225  call    cs:__imp_SetThreadpoolWait
0x18002722b  mov     r8, rsi
0x18002722e  lea     rdx, [rsp+58h+var_38]
0x180027233  mov     rcx, rbx
0x180027236  call    ?_Cleanup@CHungApp@@AEAAXAEAV?$unique_lock@Vrecursive_mutex@utl@@@utl@@PEAU_TP_WAIT@@@Z; CHungApp::_Cleanup(utl::unique_lock<utl::recursive_mutex> &,_TP_WAIT *)
0x18002723b  mov     rbx, [rsp+58h+var_38]
0x180027240  mov     rdx, rbx; pcs
0x180027243  mov     rcx, rdi; pci
0x180027246  call    cs:__imp_LeaveCriticalSectionWhenCallbackReturns
0x18002724c  nop
0x18002724d  add     rsp, 38h
0x180027251  pop     r15
0x180027253  pop     rdi
0x180027254  pop     rsi
0x180027255  pop     rbx
0x180027256  retn
```
