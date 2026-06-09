# WcPrepareForDelete

- ea: `0x1400278a4`
- end: `0x140027f6d`
- name: `WcPrepareForDelete`
- size: `1737`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA CallbackData, __int64)`
- caller_count: `2`
- callee_count: `20`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x140027780`
- `0x140034410`

## callees

- `0x140001500`
- `0x1400016f0`
- `0x140001b94`
- `0x140001bc8`
- `0x140001bf8`
- `0x140001fd0`
- `0x1400020c4`
- `0x1400024fc`
- `0x140004198`
- `0x140004b0c`
- `0x140007c60`
- `0x14001cff0`
- `0x14001eadc`
- `0x1400278a4`
- `0x14002898c`
- `0x140029658`
- `0x140029f84`
- `0x14002a11c`
- `0x14002d648`
- `0x14002eea4`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x140027f0c`
- `ntoskrnl!ObfDereferenceObject` at `0x140027f0c`
- `ntoskrnl!ExAcquireFastMutex` at `0x140027ea5`
- `ntoskrnl!ExAcquireFastMutex` at `0x140027ea5`
- `ntoskrnl!ExReleaseFastMutex` at `0x140027ebd`
- `ntoskrnl!ExReleaseFastMutex` at `0x140027ebd`
- `FLTMGR!FltQueryDirectoryFile` at `0x140027dcc`
- `FLTMGR!FltQueryDirectoryFile` at `0x140027dcc`
- `FLTMGR!FltClose` at `0x140027efb`
- `FLTMGR!FltClose` at `0x140027efb`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140027eea`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140027eea`
- `FLTMGR!FltGetFileNameInformation` at `0x140027c1e`
- `FLTMGR!FltGetFileNameInformation` at `0x140027c1e`
- `FLTMGR!FltParseFileNameInformation` at `0x140027c38`
- `FLTMGR!FltParseFileNameInformation` at `0x140027c38`
- `FLTMGR!FltQueryInformationFile` at `0x140027e57`
- `FLTMGR!FltQueryInformationFile` at `0x140027e57`
- `FLTMGR!FltReleaseContext` at `0x140027f20`
- `FLTMGR!FltReleaseContext` at `0x140027f34`
- `FLTMGR!FltReleaseContext` at `0x140027f48`
- `FLTMGR!FltReleaseContext` at `0x140027f5c`
- `FLTMGR!FltReleaseContext` at `0x140027f20`
- `FLTMGR!FltReleaseContext` at `0x140027f34`
- `FLTMGR!FltReleaseContext` at `0x140027f48`
- `FLTMGR!FltReleaseContext` at `0x140027f5c`

## pseudocode

```c
__int64 __fastcall WcPrepareForDelete(PFLT_CALLBACK_DATA CallbackData, __int64 a2)
{
  __int64 v2; // r8
  __int64 v4; // rdx
  NTSTATUS IsDirectoryEmpty; // edi
  void *v6; // rsi
  void *v7; // r15
  __int64 UnionContext; // rax
  int v10; // edx
  __int64 v11; // r13
  int v13; // edx
  int v14; // r9d
  int v15; // r8d
  __int16 v16; // cx
  __int16 v17; // ax
  __int64 v18; // rcx
  int v19; // edx
  int SetContextFileObject; // eax
  __int64 Source; // rax
  NTSTATUS v22; // eax
  char *v23; // rbx
  int FileInformationClass; // [rsp+20h] [rbp-99h]
  char FileName; // [rsp+30h] [rbp-89h]
  char RestartScan; // [rsp+38h] [rbp-81h]
  _BYTE v27[7]; // [rsp+51h] [rbp-68h] BYREF
  PFLT_CONTEXT Context; // [rsp+58h] [rbp-61h] BYREF
  PFLT_CONTEXT v29; // [rsp+60h] [rbp-59h] BYREF
  PFLT_FILE_NAME_INFORMATION FileNameInformation; // [rsp+68h] [rbp-51h] BYREF
  __int64 v31; // [rsp+70h] [rbp-49h] BYREF
  __int64 v32; // [rsp+78h] [rbp-41h] BYREF
  PVOID Object; // [rsp+80h] [rbp-39h] BYREF
  HANDLE FileHandle; // [rsp+88h] [rbp-31h] BYREF
  __m128i Name; // [rsp+90h] [rbp-29h] BYREF
  __int128 FileInformation; // [rsp+A0h] [rbp-19h] BYREF
  _OWORD v37[2]; // [rsp+B0h] [rbp-9h] BYREF
  int v38[2]; // [rsp+D0h] [rbp+17h]

  v2 = *(_QWORD *)(a2 + 32);
  v29 = 0;
  Context = 0;
  v31 = 0;
  v4 = *(_QWORD *)(a2 + 24);
  IsDirectoryEmpty = 0;
  v32 = 0;
  v6 = 0;
  v7 = 0;
  FileNameInformation = 0;
  Name = 0;
  FileHandle = 0;
  Object = 0;
  v27[0] = 0;
  FileInformation = 0;
  *(_QWORD *)v38 = 0;
  memset(v37, 0, sizeof(v37));
  UnionContext = WcGetUnionContext(CallbackData, v4, v2);
  v11 = UnionContext;
  if ( UnionContext )
  {
    if ( *(_DWORD *)(UnionContext + 24) == 2 )
    {
      IsDirectoryEmpty = -1073741637;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v10) = 2;
        WPP_RECORDER_SF_sD(
          wil_details_featureDescriptors_a->DeviceExtension,
          v10,
          13,
          187,
          (__int64)WPP_7fe91d13bb4232a4ef347966c958c4d1_Traceguids,
          (__int64)"onecore\\base\\fs\\wci\\wcifs\\utils.c",
          8);
      }
      goto LABEL_65;
    }
    if ( (unsigned __int8)WcGetContextFileObject(*(PFLT_INSTANCE *)(a2 + 24), *(PFILE_OBJECT *)(a2 + 32)) )
    {
      if ( (unsigned __int8)WcIsPlaceHolderDirectory(Context, v29) )
      {
        if ( (unsigned __int8)WcIsSourcedStream(v29) )
        {
          IsDirectoryEmpty = WcIsDirectoryEmpty(*(PFLT_INSTANCE *)(a2 + 24), *(PFILE_OBJECT *)(a2 + 32));
          if ( IsDirectoryEmpty >= 0 )
          {
            if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              LOBYTE(v13) = 4;
              WPP_RECORDER_SF_sDd(
                wil_details_featureDescriptors_a->DeviceExtension,
                v13,
                13,
                189,
                (__int64)WPP_7fe91d13bb4232a4ef347966c958c4d1_Traceguids,
                (__int64)"onecore\\base\\fs\\wci\\wcifs\\utils.c",
                51,
                IsDirectoryEmpty);
            }
            IsDirectoryEmpty = -1073741567;
            goto LABEL_65;
          }
          if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
LABEL_65:
            WcReleaseUnionContext(v11);
            goto LABEL_2;
          }
          RestartScan = IsDirectoryEmpty;
          v14 = 188;
          FileName = 36;
          LOBYTE(v13) = 2;
          goto LABEL_26;
        }
        IsDirectoryEmpty = WcRemoveTombstonesFromDirectory(CallbackData, *(_QWORD *)(a2 + 24), *(_QWORD *)(a2 + 32));
        if ( IsDirectoryEmpty < 0 )
        {
          if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            goto LABEL_65;
          RestartScan = IsDirectoryEmpty;
          v14 = 190;
          FileName = 66;
          LOBYTE(v13) = 4;
          goto LABEL_26;
        }
      }
      else if ( !(unsigned __int8)WcIsPlaceHolderStream(Context, v29) && (unsigned __int8)WcIsPlaceHolder(Context) )
      {
        IsDirectoryEmpty = WcSetPlaceHolderFlagsSynchronized(CallbackData, *(PVOID *)(a2 + 24), *(PVOID *)(a2 + 32));
        if ( IsDirectoryEmpty >= 0 || WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_65;
        RestartScan = IsDirectoryEmpty;
        v14 = 191;
        FileName = 89;
        LOBYTE(v13) = 3;
LABEL_26:
        v15 = 13;
LABEL_27:
        WPP_RECORDER_SF_sDd(
          wil_details_featureDescriptors_a->DeviceExtension,
          v13,
          v15,
          v14,
          (__int64)WPP_7fe91d13bb4232a4ef347966c958c4d1_Traceguids,
          (__int64)"onecore\\base\\fs\\wci\\wcifs\\utils.c",
          FileName,
          RestartScan);
        goto LABEL_65;
      }
LABEL_58:
      if ( v29
        || (IsDirectoryEmpty = FltQueryInformationFile(
                                 *(PFLT_INSTANCE *)(a2 + 24),
                                 *(PFILE_OBJECT *)(a2 + 32),
                                 v37,
                                 0x28u,
                                 FileBasicInformation,
                                 0),
            IsDirectoryEmpty >= 0)
        && (IsDirectoryEmpty = WcGetSetStreamContext(
                                 *(PFLT_INSTANCE *)(a2 + 24),
                                 *(PFILE_OBJECT *)(a2 + 32),
                                 Context,
                                 v38[0],
                                 0,
                                 0,
                                 (__int64)&v29),
            IsDirectoryEmpty >= 0) )
      {
        v23 = (char *)Context;
        ExAcquireFastMutex((PFAST_MUTEX)((char *)Context + 8));
        *((_BYTE *)v29 + 28) = 1;
        ExReleaseFastMutex((PFAST_MUTEX)(v23 + 8));
      }
      goto LABEL_65;
    }
    IsDirectoryEmpty = FltGetFileNameInformation(CallbackData, 0x101u, &FileNameInformation);
    if ( IsDirectoryEmpty < 0 )
      goto LABEL_65;
    IsDirectoryEmpty = FltParseFileNameInformation(FileNameInformation);
    if ( IsDirectoryEmpty < 0 || FileNameInformation->Stream.Length )
      goto LABEL_65;
    Name = (__m128i)FileNameInformation->Name;
    v16 = _mm_cvtsi128_si32(Name) - FileNameInformation->FinalComponent.Length;
    v17 = v16 - 2;
    Name.m128i_i16[0] = v16 - 2;
    if ( v16 - 2 == FileNameInformation->Volume.Length )
      v17 = v16;
    v18 = *(_QWORD *)(a2 + 24);
    Name.m128i_i16[0] = v17;
    IsDirectoryEmpty = WcOpenPlaceHolder(v18, &Name, 41, *(unsigned int *)(v11 + 36), &FileHandle, &Object, v27);
    if ( IsDirectoryEmpty < 0 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v19) = 2;
        WPP_RECORDER_SF_sDdZ(
          wil_details_featureDescriptors_a->DeviceExtension,
          v19,
          10,
          192,
          (__int64)WPP_7fe91d13bb4232a4ef347966c958c4d1_Traceguids,
          (__int64)"onecore\\base\\fs\\wci\\wcifs\\utils.c",
          159,
          IsDirectoryEmpty,
          (__int64)&Name);
      }
      goto LABEL_65;
    }
    if ( !v27[0] )
    {
LABEL_54:
      IsDirectoryEmpty = 0;
      goto LABEL_65;
    }
    SetContextFileObject = WcGetSetContextFileObject(
                             *(PFLT_INSTANCE *)(a2 + 24),
                             (PFILE_OBJECT)Object,
                             FileInformationClass,
                             (__int64)&v32,
                             (__int64)&v31);
    IsDirectoryEmpty = SetContextFileObject;
    if ( SetContextFileObject < 0 )
    {
      if ( SetContextFileObject != -1073741195 )
      {
LABEL_64:
        v7 = (void *)v32;
        v6 = (void *)v31;
        goto LABEL_65;
      }
    }
    else if ( SetContextFileObject != 260 )
    {
      v6 = (void *)v31;
      v7 = (void *)v32;
      if ( !(unsigned __int8)WcIsPlaceHolderDirectory(v32, v31)
        || !(unsigned __int8)WcIsSourcedStream(v6)
        || (Source = WcGetSource(v6),
            v22 = FltQueryDirectoryFile(
                    *(PFLT_INSTANCE *)Source,
                    *(PFILE_OBJECT *)(Source + 16),
                    &FileInformation,
                    0x10u,
                    FileNamesInformation,
                    1u,
                    &FileNameInformation->FinalComponent,
                    1u,
                    0),
            (int)(v22 + 0x80000000) < 0)
        || v22 == -2147483643 )
      {
        IsDirectoryEmpty = WcGetSetFileContext(
                             *(PFLT_INSTANCE *)(a2 + 24),
                             *(PFILE_OBJECT *)(a2 + 32),
                             (__int64)&Context);
        if ( IsDirectoryEmpty < 0 )
        {
          if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            goto LABEL_65;
          RestartScan = IsDirectoryEmpty;
          v14 = 193;
          FileName = 3;
          v15 = 5;
          LOBYTE(v13) = 2;
          goto LABEL_27;
        }
        goto LABEL_58;
      }
      goto LABEL_54;
    }
    IsDirectoryEmpty = 0;
    goto LABEL_64;
  }
LABEL_2:
  if ( FileNameInformation )
    FltReleaseFileNameInformation(FileNameInformation);
  if ( FileHandle )
    FltClose(FileHandle);
  if ( Object )
    ObfDereferenceObject(Object);
  if ( Context )
    FltReleaseContext(Context);
  if ( v29 )
    FltReleaseContext(v29);
  if ( v7 )
    FltReleaseContext(v7);
  if ( v6 )
    FltReleaseContext(v6);
  return (unsigned int)IsDirectoryEmpty;
}

```

## disassembly

```asm
0x1400278a4  mov     [rsp-8+arg_10], rbx
0x1400278a9  push    rbp
0x1400278aa  push    rsi
0x1400278ab  push    rdi
0x1400278ac  push    r12
0x1400278ae  push    r13
0x1400278b0  push    r14
0x1400278b2  push    r15
0x1400278b4  lea     rbp, [rsp-27h]
0x1400278b9  sub     rsp, 0E0h
0x1400278c0  mov     rax, cs:__security_cookie
0x1400278c7  xor     rax, rsp
0x1400278ca  mov     [rbp+57h+var_38], rax
0x1400278ce  mov     r8, [rdx+20h]
0x1400278d2  xor     r14d, r14d
0x1400278d5  xorps   xmm0, xmm0
0x1400278d8  mov     [rbp+57h+var_B0], r14
0x1400278dc  xorps   xmm1, xmm1
0x1400278df  mov     [rbp+57h+Context], r14
0x1400278e3  mov     rbx, rdx
0x1400278e6  mov     [rbp+57h+var_A0], r14
0x1400278ea  mov     rdx, [rdx+18h]
0x1400278ee  xor     eax, eax
0x1400278f0  mov     edi, r14d
0x1400278f3  mov     [rbp+57h+var_98], r14
0x1400278f7  mov     esi, r14d
0x1400278fa  mov     [rbp+57h+var_C0], r14b
0x1400278fe  mov     r15d, r14d
0x140027901  mov     [rbp+57h+FileNameInformation], r14
0x140027905  movups  [rbp+57h+var_80], xmm0
0x140027909  mov     [rbp+57h+FileHandle], r14
0x14002790d  mov     r12, rcx
0x140027910  mov     [rbp+57h+Object], r14
0x140027914  mov     [rbp+57h+var_BF], r14b
0x140027918  movups  [rbp+57h+FileInformation], xmm0
0x14002791c  mov     qword ptr [rbp+57h+var_40], rax
0x140027920  movups  [rbp+57h+var_60], xmm1
0x140027924  movups  [rbp+57h+var_50], xmm1
0x140027928  call    WcGetUnionContext
0x14002792d  mov     r13, rax
0x140027930  test    rax, rax
0x140027933  jnz     short loc_1400279B2
0x140027935  mov     rcx, [rbp+57h+FileNameInformation]; FileNameInformation
0x140027939  test    rcx, rcx
0x14002793c  jnz     loc_140027EEA
0x140027942  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x140027946  test    rcx, rcx
0x140027949  jnz     loc_140027EFB
0x14002794f  mov     rcx, [rbp+57h+Object]; Object
0x140027953  test    rcx, rcx
0x140027956  jnz     loc_140027F0C
0x14002795c  mov     r14, [rbp+57h+Context]
0x140027960  test    r14, r14
0x140027963  jnz     loc_140027F1D
0x140027969  mov     r14, [rbp+57h+var_B0]
0x14002796d  test    r14, r14
0x140027970  jnz     loc_140027F31
0x140027976  test    r15, r15
0x140027979  jnz     loc_140027F45
0x14002797f  test    rsi, rsi
0x140027982  jnz     loc_140027F59
0x140027988  mov     eax, edi
0x14002798a  mov     rcx, [rbp+57h+var_38]
0x14002798e  xor     rcx, rsp; StackCookie
0x140027991  call    __security_check_cookie
0x140027996  mov     rbx, [rsp+110h+arg_10]
0x14002799e  add     rsp, 0E0h
0x1400279a5  pop     r15
0x1400279a7  pop     r14
0x1400279a9  pop     r13
0x1400279ab  pop     r12
0x1400279ad  pop     rdi
0x1400279ae  pop     rsi
0x1400279af  pop     rbp
0x1400279b0  retn
0x1400279b2  mov     ecx, 2
0x1400279b7  cmp     [rax+18h], ecx
0x1400279ba  jnz     short loc_140027A16
0x1400279bc  mov     edi, 0C00000BBh
0x1400279c1  lea     rax, WPP_RECORDER_INITIALIZED
0x1400279c8  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400279cf  jz      loc_140027EDD
0x1400279d5  lea     r8d, [rcx+0Bh]
0x1400279d9  mov     dword ptr [rsp+110h+FileName], 2008h
0x1400279e1  mov     dl, cl
0x1400279e3  lea     rax, aOnecoreBaseFsW_1; "onecore\\base\\fs\\wci\\wcifs\\utils.c"
0x1400279ea  mov     rcx, cs:wil_details_featureDescriptors_a
0x1400279f1  mov     r9d, 0BBh
0x1400279f7  mov     qword ptr [rsp+110h+ReturnSingleEntry], rax
0x1400279fc  lea     rax, WPP_7fe91d13bb4232a4ef347966c958c4d1_Traceguids
0x140027a03  mov     qword ptr [rsp+110h+FileInformationClass], rax
0x140027a08  mov     rcx, [rcx+40h]
0x140027a0c  call    WPP_RECORDER_SF_sD
0x140027a11  jmp     loc_140027EDD
0x140027a16  mov     rdx, [rbx+20h]; FileObject
0x140027a1a  lea     r9, [rbp+57h+var_B0]
0x140027a1e  mov     rcx, [rbx+18h]; Instance
0x140027a22  lea     r8, [rbp+57h+Context]
0x140027a26  call    WcGetContextFileObject
0x140027a2b  test    al, al
0x140027a2d  jz      loc_140027C12
0x140027a33  mov     r14, [rbp+57h+var_B0]
0x140027a37  mov     rcx, [rbp+57h+Context]
0x140027a3b  mov     rdx, r14
0x140027a3e  call    WcIsPlaceHolderDirectory
0x140027a43  test    al, al
0x140027a45  jz      loc_140027BB0
0x140027a4b  mov     rcx, r14
0x140027a4e  call    WcIsSourcedStream
0x140027a53  xor     r14d, r14d
0x140027a56  test    al, al
0x140027a58  jz      loc_140027B69
0x140027a5e  mov     rdx, [rbx+20h]; FileObject
0x140027a62  lea     r8, [rbp+57h+var_C0]
0x140027a66  mov     rcx, [rbx+18h]; Instance
0x140027a6a  call    WcIsDirectoryEmpty
0x140027a6f  mov     edi, eax
0x140027a71  test    eax, eax
0x140027a73  jns     loc_140027B07
0x140027a79  lea     rax, WPP_RECORDER_INITIALIZED
0x140027a80  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140027a87  jz      loc_140027EDD
0x140027a8d  mov     dword ptr [rsp+110h+RestartScan], edi
0x140027a91  mov     r9d, 0BCh
0x140027a97  mov     dword ptr [rsp+110h+FileName], 2024h
0x140027a9f  mov     dl, 2
0x140027aa1  jmp     short loc_140027AB7
0x140027aa3  mov     dword ptr [rsp+110h+RestartScan], edi
0x140027aa7  mov     r9d, 0BFh
0x140027aad  mov     dword ptr [rsp+110h+FileName], 2059h
0x140027ab5  mov     dl, 3
0x140027ab7  mov     r8d, 0Dh
0x140027abd  jmp     short loc_140027ADA
0x140027abf  mov     dword ptr [rsp+110h+RestartScan], edi
0x140027ac3  mov     r9d, 0C1h
0x140027ac9  mov     dword ptr [rsp+110h+FileName], 2103h
0x140027ad1  mov     r8d, 5
0x140027ad7  mov     dl, r12b
0x140027ada  mov     rcx, cs:wil_details_featureDescriptors_a
0x140027ae1  lea     rax, aOnecoreBaseFsW_1; "onecore\\base\\fs\\wci\\wcifs\\utils.c"
0x140027ae8  mov     qword ptr [rsp+110h+ReturnSingleEntry], rax
0x140027aed  lea     rax, WPP_7fe91d13bb4232a4ef347966c958c4d1_Traceguids
0x140027af4  mov     qword ptr [rsp+110h+FileInformationClass], rax
0x140027af9  mov     rcx, [rcx+40h]
0x140027afd  call    WPP_RECORDER_SF_sDd
0x140027b02  jmp     loc_140027EDD
0x140027b07  cmp     [rbp+57h+var_C0], r14b
0x140027b0b  jnz     short loc_140027B69
0x140027b0d  lea     rax, WPP_RECORDER_INITIALIZED
0x140027b14  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140027b1b  jz      short loc_140027B5F
0x140027b1d  mov     rcx, cs:wil_details_featureDescriptors_a
0x140027b24  lea     rax, aOnecoreBaseFsW_1; "onecore\\base\\fs\\wci\\wcifs\\utils.c"
0x140027b2b  mov     dword ptr [rsp+110h+RestartScan], edi
0x140027b2f  mov     r9d, 0BDh
0x140027b35  mov     dword ptr [rsp+110h+FileName], 2033h
0x140027b3d  mov     r8d, 0Dh
0x140027b43  mov     qword ptr [rsp+110h+ReturnSingleEntry], rax
0x140027b48  mov     dl, 4
0x140027b4a  mov     rcx, [rcx+40h]
0x140027b4e  lea     rax, WPP_7fe91d13bb4232a4ef347966c958c4d1_Traceguids
0x140027b55  mov     qword ptr [rsp+110h+FileInformationClass], rax
0x140027b5a  call    WPP_RECORDER_SF_sDd
0x140027b5f  mov     edi, 0C0000101h
0x140027b64  jmp     loc_140027EDD
0x140027b69  mov     r8, [rbx+20h]
0x140027b6d  mov     rcx, r12
0x140027b70  mov     rdx, [rbx+18h]
0x140027b74  call    WcRemoveTombstonesFromDirectory
0x140027b79  mov     edi, eax
0x140027b7b  test    eax, eax
0x140027b7d  jns     loc_140027E32
0x140027b83  lea     rax, WPP_RECORDER_INITIALIZED
0x140027b8a  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140027b91  jz      loc_140027EDD
0x140027b97  mov     dword ptr [rsp+110h+RestartScan], edi
0x140027b9b  mov     r9d, 0BEh
0x140027ba1  mov     dword ptr [rsp+110h+FileName], 2042h
0x140027ba9  mov     dl, 4
0x140027bab  jmp     loc_140027AB7
0x140027bb0  mov     r14, [rbp+57h+Context]
0x140027bb4  mov     rdx, [rbp+57h+var_B0]
0x140027bb8  mov     rcx, r14
0x140027bbb  call    WcIsPlaceHolderStream
0x140027bc0  test    al, al
0x140027bc2  jnz     loc_140027E2F
0x140027bc8  mov     rcx, r14
0x140027bcb  call    WcIsPlaceHolder
0x140027bd0  xor     r14d, r14d
0x140027bd3  test    al, al
0x140027bd5  jz      loc_140027E32
0x140027bdb  mov     r8, [rbx+20h]; Object
0x140027bdf  lea     r9d, [r14+2]
0x140027be3  mov     rdx, [rbx+18h]; FltObject
0x140027be7  mov     rcx, r12; CallbackData
0x140027bea  call    WcSetPlaceHolderFlagsSynchronized
0x140027bef  mov     edi, eax
0x140027bf1  test    eax, eax
0x140027bf3  jns     loc_140027EDD
0x140027bf9  lea     rax, WPP_RECORDER_INITIALIZED
0x140027c00  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140027c07  jz      loc_140027EDD
0x140027c0d  jmp     loc_140027AA3
0x140027c12  lea     r8, [rbp+57h+FileNameInformation]; FileNameInformation
0x140027c16  mov     edx, 101h; NameOptions
0x140027c1b  mov     rcx, r12; CallbackData
0x140027c1e  call    cs:__imp_FltGetFileNameInformation
0x140027c25  nop     dword ptr [rax+rax+00h]
0x140027c2a  mov     edi, eax
0x140027c2c  test    eax, eax
0x140027c2e  js      loc_140027EDD
0x140027c34  mov     rcx, [rbp+57h+FileNameInformation]; FileNameInformation
0x140027c38  call    cs:__imp_FltParseFileNameInformation
0x140027c3f  nop     dword ptr [rax+rax+00h]
0x140027c44  mov     edi, eax
0x140027c46  test    eax, eax
0x140027c48  js      loc_140027EDD
0x140027c4e  mov     rdx, [rbp+57h+FileNameInformation]
0x140027c52  cmp     [rdx+48h], r14w
0x140027c57  jnz     loc_140027EDD
0x140027c5d  movups  xmm0, xmmword ptr [rdx+8]
0x140027c61  mov     r12d, 2
0x140027c67  movups  [rbp+57h+var_80], xmm0
0x140027c6b  movd    ecx, xmm0
0x140027c6f  lea     r8d, [r12+27h]
0x140027c74  sub     cx, [rdx+58h]
0x140027c78  movzx   eax, cx
0x140027c7b  sub     ax, r12w
0x140027c7f  mov     word ptr [rbp+57h+var_80], ax
0x140027c83  cmp     ax, [rdx+18h]
0x140027c87  lea     rdx, [rbp+57h+var_80]
0x140027c8b  cmovz   ax, cx
0x140027c8f  mov     rcx, [rbx+18h]
0x140027c93  mov     word ptr [rbp+57h+var_80], ax
0x140027c97  lea     rax, [rbp+57h+var_BF]
0x140027c9b  mov     r9d, [r13+24h]
0x140027c9f  mov     [rsp+110h+FileName], rax
0x140027ca4  lea     rax, [rbp+57h+Object]
0x140027ca8  mov     qword ptr [rsp+110h+ReturnSingleEntry], rax
0x140027cad  lea     rax, [rbp+57h+FileHandle]
0x140027cb1  mov     qword ptr [rsp+110h+FileInformationClass], rax; int
0x140027cb6  call    WcOpenPlaceHolder
0x140027cbb  mov     edi, eax
0x140027cbd  test    eax, eax
0x140027cbf  jns     short loc_140027D25
0x140027cc1  lea     rax, WPP_RECORDER_INITIALIZED
0x140027cc8  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140027ccf  jz      loc_140027EDD
0x140027cd5  mov     rcx, cs:wil_details_featureDescriptors_a
0x140027cdc  lea     rax, [rbp+57h+var_80]
0x140027ce0  mov     [rsp+110h+LengthReturned], rax
0x140027ce5  lea     r8d, [r12+8]
0x140027cea  mov     dword ptr [rsp+110h+RestartScan], edi
0x140027cee  lea     rax, aOnecoreBaseFsW_1; "onecore\\base\\fs\\wci\\wcifs\\utils.c"
0x140027cf5  mov     dword ptr [rsp+110h+FileName], 209Fh
0x140027cfd  mov     r9d, 0C0h
0x140027d03  mov     rcx, [rcx+40h]
0x140027d07  mov     dl, r12b
0x140027d0a  mov     qword ptr [rsp+110h+ReturnSingleEntry], rax
0x140027d0f  lea     rax, WPP_7fe91d13bb4232a4ef347966c958c4d1_Traceguids
0x140027d16  mov     qword ptr [rsp+110h+FileInformationClass], rax
0x140027d1b  call    WPP_RECORDER_SF_sDdZ
0x140027d20  jmp     loc_140027EDD
0x140027d25  cmp     [rbp+57h+var_BF], r14b
0x140027d29  jz      loc_140027DEB
0x140027d2f  mov     rdx, [rbp+57h+Object]; FileObject
0x140027d33  lea     rax, [rbp+57h+var_A0]
0x140027d37  mov     rcx, [rbx+18h]; Instance
0x140027d3b  mov     r9d, 1
0x140027d41  mov     [rsp+110h+FileName], rax; __int64
0x140027d46  mov     r8, r13
0x140027d49  lea     rax, [rbp+57h+var_98]
0x140027d4d  mov     qword ptr [rsp+110h+ReturnSingleEntry], rax; __int64
0x140027d52  call    WcGetSetContextFileObject
0x140027d57  mov     edi, eax
0x140027d59  test    eax, eax
0x140027d5b  js      loc_140027ECB
0x140027d61  cmp     eax, 104h
0x140027d66  jz      loc_140027ED2
0x140027d6c  mov     rsi, [rbp+57h+var_A0]
0x140027d70  mov     r15, [rbp+57h+var_98]
0x140027d74  mov     rdx, rsi
0x140027d77  mov     rcx, r15
0x140027d7a  call    WcIsPlaceHolderDirectory
0x140027d7f  test    al, al
0x140027d81  jz      short loc_140027DF3
0x140027d83  mov     rcx, rsi
0x140027d86  call    WcIsSourcedStream
0x140027d8b  test    al, al
0x140027d8d  jz      short loc_140027DF3
0x140027d8f  mov     rcx, rsi
0x140027d92  call    WcGetSource
0x140027d97  mov     rcx, [rbp+57h+FileNameInformation]
0x140027d9b  lea     r8, [rbp+57h+FileInformation]; FileInformation
0x140027d9f  mov     [rsp+110h+LengthReturned], r14; LengthReturned
0x140027da4  add     rcx, 58h ; 'X'
0x140027da8  mov     [rsp+110h+RestartScan], 1; RestartScan
0x140027dad  mov     r9d, 10h; Length
0x140027db3  mov     rdx, [rax+10h]; FileObject
0x140027db7  mov     [rsp+110h+FileName], rcx; FileName
  ... truncated ...
```
