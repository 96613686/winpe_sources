# WcPrepareForDelete

- ea: `0x140027854`
- end: `0x140027f1d`
- name: `WcPrepareForDelete`
- size: `1737`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA CallbackData)`
- caller_count: `2`
- callee_count: `20`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140027730`
- `0x1400343c0`

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
- `0x140027854`
- `0x14002893c`
- `0x140029608`
- `0x140029f34`
- `0x14002a0cc`
- `0x14002d5f8`
- `0x14002ee54`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x140027ebc`
- `ntoskrnl!ObfDereferenceObject` at `0x140027ebc`
- `ntoskrnl!ExAcquireFastMutex` at `0x140027e55`
- `ntoskrnl!ExAcquireFastMutex` at `0x140027e55`
- `ntoskrnl!ExReleaseFastMutex` at `0x140027e6d`
- `ntoskrnl!ExReleaseFastMutex` at `0x140027e6d`
- `FLTMGR!FltQueryDirectoryFile` at `0x140027d7c`
- `FLTMGR!FltQueryDirectoryFile` at `0x140027d7c`
- `FLTMGR!FltClose` at `0x140027eab`
- `FLTMGR!FltClose` at `0x140027eab`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140027e9a`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140027e9a`
- `FLTMGR!FltGetFileNameInformation` at `0x140027bce`
- `FLTMGR!FltGetFileNameInformation` at `0x140027bce`
- `FLTMGR!FltParseFileNameInformation` at `0x140027be8`
- `FLTMGR!FltParseFileNameInformation` at `0x140027be8`
- `FLTMGR!FltQueryInformationFile` at `0x140027e07`
- `FLTMGR!FltQueryInformationFile` at `0x140027e07`
- `FLTMGR!FltReleaseContext` at `0x140027ed0`
- `FLTMGR!FltReleaseContext` at `0x140027ee4`
- `FLTMGR!FltReleaseContext` at `0x140027ef8`
- `FLTMGR!FltReleaseContext` at `0x140027f0c`
- `FLTMGR!FltReleaseContext` at `0x140027ed0`
- `FLTMGR!FltReleaseContext` at `0x140027ee4`
- `FLTMGR!FltReleaseContext` at `0x140027ef8`
- `FLTMGR!FltReleaseContext` at `0x140027f0c`

## pseudocode

```c
__int64 __fastcall WcPrepareForDelete(PFLT_CALLBACK_DATA CallbackData, __int64 a2)
{
  __int64 v2; // r8
  __int64 v4; // rdx
  NTSTATUS IsDirectoryEmpty; // edi
  __int64 UnionContext; // rax
  int v8; // edx
  __int64 v9; // r13
  int v11; // edx
  int v12; // r9d
  __int16 v13; // cx
  __int16 v14; // ax
  __int64 v15; // rcx
  int v16; // edx
  char FileName; // [rsp+30h] [rbp-89h]
  char RestartScan; // [rsp+38h] [rbp-81h]
  PFLT_CONTEXT v19; // [rsp+60h] [rbp-59h] BYREF
  PFLT_FILE_NAME_INFORMATION FileNameInformation[3]; // [rsp+68h] [rbp-51h] BYREF
  PVOID Object; // [rsp+80h] [rbp-39h]
  HANDLE FileHandle; // [rsp+88h] [rbp-31h]
  __m128i v23[2]; // [rsp+90h] [rbp-29h] BYREF
  _OWORD v24[2]; // [rsp+B0h] [rbp-9h] BYREF
  int v25[2]; // [rsp+D0h] [rbp+17h]

  v2 = *(_QWORD *)(a2 + 32);
  v19 = 0;
  v4 = *(_QWORD *)(a2 + 24);
  IsDirectoryEmpty = 0;
  memset(FileNameInformation, 0, sizeof(FileNameInformation));
  memset(v23, 0, sizeof(v23));
  FileHandle = 0;
  Object = 0;
  *(_QWORD *)v25 = 0;
  memset(v24, 0, sizeof(v24));
  UnionContext = WcGetUnionContext(CallbackData, v4, v2);
  v9 = UnionContext;
  if ( UnionContext )
  {
    if ( *(_DWORD *)(UnionContext + 24) == 2 )
    {
      IsDirectoryEmpty = -1073741637;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v8) = 2;
        WPP_RECORDER_SF_sD(
          WPP_GLOBAL_Control->DeviceExtension,
          v8,
          13,
          187,
          (__int64)WPP_7fe91d13bb4232a4ef347966c958c4d1_Traceguids,
          (__int64)"onecore\\base\\fs\\wci\\wcifs\\utils.c",
          8);
      }
      goto LABEL_44;
    }
    if ( !(unsigned __int8)WcGetContextFileObject(*(PFLT_INSTANCE *)(a2 + 24), *(PFILE_OBJECT *)(a2 + 32)) )
    {
      IsDirectoryEmpty = FltGetFileNameInformation(CallbackData, 0x101u, FileNameInformation);
      if ( IsDirectoryEmpty >= 0 )
      {
        IsDirectoryEmpty = FltParseFileNameInformation(FileNameInformation[0]);
        if ( IsDirectoryEmpty >= 0 && !FileNameInformation[0]->Stream.Length )
        {
          v23[0] = (__m128i)FileNameInformation[0]->Name;
          v13 = _mm_cvtsi128_si32(v23[0]) - FileNameInformation[0]->FinalComponent.Length;
          v14 = v13 - 2;
          v23[0].m128i_i16[0] = v13 - 2;
          if ( v13 - 2 == FileNameInformation[0]->Volume.Length )
            v14 = v13;
          v15 = *(_QWORD *)(a2 + 24);
          v23[0].m128i_i16[0] = v14;
          IsDirectoryEmpty = WcOpenPlaceHolder(v15, v23, 41, *(unsigned int *)(v9 + 36));
          if ( IsDirectoryEmpty >= 0 )
          {
            IsDirectoryEmpty = 0;
          }
          else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v16) = 2;
            WPP_RECORDER_SF_sDdZ(
              WPP_GLOBAL_Control->DeviceExtension,
              v16,
              10,
              192,
              (__int64)WPP_7fe91d13bb4232a4ef347966c958c4d1_Traceguids,
              (__int64)"onecore\\base\\fs\\wci\\wcifs\\utils.c",
              159,
              IsDirectoryEmpty,
              (__int64)v23);
          }
        }
      }
      goto LABEL_44;
    }
    if ( (unsigned __int8)WcIsPlaceHolderDirectory(0, v19) )
    {
      if ( (unsigned __int8)WcIsSourcedStream(v19) )
      {
        IsDirectoryEmpty = WcIsDirectoryEmpty(*(PFLT_INSTANCE *)(a2 + 24), *(PFILE_OBJECT *)(a2 + 32));
        if ( IsDirectoryEmpty >= 0 )
        {
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v11) = 4;
            WPP_RECORDER_SF_sDd(
              WPP_GLOBAL_Control->DeviceExtension,
              v11,
              13,
              189,
              (__int64)WPP_7fe91d13bb4232a4ef347966c958c4d1_Traceguids,
              (__int64)"onecore\\base\\fs\\wci\\wcifs\\utils.c",
              51,
              IsDirectoryEmpty);
          }
          IsDirectoryEmpty = -1073741567;
          goto LABEL_44;
        }
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
LABEL_44:
          WcReleaseUnionContext(v9);
          goto LABEL_2;
        }
        RestartScan = IsDirectoryEmpty;
        v12 = 188;
        FileName = 36;
        LOBYTE(v11) = 2;
LABEL_20:
        WPP_RECORDER_SF_sDd(
          WPP_GLOBAL_Control->DeviceExtension,
          v11,
          13,
          v12,
          (__int64)WPP_7fe91d13bb4232a4ef347966c958c4d1_Traceguids,
          (__int64)"onecore\\base\\fs\\wci\\wcifs\\utils.c",
          FileName,
          RestartScan);
        goto LABEL_44;
      }
      IsDirectoryEmpty = WcRemoveTombstonesFromDirectory(CallbackData, *(_QWORD *)(a2 + 24), *(_QWORD *)(a2 + 32));
      if ( IsDirectoryEmpty < 0 )
      {
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_44;
        RestartScan = IsDirectoryEmpty;
        v12 = 190;
        FileName = 66;
        LOBYTE(v11) = 4;
        goto LABEL_20;
      }
    }
    else if ( !(unsigned __int8)WcIsPlaceHolderStream(0, v19) && (unsigned __int8)WcIsPlaceHolder(0) )
    {
      IsDirectoryEmpty = WcSetPlaceHolderFlagsSynchronized(CallbackData, *(PVOID *)(a2 + 24), *(PVOID *)(a2 + 32));
      if ( IsDirectoryEmpty >= 0 || WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_44;
      RestartScan = IsDirectoryEmpty;
      v12 = 191;
      FileName = 89;
      LOBYTE(v11) = 3;
      goto LABEL_20;
    }
    IsDirectoryEmpty = FltQueryInformationFile(
                         *(PFLT_INSTANCE *)(a2 + 24),
                         *(PFILE_OBJECT *)(a2 + 32),
                         v24,
                         0x28u,
                         FileBasicInformation,
                         0);
    if ( IsDirectoryEmpty >= 0 )
    {
      IsDirectoryEmpty = WcGetSetStreamContext(
                           *(PFLT_INSTANCE *)(a2 + 24),
                           *(PFILE_OBJECT *)(a2 + 32),
                           0,
                           v25[0],
                           0,
                           0,
                           (__int64)&v19);
      if ( IsDirectoryEmpty >= 0 )
      {
        ExAcquireFastMutex((PFAST_MUTEX)8);
        *((_BYTE *)v19 + 28) = 1;
        ExReleaseFastMutex((PFAST_MUTEX)8);
      }
    }
    goto LABEL_44;
  }
LABEL_2:
  if ( FileNameInformation[0] )
    FltReleaseFileNameInformation(FileNameInformation[0]);
  if ( FileHandle )
    FltClose(FileHandle);
  if ( Object )
    ObfDereferenceObject(Object);
  if ( v19 )
    FltReleaseContext(v19);
  return (unsigned int)IsDirectoryEmpty;
}

```

## disassembly

```asm
0x140027854  mov     [rsp-8+arg_10], rbx
0x140027859  push    rbp
0x14002785a  push    rsi
0x14002785b  push    rdi
0x14002785c  push    r12
0x14002785e  push    r13
0x140027860  push    r14
0x140027862  push    r15
0x140027864  lea     rbp, [rsp-27h]
0x140027869  sub     rsp, 0E0h
0x140027870  mov     rax, cs:__security_cookie
0x140027877  xor     rax, rsp
0x14002787a  mov     [rbp+57h+var_38], rax
0x14002787e  mov     r8, [rdx+20h]
0x140027882  xor     r14d, r14d
0x140027885  xorps   xmm0, xmm0
0x140027888  mov     [rbp+57h+var_B0], r14
0x14002788c  xorps   xmm1, xmm1
0x14002788f  mov     [rbp+57h+Context], r14
0x140027893  mov     rbx, rdx
0x140027896  mov     [rbp+57h+var_A0], r14
0x14002789a  mov     rdx, [rdx+18h]
0x14002789e  xor     eax, eax
0x1400278a0  mov     edi, r14d
0x1400278a3  mov     [rbp+57h+var_98], r14
0x1400278a7  mov     esi, r14d
0x1400278aa  mov     [rbp+57h+var_C0], r14b
0x1400278ae  mov     r15d, r14d
0x1400278b1  mov     [rbp+57h+FileNameInformation], r14
0x1400278b5  movups  [rbp+57h+var_80], xmm0
0x1400278b9  mov     [rbp+57h+FileHandle], r14
0x1400278bd  mov     r12, rcx
0x1400278c0  mov     [rbp+57h+Object], r14
0x1400278c4  mov     [rbp+57h+var_BF], r14b
0x1400278c8  movups  [rbp+57h+FileInformation], xmm0
0x1400278cc  mov     qword ptr [rbp+57h+var_40], rax
0x1400278d0  movups  [rbp+57h+var_60], xmm1
0x1400278d4  movups  [rbp+57h+var_50], xmm1
0x1400278d8  call    WcGetUnionContext
0x1400278dd  mov     r13, rax
0x1400278e0  test    rax, rax
0x1400278e3  jnz     short loc_140027962
0x1400278e5  mov     rcx, [rbp+57h+FileNameInformation]; FileNameInformation
0x1400278e9  test    rcx, rcx
0x1400278ec  jnz     loc_140027E9A
0x1400278f2  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x1400278f6  test    rcx, rcx
0x1400278f9  jnz     loc_140027EAB
0x1400278ff  mov     rcx, [rbp+57h+Object]; Object
0x140027903  test    rcx, rcx
0x140027906  jnz     loc_140027EBC
0x14002790c  mov     r14, [rbp+57h+Context]
0x140027910  test    r14, r14
0x140027913  jnz     loc_140027ECD
0x140027919  mov     r14, [rbp+57h+var_B0]
0x14002791d  test    r14, r14
0x140027920  jnz     loc_140027EE1
0x140027926  test    r15, r15
0x140027929  jnz     loc_140027EF5
0x14002792f  test    rsi, rsi
0x140027932  jnz     loc_140027F09
0x140027938  mov     eax, edi
0x14002793a  mov     rcx, [rbp+57h+var_38]
0x14002793e  xor     rcx, rsp; StackCookie
0x140027941  call    __security_check_cookie
0x140027946  mov     rbx, [rsp+110h+arg_10]
0x14002794e  add     rsp, 0E0h
0x140027955  pop     r15
0x140027957  pop     r14
0x140027959  pop     r13
0x14002795b  pop     r12
0x14002795d  pop     rdi
0x14002795e  pop     rsi
0x14002795f  pop     rbp
0x140027960  retn
0x140027962  mov     ecx, 2
0x140027967  cmp     [rax+18h], ecx
0x14002796a  jnz     short loc_1400279C6
0x14002796c  mov     edi, 0C00000BBh
0x140027971  lea     rax, WPP_RECORDER_INITIALIZED
0x140027978  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002797f  jz      loc_140027E8D
0x140027985  lea     r8d, [rcx+0Bh]
0x140027989  mov     dword ptr [rsp+110h+FileName], 2008h
0x140027991  mov     dl, cl
0x140027993  lea     rax, aOnecoreBaseFsW_1; "onecore\\base\\fs\\wci\\wcifs\\utils.c"
0x14002799a  mov     rcx, cs:WPP_GLOBAL_Control
0x1400279a1  mov     r9d, 0BBh
0x1400279a7  mov     qword ptr [rsp+110h+ReturnSingleEntry], rax
0x1400279ac  lea     rax, WPP_7fe91d13bb4232a4ef347966c958c4d1_Traceguids
0x1400279b3  mov     qword ptr [rsp+110h+FileInformationClass], rax
0x1400279b8  mov     rcx, [rcx+40h]
0x1400279bc  call    WPP_RECORDER_SF_sD
0x1400279c1  jmp     loc_140027E8D
0x1400279c6  mov     rdx, [rbx+20h]; FileObject
0x1400279ca  lea     r9, [rbp+57h+var_B0]
0x1400279ce  mov     rcx, [rbx+18h]; Instance
0x1400279d2  lea     r8, [rbp+57h+Context]
0x1400279d6  call    WcGetContextFileObject
0x1400279db  test    al, al
0x1400279dd  jz      loc_140027BC2
0x1400279e3  mov     r14, [rbp+57h+var_B0]
0x1400279e7  mov     rcx, [rbp+57h+Context]
0x1400279eb  mov     rdx, r14
0x1400279ee  call    WcIsPlaceHolderDirectory
0x1400279f3  test    al, al
0x1400279f5  jz      loc_140027B60
0x1400279fb  mov     rcx, r14
0x1400279fe  call    WcIsSourcedStream
0x140027a03  xor     r14d, r14d
0x140027a06  test    al, al
0x140027a08  jz      loc_140027B19
0x140027a0e  mov     rdx, [rbx+20h]; FileObject
0x140027a12  lea     r8, [rbp+57h+var_C0]
0x140027a16  mov     rcx, [rbx+18h]; Instance
0x140027a1a  call    WcIsDirectoryEmpty
0x140027a1f  mov     edi, eax
0x140027a21  test    eax, eax
0x140027a23  jns     loc_140027AB7
0x140027a29  lea     rax, WPP_RECORDER_INITIALIZED
0x140027a30  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140027a37  jz      loc_140027E8D
0x140027a3d  mov     dword ptr [rsp+110h+RestartScan], edi
0x140027a41  mov     r9d, 0BCh
0x140027a47  mov     dword ptr [rsp+110h+FileName], 2024h
0x140027a4f  mov     dl, 2
0x140027a51  jmp     short loc_140027A67
0x140027a53  mov     dword ptr [rsp+110h+RestartScan], edi
0x140027a57  mov     r9d, 0BFh
0x140027a5d  mov     dword ptr [rsp+110h+FileName], 2059h
0x140027a65  mov     dl, 3
0x140027a67  mov     r8d, 0Dh
0x140027a6d  jmp     short loc_140027A8A
0x140027a6f  mov     dword ptr [rsp+110h+RestartScan], edi
0x140027a73  mov     r9d, 0C1h
0x140027a79  mov     dword ptr [rsp+110h+FileName], 2103h
0x140027a81  mov     r8d, 5
0x140027a87  mov     dl, r12b
0x140027a8a  mov     rcx, cs:WPP_GLOBAL_Control
0x140027a91  lea     rax, aOnecoreBaseFsW_1; "onecore\\base\\fs\\wci\\wcifs\\utils.c"
0x140027a98  mov     qword ptr [rsp+110h+ReturnSingleEntry], rax
0x140027a9d  lea     rax, WPP_7fe91d13bb4232a4ef347966c958c4d1_Traceguids
0x140027aa4  mov     qword ptr [rsp+110h+FileInformationClass], rax
0x140027aa9  mov     rcx, [rcx+40h]
0x140027aad  call    WPP_RECORDER_SF_sDd
0x140027ab2  jmp     loc_140027E8D
0x140027ab7  cmp     [rbp+57h+var_C0], r14b
0x140027abb  jnz     short loc_140027B19
0x140027abd  lea     rax, WPP_RECORDER_INITIALIZED
0x140027ac4  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140027acb  jz      short loc_140027B0F
0x140027acd  mov     rcx, cs:WPP_GLOBAL_Control
0x140027ad4  lea     rax, aOnecoreBaseFsW_1; "onecore\\base\\fs\\wci\\wcifs\\utils.c"
0x140027adb  mov     dword ptr [rsp+110h+RestartScan], edi
0x140027adf  mov     r9d, 0BDh
0x140027ae5  mov     dword ptr [rsp+110h+FileName], 2033h
0x140027aed  mov     r8d, 0Dh
0x140027af3  mov     qword ptr [rsp+110h+ReturnSingleEntry], rax
0x140027af8  mov     dl, 4
0x140027afa  mov     rcx, [rcx+40h]
0x140027afe  lea     rax, WPP_7fe91d13bb4232a4ef347966c958c4d1_Traceguids
0x140027b05  mov     qword ptr [rsp+110h+FileInformationClass], rax
0x140027b0a  call    WPP_RECORDER_SF_sDd
0x140027b0f  mov     edi, 0C0000101h
0x140027b14  jmp     loc_140027E8D
0x140027b19  mov     r8, [rbx+20h]
0x140027b1d  mov     rcx, r12
0x140027b20  mov     rdx, [rbx+18h]
0x140027b24  call    WcRemoveTombstonesFromDirectory
0x140027b29  mov     edi, eax
0x140027b2b  test    eax, eax
0x140027b2d  jns     loc_140027DE2
0x140027b33  lea     rax, WPP_RECORDER_INITIALIZED
0x140027b3a  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140027b41  jz      loc_140027E8D
0x140027b47  mov     dword ptr [rsp+110h+RestartScan], edi
0x140027b4b  mov     r9d, 0BEh
0x140027b51  mov     dword ptr [rsp+110h+FileName], 2042h
0x140027b59  mov     dl, 4
0x140027b5b  jmp     loc_140027A67
0x140027b60  mov     r14, [rbp+57h+Context]
0x140027b64  mov     rdx, [rbp+57h+var_B0]
0x140027b68  mov     rcx, r14
0x140027b6b  call    WcIsPlaceHolderStream
0x140027b70  test    al, al
0x140027b72  jnz     loc_140027DDF
0x140027b78  mov     rcx, r14
0x140027b7b  call    WcIsPlaceHolder
0x140027b80  xor     r14d, r14d
0x140027b83  test    al, al
0x140027b85  jz      loc_140027DE2
0x140027b8b  mov     r8, [rbx+20h]; Object
0x140027b8f  lea     r9d, [r14+2]
0x140027b93  mov     rdx, [rbx+18h]; FltObject
0x140027b97  mov     rcx, r12; CallbackData
0x140027b9a  call    WcSetPlaceHolderFlagsSynchronized
0x140027b9f  mov     edi, eax
0x140027ba1  test    eax, eax
0x140027ba3  jns     loc_140027E8D
0x140027ba9  lea     rax, WPP_RECORDER_INITIALIZED
0x140027bb0  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140027bb7  jz      loc_140027E8D
0x140027bbd  jmp     loc_140027A53
0x140027bc2  lea     r8, [rbp+57h+FileNameInformation]; FileNameInformation
0x140027bc6  mov     edx, 101h; NameOptions
0x140027bcb  mov     rcx, r12; CallbackData
0x140027bce  call    cs:__imp_FltGetFileNameInformation
0x140027bd5  nop     dword ptr [rax+rax+00h]
0x140027bda  mov     edi, eax
0x140027bdc  test    eax, eax
0x140027bde  js      loc_140027E8D
0x140027be4  mov     rcx, [rbp+57h+FileNameInformation]; FileNameInformation
0x140027be8  call    cs:__imp_FltParseFileNameInformation
0x140027bef  nop     dword ptr [rax+rax+00h]
0x140027bf4  mov     edi, eax
0x140027bf6  test    eax, eax
0x140027bf8  js      loc_140027E8D
0x140027bfe  mov     rdx, [rbp+57h+FileNameInformation]
0x140027c02  cmp     [rdx+48h], r14w
0x140027c07  jnz     loc_140027E8D
0x140027c0d  movups  xmm0, xmmword ptr [rdx+8]
0x140027c11  mov     r12d, 2
0x140027c17  movups  [rbp+57h+var_80], xmm0
0x140027c1b  movd    ecx, xmm0
0x140027c1f  lea     r8d, [r12+27h]
0x140027c24  sub     cx, [rdx+58h]
0x140027c28  movzx   eax, cx
0x140027c2b  sub     ax, r12w
0x140027c2f  mov     word ptr [rbp+57h+var_80], ax
0x140027c33  cmp     ax, [rdx+18h]
0x140027c37  lea     rdx, [rbp+57h+var_80]
0x140027c3b  cmovz   ax, cx
0x140027c3f  mov     rcx, [rbx+18h]
0x140027c43  mov     word ptr [rbp+57h+var_80], ax
0x140027c47  lea     rax, [rbp+57h+var_BF]
0x140027c4b  mov     r9d, [r13+24h]
0x140027c4f  mov     [rsp+110h+FileName], rax
0x140027c54  lea     rax, [rbp+57h+Object]
0x140027c58  mov     qword ptr [rsp+110h+ReturnSingleEntry], rax
0x140027c5d  lea     rax, [rbp+57h+FileHandle]
0x140027c61  mov     qword ptr [rsp+110h+FileInformationClass], rax; int
0x140027c66  call    WcOpenPlaceHolder
0x140027c6b  mov     edi, eax
0x140027c6d  test    eax, eax
0x140027c6f  jns     short loc_140027CD5
0x140027c71  lea     rax, WPP_RECORDER_INITIALIZED
0x140027c78  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140027c7f  jz      loc_140027E8D
0x140027c85  mov     rcx, cs:WPP_GLOBAL_Control
0x140027c8c  lea     rax, [rbp+57h+var_80]
0x140027c90  mov     [rsp+110h+LengthReturned], rax
0x140027c95  lea     r8d, [r12+8]
0x140027c9a  mov     dword ptr [rsp+110h+RestartScan], edi
0x140027c9e  lea     rax, aOnecoreBaseFsW_1; "onecore\\base\\fs\\wci\\wcifs\\utils.c"
0x140027ca5  mov     dword ptr [rsp+110h+FileName], 209Fh
0x140027cad  mov     r9d, 0C0h
0x140027cb3  mov     rcx, [rcx+40h]
0x140027cb7  mov     dl, r12b
0x140027cba  mov     qword ptr [rsp+110h+ReturnSingleEntry], rax
0x140027cbf  lea     rax, WPP_7fe91d13bb4232a4ef347966c958c4d1_Traceguids
0x140027cc6  mov     qword ptr [rsp+110h+FileInformationClass], rax
0x140027ccb  call    WPP_RECORDER_SF_sDdZ
0x140027cd0  jmp     loc_140027E8D
0x140027cd5  cmp     [rbp+57h+var_BF], r14b
0x140027cd9  jz      loc_140027D9B
0x140027cdf  mov     rdx, [rbp+57h+Object]; FileObject
0x140027ce3  lea     rax, [rbp+57h+var_A0]
0x140027ce7  mov     rcx, [rbx+18h]; Instance
0x140027ceb  mov     r9d, 1
0x140027cf1  mov     [rsp+110h+FileName], rax; __int64
0x140027cf6  mov     r8, r13
0x140027cf9  lea     rax, [rbp+57h+var_98]
0x140027cfd  mov     qword ptr [rsp+110h+ReturnSingleEntry], rax; __int64
0x140027d02  call    WcGetSetContextFileObject
0x140027d07  mov     edi, eax
0x140027d09  test    eax, eax
0x140027d0b  js      loc_140027E7B
0x140027d11  cmp     eax, 104h
0x140027d16  jz      loc_140027E82
0x140027d1c  mov     rsi, [rbp+57h+var_A0]
0x140027d20  mov     r15, [rbp+57h+var_98]
0x140027d24  mov     rdx, rsi
0x140027d27  mov     rcx, r15
0x140027d2a  call    WcIsPlaceHolderDirectory
0x140027d2f  test    al, al
0x140027d31  jz      short loc_140027DA3
0x140027d33  mov     rcx, rsi
0x140027d36  call    WcIsSourcedStream
0x140027d3b  test    al, al
0x140027d3d  jz      short loc_140027DA3
0x140027d3f  mov     rcx, rsi
0x140027d42  call    WcGetSource
0x140027d47  mov     rcx, [rbp+57h+FileNameInformation]
0x140027d4b  lea     r8, [rbp+57h+FileInformation]; FileInformation
0x140027d4f  mov     [rsp+110h+LengthReturned], r14; LengthReturned
0x140027d54  add     rcx, 58h ; 'X'
0x140027d58  mov     [rsp+110h+RestartScan], 1; RestartScan
0x140027d5d  mov     r9d, 10h; Length
0x140027d63  mov     rdx, [rax+10h]; FileObject
0x140027d67  mov     [rsp+110h+FileName], rcx; FileName
  ... truncated ...
```
