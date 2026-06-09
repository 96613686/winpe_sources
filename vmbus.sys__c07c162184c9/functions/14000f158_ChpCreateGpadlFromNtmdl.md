# ChpCreateGpadlFromNtmdl

- ea: `0x14000f158`
- end: `0x14000f5e9`
- name: `ChpCreateGpadlFromNtmdl`
- size: `1169`
- prototype: ``
- caller_count: `4`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14000ec8c`
- `0x14000ed90`
- `0x14002d794`
- `0x14002d888`

## callees

- `0x140001e30`
- `0x14000389c`
- `0x14000c8f4`
- `0x14000f070`
- `0x14000f158`
- `0x14000f5f0`
- `0x14000f7e4`
- `0x14000f9cc`
- `0x14000fdc0`
- `0x14000fe1c`
- `0x140010fa4`
- `0x140014a40`

## import_xrefs

- `ntoskrnl!ExReleaseFastMutex` at `0x14000f5c2`
- `ntoskrnl!ExReleaseFastMutex` at `0x14000f5c2`
- `ntoskrnl!ExAcquireFastMutex` at `0x14000f195`
- `ntoskrnl!ExAcquireFastMutex` at `0x14000f195`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14000f391`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14000f391`
- `ntoskrnl!IoAllocateMdl` at `0x14000f32d`
- `ntoskrnl!IoAllocateMdl` at `0x14000f32d`
- `ntoskrnl!ExAllocatePool2` at `0x14000f1c4`
- `ntoskrnl!ExAllocatePool2` at `0x14000f1c4`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14000f2bc`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14000f2bc`

## pseudocode

```c
__int64 __fastcall ChpCreateGpadlFromNtmdl(__int64 a1, __int64 a2, int a3, int a4, __int64 a5, __int64 a6, char a7)
{
  __int64 v7; // rbp
  int MdlHostVisible; // esi
  __int64 Pool2; // rax
  __int64 v12; // r14
  _DWORD *v13; // rbx
  _QWORD *v14; // rdi
  int v15; // r8d
  int v16; // ecx
  PVOID v17; // rax
  PDEVICE_OBJECT v18; // rcx
  __int64 v19; // rdx
  struct _MDL *Mdl; // rax
  __int64 *v21; // r15
  __int64 v22; // rcx
  __int64 v23; // r8
  PDEVICE_OBJECT v24; // rcx
  __int64 v25; // rdx
  __int64 SendMessageSized; // rax
  unsigned int v27; // eax

  v7 = *(_QWORD *)(a1 + 216);
  ExAcquireFastMutex((PFAST_MUTEX)(v7 + 432));
  if ( *(_BYTE *)(a1 + 248) )
  {
    MdlHostVisible = -1073741637;
    goto LABEL_64;
  }
  Pool2 = ExAllocatePool2(64, 120, 1937072726);
  v12 = Pool2;
  if ( Pool2 )
  {
    *(_QWORD *)(Pool2 + 8) = Pool2;
    v13 = (_DWORD *)(Pool2 + 68);
    *(_QWORD *)Pool2 = Pool2;
    v14 = (_QWORD *)(Pool2 + 24);
    *(_DWORD *)(Pool2 + 68) &= 0xFFFFFFF8;
    v15 = *(_DWORD *)(Pool2 + 68);
    if ( (a7 & 1) != 0 )
    {
      *v14 = a2;
      v16 = v15 | a7 & 1 | a7 & 6;
      LOBYTE(v15) = v15 | a7 & 7;
      *v13 = v16;
    }
    if ( !*(_BYTE *)(v7 + 322) )
      goto LABEL_40;
    if ( (a7 & 8) != 0 )
    {
      if ( *(_BYTE *)(a1 + 30) )
        goto LABEL_40;
    }
    else if ( *(_BYTE *)(a1 + 31) )
    {
      goto LABEL_40;
    }
    if ( (v15 & 1) != 0 )
    {
      v21 = (__int64 *)(Pool2 + 24);
    }
    else
    {
      if ( (*(_BYTE *)(a2 + 10) & 5) != 0 )
        v17 = *(PVOID *)(a2 + 24);
      else
        v17 = MmMapLockedPagesSpecifyCache((PMDL)a2, 0, MmCached, 0, 0, 0x40000010u);
      if ( !v17 )
      {
        MdlHostVisible = -1073741670;
        v18 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        {
          goto LABEL_62;
        }
        v19 = 12;
        goto LABEL_25;
      }
      Mdl = IoAllocateMdl(v17, *(_DWORD *)(a2 + 40), 0, 0, 0);
      v21 = (__int64 *)(v12 + 24);
      *(_QWORD *)(v12 + 24) = Mdl;
      if ( !Mdl )
      {
        MdlHostVisible = -1073741670;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_b9c76b9a14f83c2168b65499a7c535e1_Traceguids);
        }
        v14 = (_QWORD *)(v12 + 24);
        goto LABEL_62;
      }
      *(_BYTE *)(v12 + 72) = 1;
      MmBuildMdlForNonPagedPool(Mdl);
    }
    v22 = *v21;
    *(_BYTE *)(v12 + 74) = 0;
    MdlHostVisible = XPartVisMakeMdlHostVisible(v22, 1);
    if ( MdlHostVisible < 0 )
    {
      MicrosoftTelemetryAssertTriggeredNoArgsKM();
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        goto LABEL_62;
      }
      v19 = 14;
LABEL_25:
      WPP_SF_(v18->AttachedDevice, v19, WPP_b9c76b9a14f83c2168b65499a7c535e1_Traceguids);
      goto LABEL_62;
    }
    *(_BYTE *)(v12 + 73) = 1;
LABEL_40:
    MdlHostVisible = ChpCreateGpaRanges(a2, a3, a4, (int)v12 + 40, v12 + 48, v12 + 32);
    if ( MdlHostVisible >= 0 )
    {
      SendMessageSized = ChAllocateSendMessageSized(v7, 16, 11);
      *(_QWORD *)(v12 + 112) = SendMessageSized;
      if ( !SendMessageSized )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF__guid_iD(
            WPP_GLOBAL_Control->AttachedDevice,
            16,
            WPP_b9c76b9a14f83c2168b65499a7c535e1_Traceguids,
            v7 + 128,
            *(_QWORD *)(v7 + 120),
            *(_DWORD *)(a1 + 24));
        }
        MdlHostVisible = -1073741670;
        goto LABEL_62;
      }
      MdlHostVisible = ChpInsertGpadlLocked(v7, a1, v12);
      if ( MdlHostVisible >= 0 )
      {
        MdlHostVisible = ChpSendEstablishGpadlPacket(v12);
        if ( MdlHostVisible >= 0 )
        {
          MdlHostVisible = 0;
          *(_QWORD *)(v12 + 80) = a5;
          *(_QWORD *)(v12 + 88) = a6;
          *(_DWORD *)(v12 + 16) = 0;
          goto LABEL_64;
        }
        v24 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        {
          goto LABEL_62;
        }
        v25 = 18;
      }
      else
      {
        v24 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        {
          goto LABEL_62;
        }
        v25 = 17;
      }
    }
    else
    {
      v24 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        goto LABEL_62;
      }
      v25 = 15;
    }
    WPP_SF__guid_iDd(
      v24->AttachedDevice,
      v25,
      v23,
      v7 + 128,
      *(_QWORD *)(v7 + 120),
      *(_DWORD *)(a1 + 24),
      MdlHostVisible);
LABEL_62:
    ChpMakeGpadlHostInvisible(v12);
    *v13 &= ~1u;
    v27 = *v13 & 0xFFFFFFFD;
    *v14 = 0;
    *v13 = v27 & 0xFFFFFFFB;
    ChpDestroyGpadlLocked(v7, v12);
    goto LABEL_64;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF__guid_iD(
      WPP_GLOBAL_Control->AttachedDevice,
      11,
      WPP_b9c76b9a14f83c2168b65499a7c535e1_Traceguids,
      v7 + 128,
      *(_QWORD *)(v7 + 120),
      *(_DWORD *)(a1 + 24));
  }
  MdlHostVisible = -1073741670;
LABEL_64:
  ExReleaseFastMutex((PFAST_MUTEX)(v7 + 432));
  return (unsigned int)MdlHostVisible;
}

```

## disassembly

```asm
0x14000f158  mov     [rsp+arg_8], rbx
0x14000f15d  mov     [rsp+arg_18], r9d
0x14000f162  mov     [rsp+arg_10], r8d
0x14000f167  push    rbp
0x14000f168  push    rsi
0x14000f169  push    rdi
0x14000f16a  push    r12
0x14000f16c  push    r13
0x14000f16e  push    r14
0x14000f170  push    r15
0x14000f172  sub     rsp, 40h
0x14000f176  mov     rbp, [rcx+0D8h]
0x14000f17d  mov     r13, rcx
0x14000f180  mov     r12, rdx
0x14000f183  lea     rax, [rbp+1B0h]
0x14000f18a  mov     rcx, rax; FastMutex
0x14000f18d  mov     [rsp+78h+FastMutex], rax
0x14000f195  call    cs:__imp_ExAcquireFastMutex
0x14000f19c  nop     dword ptr [rax+rax+00h]
0x14000f1a1  xor     esi, esi
0x14000f1a3  cmp     [r13+0F8h], sil
0x14000f1aa  jz      short loc_14000F1B6
0x14000f1ac  mov     esi, 0C00000BBh
0x14000f1b1  jmp     loc_14000F5BA
0x14000f1b6  mov     edx, 78h ; 'x'
0x14000f1bb  mov     r8d, 73756256h
0x14000f1c1  lea     ecx, [rdx-38h]
0x14000f1c4  call    cs:__imp_ExAllocatePool2
0x14000f1cb  nop     dword ptr [rax+rax+00h]
0x14000f1d0  mov     r14, rax
0x14000f1d3  test    rax, rax
0x14000f1d6  jnz     short loc_14000F230
0x14000f1d8  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f1df  lea     rax, WPP_GLOBAL_Control
0x14000f1e6  cmp     rcx, rax
0x14000f1e9  jz      short loc_14000F226
0x14000f1eb  test    dword ptr [rcx+2Ch], 40000h
0x14000f1f2  jz      short loc_14000F226
0x14000f1f4  cmp     byte ptr [rcx+29h], 2
0x14000f1f8  jb      short loc_14000F226
0x14000f1fa  mov     eax, [r13+18h]
0x14000f1fe  lea     r9, [rbp+80h]
0x14000f205  mov     rcx, [rcx+18h]
0x14000f209  lea     edx, [r14+0Bh]
0x14000f20d  mov     [rsp+78h+Priority], eax
0x14000f211  lea     r8, WPP_b9c76b9a14f83c2168b65499a7c535e1_Traceguids
0x14000f218  mov     rax, [rbp+78h]
0x14000f21c  mov     qword ptr [rsp+78h+BugCheckOnFailure], rax
0x14000f221  call    WPP_SF__guid_iD
0x14000f226  mov     esi, 0C000009Ah
0x14000f22b  jmp     loc_14000F5BA
0x14000f230  mov     [rax+8], r14
0x14000f234  lea     rbx, [rax+44h]
0x14000f238  mov     [rax], r14
0x14000f23b  lea     rdi, [r14+18h]
0x14000f23f  and     dword ptr [rbx], 0FFFFFFF8h
0x14000f242  mov     eax, [rsp+78h+arg_30]
0x14000f249  mov     edx, eax
0x14000f24b  mov     r8d, [rbx]
0x14000f24e  and     edx, 1
0x14000f251  jz      short loc_14000F265
0x14000f253  mov     ecx, eax
0x14000f255  mov     [rdi], r12
0x14000f258  and     ecx, 6
0x14000f25b  or      ecx, edx
0x14000f25d  or      ecx, r8d
0x14000f260  mov     r8d, ecx
0x14000f263  mov     [rbx], ecx
0x14000f265  cmp     [rbp+142h], sil
0x14000f26c  jz      loc_14000F3FB
0x14000f272  test    al, 8
0x14000f274  jz      short loc_14000F281
0x14000f276  cmp     [r13+1Eh], sil
0x14000f27a  jz      short loc_14000F28B
0x14000f27c  jmp     loc_14000F3FB
0x14000f281  cmp     [r13+1Fh], sil
0x14000f285  jnz     loc_14000F3FB
0x14000f28b  test    r8b, 1
0x14000f28f  jnz     loc_14000F39F
0x14000f295  test    byte ptr [r12+0Ah], 5
0x14000f29b  jz      short loc_14000F2A4
0x14000f29d  mov     rax, [r12+18h]
0x14000f2a2  jmp     short loc_14000F2C8
0x14000f2a4  xor     r9d, r9d; RequestedAddress
0x14000f2a7  mov     [rsp+78h+Priority], 40000010h; Priority
0x14000f2af  xor     edx, edx; AccessMode
0x14000f2b1  mov     [rsp+78h+BugCheckOnFailure], esi; BugCheckOnFailure
0x14000f2b5  mov     rcx, r12; MemoryDescriptorList
0x14000f2b8  lea     r8d, [r9+1]; CacheType
0x14000f2bc  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14000f2c3  nop     dword ptr [rax+rax+00h]
0x14000f2c8  test    rax, rax
0x14000f2cb  jnz     short loc_14000F31A
0x14000f2cd  mov     esi, 0C000009Ah
0x14000f2d2  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f2d9  lea     rax, WPP_GLOBAL_Control
0x14000f2e0  cmp     rcx, rax
0x14000f2e3  jz      loc_14000F56F
0x14000f2e9  test    dword ptr [rcx+2Ch], 200000h
0x14000f2f0  jz      loc_14000F56F
0x14000f2f6  cmp     byte ptr [rcx+29h], 2
0x14000f2fa  jb      loc_14000F56F
0x14000f300  mov     edx, 0Ch
0x14000f305  mov     rcx, [rcx+18h]
0x14000f309  lea     r8, WPP_b9c76b9a14f83c2168b65499a7c535e1_Traceguids
0x14000f310  call    WPP_SF_
0x14000f315  jmp     loc_14000F56F
0x14000f31a  mov     edx, [r12+28h]; Length
0x14000f31f  xor     r9d, r9d; ChargeQuota
0x14000f322  xor     r8d, r8d; SecondaryBuffer
0x14000f325  mov     qword ptr [rsp+78h+BugCheckOnFailure], rsi; Irp
0x14000f32a  mov     rcx, rax; VirtualAddress
0x14000f32d  call    cs:__imp_IoAllocateMdl
0x14000f334  nop     dword ptr [rax+rax+00h]
0x14000f339  lea     r15, [r14+18h]
0x14000f33d  mov     [r15], rax
0x14000f340  test    rax, rax
0x14000f343  jnz     short loc_14000F389
0x14000f345  mov     esi, 0C000009Ah
0x14000f34a  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f351  lea     rax, WPP_GLOBAL_Control
0x14000f358  cmp     rcx, rax
0x14000f35b  jz      short loc_14000F381
0x14000f35d  test    dword ptr [rcx+2Ch], 200000h
0x14000f364  jz      short loc_14000F381
0x14000f366  cmp     byte ptr [rcx+29h], 2
0x14000f36a  jb      short loc_14000F381
0x14000f36c  mov     rcx, [rcx+18h]
0x14000f370  lea     r8, WPP_b9c76b9a14f83c2168b65499a7c535e1_Traceguids
0x14000f377  mov     edx, 0Dh
0x14000f37c  call    WPP_SF_
0x14000f381  mov     rdi, r15
0x14000f384  jmp     loc_14000F56F
0x14000f389  mov     rcx, rax; MemoryDescriptorList
0x14000f38c  mov     byte ptr [r14+48h], 1
0x14000f391  call    cs:__imp_MmBuildMdlForNonPagedPool
0x14000f398  nop     dword ptr [rax+rax+00h]
0x14000f39d  jmp     short loc_14000F3A2
0x14000f39f  mov     r15, rdi
0x14000f3a2  mov     rcx, [r15]
0x14000f3a5  mov     edx, 1
0x14000f3aa  mov     [r14+4Ah], sil
0x14000f3ae  call    XPartVisMakeMdlHostVisible
0x14000f3b3  mov     esi, eax
0x14000f3b5  test    eax, eax
0x14000f3b7  jns     short loc_14000F3F6
0x14000f3b9  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14000f3be  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f3c5  lea     rax, WPP_GLOBAL_Control
0x14000f3cc  cmp     rcx, rax
0x14000f3cf  jz      loc_14000F56F
0x14000f3d5  test    dword ptr [rcx+2Ch], 200000h
0x14000f3dc  jz      loc_14000F56F
0x14000f3e2  cmp     byte ptr [rcx+29h], 2
0x14000f3e6  jb      loc_14000F56F
0x14000f3ec  mov     edx, 0Eh
0x14000f3f1  jmp     loc_14000F305
0x14000f3f6  mov     byte ptr [r14+49h], 1
0x14000f3fb  mov     r8d, [rsp+78h+arg_18]
0x14000f403  lea     rax, [r14+20h]
0x14000f407  mov     edx, [rsp+78h+arg_10]
0x14000f40e  lea     rcx, [r14+30h]
0x14000f412  mov     qword ptr [rsp+78h+Priority], rax
0x14000f417  lea     r9, [r14+28h]
0x14000f41b  mov     qword ptr [rsp+78h+BugCheckOnFailure], rcx
0x14000f420  mov     rcx, r12
0x14000f423  call    ChpCreateGpaRanges
0x14000f428  mov     esi, eax
0x14000f42a  test    eax, eax
0x14000f42c  jns     short loc_14000F466
0x14000f42e  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f435  lea     rax, WPP_GLOBAL_Control
0x14000f43c  cmp     rcx, rax
0x14000f43f  jz      loc_14000F56F
0x14000f445  test    dword ptr [rcx+2Ch], 40000h
0x14000f44c  jz      loc_14000F56F
0x14000f452  cmp     byte ptr [rcx+29h], 2
0x14000f456  jb      loc_14000F56F
0x14000f45c  mov     edx, 0Fh
0x14000f461  jmp     loc_14000F54A
0x14000f466  mov     esi, 10h
0x14000f46b  mov     rcx, rbp
0x14000f46e  mov     edx, esi
0x14000f470  lea     r8d, [rsi-5]
0x14000f474  call    ChAllocateSendMessageSized
0x14000f479  mov     [r14+70h], rax
0x14000f47d  test    rax, rax
0x14000f480  jnz     short loc_14000F4D8
0x14000f482  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f489  lea     rax, WPP_GLOBAL_Control
0x14000f490  cmp     rcx, rax
0x14000f493  jz      short loc_14000F4CE
0x14000f495  test    dword ptr [rcx+2Ch], 40000h
0x14000f49c  jz      short loc_14000F4CE
0x14000f49e  cmp     byte ptr [rcx+29h], 2
0x14000f4a2  jb      short loc_14000F4CE
0x14000f4a4  mov     eax, [r13+18h]
0x14000f4a8  lea     r9, [rbp+80h]
0x14000f4af  mov     rcx, [rcx+18h]
0x14000f4b3  lea     r8, WPP_b9c76b9a14f83c2168b65499a7c535e1_Traceguids
0x14000f4ba  mov     [rsp+78h+Priority], eax
0x14000f4be  mov     edx, esi
0x14000f4c0  mov     rax, [rbp+78h]
0x14000f4c4  mov     qword ptr [rsp+78h+BugCheckOnFailure], rax
0x14000f4c9  call    WPP_SF__guid_iD
0x14000f4ce  mov     esi, 0C000009Ah
0x14000f4d3  jmp     loc_14000F56F
0x14000f4d8  mov     r8, r14
0x14000f4db  mov     rdx, r13
0x14000f4de  mov     rcx, rbp
0x14000f4e1  call    ChpInsertGpadlLocked
0x14000f4e6  mov     esi, eax
0x14000f4e8  test    eax, eax
0x14000f4ea  jns     short loc_14000F515
0x14000f4ec  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f4f3  lea     rax, WPP_GLOBAL_Control
0x14000f4fa  cmp     rcx, rax
0x14000f4fd  jz      short loc_14000F56F
0x14000f4ff  test    dword ptr [rcx+2Ch], 40000h
0x14000f506  jz      short loc_14000F56F
0x14000f508  cmp     byte ptr [rcx+29h], 2
0x14000f50c  jb      short loc_14000F56F
0x14000f50e  mov     edx, 11h
0x14000f513  jmp     short loc_14000F54A
0x14000f515  mov     rcx, r14
0x14000f518  call    ChpSendEstablishGpadlPacket
0x14000f51d  mov     esi, eax
0x14000f51f  test    eax, eax
0x14000f521  jns     short loc_14000F598
0x14000f523  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f52a  lea     rax, WPP_GLOBAL_Control
0x14000f531  cmp     rcx, rax
0x14000f534  jz      short loc_14000F56F
0x14000f536  test    dword ptr [rcx+2Ch], 40000h
0x14000f53d  jz      short loc_14000F56F
0x14000f53f  cmp     byte ptr [rcx+29h], 2
0x14000f543  jb      short loc_14000F56F
0x14000f545  mov     edx, 12h
0x14000f54a  mov     eax, [r13+18h]
0x14000f54e  lea     r9, [rbp+80h]
0x14000f555  mov     rcx, [rcx+18h]
0x14000f559  mov     [rsp+78h+var_48], esi
0x14000f55d  mov     [rsp+78h+Priority], eax
0x14000f561  mov     rax, [rbp+78h]
0x14000f565  mov     qword ptr [rsp+78h+BugCheckOnFailure], rax
0x14000f56a  call    WPP_SF__guid_iDd
0x14000f56f  mov     rcx, r14
0x14000f572  call    ChpMakeGpadlHostInvisible
0x14000f577  and     dword ptr [rbx], 0FFFFFFFEh
0x14000f57a  mov     rdx, r14
0x14000f57d  mov     eax, [rbx]
0x14000f57f  mov     rcx, rbp
0x14000f582  and     eax, 0FFFFFFFDh
0x14000f585  mov     qword ptr [rdi], 0
0x14000f58c  and     eax, 0FFFFFFFBh
0x14000f58f  mov     [rbx], eax
0x14000f591  call    ChpDestroyGpadlLocked
0x14000f596  jmp     short loc_14000F5BA
0x14000f598  mov     rax, [rsp+78h+arg_20]
0x14000f5a0  xor     esi, esi
0x14000f5a2  mov     [r14+50h], rax
0x14000f5a6  mov     rax, [rsp+78h+arg_28]
0x14000f5ae  mov     [r14+58h], rax
0x14000f5b2  mov     dword ptr [r14+10h], 0
0x14000f5ba  mov     rcx, [rsp+78h+FastMutex]; FastMutex
0x14000f5c2  call    cs:__imp_ExReleaseFastMutex
0x14000f5c9  nop     dword ptr [rax+rax+00h]
0x14000f5ce  mov     rbx, [rsp+78h+arg_8]
0x14000f5d6  mov     eax, esi
0x14000f5d8  add     rsp, 40h
0x14000f5dc  pop     r15
0x14000f5de  pop     r14
0x14000f5e0  pop     r13
0x14000f5e2  pop     r12
0x14000f5e4  pop     rdi
0x14000f5e5  pop     rsi
0x14000f5e6  pop     rbp
0x14000f5e7  retn
```
