# CTouchProcessor::UpdateThreadPointerList(tagTHREADINPUTPOINTERLIST *,ushort)

- ea: `0x140078c90`
- end: `0x1400795dc`
- name: `?UpdateThreadPointerList@CTouchProcessor@@QEAAXPEAUtagTHREADINPUTPOINTERLIST@@G@Z`
- size: `2380`
- prototype: `void __fastcall(CTouchProcessor *__hidden this, struct tagTHREADINPUTPOINTERLIST *, unsigned __int16)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, installer_update, broker_com_uri`

## callees

- `0x140072a90`
- `0x140078c90`
- `0x1400795f0`
- `0x1400797c0`
- `0x140079d60`
- `0x14007a098`
- `0x140190c7c`
- `0x1401a9f9c`

## import_xrefs

- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceExclusive` at `0x140078d25`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceExclusive` at `0x140078d25`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x140079066`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x140079066`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x140078ded`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x140078e43`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x140078fe1`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x140079149`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x140078ded`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x140078e43`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x140078fe1`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x140079149`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140078f5b`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400791c0`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140078f5b`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400791c0`
- `WIN32K!W32GetUserSessionState` at `0x140078f7e`
- `WIN32K!W32GetUserSessionState` at `0x1400790f4`
- `WIN32K!W32GetUserSessionState` at `0x140078f7e`
- `WIN32K!W32GetUserSessionState` at `0x1400790f4`

## pseudocode

```c
void __fastcall CTouchProcessor::UpdateThreadPointerList(
        PERESOURCE *this,
        struct tagTHREADINPUTPOINTERLIST *a2,
        unsigned __int16 a3)
{
  unsigned __int16 v3; // r14
  struct tagTHREADINPUTPOINTERLIST *v4; // rsi
  PERESOURCE *v6; // r12
  int v7; // edx
  __int16 v8; // r8
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
  __int64 ThreadPointerData; // rbx
  __int64 v21; // [rsp+58h] [rbp-31h]
  _QWORD *v22; // [rsp+60h] [rbp-29h]
  __int64 v23; // [rsp+68h] [rbp-21h] BYREF
  char v24; // [rsp+88h] [rbp-1h]
  PERESOURCE *v25; // [rsp+90h] [rbp+7h]

  v3 = a3;
  v4 = a2;
  LOBYTE(a2) = WPP_GLOBAL_Control != (CTouchProcessor *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 5u;
  LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && *((_WORD *)WPP_GLOBAL_Control + 36);
  if ( (_BYTE)a2 || (_BYTE)a3 )
    WPP_RECORDER_AND_TRACE_SF_(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      (_DWORD)a2,
      a3,
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      5,
      4,
      111,
      (__int64)WPP_9da2ab7a54883028c158715a103b49be_Traceguids);
  v6 = this + 4;
  v23 = 0;
  v25 = this + 4;
  v24 = 0;
  ExEnterCriticalRegionAndAcquireResourceExclusive(this[4]);
  if ( v3 == 1 )
  {
    LOBYTE(v7) = WPP_GLOBAL_Control != (CTouchProcessor *)&WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 8) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 5u;
    LOBYTE(v8) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
              && *((_WORD *)WPP_GLOBAL_Control + 36);
    if ( (_BYTE)v7 || (_BYTE)v8 )
      WPP_RECORDER_AND_TRACE_SF_(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v7,
        v8,
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        5,
        4,
        112,
        (__int64)WPP_9da2ab7a54883028c158715a103b49be_Traceguids);
    goto LABEL_66;
  }
  if ( *(struct tagTHREADINPUTPOINTERLIST **)v4 != v4 )
  {
    v9 = 0;
    v10 = 0;
    v21 = 0;
    if ( v3 )
    {
      ThreadPointerData = ApiSetEditionFindThreadPointerData(v4, v3);
      if ( !ThreadPointerData )
        MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 4828);
      v9 = *(_QWORD *)(ThreadPointerData + 24);
      v21 = v9;
    }
    v11 = *(struct tagTHREADINPUTPOINTERLIST **)v4;
    if ( *(struct tagTHREADINPUTPOINTERLIST **)v4 != v4 )
    {
      HIBYTE(v8) = 0;
      do
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
            goto LABEL_23;
          if ( (*(_DWORD *)(v15 + 36) & 0x80u) != 0 )
          {
            MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 131073, 10524);
            v9 = v21;
          }
          if ( (*(_DWORD *)(v9 + 36) & 0x80u) != 0 )
          {
            MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 131073, 10524);
            v9 = v21;
          }
          if ( *(_DWORD *)(v15 + 28) != *(_DWORD *)(v9 + 28) )
          {
LABEL_23:
            v17 = *((_QWORD *)v14 + 3);
            if ( v17 && (*(_DWORD *)(v17 + 36) & 0x80u) != 0 )
              MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 131073, 10524);
            if ( !ExIsResourceAcquiredSharedLite(*v6) )
              MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 12606);
            v18 = *(_QWORD **)v17;
            v22 = *(_QWORD **)v17;
            if ( *(_QWORD *)v17 == *(_QWORD *)(v17 + 8) )
            {
              if ( *v18 != v17 )
              {
                MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 12626);
                v18 = v22;
              }
              if ( v18[1] != v17 )
              {
                MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 12627);
                v18 = v22;
              }
              if ( *((_WORD *)v18 - 112) != *(_WORD *)(v17 + 16) )
              {
                MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 12633);
                v18 = v22;
              }
              if ( *((_DWORD *)v18 - 50) == 3 && !*((_DWORD *)v18 - 55) )
                goto LABEL_88;
            }
            v19 = *((_QWORD *)v14 + 3);
            if ( v19 && (*(_DWORD *)(v19 + 36) & 0x80u) != 0 )
              MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 131073, 10524);
            if ( !ExIsResourceAcquiredSharedLite(*v6) )
              MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 12586);
            if ( (*(_DWORD *)(v19 + 36) & 0x20) != 0 )
            {
LABEL_88:
              ApiSetEditionUnlinkAndFreeThreadPointerData(v4, v14);
              v10 = v13;
            }
            v9 = v21;
          }
          HIBYTE(v8) = 0;
        }
      }
      while ( v11 != v4 );
    }
    if ( v10 != *((_DWORD *)v4 + 4) )
      MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 4906);
    LOBYTE(v9) = WPP_GLOBAL_Control != (CTouchProcessor *)&WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 8) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 5u;
    LOBYTE(v8) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
              && *((_WORD *)WPP_GLOBAL_Control + 36);
    if ( (_BYTE)v9 || (_BYTE)v8 )
      WPP_RECORDER_AND_TRACE_SF_(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v9,
        v8,
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        5,
        4,
        114,
        (__int64)WPP_9da2ab7a54883028c158715a103b49be_Traceguids);
LABEL_66:
    CRefUnRefPointerMsgId::ThreadUnlockAndUnReference((CRefUnRefPointerMsgId *)&v23);
    goto LABEL_59;
  }
  LOBYTE(v7) = WPP_GLOBAL_Control != (CTouchProcessor *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 5u;
  LOBYTE(v8) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && *((_WORD *)WPP_GLOBAL_Control + 36);
  if ( (_BYTE)v7 || (_BYTE)v8 )
    WPP_RECORDER_AND_TRACE_SF_(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      v7,
      v8,
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      5,
      4,
      113,
      (__int64)WPP_9da2ab7a54883028c158715a103b49be_Traceguids);
LABEL_59:
  ExReleaseResourceAndLeaveCriticalRegion(*v25);
}

```

## disassembly

```asm
0x140078c90  push    rbp
0x140078c92  push    rbx
0x140078c93  push    rsi
0x140078c94  push    rdi
0x140078c95  push    r12
0x140078c97  push    r13
0x140078c99  push    r14
0x140078c9b  push    r15
0x140078c9d  lea     rbp, [rsp-1Fh]
0x140078ca2  sub     rsp, 0A8h
0x140078ca9  movzx   r14d, r8w
0x140078cad  mov     rsi, rdx
0x140078cb0  mov     rbx, rcx
0x140078cb3  mov     rcx, cs:WPP_GLOBAL_Control
0x140078cba  lea     r13, WPP_GLOBAL_Control
0x140078cc1  cmp     rcx, r13
0x140078cc4  jz      short loc_140078CD1
0x140078cc6  mov     eax, [rcx+2Ch]
0x140078cc9  test    al, 8
0x140078ccb  jnz     loc_14007935E
0x140078cd1  xor     dl, dl
0x140078cd3  lea     r15, WPP_RECORDER_INITIALIZED
0x140078cda  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140078ce1  jz      loc_140078E6F
0x140078ce7  cmp     word ptr [rcx+48h], 0
0x140078cec  jz      loc_140078E6F
0x140078cf2  mov     r8b, 1
0x140078cf5  lea     rdi, WPP_9da2ab7a54883028c158715a103b49be_Traceguids
0x140078cfc  test    dl, dl
0x140078cfe  jnz     loc_1400793B2
0x140078d04  test    r8b, r8b
0x140078d07  jnz     loc_1400793B2
0x140078d0d  lea     r12, [rbx+20h]
0x140078d11  mov     [rbp+57h+var_78], 0
0x140078d19  mov     [rbp+57h+var_50], r12
0x140078d1d  mov     [rbp+57h+var_58], 0
0x140078d21  mov     rcx, [r12]; Resource
0x140078d25  call    cs:__imp_ExEnterCriticalRegionAndAcquireResourceExclusive
0x140078d2c  nop     dword ptr [rax+rax+00h]
0x140078d31  cmp     [rbp+57h+var_78], 0
0x140078d36  jnz     loc_1400790E6
0x140078d3c  cmp     r14w, 1
0x140078d41  jz      loc_140079087
0x140078d47  cmp     [rsi], rsi
0x140078d4a  jz      loc_140078F10
0x140078d50  xor     edx, edx
0x140078d52  xor     edi, edi
0x140078d54  mov     [rbp+57h+var_88], rdx
0x140078d58  test    r14w, r14w
0x140078d5c  jnz     loc_1400792AE
0x140078d62  mov     rbx, [rsi]
0x140078d65  cmp     rbx, rsi
0x140078d68  jz      loc_140078E94
0x140078d6e  mov     r8d, 1
0x140078d74  nop     dword ptr [rax+00h]
0x140078d78  nop     dword ptr [rax+rax+00000000h]
0x140078d80  mov     rcx, rbx
0x140078d83  mov     r13d, edi
0x140078d86  inc     edi
0x140078d88  mov     r15, rbx
0x140078d8b  mov     rbx, [rbx]
0x140078d8e  mov     r14, [rcx+18h]
0x140078d92  mov     eax, [rcx+30h]
0x140078d95  cmp     rdx, r14
0x140078d98  jz      loc_140078E77
0x140078d9e  test    al, 2
0x140078da0  jz      loc_140078E7D
0x140078da6  test    r14, r14
0x140078da9  jz      short loc_140078DD4
0x140078dab  test    rdx, rdx
0x140078dae  jz      short loc_140078DD4
0x140078db0  mov     eax, [r14+24h]
0x140078db4  test    al, al
0x140078db6  js      loc_140079423
0x140078dbc  mov     eax, [rdx+24h]
0x140078dbf  test    al, al
0x140078dc1  js      loc_140079448
0x140078dc7  mov     eax, [rdx+1Ch]
0x140078dca  cmp     [r14+1Ch], eax
0x140078dce  jz      loc_140078E67
0x140078dd4  mov     r14, [r15+18h]
0x140078dd8  test    r14, r14
0x140078ddb  jz      short loc_140078DE9
0x140078ddd  mov     eax, [r14+24h]
0x140078de1  test    al, al
0x140078de3  js      loc_14007946D
0x140078de9  mov     rcx, [r12]; Resource
0x140078ded  call    cs:__imp_ExIsResourceAcquiredSharedLite
0x140078df4  nop     dword ptr [rax+rax+00h]
0x140078df9  test    eax, eax
0x140078dfb  jnz     short loc_140078E19
0x140078dfd  mov     [rbp+57h+arg_18], 20000h
0x140078e04  lea     rcx, aIxptelassert; "IXPTelAssert"
0x140078e0b  mov     edx, [rbp+57h+arg_18]
0x140078e0e  mov     r8d, 313Eh
0x140078e14  call    MicrosoftTelemetryAssertTriggeredArgsKM
0x140078e19  mov     rcx, [r14]
0x140078e1c  mov     [rbp+57h+var_80], rcx
0x140078e20  cmp     rcx, [r14+8]
0x140078e24  jz      loc_140079305
0x140078e2a  mov     r14, [r15+18h]
0x140078e2e  test    r14, r14
0x140078e31  jz      short loc_140078E3F
0x140078e33  mov     eax, [r14+24h]
0x140078e37  test    al, al
0x140078e39  js      loc_14007948E
0x140078e3f  mov     rcx, [r12]; Resource
0x140078e43  call    cs:__imp_ExIsResourceAcquiredSharedLite
0x140078e4a  nop     dword ptr [rax+rax+00h]
0x140078e4f  test    eax, eax
0x140078e51  jz      loc_1400790C5
0x140078e57  mov     eax, [r14+24h]
0x140078e5b  test    al, 20h
0x140078e5d  jnz     loc_140079344
0x140078e63  mov     rdx, [rbp+57h+var_88]
0x140078e67  mov     r8d, 1
0x140078e6d  jmp     short loc_140078E7D
0x140078e6f  xor     r8b, r8b
0x140078e72  jmp     loc_140078CF5
0x140078e77  or      eax, 2
0x140078e7a  mov     [rcx+30h], eax
0x140078e7d  cmp     rbx, rsi
0x140078e80  jnz     loc_140078D80
0x140078e86  lea     r15, WPP_RECORDER_INITIALIZED
0x140078e8d  lea     r13, WPP_GLOBAL_Control
0x140078e94  cmp     edi, [rsi+10h]
0x140078e97  jnz     loc_1400795AA
0x140078e9d  mov     rcx, cs:WPP_GLOBAL_Control
0x140078ea4  cmp     rcx, r13
0x140078ea7  jz      short loc_140078EB4
0x140078ea9  mov     eax, [rcx+2Ch]
0x140078eac  test    al, 8
0x140078eae  jnz     loc_1400795CB
0x140078eb4  xor     dl, dl
0x140078eb6  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140078ebd  jz      loc_14007923D
0x140078ec3  cmp     word ptr [rcx+48h], 0
0x140078ec8  jz      loc_14007923D
0x140078ece  mov     r8b, 1
0x140078ed1  test    dl, dl
0x140078ed3  jnz     short loc_140078EDE
0x140078ed5  test    r8b, r8b
0x140078ed8  jz      loc_1400790BA
0x140078ede  lea     r9, WPP_9da2ab7a54883028c158715a103b49be_Traceguids
0x140078ee5  mov     [rsp+0E0h+var_A8], r9
0x140078eea  mov     [rsp+0E0h+var_B0], 72h ; 'r'
0x140078ef1  mov     r9, [rcx+40h]
0x140078ef5  mov     rcx, [rcx+18h]
0x140078ef9  mov     [rsp+0E0h+var_B8], 4
0x140078f01  mov     [rsp+0E0h+var_C0], 5
0x140078f06  call    WPP_RECORDER_AND_TRACE_SF_
0x140078f0b  jmp     loc_1400790BA
0x140078f10  mov     rcx, cs:WPP_GLOBAL_Control
0x140078f17  cmp     rcx, r13
0x140078f1a  jz      short loc_140078F27
0x140078f1c  mov     eax, [rcx+2Ch]
0x140078f1f  test    al, 8
0x140078f21  jnz     loc_1400792D3
0x140078f27  xor     dl, dl
0x140078f29  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140078f30  jz      short loc_140078F3D
0x140078f32  cmp     word ptr [rcx+48h], 0
0x140078f37  jnz     loc_140079245
0x140078f3d  xor     r8b, r8b
0x140078f40  test    dl, dl
0x140078f42  jnz     loc_140079283
0x140078f48  test    r8b, r8b
0x140078f4b  jnz     loc_140079283
0x140078f51  cmp     [rbp+57h+var_58], 0
0x140078f55  jz      loc_14007905F
0x140078f5b  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x140078f62  nop     dword ptr [rax+rax+00h]
0x140078f67  test    rax, rax
0x140078f6a  jz      loc_14007927C
0x140078f70  mov     rcx, [rax]
0x140078f73  mov     rax, [rbp+57h+var_70]
0x140078f77  mov     [rcx+178h], rax
0x140078f7e  call    cs:__imp_W32GetUserSessionState
0x140078f85  nop     dword ptr [rax+rax+00h]
0x140078f8a  mov     rdi, [rbp+57h+var_78]
0x140078f8e  mov     rbx, [rax+0C88h]
0x140078f95  mov     rcx, cs:WPP_GLOBAL_Control
0x140078f9c  cmp     rcx, r13
0x140078f9f  jz      short loc_140078FAC
0x140078fa1  mov     eax, [rcx+2Ch]
0x140078fa4  test    al, 8
0x140078fa6  jnz     loc_1400794F2
0x140078fac  xor     dl, dl
0x140078fae  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140078fb5  jz      short loc_140078FC2
0x140078fb7  cmp     word ptr [rcx+48h], 0
0x140078fbc  jnz     loc_1400792F5
0x140078fc2  xor     r8b, r8b
0x140078fc5  test    dl, dl
0x140078fc7  jnz     loc_140079503
0x140078fcd  test    r8b, r8b
0x140078fd0  jnz     loc_140079503
0x140078fd6  lea     rsi, WPP_9da2ab7a54883028c158715a103b49be_Traceguids
0x140078fdd  mov     rcx, [rbx+20h]; Resource
0x140078fe1  call    cs:__imp_ExIsResourceAcquiredSharedLite
0x140078fe8  nop     dword ptr [rax+rax+00h]
0x140078fed  test    eax, eax
0x140078fef  jnz     short loc_14007900D
0x140078ff1  mov     [rbp+57h+arg_10], 20000h
0x140078ff8  lea     rcx, aIxptelassert; "IXPTelAssert"
0x140078fff  mov     edx, [rbp+57h+arg_10]
0x140079002  mov     r8d, 31B5h
0x140079008  call    MicrosoftTelemetryAssertTriggeredArgsKM
0x14007900d  mov     r8d, 8
0x140079013  mov     rdx, rdi
0x140079016  mov     rcx, rbx
0x140079019  call    ?UnreferenceMsgData@CTouchProcessor@@AEAAX_KW4tagPOINTERMSGDATA_REFTYPE@@PEAX@Z; CTouchProcessor::UnreferenceMsgData(unsigned __int64,tagPOINTERMSGDATA_REFTYPE,void *)
0x14007901e  mov     rcx, cs:WPP_GLOBAL_Control
0x140079025  cmp     rcx, r13
0x140079028  jz      short loc_140079035
0x14007902a  mov     eax, [rcx+2Ch]
0x14007902d  test    al, 8
0x14007902f  jnz     loc_1400792E4
0x140079035  xor     dl, dl
0x140079037  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14007903e  jz      short loc_14007904B
0x140079040  cmp     word ptr [rcx+48h], 0
0x140079045  jnz     loc_1400792FD
0x14007904b  xor     r8b, r8b
0x14007904e  test    dl, dl
0x140079050  jnz     loc_140079535
0x140079056  test    r8b, r8b
0x140079059  jnz     loc_140079535
0x14007905f  mov     rcx, [rbp+57h+var_50]
0x140079063  mov     rcx, [rcx]; Resource
0x140079066  call    cs:__imp_ExReleaseResourceAndLeaveCriticalRegion
0x14007906d  nop     dword ptr [rax+rax+00h]
0x140079072  add     rsp, 0A8h
0x140079079  pop     r15
0x14007907b  pop     r14
0x14007907d  pop     r13
0x14007907f  pop     r12
0x140079081  pop     rdi
0x140079082  pop     rsi
0x140079083  pop     rbx
0x140079084  pop     rbp
0x140079085  retn
0x140079087  mov     rcx, cs:WPP_GLOBAL_Control
0x14007908e  cmp     rcx, r13
0x140079091  jnz     loc_14007924D
0x140079097  xor     dl, dl
0x140079099  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x1400790a0  jnz     loc_140079269
0x1400790a6  xor     r8b, r8b
0x1400790a9  test    dl, dl
0x1400790ab  jnz     loc_1400794E1
0x1400790b1  test    r8b, r8b
0x1400790b4  jnz     loc_1400794E1
0x1400790ba  lea     rcx, [rbp+57h+var_78]; this
0x1400790be  call    ?ThreadUnlockAndUnReference@CRefUnRefPointerMsgId@@QEAAXXZ; CRefUnRefPointerMsgId::ThreadUnlockAndUnReference(void)
0x1400790c3  jmp     short loc_14007905F
0x1400790c5  mov     [rbp+57h+var_90], 20000h
0x1400790cc  lea     rcx, aIxptelassert; "IXPTelAssert"
0x1400790d3  mov     edx, [rbp+57h+var_90]
0x1400790d6  mov     r8d, 312Ah
0x1400790dc  call    MicrosoftTelemetryAssertTriggeredArgsKM
0x1400790e1  jmp     loc_140078E57
0x1400790e6  cmp     [rbp+57h+var_58], 0
0x1400790ea  jnz     loc_140078D3C
0x1400790f0  mov     [rbp+57h+var_58], 1
0x1400790f4  call    cs:__imp_W32GetUserSessionState
0x1400790fb  nop     dword ptr [rax+rax+00h]
0x140079100  mov     rdi, [rbp+57h+var_78]
0x140079104  mov     rbx, [rax+0C88h]
0x14007910b  mov     rcx, cs:WPP_GLOBAL_Control
0x140079112  cmp     rcx, r13
0x140079115  jz      short loc_140079122
0x140079117  mov     eax, [rcx+2Ch]
0x14007911a  test    al, 8
0x14007911c  jnz     loc_14007936F
0x140079122  xor     dl, dl
0x140079124  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14007912b  jnz     loc_140079202
0x140079131  xor     r8b, r8b
0x140079134  test    dl, dl
0x140079136  jnz     loc_140079380
0x14007913c  test    r8b, r8b
0x14007913f  jnz     loc_140079380
0x140079145  mov     rcx, [rbx+20h]; Resource
0x140079149  call    cs:__imp_ExIsResourceAcquiredSharedLite
0x140079150  nop     dword ptr [rax+rax+00h]
0x140079155  test    eax, eax
0x140079157  jnz     short loc_140079175
0x140079159  mov     [rbp+57h+arg_10], 20000h
0x140079160  lea     rcx, aIxptelassert; "IXPTelAssert"
0x140079167  mov     edx, [rbp+57h+arg_10]
0x14007916a  mov     r8d, 31A0h
0x140079170  call    MicrosoftTelemetryAssertTriggeredArgsKM
0x140079175  mov     r8d, 8
0x14007917b  mov     rdx, rdi
0x14007917e  mov     rcx, rbx
0x140079181  call    ?ReferenceMsgData@CTouchProcessor@@AEAAX_KW4tagPOINTERMSGDATA_REFTYPE@@PEAX@Z; CTouchProcessor::ReferenceMsgData(unsigned __int64,tagPOINTERMSGDATA_REFTYPE,void *)
0x140079186  mov     rcx, cs:WPP_GLOBAL_Control
0x14007918d  cmp     rcx, r13
0x140079190  jnz     loc_140079221
  ... truncated ...
```
