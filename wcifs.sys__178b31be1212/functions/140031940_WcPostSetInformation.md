# WcPostSetInformation

- ea: `0x140031940`
- end: `0x140031e8a`
- name: `WcPostSetInformation`
- size: `1354`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA CallbackData, __int64, char *)`
- caller_count: `0`
- callee_count: `12`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x140001008`
- `0x140001030`
- `0x1400016f0`
- `0x1400020c4`
- `0x140007c60`
- `0x14001bf24`
- `0x14001ce88`
- `0x140029658`
- `0x14002eea4`
- `0x140031940`
- `0x140032550`
- `0x140032928`

## import_xrefs

- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140031e21`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140031e21`
- `ntoskrnl!ObfDereferenceObject` at `0x140031e0b`
- `ntoskrnl!ObfDereferenceObject` at `0x140031e0b`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140031df6`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140031df6`
- `FLTMGR!FltReleaseContext` at `0x140031e36`
- `FLTMGR!FltReleaseContext` at `0x140031e4b`
- `FLTMGR!FltReleaseContext` at `0x140031e36`
- `FLTMGR!FltReleaseContext` at `0x140031e4b`

## pseudocode

```c
__int64 __fastcall WcPostSetInformation(PFLT_CALLBACK_DATA CallbackData, __int64 a2, char *a3)
{
  PFLT_IO_PARAMETER_BLOCK Iopb; // r8
  __int64 v6; // rsi
  ULONG Options; // edx
  int v8; // edx
  int v9; // ecx
  int v10; // r9d
  _BYTE *EaBuffer; // rax
  int v12; // ecx
  int v13; // ecx
  int v14; // ecx
  int v15; // edx
  int v16; // ecx
  int v17; // r9d
  __int64 UnionContext; // rax
  int SetContextFileObject; // eax
  int v20; // edx
  int Tombstone; // r14d
  unsigned __int8 *v22; // rdx
  char *v23; // rax
  int v24; // edx
  int v25; // ebx
  int v26; // ecx
  void *v27; // rcx
  int v29; // [rsp+20h] [rbp-69h]
  char v30; // [rsp+30h] [rbp-59h]
  char v31; // [rsp+30h] [rbp-59h]
  int v32; // [rsp+38h] [rbp-51h]
  int v33; // [rsp+38h] [rbp-51h]
  char v34; // [rsp+40h] [rbp-49h] BYREF
  _BYTE v35[3]; // [rsp+41h] [rbp-48h] BYREF
  int v36; // [rsp+44h] [rbp-45h] BYREF
  PFLT_CONTEXT Context; // [rsp+48h] [rbp-41h] BYREF
  PFLT_CONTEXT v38[2]; // [rsp+50h] [rbp-39h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v39; // [rsp+60h] [rbp-29h] BYREF
  char *v40; // [rsp+80h] [rbp-9h]
  __int64 v41; // [rsp+88h] [rbp-1h]
  char *v42; // [rsp+90h] [rbp+7h]
  __int64 v43; // [rsp+98h] [rbp+Fh]
  int *v44; // [rsp+A0h] [rbp+17h]
  __int64 v45; // [rsp+A8h] [rbp+1Fh]

  v38[0] = 0;
  Iopb = CallbackData->Iopb;
  Context = 0;
  v6 = 0;
  Options = Iopb->Parameters.Create.Options;
  if ( Options == 10 )
    goto LABEL_30;
  if ( Iopb->Parameters.Create.Options == 11 )
    goto LABEL_7;
  if ( Iopb->Parameters.Create.Options != 13 && Iopb->Parameters.Create.Options != 64 )
  {
    if ( Iopb->Parameters.Create.Options != 65 )
    {
      if ( Iopb->Parameters.Create.Options == 72 )
      {
LABEL_7:
        if ( CallbackData->IoStatus.Status )
        {
          v14 = WcRemoveInMemoryTombstoneAfterRenameLink(CallbackData, a2, 0);
          if ( v14 < 0 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            v32 = v14;
            v10 = 21;
            v30 = -68;
            goto LABEL_19;
          }
        }
        else
        {
          LOBYTE(Iopb) = 1;
          v9 = WcRemoveInMemoryTombstoneAfterRenameLink(CallbackData, a2, Iopb);
          if ( v9 < 0 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            v32 = v9;
            v10 = 20;
            v30 = -81;
LABEL_19:
            LOBYTE(v8) = 2;
            WPP_RECORDER_SF_sDd(
              wil_details_featureDescriptors_a->DeviceExtension,
              v8,
              5,
              v10,
              (__int64)WPP_62cdeb337fdf307834c1a2cccb2efbc6_Traceguids,
              (__int64)"onecore\\base\\fs\\wci\\wcifs\\fileinfo.c",
              v30,
              v32);
            return 0;
          }
        }
        return 0;
      }
LABEL_60:
      if ( Context )
        FltReleaseContext(Context);
      if ( v38[0] )
        FltReleaseContext(v38[0]);
      if ( v6 )
        WcReleaseUnionContext(v6);
      return 0;
    }
LABEL_30:
    if ( CallbackData->IoStatus.Status )
    {
      LOBYTE(Iopb) = 1;
      v26 = WcRemoveInMemoryTombstoneAfterRenameLink(CallbackData, a2, Iopb);
      if ( v26 < 0 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v33 = v26;
        v17 = 19;
        v31 = -105;
LABEL_53:
        LOBYTE(v15) = 2;
        WPP_RECORDER_SF_sDd(
          wil_details_featureDescriptors_a->DeviceExtension,
          v15,
          5,
          v17,
          (__int64)WPP_62cdeb337fdf307834c1a2cccb2efbc6_Traceguids,
          (__int64)"onecore\\base\\fs\\wci\\wcifs\\fileinfo.c",
          v31,
          v33);
      }
    }
    else
    {
      v16 = WcRemoveInMemoryTombstoneAfterRenameLink(CallbackData, a2, 0);
      if ( v16 < 0 )
      {
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_54;
        v33 = v16;
        v17 = 16;
        v31 = 60;
        goto LABEL_53;
      }
      UnionContext = WcGetUnionContext(0, *(struct _FLT_INSTANCE **)(a2 + 24), *((struct _FILE_OBJECT **)a3 + 1));
      v6 = UnionContext;
      if ( UnionContext )
      {
        SetContextFileObject = WcGetSetContextFileObject(
                                 *(PFLT_INSTANCE *)(a2 + 24),
                                 *((PFILE_OBJECT *)a3 + 1),
                                 UnionContext,
                                 1,
                                 v29,
                                 &Context,
                                 v38);
        if ( SetContextFileObject >= 0 && SetContextFileObject != 260 )
        {
          Tombstone = WcCreateTombstone(
                        *(PFLT_INSTANCE *)(a2 + 24),
                        (struct _UNICODE_STRING *)(*(_QWORD *)a3 + 8LL),
                        a3[16]);
          if ( Tombstone >= 0 )
          {
            v25 = WcRemoveInMemoryTombstone(*(_QWORD *)(a2 + 24), *(_QWORD *)a3, *((_QWORD *)a3 + 1));
            if ( v25 >= 0 )
              goto LABEL_54;
            if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              LOBYTE(v24) = 2;
              WPP_RECORDER_SF_sDd(
                wil_details_featureDescriptors_a->DeviceExtension,
                v24,
                19,
                18,
                (__int64)WPP_62cdeb337fdf307834c1a2cccb2efbc6_Traceguids,
                (__int64)"onecore\\base\\fs\\wci\\wcifs\\fileinfo.c",
                127,
                v25);
            }
            if ( (unsigned int)dword_14000E060 <= 5 || !tlgKeywordOn((__int64)&dword_14000E060, 0x400000000000LL) )
              goto LABEL_54;
            v34 = 2;
            v40 = v35;
            v22 = (unsigned __int8 *)&dword_14000B69C;
            v23 = &v34;
            v36 = v25;
          }
          else
          {
            if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              LOBYTE(v20) = 2;
              WPP_RECORDER_SF_sDd(
                wil_details_featureDescriptors_a->DeviceExtension,
                v20,
                5,
                17,
                (__int64)WPP_62cdeb337fdf307834c1a2cccb2efbc6_Traceguids,
                (__int64)"onecore\\base\\fs\\wci\\wcifs\\fileinfo.c",
                108,
                Tombstone);
            }
            if ( (unsigned int)dword_14000E060 <= 5 || !tlgKeywordOn((__int64)&dword_14000E060, 0x400000000000LL) )
              goto LABEL_54;
            v34 = 1;
            v40 = &v34;
            v22 = (unsigned __int8 *)&word_14000B63E;
            v23 = v35;
            v36 = Tombstone;
          }
          v42 = v23;
          v45 = 4;
          v44 = &v36;
          v43 = 1;
          v35[0] = 2;
          v41 = 1;
          tlgWriteTransfer_EtwWriteTransfer((__int64)&dword_14000E060, v22, 0, 0, 5u, &v39);
        }
      }
    }
LABEL_54:
    if ( a3 )
    {
      if ( *(_QWORD *)a3 )
        FltReleaseFileNameInformation(*(PFLT_FILE_NAME_INFORMATION *)a3);
      v27 = (void *)*((_QWORD *)a3 + 1);
      if ( v27 )
        ObfDereferenceObject(v27);
      ExFreeToPagedLookasideList(&stru_14000E500, a3);
    }
    goto LABEL_60;
  }
  EaBuffer = Iopb->Parameters.Create.EaBuffer;
  if ( CallbackData->IoStatus.Status )
  {
    if ( Options == 13 && *EaBuffer == 1 || Options == 64 && (*(_DWORD *)EaBuffer & 1) != 0 )
    {
      v13 = WcRevertDelete(CallbackData);
      if ( v13 < 0 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v32 = v13;
        v10 = 23;
        v30 = -7;
        goto LABEL_19;
      }
    }
  }
  else if ( Options == 13 && !*EaBuffer || Options == 64 && (*(_DWORD *)EaBuffer & 1) == 0 )
  {
    v12 = WcRevertDelete(CallbackData);
    if ( v12 < 0 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v32 = v12;
      v10 = 22;
      v30 = -35;
      goto LABEL_19;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x140031940  mov     [rsp-8+arg_18], rbx
0x140031945  push    rbp
0x140031946  push    rsi
0x140031947  push    rdi
0x140031948  push    r14
0x14003194a  push    r15
0x14003194c  lea     rbp, [rsp-37h]
0x140031951  sub     rsp, 0C0h
0x140031958  mov     rax, cs:__security_cookie
0x14003195f  xor     rax, rsp
0x140031962  mov     [rbp+57h+var_30], rax
0x140031966  xor     r15d, r15d
0x140031969  mov     r9, rcx
0x14003196c  mov     rdi, r8
0x14003196f  mov     [rbp+57h+var_90], r15
0x140031973  mov     r8, [rcx+10h]
0x140031977  mov     rbx, rdx
0x14003197a  mov     [rbp+57h+Context], r15
0x14003197e  mov     esi, r15d
0x140031981  mov     edx, [r8+20h]
0x140031985  mov     ecx, edx
0x140031987  sub     ecx, 0Ah
0x14003198a  jz      loc_140031B30
0x140031990  sub     ecx, 1
0x140031993  jz      short loc_1400319B1
0x140031995  sub     ecx, 2
0x140031998  jz      short loc_1400319FB
0x14003199a  sub     ecx, 33h ; '3'
0x14003199d  jz      short loc_1400319FB
0x14003199f  sub     ecx, 1
0x1400319a2  jz      loc_140031B30
0x1400319a8  cmp     ecx, 7
0x1400319ab  jnz     loc_140031E2D
0x1400319b1  mov     rdx, rbx
0x1400319b4  mov     rcx, r9
0x1400319b7  cmp     [r9+18h], r15d
0x1400319bb  jnz     loc_140031AF3
0x1400319c1  mov     r8b, 1
0x1400319c4  call    WcRemoveInMemoryTombstoneAfterRenameLink
0x1400319c9  mov     ecx, eax
0x1400319cb  test    eax, eax
0x1400319cd  jns     loc_140031E64
0x1400319d3  lea     rax, WPP_RECORDER_INITIALIZED
0x1400319da  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400319e1  jz      loc_140031E64
0x1400319e7  mov     [rsp+0E0h+var_A8], ecx
0x1400319eb  mov     r9d, 14h
0x1400319f1  mov     dword ptr [rsp+0E0h+var_B0], 2AFh
0x1400319f9  jmp     short loc_140031A61
0x1400319fb  mov     rax, [r8+38h]
0x1400319ff  cmp     [r9+18h], r15d
0x140031a03  jnz     loc_140031A96
0x140031a09  cmp     edx, 0Dh
0x140031a0c  jnz     short loc_140031A13
0x140031a0e  cmp     [rax], r15b
0x140031a11  jz      short loc_140031A26
0x140031a13  cmp     edx, 40h ; '@'
0x140031a16  jnz     loc_140031E64
0x140031a1c  mov     eax, [rax]
0x140031a1e  test    al, 1
0x140031a20  jnz     loc_140031E64
0x140031a26  mov     rdx, rbx
0x140031a29  mov     rcx, r9; CallbackData
0x140031a2c  call    WcRevertDelete
0x140031a31  mov     ecx, eax
0x140031a33  test    eax, eax
0x140031a35  jns     loc_140031E64
0x140031a3b  lea     rax, WPP_RECORDER_INITIALIZED
0x140031a42  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140031a49  jz      loc_140031E64
0x140031a4f  mov     [rsp+0E0h+var_A8], ecx
0x140031a53  mov     r9d, 16h
0x140031a59  mov     dword ptr [rsp+0E0h+var_B0], 2DDh
0x140031a61  mov     rcx, cs:wil_details_featureDescriptors_a
0x140031a68  lea     rax, aOnecoreBaseFsW_8; "onecore\\base\\fs\\wci\\wcifs\\fileinfo"...
0x140031a6f  mov     [rsp+0E0h+var_B8], rax
0x140031a74  mov     r8d, 5
0x140031a7a  lea     rax, WPP_62cdeb337fdf307834c1a2cccb2efbc6_Traceguids
0x140031a81  mov     dl, 2
0x140031a83  mov     [rsp+0E0h+var_C0], rax
0x140031a88  mov     rcx, [rcx+40h]
0x140031a8c  call    WPP_RECORDER_SF_sDd
0x140031a91  jmp     loc_140031E64
0x140031a96  cmp     edx, 0Dh
0x140031a99  jnz     short loc_140031AA0
0x140031a9b  cmp     byte ptr [rax], 1
0x140031a9e  jz      short loc_140031AB3
0x140031aa0  cmp     edx, 40h ; '@'
0x140031aa3  jnz     loc_140031E64
0x140031aa9  mov     eax, [rax]
0x140031aab  test    al, 1
0x140031aad  jz      loc_140031E64
0x140031ab3  mov     rdx, rbx
0x140031ab6  mov     rcx, r9; CallbackData
0x140031ab9  call    WcRevertDelete
0x140031abe  mov     ecx, eax
0x140031ac0  test    eax, eax
0x140031ac2  jns     loc_140031E64
0x140031ac8  lea     rax, WPP_RECORDER_INITIALIZED
0x140031acf  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140031ad6  jz      loc_140031E64
0x140031adc  mov     [rsp+0E0h+var_A8], ecx
0x140031ae0  mov     r9d, 17h
0x140031ae6  mov     dword ptr [rsp+0E0h+var_B0], 2F9h
0x140031aee  jmp     loc_140031A61
0x140031af3  xor     r8d, r8d
0x140031af6  call    WcRemoveInMemoryTombstoneAfterRenameLink
0x140031afb  mov     ecx, eax
0x140031afd  test    eax, eax
0x140031aff  jns     loc_140031E64
0x140031b05  lea     rax, WPP_RECORDER_INITIALIZED
0x140031b0c  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140031b13  jz      loc_140031E64
0x140031b19  mov     [rsp+0E0h+var_A8], ecx
0x140031b1d  mov     r9d, 15h
0x140031b23  mov     dword ptr [rsp+0E0h+var_B0], 2BCh
0x140031b2b  jmp     loc_140031A61
0x140031b30  mov     rdx, rbx
0x140031b33  mov     rcx, r9
0x140031b36  cmp     [r9+18h], r15d
0x140031b3a  jnz     loc_140031D89
0x140031b40  xor     r8d, r8d
0x140031b43  call    WcRemoveInMemoryTombstoneAfterRenameLink
0x140031b48  mov     ecx, eax
0x140031b4a  test    eax, eax
0x140031b4c  jns     short loc_140031B79
0x140031b4e  lea     rax, WPP_RECORDER_INITIALIZED
0x140031b55  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140031b5c  jz      loc_140031DE9
0x140031b62  mov     [rsp+0E0h+var_A8], ecx
0x140031b66  mov     r9d, 10h
0x140031b6c  mov     dword ptr [rsp+0E0h+var_B0], 23Ch
0x140031b74  jmp     loc_140031DB9
0x140031b79  mov     r8, [rdi+8]
0x140031b7d  xor     ecx, ecx
0x140031b7f  mov     rdx, [rbx+18h]
0x140031b83  call    WcGetUnionContext
0x140031b88  mov     rsi, rax
0x140031b8b  test    rax, rax
0x140031b8e  jz      loc_140031DE9
0x140031b94  mov     rdx, [rdi+8]; FileObject
0x140031b98  lea     rax, [rbp+57h+var_90]
0x140031b9c  mov     rcx, [rbx+18h]; Instance
0x140031ba0  mov     r9d, 1
0x140031ba6  mov     [rsp+0E0h+var_B0], rax; __int64
0x140031bab  mov     r8, rsi
0x140031bae  lea     rax, [rbp+57h+Context]
0x140031bb2  mov     [rsp+0E0h+var_B8], rax; __int64
0x140031bb7  call    WcGetSetContextFileObject
0x140031bbc  test    eax, eax
0x140031bbe  js      loc_140031DE9
0x140031bc4  cmp     eax, 104h
0x140031bc9  jz      loc_140031DE9
0x140031bcf  mov     rdx, [rdi]
0x140031bd2  mov     r8b, [rdi+10h]
0x140031bd6  add     rdx, 8
0x140031bda  mov     rcx, [rbx+18h]; Instance
0x140031bde  call    WcCreateTombstone
0x140031be3  mov     r14d, eax
0x140031be6  test    eax, eax
0x140031be8  jns     loc_140031CD7
0x140031bee  lea     rax, WPP_RECORDER_INITIALIZED
0x140031bf5  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140031bfc  jz      short loc_140031C3F
0x140031bfe  mov     rcx, cs:wil_details_featureDescriptors_a
0x140031c05  lea     rax, aOnecoreBaseFsW_8; "onecore\\base\\fs\\wci\\wcifs\\fileinfo"...
0x140031c0c  mov     [rsp+0E0h+var_A8], r14d
0x140031c11  mov     r9d, 11h
0x140031c17  mov     dword ptr [rsp+0E0h+var_B0], 26Ch
0x140031c1f  mov     dl, 2
0x140031c21  mov     [rsp+0E0h+var_B8], rax
0x140031c26  lea     rax, WPP_62cdeb337fdf307834c1a2cccb2efbc6_Traceguids
0x140031c2d  mov     rcx, [rcx+40h]
0x140031c31  lea     r8d, [r9-0Ch]
0x140031c35  mov     [rsp+0E0h+var_C0], rax
0x140031c3a  call    WPP_RECORDER_SF_sDd
0x140031c3f  mov     eax, cs:dword_14000E060
0x140031c45  cmp     eax, 5
0x140031c48  jbe     loc_140031DE9
0x140031c4e  mov     rdx, 400000000000h
0x140031c58  lea     rcx, dword_14000E060
0x140031c5f  call    _tlgKeywordOn
0x140031c64  test    al, al
0x140031c66  jz      loc_140031DE9
0x140031c6c  lea     rax, [rbp+57h+var_A0]
0x140031c70  mov     [rbp+57h+var_A0], 1
0x140031c74  mov     [rbp+57h+var_60], rax
0x140031c78  lea     rdx, word_14000B63E
0x140031c7f  lea     rax, [rbp+57h+var_9F]
0x140031c83  mov     [rbp+57h+var_9C], r14d
0x140031c87  mov     [rbp+57h+var_50], rax
0x140031c8b  xor     r9d, r9d
0x140031c8e  lea     rax, [rbp+57h+var_9C]
0x140031c92  mov     [rbp+57h+var_38], 4
0x140031c9a  mov     [rbp+57h+var_40], rax
0x140031c9e  xor     r8d, r8d
0x140031ca1  lea     rax, [rbp+57h+var_80]
0x140031ca5  mov     [rbp+57h+var_48], 1
0x140031cad  mov     [rsp+0E0h+var_B8], rax
0x140031cb2  mov     dword ptr [rsp+0E0h+var_C0], 5
0x140031cba  lea     rcx, dword_14000E060
0x140031cc1  mov     [rbp+57h+var_9F], 2
0x140031cc5  mov     [rbp+57h+var_58], 1
0x140031ccd  call    _tlgWriteTransfer_EtwWriteTransfer
0x140031cd2  jmp     loc_140031DE9
0x140031cd7  mov     r8, [rdi+8]
0x140031cdb  mov     rdx, [rdi]
0x140031cde  mov     rcx, [rbx+18h]
0x140031ce2  call    WcRemoveInMemoryTombstone
0x140031ce7  mov     ebx, eax
0x140031ce9  test    eax, eax
0x140031ceb  jns     loc_140031DE9
0x140031cf1  lea     rax, WPP_RECORDER_INITIALIZED
0x140031cf8  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140031cff  jz      short loc_140031D41
0x140031d01  mov     rcx, cs:wil_details_featureDescriptors_a
0x140031d08  lea     rax, aOnecoreBaseFsW_8; "onecore\\base\\fs\\wci\\wcifs\\fileinfo"...
0x140031d0f  mov     [rsp+0E0h+var_A8], ebx
0x140031d13  mov     r9d, 12h
0x140031d19  mov     dword ptr [rsp+0E0h+var_B0], 27Fh
0x140031d21  mov     dl, 2
0x140031d23  mov     [rsp+0E0h+var_B8], rax
0x140031d28  lea     rax, WPP_62cdeb337fdf307834c1a2cccb2efbc6_Traceguids
0x140031d2f  mov     rcx, [rcx+40h]
0x140031d33  lea     r8d, [r9+1]
0x140031d37  mov     [rsp+0E0h+var_C0], rax
0x140031d3c  call    WPP_RECORDER_SF_sDd
0x140031d41  mov     eax, cs:dword_14000E060
0x140031d47  cmp     eax, 5
0x140031d4a  jbe     loc_140031DE9
0x140031d50  mov     rdx, 400000000000h
0x140031d5a  lea     rcx, dword_14000E060
0x140031d61  call    _tlgKeywordOn
0x140031d66  test    al, al
0x140031d68  jz      short loc_140031DE9
0x140031d6a  lea     rax, [rbp+57h+var_9F]
0x140031d6e  mov     [rbp+57h+var_A0], 2
0x140031d72  mov     [rbp+57h+var_60], rax
0x140031d76  lea     rdx, dword_14000B69C
0x140031d7d  lea     rax, [rbp+57h+var_A0]
0x140031d81  mov     [rbp+57h+var_9C], ebx
0x140031d84  jmp     loc_140031C87
0x140031d89  mov     r8b, 1
0x140031d8c  call    WcRemoveInMemoryTombstoneAfterRenameLink
0x140031d91  mov     ecx, eax
0x140031d93  test    eax, eax
0x140031d95  jns     short loc_140031DE9
0x140031d97  lea     rax, WPP_RECORDER_INITIALIZED
0x140031d9e  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140031da5  jz      short loc_140031DE9
0x140031da7  mov     [rsp+0E0h+var_A8], ecx
0x140031dab  mov     r9d, 13h
0x140031db1  mov     dword ptr [rsp+0E0h+var_B0], 297h
0x140031db9  mov     rcx, cs:wil_details_featureDescriptors_a
0x140031dc0  lea     rax, aOnecoreBaseFsW_8; "onecore\\base\\fs\\wci\\wcifs\\fileinfo"...
0x140031dc7  mov     [rsp+0E0h+var_B8], rax
0x140031dcc  mov     r8d, 5
0x140031dd2  lea     rax, WPP_62cdeb337fdf307834c1a2cccb2efbc6_Traceguids
0x140031dd9  mov     dl, 2
0x140031ddb  mov     [rsp+0E0h+var_C0], rax
0x140031de0  mov     rcx, [rcx+40h]
0x140031de4  call    WPP_RECORDER_SF_sDd
0x140031de9  test    rdi, rdi
0x140031dec  jz      short loc_140031E2D
0x140031dee  mov     rcx, [rdi]; FileNameInformation
0x140031df1  test    rcx, rcx
0x140031df4  jz      short loc_140031E02
0x140031df6  call    cs:__imp_FltReleaseFileNameInformation
0x140031dfd  nop     dword ptr [rax+rax+00h]
0x140031e02  mov     rcx, [rdi+8]; Object
0x140031e06  test    rcx, rcx
0x140031e09  jz      short loc_140031E17
0x140031e0b  call    cs:__imp_ObfDereferenceObject
0x140031e12  nop     dword ptr [rax+rax+00h]
0x140031e17  mov     rdx, rdi; Entry
0x140031e1a  lea     rcx, stru_14000E500; Lookaside
0x140031e21  call    cs:__imp_ExFreeToPagedLookasideList
0x140031e28  nop     dword ptr [rax+rax+00h]
0x140031e2d  mov     rcx, [rbp+57h+Context]; Context
0x140031e31  test    rcx, rcx
0x140031e34  jz      short loc_140031E42
0x140031e36  call    cs:__imp_FltReleaseContext
0x140031e3d  nop     dword ptr [rax+rax+00h]
0x140031e42  mov     rcx, [rbp+57h+var_90]; Context
0x140031e46  test    rcx, rcx
0x140031e49  jz      short loc_140031E57
0x140031e4b  call    cs:__imp_FltReleaseContext
0x140031e52  nop     dword ptr [rax+rax+00h]
0x140031e57  test    rsi, rsi
0x140031e5a  jz      short loc_140031E64
0x140031e5c  mov     rcx, rsi
0x140031e5f  call    WcReleaseUnionContext
0x140031e64  xor     eax, eax
0x140031e66  mov     rcx, [rbp+57h+var_30]
0x140031e6a  xor     rcx, rsp; StackCookie
0x140031e6d  call    __security_check_cookie
0x140031e72  mov     rbx, [rsp+0E0h+arg_18]
0x140031e7a  add     rsp, 0C0h
0x140031e81  pop     r15
0x140031e83  pop     r14
  ... truncated ...
```
