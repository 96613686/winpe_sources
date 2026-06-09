# VhdmpiSrbPartReportPresent

- ea: `0x140014c30`
- end: `0x140015113`
- name: `VhdmpiSrbPartReportPresent`
- size: `1251`
- prototype: ``
- caller_count: `3`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140014bc0`
- `0x1400156b0`
- `0x14001c4a0`

## callees

- `0x14000d550`
- `0x140012d60`
- `0x140012fe0`
- `0x140014c30`
- `0x1400193d0`
- `0x140025e74`
- `0x140036284`
- `0x1400c8558`
- `0x1400e3bec`

## import_xrefs

- `ntoskrnl!IoAllocateMdl` at `0x140014dc0`
- `ntoskrnl!IoAllocateMdl` at `0x140014dc0`
- `ntoskrnl!IoBuildPartialMdl` at `0x140014de0`
- `ntoskrnl!IoBuildPartialMdl` at `0x140014de0`
- `ntoskrnl!IoInitializeIrpEx` at `0x140014ccc`
- `ntoskrnl!IoInitializeIrpEx` at `0x140014ccc`
- `ntoskrnl!IoReuseIrp` at `0x140014d03`
- `ntoskrnl!IoReuseIrp` at `0x140014d03`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140014c6b`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140014c6b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140014f93`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140014f93`
- `ntoskrnl!KeReleaseSpinLock` at `0x140014fc4`
- `ntoskrnl!KeReleaseSpinLock` at `0x140014fc4`

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
    if ( (unsigned int)dword_1400876D0 > 5 && (qword_1400876E0 & 2) != 0 && (qword_1400876E8 & 2) == qword_1400876E8 )
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
0x140014c30  mov     [rsp+arg_10], rbx
0x140014c35  mov     [rsp+arg_18], rbp
0x140014c3a  mov     [rsp+arg_8], edx
0x140014c3e  push    rsi
0x140014c3f  push    rdi
0x140014c40  push    r12
0x140014c42  push    r14
0x140014c44  push    r15
0x140014c46  sub     rsp, 40h
0x140014c4a  mov     rbp, [rcx]
0x140014c4d  mov     rsi, r9
0x140014c50  mov     r12d, r8d
0x140014c53  mov     r15d, edx
0x140014c56  mov     r14, rcx
0x140014c59  mov     eax, [rbp+40h]
0x140014c5c  test    al, 20h
0x140014c5e  jnz     loc_140014CEB
0x140014c64  lea     rcx, [r9+680h]; Lookaside
0x140014c6b  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140014c72  nop     dword ptr [rax+rax+00h]
0x140014c77  mov     rdi, rax
0x140014c7a  test    rax, rax
0x140014c7d  jz      short loc_140014CE1
0x140014c7f  movzx   r8d, word ptr [rsi+70Ah]
0x140014c87  lea     rbx, [rax+0A0h]
0x140014c8e  xorps   xmm0, xmm0
0x140014c91  lea     r9, [rsi+48h]
0x140014c95  movups  xmmword ptr [rdi+18h], xmm0
0x140014c99  xor     eax, eax
0x140014c9b  mov     rdx, 0FFFFFFFFFFFFFFFFh
0x140014ca2  movups  xmmword ptr [rdi+28h], xmm0
0x140014ca6  mov     rcx, rbx
0x140014ca9  movups  xmmword ptr [rdi+38h], xmm0
0x140014cad  movups  xmmword ptr [rdi+48h], xmm0
0x140014cb1  movups  xmmword ptr [rdi+58h], xmm0
0x140014cb5  mov     [rdi+68h], rax
0x140014cb9  mov     [rdi], r9
0x140014cbc  mov     [rdi+8], rsi
0x140014cc0  mov     [rdi+10h], rbx
0x140014cc4  movzx   r9d, byte ptr [r9+220h]
0x140014ccc  call    cs:__imp_IoInitializeIrpEx
0x140014cd3  nop     dword ptr [rax+rax+00h]
0x140014cd8  mov     [rbx+90h], rdi
0x140014cdf  jmp     short loc_140014D0F
0x140014ce1  mov     eax, 0C000009Ah
0x140014ce6  jmp     loc_140014D7E
0x140014ceb  mov     rdi, [r9+700h]
0x140014cf2  mov     edx, 103h; Iostatus
0x140014cf7  mov     byte ptr [r9+709h], 1
0x140014cff  mov     rcx, [rdi+10h]; Irp
0x140014d03  call    cs:__imp_IoReuseIrp
0x140014d0a  nop     dword ptr [rax+rax+00h]
0x140014d0f  mov     ecx, [rbp+3Ch]
0x140014d12  xor     ebx, ebx
0x140014d14  mov     [rsp+68h+arg_0], r13
0x140014d19  sub     ecx, 1
0x140014d1c  jz      short loc_140014D3C
0x140014d1e  sub     ecx, 1
0x140014d21  jz      short loc_140014D3C
0x140014d23  sub     ecx, 3
0x140014d26  jz      short loc_140014D32
0x140014d28  cmp     ecx, 1
0x140014d2b  jz      short loc_140014D3C
0x140014d2d  jmp     loc_140014DF4
0x140014d32  cmp     dword ptr [rbp+44h], 2
0x140014d36  jnz     loc_140014DF4
0x140014d3c  mov     rax, [r14]
0x140014d3f  mov     rcx, [r14+58h]
0x140014d43  mov     rdx, [rax+20h]
0x140014d47  mov     rbx, [rax+48h]
0x140014d4b  cmp     rcx, rdx
0x140014d4e  jnz     short loc_140014D98
0x140014d50  test    r15d, r15d
0x140014d53  jnz     short loc_140014D98
0x140014d55  cmp     r12d, [rax+34h]
0x140014d59  jnz     short loc_140014D98
0x140014d5b  test    rbx, rbx
0x140014d5e  jnz     loc_140014DF4
0x140014d64  test    rdi, rdi
0x140014d67  jz      short loc_140014D74
0x140014d69  mov     rdx, rdi; struct VHD_SRB_PART_IRP_CONTEXT *
0x140014d6c  mov     rcx, rsi; struct _VHD_BACKING_STORE_HEADER *
0x140014d6f  call    ?VhdmpiFreeMainIoIrpContext@@YAXPEAU_VHD_BACKING_STORE_HEADER@@PEAUVHD_SRB_PART_IRP_CONTEXT@@@Z; VhdmpiFreeMainIoIrpContext(_VHD_BACKING_STORE_HEADER *,VHD_SRB_PART_IRP_CONTEXT *)
0x140014d74  mov     eax, 0C000009Ah
0x140014d79  mov     r13, [rsp+68h+arg_0]
0x140014d7e  lea     r11, [rsp+68h+var_28]
0x140014d83  mov     rbx, [r11+40h]
0x140014d87  mov     rbp, [r11+48h]
0x140014d8b  mov     rsp, r11
0x140014d8e  pop     r15
0x140014d90  pop     r14
0x140014d92  pop     r12
0x140014d94  pop     rdi
0x140014d95  pop     rsi
0x140014d96  retn
0x140014d98  mov     eax, [rbx+2Ch]
0x140014d9b  sub     rcx, rdx
0x140014d9e  mov     r13d, ecx
0x140014da1  xor     r9d, r9d; ChargeQuota
0x140014da4  add     r13, rax
0x140014da7  mov     [rsp+68h+Irp], 0; Irp
0x140014db0  add     r13, [rbx+20h]
0x140014db4  xor     r8d, r8d; SecondaryBuffer
0x140014db7  add     r13, r15
0x140014dba  mov     edx, r12d; Length
0x140014dbd  mov     rcx, r13; VirtualAddress
0x140014dc0  call    cs:__imp_IoAllocateMdl
0x140014dc7  nop     dword ptr [rax+rax+00h]
0x140014dcc  mov     r15, rax
0x140014dcf  test    rax, rax
0x140014dd2  jz      short loc_140014D64
0x140014dd4  mov     r9d, r12d; Length
0x140014dd7  mov     r8, r13; VirtualAddress
0x140014dda  mov     rdx, rax; TargetMdl
0x140014ddd  mov     rcx, rbx; SourceMdl
0x140014de0  call    cs:__imp_IoBuildPartialMdl
0x140014de7  nop     dword ptr [rax+rax+00h]
0x140014dec  mov     rbx, r15
0x140014def  mov     r15d, [rsp+68h+arg_8]
0x140014df4  mov     r9d, [r14+58h]
0x140014df8  sub     r9d, [rbp+20h]
0x140014dfc  mov     rax, [rsp+68h+arg_28]
0x140014e04  add     r9d, r15d
0x140014e07  mov     r10, [rsp+68h+arg_20]
0x140014e0f  mov     r8, [rdi+10h]
0x140014e13  mov     [rdi+88h], rax
0x140014e1a  mov     rax, [rsp+68h+arg_30]
0x140014e22  mov     [rdi+90h], rax
0x140014e29  mov     [rdi+58h], r9d
0x140014e2d  mov     [rdi+70h], r14
0x140014e31  mov     [rdi+48h], rbp
0x140014e35  mov     [rdi+50h], r10
0x140014e39  mov     [rdi+5Ch], r12d
0x140014e3d  mov     ecx, [rbp+3Ch]
0x140014e40  cmp     ecx, 7
0x140014e43  ja      short loc_140014E8D
0x140014e45  mov     eax, 92h
0x140014e4a  bt      eax, ecx
0x140014e4d  jnb     short loc_140014E8D
0x140014e4f  or      dword ptr [r8+10h], 200h
0x140014e57  mov     rax, [r8+0B8h]
0x140014e5e  mov     byte ptr [rax-48h], 4
0x140014e62  mov     [rax-30h], r10
0x140014e66  mov     [rax-40h], r12d
0x140014e6a  mov     qword ptr [rax-18h], 3
0x140014e72  mov     eax, [rbp+40h]
0x140014e75  test    al, 2
0x140014e77  jz      loc_140014F22
0x140014e7d  mov     rax, [r8+0B8h]
0x140014e84  or      byte ptr [rax-46h], 4
0x140014e88  jmp     loc_140014F22
0x140014e8d  cmp     ecx, 2
0x140014e90  jz      short loc_140014EB7
0x140014e92  lea     eax, [rcx-5]
0x140014e95  cmp     eax, 1
0x140014e98  jbe     short loc_140014EB7
0x140014e9a  mov     rax, [r8+0B8h]
0x140014ea1  or      dword ptr [r8+10h], 200h
0x140014ea9  mov     byte ptr [rax-48h], 9
0x140014ead  mov     qword ptr [rax-18h], 7
0x140014eb5  jmp     short loc_140014F22
0x140014eb7  mov     rdx, [rbp+80h]
0x140014ebe  test    rdx, rdx
0x140014ec1  jz      short loc_140014EFC
0x140014ec3  mov     eax, r9d
0x140014ec6  shr     rax, 9
0x140014eca  lea     rdx, [rdx+rax*8]
0x140014ece  test    rdx, rdx
0x140014ed1  jz      short loc_140014EFC
0x140014ed3  cmp     ecx, 2
0x140014ed6  jnz     short loc_140014EE0
0x140014ed8  mov     dword ptr [rdx], 5
0x140014ede  jmp     short loc_140014EF8
0x140014ee0  cmp     ecx, 5
0x140014ee3  jnz     short loc_140014EED
0x140014ee5  mov     dword ptr [rdx], 6
0x140014eeb  jmp     short loc_140014EF8
0x140014eed  cmp     ecx, 6
0x140014ef0  jnz     short loc_140014EF8
0x140014ef2  mov     dword ptr [rdx], 7
0x140014ef8  mov     [rdx+4], r12d
0x140014efc  mov     rax, [rdi+10h]
0x140014f00  mov     rcx, [rax+0B8h]
0x140014f07  or      dword ptr [rax+10h], 100h
0x140014f0e  mov     byte ptr [rcx-48h], 3
0x140014f12  mov     [rcx-30h], r10
0x140014f16  mov     [rcx-40h], r12d
0x140014f1a  mov     qword ptr [rcx-18h], 1
0x140014f22  test    rbx, rbx
0x140014f25  jz      short loc_140014F36
0x140014f27  mov     [r8+8], rbx
0x140014f2b  mov     eax, [rbx+2Ch]
0x140014f2e  add     rax, [rbx+20h]
0x140014f32  mov     [r8+70h], rax
0x140014f36  mov     rax, [r14]
0x140014f39  test    dword ptr [rax+40h], 100h
0x140014f40  jz      short loc_140014F4F
0x140014f42  mov     byte ptr [r14+6Ch], 1
0x140014f47  mov     [r14+64h], r15d
0x140014f4b  mov     [r14+68h], r12d
0x140014f4f  cmp     byte ptr [r14+6Fh], 0
0x140014f54  lea     rbx, [rdi+78h]
0x140014f58  lea     rsi, [r14+48h]
0x140014f5c  jnz     short loc_140014F8F
0x140014f5e  mov     rax, [rsi+8]
0x140014f62  cmp     [rax], rsi
0x140014f65  jz      short loc_140014F6E
0x140014f67  mov     ecx, 3
0x140014f6c  int     29h; Win8: RtlFailFast(ecx)
0x140014f6e  cmp     [rsp+68h+arg_38], 0
0x140014f76  mov     [rbx+8], rax
0x140014f7a  mov     [rbx], rsi
0x140014f7d  mov     [rax], rbx
0x140014f80  setz    al
0x140014f83  inc     al
0x140014f85  mov     [rsi+8], rbx
0x140014f89  mov     [r14+6Fh], al
0x140014f8d  jmp     short loc_140014FD0
0x140014f8f  lea     rcx, [r14+40h]; SpinLock
0x140014f93  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140014f9a  nop     dword ptr [rax+rax+00h]
0x140014f9f  mov     rcx, [rsi+8]
0x140014fa3  cmp     [rcx], rsi
0x140014fa6  jz      short loc_140014FAF
0x140014fa8  mov     ecx, 3
0x140014fad  int     29h; Win8: RtlFailFast(ecx)
0x140014faf  mov     [rbx+8], rcx
0x140014fb3  movzx   edx, al; NewIrql
0x140014fb6  mov     [rbx], rsi
0x140014fb9  mov     [rcx], rbx
0x140014fbc  lea     rcx, [r14+40h]; SpinLock
0x140014fc0  mov     [rsi+8], rbx
0x140014fc4  call    cs:__imp_KeReleaseSpinLock
0x140014fcb  nop     dword ptr [rax+rax+00h]
0x140014fd0  mov     rbx, [rdi+10h]
0x140014fd4  lea     r8, ?VhdmpiSrbPartIoCompletionRoutine@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAX@Z; int (*)(struct _DEVICE_OBJECT *, struct _IRP *, void *)
0x140014fdb  mov     rcx, rbx; struct _IRP *
0x140014fde  mov     r9, rdi; void *
0x140014fe1  mov     rdx, rbp; struct _VHD_SRB_EXTENSION *
0x140014fe4  call    ?VhdmpiPrepareIrp@@YAXPEAU_IRP@@PEAU_VHD_SRB_EXTENSION@@P6AJPEAU_DEVICE_OBJECT@@0PEAX@Z3@Z; VhdmpiPrepareIrp(_IRP *,_VHD_SRB_EXTENSION *,long (*)(_DEVICE_OBJECT *,_IRP *,void *),void *)
0x140014fe9  mov     rsi, [rdi+8]
0x140014fed  test    rsi, rsi
0x140014ff0  jnz     short loc_140015007
0x140014ff2  mov     rcx, [rdi]
0x140014ff5  mov     rdx, rbx
0x140014ff8  call    VhdmpiFileWrapperCallDriver
0x140014ffd  mov     eax, 103h
0x140015002  jmp     loc_140014D79
0x140015007  mov     ecx, [rbp+3Ch]
0x14001500a  lea     eax, [rcx-4]
0x14001500d  cmp     eax, 1
0x140015010  jbe     short loc_14001504E
0x140015012  lea     eax, [rcx-6]
0x140015015  cmp     eax, 1
0x140015018  ja      short loc_14001502C
0x14001501a  mov     rcx, rdi; struct _VHD_IRP_CONTEXT_HEADER *
0x14001501d  call    ?VhdmpiIssueMainProjectIo@@YAXPEAU_VHD_IRP_CONTEXT_HEADER@@@Z; VhdmpiIssueMainProjectIo(_VHD_IRP_CONTEXT_HEADER *)
0x140015022  mov     eax, 103h
0x140015027  jmp     loc_140014D79
0x14001502c  cmp     byte ptr [rdi+60h], 0
0x140015030  jz      short loc_140015062
0x140015032  mov     rcx, [rbx+0B8h]
0x140015039  mov     rax, [rcx-30h]
0x14001503d  mov     [rdi+50h], rax
0x140015041  mov     eax, [rcx-40h]
0x140015044  mov     [rdi+5Ch], eax
0x140015047  mov     dword ptr [rdi+58h], 0
0x14001504e  xor     edx, edx; struct _VHD_OFFLOAD_IO_CONTEXT *
0x140015050  mov     rcx, rdi; struct _VHD_IRP_CONTEXT_HEADER *
0x140015053  call    ?VhdmpiIssueMainOffloadIo@@YAXPEAU_VHD_IRP_CONTEXT_HEADER@@PEAU_VHD_OFFLOAD_IO_CONTEXT@@@Z; VhdmpiIssueMainOffloadIo(_VHD_IRP_CONTEXT_HEADER *,_VHD_OFFLOAD_IO_CONTEXT *)
0x140015058  mov     eax, 103h
0x14001505d  jmp     loc_140014D79
0x140015062  cmp     qword ptr [rsi+5C8h], 0
0x14001506a  mov     rbx, [rdi+10h]
0x14001506e  mov     rcx, [rbx+0B8h]
0x140015075  jz      short loc_140015093
0x140015077  movzx   eax, byte ptr [rcx-48h]
0x14001507b  sub     al, 3
0x14001507d  cmp     al, 1
0x14001507f  ja      short loc_140015093
0x140015081  mov     rcx, rdi; struct _VHD_IRP_CONTEXT_HEADER *
0x140015084  call    ?RmwiTriageIO@@YAJPEAU_VHD_IRP_CONTEXT_HEADER@@@Z; RmwiTriageIO(_VHD_IRP_CONTEXT_HEADER *)
0x140015089  mov     eax, 103h
0x14001508e  jmp     loc_140014D79
0x140015093  mov     eax, cs:dword_1400876D0
0x140015099  cmp     eax, 5
0x14001509c  jbe     short loc_1400150FE
0x14001509e  mov     rdx, cs:qword_1400876E8
0x1400150a5  mov     rax, cs:qword_1400876E0
0x1400150ac  test    al, 2
0x1400150ae  jz      short loc_1400150FE
0x1400150b0  mov     rax, rdx
0x1400150b3  and     eax, 2
0x1400150b6  cmp     rax, rdx
0x1400150b9  jnz     short loc_1400150FE
0x1400150bb  mov     eax, [rcx-40h]
0x1400150be  mov     edx, 24Bh; int
0x1400150c3  movzx   r9d, byte ptr [rcx-48h]
0x1400150c8  mov     r8d, 5; int
0x1400150ce  mov     [rsp+68h+var_30], eax
  ... truncated ...
```
