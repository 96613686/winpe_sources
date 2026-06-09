# VhdmpiQueueIoRequest

- ea: `0x14000e680`
- end: `0x14000ecd7`
- name: `VhdmpiQueueIoRequest`
- size: `1623`
- prototype: `__int64 __usercall@<rax>(char@<cl>, struct _VHD_SRB_EXTENSION *@<rdx>, int, char)`
- caller_count: `5`
- callee_count: `10`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x14000d080`
- `0x14000d920`
- `0x14000dd50`
- `0x140010f50`
- `0x1400b6b5c`

## callees

- `0x14000e680`
- `0x140014660`
- `0x140015b10`
- `0x1400197f4`
- `0x14001bc30`
- `0x140023940`
- `0x140025718`
- `0x140033bdc`
- `0x140035e94`
- `0x14005d840`

## import_xrefs

- `ntoskrnl!IoFreeMdl` at `0x14000ec71`
- `ntoskrnl!IoFreeMdl` at `0x14000ec71`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14000ebc8`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14000ec32`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14000ebc8`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14000ec32`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14000eb42`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14000eb42`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000ec8a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000ec8a`
- `ntoskrnl!ExAcquireRundownProtection` at `0x14000ea8f`
- `ntoskrnl!ExAcquireRundownProtection` at `0x14000eb13`
- `ntoskrnl!ExAcquireRundownProtection` at `0x14000ea8f`
- `ntoskrnl!ExAcquireRundownProtection` at `0x14000eb13`
- `ntoskrnl!EtwActivityIdControl` at `0x14000e851`
- `ntoskrnl!EtwActivityIdControl` at `0x14000e851`

## string_xrefs

- `0x14000ea61`: `Command out of range (%I64u / %u)`
- `0x14000e9cd`: `Ignoring flush request on virtual disk %p due to cache settings.`
- `0x14000eac7`: `Failed to reference an active surface for write`
- `0x14000e6e6`: `enter... SrbExtension=0x%p VirtualDisk=0x%p IoType=%d`

## pseudocode

```c
__int64 __fastcall VhdmpiQueueIoRequest(__int64 a1, struct _VHD_SRB_EXTENSION *a2, unsigned int a3, __int64 a4, int a5)
{
  int v5; // esi
  struct _MDL *v6; // rbp
  __int64 v9; // r12
  char *v11; // rcx
  __int64 v12; // rdx
  unsigned int v13; // eax
  int v14; // esi
  void *v15; // r15
  _DWORD *v16; // rbx
  unsigned __int64 v17; // rbx
  unsigned __int64 v19; // r12
  unsigned __int64 v20; // rax
  int v21; // ecx
  int v22; // ecx
  struct _EX_RUNDOWN_REF *v23; // rbx
  ULONG_PTR Count; // rdx
  __int64 v25; // rcx
  PVOID MappedSystemVa; // rax
  int v27; // eax
  void *v28; // [rsp+B0h] [rbp+8h] BYREF
  PMDL MemoryDescriptorList; // [rsp+B8h] [rbp+10h] BYREF
  char v30; // [rsp+C0h] [rbp+18h] BYREF
  __int64 v31; // [rsp+C8h] [rbp+20h]

  v5 = a5;
  v6 = 0;
  v30 = 0;
  v9 = a3;
  v28 = 0;
  MemoryDescriptorList = 0;
  if ( (unsigned int)dword_140087708 > 5 && (qword_140087718 & 8) != 0 && (qword_140087720 & 8) == qword_140087720 )
    TraceEvents(
      "VhdmpiQueueIoRequest",
      0x644u,
      5u,
      8u,
      "enter... SrbExtension=0x%p VirtualDisk=0x%p IoType=%d",
      a2,
      (const void *)a1,
      a5);
  *(_QWORD *)a2 = a1;
  *((_DWORD *)a2 + 15) = v5;
  *((_DWORD *)a2 + 13) = v9;
  *((_QWORD *)a2 + 4) = a4;
  if ( v5 == 3 )
  {
    v11 = (char *)a2 + 288;
    *((_OWORD *)a2 + 18) = 0;
    v12 = -1;
    *((_OWORD *)a2 + 19) = 0;
    a4 = -1;
    *((_OWORD *)a2 + 20) = 0;
    *((_QWORD *)a2 + 42) = 0;
    v13 = 2;
  }
  else
  {
    switch ( v5 )
    {
      case 1:
      case 2:
        v13 = (*((_DWORD *)a2 + 16) & 0x1000 | 0x400u) >> 10;
        v11 = (char *)a2 + 288;
        *((_OWORD *)a2 + 18) = 0;
        *((_OWORD *)a2 + 19) = 0;
        *((_OWORD *)a2 + 20) = 0;
        *((_QWORD *)a2 + 42) = 0;
        v12 = a4 + v9;
        break;
      default:
        __fastfail(0x25u);
    }
  }
  v31 = 24;
  *((_QWORD *)v11 + 3) = a4;
  *((_QWORD *)v11 + 4) = v12;
  v14 = a5;
  *((_QWORD *)v11 + 5) = v12;
  *((_DWORD *)v11 + 14) = v13;
  *((_DWORD *)v11 + 17) = 0;
  *((_DWORD *)v11 + 18) = 0;
  v11[64] = 0;
  v11[65] = 0;
  v15 = 0;
  if ( (Microsoft_Windows_VHDMPEnableBits & 0x100) != 0 )
  {
    if ( !*((_BYTE *)a2 + 272) )
    {
      EtwActivityIdControl(3u, (LPGUID)a2 + 16);
      *((_BYTE *)a2 + 272) = 1;
    }
    if ( (Microsoft_Windows_VHDMPEnableBits & 0x100) != 0 )
      McTemplateK0zqqxqq_EtwWriteTransfer(
        *(_QWORD *)(*(_QWORD *)a2 + 144LL),
        (unsigned int)VHD_START_IO,
        (_DWORD)a2 + 256,
        *(_QWORD *)(*(_QWORD *)(*(_QWORD *)a2 + 144LL) + 120LL),
        *((_DWORD *)a2 + 15),
        *((_DWORD *)a2 + 17),
        *((_QWORD *)a2 + 4),
        *((_DWORD *)a2 + 13),
        *((_DWORD *)a2 + 12));
  }
  if ( (unsigned int)(v14 - 1) > 1 && (unsigned int)(v14 - 4) > 3 )
  {
    v16 = (_DWORD *)((char *)a2 + 64);
    goto LABEL_28;
  }
  v17 = *((unsigned int *)a2 + 13);
  if ( !(_DWORD)v17 )
  {
    if ( (unsigned int)(v14 - 4) <= 3 )
      return 3221225473LL;
    return 0;
  }
  v19 = *((_QWORD *)a2 + 4);
  v20 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)a2 + 1) + 160LL))(*((_QWORD *)a2 + 1));
  if ( v20 >= v19 && v20 - v19 >= v17 )
  {
    v16 = (_DWORD *)((char *)a2 + 64);
    goto LABEL_23;
  }
  v16 = (_DWORD *)((char *)a2 + 64);
  if ( (*((_DWORD *)a2 + 16) & 0x40) != 0 )
  {
LABEL_23:
    if ( (unsigned int)(v14 - 1) <= 1 )
    {
      if ( ((*(_BYTE *)(*((_QWORD *)a2 + 9) + 32LL) + (unsigned __int8)*(_DWORD *)(*((_QWORD *)a2 + 9) + 44LL)) & 1) != 0 )
        return 3221225488LL;
      if ( v14 == 1 )
        goto LABEL_30;
    }
    if ( v14 == 4 || v14 == 7 )
    {
LABEL_30:
      if ( (*v16 & 1) != 0 )
      {
        v21 = *(_DWORD *)(*(_QWORD *)(a1 + 200) + 60LL);
        if ( v21 )
        {
          v22 = v21 - 1;
          if ( v22 )
          {
            if ( (unsigned int)(v22 - 1) < 2 )
            {
              *v16 |= 2u;
            }
            else
            {
              *v16 &= ~2u;
              *v16 &= ~4u;
              if ( v14 == 3 )
              {
                if ( (unsigned int)dword_140087708 > 5
                  && (qword_140087718 & 0x20) != 0
                  && (qword_140087720 & 0x20) == qword_140087720 )
                {
                  TraceEvents(
                    "VhdmpiQueueIoRequest",
                    0x6ECu,
                    5u,
                    0x20u,
                    "Ignoring flush request on virtual disk %p due to cache settings.",
                    (const void *)a1);
                }
                return 0;
              }
            }
          }
          else
          {
            *v16 |= 4u;
          }
        }
        if ( !ExAcquireRundownProtection((PEX_RUNDOWN_REF)(*(_QWORD *)(a1 + 200) + 80LL)) )
        {
          if ( (unsigned int)dword_140087708 > 2
            && (qword_140087718 & 0x20) != 0
            && (qword_140087720 & 0x20) == qword_140087720 )
          {
            TraceEvents("VhdmpiQueueIoRequest", 0x6FFu, 2u, 0x20u, "Failed to reference an active surface for write");
          }
          return 3221225488LL;
        }
      }
      *v16 |= 8u;
LABEL_55:
      v23 = *(struct _EX_RUNDOWN_REF **)(*(_QWORD *)a2 + 200LL);
      if ( v23 && ExAcquireRundownProtection(v23 + 194) )
      {
        Count = v23[191].Count;
        if ( *(_BYTE *)(Count + 172) )
          VhdmpiRecordForPrefetchWorker(a2, (struct _VHD_PREFETCH_STATE *)Count);
        ExReleaseRundownProtection(v23 + 194);
      }
      *((_DWORD *)a2 + 12) = 259;
      *((_DWORD *)a2 + 69) = 0;
      if ( (*(_DWORD *)(a1 + 2144) & 8) == 0
        || !(unsigned __int8)VhdmpiIsCTLogTrackingEnabled(a1)
        || *((_DWORD *)a2 + 15) != 1
        || (unsigned int)(*((_DWORD *)a2 + 17) - 2) <= 1 )
      {
        goto LABEL_80;
      }
      if ( (*((_DWORD *)a2 + 16) & 0x800) != 0 )
      {
        v27 = VhdmpiExtendDataBuffer(a2, 1749305430, &v28, &MemoryDescriptorList, &v30);
        v6 = MemoryDescriptorList;
        if ( v27 < 0 )
        {
          v15 = v28;
LABEL_76:
          if ( v6 )
            IoFreeMdl(v6);
          if ( v15 )
            ExFreePoolWithTag(v15, 0x68444856u);
LABEL_80:
          if ( !(unsigned __int8)VhdmpiProcessEventInsert(
                                   (struct _VHD_IO_TRACKER *)(a1 + 384),
                                   (struct _VHD_SRB_EXTENSION *)((char *)a2 + 288)) )
            return 259;
          VhdmpiReleaseParserRequestResources(a2);
          return *((unsigned int *)a2 + 12);
        }
        if ( (MemoryDescriptorList->MdlFlags & 5) != 0 )
          MappedSystemVa = MemoryDescriptorList->MappedSystemVa;
        else
          MappedSystemVa = MmMapLockedPagesSpecifyCache(MemoryDescriptorList, 0, MmCached, 0, 0, 0xC0000010);
        v15 = v28;
      }
      else
      {
        v25 = *((_QWORD *)a2 + 9);
        if ( (*(_BYTE *)(v25 + 10) & 5) != 0 )
          MappedSystemVa = *(PVOID *)(v25 + 24);
        else
          MappedSystemVa = MmMapLockedPagesSpecifyCache((PMDL)v25, 0, MmCached, 0, 0, 0xC0000010);
      }
      if ( MappedSystemVa )
        *((_DWORD *)a2 + 69) = VhdmpiCalculateChecksum(MappedSystemVa, *((unsigned int *)a2 + 13), 0);
      goto LABEL_76;
    }
LABEL_28:
    if ( v14 != 3 && v14 != 8 )
      goto LABEL_55;
    goto LABEL_30;
  }
  if ( (unsigned int)dword_140087708 > 2 && (qword_140087718 & 0x20) != 0 && (qword_140087720 & 0x20) == qword_140087720 )
    TraceEvents(
      "VhdmpiQueueIoRequest",
      0x6A7u,
      2u,
      0x20u,
      "Command out of range (%I64u / %u)",
      *((_QWORD *)a2 + 4),
      *((_DWORD *)a2 + 13));
  return 3221225861LL;
}

```

## disassembly

```asm
0x14000e680  mov     r11, rsp
0x14000e683  push    rbx
0x14000e684  push    rbp
0x14000e685  push    rsi
0x14000e686  push    rdi
0x14000e687  push    r12
0x14000e689  push    r14
0x14000e68b  push    r15
0x14000e68d  sub     rsp, 70h
0x14000e691  mov     esi, [rsp+0A8h+arg_20]
0x14000e698  xor     r15d, r15d
0x14000e69b  xor     ebp, ebp
0x14000e69d  mov     byte ptr [r11+18h], 0
0x14000e6a2  mov     [r11-50h], r15
0x14000e6a6  mov     rbx, r9
0x14000e6a9  mov     eax, cs:dword_140087708
0x14000e6af  mov     rdi, rdx
0x14000e6b2  mov     r12d, r8d
0x14000e6b5  mov     r14, rcx
0x14000e6b8  mov     [r11+8], r15
0x14000e6bc  mov     [r11+10h], rbp
0x14000e6c0  cmp     eax, 5
0x14000e6c3  jbe     short loc_14000E717
0x14000e6c5  mov     rcx, cs:qword_140087720
0x14000e6cc  mov     rax, cs:qword_140087718
0x14000e6d3  test    al, 8
0x14000e6d5  jz      short loc_14000E717
0x14000e6d7  mov     rax, rcx
0x14000e6da  and     eax, 8
0x14000e6dd  cmp     rax, rcx
0x14000e6e0  jnz     short loc_14000E717
0x14000e6e2  mov     [rsp+0A8h+var_70], esi
0x14000e6e6  lea     rax, aEnterSrbextens; "enter... SrbExtension=0x%p VirtualDisk="...
0x14000e6ed  mov     [r11-78h], r14
0x14000e6f1  lea     rcx, aVhdmpiqueueior; "VhdmpiQueueIoRequest"
0x14000e6f8  mov     [r11-80h], rdi
0x14000e6fc  mov     edx, 644h; int
0x14000e701  mov     r9d, 8; int
0x14000e707  mov     qword ptr [rsp+0A8h+BugCheckOnFailure], rax; char *
0x14000e70c  mov     r8d, 5; int
0x14000e712  call    TraceEvents
0x14000e717  mov     [rsp+0A8h+var_40], r13
0x14000e71c  mov     [rdi], r14
0x14000e71f  mov     [rdi+3Ch], esi
0x14000e722  mov     [rdi+34h], r12d
0x14000e726  mov     [rdi+20h], rbx
0x14000e72a  cmp     esi, 3
0x14000e72d  jnz     short loc_14000E75B
0x14000e72f  lea     rcx, [rdi+120h]
0x14000e736  xorps   xmm0, xmm0
0x14000e739  movups  xmmword ptr [rcx], xmm0
0x14000e73c  xor     eax, eax
0x14000e73e  mov     rdx, 0FFFFFFFFFFFFFFFFh
0x14000e745  movups  xmmword ptr [rcx+10h], xmm0
0x14000e749  mov     rbx, rdx
0x14000e74c  movups  xmmword ptr [rcx+20h], xmm0
0x14000e750  mov     [rcx+30h], rax
0x14000e754  mov     eax, 2
0x14000e759  jmp     short loc_14000E7BC
0x14000e75b  lea     eax, [rsi-1]; switch 2 cases
0x14000e75e  cmp     eax, 0Ah
0x14000e761  ja      def_14000E77A; jumptable 000000014000E77A default case
0x14000e767  lea     rdx, cs:140000000h
0x14000e76e  cdqe
0x14000e770  mov     ecx, ds:(jpt_14000E77A - 140000000h)[rdx+rax*4]
0x14000e777  add     rcx, rdx
0x14000e77a  jmp     rcx; switch jump
0x14000e780  mov     eax, 4
0x14000e785  jmp     short loc_14000E79D
0x14000e787  mov     eax, [rdi+40h]; jumptable 000000014000E77A cases 1,2
0x14000e78a  and     eax, 1000h
0x14000e78f  bts     eax, 0Ah
0x14000e793  shr     eax, 0Ah
0x14000e796  jmp     short loc_14000E79D
0x14000e798  mov     eax, 6
0x14000e79d  lea     rcx, [rdi+120h]
0x14000e7a4  xorps   xmm0, xmm0
0x14000e7a7  movups  xmmword ptr [rcx], xmm0
0x14000e7aa  xor     edx, edx
0x14000e7ac  movups  xmmword ptr [rcx+10h], xmm0
0x14000e7b0  movups  xmmword ptr [rcx+20h], xmm0
0x14000e7b4  mov     [rcx+30h], rdx
0x14000e7b8  lea     rdx, [rbx+r12]
0x14000e7bc  xor     r8d, r8d
0x14000e7bf  mov     [rsp+0A8h+arg_18], 18h
0x14000e7cb  mov     rsi, [rsp+0A8h+arg_18]
0x14000e7d3  mov     r13d, 38h ; '8'
0x14000e7d9  mov     [rsp+0A8h+var_58], 28h ; '('
0x14000e7e2  mov     r12d, 44h ; 'D'
0x14000e7e8  mov     r11d, 48h ; 'H'
0x14000e7ee  mov     r10d, 40h ; '@'
0x14000e7f4  mov     r9d, 41h ; 'A'
0x14000e7fa  mov     [rsi+rcx], rbx
0x14000e7fe  mov     esi, 20h ; ' '
0x14000e803  mov     rbx, [rsp+0A8h+var_58]
0x14000e808  mov     [rsi+rcx], rdx
0x14000e80c  mov     esi, [rsp+0A8h+arg_20]
0x14000e813  mov     [rbx+rcx], rdx
0x14000e817  mov     [rcx+r13], eax
0x14000e81b  mov     [rcx+r12], r8d
0x14000e81f  mov     [rcx+r11], r8d
0x14000e823  mov     [r10+rcx], bpl
0x14000e827  mov     [rcx+r9], bpl
0x14000e82b  test    byte ptr cs:Microsoft_Windows_VHDMPEnableBits+1, 1
0x14000e832  mov     r15, [rsp+0A8h+P]
0x14000e837  jz      short loc_14000E8B1
0x14000e839  lea     r12, [rdi+100h]
0x14000e840  cmp     [rdi+110h], bpl
0x14000e847  jnz     short loc_14000E864
0x14000e849  mov     rdx, r12; ActivityId
0x14000e84c  mov     ecx, 3; ControlCode
0x14000e851  call    cs:__imp_EtwActivityIdControl
0x14000e858  nop     dword ptr [rax+rax+00h]
0x14000e85d  mov     byte ptr [rdi+110h], 1
0x14000e864  test    byte ptr cs:Microsoft_Windows_VHDMPEnableBits+1, 1
0x14000e86b  jz      short loc_14000E8B1
0x14000e86d  mov     rax, [rdi]
0x14000e870  mov     r8, r12
0x14000e873  mov     edx, [rdi+34h]
0x14000e876  mov     r10, [rdi+20h]
0x14000e87a  mov     r11d, [rdi+44h]
0x14000e87e  mov     rcx, [rax+90h]
0x14000e885  mov     eax, [rdi+30h]
0x14000e888  mov     ebx, [rdi+3Ch]
0x14000e88b  mov     [rsp+0A8h+var_68], eax
0x14000e88f  mov     r9, [rcx+78h]
0x14000e893  mov     [rsp+0A8h+var_70], edx
0x14000e897  lea     rdx, VHD_START_IO
0x14000e89e  mov     [rsp+0A8h+var_78], r10
0x14000e8a3  mov     [rsp+0A8h+Priority], r11d; char
0x14000e8a8  mov     [rsp+0A8h+BugCheckOnFailure], ebx
0x14000e8ac  call    McTemplateK0zqqxqq_EtwWriteTransfer
0x14000e8b1  lea     eax, [rsi-1]
0x14000e8b4  cmp     eax, 1
0x14000e8b7  jbe     short loc_14000E8CA
0x14000e8b9  lea     eax, [rsi-4]
0x14000e8bc  cmp     eax, 3
0x14000e8bf  jbe     short loc_14000E8CA
0x14000e8c1  lea     rbx, [rdi+40h]
0x14000e8c5  jmp     loc_14000E951
0x14000e8ca  mov     ebx, [rdi+34h]
0x14000e8cd  test    ebx, ebx
0x14000e8cf  jnz     short loc_14000E8F7
0x14000e8d1  lea     eax, [rsi-4]
0x14000e8d4  cmp     eax, 3
0x14000e8d7  ja      loc_14000E9FB
0x14000e8dd  mov     eax, 0C0000001h
0x14000e8e2  mov     r13, [rsp+0A8h+var_40]
0x14000e8e7  add     rsp, 70h
0x14000e8eb  pop     r15
0x14000e8ed  pop     r14
0x14000e8ef  pop     r12
0x14000e8f1  pop     rdi
0x14000e8f2  pop     rsi
0x14000e8f3  pop     rbp
0x14000e8f4  pop     rbx
0x14000e8f5  retn
0x14000e8f7  mov     rcx, [rdi+8]
0x14000e8fb  mov     r12, [rdi+20h]
0x14000e8ff  mov     rax, [rcx]
0x14000e902  mov     rax, [rax+0A0h]
0x14000e909  call    _guard_dispatch_icall
0x14000e90e  cmp     rax, r12
0x14000e911  jb      loc_14000EA02
0x14000e917  sub     rax, r12
0x14000e91a  cmp     rax, rbx
0x14000e91d  jb      loc_14000EA02
0x14000e923  lea     rbx, [rdi+40h]
0x14000e927  lea     eax, [rsi-1]
0x14000e92a  cmp     eax, 1
0x14000e92d  ja      short loc_14000E947
0x14000e92f  mov     rax, [rdi+48h]
0x14000e933  mov     ecx, [rax+2Ch]
0x14000e936  add     cl, [rax+20h]
0x14000e939  test    cl, 1
0x14000e93c  jnz     loc_14000EAF0
0x14000e942  cmp     esi, 1
0x14000e945  jz      short loc_14000E95F
0x14000e947  cmp     esi, 4
0x14000e94a  jz      short loc_14000E95F
0x14000e94c  cmp     esi, 7
0x14000e94f  jz      short loc_14000E95F
0x14000e951  cmp     esi, 3
0x14000e954  jz      short loc_14000E95F
0x14000e956  cmp     esi, 8
0x14000e959  jnz     loc_14000EAFD
0x14000e95f  mov     eax, [rbx]
0x14000e961  test    al, 1
0x14000e963  jz      loc_14000EAFA
0x14000e969  mov     rax, [r14+0C8h]
0x14000e970  mov     ecx, [rax+3Ch]
0x14000e973  test    ecx, ecx
0x14000e975  jz      loc_14000EA84
0x14000e97b  sub     ecx, 1
0x14000e97e  jz      loc_14000EA81
0x14000e984  sub     ecx, 1
0x14000e987  jz      loc_14000EA7C
0x14000e98d  cmp     ecx, 1
0x14000e990  jz      loc_14000EA7C
0x14000e996  and     dword ptr [rbx], 0FFFFFFFDh
0x14000e999  and     dword ptr [rbx], 0FFFFFFFBh
0x14000e99c  cmp     esi, 3
0x14000e99f  jnz     loc_14000EA84
0x14000e9a5  mov     eax, cs:dword_140087708
0x14000e9ab  cmp     eax, 5
0x14000e9ae  jbe     short loc_14000E9FB
0x14000e9b0  mov     rcx, cs:qword_140087720
0x14000e9b7  mov     rax, cs:qword_140087718
0x14000e9be  test    al, 20h
0x14000e9c0  jz      short loc_14000E9FB
0x14000e9c2  mov     rax, rcx
0x14000e9c5  and     eax, 20h
0x14000e9c8  cmp     rax, rcx
0x14000e9cb  jnz     short loc_14000E9FB
0x14000e9cd  lea     rax, aIgnoringFlushR; "Ignoring flush request on virtual disk "...
0x14000e9d4  mov     qword ptr [rsp+0A8h+Priority], r14; char
0x14000e9d9  mov     edx, 6ECh; int
0x14000e9de  mov     qword ptr [rsp+0A8h+BugCheckOnFailure], rax; char *
0x14000e9e3  mov     r9d, 20h ; ' '; int
0x14000e9e9  lea     rcx, aVhdmpiqueueior; "VhdmpiQueueIoRequest"
0x14000e9f0  mov     r8d, 5; int
0x14000e9f6  call    TraceEvents
0x14000e9fb  xor     eax, eax
0x14000e9fd  jmp     loc_14000E8E2
0x14000ea02  mov     eax, [rdi+40h]
0x14000ea05  lea     rbx, [rdi+40h]
0x14000ea09  test    al, 40h
0x14000ea0b  jnz     loc_14000E927
0x14000ea11  mov     eax, cs:dword_140087708
0x14000ea17  cmp     eax, 2
0x14000ea1a  jbe     short loc_14000EA72
0x14000ea1c  mov     rdx, cs:qword_140087720
0x14000ea23  mov     rax, cs:qword_140087718
0x14000ea2a  test    al, 20h
0x14000ea2c  jz      short loc_14000EA72
0x14000ea2e  mov     rax, rdx
0x14000ea31  and     eax, 20h
0x14000ea34  cmp     rax, rdx
0x14000ea37  jnz     short loc_14000EA72
0x14000ea39  mov     eax, [rdi+34h]
0x14000ea3c  lea     rcx, aVhdmpiqueueior; "VhdmpiQueueIoRequest"
0x14000ea43  mov     dword ptr [rsp+0A8h+var_78], eax
0x14000ea47  mov     edx, 6A7h; int
0x14000ea4c  mov     rax, [rdi+20h]
0x14000ea50  mov     r9d, 20h ; ' '; int
0x14000ea56  mov     qword ptr [rsp+0A8h+Priority], rax; char
0x14000ea5b  mov     r8d, 2; int
0x14000ea61  lea     rax, aCommandOutOfRa; "Command out of range (%I64u / %u)"
0x14000ea68  mov     qword ptr [rsp+0A8h+BugCheckOnFailure], rax; char *
0x14000ea6d  call    TraceEvents
0x14000ea72  mov     eax, 0C0000185h
0x14000ea77  jmp     loc_14000E8E2
0x14000ea7c  or      dword ptr [rbx], 2
0x14000ea7f  jmp     short loc_14000EA84
0x14000ea81  or      dword ptr [rbx], 4
0x14000ea84  mov     rcx, [r14+0C8h]
0x14000ea8b  add     rcx, 50h ; 'P'; RunRef
0x14000ea8f  call    cs:__imp_ExAcquireRundownProtection
0x14000ea96  nop     dword ptr [rax+rax+00h]
0x14000ea9b  test    al, al
0x14000ea9d  jnz     short loc_14000EAFA
0x14000ea9f  mov     eax, cs:dword_140087708
0x14000eaa5  cmp     eax, 2
0x14000eaa8  jbe     short loc_14000EAF0
0x14000eaaa  mov     rcx, cs:qword_140087720
0x14000eab1  mov     rax, cs:qword_140087718
0x14000eab8  test    al, 20h
0x14000eaba  jz      short loc_14000EAF0
0x14000eabc  mov     rax, rcx
0x14000eabf  and     eax, 20h
0x14000eac2  cmp     rax, rcx
0x14000eac5  jnz     short loc_14000EAF0
0x14000eac7  lea     rax, aFailedToRefere; "Failed to reference an active surface f"...
0x14000eace  mov     edx, 6FFh; int
0x14000ead3  mov     r9d, 20h ; ' '; int
0x14000ead9  mov     qword ptr [rsp+0A8h+BugCheckOnFailure], rax; char *
0x14000eade  mov     r8d, 2; int
0x14000eae4  lea     rcx, aVhdmpiqueueior; "VhdmpiQueueIoRequest"
0x14000eaeb  call    TraceEvents
0x14000eaf0  mov     eax, 0C0000010h
0x14000eaf5  jmp     loc_14000E8E2
0x14000eafa  or      dword ptr [rbx], 8
0x14000eafd  mov     rax, [rdi]
0x14000eb00  mov     rbx, [rax+0C8h]
0x14000eb07  test    rbx, rbx
0x14000eb0a  jz      short loc_14000EB4E
0x14000eb0c  lea     rcx, [rbx+610h]; RunRef
0x14000eb13  call    cs:__imp_ExAcquireRundownProtection
0x14000eb1a  nop     dword ptr [rax+rax+00h]
0x14000eb1f  test    al, al
0x14000eb21  jz      short loc_14000EB4E
0x14000eb23  mov     rdx, [rbx+5F8h]; struct _VHD_PREFETCH_STATE *
0x14000eb2a  cmp     [rdx+0ACh], bpl
0x14000eb31  jz      short loc_14000EB3B
0x14000eb33  mov     rcx, rdi; struct _VHD_SRB_EXTENSION *
0x14000eb36  call    ?VhdmpiRecordForPrefetchWorker@@YAXPEAU_VHD_SRB_EXTENSION@@PEAU_VHD_PREFETCH_STATE@@@Z; VhdmpiRecordForPrefetchWorker(_VHD_SRB_EXTENSION *,_VHD_PREFETCH_STATE *)
0x14000eb3b  lea     rcx, [rbx+610h]; RunRef
0x14000eb42  call    cs:__imp_ExReleaseRundownProtection
0x14000eb49  nop     dword ptr [rax+rax+00h]
0x14000eb4e  xor     ebx, ebx
  ... truncated ...
```
