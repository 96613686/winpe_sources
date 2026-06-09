# TdxDeleteConnection

- ea: `0x1400075b0`
- end: `0x140007b84`
- name: `TdxDeleteConnection`
- size: `1492`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x1400034f0`

## callees

- `0x140002850`
- `0x1400036b0`
- `0x1400043b0`
- `0x1400054ec`
- `0x1400075b0`
- `0x1400087a0`
- `0x140008c50`
- `0x14000f4f0`
- `0x14001303c`
- `0x140013af4`
- `0x140018590`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x140007a00`
- `ntoskrnl!IofCompleteRequest` at `0x140007a00`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400075e8`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000765e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140007739`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140007789`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400075e8`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000765e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140007739`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140007789`
- `ntoskrnl!RtlGetCallersAddress` at `0x1400076bf`
- `ntoskrnl!RtlGetCallersAddress` at `0x1400077e6`
- `ntoskrnl!RtlGetCallersAddress` at `0x1400076bf`
- `ntoskrnl!RtlGetCallersAddress` at `0x1400077e6`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000764b`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400076e7`
- `ntoskrnl!KeReleaseSpinLock` at `0x140007760`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000780e`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000784f`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400078fe`
- `ntoskrnl!KeReleaseSpinLock` at `0x140007a7b`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000764b`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400076e7`
- `ntoskrnl!KeReleaseSpinLock` at `0x140007760`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000780e`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000784f`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400078fe`
- `ntoskrnl!KeReleaseSpinLock` at `0x140007a7b`

## string_xrefs

- `0x140007798`: `TdxDeleteConnection`
- `0x14000789e`: `TdxDeleteConnection`
- `0x14000793f`: `TdxDeleteConnection`

## pseudocode

```c
__int64 __fastcall TdxDeleteConnection(int *a1, __int64 a2)
{
  KIRQL v4; // al
  __int64 v5; // r14
  KIRQL v6; // di
  KIRQL v7; // di
  int v8; // ecx
  int *v9; // r12
  int v10; // edx
  int v11; // r8d
  KIRQL v12; // dl
  __int64 v13; // rdi
  KIRQL v14; // al
  int v15; // ecx
  KIRQL v16; // di
  int *v17; // r14
  int v18; // edx
  int v19; // r8d
  int v21; // edx
  unsigned int v22; // eax
  __int64 v23; // rcx
  __int64 v24; // rax
  IRP *v25; // rcx
  __int64 v26; // rcx
  __int64 (__fastcall **v27)(__int64, __int128 *); // rax
  NTSTATUS v28; // eax
  _QWORD v29[2]; // [rsp+40h] [rbp-48h] BYREF
  __int128 v30; // [rsp+50h] [rbp-38h] BYREF
  PVOID CallersAddress; // [rsp+90h] [rbp+8h] BYREF

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
  {
    WPP_SF_sq(
      WPP_GLOBAL_Control->AttachedDevice,
      15,
      (unsigned int)WPP_3f4cea39b6aa324a7b8e41338ba6e995_Traceguids,
      (unsigned int)"TdxDeleteConnection",
      (char)a1);
  }
  v4 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)a1 + 1);
  v5 = *((_QWORD *)a1 + 11);
  v6 = v4;
  if ( v5 )
    DbgTdxReferenceTransportAddress(*((_QWORD *)a1 + 11), "minio\\netio\\session\\tdi\\connection.c", 269);
  if ( (*a1 & 0x200) == 0 && *((_QWORD *)a1 + 36) )
  {
    *a1 |= 0x200u;
    if ( _InterlockedExchangeAdd(a1 + 18, 0xFFFFFFFF) == 1 )
      TdxShutdownEndpointConnection(a1, v6);
    else
      KeReleaseSpinLock((PKSPIN_LOCK)a1 + 1, v6);
    v7 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)a1 + 46);
    v8 = a1[4] - 1;
    v9 = &a1[8 * a1[158]];
    CallersAddress = 0;
    v9[100] = v8;
    *((_QWORD *)v9 + 47) = "TdxDecrementTlEndpointReference";
    v9[96] = 368;
    RtlGetCallersAddress(&CallersAddress, (PVOID *)v9 + 49);
    a1[158] = ((unsigned __int8)a1[158] + 1) & 7;
    KeReleaseSpinLock((PKSPIN_LOCK)a1 + 46, v7);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
    {
      WPP_SF_qdssD(
        WPP_GLOBAL_Control->AttachedDevice,
        v10,
        v11,
        (_DWORD)a1,
        v9[100],
        (__int64)"--",
        (__int64)"TdxDecrementTlEndpointReference",
        112);
    }
    if ( _InterlockedExchangeAdd(a1 + 4, 0xFFFFFFFF) == 1 )
      TdxCleanupObjectHeader(a1);
    goto LABEL_12;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
  {
    WPP_SF_sq(
      WPP_GLOBAL_Control->AttachedDevice,
      16,
      (unsigned int)WPP_3f4cea39b6aa324a7b8e41338ba6e995_Traceguids,
      (unsigned int)"TdxDeleteConnection",
      (char)a1);
  }
  v30 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
  {
    WPP_SF_sq(
      WPP_GLOBAL_Control->AttachedDevice,
      54,
      (unsigned int)WPP_3f4cea39b6aa324a7b8e41338ba6e995_Traceguids,
      (unsigned int)"TdxShutdownEndpointConnection",
      (char)a1);
  }
  v21 = *a1;
  if ( (*a1 & 0x80u) != 0 )
    goto LABEL_31;
  v22 = a1[19];
  if ( v22 <= 1 )
    goto LABEL_31;
  if ( v22 - 2 <= 1 )
  {
    *a1 = v21 | 0x40;
    goto LABEL_31;
  }
  if ( a1[18] != ((*a1 & 0x200) == 0) )
  {
LABEL_31:
    KeReleaseSpinLock((PKSPIN_LOCK)a1 + 1, v6);
    goto LABEL_12;
  }
  *a1 = v21 | 0x80;
  KeReleaseSpinLock((PKSPIN_LOCK)a1 + 1, v6);
  v26 = *((_QWORD *)a1 + 36);
  *(_QWORD *)&v30 = TdxCloseConnectionEndpointTlRequestComplete;
  v27 = (__int64 (__fastcall **)(__int64, __int128 *))*((_QWORD *)a1 + 33);
  *((_QWORD *)&v30 + 1) = a1;
  v28 = (*v27)(v26, &v30);
  if ( v28 != 259 )
    TdxCloseConnectionEndpointTlRequestComplete((unsigned int *)a1, v28);
LABEL_12:
  if ( v5 )
  {
    v29[1] = v29;
    v29[0] = v29;
    TdxDisassociateConnectionFromTransportAddress(v5, a1, v29);
    while ( 1 )
    {
      v23 = v29[0];
      if ( (_QWORD *)v29[0] == v29 )
        break;
      if ( *(_QWORD **)(v29[0] + 8LL) != v29
        || (v24 = *(_QWORD *)v29[0], *(_QWORD *)(*(_QWORD *)v29[0] + 8LL) != v29[0]) )
      {
        __fastfail(3u);
      }
      v29[0] = *(_QWORD *)v29[0];
      *(_QWORD *)(v24 + 8) = v29;
      v25 = (IRP *)(v23 - 168);
      v25->IoStatus.Status = -1073741536;
      v25->IoStatus.Information = 0;
      IofCompleteRequest(v25, 2);
    }
    DbgTdxDereferenceTransportAddress(v5, "minio\\netio\\session\\tdi\\connection.c", 316);
  }
  v12 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)a1 + 1);
  if ( (*a1 & 1) != 0 )
  {
    KeReleaseSpinLock((PKSPIN_LOCK)a1 + 1, v12);
    return 3221225558LL;
  }
  else
  {
    v13 = *((_QWORD *)a1 + 5);
    *a1 |= 1u;
    KeReleaseSpinLock((PKSPIN_LOCK)a1 + 1, v12);
    if ( a2 )
      *(_BYTE *)(*(_QWORD *)(a2 + 184) + 3LL) |= 1u;
    *((_QWORD *)a1 + 6) = a2;
    if ( v13 )
      TdxDetachObjectFromTransport(v13, a1);
    v14 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)a1 + 46);
    v15 = a1[4] - 1;
    v16 = v14;
    v17 = &a1[8 * a1[158]];
    CallersAddress = 0;
    v17[100] = v15;
    *((_QWORD *)v17 + 47) = "TdxDeleteConnection";
    v17[96] = 327;
    RtlGetCallersAddress(&CallersAddress, (PVOID *)v17 + 49);
    a1[158] = ((unsigned __int8)a1[158] + 1) & 7;
    KeReleaseSpinLock((PKSPIN_LOCK)a1 + 46, v16);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
    {
      WPP_SF_qdssD(
        WPP_GLOBAL_Control->AttachedDevice,
        v18,
        v19,
        (_DWORD)a1,
        v17[100],
        (__int64)"--",
        (__int64)"TdxDeleteConnection",
        71);
    }
    if ( _InterlockedExchangeAdd(a1 + 4, 0xFFFFFFFF) == 1 )
      TdxCleanupObjectHeader(a1);
    return 259;
  }
}

```

## disassembly

```asm
0x1400075b0  mov     [rsp+arg_10], rbx
0x1400075b5  mov     [rsp+arg_18], rbp
0x1400075ba  push    rdi
0x1400075bb  push    r12
0x1400075bd  push    r13
0x1400075bf  push    r14
0x1400075c1  push    r15
0x1400075c3  sub     rsp, 60h
0x1400075c7  mov     r13, rdx
0x1400075ca  mov     rbx, rcx
0x1400075cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1400075d4  lea     r12, WPP_GLOBAL_Control
0x1400075db  cmp     rcx, r12
0x1400075de  jnz     loc_140007883
0x1400075e4  lea     rcx, [rbx+8]; SpinLock
0x1400075e8  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400075ef  nop     dword ptr [rax+rax+00h]
0x1400075f4  mov     r14, [rbx+58h]
0x1400075f8  movzx   edi, al
0x1400075fb  test    r14, r14
0x1400075fe  jnz     loc_140007ACD
0x140007604  mov     ecx, [rbx]
0x140007606  mov     r15d, 0FFFFFFFFh
0x14000760c  mov     [rsp+88h+arg_8], rsi
0x140007614  bt      ecx, 9
0x140007618  jb      loc_1400078C0
0x14000761e  cmp     qword ptr [rbx+120h], 0
0x140007626  jz      loc_1400078C0
0x14000762c  bts     ecx, 9
0x140007630  mov     eax, r15d
0x140007633  mov     [rbx], ecx
0x140007635  lock xadd [rbx+48h], eax
0x14000763a  movzx   edx, dil; NewIrql
0x14000763e  cmp     eax, 1
0x140007641  jz      loc_14000791F
0x140007647  lea     rcx, [rbx+8]; SpinLock
0x14000764b  call    cs:__imp_KeReleaseSpinLock
0x140007652  nop     dword ptr [rax+rax+00h]
0x140007657  lea     rcx, [rbx+170h]; SpinLock
0x14000765e  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140007665  nop     dword ptr [rax+rax+00h]
0x14000766a  mov     ecx, [rbx+10h]
0x14000766d  movzx   edi, al
0x140007670  mov     r12d, [rbx+278h]
0x140007677  lea     rax, aTdxdecrementtl; "TdxDecrementTlEndpointReference"
0x14000767e  dec     ecx
0x140007680  shl     r12, 5
0x140007684  add     r12, rbx
0x140007687  mov     [rsp+88h+CallersAddress], 0
0x140007693  mov     [r12+190h], ecx
0x14000769b  lea     rdx, [r12+188h]; CallersCaller
0x1400076a3  lea     rcx, [rsp+88h+CallersAddress]; CallersAddress
0x1400076ab  mov     [r12+178h], rax
0x1400076b3  mov     dword ptr [r12+180h], 170h
0x1400076bf  call    cs:__imp_RtlGetCallersAddress
0x1400076c6  nop     dword ptr [rax+rax+00h]
0x1400076cb  mov     eax, [rbx+278h]
0x1400076d1  lea     rcx, [rbx+170h]; SpinLock
0x1400076d8  inc     eax
0x1400076da  movzx   edx, dil; NewIrql
0x1400076de  and     eax, 7
0x1400076e1  mov     [rbx+278h], eax
0x1400076e7  call    cs:__imp_KeReleaseSpinLock
0x1400076ee  nop     dword ptr [rax+rax+00h]
0x1400076f3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400076fa  lea     rax, WPP_GLOBAL_Control
0x140007701  cmp     rcx, rax
0x140007704  jz      short loc_140007710
0x140007706  cmp     byte ptr [rcx+29h], 5
0x14000770a  jnb     loc_140007AE7
0x140007710  mov     eax, r15d
0x140007713  lock xadd [rbx+10h], eax
0x140007718  cmp     eax, 1
0x14000771b  jnz     short loc_140007725
0x14000771d  mov     rcx, rbx
0x140007720  call    TdxCleanupObjectHeader
0x140007725  lea     r12, WPP_GLOBAL_Control
0x14000772c  test    r14, r14
0x14000772f  jnz     loc_140007961
0x140007735  lea     rcx, [rbx+8]; SpinLock
0x140007739  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140007740  nop     dword ptr [rax+rax+00h]
0x140007745  mov     ecx, [rbx]
0x140007747  movzx   edx, al; NewIrql
0x14000774a  test    cl, 1
0x14000774d  jnz     loc_14000784B
0x140007753  mov     rdi, [rbx+28h]
0x140007757  or      ecx, 1
0x14000775a  mov     [rbx], ecx
0x14000775c  lea     rcx, [rbx+8]; SpinLock
0x140007760  call    cs:__imp_KeReleaseSpinLock
0x140007767  nop     dword ptr [rax+rax+00h]
0x14000776c  test    r13, r13
0x14000776f  jnz     loc_14000790F
0x140007775  mov     [rbx+30h], r13
0x140007779  test    rdi, rdi
0x14000777c  jnz     loc_1400079AE
0x140007782  lea     rcx, [rbx+170h]; SpinLock
0x140007789  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140007790  nop     dword ptr [rax+rax+00h]
0x140007795  mov     ecx, [rbx+10h]
0x140007798  lea     rbp, aTdxdeleteconne; "TdxDeleteConnection"
0x14000779f  mov     r14d, [rbx+278h]
0x1400077a6  dec     ecx
0x1400077a8  shl     r14, 5
0x1400077ac  movzx   edi, al
0x1400077af  add     r14, rbx
0x1400077b2  mov     [rsp+88h+CallersAddress], 0
0x1400077be  mov     [r14+190h], ecx
0x1400077c5  lea     rdx, [r14+188h]; CallersCaller
0x1400077cc  lea     rcx, [rsp+88h+CallersAddress]; CallersAddress
0x1400077d4  mov     [r14+178h], rbp
0x1400077db  mov     dword ptr [r14+180h], 147h
0x1400077e6  call    cs:__imp_RtlGetCallersAddress
0x1400077ed  nop     dword ptr [rax+rax+00h]
0x1400077f2  mov     eax, [rbx+278h]
0x1400077f8  lea     rcx, [rbx+170h]; SpinLock
0x1400077ff  inc     eax
0x140007801  movzx   edx, dil; NewIrql
0x140007805  and     eax, 7
0x140007808  mov     [rbx+278h], eax
0x14000780e  call    cs:__imp_KeReleaseSpinLock
0x140007815  nop     dword ptr [rax+rax+00h]
0x14000781a  mov     rcx, cs:WPP_GLOBAL_Control
0x140007821  cmp     rcx, r12
0x140007824  jz      short loc_140007830
0x140007826  cmp     byte ptr [rcx+29h], 5
0x14000782a  jnb     loc_140007B42
0x140007830  lock xadd [rbx+10h], r15d
0x140007836  cmp     r15d, 1
0x14000783a  jnz     short loc_140007844
0x14000783c  mov     rcx, rbx
0x14000783f  call    TdxCleanupObjectHeader
0x140007844  mov     eax, 103h
0x140007849  jmp     short loc_140007860
0x14000784b  lea     rcx, [rbx+8]; SpinLock
0x14000784f  call    cs:__imp_KeReleaseSpinLock
0x140007856  nop     dword ptr [rax+rax+00h]
0x14000785b  mov     eax, 0C0000056h
0x140007860  mov     rsi, [rsp+88h+arg_8]
0x140007868  lea     r11, [rsp+88h+var_28]
0x14000786d  mov     rbx, [r11+40h]
0x140007871  mov     rbp, [r11+48h]
0x140007875  mov     rsp, r11
0x140007878  pop     r15
0x14000787a  pop     r14
0x14000787c  pop     r13
0x14000787e  pop     r12
0x140007880  pop     rdi
0x140007881  retn
0x140007883  cmp     byte ptr [rcx+29h], 5
0x140007887  jb      loc_1400075E4
0x14000788d  test    dword ptr [rcx+2Ch], 200h
0x140007894  jz      loc_1400075E4
0x14000789a  mov     rcx, [rcx+18h]
0x14000789e  lea     r9, aTdxdeleteconne; "TdxDeleteConnection"
0x1400078a5  mov     edx, 0Fh
0x1400078aa  mov     [rsp+88h+var_68], rbx
0x1400078af  lea     r8, WPP_3f4cea39b6aa324a7b8e41338ba6e995_Traceguids
0x1400078b6  call    WPP_SF_sq
0x1400078bb  jmp     loc_1400075E4
0x1400078c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400078c7  cmp     rcx, r12
0x1400078ca  jnz     short loc_14000792C
0x1400078cc  xorps   xmm0, xmm0
0x1400078cf  movups  [rsp+88h+var_38], xmm0
0x1400078d4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400078db  cmp     rcx, r12
0x1400078de  jnz     loc_140007A11
0x1400078e4  mov     edx, [rbx]
0x1400078e6  test    dl, dl
0x1400078e8  js      short loc_1400078F6
0x1400078ea  mov     eax, [rbx+4Ch]
0x1400078ed  cmp     eax, 1
0x1400078f0  ja      loc_140007A4E
0x1400078f6  movzx   edx, dil; NewIrql
0x1400078fa  lea     rcx, [rbx+8]; SpinLock
0x1400078fe  call    cs:__imp_KeReleaseSpinLock
0x140007905  nop     dword ptr [rax+rax+00h]
0x14000790a  jmp     loc_14000772C
0x14000790f  mov     rax, [r13+0B8h]
0x140007916  or      byte ptr [rax+3], 1
0x14000791a  jmp     loc_140007775
0x14000791f  mov     rcx, rbx
0x140007922  call    TdxShutdownEndpointConnection
0x140007927  jmp     loc_140007657
0x14000792c  cmp     byte ptr [rcx+29h], 4
0x140007930  jb      short loc_1400078CC
0x140007932  test    dword ptr [rcx+2Ch], 200h
0x140007939  jz      short loc_1400078CC
0x14000793b  mov     rcx, [rcx+18h]
0x14000793f  lea     r9, aTdxdeleteconne; "TdxDeleteConnection"
0x140007946  mov     edx, 10h
0x14000794b  mov     [rsp+88h+var_68], rbx
0x140007950  lea     r8, WPP_3f4cea39b6aa324a7b8e41338ba6e995_Traceguids
0x140007957  call    WPP_SF_sq
0x14000795c  jmp     loc_1400078CC
0x140007961  lea     rax, [rsp+88h+var_48]
0x140007966  mov     rdx, rbx
0x140007969  mov     [rsp+88h+var_40], rax
0x14000796e  lea     r8, [rsp+88h+var_48]
0x140007973  lea     rax, [rsp+88h+var_48]
0x140007978  mov     rcx, r14
0x14000797b  mov     [rsp+88h+var_48], rax
0x140007980  call    TdxDisassociateConnectionFromTransportAddress
0x140007985  mov     rcx, [rsp+88h+var_48]
0x14000798a  lea     rax, [rsp+88h+var_48]
0x14000798f  cmp     rcx, rax
0x140007992  jnz     short loc_1400079BE
0x140007994  mov     r8d, 13Ch
0x14000799a  lea     rdx, aMinioNetioSess_6; "minio\\netio\\session\\tdi\\connection."...
0x1400079a1  mov     rcx, r14
0x1400079a4  call    DbgTdxDereferenceTransportAddress
0x1400079a9  jmp     loc_140007735
0x1400079ae  mov     rdx, rbx
0x1400079b1  mov     rcx, rdi
0x1400079b4  call    TdxDetachObjectFromTransport
0x1400079b9  jmp     loc_140007782
0x1400079be  lea     rax, [rsp+88h+var_48]
0x1400079c3  cmp     [rcx+8], rax
0x1400079c7  jnz     loc_140007B3B
0x1400079cd  mov     rax, [rcx]
0x1400079d0  cmp     [rax+8], rcx
0x1400079d4  jnz     loc_140007B3B
0x1400079da  mov     [rsp+88h+var_48], rax
0x1400079df  lea     rdx, [rsp+88h+var_48]
0x1400079e4  mov     [rax+8], rdx
0x1400079e8  add     rcx, 0FFFFFFFFFFFFFF58h; Irp
0x1400079ef  mov     dl, 2; PriorityBoost
0x1400079f1  mov     dword ptr [rcx+30h], 0C0000120h
0x1400079f8  mov     qword ptr [rcx+38h], 0
0x140007a00  call    cs:__imp_IofCompleteRequest
0x140007a07  nop     dword ptr [rax+rax+00h]
0x140007a0c  jmp     loc_140007985
0x140007a11  cmp     byte ptr [rcx+29h], 4
0x140007a15  jb      loc_1400078E4
0x140007a1b  test    dword ptr [rcx+2Ch], 200h
0x140007a22  jz      loc_1400078E4
0x140007a28  mov     rcx, [rcx+18h]
0x140007a2c  lea     r9, aTdxshutdownend; "TdxShutdownEndpointConnection"
0x140007a33  mov     edx, 36h ; '6'
0x140007a38  mov     [rsp+88h+var_68], rbx
0x140007a3d  lea     r8, WPP_3f4cea39b6aa324a7b8e41338ba6e995_Traceguids
0x140007a44  call    WPP_SF_sq
0x140007a49  jmp     loc_1400078E4
0x140007a4e  add     eax, 0FFFFFFFEh
0x140007a51  cmp     eax, 1
0x140007a54  jbe     loc_140007B31
0x140007a5a  mov     ecx, edx
0x140007a5c  shr     ecx, 9
0x140007a5f  not     ecx
0x140007a61  and     ecx, 1
0x140007a64  cmp     [rbx+48h], ecx
0x140007a67  jnz     loc_1400078F6
0x140007a6d  bts     edx, 7
0x140007a71  lea     rcx, [rbx+8]; SpinLock
0x140007a75  mov     [rbx], edx
0x140007a77  movzx   edx, dil; NewIrql
0x140007a7b  call    cs:__imp_KeReleaseSpinLock
0x140007a82  nop     dword ptr [rax+rax+00h]
0x140007a87  mov     rcx, [rbx+120h]
0x140007a8e  lea     rax, TdxCloseConnectionEndpointTlRequestComplete
0x140007a95  mov     qword ptr [rsp+88h+var_38], rax
0x140007a9a  lea     rdx, [rsp+88h+var_38]
0x140007a9f  mov     rax, [rbx+108h]
0x140007aa6  mov     qword ptr [rsp+88h+var_38+8], rbx
0x140007aab  mov     rax, [rax]
0x140007aae  call    _guard_dispatch_icall
0x140007ab3  cmp     eax, 103h
0x140007ab8  jz      loc_14000772C
0x140007abe  mov     edx, eax
0x140007ac0  mov     rcx, rbx
0x140007ac3  call    TdxCloseConnectionEndpointTlRequestComplete
0x140007ac8  jmp     loc_14000772C
0x140007acd  mov     r8d, 10Dh
0x140007ad3  lea     rdx, aMinioNetioSess_6; "minio\\netio\\session\\tdi\\connection."...
0x140007ada  mov     rcx, r14
0x140007add  call    DbgTdxReferenceTransportAddress
0x140007ae2  jmp     loc_140007604
0x140007ae7  test    dword ptr [rcx+2Ch], 200h
0x140007aee  jz      loc_140007710
0x140007af4  mov     rcx, [rcx+18h]
0x140007af8  lea     rax, aTdxdecrementtl; "TdxDecrementTlEndpointReference"
0x140007aff  mov     [rsp+88h+var_50], 170h
0x140007b07  mov     r9, rbx
0x140007b0a  mov     [rsp+88h+var_58], rax
0x140007b0f  lea     rax, asc_14001AAE0; "--"
0x140007b16  mov     [rsp+88h+var_60], rax
0x140007b1b  mov     eax, [r12+190h]
0x140007b23  mov     dword ptr [rsp+88h+var_68], eax
0x140007b27  call    WPP_SF_qdssD
0x140007b2c  jmp     loc_140007710
0x140007b31  or      edx, 40h
0x140007b34  mov     [rbx], edx
0x140007b36  jmp     loc_1400078F6
0x140007b3b  mov     ecx, 3
0x140007b40  int     29h; Win8: RtlFailFast(ecx)
0x140007b42  test    dword ptr [rcx+2Ch], 200h
0x140007b49  jz      loc_140007830
0x140007b4f  mov     rcx, [rcx+18h]
  ... truncated ...
```
