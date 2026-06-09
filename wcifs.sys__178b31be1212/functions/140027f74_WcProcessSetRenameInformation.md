# WcProcessSetRenameInformation

- ea: `0x140027f74`
- end: `0x1400285bb`
- name: `WcProcessSetRenameInformation`
- size: `1607`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA CallbackData, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140027780`

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
- `0x140027f74`
- `0x14002898c`
- `0x14002d648`
- `0x14002eea4`

## import_xrefs

- `ntoskrnl!ExFreeToPagedLookasideList` at `0x1400284b0`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x1400284b0`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1400281e2`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1400281e2`
- `ntoskrnl!ObfDereferenceObject` at `0x1400284d9`
- `ntoskrnl!ObfDereferenceObject` at `0x1400284d9`
- `FLTMGR!FltClose` at `0x1400284c5`
- `FLTMGR!FltClose` at `0x1400284c5`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140028495`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140028495`
- `FLTMGR!FltGetFileNameInformation` at `0x14002823c`
- `FLTMGR!FltGetFileNameInformation` at `0x14002823c`
- `FLTMGR!FltParseFileNameInformation` at `0x14002825a`
- `FLTMGR!FltParseFileNameInformation` at `0x14002825a`
- `FLTMGR!FltQueryInformationFile` at `0x140028138`
- `FLTMGR!FltQueryInformationFile` at `0x140028138`
- `FLTMGR!FltReleaseContext` at `0x1400284ee`
- `FLTMGR!FltReleaseContext` at `0x140028506`
- `FLTMGR!FltReleaseContext` at `0x14002851a`
- `FLTMGR!FltReleaseContext` at `0x140028532`
- `FLTMGR!FltReleaseContext` at `0x1400284ee`
- `FLTMGR!FltReleaseContext` at `0x140028506`
- `FLTMGR!FltReleaseContext` at `0x14002851a`
- `FLTMGR!FltReleaseContext` at `0x140028532`

## pseudocode

```c
__int64 __fastcall WcProcessSetRenameInformation(PFLT_CALLBACK_DATA CallbackData, __int64 a2, _QWORD *a3)
{
  PFLT_IO_PARAMETER_BLOCK Iopb; // rdx
  struct _FLT_INSTANCE *v6; // rcx
  NTSTATUS v7; // ebx
  struct _FILE_OBJECT *ParentOfTarget; // rdx
  _BYTE *v9; // rdi
  void *v10; // r14
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
  __int64 v25; // r9
  int v26; // eax
  _QWORD *v27; // rax
  char v29; // [rsp+30h] [rbp-D0h]
  char v30; // [rsp+38h] [rbp-C8h]
  char v31; // [rsp+50h] [rbp-B0h] BYREF
  char v32; // [rsp+51h] [rbp-AFh] BYREF
  __int64 UnionContext; // [rsp+58h] [rbp-A8h]
  PFLT_FILE_NAME_INFORMATION FileNameInformation; // [rsp+60h] [rbp-A0h] BYREF
  PFLT_CONTEXT v35; // [rsp+68h] [rbp-98h] BYREF
  void *v36; // [rsp+70h] [rbp-90h] BYREF
  ULONG LengthReturned; // [rsp+78h] [rbp-88h] BYREF
  PFLT_CONTEXT Context; // [rsp+80h] [rbp-80h]
  PFLT_CONTEXT v39; // [rsp+88h] [rbp-78h]
  PFLT_CONTEXT v40; // [rsp+90h] [rbp-70h]
  HANDLE FileHandle; // [rsp+98h] [rbp-68h] BYREF
  __m128i Name; // [rsp+A0h] [rbp-60h] BYREF
  _QWORD *v43; // [rsp+B0h] [rbp-50h]
  __int128 FileInformation; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v45; // [rsp+C8h] [rbp-38h]
  char v46[32]; // [rsp+D0h] [rbp-30h] BYREF
  char *v47; // [rsp+F0h] [rbp-10h]
  __int64 v48; // [rsp+F8h] [rbp-8h]
  char *v49; // [rsp+100h] [rbp+0h]
  __int64 v50; // [rsp+108h] [rbp+8h]
  PFLT_CONTEXT *v51; // [rsp+110h] [rbp+10h]
  __int64 v52; // [rsp+118h] [rbp+18h]

  v43 = a3;
  FileNameInformation = 0;
  Iopb = CallbackData->Iopb;
  LengthReturned = 0;
  Context = 0;
  v45 = 0;
  v6 = *(struct _FLT_INSTANCE **)(a2 + 24);
  Name = 0;
  v7 = 0;
  v39 = 0;
  FileInformation = 0;
  ParentOfTarget = Iopb->Parameters.SetFileInformation.ParentOfTarget;
  v35 = 0;
  v9 = 0;
  v40 = 0;
  v10 = 0;
  FileHandle = 0;
  v36 = 0;
  v31 = 0;
  if ( !(unsigned __int8)WcGetContextFileObject(v6, ParentOfTarget)
    || !(unsigned __int8)WcIsPlaceHolderDirectory(Context, v39)
    || !(unsigned __int8)WcIsUnionValid(*((_QWORD *)v39 + 5))
    || (v11 = 0, v7 = WcPrepareTargetDirectoryForRenameOrLink(CallbackData), v7 >= 0) )
  {
    UnionContext = WcGetUnionContext(CallbackData, *(_QWORD *)(a2 + 24), *(_QWORD *)(a2 + 32));
    v11 = UnionContext;
    if ( UnionContext )
    {
      v13 = 0;
      if ( (unsigned __int8)WcGetContextFileObject(*(PFLT_INSTANCE *)(a2 + 24), *(PFILE_OBJECT *)(a2 + 32)) )
      {
        v32 = 0;
        if ( (unsigned __int8)WcIsPlaceHolderDirectory(v35, v40) )
        {
          v13 = 1;
        }
        else if ( (unsigned __int8)WcIsPlaceHolderStream(v35, v40) )
        {
          v32 = 1;
        }
        else if ( !(unsigned __int8)WcIsPlaceHolder(v35) )
        {
          goto LABEL_15;
        }
        v14 = *(void **)(a2 + 32);
        v15 = *(void **)(a2 + 24);
        v31 = 1;
        v7 = WcSetPlaceHolderFlagsSynchronized(CallbackData, v15, v14);
        if ( v7 < 0 )
          goto LABEL_45;
        if ( v13 || v32 )
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
        v30 = v16;
        v17 = 10;
        v29 = -92;
        v18 = 13;
LABEL_18:
        LOBYTE(v12) = 2;
        WPP_RECORDER_SF_sDd(
          wil_details_featureDescriptors_a->DeviceExtension,
          v12,
          v18,
          v17,
          (__int64)WPP_62cdeb337fdf307834c1a2cccb2efbc6_Traceguids,
          (__int64)"onecore\\base\\fs\\wci\\wcifs\\fileinfo.c",
          v29,
          v30);
        goto LABEL_19;
      }
      if ( BYTE5(v45) )
      {
        v13 = 1;
        goto LABEL_23;
      }
      if ( __PAIR16__(BYTE6(v45), 0) == HIBYTE(v45) )
      {
LABEL_23:
        if ( !v31 )
        {
          v19 = (_DWORD *)(UnionContext + 36);
          goto LABEL_26;
        }
LABEL_24:
        v19 = (_DWORD *)*((_QWORD *)v35 + 8);
LABEL_26:
        LODWORD(v35) = *v19;
        v20 = ExAllocateFromPagedLookasideList(&stru_14000E500);
        v9 = v20;
        if ( !v20 )
        {
          v7 = -1073741670;
          if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            goto LABEL_19;
          v30 = -102;
          v17 = 11;
          v29 = -61;
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
            v24 = WcOpenPlaceHolder(v23, &Name, 41, (unsigned int)v35, &FileHandle, &v36, &v31);
            v7 = v24;
            if ( v24 < 0 )
            {
              if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              {
                LOBYTE(v12) = 2;
                WPP_RECORDER_SF_sDdZ(
                  wil_details_featureDescriptors_a->DeviceExtension,
                  v12,
                  5,
                  12,
                  (__int64)WPP_62cdeb337fdf307834c1a2cccb2efbc6_Traceguids,
                  (__int64)"onecore\\base\\fs\\wci\\wcifs\\fileinfo.c",
                  242,
                  v24,
                  (__int64)&Name);
              }
              v10 = v36;
              goto LABEL_19;
            }
            v10 = v36;
            if ( v31 )
            {
              LOBYTE(v25) = v9[16];
              v26 = WcAddInMemoryTombstone(
                      CallbackData,
                      *(_QWORD *)(a2 + 24),
                      &FileNameInformation->FinalComponent,
                      v25,
                      v36);
              v7 = v26;
              if ( v26 < 0 )
              {
                if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                {
                  LOBYTE(v12) = 2;
                  WPP_RECORDER_SF_sDd(
                    wil_details_featureDescriptors_a->DeviceExtension,
                    v12,
                    5,
                    13,
                    (__int64)WPP_62cdeb337fdf307834c1a2cccb2efbc6_Traceguids,
                    (__int64)"onecore\\base\\fs\\wci\\wcifs\\fileinfo.c",
                    8,
                    v26);
                }
                if ( (unsigned int)dword_14000E060 > 5
                  && (unsigned __int8)tlgKeywordOn(&dword_14000E060, 0x400000000000LL) )
                {
                  v32 = 3;
                  v47 = &v32;
                  v48 = 1;
                  v49 = &v31;
                  v31 = 9;
                  v51 = &v35;
                  v50 = 1;
                  LODWORD(v35) = v7;
                  v52 = 4;
                  tlgWriteTransfer_EtwWriteTransfer(&dword_14000E060, word_14000B6FA, 0, 0, 5, v46);
                }
                goto LABEL_19;
              }
            }
            *(_QWORD *)v9 = FileNameInformation;
            v27 = v43;
            FileNameInformation = 0;
            *((_QWORD *)v9 + 1) = v10;
            v10 = 0;
            *v27 = v9;
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
  if ( v39 )
    FltReleaseContext(v39);
  if ( v40 )
    FltReleaseContext(v40);
  if ( v11 )
    WcReleaseUnionContext(v11);
  if ( v7 < 0 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v12) = 2;
    WPP_RECORDER_SF_sDd(
      wil_details_featureDescriptors_a->DeviceExtension,
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
0x140027f74  mov     [rsp-8+arg_18], rbx
0x140027f79  push    rbp
0x140027f7a  push    rsi
0x140027f7b  push    rdi
0x140027f7c  push    r12
0x140027f7e  push    r13
0x140027f80  push    r14
0x140027f82  push    r15
0x140027f84  lea     rbp, [rsp-30h]
0x140027f89  sub     rsp, 130h
0x140027f90  mov     rax, cs:__security_cookie
0x140027f97  xor     rax, rsp
0x140027f9a  mov     [rbp+60h+var_40], rax
0x140027f9e  xor     r12d, r12d
0x140027fa1  mov     [rbp+60h+var_B0], r8
0x140027fa5  mov     rsi, rdx
0x140027fa8  mov     [rsp+160h+FileNameInformation], r12
0x140027fad  mov     rdx, [rcx+10h]
0x140027fb1  lea     r9, [rbp+60h+var_D8]
0x140027fb5  xorps   xmm0, xmm0
0x140027fb8  mov     [rsp+160h+var_E8], r12d
0x140027fbd  xor     eax, eax
0x140027fbf  mov     [rbp+60h+Context], r12
0x140027fc3  mov     r13, rcx
0x140027fc6  mov     [rbp+60h+var_98], rax
0x140027fca  mov     rcx, [rsi+18h]; Instance
0x140027fce  lea     r8, [rbp+60h+Context]
0x140027fd2  movups  [rbp+60h+var_C0], xmm0
0x140027fd6  mov     ebx, r12d
0x140027fd9  mov     [rbp+60h+var_D8], r12
0x140027fdd  movups  [rbp+60h+FileInformation], xmm0
0x140027fe1  mov     rdx, [rdx+28h]; FileObject
0x140027fe5  mov     r15d, r12d
0x140027fe8  mov     [rsp+160h+var_F8], r12
0x140027fed  mov     edi, r12d
0x140027ff0  mov     [rbp+60h+var_D0], r12
0x140027ff4  mov     r14d, r12d
0x140027ff7  mov     [rbp+60h+FileHandle], r12
0x140027ffb  mov     [rsp+160h+var_F0], r12
0x140028000  mov     [rsp+160h+var_110], r12b
0x140028005  call    WcGetContextFileObject
0x14002800a  test    al, al
0x14002800c  jz      short loc_140028048
0x14002800e  mov     r12, [rbp+60h+var_D8]
0x140028012  mov     rcx, [rbp+60h+Context]
0x140028016  mov     rdx, r12
0x140028019  call    WcIsPlaceHolderDirectory
0x14002801e  test    al, al
0x140028020  jz      short loc_140028048
0x140028022  mov     rcx, [r12+28h]
0x140028027  call    WcIsUnionValid
0x14002802c  test    al, al
0x14002802e  jz      short loc_140028048
0x140028030  mov     rdx, rsi
0x140028033  mov     rcx, r13; CallbackData
0x140028036  xor     r12d, r12d
0x140028039  call    WcPrepareTargetDirectoryForRenameOrLink
0x14002803e  mov     ebx, eax
0x140028040  test    eax, eax
0x140028042  js      loc_14002847D
0x140028048  mov     r8, [rsi+20h]
0x14002804c  mov     rcx, r13
0x14002804f  mov     rdx, [rsi+18h]
0x140028053  call    WcGetUnionContext
0x140028058  mov     [rsp+160h+var_108], rax
0x14002805d  mov     r12, rax
0x140028060  test    rax, rax
0x140028063  jz      loc_14002847D
0x140028069  mov     rdx, [rsi+20h]; FileObject
0x14002806d  lea     r9, [rbp+60h+var_D0]
0x140028071  mov     rcx, [rsi+18h]; Instance
0x140028075  lea     r8, [rsp+160h+var_F8]
0x14002807a  xor     r12b, r12b
0x14002807d  call    WcGetContextFileObject
0x140028082  mov     r15, [rsp+160h+var_F8]
0x140028087  test    al, al
0x140028089  jz      loc_140028114
0x14002808f  mov     rbx, [rbp+60h+var_D0]
0x140028093  mov     rcx, r15
0x140028096  mov     rdx, rbx
0x140028099  mov     [rsp+160h+var_10F], dil
0x14002809e  call    WcIsPlaceHolderDirectory
0x1400280a3  test    al, al
0x1400280a5  jz      short loc_1400280B2
0x1400280a7  mov     r9d, 0Ah
0x1400280ad  mov     r12b, 1
0x1400280b0  jmp     short loc_1400280E0
0x1400280b2  mov     rdx, rbx
0x1400280b5  mov     rcx, r15
0x1400280b8  call    WcIsPlaceHolderStream
0x1400280bd  test    al, al
0x1400280bf  jz      short loc_1400280CE
0x1400280c1  mov     r9d, 0Ah
0x1400280c7  mov     [rsp+160h+var_10F], 1
0x1400280cc  jmp     short loc_1400280E0
0x1400280ce  mov     rcx, r15
0x1400280d1  call    WcIsPlaceHolder
0x1400280d6  test    al, al
0x1400280d8  jz      short loc_140028114
0x1400280da  mov     r9d, 2
0x1400280e0  mov     r8, [rsi+20h]; Object
0x1400280e4  mov     rcx, r13; CallbackData
0x1400280e7  mov     rdx, [rsi+18h]; FltObject
0x1400280eb  mov     [rsp+160h+var_110], 1
0x1400280f0  call    WcSetPlaceHolderFlagsSynchronized
0x1400280f5  xor     ecx, ecx
0x1400280f7  mov     ebx, eax
0x1400280f9  test    eax, eax
0x1400280fb  js      loc_140028478
0x140028101  test    r12b, r12b
0x140028104  jnz     loc_1400281C6
0x14002810a  cmp     [rsp+160h+var_10F], cl
0x14002810e  jnz     loc_1400281C6
0x140028114  mov     rdx, [rsi+20h]; FileObject
0x140028118  lea     rax, [rsp+160h+var_E8]
0x14002811d  mov     rcx, [rsi+18h]; Instance
0x140028121  lea     r8, [rbp+60h+FileInformation]; FileInformation
0x140028125  mov     [rsp+160h+LengthReturned], rax; LengthReturned
0x14002812a  mov     r9d, 18h; Length
0x140028130  mov     [rsp+160h+FileInformationClass], 5; FileInformationClass
0x140028138  call    cs:__imp_FltQueryInformationFile
0x14002813f  nop     dword ptr [rax+rax+00h]
0x140028144  xor     ecx, ecx
0x140028146  mov     ebx, eax
0x140028148  test    eax, eax
0x14002814a  jns     short loc_1400281A4
0x14002814c  lea     rsi, WPP_RECORDER_INITIALIZED
0x140028153  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x14002815a  lea     r13, aOnecoreBaseFsW_8; "onecore\\base\\fs\\wci\\wcifs\\fileinfo"...
0x140028161  jz      short loc_14002819A
0x140028163  mov     dword ptr [rsp+160h+var_128], eax
0x140028167  lea     r9d, [rcx+0Ah]
0x14002816b  mov     dword ptr [rsp+160h+var_130], 0A4h
0x140028173  lea     r8d, [rcx+0Dh]
0x140028177  mov     rcx, cs:wil_details_featureDescriptors_a
0x14002817e  lea     rax, WPP_62cdeb337fdf307834c1a2cccb2efbc6_Traceguids
0x140028185  mov     [rsp+160h+LengthReturned], r13
0x14002818a  mov     dl, 2
0x14002818c  mov     qword ptr [rsp+160h+FileInformationClass], rax
0x140028191  mov     rcx, [rcx+40h]
0x140028195  call    WPP_RECORDER_SF_sDd
0x14002819a  mov     r12, [rsp+160h+var_108]
0x14002819f  jmp     loc_14002848B
0x1400281a4  cmp     byte ptr [rbp+60h+var_98+5], cl
0x1400281a7  jz      short loc_1400281AE
0x1400281a9  mov     r12b, 1
0x1400281ac  jmp     short loc_1400281C0
0x1400281ae  cmp     byte ptr [rbp+60h+var_98+6], cl
0x1400281b1  jnz     loc_140028478
0x1400281b7  cmp     byte ptr [rbp+60h+var_98+7], cl
0x1400281ba  jnz     loc_140028478
0x1400281c0  cmp     [rsp+160h+var_110], cl
0x1400281c4  jz      short loc_1400281CC
0x1400281c6  mov     rax, [r15+40h]
0x1400281ca  jmp     short loc_1400281D5
0x1400281cc  mov     rax, [rsp+160h+var_108]
0x1400281d1  add     rax, 24h ; '$'
0x1400281d5  mov     eax, [rax]
0x1400281d7  lea     rcx, stru_14000E500; Lookaside
0x1400281de  mov     dword ptr [rsp+160h+var_F8], eax
0x1400281e2  call    cs:__imp_ExAllocateFromPagedLookasideList
0x1400281e9  nop     dword ptr [rax+rax+00h]
0x1400281ee  mov     rdi, rax
0x1400281f1  test    rax, rax
0x1400281f4  jnz     short loc_14002822B
0x1400281f6  mov     ebx, 0C000009Ah
0x1400281fb  lea     rsi, WPP_RECORDER_INITIALIZED
0x140028202  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140028209  lea     r13, aOnecoreBaseFsW_8; "onecore\\base\\fs\\wci\\wcifs\\fileinfo"...
0x140028210  jz      short loc_14002819A
0x140028212  mov     dword ptr [rsp+160h+var_128], ebx
0x140028216  lea     r9d, [rax+0Bh]
0x14002821a  mov     dword ptr [rsp+160h+var_130], 0C3h
0x140028222  lea     r8d, [rax+5]
0x140028226  jmp     loc_140028177
0x14002822b  lea     r8, [rsp+160h+FileNameInformation]; FileNameInformation
0x140028230  mov     [rax+10h], r12b
0x140028234  mov     edx, 101h; NameOptions
0x140028239  mov     rcx, r13; CallbackData
0x14002823c  call    cs:__imp_FltGetFileNameInformation
0x140028243  nop     dword ptr [rax+rax+00h]
0x140028248  xor     r12d, r12d
0x14002824b  mov     ebx, eax
0x14002824d  test    eax, eax
0x14002824f  js      loc_140028478
0x140028255  mov     rcx, [rsp+160h+FileNameInformation]; FileNameInformation
0x14002825a  call    cs:__imp_FltParseFileNameInformation
0x140028261  nop     dword ptr [rax+rax+00h]
0x140028266  mov     ebx, eax
0x140028268  test    eax, eax
0x14002826a  js      loc_140028478
0x140028270  mov     rdx, [rsp+160h+FileNameInformation]
0x140028275  lea     r8d, [r12+29h]
0x14002827a  mov     r9d, dword ptr [rsp+160h+var_F8]
0x14002827f  movups  xmm0, xmmword ptr [rdx+8]
0x140028283  movd    ecx, xmm0
0x140028287  movups  [rbp+60h+var_C0], xmm0
0x14002828b  sub     cx, [rdx+58h]
0x14002828f  lea     eax, [rcx-2]
0x140028292  mov     word ptr [rbp+60h+var_C0], ax
0x140028296  cmp     ax, [rdx+18h]
0x14002829a  lea     rdx, [rbp+60h+var_C0]
0x14002829e  cmovz   ax, cx
0x1400282a2  mov     rcx, [rsi+18h]
0x1400282a6  mov     word ptr [rbp+60h+var_C0], ax
0x1400282aa  lea     rax, [rsp+160h+var_110]
0x1400282af  mov     [rsp+160h+var_130], rax
0x1400282b4  lea     rax, [rsp+160h+var_F0]
0x1400282b9  mov     [rsp+160h+LengthReturned], rax
0x1400282be  lea     rax, [rbp+60h+FileHandle]
0x1400282c2  mov     qword ptr [rsp+160h+FileInformationClass], rax
0x1400282c7  call    WcOpenPlaceHolder
0x1400282cc  mov     ebx, eax
0x1400282ce  test    eax, eax
0x1400282d0  jns     short loc_140028335
0x1400282d2  lea     rsi, WPP_RECORDER_INITIALIZED
0x1400282d9  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x1400282e0  lea     r13, aOnecoreBaseFsW_8; "onecore\\base\\fs\\wci\\wcifs\\fileinfo"...
0x1400282e7  jz      short loc_14002832B
0x1400282e9  mov     rcx, cs:wil_details_featureDescriptors_a
0x1400282f0  lea     rax, [rbp+60h+var_C0]
0x1400282f4  mov     [rsp+160h+var_120], rax
0x1400282f9  lea     r9d, [r12+0Ch]
0x1400282fe  mov     dword ptr [rsp+160h+var_128], ebx
0x140028302  lea     rax, WPP_62cdeb337fdf307834c1a2cccb2efbc6_Traceguids
0x140028309  mov     dword ptr [rsp+160h+var_130], 0F2h
0x140028311  lea     r8d, [r12+5]
0x140028316  mov     rcx, [rcx+40h]
0x14002831a  mov     dl, 2
0x14002831c  mov     [rsp+160h+LengthReturned], r13
0x140028321  mov     qword ptr [rsp+160h+FileInformationClass], rax
0x140028326  call    WPP_RECORDER_SF_sDdZ
0x14002832b  mov     r14, [rsp+160h+var_F0]
0x140028330  jmp     loc_14002819A
0x140028335  mov     r14, [rsp+160h+var_F0]
0x14002833a  cmp     [rsp+160h+var_110], r12b
0x14002833f  jz      loc_14002845A
0x140028345  mov     r8, [rsp+160h+FileNameInformation]
0x14002834a  mov     rcx, r13
0x14002834d  mov     r9b, [rdi+10h]
0x140028351  add     r8, 58h ; 'X'
0x140028355  mov     rdx, [rsi+18h]
0x140028359  mov     qword ptr [rsp+160h+FileInformationClass], r14
0x14002835e  call    WcAddInMemoryTombstone
0x140028363  mov     ebx, eax
0x140028365  test    eax, eax
0x140028367  jns     loc_14002845A
0x14002836d  lea     rsi, WPP_RECORDER_INITIALIZED
0x140028374  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x14002837b  lea     r13, aOnecoreBaseFsW_8; "onecore\\base\\fs\\wci\\wcifs\\fileinfo"...
0x140028382  jz      short loc_1400283BD
0x140028384  mov     rcx, cs:wil_details_featureDescriptors_a
0x14002838b  mov     r9d, 0Dh
0x140028391  mov     dword ptr [rsp+160h+var_128], eax
0x140028395  mov     dl, 2
0x140028397  mov     dword ptr [rsp+160h+var_130], 108h
0x14002839f  lea     rax, WPP_62cdeb337fdf307834c1a2cccb2efbc6_Traceguids
0x1400283a6  mov     [rsp+160h+LengthReturned], r13
0x1400283ab  mov     rcx, [rcx+40h]
0x1400283af  lea     r8d, [r9-8]
0x1400283b3  mov     qword ptr [rsp+160h+FileInformationClass], rax
0x1400283b8  call    WPP_RECORDER_SF_sDd
0x1400283bd  mov     eax, cs:dword_14000E060
0x1400283c3  cmp     eax, 5
0x1400283c6  jbe     loc_14002819A
0x1400283cc  mov     rdx, 400000000000h
0x1400283d6  lea     rcx, dword_14000E060
0x1400283dd  call    _tlgKeywordOn
0x1400283e2  test    al, al
0x1400283e4  jz      loc_14002819A
0x1400283ea  lea     rax, [rsp+160h+var_10F]
0x1400283ef  mov     [rsp+160h+var_10F], 3
0x1400283f4  mov     [rbp+60h+var_70], rax
0x1400283f8  lea     rdx, word_14000B6FA
0x1400283ff  lea     rax, [rsp+160h+var_110]
0x140028404  mov     [rbp+60h+var_68], 1
0x14002840c  mov     [rbp+60h+var_60], rax
0x140028410  lea     rcx, dword_14000E060
0x140028417  lea     rax, [rsp+160h+var_F8]
0x14002841c  mov     [rsp+160h+var_110], 9
0x140028421  mov     [rbp+60h+var_50], rax
0x140028425  xor     r9d, r9d
0x140028428  lea     rax, [rbp+60h+var_90]
0x14002842c  mov     [rbp+60h+var_58], 1
0x140028434  mov     [rsp+160h+LengthReturned], rax
0x140028439  xor     r8d, r8d
0x14002843c  mov     [rsp+160h+FileInformationClass], 5
0x140028444  mov     dword ptr [rsp+160h+var_F8], ebx
0x140028448  mov     [rbp+60h+var_48], 4
0x140028450  call    _tlgWriteTransfer_EtwWriteTransfer
0x140028455  jmp     loc_14002819A
0x14002845a  mov     rax, [rsp+160h+FileNameInformation]
0x14002845f  mov     [rdi], rax
0x140028462  mov     rax, [rbp+60h+var_B0]
0x140028466  mov     [rsp+160h+FileNameInformation], r12
0x14002846b  mov     [rdi+8], r14
0x14002846f  mov     r14, r12
0x140028472  mov     [rax], rdi
0x140028475  mov     rdi, r12
0x140028478  mov     r12, [rsp+160h+var_108]
  ... truncated ...
```
