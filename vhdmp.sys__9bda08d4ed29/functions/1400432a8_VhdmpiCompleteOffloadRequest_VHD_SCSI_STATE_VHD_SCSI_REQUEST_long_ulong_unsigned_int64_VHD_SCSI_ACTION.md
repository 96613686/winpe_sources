# VhdmpiCompleteOffloadRequest(VHD_SCSI_STATE *,VHD_SCSI_REQUEST *,long,ulong,unsigned __int64,VHD_SCSI_ACTION *)

- ea: `0x1400432a8`
- end: `0x1400436ef`
- name: `?VhdmpiCompleteOffloadRequest@@YAEPEAUVHD_SCSI_STATE@@PEAUVHD_SCSI_REQUEST@@JK_KPEAUVHD_SCSI_ACTION@@@Z`
- size: `1095`
- prototype: `unsigned __int8 __usercall@<al>(struct VHD_SCSI_STATE *@<rcx>, struct VHD_SCSI_REQUEST *@<rdx>, char@<r8b>, unsigned int@<r9d>, unsigned __int64, struct VHD_SCSI_ACTION *)`
- caller_count: `5`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14000d680`
- `0x14000df20`
- `0x14000e350`
- `0x14000f670`
- `0x140012280`

## callees

- `0x14000f5e0`
- `0x140023980`
- `0x140027274`
- `0x140036284`
- `0x1400432a8`
- `0x1400436f8`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400436c7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400436c7`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400433c2`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400433c2`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400434a6`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400434a6`

## string_xrefs

- `0x14004330b`: `VhdmpiCompleteOffloadRequest`
- `0x14004338d`: `VhdmpiCompleteOffloadRequest`
- `0x1400435a9`: `VhdmpiCompleteOffloadRequest`
- `0x14004364e`: `VhdmpiCompleteOffloadRequest`
- `0x140043398`: `Offload SRB Completion: Request %p TransactionId:%d IsOffloadRead:%d status: %#08x length: %#016I64x requestedLength: %#016I64x`
- `0x14004355b`: `VhdmpiCompleteOffloadRequest() offload done (failed): RequestedTransferLength: %#016I64x TransferLength: %#016I64x`
- `0x14004359d`: `VhdmpiCompleteOffloadRequest() offload done (completely): RequestedTransferLength: %#016I64x TransferLength: %#016I64x`
- `0x140043632`: `VhdmpiCompleteOffloadRequest() offload done (truncation): RequestedTransferLength: %#016I64x TransferLength: %#016I64x`

## pseudocode

```c
unsigned __int8 __fastcall VhdmpiCompleteOffloadRequest(
        struct VHD_SCSI_STATE *a1,
        struct VHD_SCSI_REQUEST *a2,
        int a3,
        unsigned int a4,
        unsigned __int64 a5,
        struct VHD_SCSI_ACTION *a6)
{
  struct _VHD_OFFLOAD_OP *v6; // rbx
  unsigned __int64 v10; // r13
  KIRQL v11; // al
  KIRQL v12; // r8
  __int64 v13; // r14
  unsigned __int8 v14; // si
  struct VHD_SCSI_ACTION *v15; // rdi
  __int64 v16; // rdx
  struct _VHD_OFFLOAD_OP **v17; // rcx
  __int64 v18; // rcx
  struct _VHD_OFFLOAD_OP **v19; // rax
  struct VHD_SCSI_STATE **v20; // rdx
  char v21; // al
  char v22; // cl
  unsigned int v23; // r9d
  __int64 v24; // r8
  unsigned int v25; // r9d
  char v26; // al
  __int64 v27; // r8
  unsigned int v28; // r9d
  __int64 v30; // [rsp+A0h] [rbp+8h]
  struct VHD_SCSI_REQUEST *v31; // [rsp+A8h] [rbp+10h]
  int v32; // [rsp+B0h] [rbp+18h] BYREF

  v6 = (struct _VHD_OFFLOAD_OP *)*((_QWORD *)a2 + 10);
  v32 = 0;
  v31 = 0;
  if ( a3 < 0 )
  {
    if ( (unsigned int)dword_1400876D0 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 32) )
      TraceEvents(
        "VhdmpiCompleteOffloadRequest",
        0x1586u,
        2u,
        0x20u,
        "offload end (failed) : status: %#08x length: %#016I64x",
        a3,
        *((_QWORD *)v6 + 15));
  }
  else
  {
    *((_QWORD *)v6 + 15) = a4;
  }
  if ( (unsigned int)dword_1400876D0 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 32) )
    TraceEvents(
      "VhdmpiCompleteOffloadRequest",
      0x1592u,
      5u,
      0x20u,
      "Offload SRB Completion: Request %p TransactionId:%d IsOffloadRead:%d status: %#08x length: %#016I64x requestedLength: %#016I64x",
      a2,
      *((_DWORD *)v6 + 12),
      *((_DWORD *)v6 + 14) == 0,
      a3,
      *((_QWORD *)v6 + 15),
      *((_QWORD *)v6 + 14));
  v10 = *((_QWORD *)v6 + 15);
  v30 = *((_QWORD *)v6 + 14);
  v11 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)a1 + 10);
  *((_DWORD *)v6 + 160) = a3;
  --*((_DWORD *)a1 + 167);
  v12 = v11;
  *((_QWORD *)v6 + 10) = 0;
  *((_QWORD *)a2 + 10) = 0;
  if ( *((_QWORD *)v6 + 11) )
  {
    v31 = (struct VHD_SCSI_REQUEST *)*((_QWORD *)v6 + 11);
    *((_QWORD *)v6 + 11) = 0;
  }
  v13 = *((_QWORD *)v6 + 9);
  v14 = 4;
  v15 = a6;
  if ( v13 )
  {
    *((_QWORD *)v6 + 9) = 0;
    v16 = *((_QWORD *)v6 + 4);
    if ( *(struct _VHD_OFFLOAD_OP **)(v16 + 8) != (struct _VHD_OFFLOAD_OP *)((char *)v6 + 32) )
      goto LABEL_20;
    v17 = (struct _VHD_OFFLOAD_OP **)*((_QWORD *)v6 + 5);
    if ( *v17 != (struct _VHD_OFFLOAD_OP *)((char *)v6 + 32) )
      goto LABEL_20;
    *v17 = (struct _VHD_OFFLOAD_OP *)v16;
    *(_QWORD *)(v16 + 8) = v17;
LABEL_16:
    v18 = *(_QWORD *)v6;
    if ( *(struct _VHD_OFFLOAD_OP **)(*(_QWORD *)v6 + 8LL) == v6 )
    {
      v19 = (struct _VHD_OFFLOAD_OP **)*((_QWORD *)v6 + 1);
      if ( *v19 == v6 )
      {
        *v19 = (struct _VHD_OFFLOAD_OP *)v18;
        *(_QWORD *)(v18 + 8) = v19;
        --*((_DWORD *)a1 + 166);
        goto LABEL_22;
      }
    }
LABEL_20:
    __fastfail(3u);
  }
  if ( *((_DWORD *)v6 + 14) == 1 )
    goto LABEL_16;
  *((_QWORD *)v6 + 12) = a5;
  v20 = (struct VHD_SCSI_STATE **)*((_QWORD *)a1 + 80);
  if ( *v20 != (struct VHD_SCSI_STATE *)((char *)a1 + 632) )
    goto LABEL_20;
  *((_QWORD *)v6 + 2) = (char *)a1 + 632;
  *((_QWORD *)v6 + 3) = v20;
  *v20 = (struct _VHD_OFFLOAD_OP *)((char *)v6 + 16);
  *((_QWORD *)a1 + 80) = (char *)v6 + 16;
  *((_DWORD *)v15 + 6) |= 4u;
  v6 = 0;
LABEL_22:
  KeReleaseSpinLock((PKSPIN_LOCK)a1 + 10, v12);
  if ( a3 >= 0 )
  {
    if ( v10 == v30 )
    {
      if ( (unsigned int)dword_1400876D0 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 2) )
        TraceEvents(
          "VhdmpiCompleteOffloadRequest",
          0x161Cu,
          v25 + 3,
          v25,
          "VhdmpiCompleteOffloadRequest() offload done (completely): RequestedTransferLength: %#016I64x TransferLength: %#016I64x",
          v24,
          v10);
      v14 = 1;
    }
    else
    {
      *((_BYTE *)a2 + 37) = 2;
      *(_OWORD *)((char *)a2 + 42) = 0;
      *((_WORD *)a2 + 29) = 0;
      *(_WORD *)((char *)a2 + 41) = 28673;
      v26 = *((_BYTE *)a2 + 44) & 0xFB;
      *((_BYTE *)a2 + 49) = 10;
      *((_WORD *)a2 + 27) = 1037;
      *((_BYTE *)a2 + 44) = v26 | 0xB;
      *(_DWORD *)((char *)a2 + 45) = _byteswap_ulong(v10 >> *((_DWORD *)a1 + 16));
      *((_BYTE *)a2 + 42) = -16;
      if ( (unsigned int)dword_1400876D0 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 2) )
        TraceEvents(
          "VhdmpiCompleteOffloadRequest",
          0x1635u,
          5u,
          v28,
          "VhdmpiCompleteOffloadRequest() offload done (truncation): RequestedTransferLength: %#016I64x TransferLength: %#016I64x",
          v27,
          v10);
    }
  }
  else
  {
    if ( VhdmpiCopyOffloadIrpStatusNeedsSpecificScsiSense(a3, (struct _SCSI_SENSE_BYTES *)&v32) )
    {
      *((_BYTE *)a2 + 37) = v32;
      *(_OWORD *)((char *)a2 + 42) = 0;
      *((_WORD *)a2 + 29) = 0;
      v21 = BYTE1(v32);
      *(_WORD *)((char *)a2 + 41) = 28673;
      v22 = *((_BYTE *)a2 + 44) & 0xF0;
      *((_BYTE *)a2 + 49) = 10;
      *((_WORD *)a2 + 27) = HIWORD(v32);
      *((_BYTE *)a2 + 44) = v21 & 0xF | v22;
    }
    if ( (unsigned int)dword_1400876D0 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 2) )
      TraceEvents(
        "VhdmpiCompleteOffloadRequest",
        0x1610u,
        5u,
        v23,
        "VhdmpiCompleteOffloadRequest() offload done (failed): RequestedTransferLength: %#016I64x TransferLength: %#016I64x",
        v30,
        v10);
  }
  *((_DWORD *)v15 + 6) |= 8u;
  *((_QWORD *)v15 + 4) = 0;
  if ( v31 )
  {
    VhdmpiUpdateCompletedScsiRequest(a1, v31, v14);
    *((_QWORD *)v31 + 8) = *((_QWORD *)v15 + 4);
    *((_QWORD *)v15 + 4) = (char *)v31 + 64;
  }
  if ( v13 )
  {
    VhdmpiReceiveRodTokenInformation((struct VHD_SCSI_REQUEST *)v13, v6);
    VhdmpiUpdateCompletedScsiRequest(a1, (struct VHD_SCSI_REQUEST *)v13, 1u);
    *(_QWORD *)(v13 + 64) = *((_QWORD *)v15 + 4);
    *((_QWORD *)v15 + 4) = v13 + 64;
  }
  if ( v6 )
    ExFreePoolWithTag(v6, 0);
  return v14;
}

```

## disassembly

```asm
0x1400432a8  mov     rax, rsp
0x1400432ab  mov     [rax+20h], rbx
0x1400432af  push    rbp
0x1400432b0  push    rsi
0x1400432b1  push    rdi
0x1400432b2  push    r12
0x1400432b4  push    r13
0x1400432b6  push    r14
0x1400432b8  push    r15
0x1400432ba  sub     rsp, 60h
0x1400432be  mov     rbx, [rdx+50h]
0x1400432c2  xor     edi, edi
0x1400432c4  mov     [rax+18h], edi
0x1400432c7  mov     r12d, r8d
0x1400432ca  mov     [rsp+98h+arg_8], rdi
0x1400432d2  mov     rbp, rdx
0x1400432d5  mov     r15, rcx
0x1400432d8  lea     esi, [rdi+20h]
0x1400432db  test    r8d, r8d
0x1400432de  js      short loc_1400432E9
0x1400432e0  mov     eax, r9d
0x1400432e3  mov     [rbx+78h], rax
0x1400432e7  jmp     short loc_14004333B
0x1400432e9  mov     eax, cs:dword_1400876D0
0x1400432ef  cmp     eax, 2
0x1400432f2  jbe     short loc_14004333B
0x1400432f4  mov     rdx, rsi
0x1400432f7  lea     rcx, dword_1400876D0
0x1400432fe  call    _tlgKeywordOn
0x140043303  test    al, al
0x140043305  jz      short loc_14004333B
0x140043307  mov     rax, [rbx+78h]
0x14004330b  lea     rcx, aVhdmpicomplete_10; "VhdmpiCompleteOffloadRequest"
0x140043312  mov     [rsp+98h+var_68], rax
0x140043317  mov     edx, 1586h; int
0x14004331c  lea     rax, aOffloadEndFail; "offload end (failed) : status: %#08x le"...
0x140043323  mov     dword ptr [rsp+98h+var_70], r12d; char
0x140043328  mov     r9d, esi; int
0x14004332b  mov     [rsp+98h+var_78], rax; char *
0x140043330  mov     r8d, 2; int
0x140043336  call    TraceEvents
0x14004333b  mov     eax, cs:dword_1400876D0
0x140043341  cmp     eax, 5
0x140043344  jbe     short loc_1400433AE
0x140043346  mov     rdx, rsi
0x140043349  lea     rcx, dword_1400876D0
0x140043350  call    _tlgKeywordOn
0x140043355  test    al, al
0x140043357  jz      short loc_1400433AE
0x140043359  mov     rax, [rbx+70h]
0x14004335d  mov     ecx, edi
0x14004335f  cmp     [rbx+38h], edi
0x140043362  mov     edx, 1592h; int
0x140043367  mov     [rsp+98h+var_48], rax
0x14004336c  mov     r9d, esi; int
0x14004336f  mov     rax, [rbx+78h]
0x140043373  setz    cl
0x140043376  mov     [rsp+98h+var_50], rax
0x14004337b  mov     r8d, 5; int
0x140043381  mov     eax, [rbx+30h]
0x140043384  mov     [rsp+98h+var_58], r12d
0x140043389  mov     [rsp+98h+var_60], ecx
0x14004338d  lea     rcx, aVhdmpicomplete_10; "VhdmpiCompleteOffloadRequest"
0x140043394  mov     dword ptr [rsp+98h+var_68], eax
0x140043398  lea     rax, aOffloadSrbComp; "Offload SRB Completion: Request %p Tran"...
0x14004339f  mov     qword ptr [rsp+98h+var_70], rbp; char
0x1400433a4  mov     [rsp+98h+var_78], rax; char *
0x1400433a9  call    TraceEvents
0x1400433ae  mov     rax, [rbx+70h]
0x1400433b2  lea     rcx, [r15+50h]; SpinLock
0x1400433b6  mov     r13, [rbx+78h]
0x1400433ba  mov     [rsp+98h+arg_0], rax
0x1400433c2  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400433c9  nop     dword ptr [rax+rax+00h]
0x1400433ce  or      r9d, 0FFFFFFFFh
0x1400433d2  mov     [rbx+280h], r12d
0x1400433d9  add     [r15+29Ch], r9d
0x1400433e0  mov     r8b, al
0x1400433e3  mov     [rbx+50h], rdi
0x1400433e7  mov     [rbp+50h], rdi
0x1400433eb  mov     rcx, [rbx+58h]
0x1400433ef  test    rcx, rcx
0x1400433f2  jz      short loc_140043400
0x1400433f4  mov     [rsp+98h+arg_8], rcx
0x1400433fc  mov     [rbx+58h], rdi
0x140043400  mov     r14, [rbx+48h]
0x140043404  mov     esi, 4
0x140043409  mov     rdi, [rsp+98h+arg_28]
0x140043411  test    r14, r14
0x140043414  jz      short loc_14004343D
0x140043416  lea     rax, [rbx+20h]
0x14004341a  mov     qword ptr [rbx+48h], 0
0x140043422  mov     rdx, [rax]
0x140043425  cmp     [rdx+8], rax
0x140043429  jnz     short loc_140043481
0x14004342b  mov     rcx, [rax+8]
0x14004342f  cmp     [rcx], rax
0x140043432  jnz     short loc_140043481
0x140043434  mov     [rcx], rdx
0x140043437  mov     [rdx+8], rcx
0x14004343b  jmp     short loc_140043443
0x14004343d  cmp     dword ptr [rbx+38h], 1
0x140043441  jnz     short loc_140043465
0x140043443  mov     rcx, [rbx]
0x140043446  cmp     [rcx+8], rbx
0x14004344a  jnz     short loc_140043481
0x14004344c  mov     rax, [rbx+8]
0x140043450  cmp     [rax], rbx
0x140043453  jnz     short loc_140043481
0x140043455  mov     [rax], rcx
0x140043458  mov     [rcx+8], rax
0x14004345c  add     [r15+298h], r9d
0x140043463  jmp     short loc_14004349F
0x140043465  mov     rax, [rsp+98h+arg_20]
0x14004346d  lea     rcx, [r15+278h]
0x140043474  mov     [rbx+60h], rax
0x140043478  mov     rdx, [rcx+8]
0x14004347c  cmp     [rdx], rcx
0x14004347f  jz      short loc_140043488
0x140043481  mov     ecx, 3
0x140043486  int     29h; Win8: RtlFailFast(ecx)
0x140043488  lea     rax, [rbx+10h]
0x14004348c  mov     [rax], rcx
0x14004348f  mov     [rax+8], rdx
0x140043493  mov     [rdx], rax
0x140043496  mov     [rcx+8], rax
0x14004349a  or      [rdi+18h], esi
0x14004349d  xor     ebx, ebx
0x14004349f  mov     dl, r8b; NewIrql
0x1400434a2  lea     rcx, [r15+50h]; SpinLock
0x1400434a6  call    cs:__imp_KeReleaseSpinLock
0x1400434ad  nop     dword ptr [rax+rax+00h]
0x1400434b2  test    r12d, r12d
0x1400434b5  jns     loc_140043567
0x1400434bb  lea     rdx, [rsp+98h+arg_10]; struct _SCSI_SENSE_BYTES *
0x1400434c3  mov     ecx, r12d; int
0x1400434c6  call    ?VhdmpiCopyOffloadIrpStatusNeedsSpecificScsiSense@@YAEJPEAU_SCSI_SENSE_BYTES@@@Z; VhdmpiCopyOffloadIrpStatusNeedsSpecificScsiSense(long,_SCSI_SENSE_BYTES *)
0x1400434cb  test    al, al
0x1400434cd  jz      short loc_140043518
0x1400434cf  mov     al, [rsp+98h+arg_10]
0x1400434d6  xorps   xmm0, xmm0
0x1400434d9  mov     [rbp+25h], al
0x1400434dc  xor     eax, eax
0x1400434de  movups  xmmword ptr [rbp+2Ah], xmm0
0x1400434e2  mov     [rbp+3Ah], ax
0x1400434e6  mov     al, [rsp+98h+arg_11]
0x1400434ed  mov     word ptr [rbp+29h], 7001h
0x1400434f3  and     al, 0Fh
0x1400434f5  mov     cl, [rbp+2Ch]
0x1400434f8  and     cl, 0F0h
0x1400434fb  mov     byte ptr [rbp+31h], 0Ah
0x1400434ff  or      cl, al
0x140043501  mov     al, [rsp+98h+arg_12]
0x140043508  mov     [rbp+36h], al
0x14004350b  mov     al, [rsp+98h+arg_13]
0x140043512  mov     [rbp+37h], al
0x140043515  mov     [rbp+2Ch], cl
0x140043518  mov     eax, cs:dword_1400876D0
0x14004351e  cmp     eax, 5
0x140043521  jbe     loc_14004365A
0x140043527  mov     r9d, 2
0x14004352d  lea     rcx, dword_1400876D0
0x140043534  mov     edx, r9d
0x140043537  call    _tlgKeywordOn
0x14004353c  test    al, al
0x14004353e  jz      loc_14004365A
0x140043544  mov     rax, [rsp+98h+arg_0]
0x14004354c  mov     edx, 1610h
0x140043551  mov     [rsp+98h+var_68], r13
0x140043556  mov     qword ptr [rsp+98h+var_70], rax
0x14004355b  lea     rax, aVhdmpicomplete_19; "VhdmpiCompleteOffloadRequest() offload "...
0x140043562  jmp     loc_140043643
0x140043567  mov     r8, [rsp+98h+arg_0]
0x14004356f  cmp     r13, r8
0x140043572  jnz     short loc_1400435CB
0x140043574  mov     eax, cs:dword_1400876D0
0x14004357a  cmp     eax, 5
0x14004357d  jbe     short loc_1400435C3
0x14004357f  mov     r9d, 2
0x140043585  lea     rcx, dword_1400876D0
0x14004358c  mov     edx, r9d
0x14004358f  call    _tlgKeywordOn
0x140043594  test    al, al
0x140043596  jz      short loc_1400435C3
0x140043598  mov     [rsp+98h+var_68], r13
0x14004359d  lea     rax, aVhdmpicomplete_3; "VhdmpiCompleteOffloadRequest() offload "...
0x1400435a4  mov     qword ptr [rsp+98h+var_70], r8; char
0x1400435a9  lea     rcx, aVhdmpicomplete_10; "VhdmpiCompleteOffloadRequest"
0x1400435b0  lea     r8d, [r9+3]; int
0x1400435b4  mov     [rsp+98h+var_78], rax; char *
0x1400435b9  mov     edx, 161Ch; int
0x1400435be  call    TraceEvents
0x1400435c3  mov     sil, 1
0x1400435c6  jmp     loc_14004365A
0x1400435cb  xor     eax, eax
0x1400435cd  mov     r9d, 2
0x1400435d3  mov     [rbp+25h], r9b
0x1400435d7  xorps   xmm0, xmm0
0x1400435da  movups  xmmword ptr [rbp+2Ah], xmm0
0x1400435de  mov     [rbp+3Ah], ax
0x1400435e2  mov     word ptr [rbp+29h], 7001h
0x1400435e8  mov     al, [rbp+2Ch]
0x1400435eb  and     al, 0FBh
0x1400435ed  mov     byte ptr [rbp+31h], 0Ah
0x1400435f1  or      al, 0Bh
0x1400435f3  mov     word ptr [rbp+36h], 40Dh
0x1400435f9  mov     [rbp+2Ch], al
0x1400435fc  mov     rax, r13
0x1400435ff  mov     ecx, [r15+40h]
0x140043603  shr     rax, cl
0x140043606  bswap   eax
0x140043608  mov     [rbp+2Dh], eax
0x14004360b  mov     byte ptr [rbp+2Ah], 0F0h
0x14004360f  mov     eax, cs:dword_1400876D0
0x140043615  cmp     eax, 5
0x140043618  jbe     short loc_14004365A
0x14004361a  mov     edx, r9d
0x14004361d  lea     rcx, dword_1400876D0
0x140043624  call    _tlgKeywordOn
0x140043629  test    al, al
0x14004362b  jz      short loc_14004365A
0x14004362d  mov     [rsp+98h+var_68], r13
0x140043632  lea     rax, aVhdmpicomplete_13; "VhdmpiCompleteOffloadRequest() offload "...
0x140043639  mov     qword ptr [rsp+98h+var_70], r8; char
0x14004363e  mov     edx, 1635h; int
0x140043643  mov     r8d, 5; int
0x140043649  mov     [rsp+98h+var_78], rax; char *
0x14004364e  lea     rcx, aVhdmpicomplete_10; "VhdmpiCompleteOffloadRequest"
0x140043655  call    TraceEvents
0x14004365a  or      dword ptr [rdi+18h], 8
0x14004365e  mov     rbp, [rsp+98h+arg_8]
0x140043666  mov     qword ptr [rdi+20h], 0
0x14004366e  test    rbp, rbp
0x140043671  jz      short loc_140043690
0x140043673  mov     r8b, sil; unsigned __int8
0x140043676  mov     rdx, rbp; struct VHD_SCSI_REQUEST *
0x140043679  mov     rcx, r15; struct VHD_SCSI_STATE *
0x14004367c  call    ?VhdmpiUpdateCompletedScsiRequest@@YAXPEAUVHD_SCSI_STATE@@PEAUVHD_SCSI_REQUEST@@E@Z; VhdmpiUpdateCompletedScsiRequest(VHD_SCSI_STATE *,VHD_SCSI_REQUEST *,uchar)
0x140043681  mov     rax, [rdi+20h]
0x140043685  lea     rcx, [rbp+40h]
0x140043689  mov     [rcx], rax
0x14004368c  mov     [rdi+20h], rcx
0x140043690  test    r14, r14
0x140043693  jz      short loc_1400436BD
0x140043695  mov     rdx, rbx; struct _VHD_OFFLOAD_OP *
0x140043698  mov     rcx, r14; struct VHD_SCSI_REQUEST *
0x14004369b  call    ?VhdmpiReceiveRodTokenInformation@@YAXPEAUVHD_SCSI_REQUEST@@PEAU_VHD_OFFLOAD_OP@@@Z; VhdmpiReceiveRodTokenInformation(VHD_SCSI_REQUEST *,_VHD_OFFLOAD_OP *)
0x1400436a0  mov     r8b, 1; unsigned __int8
0x1400436a3  mov     rdx, r14; struct VHD_SCSI_REQUEST *
0x1400436a6  mov     rcx, r15; struct VHD_SCSI_STATE *
0x1400436a9  call    ?VhdmpiUpdateCompletedScsiRequest@@YAXPEAUVHD_SCSI_STATE@@PEAUVHD_SCSI_REQUEST@@E@Z; VhdmpiUpdateCompletedScsiRequest(VHD_SCSI_STATE *,VHD_SCSI_REQUEST *,uchar)
0x1400436ae  mov     rdx, [rdi+20h]
0x1400436b2  lea     r8, [r14+40h]
0x1400436b6  mov     [r8], rdx
0x1400436b9  mov     [rdi+20h], r8
0x1400436bd  test    rbx, rbx
0x1400436c0  jz      short loc_1400436D3
0x1400436c2  xor     edx, edx; Tag
0x1400436c4  mov     rcx, rbx; P
0x1400436c7  call    cs:__imp_ExFreePoolWithTag
0x1400436ce  nop     dword ptr [rax+rax+00h]
0x1400436d3  mov     rbx, [rsp+98h+arg_18]
0x1400436db  mov     al, sil
0x1400436de  add     rsp, 60h
0x1400436e2  pop     r15
0x1400436e4  pop     r14
0x1400436e6  pop     r13
0x1400436e8  pop     r12
0x1400436ea  pop     rdi
0x1400436eb  pop     rsi
0x1400436ec  pop     rbp
0x1400436ed  retn
```
