# CTouchProcessor::UpdateThreadPointerList(tagTHREADINPUTPOINTERLIST *,ushort)

- ea: `0x140077af0`
- end: `0x14007843c`
- name: `?UpdateThreadPointerList@CTouchProcessor@@QEAAXPEAUtagTHREADINPUTPOINTERLIST@@G@Z`
- size: `2380`
- prototype: `void __fastcall(CTouchProcessor *__hidden this, struct tagTHREADINPUTPOINTERLIST *, unsigned __int16)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, installer_update, broker_com_uri`

## callees

- `0x1400718f0`
- `0x140077af0`
- `0x140078450`
- `0x140078620`
- `0x140078bc0`
- `0x140078ef8`
- `0x140190b6c`
- `0x1401aa4fc`

## import_xrefs

- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceExclusive` at `0x140077b85`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceExclusive` at `0x140077b85`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x140077ec6`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x140077ec6`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x140077c4d`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x140077ca3`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x140077e41`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x140077fa9`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x140077c4d`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x140077ca3`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x140077e41`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x140077fa9`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140077dbb`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140078020`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140077dbb`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140078020`
- `WIN32K!W32GetUserSessionState` at `0x140077dde`
- `WIN32K!W32GetUserSessionState` at `0x140077f54`
- `WIN32K!W32GetUserSessionState` at `0x140077dde`
- `WIN32K!W32GetUserSessionState` at `0x140077f54`

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
0x140077af0  push    rbp
0x140077af2  push    rbx
0x140077af3  push    rsi
0x140077af4  push    rdi
0x140077af5  push    r12
0x140077af7  push    r13
0x140077af9  push    r14
0x140077afb  push    r15
0x140077afd  lea     rbp, [rsp-1Fh]
0x140077b02  sub     rsp, 0A8h
0x140077b09  movzx   r14d, r8w
0x140077b0d  mov     rsi, rdx
0x140077b10  mov     rbx, rcx
0x140077b13  mov     rcx, cs:WPP_GLOBAL_Control
0x140077b1a  lea     r13, WPP_GLOBAL_Control
0x140077b21  cmp     rcx, r13
0x140077b24  jz      short loc_140077B31
0x140077b26  mov     eax, [rcx+2Ch]
0x140077b29  test    al, 8
0x140077b2b  jnz     loc_1400781BE
0x140077b31  xor     dl, dl
0x140077b33  lea     r15, WPP_RECORDER_INITIALIZED
0x140077b3a  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140077b41  jz      loc_140077CCF
0x140077b47  cmp     word ptr [rcx+48h], 0
0x140077b4c  jz      loc_140077CCF
0x140077b52  mov     r8b, 1
0x140077b55  lea     rdi, WPP_9da2ab7a54883028c158715a103b49be_Traceguids
0x140077b5c  test    dl, dl
0x140077b5e  jnz     loc_140078212
0x140077b64  test    r8b, r8b
0x140077b67  jnz     loc_140078212
0x140077b6d  lea     r12, [rbx+20h]
0x140077b71  mov     [rbp+57h+var_78], 0
0x140077b79  mov     [rbp+57h+var_50], r12
0x140077b7d  mov     [rbp+57h+var_58], 0
0x140077b81  mov     rcx, [r12]; Resource
0x140077b85  call    cs:__imp_ExEnterCriticalRegionAndAcquireResourceExclusive
0x140077b8c  nop     dword ptr [rax+rax+00h]
0x140077b91  cmp     [rbp+57h+var_78], 0
0x140077b96  jnz     loc_140077F46
0x140077b9c  cmp     r14w, 1
0x140077ba1  jz      loc_140077EE7
0x140077ba7  cmp     [rsi], rsi
0x140077baa  jz      loc_140077D70
0x140077bb0  xor     edx, edx
0x140077bb2  xor     edi, edi
0x140077bb4  mov     [rbp+57h+var_88], rdx
0x140077bb8  test    r14w, r14w
0x140077bbc  jnz     loc_14007810E
0x140077bc2  mov     rbx, [rsi]
0x140077bc5  cmp     rbx, rsi
0x140077bc8  jz      loc_140077CF4
0x140077bce  mov     r8d, 1
0x140077bd4  nop     dword ptr [rax+00h]
0x140077bd8  nop     dword ptr [rax+rax+00000000h]
0x140077be0  mov     rcx, rbx
0x140077be3  mov     r13d, edi
0x140077be6  inc     edi
0x140077be8  mov     r15, rbx
0x140077beb  mov     rbx, [rbx]
0x140077bee  mov     r14, [rcx+18h]
0x140077bf2  mov     eax, [rcx+30h]
0x140077bf5  cmp     rdx, r14
0x140077bf8  jz      loc_140077CD7
0x140077bfe  test    al, 2
0x140077c00  jz      loc_140077CDD
0x140077c06  test    r14, r14
0x140077c09  jz      short loc_140077C34
0x140077c0b  test    rdx, rdx
0x140077c0e  jz      short loc_140077C34
0x140077c10  mov     eax, [r14+24h]
0x140077c14  test    al, al
0x140077c16  js      loc_140078283
0x140077c1c  mov     eax, [rdx+24h]
0x140077c1f  test    al, al
0x140077c21  js      loc_1400782A8
0x140077c27  mov     eax, [rdx+1Ch]
0x140077c2a  cmp     [r14+1Ch], eax
0x140077c2e  jz      loc_140077CC7
0x140077c34  mov     r14, [r15+18h]
0x140077c38  test    r14, r14
0x140077c3b  jz      short loc_140077C49
0x140077c3d  mov     eax, [r14+24h]
0x140077c41  test    al, al
0x140077c43  js      loc_1400782CD
0x140077c49  mov     rcx, [r12]; Resource
0x140077c4d  call    cs:__imp_ExIsResourceAcquiredSharedLite
0x140077c54  nop     dword ptr [rax+rax+00h]
0x140077c59  test    eax, eax
0x140077c5b  jnz     short loc_140077C79
0x140077c5d  mov     [rbp+57h+arg_18], 20000h
0x140077c64  lea     rcx, aIxptelassert; "IXPTelAssert"
0x140077c6b  mov     edx, [rbp+57h+arg_18]
0x140077c6e  mov     r8d, 313Eh
0x140077c74  call    MicrosoftTelemetryAssertTriggeredArgsKM
0x140077c79  mov     rcx, [r14]
0x140077c7c  mov     [rbp+57h+var_80], rcx
0x140077c80  cmp     rcx, [r14+8]
0x140077c84  jz      loc_140078165
0x140077c8a  mov     r14, [r15+18h]
0x140077c8e  test    r14, r14
0x140077c91  jz      short loc_140077C9F
0x140077c93  mov     eax, [r14+24h]
0x140077c97  test    al, al
0x140077c99  js      loc_1400782EE
0x140077c9f  mov     rcx, [r12]; Resource
0x140077ca3  call    cs:__imp_ExIsResourceAcquiredSharedLite
0x140077caa  nop     dword ptr [rax+rax+00h]
0x140077caf  test    eax, eax
0x140077cb1  jz      loc_140077F25
0x140077cb7  mov     eax, [r14+24h]
0x140077cbb  test    al, 20h
0x140077cbd  jnz     loc_1400781A4
0x140077cc3  mov     rdx, [rbp+57h+var_88]
0x140077cc7  mov     r8d, 1
0x140077ccd  jmp     short loc_140077CDD
0x140077ccf  xor     r8b, r8b
0x140077cd2  jmp     loc_140077B55
0x140077cd7  or      eax, 2
0x140077cda  mov     [rcx+30h], eax
0x140077cdd  cmp     rbx, rsi
0x140077ce0  jnz     loc_140077BE0
0x140077ce6  lea     r15, WPP_RECORDER_INITIALIZED
0x140077ced  lea     r13, WPP_GLOBAL_Control
0x140077cf4  cmp     edi, [rsi+10h]
0x140077cf7  jnz     loc_14007840A
0x140077cfd  mov     rcx, cs:WPP_GLOBAL_Control
0x140077d04  cmp     rcx, r13
0x140077d07  jz      short loc_140077D14
0x140077d09  mov     eax, [rcx+2Ch]
0x140077d0c  test    al, 8
0x140077d0e  jnz     loc_14007842B
0x140077d14  xor     dl, dl
0x140077d16  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140077d1d  jz      loc_14007809D
0x140077d23  cmp     word ptr [rcx+48h], 0
0x140077d28  jz      loc_14007809D
0x140077d2e  mov     r8b, 1
0x140077d31  test    dl, dl
0x140077d33  jnz     short loc_140077D3E
0x140077d35  test    r8b, r8b
0x140077d38  jz      loc_140077F1A
0x140077d3e  lea     r9, WPP_9da2ab7a54883028c158715a103b49be_Traceguids
0x140077d45  mov     [rsp+0E0h+var_A8], r9
0x140077d4a  mov     [rsp+0E0h+var_B0], 72h ; 'r'
0x140077d51  mov     r9, [rcx+40h]
0x140077d55  mov     rcx, [rcx+18h]
0x140077d59  mov     [rsp+0E0h+var_B8], 4
0x140077d61  mov     [rsp+0E0h+var_C0], 5
0x140077d66  call    WPP_RECORDER_AND_TRACE_SF_
0x140077d6b  jmp     loc_140077F1A
0x140077d70  mov     rcx, cs:WPP_GLOBAL_Control
0x140077d77  cmp     rcx, r13
0x140077d7a  jz      short loc_140077D87
0x140077d7c  mov     eax, [rcx+2Ch]
0x140077d7f  test    al, 8
0x140077d81  jnz     loc_140078133
0x140077d87  xor     dl, dl
0x140077d89  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140077d90  jz      short loc_140077D9D
0x140077d92  cmp     word ptr [rcx+48h], 0
0x140077d97  jnz     loc_1400780A5
0x140077d9d  xor     r8b, r8b
0x140077da0  test    dl, dl
0x140077da2  jnz     loc_1400780E3
0x140077da8  test    r8b, r8b
0x140077dab  jnz     loc_1400780E3
0x140077db1  cmp     [rbp+57h+var_58], 0
0x140077db5  jz      loc_140077EBF
0x140077dbb  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x140077dc2  nop     dword ptr [rax+rax+00h]
0x140077dc7  test    rax, rax
0x140077dca  jz      loc_1400780DC
0x140077dd0  mov     rcx, [rax]
0x140077dd3  mov     rax, [rbp+57h+var_70]
0x140077dd7  mov     [rcx+178h], rax
0x140077dde  call    cs:__imp_W32GetUserSessionState
0x140077de5  nop     dword ptr [rax+rax+00h]
0x140077dea  mov     rdi, [rbp+57h+var_78]
0x140077dee  mov     rbx, [rax+0C88h]
0x140077df5  mov     rcx, cs:WPP_GLOBAL_Control
0x140077dfc  cmp     rcx, r13
0x140077dff  jz      short loc_140077E0C
0x140077e01  mov     eax, [rcx+2Ch]
0x140077e04  test    al, 8
0x140077e06  jnz     loc_140078352
0x140077e0c  xor     dl, dl
0x140077e0e  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140077e15  jz      short loc_140077E22
0x140077e17  cmp     word ptr [rcx+48h], 0
0x140077e1c  jnz     loc_140078155
0x140077e22  xor     r8b, r8b
0x140077e25  test    dl, dl
0x140077e27  jnz     loc_140078363
0x140077e2d  test    r8b, r8b
0x140077e30  jnz     loc_140078363
0x140077e36  lea     rsi, WPP_9da2ab7a54883028c158715a103b49be_Traceguids
0x140077e3d  mov     rcx, [rbx+20h]; Resource
0x140077e41  call    cs:__imp_ExIsResourceAcquiredSharedLite
0x140077e48  nop     dword ptr [rax+rax+00h]
0x140077e4d  test    eax, eax
0x140077e4f  jnz     short loc_140077E6D
0x140077e51  mov     [rbp+57h+arg_10], 20000h
0x140077e58  lea     rcx, aIxptelassert; "IXPTelAssert"
0x140077e5f  mov     edx, [rbp+57h+arg_10]
0x140077e62  mov     r8d, 31B5h
0x140077e68  call    MicrosoftTelemetryAssertTriggeredArgsKM
0x140077e6d  mov     r8d, 8
0x140077e73  mov     rdx, rdi
0x140077e76  mov     rcx, rbx
0x140077e79  call    ?UnreferenceMsgData@CTouchProcessor@@AEAAX_KW4tagPOINTERMSGDATA_REFTYPE@@PEAX@Z; CTouchProcessor::UnreferenceMsgData(unsigned __int64,tagPOINTERMSGDATA_REFTYPE,void *)
0x140077e7e  mov     rcx, cs:WPP_GLOBAL_Control
0x140077e85  cmp     rcx, r13
0x140077e88  jz      short loc_140077E95
0x140077e8a  mov     eax, [rcx+2Ch]
0x140077e8d  test    al, 8
0x140077e8f  jnz     loc_140078144
0x140077e95  xor     dl, dl
0x140077e97  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140077e9e  jz      short loc_140077EAB
0x140077ea0  cmp     word ptr [rcx+48h], 0
0x140077ea5  jnz     loc_14007815D
0x140077eab  xor     r8b, r8b
0x140077eae  test    dl, dl
0x140077eb0  jnz     loc_140078395
0x140077eb6  test    r8b, r8b
0x140077eb9  jnz     loc_140078395
0x140077ebf  mov     rcx, [rbp+57h+var_50]
0x140077ec3  mov     rcx, [rcx]; Resource
0x140077ec6  call    cs:__imp_ExReleaseResourceAndLeaveCriticalRegion
0x140077ecd  nop     dword ptr [rax+rax+00h]
0x140077ed2  add     rsp, 0A8h
0x140077ed9  pop     r15
0x140077edb  pop     r14
0x140077edd  pop     r13
0x140077edf  pop     r12
0x140077ee1  pop     rdi
0x140077ee2  pop     rsi
0x140077ee3  pop     rbx
0x140077ee4  pop     rbp
0x140077ee5  retn
0x140077ee7  mov     rcx, cs:WPP_GLOBAL_Control
0x140077eee  cmp     rcx, r13
0x140077ef1  jnz     loc_1400780AD
0x140077ef7  xor     dl, dl
0x140077ef9  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140077f00  jnz     loc_1400780C9
0x140077f06  xor     r8b, r8b
0x140077f09  test    dl, dl
0x140077f0b  jnz     loc_140078341
0x140077f11  test    r8b, r8b
0x140077f14  jnz     loc_140078341
0x140077f1a  lea     rcx, [rbp+57h+var_78]; this
0x140077f1e  call    ?ThreadUnlockAndUnReference@CRefUnRefPointerMsgId@@QEAAXXZ; CRefUnRefPointerMsgId::ThreadUnlockAndUnReference(void)
0x140077f23  jmp     short loc_140077EBF
0x140077f25  mov     [rbp+57h+var_90], 20000h
0x140077f2c  lea     rcx, aIxptelassert; "IXPTelAssert"
0x140077f33  mov     edx, [rbp+57h+var_90]
0x140077f36  mov     r8d, 312Ah
0x140077f3c  call    MicrosoftTelemetryAssertTriggeredArgsKM
0x140077f41  jmp     loc_140077CB7
0x140077f46  cmp     [rbp+57h+var_58], 0
0x140077f4a  jnz     loc_140077B9C
0x140077f50  mov     [rbp+57h+var_58], 1
0x140077f54  call    cs:__imp_W32GetUserSessionState
0x140077f5b  nop     dword ptr [rax+rax+00h]
0x140077f60  mov     rdi, [rbp+57h+var_78]
0x140077f64  mov     rbx, [rax+0C88h]
0x140077f6b  mov     rcx, cs:WPP_GLOBAL_Control
0x140077f72  cmp     rcx, r13
0x140077f75  jz      short loc_140077F82
0x140077f77  mov     eax, [rcx+2Ch]
0x140077f7a  test    al, 8
0x140077f7c  jnz     loc_1400781CF
0x140077f82  xor     dl, dl
0x140077f84  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140077f8b  jnz     loc_140078062
0x140077f91  xor     r8b, r8b
0x140077f94  test    dl, dl
0x140077f96  jnz     loc_1400781E0
0x140077f9c  test    r8b, r8b
0x140077f9f  jnz     loc_1400781E0
0x140077fa5  mov     rcx, [rbx+20h]; Resource
0x140077fa9  call    cs:__imp_ExIsResourceAcquiredSharedLite
0x140077fb0  nop     dword ptr [rax+rax+00h]
0x140077fb5  test    eax, eax
0x140077fb7  jnz     short loc_140077FD5
0x140077fb9  mov     [rbp+57h+arg_10], 20000h
0x140077fc0  lea     rcx, aIxptelassert; "IXPTelAssert"
0x140077fc7  mov     edx, [rbp+57h+arg_10]
0x140077fca  mov     r8d, 31A0h
0x140077fd0  call    MicrosoftTelemetryAssertTriggeredArgsKM
0x140077fd5  mov     r8d, 8
0x140077fdb  mov     rdx, rdi
0x140077fde  mov     rcx, rbx
0x140077fe1  call    ?ReferenceMsgData@CTouchProcessor@@AEAAX_KW4tagPOINTERMSGDATA_REFTYPE@@PEAX@Z; CTouchProcessor::ReferenceMsgData(unsigned __int64,tagPOINTERMSGDATA_REFTYPE,void *)
0x140077fe6  mov     rcx, cs:WPP_GLOBAL_Control
0x140077fed  cmp     rcx, r13
0x140077ff0  jnz     loc_140078081
  ... truncated ...
```
