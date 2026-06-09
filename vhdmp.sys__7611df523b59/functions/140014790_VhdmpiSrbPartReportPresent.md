# VhdmpiSrbPartReportPresent

- ea: `0x140014790`
- end: `0x140014c73`
- name: `VhdmpiSrbPartReportPresent`
- size: `1251`
- prototype: ``
- caller_count: `3`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140014720`
- `0x140015210`
- `0x14001c080`

## callees

- `0x14000cf50`
- `0x140011a30`
- `0x140011cb0`
- `0x140014790`
- `0x140018f30`
- `0x140025a54`
- `0x140035e94`
- `0x1400c8568`
- `0x1400e3c5c`

## import_xrefs

- `ntoskrnl!IoAllocateMdl` at `0x140014920`
- `ntoskrnl!IoAllocateMdl` at `0x140014920`
- `ntoskrnl!IoBuildPartialMdl` at `0x140014940`
- `ntoskrnl!IoBuildPartialMdl` at `0x140014940`
- `ntoskrnl!IoInitializeIrpEx` at `0x14001482c`
- `ntoskrnl!IoInitializeIrpEx` at `0x14001482c`
- `ntoskrnl!IoReuseIrp` at `0x140014863`
- `ntoskrnl!IoReuseIrp` at `0x140014863`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400147cb`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400147cb`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140014af3`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140014af3`
- `ntoskrnl!KeReleaseSpinLock` at `0x140014b24`
- `ntoskrnl!KeReleaseSpinLock` at `0x140014b24`

## pseudocode

```c
__int64 __fastcall VhdmpiSrbPartReportPresent(
        _QWORD *a1,
        unsigned int a2,
        ULONG a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        char a8)
{
  __int64 v8; // rbp
  struct _MDL *v11; // r15
  char *v13; // rax
  char *v14; // rdi
  __int64 v15; // r8
  char *v16; // rbx
  struct _MDL *v18; // rbx
  __int64 v19; // rcx
  __int64 v20; // rdx
  char *v21; // r13
  struct _MDL *Mdl; // rax
  unsigned int v23; // r9d
  __int64 v24; // r8
  unsigned int v25; // ecx
  int v26; // eax
  __int64 v27; // rax
  __int64 v28; // rax
  __int64 v29; // rdx
  _DWORD *v30; // rdx
  __int64 v31; // rax
  __int64 v32; // rcx
  _QWORD *v33; // rbx
  _QWORD *v34; // rsi
  _QWORD *v35; // rax
  KIRQL v36; // al
  _QWORD *v37; // rcx
  IRP *v38; // rbx
  __int64 v39; // r8
  __int64 v40; // r9
  __int64 v41; // rsi
  int v42; // ecx
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rcx
  struct _IRP *v44; // rbx
  struct _IO_STACK_LOCATION *v45; // rcx

  v8 = *a1;
  v11 = (struct _MDL *)a2;
  if ( (*(_DWORD *)(*a1 + 64LL) & 0x20) != 0 )
  {
    v14 = *(char **)(a4 + 1792);
    *(_BYTE *)(a4 + 1801) = 1;
    IoReuseIrp(*((PIRP *)v14 + 2), 259);
  }
  else
  {
    v13 = (char *)ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(a4 + 1664));
    v14 = v13;
    if ( !v13 )
      return 3221225626LL;
    v15 = *(unsigned __int16 *)(a4 + 1802);
    v16 = v13 + 160;
    *(_OWORD *)(v13 + 24) = 0;
    *(_OWORD *)(v13 + 40) = 0;
    *(_OWORD *)(v13 + 56) = 0;
    *(_OWORD *)(v13 + 72) = 0;
    *(_OWORD *)(v13 + 88) = 0;
    *((_QWORD *)v13 + 13) = 0;
    *(_QWORD *)v13 = a4 + 72;
    *((_QWORD *)v13 + 1) = a4;
    *((_QWORD *)v13 + 2) = v13 + 160;
    IoInitializeIrpEx(v13 + 160, -1, v15, *(unsigned __int8 *)(a4 + 616));
    *((_QWORD *)v16 + 18) = v14;
  }
  v18 = 0;
  switch ( *(_DWORD *)(v8 + 60) )
  {
    case 1:
    case 2:
      goto LABEL_12;
    case 5:
      if ( *(_DWORD *)(v8 + 68) != 2 )
        break;
LABEL_12:
      v19 = a1[11];
      v20 = *(_QWORD *)(*a1 + 32LL);
      v18 = *(struct _MDL **)(*a1 + 72LL);
      if ( v19 == v20 && !(_DWORD)v11 && a3 == *(_DWORD *)(*a1 + 52LL) )
      {
        if ( v18 )
          break;
      }
      else
      {
        v21 = (char *)v11
            + (unsigned __int64)v18->StartVa
            + v18->ByteOffset
            + (unsigned __int64)(unsigned int)(v19 - v20);
        Mdl = IoAllocateMdl(v21, a3, 0, 0, 0);
        v11 = Mdl;
        if ( Mdl )
        {
          IoBuildPartialMdl(v18, Mdl, v21, a3);
          v18 = v11;
          LODWORD(v11) = a2;
          break;
        }
      }
      if ( v14 )
        VhdmpiFreeMainIoIrpContext((struct _VHD_BACKING_STORE_HEADER *)a4, (struct VHD_SRB_PART_IRP_CONTEXT *)v14);
      return 3221225626LL;
    case 6:
      goto LABEL_12;
  }
  v23 = (_DWORD)v11 + *((_DWORD *)a1 + 22) - *(_DWORD *)(v8 + 32);
  v24 = *((_QWORD *)v14 + 2);
  *((_QWORD *)v14 + 17) = a6;
  *((_QWORD *)v14 + 18) = a7;
  *((_DWORD *)v14 + 22) = v23;
  *((_QWORD *)v14 + 14) = a1;
  *((_QWORD *)v14 + 9) = v8;
  *((_QWORD *)v14 + 10) = a5;
  *((_DWORD *)v14 + 23) = a3;
  v25 = *(_DWORD *)(v8 + 60);
  if ( v25 <= 7 && (v26 = 146, _bittest(&v26, v25)) )
  {
    *(_DWORD *)(v24 + 16) |= 0x200u;
    v27 = *(_QWORD *)(v24 + 184);
    *(_BYTE *)(v27 - 72) = 4;
    *(_QWORD *)(v27 - 48) = a5;
    *(_DWORD *)(v27 - 64) = a3;
    *(_QWORD *)(v27 - 24) = 3;
    if ( (*(_DWORD *)(v8 + 64) & 2) != 0 )
      *(_BYTE *)(*(_QWORD *)(v24 + 184) - 70LL) |= 4u;
  }
  else if ( v25 == 2 || v25 - 5 <= 1 )
  {
    v29 = *(_QWORD *)(v8 + 128);
    if ( v29 )
    {
      v30 = (_DWORD *)(v29 + 8 * ((unsigned __int64)v23 >> 9));
      if ( v30 )
      {
        switch ( v25 )
        {
          case 2u:
            *v30 = 5;
            break;
          case 5u:
            *v30 = 6;
            break;
          case 6u:
            *v30 = 7;
            break;
        }
        v30[1] = a3;
      }
    }
    v31 = *((_QWORD *)v14 + 2);
    v32 = *(_QWORD *)(v31 + 184);
    *(_DWORD *)(v31 + 16) |= 0x100u;
    *(_BYTE *)(v32 - 72) = 3;
    *(_QWORD *)(v32 - 48) = a5;
    *(_DWORD *)(v32 - 64) = a3;
    *(_QWORD *)(v32 - 24) = 1;
  }
  else
  {
    v28 = *(_QWORD *)(v24 + 184);
    *(_DWORD *)(v24 + 16) |= 0x200u;
    *(_BYTE *)(v28 - 72) = 9;
    *(_QWORD *)(v28 - 24) = 7;
  }
  if ( v18 )
  {
    *(_QWORD *)(v24 + 8) = v18;
    *(_QWORD *)(v24 + 112) = (char *)v18->StartVa + v18->ByteOffset;
  }
  if ( (*(_DWORD *)(*a1 + 64LL) & 0x100) != 0 )
  {
    *((_BYTE *)a1 + 108) = 1;
    *((_DWORD *)a1 + 25) = (_DWORD)v11;
    *((_DWORD *)a1 + 26) = a3;
  }
  v33 = v14 + 120;
  v34 = a1 + 9;
  if ( *((_BYTE *)a1 + 111) )
  {
    v36 = KeAcquireSpinLockRaiseToDpc(a1 + 8);
    v37 = (_QWORD *)a1[10];
    if ( (_QWORD *)*v37 != v34 )
      __fastfail(3u);
    *((_QWORD *)v14 + 16) = v37;
    *v33 = v34;
    *v37 = v33;
    a1[10] = v33;
    KeReleaseSpinLock(a1 + 8, v36);
  }
  else
  {
    v35 = (_QWORD *)a1[10];
    if ( (_QWORD *)*v35 != v34 )
      __fastfail(3u);
    *((_QWORD *)v14 + 16) = v35;
    *v33 = v34;
    *v35 = v33;
    a1[10] = v33;
    *((_BYTE *)a1 + 111) = (a8 == 0) + 1;
  }
  v38 = (IRP *)*((_QWORD *)v14 + 2);
  VhdmpiPrepareIrp(v38, (struct _VHD_SRB_EXTENSION *)v8, (unsigned __int64)VhdmpiSrbPartIoCompletionRoutine, v14);
  v41 = *((_QWORD *)v14 + 1);
  if ( !v41 )
  {
    VhdmpiFileWrapperCallDriver(*(_QWORD *)v14, v38);
    return 259;
  }
  v42 = *(_DWORD *)(v8 + 60);
  if ( (unsigned int)(v42 - 4) <= 1 )
    goto LABEL_57;
  if ( (unsigned int)(v42 - 6) <= 1 )
  {
    VhdmpiIssueMainProjectIo((struct _VHD_IRP_CONTEXT_HEADER *)v14);
    return 259;
  }
  if ( v14[96] )
  {
    CurrentStackLocation = v38->Tail.Overlay.CurrentStackLocation;
    *((_QWORD *)v14 + 10) = CurrentStackLocation[-1].Parameters.Read.ByteOffset.QuadPart;
    *((_DWORD *)v14 + 23) = CurrentStackLocation[-1].Parameters.Read.Length;
    *((_DWORD *)v14 + 22) = 0;
LABEL_57:
    VhdmpiIssueMainOffloadIo((struct _VHD_IRP_CONTEXT_HEADER *)v14, 0, v39, v40);
    return 259;
  }
  v44 = (struct _IRP *)*((_QWORD *)v14 + 2);
  v45 = v44->Tail.Overlay.CurrentStackLocation;
  if ( *(_QWORD *)(v41 + 1480) && (unsigned __int8)(v45[-1].MajorFunction - 3) <= 1u )
  {
    RmwiTriageIO((struct _VHD_IRP_CONTEXT_HEADER *)v14);
    return 259;
  }
  else
  {
    if ( (unsigned int)dword_140087708 > 5 && (qword_140087718 & 2) != 0 && (qword_140087720 & 2) == qword_140087720 )
      TraceEvents(
        "RmwIoCallDriver",
        0x24Bu,
        5u,
        2u,
        "RmwIoCallDriver() IRP Major: %lu Offset: %llu Length: %lu",
        v45[-1].MajorFunction,
        v45[-1].Parameters.Read.ByteOffset.QuadPart,
        v45[-1].Parameters.Read.Length);
    VhdmpiCallDriverWithoutBlocking((struct _VHD_BACKING_STORE_HEADER *)v41, v44);
    return 259;
  }
}

```

## disassembly

```asm
0x140014790  mov     [rsp+arg_10], rbx
0x140014795  mov     [rsp+arg_18], rbp
0x14001479a  mov     [rsp+arg_8], edx
0x14001479e  push    rsi
0x14001479f  push    rdi
0x1400147a0  push    r12
0x1400147a2  push    r14
0x1400147a4  push    r15
0x1400147a6  sub     rsp, 40h
0x1400147aa  mov     rbp, [rcx]
0x1400147ad  mov     rsi, r9
0x1400147b0  mov     r12d, r8d
0x1400147b3  mov     r15d, edx
0x1400147b6  mov     r14, rcx
0x1400147b9  mov     eax, [rbp+40h]
0x1400147bc  test    al, 20h
0x1400147be  jnz     loc_14001484B
0x1400147c4  lea     rcx, [r9+680h]; Lookaside
0x1400147cb  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x1400147d2  nop     dword ptr [rax+rax+00h]
0x1400147d7  mov     rdi, rax
0x1400147da  test    rax, rax
0x1400147dd  jz      short loc_140014841
0x1400147df  movzx   r8d, word ptr [rsi+70Ah]
0x1400147e7  lea     rbx, [rax+0A0h]
0x1400147ee  xorps   xmm0, xmm0
0x1400147f1  lea     r9, [rsi+48h]
0x1400147f5  movups  xmmword ptr [rdi+18h], xmm0
0x1400147f9  xor     eax, eax
0x1400147fb  mov     rdx, 0FFFFFFFFFFFFFFFFh
0x140014802  movups  xmmword ptr [rdi+28h], xmm0
0x140014806  mov     rcx, rbx
0x140014809  movups  xmmword ptr [rdi+38h], xmm0
0x14001480d  movups  xmmword ptr [rdi+48h], xmm0
0x140014811  movups  xmmword ptr [rdi+58h], xmm0
0x140014815  mov     [rdi+68h], rax
0x140014819  mov     [rdi], r9
0x14001481c  mov     [rdi+8], rsi
0x140014820  mov     [rdi+10h], rbx
0x140014824  movzx   r9d, byte ptr [r9+220h]
0x14001482c  call    cs:__imp_IoInitializeIrpEx
0x140014833  nop     dword ptr [rax+rax+00h]
0x140014838  mov     [rbx+90h], rdi
0x14001483f  jmp     short loc_14001486F
0x140014841  mov     eax, 0C000009Ah
0x140014846  jmp     loc_1400148DE
0x14001484b  mov     rdi, [r9+700h]
0x140014852  mov     edx, 103h; Iostatus
0x140014857  mov     byte ptr [r9+709h], 1
0x14001485f  mov     rcx, [rdi+10h]; Irp
0x140014863  call    cs:__imp_IoReuseIrp
0x14001486a  nop     dword ptr [rax+rax+00h]
0x14001486f  mov     ecx, [rbp+3Ch]
0x140014872  xor     ebx, ebx
0x140014874  mov     [rsp+68h+arg_0], r13
0x140014879  sub     ecx, 1
0x14001487c  jz      short loc_14001489C
0x14001487e  sub     ecx, 1
0x140014881  jz      short loc_14001489C
0x140014883  sub     ecx, 3
0x140014886  jz      short loc_140014892
0x140014888  cmp     ecx, 1
0x14001488b  jz      short loc_14001489C
0x14001488d  jmp     loc_140014954
0x140014892  cmp     dword ptr [rbp+44h], 2
0x140014896  jnz     loc_140014954
0x14001489c  mov     rax, [r14]
0x14001489f  mov     rcx, [r14+58h]
0x1400148a3  mov     rdx, [rax+20h]
0x1400148a7  mov     rbx, [rax+48h]
0x1400148ab  cmp     rcx, rdx
0x1400148ae  jnz     short loc_1400148F8
0x1400148b0  test    r15d, r15d
0x1400148b3  jnz     short loc_1400148F8
0x1400148b5  cmp     r12d, [rax+34h]
0x1400148b9  jnz     short loc_1400148F8
0x1400148bb  test    rbx, rbx
0x1400148be  jnz     loc_140014954
0x1400148c4  test    rdi, rdi
0x1400148c7  jz      short loc_1400148D4
0x1400148c9  mov     rdx, rdi; struct VHD_SRB_PART_IRP_CONTEXT *
0x1400148cc  mov     rcx, rsi; struct _VHD_BACKING_STORE_HEADER *
0x1400148cf  call    ?VhdmpiFreeMainIoIrpContext@@YAXPEAU_VHD_BACKING_STORE_HEADER@@PEAUVHD_SRB_PART_IRP_CONTEXT@@@Z; VhdmpiFreeMainIoIrpContext(_VHD_BACKING_STORE_HEADER *,VHD_SRB_PART_IRP_CONTEXT *)
0x1400148d4  mov     eax, 0C000009Ah
0x1400148d9  mov     r13, [rsp+68h+arg_0]
0x1400148de  lea     r11, [rsp+68h+var_28]
0x1400148e3  mov     rbx, [r11+40h]
0x1400148e7  mov     rbp, [r11+48h]
0x1400148eb  mov     rsp, r11
0x1400148ee  pop     r15
0x1400148f0  pop     r14
0x1400148f2  pop     r12
0x1400148f4  pop     rdi
0x1400148f5  pop     rsi
0x1400148f6  retn
0x1400148f8  mov     eax, [rbx+2Ch]
0x1400148fb  sub     rcx, rdx
0x1400148fe  mov     r13d, ecx
0x140014901  xor     r9d, r9d; ChargeQuota
0x140014904  add     r13, rax
0x140014907  mov     [rsp+68h+Irp], 0; Irp
0x140014910  add     r13, [rbx+20h]
0x140014914  xor     r8d, r8d; SecondaryBuffer
0x140014917  add     r13, r15
0x14001491a  mov     edx, r12d; Length
0x14001491d  mov     rcx, r13; VirtualAddress
0x140014920  call    cs:__imp_IoAllocateMdl
0x140014927  nop     dword ptr [rax+rax+00h]
0x14001492c  mov     r15, rax
0x14001492f  test    rax, rax
0x140014932  jz      short loc_1400148C4
0x140014934  mov     r9d, r12d; Length
0x140014937  mov     r8, r13; VirtualAddress
0x14001493a  mov     rdx, rax; TargetMdl
0x14001493d  mov     rcx, rbx; SourceMdl
0x140014940  call    cs:__imp_IoBuildPartialMdl
0x140014947  nop     dword ptr [rax+rax+00h]
0x14001494c  mov     rbx, r15
0x14001494f  mov     r15d, [rsp+68h+arg_8]
0x140014954  mov     r9d, [r14+58h]
0x140014958  sub     r9d, [rbp+20h]
0x14001495c  mov     rax, [rsp+68h+arg_28]
0x140014964  add     r9d, r15d
0x140014967  mov     r10, [rsp+68h+arg_20]
0x14001496f  mov     r8, [rdi+10h]
0x140014973  mov     [rdi+88h], rax
0x14001497a  mov     rax, [rsp+68h+arg_30]
0x140014982  mov     [rdi+90h], rax
0x140014989  mov     [rdi+58h], r9d
0x14001498d  mov     [rdi+70h], r14
0x140014991  mov     [rdi+48h], rbp
0x140014995  mov     [rdi+50h], r10
0x140014999  mov     [rdi+5Ch], r12d
0x14001499d  mov     ecx, [rbp+3Ch]
0x1400149a0  cmp     ecx, 7
0x1400149a3  ja      short loc_1400149ED
0x1400149a5  mov     eax, 92h
0x1400149aa  bt      eax, ecx
0x1400149ad  jnb     short loc_1400149ED
0x1400149af  or      dword ptr [r8+10h], 200h
0x1400149b7  mov     rax, [r8+0B8h]
0x1400149be  mov     byte ptr [rax-48h], 4
0x1400149c2  mov     [rax-30h], r10
0x1400149c6  mov     [rax-40h], r12d
0x1400149ca  mov     qword ptr [rax-18h], 3
0x1400149d2  mov     eax, [rbp+40h]
0x1400149d5  test    al, 2
0x1400149d7  jz      loc_140014A82
0x1400149dd  mov     rax, [r8+0B8h]
0x1400149e4  or      byte ptr [rax-46h], 4
0x1400149e8  jmp     loc_140014A82
0x1400149ed  cmp     ecx, 2
0x1400149f0  jz      short loc_140014A17
0x1400149f2  lea     eax, [rcx-5]
0x1400149f5  cmp     eax, 1
0x1400149f8  jbe     short loc_140014A17
0x1400149fa  mov     rax, [r8+0B8h]
0x140014a01  or      dword ptr [r8+10h], 200h
0x140014a09  mov     byte ptr [rax-48h], 9
0x140014a0d  mov     qword ptr [rax-18h], 7
0x140014a15  jmp     short loc_140014A82
0x140014a17  mov     rdx, [rbp+80h]
0x140014a1e  test    rdx, rdx
0x140014a21  jz      short loc_140014A5C
0x140014a23  mov     eax, r9d
0x140014a26  shr     rax, 9
0x140014a2a  lea     rdx, [rdx+rax*8]
0x140014a2e  test    rdx, rdx
0x140014a31  jz      short loc_140014A5C
0x140014a33  cmp     ecx, 2
0x140014a36  jnz     short loc_140014A40
0x140014a38  mov     dword ptr [rdx], 5
0x140014a3e  jmp     short loc_140014A58
0x140014a40  cmp     ecx, 5
0x140014a43  jnz     short loc_140014A4D
0x140014a45  mov     dword ptr [rdx], 6
0x140014a4b  jmp     short loc_140014A58
0x140014a4d  cmp     ecx, 6
0x140014a50  jnz     short loc_140014A58
0x140014a52  mov     dword ptr [rdx], 7
0x140014a58  mov     [rdx+4], r12d
0x140014a5c  mov     rax, [rdi+10h]
0x140014a60  mov     rcx, [rax+0B8h]
0x140014a67  or      dword ptr [rax+10h], 100h
0x140014a6e  mov     byte ptr [rcx-48h], 3
0x140014a72  mov     [rcx-30h], r10
0x140014a76  mov     [rcx-40h], r12d
0x140014a7a  mov     qword ptr [rcx-18h], 1
0x140014a82  test    rbx, rbx
0x140014a85  jz      short loc_140014A96
0x140014a87  mov     [r8+8], rbx
0x140014a8b  mov     eax, [rbx+2Ch]
0x140014a8e  add     rax, [rbx+20h]
0x140014a92  mov     [r8+70h], rax
0x140014a96  mov     rax, [r14]
0x140014a99  test    dword ptr [rax+40h], 100h
0x140014aa0  jz      short loc_140014AAF
0x140014aa2  mov     byte ptr [r14+6Ch], 1
0x140014aa7  mov     [r14+64h], r15d
0x140014aab  mov     [r14+68h], r12d
0x140014aaf  cmp     byte ptr [r14+6Fh], 0
0x140014ab4  lea     rbx, [rdi+78h]
0x140014ab8  lea     rsi, [r14+48h]
0x140014abc  jnz     short loc_140014AEF
0x140014abe  mov     rax, [rsi+8]
0x140014ac2  cmp     [rax], rsi
0x140014ac5  jz      short loc_140014ACE
0x140014ac7  mov     ecx, 3
0x140014acc  int     29h; Win8: RtlFailFast(ecx)
0x140014ace  cmp     [rsp+68h+arg_38], 0
0x140014ad6  mov     [rbx+8], rax
0x140014ada  mov     [rbx], rsi
0x140014add  mov     [rax], rbx
0x140014ae0  setz    al
0x140014ae3  inc     al
0x140014ae5  mov     [rsi+8], rbx
0x140014ae9  mov     [r14+6Fh], al
0x140014aed  jmp     short loc_140014B30
0x140014aef  lea     rcx, [r14+40h]; SpinLock
0x140014af3  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140014afa  nop     dword ptr [rax+rax+00h]
0x140014aff  mov     rcx, [rsi+8]
0x140014b03  cmp     [rcx], rsi
0x140014b06  jz      short loc_140014B0F
0x140014b08  mov     ecx, 3
0x140014b0d  int     29h; Win8: RtlFailFast(ecx)
0x140014b0f  mov     [rbx+8], rcx
0x140014b13  movzx   edx, al; NewIrql
0x140014b16  mov     [rbx], rsi
0x140014b19  mov     [rcx], rbx
0x140014b1c  lea     rcx, [r14+40h]; SpinLock
0x140014b20  mov     [rsi+8], rbx
0x140014b24  call    cs:__imp_KeReleaseSpinLock
0x140014b2b  nop     dword ptr [rax+rax+00h]
0x140014b30  mov     rbx, [rdi+10h]
0x140014b34  lea     r8, ?VhdmpiSrbPartIoCompletionRoutine@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAX@Z; int (*)(struct _DEVICE_OBJECT *, struct _IRP *, void *)
0x140014b3b  mov     rcx, rbx; struct _IRP *
0x140014b3e  mov     r9, rdi; void *
0x140014b41  mov     rdx, rbp; struct _VHD_SRB_EXTENSION *
0x140014b44  call    ?VhdmpiPrepareIrp@@YAXPEAU_IRP@@PEAU_VHD_SRB_EXTENSION@@P6AJPEAU_DEVICE_OBJECT@@0PEAX@Z3@Z; VhdmpiPrepareIrp(_IRP *,_VHD_SRB_EXTENSION *,long (*)(_DEVICE_OBJECT *,_IRP *,void *),void *)
0x140014b49  mov     rsi, [rdi+8]
0x140014b4d  test    rsi, rsi
0x140014b50  jnz     short loc_140014B67
0x140014b52  mov     rcx, [rdi]
0x140014b55  mov     rdx, rbx
0x140014b58  call    VhdmpiFileWrapperCallDriver
0x140014b5d  mov     eax, 103h
0x140014b62  jmp     loc_1400148D9
0x140014b67  mov     ecx, [rbp+3Ch]
0x140014b6a  lea     eax, [rcx-4]
0x140014b6d  cmp     eax, 1
0x140014b70  jbe     short loc_140014BAE
0x140014b72  lea     eax, [rcx-6]
0x140014b75  cmp     eax, 1
0x140014b78  ja      short loc_140014B8C
0x140014b7a  mov     rcx, rdi; struct _VHD_IRP_CONTEXT_HEADER *
0x140014b7d  call    ?VhdmpiIssueMainProjectIo@@YAXPEAU_VHD_IRP_CONTEXT_HEADER@@@Z; VhdmpiIssueMainProjectIo(_VHD_IRP_CONTEXT_HEADER *)
0x140014b82  mov     eax, 103h
0x140014b87  jmp     loc_1400148D9
0x140014b8c  cmp     byte ptr [rdi+60h], 0
0x140014b90  jz      short loc_140014BC2
0x140014b92  mov     rcx, [rbx+0B8h]
0x140014b99  mov     rax, [rcx-30h]
0x140014b9d  mov     [rdi+50h], rax
0x140014ba1  mov     eax, [rcx-40h]
0x140014ba4  mov     [rdi+5Ch], eax
0x140014ba7  mov     dword ptr [rdi+58h], 0
0x140014bae  xor     edx, edx; struct _VHD_OFFLOAD_IO_CONTEXT *
0x140014bb0  mov     rcx, rdi; struct _VHD_IRP_CONTEXT_HEADER *
0x140014bb3  call    ?VhdmpiIssueMainOffloadIo@@YAXPEAU_VHD_IRP_CONTEXT_HEADER@@PEAU_VHD_OFFLOAD_IO_CONTEXT@@@Z; VhdmpiIssueMainOffloadIo(_VHD_IRP_CONTEXT_HEADER *,_VHD_OFFLOAD_IO_CONTEXT *)
0x140014bb8  mov     eax, 103h
0x140014bbd  jmp     loc_1400148D9
0x140014bc2  cmp     qword ptr [rsi+5C8h], 0
0x140014bca  mov     rbx, [rdi+10h]
0x140014bce  mov     rcx, [rbx+0B8h]
0x140014bd5  jz      short loc_140014BF3
0x140014bd7  movzx   eax, byte ptr [rcx-48h]
0x140014bdb  sub     al, 3
0x140014bdd  cmp     al, 1
0x140014bdf  ja      short loc_140014BF3
0x140014be1  mov     rcx, rdi; struct _VHD_IRP_CONTEXT_HEADER *
0x140014be4  call    ?RmwiTriageIO@@YAJPEAU_VHD_IRP_CONTEXT_HEADER@@@Z; RmwiTriageIO(_VHD_IRP_CONTEXT_HEADER *)
0x140014be9  mov     eax, 103h
0x140014bee  jmp     loc_1400148D9
0x140014bf3  mov     eax, cs:dword_140087708
0x140014bf9  cmp     eax, 5
0x140014bfc  jbe     short loc_140014C5E
0x140014bfe  mov     rdx, cs:qword_140087720
0x140014c05  mov     rax, cs:qword_140087718
0x140014c0c  test    al, 2
0x140014c0e  jz      short loc_140014C5E
0x140014c10  mov     rax, rdx
0x140014c13  and     eax, 2
0x140014c16  cmp     rax, rdx
0x140014c19  jnz     short loc_140014C5E
0x140014c1b  mov     eax, [rcx-40h]
0x140014c1e  mov     edx, 24Bh; int
0x140014c23  movzx   r9d, byte ptr [rcx-48h]
0x140014c28  mov     r8d, 5; int
0x140014c2e  mov     [rsp+68h+var_30], eax
  ... truncated ...
```
