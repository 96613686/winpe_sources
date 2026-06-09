# VhdmpiCompleteOffloadRequest(VHD_SCSI_STATE *,VHD_SCSI_REQUEST *,long,ulong,unsigned __int64,VHD_SCSI_ACTION *)

- ea: `0x140042eb8`
- end: `0x1400432ff`
- name: `?VhdmpiCompleteOffloadRequest@@YAEPEAUVHD_SCSI_STATE@@PEAUVHD_SCSI_REQUEST@@JK_KPEAUVHD_SCSI_ACTION@@@Z`
- size: `1095`
- prototype: `unsigned __int8 __fastcall(struct VHD_SCSI_STATE *, struct VHD_SCSI_REQUEST *, int, unsigned int, unsigned __int64, struct VHD_SCSI_ACTION *)`
- caller_count: `5`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14000d080`
- `0x14000d920`
- `0x14000dd50`
- `0x14000f670`
- `0x140010f50`

## callees

- `0x14000efe0`
- `0x140023560`
- `0x140026d50`
- `0x140035e94`
- `0x140042eb8`
- `0x140043308`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400432d7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400432d7`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140042fd2`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140042fd2`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400430b6`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400430b6`

## string_xrefs

- `0x1400431ad`: `VhdmpiCompleteOffloadRequest() offload done (completely): RequestedTransferLength: %#016I64x TransferLength: %#016I64x`
- `0x140043242`: `VhdmpiCompleteOffloadRequest() offload done (truncation): RequestedTransferLength: %#016I64x TransferLength: %#016I64x`
- `0x140042f1b`: `VhdmpiCompleteOffloadRequest`
- `0x140042f9d`: `VhdmpiCompleteOffloadRequest`
- `0x1400431b9`: `VhdmpiCompleteOffloadRequest`
- `0x14004325e`: `VhdmpiCompleteOffloadRequest`
- `0x140042fa8`: `Offload SRB Completion: Request %p TransactionId:%d IsOffloadRead:%d status: %#08x length: %#016I64x requestedLength: %#016I64x`
- `0x14004316b`: `VhdmpiCompleteOffloadRequest() offload done (failed): RequestedTransferLength: %#016I64x TransferLength: %#016I64x`

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
  int v23; // r9d
  char v24; // r8
  int v25; // r9d
  char v26; // al
  char v27; // r8
  int v28; // r9d
  __int64 v30; // [rsp+A0h] [rbp+8h]
  struct VHD_SCSI_REQUEST *v31; // [rsp+A8h] [rbp+10h]
  int v32; // [rsp+B0h] [rbp+18h] BYREF

  v6 = (struct _VHD_OFFLOAD_OP *)*((_QWORD *)a2 + 10);
  v32 = 0;
  v31 = 0;
  if ( a3 < 0 )
  {
    if ( (unsigned int)dword_140087708 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 32) )
      TraceEvents(
        (int)"VhdmpiCompleteOffloadRequest",
        5510,
        2,
        32,
        "offload end (failed) : status: %#08x length: %#016I64x",
        a3);
  }
  else
  {
    *((_QWORD *)v6 + 15) = a4;
  }
  if ( (unsigned int)dword_140087708 > 5 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 32) )
    TraceEvents(
      (int)"VhdmpiCompleteOffloadRequest",
      5522,
      5,
      32,
      "Offload SRB Completion: Request %p TransactionId:%d IsOffloadRead:%d status: %#08x length: %#016I64x requestedLength: %#016I64x",
      (char)a2);
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
      if ( (unsigned int)dword_140087708 > 5 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 2) )
        TraceEvents(
          (int)"VhdmpiCompleteOffloadRequest",
          5660,
          v25 + 3,
          v25,
          "VhdmpiCompleteOffloadRequest() offload done (completely): RequestedTransferLength: %#016I64x TransferLength: %#016I64x",
          v24);
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
      if ( (unsigned int)dword_140087708 > 5 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 2) )
        TraceEvents(
          (int)"VhdmpiCompleteOffloadRequest",
          5685,
          5,
          v28,
          "VhdmpiCompleteOffloadRequest() offload done (truncation): RequestedTransferLength: %#016I64x TransferLength: %#016I64x",
          v27);
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
    if ( (unsigned int)dword_140087708 > 5 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 2) )
      TraceEvents(
        (int)"VhdmpiCompleteOffloadRequest",
        5648,
        5,
        v23,
        "VhdmpiCompleteOffloadRequest() offload done (failed): RequestedTransferLength: %#016I64x TransferLength: %#016I64x",
        v30);
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
0x140042eb8  mov     rax, rsp
0x140042ebb  mov     [rax+20h], rbx
0x140042ebf  push    rbp
0x140042ec0  push    rsi
0x140042ec1  push    rdi
0x140042ec2  push    r12
0x140042ec4  push    r13
0x140042ec6  push    r14
0x140042ec8  push    r15
0x140042eca  sub     rsp, 60h
0x140042ece  mov     rbx, [rdx+50h]
0x140042ed2  xor     edi, edi
0x140042ed4  mov     [rax+18h], edi
0x140042ed7  mov     r12d, r8d
0x140042eda  mov     [rsp+98h+arg_8], rdi
0x140042ee2  mov     rbp, rdx
0x140042ee5  mov     r15, rcx
0x140042ee8  lea     esi, [rdi+20h]
0x140042eeb  test    r8d, r8d
0x140042eee  js      short loc_140042EF9
0x140042ef0  mov     eax, r9d
0x140042ef3  mov     [rbx+78h], rax
0x140042ef7  jmp     short loc_140042F4B
0x140042ef9  mov     eax, cs:dword_140087708
0x140042eff  cmp     eax, 2
0x140042f02  jbe     short loc_140042F4B
0x140042f04  mov     rdx, rsi
0x140042f07  lea     rcx, dword_140087708
0x140042f0e  call    _tlgKeywordOn
0x140042f13  test    al, al
0x140042f15  jz      short loc_140042F4B
0x140042f17  mov     rax, [rbx+78h]
0x140042f1b  lea     rcx, aVhdmpicomplete_10; "VhdmpiCompleteOffloadRequest"
0x140042f22  mov     [rsp+98h+var_68], rax
0x140042f27  mov     edx, 1586h; int
0x140042f2c  lea     rax, aOffloadEndFail; "offload end (failed) : status: %#08x le"...
0x140042f33  mov     dword ptr [rsp+98h+var_70], r12d; char
0x140042f38  mov     r9d, esi; int
0x140042f3b  mov     [rsp+98h+var_78], rax; char *
0x140042f40  mov     r8d, 2; int
0x140042f46  call    TraceEvents
0x140042f4b  mov     eax, cs:dword_140087708
0x140042f51  cmp     eax, 5
0x140042f54  jbe     short loc_140042FBE
0x140042f56  mov     rdx, rsi
0x140042f59  lea     rcx, dword_140087708
0x140042f60  call    _tlgKeywordOn
0x140042f65  test    al, al
0x140042f67  jz      short loc_140042FBE
0x140042f69  mov     rax, [rbx+70h]
0x140042f6d  mov     ecx, edi
0x140042f6f  cmp     [rbx+38h], edi
0x140042f72  mov     edx, 1592h; int
0x140042f77  mov     [rsp+98h+var_48], rax
0x140042f7c  mov     r9d, esi; int
0x140042f7f  mov     rax, [rbx+78h]
0x140042f83  setz    cl
0x140042f86  mov     [rsp+98h+var_50], rax
0x140042f8b  mov     r8d, 5; int
0x140042f91  mov     eax, [rbx+30h]
0x140042f94  mov     [rsp+98h+var_58], r12d
0x140042f99  mov     [rsp+98h+var_60], ecx
0x140042f9d  lea     rcx, aVhdmpicomplete_10; "VhdmpiCompleteOffloadRequest"
0x140042fa4  mov     dword ptr [rsp+98h+var_68], eax
0x140042fa8  lea     rax, aOffloadSrbComp; "Offload SRB Completion: Request %p Tran"...
0x140042faf  mov     qword ptr [rsp+98h+var_70], rbp; char
0x140042fb4  mov     [rsp+98h+var_78], rax; char *
0x140042fb9  call    TraceEvents
0x140042fbe  mov     rax, [rbx+70h]
0x140042fc2  lea     rcx, [r15+50h]; SpinLock
0x140042fc6  mov     r13, [rbx+78h]
0x140042fca  mov     [rsp+98h+arg_0], rax
0x140042fd2  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140042fd9  nop     dword ptr [rax+rax+00h]
0x140042fde  or      r9d, 0FFFFFFFFh
0x140042fe2  mov     [rbx+280h], r12d
0x140042fe9  add     [r15+29Ch], r9d
0x140042ff0  mov     r8b, al
0x140042ff3  mov     [rbx+50h], rdi
0x140042ff7  mov     [rbp+50h], rdi
0x140042ffb  mov     rcx, [rbx+58h]
0x140042fff  test    rcx, rcx
0x140043002  jz      short loc_140043010
0x140043004  mov     [rsp+98h+arg_8], rcx
0x14004300c  mov     [rbx+58h], rdi
0x140043010  mov     r14, [rbx+48h]
0x140043014  mov     esi, 4
0x140043019  mov     rdi, [rsp+98h+arg_28]
0x140043021  test    r14, r14
0x140043024  jz      short loc_14004304D
0x140043026  lea     rax, [rbx+20h]
0x14004302a  mov     qword ptr [rbx+48h], 0
0x140043032  mov     rdx, [rax]
0x140043035  cmp     [rdx+8], rax
0x140043039  jnz     short loc_140043091
0x14004303b  mov     rcx, [rax+8]
0x14004303f  cmp     [rcx], rax
0x140043042  jnz     short loc_140043091
0x140043044  mov     [rcx], rdx
0x140043047  mov     [rdx+8], rcx
0x14004304b  jmp     short loc_140043053
0x14004304d  cmp     dword ptr [rbx+38h], 1
0x140043051  jnz     short loc_140043075
0x140043053  mov     rcx, [rbx]
0x140043056  cmp     [rcx+8], rbx
0x14004305a  jnz     short loc_140043091
0x14004305c  mov     rax, [rbx+8]
0x140043060  cmp     [rax], rbx
0x140043063  jnz     short loc_140043091
0x140043065  mov     [rax], rcx
0x140043068  mov     [rcx+8], rax
0x14004306c  add     [r15+298h], r9d
0x140043073  jmp     short loc_1400430AF
0x140043075  mov     rax, [rsp+98h+arg_20]
0x14004307d  lea     rcx, [r15+278h]
0x140043084  mov     [rbx+60h], rax
0x140043088  mov     rdx, [rcx+8]
0x14004308c  cmp     [rdx], rcx
0x14004308f  jz      short loc_140043098
0x140043091  mov     ecx, 3
0x140043096  int     29h; Win8: RtlFailFast(ecx)
0x140043098  lea     rax, [rbx+10h]
0x14004309c  mov     [rax], rcx
0x14004309f  mov     [rax+8], rdx
0x1400430a3  mov     [rdx], rax
0x1400430a6  mov     [rcx+8], rax
0x1400430aa  or      [rdi+18h], esi
0x1400430ad  xor     ebx, ebx
0x1400430af  mov     dl, r8b; NewIrql
0x1400430b2  lea     rcx, [r15+50h]; SpinLock
0x1400430b6  call    cs:__imp_KeReleaseSpinLock
0x1400430bd  nop     dword ptr [rax+rax+00h]
0x1400430c2  test    r12d, r12d
0x1400430c5  jns     loc_140043177
0x1400430cb  lea     rdx, [rsp+98h+arg_10]; struct _SCSI_SENSE_BYTES *
0x1400430d3  mov     ecx, r12d; int
0x1400430d6  call    ?VhdmpiCopyOffloadIrpStatusNeedsSpecificScsiSense@@YAEJPEAU_SCSI_SENSE_BYTES@@@Z; VhdmpiCopyOffloadIrpStatusNeedsSpecificScsiSense(long,_SCSI_SENSE_BYTES *)
0x1400430db  test    al, al
0x1400430dd  jz      short loc_140043128
0x1400430df  mov     al, [rsp+98h+arg_10]
0x1400430e6  xorps   xmm0, xmm0
0x1400430e9  mov     [rbp+25h], al
0x1400430ec  xor     eax, eax
0x1400430ee  movups  xmmword ptr [rbp+2Ah], xmm0
0x1400430f2  mov     [rbp+3Ah], ax
0x1400430f6  mov     al, [rsp+98h+arg_11]
0x1400430fd  mov     word ptr [rbp+29h], 7001h
0x140043103  and     al, 0Fh
0x140043105  mov     cl, [rbp+2Ch]
0x140043108  and     cl, 0F0h
0x14004310b  mov     byte ptr [rbp+31h], 0Ah
0x14004310f  or      cl, al
0x140043111  mov     al, [rsp+98h+arg_12]
0x140043118  mov     [rbp+36h], al
0x14004311b  mov     al, [rsp+98h+arg_13]
0x140043122  mov     [rbp+37h], al
0x140043125  mov     [rbp+2Ch], cl
0x140043128  mov     eax, cs:dword_140087708
0x14004312e  cmp     eax, 5
0x140043131  jbe     loc_14004326A
0x140043137  mov     r9d, 2
0x14004313d  lea     rcx, dword_140087708
0x140043144  mov     edx, r9d
0x140043147  call    _tlgKeywordOn
0x14004314c  test    al, al
0x14004314e  jz      loc_14004326A
0x140043154  mov     rax, [rsp+98h+arg_0]
0x14004315c  mov     edx, 1610h
0x140043161  mov     [rsp+98h+var_68], r13
0x140043166  mov     qword ptr [rsp+98h+var_70], rax
0x14004316b  lea     rax, aVhdmpicomplete_19; "VhdmpiCompleteOffloadRequest() offload "...
0x140043172  jmp     loc_140043253
0x140043177  mov     r8, [rsp+98h+arg_0]
0x14004317f  cmp     r13, r8
0x140043182  jnz     short loc_1400431DB
0x140043184  mov     eax, cs:dword_140087708
0x14004318a  cmp     eax, 5
0x14004318d  jbe     short loc_1400431D3
0x14004318f  mov     r9d, 2
0x140043195  lea     rcx, dword_140087708
0x14004319c  mov     edx, r9d
0x14004319f  call    _tlgKeywordOn
0x1400431a4  test    al, al
0x1400431a6  jz      short loc_1400431D3
0x1400431a8  mov     [rsp+98h+var_68], r13
0x1400431ad  lea     rax, aVhdmpicomplete_3; "VhdmpiCompleteOffloadRequest() offload "...
0x1400431b4  mov     qword ptr [rsp+98h+var_70], r8; char
0x1400431b9  lea     rcx, aVhdmpicomplete_10; "VhdmpiCompleteOffloadRequest"
0x1400431c0  lea     r8d, [r9+3]; int
0x1400431c4  mov     [rsp+98h+var_78], rax; char *
0x1400431c9  mov     edx, 161Ch; int
0x1400431ce  call    TraceEvents
0x1400431d3  mov     sil, 1
0x1400431d6  jmp     loc_14004326A
0x1400431db  xor     eax, eax
0x1400431dd  mov     r9d, 2
0x1400431e3  mov     [rbp+25h], r9b
0x1400431e7  xorps   xmm0, xmm0
0x1400431ea  movups  xmmword ptr [rbp+2Ah], xmm0
0x1400431ee  mov     [rbp+3Ah], ax
0x1400431f2  mov     word ptr [rbp+29h], 7001h
0x1400431f8  mov     al, [rbp+2Ch]
0x1400431fb  and     al, 0FBh
0x1400431fd  mov     byte ptr [rbp+31h], 0Ah
0x140043201  or      al, 0Bh
0x140043203  mov     word ptr [rbp+36h], 40Dh
0x140043209  mov     [rbp+2Ch], al
0x14004320c  mov     rax, r13
0x14004320f  mov     ecx, [r15+40h]
0x140043213  shr     rax, cl
0x140043216  bswap   eax
0x140043218  mov     [rbp+2Dh], eax
0x14004321b  mov     byte ptr [rbp+2Ah], 0F0h
0x14004321f  mov     eax, cs:dword_140087708
0x140043225  cmp     eax, 5
0x140043228  jbe     short loc_14004326A
0x14004322a  mov     edx, r9d
0x14004322d  lea     rcx, dword_140087708
0x140043234  call    _tlgKeywordOn
0x140043239  test    al, al
0x14004323b  jz      short loc_14004326A
0x14004323d  mov     [rsp+98h+var_68], r13
0x140043242  lea     rax, aVhdmpicomplete_13; "VhdmpiCompleteOffloadRequest() offload "...
0x140043249  mov     qword ptr [rsp+98h+var_70], r8; char
0x14004324e  mov     edx, 1635h; int
0x140043253  mov     r8d, 5; int
0x140043259  mov     [rsp+98h+var_78], rax; char *
0x14004325e  lea     rcx, aVhdmpicomplete_10; "VhdmpiCompleteOffloadRequest"
0x140043265  call    TraceEvents
0x14004326a  or      dword ptr [rdi+18h], 8
0x14004326e  mov     rbp, [rsp+98h+arg_8]
0x140043276  mov     qword ptr [rdi+20h], 0
0x14004327e  test    rbp, rbp
0x140043281  jz      short loc_1400432A0
0x140043283  mov     r8b, sil; unsigned __int8
0x140043286  mov     rdx, rbp; struct VHD_SCSI_REQUEST *
0x140043289  mov     rcx, r15; struct VHD_SCSI_STATE *
0x14004328c  call    ?VhdmpiUpdateCompletedScsiRequest@@YAXPEAUVHD_SCSI_STATE@@PEAUVHD_SCSI_REQUEST@@E@Z; VhdmpiUpdateCompletedScsiRequest(VHD_SCSI_STATE *,VHD_SCSI_REQUEST *,uchar)
0x140043291  mov     rax, [rdi+20h]
0x140043295  lea     rcx, [rbp+40h]
0x140043299  mov     [rcx], rax
0x14004329c  mov     [rdi+20h], rcx
0x1400432a0  test    r14, r14
0x1400432a3  jz      short loc_1400432CD
0x1400432a5  mov     rdx, rbx; struct _VHD_OFFLOAD_OP *
0x1400432a8  mov     rcx, r14; struct VHD_SCSI_REQUEST *
0x1400432ab  call    ?VhdmpiReceiveRodTokenInformation@@YAXPEAUVHD_SCSI_REQUEST@@PEAU_VHD_OFFLOAD_OP@@@Z; VhdmpiReceiveRodTokenInformation(VHD_SCSI_REQUEST *,_VHD_OFFLOAD_OP *)
0x1400432b0  mov     r8b, 1; unsigned __int8
0x1400432b3  mov     rdx, r14; struct VHD_SCSI_REQUEST *
0x1400432b6  mov     rcx, r15; struct VHD_SCSI_STATE *
0x1400432b9  call    ?VhdmpiUpdateCompletedScsiRequest@@YAXPEAUVHD_SCSI_STATE@@PEAUVHD_SCSI_REQUEST@@E@Z; VhdmpiUpdateCompletedScsiRequest(VHD_SCSI_STATE *,VHD_SCSI_REQUEST *,uchar)
0x1400432be  mov     rdx, [rdi+20h]
0x1400432c2  lea     r8, [r14+40h]
0x1400432c6  mov     [r8], rdx
0x1400432c9  mov     [rdi+20h], r8
0x1400432cd  test    rbx, rbx
0x1400432d0  jz      short loc_1400432E3
0x1400432d2  xor     edx, edx; Tag
0x1400432d4  mov     rcx, rbx; P
0x1400432d7  call    cs:__imp_ExFreePoolWithTag
0x1400432de  nop     dword ptr [rax+rax+00h]
0x1400432e3  mov     rbx, [rsp+98h+arg_18]
0x1400432eb  mov     al, sil
0x1400432ee  add     rsp, 60h
0x1400432f2  pop     r15
0x1400432f4  pop     r14
0x1400432f6  pop     r13
0x1400432f8  pop     r12
0x1400432fa  pop     rdi
0x1400432fb  pop     rsi
0x1400432fc  pop     rbp
0x1400432fd  retn
```
