# WcProcessSetRenameInformation

- ea: `0x140027f24`
- end: `0x14002856b`
- name: `WcProcessSetRenameInformation`
- size: `1607`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA CallbackData)`
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140027730`

## callees

- `0x140001008`
- `0x140001030`
- `0x140001500`
- `0x1400016f0`
- `0x140001b94`
- `0x140001bc8`
- `0x140001bf8`
- `0x1400020c4`
- `0x140004b0c`
- `0x140006324`
- `0x140007c60`
- `0x14001bcec`
- `0x14001f08c`
- `0x140027f24`
- `0x14002893c`
- `0x14002d5f8`
- `0x14002ee54`

## import_xrefs

- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140028460`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140028460`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x140028192`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x140028192`
- `ntoskrnl!ObfDereferenceObject` at `0x140028489`
- `ntoskrnl!ObfDereferenceObject` at `0x140028489`
- `FLTMGR!FltClose` at `0x140028475`
- `FLTMGR!FltClose` at `0x140028475`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140028445`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140028445`
- `FLTMGR!FltGetFileNameInformation` at `0x1400281ec`
- `FLTMGR!FltGetFileNameInformation` at `0x1400281ec`
- `FLTMGR!FltParseFileNameInformation` at `0x14002820a`
- `FLTMGR!FltParseFileNameInformation` at `0x14002820a`
- `FLTMGR!FltQueryInformationFile` at `0x1400280e8`
- `FLTMGR!FltQueryInformationFile` at `0x1400280e8`
- `FLTMGR!FltReleaseContext` at `0x14002849e`
- `FLTMGR!FltReleaseContext` at `0x1400284b6`
- `FLTMGR!FltReleaseContext` at `0x1400284ca`
- `FLTMGR!FltReleaseContext` at `0x1400284e2`
- `FLTMGR!FltReleaseContext` at `0x14002849e`
- `FLTMGR!FltReleaseContext` at `0x1400284b6`
- `FLTMGR!FltReleaseContext` at `0x1400284ca`
- `FLTMGR!FltReleaseContext` at `0x1400284e2`

## pseudocode

```c
__int64 __fastcall WcProcessSetRenameInformation(PFLT_CALLBACK_DATA CallbackData, __int64 a2, _QWORD *a3)
{
  PFLT_IO_PARAMETER_BLOCK Iopb; // rdx
  struct _FLT_INSTANCE *v6; // rcx
  NTSTATUS v7; // ebx
  struct _FILE_OBJECT *ParentOfTarget; // rdx
  _BYTE *v9; // rdi
  struct _FILE_OBJECT *v10; // r14
  __int64 v11; // r12
  int v12; // edx
  char v13; // r12
  void *v14; // r8
  void *v15; // rdx
  NTSTATUS v16; // eax
  int v17; // r9d
  int v18; // r8d
  _DWORD *v19; // rax
  _BYTE *v20; // rax
  __int16 v21; // cx
  __int16 v22; // ax
  __int64 v23; // rcx
  int v24; // eax
  int v25; // eax
  _QWORD *v26; // rax
  char v28; // [rsp+30h] [rbp-D0h]
  char v29; // [rsp+38h] [rbp-C8h]
  char v30; // [rsp+50h] [rbp-B0h] BYREF
  char v31; // [rsp+51h] [rbp-AFh] BYREF
  __int64 UnionContext; // [rsp+58h] [rbp-A8h]
  PFLT_FILE_NAME_INFORMATION FileNameInformation; // [rsp+60h] [rbp-A0h] BYREF
  PFLT_CONTEXT v34; // [rsp+68h] [rbp-98h] BYREF
  struct _FILE_OBJECT *v35; // [rsp+70h] [rbp-90h]
  ULONG LengthReturned; // [rsp+78h] [rbp-88h] BYREF
  PFLT_CONTEXT Context; // [rsp+80h] [rbp-80h]
  PFLT_CONTEXT v38; // [rsp+88h] [rbp-78h]
  PFLT_CONTEXT v39; // [rsp+90h] [rbp-70h]
  HANDLE FileHandle; // [rsp+98h] [rbp-68h]
  __m128i Name; // [rsp+A0h] [rbp-60h] BYREF
  _QWORD *v42; // [rsp+B0h] [rbp-50h]
  __int128 FileInformation; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v44; // [rsp+C8h] [rbp-38h]
  char v45[32]; // [rsp+D0h] [rbp-30h] BYREF
  char *v46; // [rsp+F0h] [rbp-10h]
  __int64 v47; // [rsp+F8h] [rbp-8h]
  char *v48; // [rsp+100h] [rbp+0h]
  __int64 v49; // [rsp+108h] [rbp+8h]
  PFLT_CONTEXT *v50; // [rsp+110h] [rbp+10h]
  __int64 v51; // [rsp+118h] [rbp+18h]

  v42 = a3;
  FileNameInformation = 0;
  Iopb = CallbackData->Iopb;
  LengthReturned = 0;
  Context = 0;
  v44 = 0;
  v6 = *(struct _FLT_INSTANCE **)(a2 + 24);
  Name = 0;
  v7 = 0;
  v38 = 0;
  FileInformation = 0;
  ParentOfTarget = Iopb->Parameters.SetFileInformation.ParentOfTarget;
  v34 = 0;
  v9 = 0;
  v39 = 0;
  v10 = 0;
  FileHandle = 0;
  v35 = 0;
  v30 = 0;
  if ( !(unsigned __int8)WcGetContextFileObject(v6, ParentOfTarget)
    || !(unsigned __int8)WcIsPlaceHolderDirectory(Context, v38)
    || !(unsigned __int8)WcIsUnionValid(*((_QWORD *)v38 + 5))
    || (v11 = 0, v7 = WcPrepareTargetDirectoryForRenameOrLink(CallbackData), v7 >= 0) )
  {
    UnionContext = WcGetUnionContext(CallbackData, *(_QWORD *)(a2 + 24), *(_QWORD *)(a2 + 32));
    v11 = UnionContext;
    if ( UnionContext )
    {
      v13 = 0;
      if ( (unsigned __int8)WcGetContextFileObject(*(PFLT_INSTANCE *)(a2 + 24), *(PFILE_OBJECT *)(a2 + 32)) )
      {
        v31 = 0;
        if ( (unsigned __int8)WcIsPlaceHolderDirectory(v34, v39) )
        {
          v13 = 1;
        }
        else if ( (unsigned __int8)WcIsPlaceHolderStream(v34, v39) )
        {
          v31 = 1;
        }
        else if ( !(unsigned __int8)WcIsPlaceHolder(v34) )
        {
          goto LABEL_15;
        }
        v14 = *(void **)(a2 + 32);
        v15 = *(void **)(a2 + 24);
        v30 = 1;
        v7 = WcSetPlaceHolderFlagsSynchronized(CallbackData, v15, v14);
        if ( v7 < 0 )
          goto LABEL_45;
        if ( v13 || v31 )
          goto LABEL_24;
      }
LABEL_15:
      v16 = FltQueryInformationFile(
              *(PFLT_INSTANCE *)(a2 + 24),
              *(PFILE_OBJECT *)(a2 + 32),
              &FileInformation,
              0x18u,
              FileStandardInformation,
              &LengthReturned);
      v7 = v16;
      if ( v16 < 0 )
      {
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
LABEL_19:
          v11 = UnionContext;
          goto LABEL_46;
        }
        v29 = v16;
        v17 = 10;
        v28 = -92;
        v18 = 13;
LABEL_18:
        LOBYTE(v12) = 2;
        WPP_RECORDER_SF_sDd(
          WPP_GLOBAL_Control->DeviceExtension,
          v12,
          v18,
          v17,
          (__int64)WPP_62cdeb337fdf307834c1a2cccb2efbc6_Traceguids,
          (__int64)"onecore\\base\\fs\\wci\\wcifs\\fileinfo.c",
          v28,
          v29);
        goto LABEL_19;
      }
      if ( BYTE5(v44) )
      {
        v13 = 1;
        goto LABEL_23;
      }
      if ( __PAIR16__(BYTE6(v44), 0) == HIBYTE(v44) )
      {
LABEL_23:
        if ( !v30 )
        {
          v19 = (_DWORD *)(UnionContext + 36);
          goto LABEL_26;
        }
LABEL_24:
        v19 = (_DWORD *)*((_QWORD *)v34 + 8);
LABEL_26:
        LODWORD(v34) = *v19;
        v20 = ExAllocateFromPagedLookasideList(&stru_14000E500);
        v9 = v20;
        if ( !v20 )
        {
          v7 = -1073741670;
          if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            goto LABEL_19;
          v29 = -102;
          v17 = 11;
          v28 = -61;
          v18 = 5;
          goto LABEL_18;
        }
        v20[16] = v13;
        v7 = FltGetFileNameInformation(CallbackData, 0x101u, &FileNameInformation);
        if ( v7 >= 0 )
        {
          v7 = FltParseFileNameInformation(FileNameInformation);
          if ( v7 >= 0 )
          {
            Name = (__m128i)FileNameInformation->Name;
            v21 = _mm_cvtsi128_si32(Name) - FileNameInformation->FinalComponent.Length;
            v22 = v21 - 2;
            Name.m128i_i16[0] = v21 - 2;
            if ( v21 - 2 == FileNameInformation->Volume.Length )
              v22 = v21;
            v23 = *(_QWORD *)(a2 + 24);
            Name.m128i_i16[0] = v22;
            v24 = WcOpenPlaceHolder(v23, &Name, 41, (unsigned int)v34);
            v7 = v24;
            if ( v24 < 0 )
            {
              if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              {
                LOBYTE(v12) = 2;
                WPP_RECORDER_SF_sDdZ(
                  WPP_GLOBAL_Control->DeviceExtension,
                  v12,
                  5,
                  12,
                  (__int64)WPP_62cdeb337fdf307834c1a2cccb2efbc6_Traceguids,
                  (__int64)"onecore\\base\\fs\\wci\\wcifs\\fileinfo.c",
                  242,
                  v24,
                  (__int64)&Name);
              }
              v10 = v35;
              goto LABEL_19;
            }
            v10 = v35;
            if ( v30 )
            {
              v25 = WcAddInMemoryTombstone(
                      (__int64)CallbackData,
                      *(struct _FLT_INSTANCE **)(a2 + 24),
                      &FileNameInformation->FinalComponent,
                      v9[16],
                      v35);
              v7 = v25;
              if ( v25 < 0 )
              {
                if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                {
                  LOBYTE(v12) = 2;
                  WPP_RECORDER_SF_sDd(
                    WPP_GLOBAL_Control->DeviceExtension,
                    v12,
                    5,
                    13,
                    (__int64)WPP_62cdeb337fdf307834c1a2cccb2efbc6_Traceguids,
                    (__int64)"onecore\\base\\fs\\wci\\wcifs\\fileinfo.c",
                    8,
                    v25);
                }
                if ( (unsigned int)dword_14000E060 > 5
                  && (unsigned __int8)tlgKeywordOn(&dword_14000E060, 0x400000000000LL) )
                {
                  v31 = 3;
                  v46 = &v31;
                  v47 = 1;
                  v48 = &v30;
                  v30 = 9;
                  v50 = &v34;
                  v49 = 1;
                  LODWORD(v34) = v7;
                  v51 = 4;
                  tlgWriteTransfer_EtwWriteTransfer(&dword_14000E060, word_14000B6FA, 0, 0, 5, v45);
                }
                goto LABEL_19;
              }
            }
            *(_QWORD *)v9 = FileNameInformation;
            v26 = v42;
            FileNameInformation = 0;
            *((_QWORD *)v9 + 1) = v10;
            v10 = 0;
            *v26 = v9;
            v9 = 0;
          }
        }
      }
LABEL_45:
      v11 = UnionContext;
    }
  }
LABEL_46:
  if ( FileNameInformation )
    FltReleaseFileNameInformation(FileNameInformation);
  if ( v9 )
    ExFreeToPagedLookasideList(&stru_14000E500, v9);
  if ( FileHandle )
    FltClose(FileHandle);
  if ( v10 )
    ObfDereferenceObject(v10);
  if ( Context )
    FltReleaseContext(Context);
  if ( v38 )
    FltReleaseContext(v38);
  if ( v39 )
    FltReleaseContext(v39);
  if ( v11 )
    WcReleaseUnionContext(v11);
  if ( v7 < 0 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v12) = 2;
    WPP_RECORDER_SF_sDd(
      WPP_GLOBAL_Control->DeviceExtension,
      v12,
      10,
      14,
      (__int64)WPP_62cdeb337fdf307834c1a2cccb2efbc6_Traceguids,
      (__int64)"onecore\\base\\fs\\wci\\wcifs\\fileinfo.c",
      78,
      v7);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x140027f24  mov     [rsp-8+arg_18], rbx
0x140027f29  push    rbp
0x140027f2a  push    rsi
0x140027f2b  push    rdi
0x140027f2c  push    r12
0x140027f2e  push    r13
0x140027f30  push    r14
0x140027f32  push    r15
0x140027f34  lea     rbp, [rsp-30h]
0x140027f39  sub     rsp, 130h
0x140027f40  mov     rax, cs:__security_cookie
0x140027f47  xor     rax, rsp
0x140027f4a  mov     [rbp+60h+var_40], rax
0x140027f4e  xor     r12d, r12d
0x140027f51  mov     [rbp+60h+var_B0], r8
0x140027f55  mov     rsi, rdx
0x140027f58  mov     [rsp+160h+FileNameInformation], r12
0x140027f5d  mov     rdx, [rcx+10h]
0x140027f61  lea     r9, [rbp+60h+var_D8]
0x140027f65  xorps   xmm0, xmm0
0x140027f68  mov     [rsp+160h+var_E8], r12d
0x140027f6d  xor     eax, eax
0x140027f6f  mov     [rbp+60h+Context], r12
0x140027f73  mov     r13, rcx
0x140027f76  mov     [rbp+60h+var_98], rax
0x140027f7a  mov     rcx, [rsi+18h]; Instance
0x140027f7e  lea     r8, [rbp+60h+Context]
0x140027f82  movups  [rbp+60h+var_C0], xmm0
0x140027f86  mov     ebx, r12d
0x140027f89  mov     [rbp+60h+var_D8], r12
0x140027f8d  movups  [rbp+60h+FileInformation], xmm0
0x140027f91  mov     rdx, [rdx+28h]; FileObject
0x140027f95  mov     r15d, r12d
0x140027f98  mov     [rsp+160h+var_F8], r12
0x140027f9d  mov     edi, r12d
0x140027fa0  mov     [rbp+60h+var_D0], r12
0x140027fa4  mov     r14d, r12d
0x140027fa7  mov     [rbp+60h+FileHandle], r12
0x140027fab  mov     [rsp+160h+var_F0], r12
0x140027fb0  mov     [rsp+160h+var_110], r12b
0x140027fb5  call    WcGetContextFileObject
0x140027fba  test    al, al
0x140027fbc  jz      short loc_140027FF8
0x140027fbe  mov     r12, [rbp+60h+var_D8]
0x140027fc2  mov     rcx, [rbp+60h+Context]
0x140027fc6  mov     rdx, r12
0x140027fc9  call    WcIsPlaceHolderDirectory
0x140027fce  test    al, al
0x140027fd0  jz      short loc_140027FF8
0x140027fd2  mov     rcx, [r12+28h]
0x140027fd7  call    WcIsUnionValid
0x140027fdc  test    al, al
0x140027fde  jz      short loc_140027FF8
0x140027fe0  mov     rdx, rsi
0x140027fe3  mov     rcx, r13; CallbackData
0x140027fe6  xor     r12d, r12d
0x140027fe9  call    WcPrepareTargetDirectoryForRenameOrLink
0x140027fee  mov     ebx, eax
0x140027ff0  test    eax, eax
0x140027ff2  js      loc_14002842D
0x140027ff8  mov     r8, [rsi+20h]
0x140027ffc  mov     rcx, r13
0x140027fff  mov     rdx, [rsi+18h]
0x140028003  call    WcGetUnionContext
0x140028008  mov     [rsp+160h+var_108], rax
0x14002800d  mov     r12, rax
0x140028010  test    rax, rax
0x140028013  jz      loc_14002842D
0x140028019  mov     rdx, [rsi+20h]; FileObject
0x14002801d  lea     r9, [rbp+60h+var_D0]
0x140028021  mov     rcx, [rsi+18h]; Instance
0x140028025  lea     r8, [rsp+160h+var_F8]
0x14002802a  xor     r12b, r12b
0x14002802d  call    WcGetContextFileObject
0x140028032  mov     r15, [rsp+160h+var_F8]
0x140028037  test    al, al
0x140028039  jz      loc_1400280C4
0x14002803f  mov     rbx, [rbp+60h+var_D0]
0x140028043  mov     rcx, r15
0x140028046  mov     rdx, rbx
0x140028049  mov     [rsp+160h+var_10F], dil
0x14002804e  call    WcIsPlaceHolderDirectory
0x140028053  test    al, al
0x140028055  jz      short loc_140028062
0x140028057  mov     r9d, 0Ah
0x14002805d  mov     r12b, 1
0x140028060  jmp     short loc_140028090
0x140028062  mov     rdx, rbx
0x140028065  mov     rcx, r15
0x140028068  call    WcIsPlaceHolderStream
0x14002806d  test    al, al
0x14002806f  jz      short loc_14002807E
0x140028071  mov     r9d, 0Ah
0x140028077  mov     [rsp+160h+var_10F], 1
0x14002807c  jmp     short loc_140028090
0x14002807e  mov     rcx, r15
0x140028081  call    WcIsPlaceHolder
0x140028086  test    al, al
0x140028088  jz      short loc_1400280C4
0x14002808a  mov     r9d, 2
0x140028090  mov     r8, [rsi+20h]; Object
0x140028094  mov     rcx, r13; CallbackData
0x140028097  mov     rdx, [rsi+18h]; FltObject
0x14002809b  mov     [rsp+160h+var_110], 1
0x1400280a0  call    WcSetPlaceHolderFlagsSynchronized
0x1400280a5  xor     ecx, ecx
0x1400280a7  mov     ebx, eax
0x1400280a9  test    eax, eax
0x1400280ab  js      loc_140028428
0x1400280b1  test    r12b, r12b
0x1400280b4  jnz     loc_140028176
0x1400280ba  cmp     [rsp+160h+var_10F], cl
0x1400280be  jnz     loc_140028176
0x1400280c4  mov     rdx, [rsi+20h]; FileObject
0x1400280c8  lea     rax, [rsp+160h+var_E8]
0x1400280cd  mov     rcx, [rsi+18h]; Instance
0x1400280d1  lea     r8, [rbp+60h+FileInformation]; FileInformation
0x1400280d5  mov     [rsp+160h+LengthReturned], rax; LengthReturned
0x1400280da  mov     r9d, 18h; Length
0x1400280e0  mov     [rsp+160h+FileInformationClass], 5; FileInformationClass
0x1400280e8  call    cs:__imp_FltQueryInformationFile
0x1400280ef  nop     dword ptr [rax+rax+00h]
0x1400280f4  xor     ecx, ecx
0x1400280f6  mov     ebx, eax
0x1400280f8  test    eax, eax
0x1400280fa  jns     short loc_140028154
0x1400280fc  lea     rsi, WPP_RECORDER_INITIALIZED
0x140028103  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x14002810a  lea     r13, aOnecoreBaseFsW_8; "onecore\\base\\fs\\wci\\wcifs\\fileinfo"...
0x140028111  jz      short loc_14002814A
0x140028113  mov     dword ptr [rsp+160h+var_128], eax
0x140028117  lea     r9d, [rcx+0Ah]
0x14002811b  mov     dword ptr [rsp+160h+var_130], 0A4h
0x140028123  lea     r8d, [rcx+0Dh]
0x140028127  mov     rcx, cs:WPP_GLOBAL_Control
0x14002812e  lea     rax, WPP_62cdeb337fdf307834c1a2cccb2efbc6_Traceguids
0x140028135  mov     [rsp+160h+LengthReturned], r13
0x14002813a  mov     dl, 2
0x14002813c  mov     qword ptr [rsp+160h+FileInformationClass], rax
0x140028141  mov     rcx, [rcx+40h]
0x140028145  call    WPP_RECORDER_SF_sDd
0x14002814a  mov     r12, [rsp+160h+var_108]
0x14002814f  jmp     loc_14002843B
0x140028154  cmp     byte ptr [rbp+60h+var_98+5], cl
0x140028157  jz      short loc_14002815E
0x140028159  mov     r12b, 1
0x14002815c  jmp     short loc_140028170
0x14002815e  cmp     byte ptr [rbp+60h+var_98+6], cl
0x140028161  jnz     loc_140028428
0x140028167  cmp     byte ptr [rbp+60h+var_98+7], cl
0x14002816a  jnz     loc_140028428
0x140028170  cmp     [rsp+160h+var_110], cl
0x140028174  jz      short loc_14002817C
0x140028176  mov     rax, [r15+40h]
0x14002817a  jmp     short loc_140028185
0x14002817c  mov     rax, [rsp+160h+var_108]
0x140028181  add     rax, 24h ; '$'
0x140028185  mov     eax, [rax]
0x140028187  lea     rcx, stru_14000E500; Lookaside
0x14002818e  mov     dword ptr [rsp+160h+var_F8], eax
0x140028192  call    cs:__imp_ExAllocateFromPagedLookasideList
0x140028199  nop     dword ptr [rax+rax+00h]
0x14002819e  mov     rdi, rax
0x1400281a1  test    rax, rax
0x1400281a4  jnz     short loc_1400281DB
0x1400281a6  mov     ebx, 0C000009Ah
0x1400281ab  lea     rsi, WPP_RECORDER_INITIALIZED
0x1400281b2  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x1400281b9  lea     r13, aOnecoreBaseFsW_8; "onecore\\base\\fs\\wci\\wcifs\\fileinfo"...
0x1400281c0  jz      short loc_14002814A
0x1400281c2  mov     dword ptr [rsp+160h+var_128], ebx
0x1400281c6  lea     r9d, [rax+0Bh]
0x1400281ca  mov     dword ptr [rsp+160h+var_130], 0C3h
0x1400281d2  lea     r8d, [rax+5]
0x1400281d6  jmp     loc_140028127
0x1400281db  lea     r8, [rsp+160h+FileNameInformation]; FileNameInformation
0x1400281e0  mov     [rax+10h], r12b
0x1400281e4  mov     edx, 101h; NameOptions
0x1400281e9  mov     rcx, r13; CallbackData
0x1400281ec  call    cs:__imp_FltGetFileNameInformation
0x1400281f3  nop     dword ptr [rax+rax+00h]
0x1400281f8  xor     r12d, r12d
0x1400281fb  mov     ebx, eax
0x1400281fd  test    eax, eax
0x1400281ff  js      loc_140028428
0x140028205  mov     rcx, [rsp+160h+FileNameInformation]; FileNameInformation
0x14002820a  call    cs:__imp_FltParseFileNameInformation
0x140028211  nop     dword ptr [rax+rax+00h]
0x140028216  mov     ebx, eax
0x140028218  test    eax, eax
0x14002821a  js      loc_140028428
0x140028220  mov     rdx, [rsp+160h+FileNameInformation]
0x140028225  lea     r8d, [r12+29h]
0x14002822a  mov     r9d, dword ptr [rsp+160h+var_F8]
0x14002822f  movups  xmm0, xmmword ptr [rdx+8]
0x140028233  movd    ecx, xmm0
0x140028237  movups  [rbp+60h+var_C0], xmm0
0x14002823b  sub     cx, [rdx+58h]
0x14002823f  lea     eax, [rcx-2]
0x140028242  mov     word ptr [rbp+60h+var_C0], ax
0x140028246  cmp     ax, [rdx+18h]
0x14002824a  lea     rdx, [rbp+60h+var_C0]
0x14002824e  cmovz   ax, cx
0x140028252  mov     rcx, [rsi+18h]
0x140028256  mov     word ptr [rbp+60h+var_C0], ax
0x14002825a  lea     rax, [rsp+160h+var_110]
0x14002825f  mov     [rsp+160h+var_130], rax
0x140028264  lea     rax, [rsp+160h+var_F0]
0x140028269  mov     [rsp+160h+LengthReturned], rax
0x14002826e  lea     rax, [rbp+60h+FileHandle]
0x140028272  mov     qword ptr [rsp+160h+FileInformationClass], rax
0x140028277  call    WcOpenPlaceHolder
0x14002827c  mov     ebx, eax
0x14002827e  test    eax, eax
0x140028280  jns     short loc_1400282E5
0x140028282  lea     rsi, WPP_RECORDER_INITIALIZED
0x140028289  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140028290  lea     r13, aOnecoreBaseFsW_8; "onecore\\base\\fs\\wci\\wcifs\\fileinfo"...
0x140028297  jz      short loc_1400282DB
0x140028299  mov     rcx, cs:WPP_GLOBAL_Control
0x1400282a0  lea     rax, [rbp+60h+var_C0]
0x1400282a4  mov     [rsp+160h+var_120], rax
0x1400282a9  lea     r9d, [r12+0Ch]
0x1400282ae  mov     dword ptr [rsp+160h+var_128], ebx
0x1400282b2  lea     rax, WPP_62cdeb337fdf307834c1a2cccb2efbc6_Traceguids
0x1400282b9  mov     dword ptr [rsp+160h+var_130], 0F2h
0x1400282c1  lea     r8d, [r12+5]
0x1400282c6  mov     rcx, [rcx+40h]
0x1400282ca  mov     dl, 2
0x1400282cc  mov     [rsp+160h+LengthReturned], r13
0x1400282d1  mov     qword ptr [rsp+160h+FileInformationClass], rax
0x1400282d6  call    WPP_RECORDER_SF_sDdZ
0x1400282db  mov     r14, [rsp+160h+var_F0]
0x1400282e0  jmp     loc_14002814A
0x1400282e5  mov     r14, [rsp+160h+var_F0]
0x1400282ea  cmp     [rsp+160h+var_110], r12b
0x1400282ef  jz      loc_14002840A
0x1400282f5  mov     r8, [rsp+160h+FileNameInformation]
0x1400282fa  mov     rcx, r13
0x1400282fd  mov     r9b, [rdi+10h]
0x140028301  add     r8, 58h ; 'X'
0x140028305  mov     rdx, [rsi+18h]
0x140028309  mov     qword ptr [rsp+160h+FileInformationClass], r14
0x14002830e  call    WcAddInMemoryTombstone
0x140028313  mov     ebx, eax
0x140028315  test    eax, eax
0x140028317  jns     loc_14002840A
0x14002831d  lea     rsi, WPP_RECORDER_INITIALIZED
0x140028324  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x14002832b  lea     r13, aOnecoreBaseFsW_8; "onecore\\base\\fs\\wci\\wcifs\\fileinfo"...
0x140028332  jz      short loc_14002836D
0x140028334  mov     rcx, cs:WPP_GLOBAL_Control
0x14002833b  mov     r9d, 0Dh
0x140028341  mov     dword ptr [rsp+160h+var_128], eax
0x140028345  mov     dl, 2
0x140028347  mov     dword ptr [rsp+160h+var_130], 108h
0x14002834f  lea     rax, WPP_62cdeb337fdf307834c1a2cccb2efbc6_Traceguids
0x140028356  mov     [rsp+160h+LengthReturned], r13
0x14002835b  mov     rcx, [rcx+40h]
0x14002835f  lea     r8d, [r9-8]
0x140028363  mov     qword ptr [rsp+160h+FileInformationClass], rax
0x140028368  call    WPP_RECORDER_SF_sDd
0x14002836d  mov     eax, cs:dword_14000E060
0x140028373  cmp     eax, 5
0x140028376  jbe     loc_14002814A
0x14002837c  mov     rdx, 400000000000h
0x140028386  lea     rcx, dword_14000E060
0x14002838d  call    _tlgKeywordOn
0x140028392  test    al, al
0x140028394  jz      loc_14002814A
0x14002839a  lea     rax, [rsp+160h+var_10F]
0x14002839f  mov     [rsp+160h+var_10F], 3
0x1400283a4  mov     [rbp+60h+var_70], rax
0x1400283a8  lea     rdx, word_14000B6FA
0x1400283af  lea     rax, [rsp+160h+var_110]
0x1400283b4  mov     [rbp+60h+var_68], 1
0x1400283bc  mov     [rbp+60h+var_60], rax
0x1400283c0  lea     rcx, dword_14000E060
0x1400283c7  lea     rax, [rsp+160h+var_F8]
0x1400283cc  mov     [rsp+160h+var_110], 9
0x1400283d1  mov     [rbp+60h+var_50], rax
0x1400283d5  xor     r9d, r9d
0x1400283d8  lea     rax, [rbp+60h+var_90]
0x1400283dc  mov     [rbp+60h+var_58], 1
0x1400283e4  mov     [rsp+160h+LengthReturned], rax
0x1400283e9  xor     r8d, r8d
0x1400283ec  mov     [rsp+160h+FileInformationClass], 5
0x1400283f4  mov     dword ptr [rsp+160h+var_F8], ebx
0x1400283f8  mov     [rbp+60h+var_48], 4
0x140028400  call    _tlgWriteTransfer_EtwWriteTransfer
0x140028405  jmp     loc_14002814A
0x14002840a  mov     rax, [rsp+160h+FileNameInformation]
0x14002840f  mov     [rdi], rax
0x140028412  mov     rax, [rbp+60h+var_B0]
0x140028416  mov     [rsp+160h+FileNameInformation], r12
0x14002841b  mov     [rdi+8], r14
0x14002841f  mov     r14, r12
0x140028422  mov     [rax], rdi
0x140028425  mov     rdi, r12
0x140028428  mov     r12, [rsp+160h+var_108]
  ... truncated ...
```
