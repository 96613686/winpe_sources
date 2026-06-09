# FreeSubscriber(UPNP_SUBSCRIBER *)

- ea: `0x1800318ec`
- end: `0x180031c62`
- name: `?FreeSubscriber@@YAXPEAUUPNP_SUBSCRIBER@@@Z`
- size: `886`
- prototype: `void __fastcall(struct UPNP_SUBSCRIBER *)`
- caller_count: `4`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x180031790`
- `0x180031894`
- `0x180036354`
- `0x18003b210`

## callees

- `0x1800074dc`
- `0x1800200f4`
- `0x180028060`
- `0x1800318ec`
- `0x18003c018`
- `0x18003cb84`
- `0x1800480c0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180031927`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18003193e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180031981`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180031bf0`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180031c03`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180031c16`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180031c29`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180031927`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18003193e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180031981`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180031bf0`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180031c03`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180031c16`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180031c29`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180031a22`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180031bdd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180031a22`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180031bdd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180031a58`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180031c49`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180031a58`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180031c49`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180031a45`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180031a45`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x180031a6d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x180031a6d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x180031a80`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x180031a80`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180031ac8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180031ac8`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x180031b4e`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x180031b4e`

## string_xrefs

- `0x180031b85`: `FreeSubscriber: DeleteTimerQueueTimer`

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
                operator delete((void *)v4, 0x10u);
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
                operator delete(a1, 0x118u);
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
0x1800318ec  test    rcx, rcx
0x1800318ef  jz      locret_180031C60
0x1800318f5  push    rbx
0x1800318f6  push    rsi
0x1800318f7  push    rdi
0x1800318f8  push    r14
0x1800318fa  push    r15
0x1800318fc  sub     rsp, 30h
0x180031900  cmp     qword ptr [rcx+8], 0
0x180031905  lea     r15, WPP_2e07143474063d9a59b5fe4ea0113338_Traceguids
0x18003190c  mov     rdi, rcx
0x18003190f  lea     r14, WPP_GLOBAL_Control
0x180031916  jz      short loc_18003194C
0x180031918  xor     ebx, ebx
0x18003191a  cmp     [rcx+10h], ebx
0x18003191d  jbe     short loc_18003193A
0x18003191f  mov     rcx, [rdi+8]
0x180031923  mov     rcx, [rcx+rbx*8]; Block
0x180031927  call    cs:__imp_free
0x18003192e  nop     dword ptr [rax+rax+00h]
0x180031933  inc     ebx
0x180031935  cmp     ebx, [rdi+10h]
0x180031938  jb      short loc_18003191F
0x18003193a  mov     rcx, [rdi+8]; Block
0x18003193e  call    cs:__imp_free
0x180031945  nop     dword ptr [rax+rax+00h]
0x18003194a  jmp     short loc_18003196F
0x18003194c  mov     rcx, cs:WPP_GLOBAL_Control
0x180031953  cmp     rcx, r14
0x180031956  jz      short loc_180031976
0x180031958  test    byte ptr [rcx+1Ch], 1
0x18003195c  jz      short loc_180031976
0x18003195e  mov     rcx, [rcx+10h]
0x180031962  mov     edx, 18h
0x180031967  mov     r8, r15
0x18003196a  call    WPP_SF_
0x18003196f  mov     rcx, cs:WPP_GLOBAL_Control
0x180031976  cmp     qword ptr [rdi+28h], 0
0x18003197b  jz      short loc_18003198F
0x18003197d  mov     rcx, [rdi+28h]; Block
0x180031981  call    cs:__imp_free
0x180031988  nop     dword ptr [rax+rax+00h]
0x18003198d  jmp     short loc_1800319AB
0x18003198f  cmp     rcx, r14
0x180031992  jz      short loc_1800319B2
0x180031994  test    byte ptr [rcx+1Ch], 1
0x180031998  jz      short loc_1800319B2
0x18003199a  mov     rcx, [rcx+10h]
0x18003199e  mov     edx, 19h
0x1800319a3  mov     r8, r15
0x1800319a6  call    WPP_SF_
0x1800319ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1800319b2  mov     rsi, [rdi+0C8h]
0x1800319b9  test    rsi, rsi
0x1800319bc  jz      short loc_1800319E6
0x1800319be  mov     rcx, [rsi]; struct UPNP_EVENT_BODY *
0x1800319c1  call    ?ReleaseEventBody@@YAXPEAUUPNP_EVENT_BODY@@@Z; ReleaseEventBody(UPNP_EVENT_BODY *)
0x1800319c6  mov     rbx, [rsi+8]
0x1800319ca  mov     edx, 10h; unsigned __int64
0x1800319cf  mov     rcx, rsi; void *
0x1800319d2  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800319d7  mov     rsi, rbx
0x1800319da  test    rbx, rbx
0x1800319dd  jnz     short loc_1800319BE
0x1800319df  mov     rcx, cs:WPP_GLOBAL_Control
0x1800319e6  cmp     qword ptr [rdi+0D8h], 0
0x1800319ee  mov     esi, 800h
0x1800319f3  mov     rbx, [rdi+0B8h]
0x1800319fa  jz      loc_180031AC0
0x180031a00  cmp     rcx, r14
0x180031a03  jz      short loc_180031A1B
0x180031a05  test    [rcx+1Ch], esi
0x180031a08  jz      short loc_180031A1B
0x180031a0a  mov     rcx, [rcx+10h]
0x180031a0e  mov     edx, 1Ah
0x180031a13  mov     r8, r15
0x180031a16  call    WPP_SF_
0x180031a1b  lea     rcx, ?g_csEventApiLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180031a22  call    cs:__imp_EnterCriticalSection
0x180031a29  nop     dword ptr [rax+rax+00h]
0x180031a2e  mov     rcx, [rdi+0D8h]; pwa
0x180031a35  xor     r8d, r8d; pftTimeout
0x180031a38  xor     edx, edx; h
0x180031a3a  mov     qword ptr [rdi+0B8h], 0
0x180031a45  call    cs:__imp_SetThreadpoolWait
0x180031a4c  nop     dword ptr [rax+rax+00h]
0x180031a51  lea     rcx, ?g_csEventApiLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180031a58  call    cs:__imp_LeaveCriticalSection
0x180031a5f  nop     dword ptr [rax+rax+00h]
0x180031a64  mov     rcx, [rdi+0D8h]; pwa
0x180031a6b  xor     edx, edx; fCancelPendingCallbacks
0x180031a6d  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x180031a74  nop     dword ptr [rax+rax+00h]
0x180031a79  mov     rcx, [rdi+0D8h]; pwa
0x180031a80  call    cs:__imp_CloseThreadpoolWait
0x180031a87  nop     dword ptr [rax+rax+00h]
0x180031a8c  mov     qword ptr [rdi+0D8h], 0
0x180031a97  mov     rcx, cs:WPP_GLOBAL_Control
0x180031a9e  cmp     rcx, r14
0x180031aa1  jz      short loc_180031AC0
0x180031aa3  test    [rcx+1Ch], esi
0x180031aa6  jz      short loc_180031AC0
0x180031aa8  mov     rcx, [rcx+10h]
0x180031aac  mov     edx, 1Bh
0x180031ab1  mov     r8, r15
0x180031ab4  call    WPP_SF_
0x180031ab9  mov     rcx, cs:WPP_GLOBAL_Control
0x180031ac0  test    rbx, rbx
0x180031ac3  jz      short loc_180031AFD
0x180031ac5  mov     rcx, rbx; hObject
0x180031ac8  call    cs:__imp_CloseHandle
0x180031acf  nop     dword ptr [rax+rax+00h]
0x180031ad4  mov     rcx, cs:WPP_GLOBAL_Control
0x180031adb  cmp     rcx, r14
0x180031ade  jz      short loc_180031AFD
0x180031ae0  test    [rcx+1Ch], esi
0x180031ae3  jz      short loc_180031AFD
0x180031ae5  mov     rcx, [rcx+10h]
0x180031ae9  mov     edx, 1Ch
0x180031aee  mov     r8, r15
0x180031af1  call    WPP_SF_
0x180031af6  mov     rcx, cs:WPP_GLOBAL_Control
0x180031afd  cmp     qword ptr [rdi+0E0h], 0
0x180031b05  jz      loc_180031BD6
0x180031b0b  cmp     rcx, r14
0x180031b0e  jz      short loc_180031B34
0x180031b10  test    [rcx+1Ch], esi
0x180031b13  jz      short loc_180031B34
0x180031b15  mov     r9, cs:?g_hTimerQ@@3PEAXEA; void * g_hTimerQ
0x180031b1c  mov     edx, 1Dh
0x180031b21  mov     rcx, [rcx+10h]
0x180031b25  mov     r8, r15
0x180031b28  call    WPP_SF_q
0x180031b2d  mov     rcx, cs:WPP_GLOBAL_Control
0x180031b34  mov     rax, cs:?g_hTimerQ@@3PEAXEA; void * g_hTimerQ
0x180031b3b  test    rax, rax
0x180031b3e  jz      short loc_180031BBB
0x180031b40  mov     rdx, [rdi+0E0h]; Timer
0x180031b47  or      r8, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x180031b4b  mov     rcx, rax; TimerQueue
0x180031b4e  call    cs:__imp_DeleteTimerQueueTimer
0x180031b55  nop     dword ptr [rax+rax+00h]
0x180031b5a  test    eax, eax
0x180031b5c  jnz     short loc_180031BA3
0x180031b5e  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x180031b63  test    eax, eax
0x180031b65  jz      short loc_180031BD6
0x180031b67  mov     rax, cs:WPP_GLOBAL_Control
0x180031b6e  cmp     rax, r14
0x180031b71  jz      short loc_180031BD6
0x180031b73  test    byte ptr [rax+1Ch], 1
0x180031b77  jz      short loc_180031BD6
0x180031b79  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x180031b7e  mov     rcx, cs:WPP_GLOBAL_Control
0x180031b85  lea     r9, aFreesubscriber; "FreeSubscriber: DeleteTimerQueueTimer"
0x180031b8c  mov     edx, 1Eh
0x180031b91  mov     [rsp+58h+var_38], eax
0x180031b95  mov     r8, r15
0x180031b98  mov     rcx, [rcx+10h]
0x180031b9c  call    WPP_SF_sd
0x180031ba1  jmp     short loc_180031BD6
0x180031ba3  mov     rcx, cs:WPP_GLOBAL_Control
0x180031baa  cmp     rcx, r14
0x180031bad  jz      short loc_180031BD6
0x180031baf  test    [rcx+1Ch], esi
0x180031bb2  jz      short loc_180031BD6
0x180031bb4  mov     edx, 1Fh
0x180031bb9  jmp     short loc_180031BCA
0x180031bbb  cmp     rcx, r14
0x180031bbe  jz      short loc_180031BD6
0x180031bc0  test    [rcx+1Ch], esi
0x180031bc3  jz      short loc_180031BD6
0x180031bc5  mov     edx, 20h ; ' '
0x180031bca  mov     rcx, [rcx+10h]
0x180031bce  mov     r8, r15
0x180031bd1  call    WPP_SF_
0x180031bd6  lea     rcx, ?g_csEventTimerLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180031bdd  call    cs:__imp_EnterCriticalSection
0x180031be4  nop     dword ptr [rax+rax+00h]
0x180031be9  mov     rcx, [rdi+0F8h]; Block
0x180031bf0  call    cs:__imp_free
0x180031bf7  nop     dword ptr [rax+rax+00h]
0x180031bfc  mov     rcx, [rdi+100h]; Block
0x180031c03  call    cs:__imp_free
0x180031c0a  nop     dword ptr [rax+rax+00h]
0x180031c0f  mov     rcx, [rdi+0E8h]; Block
0x180031c16  call    cs:__imp_free
0x180031c1d  nop     dword ptr [rax+rax+00h]
0x180031c22  mov     rcx, [rdi+0F0h]; Block
0x180031c29  call    cs:__imp_free
0x180031c30  nop     dword ptr [rax+rax+00h]
0x180031c35  mov     edx, 118h; unsigned __int64
0x180031c3a  mov     rcx, rdi; void *
0x180031c3d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180031c42  lea     rcx, ?g_csEventTimerLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180031c49  call    cs:__imp_LeaveCriticalSection
0x180031c50  nop     dword ptr [rax+rax+00h]
0x180031c55  add     rsp, 30h
0x180031c59  pop     r15
0x180031c5b  pop     r14
0x180031c5d  pop     rdi
0x180031c5e  pop     rsi
0x180031c5f  pop     rbx
0x180031c60  retn
```
