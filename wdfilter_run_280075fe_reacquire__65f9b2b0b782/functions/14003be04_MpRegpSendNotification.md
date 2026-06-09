# MpRegpSendNotification

- ea: `0x14003be04`
- end: `0x14003c3a7`
- name: `MpRegpSendNotification`
- size: `1443`
- prototype: ``
- caller_count: `16`
- callee_count: `16`
- tags: `authz_impersonation`

## callers

- `0x1400496d8`
- `0x140049ec0`
- `0x14004a930`
- `0x14004b990`
- `0x14004da60`
- `0x14004dda0`
- `0x14004ea60`
- `0x14004f9a8`
- `0x14004ffb0`
- `0x1400508c4`
- `0x14007dae8`
- `0x14007dd00`
- `0x14007df24`
- `0x14007e274`
- `0x14007ea68`
- `0x14007f16c`

## callees

- `0x140003950`
- `0x140003d20`
- `0x1400051bc`
- `0x140030060`
- `0x140034b50`
- `0x140035080`
- `0x140035100`
- `0x140035e50`
- `0x14003a1b0`
- `0x14003be04`
- `0x140050b88`
- `0x140056b50`
- `0x140056c20`
- `0x14006488c`
- `0x140069068`
- `0x14006c598`

## import_xrefs

- `ntoskrnl!CmGetBoundTransaction` at `0x14003c006`
- `ntoskrnl!CmGetBoundTransaction` at `0x14003c006`
- `ntoskrnl!PsGetProcessCreateTimeQuadPart` at `0x14003bf66`
- `ntoskrnl!PsGetProcessCreateTimeQuadPart` at `0x14003bf66`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14003bf7e`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14003bf7e`
- `ntoskrnl!IoGetCurrentProcess` at `0x14003be79`
- `ntoskrnl!IoGetCurrentProcess` at `0x14003bf57`
- `ntoskrnl!IoGetCurrentProcess` at `0x14003be79`
- `ntoskrnl!IoGetCurrentProcess` at `0x14003bf57`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14003bf47`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14003bf47`

## pseudocode

```c
__int64 __fastcall MpRegpSendNotification(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v3; // r14
  __int64 v4; // r15
  __int64 v6; // rsi
  __int64 v7; // rax
  bool v8; // bl
  struct _KPROCESS *CurrentProcess; // rax
  char ShouldSendBmMessage; // al
  int v11; // r9d
  char v12; // dl
  bool v13; // al
  char v14; // al
  char v15; // cl
  __int64 v16; // rax
  int v17; // eax
  int Notification; // ebx
  unsigned int v19; // r13d
  struct _KPROCESS *v20; // rax
  LONGLONG TimeQuadPart; // rax
  __int64 v22; // rdx
  __int64 v23; // rcx
  int SessionId; // eax
  PVOID BoundTransaction; // rax
  int TransactionId; // eax
  int v28; // eax
  __int64 v29; // rdx
  int v30; // [rsp+20h] [rbp-48h]
  char v31; // [rsp+30h] [rbp-38h]
  _BYTE v32[12]; // [rsp+38h] [rbp-30h] BYREF
  _OWORD v33[2]; // [rsp+48h] [rbp-20h] BYREF
  __int64 v35; // [rsp+B8h] [rbp+50h] BYREF
  unsigned int v36; // [rsp+C0h] [rbp+58h] BYREF
  int v37; // [rsp+C8h] [rbp+60h]

  v3 = 0;
  v4 = 0;
  *(_QWORD *)v32 = 0;
  v35 = 0;
  v6 = a1;
  if ( a2 )
  {
    v7 = *(_QWORD *)(a2 + 96);
    if ( !v7 || !*(_QWORD *)(v7 + 8) || !*(_DWORD *)v7 )
    {
      Notification = -1073741811;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
        return (unsigned int)Notification;
      WPP_SF_q(
        WPP_GLOBAL_Control->AttachedDevice,
        39,
        WPP_4435874bcd033210a8e834cab0696823_Traceguids,
        KeGetCurrentThread());
      goto LABEL_29;
    }
    v8 = (*(_DWORD *)(MpData + 868) & 4) != 0;
    if ( a1 )
    {
      v4 = a1;
    }
    else
    {
      CurrentProcess = IoGetCurrentProcess();
      MpGetProcessContextByObject(CurrentProcess);
      v4 = v35;
    }
    if ( !v4 )
      return 0;
    ShouldSendBmMessage = MpShouldSendBmMessage(v4, a2, a3, *(unsigned int *)(v4 + 56));
    v12 = 0;
    v13 = ShouldSendBmMessage != 0 && v8;
    if ( (v11 & 0x10) == 0 )
      v12 = v13;
    v14 = v12;
    if ( (*(_BYTE *)(v4 + 60) & 0x20) != 0 )
      v14 = 1;
    v15 = *(_BYTE *)(a2 + 92) & 2;
    if ( v15 )
      v14 = 1;
    v37 = v11 & 0x200000;
    v31 = v14;
    if ( (v11 & 0x200000) == 0 && !v14 )
    {
      Notification = 0;
LABEL_32:
      if ( v4 && !v6 )
        MpReleaseProcessContext(v4);
      return (unsigned int)Notification;
    }
    if ( v15 )
      v16 = *(_QWORD *)(v4 + 128);
    else
      v16 = 0;
    *(_QWORD *)(a2 + 112) = v16;
    LODWORD(v35) = 0;
    v36 = 0;
    v17 = MpRegpCalculateNotificationSize(a2, &v35, &v36);
    Notification = v17;
    if ( v17 < 0 )
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
        goto LABEL_29;
      v29 = 40;
      v30 = v17;
    }
    else
    {
      v19 = v35;
      Notification = MpAsyncCreateNotification(v32, (unsigned int)v35);
      if ( Notification < 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        {
          _mm_lfence();
          WPP_SF_qD(
            WPP_GLOBAL_Control->AttachedDevice,
            41,
            WPP_4435874bcd033210a8e834cab0696823_Traceguids,
            KeGetCurrentThread(),
            Notification);
        }
        v3 = *(_QWORD *)v32;
        goto LABEL_29;
      }
      _mm_lfence();
      v3 = *(_QWORD *)v32;
      *(_DWORD *)(*(_QWORD *)v32 + 16LL) = 1;
      *(_DWORD *)(v3 + 8) = v19;
      *(_DWORD *)(v3 + 64) = (unsigned int)PsGetCurrentProcessId();
      v20 = IoGetCurrentProcess();
      TimeQuadPart = PsGetProcessCreateTimeQuadPart(v20);
      *(_QWORD *)(v3 + 68) = MpFileTimeToUlong64(TimeQuadPart);
      *(_DWORD *)(v3 + 76) = (unsigned int)PsGetCurrentThreadId();
      *(_QWORD *)(v3 + 88) = *(_QWORD *)(a2 + 88);
      *(_DWORD *)(v3 + 112) = *(_DWORD *)(a2 + 48);
      *(_DWORD *)(v3 + 96) = *(_DWORD *)(a2 + 64);
      *(_DWORD *)(v3 + 128) = *(_DWORD *)(a2 + 72);
      *(_DWORD *)(v3 + 132) = *(_DWORD *)(a2 + 104);
      *(_BYTE *)(v3 + 168) = *(_BYTE *)(a2 + 108);
      SessionId = MpQuerySessionId(v23, v22, v3 + 80);
      if ( SessionId < 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        {
          _mm_lfence();
          WPP_SF_qD(
            WPP_GLOBAL_Control->AttachedDevice,
            42,
            WPP_4435874bcd033210a8e834cab0696823_Traceguids,
            KeGetCurrentThread(),
            SessionId);
        }
        *(_DWORD *)(v3 + 80) = 0;
      }
      *(_OWORD *)(v3 + 136) = 0;
      if ( *(_QWORD *)a2 )
      {
        BoundTransaction = CmGetBoundTransaction((PLARGE_INTEGER)MpRegData + 6, *(PVOID *)a2);
        if ( BoundTransaction )
        {
          TransactionId = MpQueryTransactionId(BoundTransaction, v3 + 136);
          if ( TransactionId < 0
            && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
          {
            _mm_lfence();
            WPP_SF_qD(
              WPP_GLOBAL_Control->AttachedDevice,
              43,
              WPP_4435874bcd033210a8e834cab0696823_Traceguids,
              KeGetCurrentThread(),
              TransactionId);
          }
        }
      }
      Notification = MpRegpCopyVariableNotificationData(a2, v3, v19, v36);
      if ( Notification < 0 )
      {
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
          goto LABEL_29;
        v29 = 44;
      }
      else
      {
        if ( v37 )
        {
          *(_DWORD *)v32 = *(_DWORD *)(v3 + 64);
          *(_QWORD *)&v32[4] = *(_QWORD *)(v3 + 68);
          v33[0] = 0;
          MpGetPriorityInfo(0, 0, v33);
          v28 = MpSendSyncMonitorNotification(2, (unsigned int)v32, v3, (unsigned int)v33, v4 + 56);
          if ( v28 < 0
            && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
          {
            _mm_lfence();
            WPP_SF_qD(
              WPP_GLOBAL_Control->AttachedDevice,
              45,
              WPP_4435874bcd033210a8e834cab0696823_Traceguids,
              KeGetCurrentThread(),
              v28);
          }
        }
        if ( !v31 || (Notification = MpAsyncSendNotification(v3, v19, 0, 1, v4), Notification >= 0) )
        {
          Notification = 0;
LABEL_29:
          if ( v3 )
            MpAsyncDereferenceNotification(v3);
          v6 = a1;
          goto LABEL_32;
        }
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
          goto LABEL_29;
        v29 = 46;
      }
      v30 = Notification;
    }
    _mm_lfence();
    WPP_SF_qD(
      WPP_GLOBAL_Control->AttachedDevice,
      v29,
      WPP_4435874bcd033210a8e834cab0696823_Traceguids,
      KeGetCurrentThread(),
      v30);
    goto LABEL_29;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    WPP_SF_q(
      WPP_GLOBAL_Control->AttachedDevice,
      38,
      WPP_4435874bcd033210a8e834cab0696823_Traceguids,
      KeGetCurrentThread());
  return (unsigned int)-1073741811;
}

```

## disassembly

```asm
0x14003be04  mov     [rsp-40h+arg_0], rcx
0x14003be09  push    rbp
0x14003be0a  push    rbx
0x14003be0b  push    rsi
0x14003be0c  push    rdi
0x14003be0d  push    r12
0x14003be0f  push    r13
0x14003be11  push    r14
0x14003be13  push    r15
0x14003be15  mov     rbp, rsp
0x14003be18  sub     rsp, 68h
0x14003be1c  xor     r14d, r14d
0x14003be1f  xor     r15d, r15d
0x14003be22  mov     [rbp+var_30], r14
0x14003be26  mov     r12, rdx
0x14003be29  mov     [rbp+arg_8], r15
0x14003be2d  mov     rsi, rcx
0x14003be30  test    rdx, rdx
0x14003be33  jz      loc_14003C227
0x14003be39  mov     rax, [rdx+60h]
0x14003be3d  test    rax, rax
0x14003be40  jz      loc_14003C1B2
0x14003be46  cmp     [rax+8], r14
0x14003be4a  jz      loc_14003C1B2
0x14003be50  cmp     [rax], r14d
0x14003be53  jz      loc_14003C1B2
0x14003be59  mov     rax, cs:MpData
0x14003be60  lea     edi, [r14+1]
0x14003be64  mov     ebx, [rax+364h]
0x14003be6a  shr     ebx, 2
0x14003be6d  and     bl, dil
0x14003be70  test    rcx, rcx
0x14003be73  jnz     loc_14003C0B4
0x14003be79  call    cs:__imp_IoGetCurrentProcess
0x14003be80  nop     dword ptr [rax+rax+00h]
0x14003be85  mov     rcx, rax; Process
0x14003be88  lea     rdx, [rbp+arg_8]
0x14003be8c  call    MpGetProcessContextByObject
0x14003be91  mov     r15, [rbp+arg_8]
0x14003be95  test    r15, r15
0x14003be98  jz      loc_14003C274
0x14003be9e  mov     r9d, [r15+38h]
0x14003bea2  mov     rcx, r15
0x14003bea5  call    MpShouldSendBmMessage
0x14003beaa  neg     al
0x14003beac  sbb     cl, cl
0x14003beae  xor     edx, edx
0x14003beb0  and     cl, bl
0x14003beb2  test    r9b, 10h
0x14003beb6  movzx   eax, cl
0x14003beb9  mov     cl, [r12+5Ch]
0x14003bebe  cmovz   edx, eax
0x14003bec1  test    byte ptr [r15+3Ch], 20h
0x14003bec6  movzx   eax, dl
0x14003bec9  cmovnz  eax, edi
0x14003becc  and     cl, 2
0x14003becf  movzx   eax, al
0x14003bed2  cmovnz  eax, edi
0x14003bed5  and     r9d, 200000h
0x14003bedc  mov     [rbp+arg_18], r9d
0x14003bee0  mov     dword ptr [rbp+var_38], eax
0x14003bee3  jnz     short loc_14003BEED
0x14003bee5  test    al, al
0x14003bee7  jz      loc_14003C0B0
0x14003beed  test    cl, cl
0x14003beef  jnz     loc_14003C27B
0x14003bef5  xor     eax, eax
0x14003bef7  mov     [r12+70h], rax
0x14003befc  lea     r8, [rbp+arg_10]
0x14003bf00  lea     rdx, [rbp+arg_8]
0x14003bf04  mov     dword ptr [rbp+arg_8], r14d
0x14003bf08  mov     rcx, r12
0x14003bf0b  mov     [rbp+arg_10], r14d
0x14003bf0f  call    MpRegpCalculateNotificationSize
0x14003bf14  mov     ebx, eax
0x14003bf16  test    eax, eax
0x14003bf18  js      loc_14003C287
0x14003bf1e  mov     r13d, dword ptr [rbp+arg_8]
0x14003bf22  lea     rcx, [rbp+var_30]
0x14003bf26  mov     edx, r13d
0x14003bf29  call    MpAsyncCreateNotification
0x14003bf2e  mov     ebx, eax
0x14003bf30  test    eax, eax
0x14003bf32  js      loc_14003C207
0x14003bf38  lfence
0x14003bf3b  mov     r14, [rbp+var_30]
0x14003bf3f  mov     [r14+10h], edi
0x14003bf43  mov     [r14+8], r13d
0x14003bf47  call    cs:__imp_PsGetCurrentProcessId
0x14003bf4e  nop     dword ptr [rax+rax+00h]
0x14003bf53  mov     [r14+40h], eax
0x14003bf57  call    cs:__imp_IoGetCurrentProcess
0x14003bf5e  nop     dword ptr [rax+rax+00h]
0x14003bf63  mov     rcx, rax; Process
0x14003bf66  call    cs:__imp_PsGetProcessCreateTimeQuadPart
0x14003bf6d  nop     dword ptr [rax+rax+00h]
0x14003bf72  mov     rcx, rax
0x14003bf75  call    MpFileTimeToUlong64
0x14003bf7a  mov     [r14+44h], rax
0x14003bf7e  call    cs:__imp_PsGetCurrentThreadId
0x14003bf85  nop     dword ptr [rax+rax+00h]
0x14003bf8a  mov     [r14+4Ch], eax
0x14003bf8e  lea     r8, [r14+50h]
0x14003bf92  mov     rax, [r12+58h]
0x14003bf97  mov     [r14+58h], rax
0x14003bf9b  mov     eax, [r12+30h]
0x14003bfa0  mov     [r14+70h], eax
0x14003bfa4  mov     eax, [r12+40h]
0x14003bfa9  mov     [r14+60h], eax
0x14003bfad  mov     eax, [r12+48h]
0x14003bfb2  mov     [r14+80h], eax
0x14003bfb9  mov     eax, [r12+68h]
0x14003bfbe  mov     [r14+84h], eax
0x14003bfc5  mov     al, [r12+6Ch]
0x14003bfca  mov     [r14+0A8h], al
0x14003bfd1  call    MpQuerySessionId
0x14003bfd6  lea     rsi, WPP_GLOBAL_Control
0x14003bfdd  test    eax, eax
0x14003bfdf  js      loc_14003C323
0x14003bfe5  lea     rbx, [r14+88h]
0x14003bfec  xorps   xmm0, xmm0
0x14003bfef  movups  xmmword ptr [rbx], xmm0
0x14003bff2  mov     rdx, [r12]; Object
0x14003bff6  test    rdx, rdx
0x14003bff9  jz      short loc_14003C01B
0x14003bffb  mov     rcx, cs:MpRegData
0x14003c002  add     rcx, 30h ; '0'; Cookie
0x14003c006  call    cs:__imp_CmGetBoundTransaction
0x14003c00d  nop     dword ptr [rax+rax+00h]
0x14003c012  test    rax, rax
0x14003c015  jnz     loc_14003C0BC
0x14003c01b  mov     r9d, [rbp+arg_10]
0x14003c01f  mov     r8d, r13d
0x14003c022  mov     rdx, r14
0x14003c025  mov     rcx, r12
0x14003c028  call    MpRegpCopyVariableNotificationData
0x14003c02d  mov     ebx, eax
0x14003c02f  test    eax, eax
0x14003c031  js      short loc_14003C067
0x14003c033  cmp     [rbp+arg_18], 0
0x14003c037  jnz     loc_14003C11C
0x14003c03d  cmp     [rbp+var_38], 0
0x14003c041  jz      short loc_14003C063
0x14003c043  mov     r9d, edi
0x14003c046  mov     qword ptr [rsp+68h+var_48], r15
0x14003c04b  xor     r8d, r8d
0x14003c04e  mov     edx, r13d
0x14003c051  mov     rcx, r14
0x14003c054  call    MpAsyncSendNotification
0x14003c059  mov     ebx, eax
0x14003c05b  test    eax, eax
0x14003c05d  js      loc_14003C381
0x14003c063  xor     ebx, ebx
0x14003c065  jmp     short loc_14003C077
0x14003c067  mov     rax, cs:WPP_GLOBAL_Control
0x14003c06e  cmp     rax, rsi
0x14003c071  jnz     loc_14003C370
0x14003c077  test    r14, r14
0x14003c07a  jz      short loc_14003C084
0x14003c07c  mov     rcx, r14
0x14003c07f  call    MpAsyncDereferenceNotification
0x14003c084  mov     rsi, [rbp+arg_0]
0x14003c088  test    r15, r15
0x14003c08b  jnz     short loc_14003C0A1
0x14003c08d  mov     eax, ebx
0x14003c08f  add     rsp, 68h
0x14003c093  pop     r15
0x14003c095  pop     r14
0x14003c097  pop     r13
0x14003c099  pop     r12
0x14003c09b  pop     rdi
0x14003c09c  pop     rsi
0x14003c09d  pop     rbx
0x14003c09e  pop     rbp
0x14003c09f  retn
0x14003c0a1  test    rsi, rsi
0x14003c0a4  jnz     short loc_14003C08D
0x14003c0a6  mov     rcx, r15
0x14003c0a9  call    MpReleaseProcessContext
0x14003c0ae  jmp     short loc_14003C08D
0x14003c0b0  xor     ebx, ebx
0x14003c0b2  jmp     short loc_14003C088
0x14003c0b4  mov     r15, rcx
0x14003c0b7  jmp     loc_14003BE95
0x14003c0bc  mov     rdx, rbx
0x14003c0bf  mov     rcx, rax
0x14003c0c2  call    MpQueryTransactionId
0x14003c0c7  test    eax, eax
0x14003c0c9  jns     loc_14003C01B
0x14003c0cf  mov     rcx, cs:WPP_GLOBAL_Control
0x14003c0d6  cmp     rcx, rsi
0x14003c0d9  jz      loc_14003C01B
0x14003c0df  mov     ecx, [rcx+2Ch]
0x14003c0e2  test    dil, cl
0x14003c0e5  jz      loc_14003C01B
0x14003c0eb  lfence
0x14003c0ee  mov     r9, gs:188h
0x14003c0f7  lea     r8, WPP_4435874bcd033210a8e834cab0696823_Traceguids
0x14003c0fe  mov     rcx, cs:WPP_GLOBAL_Control
0x14003c105  mov     edx, 2Bh ; '+'
0x14003c10a  mov     [rsp+68h+var_48], eax
0x14003c10e  mov     rcx, [rcx+18h]
0x14003c112  call    WPP_SF_qD
0x14003c117  jmp     loc_14003C01B
0x14003c11c  mov     eax, [r14+40h]
0x14003c120  lea     r8, [rbp+var_20]
0x14003c124  mov     dword ptr [rbp+var_30], eax
0x14003c127  xorps   xmm0, xmm0
0x14003c12a  mov     rax, [r14+44h]
0x14003c12e  xor     edx, edx
0x14003c130  xor     ecx, ecx
0x14003c132  mov     [rbp+var_30+4], rax
0x14003c136  movups  [rbp+var_20], xmm0
0x14003c13a  call    MpGetPriorityInfo
0x14003c13f  lea     rax, [r15+38h]
0x14003c143  mov     r8, r14
0x14003c146  lea     r9, [rbp+var_20]
0x14003c14a  mov     qword ptr [rsp+68h+var_48], rax
0x14003c14f  lea     rdx, [rbp+var_30]
0x14003c153  mov     ecx, 2
0x14003c158  call    MpSendSyncMonitorNotification
0x14003c15d  test    eax, eax
0x14003c15f  jns     loc_14003C03D
0x14003c165  mov     rcx, cs:WPP_GLOBAL_Control
0x14003c16c  cmp     rcx, rsi
0x14003c16f  jz      loc_14003C03D
0x14003c175  mov     ecx, [rcx+2Ch]
0x14003c178  test    dil, cl
0x14003c17b  jz      loc_14003C03D
0x14003c181  lfence
0x14003c184  mov     r9, gs:188h
0x14003c18d  lea     r8, WPP_4435874bcd033210a8e834cab0696823_Traceguids
0x14003c194  mov     rcx, cs:WPP_GLOBAL_Control
0x14003c19b  mov     edx, 2Dh ; '-'
0x14003c1a0  mov     [rsp+68h+var_48], eax
0x14003c1a4  mov     rcx, [rcx+18h]
0x14003c1a8  call    WPP_SF_qD
0x14003c1ad  jmp     loc_14003C03D
0x14003c1b2  mov     ebx, 0C000000Dh
0x14003c1b7  mov     rax, cs:WPP_GLOBAL_Control
0x14003c1be  lea     rsi, WPP_GLOBAL_Control
0x14003c1c5  cmp     rax, rsi
0x14003c1c8  jz      loc_14003C08D
0x14003c1ce  mov     eax, [rax+2Ch]
0x14003c1d1  mov     edi, 1
0x14003c1d6  test    dil, al
0x14003c1d9  jz      loc_14003C08D
0x14003c1df  mov     r9, gs:188h
0x14003c1e8  lea     edx, [rdi+26h]
0x14003c1eb  mov     rcx, cs:WPP_GLOBAL_Control
0x14003c1f2  lea     r8, WPP_4435874bcd033210a8e834cab0696823_Traceguids
0x14003c1f9  mov     rcx, [rcx+18h]
0x14003c1fd  call    WPP_SF_q
0x14003c202  jmp     loc_14003C077
0x14003c207  mov     rax, cs:WPP_GLOBAL_Control
0x14003c20e  lea     rsi, WPP_GLOBAL_Control
0x14003c215  cmp     rax, rsi
0x14003c218  jnz     loc_14003C2E6
0x14003c21e  mov     r14, [rbp+var_30]
0x14003c222  jmp     loc_14003C077
0x14003c227  mov     rax, cs:WPP_GLOBAL_Control
0x14003c22e  lea     rsi, WPP_GLOBAL_Control
0x14003c235  cmp     rax, rsi
0x14003c238  jz      short loc_14003C26A
0x14003c23a  mov     eax, [rax+2Ch]
0x14003c23d  mov     edi, 1
0x14003c242  test    dil, al
0x14003c245  jz      short loc_14003C26A
0x14003c247  mov     r9, gs:188h
0x14003c250  lea     edx, [rdi+25h]
0x14003c253  mov     rcx, cs:WPP_GLOBAL_Control
0x14003c25a  lea     r8, WPP_4435874bcd033210a8e834cab0696823_Traceguids
0x14003c261  mov     rcx, [rcx+18h]
0x14003c265  call    WPP_SF_q
0x14003c26a  mov     ebx, 0C000000Dh
0x14003c26f  jmp     loc_14003C08D
0x14003c274  xor     ebx, ebx
0x14003c276  jmp     loc_14003C08D
0x14003c27b  mov     rax, [r15+80h]
0x14003c282  jmp     loc_14003BEF7
0x14003c287  mov     rcx, cs:WPP_GLOBAL_Control
0x14003c28e  lea     rsi, WPP_GLOBAL_Control
0x14003c295  cmp     rcx, rsi
0x14003c298  jz      loc_14003C077
0x14003c29e  mov     ecx, [rcx+2Ch]
0x14003c2a1  test    dil, cl
0x14003c2a4  jz      loc_14003C077
0x14003c2aa  mov     edx, 28h ; '('
0x14003c2af  mov     [rsp+68h+var_48], eax
0x14003c2b3  jmp     short loc_14003C2BE
0x14003c2b5  mov     edx, 2Ch ; ','
0x14003c2ba  mov     [rsp+68h+var_48], ebx
0x14003c2be  lfence
0x14003c2c1  mov     r9, gs:188h
0x14003c2ca  lea     r8, WPP_4435874bcd033210a8e834cab0696823_Traceguids
0x14003c2d1  mov     rcx, cs:WPP_GLOBAL_Control
0x14003c2d8  mov     rcx, [rcx+18h]
0x14003c2dc  call    WPP_SF_qD
0x14003c2e1  jmp     loc_14003C077
0x14003c2e6  mov     eax, [rax+2Ch]
  ... truncated ...
```
