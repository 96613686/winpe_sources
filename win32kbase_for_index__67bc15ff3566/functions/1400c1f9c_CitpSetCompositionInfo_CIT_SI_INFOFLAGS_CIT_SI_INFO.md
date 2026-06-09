# CitpSetCompositionInfo(_CIT_SI_INFOFLAGS *,_CIT_SI_INFO *)

- ea: `0x1400c1f9c`
- end: `0x1400c2382`
- name: `?CitpSetCompositionInfo@@YAJPEAT_CIT_SI_INFOFLAGS@@PEAT_CIT_SI_INFO@@@Z`
- size: `998`
- prototype: `__int64 __fastcall(union _CIT_SI_INFOFLAGS *, union _CIT_SI_INFO *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1400c1ec0`

## callees

- `0x140037020`
- `0x1400371c0`
- `0x14004dfb0`
- `0x14006a6d0`
- `0x1400c1b64`
- `0x1400c1f9c`
- `0x1400c3dd4`
- `0x1400e63bc`
- `0x1401343c8`
- `0x1401888b4`
- `0x1401b10e8`

## import_xrefs

- `ntoskrnl!ProbeForRead` at `0x1400c204a`
- `ntoskrnl!ProbeForRead` at `0x1400c204a`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x1400c219a`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x1400c219a`
- `ntoskrnl!PsUpdateComponentPower` at `0x1400c20f3`
- `ntoskrnl!PsUpdateComponentPower` at `0x1400c21d8`
- `ntoskrnl!PsUpdateComponentPower` at `0x1400c20f3`
- `ntoskrnl!PsUpdateComponentPower` at `0x1400c21d8`
- `ntoskrnl!PsGetProcessSequenceNumber` at `0x1400c217b`
- `ntoskrnl!PsGetProcessSequenceNumber` at `0x1400c217b`
- `ntoskrnl!PsLookupProcessByProcessId` at `0x1400c2163`
- `ntoskrnl!PsLookupProcessByProcessId` at `0x1400c2163`
- `ntoskrnl!ObfDereferenceObject` at `0x1400c2222`
- `ntoskrnl!ObfDereferenceObject` at `0x1400c2222`
- `ntoskrnl!PsGetProcessWin32Process` at `0x1400c210d`
- `ntoskrnl!PsGetProcessWin32Process` at `0x1400c21ec`
- `ntoskrnl!PsGetProcessWin32Process` at `0x1400c210d`
- `ntoskrnl!PsGetProcessWin32Process` at `0x1400c21ec`
- `WIN32K!W32GetUserSessionState` at `0x1400c1fbc`
- `WIN32K!W32GetUserSessionState` at `0x1400c1fbc`

## pseudocode

```c
__int64 __fastcall CitpSetCompositionInfo(union _CIT_SI_INFOFLAGS *a1, volatile void **a2, __int64 a3)
{
  struct _CIT_IMPACT_CONTEXT *v5; // r15
  const char *v6; // rdx
  char *v8; // r12
  __int64 v9; // r14
  unsigned __int16 i; // di
  __int64 ProcessWin32Process; // rax
  struct _CIT_PROCESS **v12; // rbx
  int ProcessSessionId; // ebx
  __int64 v14; // rax
  struct _CIT_PROCESS **v15; // rbx
  struct _CIT_INTERACTION_SUMMARY *v16; // rax
  struct _CIT_INTERACTION_SUMMARY *v17; // r9
  struct _CIT_INTERACTION_SUMMARY *v18; // rax
  struct _CIT_INTERACTION_SUMMARY *v19; // r9
  __int128 v20; // [rsp+20h] [rbp-A8h]
  __int64 v21; // [rsp+30h] [rbp-98h]
  _BYTE v22[8]; // [rsp+50h] [rbp-78h] BYREF
  int v23; // [rsp+58h] [rbp-70h]
  char v24; // [rsp+64h] [rbp-64h]
  __int64 v25; // [rsp+68h] [rbp-60h]
  __int64 v26; // [rsp+80h] [rbp-48h]
  PEPROCESS Process; // [rsp+E0h] [rbp+18h] BYREF

  v5 = *(struct _CIT_IMPACT_CONTEXT **)(*(_QWORD *)(W32GetUserSessionState(a1, a2, a3) + 18992) + 32LL);
  if ( !(unsigned int)UserIsCurrentProcessDwm() )
    return 3221225506LL;
  v8 = (char *)*a2;
  v9 = *((unsigned __int16 *)a1 + 1);
  for ( i = 0; ; ++i )
  {
    if ( i >= (unsigned __int16)v9 )
      return 0;
    if ( (unsigned __int64)(24 * v9 - 1) > 0xFFFE )
      break;
    ProbeForRead(v8, 1u, 4u);
    v20 = *(_OWORD *)&v8[24 * i];
    v21 = *(_QWORD *)&v8[24 * i + 16];
    if ( (_QWORD)v20 )
    {
      if ( (unsigned int)Feature_ResponsiblePid__private_IsEnabledDeviceUsageNoInline() )
      {
        CLockProcessByPid::CLockProcessByPid(v22, (int)v21, 3, *((_QWORD *)&v20 + 1));
        if ( v23 >= 0 )
        {
          PsUpdateComponentPower(v25, 7);
          if ( v25 )
          {
            ProcessWin32Process = PsGetProcessWin32Process(v25);
            v12 = (struct _CIT_PROCESS **)ProcessWin32Process;
            if ( ProcessWin32Process )
              v12 = (struct _CIT_PROCESS **)(-(__int64)(*(_QWORD *)ProcessWin32Process != 0) & ProcessWin32Process);
          }
          else
          {
            v12 = 0;
          }
          if ( v12 )
          {
            if ( CitpProcessEnsureContext((struct tagPROCESSINFO *)v12) )
            {
              v16 = CitpInteractionSummaryEnsure(v5, v12[114], 4u);
              v17 = v16;
              if ( v16 )
              {
                if ( (_WORD)v20 )
                  CitpStatIncrement((unsigned __int16 *)v16 + 54, 1u);
                if ( WORD1(v20) )
                  CitpStatIncrement((unsigned __int16 *)v17 + 55, 1u);
                if ( WORD2(v20) )
                  CitpStatIncrement((unsigned __int16 *)v17 + 56, 1u);
              }
            }
          }
        }
        if ( v25 )
        {
          if ( (v24 & 8) != 0 )
            *((_QWORD *)PtiCurrent() + 47) = v26;
          CLockProcessByPid::_Cleanup((CLockProcessByPid *)v22);
        }
      }
      else
      {
        Process = 0;
        if ( PsLookupProcessByProcessId((HANDLE)(int)v21, &Process) >= 0 )
        {
          if ( PsGetProcessSequenceNumber(Process) == *((_QWORD *)&v20 + 1) )
          {
            ProcessSessionId = PsGetProcessSessionIdEx(Process);
            if ( ProcessSessionId == (unsigned int)W32GetCurrentWin32kSessionId() )
            {
              PsUpdateComponentPower(Process, 7);
              v14 = PsGetProcessWin32Process(Process);
              v15 = (struct _CIT_PROCESS **)v14;
              if ( v14 )
                v15 = (struct _CIT_PROCESS **)(-(__int64)(*(_QWORD *)v14 != 0) & v14);
              if ( v15 )
              {
                if ( CitpProcessEnsureContext((struct tagPROCESSINFO *)v15) )
                {
                  v18 = CitpInteractionSummaryEnsure(v5, v15[114], 4u);
                  v19 = v18;
                  if ( v18 )
                  {
                    if ( (_WORD)v20 )
                      CitpStatIncrement((unsigned __int16 *)v18 + 54, 1u);
                    if ( WORD1(v20) )
                      CitpStatIncrement((unsigned __int16 *)v19 + 55, 1u);
                    if ( WORD2(v20) )
                      CitpStatIncrement((unsigned __int16 *)v19 + 56, 1u);
                  }
                }
              }
            }
          }
          ObfDereferenceObject(Process);
        }
      }
    }
  }
  CitpLogFailureWorker(-1073741823, v6, 0x11F5u);
  return 3221225473LL;
}

```

## disassembly

```asm
0x1400c1f9c  mov     [rsp+arg_0], rbx
0x1400c1fa1  mov     [rsp+arg_8], rsi
0x1400c1fa6  push    rdi
0x1400c1fa7  push    r12
0x1400c1fa9  push    r13
0x1400c1fab  push    r14
0x1400c1fad  push    r15
0x1400c1faf  sub     rsp, 0A0h
0x1400c1fb6  mov     rbx, rdx
0x1400c1fb9  mov     rdi, rcx
0x1400c1fbc  call    cs:__imp_W32GetUserSessionState
0x1400c1fc3  nop     dword ptr [rax+rax+00h]
0x1400c1fc8  mov     r8, [rax+4A30h]
0x1400c1fcf  mov     r15, [r8+20h]
0x1400c1fd3  call    UserIsCurrentProcessDwm
0x1400c1fd8  xor     r13d, r13d
0x1400c1fdb  test    eax, eax
0x1400c1fdd  jnz     short loc_1400C2002
0x1400c1fdf  mov     eax, 0C0000022h
0x1400c1fe4  lea     r11, [rsp+0C8h+var_28]
0x1400c1fec  mov     rbx, [r11+30h]
0x1400c1ff0  mov     rsi, [r11+38h]
0x1400c1ff4  mov     rsp, r11
0x1400c1ff7  pop     r15
0x1400c1ff9  pop     r14
0x1400c1ffb  pop     r13
0x1400c1ffd  pop     r12
0x1400c1fff  pop     rdi
0x1400c2000  retn
0x1400c2002  mov     r12, [rbx]
0x1400c2005  movzx   r14d, word ptr [rdi+2]
0x1400c200a  lea     rsi, [r14+r14*2]
0x1400c200e  shl     rsi, 3
0x1400c2012  mov     edi, r13d
0x1400c2015  mov     ebx, 1
0x1400c201a  cmp     di, r14w
0x1400c201e  jnb     loc_1400C2323
0x1400c2024  lea     rax, [rsi-1]
0x1400c2028  cmp     rax, 0FFFEh
0x1400c202e  ja      loc_1400C2369
0x1400c2034  mov     [rsp+0C8h+var_90], rsi
0x1400c2039  mov     [rsp+0C8h+var_90], rbx
0x1400c203e  mov     r8d, 4; Alignment
0x1400c2044  mov     rdx, rbx; Length
0x1400c2047  mov     rcx, r12; Address
0x1400c204a  call    cs:__imp_ProbeForRead
0x1400c2051  nop     dword ptr [rax+rax+00h]
0x1400c2056  movzx   eax, di
0x1400c2059  lea     rcx, [rax+rax*2]
0x1400c205d  movups  xmm0, xmmword ptr [r12+rcx*8]
0x1400c2062  movups  [rsp+0C8h+var_A8], xmm0
0x1400c2067  movsd   xmm1, qword ptr [r12+rcx*8+10h]
0x1400c206e  movsd   [rsp+0C8h+var_98], xmm1
0x1400c2074  jmp     short loc_1400C2096
0x1400c2076  mov     ebx, eax
0x1400c2078  mov     eax, 0C0000001h
0x1400c207d  test    ebx, ebx
0x1400c207f  cmovns  ebx, eax
0x1400c2082  mov     r8d, 1202h; unsigned int
0x1400c2088  mov     ecx, ebx; int
0x1400c208a  call    ?CitpLogFailureWorker@@YAXJPEBDI@Z; CitpLogFailureWorker(long,char const *,uint)
0x1400c208f  mov     eax, ebx
0x1400c2091  jmp     loc_1400C1FE4
0x1400c2096  cmp     qword ptr [rsp+0C8h+var_A8], r13
0x1400c209b  jz      loc_1400C2146
0x1400c20a1  call    Feature_ResponsiblePid__private_IsEnabledDeviceUsageNoInline
0x1400c20a6  test    eax, eax
0x1400c20a8  jz      loc_1400C214E
0x1400c20ae  movsxd  rdx, dword ptr [rsp+0C8h+var_98]
0x1400c20b3  mov     r9, qword ptr [rsp+0C8h+var_A8+8]
0x1400c20b8  mov     r8d, 3
0x1400c20be  lea     rcx, [rsp+0C8h+var_78]
0x1400c20c3  call    ??0CLockProcessByPid@@QEAA@PEAXW4LockProcessOptions@@_K@Z; CLockProcessByPid::CLockProcessByPid(void *,LockProcessOptions,unsigned __int64)
0x1400c20c8  cmp     [rsp+0C8h+var_70], r13d
0x1400c20cd  jl      short loc_1400C213B
0x1400c20cf  mov     eax, 0FFFFh
0x1400c20d4  cmp     dword ptr [rsp+0C8h+var_98+4], eax
0x1400c20d8  ja      short loc_1400C20DF
0x1400c20da  movzx   eax, word ptr [rsp+0C8h+var_98+4]
0x1400c20df  mov     word ptr [rsp+0C8h+var_A8+6], ax
0x1400c20e4  mov     r8, qword ptr [rsp+0C8h+var_A8]
0x1400c20e9  mov     edx, 7
0x1400c20ee  mov     rcx, [rsp+0C8h+var_60]
0x1400c20f3  call    cs:__imp_PsUpdateComponentPower
0x1400c20fa  nop     dword ptr [rax+rax+00h]
0x1400c20ff  mov     rcx, [rsp+0C8h+var_60]
0x1400c2104  test    rcx, rcx
0x1400c2107  jz      loc_1400C232A
0x1400c210d  call    cs:__imp_PsGetProcessWin32Process
0x1400c2114  nop     dword ptr [rax+rax+00h]
0x1400c2119  mov     rbx, rax
0x1400c211c  test    rax, rax
0x1400c211f  jz      short loc_1400C212D
0x1400c2121  mov     rax, [rax]
0x1400c2124  neg     rax
0x1400c2127  sbb     rcx, rcx
0x1400c212a  and     rbx, rcx
0x1400c212d  test    rbx, rbx
0x1400c2130  jnz     loc_1400C2233
0x1400c2136  mov     ebx, 1
0x1400c213b  cmp     [rsp+0C8h+var_60], r13
0x1400c2140  jnz     loc_1400C233F
0x1400c2146  add     di, bx
0x1400c2149  jmp     loc_1400C201A
0x1400c214e  mov     [rsp+0C8h+Process], r13
0x1400c2156  movsxd  rcx, dword ptr [rsp+0C8h+var_98]; ProcessId
0x1400c215b  lea     rdx, [rsp+0C8h+Process]; Process
0x1400c2163  call    cs:__imp_PsLookupProcessByProcessId
0x1400c216a  nop     dword ptr [rax+rax+00h]
0x1400c216f  test    eax, eax
0x1400c2171  js      short loc_1400C2146
0x1400c2173  mov     rcx, [rsp+0C8h+Process]
0x1400c217b  call    cs:__imp_PsGetProcessSequenceNumber
0x1400c2182  nop     dword ptr [rax+rax+00h]
0x1400c2187  cmp     rax, qword ptr [rsp+0C8h+var_A8+8]
0x1400c218c  jnz     loc_1400C221A
0x1400c2192  mov     rcx, [rsp+0C8h+Process]
0x1400c219a  call    cs:__imp_PsGetProcessSessionIdEx
0x1400c21a1  nop     dword ptr [rax+rax+00h]
0x1400c21a6  mov     ebx, eax
0x1400c21a8  call    W32GetCurrentWin32kSessionId
0x1400c21ad  cmp     ebx, eax
0x1400c21af  jnz     short loc_1400C2215
0x1400c21b1  mov     eax, 0FFFFh
0x1400c21b6  cmp     dword ptr [rsp+0C8h+var_98+4], eax
0x1400c21ba  ja      short loc_1400C21C1
0x1400c21bc  movzx   eax, word ptr [rsp+0C8h+var_98+4]
0x1400c21c1  mov     word ptr [rsp+0C8h+var_A8+6], ax
0x1400c21c6  mov     r8, qword ptr [rsp+0C8h+var_A8]
0x1400c21cb  mov     edx, 7
0x1400c21d0  mov     rcx, [rsp+0C8h+Process]
0x1400c21d8  call    cs:__imp_PsUpdateComponentPower
0x1400c21df  nop     dword ptr [rax+rax+00h]
0x1400c21e4  mov     rcx, [rsp+0C8h+Process]
0x1400c21ec  call    cs:__imp_PsGetProcessWin32Process
0x1400c21f3  nop     dword ptr [rax+rax+00h]
0x1400c21f8  mov     rbx, rax
0x1400c21fb  test    rax, rax
0x1400c21fe  jz      short loc_1400C220C
0x1400c2200  mov     rax, [rax]
0x1400c2203  neg     rax
0x1400c2206  sbb     rcx, rcx
0x1400c2209  and     rbx, rcx
0x1400c220c  test    rbx, rbx
0x1400c220f  jnz     loc_1400C22A5
0x1400c2215  mov     ebx, 1
0x1400c221a  mov     rcx, [rsp+0C8h+Process]; Object
0x1400c2222  call    cs:__imp_ObfDereferenceObject
0x1400c2229  nop     dword ptr [rax+rax+00h]
0x1400c222e  jmp     loc_1400C2146
0x1400c2233  mov     rcx, rbx; struct tagPROCESSINFO *
0x1400c2236  call    ?CitpProcessEnsureContext@@YAPEAU_CIT_PROCESS@@PEAUtagPROCESSINFO@@@Z; CitpProcessEnsureContext(tagPROCESSINFO *)
0x1400c223b  test    rax, rax
0x1400c223e  jz      loc_1400C2136
0x1400c2244  mov     r8d, 4; unsigned __int16
0x1400c224a  mov     rdx, [rbx+390h]; struct _CIT_PROCESS *
0x1400c2251  mov     rcx, r15; struct _CIT_IMPACT_CONTEXT *
0x1400c2254  call    ?CitpInteractionSummaryEnsure@@YAPEAU_CIT_INTERACTION_SUMMARY@@PEAU_CIT_IMPACT_CONTEXT@@PEAU_CIT_PROCESS@@G@Z; CitpInteractionSummaryEnsure(_CIT_IMPACT_CONTEXT *,_CIT_PROCESS *,ushort)
0x1400c2259  mov     r9, rax
0x1400c225c  mov     ebx, 1
0x1400c2261  test    rax, rax
0x1400c2264  jz      loc_1400C213B
0x1400c226a  cmp     word ptr [rsp+0C8h+var_A8], r13w
0x1400c2270  jnz     loc_1400C2313
0x1400c2276  cmp     word ptr [rsp+0C8h+var_A8+2], r13w
0x1400c227c  jz      short loc_1400C2289
0x1400c227e  mov     edx, ebx; unsigned __int16
0x1400c2280  lea     rcx, [r9+6Eh]; unsigned __int16 *
0x1400c2284  call    ?CitpStatIncrement@@YAXPEAGG@Z; CitpStatIncrement(ushort *,ushort)
0x1400c2289  cmp     word ptr [rsp+0C8h+var_A8+4], r13w
0x1400c228f  jz      loc_1400C213B
0x1400c2295  mov     edx, ebx; unsigned __int16
0x1400c2297  lea     rcx, [r9+70h]; unsigned __int16 *
0x1400c229b  call    ?CitpStatIncrement@@YAXPEAGG@Z; CitpStatIncrement(ushort *,ushort)
0x1400c22a0  jmp     loc_1400C213B
0x1400c22a5  mov     rcx, rbx; struct tagPROCESSINFO *
0x1400c22a8  call    ?CitpProcessEnsureContext@@YAPEAU_CIT_PROCESS@@PEAUtagPROCESSINFO@@@Z; CitpProcessEnsureContext(tagPROCESSINFO *)
0x1400c22ad  test    rax, rax
0x1400c22b0  jz      loc_1400C2215
0x1400c22b6  mov     r8d, 4; unsigned __int16
0x1400c22bc  mov     rdx, [rbx+390h]; struct _CIT_PROCESS *
0x1400c22c3  mov     rcx, r15; struct _CIT_IMPACT_CONTEXT *
0x1400c22c6  call    ?CitpInteractionSummaryEnsure@@YAPEAU_CIT_INTERACTION_SUMMARY@@PEAU_CIT_IMPACT_CONTEXT@@PEAU_CIT_PROCESS@@G@Z; CitpInteractionSummaryEnsure(_CIT_IMPACT_CONTEXT *,_CIT_PROCESS *,ushort)
0x1400c22cb  mov     r9, rax
0x1400c22ce  mov     ebx, 1
0x1400c22d3  test    rax, rax
0x1400c22d6  jz      loc_1400C221A
0x1400c22dc  cmp     word ptr [rsp+0C8h+var_A8], r13w
0x1400c22e2  jnz     short loc_1400C2332
0x1400c22e4  cmp     word ptr [rsp+0C8h+var_A8+2], r13w
0x1400c22ea  jz      short loc_1400C22F7
0x1400c22ec  mov     edx, ebx; unsigned __int16
0x1400c22ee  lea     rcx, [r9+6Eh]; unsigned __int16 *
0x1400c22f2  call    ?CitpStatIncrement@@YAXPEAGG@Z; CitpStatIncrement(ushort *,ushort)
0x1400c22f7  cmp     word ptr [rsp+0C8h+var_A8+4], r13w
0x1400c22fd  jz      loc_1400C221A
0x1400c2303  mov     edx, ebx; unsigned __int16
0x1400c2305  lea     rcx, [r9+70h]; unsigned __int16 *
0x1400c2309  call    ?CitpStatIncrement@@YAXPEAGG@Z; CitpStatIncrement(ushort *,ushort)
0x1400c230e  jmp     loc_1400C221A
0x1400c2313  mov     edx, ebx; unsigned __int16
0x1400c2315  lea     rcx, [rax+6Ch]; unsigned __int16 *
0x1400c2319  call    ?CitpStatIncrement@@YAXPEAGG@Z; CitpStatIncrement(ushort *,ushort)
0x1400c231e  jmp     loc_1400C2276
0x1400c2323  xor     eax, eax
0x1400c2325  jmp     loc_1400C1FE4
0x1400c232a  mov     rbx, r13
0x1400c232d  jmp     loc_1400C212D
0x1400c2332  mov     edx, ebx; unsigned __int16
0x1400c2334  lea     rcx, [rax+6Ch]; unsigned __int16 *
0x1400c2338  call    ?CitpStatIncrement@@YAXPEAGG@Z; CitpStatIncrement(ushort *,ushort)
0x1400c233d  jmp     short loc_1400C22E4
0x1400c233f  test    [rsp+0C8h+var_64], 8
0x1400c2344  jz      short loc_1400C235A
0x1400c2346  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x1400c234b  mov     rcx, [rsp+0C8h+var_48]
0x1400c2353  mov     [rax+178h], rcx
0x1400c235a  lea     rcx, [rsp+0C8h+var_78]; this
0x1400c235f  call    ?_Cleanup@CLockProcessByPid@@AEAAXXZ; CLockProcessByPid::_Cleanup(void)
0x1400c2364  jmp     loc_1400C2146
0x1400c2369  mov     ebx, 0C0000001h
0x1400c236e  mov     r8d, 11F5h; unsigned int
0x1400c2374  mov     ecx, ebx; int
0x1400c2376  call    ?CitpLogFailureWorker@@YAXJPEBDI@Z; CitpLogFailureWorker(long,char const *,uint)
0x1400c237b  mov     eax, ebx
0x1400c237d  jmp     loc_1400C1FE4
0x1402396cb  push    rbp
0x1402396cd  sub     rsp, 20h
0x1402396d1  mov     rbp, rdx
0x1402396d4  mov     eax, 1
0x1402396d9  add     rsp, 20h
0x1402396dd  pop     rbp
0x1402396de  retn
```
