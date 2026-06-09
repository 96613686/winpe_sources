# TdxSendDatagramTransportAddress

- ea: `0x140006608`
- end: `0x140006b33`
- name: `TdxSendDatagramTransportAddress`
- size: `1323`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x140005fe0`

## callees

- `0x140002850`
- `0x1400034c0`
- `0x1400054ec`
- `0x140006608`
- `0x140006b40`
- `0x14000b250`
- `0x14000ccfc`
- `0x14000f7c0`
- `0x14000fcf0`
- `0x140012ee4`
- `0x140012fd0`
- `0x140018590`
- `0x140018600`
- `0x140018900`

## import_xrefs

- `ntoskrnl!KeLowerIrql` at `0x140006680`
- `ntoskrnl!KeLowerIrql` at `0x140006680`
- `ntoskrnl!ExAllocatePool2` at `0x1400069c6`
- `ntoskrnl!ExAllocatePool2` at `0x1400069c6`
- `ntoskrnl!ExFreePoolWithTag` at `0x140006868`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000692a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140006a9e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140006868`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000692a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140006a9e`
- `ntoskrnl!IofCompleteRequest` at `0x1400066c1`
- `ntoskrnl!IofCompleteRequest` at `0x14000672e`
- `ntoskrnl!IofCompleteRequest` at `0x140006888`
- `ntoskrnl!IofCompleteRequest` at `0x14000694a`
- `ntoskrnl!IofCompleteRequest` at `0x140006b11`
- `ntoskrnl!IofCompleteRequest` at `0x1400066c1`
- `ntoskrnl!IofCompleteRequest` at `0x14000672e`
- `ntoskrnl!IofCompleteRequest` at `0x140006888`
- `ntoskrnl!IofCompleteRequest` at `0x14000694a`
- `ntoskrnl!IofCompleteRequest` at `0x140006b11`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000663d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000663d`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400066a1`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000670b`
- `ntoskrnl!KeReleaseSpinLock` at `0x140006782`
- `ntoskrnl!KeReleaseSpinLock` at `0x140006af0`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400066a1`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000670b`
- `ntoskrnl!KeReleaseSpinLock` at `0x140006782`
- `ntoskrnl!KeReleaseSpinLock` at `0x140006af0`

## pseudocode

```c
__int64 __fastcall TdxSendDatagramTransportAddress(__int64 a1, IRP *a2, __int64 a3)
{
  KIRQL v5; // al
  KIRQL v6; // r14
  int v7; // r13d
  __int64 v8; // rax
  __int64 v9; // rdi
  KSPIN_LOCK *v10; // r12
  __int64 v12; // rcx
  __int64 v13; // r8
  ADDRESS_FAMILY *v14; // r12
  ADDRESS_FAMILY *v15; // r14
  ADDRESS_FAMILY v16; // dx
  UCHAR v17; // al
  __int16 v18; // dx
  __int64 v19; // r8
  __int16 v20; // r10
  __int64 v21; // r9
  PDEVICE_OBJECT v22; // rcx
  __int64 v23; // rdx
  __int16 v24; // cx
  unsigned __int16 v25; // ax
  ADDRESS_FAMILY *Pool2; // rax
  __int64 v27; // rdx
  ADDRESS_FAMILY v28; // cx
  __int64 v29; // r8
  unsigned int v30; // ebx
  __int128 v31; // [rsp+30h] [rbp-39h] BYREF
  _QWORD v32[16]; // [rsp+40h] [rbp-29h] BYREF
  UCHAR v33; // [rsp+D8h] [rbp+6Fh]
  _QWORD *P; // [rsp+E8h] [rbp+7Fh]

  memset(v32, 0, 0x48u);
  v5 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 8));
  v6 = v5;
  if ( a2->Cancel || (*(_DWORD *)a1 & 4) == 0 )
  {
    KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 8), v5);
    goto LABEL_59;
  }
  v7 = *(_DWORD *)a1 & 0x40;
  v8 = TdxSelectTlRequestTransportAddress(a1, 0);
  v9 = v8;
  if ( !v8 )
  {
    KeLowerIrql(v6);
LABEL_59:
    a2->IoStatus.Information = 0;
    a2->IoStatus.Status = -1073741536;
    IofCompleteRequest(a2, 2);
    return 3221225760LL;
  }
  v10 = (KSPIN_LOCK *)(v8 + 8);
  if ( (*(_DWORD *)v8 & 2) == 0 )
  {
    KeReleaseSpinLock(v10, v6);
    a2->IoStatus.Status = -1073741811;
    a2->IoStatus.Information = 0;
    IofCompleteRequest(a2, 2);
    if ( v9 != a1 )
      DbgTdxDereferenceTransportAddress(v9, "minio\\netio\\session\\tdi\\address.c", 2696);
    return 3221225485LL;
  }
  P = (_QWORD *)TdxAllocateMessageTlRequest(*(_QWORD *)(v8 + 40), a2);
  if ( !P )
  {
    KeReleaseSpinLock(v10, v6);
    a2->IoStatus.Information = 0;
    a2->IoStatus.Status = -1073741670;
    IofCompleteRequest(a2, 2);
    if ( v9 != a1 )
      DbgTdxDereferenceTransportAddress(v9, "minio\\netio\\session\\tdi\\address.c", 2709);
    return 3221225626LL;
  }
  a2->Tail.Overlay.CurrentStackLocation->Control |= 1u;
  DbgTdxReferenceTransportAddress(a1, "minio\\netio\\session\\tdi\\address.c", 2715);
  KeReleaseSpinLock(v10, v6);
  P[2] = 0;
  P[3] = a2->MdlAddress;
  *((_DWORD *)P + 8) = 0;
  P[5] = *(unsigned int *)(a3 + 8);
  v32[5] = P + 2;
  v12 = *(_QWORD *)(a3 + 16);
  v32[0] = TdxMessageTlRequestComplete;
  v32[1] = P;
  LODWORD(v32[2]) = 0;
  if ( *(_QWORD *)(v12 + 8) == 8937731 )
  {
    v32[6] = *(_QWORD *)(v12 + 24);
    LODWORD(v32[7]) = *(_DWORD *)(v12 + 16);
  }
  v32[8] = 0;
  v13 = *(_QWORD *)(v12 + 40);
  v14 = (ADDRESS_FAMILY *)(v13 + 6);
  if ( v13 + 6 == ((v13 + 6) & 0xFFFFFFFFFFFFFFFCuLL) )
  {
    if ( !v7 )
    {
      if ( v13 != -6 )
      {
        v15 = (ADDRESS_FAMILY *)(v13 + 6);
        goto LABEL_45;
      }
      goto LABEL_53;
    }
  }
  else if ( !v7 )
  {
    v16 = *v14;
    goto LABEL_21;
  }
  v16 = 23;
LABEL_21:
  v17 = SOCKADDR_SIZE(v16);
  v21 = v17;
  v33 = v17;
  if ( v18 != v20 && v18 != 2 )
  {
    DbgTdxDereferenceTransport(*P, "minio\\netio\\session\\tdi\\address.c", 2786);
    ExFreePoolWithTag(P, 0);
    a2->IoStatus.Status = -1073741811;
    a2->IoStatus.Information = 0;
    IofCompleteRequest(a2, 2);
    if ( v9 != a1 )
      DbgTdxDereferenceTransportAddress(v9, "minio\\netio\\session\\tdi\\address.c", 2792);
    v22 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || BYTE1(WPP_GLOBAL_Control->Timer) < 5u
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) == 0 )
    {
      return 3221225485LL;
    }
    v23 = 31;
    goto LABEL_39;
  }
  v24 = *(_WORD *)(v19 + 6);
  v25 = *(_WORD *)(v19 + 4);
  if ( v24 == 2 && v25 < 0xEu || v24 == v20 && v25 < 0x1Au )
  {
    DbgTdxDereferenceTransport(*P, "minio\\netio\\session\\tdi\\address.c", 2805);
    ExFreePoolWithTag(P, 0);
    a2->IoStatus.Status = -1073741811;
    a2->IoStatus.Information = 0;
    IofCompleteRequest(a2, 2);
    if ( v9 != a1 )
      DbgTdxDereferenceTransportAddress(v9, "minio\\netio\\session\\tdi\\address.c", 2811);
    v22 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || BYTE1(WPP_GLOBAL_Control->Timer) < 5u
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) == 0 )
    {
      return 3221225485LL;
    }
    v23 = 32;
LABEL_39:
    WPP_SF_s(
      v22->AttachedDevice,
      v23,
      WPP_63c55c6b4ff2326ef703f60977e9aaef_Traceguids,
      "TdxSendDatagramTransportAddress");
    return 3221225485LL;
  }
  Pool2 = (ADDRESS_FAMILY *)ExAllocatePool2(64, v21, 544760916);
  v15 = Pool2;
  if ( Pool2 )
  {
    if ( v7 )
    {
      LOBYTE(v27) = 1;
      TaListToSockAddr(*(_QWORD *)(*(_QWORD *)(a3 + 16) + 40LL), v27, Pool2);
    }
    else
    {
      memmove(Pool2, v14, v33);
    }
LABEL_45:
    v32[4] = v15;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
    {
      v28 = *v15;
      v31 = (unsigned __int64)v15;
      WORD4(v31) = SOCKADDR_SIZE(v28);
      WPP_SF_qq_SOCKADDR_(*(_QWORD *)(v29 + 24), 33, v29, a1, (_DWORD)a2, (__int64)&v31);
    }
    v30 = (*(__int64 (__fastcall **)(_QWORD, _QWORD *))(*(_QWORD *)(v9 + 328) + 24LL))(*(_QWORD *)(v9 + 320), v32);
    if ( v15 != v14 )
      ExFreePoolWithTag(v15, 0);
    if ( v30 == 259 )
      goto LABEL_55;
    goto LABEL_54;
  }
LABEL_53:
  v30 = -1073741801;
LABEL_54:
  TdxMessageTlRequestComplete(P, v30, v32[8]);
LABEL_55:
  if ( v9 != a1 )
    DbgTdxDereferenceTransportAddress(v9, "minio\\netio\\session\\tdi\\address.c", 2859);
  return 259;
}

```

## disassembly

```asm
0x140006608  mov     [rsp-8+arg_10], r8
0x14000660d  push    rbp
0x14000660e  push    rbx
0x14000660f  push    rdi
0x140006610  push    r12
0x140006612  push    r13
0x140006614  push    r14
0x140006616  push    r15
0x140006618  lea     rbp, [rsp-27h]
0x14000661d  sub     rsp, 90h
0x140006624  mov     rbx, rdx
0x140006627  mov     r15, rcx
0x14000662a  xor     edx, edx; Val
0x14000662c  lea     rcx, [rbp+57h+var_80]; void *
0x140006630  lea     r8d, [rdx+48h]; Size
0x140006634  call    memset
0x140006639  lea     rcx, [r15+8]; SpinLock
0x14000663d  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140006644  nop     dword ptr [rax+rax+00h]
0x140006649  cmp     byte ptr [rbx+44h], 0
0x14000664d  mov     r14b, al
0x140006650  jnz     loc_140006AE9
0x140006656  mov     r13d, [r15]
0x140006659  test    r13b, 4
0x14000665d  jz      loc_140006AE9
0x140006663  and     r13d, 40h
0x140006667  mov     rcx, r15
0x14000666a  setnz   [rbp+57h+arg_0]
0x14000666e  xor     edx, edx
0x140006670  call    TdxSelectTlRequestTransportAddress
0x140006675  mov     rdi, rax
0x140006678  test    rax, rax
0x14000667b  jnz     short loc_140006691
0x14000667d  mov     cl, r14b; NewIrql
0x140006680  call    cs:__imp_KeLowerIrql
0x140006687  nop     dword ptr [rax+rax+00h]
0x14000668c  jmp     loc_140006AFC
0x140006691  lea     r12, [rax+8]
0x140006695  mov     eax, [rax]
0x140006697  test    al, 2
0x140006699  jnz     short loc_1400066F0
0x14000669b  mov     dl, r14b; NewIrql
0x14000669e  mov     rcx, r12; SpinLock
0x1400066a1  call    cs:__imp_KeReleaseSpinLock
0x1400066a8  nop     dword ptr [rax+rax+00h]
0x1400066ad  mov     dl, 2; PriorityBoost
0x1400066af  mov     dword ptr [rbx+30h], 0C000000Dh
0x1400066b6  mov     rcx, rbx; Irp
0x1400066b9  mov     qword ptr [rbx+38h], 0
0x1400066c1  call    cs:__imp_IofCompleteRequest
0x1400066c8  nop     dword ptr [rax+rax+00h]
0x1400066cd  cmp     rdi, r15
0x1400066d0  jz      loc_1400069AE
0x1400066d6  mov     r8d, 0A88h
0x1400066dc  lea     rdx, aMinioNetioSess_2; "minio\\netio\\session\\tdi\\address.c"
0x1400066e3  mov     rcx, rdi
0x1400066e6  call    DbgTdxDereferenceTransportAddress
0x1400066eb  jmp     loc_1400069AE
0x1400066f0  mov     rcx, [rdi+28h]
0x1400066f4  mov     rdx, rbx
0x1400066f7  call    TdxAllocateMessageTlRequest
0x1400066fc  mov     [rbp+57h+P], rax
0x140006700  test    rax, rax
0x140006703  jnz     short loc_14000675C
0x140006705  mov     dl, r14b; NewIrql
0x140006708  mov     rcx, r12; SpinLock
0x14000670b  call    cs:__imp_KeReleaseSpinLock
0x140006712  nop     dword ptr [rax+rax+00h]
0x140006717  mov     r14d, 0C000009Ah
0x14000671d  mov     qword ptr [rbx+38h], 0
0x140006725  mov     dl, 2; PriorityBoost
0x140006727  mov     [rbx+30h], r14d
0x14000672b  mov     rcx, rbx; Irp
0x14000672e  call    cs:__imp_IofCompleteRequest
0x140006735  nop     dword ptr [rax+rax+00h]
0x14000673a  cmp     rdi, r15
0x14000673d  jz      short loc_140006754
0x14000673f  mov     r8d, 0A95h
0x140006745  lea     rdx, aMinioNetioSess_2; "minio\\netio\\session\\tdi\\address.c"
0x14000674c  mov     rcx, rdi
0x14000674f  call    DbgTdxDereferenceTransportAddress
0x140006754  mov     eax, r14d
0x140006757  jmp     loc_140006B1F
0x14000675c  mov     rax, [rbx+0B8h]
0x140006763  lea     rdx, aMinioNetioSess_2; "minio\\netio\\session\\tdi\\address.c"
0x14000676a  mov     r8d, 0A9Bh
0x140006770  mov     rcx, r15
0x140006773  or      byte ptr [rax+3], 1
0x140006777  call    DbgTdxReferenceTransportAddress
0x14000677c  mov     dl, r14b; NewIrql
0x14000677f  mov     rcx, r12; SpinLock
0x140006782  call    cs:__imp_KeReleaseSpinLock
0x140006789  nop     dword ptr [rax+rax+00h]
0x14000678e  mov     r14, [rbp+57h+P]
0x140006792  xor     r9d, r9d
0x140006795  mov     rdx, [rbp+57h+arg_10]
0x140006799  lea     rcx, [r14+10h]
0x14000679d  mov     [rcx], r9
0x1400067a0  mov     rax, [rbx+8]
0x1400067a4  mov     [r14+18h], rax
0x1400067a8  mov     [r14+20h], r9d
0x1400067ac  mov     eax, [rdx+8]
0x1400067af  mov     [r14+28h], rax
0x1400067b3  lea     rax, TdxMessageTlRequestComplete
0x1400067ba  mov     [rbp+57h+var_58], rcx
0x1400067be  mov     rcx, [rdx+10h]
0x1400067c2  mov     [rbp+57h+var_80], rax
0x1400067c6  mov     [rbp+57h+var_78], r14
0x1400067ca  mov     [rbp+57h+var_70], r9d
0x1400067ce  cmp     qword ptr [rcx+8], 886103h
0x1400067d6  jnz     short loc_1400067E6
0x1400067d8  mov     rax, [rcx+18h]
0x1400067dc  mov     [rbp+57h+var_50], rax
0x1400067e0  mov     eax, [rcx+10h]
0x1400067e3  mov     [rbp+57h+var_48], eax
0x1400067e6  mov     [rbp+57h+var_40], r9
0x1400067ea  mov     r10d, 17h
0x1400067f0  mov     r8, [rcx+28h]
0x1400067f4  lea     r12, [r8+6]
0x1400067f8  mov     rax, r12
0x1400067fb  and     rax, 0FFFFFFFFFFFFFFFCh
0x1400067ff  cmp     r12, rax
0x140006802  jnz     short loc_14000681A
0x140006804  test    r13d, r13d
0x140006807  jnz     short loc_14000681F
0x140006809  test    r12, r12
0x14000680c  jz      loc_140006AB4
0x140006812  mov     r14, r12
0x140006815  jmp     loc_140006A0C
0x14000681a  test    r13d, r13d
0x14000681d  jz      short loc_140006825
0x14000681f  movzx   edx, r10w
0x140006823  jmp     short loc_14000682A
0x140006825  movzx   edx, word ptr [r12]
0x14000682a  movzx   ecx, dx; af
0x14000682d  call    SOCKADDR_SIZE
0x140006832  movzx   r9d, al
0x140006836  mov     [rbp+57h+arg_8], r9b
0x14000683a  cmp     dx, r10w
0x14000683e  jz      loc_1400068E6
0x140006844  cmp     dx, 2
0x140006848  jz      loc_1400068E6
0x14000684e  mov     rcx, [r14]
0x140006851  lea     rdx, aMinioNetioSess_2; "minio\\netio\\session\\tdi\\address.c"
0x140006858  mov     r8d, 0AE2h
0x14000685e  call    DbgTdxDereferenceTransport
0x140006863  xor     edx, edx; Tag
0x140006865  mov     rcx, r14; P
0x140006868  call    cs:__imp_ExFreePoolWithTag
0x14000686f  nop     dword ptr [rax+rax+00h]
0x140006874  mov     dl, 2; PriorityBoost
0x140006876  mov     dword ptr [rbx+30h], 0C000000Dh
0x14000687d  mov     rcx, rbx; Irp
0x140006880  mov     qword ptr [rbx+38h], 0
0x140006888  call    cs:__imp_IofCompleteRequest
0x14000688f  nop     dword ptr [rax+rax+00h]
0x140006894  cmp     rdi, r15
0x140006897  jz      short loc_1400068AE
0x140006899  mov     r8d, 0AE8h
0x14000689f  lea     rdx, aMinioNetioSess_2; "minio\\netio\\session\\tdi\\address.c"
0x1400068a6  mov     rcx, rdi
0x1400068a9  call    DbgTdxDereferenceTransportAddress
0x1400068ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1400068b5  lea     rax, WPP_GLOBAL_Control
0x1400068bc  cmp     rcx, rax
0x1400068bf  jz      loc_1400069AE
0x1400068c5  cmp     byte ptr [rcx+29h], 5
0x1400068c9  jb      loc_1400069AE
0x1400068cf  test    dword ptr [rcx+2Ch], 200h
0x1400068d6  jz      loc_1400069AE
0x1400068dc  mov     edx, 1Fh
0x1400068e1  jmp     loc_140006997
0x1400068e6  movzx   ecx, word ptr [r8+6]
0x1400068eb  movzx   eax, word ptr [r8+4]
0x1400068f0  cmp     cx, 2
0x1400068f4  jnz     short loc_1400068FC
0x1400068f6  cmp     ax, 0Eh
0x1400068fa  jb      short loc_140006910
0x1400068fc  cmp     cx, r10w
0x140006900  jnz     loc_1400069B8
0x140006906  cmp     ax, 1Ah
0x14000690a  jnb     loc_1400069B8
0x140006910  mov     rcx, [r14]
0x140006913  lea     rdx, aMinioNetioSess_2; "minio\\netio\\session\\tdi\\address.c"
0x14000691a  mov     r8d, 0AF5h
0x140006920  call    DbgTdxDereferenceTransport
0x140006925  xor     edx, edx; Tag
0x140006927  mov     rcx, r14; P
0x14000692a  call    cs:__imp_ExFreePoolWithTag
0x140006931  nop     dword ptr [rax+rax+00h]
0x140006936  mov     dl, 2; PriorityBoost
0x140006938  mov     dword ptr [rbx+30h], 0C000000Dh
0x14000693f  mov     rcx, rbx; Irp
0x140006942  mov     qword ptr [rbx+38h], 0
0x14000694a  call    cs:__imp_IofCompleteRequest
0x140006951  nop     dword ptr [rax+rax+00h]
0x140006956  cmp     rdi, r15
0x140006959  jz      short loc_140006970
0x14000695b  mov     r8d, 0AFBh
0x140006961  lea     rdx, aMinioNetioSess_2; "minio\\netio\\session\\tdi\\address.c"
0x140006968  mov     rcx, rdi
0x14000696b  call    DbgTdxDereferenceTransportAddress
0x140006970  mov     rcx, cs:WPP_GLOBAL_Control
0x140006977  lea     rax, WPP_GLOBAL_Control
0x14000697e  cmp     rcx, rax
0x140006981  jz      short loc_1400069AE
0x140006983  cmp     byte ptr [rcx+29h], 5
0x140006987  jb      short loc_1400069AE
0x140006989  test    dword ptr [rcx+2Ch], 200h
0x140006990  jz      short loc_1400069AE
0x140006992  mov     edx, 20h ; ' '
0x140006997  mov     rcx, [rcx+18h]
0x14000699b  lea     r9, aTdxsenddatagra; "TdxSendDatagramTransportAddress"
0x1400069a2  lea     r8, WPP_63c55c6b4ff2326ef703f60977e9aaef_Traceguids
0x1400069a9  call    WPP_SF_s
0x1400069ae  mov     eax, 0C000000Dh
0x1400069b3  jmp     loc_140006B1F
0x1400069b8  mov     rdx, r9
0x1400069bb  mov     ecx, 40h ; '@'
0x1400069c0  mov     r8d, 20786454h
0x1400069c6  call    cs:__imp_ExAllocatePool2
0x1400069cd  nop     dword ptr [rax+rax+00h]
0x1400069d2  mov     r14, rax
0x1400069d5  test    rax, rax
0x1400069d8  jz      loc_140006AB4
0x1400069de  test    r13d, r13d
0x1400069e1  jz      short loc_1400069FC
0x1400069e3  mov     rcx, [rbp+57h+arg_10]
0x1400069e7  mov     r8, rax
0x1400069ea  mov     dl, [rbp+57h+arg_0]
0x1400069ed  mov     rcx, [rcx+10h]
0x1400069f1  mov     rcx, [rcx+28h]
0x1400069f5  call    TaListToSockAddr
0x1400069fa  jmp     short loc_140006A0C
0x1400069fc  movzx   r8d, [rbp+57h+arg_8]; Size
0x140006a01  mov     rdx, r12; Src
0x140006a04  mov     rcx, rax; void *
0x140006a07  call    memmove
0x140006a0c  mov     [rbp+57h+var_60], r14
0x140006a10  mov     r8, cs:WPP_GLOBAL_Control
0x140006a17  lea     rax, WPP_GLOBAL_Control
0x140006a1e  cmp     r8, rax
0x140006a21  jz      short loc_140006A77
0x140006a23  cmp     byte ptr [r8+29h], 5
0x140006a28  jb      short loc_140006A77
0x140006a2a  test    dword ptr [r8+2Ch], 200h
0x140006a32  jz      short loc_140006A77
0x140006a34  movzx   ecx, word ptr [r14]; af
0x140006a38  xorps   xmm0, xmm0
0x140006a3b  movups  [rbp+57h+var_90], xmm0
0x140006a3f  mov     qword ptr [rbp+57h+var_90], r14
0x140006a43  call    SOCKADDR_SIZE
0x140006a48  movzx   edx, al
0x140006a4b  mov     r9, r15
0x140006a4e  mov     word ptr [rbp+57h+var_90+8], dx
0x140006a52  lea     rax, [rbp+57h+var_90]
0x140006a56  movaps  xmm0, [rbp+57h+var_90]
0x140006a5a  mov     edx, 21h ; '!'
0x140006a5f  movdqa  [rbp+57h+var_90], xmm0
0x140006a64  mov     rcx, [r8+18h]
0x140006a68  mov     [rsp+0C0h+var_98], rax
0x140006a6d  mov     [rsp+0C0h+var_A0], rbx
0x140006a72  call    WPP_SF_qq_SOCKADDR_
0x140006a77  mov     rax, [rdi+148h]
0x140006a7e  lea     rdx, [rbp+57h+var_80]
0x140006a82  mov     rcx, [rdi+140h]
0x140006a89  mov     rax, [rax+18h]
0x140006a8d  call    _guard_dispatch_icall
0x140006a92  mov     ebx, eax
0x140006a94  cmp     r14, r12
0x140006a97  jz      short loc_140006AAA
0x140006a99  xor     edx, edx; Tag
0x140006a9b  mov     rcx, r14; P
0x140006a9e  call    cs:__imp_ExFreePoolWithTag
0x140006aa5  nop     dword ptr [rax+rax+00h]
0x140006aaa  cmp     ebx, 103h
0x140006ab0  jnz     short loc_140006AB9
0x140006ab2  jmp     short loc_140006AC8
0x140006ab4  mov     ebx, 0C0000017h
0x140006ab9  mov     r8, [rbp+57h+var_40]
0x140006abd  mov     edx, ebx
0x140006abf  mov     rcx, [rbp+57h+P]
0x140006ac3  call    TdxMessageTlRequestComplete
0x140006ac8  cmp     rdi, r15
0x140006acb  jz      short loc_140006AE2
0x140006acd  mov     r8d, 0B2Bh
0x140006ad3  lea     rdx, aMinioNetioSess_2; "minio\\netio\\session\\tdi\\address.c"
0x140006ada  mov     rcx, rdi
0x140006add  call    DbgTdxDereferenceTransportAddress
0x140006ae2  mov     eax, 103h
0x140006ae7  jmp     short loc_140006B1F
0x140006ae9  mov     dl, r14b; NewIrql
0x140006aec  lea     rcx, [r15+8]; SpinLock
0x140006af0  call    cs:__imp_KeReleaseSpinLock
0x140006af7  nop     dword ptr [rax+rax+00h]
0x140006afc  mov     edi, 0C0000120h
0x140006b01  mov     qword ptr [rbx+38h], 0
0x140006b09  mov     dl, 2; PriorityBoost
0x140006b0b  mov     [rbx+30h], edi
0x140006b0e  mov     rcx, rbx; Irp
  ... truncated ...
```
