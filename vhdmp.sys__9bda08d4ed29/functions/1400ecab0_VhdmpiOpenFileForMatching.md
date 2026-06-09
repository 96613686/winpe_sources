# VhdmpiOpenFileForMatching

- ea: `0x1400ecab0`
- end: `0x1400ed296`
- name: `VhdmpiOpenFileForMatching`
- size: `2022`
- prototype: `__int64 __fastcall(struct _UNICODE_STRING *, char, unsigned __int8, __int64)`
- caller_count: `6`
- callee_count: `18`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x14003ff98`
- `0x140040430`
- `0x1400a2db4`
- `0x1400c7654`
- `0x1400cf014`
- `0x1400ec068`

## callees

- `0x1400010d0`
- `0x1400152fc`
- `0x14001c1d0`
- `0x14001dfd4`
- `0x140020c94`
- `0x140023980`
- `0x14002e37c`
- `0x140036284`
- `0x14005dbb0`
- `0x14009d9a4`
- `0x14009e1c0`
- `0x1400ad718`
- `0x1400d0f84`
- `0x1400e5ae4`
- `0x1400e8098`
- `0x1400e9190`
- `0x1400eab9c`
- `0x1400ecab0`

## import_xrefs

- `ntoskrnl!ZwFsControlFile` at `0x1400ed15b`
- `ntoskrnl!ZwFsControlFile` at `0x1400ed15b`
- `ntoskrnl!ZwWaitForSingleObject` at `0x1400ed177`
- `ntoskrnl!ZwWaitForSingleObject` at `0x1400ed177`
- `ntoskrnl!IoFileObjectType` at `0x1400ed069`
- `ntoskrnl!IoCreateFileEx` at `0x1400ecd35`
- `ntoskrnl!IoCreateFileEx` at `0x1400ecd35`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400ed096`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400ed096`
- `ntoskrnl!ObfDereferenceObject` at `0x1400ed203`
- `ntoskrnl!ObfDereferenceObject` at `0x1400ed203`
- `ntoskrnl!ZwClose` at `0x1400ed042`
- `ntoskrnl!ZwClose` at `0x1400ed235`
- `ntoskrnl!ZwClose` at `0x1400ed042`
- `ntoskrnl!ZwClose` at `0x1400ed235`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ed24e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ed24e`
- `ntoskrnl!EtwActivityIdControl` at `0x1400ecc50`
- `ntoskrnl!EtwActivityIdControl` at `0x1400ecc50`

## string_xrefs

- `0x1400ece0a`: `Failed to open file '%wZ' for matching: 0x%08x`
- `0x1400ecbef`: `VhdmpiOpenFileForMatching`
- `0x1400ece16`: `VhdmpiOpenFileForMatching`
- `0x1400ecf1a`: `VhdmpiOpenFileForMatching`
- `0x1400ecffe`: `VhdmpiOpenFileForMatching`
- `0x1400ed1e4`: `VhdmpiOpenFileForMatching`
- `0x1400ecbe1`: `Opening file '%wZ' for matching/attribute purposes.`
- `0x1400ecefe`: `Successfully opened file '%wZ' for matching/attribute purposes.`

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
  char AllocationSize; // [rsp+20h] [rbp-E0h]
  unsigned __int8 v38; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int8 v39; // [rsp+81h] [rbp-7Fh] BYREF
  unsigned __int8 v40; // [rsp+82h] [rbp-7Eh] BYREF
  char v41[5]; // [rsp+83h] [rbp-7Dh] BYREF
  wchar_t *v42; // [rsp+88h] [rbp-78h] BYREF
  void *FileHandle; // [rsp+90h] [rbp-70h] BYREF
  const wchar_t *v44; // [rsp+98h] [rbp-68h] BYREF
  PVOID Object; // [rsp+A0h] [rbp-60h] BYREF
  int v46; // [rsp+A8h] [rbp-58h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+B0h] [rbp-50h] BYREF
  struct _UNICODE_STRING v48; // [rsp+C0h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+D0h] [rbp-30h] BYREF
  struct _IO_DRIVER_CREATE_CONTEXT DriverContext; // [rsp+100h] [rbp+0h] BYREF
  __int64 v51; // [rsp+120h] [rbp+20h]
  GUID ActivityId; // [rsp+128h] [rbp+28h] BYREF
  __int64 v53; // [rsp+138h] [rbp+38h]

  *(_OWORD *)a4 = 0;
  v39 = 0;
  *(_OWORD *)(a4 + 16) = 0;
  v51 = 0;
  *(_OWORD *)(a4 + 32) = 0;
  *(_QWORD *)(a4 + 48) = 0;
  v38 = 0;
  Object = 0;
  v40 = 0;
  memset(&DriverContext, 0, sizeof(DriverContext));
  v53 = 0;
  v8 = 0;
  FileHandle = 0;
  IoStatusBlock = 0;
  v42 = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  ActivityId = 0;
  v48 = 0;
  FileId = VhdmpiFileWrapperInitializeDriverCreateContext(&DriverContext);
  if ( FileId < 0 )
    goto LABEL_85;
  FileId = VhdmpiCreateNtFilePath(a1, &v48);
  if ( FileId < 0 )
    goto LABEL_85;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Length = 48;
  ObjectAttributes.Attributes = 576;
  ObjectAttributes.ObjectName = &v48;
  Options = (a2 != 0) + 256;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  FileId = VhdmpiCreateBackingStoreOpenEcp(a3, &DriverContext);
  if ( FileId < 0 )
    goto LABEL_85;
  if ( (unsigned int)dword_1400876D0 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 2048) )
    TraceEvents(
      (int)"VhdmpiOpenFileForMatching",
      2859,
      5,
      v11,
      "Opening file '%wZ' for matching/attribute purposes.",
      (char)a1);
  v12 = VhdmpiDuplicateUnicodeStringToString(a1, &v42);
  v8 = v42;
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
  v53 = 0;
  if ( (unsigned int)dword_140087708 > 4 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 0x10000) )
  {
    v46 = 7;
    v19 = L"Unknown";
    LODWORD(v42) = 1048704;
    if ( v8 )
      v19 = v8;
    v41[0] = 1;
    v44 = v19;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v17,
      (unsigned int)&word_14007CEC6,
      (unsigned int)&ActivityId,
      v18,
      (__int64)&v44,
      (__int64)v41,
      (__int64)&v42,
      (__int64)&v46);
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
    if ( (unsigned int)dword_140087708 > 4 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 0x10000) )
    {
      LODWORD(v42) = -1073741772;
      if ( v8 )
        v16 = v8;
      v44 = v16;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        v21,
        (unsigned int)word_14007CF22,
        (unsigned int)&ActivityId,
        v53,
        (__int64)&v44,
        (__int64)&v42);
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
    if ( (unsigned int)dword_1400876D0 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 2048) )
      TraceEvents(
        (int)"VhdmpiOpenFileForMatching",
        2939,
        5,
        v25,
        "Successfully opened file '%wZ' for matching/attribute purposes.",
        (char)a1);
    if ( (unsigned int)dword_140087708 > 4 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 0x10000) )
    {
      LODWORD(v42) = FileId;
      if ( v8 )
        v16 = v8;
      v44 = v16;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        v26,
        (unsigned int)&word_14007CE86,
        (unsigned int)&ActivityId,
        v53,
        (__int64)&v44,
        (__int64)&v42);
    }
    if ( (Microsoft_Windows_VHDMPEnableBits & 1) != 0 )
    {
      if ( v8 )
        LODWORD(v14) = (_DWORD)v8;
      McTemplateK0zq_EtwWriteTransfer(1, (unsigned int)FileWrapperHandleCreateEnd, v20, (_DWORD)v14, FileId);
    }
    FileId = VhdmpiQuerySmbCapabilities(FileHandle, &v38, &v39, &v40);
    if ( FileId < 0 )
    {
      if ( (unsigned int)dword_1400876D0 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 2048) )
        TraceEvents(
          (int)"VhdmpiOpenFileForMatching",
          2967,
          2,
          v27,
          "Failed to query SMB capabilities for '%wZ': 0x%08x",
          (char)a1);
      goto LABEL_85;
    }
    v28 = v39;
    v29 = v38;
    if ( v39 )
    {
      FileId = VhdmpiTranslateLoopbackFileHandle(FileHandle, &Object);
      if ( FileId < 0 )
        goto LABEL_85;
      ZwClose(FileHandle);
      FileHandle = Object;
    }
    else if ( v38 )
    {
      *(_BYTE *)(a4 + 49) = v40;
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
        if ( (unsigned int)dword_1400876D0 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 2048) )
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
        if ( (unsigned int)dword_1400876D0 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 2048) )
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
  if ( (unsigned int)dword_1400876D0 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 2048) )
    TraceEvents(
      (int)"VhdmpiOpenFileForMatching",
      2923,
      2,
      v22,
      "Failed to open file '%wZ' for matching: 0x%08x",
      (char)a1);
  if ( (unsigned int)dword_140087708 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 0x10000) )
  {
    LODWORD(v42) = FileId;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      v23,
      (unsigned int)word_14007CF62,
      (unsigned int)&ActivityId,
      v53,
      (__int64)&v42);
  }
  if ( (unsigned int)dword_140087708 > 4 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 0x10000) )
  {
    LODWORD(v42) = FileId;
    if ( v8 )
      v16 = v8;
    v44 = v16;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
      v24,
      (unsigned int)&word_14007CE46,
      (unsigned int)&ActivityId,
      v53,
      (__int64)&v44,
      (__int64)&v42);
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
  VhdmpiFreeFilePath(&v48);
  return (unsigned int)FileId;
}

```

## disassembly

```asm
0x1400ecab0  mov     [rsp-8+arg_8], rbx
0x1400ecab5  push    rbp
0x1400ecab6  push    rsi
0x1400ecab7  push    rdi
0x1400ecab8  push    r12
0x1400ecaba  push    r13
0x1400ecabc  push    r14
0x1400ecabe  push    r15
0x1400ecac0  lea     rbp, [rsp-50h]
0x1400ecac5  sub     rsp, 150h
0x1400ecacc  mov     rax, cs:__security_cookie
0x1400ecad3  xor     rax, rsp
0x1400ecad6  mov     [rbp+80h+var_40], rax
0x1400ecada  xorps   xmm0, xmm0
0x1400ecadd  xor     r12d, r12d
0x1400ecae0  movups  xmmword ptr [r9], xmm0
0x1400ecae4  xor     eax, eax
0x1400ecae6  mov     [rbp+80h+var_FF], r12b
0x1400ecaea  movups  xmmword ptr [r9+10h], xmm0
0x1400ecaef  mov     r13, rcx
0x1400ecaf2  mov     [rbp+80h+var_60], rax
0x1400ecaf6  movups  xmmword ptr [r9+20h], xmm0
0x1400ecafb  lea     rcx, [rbp+80h+var_80]; struct _IO_DRIVER_CREATE_CONTEXT *
0x1400ecaff  mov     [r9+30h], rax
0x1400ecb03  mov     r14, r9
0x1400ecb06  mov     [rbp+80h+var_100], r12b
0x1400ecb0a  mov     r15b, r8b
0x1400ecb0d  mov     [rbp+80h+Object], r12
0x1400ecb11  mov     sil, dl
0x1400ecb14  mov     [rbp+80h+var_FE], r12b
0x1400ecb18  movups  xmmword ptr [rbp+80h+var_80.Size], xmm0
0x1400ecb1c  mov     [rbp+80h+var_48], rax
0x1400ecb20  mov     edi, r12d
0x1400ecb23  movups  xmmword ptr [rbp+80h+var_80.DeviceObjectHint], xmm0
0x1400ecb27  mov     [rbp+80h+FileHandle], r12
0x1400ecb2b  movups  xmmword ptr [rbp+80h+IoStatusBlock], xmm0
0x1400ecb2f  mov     [rbp+80h+var_F8], r12
0x1400ecb33  movups  xmmword ptr [rbp+80h+ObjectAttributes.Length], xmm0
0x1400ecb37  movups  xmmword ptr [rbp+80h+ObjectAttributes.ObjectName], xmm0
0x1400ecb3b  movups  xmmword ptr [rbp+80h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400ecb3f  movups  xmmword ptr [rbp+80h+ActivityId.Data1], xmm0
0x1400ecb43  movups  xmmword ptr [rbp+80h+var_C0.Length], xmm0
0x1400ecb47  call    ?VhdmpiFileWrapperInitializeDriverCreateContext@@YAJPEAU_IO_DRIVER_CREATE_CONTEXT@@@Z; VhdmpiFileWrapperInitializeDriverCreateContext(_IO_DRIVER_CREATE_CONTEXT *)
0x1400ecb4c  mov     ebx, eax
0x1400ecb4e  test    eax, eax
0x1400ecb50  js      loc_1400ED22C
0x1400ecb56  lea     rdx, [rbp+80h+var_C0]; struct _UNICODE_STRING *
0x1400ecb5a  mov     rcx, r13; struct _UNICODE_STRING *
0x1400ecb5d  call    VhdmpiCreateNtFilePath
0x1400ecb62  mov     ebx, eax
0x1400ecb64  test    eax, eax
0x1400ecb66  js      loc_1400ED22C
0x1400ecb6c  mov     [rbp+80h+ObjectAttributes.RootDirectory], r12
0x1400ecb70  lea     rax, [rbp+80h+var_C0]
0x1400ecb74  xorps   xmm0, xmm0
0x1400ecb77  mov     [rbp+80h+ObjectAttributes.Length], 30h ; '0'
0x1400ecb7e  neg     sil
0x1400ecb81  mov     [rbp+80h+ObjectAttributes.Attributes], 240h
0x1400ecb88  lea     rdx, [rbp+80h+var_80]; struct _IO_DRIVER_CREATE_CONTEXT *
0x1400ecb8c  mov     [rbp+80h+ObjectAttributes.ObjectName], rax
0x1400ecb90  sbb     r12d, r12d
0x1400ecb93  mov     cl, r15b; unsigned __int8
0x1400ecb96  neg     r12d
0x1400ecb99  add     r12d, 100h
0x1400ecba0  movdqu  xmmword ptr [rbp+80h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400ecba5  call    ?VhdmpiCreateBackingStoreOpenEcp@@YAJEPEAU_IO_DRIVER_CREATE_CONTEXT@@@Z; VhdmpiCreateBackingStoreOpenEcp(uchar,_IO_DRIVER_CREATE_CONTEXT *)
0x1400ecbaa  mov     ebx, eax
0x1400ecbac  test    eax, eax
0x1400ecbae  js      loc_1400ED22C
0x1400ecbb4  mov     eax, cs:dword_1400876D0
0x1400ecbba  mov     edx, 800h
0x1400ecbbf  cmp     eax, 5
0x1400ecbc2  jbe     short loc_1400ECBFF
0x1400ecbc4  lea     rcx, dword_1400876D0
0x1400ecbcb  call    _tlgKeywordOn
0x1400ecbd0  test    al, al
0x1400ecbd2  jz      short loc_1400ECBFF
0x1400ecbd4  mov     ecx, 0B2Bh
0x1400ecbd9  mov     qword ptr [rsp+180h+FileAttributes], r13; char
0x1400ecbde  mov     r9d, edx; int
0x1400ecbe1  lea     rax, aOpeningFileWzF; "Opening file '%wZ' for matching/attribu"...
0x1400ecbe8  mov     edx, ecx; int
0x1400ecbea  mov     [rsp+180h+AllocationSize], rax; char *
0x1400ecbef  lea     rcx, aVhdmpiopenfile; "VhdmpiOpenFileForMatching"
0x1400ecbf6  lea     r8d, [rdi+5]; int
0x1400ecbfa  call    TraceEvents
0x1400ecbff  lea     rdx, [rbp+80h+var_F8]
0x1400ecc03  mov     rcx, r13
0x1400ecc06  call    VhdmpiDuplicateUnicodeStringToString
0x1400ecc0b  mov     rdi, [rbp+80h+var_F8]
0x1400ecc0f  lea     rsi, dword_1400613A4
0x1400ecc16  xor     ecx, ecx
0x1400ecc18  test    eax, eax
0x1400ecc1a  cmovs   rdi, rcx
0x1400ecc1e  lea     ebx, [rcx+1]
0x1400ecc21  test    byte ptr cs:Microsoft_Windows_VHDMPEnableBits, bl
0x1400ecc27  jz      short loc_1400ECC47
0x1400ecc29  test    rdi, rdi
0x1400ecc2c  mov     dword ptr [rsp+180h+AllocationSize], 100080h
0x1400ecc34  mov     r9, rsi
0x1400ecc37  lea     rdx, FileWrapperHandleCreateBegin
0x1400ecc3e  cmovnz  r9, rdi
0x1400ecc42  call    McTemplateK0zq_EtwWriteTransfer
0x1400ecc47  lea     rdx, [rbp+80h+ActivityId]; ActivityId
0x1400ecc4b  mov     ecx, 3; ControlCode
0x1400ecc50  call    cs:__imp_EtwActivityIdControl
0x1400ecc57  nop     dword ptr [rax+rax+00h]
0x1400ecc5c  mov     eax, cs:dword_140087708
0x1400ecc62  lea     r15, aUnknown; "Unknown"
0x1400ecc69  mov     [rbp+80h+var_48], 0
0x1400ecc71  cmp     eax, 4
0x1400ecc74  jbe     short loc_1400ECCDE
0x1400ecc76  mov     edx, 10000h
0x1400ecc7b  lea     rcx, dword_140087708
0x1400ecc82  call    _tlgKeywordOn
0x1400ecc87  test    al, al
0x1400ecc89  jz      short loc_1400ECCDE
0x1400ecc8b  test    rdi, rdi
0x1400ecc8e  mov     [rbp+80h+var_D8], 7
0x1400ecc95  mov     rax, r15
0x1400ecc98  mov     dword ptr [rbp+80h+var_F8], 100080h
0x1400ecc9f  cmovnz  rax, rdi
0x1400ecca3  mov     [rbp+80h+var_FD], bl
0x1400ecca6  mov     [rbp+80h+var_E8], rax
0x1400eccaa  lea     r8, [rbp+80h+ActivityId]
0x1400eccae  lea     rax, [rbp+80h+var_D8]
0x1400eccb2  mov     qword ptr [rsp+180h+Disposition], rax
0x1400eccb7  lea     rdx, word_14007CEC6
0x1400eccbe  lea     rax, [rbp+80h+var_F8]
0x1400eccc2  mov     qword ptr [rsp+180h+ShareAccess], rax
0x1400eccc7  lea     rax, [rbp+80h+var_FD]
0x1400ecccb  mov     qword ptr [rsp+180h+FileAttributes], rax
0x1400eccd0  lea     rax, [rbp+80h+var_E8]
0x1400eccd4  mov     [rsp+180h+AllocationSize], rax
0x1400eccd9  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$00@@U?$_tlgWrapperByVal@$03@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$00@@AEBU?$_tlgWrapperByVal@$03@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1400eccde  lea     rax, [rbp+80h+var_80]
0x1400ecce2  mov     edx, 100080h; DesiredAccess
0x1400ecce7  mov     [rsp+180h+DriverContext], rax; DriverContext
0x1400eccec  lea     r9, [rbp+80h+IoStatusBlock]; IoStatusBlock
0x1400eccf0  mov     [rsp+180h+Options], r12d; Options
0x1400eccf5  lea     r8, [rbp+80h+ObjectAttributes]; ObjectAttributes
0x1400eccf9  xor     r12d, r12d
0x1400eccfc  lea     rcx, [rbp+80h+FileHandle]; FileHandle
0x1400ecd00  mov     [rsp+180h+InternalParameters], r12; InternalParameters
0x1400ecd05  mov     [rsp+180h+CreateFileType], r12d; CreateFileType
0x1400ecd0a  mov     [rsp+180h+EaLength], r12d; EaLength
0x1400ecd0f  mov     [rsp+180h+EaBuffer], r12; EaBuffer
0x1400ecd14  mov     [rsp+180h+CreateOptions], 400040h; CreateOptions
0x1400ecd1c  mov     [rsp+180h+Disposition], ebx; Disposition
0x1400ecd20  mov     [rsp+180h+ShareAccess], 7; ShareAccess
0x1400ecd28  mov     [rsp+180h+FileAttributes], 80h; FileAttributes
0x1400ecd30  mov     [rsp+180h+AllocationSize], r12; AllocationSize
0x1400ecd35  call    cs:__imp_IoCreateFileEx
0x1400ecd3c  nop     dword ptr [rax+rax+00h]
0x1400ecd41  mov     ebx, eax
0x1400ecd43  cmp     eax, 0C0000034h
0x1400ecd48  jnz     loc_1400ECDDA
0x1400ecd4e  mov     eax, cs:dword_140087708
0x1400ecd54  mov     r14d, 0C0000034h
0x1400ecd5a  cmp     eax, 4
0x1400ecd5d  jbe     short loc_1400ECDA9
0x1400ecd5f  mov     edx, 10000h
0x1400ecd64  lea     rcx, dword_140087708
0x1400ecd6b  call    _tlgKeywordOn
0x1400ecd70  test    al, al
0x1400ecd72  jz      short loc_1400ECDA9
0x1400ecd74  mov     r9, [rbp+80h+var_48]
0x1400ecd78  lea     rax, [rbp+80h+var_F8]
0x1400ecd7c  mov     qword ptr [rsp+180h+FileAttributes], rax
0x1400ecd81  lea     r8, [rbp+80h+ActivityId]
0x1400ecd85  test    rdi, rdi
0x1400ecd88  mov     dword ptr [rbp+80h+var_F8], r14d
0x1400ecd8c  lea     rax, [rbp+80h+var_E8]
0x1400ecd90  cmovnz  r15, rdi
0x1400ecd94  mov     [rsp+180h+AllocationSize], rax
0x1400ecd99  lea     rdx, word_14007CF22
0x1400ecda0  mov     [rbp+80h+var_E8], r15
0x1400ecda4  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x1400ecda9  mov     ecx, 1
0x1400ecdae  test    byte ptr cs:Microsoft_Windows_VHDMPEnableBits, cl
0x1400ecdb4  jz      loc_1400ED22C
0x1400ecdba  mov     dword ptr [rsp+180h+AllocationSize], r14d
0x1400ecdbf  test    rdi, rdi
0x1400ecdc2  lea     rdx, FileWrapperHandleCreateEndFailure
0x1400ecdc9  cmovnz  rsi, rdi
0x1400ecdcd  mov     r9, rsi
0x1400ecdd0  call    McTemplateK0zq_EtwWriteTransfer
0x1400ecdd5  jmp     loc_1400ED22C
0x1400ecdda  mov     eax, cs:dword_1400876D0
0x1400ecde0  test    ebx, ebx
0x1400ecde2  jns     loc_1400ECEE0
0x1400ecde8  cmp     eax, 2
0x1400ecdeb  jbe     short loc_1400ECE32
0x1400ecded  mov     r9d, 800h
0x1400ecdf3  lea     rcx, dword_1400876D0
0x1400ecdfa  mov     edx, r9d
0x1400ecdfd  call    _tlgKeywordOn
0x1400ece02  test    al, al
0x1400ece04  jz      short loc_1400ECE32
0x1400ece06  mov     [rsp+180h+ShareAccess], ebx
0x1400ece0a  lea     rax, aFailedToOpenFi; "Failed to open file '%wZ' for matching:"...
0x1400ece11  mov     qword ptr [rsp+180h+FileAttributes], r13; char
0x1400ece16  lea     rcx, aVhdmpiopenfile; "VhdmpiOpenFileForMatching"
0x1400ece1d  mov     edx, 0B6Bh; int
0x1400ece22  mov     [rsp+180h+AllocationSize], rax; char *
0x1400ece27  mov     r8d, 2; int
0x1400ece2d  call    TraceEvents
0x1400ece32  mov     eax, cs:dword_140087708
0x1400ece38  cmp     eax, 2
0x1400ece3b  jbe     short loc_1400ECE72
0x1400ece3d  mov     edx, 10000h
0x1400ece42  lea     rcx, dword_140087708
0x1400ece49  call    _tlgKeywordOn
0x1400ece4e  test    al, al
0x1400ece50  jz      short loc_1400ECE72
0x1400ece52  mov     r9, [rbp+80h+var_48]
0x1400ece56  lea     rax, [rbp+80h+var_F8]
0x1400ece5a  lea     r8, [rbp+80h+ActivityId]
0x1400ece5e  mov     [rsp+180h+AllocationSize], rax
0x1400ece63  lea     rdx, word_14007CF62
0x1400ece6a  mov     dword ptr [rbp+80h+var_F8], ebx
0x1400ece6d  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1400ece72  mov     eax, cs:dword_140087708
0x1400ece78  cmp     eax, 4
0x1400ece7b  jbe     short loc_1400ECEC6
0x1400ece7d  mov     edx, 10000h
0x1400ece82  lea     rcx, dword_140087708
0x1400ece89  call    _tlgKeywordOn
0x1400ece8e  test    al, al
0x1400ece90  jz      short loc_1400ECEC6
0x1400ece92  mov     r9, [rbp+80h+var_48]
0x1400ece96  lea     rax, [rbp+80h+var_F8]
0x1400ece9a  mov     qword ptr [rsp+180h+FileAttributes], rax
0x1400ece9f  lea     r8, [rbp+80h+ActivityId]
0x1400ecea3  test    rdi, rdi
0x1400ecea6  mov     dword ptr [rbp+80h+var_F8], ebx
0x1400ecea9  lea     rax, [rbp+80h+var_E8]
0x1400ecead  cmovnz  r15, rdi
0x1400eceb1  mov     [rsp+180h+AllocationSize], rax
0x1400eceb6  lea     rdx, word_14007CE46
0x1400ecebd  mov     [rbp+80h+var_E8], r15
0x1400ecec1  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x1400ecec6  mov     ecx, 1
0x1400ececb  test    byte ptr cs:Microsoft_Windows_VHDMPEnableBits, cl
0x1400eced1  jz      loc_1400ED22C
0x1400eced7  mov     dword ptr [rsp+180h+AllocationSize], ebx
0x1400ecedb  jmp     loc_1400ECDBF
0x1400ecee0  cmp     eax, 5
0x1400ecee3  jbe     short loc_1400ECF26
0x1400ecee5  mov     r9d, 800h
0x1400eceeb  lea     rcx, dword_1400876D0
0x1400ecef2  mov     edx, r9d
0x1400ecef5  call    _tlgKeywordOn
0x1400ecefa  test    al, al
0x1400ecefc  jz      short loc_1400ECF26
0x1400ecefe  lea     rax, aSuccessfullyOp_0; "Successfully opened file '%wZ' for matc"...
0x1400ecf05  mov     qword ptr [rsp+180h+FileAttributes], r13; char
0x1400ecf0a  mov     edx, 0B7Bh; int
0x1400ecf0f  mov     [rsp+180h+AllocationSize], rax; char *
0x1400ecf14  mov     r8d, 5; int
0x1400ecf1a  lea     rcx, aVhdmpiopenfile; "VhdmpiOpenFileForMatching"
0x1400ecf21  call    TraceEvents
0x1400ecf26  mov     eax, cs:dword_140087708
0x1400ecf2c  cmp     eax, 4
0x1400ecf2f  jbe     short loc_1400ECF7A
0x1400ecf31  mov     edx, 10000h
0x1400ecf36  lea     rcx, dword_140087708
0x1400ecf3d  call    _tlgKeywordOn
0x1400ecf42  test    al, al
0x1400ecf44  jz      short loc_1400ECF7A
0x1400ecf46  mov     r9, [rbp+80h+var_48]
0x1400ecf4a  lea     rax, [rbp+80h+var_F8]
0x1400ecf4e  mov     qword ptr [rsp+180h+FileAttributes], rax
0x1400ecf53  lea     r8, [rbp+80h+ActivityId]
0x1400ecf57  test    rdi, rdi
0x1400ecf5a  mov     dword ptr [rbp+80h+var_F8], ebx
0x1400ecf5d  lea     rax, [rbp+80h+var_E8]
0x1400ecf61  cmovnz  r15, rdi
0x1400ecf65  mov     [rsp+180h+AllocationSize], rax
0x1400ecf6a  lea     rdx, word_14007CE86
0x1400ecf71  mov     [rbp+80h+var_E8], r15
0x1400ecf75  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x1400ecf7a  mov     ecx, 1
0x1400ecf7f  test    byte ptr cs:Microsoft_Windows_VHDMPEnableBits, cl
0x1400ecf85  jz      short loc_1400ECFA1
0x1400ecf87  test    rdi, rdi
0x1400ecf8a  mov     dword ptr [rsp+180h+AllocationSize], ebx
0x1400ecf8e  lea     rdx, FileWrapperHandleCreateEnd
0x1400ecf95  cmovnz  rsi, rdi
0x1400ecf99  mov     r9, rsi
0x1400ecf9c  call    McTemplateK0zq_EtwWriteTransfer
0x1400ecfa1  mov     rcx, [rbp+80h+FileHandle]; FileHandle
0x1400ecfa5  lea     r9, [rbp+80h+var_FE]; unsigned __int8 *
0x1400ecfa9  lea     r8, [rbp+80h+var_FF]; unsigned __int8 *
0x1400ecfad  lea     rdx, [rbp+80h+var_100]; unsigned __int8 *
0x1400ecfb1  call    ?VhdmpiQuerySmbCapabilities@@YAJPEAXPEAE11@Z; VhdmpiQuerySmbCapabilities(void *,uchar *,uchar *,uchar *)
0x1400ecfb6  mov     ebx, eax
0x1400ecfb8  test    eax, eax
0x1400ecfba  jns     short loc_1400ED01A
0x1400ecfbc  mov     eax, cs:dword_1400876D0
  ... truncated ...
```
