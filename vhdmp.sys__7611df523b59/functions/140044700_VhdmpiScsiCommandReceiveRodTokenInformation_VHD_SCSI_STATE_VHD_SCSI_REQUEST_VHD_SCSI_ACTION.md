# VhdmpiScsiCommandReceiveRodTokenInformation(VHD_SCSI_STATE *,VHD_SCSI_REQUEST *,VHD_SCSI_ACTION *)

- ea: `0x140044700`
- end: `0x1400449f9`
- name: `?VhdmpiScsiCommandReceiveRodTokenInformation@@YAEPEAUVHD_SCSI_STATE@@PEAUVHD_SCSI_REQUEST@@PEAUVHD_SCSI_ACTION@@@Z`
- size: `761`
- prototype: `unsigned __int8(struct VHD_SCSI_STATE *, struct VHD_SCSI_REQUEST *, struct VHD_SCSI_ACTION *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x140023560`
- `0x140026d50`
- `0x140035e94`
- `0x1400435b8`
- `0x140044700`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400449e1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400449e1`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14004472b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14004472b`
- `ntoskrnl!KeReleaseSpinLock` at `0x140044778`
- `ntoskrnl!KeReleaseSpinLock` at `0x140044778`

## string_xrefs

- `0x1400448ae`: `VhdmpiScsiCommandReceiveRodTokenInformation: allocation length too large 0x%x > 0x%x`
- `0x140044815`: `VhdmpiScsiCommandReceiveRodTokenInformation: list ID not found.  ListIdentifier: %lun`
- `0x14004482f`: `VhdmpiScsiCommandReceiveRodTokenInformation`
- `0x1400448c0`: `VhdmpiScsiCommandReceiveRodTokenInformation`

## pseudocode

```c
char __fastcall VhdmpiScsiCommandReceiveRodTokenInformation(
        struct VHD_SCSI_STATE *a1,
        struct VHD_SCSI_REQUEST *a2,
        struct VHD_SCSI_ACTION *a3)
{
  _BYTE *v7; // rsi
  KIRQL v8; // r13
  char v9; // si
  struct _VHD_OFFLOAD_OP *v10; // rdi
  unsigned int v11; // edx
  int v12; // r8d
  unsigned int v13; // edx
  int v14; // r8d
  _DWORD *v15; // r15
  char v16; // al
  _QWORD *v17; // rax
  struct VHD_SCSI_STATE **v18; // rdx
  __int64 v19; // rax
  struct _VHD_OFFLOAD_OP **v20; // rcx
  __int64 v21; // rdx
  struct _VHD_OFFLOAD_OP **v22; // rcx
  unsigned int v23; // [rsp+90h] [rbp+8h]
  unsigned int v24; // [rsp+90h] [rbp+8h]

  if ( !*((_BYTE *)a1 + 27) )
    return 6;
  v7 = *(_BYTE **)a2;
  v8 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)a1 + 10);
  if ( (v7[1] & 0x1F) != 7 )
    goto LABEL_4;
  HIBYTE(v23) = v7[2];
  BYTE2(v23) = v7[3];
  BYTE1(v23) = v7[4];
  LOBYTE(v23) = v7[5];
  v10 = VhdmpiOffloadTableScanBin((struct _LIST_ENTRY *)((char *)a1 + 16 * (v23 & 0x1F) + 120), v23);
  if ( v10 )
  {
    HIBYTE(v24) = v7[10];
    BYTE2(v24) = v7[11];
    BYTE1(v24) = v7[12];
    LOBYTE(v24) = v7[13];
    if ( v24 <= *((_DWORD *)a2 + 4) )
    {
      v15 = (_DWORD *)((char *)v10 + 640);
      if ( *((_DWORD *)v10 + 160) == 259 )
      {
        *((_DWORD *)a3 + 6) |= 4u;
        if ( *((_QWORD *)v10 + 9) )
        {
          *((_DWORD *)a3 + 6) |= 8u;
          *((_QWORD *)a3 + 4) = 0;
          v17 = (_QWORD *)(*((_QWORD *)v10 + 9) + 64LL);
          *v17 = 0;
          *((_QWORD *)a3 + 4) = v17;
          VhdmpiReceiveRodTokenInformation(*((struct VHD_SCSI_REQUEST **)v10 + 9), v10);
        }
        else
        {
          v18 = (struct VHD_SCSI_STATE **)*((_QWORD *)a1 + 82);
          if ( *v18 != (struct VHD_SCSI_STATE *)((char *)a1 + 648) )
            goto LABEL_28;
          *((_QWORD *)v10 + 4) = (char *)a1 + 648;
          *((_QWORD *)v10 + 5) = v18;
          *v18 = (struct _VHD_OFFLOAD_OP *)((char *)v10 + 32);
          *((_QWORD *)a1 + 82) = (char *)v10 + 32;
        }
        *((_QWORD *)v10 + 9) = a2;
        v9 = 0;
        *((_QWORD *)v10 + 13) = *((_QWORD *)a2 + 9);
      }
      else
      {
        VhdmpiReceiveRodTokenInformation(a2, v10);
        v9 = 1;
      }
    }
    else
    {
      if ( (unsigned int)dword_140087708 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 32) )
        TraceEvents(
          "VhdmpiScsiCommandReceiveRodTokenInformation",
          0x1B6Eu,
          v13 - 30,
          v13,
          "VhdmpiScsiCommandReceiveRodTokenInformation: allocation length too large 0x%x > 0x%x",
          v14,
          *((_DWORD *)a2 + 4));
      *((_BYTE *)a2 + 37) = 2;
      v15 = (_DWORD *)((char *)v10 + 640);
      *(_OWORD *)((char *)a2 + 42) = 0;
      *((_WORD *)a2 + 29) = 0;
      v9 = 6;
      *(_WORD *)((char *)a2 + 41) = 28673;
      v16 = *((_BYTE *)a2 + 44) & 0xF5;
      *((_BYTE *)a2 + 49) = 10;
      *((_BYTE *)a2 + 54) = 36;
      *((_BYTE *)a2 + 44) = v16 | 5;
    }
    if ( *v15 == 259 )
      goto LABEL_5;
    v19 = *(_QWORD *)v10;
    if ( *(struct _VHD_OFFLOAD_OP **)(*(_QWORD *)v10 + 8LL) == v10 )
    {
      v20 = (struct _VHD_OFFLOAD_OP **)*((_QWORD *)v10 + 1);
      if ( *v20 == v10 )
      {
        *v20 = (struct _VHD_OFFLOAD_OP *)v19;
        *(_QWORD *)(v19 + 8) = v20;
        --*((_DWORD *)a1 + 166);
        v21 = *((_QWORD *)v10 + 2);
        if ( *(struct _VHD_OFFLOAD_OP **)(v21 + 8) == (struct _VHD_OFFLOAD_OP *)((char *)v10 + 16) )
        {
          v22 = (struct _VHD_OFFLOAD_OP **)*((_QWORD *)v10 + 3);
          if ( *v22 == (struct _VHD_OFFLOAD_OP *)((char *)v10 + 16) )
          {
            *v22 = (struct _VHD_OFFLOAD_OP *)v21;
            *(_QWORD *)(v21 + 8) = v22;
            ExFreePoolWithTag(v10, 0);
            goto LABEL_5;
          }
        }
      }
    }
LABEL_28:
    __fastfail(3u);
  }
  if ( (unsigned int)dword_140087708 > 2 )
  {
    if ( (unsigned __int8)tlgKeywordOn(&dword_140087708, 32) )
      TraceEvents(
        "VhdmpiScsiCommandReceiveRodTokenInformation",
        0x1B5Bu,
        2u,
        v11,
        "VhdmpiScsiCommandReceiveRodTokenInformation: list ID not found.  ListIdentifier: %lun",
        v12);
  }
LABEL_4:
  *((_BYTE *)a2 + 37) = 2;
  v9 = 6;
  *(_OWORD *)((char *)a2 + 42) = 0;
  *((_WORD *)a2 + 29) = 0;
  *(_WORD *)((char *)a2 + 41) = 28673;
  *((_BYTE *)a2 + 44) = *((_BYTE *)a2 + 44) & 0xF0 | 5;
  *((_BYTE *)a2 + 49) = 10;
  *((_BYTE *)a2 + 54) = 36;
LABEL_5:
  KeReleaseSpinLock((PKSPIN_LOCK)a1 + 10, v8);
  return v9;
}

```

## disassembly

```asm
0x140044700  push    rbx
0x140044702  push    rbp
0x140044703  push    rsi
0x140044704  push    rdi
0x140044705  push    r12
0x140044707  push    r13
0x140044709  push    r14
0x14004470b  push    r15
0x14004470d  sub     rsp, 48h
0x140044711  cmp     byte ptr [rcx+1Bh], 0
0x140044715  mov     r14, r8
0x140044718  mov     rbx, rdx
0x14004471b  mov     rbp, rcx
0x14004471e  jnz     short loc_140044724
0x140044720  mov     al, 6
0x140044722  jmp     short loc_140044787
0x140044724  mov     rsi, [rdx]
0x140044727  add     rcx, 50h ; 'P'; SpinLock
0x14004472b  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140044732  nop     dword ptr [rax+rax+00h]
0x140044737  mov     cl, [rsi+1]
0x14004473a  mov     r13b, al
0x14004473d  and     cl, 1Fh
0x140044740  cmp     cl, 7
0x140044743  jz      short loc_140044799
0x140044745  mov     byte ptr [rbx+25h], 2
0x140044749  xor     eax, eax
0x14004474b  xorps   xmm0, xmm0
0x14004474e  mov     sil, 6
0x140044751  movups  xmmword ptr [rbx+2Ah], xmm0
0x140044755  mov     [rbx+3Ah], ax
0x140044759  mov     word ptr [rbx+29h], 7001h
0x14004475f  mov     al, [rbx+2Ch]
0x140044762  and     al, 0F5h
0x140044764  or      al, 5
0x140044766  mov     [rbx+2Ch], al
0x140044769  mov     byte ptr [rbx+31h], 0Ah
0x14004476d  mov     byte ptr [rbx+36h], 24h ; '$'
0x140044771  mov     dl, r13b; NewIrql
0x140044774  lea     rcx, [rbp+50h]; SpinLock
0x140044778  call    cs:__imp_KeReleaseSpinLock
0x14004477f  nop     dword ptr [rax+rax+00h]
0x140044784  mov     al, sil
0x140044787  add     rsp, 48h
0x14004478b  pop     r15
0x14004478d  pop     r14
0x14004478f  pop     r13
0x140044791  pop     r12
0x140044793  pop     rdi
0x140044794  pop     rsi
0x140044795  pop     rbp
0x140044796  pop     rbx
0x140044797  retn
0x140044799  mov     al, [rsi+2]
0x14004479c  mov     byte ptr [rsp+88h+arg_0+3], al
0x1400447a3  mov     al, [rsi+3]
0x1400447a6  mov     byte ptr [rsp+88h+arg_0+2], al
0x1400447ad  mov     al, [rsi+4]
0x1400447b0  mov     byte ptr [rsp+88h+arg_0+1], al
0x1400447b7  mov     al, [rsi+5]
0x1400447ba  mov     byte ptr [rsp+88h+arg_0], al
0x1400447c1  mov     r8d, [rsp+88h+arg_0]
0x1400447c9  mov     ecx, r8d
0x1400447cc  and     ecx, 1Fh
0x1400447cf  mov     edx, r8d; unsigned int
0x1400447d2  shl     rcx, 4
0x1400447d6  add     rcx, 78h ; 'x'
0x1400447da  add     rcx, rbp; struct _LIST_ENTRY *
0x1400447dd  call    ?VhdmpiOffloadTableScanBin@@YAPEAU_VHD_OFFLOAD_OP@@PEAU_LIST_ENTRY@@I@Z; VhdmpiOffloadTableScanBin(_LIST_ENTRY *,uint)
0x1400447e2  mov     rdi, rax
0x1400447e5  test    rax, rax
0x1400447e8  jnz     short loc_140044840
0x1400447ea  mov     eax, cs:dword_140087708
0x1400447f0  cmp     eax, 2
0x1400447f3  jbe     loc_140044745
0x1400447f9  lea     edx, [rdi+20h]
0x1400447fc  lea     rcx, dword_140087708
0x140044803  call    _tlgKeywordOn
0x140044808  test    al, al
0x14004480a  jz      loc_140044745
0x140044810  mov     dword ptr [rsp+88h+var_60], r8d; char
0x140044815  lea     rax, aVhdmpiscsicomm_27; "VhdmpiScsiCommandReceiveRodTokenInforma"...
0x14004481c  mov     ecx, 1B5Bh
0x140044821  mov     [rsp+88h+var_68], rax; char *
0x140044826  mov     r9d, edx; int
0x140044829  lea     r8d, [rdi+2]; int
0x14004482d  mov     edx, ecx; int
0x14004482f  lea     rcx, aVhdmpiscsicomm_21; "VhdmpiScsiCommandReceiveRodTokenInforma"...
0x140044836  call    TraceEvents
0x14004483b  jmp     loc_140044745
0x140044840  mov     al, [rsi+0Ah]
0x140044843  mov     byte ptr [rsp+88h+arg_0+3], al
0x14004484a  mov     al, [rsi+0Bh]
0x14004484d  mov     byte ptr [rsp+88h+arg_0+2], al
0x140044854  mov     al, [rsi+0Ch]
0x140044857  mov     byte ptr [rsp+88h+arg_0+1], al
0x14004485e  mov     al, [rsi+0Dh]
0x140044861  mov     byte ptr [rsp+88h+arg_0], al
0x140044868  mov     r8d, [rsp+88h+arg_0]
0x140044870  cmp     r8d, [rbx+10h]
0x140044874  jbe     loc_140044904
0x14004487a  mov     eax, cs:dword_140087708
0x140044880  cmp     eax, 2
0x140044883  jbe     short loc_1400448CC
0x140044885  mov     edx, 20h ; ' '
0x14004488a  lea     rcx, dword_140087708
0x140044891  call    _tlgKeywordOn
0x140044896  test    al, al
0x140044898  jz      short loc_1400448CC
0x14004489a  mov     eax, [rbx+10h]
0x14004489d  mov     ecx, 1B6Eh
0x1400448a2  mov     [rsp+88h+var_58], eax
0x1400448a6  mov     r9d, edx; int
0x1400448a9  mov     dword ptr [rsp+88h+var_60], r8d; char
0x1400448ae  lea     rax, aVhdmpiscsicomm_38; "VhdmpiScsiCommandReceiveRodTokenInforma"...
0x1400448b5  lea     r8d, [rdx-1Eh]; int
0x1400448b9  mov     [rsp+88h+var_68], rax; char *
0x1400448be  mov     edx, ecx; int
0x1400448c0  lea     rcx, aVhdmpiscsicomm_21; "VhdmpiScsiCommandReceiveRodTokenInforma"...
0x1400448c7  call    TraceEvents
0x1400448cc  mov     byte ptr [rbx+25h], 2
0x1400448d0  lea     r15, [rdi+280h]
0x1400448d7  xor     eax, eax
0x1400448d9  xorps   xmm0, xmm0
0x1400448dc  movups  xmmword ptr [rbx+2Ah], xmm0
0x1400448e0  mov     [rbx+3Ah], ax
0x1400448e4  mov     sil, 6
0x1400448e7  mov     word ptr [rbx+29h], 7001h
0x1400448ed  mov     al, [rbx+2Ch]
0x1400448f0  and     al, 0F5h
0x1400448f2  mov     byte ptr [rbx+31h], 0Ah
0x1400448f6  or      al, 5
0x1400448f8  mov     byte ptr [rbx+36h], 24h ; '$'
0x1400448fc  mov     [rbx+2Ch], al
0x1400448ff  jmp     loc_140044993
0x140044904  lea     r15, [rdi+280h]
0x14004490b  cmp     dword ptr [r15], 103h
0x140044912  jnz     short loc_140044985
0x140044914  or      dword ptr [r14+18h], 4
0x140044919  cmp     qword ptr [rdi+48h], 0
0x14004491e  jz      short loc_14004494E
0x140044920  or      dword ptr [r14+18h], 8
0x140044925  mov     rdx, rdi; struct _VHD_OFFLOAD_OP *
0x140044928  mov     qword ptr [r14+20h], 0
0x140044930  mov     rax, [rdi+48h]
0x140044934  add     rax, 40h ; '@'
0x140044938  mov     qword ptr [rax], 0
0x14004493f  mov     [r14+20h], rax
0x140044943  mov     rcx, [rdi+48h]; struct VHD_SCSI_REQUEST *
0x140044947  call    ?VhdmpiReceiveRodTokenInformation@@YAXPEAUVHD_SCSI_REQUEST@@PEAU_VHD_OFFLOAD_OP@@@Z; VhdmpiReceiveRodTokenInformation(VHD_SCSI_REQUEST *,_VHD_OFFLOAD_OP *)
0x14004494c  jmp     short loc_140044974
0x14004494e  lea     rcx, [rbp+288h]
0x140044955  mov     rdx, [rcx+8]
0x140044959  cmp     [rdx], rcx
0x14004495c  jnz     loc_1400449F2
0x140044962  lea     rax, [rdi+20h]
0x140044966  mov     [rax], rcx
0x140044969  mov     [rax+8], rdx
0x14004496d  mov     [rdx], rax
0x140044970  mov     [rcx+8], rax
0x140044974  mov     [rdi+48h], rbx
0x140044978  xor     sil, sil
0x14004497b  mov     rax, [rbx+48h]
0x14004497f  mov     [rdi+68h], rax
0x140044983  jmp     short loc_140044993
0x140044985  mov     rdx, rdi; struct _VHD_OFFLOAD_OP *
0x140044988  mov     rcx, rbx; struct VHD_SCSI_REQUEST *
0x14004498b  call    ?VhdmpiReceiveRodTokenInformation@@YAXPEAUVHD_SCSI_REQUEST@@PEAU_VHD_OFFLOAD_OP@@@Z; VhdmpiReceiveRodTokenInformation(VHD_SCSI_REQUEST *,_VHD_OFFLOAD_OP *)
0x140044990  mov     sil, 1
0x140044993  cmp     dword ptr [r15], 103h
0x14004499a  jz      loc_140044771
0x1400449a0  mov     rax, [rdi]
0x1400449a3  cmp     [rax+8], rdi
0x1400449a7  jnz     short loc_1400449F2
0x1400449a9  mov     rcx, [rdi+8]
0x1400449ad  cmp     [rcx], rdi
0x1400449b0  jnz     short loc_1400449F2
0x1400449b2  mov     [rcx], rax
0x1400449b5  mov     [rax+8], rcx
0x1400449b9  lea     rax, [rdi+10h]
0x1400449bd  dec     dword ptr [rbp+298h]
0x1400449c3  mov     rdx, [rax]
0x1400449c6  cmp     [rdx+8], rax
0x1400449ca  jnz     short loc_1400449F2
0x1400449cc  mov     rcx, [rax+8]
0x1400449d0  cmp     [rcx], rax
0x1400449d3  jnz     short loc_1400449F2
0x1400449d5  mov     [rcx], rdx
0x1400449d8  mov     [rdx+8], rcx
0x1400449dc  xor     edx, edx; Tag
0x1400449de  mov     rcx, rdi; P
0x1400449e1  call    cs:__imp_ExFreePoolWithTag
0x1400449e8  nop     dword ptr [rax+rax+00h]
0x1400449ed  jmp     loc_140044771
0x1400449f2  mov     ecx, 3
0x1400449f7  int     29h; Win8: RtlFailFast(ecx)
```
