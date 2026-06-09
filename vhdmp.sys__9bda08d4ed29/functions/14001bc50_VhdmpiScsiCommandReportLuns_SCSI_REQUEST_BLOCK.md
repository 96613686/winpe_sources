# VhdmpiScsiCommandReportLuns(_SCSI_REQUEST_BLOCK *)

- ea: `0x14001bc50`
- end: `0x14001bf4e`
- name: `?VhdmpiScsiCommandReportLuns@@YAEPEAU_SCSI_REQUEST_BLOCK@@@Z`
- size: `766`
- prototype: `unsigned __int8 __fastcall(struct _SCSI_REQUEST_BLOCK *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140017d40`

## callees

- `0x14001bc50`
- `0x140021d9c`
- `0x140023980`
- `0x140035fac`
- `0x140036284`
- `0x14005e100`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001bd3c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001bd3c`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001bed7`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001bed7`

## string_xrefs

- `0x14001bca5`: `VhdmpiScsiCommandReportLuns: Path=0x%x Target=0x%x Lun=0x%x`
- `0x14001bcb0`: `VhdmpiScsiCommandReportLuns`
- `0x14001bdbf`: `VhdmpiScsiCommandReportLuns`
- `0x14001be33`: `VhdmpiScsiCommandReportLuns`
- `0x14001bf16`: `VhdmpiScsiCommandReportLuns`
- `0x14001bdda`: `VhdmpiScsiCommandReportLuns: Reporting address missing Lun=0x%x Disk=0x%p`
- `0x14001be43`: `VhdmpiScsiCommandReportLuns: Lun=0x%x Surface=0x%p`
- `0x14001bf0b`: `VhdmpiScsiCommandReportLuns: returning 0%x`

## pseudocode

```c
unsigned __int8 __fastcall VhdmpiScsiCommandReportLuns(struct _SCSI_REQUEST_BLOCK *a1)
{
  ULONG DataTransferLength; // eax
  unsigned __int8 v3; // si
  _BYTE *DataBuffer; // r15
  __int64 v5; // r12
  ULONG v6; // ebp
  KIRQL v7; // al
  struct _VHD_ADAPTER_EXTENSION *v8; // r8
  _QWORD *v9; // rdi
  _QWORD *i; // r13
  unsigned int v11; // eax
  _BYTE *v12; // r14
  int v13; // eax
  ULONG NewIrqla; // [rsp+90h] [rbp+8h]
  KIRQL NewIrql; // [rsp+90h] [rbp+8h]

  if ( (unsigned int)dword_1400876D0 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 2) )
    TraceEvents(
      "VhdmpiScsiCommandReportLuns",
      0xB1u,
      5u,
      2u,
      "VhdmpiScsiCommandReportLuns: Path=0x%x Target=0x%x Lun=0x%x",
      a1->PathId,
      a1->TargetId,
      a1->Lun);
  HIBYTE(NewIrqla) = a1->Cdb[6];
  BYTE2(NewIrqla) = a1->Cdb[7];
  BYTE1(NewIrqla) = a1->Cdb[8];
  LOBYTE(NewIrqla) = a1->Cdb[9];
  DataTransferLength = a1->DataTransferLength;
  if ( DataTransferLength < NewIrqla )
  {
    v3 = 4;
LABEL_6:
    a1->DataTransferLength = 0;
    goto LABEL_31;
  }
  if ( DataTransferLength < 0x10 )
  {
    v3 = 18;
    goto LABEL_6;
  }
  DataBuffer = a1->DataBuffer;
  memset(DataBuffer, 0, a1->DataTransferLength);
  v5 = 0;
  v6 = a1->DataTransferLength - 8;
  v7 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)VhdmpAdapterExtension + 6);
  v8 = VhdmpAdapterExtension;
  NewIrql = v7;
  v9 = (_QWORD *)*((_QWORD *)VhdmpAdapterExtension + 4);
  for ( i = (_QWORD *)*v9; v9 != (_QWORD *)((char *)VhdmpAdapterExtension + 32); i = (_QWORD *)*i )
  {
    if ( (v9[7] & 0x610) == 0x10 && *((_BYTE *)v9 + 33) == a1->TargetId && *((_BYTE *)v9 + 32) == a1->PathId )
    {
      if ( v9[2] )
      {
        if ( (unsigned int)dword_1400876D0 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 2) )
        {
          v12 = (char *)v9 + 34;
          TraceEvents(
            "VhdmpiScsiCommandReportLuns",
            0x101u,
            4u,
            2u,
            "VhdmpiScsiCommandReportLuns: Lun=0x%x Surface=0x%p",
            *((unsigned __int8 *)v9 + 34),
            v9);
        }
        else
        {
          v12 = (char *)v9 + 34;
        }
        if ( v6 >= 2 )
        {
          DataBuffer[8 * v5 + 9] = *v12;
          VhdmpiMarkSurfaceAsReported(v9);
          v13 = 8;
          if ( v6 < 8 )
            v13 = v6;
          v6 -= v13;
        }
        v5 = (unsigned int)(v5 + 1);
      }
      else
      {
        if ( (unsigned int)dword_1400876D0 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 16) )
          TraceEvents(
            "VhdmpiScsiCommandReportLuns",
            0xECu,
            4u,
            0x10u,
            "VhdmpiScsiCommandReportLuns: Reporting address missing Lun=0x%x Disk=0x%p",
            *((unsigned __int8 *)v9 + 34),
            v9);
        *((_DWORD *)v9 + 14) &= ~1u;
        v11 = *((_DWORD *)v9 + 125);
        if ( v11 < 3 )
          *((_DWORD *)v9 + 125) = v11 + 1;
        VhdmpiTryRemoveSurfaceFromSurfaceList((char)v9);
      }
    }
    v8 = VhdmpAdapterExtension;
    v9 = i;
  }
  DataBuffer[3] = 8 * v5;
  DataBuffer[2] = (unsigned __int16)v5 >> 5;
  *DataBuffer = (unsigned int)(8 * v5) >> 24;
  DataBuffer[1] = (unsigned int)v5 >> 13;
  KeReleaseSpinLock((PKSPIN_LOCK)v8 + 6, NewIrql);
  a1->DataTransferLength -= v6;
  v3 = 1;
LABEL_31:
  if ( (unsigned int)dword_1400876D0 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 2) )
    TraceEvents("VhdmpiScsiCommandReportLuns", 0x11Eu, 5u, 2u, "VhdmpiScsiCommandReportLuns: returning 0%x", v3);
  return v3;
}

```

## disassembly

```asm
0x14001bc50  push    rbx
0x14001bc52  push    rbp
0x14001bc53  push    rsi
0x14001bc54  push    rdi
0x14001bc55  push    r12
0x14001bc57  push    r13
0x14001bc59  push    r14
0x14001bc5b  push    r15
0x14001bc5d  sub     rsp, 48h
0x14001bc61  mov     eax, cs:dword_1400876D0
0x14001bc67  mov     rbx, rcx
0x14001bc6a  mov     r14d, 2
0x14001bc70  cmp     eax, 5
0x14001bc73  jbe     short loc_14001BCC8
0x14001bc75  mov     edx, r14d
0x14001bc78  lea     rcx, dword_1400876D0
0x14001bc7f  call    _tlgKeywordOn
0x14001bc84  test    al, al
0x14001bc86  jz      short loc_14001BCC8
0x14001bc88  movzx   eax, byte ptr [rbx+7]
0x14001bc8c  lea     r8d, [r14+3]; int
0x14001bc90  movzx   ecx, byte ptr [rbx+6]
0x14001bc94  mov     r10d, 0B1h
0x14001bc9a  movzx   edx, byte ptr [rbx+5]
0x14001bc9e  mov     r9d, r14d; int
0x14001bca1  mov     [rsp+88h+var_50], eax
0x14001bca5  lea     rax, aVhdmpiscsicomm_28; "VhdmpiScsiCommandReportLuns: Path=0x%x "...
0x14001bcac  mov     dword ptr [rsp+88h+var_58], ecx
0x14001bcb0  lea     rcx, aVhdmpiscsicomm_34; "VhdmpiScsiCommandReportLuns"
0x14001bcb7  mov     dword ptr [rsp+88h+var_60], edx; char
0x14001bcbb  mov     edx, r10d; int
0x14001bcbe  mov     [rsp+88h+var_68], rax; char *
0x14001bcc3  call    TraceEvents
0x14001bcc8  mov     al, [rbx+4Eh]
0x14001bccb  mov     [rsp+93h], al
0x14001bcd2  mov     al, [rbx+4Fh]
0x14001bcd5  mov     [rsp+92h], al
0x14001bcdc  mov     al, [rbx+50h]
0x14001bcdf  mov     [rsp+91h], al
0x14001bce6  mov     al, [rbx+51h]
0x14001bce9  mov     [rsp+88h+NewIrql], al
0x14001bcf0  mov     eax, [rbx+10h]
0x14001bcf3  cmp     eax, dword ptr [rsp+88h+NewIrql]
0x14001bcfa  jnb     short loc_14001BD0D
0x14001bcfc  mov     esi, 4
0x14001bd01  mov     dword ptr [rbx+10h], 0
0x14001bd08  jmp     loc_14001BEE9
0x14001bd0d  cmp     eax, 10h
0x14001bd10  jnb     short loc_14001BD17
0x14001bd12  mov     sil, 12h
0x14001bd15  jmp     short loc_14001BD01
0x14001bd17  mov     r15, [rbx+18h]
0x14001bd1b  mov     r8, rax; Size
0x14001bd1e  mov     rcx, r15; void *
0x14001bd21  xor     edx, edx; Val
0x14001bd23  call    memset
0x14001bd28  mov     rcx, cs:VhdmpAdapterExtension
0x14001bd2f  xor     r12d, r12d
0x14001bd32  mov     ebp, [rbx+10h]
0x14001bd35  add     rcx, 30h ; '0'; SpinLock
0x14001bd39  sub     ebp, 8
0x14001bd3c  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14001bd43  nop     dword ptr [rax+rax+00h]
0x14001bd48  mov     r8, cs:VhdmpAdapterExtension
0x14001bd4f  mov     [rsp+88h+NewIrql], al
0x14001bd56  lea     rcx, [r8+20h]
0x14001bd5a  mov     rdi, [rcx]
0x14001bd5d  mov     r13, [rdi]
0x14001bd60  cmp     rdi, rcx
0x14001bd63  jz      loc_14001BEA8
0x14001bd69  lea     esi, [r12+4]
0x14001bd6e  mov     ecx, [rdi+38h]
0x14001bd71  and     ecx, 610h
0x14001bd77  cmp     ecx, 10h
0x14001bd7a  jnz     loc_14001BE8D
0x14001bd80  mov     al, [rbx+6]
0x14001bd83  cmp     [rdi+21h], al
0x14001bd86  jnz     loc_14001BE8D
0x14001bd8c  mov     al, [rbx+5]
0x14001bd8f  cmp     [rdi+20h], al
0x14001bd92  jnz     loc_14001BE8D
0x14001bd98  cmp     qword ptr [rdi+10h], 0
0x14001bd9d  mov     eax, cs:dword_1400876D0
0x14001bda3  jnz     short loc_14001BE0F
0x14001bda5  cmp     eax, esi
0x14001bda7  jbe     short loc_14001BDEE
0x14001bda9  mov     edx, ecx
0x14001bdab  lea     rcx, dword_1400876D0
0x14001bdb2  call    _tlgKeywordOn
0x14001bdb7  test    al, al
0x14001bdb9  jz      short loc_14001BDEE
0x14001bdbb  movzx   eax, byte ptr [rdi+22h]
0x14001bdbf  lea     rcx, aVhdmpiscsicomm_34; "VhdmpiScsiCommandReportLuns"
0x14001bdc6  mov     [rsp+88h+var_58], rdi
0x14001bdcb  mov     edx, 0ECh; int
0x14001bdd0  mov     dword ptr [rsp+88h+var_60], eax; char
0x14001bdd4  mov     r9d, 10h; int
0x14001bdda  lea     rax, aVhdmpiscsicomm_2; "VhdmpiScsiCommandReportLuns: Reporting "...
0x14001bde1  mov     r8d, esi; int
0x14001bde4  mov     [rsp+88h+var_68], rax; char *
0x14001bde9  call    TraceEvents
0x14001bdee  and     dword ptr [rdi+38h], 0FFFFFFFEh
0x14001bdf2  mov     eax, [rdi+1F4h]
0x14001bdf8  cmp     eax, 3
0x14001bdfb  jnb     short loc_14001BE05
0x14001bdfd  inc     eax
0x14001bdff  mov     [rdi+1F4h], eax
0x14001be05  mov     rcx, rdi; char
0x14001be08  call    VhdmpiTryRemoveSurfaceFromSurfaceList
0x14001be0d  jmp     short loc_14001BE8D
0x14001be0f  cmp     eax, esi
0x14001be11  jbe     short loc_14001BE5F
0x14001be13  mov     rdx, r14
0x14001be16  lea     rcx, dword_1400876D0
0x14001be1d  call    _tlgKeywordOn
0x14001be22  test    al, al
0x14001be24  jz      short loc_14001BE5F
0x14001be26  mov     [rsp+88h+var_58], rdi
0x14001be2b  lea     r14, [rdi+22h]
0x14001be2f  movzx   eax, byte ptr [r14]
0x14001be33  lea     rcx, aVhdmpiscsicomm_34; "VhdmpiScsiCommandReportLuns"
0x14001be3a  mov     dword ptr [rsp+88h+var_60], eax; char
0x14001be3e  mov     edx, 101h; int
0x14001be43  lea     rax, aVhdmpiscsicomm_6; "VhdmpiScsiCommandReportLuns: Lun=0x%x S"...
0x14001be4a  mov     r9d, 2; int
0x14001be50  mov     r8d, esi; int
0x14001be53  mov     [rsp+88h+var_68], rax; char *
0x14001be58  call    TraceEvents
0x14001be5d  jmp     short loc_14001BE63
0x14001be5f  lea     r14, [rdi+22h]
0x14001be63  cmp     ebp, 2
0x14001be66  jb      short loc_14001BE84
0x14001be68  mov     al, [r14]
0x14001be6b  mov     rcx, rdi
0x14001be6e  mov     [r15+r12*8+9], al
0x14001be73  call    VhdmpiMarkSurfaceAsReported
0x14001be78  mov     eax, 8
0x14001be7d  cmp     ebp, eax
0x14001be7f  cmovb   eax, ebp
0x14001be82  sub     ebp, eax
0x14001be84  inc     r12d
0x14001be87  mov     r14d, 2
0x14001be8d  mov     r8, cs:VhdmpAdapterExtension
0x14001be94  mov     rdi, r13
0x14001be97  mov     r13, [r13+0]
0x14001be9b  lea     rax, [r8+20h]
0x14001be9f  cmp     rdi, rax
0x14001bea2  jnz     loc_14001BD6E
0x14001bea8  lea     edx, ds:0[r12*8]
0x14001beb0  mov     eax, edx
0x14001beb2  mov     [r15+3], dl
0x14001beb6  shr     eax, 8
0x14001beb9  lea     rcx, [r8+30h]; SpinLock
0x14001bebd  mov     [r15+2], al
0x14001bec1  mov     eax, edx
0x14001bec3  shr     edx, 18h
0x14001bec6  mov     [r15], dl
0x14001bec9  mov     dl, [rsp+88h+NewIrql]; NewIrql
0x14001bed0  shr     eax, 10h
0x14001bed3  mov     [r15+1], al
0x14001bed7  call    cs:__imp_KeReleaseSpinLock
0x14001bede  nop     dword ptr [rax+rax+00h]
0x14001bee3  sub     [rbx+10h], ebp
0x14001bee6  mov     sil, 1
0x14001bee9  mov     eax, cs:dword_1400876D0
0x14001beef  cmp     eax, 5
0x14001bef2  jbe     short loc_14001BF39
0x14001bef4  mov     rdx, r14
0x14001bef7  lea     rcx, dword_1400876D0
0x14001befe  call    _tlgKeywordOn
0x14001bf03  test    al, al
0x14001bf05  jz      short loc_14001BF39
0x14001bf07  movzx   edx, sil
0x14001bf0b  lea     rax, aVhdmpiscsicomm_37; "VhdmpiScsiCommandReportLuns: returning "...
0x14001bf12  mov     dword ptr [rsp+88h+var_60], edx; char
0x14001bf16  lea     rcx, aVhdmpiscsicomm_34; "VhdmpiScsiCommandReportLuns"
0x14001bf1d  mov     r10d, 11Eh
0x14001bf23  mov     [rsp+88h+var_68], rax; char *
0x14001bf28  mov     edx, r10d; int
0x14001bf2b  mov     r9d, r14d; int
0x14001bf2e  mov     r8d, 5; int
0x14001bf34  call    TraceEvents
0x14001bf39  mov     al, sil
0x14001bf3c  add     rsp, 48h
0x14001bf40  pop     r15
0x14001bf42  pop     r14
0x14001bf44  pop     r13
0x14001bf46  pop     r12
0x14001bf48  pop     rdi
0x14001bf49  pop     rsi
0x14001bf4a  pop     rbp
0x14001bf4b  pop     rbx
0x14001bf4c  retn
```
