# MSMConnectCompletion(ulong,void *,void *,ulong,ulong,ulong (*)(void *,void *,ulong,ulong))

- ea: `0x18002589c`
- end: `0x180025a5c`
- name: `?MSMConnectCompletion@@YAKKPEAX0KKP6AK00KK@Z@Z`
- size: `448`
- prototype: `unsigned int __fastcall(unsigned int, void *, void *, unsigned int, unsigned int, unsigned int (*)(void *, void *, unsigned int, unsigned int))`
- caller_count: `3`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18001d8ac`
- `0x1800363c0`
- `0x180058fc8`

## callees

- `0x18000892c`
- `0x180008998`
- `0x18000a4e0`
- `0x18000c730`
- `0x18000e620`
- `0x1800163e0`
- `0x18002589c`
- `0x180025a70`
- `0x180056268`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800259e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800259e1`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x180025944`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x180025944`

## string_xrefs

- `0x1800258fe`: `MSMConnectCompletion`
- `0x1800259ba`: `MSMConnectCompletion`

## pseudocode

```c
__int64 __fastcall MSMConnectCompletion(
        int a1,
        void *a2,
        void *a3,
        int a4,
        unsigned int a5,
        unsigned int (*a6)(void *, void *, unsigned int, unsigned int))
{
  DWORD MSMSecMemory; // eax
  _QWORD *v11; // rdi
  DWORD v12; // ebx
  int v14; // esi
  _QWORD *v15; // rcx
  __int64 v16; // rdx
  PVOID Context[9]; // [rsp+20h] [rbp-48h] BYREF

  Context[0] = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 40, &WPP_b56916f94f50376d7382066de30fa1b3_Traceguids);
  MSMSecMemory = AllocateMSMSecMemory(0x28u);
  v11 = Context[0];
  v12 = MSMSecMemory;
  if ( MSMSecMemory )
  {
    v14 = 0;
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    {
      v16 = 41;
LABEL_19:
      WPP_SF_d(v15[7], v16, &WPP_b56916f94f50376d7382066de30fa1b3_Traceguids, MSMSecMemory);
    }
  }
  else
  {
    *(_DWORD *)Context[0] = a1;
    v11[1] = a2;
    v11[2] = a3;
    *((_DWORD *)v11 + 6) = a4;
    *((_DWORD *)v11 + 7) = a5;
    v11[4] = a6;
    IncThreadCountEx("MSMConnectCompletion", 327);
    NetTraceMarkContextActivityStart(v11, 0x11u);
    if ( QueueUserWorkItem(ConnectCompletionWorker, v11, 0) )
      goto LABEL_4;
    MSMSecMemory = GetLastError();
    v12 = MSMSecMemory;
    if ( !MSMSecMemory )
      goto LABEL_4;
    v14 = 1;
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    {
      v16 = 42;
      goto LABEL_19;
    }
  }
  FreeMSMSecMemory(Context);
  if ( v14 )
    DecThreadCountEx("MSMConnectCompletion", 351);
LABEL_4:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 43, &WPP_b56916f94f50376d7382066de30fa1b3_Traceguids, v12);
  return v12;
}

```

## disassembly

```asm
0x18002589c  push    rbx
0x18002589e  push    rbp
0x18002589f  push    rsi
0x1800258a0  push    rdi
0x1800258a1  push    r12
0x1800258a3  push    r14
0x1800258a5  push    r15
0x1800258a7  sub     rsp, 30h
0x1800258ab  mov     esi, r9d
0x1800258ae  mov     [rsp+68h+Context], 0
0x1800258b7  mov     rbp, r8
0x1800258ba  mov     r14, rdx
0x1800258bd  mov     r15d, ecx
0x1800258c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800258c7  lea     r12, WPP_GLOBAL_Control
0x1800258ce  mov     ebx, 28h ; '('
0x1800258d3  cmp     rcx, r12
0x1800258d6  jnz     loc_180025983
0x1800258dc  lea     rdx, [rsp+68h+Context]
0x1800258e1  mov     ecx, ebx; dwBytes
0x1800258e3  call    AllocateMSMSecMemory
0x1800258e8  mov     rdi, [rsp+68h+Context]
0x1800258ed  mov     ebx, eax
0x1800258ef  test    eax, eax
0x1800258f1  jnz     loc_1800259C8
0x1800258f7  mov     eax, [rsp+68h+arg_20]
0x1800258fe  lea     rcx, aMsmconnectcomp; "MSMConnectCompletion"
0x180025905  mov     [rdi], r15d
0x180025908  mov     edx, 147h; int
0x18002590d  mov     [rdi+8], r14
0x180025911  mov     [rdi+10h], rbp
0x180025915  mov     [rdi+18h], esi
0x180025918  mov     [rdi+1Ch], eax
0x18002591b  mov     rax, [rsp+68h+arg_28]
0x180025923  mov     [rdi+20h], rax
0x180025927  call    ?IncThreadCountEx@@YAXPEBDH@Z; IncThreadCountEx(char const *,int)
0x18002592c  lea     edx, [rbx+11h]; unsigned int
0x18002592f  mov     rcx, rdi; void *
0x180025932  call    ?NetTraceMarkContextActivityStart@@YAXPEAXI@Z; NetTraceMarkContextActivityStart(void *,uint)
0x180025937  xor     r8d, r8d; Flags
0x18002593a  lea     rcx, ?ConnectCompletionWorker@@YAKPEAX@Z; Function
0x180025941  mov     rdx, rdi; Context
0x180025944  call    cs:__imp_QueueUserWorkItem
0x18002594b  nop     dword ptr [rax+rax+00h]
0x180025950  test    eax, eax
0x180025952  jz      loc_1800259E1
0x180025958  mov     rcx, cs:WPP_GLOBAL_Control
0x18002595f  cmp     rcx, r12
0x180025962  jz      short loc_180025971
0x180025964  test    dword ptr [rcx+44h], 100h
0x18002596b  jnz     loc_180025A3F
0x180025971  mov     eax, ebx
0x180025973  add     rsp, 30h
0x180025977  pop     r15
0x180025979  pop     r14
0x18002597b  pop     r12
0x18002597d  pop     rdi
0x18002597e  pop     rsi
0x18002597f  pop     rbp
0x180025980  pop     rbx
0x180025981  retn
0x180025983  test    dword ptr [rcx+44h], 100h
0x18002598a  jz      loc_1800258DC
0x180025990  mov     rcx, [rcx+38h]
0x180025994  lea     r8, WPP_b56916f94f50376d7382066de30fa1b3_Traceguids
0x18002599b  mov     edx, ebx
0x18002599d  call    WPP_SF_
0x1800259a2  jmp     loc_1800258DC
0x1800259a7  lea     rcx, [rsp+68h+Context]
0x1800259ac  call    FreeMSMSecMemory
0x1800259b1  test    esi, esi
0x1800259b3  jz      short loc_180025958
0x1800259b5  mov     edx, 15Fh; int
0x1800259ba  lea     rcx, aMsmconnectcomp; "MSMConnectCompletion"
0x1800259c1  call    ?DecThreadCountEx@@YAXPEBDH@Z; DecThreadCountEx(char const *,int)
0x1800259c6  jmp     short loc_180025958
0x1800259c8  xor     esi, esi
0x1800259ca  mov     rcx, cs:WPP_GLOBAL_Control
0x1800259d1  cmp     rcx, r12
0x1800259d4  jz      short loc_180025A24
0x1800259d6  test    byte ptr [rcx+44h], 1
0x1800259da  jz      short loc_180025A24
0x1800259dc  lea     edx, [rsi+29h]
0x1800259df  jmp     short loc_180025A11
0x1800259e1  call    cs:__imp_GetLastError
0x1800259e8  nop     dword ptr [rax+rax+00h]
0x1800259ed  mov     ebx, eax
0x1800259ef  test    eax, eax
0x1800259f1  jz      loc_180025958
0x1800259f7  mov     esi, 1
0x1800259fc  mov     rcx, cs:WPP_GLOBAL_Control
0x180025a03  cmp     rcx, r12
0x180025a06  jz      short loc_180025A24
0x180025a08  test    [rcx+44h], sil
0x180025a0c  jz      short loc_180025A24
0x180025a0e  lea     edx, [rsi+29h]
0x180025a11  mov     rcx, [rcx+38h]
0x180025a15  lea     r8, WPP_b56916f94f50376d7382066de30fa1b3_Traceguids
0x180025a1c  mov     r9d, eax
0x180025a1f  call    WPP_SF_d
0x180025a24  test    rdi, rdi
0x180025a27  jz      loc_1800259A7
0x180025a2d  mov     edx, 11h; unsigned int
0x180025a32  mov     rcx, rdi; void *
0x180025a35  call    ?NetTraceMarkContextActivityStop@@YAXPEAXI@Z; NetTraceMarkContextActivityStop(void *,uint)
0x180025a3a  jmp     loc_1800259A7
0x180025a3f  mov     rcx, [rcx+38h]
0x180025a43  lea     r8, WPP_b56916f94f50376d7382066de30fa1b3_Traceguids
0x180025a4a  mov     edx, 2Bh ; '+'
0x180025a4f  mov     r9d, ebx
0x180025a52  call    WPP_SF_d
0x180025a57  jmp     loc_180025971
```
