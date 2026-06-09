# WFDGOCancelPeerTimer(_WLAN_INTERFACE_CONTEXT *,_WFD_GO_PEER *)

- ea: `0x18019d618`
- end: `0x18019d7ee`
- name: `?WFDGOCancelPeerTimer@@YAXPEAU_WLAN_INTERFACE_CONTEXT@@PEAU_WFD_GO_PEER@@@Z`
- size: `470`
- prototype: `void __fastcall(struct _WLAN_INTERFACE_CONTEXT *, struct _WFD_GO_PEER *)`
- caller_count: `5`
- callee_count: `5`
- tags: ``

## callers

- `0x180091a6c`
- `0x1801043dc`
- `0x18019d390`
- `0x18019f2b4`
- `0x1801a1614`

## callees

- `0x18000aa0c`
- `0x18000be00`
- `0x180011530`
- `0x18019d618`
- `0x18022c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18019d709`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18019d773`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18019d7b0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18019d709`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18019d773`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18019d7b0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18019d66b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18019d720`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18019d66b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18019d720`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18019d717`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18019d780`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18019d717`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18019d780`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18019d6d4`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18019d6d4`

## pseudocode

```c
void __fastcall WFDGOCancelPeerTimer(struct _WLAN_INTERFACE_CONTEXT *a1, struct _WFD_GO_PEER *a2)
{
  struct _RTL_CRITICAL_SECTION *v4; // rsi
  PVOID *v5; // rcx
  struct _TP_TIMER *v6; // rdi
  void (__fastcall *v7)(_QWORD, struct _WFD_GO_PEER *, struct _TP_TIMER *); // rax

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 75, &WPP_d9ecea357ab2342fc3040b4a1bc3b2b2_Traceguids);
  }
  v4 = (struct _RTL_CRITICAL_SECTION *)((char *)a1 + 144);
  EnterCriticalSection(v4);
  v5 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 12), 76, &WPP_d9ecea357ab2342fc3040b4a1bc3b2b2_Traceguids, a2);
    v5 = (PVOID *)WPP_GLOBAL_Control;
  }
  v6 = (struct _TP_TIMER *)*((_QWORD *)a2 + 32);
  if ( v6 )
  {
    if ( !*((_DWORD *)a2 + 66) )
    {
      *((_QWORD *)a2 + 32) = 0;
      SetThreadpoolTimer(v6, 0, 0, 0);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
      {
        WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 12), 77, &WPP_d9ecea357ab2342fc3040b4a1bc3b2b2_Traceguids, a2);
      }
      LeaveCriticalSection(v4);
      WaitForThreadpoolTimerCallbacks(v6, 1);
      EnterCriticalSection(v4);
      v7 = (void (__fastcall *)(_QWORD, struct _WFD_GO_PEER *, struct _TP_TIMER *))*((_QWORD *)a2 + 31);
      *((_QWORD *)a2 + 32) = v6;
      v7(0, a2, v6);
LABEL_26:
      LeaveCriticalSection(v4);
      goto LABEL_27;
    }
  }
  else if ( !*((_DWORD *)a2 + 66) )
  {
    if ( v5 != &WPP_GLOBAL_Control && *((_BYTE *)v5 + 105) >= 4u && (*((_BYTE *)v5 + 108) & 1) != 0 )
      WPP_SF_q(v5[12], 79, &WPP_d9ecea357ab2342fc3040b4a1bc3b2b2_Traceguids, a2);
    goto LABEL_26;
  }
  if ( v5 != &WPP_GLOBAL_Control && *((_BYTE *)v5 + 105) >= 4u && (*((_BYTE *)v5 + 108) & 1) != 0 )
    WPP_SF_q(v5[12], 78, &WPP_d9ecea357ab2342fc3040b4a1bc3b2b2_Traceguids, a2);
  LeaveCriticalSection(v4);
  WaitForThreadpoolTimerCallbacks(0, 1);
LABEL_27:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 80, &WPP_d9ecea357ab2342fc3040b4a1bc3b2b2_Traceguids, 0);
  }
}

```

## disassembly

```asm
0x18019d618  push    rbx
0x18019d61a  push    rsi
0x18019d61b  push    rdi
0x18019d61c  push    r12
0x18019d61e  push    r15
0x18019d620  sub     rsp, 20h
0x18019d624  mov     rbx, rdx
0x18019d627  mov     rsi, rcx
0x18019d62a  mov     rcx, cs:WPP_GLOBAL_Control
0x18019d631  lea     r15, WPP_GLOBAL_Control
0x18019d638  lea     r12, WPP_d9ecea357ab2342fc3040b4a1bc3b2b2_Traceguids
0x18019d63f  cmp     rcx, r15
0x18019d642  jz      short loc_18019D661
0x18019d644  cmp     byte ptr [rcx+69h], 4
0x18019d648  jb      short loc_18019D661
0x18019d64a  test    byte ptr [rcx+6Ch], 1
0x18019d64e  jz      short loc_18019D661
0x18019d650  mov     rcx, [rcx+60h]
0x18019d654  mov     edx, 4Bh ; 'K'
0x18019d659  mov     r8, r12
0x18019d65c  call    WPP_SF_
0x18019d661  add     rsi, 90h
0x18019d668  mov     rcx, rsi; lpCriticalSection
0x18019d66b  call    cs:__imp_EnterCriticalSection
0x18019d671  mov     rcx, cs:WPP_GLOBAL_Control
0x18019d678  cmp     rcx, r15
0x18019d67b  jz      short loc_18019D6A4
0x18019d67d  cmp     byte ptr [rcx+69h], 4
0x18019d681  jb      short loc_18019D6A4
0x18019d683  test    byte ptr [rcx+6Ch], 1
0x18019d687  jz      short loc_18019D6A4
0x18019d689  mov     rcx, [rcx+60h]
0x18019d68d  mov     edx, 4Ch ; 'L'
0x18019d692  mov     r9, rbx
0x18019d695  mov     r8, r12
0x18019d698  call    WPP_SF_q
0x18019d69d  mov     rcx, cs:WPP_GLOBAL_Control
0x18019d6a4  mov     rdi, [rbx+100h]
0x18019d6ab  xor     eax, eax
0x18019d6ad  test    rdi, rdi
0x18019d6b0  jz      loc_18019D743
0x18019d6b6  cmp     [rbx+108h], eax
0x18019d6bc  jnz     loc_18019D74B
0x18019d6c2  xor     r9d, r9d; msWindowLength
0x18019d6c5  mov     [rbx+100h], rax
0x18019d6cc  xor     r8d, r8d; msPeriod
0x18019d6cf  xor     edx, edx; pftDueTime
0x18019d6d1  mov     rcx, rdi; pti
0x18019d6d4  call    cs:__imp_SetThreadpoolTimer
0x18019d6da  mov     rcx, cs:WPP_GLOBAL_Control
0x18019d6e1  cmp     rcx, r15
0x18019d6e4  jz      short loc_18019D706
0x18019d6e6  cmp     byte ptr [rcx+69h], 4
0x18019d6ea  jb      short loc_18019D706
0x18019d6ec  test    byte ptr [rcx+6Ch], 1
0x18019d6f0  jz      short loc_18019D706
0x18019d6f2  mov     rcx, [rcx+60h]
0x18019d6f6  mov     edx, 4Dh ; 'M'
0x18019d6fb  mov     r9, rbx
0x18019d6fe  mov     r8, r12
0x18019d701  call    WPP_SF_q
0x18019d706  mov     rcx, rsi; lpCriticalSection
0x18019d709  call    cs:__imp_LeaveCriticalSection
0x18019d70f  mov     edx, 1; fCancelPendingCallbacks
0x18019d714  mov     rcx, rdi; pti
0x18019d717  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18019d71d  mov     rcx, rsi; lpCriticalSection
0x18019d720  call    cs:__imp_EnterCriticalSection
0x18019d726  mov     rax, [rbx+0F8h]
0x18019d72d  mov     r8, rdi
0x18019d730  mov     rdx, rbx
0x18019d733  mov     [rbx+100h], rdi
0x18019d73a  xor     ecx, ecx
0x18019d73c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019d741  jmp     short loc_18019D7AD
0x18019d743  cmp     [rbx+108h], eax
0x18019d749  jz      short loc_18019D788
0x18019d74b  cmp     rcx, r15
0x18019d74e  jz      short loc_18019D770
0x18019d750  cmp     byte ptr [rcx+69h], 4
0x18019d754  jb      short loc_18019D770
0x18019d756  test    byte ptr [rcx+6Ch], 1
0x18019d75a  jz      short loc_18019D770
0x18019d75c  mov     rcx, [rcx+60h]
0x18019d760  mov     edx, 4Eh ; 'N'
0x18019d765  mov     r9, rbx
0x18019d768  mov     r8, r12
0x18019d76b  call    WPP_SF_q
0x18019d770  mov     rcx, rsi; lpCriticalSection
0x18019d773  call    cs:__imp_LeaveCriticalSection
0x18019d779  mov     edx, 1; fCancelPendingCallbacks
0x18019d77e  xor     ecx, ecx; pti
0x18019d780  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18019d786  jmp     short loc_18019D7B6
0x18019d788  cmp     rcx, r15
0x18019d78b  jz      short loc_18019D7AD
0x18019d78d  cmp     byte ptr [rcx+69h], 4
0x18019d791  jb      short loc_18019D7AD
0x18019d793  test    byte ptr [rcx+6Ch], 1
0x18019d797  jz      short loc_18019D7AD
0x18019d799  mov     rcx, [rcx+60h]
0x18019d79d  mov     edx, 4Fh ; 'O'
0x18019d7a2  mov     r9, rbx
0x18019d7a5  mov     r8, r12
0x18019d7a8  call    WPP_SF_q
0x18019d7ad  mov     rcx, rsi; lpCriticalSection
0x18019d7b0  call    cs:__imp_LeaveCriticalSection
0x18019d7b6  mov     rcx, cs:WPP_GLOBAL_Control
0x18019d7bd  cmp     rcx, r15
0x18019d7c0  jz      short loc_18019D7E2
0x18019d7c2  cmp     byte ptr [rcx+69h], 4
0x18019d7c6  jb      short loc_18019D7E2
0x18019d7c8  test    byte ptr [rcx+6Ch], 1
0x18019d7cc  jz      short loc_18019D7E2
0x18019d7ce  mov     rcx, [rcx+60h]
0x18019d7d2  mov     edx, 50h ; 'P'
0x18019d7d7  xor     r9d, r9d
0x18019d7da  mov     r8, r12
0x18019d7dd  call    WPP_SF_d
0x18019d7e2  add     rsp, 20h
0x18019d7e6  pop     r15
0x18019d7e8  pop     r12
0x18019d7ea  pop     rdi
0x18019d7eb  pop     rsi
0x18019d7ec  pop     rbx
0x18019d7ed  retn
```
