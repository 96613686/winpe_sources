# VhdmpiDeleteFile

- ea: `0x1400ebcd0`
- end: `0x1400ec060`
- name: `VhdmpiDeleteFile`
- size: `912`
- prototype: `__int64 __fastcall(char)`
- caller_count: `10`
- callee_count: `9`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140040608`
- `0x14004def0`
- `0x14009e48c`
- `0x1400a38a0`
- `0x1400a41d0`
- `0x1400a5844`
- `0x1400c5550`
- `0x1400c62b0`
- `0x1400c78d0`
- `0x1400ebb10`

## callees

- `0x1400010d0`
- `0x1400152fc`
- `0x14001c1d0`
- `0x14001dfd4`
- `0x140023980`
- `0x140036284`
- `0x14005dbb0`
- `0x14009d9a4`
- `0x1400ebcd0`

## import_xrefs

- `ntoskrnl!IoCreateFileEx` at `0x1400ebe64`
- `ntoskrnl!IoCreateFileEx` at `0x1400ebe64`
- `ntoskrnl!ZwClose` at `0x1400ebf9c`
- `ntoskrnl!ZwClose` at `0x1400ebf9c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ec029`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ec029`
- `ntoskrnl!EtwActivityIdControl` at `0x1400ebd8c`
- `ntoskrnl!EtwActivityIdControl` at `0x1400ebd8c`

## string_xrefs

- `0x1400ebfe4`: `VhdmpiDeleteFile`
- `0x1400ebfdd`: `VhdmpiDeleteFile: Unable to delete file '%wZ', status = 0x%08x`

## pseudocode

```c
__int64 __fastcall VhdmpiDeleteFile(struct _UNICODE_STRING *a1)
{
  int v2; // eax
  int v3; // ecx
  int v4; // r8d
  wchar_t *v5; // rbx
  const wchar_t *v6; // rsi
  int v7; // ecx
  int v8; // r9d
  const wchar_t *v9; // rax
  int v10; // ecx
  NTSTATUS v11; // edi
  int v12; // r8d
  int v13; // ecx
  unsigned int v14; // edx
  ULONG ShareAccess[2]; // [rsp+30h] [rbp-D0h]
  char v17[8]; // [rsp+80h] [rbp-80h] BYREF
  wchar_t *v18; // [rsp+88h] [rbp-78h] BYREF
  const wchar_t *v19; // [rsp+90h] [rbp-70h] BYREF
  int v20; // [rsp+98h] [rbp-68h] BYREF
  void *FileHandle; // [rsp+A0h] [rbp-60h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+A8h] [rbp-58h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+D8h] [rbp-28h] BYREF
  GUID ActivityId; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v25; // [rsp+F8h] [rbp-8h]

  FileHandle = 0;
  IoStatusBlock = 0;
  v18 = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  v25 = 0;
  ActivityId = 0;
  v2 = VhdmpiDuplicateUnicodeStringToString(a1, &v18);
  v5 = v18;
  ObjectAttributes.Length = 48;
  if ( v2 < 0 )
    v5 = 0;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  ObjectAttributes.ObjectName = a1;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  if ( v5 && (Microsoft_Windows_VHDMPEnableBits & 1) != 0 )
    McTemplateK0zq_EtwWriteTransfer(v3, (unsigned int)FileWrapperHandleCreateBegin, v4, (_DWORD)v5, 0);
  EtwActivityIdControl(3u, &ActivityId);
  v6 = L"Unknown";
  v25 = 0;
  if ( (unsigned int)dword_140087708 > 4 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 0x10000) )
  {
    v20 = 7;
    v9 = L"Unknown";
    LODWORD(v18) = 0x10000;
    if ( v5 )
      v9 = v5;
    v17[0] = 0;
    v19 = v9;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v7,
      (unsigned int)byte_14007CC89,
      (unsigned int)&ActivityId,
      v8,
      (__int64)&v19,
      (__int64)v17,
      (__int64)&v18,
      (__int64)&v20);
  }
  v11 = IoCreateFileEx(
          &FileHandle,
          0x10000u,
          &ObjectAttributes,
          &IoStatusBlock,
          0,
          0x80u,
          7u,
          1u,
          0x1000u,
          0,
          0,
          CreateFileTypeNone,
          0,
          0x101u,
          0);
  if ( v11 == -1073741772 )
  {
    if ( (unsigned int)dword_140087708 > 4 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 0x10000) )
    {
      LODWORD(v18) = -1073741772;
      if ( v5 )
        v6 = v5;
      v19 = v6;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        v13,
        (unsigned int)byte_14007CBE1,
        (unsigned int)&ActivityId,
        v25,
        (__int64)&v19,
        (__int64)&v18);
    }
LABEL_37:
    if ( v5 )
      ExFreePoolWithTag(v5, 0x7A444856u);
    return (unsigned int)v11;
  }
  if ( v11 < 0 && (unsigned int)dword_140087708 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 0x10000) )
  {
    LODWORD(v18) = v11;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      v10,
      (unsigned int)byte_14007CC21,
      (unsigned int)&ActivityId,
      v25,
      (__int64)&v18);
  }
  if ( (unsigned int)dword_140087708 > 4 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 0x10000) )
  {
    LODWORD(v18) = v11;
    if ( v5 )
      v6 = v5;
    v19 = v6;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
      v10,
      (unsigned int)byte_14007CC49,
      (unsigned int)&ActivityId,
      v25,
      (__int64)&v19,
      (__int64)&v18);
  }
  if ( v11 >= 0 )
  {
    if ( v5 && (Microsoft_Windows_VHDMPEnableBits & 1) != 0 )
      McTemplateK0zq_EtwWriteTransfer(v10, (unsigned int)FileWrapperHandleCreateEnd, v12, (_DWORD)v5, 0);
    ZwClose(FileHandle);
    goto LABEL_37;
  }
  if ( (unsigned int)dword_1400876D0 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 2048) )
  {
    ShareAccess[0] = v11;
    TraceEvents(
      "VhdmpiDeleteFile",
      0x23B3u,
      2u,
      v14,
      "VhdmpiDeleteFile: Unable to delete file '%wZ', status = 0x%08x",
      a1,
      *(_QWORD *)ShareAccess);
  }
  if ( v5 )
  {
    if ( (Microsoft_Windows_VHDMPEnableBits & 1) != 0 )
      McTemplateK0zq_EtwWriteTransfer(v10, (unsigned int)FileWrapperHandleCreateEndFailure, v12, (_DWORD)v5, v11);
    goto LABEL_37;
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1400ebcd0  mov     [rsp-8+arg_8], rbx
0x1400ebcd5  mov     [rsp-8+arg_10], rsi
0x1400ebcda  push    rbp
0x1400ebcdb  push    rdi
0x1400ebcdc  push    r12
0x1400ebcde  push    r14
0x1400ebce0  push    r15
0x1400ebce2  lea     rbp, [rsp-10h]
0x1400ebce7  sub     rsp, 110h
0x1400ebcee  mov     rax, cs:__security_cookie
0x1400ebcf5  xor     rax, rsp
0x1400ebcf8  mov     [rbp+30h+var_30], rax
0x1400ebcfc  xorps   xmm1, xmm1
0x1400ebcff  lea     rdx, [rbp+30h+var_A8]
0x1400ebd03  xorps   xmm0, xmm0
0x1400ebd06  xor     r15d, r15d
0x1400ebd09  xor     eax, eax
0x1400ebd0b  mov     [rbp+30h+FileHandle], r15
0x1400ebd0f  movups  xmmword ptr [rbp+30h+IoStatusBlock], xmm0
0x1400ebd13  mov     [rbp+30h+var_A8], r15
0x1400ebd17  mov     r14, rcx
0x1400ebd1a  movups  xmmword ptr [rbp+30h+ObjectAttributes.Length], xmm1
0x1400ebd1e  mov     [rbp+30h+var_38], rax
0x1400ebd22  movups  xmmword ptr [rbp+30h+ObjectAttributes.ObjectName], xmm1
0x1400ebd26  movups  xmmword ptr [rbp+30h+ObjectAttributes.SecurityDescriptor], xmm1
0x1400ebd2a  movups  xmmword ptr [rbp+30h+ActivityId.Data1], xmm0
0x1400ebd2e  call    VhdmpiDuplicateUnicodeStringToString
0x1400ebd33  mov     rbx, [rbp+30h+var_A8]
0x1400ebd37  test    eax, eax
0x1400ebd39  xorps   xmm0, xmm0
0x1400ebd3c  mov     [rbp+30h+ObjectAttributes.Length], 30h ; '0'
0x1400ebd43  cmovs   rbx, r15
0x1400ebd47  mov     [rbp+30h+ObjectAttributes.RootDirectory], r15
0x1400ebd4b  mov     [rbp+30h+ObjectAttributes.Attributes], 240h
0x1400ebd52  mov     r12d, 10000h
0x1400ebd58  mov     [rbp+30h+ObjectAttributes.ObjectName], r14
0x1400ebd5c  movdqu  xmmword ptr [rbp+30h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400ebd61  test    rbx, rbx
0x1400ebd64  jz      short loc_1400EBD83
0x1400ebd66  test    byte ptr cs:Microsoft_Windows_VHDMPEnableBits, 1
0x1400ebd6d  jz      short loc_1400EBD83
0x1400ebd6f  mov     r9, rbx
0x1400ebd72  mov     dword ptr [rsp+130h+AllocationSize], r12d
0x1400ebd77  lea     rdx, FileWrapperHandleCreateBegin
0x1400ebd7e  call    McTemplateK0zq_EtwWriteTransfer
0x1400ebd83  lea     rdx, [rbp+30h+ActivityId]; ActivityId
0x1400ebd87  mov     ecx, 3; ControlCode
0x1400ebd8c  call    cs:__imp_EtwActivityIdControl
0x1400ebd93  nop     dword ptr [rax+rax+00h]
0x1400ebd98  mov     eax, cs:dword_140087708
0x1400ebd9e  lea     rsi, aUnknown; "Unknown"
0x1400ebda5  mov     [rbp+30h+var_38], r15
0x1400ebda9  mov     edi, 7
0x1400ebdae  cmp     eax, 4
0x1400ebdb1  jbe     short loc_1400EBE13
0x1400ebdb3  mov     rdx, r12
0x1400ebdb6  lea     rcx, dword_140087708
0x1400ebdbd  call    _tlgKeywordOn
0x1400ebdc2  test    al, al
0x1400ebdc4  jz      short loc_1400EBE13
0x1400ebdc6  test    rbx, rbx
0x1400ebdc9  mov     [rbp+30h+var_98], edi
0x1400ebdcc  mov     rax, rsi
0x1400ebdcf  mov     dword ptr [rbp+30h+var_A8], r12d
0x1400ebdd3  cmovnz  rax, rbx
0x1400ebdd7  mov     [rbp+30h+var_B0], r15b
0x1400ebddb  mov     [rbp+30h+var_A0], rax
0x1400ebddf  lea     r8, [rbp+30h+ActivityId]
0x1400ebde3  lea     rax, [rbp+30h+var_98]
0x1400ebde7  mov     qword ptr [rsp+130h+Disposition], rax
0x1400ebdec  lea     rdx, byte_14007CC89
0x1400ebdf3  lea     rax, [rbp+30h+var_A8]
0x1400ebdf7  mov     qword ptr [rsp+130h+ShareAccess], rax
0x1400ebdfc  lea     rax, [rbp+30h+var_B0]
0x1400ebe00  mov     qword ptr [rsp+130h+FileAttributes], rax
0x1400ebe05  lea     rax, [rbp+30h+var_A0]
0x1400ebe09  mov     [rsp+130h+AllocationSize], rax
0x1400ebe0e  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$00@@U?$_tlgWrapperByVal@$03@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$00@@AEBU?$_tlgWrapperByVal@$03@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1400ebe13  mov     [rsp+130h+DriverContext], r15; DriverContext
0x1400ebe18  lea     r9, [rbp+30h+IoStatusBlock]; IoStatusBlock
0x1400ebe1c  mov     [rsp+130h+Options], 101h; Options
0x1400ebe24  lea     r8, [rbp+30h+ObjectAttributes]; ObjectAttributes
0x1400ebe28  mov     [rsp+130h+InternalParameters], r15; InternalParameters
0x1400ebe2d  lea     rcx, [rbp+30h+FileHandle]; FileHandle
0x1400ebe31  mov     [rsp+130h+CreateFileType], r15d; CreateFileType
0x1400ebe36  mov     edx, r12d; DesiredAccess
0x1400ebe39  mov     [rsp+130h+EaLength], r15d; EaLength
0x1400ebe3e  mov     [rsp+130h+EaBuffer], r15; EaBuffer
0x1400ebe43  mov     [rsp+130h+CreateOptions], 1000h; CreateOptions
0x1400ebe4b  mov     [rsp+130h+Disposition], 1; Disposition
0x1400ebe53  mov     [rsp+130h+ShareAccess], edi; ShareAccess
0x1400ebe57  mov     [rsp+130h+FileAttributes], 80h; FileAttributes
0x1400ebe5f  mov     [rsp+130h+AllocationSize], r15; AllocationSize
0x1400ebe64  call    cs:__imp_IoCreateFileEx
0x1400ebe6b  nop     dword ptr [rax+rax+00h]
0x1400ebe70  mov     edi, eax
0x1400ebe72  cmp     eax, 0C0000034h
0x1400ebe77  jnz     short loc_1400EBEDE
0x1400ebe79  mov     r8d, cs:dword_140087708
0x1400ebe80  cmp     r8d, 4
0x1400ebe84  jbe     loc_1400EC01C
0x1400ebe8a  mov     rdx, r12
0x1400ebe8d  lea     rcx, dword_140087708
0x1400ebe94  call    _tlgKeywordOn
0x1400ebe99  test    al, al
0x1400ebe9b  jz      loc_1400EC01C
0x1400ebea1  mov     r9, [rbp+30h+var_38]
0x1400ebea5  lea     rax, [rbp+30h+var_A8]
0x1400ebea9  mov     qword ptr [rsp+130h+FileAttributes], rax
0x1400ebeae  lea     r8, [rbp+30h+ActivityId]
0x1400ebeb2  test    rbx, rbx
0x1400ebeb5  mov     dword ptr [rbp+30h+var_A8], 0C0000034h
0x1400ebebc  lea     rax, [rbp+30h+var_A0]
0x1400ebec0  cmovnz  rsi, rbx
0x1400ebec4  mov     [rsp+130h+AllocationSize], rax
0x1400ebec9  lea     rdx, byte_14007CBE1
0x1400ebed0  mov     [rbp+30h+var_A0], rsi
0x1400ebed4  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x1400ebed9  jmp     loc_1400EC01C
0x1400ebede  test    edi, edi
0x1400ebee0  jns     short loc_1400EBF20
0x1400ebee2  mov     eax, cs:dword_140087708
0x1400ebee8  cmp     eax, 2
0x1400ebeeb  jbe     short loc_1400EBF20
0x1400ebeed  mov     rdx, r12
0x1400ebef0  lea     rcx, dword_140087708
0x1400ebef7  call    _tlgKeywordOn
0x1400ebefc  test    al, al
0x1400ebefe  jz      short loc_1400EBF20
0x1400ebf00  mov     r9, [rbp+30h+var_38]
0x1400ebf04  lea     rax, [rbp+30h+var_A8]
0x1400ebf08  lea     r8, [rbp+30h+ActivityId]
0x1400ebf0c  mov     [rsp+130h+AllocationSize], rax
0x1400ebf11  lea     rdx, byte_14007CC21
0x1400ebf18  mov     dword ptr [rbp+30h+var_A8], edi
0x1400ebf1b  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1400ebf20  mov     eax, cs:dword_140087708
0x1400ebf26  cmp     eax, 4
0x1400ebf29  jbe     short loc_1400EBF72
0x1400ebf2b  mov     rdx, r12
0x1400ebf2e  lea     rcx, dword_140087708
0x1400ebf35  call    _tlgKeywordOn
0x1400ebf3a  test    al, al
0x1400ebf3c  jz      short loc_1400EBF72
0x1400ebf3e  mov     r9, [rbp+30h+var_38]
0x1400ebf42  lea     rax, [rbp+30h+var_A8]
0x1400ebf46  mov     qword ptr [rsp+130h+FileAttributes], rax
0x1400ebf4b  lea     r8, [rbp+30h+ActivityId]
0x1400ebf4f  test    rbx, rbx
0x1400ebf52  mov     dword ptr [rbp+30h+var_A8], edi
0x1400ebf55  lea     rax, [rbp+30h+var_A0]
0x1400ebf59  cmovnz  rsi, rbx
0x1400ebf5d  mov     [rsp+130h+AllocationSize], rax
0x1400ebf62  lea     rdx, byte_14007CC49
0x1400ebf69  mov     [rbp+30h+var_A0], rsi
0x1400ebf6d  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x1400ebf72  test    edi, edi
0x1400ebf74  js      short loc_1400EBFAA
0x1400ebf76  test    rbx, rbx
0x1400ebf79  jz      short loc_1400EBF98
0x1400ebf7b  test    byte ptr cs:Microsoft_Windows_VHDMPEnableBits, 1
0x1400ebf82  jz      short loc_1400EBF98
0x1400ebf84  mov     r9, rbx
0x1400ebf87  mov     dword ptr [rsp+130h+AllocationSize], r15d
0x1400ebf8c  lea     rdx, FileWrapperHandleCreateEnd
0x1400ebf93  call    McTemplateK0zq_EtwWriteTransfer
0x1400ebf98  mov     rcx, [rbp+30h+FileHandle]; Handle
0x1400ebf9c  call    cs:__imp_ZwClose
0x1400ebfa3  nop     dword ptr [rax+rax+00h]
0x1400ebfa8  jmp     short loc_1400EC01C
0x1400ebfaa  mov     eax, cs:dword_1400876D0
0x1400ebfb0  cmp     eax, 2
0x1400ebfb3  jbe     short loc_1400EBFFB
0x1400ebfb5  mov     edx, 800h
0x1400ebfba  lea     rcx, dword_1400876D0
0x1400ebfc1  call    _tlgKeywordOn
0x1400ebfc6  test    al, al
0x1400ebfc8  jz      short loc_1400EBFFB
0x1400ebfca  mov     ecx, 23B3h
0x1400ebfcf  mov     [rsp+130h+ShareAccess], edi
0x1400ebfd3  mov     r9d, edx; int
0x1400ebfd6  mov     qword ptr [rsp+130h+FileAttributes], r14; char
0x1400ebfdb  mov     edx, ecx; int
0x1400ebfdd  lea     rax, aVhdmpideletefi_0; "VhdmpiDeleteFile: Unable to delete file"...
0x1400ebfe4  lea     rcx, aVhdmpideletefi; "VhdmpiDeleteFile"
0x1400ebfeb  mov     [rsp+130h+AllocationSize], rax; char *
0x1400ebff0  mov     r8d, 2; int
0x1400ebff6  call    TraceEvents
0x1400ebffb  test    rbx, rbx
0x1400ebffe  jz      short loc_1400EC035
0x1400ec000  test    byte ptr cs:Microsoft_Windows_VHDMPEnableBits, 1
0x1400ec007  jz      short loc_1400EC01C
0x1400ec009  mov     r9, rbx
0x1400ec00c  mov     dword ptr [rsp+130h+AllocationSize], edi
0x1400ec010  lea     rdx, FileWrapperHandleCreateEndFailure
0x1400ec017  call    McTemplateK0zq_EtwWriteTransfer
0x1400ec01c  test    rbx, rbx
0x1400ec01f  jz      short loc_1400EC035
0x1400ec021  mov     edx, 7A444856h; Tag
0x1400ec026  mov     rcx, rbx; P
0x1400ec029  call    cs:__imp_ExFreePoolWithTag
0x1400ec030  nop     dword ptr [rax+rax+00h]
0x1400ec035  mov     eax, edi
0x1400ec037  mov     rcx, [rbp+30h+var_30]
0x1400ec03b  xor     rcx, rsp; StackCookie
0x1400ec03e  call    __security_check_cookie
0x1400ec043  lea     r11, [rsp+130h+var_20]
0x1400ec04b  mov     rbx, [r11+38h]
0x1400ec04f  mov     rsi, [r11+40h]
0x1400ec053  mov     rsp, r11
0x1400ec056  pop     r15
0x1400ec058  pop     r14
0x1400ec05a  pop     r12
0x1400ec05c  pop     rdi
0x1400ec05d  pop     rbp
0x1400ec05e  retn
```
