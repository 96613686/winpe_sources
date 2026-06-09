# VhdmpiScsiCommandReportLuns(_SCSI_REQUEST_BLOCK *)

- ea: `0x14001b830`
- end: `0x14001bb2e`
- name: `?VhdmpiScsiCommandReportLuns@@YAEPEAU_SCSI_REQUEST_BLOCK@@@Z`
- size: `766`
- prototype: `unsigned __int8 __fastcall(struct _SCSI_REQUEST_BLOCK *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400178a0`

## callees

- `0x14001b830`
- `0x14002197c`
- `0x140023560`
- `0x140035bbc`
- `0x140035e94`
- `0x14005dd00`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001b91c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001b91c`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001bab7`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001bab7`

## string_xrefs

- `0x14001b885`: `VhdmpiScsiCommandReportLuns: Path=0x%x Target=0x%x Lun=0x%x`
- `0x14001b890`: `VhdmpiScsiCommandReportLuns`
- `0x14001b99f`: `VhdmpiScsiCommandReportLuns`
- `0x14001ba13`: `VhdmpiScsiCommandReportLuns`
- `0x14001baf6`: `VhdmpiScsiCommandReportLuns`
- `0x14001b9ba`: `VhdmpiScsiCommandReportLuns: Reporting address missing Lun=0x%x Disk=0x%p`
- `0x14001ba23`: `VhdmpiScsiCommandReportLuns: Lun=0x%x Surface=0x%p`
- `0x14001baeb`: `VhdmpiScsiCommandReportLuns: returning 0%x`

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

  if ( (unsigned int)dword_140087708 > 5 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 2) )
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
        if ( (unsigned int)dword_140087708 > 4 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 2) )
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
        if ( (unsigned int)dword_140087708 > 4 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 16) )
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
  if ( (unsigned int)dword_140087708 > 5 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 2) )
    TraceEvents("VhdmpiScsiCommandReportLuns", 0x11Eu, 5u, 2u, "VhdmpiScsiCommandReportLuns: returning 0%x", v3);
  return v3;
}

```

## disassembly

```asm
0x14001b830  push    rbx
0x14001b832  push    rbp
0x14001b833  push    rsi
0x14001b834  push    rdi
0x14001b835  push    r12
0x14001b837  push    r13
0x14001b839  push    r14
0x14001b83b  push    r15
0x14001b83d  sub     rsp, 48h
0x14001b841  mov     eax, cs:dword_140087708
0x14001b847  mov     rbx, rcx
0x14001b84a  mov     r14d, 2
0x14001b850  cmp     eax, 5
0x14001b853  jbe     short loc_14001B8A8
0x14001b855  mov     edx, r14d
0x14001b858  lea     rcx, dword_140087708
0x14001b85f  call    _tlgKeywordOn
0x14001b864  test    al, al
0x14001b866  jz      short loc_14001B8A8
0x14001b868  movzx   eax, byte ptr [rbx+7]
0x14001b86c  lea     r8d, [r14+3]; int
0x14001b870  movzx   ecx, byte ptr [rbx+6]
0x14001b874  mov     r10d, 0B1h
0x14001b87a  movzx   edx, byte ptr [rbx+5]
0x14001b87e  mov     r9d, r14d; int
0x14001b881  mov     [rsp+88h+var_50], eax
0x14001b885  lea     rax, aVhdmpiscsicomm_28; "VhdmpiScsiCommandReportLuns: Path=0x%x "...
0x14001b88c  mov     dword ptr [rsp+88h+var_58], ecx
0x14001b890  lea     rcx, aVhdmpiscsicomm_34; "VhdmpiScsiCommandReportLuns"
0x14001b897  mov     dword ptr [rsp+88h+var_60], edx; char
0x14001b89b  mov     edx, r10d; int
0x14001b89e  mov     [rsp+88h+var_68], rax; char *
0x14001b8a3  call    TraceEvents
0x14001b8a8  mov     al, [rbx+4Eh]
0x14001b8ab  mov     [rsp+93h], al
0x14001b8b2  mov     al, [rbx+4Fh]
0x14001b8b5  mov     [rsp+92h], al
0x14001b8bc  mov     al, [rbx+50h]
0x14001b8bf  mov     [rsp+91h], al
0x14001b8c6  mov     al, [rbx+51h]
0x14001b8c9  mov     [rsp+88h+NewIrql], al
0x14001b8d0  mov     eax, [rbx+10h]
0x14001b8d3  cmp     eax, dword ptr [rsp+88h+NewIrql]
0x14001b8da  jnb     short loc_14001B8ED
0x14001b8dc  mov     esi, 4
0x14001b8e1  mov     dword ptr [rbx+10h], 0
0x14001b8e8  jmp     loc_14001BAC9
0x14001b8ed  cmp     eax, 10h
0x14001b8f0  jnb     short loc_14001B8F7
0x14001b8f2  mov     sil, 12h
0x14001b8f5  jmp     short loc_14001B8E1
0x14001b8f7  mov     r15, [rbx+18h]
0x14001b8fb  mov     r8, rax; Size
0x14001b8fe  mov     rcx, r15; void *
0x14001b901  xor     edx, edx; Val
0x14001b903  call    memset
0x14001b908  mov     rcx, cs:VhdmpAdapterExtension
0x14001b90f  xor     r12d, r12d
0x14001b912  mov     ebp, [rbx+10h]
0x14001b915  add     rcx, 30h ; '0'; SpinLock
0x14001b919  sub     ebp, 8
0x14001b91c  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14001b923  nop     dword ptr [rax+rax+00h]
0x14001b928  mov     r8, cs:VhdmpAdapterExtension
0x14001b92f  mov     [rsp+88h+NewIrql], al
0x14001b936  lea     rcx, [r8+20h]
0x14001b93a  mov     rdi, [rcx]
0x14001b93d  mov     r13, [rdi]
0x14001b940  cmp     rdi, rcx
0x14001b943  jz      loc_14001BA88
0x14001b949  lea     esi, [r12+4]
0x14001b94e  mov     ecx, [rdi+38h]
0x14001b951  and     ecx, 610h
0x14001b957  cmp     ecx, 10h
0x14001b95a  jnz     loc_14001BA6D
0x14001b960  mov     al, [rbx+6]
0x14001b963  cmp     [rdi+21h], al
0x14001b966  jnz     loc_14001BA6D
0x14001b96c  mov     al, [rbx+5]
0x14001b96f  cmp     [rdi+20h], al
0x14001b972  jnz     loc_14001BA6D
0x14001b978  cmp     qword ptr [rdi+10h], 0
0x14001b97d  mov     eax, cs:dword_140087708
0x14001b983  jnz     short loc_14001B9EF
0x14001b985  cmp     eax, esi
0x14001b987  jbe     short loc_14001B9CE
0x14001b989  mov     edx, ecx
0x14001b98b  lea     rcx, dword_140087708
0x14001b992  call    _tlgKeywordOn
0x14001b997  test    al, al
0x14001b999  jz      short loc_14001B9CE
0x14001b99b  movzx   eax, byte ptr [rdi+22h]
0x14001b99f  lea     rcx, aVhdmpiscsicomm_34; "VhdmpiScsiCommandReportLuns"
0x14001b9a6  mov     [rsp+88h+var_58], rdi
0x14001b9ab  mov     edx, 0ECh; int
0x14001b9b0  mov     dword ptr [rsp+88h+var_60], eax; char
0x14001b9b4  mov     r9d, 10h; int
0x14001b9ba  lea     rax, aVhdmpiscsicomm_2; "VhdmpiScsiCommandReportLuns: Reporting "...
0x14001b9c1  mov     r8d, esi; int
0x14001b9c4  mov     [rsp+88h+var_68], rax; char *
0x14001b9c9  call    TraceEvents
0x14001b9ce  and     dword ptr [rdi+38h], 0FFFFFFFEh
0x14001b9d2  mov     eax, [rdi+1F4h]
0x14001b9d8  cmp     eax, 3
0x14001b9db  jnb     short loc_14001B9E5
0x14001b9dd  inc     eax
0x14001b9df  mov     [rdi+1F4h], eax
0x14001b9e5  mov     rcx, rdi; char
0x14001b9e8  call    VhdmpiTryRemoveSurfaceFromSurfaceList
0x14001b9ed  jmp     short loc_14001BA6D
0x14001b9ef  cmp     eax, esi
0x14001b9f1  jbe     short loc_14001BA3F
0x14001b9f3  mov     rdx, r14
0x14001b9f6  lea     rcx, dword_140087708
0x14001b9fd  call    _tlgKeywordOn
0x14001ba02  test    al, al
0x14001ba04  jz      short loc_14001BA3F
0x14001ba06  mov     [rsp+88h+var_58], rdi
0x14001ba0b  lea     r14, [rdi+22h]
0x14001ba0f  movzx   eax, byte ptr [r14]
0x14001ba13  lea     rcx, aVhdmpiscsicomm_34; "VhdmpiScsiCommandReportLuns"
0x14001ba1a  mov     dword ptr [rsp+88h+var_60], eax; char
0x14001ba1e  mov     edx, 101h; int
0x14001ba23  lea     rax, aVhdmpiscsicomm_6; "VhdmpiScsiCommandReportLuns: Lun=0x%x S"...
0x14001ba2a  mov     r9d, 2; int
0x14001ba30  mov     r8d, esi; int
0x14001ba33  mov     [rsp+88h+var_68], rax; char *
0x14001ba38  call    TraceEvents
0x14001ba3d  jmp     short loc_14001BA43
0x14001ba3f  lea     r14, [rdi+22h]
0x14001ba43  cmp     ebp, 2
0x14001ba46  jb      short loc_14001BA64
0x14001ba48  mov     al, [r14]
0x14001ba4b  mov     rcx, rdi
0x14001ba4e  mov     [r15+r12*8+9], al
0x14001ba53  call    VhdmpiMarkSurfaceAsReported
0x14001ba58  mov     eax, 8
0x14001ba5d  cmp     ebp, eax
0x14001ba5f  cmovb   eax, ebp
0x14001ba62  sub     ebp, eax
0x14001ba64  inc     r12d
0x14001ba67  mov     r14d, 2
0x14001ba6d  mov     r8, cs:VhdmpAdapterExtension
0x14001ba74  mov     rdi, r13
0x14001ba77  mov     r13, [r13+0]
0x14001ba7b  lea     rax, [r8+20h]
0x14001ba7f  cmp     rdi, rax
0x14001ba82  jnz     loc_14001B94E
0x14001ba88  lea     edx, ds:0[r12*8]
0x14001ba90  mov     eax, edx
0x14001ba92  mov     [r15+3], dl
0x14001ba96  shr     eax, 8
0x14001ba99  lea     rcx, [r8+30h]; SpinLock
0x14001ba9d  mov     [r15+2], al
0x14001baa1  mov     eax, edx
0x14001baa3  shr     edx, 18h
0x14001baa6  mov     [r15], dl
0x14001baa9  mov     dl, [rsp+88h+NewIrql]; NewIrql
0x14001bab0  shr     eax, 10h
0x14001bab3  mov     [r15+1], al
0x14001bab7  call    cs:__imp_KeReleaseSpinLock
0x14001babe  nop     dword ptr [rax+rax+00h]
0x14001bac3  sub     [rbx+10h], ebp
0x14001bac6  mov     sil, 1
0x14001bac9  mov     eax, cs:dword_140087708
0x14001bacf  cmp     eax, 5
0x14001bad2  jbe     short loc_14001BB19
0x14001bad4  mov     rdx, r14
0x14001bad7  lea     rcx, dword_140087708
0x14001bade  call    _tlgKeywordOn
0x14001bae3  test    al, al
0x14001bae5  jz      short loc_14001BB19
0x14001bae7  movzx   edx, sil
0x14001baeb  lea     rax, aVhdmpiscsicomm_37; "VhdmpiScsiCommandReportLuns: returning "...
0x14001baf2  mov     dword ptr [rsp+88h+var_60], edx; char
0x14001baf6  lea     rcx, aVhdmpiscsicomm_34; "VhdmpiScsiCommandReportLuns"
0x14001bafd  mov     r10d, 11Eh
0x14001bb03  mov     [rsp+88h+var_68], rax; char *
0x14001bb08  mov     edx, r10d; int
0x14001bb0b  mov     r9d, r14d; int
0x14001bb0e  mov     r8d, 5; int
0x14001bb14  call    TraceEvents
0x14001bb19  mov     al, sil
0x14001bb1c  add     rsp, 48h
0x14001bb20  pop     r15
0x14001bb22  pop     r14
0x14001bb24  pop     r13
0x14001bb26  pop     r12
0x14001bb28  pop     rdi
0x14001bb29  pop     rsi
0x14001bb2a  pop     rbp
0x14001bb2b  pop     rbx
0x14001bb2c  retn
```
