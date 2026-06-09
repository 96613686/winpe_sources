# VhdmpiCompleteParserRequest

- ea: `0x140010fa0`
- end: `0x140011631`
- name: `VhdmpiCompleteParserRequest`
- size: `1681`
- prototype: `__int64 __fastcall(struct _VHD_SRB_EXTENSION *)`
- caller_count: `1`
- callee_count: `18`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140010f40`

## callees

- `0x14000f670`
- `0x140010a10`
- `0x140010fa0`
- `0x140011e90`
- `0x1400149f0`
- `0x140014b00`
- `0x140015ba0`
- `0x14001c050`
- `0x140023d60`
- `0x140025b38`
- `0x14002a550`
- `0x14002a8b0`
- `0x140032268`
- `0x140033910`
- `0x140036284`
- `0x140041338`
- `0x14005dc30`
- `0x14005de00`

## import_xrefs

- `ntoskrnl!IoFreeMdl` at `0x140011149`
- `ntoskrnl!IoFreeMdl` at `0x140011549`
- `ntoskrnl!IoFreeMdl` at `0x140011149`
- `ntoskrnl!IoFreeMdl` at `0x140011549`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14001105c`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14001140b`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14001147a`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14001105c`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14001140b`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14001147a`
- `ntoskrnl!RtlCompareMemory` at `0x140011076`
- `ntoskrnl!RtlCompareMemory` at `0x140011076`
- `ntoskrnl!ExReleaseRundownProtection` at `0x1400115db`
- `ntoskrnl!ExReleaseRundownProtection` at `0x1400115db`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001116f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140011562`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001116f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140011562`

## string_xrefs

- `0x1400114fe`: `VhdmpiCompleteParserRequest: checksum mismatch at disk offset 0x%I64x  for virtual disk 0x%I64u`
- `0x1400112dd`: `VhdmpiCompleteParserRequest: SRB issued on low resources queue -> SrbExtension=0x%p, Status=0x%08x, Op=%d, Length=%lu`
- `0x1400111c8`: `VhdmpiCompleteParserRequest`
- `0x1400112b6`: `VhdmpiCompleteParserRequest`
- `0x1400114e2`: `VhdmpiCompleteParserRequest`
- `0x1400111bc`: `VhdmpiCompleteParserRequest: SrbExtension=0x%p IrpStatus=0x%08x`

## pseudocode

```c
void __fastcall VhdmpiCompleteParserRequest(struct _VHD_SRB_EXTENSION *a1)
{
  __int64 v1; // rdi
  int v2; // r15d
  struct _MDL *v3; // rbp
  void *v5; // r14
  int v6; // eax
  bool v7; // zf
  __int64 v8; // rcx
  char *v9; // rsi
  int v10; // eax
  __int64 v11; // rcx
  int v12; // ecx
  __int64 v13; // rax
  __int64 v14; // rcx
  int v15; // esi
  int v16; // ecx
  char v17; // dl
  PVOID MappedSystemVa; // rax
  int v19; // eax
  int v20; // edx
  int v21; // r8d
  int v22; // r9d
  _OWORD v23[4]; // [rsp+50h] [rbp-48h] BYREF
  char v24; // [rsp+A0h] [rbp+8h] BYREF
  void *v25; // [rsp+A8h] [rbp+10h] BYREF
  PMDL MemoryDescriptorList; // [rsp+B0h] [rbp+18h] BYREF

  v1 = *(_QWORD *)a1;
  v2 = *((_DWORD *)a1 + 17);
  v3 = 0;
  v24 = 0;
  v23[0] = 0;
  v25 = 0;
  MemoryDescriptorList = 0;
  v5 = 0;
  v6 = *((_DWORD *)a1 + 16);
  if ( (v6 & 0x800) != 0 )
  {
    if ( *((_DWORD *)a1 + 15) == 4 && *((int *)a1 + 12) < 0 )
    {
      *((_DWORD *)a1 + 16) &= ~0x100u;
      *((_DWORD *)a1 + 15) = 1;
      *((_QWORD *)a1 + 29) = 0;
LABEL_17:
      *((_QWORD *)a1 + 5) = 1;
      *((_QWORD *)&v23[0] + 1) = v23;
      *((_DWORD *)a1 + 12) = 259;
      *(_QWORD *)&v23[0] = v23;
      VhdmpiSrbExtensionEnqueueForProcessing(a1, v23);
      VhdmpiProcessParseThreadContext(v23, 0);
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
  if ( (unsigned int)dword_1400876D0 > 5 )
  {
    LODWORD(v14) = qword_1400876E8;
    if ( (qword_1400876E0 & 8) != 0 && (qword_1400876E8 & 8) == qword_1400876E8 )
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
      if ( (unsigned int)dword_1400876D0 > 5 && (qword_1400876E0 & 8) != 0 && (qword_1400876E8 & 8) == qword_1400876E8 )
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
  v19 = VhdmpiExtendDataBuffer(a1, 1749305430, &v25, &MemoryDescriptorList, &v24);
  v3 = MemoryDescriptorList;
  if ( v19 >= 0 )
  {
    if ( (MemoryDescriptorList->MdlFlags & 5) != 0 )
      MappedSystemVa = MemoryDescriptorList->MappedSystemVa;
    else
      MappedSystemVa = MmMapLockedPagesSpecifyCache(MemoryDescriptorList, 0, MmCached, 0, 0, 0xC0000010);
    v5 = v25;
LABEL_75:
    if ( MappedSystemVa
      && *((_DWORD *)a1 + 69) != (unsigned int)VhdmpiCalculateChecksum(MappedSystemVa, *((unsigned int *)a1 + 13), 0) )
    {
      if ( (unsigned int)dword_1400876D0 > 2 )
      {
        LODWORD(v14) = qword_1400876E8;
        if ( (qword_1400876E0 & 0x1000) != 0 && (qword_1400876E8 & 0x1000) == qword_1400876E8 )
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
  v5 = v25;
LABEL_85:
  if ( v3 )
    IoFreeMdl(v3);
  if ( v5 )
    ExFreePoolWithTag(v5, 0x68444856u);
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
    VhdmpiCompleteRequestToScsiParser(a1, *((_DWORD *)a1 + 12));
  }
  else
  {
    VhdmpiReleaseRequestResources(a1);
    (*((void (__fastcall **)(_QWORD, _QWORD))a1 + 11))(*((_QWORD *)a1 + 10), *((unsigned int *)a1 + 12));
  }
}

```

## disassembly

```asm
0x140010fa0  mov     rax, rsp
0x140010fa3  push    rbx
0x140010fa4  push    rbp
0x140010fa5  push    rsi
0x140010fa6  push    rdi
0x140010fa7  push    r12
0x140010fa9  push    r14
0x140010fab  push    r15
0x140010fad  sub     rsp, 60h
0x140010fb1  mov     rdi, [rcx]
0x140010fb4  xor     r12d, r12d
0x140010fb7  mov     r15d, [rcx+44h]
0x140010fbb  mov     ebp, r12d
0x140010fbe  xorps   xmm0, xmm0
0x140010fc1  mov     [rax+8], bpl
0x140010fc5  movups  xmmword ptr [rax-48h], xmm0
0x140010fc9  mov     [rax+10h], r12
0x140010fcd  mov     rbx, rcx
0x140010fd0  mov     [rax+18h], r12
0x140010fd4  mov     r14d, r12d
0x140010fd7  mov     eax, [rcx+40h]
0x140010fda  bt      eax, 0Bh
0x140010fde  jnb     short loc_14001100F
0x140010fe0  cmp     dword ptr [rcx+3Ch], 4
0x140010fe4  jnz     loc_14001113F
0x140010fea  mov     eax, [rcx+30h]
0x140010fed  test    eax, eax
0x140010fef  jns     loc_14001113F
0x140010ff5  and     dword ptr [rcx+40h], 0FFFFFEFFh
0x140010ffc  mov     dword ptr [rcx+3Ch], 1
0x140011003  mov     [rcx+0E8h], r12
0x14001100a  jmp     loc_1400110DA
0x14001100f  bt      eax, 0Ch
0x140011013  jnb     loc_1400110B1
0x140011019  cmp     dword ptr [rcx+3Ch], 2
0x14001101d  mov     eax, [rcx+34h]
0x140011020  mov     [rcx+38h], eax
0x140011023  jnz     loc_14001113F
0x140011029  mov     eax, [rcx+30h]
0x14001102c  test    eax, eax
0x14001102e  js      loc_14001113F
0x140011034  mov     rcx, [rcx+68h]; MemoryDescriptorList
0x140011038  test    byte ptr [rcx+0Ah], 5
0x14001103c  jz      short loc_140011044
0x14001103e  mov     rsi, [rcx+18h]
0x140011042  jmp     short loc_14001106B
0x140011044  mov     [rsp+98h+Priority], 40000010h; Priority
0x14001104c  xor     r9d, r9d; RequestedAddress
0x14001104f  xor     edx, edx; AccessMode
0x140011051  mov     [rsp+98h+BugCheckOnFailure], r12d; BugCheckOnFailure
0x140011056  mov     r8d, 1; CacheType
0x14001105c  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140011063  nop     dword ptr [rax+rax+00h]
0x140011068  mov     rsi, rax
0x14001106b  mov     r8d, [rbx+34h]; Length
0x14001106f  mov     rcx, rsi; Source1
0x140011072  mov     rdx, [rbx+70h]; Source2
0x140011076  call    cs:__imp_RtlCompareMemory
0x14001107d  nop     dword ptr [rax+rax+00h]
0x140011082  mov     ecx, [rbx+34h]
0x140011085  cmp     eax, ecx
0x140011087  jnz     short loc_1400110A2
0x140011089  mov     r8d, ecx; Size
0x14001108c  mov     dword ptr [rbx+3Ch], 1
0x140011093  lea     rdx, [rcx+rsi]; Src
0x140011097  mov     rcx, [rbx+70h]; void *
0x14001109b  call    memmove
0x1400110a0  jmp     short loc_1400110DA
0x1400110a2  mov     [rbx+38h], eax
0x1400110a5  mov     dword ptr [rbx+30h], 0C0000001h
0x1400110ac  jmp     loc_14001113F
0x1400110b1  bt      eax, 0Dh
0x1400110b5  jnb     loc_14001113F
0x1400110bb  mov     eax, [rcx+34h]
0x1400110be  add     [rcx+7Ch], eax
0x1400110c1  mov     rax, [rbx+48h]
0x1400110c5  mov     ecx, [rcx+7Ch]
0x1400110c8  mov     rax, [rax]
0x1400110cb  test    rax, rax
0x1400110ce  jz      short loc_140011126
0x1400110d0  mov     [rbx+48h], rax
0x1400110d4  mov     eax, [rax+28h]
0x1400110d7  mov     [rbx+34h], eax
0x1400110da  lea     rax, [rsp+98h+var_48]
0x1400110df  mov     qword ptr [rbx+28h], 1
0x1400110e7  mov     [rsp+98h+var_40], rax
0x1400110ec  lea     rdx, [rsp+98h+var_48]
0x1400110f1  lea     rax, [rsp+98h+var_48]
0x1400110f6  mov     dword ptr [rbx+30h], 103h
0x1400110fd  mov     rcx, rbx
0x140011100  mov     [rsp+98h+var_48], rax
0x140011105  call    VhdmpiSrbExtensionEnqueueForProcessing
0x14001110a  xor     edx, edx
0x14001110c  lea     rcx, [rsp+98h+var_48]
0x140011111  call    VhdmpiProcessParseThreadContext
0x140011116  add     rsp, 60h
0x14001111a  pop     r15
0x14001111c  pop     r14
0x14001111e  pop     r12
0x140011120  pop     rdi
0x140011121  pop     rsi
0x140011122  pop     rbp
0x140011123  pop     rbx
0x140011124  retn
0x140011126  mov     rax, [rbx+68h]
0x14001112a  mov     [rbx+48h], rax
0x14001112e  mov     eax, [rbx+78h]
0x140011131  mov     [rbx+34h], eax
0x140011134  mov     [rbx+78h], r12
0x140011138  mov     [rbx+68h], r12
0x14001113c  mov     [rbx+38h], ecx
0x14001113f  cmp     [rbx+68h], rbp
0x140011143  jz      short loc_140011161
0x140011145  mov     rcx, [rbx+48h]; Mdl
0x140011149  call    cs:__imp_IoFreeMdl
0x140011150  nop     dword ptr [rax+rax+00h]
0x140011155  mov     rax, [rbx+68h]
0x140011159  mov     [rbx+48h], rax
0x14001115d  mov     [rbx+68h], r12
0x140011161  mov     rcx, [rbx+70h]; P
0x140011165  test    rcx, rcx
0x140011168  jz      short loc_14001117F
0x14001116a  mov     edx, 5A444856h; Tag
0x14001116f  call    cs:__imp_ExFreePoolWithTag
0x140011176  nop     dword ptr [rax+rax+00h]
0x14001117b  mov     [rbx+70h], r12
0x14001117f  mov     eax, [rbx+30h]
0x140011182  cmp     eax, 103h
0x140011187  jnz     short loc_14001118D
0x140011189  mov     [rbx+30h], r12d
0x14001118d  mov     esi, [rbx+30h]
0x140011190  mov     eax, cs:dword_1400876D0
0x140011196  cmp     eax, 5
0x140011199  jbe     short loc_1400111EA
0x14001119b  mov     rcx, cs:qword_1400876E8
0x1400111a2  mov     rax, cs:qword_1400876E0
0x1400111a9  test    al, 8
0x1400111ab  jz      short loc_1400111EA
0x1400111ad  mov     rax, rcx
0x1400111b0  and     eax, 8
0x1400111b3  cmp     rax, rcx
0x1400111b6  jnz     short loc_1400111EA
0x1400111b8  mov     dword ptr [rsp+98h+var_68], esi
0x1400111bc  lea     rax, aVhdmpicomplete_8; "VhdmpiCompleteParserRequest: SrbExtensi"...
0x1400111c3  mov     qword ptr [rsp+98h+Priority], rbx; char
0x1400111c8  lea     rcx, aVhdmpicomplete_17; "VhdmpiCompleteParserRequest"
0x1400111cf  mov     edx, 0B50h; int
0x1400111d4  mov     qword ptr [rsp+98h+BugCheckOnFailure], rax; char *
0x1400111d9  mov     r9d, 8; int
0x1400111df  mov     r8d, 5; int
0x1400111e5  call    TraceEvents
0x1400111ea  test    esi, esi
0x1400111ec  jns     loc_140011371
0x1400111f2  cmp     r15d, 3
0x1400111f6  jz      short loc_140011213
0x1400111f8  cmp     esi, 0C000007Fh
0x1400111fe  jz      short loc_140011246
0x140011200  mov     eax, [rbx+3Ch]
0x140011203  sub     eax, 4
0x140011206  cmp     eax, 3
0x140011209  jbe     short loc_140011213
0x14001120b  mov     rcx, rbx; struct _VHD_SRB_EXTENSION *
0x14001120e  call    ?VhdmpiCreateErrorLogEntry@@YAXPEAU_VHD_SRB_EXTENSION@@@Z; VhdmpiCreateErrorLogEntry(_VHD_SRB_EXTENSION *)
0x140011213  cmp     esi, 0C000009Ah
0x140011219  jz      short loc_14001122B
0x14001121b  cmp     esi, 0C0000017h
0x140011221  jz      short loc_14001122B
0x140011223  cmp     esi, 0C00000A1h
0x140011229  jnz     short loc_140011246
0x14001122b  mov     eax, [rbx+40h]
0x14001122e  test    al, 20h
0x140011230  jnz     short loc_140011246
0x140011232  mov     eax, [rbx+3Ch]
0x140011235  dec     eax
0x140011237  cmp     eax, 2
0x14001123a  ja      short loc_140011246
0x14001123c  mov     dword ptr [rbx+118h], 1
0x140011246  cmp     dword ptr [rbx+118h], 1
0x14001124d  jnz     loc_140011312
0x140011253  mov     eax, [rbx+40h]
0x140011256  test    al, 20h
0x140011258  jnz     loc_140011312
0x14001125e  mov     rcx, [rbx+8]
0x140011262  mov     rax, [rbx]
0x140011265  cmp     [rcx+470h], rax
0x14001126c  jnz     loc_140011312
0x140011272  mov     qword ptr [rbx+28h], 1
0x14001127a  mov     dword ptr [rbx+30h], 103h
0x140011281  mov     dword ptr [rbx+118h], 2
0x14001128b  mov     eax, cs:dword_1400876D0
0x140011291  cmp     eax, 5
0x140011294  jbe     short loc_1400112F3
0x140011296  mov     rcx, cs:qword_1400876E8
0x14001129d  mov     rax, cs:qword_1400876E0
0x1400112a4  test    al, 8
0x1400112a6  jz      short loc_1400112F3
0x1400112a8  mov     rax, rcx
0x1400112ab  and     eax, 8
0x1400112ae  cmp     rax, rcx
0x1400112b1  jnz     short loc_1400112F3
0x1400112b3  mov     eax, [rbx+34h]
0x1400112b6  lea     rcx, aVhdmpicomplete_17; "VhdmpiCompleteParserRequest"
0x1400112bd  mov     [rsp+98h+var_58], eax
0x1400112c1  mov     edx, 0B89h; int
0x1400112c6  mov     eax, [rbx+3Ch]
0x1400112c9  mov     r9d, 8; int
0x1400112cf  mov     [rsp+98h+var_60], eax
0x1400112d3  mov     r8d, 5; int
0x1400112d9  mov     dword ptr [rsp+98h+var_68], esi
0x1400112dd  lea     rax, aVhdmpicomplete_5; "VhdmpiCompleteParserRequest: SRB issued"...
0x1400112e4  mov     qword ptr [rsp+98h+Priority], rbx; char
0x1400112e9  mov     qword ptr [rsp+98h+BugCheckOnFailure], rax; char *
0x1400112ee  call    TraceEvents
0x1400112f3  lea     rcx, [rdi+388h]; struct VHD_LOW_RESOURCES_QUEUE *
0x1400112fa  mov     rdx, rbx; struct _VHD_SRB_EXTENSION *
0x1400112fd  call    ?VhdmpiIssueSrbExtensionOnLowResourcesQueue@@YAXPEAUVHD_LOW_RESOURCES_QUEUE@@PEAU_VHD_SRB_EXTENSION@@@Z; VhdmpiIssueSrbExtensionOnLowResourcesQueue(VHD_LOW_RESOURCES_QUEUE *,_VHD_SRB_EXTENSION *)
0x140011302  add     rsp, 60h
0x140011306  pop     r15
0x140011308  pop     r14
0x14001130a  pop     r12
0x14001130c  pop     rdi
0x14001130d  pop     rsi
0x14001130e  pop     rbp
0x14001130f  pop     rbx
0x140011310  retn
0x140011312  cmp     [rdi+3F0h], rbp
0x140011319  jz      short loc_140011338
0x14001131b  cmp     [rdi+408h], bpl
0x140011322  jz      short loc_140011338
0x140011324  mov     eax, [rbx+3Ch]
0x140011327  dec     eax
0x140011329  cmp     eax, 2
0x14001132c  ja      short loc_140011338
0x14001132e  mov     edx, esi
0x140011330  mov     rcx, rdi
0x140011333  call    VhdmpiAccumulateMirrorStatus
0x140011338  lea     eax, [r15-2]
0x14001133c  cmp     eax, 1
0x14001133f  jbe     short loc_140011371
0x140011341  mov     eax, [rbx+3Ch]
0x140011344  sub     eax, 4
0x140011347  cmp     eax, 1
0x14001134a  jbe     short loc_140011371
0x14001134c  mov     ecx, [rdi+740h]
0x140011352  test    ecx, ecx
0x140011354  jz      short loc_140011371
0x140011356  sub     ecx, 1
0x140011359  jz      short loc_140011360
0x14001135b  sub     ecx, 1
0x14001135e  jmp     short loc_140011371
0x140011360  mov     r8d, [rbx+0E0h]
0x140011367  mov     edx, esi
0x140011369  mov     rcx, rdi
0x14001136c  call    VhdmpiCTLogFailChangeTracking
0x140011371  lea     rdx, [rbx+120h]
0x140011378  cmp     [rdx+40h], bpl
0x14001137c  jz      short loc_14001138A
0x14001137e  lea     rcx, [rdi+180h]; RunRef
0x140011385  call    VhdmpiProcessEventComplete
0x14001138a  mov     edx, [rdi+860h]
0x140011390  test    dl, 8
0x140011393  jz      loc_14001156E
0x140011399  mov     rcx, rdi
0x14001139c  call    VhdmpiIsCTLogTrackingEnabled
0x1400113a1  test    al, al
0x1400113a3  jz      loc_14001156E
0x1400113a9  cmp     dword ptr [rbx+3Ch], 1
0x1400113ad  jnz     loc_14001156E
0x1400113b3  mov     eax, [rbx+44h]
0x1400113b6  sub     eax, 2
0x1400113b9  cmp     eax, 1
0x1400113bc  jbe     loc_14001156E
0x1400113c2  test    dl, 40h
0x1400113c5  jnz     loc_14001156E
0x1400113cb  cmp     [rbx+114h], ebp
0x1400113d1  jz      loc_14001156E
0x1400113d7  test    dword ptr [rbx+40h], 800h
0x1400113de  jnz     short loc_140011419
0x1400113e0  mov     rcx, [rbx+48h]; MemoryDescriptorList
0x1400113e4  test    byte ptr [rcx+0Ah], 5
0x1400113e8  jz      short loc_1400113F3
0x1400113ea  mov     rax, [rcx+18h]
0x1400113ee  jmp     loc_14001148E
0x1400113f3  mov     [rsp+98h+Priority], 0C0000010h; Priority
0x1400113fb  xor     r9d, r9d; RequestedAddress
0x1400113fe  xor     edx, edx; AccessMode
0x140011400  mov     [rsp+98h+BugCheckOnFailure], r12d; BugCheckOnFailure
0x140011405  mov     r8d, 1; CacheType
0x14001140b  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140011412  nop     dword ptr [rax+rax+00h]
0x140011417  jmp     short loc_14001148E
0x140011419  lea     rax, [rsp+98h+arg_0]
0x140011421  mov     edx, 68444856h
0x140011426  lea     r9, [rsp+98h+MemoryDescriptorList]
0x14001142e  mov     qword ptr [rsp+98h+BugCheckOnFailure], rax
0x140011433  lea     r8, [rsp+98h+arg_8]
0x14001143b  mov     rcx, rbx
0x14001143e  call    VhdmpiExtendDataBuffer
0x140011443  mov     rbp, [rsp+98h+MemoryDescriptorList]
0x14001144b  test    eax, eax
  ... truncated ...
```
