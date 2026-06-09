# TdxEventConnectConnection

- ea: `0x140002fb0`
- end: `0x1400034b9`
- name: `TdxEventConnectConnection`
- size: `1289`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140001550`
- `0x140001a70`

## callees

- `0x140001980`
- `0x140002ccc`
- `0x140002fb0`
- `0x1400034c0`
- `0x140003590`
- `0x1400047d0`
- `0x1400054ec`
- `0x140008620`
- `0x14000f4f0`
- `0x14001303c`
- `0x1400130bc`
- `0x140013d04`
- `0x140018600`

## import_xrefs

- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140003296`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140003296`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x140003282`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x140003282`
- `ntoskrnl!IofCompleteRequest` at `0x1400033ea`
- `ntoskrnl!IofCompleteRequest` at `0x1400033ea`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14000301a`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400032a6`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400032b6`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14000301a`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400032a6`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400032b6`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140003034`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14000325e`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14000326e`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400032d3`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140003034`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14000325e`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14000326e`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400032d3`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140003403`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140003403`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000304c`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000304c`

## pseudocode

```c
__int64 __fastcall TdxEventConnectConnection(__int64 a1, __int64 a2, __int64 a3, __int64 a4, KIRQL a5)
{
  _QWORD *v9; // r15
  bool v11; // si
  bool v12; // bp
  __int64 v13; // rdx
  __int64 v14; // rax
  char v15; // r15
  __int64 v16; // rdx
  _QWORD *v17; // rcx
  __int64 v18; // rax
  const char *v19; // rax
  unsigned int v20; // eax
  UCHAR v21; // al
  const void *v22; // rdx
  KSPIN_LOCK *v23; // rax
  bool v24; // bp
  __int64 v25; // r8
  __int64 v26; // rcx
  __int64 v27; // r8
  __int64 v28; // rcx
  ADDRESS_FAMILY *v29; // rcx
  __int64 v30; // r8
  KIRQL v31; // al
  __int64 v32; // r8
  KIRQL v33; // di
  __int128 v34; // [rsp+30h] [rbp-48h] BYREF
  int Irql; // [rsp+80h] [rbp+8h] BYREF
  __int64 v36; // [rsp+98h] [rbp+20h]

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
  {
    WPP_SF_sq(
      WPP_GLOBAL_Control->AttachedDevice,
      17,
      (unsigned int)WPP_3f4cea39b6aa324a7b8e41338ba6e995_Traceguids,
      (unsigned int)"TdxEventConnectConnection",
      a1);
  }
  v9 = *(_QWORD **)(a4 + 184);
  KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)(a1 + 8));
  if ( (unsigned int)(*(_DWORD *)(a1 + 76) - 1) <= 1 )
  {
    v11 = (*(_DWORD *)a1 & 0x40) != 0;
    if ( (*(_DWORD *)a1 & 0x40) != 0 )
      DbgTdxReferenceConnection(a1, "TdxEventConnectConnection", 393);
    v12 = _InterlockedExchange64((volatile __int64 *)(a4 + 104), 0) == 0;
    if ( (*(_DWORD *)a1 & 4) != 0 )
    {
      v13 = v9[2];
      v14 = v9[1];
      v15 = 0;
      v36 = v13;
      *(_QWORD *)&v34 = v14;
    }
    else
    {
      v16 = *(_QWORD *)(a4 + 168);
      if ( *(_QWORD *)(v16 + 8) != a4 + 168 || (v17 = *(_QWORD **)(a4 + 176), *v17 != a4 + 168) )
        __fastfail(3u);
      v18 = v9[3];
      v15 = 1;
      *v17 = v16;
      v36 = v18;
      *(_QWORD *)(v16 + 8) = v17;
      *(_QWORD *)&v34 = 0;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
    {
      v19 = "TRUE";
      if ( (*(_DWORD *)a1 & 0x1000) == 0 )
        v19 = "FALSE";
      WPP_SF_sqs(
        WPP_GLOBAL_Control->AttachedDevice,
        19,
        (unsigned int)WPP_3f4cea39b6aa324a7b8e41338ba6e995_Traceguids,
        (unsigned int)"TdxEventConnectConnection",
        a1,
        (__int64)v19);
    }
    v20 = *(_DWORD *)a1 & 0xFFFFFFF9;
    *(_DWORD *)(a1 + 76) = 4;
    *(_DWORD *)a1 = v20 | 0x1000;
    _InterlockedIncrement((volatile signed __int32 *)(a1 + 72));
    DbgTdxReferenceConnection(a1, "TdxEventConnectConnection", 451);
    *(_OWORD *)(a1 + 248) = 0;
    v21 = SOCKADDR_SIZE(**(_WORD **)(a3 + 24));
    memmove((void *)(a1 + 120), v22, v21);
    *(_QWORD *)(a1 + 264) = *(_QWORD *)(a3 + 40);
    *(_QWORD *)(a1 + 288) = *(_QWORD *)(a3 + 32);
    *(_QWORD *)(a3 + 64) = TdxConnectionConnectDispatch;
    *(_QWORD *)(a3 + 56) = a1;
    *(_QWORD *)(a1 + 336) = *(_QWORD *)(a2 + 424);
    *(_QWORD *)(a1 + 344) = *(_QWORD *)(a2 + 432);
    *(_QWORD *)(a1 + 352) = *(_QWORD *)(a2 + 440);
    *(_QWORD *)(a1 + 360) = *(_QWORD *)(a2 + 448);
    v23 = (KSPIN_LOCK *)(a2 + 8);
    if ( v12 )
    {
      LOBYTE(Irql) = 0;
      KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)(a1 + 8));
      KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)(a2 + 8));
      IoAcquireCancelSpinLock((PKIRQL)&Irql);
      IoReleaseCancelSpinLock(Irql);
      KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)(a2 + 8));
      KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)(a1 + 8));
      v23 = (KSPIN_LOCK *)(a2 + 8);
    }
    v24 = (*(_DWORD *)a2 & 0x40) != 0;
    KeReleaseSpinLockFromDpcLevel(v23);
    TdxSetOptionsConnection(a1, a5);
    if ( v36 )
    {
      v25 = *(_QWORD *)(v36 + 40);
      v26 = *(_QWORD *)(a3 + 24);
      Irql = *(_DWORD *)(v36 + 32);
      SockAddrToTaList(v26, v24, v25, &Irql);
    }
    if ( (_QWORD)v34 )
    {
      v27 = *(_QWORD *)(v34 + 40);
      v28 = *(_QWORD *)(a3 + 16);
      Irql = *(_DWORD *)(v34 + 32);
      SockAddrToTaList(v28, v24, v27, &Irql);
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
    {
      v29 = *(ADDRESS_FAMILY **)(a3 + 24);
      v34 = (unsigned __int64)v29;
      WORD4(v34) = SOCKADDR_SIZE(*v29);
      WPP_SF_sq_SOCKADDR_(*(_QWORD *)(v30 + 24), 20, v30, (unsigned int)"TdxEventConnectConnection", a1, (__int64)&v34);
    }
    if ( v15 )
      DbgTdxDereferenceTransportAddress(a2, "minio\\netio\\session\\tdi\\connection.c", 536);
    *(_DWORD *)(a4 + 48) = 0;
    *(_QWORD *)(a4 + 56) = 0;
    IofCompleteRequest((PIRP)a4, 2);
    if ( v11 )
    {
      v31 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 8));
      v33 = v31;
      if ( (*(_DWORD *)a1 & 0x200) != 0 || !*(_QWORD *)(a1 + 288) )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
        {
          WPP_SF_sq(
            WPP_GLOBAL_Control->AttachedDevice,
            21,
            (unsigned int)WPP_3f4cea39b6aa324a7b8e41338ba6e995_Traceguids,
            (unsigned int)"TdxEventConnectConnection",
            a1);
        }
        TdxShutdownEndpointConnection(a1, v33);
      }
      else
      {
        LOBYTE(v32) = 1;
        *(_DWORD *)a1 |= 0x200u;
        TdxDecrementTlEndpointReference(a1, v31, v32);
      }
      DbgTdxDereferenceConnection(a1, (__int64)"TdxEventConnectConnection", 564);
    }
    return 0;
  }
  else
  {
    KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)(a1 + 8));
    KeReleaseSpinLock((PKSPIN_LOCK)(a2 + 8), a5);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
    {
      WPP_SF_sq(
        WPP_GLOBAL_Control->AttachedDevice,
        18,
        (unsigned int)WPP_3f4cea39b6aa324a7b8e41338ba6e995_Traceguids,
        (unsigned int)"TdxEventConnectConnection",
        a1);
    }
    return 3221225792LL;
  }
}

```

## disassembly

```asm
0x140002fb0  push    rbx
0x140002fb2  push    rsi
0x140002fb3  push    rdi
0x140002fb4  push    r12
0x140002fb6  push    r13
0x140002fb8  push    r14
0x140002fba  push    r15
0x140002fbc  sub     rsp, 40h
0x140002fc0  mov     rdi, r9
0x140002fc3  mov     r13, r8
0x140002fc6  mov     r14, rdx
0x140002fc9  mov     rbx, rcx
0x140002fcc  mov     rcx, cs:WPP_GLOBAL_Control
0x140002fd3  lea     rsi, WPP_GLOBAL_Control
0x140002fda  cmp     rcx, rsi
0x140002fdd  jz      short loc_14000300F
0x140002fdf  cmp     byte ptr [rcx+29h], 5
0x140002fe3  jb      short loc_14000300F
0x140002fe5  test    dword ptr [rcx+2Ch], 200h
0x140002fec  jz      short loc_14000300F
0x140002fee  mov     rcx, [rcx+18h]
0x140002ff2  lea     r9, aTdxeventconnec; "TdxEventConnectConnection"
0x140002ff9  mov     edx, 11h
0x140002ffe  mov     [rsp+78h+var_58], rbx
0x140003003  lea     r8, WPP_3f4cea39b6aa324a7b8e41338ba6e995_Traceguids
0x14000300a  call    WPP_SF_sq
0x14000300f  mov     r15, [rdi+0B8h]
0x140003016  lea     rcx, [rbx+8]; SpinLock
0x14000301a  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x140003021  nop     dword ptr [rax+rax+00h]
0x140003026  mov     eax, [rbx+4Ch]
0x140003029  dec     eax
0x14000302b  cmp     eax, 1
0x14000302e  jbe     short loc_14000309E
0x140003030  lea     rcx, [rbx+8]; SpinLock
0x140003034  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x14000303b  nop     dword ptr [rax+rax+00h]
0x140003040  movzx   edx, [rsp+78h+arg_20]; NewIrql
0x140003048  lea     rcx, [r14+8]; SpinLock
0x14000304c  call    cs:__imp_KeReleaseSpinLock
0x140003053  nop     dword ptr [rax+rax+00h]
0x140003058  mov     rcx, cs:WPP_GLOBAL_Control
0x14000305f  cmp     rcx, rsi
0x140003062  jz      short loc_140003094
0x140003064  cmp     byte ptr [rcx+29h], 4
0x140003068  jb      short loc_140003094
0x14000306a  test    dword ptr [rcx+2Ch], 200h
0x140003071  jz      short loc_140003094
0x140003073  mov     rcx, [rcx+18h]
0x140003077  lea     r9, aTdxeventconnec; "TdxEventConnectConnection"
0x14000307e  mov     edx, 12h
0x140003083  mov     [rsp+78h+var_58], rbx
0x140003088  lea     r8, WPP_3f4cea39b6aa324a7b8e41338ba6e995_Traceguids
0x14000308f  call    WPP_SF_sq
0x140003094  mov     eax, 0C0000140h
0x140003099  jmp     loc_1400034A1
0x14000309e  mov     esi, [rbx]
0x1400030a0  mov     [rsp+78h+arg_8], rbp
0x1400030a8  xor     bpl, bpl
0x1400030ab  shr     esi, 6
0x1400030ae  and     sil, 1
0x1400030b2  jz      short loc_1400030C9
0x1400030b4  mov     r8d, 189h
0x1400030ba  lea     rdx, aTdxeventconnec; "TdxEventConnectConnection"
0x1400030c1  mov     rcx, rbx
0x1400030c4  call    DbgTdxReferenceConnection
0x1400030c9  xor     eax, eax
0x1400030cb  movzx   ebp, bpl
0x1400030cf  xchg    rax, [rdi+68h]
0x1400030d3  test    rax, rax
0x1400030d6  mov     ecx, 1
0x1400030db  mov     eax, [rbx]
0x1400030dd  cmovz   ebp, ecx
0x1400030e0  test    al, 4
0x1400030e2  jz      short loc_1400030FE
0x1400030e4  mov     rdx, [r15+10h]
0x1400030e8  mov     rax, [r15+8]
0x1400030ec  xor     r15b, r15b
0x1400030ef  mov     [rsp+78h+arg_18], rdx
0x1400030f7  mov     qword ptr [rsp+78h+var_48], rax
0x1400030fc  jmp     short loc_14000313E
0x1400030fe  lea     rax, [rdi+0A8h]
0x140003105  mov     rdx, [rax]
0x140003108  cmp     [rdx+8], rax
0x14000310c  jnz     loc_1400034B2
0x140003112  mov     rcx, [rax+8]
0x140003116  cmp     [rcx], rax
0x140003119  jnz     loc_1400034B2
0x14000311f  mov     rax, [r15+18h]
0x140003123  mov     r15b, 1
0x140003126  mov     [rcx], rdx
0x140003129  mov     [rsp+78h+arg_18], rax
0x140003131  mov     [rdx+8], rcx
0x140003135  mov     qword ptr [rsp+78h+var_48], 0
0x14000313e  mov     rcx, cs:WPP_GLOBAL_Control
0x140003145  lea     rax, WPP_GLOBAL_Control
0x14000314c  cmp     rcx, rax
0x14000314f  jz      short loc_14000319E
0x140003151  cmp     byte ptr [rcx+29h], 5
0x140003155  jb      short loc_14000319E
0x140003157  test    dword ptr [rcx+2Ch], 200h
0x14000315e  jz      short loc_14000319E
0x140003160  test    dword ptr [rbx], 1000h
0x140003166  lea     rdx, aFalse; "FALSE"
0x14000316d  mov     rcx, [rcx+18h]
0x140003171  lea     rax, aTrue; "TRUE"
0x140003178  cmovz   rax, rdx
0x14000317c  lea     r9, aTdxeventconnec; "TdxEventConnectConnection"
0x140003183  mov     [rsp+78h+var_50], rax
0x140003188  lea     r8, WPP_3f4cea39b6aa324a7b8e41338ba6e995_Traceguids
0x14000318f  mov     edx, 13h
0x140003194  mov     [rsp+78h+var_58], rbx
0x140003199  call    WPP_SF_sqs
0x14000319e  mov     eax, [rbx]
0x1400031a0  and     eax, 0FFFFFFF9h
0x1400031a3  mov     dword ptr [rbx+4Ch], 4
0x1400031aa  bts     eax, 0Ch
0x1400031ae  mov     [rbx], eax
0x1400031b0  lock inc dword ptr [rbx+48h]
0x1400031b4  mov     r8d, 1C3h
0x1400031ba  lea     rdx, aTdxeventconnec; "TdxEventConnectConnection"
0x1400031c1  mov     rcx, rbx
0x1400031c4  call    DbgTdxReferenceConnection
0x1400031c9  xorps   xmm0, xmm0
0x1400031cc  movups  xmmword ptr [rbx+0F8h], xmm0
0x1400031d3  mov     rdx, [r13+18h]
0x1400031d7  movzx   ecx, word ptr [rdx]; af
0x1400031da  call    SOCKADDR_SIZE
0x1400031df  movzx   r8d, al; Size
0x1400031e3  lea     rcx, [rbx+78h]; void *
0x1400031e7  call    memmove
0x1400031ec  mov     rax, [r13+28h]
0x1400031f0  mov     [rbx+108h], rax
0x1400031f7  mov     rax, [r13+20h]
0x1400031fb  mov     [rbx+120h], rax
0x140003202  lea     rax, TdxConnectionConnectDispatch
0x140003209  mov     [r13+40h], rax
0x14000320d  mov     [r13+38h], rbx
0x140003211  mov     rax, [r14+1A8h]
0x140003218  mov     [rbx+150h], rax
0x14000321f  mov     rax, [r14+1B0h]
0x140003226  mov     [rbx+158h], rax
0x14000322d  mov     rax, [r14+1B8h]
0x140003234  mov     [rbx+160h], rax
0x14000323b  mov     rax, [r14+1C0h]
0x140003242  mov     [rbx+168h], rax
0x140003249  lea     rax, [r14+8]
0x14000324d  test    bpl, bpl
0x140003250  jz      short loc_1400032C6
0x140003252  lea     rcx, [rbx+8]; SpinLock
0x140003256  mov     byte ptr [rsp+78h+Irql], 0
0x14000325e  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x140003265  nop     dword ptr [rax+rax+00h]
0x14000326a  lea     rcx, [r14+8]; SpinLock
0x14000326e  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x140003275  nop     dword ptr [rax+rax+00h]
0x14000327a  lea     rcx, [rsp+78h+Irql]; Irql
0x140003282  call    cs:__imp_IoAcquireCancelSpinLock
0x140003289  nop     dword ptr [rax+rax+00h]
0x14000328e  movzx   ecx, byte ptr [rsp+78h+Irql]; Irql
0x140003296  call    cs:__imp_IoReleaseCancelSpinLock
0x14000329d  nop     dword ptr [rax+rax+00h]
0x1400032a2  lea     rcx, [r14+8]; SpinLock
0x1400032a6  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x1400032ad  nop     dword ptr [rax+rax+00h]
0x1400032b2  lea     rcx, [rbx+8]; SpinLock
0x1400032b6  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x1400032bd  nop     dword ptr [rax+rax+00h]
0x1400032c2  lea     rax, [r14+8]
0x1400032c6  mov     ebp, [r14]
0x1400032c9  mov     rcx, rax; SpinLock
0x1400032cc  shr     ebp, 6
0x1400032cf  and     bpl, 1
0x1400032d3  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x1400032da  nop     dword ptr [rax+rax+00h]
0x1400032df  movzx   edx, [rsp+78h+arg_20]
0x1400032e7  mov     rcx, rbx
0x1400032ea  call    TdxSetOptionsConnection
0x1400032ef  mov     r8, [rsp+78h+arg_18]
0x1400032f7  test    r8, r8
0x1400032fa  jz      short loc_140003320
0x1400032fc  mov     eax, [r8+20h]
0x140003300  lea     r9, [rsp+78h+Irql]
0x140003308  mov     r8, [r8+28h]
0x14000330c  movzx   edx, bpl
0x140003310  mov     rcx, [r13+18h]
0x140003314  mov     [rsp+78h+Irql], eax
0x14000331b  call    SockAddrToTaList
0x140003320  mov     r8, qword ptr [rsp+78h+var_48]
0x140003325  test    r8, r8
0x140003328  jz      short loc_14000334E
0x14000332a  mov     eax, [r8+20h]
0x14000332e  lea     r9, [rsp+78h+Irql]
0x140003336  mov     r8, [r8+28h]
0x14000333a  movzx   edx, bpl
0x14000333e  mov     rcx, [r13+10h]
0x140003342  mov     [rsp+78h+Irql], eax
0x140003349  call    SockAddrToTaList
0x14000334e  mov     r8, cs:WPP_GLOBAL_Control
0x140003355  lea     rbp, WPP_GLOBAL_Control
0x14000335c  cmp     r8, rbp
0x14000335f  jz      short loc_1400033C2
0x140003361  cmp     byte ptr [r8+29h], 4
0x140003366  jb      short loc_1400033C2
0x140003368  test    dword ptr [r8+2Ch], 200h
0x140003370  jz      short loc_1400033C2
0x140003372  mov     rcx, [r13+18h]
0x140003376  xorps   xmm0, xmm0
0x140003379  movups  [rsp+78h+var_48], xmm0
0x14000337e  mov     qword ptr [rsp+78h+var_48], rcx
0x140003383  movzx   ecx, word ptr [rcx]; af
0x140003386  call    SOCKADDR_SIZE
0x14000338b  movzx   edx, al
0x14000338e  lea     r9, aTdxeventconnec; "TdxEventConnectConnection"
0x140003395  mov     word ptr [rsp+78h+var_48+8], dx
0x14000339a  lea     rax, [rsp+78h+var_48]
0x14000339f  movaps  xmm0, [rsp+78h+var_48]
0x1400033a4  mov     edx, 14h
0x1400033a9  movdqa  [rsp+78h+var_48], xmm0
0x1400033af  mov     rcx, [r8+18h]
0x1400033b3  mov     [rsp+78h+var_50], rax
0x1400033b8  mov     [rsp+78h+var_58], rbx
0x1400033bd  call    WPP_SF_sq_SOCKADDR_
0x1400033c2  test    r15b, r15b
0x1400033c5  jz      short loc_1400033DC
0x1400033c7  mov     r8d, 218h
0x1400033cd  lea     rdx, aMinioNetioSess_6; "minio\\netio\\session\\tdi\\connection."...
0x1400033d4  mov     rcx, r14
0x1400033d7  call    DbgTdxDereferenceTransportAddress
0x1400033dc  xor     eax, eax
0x1400033de  mov     dl, 2; PriorityBoost
0x1400033e0  mov     rcx, rdi; Irp
0x1400033e3  mov     [rdi+30h], eax
0x1400033e6  mov     [rdi+38h], rax
0x1400033ea  call    cs:__imp_IofCompleteRequest
0x1400033f1  nop     dword ptr [rax+rax+00h]
0x1400033f6  test    sil, sil
0x1400033f9  jz      loc_140003497
0x1400033ff  lea     rcx, [rbx+8]; SpinLock
0x140003403  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000340a  nop     dword ptr [rax+rax+00h]
0x14000340f  mov     ecx, [rbx]
0x140003411  movzx   edi, al
0x140003414  bt      ecx, 9
0x140003418  jb      short loc_14000343A
0x14000341a  cmp     qword ptr [rbx+120h], 0
0x140003422  jz      short loc_14000343A
0x140003424  bts     ecx, 9
0x140003428  mov     r8b, 1
0x14000342b  mov     [rbx], ecx
0x14000342d  movzx   edx, al
0x140003430  mov     rcx, rbx
0x140003433  call    TdxDecrementTlEndpointReference
0x140003438  jmp     short loc_140003482
0x14000343a  mov     rcx, cs:WPP_GLOBAL_Control
0x140003441  cmp     rcx, rbp
0x140003444  jz      short loc_140003476
0x140003446  cmp     byte ptr [rcx+29h], 4
0x14000344a  jb      short loc_140003476
0x14000344c  test    dword ptr [rcx+2Ch], 200h
0x140003453  jz      short loc_140003476
0x140003455  mov     rcx, [rcx+18h]
0x140003459  lea     r9, aTdxeventconnec; "TdxEventConnectConnection"
0x140003460  mov     edx, 15h
0x140003465  mov     [rsp+78h+var_58], rbx
0x14000346a  lea     r8, WPP_3f4cea39b6aa324a7b8e41338ba6e995_Traceguids
0x140003471  call    WPP_SF_sq
0x140003476  movzx   edx, dil
0x14000347a  mov     rcx, rbx
0x14000347d  call    TdxShutdownEndpointConnection
0x140003482  mov     r8d, 234h
0x140003488  lea     rdx, aTdxeventconnec; "TdxEventConnectConnection"
0x14000348f  mov     rcx, rbx
0x140003492  call    DbgTdxDereferenceConnection
0x140003497  mov     rbp, [rsp+78h+arg_8]
0x14000349f  xor     eax, eax
0x1400034a1  add     rsp, 40h
0x1400034a5  pop     r15
0x1400034a7  pop     r14
0x1400034a9  pop     r13
0x1400034ab  pop     r12
0x1400034ad  pop     rdi
0x1400034ae  pop     rsi
0x1400034af  pop     rbx
0x1400034b0  retn
0x1400034b2  mov     ecx, 3
0x1400034b7  int     29h; Win8: RtlFailFast(ecx)
```
