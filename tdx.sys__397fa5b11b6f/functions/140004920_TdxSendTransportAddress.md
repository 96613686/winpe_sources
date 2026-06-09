# TdxSendTransportAddress

- ea: `0x140004920`
- end: `0x140004dec`
- name: `TdxSendTransportAddress`
- size: `1228`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x140005fe0`

## callees

- `0x140002850`
- `0x140004920`
- `0x1400054ec`
- `0x140006b40`
- `0x140012f64`
- `0x140018590`
- `0x140018900`

## import_xrefs

- `ntoskrnl!KeLowerIrql` at `0x140004c72`
- `ntoskrnl!KeLowerIrql` at `0x140004c72`
- `ntoskrnl!ExAllocatePool2` at `0x1400049c2`
- `ntoskrnl!ExAllocatePool2` at `0x1400049c2`
- `ntoskrnl!IofCompleteRequest` at `0x140004c91`
- `ntoskrnl!IofCompleteRequest` at `0x140004cce`
- `ntoskrnl!IofCompleteRequest` at `0x140004d7f`
- `ntoskrnl!IofCompleteRequest` at `0x140004dd6`
- `ntoskrnl!IofCompleteRequest` at `0x140004c91`
- `ntoskrnl!IofCompleteRequest` at `0x140004cce`
- `ntoskrnl!IofCompleteRequest` at `0x140004d7f`
- `ntoskrnl!IofCompleteRequest` at `0x140004dd6`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140004c4d`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140004c4d`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140004c3d`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140004c62`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140004c3d`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140004c62`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000494f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400049e2`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140004aa7`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000494f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400049e2`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140004aa7`
- `ntoskrnl!RtlGetCallersAddress` at `0x140004a35`
- `ntoskrnl!RtlGetCallersAddress` at `0x140004aff`
- `ntoskrnl!RtlGetCallersAddress` at `0x140004a35`
- `ntoskrnl!RtlGetCallersAddress` at `0x140004aff`
- `ntoskrnl!KeReleaseSpinLock` at `0x140004a71`
- `ntoskrnl!KeReleaseSpinLock` at `0x140004b29`
- `ntoskrnl!KeReleaseSpinLock` at `0x140004b42`
- `ntoskrnl!KeReleaseSpinLock` at `0x140004caf`
- `ntoskrnl!KeReleaseSpinLock` at `0x140004d60`
- `ntoskrnl!KeReleaseSpinLock` at `0x140004db7`
- `ntoskrnl!KeReleaseSpinLock` at `0x140004a71`
- `ntoskrnl!KeReleaseSpinLock` at `0x140004b29`
- `ntoskrnl!KeReleaseSpinLock` at `0x140004b42`
- `ntoskrnl!KeReleaseSpinLock` at `0x140004caf`
- `ntoskrnl!KeReleaseSpinLock` at `0x140004d60`
- `ntoskrnl!KeReleaseSpinLock` at `0x140004db7`

## pseudocode

```c
__int64 __fastcall TdxSendTransportAddress(__int64 a1, IRP *a2, __int64 a3)
{
  KIRQL v5; // al
  KIRQL v6; // si
  __int64 v7; // rbx
  __int64 v8; // r12
  __int64 Pool2; // r15
  KIRQL v10; // al
  int v11; // ecx
  KIRQL v12; // di
  __int64 v13; // rdx
  __int64 v14; // rdx
  KIRQL v15; // al
  int v16; // ecx
  KIRQL v17; // di
  __int64 v18; // rdx
  __int64 v19; // r8
  unsigned int v20; // eax
  _QWORD v22[10]; // [rsp+30h] [rbp-88h] BYREF
  PVOID CallersAddress; // [rsp+C8h] [rbp+10h] BYREF
  __int64 v24; // [rsp+D0h] [rbp+18h]

  v24 = a3;
  memset(v22, 0, 0x48u);
  v5 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 8));
  v6 = v5;
  if ( a2->Cancel || (*(_DWORD *)a1 & 4) == 0 )
  {
    KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 8), v5);
    a2->IoStatus.Status = -1073741536;
    a2->IoStatus.Information = 0;
    IofCompleteRequest(a2, 2);
    return 3221225760LL;
  }
  if ( (*(_DWORD *)a1 & 0x40) == 0 )
  {
    if ( a1 )
    {
      v7 = a1;
      goto LABEL_6;
    }
LABEL_18:
    KeLowerIrql(v6);
    a2->IoStatus.Status = -1073741503;
    a2->IoStatus.Information = 0;
    IofCompleteRequest(a2, 2);
    return 3221225793LL;
  }
  v7 = *(_QWORD *)(a1 + 512);
  if ( !v7 )
  {
    KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)(a1 + 8));
    goto LABEL_18;
  }
  DbgTdxReferenceTransportAddress(*(_QWORD *)(a1 + 512), "minio\\netio\\session\\tdi\\address.h", 392);
  KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)(a1 + 8));
  KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)(v7 + 8));
LABEL_6:
  if ( (*(_DWORD *)v7 & 2) != 0 )
  {
    v8 = *(_QWORD *)(v7 + 40);
    Pool2 = ExAllocatePool2(64, 48, 1115186260);
    if ( Pool2 )
    {
      v10 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v8 + 216));
      v11 = *(_DWORD *)(v8 + 24);
      v12 = v10;
      v13 = *(unsigned int *)(v8 + 1184) + 7LL;
      CallersAddress = 0;
      v14 = v8 + 32 * v13;
      *(_DWORD *)(v14 + 24) = v11 + 1;
      *(_QWORD *)v14 = "minio\\netio\\session\\tdi\\request.c";
      *(_DWORD *)(v14 + 8) = 48;
      RtlGetCallersAddress(&CallersAddress, (PVOID *)(v14 + 16));
      *(_DWORD *)(v8 + 1184) = (*(_DWORD *)(v8 + 1184) + 1) % 0x1Eu;
      KeReleaseSpinLock((PKSPIN_LOCK)(v8 + 216), v12);
      _InterlockedIncrement((volatile signed __int32 *)(v8 + 24));
      *(_QWORD *)Pool2 = v8;
      *(_QWORD *)(Pool2 + 8) = a2;
      a2->Tail.Overlay.CurrentStackLocation->Control |= 1u;
      a2->Tail.Overlay.CurrentStackLocation->Control |= 1u;
      v15 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 552));
      v16 = *(_DWORD *)(a1 + 16) + 1;
      v17 = v15;
      v18 = a1 + 32LL * *(unsigned int *)(a1 + 816);
      CallersAddress = 0;
      *(_DWORD *)(v18 + 584) = v16;
      *(_QWORD *)(v18 + 560) = "minio\\netio\\session\\tdi\\address.c";
      *(_DWORD *)(v18 + 568) = 3197;
      RtlGetCallersAddress(&CallersAddress, (PVOID *)(v18 + 576));
      *(_DWORD *)(a1 + 816) = ((unsigned __int8)*(_DWORD *)(a1 + 816) + 1) & 7;
      KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 552), v17);
      _InterlockedIncrement((volatile signed __int32 *)(a1 + 16));
      KeReleaseSpinLock((PKSPIN_LOCK)(v7 + 8), v6);
      v19 = v24;
      *(_QWORD *)(Pool2 + 16) = 0;
      *(_QWORD *)(Pool2 + 24) = a2->MdlAddress;
      *(_DWORD *)(Pool2 + 32) = 0;
      *(_QWORD *)(Pool2 + 40) = *(unsigned int *)(v19 + 8);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
      {
        WPP_SF_qqd(WPP_GLOBAL_Control->AttachedDevice, 38, v19, a1, a2, *(_DWORD *)(v19 + 8));
      }
      v22[1] = Pool2;
      v22[0] = TdxMessageTlRequestComplete;
      LODWORD(v22[2]) = 0;
      v22[4] = 0;
      v22[5] = Pool2 + 16;
      v22[6] = 0;
      LODWORD(v22[7]) = 0;
      v22[8] = 0;
      v20 = (*(__int64 (__fastcall **)(_QWORD, _QWORD *))(*(_QWORD *)(v7 + 328) + 24LL))(*(_QWORD *)(v7 + 320), v22);
      if ( v20 != 259 )
        TdxMessageTlRequestComplete(Pool2, v20, v22[8]);
      if ( v7 != a1 )
        DbgTdxDereferenceTransportAddress(v7, "minio\\netio\\session\\tdi\\address.c", 3239);
      return 259;
    }
    else
    {
      KeReleaseSpinLock((PKSPIN_LOCK)(v7 + 8), v6);
      a2->IoStatus.Status = -1073741670;
      a2->IoStatus.Information = 0;
      IofCompleteRequest(a2, 2);
      if ( v7 != a1 )
        DbgTdxDereferenceTransportAddress(v7, "minio\\netio\\session\\tdi\\address.c", 3191);
      return 3221225626LL;
    }
  }
  else
  {
    KeReleaseSpinLock((PKSPIN_LOCK)(v7 + 8), v6);
    a2->IoStatus.Status = -1073741811;
    a2->IoStatus.Information = 0;
    IofCompleteRequest(a2, 2);
    if ( v7 != a1 )
      DbgTdxDereferenceTransportAddress(v7, "minio\\netio\\session\\tdi\\address.c", 3178);
    return 3221225485LL;
  }
}

```

## disassembly

```asm
0x140004920  mov     [rsp+arg_10], r8
0x140004925  push    rbp
0x140004926  push    rsi
0x140004927  push    rdi
0x140004928  push    r13
0x14000492a  push    r14
0x14000492c  sub     rsp, 90h
0x140004933  mov     r13, rdx
0x140004936  mov     r14, rcx
0x140004939  xor     edx, edx; Val
0x14000493b  lea     rcx, [rsp+0B8h+var_88]; void *
0x140004940  mov     r8d, 48h ; 'H'; Size
0x140004946  call    memset
0x14000494b  lea     rcx, [r14+8]; SpinLock
0x14000494f  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140004956  nop     dword ptr [rax+rax+00h]
0x14000495b  cmp     byte ptr [r13+44h], 0
0x140004960  movzx   esi, al
0x140004963  jnz     loc_140004DAF
0x140004969  mov     r8d, [r14]
0x14000496c  test    r8b, 4
0x140004970  jz      loc_140004DAF
0x140004976  mov     [rsp+0B8h+arg_18], rbx
0x14000497e  test    r8b, 40h
0x140004982  jnz     loc_140004C18
0x140004988  test    r14, r14
0x14000498b  jz      loc_140004C6E
0x140004991  mov     rbx, r14
0x140004994  mov     eax, [rbx]
0x140004996  mov     [rsp+0B8h+var_30], r12
0x14000499e  test    al, 2
0x1400049a0  jz      loc_140004CA7
0x1400049a6  mov     r12, [rbx+28h]
0x1400049aa  mov     edx, 30h ; '0'
0x1400049af  mov     ecx, 40h ; '@'
0x1400049b4  mov     [rsp+0B8h+var_38], r15
0x1400049bc  mov     r8d, 42786454h
0x1400049c2  call    cs:__imp_ExAllocatePool2
0x1400049c9  nop     dword ptr [rax+rax+00h]
0x1400049ce  mov     r15, rax
0x1400049d1  test    rax, rax
0x1400049d4  jz      loc_140004D58
0x1400049da  lea     rcx, [r12+0D8h]; SpinLock
0x1400049e2  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400049e9  nop     dword ptr [rax+rax+00h]
0x1400049ee  mov     ecx, [r12+18h]
0x1400049f3  xor     ebp, ebp
0x1400049f5  mov     edx, [r12+4A0h]
0x1400049fd  movzx   edi, al
0x140004a00  add     rdx, 7
0x140004a04  mov     [rsp+0B8h+CallersAddress], rbp
0x140004a0c  shl     rdx, 5
0x140004a10  lea     rax, aMinioNetioSess_0; "minio\\netio\\session\\tdi\\request.c"
0x140004a17  add     rdx, r12
0x140004a1a  inc     ecx
0x140004a1c  mov     [rdx+18h], ecx
0x140004a1f  lea     rcx, [rsp+0B8h+CallersAddress]; CallersAddress
0x140004a27  mov     [rdx], rax
0x140004a2a  mov     dword ptr [rdx+8], 30h ; '0'
0x140004a31  add     rdx, 10h; CallersCaller
0x140004a35  call    cs:__imp_RtlGetCallersAddress
0x140004a3c  nop     dword ptr [rax+rax+00h]
0x140004a41  mov     r8d, [r12+4A0h]
0x140004a49  lea     rcx, [r12+0D8h]; SpinLock
0x140004a51  inc     r8d
0x140004a54  mov     eax, 88888889h
0x140004a59  mul     r8d
0x140004a5c  shr     edx, 4
0x140004a5f  imul    eax, edx, 1Eh
0x140004a62  movzx   edx, dil; NewIrql
0x140004a66  sub     r8d, eax
0x140004a69  mov     [r12+4A0h], r8d
0x140004a71  call    cs:__imp_KeReleaseSpinLock
0x140004a78  nop     dword ptr [rax+rax+00h]
0x140004a7d  lock inc dword ptr [r12+18h]
0x140004a83  mov     [r15], r12
0x140004a86  lea     rcx, [r14+228h]; SpinLock
0x140004a8d  mov     [r15+8], r13
0x140004a91  mov     rax, [r13+0B8h]
0x140004a98  or      byte ptr [rax+3], 1
0x140004a9c  mov     rax, [r13+0B8h]
0x140004aa3  or      byte ptr [rax+3], 1
0x140004aa7  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140004aae  nop     dword ptr [rax+rax+00h]
0x140004ab3  mov     ecx, [r14+10h]
0x140004ab7  lea     r12, aMinioNetioSess_2; "minio\\netio\\session\\tdi\\address.c"
0x140004abe  mov     edx, [r14+330h]
0x140004ac5  inc     ecx
0x140004ac7  shl     rdx, 5
0x140004acb  movzx   edi, al
0x140004ace  add     rdx, r14
0x140004ad1  mov     [rsp+0B8h+CallersAddress], rbp
0x140004ad9  mov     [rdx+248h], ecx
0x140004adf  lea     rcx, [rsp+0B8h+CallersAddress]; CallersAddress
0x140004ae7  mov     [rdx+230h], r12
0x140004aee  mov     dword ptr [rdx+238h], 0C7Dh
0x140004af8  add     rdx, 240h; CallersCaller
0x140004aff  call    cs:__imp_RtlGetCallersAddress
0x140004b06  nop     dword ptr [rax+rax+00h]
0x140004b0b  mov     eax, [r14+330h]
0x140004b12  lea     rcx, [r14+228h]; SpinLock
0x140004b19  inc     eax
0x140004b1b  movzx   edx, dil; NewIrql
0x140004b1f  and     eax, 7
0x140004b22  mov     [r14+330h], eax
0x140004b29  call    cs:__imp_KeReleaseSpinLock
0x140004b30  nop     dword ptr [rax+rax+00h]
0x140004b35  lock inc dword ptr [r14+10h]
0x140004b3a  movzx   edx, sil; NewIrql
0x140004b3e  lea     rcx, [rbx+8]; SpinLock
0x140004b42  call    cs:__imp_KeReleaseSpinLock
0x140004b49  nop     dword ptr [rax+rax+00h]
0x140004b4e  mov     r8, [rsp+0B8h+arg_10]
0x140004b56  lea     rdi, [r15+10h]
0x140004b5a  mov     [rdi], rbp
0x140004b5d  mov     rax, [r13+8]
0x140004b61  mov     [r15+18h], rax
0x140004b65  mov     [r15+20h], ebp
0x140004b69  mov     eax, [r8+8]
0x140004b6d  mov     [r15+28h], rax
0x140004b71  mov     rcx, cs:WPP_GLOBAL_Control
0x140004b78  lea     rax, WPP_GLOBAL_Control
0x140004b7f  cmp     rcx, rax
0x140004b82  jz      short loc_140004B8E
0x140004b84  cmp     byte ptr [rcx+29h], 5
0x140004b88  jnb     loc_140004CFE
0x140004b8e  mov     [rsp+0B8h+var_80], r15
0x140004b93  lea     rax, TdxMessageTlRequestComplete
0x140004b9a  mov     [rsp+0B8h+var_88], rax
0x140004b9f  lea     rdx, [rsp+0B8h+var_88]
0x140004ba4  mov     [rsp+0B8h+var_78], ebp
0x140004ba8  mov     [rsp+0B8h+var_68], rbp
0x140004bad  mov     [rsp+0B8h+var_60], rdi
0x140004bb2  mov     [rsp+0B8h+var_58], rbp
0x140004bb7  mov     [rsp+0B8h+var_50], ebp
0x140004bbb  mov     [rsp+0B8h+var_48], rbp
0x140004bc0  mov     rax, [rbx+148h]
0x140004bc7  mov     rcx, [rbx+140h]
0x140004bce  mov     rax, [rax+18h]
0x140004bd2  call    _guard_dispatch_icall
0x140004bd7  cmp     eax, 103h
0x140004bdc  jnz     loc_140004D2E
0x140004be2  cmp     rbx, r14
0x140004be5  jnz     loc_140004D42
0x140004beb  mov     eax, 103h
0x140004bf0  mov     r15, [rsp+0B8h+var_38]
0x140004bf8  mov     r12, [rsp+0B8h+var_30]
0x140004c00  mov     rbx, [rsp+0B8h+arg_18]
0x140004c08  add     rsp, 90h
0x140004c0f  pop     r14
0x140004c11  pop     r13
0x140004c13  pop     rdi
0x140004c14  pop     rsi
0x140004c15  pop     rbp
0x140004c16  retn
0x140004c18  mov     rbx, [r14+200h]
0x140004c1f  test    rbx, rbx
0x140004c22  jz      short loc_140004C5E
0x140004c24  mov     r8d, 188h
0x140004c2a  lea     rdx, aMinioNetioSess; "minio\\netio\\session\\tdi\\address.h"
0x140004c31  mov     rcx, rbx
0x140004c34  call    DbgTdxReferenceTransportAddress
0x140004c39  lea     rcx, [r14+8]; SpinLock
0x140004c3d  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x140004c44  nop     dword ptr [rax+rax+00h]
0x140004c49  lea     rcx, [rbx+8]; SpinLock
0x140004c4d  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x140004c54  nop     dword ptr [rax+rax+00h]
0x140004c59  jmp     loc_140004994
0x140004c5e  lea     rcx, [r14+8]; SpinLock
0x140004c62  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x140004c69  nop     dword ptr [rax+rax+00h]
0x140004c6e  movzx   ecx, sil; NewIrql
0x140004c72  call    cs:__imp_KeLowerIrql
0x140004c79  nop     dword ptr [rax+rax+00h]
0x140004c7e  xor     ebp, ebp
0x140004c80  mov     dword ptr [r13+30h], 0C0000141h
0x140004c88  mov     dl, 2; PriorityBoost
0x140004c8a  mov     [r13+38h], rbp
0x140004c8e  mov     rcx, r13; Irp
0x140004c91  call    cs:__imp_IofCompleteRequest
0x140004c98  nop     dword ptr [rax+rax+00h]
0x140004c9d  mov     eax, 0C0000141h
0x140004ca2  jmp     loc_140004C00
0x140004ca7  movzx   edx, sil; NewIrql
0x140004cab  lea     rcx, [rbx+8]; SpinLock
0x140004caf  call    cs:__imp_KeReleaseSpinLock
0x140004cb6  nop     dword ptr [rax+rax+00h]
0x140004cbb  xor     ebp, ebp
0x140004cbd  mov     dword ptr [r13+30h], 0C000000Dh
0x140004cc5  mov     dl, 2; PriorityBoost
0x140004cc7  mov     [r13+38h], rbp
0x140004ccb  mov     rcx, r13; Irp
0x140004cce  call    cs:__imp_IofCompleteRequest
0x140004cd5  nop     dword ptr [rax+rax+00h]
0x140004cda  cmp     rbx, r14
0x140004cdd  jz      short loc_140004CF4
0x140004cdf  mov     r8d, 0C6Ah
0x140004ce5  lea     rdx, aMinioNetioSess_2; "minio\\netio\\session\\tdi\\address.c"
0x140004cec  mov     rcx, rbx
0x140004cef  call    DbgTdxDereferenceTransportAddress
0x140004cf4  mov     eax, 0C000000Dh
0x140004cf9  jmp     loc_140004BF8
0x140004cfe  test    dword ptr [rcx+2Ch], 200h
0x140004d05  jz      loc_140004B8E
0x140004d0b  mov     eax, [r8+8]
0x140004d0f  mov     edx, 26h ; '&'
0x140004d14  mov     rcx, [rcx+18h]
0x140004d18  mov     r9, r14
0x140004d1b  mov     [rsp+0B8h+var_90], eax
0x140004d1f  mov     [rsp+0B8h+var_98], r13
0x140004d24  call    WPP_SF_qqd
0x140004d29  jmp     loc_140004B8E
0x140004d2e  mov     r8, [rsp+0B8h+var_48]
0x140004d33  mov     edx, eax
0x140004d35  mov     rcx, r15
0x140004d38  call    TdxMessageTlRequestComplete
0x140004d3d  jmp     loc_140004BE2
0x140004d42  mov     r8d, 0CA7h
0x140004d48  mov     rdx, r12
0x140004d4b  mov     rcx, rbx
0x140004d4e  call    DbgTdxDereferenceTransportAddress
0x140004d53  jmp     loc_140004BEB
0x140004d58  movzx   edx, sil; NewIrql
0x140004d5c  lea     rcx, [rbx+8]; SpinLock
0x140004d60  call    cs:__imp_KeReleaseSpinLock
0x140004d67  nop     dword ptr [rax+rax+00h]
0x140004d6c  xor     ebp, ebp
0x140004d6e  mov     dword ptr [r13+30h], 0C000009Ah
0x140004d76  mov     dl, 2; PriorityBoost
0x140004d78  mov     [r13+38h], rbp
0x140004d7c  mov     rcx, r13; Irp
0x140004d7f  call    cs:__imp_IofCompleteRequest
0x140004d86  nop     dword ptr [rax+rax+00h]
0x140004d8b  cmp     rbx, r14
0x140004d8e  jz      short loc_140004DA5
0x140004d90  mov     r8d, 0C77h
0x140004d96  lea     rdx, aMinioNetioSess_2; "minio\\netio\\session\\tdi\\address.c"
0x140004d9d  mov     rcx, rbx
0x140004da0  call    DbgTdxDereferenceTransportAddress
0x140004da5  mov     eax, 0C000009Ah
0x140004daa  jmp     loc_140004BF0
0x140004daf  movzx   edx, sil; NewIrql
0x140004db3  lea     rcx, [r14+8]; SpinLock
0x140004db7  call    cs:__imp_KeReleaseSpinLock
0x140004dbe  nop     dword ptr [rax+rax+00h]
0x140004dc3  xor     ebp, ebp
0x140004dc5  mov     dword ptr [r13+30h], 0C0000120h
0x140004dcd  mov     dl, 2; PriorityBoost
0x140004dcf  mov     [r13+38h], rbp
0x140004dd3  mov     rcx, r13; Irp
0x140004dd6  call    cs:__imp_IofCompleteRequest
0x140004ddd  nop     dword ptr [rax+rax+00h]
0x140004de2  mov     eax, 0C0000120h
0x140004de7  jmp     loc_140004C08
```
