# FreeSubscriber(UPNP_SUBSCRIBER *)

- ea: `0x18002fdc8`
- end: `0x1800300dd`
- name: `?FreeSubscriber@@YAXPEAUUPNP_SUBSCRIBER@@@Z`
- size: `789`
- prototype: `void __fastcall(struct UPNP_SUBSCRIBER *)`
- caller_count: `4`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x18002fc90`
- `0x18002fd78`
- `0x180034374`
- `0x180038dc0`

## callees

- `0x18000db4c`
- `0x18001347c`
- `0x180026edc`
- `0x18002fdc8`
- `0x180039a84`
- `0x18003a584`
- `0x1800454d0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18002fe03`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18002fe14`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18002fe51`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18003008a`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180030097`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800300a4`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800300b1`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18002fe03`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18002fe14`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18002fe51`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18003008a`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180030097`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800300a4`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800300b1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002feec`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003007d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002feec`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003007d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002ff16`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800300cb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002ff16`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800300cb`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18002ff09`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18002ff09`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x18002ff25`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x18002ff25`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18002ff32`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18002ff32`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002ff74`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002ff74`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x18002fff4`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x18002fff4`

## string_xrefs

- `0x180030025`: `FreeSubscriber: DeleteTimerQueueTimer`

## pseudocode

```c
void __fastcall FreeSubscriber(struct UPNP_SUBSCRIBER *a1)
{
  __int64 i; // rbx
  STRSAFE_PCNZWCH v3; // rcx
  __int64 v4; // rsi
  __int64 v5; // rbx
  void *v6; // rbx
  struct _TP_WAIT *v7; // rcx
  char Win32Error; // al
  __int64 v9; // rdx

  if ( a1 )
  {
    if ( *((_QWORD *)a1 + 1) )
    {
      for ( i = 0; (unsigned int)i < *((_DWORD *)a1 + 4); i = (unsigned int)(i + 1) )
        free(*(void **)(*((_QWORD *)a1 + 1) + 8 * i));
      free(*((void **)a1 + 1));
    }
    else
    {
      v3 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      {
LABEL_10:
        if ( *((_QWORD *)a1 + 5) )
        {
          free(*((void **)a1 + 5));
        }
        else
        {
          if ( v3 == (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control || (v3[14] & 1) == 0 )
          {
LABEL_16:
            v4 = *((_QWORD *)a1 + 25);
            if ( v4 )
            {
              do
              {
                ReleaseEventBody(*(struct UPNP_EVENT_BODY **)v4);
                v5 = *(_QWORD *)(v4 + 8);
                operator delete((void *)v4);
                v4 = v5;
              }
              while ( v5 );
              v3 = WPP_GLOBAL_Control;
            }
            v6 = (void *)*((_QWORD *)a1 + 23);
            if ( *((_QWORD *)a1 + 27) )
            {
              if ( v3 != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (*((_DWORD *)v3 + 7) & 0x800) != 0 )
                WPP_SF_(*((_QWORD *)v3 + 2), 26, WPP_2e07143474063d9a59b5fe4ea0113338_Traceguids);
              EnterCriticalSection(&g_csEventApiLock);
              v7 = (struct _TP_WAIT *)*((_QWORD *)a1 + 27);
              *((_QWORD *)a1 + 23) = 0;
              SetThreadpoolWait(v7, 0, 0);
              LeaveCriticalSection(&g_csEventApiLock);
              WaitForThreadpoolWaitCallbacks(*((PTP_WAIT *)a1 + 27), 0);
              CloseThreadpoolWait(*((PTP_WAIT *)a1 + 27));
              *((_QWORD *)a1 + 27) = 0;
              v3 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control
                && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
              {
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_2e07143474063d9a59b5fe4ea0113338_Traceguids);
                v3 = WPP_GLOBAL_Control;
              }
            }
            if ( v6 )
            {
              CloseHandle(v6);
              v3 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control
                && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
              {
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_2e07143474063d9a59b5fe4ea0113338_Traceguids);
                v3 = WPP_GLOBAL_Control;
              }
            }
            if ( !*((_QWORD *)a1 + 28) )
              goto LABEL_47;
            if ( v3 != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (*((_DWORD *)v3 + 7) & 0x800) != 0 )
            {
              WPP_SF_q(*((_QWORD *)v3 + 2), 29, WPP_2e07143474063d9a59b5fe4ea0113338_Traceguids, g_hTimerQ);
              v3 = WPP_GLOBAL_Control;
            }
            if ( g_hTimerQ )
            {
              if ( !DeleteTimerQueueTimer(g_hTimerQ, *((HANDLE *)a1 + 28), (HANDLE)0xFFFFFFFFFFFFFFFFLL) )
              {
                if ( (unsigned int)HrFromLastWin32Error()
                  && WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control
                  && (WPP_GLOBAL_Control[14] & 1) != 0 )
                {
                  Win32Error = HrFromLastWin32Error();
                  WPP_SF_sd(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    30,
                    (unsigned int)WPP_2e07143474063d9a59b5fe4ea0113338_Traceguids,
                    (unsigned int)"FreeSubscriber: DeleteTimerQueueTimer",
                    Win32Error);
                }
                goto LABEL_47;
              }
              v3 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control
                || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0 )
              {
LABEL_47:
                EnterCriticalSection(&g_csEventTimerLock);
                free(*((void **)a1 + 31));
                free(*((void **)a1 + 32));
                free(*((void **)a1 + 29));
                free(*((void **)a1 + 30));
                operator delete(a1);
                LeaveCriticalSection(&g_csEventTimerLock);
                return;
              }
              v9 = 31;
            }
            else
            {
              if ( v3 == (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control || (*((_DWORD *)v3 + 7) & 0x800) == 0 )
                goto LABEL_47;
              v9 = 32;
            }
            WPP_SF_(*((_QWORD *)v3 + 2), v9, WPP_2e07143474063d9a59b5fe4ea0113338_Traceguids);
            goto LABEL_47;
          }
          WPP_SF_(*((_QWORD *)v3 + 2), 25, WPP_2e07143474063d9a59b5fe4ea0113338_Traceguids);
        }
        v3 = WPP_GLOBAL_Control;
        goto LABEL_16;
      }
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_2e07143474063d9a59b5fe4ea0113338_Traceguids);
    }
    v3 = WPP_GLOBAL_Control;
    goto LABEL_10;
  }
}

```

## disassembly

```asm
0x18002fdc8  test    rcx, rcx
0x18002fdcb  jz      locret_1800300DC
0x18002fdd1  push    rbx
0x18002fdd2  push    rsi
0x18002fdd3  push    rdi
0x18002fdd4  push    r14
0x18002fdd6  push    r15
0x18002fdd8  sub     rsp, 30h
0x18002fddc  cmp     qword ptr [rcx+8], 0
0x18002fde1  lea     r15, WPP_2e07143474063d9a59b5fe4ea0113338_Traceguids
0x18002fde8  mov     rdi, rcx
0x18002fdeb  lea     r14, WPP_GLOBAL_Control
0x18002fdf2  jz      short loc_18002FE1C
0x18002fdf4  xor     ebx, ebx
0x18002fdf6  cmp     [rcx+10h], ebx
0x18002fdf9  jbe     short loc_18002FE10
0x18002fdfb  mov     rcx, [rdi+8]
0x18002fdff  mov     rcx, [rcx+rbx*8]; Block
0x18002fe03  call    cs:__imp_free
0x18002fe09  inc     ebx
0x18002fe0b  cmp     ebx, [rdi+10h]
0x18002fe0e  jb      short loc_18002FDFB
0x18002fe10  mov     rcx, [rdi+8]; Block
0x18002fe14  call    cs:__imp_free
0x18002fe1a  jmp     short loc_18002FE3F
0x18002fe1c  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fe23  cmp     rcx, r14
0x18002fe26  jz      short loc_18002FE46
0x18002fe28  test    byte ptr [rcx+1Ch], 1
0x18002fe2c  jz      short loc_18002FE46
0x18002fe2e  mov     rcx, [rcx+10h]
0x18002fe32  mov     edx, 18h
0x18002fe37  mov     r8, r15
0x18002fe3a  call    WPP_SF_
0x18002fe3f  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fe46  cmp     qword ptr [rdi+28h], 0
0x18002fe4b  jz      short loc_18002FE59
0x18002fe4d  mov     rcx, [rdi+28h]; Block
0x18002fe51  call    cs:__imp_free
0x18002fe57  jmp     short loc_18002FE75
0x18002fe59  cmp     rcx, r14
0x18002fe5c  jz      short loc_18002FE7C
0x18002fe5e  test    byte ptr [rcx+1Ch], 1
0x18002fe62  jz      short loc_18002FE7C
0x18002fe64  mov     rcx, [rcx+10h]
0x18002fe68  mov     edx, 19h
0x18002fe6d  mov     r8, r15
0x18002fe70  call    WPP_SF_
0x18002fe75  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fe7c  mov     rsi, [rdi+0C8h]
0x18002fe83  test    rsi, rsi
0x18002fe86  jz      short loc_18002FEB0
0x18002fe88  mov     rcx, [rsi]; struct UPNP_EVENT_BODY *
0x18002fe8b  call    ?ReleaseEventBody@@YAXPEAUUPNP_EVENT_BODY@@@Z; ReleaseEventBody(UPNP_EVENT_BODY *)
0x18002fe90  mov     rbx, [rsi+8]
0x18002fe94  mov     edx, 10h; unsigned __int64
0x18002fe99  mov     rcx, rsi; void *
0x18002fe9c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002fea1  mov     rsi, rbx
0x18002fea4  test    rbx, rbx
0x18002fea7  jnz     short loc_18002FE88
0x18002fea9  mov     rcx, cs:WPP_GLOBAL_Control
0x18002feb0  cmp     qword ptr [rdi+0D8h], 0
0x18002feb8  mov     esi, 800h
0x18002febd  mov     rbx, [rdi+0B8h]
0x18002fec4  jz      loc_18002FF6C
0x18002feca  cmp     rcx, r14
0x18002fecd  jz      short loc_18002FEE5
0x18002fecf  test    [rcx+1Ch], esi
0x18002fed2  jz      short loc_18002FEE5
0x18002fed4  mov     rcx, [rcx+10h]
0x18002fed8  mov     edx, 1Ah
0x18002fedd  mov     r8, r15
0x18002fee0  call    WPP_SF_
0x18002fee5  lea     rcx, ?g_csEventApiLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18002feec  call    cs:__imp_EnterCriticalSection
0x18002fef2  mov     rcx, [rdi+0D8h]; pwa
0x18002fef9  xor     r8d, r8d; pftTimeout
0x18002fefc  xor     edx, edx; h
0x18002fefe  mov     qword ptr [rdi+0B8h], 0
0x18002ff09  call    cs:__imp_SetThreadpoolWait
0x18002ff0f  lea     rcx, ?g_csEventApiLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18002ff16  call    cs:__imp_LeaveCriticalSection
0x18002ff1c  mov     rcx, [rdi+0D8h]; pwa
0x18002ff23  xor     edx, edx; fCancelPendingCallbacks
0x18002ff25  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x18002ff2b  mov     rcx, [rdi+0D8h]; pwa
0x18002ff32  call    cs:__imp_CloseThreadpoolWait
0x18002ff38  mov     qword ptr [rdi+0D8h], 0
0x18002ff43  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ff4a  cmp     rcx, r14
0x18002ff4d  jz      short loc_18002FF6C
0x18002ff4f  test    [rcx+1Ch], esi
0x18002ff52  jz      short loc_18002FF6C
0x18002ff54  mov     rcx, [rcx+10h]
0x18002ff58  mov     edx, 1Bh
0x18002ff5d  mov     r8, r15
0x18002ff60  call    WPP_SF_
0x18002ff65  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ff6c  test    rbx, rbx
0x18002ff6f  jz      short loc_18002FFA3
0x18002ff71  mov     rcx, rbx; hObject
0x18002ff74  call    cs:__imp_CloseHandle
0x18002ff7a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ff81  cmp     rcx, r14
0x18002ff84  jz      short loc_18002FFA3
0x18002ff86  test    [rcx+1Ch], esi
0x18002ff89  jz      short loc_18002FFA3
0x18002ff8b  mov     rcx, [rcx+10h]
0x18002ff8f  mov     edx, 1Ch
0x18002ff94  mov     r8, r15
0x18002ff97  call    WPP_SF_
0x18002ff9c  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ffa3  cmp     qword ptr [rdi+0E0h], 0
0x18002ffab  jz      loc_180030076
0x18002ffb1  cmp     rcx, r14
0x18002ffb4  jz      short loc_18002FFDA
0x18002ffb6  test    [rcx+1Ch], esi
0x18002ffb9  jz      short loc_18002FFDA
0x18002ffbb  mov     r9, cs:?g_hTimerQ@@3PEAXEA; void * g_hTimerQ
0x18002ffc2  mov     edx, 1Dh
0x18002ffc7  mov     rcx, [rcx+10h]
0x18002ffcb  mov     r8, r15
0x18002ffce  call    WPP_SF_q
0x18002ffd3  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ffda  mov     rax, cs:?g_hTimerQ@@3PEAXEA; void * g_hTimerQ
0x18002ffe1  test    rax, rax
0x18002ffe4  jz      short loc_18003005B
0x18002ffe6  mov     rdx, [rdi+0E0h]; Timer
0x18002ffed  or      r8, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x18002fff1  mov     rcx, rax; TimerQueue
0x18002fff4  call    cs:__imp_DeleteTimerQueueTimer
0x18002fffa  test    eax, eax
0x18002fffc  jnz     short loc_180030043
0x18002fffe  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x180030003  test    eax, eax
0x180030005  jz      short loc_180030076
0x180030007  mov     rax, cs:WPP_GLOBAL_Control
0x18003000e  cmp     rax, r14
0x180030011  jz      short loc_180030076
0x180030013  test    byte ptr [rax+1Ch], 1
0x180030017  jz      short loc_180030076
0x180030019  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x18003001e  mov     rcx, cs:WPP_GLOBAL_Control
0x180030025  lea     r9, aFreesubscriber; "FreeSubscriber: DeleteTimerQueueTimer"
0x18003002c  mov     edx, 1Eh
0x180030031  mov     [rsp+58h+var_38], eax
0x180030035  mov     r8, r15
0x180030038  mov     rcx, [rcx+10h]
0x18003003c  call    WPP_SF_sd
0x180030041  jmp     short loc_180030076
0x180030043  mov     rcx, cs:WPP_GLOBAL_Control
0x18003004a  cmp     rcx, r14
0x18003004d  jz      short loc_180030076
0x18003004f  test    [rcx+1Ch], esi
0x180030052  jz      short loc_180030076
0x180030054  mov     edx, 1Fh
0x180030059  jmp     short loc_18003006A
0x18003005b  cmp     rcx, r14
0x18003005e  jz      short loc_180030076
0x180030060  test    [rcx+1Ch], esi
0x180030063  jz      short loc_180030076
0x180030065  mov     edx, 20h ; ' '
0x18003006a  mov     rcx, [rcx+10h]
0x18003006e  mov     r8, r15
0x180030071  call    WPP_SF_
0x180030076  lea     rcx, ?g_csEventTimerLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18003007d  call    cs:__imp_EnterCriticalSection
0x180030083  mov     rcx, [rdi+0F8h]; Block
0x18003008a  call    cs:__imp_free
0x180030090  mov     rcx, [rdi+100h]; Block
0x180030097  call    cs:__imp_free
0x18003009d  mov     rcx, [rdi+0E8h]; Block
0x1800300a4  call    cs:__imp_free
0x1800300aa  mov     rcx, [rdi+0F0h]; Block
0x1800300b1  call    cs:__imp_free
0x1800300b7  mov     edx, 118h; unsigned __int64
0x1800300bc  mov     rcx, rdi; void *
0x1800300bf  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800300c4  lea     rcx, ?g_csEventTimerLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800300cb  call    cs:__imp_LeaveCriticalSection
0x1800300d1  add     rsp, 30h
0x1800300d5  pop     r15
0x1800300d7  pop     r14
0x1800300d9  pop     rdi
0x1800300da  pop     rsi
0x1800300db  pop     rbx
0x1800300dc  retn
```
