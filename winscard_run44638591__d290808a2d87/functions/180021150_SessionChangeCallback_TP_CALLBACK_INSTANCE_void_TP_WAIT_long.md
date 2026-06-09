# SessionChangeCallback(_TP_CALLBACK_INSTANCE *,void *,_TP_WAIT *,long)

- ea: `0x180021150`
- end: `0x180021339`
- name: `?SessionChangeCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z`
- size: `489`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_WAIT Wait, TP_WAIT_RESULT WaitResult)`
- caller_count: `0`
- callee_count: `10`
- tags: `installer_update`

## callees

- `0x180006400`
- `0x180007bc0`
- `0x180007ec0`
- `0x180008d20`
- `0x1800150c0`
- `0x180016040`
- `0x18001991c`
- `0x18001ff14`
- `0x180021150`
- `0x180024b20`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18002129f`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18002130b`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18002129f`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18002130b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800211a6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800212fd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800211a6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800212fd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800211fe`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180021314`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180021327`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800211fe`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180021314`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180021327`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800211c7`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800211e3`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800211f5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800211c7`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800211e3`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800211f5`

## pseudocode

```c
void __fastcall SessionChangeCallback(
        PTP_CALLBACK_INSTANCE Instance,
        PVOID Context,
        PTP_WAIT Wait,
        TP_WAIT_RESULT WaitResult)
{
  int v5; // r9d
  __int64 v6; // rcx
  int v7; // r9d
  PVOID v8; // rcx
  int v9; // r9d
  int v10; // r9d
  void *v11; // rcx

  WppTraceIndent(Instance, 2);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      42,
      (unsigned int)&WPP_ff6f9e331ef63b4fe1fc76f2b0998229_Traceguids,
      v5,
      *((_DWORD *)Context + 18));
  }
  EnterCriticalSection((LPCRITICAL_SECTION)Context);
  if ( RedirectionContextThreadpoolIsSafeForUse((struct _REDIRECTION_CONTEXT *)Context)
    && (SetThreadpoolWait(*((PTP_WAIT *)Context + 14), *((HANDLE *)Context + 13), 0), *((_DWORD *)Context + 18)) )
  {
    SetThreadpoolWait(*((PTP_WAIT *)Context + 19), 0, 0);
    SetThreadpoolWait(*((PTP_WAIT *)Context + 20), 0, 0);
    LeaveCriticalSection((LPCRITICAL_SECTION)Context);
    UpdateConnectionStateForContext((LPCRITICAL_SECTION)Context);
    if ( RedirectionContextIsSessionConnected((struct _REDIRECTION_CONTEXT *)Context) )
    {
      WppTraceIndent(v6, 2);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          45,
          (unsigned int)&WPP_ff6f9e331ef63b4fe1fc76f2b0998229_Traceguids,
          v10,
          *((_DWORD *)Context + 18));
      }
      SetRedirectDisabledValue();
      EnterCriticalSection((LPCRITICAL_SECTION)Context);
      v11 = (void *)*((_QWORD *)Context + 7);
      *((_BYTE *)Context + 43) = 0;
      ResetEvent(v11);
      LeaveCriticalSection((LPCRITICAL_SECTION)Context);
      SetStartedEventWhenSCardSubsytemIsStarted((struct _REDIRECTION_CONTEXT *)Context);
    }
    else
    {
      WppTraceIndent(v6, 2);
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          43,
          (unsigned int)&WPP_ff6f9e331ef63b4fe1fc76f2b0998229_Traceguids,
          v7,
          *((_DWORD *)Context + 18));
      }
      WppTraceIndent(v8, 2);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          44,
          (unsigned int)&WPP_ff6f9e331ef63b4fe1fc76f2b0998229_Traceguids,
          v9,
          *((_DWORD *)Context + 18));
      }
      ResetEvent(*((HANDLE *)Context + 16));
      MarkContextsAsBad(1, *((_DWORD *)Context + 18));
      I_RedirectionContextCancelAndCloseRdpdr((LPCRITICAL_SECTION)Context);
    }
  }
  else
  {
    LeaveCriticalSection((LPCRITICAL_SECTION)Context);
  }
}

```

## disassembly

```asm
0x180021150  mov     [rsp+arg_0], rbx
0x180021155  push    r14
0x180021157  sub     rsp, 30h
0x18002115b  mov     rbx, rdx
0x18002115e  mov     edx, 2
0x180021163  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180021168  mov     rcx, cs:WPP_GLOBAL_Control
0x18002116f  lea     r14, WPP_GLOBAL_Control
0x180021176  cmp     rcx, r14
0x180021179  jz      short loc_1800211A3
0x18002117b  test    byte ptr [rcx+1Ch], 1
0x18002117f  jz      short loc_1800211A3
0x180021181  cmp     byte ptr [rcx+19h], 4
0x180021185  jb      short loc_1800211A3
0x180021187  mov     eax, [rbx+48h]
0x18002118a  lea     r8, WPP_ff6f9e331ef63b4fe1fc76f2b0998229_Traceguids
0x180021191  mov     rcx, [rcx+10h]
0x180021195  mov     edx, 2Ah ; '*'
0x18002119a  mov     [rsp+38h+var_18], eax
0x18002119e  call    WPP_SF_sd
0x1800211a3  mov     rcx, rbx; lpCriticalSection
0x1800211a6  call    cs:__imp_EnterCriticalSection
0x1800211ac  mov     rcx, rbx; struct _REDIRECTION_CONTEXT *
0x1800211af  call    ?RedirectionContextThreadpoolIsSafeForUse@@YA_NPEAU_REDIRECTION_CONTEXT@@@Z; RedirectionContextThreadpoolIsSafeForUse(_REDIRECTION_CONTEXT *)
0x1800211b4  test    al, al
0x1800211b6  jz      loc_180021324
0x1800211bc  mov     rdx, [rbx+68h]; h
0x1800211c0  xor     r8d, r8d; pftTimeout
0x1800211c3  mov     rcx, [rbx+70h]; pwa
0x1800211c7  call    cs:__imp_SetThreadpoolWait
0x1800211cd  cmp     dword ptr [rbx+48h], 0
0x1800211d1  jz      loc_180021324
0x1800211d7  mov     rcx, [rbx+98h]; pwa
0x1800211de  xor     r8d, r8d; pftTimeout
0x1800211e1  xor     edx, edx; h
0x1800211e3  call    cs:__imp_SetThreadpoolWait
0x1800211e9  mov     rcx, [rbx+0A0h]; pwa
0x1800211f0  xor     r8d, r8d; pftTimeout
0x1800211f3  xor     edx, edx; h
0x1800211f5  call    cs:__imp_SetThreadpoolWait
0x1800211fb  mov     rcx, rbx; lpCriticalSection
0x1800211fe  call    cs:__imp_LeaveCriticalSection
0x180021204  mov     rcx, rbx; lpCriticalSection
0x180021207  call    ?UpdateConnectionStateForContext@@YAXPEAU_REDIRECTION_CONTEXT@@@Z; UpdateConnectionStateForContext(_REDIRECTION_CONTEXT *)
0x18002120c  mov     rcx, rbx; struct _REDIRECTION_CONTEXT *
0x18002120f  call    ?RedirectionContextIsSessionConnected@@YA_NPEAU_REDIRECTION_CONTEXT@@@Z; RedirectionContextIsSessionConnected(_REDIRECTION_CONTEXT *)
0x180021214  mov     edx, 2
0x180021219  test    al, al
0x18002121b  jnz     loc_1800212BC
0x180021221  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180021226  mov     rcx, cs:WPP_GLOBAL_Control
0x18002122d  cmp     rcx, r14
0x180021230  jz      short loc_18002125A
0x180021232  test    byte ptr [rcx+1Ch], 1
0x180021236  jz      short loc_18002125A
0x180021238  cmp     byte ptr [rcx+19h], 4
0x18002123c  jb      short loc_18002125A
0x18002123e  mov     eax, [rbx+48h]
0x180021241  lea     r8, WPP_ff6f9e331ef63b4fe1fc76f2b0998229_Traceguids
0x180021248  mov     rcx, [rcx+10h]
0x18002124c  mov     edx, 2Bh ; '+'
0x180021251  mov     [rsp+38h+var_18], eax
0x180021255  call    WPP_SF_sd
0x18002125a  mov     edx, 2
0x18002125f  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180021264  mov     rcx, cs:WPP_GLOBAL_Control
0x18002126b  cmp     rcx, r14
0x18002126e  jz      short loc_180021298
0x180021270  test    byte ptr [rcx+1Ch], 1
0x180021274  jz      short loc_180021298
0x180021276  cmp     byte ptr [rcx+19h], 4
0x18002127a  jb      short loc_180021298
0x18002127c  mov     eax, [rbx+48h]
0x18002127f  lea     r8, WPP_ff6f9e331ef63b4fe1fc76f2b0998229_Traceguids
0x180021286  mov     rcx, [rcx+10h]
0x18002128a  mov     edx, 2Ch ; ','
0x18002128f  mov     [rsp+38h+var_18], eax
0x180021293  call    WPP_SF_sd
0x180021298  mov     rcx, [rbx+80h]; hEvent
0x18002129f  call    cs:__imp_ResetEvent
0x1800212a5  mov     edx, [rbx+48h]; unsigned int
0x1800212a8  mov     ecx, 1; int
0x1800212ad  call    ?MarkContextsAsBad@@YAXHK@Z; MarkContextsAsBad(int,ulong)
0x1800212b2  mov     rcx, rbx; lpCriticalSection
0x1800212b5  call    ?I_RedirectionContextCancelAndCloseRdpdr@@YAXPEAU_REDIRECTION_CONTEXT@@@Z; I_RedirectionContextCancelAndCloseRdpdr(_REDIRECTION_CONTEXT *)
0x1800212ba  jmp     short loc_18002132D
0x1800212bc  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x1800212c1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800212c8  cmp     rcx, r14
0x1800212cb  jz      short loc_1800212F5
0x1800212cd  test    byte ptr [rcx+1Ch], 1
0x1800212d1  jz      short loc_1800212F5
0x1800212d3  cmp     byte ptr [rcx+19h], 4
0x1800212d7  jb      short loc_1800212F5
0x1800212d9  mov     eax, [rbx+48h]
0x1800212dc  lea     r8, WPP_ff6f9e331ef63b4fe1fc76f2b0998229_Traceguids
0x1800212e3  mov     rcx, [rcx+10h]
0x1800212e7  mov     edx, 2Dh ; '-'
0x1800212ec  mov     [rsp+38h+var_18], eax
0x1800212f0  call    WPP_SF_sd
0x1800212f5  call    ?SetRedirectDisabledValue@@YAXXZ; SetRedirectDisabledValue(void)
0x1800212fa  mov     rcx, rbx; lpCriticalSection
0x1800212fd  call    cs:__imp_EnterCriticalSection
0x180021303  mov     rcx, [rbx+38h]; hEvent
0x180021307  mov     byte ptr [rbx+2Bh], 0
0x18002130b  call    cs:__imp_ResetEvent
0x180021311  mov     rcx, rbx; lpCriticalSection
0x180021314  call    cs:__imp_LeaveCriticalSection
0x18002131a  mov     rcx, rbx; struct _REDIRECTION_CONTEXT *
0x18002131d  call    ?SetStartedEventWhenSCardSubsytemIsStarted@@YAHPEAU_REDIRECTION_CONTEXT@@@Z; SetStartedEventWhenSCardSubsytemIsStarted(_REDIRECTION_CONTEXT *)
0x180021322  jmp     short loc_18002132D
0x180021324  mov     rcx, rbx; lpCriticalSection
0x180021327  call    cs:__imp_LeaveCriticalSection
0x18002132d  mov     rbx, [rsp+38h+arg_0]
0x180021332  add     rsp, 30h
0x180021336  pop     r14
0x180021338  retn
```
