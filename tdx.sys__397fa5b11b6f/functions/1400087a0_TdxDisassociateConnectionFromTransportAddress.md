# TdxDisassociateConnectionFromTransportAddress

- ea: `0x1400087a0`
- end: `0x140008c40`
- name: `TdxDisassociateConnectionFromTransportAddress`
- size: `1184`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `7`
- tags: ``

## callers

- `0x1400039c0`
- `0x140003c9c`
- `0x1400075b0`

## callees

- `0x1400047d0`
- `0x1400054ec`
- `0x1400087a0`
- `0x140008c50`
- `0x140012b8c`
- `0x140013af4`
- `0x140013bf8`

## import_xrefs

- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140008b9c`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140008b9c`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x140008b88`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x140008b88`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400087f3`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140008bac`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140008bbc`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400087f3`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140008bac`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140008bbc`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140008882`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140008b25`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140008b64`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140008b74`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140008882`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140008b25`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140008b64`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140008b74`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400087df`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400088a9`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140008976`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400087df`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400088a9`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140008976`
- `ntoskrnl!RtlGetCallersAddress` at `0x140008905`
- `ntoskrnl!RtlGetCallersAddress` at `0x1400089cc`
- `ntoskrnl!RtlGetCallersAddress` at `0x140008905`
- `ntoskrnl!RtlGetCallersAddress` at `0x1400089cc`
- `ntoskrnl!KeReleaseSpinLock` at `0x140008896`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000892d`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400089f3`
- `ntoskrnl!KeReleaseSpinLock` at `0x140008b39`
- `ntoskrnl!KeReleaseSpinLock` at `0x140008896`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000892d`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400089f3`
- `ntoskrnl!KeReleaseSpinLock` at `0x140008b39`

## pseudocode

```c
__int64 __fastcall TdxDisassociateConnectionFromTransportAddress(__int64 a1, __int64 a2, __int64 a3)
{
  KIRQL v5; // r13
  __int64 v6; // rax
  __int64 v7; // rcx
  _QWORD *v8; // rdx
  _QWORD **v9; // rdi
  char v10; // r12
  _QWORD *v11; // rsi
  KIRQL v12; // al
  int v13; // ecx
  __int64 v14; // r14
  KIRQL v15; // di
  int v16; // edx
  int v17; // r8d
  KIRQL v18; // al
  int v19; // ecx
  KIRQL v20; // bl
  __int64 v21; // rdx
  __int64 v23; // rcx
  _QWORD *v24; // rax
  __int64 v25; // rdx
  _QWORD *v26; // rcx
  __int64 v27; // rax
  _QWORD *v28; // rcx
  PVOID CallersAddress; // [rsp+80h] [rbp+8h] BYREF
  __int64 v30; // [rsp+90h] [rbp+18h]

  v30 = a3;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
  {
    WPP_SF_qs(
      WPP_GLOBAL_Control->AttachedDevice,
      11,
      (unsigned int)WPP_3f4cea39b6aa324a7b8e41338ba6e995_Traceguids,
      a2,
      (__int64)"TdxDisassociateConnectionFromTransportAddress");
  }
  v5 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 8));
  KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)(a2 + 8));
  if ( *(_QWORD *)(a2 + 88) == a1 )
  {
    v6 = a2 + 272;
    v7 = *(_QWORD *)(a2 + 272);
    if ( *(_QWORD *)(*(_QWORD *)v6 + 8LL) != v6 || (v8 = *(_QWORD **)(a2 + 280), *v8 != v6) )
LABEL_36:
      __fastfail(3u);
    *v8 = v7;
    v9 = (_QWORD **)(a2 + 304);
    *(_QWORD *)(v7 + 8) = v8;
    v10 = 0;
    *(_DWORD *)a2 &= ~0x800u;
    *(_QWORD *)(a2 + 88) = 0;
    while ( 1 )
    {
      v11 = *v9;
      if ( *v9 == v9 )
        break;
      if ( !_InterlockedExchange64(v11 - 8, 0) )
        v10 = 1;
      v23 = *v11;
      if ( *(_QWORD **)(*v11 + 8LL) != v11 )
        goto LABEL_36;
      v24 = (_QWORD *)v11[1];
      if ( (_QWORD *)*v24 != v11 )
        goto LABEL_36;
      *v24 = v23;
      *(_QWORD *)(v23 + 8) = v24;
      v25 = *(v11 - 6);
      if ( *(_QWORD **)(v25 + 8) != v11 - 6 )
        goto LABEL_36;
      v26 = (_QWORD *)*(v11 - 5);
      if ( (_QWORD *)*v26 != v11 - 6 )
        goto LABEL_36;
      *v26 = v25;
      *(_QWORD *)(v25 + 8) = v26;
      DbgTdxDereferenceConnection(a2, (__int64)"TdxDisassociateConnectionFromTransportAddress", 3370);
      DbgTdxDereferenceTransportAddress(a1, (__int64)"minio\\netio\\session\\tdi\\address.c", 3371);
      v27 = v30;
      v28 = *(_QWORD **)(v30 + 8);
      if ( *v28 != v30 )
        goto LABEL_36;
      *v11 = v30;
      v11[1] = v28;
      *v28 = v11;
      *(_QWORD *)(v27 + 8) = v11;
    }
    if ( *(_DWORD *)(a2 + 76) == 1 )
      *(_DWORD *)(a2 + 76) = 0;
    if ( v10 )
    {
      LOBYTE(CallersAddress) = 0;
      KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)(a2 + 8));
      KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)(a1 + 8));
      IoAcquireCancelSpinLock((PKIRQL)&CallersAddress);
      IoReleaseCancelSpinLock((KIRQL)CallersAddress);
      KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)(a1 + 8));
      KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)(a2 + 8));
    }
    KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)(a2 + 8));
    KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 8), v5);
    v12 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a2 + 368));
    v13 = *(_DWORD *)(a2 + 16) - 1;
    v14 = a2 + 32LL * *(unsigned int *)(a2 + 632);
    CallersAddress = 0;
    v15 = v12;
    *(_DWORD *)(v14 + 400) = v13;
    *(_QWORD *)(v14 + 376) = "TdxDisassociateConnectionFromTransportAddress";
    *(_DWORD *)(v14 + 384) = 3415;
    RtlGetCallersAddress(&CallersAddress, (PVOID *)(v14 + 392));
    *(_DWORD *)(a2 + 632) = ((unsigned __int8)*(_DWORD *)(a2 + 632) + 1) & 7;
    KeReleaseSpinLock((PKSPIN_LOCK)(a2 + 368), v15);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
    {
      WPP_SF_qdssD(
        WPP_GLOBAL_Control->AttachedDevice,
        v16,
        v17,
        a2,
        *(_DWORD *)(v14 + 400),
        (__int64)"--",
        (__int64)"TdxDisassociateConnectionFromTransportAddress",
        87);
    }
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(a2 + 16), 0xFFFFFFFF) == 1 )
      TdxCleanupObjectHeader(a2);
    v18 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 552));
    v19 = *(_DWORD *)(a1 + 16);
    v20 = v18;
    v21 = a1 + 32LL * *(unsigned int *)(a1 + 816);
    CallersAddress = 0;
    *(_DWORD *)(v21 + 584) = v19 - 1;
    *(_QWORD *)(v21 + 560) = "minio\\netio\\session\\tdi\\address.c";
    *(_DWORD *)(v21 + 568) = 3416;
    RtlGetCallersAddress(&CallersAddress, (PVOID *)(v21 + 576));
    *(_DWORD *)(a1 + 816) = ((unsigned __int8)*(_DWORD *)(a1 + 816) + 1) & 7;
    KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 552), v20);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 16), 0xFFFFFFFF) == 1 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
      {
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 17, WPP_63c55c6b4ff2326ef703f60977e9aaef_Traceguids, a1);
      }
      TdxCleanupObjectHeader(a1);
    }
    return 0;
  }
  else
  {
    KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)(a2 + 8));
    KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 8), v5);
    return 0;
  }
}

```

## disassembly

```asm
0x1400087a0  mov     [rsp+arg_10], r8
0x1400087a5  push    rbx
0x1400087a6  push    rbp
0x1400087a7  push    r13
0x1400087a9  push    r14
0x1400087ab  push    r15
0x1400087ad  sub     rsp, 50h
0x1400087b1  mov     rbx, rdx
0x1400087b4  mov     rbp, rcx
0x1400087b7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400087be  lea     rax, WPP_GLOBAL_Control
0x1400087c5  lea     r8, aTdxdisassociat_0; "TdxDisassociateConnectionFromTransportA"...
0x1400087cc  cmp     rcx, rax
0x1400087cf  jz      short loc_1400087DB
0x1400087d1  cmp     byte ptr [rcx+29h], 5
0x1400087d5  jnb     loc_140008AF2
0x1400087db  lea     rcx, [rbp+8]; SpinLock
0x1400087df  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400087e6  nop     dword ptr [rax+rax+00h]
0x1400087eb  lea     rcx, [rbx+8]; SpinLock
0x1400087ef  movzx   r13d, al
0x1400087f3  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x1400087fa  nop     dword ptr [rax+rax+00h]
0x1400087ff  cmp     [rbx+58h], rbp
0x140008803  jnz     loc_140008B21
0x140008809  lea     rax, [rbx+110h]
0x140008810  mov     [rsp+78h+arg_8], rsi
0x140008818  mov     rcx, [rax]
0x14000881b  mov     [rsp+78h+var_30], rdi
0x140008820  mov     [rsp+78h+var_38], r12
0x140008825  cmp     [rcx+8], rax
0x140008829  jnz     loc_140008C39
0x14000882f  mov     rdx, [rax+8]
0x140008833  cmp     [rdx], rax
0x140008836  jnz     loc_140008C39
0x14000883c  mov     [rdx], rcx
0x14000883f  lea     rdi, [rbx+130h]
0x140008846  mov     [rcx+8], rdx
0x14000884a  xor     r12b, r12b
0x14000884d  and     dword ptr [rbx], 0FFFFF7FFh
0x140008853  mov     qword ptr [rbx+58h], 0
0x14000885b  mov     rsi, [rdi]
0x14000885e  mov     ecx, 1
0x140008863  cmp     rsi, rdi
0x140008866  jnz     loc_140008A49
0x14000886c  cmp     [rbx+4Ch], ecx
0x14000886f  jz      loc_140008B4C
0x140008875  test    r12b, r12b
0x140008878  jnz     loc_140008B58
0x14000887e  lea     rcx, [rbx+8]; SpinLock
0x140008882  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x140008889  nop     dword ptr [rax+rax+00h]
0x14000888e  movzx   edx, r13b; NewIrql
0x140008892  lea     rcx, [rbp+8]; SpinLock
0x140008896  call    cs:__imp_KeReleaseSpinLock
0x14000889d  nop     dword ptr [rax+rax+00h]
0x1400088a2  lea     rcx, [rbx+170h]; SpinLock
0x1400088a9  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400088b0  nop     dword ptr [rax+rax+00h]
0x1400088b5  mov     ecx, [rbx+10h]
0x1400088b8  lea     r13, aTdxdisassociat_0; "TdxDisassociateConnectionFromTransportA"...
0x1400088bf  mov     r14d, [rbx+278h]
0x1400088c6  dec     ecx
0x1400088c8  shl     r14, 5
0x1400088cc  xor     r12d, r12d
0x1400088cf  add     r14, rbx
0x1400088d2  mov     [rsp+78h+CallersAddress], r12
0x1400088da  movzx   edi, al
0x1400088dd  mov     [r14+190h], ecx
0x1400088e4  lea     rdx, [r14+188h]; CallersCaller
0x1400088eb  lea     rcx, [rsp+78h+CallersAddress]; CallersAddress
0x1400088f3  mov     [r14+178h], r13
0x1400088fa  mov     dword ptr [r14+180h], 0D57h
0x140008905  call    cs:__imp_RtlGetCallersAddress
0x14000890c  nop     dword ptr [rax+rax+00h]
0x140008911  mov     eax, [rbx+278h]
0x140008917  lea     rcx, [rbx+170h]; SpinLock
0x14000891e  inc     eax
0x140008920  movzx   edx, dil; NewIrql
0x140008924  and     eax, 7
0x140008927  mov     [rbx+278h], eax
0x14000892d  call    cs:__imp_KeReleaseSpinLock
0x140008934  nop     dword ptr [rax+rax+00h]
0x140008939  mov     rcx, cs:WPP_GLOBAL_Control
0x140008940  lea     r15, WPP_GLOBAL_Control
0x140008947  cmp     rcx, r15
0x14000894a  jz      short loc_140008956
0x14000894c  cmp     byte ptr [rcx+29h], 5
0x140008950  jnb     loc_140008BCD
0x140008956  mov     esi, 0FFFFFFFFh
0x14000895b  mov     eax, esi
0x14000895d  lock xadd [rbx+10h], eax
0x140008962  cmp     eax, 1
0x140008965  jnz     short loc_14000896F
0x140008967  mov     rcx, rbx
0x14000896a  call    TdxCleanupObjectHeader
0x14000896f  lea     rcx, [rbp+228h]; SpinLock
0x140008976  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000897d  nop     dword ptr [rax+rax+00h]
0x140008982  mov     ecx, [rbp+10h]
0x140008985  movzx   ebx, al
0x140008988  mov     edx, [rbp+330h]
0x14000898e  lea     rax, aMinioNetioSess_2; "minio\\netio\\session\\tdi\\address.c"
0x140008995  shl     rdx, 5
0x140008999  add     rdx, rbp
0x14000899c  mov     [rsp+78h+CallersAddress], r12
0x1400089a4  dec     ecx
0x1400089a6  mov     [rdx+248h], ecx
0x1400089ac  lea     rcx, [rsp+78h+CallersAddress]; CallersAddress
0x1400089b4  mov     [rdx+230h], rax
0x1400089bb  mov     dword ptr [rdx+238h], 0D58h
0x1400089c5  add     rdx, 240h; CallersCaller
0x1400089cc  call    cs:__imp_RtlGetCallersAddress
0x1400089d3  nop     dword ptr [rax+rax+00h]
0x1400089d8  mov     eax, [rbp+330h]
0x1400089de  lea     rcx, [rbp+228h]; SpinLock
0x1400089e5  inc     eax
0x1400089e7  movzx   edx, bl; NewIrql
0x1400089ea  and     eax, 7
0x1400089ed  mov     [rbp+330h], eax
0x1400089f3  call    cs:__imp_KeReleaseSpinLock
0x1400089fa  nop     dword ptr [rax+rax+00h]
0x1400089ff  lock xadd [rbp+10h], esi
0x140008a04  cmp     esi, 1
0x140008a07  jnz     short loc_140008A27
0x140008a09  mov     rcx, cs:WPP_GLOBAL_Control
0x140008a10  cmp     rcx, r15
0x140008a13  jz      short loc_140008A1F
0x140008a15  cmp     byte ptr [rcx+29h], 5
0x140008a19  jnb     loc_140008C0F
0x140008a1f  mov     rcx, rbp
0x140008a22  call    TdxCleanupObjectHeader
0x140008a27  mov     rdi, [rsp+78h+var_30]
0x140008a2c  xor     eax, eax
0x140008a2e  mov     rsi, [rsp+78h+arg_8]
0x140008a36  mov     r12, [rsp+78h+var_38]
0x140008a3b  add     rsp, 50h
0x140008a3f  pop     r15
0x140008a41  pop     r14
0x140008a43  pop     r13
0x140008a45  pop     rbp
0x140008a46  pop     rbx
0x140008a47  retn
0x140008a49  xor     eax, eax
0x140008a4b  movzx   r12d, r12b
0x140008a4f  xchg    rax, [rsi-40h]
0x140008a53  test    rax, rax
0x140008a56  cmovz   r12d, ecx
0x140008a5a  mov     rcx, [rsi]
0x140008a5d  cmp     [rcx+8], rsi
0x140008a61  jnz     loc_140008C39
0x140008a67  mov     rax, [rsi+8]
0x140008a6b  cmp     [rax], rsi
0x140008a6e  jnz     loc_140008C39
0x140008a74  mov     [rax], rcx
0x140008a77  mov     [rcx+8], rax
0x140008a7b  lea     rax, [rsi-30h]
0x140008a7f  mov     rdx, [rax]
0x140008a82  cmp     [rdx+8], rax
0x140008a86  jnz     loc_140008C39
0x140008a8c  mov     rcx, [rsi-28h]
0x140008a90  cmp     [rcx], rax
0x140008a93  jnz     loc_140008C39
0x140008a99  mov     [rcx], rdx
0x140008a9c  mov     r8d, 0D2Ah
0x140008aa2  mov     [rdx+8], rcx
0x140008aa6  lea     rdx, aTdxdisassociat_0; "TdxDisassociateConnectionFromTransportA"...
0x140008aad  mov     rcx, rbx
0x140008ab0  call    DbgTdxDereferenceConnection
0x140008ab5  mov     r8d, 0D2Bh
0x140008abb  lea     rdx, aMinioNetioSess_2; "minio\\netio\\session\\tdi\\address.c"
0x140008ac2  mov     rcx, rbp
0x140008ac5  call    DbgTdxDereferenceTransportAddress
0x140008aca  mov     rax, [rsp+78h+arg_10]
0x140008ad2  mov     rcx, [rax+8]
0x140008ad6  cmp     [rcx], rax
0x140008ad9  jnz     loc_140008C39
0x140008adf  mov     [rsi], rax
0x140008ae2  mov     [rsi+8], rcx
0x140008ae6  mov     [rcx], rsi
0x140008ae9  mov     [rax+8], rsi
0x140008aed  jmp     loc_14000885B
0x140008af2  test    dword ptr [rcx+2Ch], 200h
0x140008af9  jz      loc_1400087DB
0x140008aff  mov     rcx, [rcx+18h]
0x140008b03  mov     edx, 0Bh
0x140008b08  mov     [rsp+78h+var_58], r8
0x140008b0d  mov     r9, rbx
0x140008b10  lea     r8, WPP_3f4cea39b6aa324a7b8e41338ba6e995_Traceguids
0x140008b17  call    WPP_SF_qs
0x140008b1c  jmp     loc_1400087DB
0x140008b21  lea     rcx, [rbx+8]; SpinLock
0x140008b25  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x140008b2c  nop     dword ptr [rax+rax+00h]
0x140008b31  movzx   edx, r13b; NewIrql
0x140008b35  lea     rcx, [rbp+8]; SpinLock
0x140008b39  call    cs:__imp_KeReleaseSpinLock
0x140008b40  nop     dword ptr [rax+rax+00h]
0x140008b45  xor     eax, eax
0x140008b47  jmp     loc_140008A3B
0x140008b4c  mov     dword ptr [rbx+4Ch], 0
0x140008b53  jmp     loc_140008875
0x140008b58  lea     rcx, [rbx+8]; SpinLock
0x140008b5c  mov     byte ptr [rsp+78h+CallersAddress], 0
0x140008b64  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x140008b6b  nop     dword ptr [rax+rax+00h]
0x140008b70  lea     rcx, [rbp+8]; SpinLock
0x140008b74  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x140008b7b  nop     dword ptr [rax+rax+00h]
0x140008b80  lea     rcx, [rsp+78h+CallersAddress]; Irql
0x140008b88  call    cs:__imp_IoAcquireCancelSpinLock
0x140008b8f  nop     dword ptr [rax+rax+00h]
0x140008b94  movzx   ecx, byte ptr [rsp+78h+CallersAddress]; Irql
0x140008b9c  call    cs:__imp_IoReleaseCancelSpinLock
0x140008ba3  nop     dword ptr [rax+rax+00h]
0x140008ba8  lea     rcx, [rbp+8]; SpinLock
0x140008bac  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x140008bb3  nop     dword ptr [rax+rax+00h]
0x140008bb8  lea     rcx, [rbx+8]; SpinLock
0x140008bbc  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x140008bc3  nop     dword ptr [rax+rax+00h]
0x140008bc8  jmp     loc_14000887E
0x140008bcd  test    dword ptr [rcx+2Ch], 200h
0x140008bd4  jz      loc_140008956
0x140008bda  mov     rcx, [rcx+18h]
0x140008bde  lea     rax, asc_14001AAE0; "--"
0x140008be5  mov     [rsp+78h+var_40], 0D57h
0x140008bed  mov     r9, rbx
0x140008bf0  mov     [rsp+78h+var_48], r13
0x140008bf5  mov     [rsp+78h+var_50], rax
0x140008bfa  mov     eax, [r14+190h]
0x140008c01  mov     dword ptr [rsp+78h+var_58], eax
0x140008c05  call    WPP_SF_qdssD
0x140008c0a  jmp     loc_140008956
0x140008c0f  test    dword ptr [rcx+2Ch], 200h
0x140008c16  jz      loc_140008A1F
0x140008c1c  mov     rcx, [rcx+18h]
0x140008c20  lea     r8, WPP_63c55c6b4ff2326ef703f60977e9aaef_Traceguids
0x140008c27  mov     edx, 11h
0x140008c2c  mov     r9, rbp
0x140008c2f  call    WPP_SF_q
0x140008c34  jmp     loc_140008A1F
0x140008c39  mov     ecx, 3
0x140008c3e  int     29h; Win8: RtlFailFast(ecx)
```
