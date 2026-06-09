# VhdmpiCompleteParserRequest

- ea: `0x14000fbf0`
- end: `0x140010302`
- name: `VhdmpiCompleteParserRequest`
- size: `1810`
- prototype: `__int64 __fastcall(struct _VHD_SRB_EXTENSION *)`
- caller_count: `1`
- callee_count: `20`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14000fb90`

## callees

- `0x14000d920`
- `0x14000f670`
- `0x14000fbf0`
- `0x140010b60`
- `0x1400121d0`
- `0x1400122b0`
- `0x140014550`
- `0x140014660`
- `0x140015700`
- `0x14001bc30`
- `0x140023940`
- `0x140025718`
- `0x14002a030`
- `0x14002a390`
- `0x140031da8`
- `0x140033450`
- `0x140035e94`
- `0x140040f48`
- `0x14005d840`
- `0x14005da00`

## import_xrefs

- `ntoskrnl!IoFreeMdl` at `0x14000fd8a`
- `ntoskrnl!IoFreeMdl` at `0x140010182`
- `ntoskrnl!IoFreeMdl` at `0x14000fd8a`
- `ntoskrnl!IoFreeMdl` at `0x140010182`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14000fcaf`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140010043`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400100b3`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14000fcaf`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140010043`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400100b3`
- `ntoskrnl!RtlCompareMemory` at `0x14000fcc9`
- `ntoskrnl!RtlCompareMemory` at `0x14000fcc9`
- `ntoskrnl!ExReleaseRundownProtection` at `0x140010214`
- `ntoskrnl!ExReleaseRundownProtection` at `0x140010214`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000fdb0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001019b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000fdb0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001019b`

## string_xrefs

- `0x14000fe09`: `VhdmpiCompleteParserRequest`
- `0x14000fef6`: `VhdmpiCompleteParserRequest`
- `0x14001011b`: `VhdmpiCompleteParserRequest`
- `0x14000fdfd`: `VhdmpiCompleteParserRequest: SrbExtension=0x%p IrpStatus=0x%08x`
- `0x140010137`: `VhdmpiCompleteParserRequest: checksum mismatch at disk offset 0x%I64x  for virtual disk 0x%I64u`
- `0x14000ff1d`: `VhdmpiCompleteParserRequest: SRB issued on low resources queue -> SrbExtension=0x%p, Status=0x%08x, Op=%d, Length=%lu`

## pseudocode

```c
void __fastcall VhdmpiCompleteParserRequest(struct _VHD_SRB_EXTENSION *a1)
{
  __int64 v1; // rsi
  int v2; // ebp
  void *v4; // r15
  struct _MDL *v5; // r14
  int v6; // eax
  bool v7; // zf
  __int64 v8; // rcx
  char *v9; // rbx
  int v10; // eax
  __int64 v11; // rcx
  int v12; // ecx
  __int64 v13; // rax
  __int64 v14; // rcx
  int v15; // ebx
  int v16; // ecx
  char v17; // dl
  PVOID MappedSystemVa; // rax
  int v19; // eax
  int v20; // edx
  int v21; // r8d
  int v22; // r9d
  int v23; // r8d
  __int64 v24; // rax
  __int64 v25; // rbx
  unsigned __int8 v26; // al
  unsigned __int8 v27; // al
  __int128 v28; // [rsp+50h] [rbp-88h] BYREF
  _OWORD v29[3]; // [rsp+60h] [rbp-78h] BYREF
  __int64 v30; // [rsp+90h] [rbp-48h]
  char v31; // [rsp+E0h] [rbp+8h] BYREF
  void *v32; // [rsp+E8h] [rbp+10h] BYREF
  PMDL MemoryDescriptorList; // [rsp+F0h] [rbp+18h] BYREF

  v1 = *(_QWORD *)a1;
  v2 = *((_DWORD *)a1 + 17);
  v32 = 0;
  MemoryDescriptorList = 0;
  v4 = 0;
  v31 = 0;
  v5 = 0;
  v6 = *((_DWORD *)a1 + 16);
  v28 = 0;
  if ( (v6 & 0x800) != 0 )
  {
    if ( *((_DWORD *)a1 + 15) == 4 && *((int *)a1 + 12) < 0 )
    {
      *((_DWORD *)a1 + 16) &= ~0x100u;
      *((_DWORD *)a1 + 15) = 1;
      *((_QWORD *)a1 + 29) = 0;
LABEL_17:
      *((_QWORD *)a1 + 5) = 1;
      *((_QWORD *)&v28 + 1) = &v28;
      *((_DWORD *)a1 + 12) = 259;
      *(_QWORD *)&v28 = &v28;
      VhdmpiSrbExtensionEnqueueForProcessing(a1, &v28);
      VhdmpiProcessParseThreadContext(&v28, 0);
      return;
    }
  }
  else if ( (v6 & 0x1000) != 0 )
  {
    v7 = *((_DWORD *)a1 + 15) == 2;
    *((_DWORD *)a1 + 14) = *((_DWORD *)a1 + 13);
    if ( v7 && *((int *)a1 + 12) >= 0 )
    {
      v8 = *((_QWORD *)a1 + 13);
      if ( (*(_BYTE *)(v8 + 10) & 5) != 0 )
        v9 = *(char **)(v8 + 24);
      else
        v9 = (char *)MmMapLockedPagesSpecifyCache((PMDL)v8, 0, MmCached, 0, 0, 0x40000010u);
      v10 = RtlCompareMemory(v9, *((const void **)a1 + 14), *((unsigned int *)a1 + 13));
      v11 = *((unsigned int *)a1 + 13);
      if ( v10 == (_DWORD)v11 )
      {
        *((_DWORD *)a1 + 15) = 1;
        memmove(*((void **)a1 + 14), &v9[v11], (unsigned int)v11);
        goto LABEL_17;
      }
      *((_DWORD *)a1 + 14) = v10;
      *((_DWORD *)a1 + 12) = -1073741823;
    }
  }
  else if ( (v6 & 0x2000) != 0 )
  {
    *((_DWORD *)a1 + 31) += *((_DWORD *)a1 + 13);
    v12 = *((_DWORD *)a1 + 31);
    v13 = **((_QWORD **)a1 + 9);
    if ( v13 )
    {
      *((_QWORD *)a1 + 9) = v13;
      *((_DWORD *)a1 + 13) = *(_DWORD *)(v13 + 40);
      goto LABEL_17;
    }
    *((_QWORD *)a1 + 9) = *((_QWORD *)a1 + 13);
    *((_DWORD *)a1 + 13) = *((_DWORD *)a1 + 30);
    *((_QWORD *)a1 + 15) = 0;
    *((_QWORD *)a1 + 13) = 0;
    *((_DWORD *)a1 + 14) = v12;
  }
  if ( *((_QWORD *)a1 + 13) )
  {
    IoFreeMdl(*((PMDL *)a1 + 9));
    *((_QWORD *)a1 + 9) = *((_QWORD *)a1 + 13);
    *((_QWORD *)a1 + 13) = 0;
  }
  v14 = *((_QWORD *)a1 + 14);
  if ( v14 )
  {
    ExFreePoolWithTag((PVOID)v14, 0x5A444856u);
    *((_QWORD *)a1 + 14) = 0;
  }
  if ( *((_DWORD *)a1 + 12) == 259 )
    *((_DWORD *)a1 + 12) = 0;
  v15 = *((_DWORD *)a1 + 12);
  if ( (unsigned int)dword_140087708 > 5 )
  {
    LODWORD(v14) = qword_140087720;
    if ( (qword_140087718 & 8) != 0 && (qword_140087720 & 8) == qword_140087720 )
      TraceEvents(
        "VhdmpiCompleteParserRequest",
        0xB50u,
        5u,
        8u,
        "VhdmpiCompleteParserRequest: SrbExtension=0x%p IrpStatus=0x%08x",
        a1,
        *((_DWORD *)a1 + 12));
  }
  if ( v15 >= 0 )
    goto LABEL_58;
  if ( v2 == 3 )
    goto LABEL_34;
  if ( v15 != -1073741697 )
  {
    if ( (unsigned int)(*((_DWORD *)a1 + 15) - 4) > 3 )
      VhdmpiCreateErrorLogEntry(a1);
LABEL_34:
    if ( (v15 == -1073741670 || v15 == -1073741801 || v15 == -1073741663)
      && (*((_DWORD *)a1 + 16) & 0x20) == 0
      && (unsigned int)(*((_DWORD *)a1 + 15) - 1) <= 2 )
    {
      *((_DWORD *)a1 + 70) = 1;
    }
  }
  if ( *((_DWORD *)a1 + 70) == 1 && (*((_DWORD *)a1 + 16) & 0x20) == 0 )
  {
    v14 = *((_QWORD *)a1 + 1);
    if ( *(_QWORD *)(v14 + 1136) == *(_QWORD *)a1 )
    {
      *((_QWORD *)a1 + 5) = 1;
      *((_DWORD *)a1 + 12) = 259;
      *((_DWORD *)a1 + 70) = 2;
      if ( (unsigned int)dword_140087708 > 5 && (qword_140087718 & 8) != 0 && (qword_140087720 & 8) == qword_140087720 )
        TraceEvents(
          "VhdmpiCompleteParserRequest",
          0xB89u,
          5u,
          8u,
          "VhdmpiCompleteParserRequest: SRB issued on low resources queue -> SrbExtension=0x%p, Status=0x%08x, Op=%d, Length=%lu",
          a1,
          v15,
          *((_DWORD *)a1 + 15),
          *((_DWORD *)a1 + 13));
      VhdmpiIssueSrbExtensionOnLowResourcesQueue((struct VHD_LOW_RESOURCES_QUEUE *)(v1 + 904), a1);
      return;
    }
  }
  if ( *(_QWORD *)(v1 + 1008) && *(_BYTE *)(v1 + 1032) && (unsigned int)(*((_DWORD *)a1 + 15) - 1) <= 2 )
    VhdmpiAccumulateMirrorStatus(v1, (unsigned int)v15);
  if ( (unsigned int)(v2 - 2) > 1 && (unsigned int)(*((_DWORD *)a1 + 15) - 4) > 1 )
  {
    LODWORD(v14) = *(_DWORD *)(v1 + 1856);
    if ( (_DWORD)v14 )
    {
      v16 = v14 - 1;
      if ( v16 )
        LODWORD(v14) = v16 - 1;
      else
        VhdmpiCTLogFailChangeTracking(v1, (unsigned int)v15, *((unsigned int *)a1 + 56));
    }
  }
LABEL_58:
  if ( *((_BYTE *)a1 + 352) )
    VhdmpiProcessEventComplete((PEX_RUNDOWN_REF)(v1 + 384));
  if ( (*(_DWORD *)(v1 + 2144) & 8) == 0
    || !(unsigned __int8)VhdmpiIsCTLogTrackingEnabled(v1)
    || *((_DWORD *)a1 + 15) != 1
    || (unsigned int)(*((_DWORD *)a1 + 17) - 2) <= 1
    || (v17 & 0x40) != 0
    || !*((_DWORD *)a1 + 69) )
  {
    goto LABEL_89;
  }
  if ( (*((_DWORD *)a1 + 16) & 0x800) == 0 )
  {
    v14 = *((_QWORD *)a1 + 9);
    if ( (*(_BYTE *)(v14 + 10) & 5) != 0 )
      MappedSystemVa = *(PVOID *)(v14 + 24);
    else
      MappedSystemVa = MmMapLockedPagesSpecifyCache((PMDL)v14, 0, MmCached, 0, 0, 0xC0000010);
    goto LABEL_75;
  }
  v19 = VhdmpiExtendDataBuffer(a1, 1749305430, &v32, &MemoryDescriptorList, &v31);
  v5 = MemoryDescriptorList;
  if ( v19 >= 0 )
  {
    if ( (MemoryDescriptorList->MdlFlags & 5) != 0 )
      MappedSystemVa = MemoryDescriptorList->MappedSystemVa;
    else
      MappedSystemVa = MmMapLockedPagesSpecifyCache(MemoryDescriptorList, 0, MmCached, 0, 0, 0xC0000010);
    v4 = v32;
LABEL_75:
    if ( MappedSystemVa
      && *((_DWORD *)a1 + 69) != (unsigned int)VhdmpiCalculateChecksum(MappedSystemVa, *((unsigned int *)a1 + 13), 0) )
    {
      if ( (unsigned int)dword_140087708 > 2 )
      {
        LODWORD(v14) = qword_140087720;
        if ( (qword_140087718 & 0x1000) != 0 && (qword_140087720 & 0x1000) == qword_140087720 )
          TraceEvents(
            "VhdmpiCompleteParserRequest",
            0xBE8u,
            2u,
            0x1000u,
            "VhdmpiCompleteParserRequest: checksum mismatch at disk offset 0x%I64x  for virtual disk 0x%I64u",
            *((_QWORD *)a1 + 4),
            v1);
      }
      if ( (Microsoft_Windows_VHDMPEnableBits & 4) != 0 )
        McTemplateK0xzq_EtwWriteTransfer(v14, v20, v21, v22, 0, 33);
      *(_DWORD *)(v1 + 2144) |= 0x40u;
    }
    goto LABEL_85;
  }
  v4 = v32;
LABEL_85:
  if ( v5 )
    IoFreeMdl(v5);
  if ( v4 )
    ExFreePoolWithTag(v4, 0x68444856u);
LABEL_89:
  if ( (Microsoft_Windows_VHDMPEnableBits & 0x100) != 0 && *((_BYTE *)a1 + 272) )
    McTemplateK0zqqxqq_EtwWriteTransfer(
      v14,
      (unsigned int)VHD_COMPLETE_IO,
      (_DWORD)a1 + 256,
      *(_QWORD *)(*(_QWORD *)(v1 + 144) + 120LL),
      *((_DWORD *)a1 + 15),
      *((_DWORD *)a1 + 17),
      *((_QWORD *)a1 + 4),
      *((_DWORD *)a1 + 13),
      *((_DWORD *)a1 + 12));
  if ( (*((_BYTE *)a1 + 64) & 9) == 9 )
  {
    ExReleaseRundownProtection((PEX_RUNDOWN_REF)(*(_QWORD *)(*(_QWORD *)a1 + 200LL) + 80LL));
    *((_DWORD *)a1 + 16) &= ~8u;
  }
  if ( *((_QWORD *)a1 + 3) )
  {
    v23 = *((_DWORD *)a1 + 12);
    v30 = 0;
    v24 = *(_QWORD *)a1;
    memset(v29, 0, sizeof(v29));
    v25 = *(_QWORD *)(v24 + 200);
    v26 = VhdmpiScsiProcessActionCompletion(
            (struct VHD_SCSI_STATE *)(v25 + 656),
            (struct _VHD_SRB_EXTENSION *)((char *)a1 + 384),
            v23,
            MEMORY[0xFFFFF78000000008],
            (struct VHD_SCSI_ACTION *)v29);
    v27 = VhdmpiHandleScsiParsingResult((struct _VHD_SURFACE *)v25, a1, (struct VHD_SCSI_ACTION *)v29, v26, 0);
    if ( !v27 )
      return;
    VhdmpiCompleteScsiRequest(a1, v27);
    if ( *((_BYTE *)a1 + 352) )
      VhdmpiProcessEventComplete((PEX_RUNDOWN_REF)(*(_QWORD *)a1 + 384LL));
  }
  else
  {
    VhdmpiReleaseRequestResources(a1);
  }
  (*((void (__fastcall **)(_QWORD, _QWORD))a1 + 11))(*((_QWORD *)a1 + 10), *((unsigned int *)a1 + 12));
}

```

## disassembly

```asm
0x14000fbf0  mov     rax, rsp
0x14000fbf3  push    rbx
0x14000fbf4  push    rbp
0x14000fbf5  push    rsi
0x14000fbf6  push    rdi
0x14000fbf7  push    r12
0x14000fbf9  push    r14
0x14000fbfb  push    r15
0x14000fbfd  sub     rsp, 0A0h
0x14000fc04  mov     rsi, [rcx]
0x14000fc07  xor     r12d, r12d
0x14000fc0a  mov     ebp, [rcx+44h]
0x14000fc0d  xorps   xmm0, xmm0
0x14000fc10  mov     [rax+10h], r12
0x14000fc14  mov     rdi, rcx
0x14000fc17  mov     [rax+18h], r12
0x14000fc1b  mov     r15d, r12d
0x14000fc1e  mov     [rax+8], r12b
0x14000fc22  mov     r14d, r12d
0x14000fc25  mov     eax, [rcx+40h]
0x14000fc28  movups  [rsp+0D8h+var_88], xmm0
0x14000fc2d  bt      eax, 0Bh
0x14000fc31  jnb     short loc_14000FC62
0x14000fc33  cmp     dword ptr [rcx+3Ch], 4
0x14000fc37  jnz     loc_14000FD80
0x14000fc3d  mov     eax, [rcx+30h]
0x14000fc40  test    eax, eax
0x14000fc42  jns     loc_14000FD80
0x14000fc48  and     dword ptr [rcx+40h], 0FFFFFEFFh
0x14000fc4f  mov     dword ptr [rcx+3Ch], 1
0x14000fc56  mov     [rcx+0E8h], r12
0x14000fc5d  jmp     loc_14000FD26
0x14000fc62  bt      eax, 0Ch
0x14000fc66  jnb     loc_14000FD01
0x14000fc6c  cmp     dword ptr [rcx+3Ch], 2
0x14000fc70  mov     eax, [rcx+34h]
0x14000fc73  mov     [rcx+38h], eax
0x14000fc76  jnz     loc_14000FD80
0x14000fc7c  mov     eax, [rcx+30h]
0x14000fc7f  test    eax, eax
0x14000fc81  js      loc_14000FD80
0x14000fc87  mov     rcx, [rcx+68h]; MemoryDescriptorList
0x14000fc8b  test    byte ptr [rcx+0Ah], 5
0x14000fc8f  jz      short loc_14000FC97
0x14000fc91  mov     rbx, [rcx+18h]
0x14000fc95  jmp     short loc_14000FCBE
0x14000fc97  mov     [rsp+0D8h+Priority], 40000010h; Priority
0x14000fc9f  xor     r9d, r9d; RequestedAddress
0x14000fca2  xor     edx, edx; AccessMode
0x14000fca4  mov     [rsp+0D8h+BugCheckOnFailure], r12d; BugCheckOnFailure
0x14000fca9  mov     r8d, 1; CacheType
0x14000fcaf  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14000fcb6  nop     dword ptr [rax+rax+00h]
0x14000fcbb  mov     rbx, rax
0x14000fcbe  mov     r8d, [rdi+34h]; Length
0x14000fcc2  mov     rcx, rbx; Source1
0x14000fcc5  mov     rdx, [rdi+70h]; Source2
0x14000fcc9  call    cs:__imp_RtlCompareMemory
0x14000fcd0  nop     dword ptr [rax+rax+00h]
0x14000fcd5  mov     ecx, [rdi+34h]
0x14000fcd8  cmp     eax, ecx
0x14000fcda  jnz     short loc_14000FCF5
0x14000fcdc  mov     r8d, ecx; Size
0x14000fcdf  mov     dword ptr [rdi+3Ch], 1
0x14000fce6  lea     rdx, [rcx+rbx]; Src
0x14000fcea  mov     rcx, [rdi+70h]; void *
0x14000fcee  call    memmove
0x14000fcf3  jmp     short loc_14000FD26
0x14000fcf5  mov     [rdi+38h], eax
0x14000fcf8  mov     dword ptr [rdi+30h], 0C0000001h
0x14000fcff  jmp     short loc_14000FD80
0x14000fd01  bt      eax, 0Dh
0x14000fd05  jnb     short loc_14000FD80
0x14000fd07  mov     eax, [rcx+34h]
0x14000fd0a  add     [rcx+7Ch], eax
0x14000fd0d  mov     rax, [rdi+48h]
0x14000fd11  mov     ecx, [rcx+7Ch]
0x14000fd14  mov     rax, [rax]
0x14000fd17  test    rax, rax
0x14000fd1a  jz      short loc_14000FD67
0x14000fd1c  mov     [rdi+48h], rax
0x14000fd20  mov     eax, [rax+28h]
0x14000fd23  mov     [rdi+34h], eax
0x14000fd26  lea     rax, [rsp+0D8h+var_88]
0x14000fd2b  mov     qword ptr [rdi+28h], 1
0x14000fd33  mov     qword ptr [rsp+0D8h+var_88+8], rax
0x14000fd38  lea     rdx, [rsp+0D8h+var_88]
0x14000fd3d  lea     rax, [rsp+0D8h+var_88]
0x14000fd42  mov     dword ptr [rdi+30h], 103h
0x14000fd49  mov     rcx, rdi
0x14000fd4c  mov     qword ptr [rsp+0D8h+var_88], rax
0x14000fd51  call    VhdmpiSrbExtensionEnqueueForProcessing
0x14000fd56  xor     edx, edx
0x14000fd58  lea     rcx, [rsp+0D8h+var_88]
0x14000fd5d  call    VhdmpiProcessParseThreadContext
0x14000fd62  jmp     loc_1400102EF
0x14000fd67  mov     rax, [rdi+68h]
0x14000fd6b  mov     [rdi+48h], rax
0x14000fd6f  mov     eax, [rdi+78h]
0x14000fd72  mov     [rdi+34h], eax
0x14000fd75  mov     [rdi+78h], r12
0x14000fd79  mov     [rdi+68h], r12
0x14000fd7d  mov     [rdi+38h], ecx
0x14000fd80  cmp     [rdi+68h], r12
0x14000fd84  jz      short loc_14000FDA2
0x14000fd86  mov     rcx, [rdi+48h]; Mdl
0x14000fd8a  call    cs:__imp_IoFreeMdl
0x14000fd91  nop     dword ptr [rax+rax+00h]
0x14000fd96  mov     rax, [rdi+68h]
0x14000fd9a  mov     [rdi+48h], rax
0x14000fd9e  mov     [rdi+68h], r12
0x14000fda2  mov     rcx, [rdi+70h]; P
0x14000fda6  test    rcx, rcx
0x14000fda9  jz      short loc_14000FDC0
0x14000fdab  mov     edx, 5A444856h; Tag
0x14000fdb0  call    cs:__imp_ExFreePoolWithTag
0x14000fdb7  nop     dword ptr [rax+rax+00h]
0x14000fdbc  mov     [rdi+70h], r12
0x14000fdc0  mov     eax, [rdi+30h]
0x14000fdc3  cmp     eax, 103h
0x14000fdc8  jnz     short loc_14000FDCE
0x14000fdca  mov     [rdi+30h], r12d
0x14000fdce  mov     ebx, [rdi+30h]
0x14000fdd1  mov     eax, cs:dword_140087708
0x14000fdd7  cmp     eax, 5
0x14000fdda  jbe     short loc_14000FE2B
0x14000fddc  mov     rcx, cs:qword_140087720
0x14000fde3  mov     rax, cs:qword_140087718
0x14000fdea  test    al, 8
0x14000fdec  jz      short loc_14000FE2B
0x14000fdee  mov     rax, rcx
0x14000fdf1  and     eax, 8
0x14000fdf4  cmp     rax, rcx
0x14000fdf7  jnz     short loc_14000FE2B
0x14000fdf9  mov     dword ptr [rsp+0D8h+var_A8], ebx
0x14000fdfd  lea     rax, aVhdmpicomplete_8; "VhdmpiCompleteParserRequest: SrbExtensi"...
0x14000fe04  mov     qword ptr [rsp+0D8h+Priority], rdi; char
0x14000fe09  lea     rcx, aVhdmpicomplete_17; "VhdmpiCompleteParserRequest"
0x14000fe10  mov     edx, 0B50h; int
0x14000fe15  mov     qword ptr [rsp+0D8h+BugCheckOnFailure], rax; char *
0x14000fe1a  mov     r9d, 8; int
0x14000fe20  mov     r8d, 5; int
0x14000fe26  call    TraceEvents
0x14000fe2b  test    ebx, ebx
0x14000fe2d  jns     loc_14000FFA5
0x14000fe33  cmp     ebp, 3
0x14000fe36  jz      short loc_14000FE53
0x14000fe38  cmp     ebx, 0C000007Fh
0x14000fe3e  jz      short loc_14000FE86
0x14000fe40  mov     eax, [rdi+3Ch]
0x14000fe43  sub     eax, 4
0x14000fe46  cmp     eax, 3
0x14000fe49  jbe     short loc_14000FE53
0x14000fe4b  mov     rcx, rdi; struct _VHD_SRB_EXTENSION *
0x14000fe4e  call    ?VhdmpiCreateErrorLogEntry@@YAXPEAU_VHD_SRB_EXTENSION@@@Z; VhdmpiCreateErrorLogEntry(_VHD_SRB_EXTENSION *)
0x14000fe53  cmp     ebx, 0C000009Ah
0x14000fe59  jz      short loc_14000FE6B
0x14000fe5b  cmp     ebx, 0C0000017h
0x14000fe61  jz      short loc_14000FE6B
0x14000fe63  cmp     ebx, 0C00000A1h
0x14000fe69  jnz     short loc_14000FE86
0x14000fe6b  mov     eax, [rdi+40h]
0x14000fe6e  test    al, 20h
0x14000fe70  jnz     short loc_14000FE86
0x14000fe72  mov     eax, [rdi+3Ch]
0x14000fe75  dec     eax
0x14000fe77  cmp     eax, 2
0x14000fe7a  ja      short loc_14000FE86
0x14000fe7c  mov     dword ptr [rdi+118h], 1
0x14000fe86  cmp     dword ptr [rdi+118h], 1
0x14000fe8d  jnz     loc_14000FF47
0x14000fe93  mov     eax, [rdi+40h]
0x14000fe96  test    al, 20h
0x14000fe98  jnz     loc_14000FF47
0x14000fe9e  mov     rcx, [rdi+8]
0x14000fea2  mov     rax, [rdi]
0x14000fea5  cmp     [rcx+470h], rax
0x14000feac  jnz     loc_14000FF47
0x14000feb2  mov     qword ptr [rdi+28h], 1
0x14000feba  mov     dword ptr [rdi+30h], 103h
0x14000fec1  mov     dword ptr [rdi+118h], 2
0x14000fecb  mov     eax, cs:dword_140087708
0x14000fed1  cmp     eax, 5
0x14000fed4  jbe     short loc_14000FF33
0x14000fed6  mov     rcx, cs:qword_140087720
0x14000fedd  mov     rax, cs:qword_140087718
0x14000fee4  test    al, 8
0x14000fee6  jz      short loc_14000FF33
0x14000fee8  mov     rax, rcx
0x14000feeb  and     eax, 8
0x14000feee  cmp     rax, rcx
0x14000fef1  jnz     short loc_14000FF33
0x14000fef3  mov     eax, [rdi+34h]
0x14000fef6  lea     rcx, aVhdmpicomplete_17; "VhdmpiCompleteParserRequest"
0x14000fefd  mov     [rsp+0D8h+var_98], eax
0x14000ff01  mov     edx, 0B89h; int
0x14000ff06  mov     eax, [rdi+3Ch]
0x14000ff09  mov     r9d, 8; int
0x14000ff0f  mov     [rsp+0D8h+var_A0], eax
0x14000ff13  mov     r8d, 5; int
0x14000ff19  mov     dword ptr [rsp+0D8h+var_A8], ebx
0x14000ff1d  lea     rax, aVhdmpicomplete_5; "VhdmpiCompleteParserRequest: SRB issued"...
0x14000ff24  mov     qword ptr [rsp+0D8h+Priority], rdi; char
0x14000ff29  mov     qword ptr [rsp+0D8h+BugCheckOnFailure], rax; char *
0x14000ff2e  call    TraceEvents
0x14000ff33  lea     rcx, [rsi+388h]; struct VHD_LOW_RESOURCES_QUEUE *
0x14000ff3a  mov     rdx, rdi; struct _VHD_SRB_EXTENSION *
0x14000ff3d  call    ?VhdmpiIssueSrbExtensionOnLowResourcesQueue@@YAXPEAUVHD_LOW_RESOURCES_QUEUE@@PEAU_VHD_SRB_EXTENSION@@@Z; VhdmpiIssueSrbExtensionOnLowResourcesQueue(VHD_LOW_RESOURCES_QUEUE *,_VHD_SRB_EXTENSION *)
0x14000ff42  jmp     loc_1400102EF
0x14000ff47  cmp     [rsi+3F0h], r12
0x14000ff4e  jz      short loc_14000FF6D
0x14000ff50  cmp     [rsi+408h], r12b
0x14000ff57  jz      short loc_14000FF6D
0x14000ff59  mov     eax, [rdi+3Ch]
0x14000ff5c  dec     eax
0x14000ff5e  cmp     eax, 2
0x14000ff61  ja      short loc_14000FF6D
0x14000ff63  mov     edx, ebx
0x14000ff65  mov     rcx, rsi
0x14000ff68  call    VhdmpiAccumulateMirrorStatus
0x14000ff6d  lea     eax, [rbp-2]
0x14000ff70  cmp     eax, 1
0x14000ff73  jbe     short loc_14000FFA5
0x14000ff75  mov     eax, [rdi+3Ch]
0x14000ff78  sub     eax, 4
0x14000ff7b  cmp     eax, 1
0x14000ff7e  jbe     short loc_14000FFA5
0x14000ff80  mov     ecx, [rsi+740h]
0x14000ff86  test    ecx, ecx
0x14000ff88  jz      short loc_14000FFA5
0x14000ff8a  sub     ecx, 1
0x14000ff8d  jz      short loc_14000FF94
0x14000ff8f  sub     ecx, 1
0x14000ff92  jmp     short loc_14000FFA5
0x14000ff94  mov     r8d, [rdi+0E0h]
0x14000ff9b  mov     edx, ebx
0x14000ff9d  mov     rcx, rsi
0x14000ffa0  call    VhdmpiCTLogFailChangeTracking
0x14000ffa5  cmp     [rdi+160h], r12b
0x14000ffac  jz      short loc_14000FFC1
0x14000ffae  lea     rcx, [rsi+180h]; RunRef
0x14000ffb5  lea     rdx, [rdi+120h]
0x14000ffbc  call    VhdmpiProcessEventComplete
0x14000ffc1  mov     edx, [rsi+860h]
0x14000ffc7  test    dl, 8
0x14000ffca  jz      loc_1400101A7
0x14000ffd0  mov     rcx, rsi
0x14000ffd3  call    VhdmpiIsCTLogTrackingEnabled
0x14000ffd8  test    al, al
0x14000ffda  jz      loc_1400101A7
0x14000ffe0  cmp     dword ptr [rdi+3Ch], 1
0x14000ffe4  jnz     loc_1400101A7
0x14000ffea  mov     eax, [rdi+44h]
0x14000ffed  sub     eax, 2
0x14000fff0  cmp     eax, 1
0x14000fff3  jbe     loc_1400101A7
0x14000fff9  test    dl, 40h
0x14000fffc  jnz     loc_1400101A7
0x140010002  cmp     [rdi+114h], r12d
0x140010009  jz      loc_1400101A7
0x14001000f  test    dword ptr [rdi+40h], 800h
0x140010016  jnz     short loc_140010051
0x140010018  mov     rcx, [rdi+48h]; MemoryDescriptorList
0x14001001c  test    byte ptr [rcx+0Ah], 5
0x140010020  jz      short loc_14001002B
0x140010022  mov     rax, [rcx+18h]
0x140010026  jmp     loc_1400100C7
0x14001002b  mov     [rsp+0D8h+Priority], 0C0000010h; Priority
0x140010033  xor     r9d, r9d; RequestedAddress
0x140010036  xor     edx, edx; AccessMode
0x140010038  mov     [rsp+0D8h+BugCheckOnFailure], r12d; BugCheckOnFailure
0x14001003d  mov     r8d, 1; CacheType
0x140010043  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14001004a  nop     dword ptr [rax+rax+00h]
0x14001004f  jmp     short loc_1400100C7
0x140010051  lea     rax, [rsp+0D8h+arg_0]
0x140010059  mov     edx, 68444856h
0x14001005e  lea     r9, [rsp+0D8h+MemoryDescriptorList]
0x140010066  mov     qword ptr [rsp+0D8h+BugCheckOnFailure], rax
0x14001006b  lea     r8, [rsp+0D8h+arg_8]
0x140010073  mov     rcx, rdi
0x140010076  call    VhdmpiExtendDataBuffer
0x14001007b  mov     r14, [rsp+0D8h+MemoryDescriptorList]
0x140010083  test    eax, eax
0x140010085  js      loc_140010172
0x14001008b  test    byte ptr [r14+0Ah], 5
0x140010090  jz      short loc_140010098
0x140010092  mov     rax, [r14+18h]
0x140010096  jmp     short loc_1400100BF
0x140010098  mov     [rsp+0D8h+Priority], 0C0000010h; Priority
0x1400100a0  xor     r9d, r9d; RequestedAddress
0x1400100a3  xor     edx, edx; AccessMode
0x1400100a5  mov     [rsp+0D8h+BugCheckOnFailure], r12d; BugCheckOnFailure
0x1400100aa  mov     r8d, 1; CacheType
0x1400100b0  mov     rcx, r14; MemoryDescriptorList
0x1400100b3  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x1400100ba  nop     dword ptr [rax+rax+00h]
0x1400100bf  mov     r15, [rsp+0D8h+arg_8]
0x1400100c7  test    rax, rax
0x1400100ca  jz      loc_14001017A
  ... truncated ...
```
