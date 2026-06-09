# VhdmpiOpenFileForMatching

- ea: `0x1400ecb20`
- end: `0x1400ed306`
- name: `VhdmpiOpenFileForMatching`
- size: `2022`
- prototype: `__int64 __fastcall(struct _UNICODE_STRING *, char, unsigned __int8, __int64)`
- caller_count: `6`
- callee_count: `18`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x14003fba8`
- `0x140040040`
- `0x1400a2db4`
- `0x1400c7664`
- `0x1400cf084`
- `0x1400ec0d8`

## callees

- `0x1400010d0`
- `0x140014e5c`
- `0x14001bdb0`
- `0x14001dbb4`
- `0x140020874`
- `0x140023560`
- `0x14002debc`
- `0x140035e94`
- `0x14005d7c0`
- `0x14009d9a4`
- `0x14009e1c0`
- `0x1400ad718`
- `0x1400d0ff4`
- `0x1400e5b54`
- `0x1400e8108`
- `0x1400e9200`
- `0x1400eac0c`
- `0x1400ecb20`

## import_xrefs

- `ntoskrnl!ZwFsControlFile` at `0x1400ed1cb`
- `ntoskrnl!ZwFsControlFile` at `0x1400ed1cb`
- `ntoskrnl!ZwWaitForSingleObject` at `0x1400ed1e7`
- `ntoskrnl!ZwWaitForSingleObject` at `0x1400ed1e7`
- `ntoskrnl!IoFileObjectType` at `0x1400ed0d9`
- `ntoskrnl!IoCreateFileEx` at `0x1400ecda5`
- `ntoskrnl!IoCreateFileEx` at `0x1400ecda5`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400ed106`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400ed106`
- `ntoskrnl!ObfDereferenceObject` at `0x1400ed273`
- `ntoskrnl!ObfDereferenceObject` at `0x1400ed273`
- `ntoskrnl!ZwClose` at `0x1400ed0b2`
- `ntoskrnl!ZwClose` at `0x1400ed2a5`
- `ntoskrnl!ZwClose` at `0x1400ed0b2`
- `ntoskrnl!ZwClose` at `0x1400ed2a5`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ed2be`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ed2be`
- `ntoskrnl!EtwActivityIdControl` at `0x1400eccc0`
- `ntoskrnl!EtwActivityIdControl` at `0x1400eccc0`

## string_xrefs

- `0x1400ecc5f`: `VhdmpiOpenFileForMatching`
- `0x1400ece86`: `VhdmpiOpenFileForMatching`
- `0x1400ecf8a`: `VhdmpiOpenFileForMatching`
- `0x1400ed06e`: `VhdmpiOpenFileForMatching`
- `0x1400ed254`: `VhdmpiOpenFileForMatching`
- `0x1400ecc51`: `Opening file '%wZ' for matching/attribute purposes.`
- `0x1400ecf6e`: `Successfully opened file '%wZ' for matching/attribute purposes.`
- `0x1400ece7a`: `Failed to open file '%wZ' for matching: 0x%08x`

## pseudocode

```c
__int64 __fastcall VhdmpiOpenFileForMatching(struct _UNICODE_STRING *a1, char a2, unsigned __int8 a3, __int64 a4)
{
  wchar_t *v8; // rdi
  NTSTATUS FileId; // ebx
  ULONG Options; // r12d
  int v11; // edx
  int v12; // eax
  int v13; // r8d
  int *v14; // rsi
  int *v15; // r9
  const wchar_t *v16; // r15
  int v17; // ecx
  int v18; // r9d
  const wchar_t *v19; // rax
  int v20; // r8d
  int v21; // ecx
  int v22; // r9d
  int v23; // ecx
  int v24; // ecx
  int v25; // r9d
  int v26; // ecx
  int v27; // edx
  unsigned __int8 v28; // r15
  unsigned __int8 v29; // r12
  _QWORD *v30; // rsi
  bool v31; // bl
  int v32; // edx
  int v33; // ecx
  char *v34; // rax
  NTSTATUS Status; // eax
  __int64 v36; // rdx
  __int64 v37; // r8
  char AllocationSize; // [rsp+20h] [rbp-E0h]
  unsigned __int8 v40; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int8 v41; // [rsp+81h] [rbp-7Fh] BYREF
  unsigned __int8 v42; // [rsp+82h] [rbp-7Eh] BYREF
  char v43[5]; // [rsp+83h] [rbp-7Dh] BYREF
  wchar_t *v44; // [rsp+88h] [rbp-78h] BYREF
  void *FileHandle; // [rsp+90h] [rbp-70h] BYREF
  const wchar_t *v46; // [rsp+98h] [rbp-68h] BYREF
  PVOID Object; // [rsp+A0h] [rbp-60h] BYREF
  int v48; // [rsp+A8h] [rbp-58h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+B0h] [rbp-50h] BYREF
  struct _UNICODE_STRING v50; // [rsp+C0h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+D0h] [rbp-30h] BYREF
  struct _IO_DRIVER_CREATE_CONTEXT DriverContext; // [rsp+100h] [rbp+0h] BYREF
  __int64 v53; // [rsp+120h] [rbp+20h]
  GUID ActivityId; // [rsp+128h] [rbp+28h] BYREF
  __int64 v55; // [rsp+138h] [rbp+38h]

  *(_OWORD *)a4 = 0;
  v41 = 0;
  *(_OWORD *)(a4 + 16) = 0;
  v53 = 0;
  *(_OWORD *)(a4 + 32) = 0;
  *(_QWORD *)(a4 + 48) = 0;
  v40 = 0;
  Object = 0;
  v42 = 0;
  memset(&DriverContext, 0, sizeof(DriverContext));
  v55 = 0;
  v8 = 0;
  FileHandle = 0;
  IoStatusBlock = 0;
  v44 = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  ActivityId = 0;
  v50 = 0;
  FileId = VhdmpiFileWrapperInitializeDriverCreateContext(&DriverContext);
  if ( FileId < 0 )
    goto LABEL_85;
  FileId = VhdmpiCreateNtFilePath(a1, &v50);
  if ( FileId < 0 )
    goto LABEL_85;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Length = 48;
  ObjectAttributes.Attributes = 576;
  ObjectAttributes.ObjectName = &v50;
  Options = (a2 != 0) + 256;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  FileId = VhdmpiCreateBackingStoreOpenEcp(a3, &DriverContext);
  if ( FileId < 0 )
    goto LABEL_85;
  if ( (unsigned int)dword_140087708 > 5 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 2048) )
    TraceEvents(
      (int)"VhdmpiOpenFileForMatching",
      2859,
      5,
      v11,
      "Opening file '%wZ' for matching/attribute purposes.",
      (char)a1);
  v12 = VhdmpiDuplicateUnicodeStringToString(a1, &v44);
  v8 = v44;
  v14 = &dword_1400613A4;
  if ( v12 < 0 )
    v8 = 0;
  if ( (Microsoft_Windows_VHDMPEnableBits & 1) != 0 )
  {
    v15 = &dword_1400613A4;
    if ( v8 )
      LODWORD(v15) = (_DWORD)v8;
    McTemplateK0zq_EtwWriteTransfer(0, (unsigned int)FileWrapperHandleCreateBegin, v13, (_DWORD)v15, 128);
  }
  EtwActivityIdControl(3u, &ActivityId);
  v16 = L"Unknown";
  v55 = 0;
  if ( (unsigned int)dword_1400876D0 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 0x10000) )
  {
    v48 = 7;
    v19 = L"Unknown";
    LODWORD(v44) = 1048704;
    if ( v8 )
      v19 = v8;
    v43[0] = 1;
    v46 = v19;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v17,
      (unsigned int)&word_14007CF2E,
      (unsigned int)&ActivityId,
      v18,
      (__int64)&v46,
      (__int64)v43,
      (__int64)&v44,
      (__int64)&v48);
  }
  FileId = IoCreateFileEx(
             &FileHandle,
             0x100080u,
             &ObjectAttributes,
             &IoStatusBlock,
             0,
             0x80u,
             7u,
             1u,
             0x400040u,
             0,
             0,
             CreateFileTypeNone,
             0,
             Options,
             &DriverContext);
  if ( FileId == -1073741772 )
  {
    if ( (unsigned int)dword_1400876D0 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 0x10000) )
    {
      LODWORD(v44) = -1073741772;
      if ( v8 )
        v16 = v8;
      v46 = v16;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        v21,
        (unsigned int)&word_14007CE86,
        (unsigned int)&ActivityId,
        v55,
        (__int64)&v46,
        (__int64)&v44);
    }
    if ( (Microsoft_Windows_VHDMPEnableBits & 1) != 0 )
    {
      AllocationSize = 52;
LABEL_26:
      if ( v8 )
        LODWORD(v14) = (_DWORD)v8;
      McTemplateK0zq_EtwWriteTransfer(
        1,
        (unsigned int)FileWrapperHandleCreateEndFailure,
        v20,
        (_DWORD)v14,
        AllocationSize);
      goto LABEL_85;
    }
    goto LABEL_85;
  }
  if ( FileId >= 0 )
  {
    if ( (unsigned int)dword_140087708 > 5 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 2048) )
      TraceEvents(
        (int)"VhdmpiOpenFileForMatching",
        2939,
        5,
        v25,
        "Successfully opened file '%wZ' for matching/attribute purposes.",
        (char)a1);
    if ( (unsigned int)dword_1400876D0 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 0x10000) )
    {
      LODWORD(v44) = FileId;
      if ( v8 )
        v16 = v8;
      v46 = v16;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        v26,
        (unsigned int)&word_14007CE46,
        (unsigned int)&ActivityId,
        v55,
        (__int64)&v46,
        (__int64)&v44);
    }
    if ( (Microsoft_Windows_VHDMPEnableBits & 1) != 0 )
    {
      if ( v8 )
        LODWORD(v14) = (_DWORD)v8;
      McTemplateK0zq_EtwWriteTransfer(1, (unsigned int)FileWrapperHandleCreateEnd, v20, (_DWORD)v14, FileId);
    }
    FileId = VhdmpiQuerySmbCapabilities(FileHandle, &v40, &v41, &v42);
    if ( FileId < 0 )
    {
      if ( (unsigned int)dword_140087708 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 2048) )
        TraceEvents(
          (int)"VhdmpiOpenFileForMatching",
          2967,
          2,
          v27,
          "Failed to query SMB capabilities for '%wZ': 0x%08x",
          (char)a1);
      goto LABEL_85;
    }
    v28 = v41;
    v29 = v40;
    if ( v41 )
    {
      FileId = VhdmpiTranslateLoopbackFileHandle(FileHandle, &Object);
      if ( FileId < 0 )
        goto LABEL_85;
      ZwClose(FileHandle);
      FileHandle = Object;
    }
    else if ( v40 )
    {
      *(_BYTE *)(a4 + 49) = v42;
      *(_BYTE *)(a4 + 48) = 1;
    }
    Object = 0;
    ObReferenceObjectByHandle(FileHandle, 0, (POBJECT_TYPE)IoFileObjectType, 0, &Object, 0);
    v30 = Object;
    if ( (*(_DWORD *)(*((_QWORD *)Object + 1) + 52LL) & 0x10000) != 0 )
    {
      v31 = 1;
    }
    else
    {
      v31 = 0;
      if ( !v29 )
      {
        Status = ZwFsControlFile(FileHandle, 0, 0, 0, &IoStatusBlock, 0x9025Cu, 0, 0, 0, 0);
        if ( Status == 259 )
        {
          ZwWaitForSingleObject(FileHandle, 0, 0);
          Status = IoStatusBlock.Status;
        }
        v31 = Status >= 0;
      }
    }
    *(_BYTE *)a4 = v28;
    *(_BYTE *)(a4 + 1) = v31;
    if ( !v31 || v28 )
    {
      *(_QWORD *)(a4 + 8) = v30[3];
    }
    else
    {
      FileId = VhdmpiGetFileId(FileHandle, (__int64 *)(a4 + 8));
      if ( FileId < 0 )
      {
        if ( (unsigned int)dword_140087708 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 2048) )
        {
          v33 = 3035;
          v34 = "Failed to query file id for '%wZ': 0x%08x";
LABEL_80:
          TraceEvents((int)"VhdmpiOpenFileForMatching", v33, 2, v32, v34, (char)a1);
          goto LABEL_81;
        }
        goto LABEL_81;
      }
      FileId = VhdmpiGetVolumeStableGuid(v30, a4 + 16);
      if ( FileId < 0 )
      {
        if ( (unsigned int)dword_140087708 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 2048) )
        {
          v33 = 3048;
          v34 = "Failed to query volume stable guid for '%wZ': 0x%08x";
          goto LABEL_80;
        }
LABEL_81:
        if ( v30 )
          ObfDereferenceObject(v30);
        goto LABEL_85;
      }
    }
    FileId = 0;
    *(_QWORD *)(a4 + 32) = FileHandle;
    *(_QWORD *)(a4 + 40) = v30;
    FileHandle = 0;
    goto LABEL_85;
  }
  if ( (unsigned int)dword_140087708 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 2048) )
    TraceEvents(
      (int)"VhdmpiOpenFileForMatching",
      2923,
      2,
      v22,
      "Failed to open file '%wZ' for matching: 0x%08x",
      (char)a1);
  if ( (unsigned int)dword_1400876D0 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 0x10000) )
  {
    LODWORD(v44) = FileId;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      v23,
      (unsigned int)&word_14007CEC6,
      (unsigned int)&ActivityId,
      v55,
      (__int64)&v44);
  }
  if ( (unsigned int)dword_1400876D0 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 0x10000) )
  {
    LODWORD(v44) = FileId;
    if ( v8 )
      v16 = v8;
    v46 = v16;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
      v24,
      (unsigned int)&word_14007CEEE,
      (unsigned int)&ActivityId,
      v55,
      (__int64)&v46,
      (__int64)&v44);
  }
  if ( (Microsoft_Windows_VHDMPEnableBits & 1) != 0 )
  {
    AllocationSize = FileId;
    goto LABEL_26;
  }
LABEL_85:
  if ( FileHandle )
    ZwClose(FileHandle);
  if ( v8 )
    ExFreePoolWithTag(v8, 0x7A444856u);
  VhdmpiFileWrapperCleanupDriverCreateContext(&DriverContext);
  VhdmpiFreeFilePath(&v50, v36, v37);
  return (unsigned int)FileId;
}

```

## disassembly

```asm
0x1400ecb20  mov     [rsp-8+arg_8], rbx
0x1400ecb25  push    rbp
0x1400ecb26  push    rsi
0x1400ecb27  push    rdi
0x1400ecb28  push    r12
0x1400ecb2a  push    r13
0x1400ecb2c  push    r14
0x1400ecb2e  push    r15
0x1400ecb30  lea     rbp, [rsp-50h]
0x1400ecb35  sub     rsp, 150h
0x1400ecb3c  mov     rax, cs:__security_cookie
0x1400ecb43  xor     rax, rsp
0x1400ecb46  mov     [rbp+80h+var_40], rax
0x1400ecb4a  xorps   xmm0, xmm0
0x1400ecb4d  xor     r12d, r12d
0x1400ecb50  movups  xmmword ptr [r9], xmm0
0x1400ecb54  xor     eax, eax
0x1400ecb56  mov     [rbp+80h+var_FF], r12b
0x1400ecb5a  movups  xmmword ptr [r9+10h], xmm0
0x1400ecb5f  mov     r13, rcx
0x1400ecb62  mov     [rbp+80h+var_60], rax
0x1400ecb66  movups  xmmword ptr [r9+20h], xmm0
0x1400ecb6b  lea     rcx, [rbp+80h+var_80]; struct _IO_DRIVER_CREATE_CONTEXT *
0x1400ecb6f  mov     [r9+30h], rax
0x1400ecb73  mov     r14, r9
0x1400ecb76  mov     [rbp+80h+var_100], r12b
0x1400ecb7a  mov     r15b, r8b
0x1400ecb7d  mov     [rbp+80h+Object], r12
0x1400ecb81  mov     sil, dl
0x1400ecb84  mov     [rbp+80h+var_FE], r12b
0x1400ecb88  movups  xmmword ptr [rbp+80h+var_80.Size], xmm0
0x1400ecb8c  mov     [rbp+80h+var_48], rax
0x1400ecb90  mov     edi, r12d
0x1400ecb93  movups  xmmword ptr [rbp+80h+var_80.DeviceObjectHint], xmm0
0x1400ecb97  mov     [rbp+80h+FileHandle], r12
0x1400ecb9b  movups  xmmword ptr [rbp+80h+IoStatusBlock], xmm0
0x1400ecb9f  mov     [rbp+80h+var_F8], r12
0x1400ecba3  movups  xmmword ptr [rbp+80h+ObjectAttributes.Length], xmm0
0x1400ecba7  movups  xmmword ptr [rbp+80h+ObjectAttributes.ObjectName], xmm0
0x1400ecbab  movups  xmmword ptr [rbp+80h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400ecbaf  movups  xmmword ptr [rbp+80h+ActivityId.Data1], xmm0
0x1400ecbb3  movups  xmmword ptr [rbp+80h+var_C0.Length], xmm0
0x1400ecbb7  call    ?VhdmpiFileWrapperInitializeDriverCreateContext@@YAJPEAU_IO_DRIVER_CREATE_CONTEXT@@@Z; VhdmpiFileWrapperInitializeDriverCreateContext(_IO_DRIVER_CREATE_CONTEXT *)
0x1400ecbbc  mov     ebx, eax
0x1400ecbbe  test    eax, eax
0x1400ecbc0  js      loc_1400ED29C
0x1400ecbc6  lea     rdx, [rbp+80h+var_C0]; struct _UNICODE_STRING *
0x1400ecbca  mov     rcx, r13; struct _UNICODE_STRING *
0x1400ecbcd  call    VhdmpiCreateNtFilePath
0x1400ecbd2  mov     ebx, eax
0x1400ecbd4  test    eax, eax
0x1400ecbd6  js      loc_1400ED29C
0x1400ecbdc  mov     [rbp+80h+ObjectAttributes.RootDirectory], r12
0x1400ecbe0  lea     rax, [rbp+80h+var_C0]
0x1400ecbe4  xorps   xmm0, xmm0
0x1400ecbe7  mov     [rbp+80h+ObjectAttributes.Length], 30h ; '0'
0x1400ecbee  neg     sil
0x1400ecbf1  mov     [rbp+80h+ObjectAttributes.Attributes], 240h
0x1400ecbf8  lea     rdx, [rbp+80h+var_80]; struct _IO_DRIVER_CREATE_CONTEXT *
0x1400ecbfc  mov     [rbp+80h+ObjectAttributes.ObjectName], rax
0x1400ecc00  sbb     r12d, r12d
0x1400ecc03  mov     cl, r15b; unsigned __int8
0x1400ecc06  neg     r12d
0x1400ecc09  add     r12d, 100h
0x1400ecc10  movdqu  xmmword ptr [rbp+80h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400ecc15  call    ?VhdmpiCreateBackingStoreOpenEcp@@YAJEPEAU_IO_DRIVER_CREATE_CONTEXT@@@Z; VhdmpiCreateBackingStoreOpenEcp(uchar,_IO_DRIVER_CREATE_CONTEXT *)
0x1400ecc1a  mov     ebx, eax
0x1400ecc1c  test    eax, eax
0x1400ecc1e  js      loc_1400ED29C
0x1400ecc24  mov     eax, cs:dword_140087708
0x1400ecc2a  mov     edx, 800h
0x1400ecc2f  cmp     eax, 5
0x1400ecc32  jbe     short loc_1400ECC6F
0x1400ecc34  lea     rcx, dword_140087708
0x1400ecc3b  call    _tlgKeywordOn
0x1400ecc40  test    al, al
0x1400ecc42  jz      short loc_1400ECC6F
0x1400ecc44  mov     ecx, 0B2Bh
0x1400ecc49  mov     qword ptr [rsp+180h+FileAttributes], r13; char
0x1400ecc4e  mov     r9d, edx; int
0x1400ecc51  lea     rax, aOpeningFileWzF; "Opening file '%wZ' for matching/attribu"...
0x1400ecc58  mov     edx, ecx; int
0x1400ecc5a  mov     [rsp+180h+AllocationSize], rax; char *
0x1400ecc5f  lea     rcx, aVhdmpiopenfile; "VhdmpiOpenFileForMatching"
0x1400ecc66  lea     r8d, [rdi+5]; int
0x1400ecc6a  call    TraceEvents
0x1400ecc6f  lea     rdx, [rbp+80h+var_F8]
0x1400ecc73  mov     rcx, r13
0x1400ecc76  call    VhdmpiDuplicateUnicodeStringToString
0x1400ecc7b  mov     rdi, [rbp+80h+var_F8]
0x1400ecc7f  lea     rsi, dword_1400613A4
0x1400ecc86  xor     ecx, ecx
0x1400ecc88  test    eax, eax
0x1400ecc8a  cmovs   rdi, rcx
0x1400ecc8e  lea     ebx, [rcx+1]
0x1400ecc91  test    byte ptr cs:Microsoft_Windows_VHDMPEnableBits, bl
0x1400ecc97  jz      short loc_1400ECCB7
0x1400ecc99  test    rdi, rdi
0x1400ecc9c  mov     dword ptr [rsp+180h+AllocationSize], 100080h
0x1400ecca4  mov     r9, rsi
0x1400ecca7  lea     rdx, FileWrapperHandleCreateBegin
0x1400eccae  cmovnz  r9, rdi
0x1400eccb2  call    McTemplateK0zq_EtwWriteTransfer
0x1400eccb7  lea     rdx, [rbp+80h+ActivityId]; ActivityId
0x1400eccbb  mov     ecx, 3; ControlCode
0x1400eccc0  call    cs:__imp_EtwActivityIdControl
0x1400eccc7  nop     dword ptr [rax+rax+00h]
0x1400ecccc  mov     eax, cs:dword_1400876D0
0x1400eccd2  lea     r15, aUnknown; "Unknown"
0x1400eccd9  mov     [rbp+80h+var_48], 0
0x1400ecce1  cmp     eax, 4
0x1400ecce4  jbe     short loc_1400ECD4E
0x1400ecce6  mov     edx, 10000h
0x1400ecceb  lea     rcx, dword_1400876D0
0x1400eccf2  call    _tlgKeywordOn
0x1400eccf7  test    al, al
0x1400eccf9  jz      short loc_1400ECD4E
0x1400eccfb  test    rdi, rdi
0x1400eccfe  mov     [rbp+80h+var_D8], 7
0x1400ecd05  mov     rax, r15
0x1400ecd08  mov     dword ptr [rbp+80h+var_F8], 100080h
0x1400ecd0f  cmovnz  rax, rdi
0x1400ecd13  mov     [rbp+80h+var_FD], bl
0x1400ecd16  mov     [rbp+80h+var_E8], rax
0x1400ecd1a  lea     r8, [rbp+80h+ActivityId]
0x1400ecd1e  lea     rax, [rbp+80h+var_D8]
0x1400ecd22  mov     qword ptr [rsp+180h+Disposition], rax
0x1400ecd27  lea     rdx, word_14007CF2E
0x1400ecd2e  lea     rax, [rbp+80h+var_F8]
0x1400ecd32  mov     qword ptr [rsp+180h+ShareAccess], rax
0x1400ecd37  lea     rax, [rbp+80h+var_FD]
0x1400ecd3b  mov     qword ptr [rsp+180h+FileAttributes], rax
0x1400ecd40  lea     rax, [rbp+80h+var_E8]
0x1400ecd44  mov     [rsp+180h+AllocationSize], rax
0x1400ecd49  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$00@@U?$_tlgWrapperByVal@$03@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$00@@AEBU?$_tlgWrapperByVal@$03@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1400ecd4e  lea     rax, [rbp+80h+var_80]
0x1400ecd52  mov     edx, 100080h; DesiredAccess
0x1400ecd57  mov     [rsp+180h+DriverContext], rax; DriverContext
0x1400ecd5c  lea     r9, [rbp+80h+IoStatusBlock]; IoStatusBlock
0x1400ecd60  mov     [rsp+180h+Options], r12d; Options
0x1400ecd65  lea     r8, [rbp+80h+ObjectAttributes]; ObjectAttributes
0x1400ecd69  xor     r12d, r12d
0x1400ecd6c  lea     rcx, [rbp+80h+FileHandle]; FileHandle
0x1400ecd70  mov     [rsp+180h+InternalParameters], r12; InternalParameters
0x1400ecd75  mov     [rsp+180h+CreateFileType], r12d; CreateFileType
0x1400ecd7a  mov     [rsp+180h+EaLength], r12d; EaLength
0x1400ecd7f  mov     [rsp+180h+EaBuffer], r12; EaBuffer
0x1400ecd84  mov     [rsp+180h+CreateOptions], 400040h; CreateOptions
0x1400ecd8c  mov     [rsp+180h+Disposition], ebx; Disposition
0x1400ecd90  mov     [rsp+180h+ShareAccess], 7; ShareAccess
0x1400ecd98  mov     [rsp+180h+FileAttributes], 80h; FileAttributes
0x1400ecda0  mov     [rsp+180h+AllocationSize], r12; AllocationSize
0x1400ecda5  call    cs:__imp_IoCreateFileEx
0x1400ecdac  nop     dword ptr [rax+rax+00h]
0x1400ecdb1  mov     ebx, eax
0x1400ecdb3  cmp     eax, 0C0000034h
0x1400ecdb8  jnz     loc_1400ECE4A
0x1400ecdbe  mov     eax, cs:dword_1400876D0
0x1400ecdc4  mov     r14d, 0C0000034h
0x1400ecdca  cmp     eax, 4
0x1400ecdcd  jbe     short loc_1400ECE19
0x1400ecdcf  mov     edx, 10000h
0x1400ecdd4  lea     rcx, dword_1400876D0
0x1400ecddb  call    _tlgKeywordOn
0x1400ecde0  test    al, al
0x1400ecde2  jz      short loc_1400ECE19
0x1400ecde4  mov     r9, [rbp+80h+var_48]
0x1400ecde8  lea     rax, [rbp+80h+var_F8]
0x1400ecdec  mov     qword ptr [rsp+180h+FileAttributes], rax
0x1400ecdf1  lea     r8, [rbp+80h+ActivityId]
0x1400ecdf5  test    rdi, rdi
0x1400ecdf8  mov     dword ptr [rbp+80h+var_F8], r14d
0x1400ecdfc  lea     rax, [rbp+80h+var_E8]
0x1400ece00  cmovnz  r15, rdi
0x1400ece04  mov     [rsp+180h+AllocationSize], rax
0x1400ece09  lea     rdx, word_14007CE86
0x1400ece10  mov     [rbp+80h+var_E8], r15
0x1400ece14  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x1400ece19  mov     ecx, 1
0x1400ece1e  test    byte ptr cs:Microsoft_Windows_VHDMPEnableBits, cl
0x1400ece24  jz      loc_1400ED29C
0x1400ece2a  mov     dword ptr [rsp+180h+AllocationSize], r14d
0x1400ece2f  test    rdi, rdi
0x1400ece32  lea     rdx, FileWrapperHandleCreateEndFailure
0x1400ece39  cmovnz  rsi, rdi
0x1400ece3d  mov     r9, rsi
0x1400ece40  call    McTemplateK0zq_EtwWriteTransfer
0x1400ece45  jmp     loc_1400ED29C
0x1400ece4a  mov     eax, cs:dword_140087708
0x1400ece50  test    ebx, ebx
0x1400ece52  jns     loc_1400ECF50
0x1400ece58  cmp     eax, 2
0x1400ece5b  jbe     short loc_1400ECEA2
0x1400ece5d  mov     r9d, 800h
0x1400ece63  lea     rcx, dword_140087708
0x1400ece6a  mov     edx, r9d
0x1400ece6d  call    _tlgKeywordOn
0x1400ece72  test    al, al
0x1400ece74  jz      short loc_1400ECEA2
0x1400ece76  mov     [rsp+180h+ShareAccess], ebx
0x1400ece7a  lea     rax, aFailedToOpenFi; "Failed to open file '%wZ' for matching:"...
0x1400ece81  mov     qword ptr [rsp+180h+FileAttributes], r13; char
0x1400ece86  lea     rcx, aVhdmpiopenfile; "VhdmpiOpenFileForMatching"
0x1400ece8d  mov     edx, 0B6Bh; int
0x1400ece92  mov     [rsp+180h+AllocationSize], rax; char *
0x1400ece97  mov     r8d, 2; int
0x1400ece9d  call    TraceEvents
0x1400ecea2  mov     eax, cs:dword_1400876D0
0x1400ecea8  cmp     eax, 2
0x1400eceab  jbe     short loc_1400ECEE2
0x1400ecead  mov     edx, 10000h
0x1400eceb2  lea     rcx, dword_1400876D0
0x1400eceb9  call    _tlgKeywordOn
0x1400ecebe  test    al, al
0x1400ecec0  jz      short loc_1400ECEE2
0x1400ecec2  mov     r9, [rbp+80h+var_48]
0x1400ecec6  lea     rax, [rbp+80h+var_F8]
0x1400ececa  lea     r8, [rbp+80h+ActivityId]
0x1400ecece  mov     [rsp+180h+AllocationSize], rax
0x1400eced3  lea     rdx, word_14007CEC6
0x1400eceda  mov     dword ptr [rbp+80h+var_F8], ebx
0x1400ecedd  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1400ecee2  mov     eax, cs:dword_1400876D0
0x1400ecee8  cmp     eax, 4
0x1400eceeb  jbe     short loc_1400ECF36
0x1400eceed  mov     edx, 10000h
0x1400ecef2  lea     rcx, dword_1400876D0
0x1400ecef9  call    _tlgKeywordOn
0x1400ecefe  test    al, al
0x1400ecf00  jz      short loc_1400ECF36
0x1400ecf02  mov     r9, [rbp+80h+var_48]
0x1400ecf06  lea     rax, [rbp+80h+var_F8]
0x1400ecf0a  mov     qword ptr [rsp+180h+FileAttributes], rax
0x1400ecf0f  lea     r8, [rbp+80h+ActivityId]
0x1400ecf13  test    rdi, rdi
0x1400ecf16  mov     dword ptr [rbp+80h+var_F8], ebx
0x1400ecf19  lea     rax, [rbp+80h+var_E8]
0x1400ecf1d  cmovnz  r15, rdi
0x1400ecf21  mov     [rsp+180h+AllocationSize], rax
0x1400ecf26  lea     rdx, word_14007CEEE
0x1400ecf2d  mov     [rbp+80h+var_E8], r15
0x1400ecf31  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x1400ecf36  mov     ecx, 1
0x1400ecf3b  test    byte ptr cs:Microsoft_Windows_VHDMPEnableBits, cl
0x1400ecf41  jz      loc_1400ED29C
0x1400ecf47  mov     dword ptr [rsp+180h+AllocationSize], ebx
0x1400ecf4b  jmp     loc_1400ECE2F
0x1400ecf50  cmp     eax, 5
0x1400ecf53  jbe     short loc_1400ECF96
0x1400ecf55  mov     r9d, 800h
0x1400ecf5b  lea     rcx, dword_140087708
0x1400ecf62  mov     edx, r9d
0x1400ecf65  call    _tlgKeywordOn
0x1400ecf6a  test    al, al
0x1400ecf6c  jz      short loc_1400ECF96
0x1400ecf6e  lea     rax, aSuccessfullyOp_0; "Successfully opened file '%wZ' for matc"...
0x1400ecf75  mov     qword ptr [rsp+180h+FileAttributes], r13; char
0x1400ecf7a  mov     edx, 0B7Bh; int
0x1400ecf7f  mov     [rsp+180h+AllocationSize], rax; char *
0x1400ecf84  mov     r8d, 5; int
0x1400ecf8a  lea     rcx, aVhdmpiopenfile; "VhdmpiOpenFileForMatching"
0x1400ecf91  call    TraceEvents
0x1400ecf96  mov     eax, cs:dword_1400876D0
0x1400ecf9c  cmp     eax, 4
0x1400ecf9f  jbe     short loc_1400ECFEA
0x1400ecfa1  mov     edx, 10000h
0x1400ecfa6  lea     rcx, dword_1400876D0
0x1400ecfad  call    _tlgKeywordOn
0x1400ecfb2  test    al, al
0x1400ecfb4  jz      short loc_1400ECFEA
0x1400ecfb6  mov     r9, [rbp+80h+var_48]
0x1400ecfba  lea     rax, [rbp+80h+var_F8]
0x1400ecfbe  mov     qword ptr [rsp+180h+FileAttributes], rax
0x1400ecfc3  lea     r8, [rbp+80h+ActivityId]
0x1400ecfc7  test    rdi, rdi
0x1400ecfca  mov     dword ptr [rbp+80h+var_F8], ebx
0x1400ecfcd  lea     rax, [rbp+80h+var_E8]
0x1400ecfd1  cmovnz  r15, rdi
0x1400ecfd5  mov     [rsp+180h+AllocationSize], rax
0x1400ecfda  lea     rdx, word_14007CE46
0x1400ecfe1  mov     [rbp+80h+var_E8], r15
0x1400ecfe5  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x1400ecfea  mov     ecx, 1
0x1400ecfef  test    byte ptr cs:Microsoft_Windows_VHDMPEnableBits, cl
0x1400ecff5  jz      short loc_1400ED011
0x1400ecff7  test    rdi, rdi
0x1400ecffa  mov     dword ptr [rsp+180h+AllocationSize], ebx
0x1400ecffe  lea     rdx, FileWrapperHandleCreateEnd
0x1400ed005  cmovnz  rsi, rdi
0x1400ed009  mov     r9, rsi
0x1400ed00c  call    McTemplateK0zq_EtwWriteTransfer
0x1400ed011  mov     rcx, [rbp+80h+FileHandle]; FileHandle
0x1400ed015  lea     r9, [rbp+80h+var_FE]; unsigned __int8 *
0x1400ed019  lea     r8, [rbp+80h+var_FF]; unsigned __int8 *
0x1400ed01d  lea     rdx, [rbp+80h+var_100]; unsigned __int8 *
0x1400ed021  call    ?VhdmpiQuerySmbCapabilities@@YAJPEAXPEAE11@Z; VhdmpiQuerySmbCapabilities(void *,uchar *,uchar *,uchar *)
0x1400ed026  mov     ebx, eax
0x1400ed028  test    eax, eax
0x1400ed02a  jns     short loc_1400ED08A
0x1400ed02c  mov     eax, cs:dword_140087708
  ... truncated ...
```
