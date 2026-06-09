# Smb2RestartNonMdlRead

- ea: `0x140080114`
- end: `0x1400803ac`
- name: `Smb2RestartNonMdlRead`
- size: `664`
- prototype: ``
- caller_count: `2`
- callee_count: `16`
- tags: `broker_com_uri`

## callers

- `0x14007f510`
- `0x14007fd50`

## callees

- `0x1400041a0`
- `0x140004560`
- `0x140005070`
- `0x140006ad0`
- `0x140007090`
- `0x140007400`
- `0x140008190`
- `0x1400125d0`
- `0x140015000`
- `0x1400186f0`
- `0x1400222ec`
- `0x140022958`
- `0x1400384d0`
- `0x14007f340`
- `0x140080114`
- `0x1400803b4`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400802d3`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400802d3`
- `ntoskrnl!KeDelayExecutionThread` at `0x1400986cd`
- `ntoskrnl!KeDelayExecutionThread` at `0x1400986cd`
- `ntoskrnl!IofCallDriver` at `0x1400986a0`
- `ntoskrnl!IofCallDriver` at `0x1400986a0`
- `srvnet!SrvNetAllocateBufferNoTransportHeader` at `0x140080136`
- `srvnet!SrvNetAllocateBufferNoTransportHeader` at `0x140080136`

## string_xrefs

- `0x1400801d2`: `Smb2RestartNonMdlRead`
- `0x14008023f`: `Smb2RestartNonMdlRead`
- `0x140098684`: `Smb2RestartNonMdlRead`
- `0x1400802a0`: `onecore\base\fs\remotefs\smb\srv\srv.v2\smb2\read.c`

## pseudocode

```c
NTSTATUS __fastcall Smb2RestartNonMdlRead(__int64 a1)
{
  __int64 v1; // rdi
  __int64 BufferNoTransportHeader; // rax
  __int64 v4; // rcx
  PVOID v5; // rax
  __int64 v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // rbp
  char v9; // al
  __int64 v10; // rcx
  NTSTATUS result; // eax
  __int64 v12; // r9
  __int64 v13; // rdx
  char v14; // cl
  __int64 v15; // r8
  __int64 v16; // r9
  char v17; // r14
  int v18; // eax
  __int64 v19; // rdx
  unsigned int v20; // ebp
  char v21; // bp
  __int64 v22; // rdx
  ULONG BugCheckOnFailure; // [rsp+20h] [rbp-68h]
  ULONG BugCheckOnFailurea; // [rsp+20h] [rbp-68h]
  ULONG BugCheckOnFailureb; // [rsp+20h] [rbp-68h]
  int Priority; // [rsp+28h] [rbp-60h]
  bool v27; // [rsp+60h] [rbp-28h]
  char v28; // [rsp+68h] [rbp-20h]
  union _LARGE_INTEGER Interval; // [rsp+90h] [rbp+8h] BYREF

  v1 = *(_QWORD *)(a1 + 560);
  BufferNoTransportHeader = SrvNetAllocateBufferNoTransportHeader(*(unsigned int *)(v1 + 236));
  *(_QWORD *)(v1 + 160) = BufferNoTransportHeader;
  if ( !BufferNoTransportHeader )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 28, WPP_464c4860859737a1da74cf96eb989b6c_Traceguids, a1);
    }
    Smb2SequentialReadComplete(a1);
    v12 = 1632;
    goto LABEL_14;
  }
  v4 = *(_QWORD *)(BufferNoTransportHeader + 56);
  if ( (*(_BYTE *)(v4 + 10) & 5) != 0 )
    v5 = *(PVOID *)(v4 + 24);
  else
    v5 = MmMapLockedPagesSpecifyCache((PMDL)v4, 0, MmCached, 0, 0, 0x40000010u);
  v6 = *(_QWORD *)(v1 + 160);
  *(_QWORD *)(v1 + 208) = v5;
  v7 = *(_QWORD *)(v6 + 56);
  *(_QWORD *)(v1 + 200) = v7;
  if ( !v5 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 29, WPP_464c4860859737a1da74cf96eb989b6c_Traceguids, a1);
    }
    Smb2SequentialReadComplete(a1);
    v12 = 1647;
LABEL_14:
    v13 = 3221225989LL;
LABEL_15:
    Smb2SetError(a1, v13, "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\read.c", v12);
    return Srv2CompleteWorkItem(a1, 0);
  }
  LOBYTE(v7) = 2;
  if ( (*(_BYTE *)(v1 + 264) & 2) == 0 )
  {
    v8 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v1 + 96) + 8LL) + 80LL);
    if ( v8 )
    {
      if ( *(_DWORD *)v8 > 0x10u && *(_QWORD *)(v8 + 16) )
      {
        LOBYTE(BugCheckOnFailure) = 1;
        SRV2_PERF_ENTER_EX(a1 + 584, v7, 1660, "Smb2RestartNonMdlRead", BugCheckOnFailure);
        v9 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD, _DWORD, _QWORD, __int64, _QWORD))(v8 + 16))(
               *(_QWORD *)(v1 + 88),
               v1 + 192,
               *(unsigned int *)(v1 + 236),
               0,
               *(_DWORD *)(v1 + 252),
               *(_QWORD *)(*(_QWORD *)(v1 + 200) + 32LL) + *(unsigned int *)(*(_QWORD *)(v1 + 200) + 44LL),
               *(_QWORD *)(a1 + 120) + 48LL,
               *(_QWORD *)(v1 + 96));
        LOBYTE(BugCheckOnFailurea) = 1;
        v10 = a1 + 584;
        if ( v9 )
        {
          SRV2_PERF_ENTER_EX(v10, 0, 1675, "Smb2RestartNonMdlRead", BugCheckOnFailurea);
          return Smb2ContinueUncachedRead(a1);
        }
        SRV2_PERF_ENTER_EX(v10, 0, 1680, "Smb2RestartNonMdlRead", BugCheckOnFailurea);
      }
    }
  }
  v14 = *(_BYTE *)(v1 + 264);
  v15 = *(_QWORD *)(v1 + 200);
  if ( (v14 & 4) != 0 )
  {
    v16 = *(_QWORD *)(v15 + 32) + *(unsigned int *)(v15 + 44);
    v17 = 1;
    LOBYTE(v15) = 3;
    v18 = Smb2BuildPipeReadOrWriteRequest(a1, *(_QWORD *)(v1 + 88), v15, v16, *(_DWORD *)(v1 + 236));
  }
  else
  {
    v17 = 0;
    v28 = 0;
    v27 = (v14 & 0x10) != 0;
    LOBYTE(Priority) = 0;
    LOBYTE(BugCheckOnFailure) = 3;
    v18 = Smb2BuildReadOrWriteRequest(
            a1,
            0,
            *(_QWORD *)(v1 + 88),
            *(_QWORD *)(v1 + 96),
            BugCheckOnFailure,
            Priority,
            *(_QWORD *)(v15 + 32) + *(unsigned int *)(v15 + 44),
            *(_DWORD *)(v1 + 236),
            v15,
            *(_QWORD *)(v1 + 192),
            *(_DWORD *)(v1 + 252),
            Srv2PostOnCompletionAndClearCancel,
            v27,
            v28);
  }
  v20 = v18;
  if ( v18 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800000) != 0 )
    {
      if ( BYTE1(WPP_GLOBAL_Control->Timer) )
        WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 30, WPP_464c4860859737a1da74cf96eb989b6c_Traceguids, a1, v18);
    }
    Smb2SequentialReadComplete(a1);
    v12 = 1722;
    v13 = v20;
    goto LABEL_15;
  }
  v21 = v17;
  *(_QWORD *)(a1 + 48) = Smb2ContinueUncachedIrpRead;
  if ( (*(_BYTE *)(v1 + 264) & 8) != 0 )
    v21 = 1;
  LOBYTE(v19) = v21;
  if ( (int)Srv2MarkWorkItemCancellable(a1, v19) < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 31, WPP_464c4860859737a1da74cf96eb989b6c_Traceguids, a1);
    }
    Smb2SequentialReadComplete(a1);
    v12 = 1741;
    v13 = 3221225760LL;
    goto LABEL_15;
  }
  if ( v21 )
    Srv2ReferenceConnection(a1);
  LOBYTE(BugCheckOnFailureb) = 1;
  LOBYTE(v22) = 3;
  SRV2_PERF_ENTER_EX(a1 + 584, v22, 1752, "Smb2RestartNonMdlRead", BugCheckOnFailureb);
  result = IofCallDriver(*(PDEVICE_OBJECT *)(v1 + 96), *(PIRP *)(a1 + 120));
  if ( v21 )
  {
    Interval.QuadPart = -5000;
    KeDelayExecutionThread(0, 0, &Interval);
    if ( (unsigned int)Srv2MarkWorkItemPending(a1) )
      return Srv2DereferenceWorkItem(a1);
    else
      return Smb2GoAsync2(a1);
  }
  return result;
}

```

## disassembly

```asm
0x140080114  mov     [rsp+arg_8], rbx
0x140080119  mov     [rsp+arg_10], rbp
0x14008011e  push    rsi
0x14008011f  push    rdi
0x140080120  push    r14
0x140080122  sub     rsp, 70h
0x140080126  mov     rdi, [rcx+230h]
0x14008012d  mov     rbx, rcx
0x140080130  mov     ecx, [rdi+0ECh]
0x140080136  call    cs:__imp_SrvNetAllocateBufferNoTransportHeader
0x14008013d  nop     dword ptr [rax+rax+00h]
0x140080142  mov     [rdi+0A0h], rax
0x140080149  test    rax, rax
0x14008014c  jz      loc_14008027A
0x140080152  mov     rcx, [rax+38h]; MemoryDescriptorList
0x140080156  mov     esi, 1
0x14008015b  test    byte ptr [rcx+0Ah], 5
0x14008015f  jz      loc_1400802BB
0x140080165  mov     rax, [rcx+18h]
0x140080169  mov     rcx, [rdi+0A0h]
0x140080170  mov     [rdi+0D0h], rax
0x140080177  mov     rdx, [rcx+38h]
0x14008017b  mov     [rdi+0C8h], rdx
0x140080182  test    rax, rax
0x140080185  jz      loc_140080313
0x14008018b  mov     dl, 2
0x14008018d  test    [rdi+108h], dl
0x140080193  jnz     loc_14008036A
0x140080199  mov     rax, [rdi+60h]
0x14008019d  mov     rcx, [rax+8]
0x1400801a1  mov     rbp, [rcx+50h]
0x1400801a5  test    rbp, rbp
0x1400801a8  jz      loc_14008036A
0x1400801ae  cmp     dword ptr [rbp+0], 10h
0x1400801b2  jbe     loc_14008036A
0x1400801b8  cmp     qword ptr [rbp+10h], 0
0x1400801bd  jz      loc_14008036A
0x1400801c3  lea     r14, [rbx+248h]
0x1400801ca  mov     byte ptr [rsp+88h+BugCheckOnFailure], sil
0x1400801cf  mov     rcx, r14
0x1400801d2  lea     r9, aSmb2restartnon; "Smb2RestartNonMdlRead"
0x1400801d9  mov     r8d, 67Ch
0x1400801df  call    SRV2_PERF_ENTER_EX
0x1400801e4  mov     rax, [rdi+0C8h]
0x1400801eb  lea     rdx, [rdi+0C0h]
0x1400801f2  mov     rcx, [rdi+60h]
0x1400801f6  xor     r9d, r9d
0x1400801f9  mov     r10, [rbx+78h]
0x1400801fd  mov     [rsp+88h+var_50], rcx
0x140080202  add     r10, 30h ; '0'
0x140080206  mov     r8d, [rax+2Ch]
0x14008020a  add     r8, [rax+20h]
0x14008020e  mov     rax, [rbp+10h]
0x140080212  mov     rcx, [rdi+58h]
0x140080216  mov     [rsp+88h+var_58], r10
0x14008021b  mov     qword ptr [rsp+88h+Priority], r8
0x140080220  mov     r8d, [rdi+0FCh]
0x140080227  mov     [rsp+88h+BugCheckOnFailure], r8d
0x14008022c  mov     r8d, [rdi+0ECh]
0x140080233  call    _guard_dispatch_icall
0x140080238  xor     edx, edx
0x14008023a  mov     byte ptr [rsp+88h+BugCheckOnFailure], sil
0x14008023f  lea     r9, aSmb2restartnon; "Smb2RestartNonMdlRead"
0x140080246  mov     rcx, r14
0x140080249  test    al, al
0x14008024b  jz      loc_14008035F
0x140080251  mov     r8d, 68Bh
0x140080257  call    SRV2_PERF_ENTER_EX
0x14008025c  mov     rcx, rbx
0x14008025f  call    Smb2ContinueUncachedRead
0x140080264  lea     r11, [rsp+88h+var_18]
0x140080269  mov     rbx, [r11+28h]
0x14008026d  mov     rbp, [r11+30h]
0x140080271  mov     rsp, r11
0x140080274  pop     r14
0x140080276  pop     rdi
0x140080277  pop     rsi
0x140080278  retn
0x14008027a  mov     rcx, cs:WPP_GLOBAL_Control
0x140080281  lea     rax, WPP_GLOBAL_Control
0x140080288  cmp     rcx, rax
0x14008028b  jnz     short loc_1400802E4
0x14008028d  mov     rcx, rbx
0x140080290  call    Smb2SequentialReadComplete
0x140080295  mov     r9d, 660h
0x14008029b  mov     edx, 0C0000205h
0x1400802a0  lea     r8, aOnecoreBaseFsR_9; "onecore\\base\\fs\\remotefs\\smb\\srv\\"...
0x1400802a7  mov     rcx, rbx
0x1400802aa  call    _Smb2SetError
0x1400802af  xor     edx, edx
0x1400802b1  mov     rcx, rbx
0x1400802b4  call    Srv2CompleteWorkItem
0x1400802b9  jmp     short loc_140080264
0x1400802bb  mov     [rsp+88h+Priority], 40000010h; Priority
0x1400802c3  xor     r9d, r9d; RequestedAddress
0x1400802c6  mov     r8d, esi; CacheType
0x1400802c9  mov     [rsp+88h+BugCheckOnFailure], 0; BugCheckOnFailure
0x1400802d1  xor     edx, edx; AccessMode
0x1400802d3  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x1400802da  nop     dword ptr [rax+rax+00h]
0x1400802df  jmp     loc_140080169
0x1400802e4  test    dword ptr [rcx+2Ch], 800000h
0x1400802eb  jz      short loc_14008028D
0x1400802ed  mov     esi, 1
0x1400802f2  cmp     [rcx+29h], sil
0x1400802f6  jb      short loc_14008028D
0x1400802f8  mov     rcx, [rcx+18h]
0x1400802fc  lea     edx, [rsi+1Bh]
0x1400802ff  mov     r9, rbx
0x140080302  lea     r8, WPP_464c4860859737a1da74cf96eb989b6c_Traceguids
0x140080309  call    WPP_SF_q
0x14008030e  jmp     loc_14008028D
0x140080313  mov     rcx, cs:WPP_GLOBAL_Control
0x14008031a  lea     rax, WPP_GLOBAL_Control
0x140080321  cmp     rcx, rax
0x140080324  jz      loc_14009851E
0x14008032a  test    dword ptr [rcx+2Ch], 800000h
0x140080331  jz      loc_14009851E
0x140080337  cmp     [rcx+29h], sil
0x14008033b  jb      loc_14009851E
0x140080341  mov     rcx, [rcx+18h]
0x140080345  lea     r8, WPP_464c4860859737a1da74cf96eb989b6c_Traceguids
0x14008034c  mov     edx, 1Dh
0x140080351  mov     r9, rbx
0x140080354  call    WPP_SF_q
0x140080359  nop
0x14008035a  jmp     loc_14009851E
0x14008035f  mov     r8d, 690h
0x140080365  call    SRV2_PERF_ENTER_EX
0x14008036a  mov     cl, [rdi+108h]
0x140080370  mov     r8, [rdi+0C8h]
0x140080377  mov     r10d, [rdi+0ECh]
0x14008037e  test    cl, 4
0x140080381  jz      loc_140098531
0x140080387  mov     r9d, [r8+2Ch]
0x14008038b  mov     rcx, rbx
0x14008038e  add     r9, [r8+20h]
0x140080392  mov     r14b, sil
0x140080395  mov     rdx, [rdi+58h]
0x140080399  mov     r8b, 3
0x14008039c  mov     [rsp+88h+BugCheckOnFailure], r10d
0x1400803a1  call    Smb2BuildPipeReadOrWriteRequest
0x1400803a6  nop
0x1400803a7  jmp     loc_140098598
0x14009851e  mov     rcx, rbx
0x140098521  call    Smb2SequentialReadComplete
0x140098526  mov     r9d, 66Fh
0x14009852c  jmp     loc_14008029B
0x140098531  mov     edx, [r8+2Ch]
0x140098535  xor     r14b, r14b
0x140098538  add     rdx, [r8+20h]
0x14009853c  mov     rax, [rdi+0C0h]
0x140098543  mov     r9, [rdi+60h]
0x140098547  mov     [rsp+88h+var_20], r14b
0x14009854c  shr     cl, 4
0x14009854f  and     cl, sil
0x140098552  mov     [rsp+88h+var_28], cl
0x140098556  lea     rcx, Srv2PostOnCompletionAndClearCancel
0x14009855d  mov     [rsp+88h+var_30], rcx
0x140098562  mov     ecx, [rdi+0FCh]
0x140098568  mov     [rsp+88h+var_38], ecx
0x14009856c  mov     rcx, rbx
0x14009856f  mov     [rsp+88h+var_40], rax
0x140098574  mov     [rsp+88h+var_48], r8
0x140098579  mov     r8, [rdi+58h]
0x14009857d  mov     dword ptr [rsp+88h+var_50], r10d
0x140098582  mov     [rsp+88h+var_58], rdx
0x140098587  xor     edx, edx
0x140098589  mov     byte ptr [rsp+88h+Priority], r14b
0x14009858e  mov     byte ptr [rsp+88h+BugCheckOnFailure], 3
0x140098593  call    Smb2BuildReadOrWriteRequest
0x140098598  mov     ebp, eax
0x14009859a  test    eax, eax
0x14009859c  jns     short loc_1400985F1
0x14009859e  mov     rcx, cs:WPP_GLOBAL_Control
0x1400985a5  lea     rax, WPP_GLOBAL_Control
0x1400985ac  cmp     rcx, rax
0x1400985af  jz      short loc_1400985DC
0x1400985b1  test    dword ptr [rcx+2Ch], 800000h
0x1400985b8  jz      short loc_1400985DC
0x1400985ba  cmp     [rcx+29h], sil
0x1400985be  jb      short loc_1400985DC
0x1400985c0  mov     rcx, [rcx+18h]
0x1400985c4  lea     r8, WPP_464c4860859737a1da74cf96eb989b6c_Traceguids
0x1400985cb  mov     edx, 1Eh
0x1400985d0  mov     [rsp+88h+BugCheckOnFailure], ebp
0x1400985d4  mov     r9, rbx
0x1400985d7  call    WPP_SF_qD
0x1400985dc  mov     rcx, rbx
0x1400985df  call    Smb2SequentialReadComplete
0x1400985e4  mov     r9d, 6BAh
0x1400985ea  mov     edx, ebp
0x1400985ec  jmp     loc_1400802A0
0x1400985f1  lea     rax, Smb2ContinueUncachedIrpRead
0x1400985f8  movzx   ebp, r14b
0x1400985fc  mov     [rbx+30h], rax
0x140098600  mov     rcx, rbx
0x140098603  test    byte ptr [rdi+108h], 8
0x14009860a  cmovnz  ebp, esi
0x14009860d  mov     dl, bpl
0x140098610  call    Srv2MarkWorkItemCancellable
0x140098615  test    eax, eax
0x140098617  jns     short loc_14009866B
0x140098619  mov     rcx, cs:WPP_GLOBAL_Control
0x140098620  lea     rax, WPP_GLOBAL_Control
0x140098627  cmp     rcx, rax
0x14009862a  jz      short loc_140098653
0x14009862c  test    dword ptr [rcx+2Ch], 800000h
0x140098633  jz      short loc_140098653
0x140098635  cmp     [rcx+29h], sil
0x140098639  jb      short loc_140098653
0x14009863b  mov     rcx, [rcx+18h]
0x14009863f  lea     r8, WPP_464c4860859737a1da74cf96eb989b6c_Traceguids
0x140098646  mov     edx, 1Fh
0x14009864b  mov     r9, rbx
0x14009864e  call    WPP_SF_q
0x140098653  mov     rcx, rbx
0x140098656  call    Smb2SequentialReadComplete
0x14009865b  mov     r9d, 6CDh
0x140098661  mov     edx, 0C0000120h
0x140098666  jmp     loc_1400802A0
0x14009866b  test    bpl, bpl
0x14009866e  jz      short loc_140098678
0x140098670  mov     rcx, rbx
0x140098673  call    Srv2ReferenceConnection
0x140098678  lea     rcx, [rbx+248h]
0x14009867f  mov     byte ptr [rsp+88h+BugCheckOnFailure], sil
0x140098684  lea     r9, aSmb2restartnon; "Smb2RestartNonMdlRead"
0x14009868b  mov     r8d, 6D8h
0x140098691  mov     dl, 3
0x140098693  call    SRV2_PERF_ENTER_EX
0x140098698  mov     rdx, [rbx+78h]; Irp
0x14009869c  mov     rcx, [rdi+60h]; DeviceObject
0x1400986a0  call    cs:__imp_IofCallDriver
0x1400986a7  nop     dword ptr [rax+rax+00h]
0x1400986ac  test    bpl, bpl
0x1400986af  jz      loc_140080264
0x1400986b5  lea     r8, [rsp+88h+Interval]; Interval
0x1400986bd  mov     qword ptr [rsp+88h+Interval], 0FFFFFFFFFFFFEC78h
0x1400986c9  xor     edx, edx; Alertable
0x1400986cb  xor     ecx, ecx; WaitMode
0x1400986cd  call    cs:__imp_KeDelayExecutionThread
0x1400986d4  nop     dword ptr [rax+rax+00h]
0x1400986d9  mov     rcx, rbx
0x1400986dc  call    Srv2MarkWorkItemPending
0x1400986e1  mov     rcx, rbx
0x1400986e4  test    eax, eax
0x1400986e6  jnz     short loc_1400986F3
0x1400986e8  call    Smb2GoAsync2
0x1400986ed  nop
0x1400986ee  jmp     loc_140080264
0x1400986f3  call    Srv2DereferenceWorkItem
0x1400986f8  nop
0x1400986f9  jmp     loc_140080264
```
