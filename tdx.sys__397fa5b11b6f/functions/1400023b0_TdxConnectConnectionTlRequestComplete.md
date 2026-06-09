# TdxConnectConnectionTlRequestComplete

- ea: `0x1400023b0`
- end: `0x14000283f`
- name: `TdxConnectConnectionTlRequestComplete`
- size: `1167`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x140004df4`

## callees

- `0x1400023b0`
- `0x140002ccc`
- `0x140003590`
- `0x1400047d0`
- `0x140008620`
- `0x14000f4f0`
- `0x14001303c`
- `0x140013af4`
- `0x140013bf8`
- `0x140013dc0`
- `0x1400140ac`

## import_xrefs

- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14000269c`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14000269c`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x140002688`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x140002688`
- `ntoskrnl!IofCompleteRequest` at `0x140002589`
- `ntoskrnl!IofCompleteRequest` at `0x1400025de`
- `ntoskrnl!IofCompleteRequest` at `0x140002589`
- `ntoskrnl!IofCompleteRequest` at `0x1400025de`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400026ac`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400026ac`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140002674`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140002674`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140002402`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000248d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000279f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140002402`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000248d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000279f`
- `ntoskrnl!RtlGetCallersAddress` at `0x1400024e5`
- `ntoskrnl!RtlGetCallersAddress` at `0x1400024e5`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000250d`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002570`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000250d`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002570`

## string_xrefs

- `0x1400023e8`: `TdxConnectConnectionTlRequestComplete`
- `0x1400024cc`: `TdxConnectConnectionTlRequestComplete`
- `0x140002654`: `TdxConnectConnectionTlRequestComplete`
- `0x1400026f2`: `TdxConnectConnectionTlRequestComplete`
- `0x14000271d`: `TdxConnectConnectionTlRequestComplete`
- `0x14000275b`: `TdxConnectConnectionTlRequestComplete`
- `0x1400027fc`: `TdxConnectConnectionTlRequestComplete`
- `0x14000282b`: `TdxConnectConnectionTlRequestComplete`

## pseudocode

```c
void __fastcall TdxConnectConnectionTlRequestComplete(__int64 a1, int a2, __int64 a3, __int64 a4)
{
  __int64 v4; // r14
  __int64 v6; // rbx
  KIRQL v8; // di
  int v9; // r8d
  int v10; // ebp
  char v11; // bp
  bool v12; // r12
  KIRQL v13; // di
  int v14; // ecx
  __int64 v15; // rax
  int v16; // edx
  int v17; // r8d
  const char *v18; // r8
  const char *v19; // rdx
  KIRQL v20; // al
  __int64 v21; // r8
  KIRQL v22; // di
  __int64 v23; // [rsp+40h] [rbp-48h]
  PVOID CallersAddress; // [rsp+90h] [rbp+8h] BYREF
  KIRQL Irql; // [rsp+98h] [rbp+10h] BYREF
  __int64 v26; // [rsp+A0h] [rbp+18h]

  v26 = a3;
  v4 = *(_QWORD *)(a1 + 16);
  v6 = *(_QWORD *)(a1 + 8);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
  {
    WPP_SF_qs(
      WPP_GLOBAL_Control->AttachedDevice,
      11,
      (unsigned int)WPP_3f4cea39b6aa324a7b8e41338ba6e995_Traceguids,
      v6,
      (__int64)"TdxConnectConnectionTlRequestComplete");
  }
  v8 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v6 + 8));
  v10 = *(_DWORD *)v6 >> 6;
  Irql = v8;
  *(_QWORD *)(v6 + 112) = 0;
  v11 = v10 & 1;
  if ( v11 )
    DbgTdxReferenceConnection(v6, "TdxConnectConnectionTlRequestComplete", 1789);
  v12 = _InterlockedExchange64((volatile __int64 *)(v4 + 104), 0) == 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
  {
    WPP_SF_sqd(
      WPP_GLOBAL_Control->AttachedDevice,
      42,
      v9,
      (unsigned int)"TdxConnectConnectionTlRequestComplete",
      v6,
      a2);
  }
  if ( a2 < 0 )
  {
    *(_DWORD *)(v6 + 76) = 0;
  }
  else
  {
    *(_QWORD *)(v6 + 288) = v26;
    *(_DWORD *)(v6 + 76) = 4;
    *(_QWORD *)(v6 + 264) = a4;
    _InterlockedIncrement((volatile signed __int32 *)(v6 + 72));
    v13 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v6 + 368));
    v14 = *(_DWORD *)(v6 + 16) + 1;
    v15 = 32LL * *(unsigned int *)(v6 + 632) + 376;
    CallersAddress = 0;
    v23 = v6 + v15;
    *(_DWORD *)(v23 + 24) = v14;
    *(_DWORD *)(v23 + 8) = 1818;
    *(_QWORD *)v23 = "TdxConnectConnectionTlRequestComplete";
    RtlGetCallersAddress(&CallersAddress, (PVOID *)(v6 + v15 + 16));
    *(_DWORD *)(v6 + 632) = ((unsigned __int8)*(_DWORD *)(v6 + 632) + 1) & 7;
    KeReleaseSpinLock((PKSPIN_LOCK)(v6 + 368), v13);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
    {
      WPP_SF_qdssD(
        WPP_GLOBAL_Control->AttachedDevice,
        v16,
        v17,
        v6,
        *(_DWORD *)(v23 + 24),
        (__int64)"++",
        (__int64)"TdxConnectConnectionTlRequestComplete",
        26);
    }
    _InterlockedIncrement((volatile signed __int32 *)(v6 + 16));
    v8 = Irql;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
  {
    v18 = "TRUE";
    if ( (*(_DWORD *)v6 & 0x1000) == 0 )
      v18 = "FALSE";
    v19 = "ConnectionClosed";
    if ( *(_DWORD *)(v6 + 76) )
      v19 = "ConnectionConnected";
    WPP_SF_sqss(
      WPP_GLOBAL_Control->AttachedDevice,
      (_DWORD)v19,
      (_DWORD)v18,
      (unsigned int)"ConnectionConnected",
      v6,
      (__int64)v19,
      (__int64)v18);
  }
  *(_DWORD *)v6 |= 0x1000u;
  if ( v12 )
  {
    Irql = 0;
    KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)(v6 + 8));
    IoAcquireCancelSpinLock(&Irql);
    IoReleaseCancelSpinLock(Irql);
    KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)(v6 + 8));
  }
  if ( v11 || a2 < 0 )
  {
    KeReleaseSpinLock((PKSPIN_LOCK)(v6 + 8), v8);
    *(_DWORD *)(v4 + 48) = a2;
    *(_QWORD *)(v4 + 56) = 0;
    IofCompleteRequest((PIRP)v4, 2);
    if ( a2 < 0 )
      DbgTdxDereferenceConnection(v6, "TdxConnectConnectionTlRequestComplete", 1878);
    if ( v11 )
    {
      v20 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v6 + 8));
      v22 = v20;
      if ( (*(_DWORD *)v6 & 0x200) != 0 || !*(_QWORD *)(v6 + 288) )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
        {
          WPP_SF_sq(
            WPP_GLOBAL_Control->AttachedDevice,
            44,
            (unsigned int)WPP_3f4cea39b6aa324a7b8e41338ba6e995_Traceguids,
            (unsigned int)"TdxConnectConnectionTlRequestComplete",
            v6);
        }
        TdxShutdownEndpointConnection(v6, v22);
      }
      else
      {
        LOBYTE(v21) = 1;
        *(_DWORD *)v6 |= 0x200u;
        TdxDecrementTlEndpointReference(v6, v20, v21);
      }
      DbgTdxDereferenceConnection(v6, "TdxConnectConnectionTlRequestComplete", 1896);
    }
  }
  else
  {
    TdxSetOptionsConnection(v6, v8);
    *(_DWORD *)(v4 + 48) = a2;
    *(_QWORD *)(v4 + 56) = 0;
    IofCompleteRequest((PIRP)v4, 2);
  }
}

```

## disassembly

```asm
0x1400023b0  mov     [rsp+arg_18], rbx
0x1400023b5  mov     [rsp+arg_10], r8
0x1400023ba  push    rbp
0x1400023bb  push    rsi
0x1400023bc  push    rdi
0x1400023bd  push    r12
0x1400023bf  push    r13
0x1400023c1  push    r14
0x1400023c3  push    r15
0x1400023c5  sub     rsp, 50h
0x1400023c9  mov     r14, [rcx+10h]
0x1400023cd  mov     rsi, r9
0x1400023d0  mov     rbx, [rcx+8]
0x1400023d4  mov     r15d, edx
0x1400023d7  xor     r12b, r12b
0x1400023da  mov     rcx, cs:WPP_GLOBAL_Control
0x1400023e1  lea     rax, WPP_GLOBAL_Control
0x1400023e8  lea     r8, aTdxconnectconn_0; "TdxConnectConnectionTlRequestComplete"
0x1400023ef  cmp     rcx, rax
0x1400023f2  jz      short loc_1400023FE
0x1400023f4  cmp     byte ptr [rcx+29h], 5
0x1400023f8  jnb     loc_1400026BD
0x1400023fe  lea     rcx, [rbx+8]; SpinLock
0x140002402  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140002409  nop     dword ptr [rax+rax+00h]
0x14000240e  mov     ebp, [rbx]
0x140002410  movzx   edi, al
0x140002413  shr     ebp, 6
0x140002416  mov     [rsp+88h+Irql], al
0x14000241d  mov     qword ptr [rbx+70h], 0
0x140002425  and     bpl, 1
0x140002429  jnz     loc_1400026EC
0x14000242f  xor     eax, eax
0x140002431  movzx   r12d, r12b
0x140002435  xchg    rax, [r14+68h]
0x140002439  test    rax, rax
0x14000243c  mov     ecx, 1
0x140002441  cmovz   r12d, ecx
0x140002445  mov     rcx, cs:WPP_GLOBAL_Control
0x14000244c  lea     rax, WPP_GLOBAL_Control
0x140002453  cmp     rcx, rax
0x140002456  jnz     loc_140002706
0x14000245c  test    r15d, r15d
0x14000245f  js      loc_140002744
0x140002465  mov     rax, [rsp+88h+arg_10]
0x14000246d  mov     [rbx+120h], rax
0x140002474  mov     dword ptr [rbx+4Ch], 4
0x14000247b  mov     [rbx+108h], rsi
0x140002482  lock inc dword ptr [rbx+48h]
0x140002486  lea     rcx, [rbx+170h]; SpinLock
0x14000248d  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140002494  nop     dword ptr [rax+rax+00h]
0x140002499  mov     ecx, [rbx+10h]
0x14000249c  movzx   edi, al
0x14000249f  mov     eax, [rbx+278h]
0x1400024a5  inc     ecx
0x1400024a7  shl     rax, 5
0x1400024ab  add     rax, 178h
0x1400024b1  mov     [rsp+88h+CallersAddress], 0
0x1400024bd  add     rax, rbx
0x1400024c0  mov     [rsp+88h+var_48], rax
0x1400024c5  mov     [rax+18h], ecx
0x1400024c8  lea     rdx, [rax+10h]; CallersCaller
0x1400024cc  lea     rcx, aTdxconnectconn_0; "TdxConnectConnectionTlRequestComplete"
0x1400024d3  mov     dword ptr [rax+8], 71Ah
0x1400024da  mov     [rax], rcx
0x1400024dd  lea     rcx, [rsp+88h+CallersAddress]; CallersAddress
0x1400024e5  call    cs:__imp_RtlGetCallersAddress
0x1400024ec  nop     dword ptr [rax+rax+00h]
0x1400024f1  mov     eax, [rbx+278h]
0x1400024f7  lea     rcx, [rbx+170h]; SpinLock
0x1400024fe  inc     eax
0x140002500  movzx   edx, dil; NewIrql
0x140002504  and     eax, 7
0x140002507  mov     [rbx+278h], eax
0x14000250d  call    cs:__imp_KeReleaseSpinLock
0x140002514  nop     dword ptr [rax+rax+00h]
0x140002519  mov     rcx, cs:WPP_GLOBAL_Control
0x140002520  lea     rax, WPP_GLOBAL_Control
0x140002527  cmp     rcx, rax
0x14000252a  jz      short loc_140002536
0x14000252c  cmp     byte ptr [rcx+29h], 5
0x140002530  jnb     loc_14000274E
0x140002536  lock inc dword ptr [rbx+10h]
0x14000253a  movzx   edi, [rsp+88h+Irql]
0x140002542  xor     esi, esi
0x140002544  mov     rcx, cs:WPP_GLOBAL_Control
0x14000254b  cmp     rcx, rax
0x14000254e  jnz     loc_1400025EC
0x140002554  or      dword ptr [rbx], 1000h
0x14000255a  test    r12b, r12b
0x14000255d  jnz     loc_140002668
0x140002563  test    bpl, bpl
0x140002566  jz      short loc_1400025C0
0x140002568  movzx   edx, dil; NewIrql
0x14000256c  lea     rcx, [rbx+8]; SpinLock
0x140002570  call    cs:__imp_KeReleaseSpinLock
0x140002577  nop     dword ptr [rax+rax+00h]
0x14000257c  mov     dl, 2; PriorityBoost
0x14000257e  mov     [r14+30h], r15d
0x140002582  mov     rcx, r14; Irp
0x140002585  mov     [r14+38h], rsi
0x140002589  call    cs:__imp_IofCompleteRequest
0x140002590  nop     dword ptr [rax+rax+00h]
0x140002595  test    r15d, r15d
0x140002598  js      loc_14000264E
0x14000259e  test    bpl, bpl
0x1400025a1  jnz     loc_14000279B
0x1400025a7  mov     rbx, [rsp+88h+arg_18]
0x1400025af  add     rsp, 50h
0x1400025b3  pop     r15
0x1400025b5  pop     r14
0x1400025b7  pop     r13
0x1400025b9  pop     r12
0x1400025bb  pop     rdi
0x1400025bc  pop     rsi
0x1400025bd  pop     rbp
0x1400025be  retn
0x1400025c0  test    r15d, r15d
0x1400025c3  js      short loc_140002568
0x1400025c5  movzx   edx, dil
0x1400025c9  mov     rcx, rbx
0x1400025cc  call    TdxSetOptionsConnection
0x1400025d1  mov     dl, 2; PriorityBoost
0x1400025d3  mov     [r14+30h], r15d
0x1400025d7  mov     rcx, r14; Irp
0x1400025da  mov     [r14+38h], rsi
0x1400025de  call    cs:__imp_IofCompleteRequest
0x1400025e5  nop     dword ptr [rax+rax+00h]
0x1400025ea  jmp     short loc_1400025A7
0x1400025ec  cmp     byte ptr [rcx+29h], 5
0x1400025f0  jb      loc_140002554
0x1400025f6  test    dword ptr [rcx+2Ch], 200h
0x1400025fd  jz      loc_140002554
0x140002603  test    dword ptr [rbx], 1000h
0x140002609  lea     rax, aFalse; "FALSE"
0x140002610  mov     rcx, [rcx+18h]
0x140002614  lea     r9, aConnectionconn; "ConnectionConnected"
0x14000261b  lea     r8, aTrue; "TRUE"
0x140002622  cmovz   r8, rax
0x140002626  lea     rdx, aConnectionclos; "ConnectionClosed"
0x14000262d  cmp     dword ptr [rbx+4Ch], 0
0x140002631  mov     [rsp+88h+var_58], r8
0x140002636  cmovnz  rdx, r9
0x14000263a  mov     [rsp+88h+var_60], rdx
0x14000263f  mov     [rsp+88h+var_68], rbx
0x140002644  call    WPP_SF_sqss
0x140002649  jmp     loc_140002554
0x14000264e  mov     r8d, 756h
0x140002654  lea     rdx, aTdxconnectconn_0; "TdxConnectConnectionTlRequestComplete"
0x14000265b  mov     rcx, rbx
0x14000265e  call    DbgTdxDereferenceConnection
0x140002663  jmp     loc_14000259E
0x140002668  lea     rcx, [rbx+8]; SpinLock
0x14000266c  mov     [rsp+88h+Irql], 0
0x140002674  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x14000267b  nop     dword ptr [rax+rax+00h]
0x140002680  lea     rcx, [rsp+88h+Irql]; Irql
0x140002688  call    cs:__imp_IoAcquireCancelSpinLock
0x14000268f  nop     dword ptr [rax+rax+00h]
0x140002694  movzx   ecx, [rsp+88h+Irql]; Irql
0x14000269c  call    cs:__imp_IoReleaseCancelSpinLock
0x1400026a3  nop     dword ptr [rax+rax+00h]
0x1400026a8  lea     rcx, [rbx+8]; SpinLock
0x1400026ac  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x1400026b3  nop     dword ptr [rax+rax+00h]
0x1400026b8  jmp     loc_140002563
0x1400026bd  test    dword ptr [rcx+2Ch], 200h
0x1400026c4  jz      loc_1400023FE
0x1400026ca  mov     rcx, [rcx+18h]
0x1400026ce  mov     edx, 0Bh
0x1400026d3  mov     [rsp+88h+var_68], r8
0x1400026d8  mov     r9, rbx
0x1400026db  lea     r8, WPP_3f4cea39b6aa324a7b8e41338ba6e995_Traceguids
0x1400026e2  call    WPP_SF_qs
0x1400026e7  jmp     loc_1400023FE
0x1400026ec  mov     r8d, 6FDh
0x1400026f2  lea     rdx, aTdxconnectconn_0; "TdxConnectConnectionTlRequestComplete"
0x1400026f9  mov     rcx, rbx
0x1400026fc  call    DbgTdxReferenceConnection
0x140002701  jmp     loc_14000242F
0x140002706  cmp     byte ptr [rcx+29h], 4
0x14000270a  jb      loc_14000245C
0x140002710  test    dword ptr [rcx+2Ch], 200h
0x140002717  jz      short loc_140002738
0x140002719  mov     rcx, [rcx+18h]
0x14000271d  lea     r9, aTdxconnectconn_0; "TdxConnectConnectionTlRequestComplete"
0x140002724  mov     edx, 2Ah ; '*'
0x140002729  mov     dword ptr [rsp+88h+var_60], r15d
0x14000272e  mov     [rsp+88h+var_68], rbx
0x140002733  call    WPP_SF_sqd
0x140002738  lea     rax, WPP_GLOBAL_Control
0x14000273f  jmp     loc_14000245C
0x140002744  xor     esi, esi
0x140002746  mov     [rbx+4Ch], esi
0x140002749  jmp     loc_140002544
0x14000274e  test    dword ptr [rcx+2Ch], 200h
0x140002755  jz      short loc_14000278F
0x140002757  mov     rcx, [rcx+18h]
0x14000275b  lea     rax, aTdxconnectconn_0; "TdxConnectConnectionTlRequestComplete"
0x140002762  mov     [rsp+88h+var_50], 71Ah
0x14000276a  mov     r9, rbx
0x14000276d  mov     [rsp+88h+var_58], rax
0x140002772  lea     rax, asc_14001A510; "++"
0x140002779  mov     [rsp+88h+var_60], rax
0x14000277e  mov     rax, [rsp+88h+var_48]
0x140002783  mov     eax, [rax+18h]
0x140002786  mov     dword ptr [rsp+88h+var_68], eax
0x14000278a  call    WPP_SF_qdssD
0x14000278f  lea     rax, WPP_GLOBAL_Control
0x140002796  jmp     loc_140002536
0x14000279b  lea     rcx, [rbx+8]; SpinLock
0x14000279f  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400027a6  nop     dword ptr [rax+rax+00h]
0x1400027ab  mov     ecx, [rbx]
0x1400027ad  movzx   edi, al
0x1400027b0  bt      ecx, 9
0x1400027b4  jb      short loc_1400027D6
0x1400027b6  cmp     qword ptr [rbx+120h], 0
0x1400027be  jz      short loc_1400027D6
0x1400027c0  bts     ecx, 9
0x1400027c4  mov     r8b, 1
0x1400027c7  mov     [rbx], ecx
0x1400027c9  movzx   edx, al
0x1400027cc  mov     rcx, rbx
0x1400027cf  call    TdxDecrementTlEndpointReference
0x1400027d4  jmp     short loc_140002825
0x1400027d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400027dd  lea     rax, WPP_GLOBAL_Control
0x1400027e4  cmp     rcx, rax
0x1400027e7  jz      short loc_140002819
0x1400027e9  cmp     byte ptr [rcx+29h], 4
0x1400027ed  jb      short loc_140002819
0x1400027ef  test    dword ptr [rcx+2Ch], 200h
0x1400027f6  jz      short loc_140002819
0x1400027f8  mov     rcx, [rcx+18h]
0x1400027fc  lea     r9, aTdxconnectconn_0; "TdxConnectConnectionTlRequestComplete"
0x140002803  mov     edx, 2Ch ; ','
0x140002808  mov     [rsp+88h+var_68], rbx
0x14000280d  lea     r8, WPP_3f4cea39b6aa324a7b8e41338ba6e995_Traceguids
0x140002814  call    WPP_SF_sq
0x140002819  movzx   edx, dil
0x14000281d  mov     rcx, rbx
0x140002820  call    TdxShutdownEndpointConnection
0x140002825  mov     r8d, 768h
0x14000282b  lea     rdx, aTdxconnectconn_0; "TdxConnectConnectionTlRequestComplete"
0x140002832  mov     rcx, rbx
0x140002835  call    DbgTdxDereferenceConnection
0x14000283a  jmp     loc_1400025A7
```
