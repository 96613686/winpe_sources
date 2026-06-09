# CTouchProcessor::UpdateThreadPointerList(tagTHREADINPUTPOINTERLIST *,ushort)

- ea: `0x1400500c0`
- end: `0x140050a0c`
- name: `?UpdateThreadPointerList@CTouchProcessor@@QEAAXPEAUtagTHREADINPUTPOINTERLIST@@G@Z`
- size: `2380`
- prototype: `void __fastcall(PERESOURCE *this, struct tagTHREADINPUTPOINTERLIST *, unsigned __int16)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, installer_update, broker_com_uri`

## callees

- `0x140049ec0`
- `0x1400500c0`
- `0x140050a20`
- `0x140050bf0`
- `0x140051190`
- `0x1400514c8`
- `0x14019308c`
- `0x1401aab9c`

## import_xrefs

- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceExclusive` at `0x140050155`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceExclusive` at `0x140050155`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x140050496`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x140050496`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x14005021d`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x140050273`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x140050411`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x140050579`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x14005021d`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x140050273`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x140050411`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x140050579`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14005038b`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400505f0`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14005038b`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400505f0`
- `WIN32K!W32GetUserSessionState` at `0x1400503ae`
- `WIN32K!W32GetUserSessionState` at `0x140050524`
- `WIN32K!W32GetUserSessionState` at `0x1400503ae`
- `WIN32K!W32GetUserSessionState` at `0x140050524`

## pseudocode

```c
void __fastcall CTouchProcessor::UpdateThreadPointerList(
        PERESOURCE *this,
        struct tagTHREADINPUTPOINTERLIST *a2,
        unsigned __int16 a3)
{
  char v6; // dl
  char v7; // r8
  PERESOURCE *v8; // r12
  __int64 v9; // rdx
  int v10; // edi
  struct tagTHREADINPUTPOINTERLIST *v11; // rbx
  struct tagTHREADINPUTPOINTERLIST *v12; // rcx
  int v13; // r13d
  struct tagTHREADINPUTPOINTERLIST *v14; // r15
  __int64 v15; // r14
  int v16; // eax
  __int64 v17; // r14
  _QWORD *v18; // rcx
  __int64 v19; // r14
  char v20; // dl
  char v21; // r8
  CTouchProcessor *v22; // rcx
  char v23; // dl
  char v24; // r8
  __int64 *CurrentThreadWin32Thread; // rax
  __int64 v26; // rdx
  __int64 v27; // rcx
  __int64 v28; // rbx
  char v29; // dl
  char v30; // r8
  char v31; // dl
  char v32; // r8
  char v33; // dl
  char v34; // r8
  __int64 ThreadPointerData; // rbx
  __int64 v36; // [rsp+58h] [rbp-31h]
  _QWORD *v37; // [rsp+60h] [rbp-29h]
  _QWORD v38[2]; // [rsp+68h] [rbp-21h] BYREF
  char v39; // [rsp+88h] [rbp-1h]
  PERESOURCE *v40; // [rsp+90h] [rbp+7h]

  v6 = WPP_GLOBAL_Control != (CTouchProcessor *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 5u;
  v7 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && *((_WORD *)WPP_GLOBAL_Control + 36);
  if ( v6 || v7 )
    WPP_RECORDER_AND_TRACE_SF_(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      v6,
      v7,
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      5u,
      4u,
      0x6Fu,
      (__int64)WPP_d2072d3b1a993f65232a6b1bf9fbe4ab_Traceguids);
  v8 = this + 4;
  v38[0] = 0;
  v40 = this + 4;
  v39 = 0;
  ExEnterCriticalRegionAndAcquireResourceExclusive(this[4]);
  if ( a3 == 1 )
  {
    v33 = WPP_GLOBAL_Control != (CTouchProcessor *)&WPP_GLOBAL_Control
       && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 8) != 0
       && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 5u;
    v34 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && *((_WORD *)WPP_GLOBAL_Control + 36);
    if ( v33 || v34 )
      WPP_RECORDER_AND_TRACE_SF_(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v33,
        v34,
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        5u,
        4u,
        0x70u,
        (__int64)WPP_d2072d3b1a993f65232a6b1bf9fbe4ab_Traceguids);
    goto LABEL_86;
  }
  if ( *(struct tagTHREADINPUTPOINTERLIST **)a2 != a2 )
  {
    v9 = 0;
    v10 = 0;
    v36 = 0;
    if ( a3 )
    {
      ThreadPointerData = ApiSetEditionFindThreadPointerData(a2, a3);
      if ( !ThreadPointerData )
        MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 4828);
      v9 = *(_QWORD *)(ThreadPointerData + 24);
      v36 = v9;
    }
    v11 = *(struct tagTHREADINPUTPOINTERLIST **)a2;
    while ( v11 != a2 )
    {
      v12 = v11;
      v13 = v10++;
      v14 = v11;
      v11 = *(struct tagTHREADINPUTPOINTERLIST **)v11;
      v15 = *((_QWORD *)v12 + 3);
      v16 = *((_DWORD *)v12 + 12);
      if ( v9 == v15 )
      {
        *((_DWORD *)v12 + 12) = v16 | 2;
      }
      else if ( (v16 & 2) != 0 )
      {
        if ( !v15 || !v9 )
          goto LABEL_22;
        if ( (*(_DWORD *)(v15 + 36) & 0x80u) != 0 )
        {
          MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 131073, 10511);
          v9 = v36;
        }
        if ( (*(_DWORD *)(v9 + 36) & 0x80u) != 0 )
        {
          MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 131073, 10511);
          v9 = v36;
        }
        if ( *(_DWORD *)(v15 + 28) != *(_DWORD *)(v9 + 28) )
        {
LABEL_22:
          v17 = *((_QWORD *)v14 + 3);
          if ( v17 && (*(_DWORD *)(v17 + 36) & 0x80u) != 0 )
            MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 131073, 10511);
          if ( !ExIsResourceAcquiredSharedLite(*v8) )
            MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 12593);
          v18 = *(_QWORD **)v17;
          v37 = *(_QWORD **)v17;
          if ( *(_QWORD *)v17 == *(_QWORD *)(v17 + 8) )
          {
            if ( *v18 != v17 )
            {
              MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 12613);
              v18 = v37;
            }
            if ( v18[1] != v17 )
            {
              MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 12614);
              v18 = v37;
            }
            if ( *((_WORD *)v18 - 112) != *(_WORD *)(v17 + 16) )
            {
              MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 12620);
              v18 = v37;
            }
            if ( *((_DWORD *)v18 - 50) == 3 && !*((_DWORD *)v18 - 55) )
              goto LABEL_113;
          }
          v19 = *((_QWORD *)v14 + 3);
          if ( v19 && (*(_DWORD *)(v19 + 36) & 0x80u) != 0 )
            MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 131073, 10511);
          if ( !ExIsResourceAcquiredSharedLite(*v8) )
            MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 12573);
          if ( (*(_DWORD *)(v19 + 36) & 0x20) != 0 )
          {
LABEL_113:
            ApiSetEditionUnlinkAndFreeThreadPointerData(a2, v14);
            v10 = v13;
          }
          v9 = v36;
        }
      }
    }
    if ( v10 != *((_DWORD *)a2 + 4) )
      MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 4906);
    v20 = WPP_GLOBAL_Control != (CTouchProcessor *)&WPP_GLOBAL_Control
       && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 8) != 0
       && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 5u;
    v21 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && *((_WORD *)WPP_GLOBAL_Control + 36);
    if ( v20 || v21 )
      WPP_RECORDER_AND_TRACE_SF_(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v20,
        v21,
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        5u,
        4u,
        0x72u,
        (__int64)WPP_d2072d3b1a993f65232a6b1bf9fbe4ab_Traceguids);
LABEL_86:
    CRefUnRefPointerMsgId::ThreadUnlockAndUnReference((CRefUnRefPointerMsgId *)v38);
    goto LABEL_79;
  }
  v22 = WPP_GLOBAL_Control;
  v23 = WPP_GLOBAL_Control != (CTouchProcessor *)&WPP_GLOBAL_Control
     && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 8) != 0
     && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 5u;
  v24 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && *((_WORD *)WPP_GLOBAL_Control + 36);
  if ( v23 || v24 )
    WPP_RECORDER_AND_TRACE_SF_(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      v23,
      v24,
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      5u,
      4u,
      0x71u,
      (__int64)WPP_d2072d3b1a993f65232a6b1bf9fbe4ab_Traceguids);
  if ( v39 )
  {
    CurrentThreadWin32Thread = (__int64 *)PsGetCurrentThreadWin32Thread(v22);
    if ( CurrentThreadWin32Thread )
      v27 = *CurrentThreadWin32Thread;
    else
      v27 = 0;
    *(_QWORD *)(v27 + 376) = v38[1];
    v28 = *(_QWORD *)(W32GetUserSessionState(v27, v26) + 3208);
    v29 = WPP_GLOBAL_Control != (CTouchProcessor *)&WPP_GLOBAL_Control
       && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 8) != 0
       && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 5u;
    v30 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && *((_WORD *)WPP_GLOBAL_Control + 36);
    if ( v29 || v30 )
      WPP_RECORDER_AND_TRACE_SF_(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v29,
        v30,
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        5u,
        4u,
        0x12Du,
        (__int64)WPP_d2072d3b1a993f65232a6b1bf9fbe4ab_Traceguids);
    if ( !ExIsResourceAcquiredSharedLite(*(PERESOURCE *)(v28 + 32)) )
      MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 12712);
    CTouchProcessor::UnreferenceMsgData(v28, v38[0], 8);
    v31 = WPP_GLOBAL_Control != (CTouchProcessor *)&WPP_GLOBAL_Control
       && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 8) != 0
       && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 5u;
    v32 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && *((_WORD *)WPP_GLOBAL_Control + 36);
    if ( v31 || v32 )
      WPP_RECORDER_AND_TRACE_SF_(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v31,
        v32,
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        5u,
        4u,
        0x12Eu,
        (__int64)WPP_d2072d3b1a993f65232a6b1bf9fbe4ab_Traceguids);
  }
LABEL_79:
  ExReleaseResourceAndLeaveCriticalRegion(*v40);
}

```

## disassembly

```asm
0x1400500c0  push    rbp
0x1400500c2  push    rbx
0x1400500c3  push    rsi
0x1400500c4  push    rdi
0x1400500c5  push    r12
0x1400500c7  push    r13
0x1400500c9  push    r14
0x1400500cb  push    r15
0x1400500cd  lea     rbp, [rsp-1Fh]
0x1400500d2  sub     rsp, 0A8h
0x1400500d9  movzx   r14d, r8w
0x1400500dd  mov     rsi, rdx
0x1400500e0  mov     rbx, rcx
0x1400500e3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400500ea  lea     r13, WPP_GLOBAL_Control
0x1400500f1  cmp     rcx, r13
0x1400500f4  jz      short loc_140050101
0x1400500f6  mov     eax, [rcx+2Ch]
0x1400500f9  test    al, 8
0x1400500fb  jnz     loc_14005078E
0x140050101  xor     dl, dl
0x140050103  lea     r15, WPP_RECORDER_INITIALIZED
0x14005010a  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140050111  jz      loc_14005029F
0x140050117  cmp     word ptr [rcx+48h], 0
0x14005011c  jz      loc_14005029F
0x140050122  mov     r8b, 1
0x140050125  lea     rdi, WPP_d2072d3b1a993f65232a6b1bf9fbe4ab_Traceguids
0x14005012c  test    dl, dl
0x14005012e  jnz     loc_1400507E2
0x140050134  test    r8b, r8b
0x140050137  jnz     loc_1400507E2
0x14005013d  lea     r12, [rbx+20h]
0x140050141  mov     [rbp+57h+var_78], 0
0x140050149  mov     [rbp+57h+var_50], r12
0x14005014d  mov     [rbp+57h+var_58], 0
0x140050151  mov     rcx, [r12]; Resource
0x140050155  call    cs:__imp_ExEnterCriticalRegionAndAcquireResourceExclusive
0x14005015c  nop     dword ptr [rax+rax+00h]
0x140050161  cmp     [rbp+57h+var_78], 0
0x140050166  jnz     loc_140050516
0x14005016c  cmp     r14w, 1
0x140050171  jz      loc_1400504B7
0x140050177  cmp     [rsi], rsi
0x14005017a  jz      loc_140050340
0x140050180  xor     edx, edx
0x140050182  xor     edi, edi
0x140050184  mov     [rbp+57h+var_88], rdx
0x140050188  test    r14w, r14w
0x14005018c  jnz     loc_1400506DE
0x140050192  mov     rbx, [rsi]
0x140050195  cmp     rbx, rsi
0x140050198  jz      loc_1400502C4
0x14005019e  mov     r8d, 1
0x1400501a4  nop     dword ptr [rax+00h]
0x1400501a8  nop     dword ptr [rax+rax+00000000h]
0x1400501b0  mov     rcx, rbx
0x1400501b3  mov     r13d, edi
0x1400501b6  inc     edi
0x1400501b8  mov     r15, rbx
0x1400501bb  mov     rbx, [rbx]
0x1400501be  mov     r14, [rcx+18h]
0x1400501c2  mov     eax, [rcx+30h]
0x1400501c5  cmp     rdx, r14
0x1400501c8  jz      loc_1400502A7
0x1400501ce  test    al, 2
0x1400501d0  jz      loc_1400502AD
0x1400501d6  test    r14, r14
0x1400501d9  jz      short loc_140050204
0x1400501db  test    rdx, rdx
0x1400501de  jz      short loc_140050204
0x1400501e0  mov     eax, [r14+24h]
0x1400501e4  test    al, al
0x1400501e6  js      loc_140050853
0x1400501ec  mov     eax, [rdx+24h]
0x1400501ef  test    al, al
0x1400501f1  js      loc_140050878
0x1400501f7  mov     eax, [rdx+1Ch]
0x1400501fa  cmp     [r14+1Ch], eax
0x1400501fe  jz      loc_140050297
0x140050204  mov     r14, [r15+18h]
0x140050208  test    r14, r14
0x14005020b  jz      short loc_140050219
0x14005020d  mov     eax, [r14+24h]
0x140050211  test    al, al
0x140050213  js      loc_14005089D
0x140050219  mov     rcx, [r12]; Resource
0x14005021d  call    cs:__imp_ExIsResourceAcquiredSharedLite
0x140050224  nop     dword ptr [rax+rax+00h]
0x140050229  test    eax, eax
0x14005022b  jnz     short loc_140050249
0x14005022d  mov     [rbp+57h+arg_18], 20000h
0x140050234  lea     rcx, aIxptelassert; "IXPTelAssert"
0x14005023b  mov     edx, [rbp+57h+arg_18]
0x14005023e  mov     r8d, 3131h
0x140050244  call    MicrosoftTelemetryAssertTriggeredArgsKM
0x140050249  mov     rcx, [r14]
0x14005024c  mov     [rbp+57h+var_80], rcx
0x140050250  cmp     rcx, [r14+8]
0x140050254  jz      loc_140050735
0x14005025a  mov     r14, [r15+18h]
0x14005025e  test    r14, r14
0x140050261  jz      short loc_14005026F
0x140050263  mov     eax, [r14+24h]
0x140050267  test    al, al
0x140050269  js      loc_1400508BE
0x14005026f  mov     rcx, [r12]; Resource
0x140050273  call    cs:__imp_ExIsResourceAcquiredSharedLite
0x14005027a  nop     dword ptr [rax+rax+00h]
0x14005027f  test    eax, eax
0x140050281  jz      loc_1400504F5
0x140050287  mov     eax, [r14+24h]
0x14005028b  test    al, 20h
0x14005028d  jnz     loc_140050774
0x140050293  mov     rdx, [rbp+57h+var_88]
0x140050297  mov     r8d, 1
0x14005029d  jmp     short loc_1400502AD
0x14005029f  xor     r8b, r8b
0x1400502a2  jmp     loc_140050125
0x1400502a7  or      eax, 2
0x1400502aa  mov     [rcx+30h], eax
0x1400502ad  cmp     rbx, rsi
0x1400502b0  jnz     loc_1400501B0
0x1400502b6  lea     r15, WPP_RECORDER_INITIALIZED
0x1400502bd  lea     r13, WPP_GLOBAL_Control
0x1400502c4  cmp     edi, [rsi+10h]
0x1400502c7  jnz     loc_1400509DA
0x1400502cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1400502d4  cmp     rcx, r13
0x1400502d7  jz      short loc_1400502E4
0x1400502d9  mov     eax, [rcx+2Ch]
0x1400502dc  test    al, 8
0x1400502de  jnz     loc_1400509FB
0x1400502e4  xor     dl, dl
0x1400502e6  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x1400502ed  jz      loc_14005066D
0x1400502f3  cmp     word ptr [rcx+48h], 0
0x1400502f8  jz      loc_14005066D
0x1400502fe  mov     r8b, 1
0x140050301  test    dl, dl
0x140050303  jnz     short loc_14005030E
0x140050305  test    r8b, r8b
0x140050308  jz      loc_1400504EA
0x14005030e  lea     r9, WPP_d2072d3b1a993f65232a6b1bf9fbe4ab_Traceguids
0x140050315  mov     [rsp+0E0h+var_A8], r9
0x14005031a  mov     [rsp+0E0h+var_B0], 72h ; 'r'
0x140050321  mov     r9, [rcx+40h]
0x140050325  mov     rcx, [rcx+18h]
0x140050329  mov     [rsp+0E0h+var_B8], 4
0x140050331  mov     [rsp+0E0h+var_C0], 5
0x140050336  call    WPP_RECORDER_AND_TRACE_SF_
0x14005033b  jmp     loc_1400504EA
0x140050340  mov     rcx, cs:WPP_GLOBAL_Control
0x140050347  cmp     rcx, r13
0x14005034a  jz      short loc_140050357
0x14005034c  mov     eax, [rcx+2Ch]
0x14005034f  test    al, 8
0x140050351  jnz     loc_140050703
0x140050357  xor     dl, dl
0x140050359  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140050360  jz      short loc_14005036D
0x140050362  cmp     word ptr [rcx+48h], 0
0x140050367  jnz     loc_140050675
0x14005036d  xor     r8b, r8b
0x140050370  test    dl, dl
0x140050372  jnz     loc_1400506B3
0x140050378  test    r8b, r8b
0x14005037b  jnz     loc_1400506B3
0x140050381  cmp     [rbp+57h+var_58], 0
0x140050385  jz      loc_14005048F
0x14005038b  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x140050392  nop     dword ptr [rax+rax+00h]
0x140050397  test    rax, rax
0x14005039a  jz      loc_1400506AC
0x1400503a0  mov     rcx, [rax]
0x1400503a3  mov     rax, [rbp+57h+var_70]
0x1400503a7  mov     [rcx+178h], rax
0x1400503ae  call    cs:__imp_W32GetUserSessionState
0x1400503b5  nop     dword ptr [rax+rax+00h]
0x1400503ba  mov     rdi, [rbp+57h+var_78]
0x1400503be  mov     rbx, [rax+0C88h]
0x1400503c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400503cc  cmp     rcx, r13
0x1400503cf  jz      short loc_1400503DC
0x1400503d1  mov     eax, [rcx+2Ch]
0x1400503d4  test    al, 8
0x1400503d6  jnz     loc_140050922
0x1400503dc  xor     dl, dl
0x1400503de  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x1400503e5  jz      short loc_1400503F2
0x1400503e7  cmp     word ptr [rcx+48h], 0
0x1400503ec  jnz     loc_140050725
0x1400503f2  xor     r8b, r8b
0x1400503f5  test    dl, dl
0x1400503f7  jnz     loc_140050933
0x1400503fd  test    r8b, r8b
0x140050400  jnz     loc_140050933
0x140050406  lea     rsi, WPP_d2072d3b1a993f65232a6b1bf9fbe4ab_Traceguids
0x14005040d  mov     rcx, [rbx+20h]; Resource
0x140050411  call    cs:__imp_ExIsResourceAcquiredSharedLite
0x140050418  nop     dword ptr [rax+rax+00h]
0x14005041d  test    eax, eax
0x14005041f  jnz     short loc_14005043D
0x140050421  mov     [rbp+57h+arg_10], 20000h
0x140050428  lea     rcx, aIxptelassert; "IXPTelAssert"
0x14005042f  mov     edx, [rbp+57h+arg_10]
0x140050432  mov     r8d, 31A8h
0x140050438  call    MicrosoftTelemetryAssertTriggeredArgsKM
0x14005043d  mov     r8d, 8
0x140050443  mov     rdx, rdi
0x140050446  mov     rcx, rbx
0x140050449  call    ?UnreferenceMsgData@CTouchProcessor@@AEAAX_KW4tagPOINTERMSGDATA_REFTYPE@@PEAX@Z; CTouchProcessor::UnreferenceMsgData(unsigned __int64,tagPOINTERMSGDATA_REFTYPE,void *)
0x14005044e  mov     rcx, cs:WPP_GLOBAL_Control
0x140050455  cmp     rcx, r13
0x140050458  jz      short loc_140050465
0x14005045a  mov     eax, [rcx+2Ch]
0x14005045d  test    al, 8
0x14005045f  jnz     loc_140050714
0x140050465  xor     dl, dl
0x140050467  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14005046e  jz      short loc_14005047B
0x140050470  cmp     word ptr [rcx+48h], 0
0x140050475  jnz     loc_14005072D
0x14005047b  xor     r8b, r8b
0x14005047e  test    dl, dl
0x140050480  jnz     loc_140050965
0x140050486  test    r8b, r8b
0x140050489  jnz     loc_140050965
0x14005048f  mov     rcx, [rbp+57h+var_50]
0x140050493  mov     rcx, [rcx]; Resource
0x140050496  call    cs:__imp_ExReleaseResourceAndLeaveCriticalRegion
0x14005049d  nop     dword ptr [rax+rax+00h]
0x1400504a2  add     rsp, 0A8h
0x1400504a9  pop     r15
0x1400504ab  pop     r14
0x1400504ad  pop     r13
0x1400504af  pop     r12
0x1400504b1  pop     rdi
0x1400504b2  pop     rsi
0x1400504b3  pop     rbx
0x1400504b4  pop     rbp
0x1400504b5  retn
0x1400504b7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400504be  cmp     rcx, r13
0x1400504c1  jnz     loc_14005067D
0x1400504c7  xor     dl, dl
0x1400504c9  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x1400504d0  jnz     loc_140050699
0x1400504d6  xor     r8b, r8b
0x1400504d9  test    dl, dl
0x1400504db  jnz     loc_140050911
0x1400504e1  test    r8b, r8b
0x1400504e4  jnz     loc_140050911
0x1400504ea  lea     rcx, [rbp+57h+var_78]; this
0x1400504ee  call    ?ThreadUnlockAndUnReference@CRefUnRefPointerMsgId@@QEAAXXZ; CRefUnRefPointerMsgId::ThreadUnlockAndUnReference(void)
0x1400504f3  jmp     short loc_14005048F
0x1400504f5  mov     [rbp+57h+var_90], 20000h
0x1400504fc  lea     rcx, aIxptelassert; "IXPTelAssert"
0x140050503  mov     edx, [rbp+57h+var_90]
0x140050506  mov     r8d, 311Dh
0x14005050c  call    MicrosoftTelemetryAssertTriggeredArgsKM
0x140050511  jmp     loc_140050287
0x140050516  cmp     [rbp+57h+var_58], 0
0x14005051a  jnz     loc_14005016C
0x140050520  mov     [rbp+57h+var_58], 1
0x140050524  call    cs:__imp_W32GetUserSessionState
0x14005052b  nop     dword ptr [rax+rax+00h]
0x140050530  mov     rdi, [rbp+57h+var_78]
0x140050534  mov     rbx, [rax+0C88h]
0x14005053b  mov     rcx, cs:WPP_GLOBAL_Control
0x140050542  cmp     rcx, r13
0x140050545  jz      short loc_140050552
0x140050547  mov     eax, [rcx+2Ch]
0x14005054a  test    al, 8
0x14005054c  jnz     loc_14005079F
0x140050552  xor     dl, dl
0x140050554  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14005055b  jnz     loc_140050632
0x140050561  xor     r8b, r8b
0x140050564  test    dl, dl
0x140050566  jnz     loc_1400507B0
0x14005056c  test    r8b, r8b
0x14005056f  jnz     loc_1400507B0
0x140050575  mov     rcx, [rbx+20h]; Resource
0x140050579  call    cs:__imp_ExIsResourceAcquiredSharedLite
0x140050580  nop     dword ptr [rax+rax+00h]
0x140050585  test    eax, eax
0x140050587  jnz     short loc_1400505A5
0x140050589  mov     [rbp+57h+arg_10], 20000h
0x140050590  lea     rcx, aIxptelassert; "IXPTelAssert"
0x140050597  mov     edx, [rbp+57h+arg_10]
0x14005059a  mov     r8d, 3193h
0x1400505a0  call    MicrosoftTelemetryAssertTriggeredArgsKM
0x1400505a5  mov     r8d, 8
0x1400505ab  mov     rdx, rdi
0x1400505ae  mov     rcx, rbx
0x1400505b1  call    ?ReferenceMsgData@CTouchProcessor@@AEAAX_KW4tagPOINTERMSGDATA_REFTYPE@@PEAX@Z; CTouchProcessor::ReferenceMsgData(unsigned __int64,tagPOINTERMSGDATA_REFTYPE,void *)
0x1400505b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400505bd  cmp     rcx, r13
0x1400505c0  jnz     loc_140050651
  ... truncated ...
```
