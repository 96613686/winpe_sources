# VhdmpiQueueIoRequest

- ea: `0x14000ec80`
- end: `0x14000f2d7`
- name: `VhdmpiQueueIoRequest`
- size: `1623`
- prototype: `__int64 __usercall@<rax>(char@<cl>, struct _VHD_SRB_EXTENSION *@<rdx>, int, char)`
- caller_count: `6`
- callee_count: `10`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x14000d680`
- `0x14000df20`
- `0x14000e350`
- `0x14000f670`
- `0x140012280`
- `0x1400b6b5c`

## callees

- `0x14000ec80`
- `0x140014b00`
- `0x140015fb0`
- `0x140019c14`
- `0x14001c050`
- `0x140023d60`
- `0x140025b38`
- `0x14003409c`
- `0x140036284`
- `0x14005dc30`

## import_xrefs

- `ntoskrnl!IoFreeMdl` at `0x14000f271`
- `ntoskrnl!IoFreeMdl` at `0x14000f271`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14000f1c8`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14000f232`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14000f1c8`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14000f232`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14000f142`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14000f142`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f28a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f28a`
- `ntoskrnl!ExAcquireRundownProtection` at `0x14000f08f`
- `ntoskrnl!ExAcquireRundownProtection` at `0x14000f113`
- `ntoskrnl!ExAcquireRundownProtection` at `0x14000f08f`
- `ntoskrnl!ExAcquireRundownProtection` at `0x14000f113`
- `ntoskrnl!EtwActivityIdControl` at `0x14000ee51`
- `ntoskrnl!EtwActivityIdControl` at `0x14000ee51`

## string_xrefs

- `0x14000efcd`: `Ignoring flush request on virtual disk %p due to cache settings.`
- `0x14000f0c7`: `Failed to reference an active surface for write`
- `0x14000ece6`: `enter... SrbExtension=0x%p VirtualDisk=0x%p IoType=%d`
- `0x14000f061`: `Command out of range (%I64u / %u)`

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
  if ( (unsigned int)dword_1400876D0 > 5 && (qword_1400876E0 & 8) != 0 && (qword_1400876E8 & 8) == qword_1400876E8 )
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
                if ( (unsigned int)dword_1400876D0 > 5
                  && (qword_1400876E0 & 0x20) != 0
                  && (qword_1400876E8 & 0x20) == qword_1400876E8 )
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
          if ( (unsigned int)dword_1400876D0 > 2
            && (qword_1400876E0 & 0x20) != 0
            && (qword_1400876E8 & 0x20) == qword_1400876E8 )
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
  if ( (unsigned int)dword_1400876D0 > 2 && (qword_1400876E0 & 0x20) != 0 && (qword_1400876E8 & 0x20) == qword_1400876E8 )
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
0x14000ec80  mov     r11, rsp
0x14000ec83  push    rbx
0x14000ec84  push    rbp
0x14000ec85  push    rsi
0x14000ec86  push    rdi
0x14000ec87  push    r12
0x14000ec89  push    r14
0x14000ec8b  push    r15
0x14000ec8d  sub     rsp, 70h
0x14000ec91  mov     esi, [rsp+0A8h+arg_20]
0x14000ec98  xor     r15d, r15d
0x14000ec9b  xor     ebp, ebp
0x14000ec9d  mov     byte ptr [r11+18h], 0
0x14000eca2  mov     [r11-50h], r15
0x14000eca6  mov     rbx, r9
0x14000eca9  mov     eax, cs:dword_1400876D0
0x14000ecaf  mov     rdi, rdx
0x14000ecb2  mov     r12d, r8d
0x14000ecb5  mov     r14, rcx
0x14000ecb8  mov     [r11+8], r15
0x14000ecbc  mov     [r11+10h], rbp
0x14000ecc0  cmp     eax, 5
0x14000ecc3  jbe     short loc_14000ED17
0x14000ecc5  mov     rcx, cs:qword_1400876E8
0x14000eccc  mov     rax, cs:qword_1400876E0
0x14000ecd3  test    al, 8
0x14000ecd5  jz      short loc_14000ED17
0x14000ecd7  mov     rax, rcx
0x14000ecda  and     eax, 8
0x14000ecdd  cmp     rax, rcx
0x14000ece0  jnz     short loc_14000ED17
0x14000ece2  mov     [rsp+0A8h+var_70], esi
0x14000ece6  lea     rax, aEnterSrbextens; "enter... SrbExtension=0x%p VirtualDisk="...
0x14000eced  mov     [r11-78h], r14
0x14000ecf1  lea     rcx, aVhdmpiqueueior; "VhdmpiQueueIoRequest"
0x14000ecf8  mov     [r11-80h], rdi
0x14000ecfc  mov     edx, 644h; int
0x14000ed01  mov     r9d, 8; int
0x14000ed07  mov     qword ptr [rsp+0A8h+BugCheckOnFailure], rax; char *
0x14000ed0c  mov     r8d, 5; int
0x14000ed12  call    TraceEvents
0x14000ed17  mov     [rsp+0A8h+var_40], r13
0x14000ed1c  mov     [rdi], r14
0x14000ed1f  mov     [rdi+3Ch], esi
0x14000ed22  mov     [rdi+34h], r12d
0x14000ed26  mov     [rdi+20h], rbx
0x14000ed2a  cmp     esi, 3
0x14000ed2d  jnz     short loc_14000ED5B
0x14000ed2f  lea     rcx, [rdi+120h]
0x14000ed36  xorps   xmm0, xmm0
0x14000ed39  movups  xmmword ptr [rcx], xmm0
0x14000ed3c  xor     eax, eax
0x14000ed3e  mov     rdx, 0FFFFFFFFFFFFFFFFh
0x14000ed45  movups  xmmword ptr [rcx+10h], xmm0
0x14000ed49  mov     rbx, rdx
0x14000ed4c  movups  xmmword ptr [rcx+20h], xmm0
0x14000ed50  mov     [rcx+30h], rax
0x14000ed54  mov     eax, 2
0x14000ed59  jmp     short loc_14000EDBC
0x14000ed5b  lea     eax, [rsi-1]; switch 2 cases
0x14000ed5e  cmp     eax, 0Ah
0x14000ed61  ja      def_14000ED7A; jumptable 000000014000ED7A default case
0x14000ed67  lea     rdx, cs:140000000h
0x14000ed6e  cdqe
0x14000ed70  mov     ecx, ds:(jpt_14000ED7A - 140000000h)[rdx+rax*4]
0x14000ed77  add     rcx, rdx
0x14000ed7a  jmp     rcx; switch jump
0x14000ed80  mov     eax, 4
0x14000ed85  jmp     short loc_14000ED9D
0x14000ed87  mov     eax, [rdi+40h]; jumptable 000000014000ED7A cases 1,2
0x14000ed8a  and     eax, 1000h
0x14000ed8f  bts     eax, 0Ah
0x14000ed93  shr     eax, 0Ah
0x14000ed96  jmp     short loc_14000ED9D
0x14000ed98  mov     eax, 6
0x14000ed9d  lea     rcx, [rdi+120h]
0x14000eda4  xorps   xmm0, xmm0
0x14000eda7  movups  xmmword ptr [rcx], xmm0
0x14000edaa  xor     edx, edx
0x14000edac  movups  xmmword ptr [rcx+10h], xmm0
0x14000edb0  movups  xmmword ptr [rcx+20h], xmm0
0x14000edb4  mov     [rcx+30h], rdx
0x14000edb8  lea     rdx, [rbx+r12]
0x14000edbc  xor     r8d, r8d
0x14000edbf  mov     [rsp+0A8h+arg_18], 18h
0x14000edcb  mov     rsi, [rsp+0A8h+arg_18]
0x14000edd3  mov     r13d, 38h ; '8'
0x14000edd9  mov     [rsp+0A8h+var_58], 28h ; '('
0x14000ede2  mov     r12d, 44h ; 'D'
0x14000ede8  mov     r11d, 48h ; 'H'
0x14000edee  mov     r10d, 40h ; '@'
0x14000edf4  mov     r9d, 41h ; 'A'
0x14000edfa  mov     [rsi+rcx], rbx
0x14000edfe  mov     esi, 20h ; ' '
0x14000ee03  mov     rbx, [rsp+0A8h+var_58]
0x14000ee08  mov     [rsi+rcx], rdx
0x14000ee0c  mov     esi, [rsp+0A8h+arg_20]
0x14000ee13  mov     [rbx+rcx], rdx
0x14000ee17  mov     [rcx+r13], eax
0x14000ee1b  mov     [rcx+r12], r8d
0x14000ee1f  mov     [rcx+r11], r8d
0x14000ee23  mov     [r10+rcx], bpl
0x14000ee27  mov     [rcx+r9], bpl
0x14000ee2b  test    byte ptr cs:Microsoft_Windows_VHDMPEnableBits+1, 1
0x14000ee32  mov     r15, [rsp+0A8h+P]
0x14000ee37  jz      short loc_14000EEB1
0x14000ee39  lea     r12, [rdi+100h]
0x14000ee40  cmp     [rdi+110h], bpl
0x14000ee47  jnz     short loc_14000EE64
0x14000ee49  mov     rdx, r12; ActivityId
0x14000ee4c  mov     ecx, 3; ControlCode
0x14000ee51  call    cs:__imp_EtwActivityIdControl
0x14000ee58  nop     dword ptr [rax+rax+00h]
0x14000ee5d  mov     byte ptr [rdi+110h], 1
0x14000ee64  test    byte ptr cs:Microsoft_Windows_VHDMPEnableBits+1, 1
0x14000ee6b  jz      short loc_14000EEB1
0x14000ee6d  mov     rax, [rdi]
0x14000ee70  mov     r8, r12
0x14000ee73  mov     edx, [rdi+34h]
0x14000ee76  mov     r10, [rdi+20h]
0x14000ee7a  mov     r11d, [rdi+44h]
0x14000ee7e  mov     rcx, [rax+90h]
0x14000ee85  mov     eax, [rdi+30h]
0x14000ee88  mov     ebx, [rdi+3Ch]
0x14000ee8b  mov     [rsp+0A8h+var_68], eax
0x14000ee8f  mov     r9, [rcx+78h]
0x14000ee93  mov     [rsp+0A8h+var_70], edx
0x14000ee97  lea     rdx, VHD_START_IO
0x14000ee9e  mov     [rsp+0A8h+var_78], r10
0x14000eea3  mov     [rsp+0A8h+Priority], r11d; char
0x14000eea8  mov     [rsp+0A8h+BugCheckOnFailure], ebx
0x14000eeac  call    McTemplateK0zqqxqq_EtwWriteTransfer
0x14000eeb1  lea     eax, [rsi-1]
0x14000eeb4  cmp     eax, 1
0x14000eeb7  jbe     short loc_14000EECA
0x14000eeb9  lea     eax, [rsi-4]
0x14000eebc  cmp     eax, 3
0x14000eebf  jbe     short loc_14000EECA
0x14000eec1  lea     rbx, [rdi+40h]
0x14000eec5  jmp     loc_14000EF51
0x14000eeca  mov     ebx, [rdi+34h]
0x14000eecd  test    ebx, ebx
0x14000eecf  jnz     short loc_14000EEF7
0x14000eed1  lea     eax, [rsi-4]
0x14000eed4  cmp     eax, 3
0x14000eed7  ja      loc_14000EFFB
0x14000eedd  mov     eax, 0C0000001h
0x14000eee2  mov     r13, [rsp+0A8h+var_40]
0x14000eee7  add     rsp, 70h
0x14000eeeb  pop     r15
0x14000eeed  pop     r14
0x14000eeef  pop     r12
0x14000eef1  pop     rdi
0x14000eef2  pop     rsi
0x14000eef3  pop     rbp
0x14000eef4  pop     rbx
0x14000eef5  retn
0x14000eef7  mov     rcx, [rdi+8]
0x14000eefb  mov     r12, [rdi+20h]
0x14000eeff  mov     rax, [rcx]
0x14000ef02  mov     rax, [rax+0A0h]
0x14000ef09  call    _guard_dispatch_icall
0x14000ef0e  cmp     rax, r12
0x14000ef11  jb      loc_14000F002
0x14000ef17  sub     rax, r12
0x14000ef1a  cmp     rax, rbx
0x14000ef1d  jb      loc_14000F002
0x14000ef23  lea     rbx, [rdi+40h]
0x14000ef27  lea     eax, [rsi-1]
0x14000ef2a  cmp     eax, 1
0x14000ef2d  ja      short loc_14000EF47
0x14000ef2f  mov     rax, [rdi+48h]
0x14000ef33  mov     ecx, [rax+2Ch]
0x14000ef36  add     cl, [rax+20h]
0x14000ef39  test    cl, 1
0x14000ef3c  jnz     loc_14000F0F0
0x14000ef42  cmp     esi, 1
0x14000ef45  jz      short loc_14000EF5F
0x14000ef47  cmp     esi, 4
0x14000ef4a  jz      short loc_14000EF5F
0x14000ef4c  cmp     esi, 7
0x14000ef4f  jz      short loc_14000EF5F
0x14000ef51  cmp     esi, 3
0x14000ef54  jz      short loc_14000EF5F
0x14000ef56  cmp     esi, 8
0x14000ef59  jnz     loc_14000F0FD
0x14000ef5f  mov     eax, [rbx]
0x14000ef61  test    al, 1
0x14000ef63  jz      loc_14000F0FA
0x14000ef69  mov     rax, [r14+0C8h]
0x14000ef70  mov     ecx, [rax+3Ch]
0x14000ef73  test    ecx, ecx
0x14000ef75  jz      loc_14000F084
0x14000ef7b  sub     ecx, 1
0x14000ef7e  jz      loc_14000F081
0x14000ef84  sub     ecx, 1
0x14000ef87  jz      loc_14000F07C
0x14000ef8d  cmp     ecx, 1
0x14000ef90  jz      loc_14000F07C
0x14000ef96  and     dword ptr [rbx], 0FFFFFFFDh
0x14000ef99  and     dword ptr [rbx], 0FFFFFFFBh
0x14000ef9c  cmp     esi, 3
0x14000ef9f  jnz     loc_14000F084
0x14000efa5  mov     eax, cs:dword_1400876D0
0x14000efab  cmp     eax, 5
0x14000efae  jbe     short loc_14000EFFB
0x14000efb0  mov     rcx, cs:qword_1400876E8
0x14000efb7  mov     rax, cs:qword_1400876E0
0x14000efbe  test    al, 20h
0x14000efc0  jz      short loc_14000EFFB
0x14000efc2  mov     rax, rcx
0x14000efc5  and     eax, 20h
0x14000efc8  cmp     rax, rcx
0x14000efcb  jnz     short loc_14000EFFB
0x14000efcd  lea     rax, aIgnoringFlushR; "Ignoring flush request on virtual disk "...
0x14000efd4  mov     qword ptr [rsp+0A8h+Priority], r14; char
0x14000efd9  mov     edx, 6ECh; int
0x14000efde  mov     qword ptr [rsp+0A8h+BugCheckOnFailure], rax; char *
0x14000efe3  mov     r9d, 20h ; ' '; int
0x14000efe9  lea     rcx, aVhdmpiqueueior; "VhdmpiQueueIoRequest"
0x14000eff0  mov     r8d, 5; int
0x14000eff6  call    TraceEvents
0x14000effb  xor     eax, eax
0x14000effd  jmp     loc_14000EEE2
0x14000f002  mov     eax, [rdi+40h]
0x14000f005  lea     rbx, [rdi+40h]
0x14000f009  test    al, 40h
0x14000f00b  jnz     loc_14000EF27
0x14000f011  mov     eax, cs:dword_1400876D0
0x14000f017  cmp     eax, 2
0x14000f01a  jbe     short loc_14000F072
0x14000f01c  mov     rdx, cs:qword_1400876E8
0x14000f023  mov     rax, cs:qword_1400876E0
0x14000f02a  test    al, 20h
0x14000f02c  jz      short loc_14000F072
0x14000f02e  mov     rax, rdx
0x14000f031  and     eax, 20h
0x14000f034  cmp     rax, rdx
0x14000f037  jnz     short loc_14000F072
0x14000f039  mov     eax, [rdi+34h]
0x14000f03c  lea     rcx, aVhdmpiqueueior; "VhdmpiQueueIoRequest"
0x14000f043  mov     dword ptr [rsp+0A8h+var_78], eax
0x14000f047  mov     edx, 6A7h; int
0x14000f04c  mov     rax, [rdi+20h]
0x14000f050  mov     r9d, 20h ; ' '; int
0x14000f056  mov     qword ptr [rsp+0A8h+Priority], rax; char
0x14000f05b  mov     r8d, 2; int
0x14000f061  lea     rax, aCommandOutOfRa; "Command out of range (%I64u / %u)"
0x14000f068  mov     qword ptr [rsp+0A8h+BugCheckOnFailure], rax; char *
0x14000f06d  call    TraceEvents
0x14000f072  mov     eax, 0C0000185h
0x14000f077  jmp     loc_14000EEE2
0x14000f07c  or      dword ptr [rbx], 2
0x14000f07f  jmp     short loc_14000F084
0x14000f081  or      dword ptr [rbx], 4
0x14000f084  mov     rcx, [r14+0C8h]
0x14000f08b  add     rcx, 50h ; 'P'; RunRef
0x14000f08f  call    cs:__imp_ExAcquireRundownProtection
0x14000f096  nop     dword ptr [rax+rax+00h]
0x14000f09b  test    al, al
0x14000f09d  jnz     short loc_14000F0FA
0x14000f09f  mov     eax, cs:dword_1400876D0
0x14000f0a5  cmp     eax, 2
0x14000f0a8  jbe     short loc_14000F0F0
0x14000f0aa  mov     rcx, cs:qword_1400876E8
0x14000f0b1  mov     rax, cs:qword_1400876E0
0x14000f0b8  test    al, 20h
0x14000f0ba  jz      short loc_14000F0F0
0x14000f0bc  mov     rax, rcx
0x14000f0bf  and     eax, 20h
0x14000f0c2  cmp     rax, rcx
0x14000f0c5  jnz     short loc_14000F0F0
0x14000f0c7  lea     rax, aFailedToRefere; "Failed to reference an active surface f"...
0x14000f0ce  mov     edx, 6FFh; int
0x14000f0d3  mov     r9d, 20h ; ' '; int
0x14000f0d9  mov     qword ptr [rsp+0A8h+BugCheckOnFailure], rax; char *
0x14000f0de  mov     r8d, 2; int
0x14000f0e4  lea     rcx, aVhdmpiqueueior; "VhdmpiQueueIoRequest"
0x14000f0eb  call    TraceEvents
0x14000f0f0  mov     eax, 0C0000010h
0x14000f0f5  jmp     loc_14000EEE2
0x14000f0fa  or      dword ptr [rbx], 8
0x14000f0fd  mov     rax, [rdi]
0x14000f100  mov     rbx, [rax+0C8h]
0x14000f107  test    rbx, rbx
0x14000f10a  jz      short loc_14000F14E
0x14000f10c  lea     rcx, [rbx+610h]; RunRef
0x14000f113  call    cs:__imp_ExAcquireRundownProtection
0x14000f11a  nop     dword ptr [rax+rax+00h]
0x14000f11f  test    al, al
0x14000f121  jz      short loc_14000F14E
0x14000f123  mov     rdx, [rbx+5F8h]; struct _VHD_PREFETCH_STATE *
0x14000f12a  cmp     [rdx+0ACh], bpl
0x14000f131  jz      short loc_14000F13B
0x14000f133  mov     rcx, rdi; struct _VHD_SRB_EXTENSION *
0x14000f136  call    ?VhdmpiRecordForPrefetchWorker@@YAXPEAU_VHD_SRB_EXTENSION@@PEAU_VHD_PREFETCH_STATE@@@Z; VhdmpiRecordForPrefetchWorker(_VHD_SRB_EXTENSION *,_VHD_PREFETCH_STATE *)
0x14000f13b  lea     rcx, [rbx+610h]; RunRef
0x14000f142  call    cs:__imp_ExReleaseRundownProtection
0x14000f149  nop     dword ptr [rax+rax+00h]
0x14000f14e  xor     ebx, ebx
  ... truncated ...
```
