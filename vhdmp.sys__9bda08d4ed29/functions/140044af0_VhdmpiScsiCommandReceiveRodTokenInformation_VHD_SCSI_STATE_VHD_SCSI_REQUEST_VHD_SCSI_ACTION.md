# VhdmpiScsiCommandReceiveRodTokenInformation(VHD_SCSI_STATE *,VHD_SCSI_REQUEST *,VHD_SCSI_ACTION *)

- ea: `0x140044af0`
- end: `0x140044de9`
- name: `?VhdmpiScsiCommandReceiveRodTokenInformation@@YAEPEAUVHD_SCSI_STATE@@PEAUVHD_SCSI_REQUEST@@PEAUVHD_SCSI_ACTION@@@Z`
- size: `761`
- prototype: `unsigned __int8(struct VHD_SCSI_STATE *, struct VHD_SCSI_REQUEST *, struct VHD_SCSI_ACTION *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x140023980`
- `0x140027274`
- `0x140036284`
- `0x1400439a8`
- `0x140044af0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140044dd1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140044dd1`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140044b1b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140044b1b`
- `ntoskrnl!KeReleaseSpinLock` at `0x140044b68`
- `ntoskrnl!KeReleaseSpinLock` at `0x140044b68`

## string_xrefs

- `0x140044c1f`: `VhdmpiScsiCommandReceiveRodTokenInformation`
- `0x140044cb0`: `VhdmpiScsiCommandReceiveRodTokenInformation`
- `0x140044c9e`: `VhdmpiScsiCommandReceiveRodTokenInformation: allocation length too large 0x%x > 0x%x`
- `0x140044c05`: `VhdmpiScsiCommandReceiveRodTokenInformation: list ID not found.  ListIdentifier: %lun`

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
      if ( (unsigned int)dword_1400876D0 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 32) )
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
  if ( (unsigned int)dword_1400876D0 > 2 )
  {
    if ( (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 32) )
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
0x140044af0  push    rbx
0x140044af2  push    rbp
0x140044af3  push    rsi
0x140044af4  push    rdi
0x140044af5  push    r12
0x140044af7  push    r13
0x140044af9  push    r14
0x140044afb  push    r15
0x140044afd  sub     rsp, 48h
0x140044b01  cmp     byte ptr [rcx+1Bh], 0
0x140044b05  mov     r14, r8
0x140044b08  mov     rbx, rdx
0x140044b0b  mov     rbp, rcx
0x140044b0e  jnz     short loc_140044B14
0x140044b10  mov     al, 6
0x140044b12  jmp     short loc_140044B77
0x140044b14  mov     rsi, [rdx]
0x140044b17  add     rcx, 50h ; 'P'; SpinLock
0x140044b1b  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140044b22  nop     dword ptr [rax+rax+00h]
0x140044b27  mov     cl, [rsi+1]
0x140044b2a  mov     r13b, al
0x140044b2d  and     cl, 1Fh
0x140044b30  cmp     cl, 7
0x140044b33  jz      short loc_140044B89
0x140044b35  mov     byte ptr [rbx+25h], 2
0x140044b39  xor     eax, eax
0x140044b3b  xorps   xmm0, xmm0
0x140044b3e  mov     sil, 6
0x140044b41  movups  xmmword ptr [rbx+2Ah], xmm0
0x140044b45  mov     [rbx+3Ah], ax
0x140044b49  mov     word ptr [rbx+29h], 7001h
0x140044b4f  mov     al, [rbx+2Ch]
0x140044b52  and     al, 0F5h
0x140044b54  or      al, 5
0x140044b56  mov     [rbx+2Ch], al
0x140044b59  mov     byte ptr [rbx+31h], 0Ah
0x140044b5d  mov     byte ptr [rbx+36h], 24h ; '$'
0x140044b61  mov     dl, r13b; NewIrql
0x140044b64  lea     rcx, [rbp+50h]; SpinLock
0x140044b68  call    cs:__imp_KeReleaseSpinLock
0x140044b6f  nop     dword ptr [rax+rax+00h]
0x140044b74  mov     al, sil
0x140044b77  add     rsp, 48h
0x140044b7b  pop     r15
0x140044b7d  pop     r14
0x140044b7f  pop     r13
0x140044b81  pop     r12
0x140044b83  pop     rdi
0x140044b84  pop     rsi
0x140044b85  pop     rbp
0x140044b86  pop     rbx
0x140044b87  retn
0x140044b89  mov     al, [rsi+2]
0x140044b8c  mov     byte ptr [rsp+88h+arg_0+3], al
0x140044b93  mov     al, [rsi+3]
0x140044b96  mov     byte ptr [rsp+88h+arg_0+2], al
0x140044b9d  mov     al, [rsi+4]
0x140044ba0  mov     byte ptr [rsp+88h+arg_0+1], al
0x140044ba7  mov     al, [rsi+5]
0x140044baa  mov     byte ptr [rsp+88h+arg_0], al
0x140044bb1  mov     r8d, [rsp+88h+arg_0]
0x140044bb9  mov     ecx, r8d
0x140044bbc  and     ecx, 1Fh
0x140044bbf  mov     edx, r8d; unsigned int
0x140044bc2  shl     rcx, 4
0x140044bc6  add     rcx, 78h ; 'x'
0x140044bca  add     rcx, rbp; struct _LIST_ENTRY *
0x140044bcd  call    ?VhdmpiOffloadTableScanBin@@YAPEAU_VHD_OFFLOAD_OP@@PEAU_LIST_ENTRY@@I@Z; VhdmpiOffloadTableScanBin(_LIST_ENTRY *,uint)
0x140044bd2  mov     rdi, rax
0x140044bd5  test    rax, rax
0x140044bd8  jnz     short loc_140044C30
0x140044bda  mov     eax, cs:dword_1400876D0
0x140044be0  cmp     eax, 2
0x140044be3  jbe     loc_140044B35
0x140044be9  lea     edx, [rdi+20h]
0x140044bec  lea     rcx, dword_1400876D0
0x140044bf3  call    _tlgKeywordOn
0x140044bf8  test    al, al
0x140044bfa  jz      loc_140044B35
0x140044c00  mov     dword ptr [rsp+88h+var_60], r8d; char
0x140044c05  lea     rax, aVhdmpiscsicomm_27; "VhdmpiScsiCommandReceiveRodTokenInforma"...
0x140044c0c  mov     ecx, 1B5Bh
0x140044c11  mov     [rsp+88h+var_68], rax; char *
0x140044c16  mov     r9d, edx; int
0x140044c19  lea     r8d, [rdi+2]; int
0x140044c1d  mov     edx, ecx; int
0x140044c1f  lea     rcx, aVhdmpiscsicomm_21; "VhdmpiScsiCommandReceiveRodTokenInforma"...
0x140044c26  call    TraceEvents
0x140044c2b  jmp     loc_140044B35
0x140044c30  mov     al, [rsi+0Ah]
0x140044c33  mov     byte ptr [rsp+88h+arg_0+3], al
0x140044c3a  mov     al, [rsi+0Bh]
0x140044c3d  mov     byte ptr [rsp+88h+arg_0+2], al
0x140044c44  mov     al, [rsi+0Ch]
0x140044c47  mov     byte ptr [rsp+88h+arg_0+1], al
0x140044c4e  mov     al, [rsi+0Dh]
0x140044c51  mov     byte ptr [rsp+88h+arg_0], al
0x140044c58  mov     r8d, [rsp+88h+arg_0]
0x140044c60  cmp     r8d, [rbx+10h]
0x140044c64  jbe     loc_140044CF4
0x140044c6a  mov     eax, cs:dword_1400876D0
0x140044c70  cmp     eax, 2
0x140044c73  jbe     short loc_140044CBC
0x140044c75  mov     edx, 20h ; ' '
0x140044c7a  lea     rcx, dword_1400876D0
0x140044c81  call    _tlgKeywordOn
0x140044c86  test    al, al
0x140044c88  jz      short loc_140044CBC
0x140044c8a  mov     eax, [rbx+10h]
0x140044c8d  mov     ecx, 1B6Eh
0x140044c92  mov     [rsp+88h+var_58], eax
0x140044c96  mov     r9d, edx; int
0x140044c99  mov     dword ptr [rsp+88h+var_60], r8d; char
0x140044c9e  lea     rax, aVhdmpiscsicomm_38; "VhdmpiScsiCommandReceiveRodTokenInforma"...
0x140044ca5  lea     r8d, [rdx-1Eh]; int
0x140044ca9  mov     [rsp+88h+var_68], rax; char *
0x140044cae  mov     edx, ecx; int
0x140044cb0  lea     rcx, aVhdmpiscsicomm_21; "VhdmpiScsiCommandReceiveRodTokenInforma"...
0x140044cb7  call    TraceEvents
0x140044cbc  mov     byte ptr [rbx+25h], 2
0x140044cc0  lea     r15, [rdi+280h]
0x140044cc7  xor     eax, eax
0x140044cc9  xorps   xmm0, xmm0
0x140044ccc  movups  xmmword ptr [rbx+2Ah], xmm0
0x140044cd0  mov     [rbx+3Ah], ax
0x140044cd4  mov     sil, 6
0x140044cd7  mov     word ptr [rbx+29h], 7001h
0x140044cdd  mov     al, [rbx+2Ch]
0x140044ce0  and     al, 0F5h
0x140044ce2  mov     byte ptr [rbx+31h], 0Ah
0x140044ce6  or      al, 5
0x140044ce8  mov     byte ptr [rbx+36h], 24h ; '$'
0x140044cec  mov     [rbx+2Ch], al
0x140044cef  jmp     loc_140044D83
0x140044cf4  lea     r15, [rdi+280h]
0x140044cfb  cmp     dword ptr [r15], 103h
0x140044d02  jnz     short loc_140044D75
0x140044d04  or      dword ptr [r14+18h], 4
0x140044d09  cmp     qword ptr [rdi+48h], 0
0x140044d0e  jz      short loc_140044D3E
0x140044d10  or      dword ptr [r14+18h], 8
0x140044d15  mov     rdx, rdi; struct _VHD_OFFLOAD_OP *
0x140044d18  mov     qword ptr [r14+20h], 0
0x140044d20  mov     rax, [rdi+48h]
0x140044d24  add     rax, 40h ; '@'
0x140044d28  mov     qword ptr [rax], 0
0x140044d2f  mov     [r14+20h], rax
0x140044d33  mov     rcx, [rdi+48h]; struct VHD_SCSI_REQUEST *
0x140044d37  call    ?VhdmpiReceiveRodTokenInformation@@YAXPEAUVHD_SCSI_REQUEST@@PEAU_VHD_OFFLOAD_OP@@@Z; VhdmpiReceiveRodTokenInformation(VHD_SCSI_REQUEST *,_VHD_OFFLOAD_OP *)
0x140044d3c  jmp     short loc_140044D64
0x140044d3e  lea     rcx, [rbp+288h]
0x140044d45  mov     rdx, [rcx+8]
0x140044d49  cmp     [rdx], rcx
0x140044d4c  jnz     loc_140044DE2
0x140044d52  lea     rax, [rdi+20h]
0x140044d56  mov     [rax], rcx
0x140044d59  mov     [rax+8], rdx
0x140044d5d  mov     [rdx], rax
0x140044d60  mov     [rcx+8], rax
0x140044d64  mov     [rdi+48h], rbx
0x140044d68  xor     sil, sil
0x140044d6b  mov     rax, [rbx+48h]
0x140044d6f  mov     [rdi+68h], rax
0x140044d73  jmp     short loc_140044D83
0x140044d75  mov     rdx, rdi; struct _VHD_OFFLOAD_OP *
0x140044d78  mov     rcx, rbx; struct VHD_SCSI_REQUEST *
0x140044d7b  call    ?VhdmpiReceiveRodTokenInformation@@YAXPEAUVHD_SCSI_REQUEST@@PEAU_VHD_OFFLOAD_OP@@@Z; VhdmpiReceiveRodTokenInformation(VHD_SCSI_REQUEST *,_VHD_OFFLOAD_OP *)
0x140044d80  mov     sil, 1
0x140044d83  cmp     dword ptr [r15], 103h
0x140044d8a  jz      loc_140044B61
0x140044d90  mov     rax, [rdi]
0x140044d93  cmp     [rax+8], rdi
0x140044d97  jnz     short loc_140044DE2
0x140044d99  mov     rcx, [rdi+8]
0x140044d9d  cmp     [rcx], rdi
0x140044da0  jnz     short loc_140044DE2
0x140044da2  mov     [rcx], rax
0x140044da5  mov     [rax+8], rcx
0x140044da9  lea     rax, [rdi+10h]
0x140044dad  dec     dword ptr [rbp+298h]
0x140044db3  mov     rdx, [rax]
0x140044db6  cmp     [rdx+8], rax
0x140044dba  jnz     short loc_140044DE2
0x140044dbc  mov     rcx, [rax+8]
0x140044dc0  cmp     [rcx], rax
0x140044dc3  jnz     short loc_140044DE2
0x140044dc5  mov     [rcx], rdx
0x140044dc8  mov     [rdx+8], rcx
0x140044dcc  xor     edx, edx; Tag
0x140044dce  mov     rcx, rdi; P
0x140044dd1  call    cs:__imp_ExFreePoolWithTag
0x140044dd8  nop     dword ptr [rax+rax+00h]
0x140044ddd  jmp     loc_140044B61
0x140044de2  mov     ecx, 3
0x140044de7  int     29h; Win8: RtlFailFast(ecx)
```
