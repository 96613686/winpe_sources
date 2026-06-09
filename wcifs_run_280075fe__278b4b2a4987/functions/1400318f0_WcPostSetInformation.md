# WcPostSetInformation

- ea: `0x1400318f0`
- end: `0x140031e3a`
- name: `WcPostSetInformation`
- size: `1354`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA CallbackData)`
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
- `0x140029608`
- `0x14002ee54`
- `0x1400318f0`
- `0x140032500`
- `0x1400328d8`

## import_xrefs

- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140031dd1`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140031dd1`
- `ntoskrnl!ObfDereferenceObject` at `0x140031dbb`
- `ntoskrnl!ObfDereferenceObject` at `0x140031dbb`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140031da6`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140031da6`
- `FLTMGR!FltReleaseContext` at `0x140031de6`
- `FLTMGR!FltReleaseContext` at `0x140031dfb`
- `FLTMGR!FltReleaseContext` at `0x140031de6`
- `FLTMGR!FltReleaseContext` at `0x140031dfb`

## pseudocode

```c
__int64 __fastcall WcPostSetInformation(PFLT_CALLBACK_DATA CallbackData, __int64 a2, __int64 a3)
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
  char v32; // [rsp+38h] [rbp-51h]
  char v33; // [rsp+38h] [rbp-51h]
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
          v14 = WcRemoveInMemoryTombstoneAfterRenameLink((__int64)CallbackData, a2);
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
          v9 = WcRemoveInMemoryTombstoneAfterRenameLink((__int64)CallbackData, a2);
          if ( v9 < 0 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            v32 = v9;
            v10 = 20;
            v30 = -81;
LABEL_19:
            LOBYTE(v8) = 2;
            WPP_RECORDER_SF_sDd(
              WPP_GLOBAL_Control->DeviceExtension,
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
      v26 = WcRemoveInMemoryTombstoneAfterRenameLink((__int64)CallbackData, a2);
      if ( v26 < 0 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v33 = v26;
        v17 = 19;
        v31 = -105;
LABEL_53:
        LOBYTE(v15) = 2;
        WPP_RECORDER_SF_sDd(
          WPP_GLOBAL_Control->DeviceExtension,
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
      v16 = WcRemoveInMemoryTombstoneAfterRenameLink((__int64)CallbackData, a2);
      if ( v16 < 0 )
      {
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_54;
        v33 = v16;
        v17 = 16;
        v31 = 60;
        goto LABEL_53;
      }
      UnionContext = WcGetUnionContext(0, *(_QWORD *)(a2 + 24), *(_QWORD *)(a3 + 8));
      v6 = UnionContext;
      if ( UnionContext )
      {
        SetContextFileObject = WcGetSetContextFileObject(
                                 *(PFLT_INSTANCE *)(a2 + 24),
                                 *(PFILE_OBJECT *)(a3 + 8),
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
                        *(_BYTE *)(a3 + 16));
          if ( Tombstone >= 0 )
          {
            v25 = WcRemoveInMemoryTombstone(
                    *(struct _FLT_INSTANCE **)(a2 + 24),
                    *(_QWORD *)a3,
                    *(struct _FILE_OBJECT **)(a3 + 8));
            if ( v25 >= 0 )
              goto LABEL_54;
            if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              LOBYTE(v24) = 2;
              WPP_RECORDER_SF_sDd(
                WPP_GLOBAL_Control->DeviceExtension,
                v24,
                19,
                18,
                (__int64)WPP_62cdeb337fdf307834c1a2cccb2efbc6_Traceguids,
                (__int64)"onecore\\base\\fs\\wci\\wcifs\\fileinfo.c",
                127,
                v25);
            }
            if ( (unsigned int)dword_14000E060 <= 5
              || !(unsigned __int8)tlgKeywordOn(&dword_14000E060, 0x400000000000LL) )
            {
              goto LABEL_54;
            }
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
                WPP_GLOBAL_Control->DeviceExtension,
                v20,
                5,
                17,
                (__int64)WPP_62cdeb337fdf307834c1a2cccb2efbc6_Traceguids,
                (__int64)"onecore\\base\\fs\\wci\\wcifs\\fileinfo.c",
                108,
                Tombstone);
            }
            if ( (unsigned int)dword_14000E060 <= 5
              || !(unsigned __int8)tlgKeywordOn(&dword_14000E060, 0x400000000000LL) )
            {
              goto LABEL_54;
            }
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
      v27 = *(void **)(a3 + 8);
      if ( v27 )
        ObfDereferenceObject(v27);
      ExFreeToPagedLookasideList(&stru_14000E500, (PVOID)a3);
    }
    goto LABEL_60;
  }
  EaBuffer = Iopb->Parameters.Create.EaBuffer;
  if ( CallbackData->IoStatus.Status )
  {
    if ( Options == 13 && *EaBuffer == 1 || Options == 64 && (*(_DWORD *)EaBuffer & 1) != 0 )
    {
      v13 = WcRevertDelete(CallbackData, a2);
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
    v12 = WcRevertDelete(CallbackData, a2);
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
0x1400318f0  mov     [rsp-8+arg_18], rbx
0x1400318f5  push    rbp
0x1400318f6  push    rsi
0x1400318f7  push    rdi
0x1400318f8  push    r14
0x1400318fa  push    r15
0x1400318fc  lea     rbp, [rsp-37h]
0x140031901  sub     rsp, 0C0h
0x140031908  mov     rax, cs:__security_cookie
0x14003190f  xor     rax, rsp
0x140031912  mov     [rbp+57h+var_30], rax
0x140031916  xor     r15d, r15d
0x140031919  mov     r9, rcx
0x14003191c  mov     rdi, r8
0x14003191f  mov     [rbp+57h+var_90], r15
0x140031923  mov     r8, [rcx+10h]
0x140031927  mov     rbx, rdx
0x14003192a  mov     [rbp+57h+Context], r15
0x14003192e  mov     esi, r15d
0x140031931  mov     edx, [r8+20h]
0x140031935  mov     ecx, edx
0x140031937  sub     ecx, 0Ah
0x14003193a  jz      loc_140031AE0
0x140031940  sub     ecx, 1
0x140031943  jz      short loc_140031961
0x140031945  sub     ecx, 2
0x140031948  jz      short loc_1400319AB
0x14003194a  sub     ecx, 33h ; '3'
0x14003194d  jz      short loc_1400319AB
0x14003194f  sub     ecx, 1
0x140031952  jz      loc_140031AE0
0x140031958  cmp     ecx, 7
0x14003195b  jnz     loc_140031DDD
0x140031961  mov     rdx, rbx
0x140031964  mov     rcx, r9
0x140031967  cmp     [r9+18h], r15d
0x14003196b  jnz     loc_140031AA3
0x140031971  mov     r8b, 1
0x140031974  call    WcRemoveInMemoryTombstoneAfterRenameLink
0x140031979  mov     ecx, eax
0x14003197b  test    eax, eax
0x14003197d  jns     loc_140031E14
0x140031983  lea     rax, WPP_RECORDER_INITIALIZED
0x14003198a  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140031991  jz      loc_140031E14
0x140031997  mov     dword ptr [rsp+0E0h+var_A8], ecx
0x14003199b  mov     r9d, 14h
0x1400319a1  mov     dword ptr [rsp+0E0h+var_B0], 2AFh
0x1400319a9  jmp     short loc_140031A11
0x1400319ab  mov     rax, [r8+38h]
0x1400319af  cmp     [r9+18h], r15d
0x1400319b3  jnz     loc_140031A46
0x1400319b9  cmp     edx, 0Dh
0x1400319bc  jnz     short loc_1400319C3
0x1400319be  cmp     [rax], r15b
0x1400319c1  jz      short loc_1400319D6
0x1400319c3  cmp     edx, 40h ; '@'
0x1400319c6  jnz     loc_140031E14
0x1400319cc  mov     eax, [rax]
0x1400319ce  test    al, 1
0x1400319d0  jnz     loc_140031E14
0x1400319d6  mov     rdx, rbx
0x1400319d9  mov     rcx, r9; CallbackData
0x1400319dc  call    WcRevertDelete
0x1400319e1  mov     ecx, eax
0x1400319e3  test    eax, eax
0x1400319e5  jns     loc_140031E14
0x1400319eb  lea     rax, WPP_RECORDER_INITIALIZED
0x1400319f2  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400319f9  jz      loc_140031E14
0x1400319ff  mov     dword ptr [rsp+0E0h+var_A8], ecx
0x140031a03  mov     r9d, 16h
0x140031a09  mov     dword ptr [rsp+0E0h+var_B0], 2DDh
0x140031a11  mov     rcx, cs:WPP_GLOBAL_Control
0x140031a18  lea     rax, aOnecoreBaseFsW_8; "onecore\\base\\fs\\wci\\wcifs\\fileinfo"...
0x140031a1f  mov     [rsp+0E0h+var_B8], rax
0x140031a24  mov     r8d, 5
0x140031a2a  lea     rax, WPP_62cdeb337fdf307834c1a2cccb2efbc6_Traceguids
0x140031a31  mov     dl, 2
0x140031a33  mov     [rsp+0E0h+var_C0], rax
0x140031a38  mov     rcx, [rcx+40h]
0x140031a3c  call    WPP_RECORDER_SF_sDd
0x140031a41  jmp     loc_140031E14
0x140031a46  cmp     edx, 0Dh
0x140031a49  jnz     short loc_140031A50
0x140031a4b  cmp     byte ptr [rax], 1
0x140031a4e  jz      short loc_140031A63
0x140031a50  cmp     edx, 40h ; '@'
0x140031a53  jnz     loc_140031E14
0x140031a59  mov     eax, [rax]
0x140031a5b  test    al, 1
0x140031a5d  jz      loc_140031E14
0x140031a63  mov     rdx, rbx
0x140031a66  mov     rcx, r9; CallbackData
0x140031a69  call    WcRevertDelete
0x140031a6e  mov     ecx, eax
0x140031a70  test    eax, eax
0x140031a72  jns     loc_140031E14
0x140031a78  lea     rax, WPP_RECORDER_INITIALIZED
0x140031a7f  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140031a86  jz      loc_140031E14
0x140031a8c  mov     dword ptr [rsp+0E0h+var_A8], ecx
0x140031a90  mov     r9d, 17h
0x140031a96  mov     dword ptr [rsp+0E0h+var_B0], 2F9h
0x140031a9e  jmp     loc_140031A11
0x140031aa3  xor     r8d, r8d
0x140031aa6  call    WcRemoveInMemoryTombstoneAfterRenameLink
0x140031aab  mov     ecx, eax
0x140031aad  test    eax, eax
0x140031aaf  jns     loc_140031E14
0x140031ab5  lea     rax, WPP_RECORDER_INITIALIZED
0x140031abc  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140031ac3  jz      loc_140031E14
0x140031ac9  mov     dword ptr [rsp+0E0h+var_A8], ecx
0x140031acd  mov     r9d, 15h
0x140031ad3  mov     dword ptr [rsp+0E0h+var_B0], 2BCh
0x140031adb  jmp     loc_140031A11
0x140031ae0  mov     rdx, rbx
0x140031ae3  mov     rcx, r9
0x140031ae6  cmp     [r9+18h], r15d
0x140031aea  jnz     loc_140031D39
0x140031af0  xor     r8d, r8d
0x140031af3  call    WcRemoveInMemoryTombstoneAfterRenameLink
0x140031af8  mov     ecx, eax
0x140031afa  test    eax, eax
0x140031afc  jns     short loc_140031B29
0x140031afe  lea     rax, WPP_RECORDER_INITIALIZED
0x140031b05  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140031b0c  jz      loc_140031D99
0x140031b12  mov     dword ptr [rsp+0E0h+var_A8], ecx
0x140031b16  mov     r9d, 10h
0x140031b1c  mov     dword ptr [rsp+0E0h+var_B0], 23Ch
0x140031b24  jmp     loc_140031D69
0x140031b29  mov     r8, [rdi+8]
0x140031b2d  xor     ecx, ecx
0x140031b2f  mov     rdx, [rbx+18h]
0x140031b33  call    WcGetUnionContext
0x140031b38  mov     rsi, rax
0x140031b3b  test    rax, rax
0x140031b3e  jz      loc_140031D99
0x140031b44  mov     rdx, [rdi+8]; FileObject
0x140031b48  lea     rax, [rbp+57h+var_90]
0x140031b4c  mov     rcx, [rbx+18h]; Instance
0x140031b50  mov     r9d, 1
0x140031b56  mov     [rsp+0E0h+var_B0], rax; __int64
0x140031b5b  mov     r8, rsi
0x140031b5e  lea     rax, [rbp+57h+Context]
0x140031b62  mov     [rsp+0E0h+var_B8], rax; __int64
0x140031b67  call    WcGetSetContextFileObject
0x140031b6c  test    eax, eax
0x140031b6e  js      loc_140031D99
0x140031b74  cmp     eax, 104h
0x140031b79  jz      loc_140031D99
0x140031b7f  mov     rdx, [rdi]
0x140031b82  mov     r8b, [rdi+10h]
0x140031b86  add     rdx, 8
0x140031b8a  mov     rcx, [rbx+18h]; Instance
0x140031b8e  call    WcCreateTombstone
0x140031b93  mov     r14d, eax
0x140031b96  test    eax, eax
0x140031b98  jns     loc_140031C87
0x140031b9e  lea     rax, WPP_RECORDER_INITIALIZED
0x140031ba5  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140031bac  jz      short loc_140031BEF
0x140031bae  mov     rcx, cs:WPP_GLOBAL_Control
0x140031bb5  lea     rax, aOnecoreBaseFsW_8; "onecore\\base\\fs\\wci\\wcifs\\fileinfo"...
0x140031bbc  mov     dword ptr [rsp+0E0h+var_A8], r14d
0x140031bc1  mov     r9d, 11h
0x140031bc7  mov     dword ptr [rsp+0E0h+var_B0], 26Ch
0x140031bcf  mov     dl, 2
0x140031bd1  mov     [rsp+0E0h+var_B8], rax
0x140031bd6  lea     rax, WPP_62cdeb337fdf307834c1a2cccb2efbc6_Traceguids
0x140031bdd  mov     rcx, [rcx+40h]
0x140031be1  lea     r8d, [r9-0Ch]
0x140031be5  mov     [rsp+0E0h+var_C0], rax
0x140031bea  call    WPP_RECORDER_SF_sDd
0x140031bef  mov     eax, cs:dword_14000E060
0x140031bf5  cmp     eax, 5
0x140031bf8  jbe     loc_140031D99
0x140031bfe  mov     rdx, 400000000000h
0x140031c08  lea     rcx, dword_14000E060
0x140031c0f  call    _tlgKeywordOn
0x140031c14  test    al, al
0x140031c16  jz      loc_140031D99
0x140031c1c  lea     rax, [rbp+57h+var_A0]
0x140031c20  mov     [rbp+57h+var_A0], 1
0x140031c24  mov     [rbp+57h+var_60], rax
0x140031c28  lea     rdx, word_14000B63E
0x140031c2f  lea     rax, [rbp+57h+var_9F]
0x140031c33  mov     [rbp+57h+var_9C], r14d
0x140031c37  mov     [rbp+57h+var_50], rax
0x140031c3b  xor     r9d, r9d
0x140031c3e  lea     rax, [rbp+57h+var_9C]
0x140031c42  mov     [rbp+57h+var_38], 4
0x140031c4a  mov     [rbp+57h+var_40], rax
0x140031c4e  xor     r8d, r8d
0x140031c51  lea     rax, [rbp+57h+var_80]
0x140031c55  mov     [rbp+57h+var_48], 1
0x140031c5d  mov     [rsp+0E0h+var_B8], rax
0x140031c62  mov     dword ptr [rsp+0E0h+var_C0], 5
0x140031c6a  lea     rcx, dword_14000E060
0x140031c71  mov     [rbp+57h+var_9F], 2
0x140031c75  mov     [rbp+57h+var_58], 1
0x140031c7d  call    _tlgWriteTransfer_EtwWriteTransfer
0x140031c82  jmp     loc_140031D99
0x140031c87  mov     r8, [rdi+8]
0x140031c8b  mov     rdx, [rdi]
0x140031c8e  mov     rcx, [rbx+18h]
0x140031c92  call    WcRemoveInMemoryTombstone
0x140031c97  mov     ebx, eax
0x140031c99  test    eax, eax
0x140031c9b  jns     loc_140031D99
0x140031ca1  lea     rax, WPP_RECORDER_INITIALIZED
0x140031ca8  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140031caf  jz      short loc_140031CF1
0x140031cb1  mov     rcx, cs:WPP_GLOBAL_Control
0x140031cb8  lea     rax, aOnecoreBaseFsW_8; "onecore\\base\\fs\\wci\\wcifs\\fileinfo"...
0x140031cbf  mov     dword ptr [rsp+0E0h+var_A8], ebx
0x140031cc3  mov     r9d, 12h
0x140031cc9  mov     dword ptr [rsp+0E0h+var_B0], 27Fh
0x140031cd1  mov     dl, 2
0x140031cd3  mov     [rsp+0E0h+var_B8], rax
0x140031cd8  lea     rax, WPP_62cdeb337fdf307834c1a2cccb2efbc6_Traceguids
0x140031cdf  mov     rcx, [rcx+40h]
0x140031ce3  lea     r8d, [r9+1]
0x140031ce7  mov     [rsp+0E0h+var_C0], rax
0x140031cec  call    WPP_RECORDER_SF_sDd
0x140031cf1  mov     eax, cs:dword_14000E060
0x140031cf7  cmp     eax, 5
0x140031cfa  jbe     loc_140031D99
0x140031d00  mov     rdx, 400000000000h
0x140031d0a  lea     rcx, dword_14000E060
0x140031d11  call    _tlgKeywordOn
0x140031d16  test    al, al
0x140031d18  jz      short loc_140031D99
0x140031d1a  lea     rax, [rbp+57h+var_9F]
0x140031d1e  mov     [rbp+57h+var_A0], 2
0x140031d22  mov     [rbp+57h+var_60], rax
0x140031d26  lea     rdx, dword_14000B69C
0x140031d2d  lea     rax, [rbp+57h+var_A0]
0x140031d31  mov     [rbp+57h+var_9C], ebx
0x140031d34  jmp     loc_140031C37
0x140031d39  mov     r8b, 1
0x140031d3c  call    WcRemoveInMemoryTombstoneAfterRenameLink
0x140031d41  mov     ecx, eax
0x140031d43  test    eax, eax
0x140031d45  jns     short loc_140031D99
0x140031d47  lea     rax, WPP_RECORDER_INITIALIZED
0x140031d4e  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140031d55  jz      short loc_140031D99
0x140031d57  mov     dword ptr [rsp+0E0h+var_A8], ecx
0x140031d5b  mov     r9d, 13h
0x140031d61  mov     dword ptr [rsp+0E0h+var_B0], 297h
0x140031d69  mov     rcx, cs:WPP_GLOBAL_Control
0x140031d70  lea     rax, aOnecoreBaseFsW_8; "onecore\\base\\fs\\wci\\wcifs\\fileinfo"...
0x140031d77  mov     [rsp+0E0h+var_B8], rax
0x140031d7c  mov     r8d, 5
0x140031d82  lea     rax, WPP_62cdeb337fdf307834c1a2cccb2efbc6_Traceguids
0x140031d89  mov     dl, 2
0x140031d8b  mov     [rsp+0E0h+var_C0], rax
0x140031d90  mov     rcx, [rcx+40h]
0x140031d94  call    WPP_RECORDER_SF_sDd
0x140031d99  test    rdi, rdi
0x140031d9c  jz      short loc_140031DDD
0x140031d9e  mov     rcx, [rdi]; FileNameInformation
0x140031da1  test    rcx, rcx
0x140031da4  jz      short loc_140031DB2
0x140031da6  call    cs:__imp_FltReleaseFileNameInformation
0x140031dad  nop     dword ptr [rax+rax+00h]
0x140031db2  mov     rcx, [rdi+8]; Object
0x140031db6  test    rcx, rcx
0x140031db9  jz      short loc_140031DC7
0x140031dbb  call    cs:__imp_ObfDereferenceObject
0x140031dc2  nop     dword ptr [rax+rax+00h]
0x140031dc7  mov     rdx, rdi; Entry
0x140031dca  lea     rcx, stru_14000E500; Lookaside
0x140031dd1  call    cs:__imp_ExFreeToPagedLookasideList
0x140031dd8  nop     dword ptr [rax+rax+00h]
0x140031ddd  mov     rcx, [rbp+57h+Context]; Context
0x140031de1  test    rcx, rcx
0x140031de4  jz      short loc_140031DF2
0x140031de6  call    cs:__imp_FltReleaseContext
0x140031ded  nop     dword ptr [rax+rax+00h]
0x140031df2  mov     rcx, [rbp+57h+var_90]; Context
0x140031df6  test    rcx, rcx
0x140031df9  jz      short loc_140031E07
0x140031dfb  call    cs:__imp_FltReleaseContext
0x140031e02  nop     dword ptr [rax+rax+00h]
0x140031e07  test    rsi, rsi
0x140031e0a  jz      short loc_140031E14
0x140031e0c  mov     rcx, rsi
0x140031e0f  call    WcReleaseUnionContext
0x140031e14  xor     eax, eax
0x140031e16  mov     rcx, [rbp+57h+var_30]
0x140031e1a  xor     rcx, rsp; StackCookie
0x140031e1d  call    __security_check_cookie
0x140031e22  mov     rbx, [rsp+0E0h+arg_18]
0x140031e2a  add     rsp, 0C0h
0x140031e31  pop     r15
0x140031e33  pop     r14
  ... truncated ...
```
