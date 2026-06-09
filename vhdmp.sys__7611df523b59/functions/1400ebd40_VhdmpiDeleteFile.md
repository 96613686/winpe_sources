# VhdmpiDeleteFile

- ea: `0x1400ebd40`
- end: `0x1400ec0d0`
- name: `VhdmpiDeleteFile`
- size: `912`
- prototype: `__int64 __fastcall(struct _UNICODE_STRING *)`
- caller_count: `10`
- callee_count: `9`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140040218`
- `0x14004db00`
- `0x14009e48c`
- `0x1400a38a0`
- `0x1400a41d0`
- `0x1400a5844`
- `0x1400c5560`
- `0x1400c62c0`
- `0x1400c78e0`
- `0x1400ebb80`

## callees

- `0x1400010d0`
- `0x140014e5c`
- `0x14001bdb0`
- `0x14001dbb4`
- `0x140023560`
- `0x140035e94`
- `0x14005d7c0`
- `0x14009d9a4`
- `0x1400ebd40`

## import_xrefs

- `ntoskrnl!IoCreateFileEx` at `0x1400ebed4`
- `ntoskrnl!IoCreateFileEx` at `0x1400ebed4`
- `ntoskrnl!ZwClose` at `0x1400ec00c`
- `ntoskrnl!ZwClose` at `0x1400ec00c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ec099`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ec099`
- `ntoskrnl!EtwActivityIdControl` at `0x1400ebdfc`
- `ntoskrnl!EtwActivityIdControl` at `0x1400ebdfc`

## string_xrefs

- `0x1400ec054`: `VhdmpiDeleteFile`
- `0x1400ec04d`: `VhdmpiDeleteFile: Unable to delete file '%wZ', status = 0x%08x`

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
  int v14; // edx
  char v16[8]; // [rsp+80h] [rbp-80h] BYREF
  wchar_t *v17; // [rsp+88h] [rbp-78h] BYREF
  const wchar_t *v18; // [rsp+90h] [rbp-70h] BYREF
  int v19; // [rsp+98h] [rbp-68h] BYREF
  void *FileHandle; // [rsp+A0h] [rbp-60h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+A8h] [rbp-58h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+D8h] [rbp-28h] BYREF
  GUID ActivityId; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v24; // [rsp+F8h] [rbp-8h]

  FileHandle = 0;
  IoStatusBlock = 0;
  v17 = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  v24 = 0;
  ActivityId = 0;
  v2 = VhdmpiDuplicateUnicodeStringToString(a1, &v17);
  v5 = v17;
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
  v24 = 0;
  if ( (unsigned int)dword_1400876D0 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 0x10000) )
  {
    v19 = 7;
    v9 = L"Unknown";
    LODWORD(v17) = 0x10000;
    if ( v5 )
      v9 = v5;
    v16[0] = 0;
    v18 = v9;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v7,
      (unsigned int)byte_14007CC49,
      (unsigned int)&ActivityId,
      v8,
      (__int64)&v18,
      (__int64)v16,
      (__int64)&v17,
      (__int64)&v19);
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
    if ( (unsigned int)dword_1400876D0 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 0x10000) )
    {
      LODWORD(v17) = -1073741772;
      if ( v5 )
        v6 = v5;
      v18 = v6;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        v13,
        (unsigned int)byte_14007CCA5,
        (unsigned int)&ActivityId,
        v24,
        (__int64)&v18,
        (__int64)&v17);
    }
LABEL_37:
    if ( v5 )
      ExFreePoolWithTag(v5, 0x7A444856u);
    return (unsigned int)v11;
  }
  if ( v11 < 0 && (unsigned int)dword_1400876D0 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 0x10000) )
  {
    LODWORD(v17) = v11;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      v10,
      (unsigned int)&word_14007CB9E,
      (unsigned int)&ActivityId,
      v24,
      (__int64)&v17);
  }
  if ( (unsigned int)dword_1400876D0 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 0x10000) )
  {
    LODWORD(v17) = v11;
    if ( v5 )
      v6 = v5;
    v18 = v6;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
      v10,
      (unsigned int)&word_14007CBC6,
      (unsigned int)&ActivityId,
      v24,
      (__int64)&v18,
      (__int64)&v17);
  }
  if ( v11 >= 0 )
  {
    if ( v5 && (Microsoft_Windows_VHDMPEnableBits & 1) != 0 )
      McTemplateK0zq_EtwWriteTransfer(v10, (unsigned int)FileWrapperHandleCreateEnd, v12, (_DWORD)v5, 0);
    ZwClose(FileHandle);
    goto LABEL_37;
  }
  if ( (unsigned int)dword_140087708 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 2048) )
    TraceEvents(
      (int)"VhdmpiDeleteFile",
      9139,
      2,
      v14,
      "VhdmpiDeleteFile: Unable to delete file '%wZ', status = 0x%08x",
      (char)a1);
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
0x1400ebd40  mov     [rsp-8+arg_8], rbx
0x1400ebd45  mov     [rsp-8+arg_10], rsi
0x1400ebd4a  push    rbp
0x1400ebd4b  push    rdi
0x1400ebd4c  push    r12
0x1400ebd4e  push    r14
0x1400ebd50  push    r15
0x1400ebd52  lea     rbp, [rsp-10h]
0x1400ebd57  sub     rsp, 110h
0x1400ebd5e  mov     rax, cs:__security_cookie
0x1400ebd65  xor     rax, rsp
0x1400ebd68  mov     [rbp+30h+var_30], rax
0x1400ebd6c  xorps   xmm1, xmm1
0x1400ebd6f  lea     rdx, [rbp+30h+var_A8]
0x1400ebd73  xorps   xmm0, xmm0
0x1400ebd76  xor     r15d, r15d
0x1400ebd79  xor     eax, eax
0x1400ebd7b  mov     [rbp+30h+FileHandle], r15
0x1400ebd7f  movups  xmmword ptr [rbp+30h+IoStatusBlock], xmm0
0x1400ebd83  mov     [rbp+30h+var_A8], r15
0x1400ebd87  mov     r14, rcx
0x1400ebd8a  movups  xmmword ptr [rbp+30h+ObjectAttributes.Length], xmm1
0x1400ebd8e  mov     [rbp+30h+var_38], rax
0x1400ebd92  movups  xmmword ptr [rbp+30h+ObjectAttributes.ObjectName], xmm1
0x1400ebd96  movups  xmmword ptr [rbp+30h+ObjectAttributes.SecurityDescriptor], xmm1
0x1400ebd9a  movups  xmmword ptr [rbp+30h+ActivityId.Data1], xmm0
0x1400ebd9e  call    VhdmpiDuplicateUnicodeStringToString
0x1400ebda3  mov     rbx, [rbp+30h+var_A8]
0x1400ebda7  test    eax, eax
0x1400ebda9  xorps   xmm0, xmm0
0x1400ebdac  mov     [rbp+30h+ObjectAttributes.Length], 30h ; '0'
0x1400ebdb3  cmovs   rbx, r15
0x1400ebdb7  mov     [rbp+30h+ObjectAttributes.RootDirectory], r15
0x1400ebdbb  mov     [rbp+30h+ObjectAttributes.Attributes], 240h
0x1400ebdc2  mov     r12d, 10000h
0x1400ebdc8  mov     [rbp+30h+ObjectAttributes.ObjectName], r14
0x1400ebdcc  movdqu  xmmword ptr [rbp+30h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400ebdd1  test    rbx, rbx
0x1400ebdd4  jz      short loc_1400EBDF3
0x1400ebdd6  test    byte ptr cs:Microsoft_Windows_VHDMPEnableBits, 1
0x1400ebddd  jz      short loc_1400EBDF3
0x1400ebddf  mov     r9, rbx
0x1400ebde2  mov     dword ptr [rsp+130h+AllocationSize], r12d
0x1400ebde7  lea     rdx, FileWrapperHandleCreateBegin
0x1400ebdee  call    McTemplateK0zq_EtwWriteTransfer
0x1400ebdf3  lea     rdx, [rbp+30h+ActivityId]; ActivityId
0x1400ebdf7  mov     ecx, 3; ControlCode
0x1400ebdfc  call    cs:__imp_EtwActivityIdControl
0x1400ebe03  nop     dword ptr [rax+rax+00h]
0x1400ebe08  mov     eax, cs:dword_1400876D0
0x1400ebe0e  lea     rsi, aUnknown; "Unknown"
0x1400ebe15  mov     [rbp+30h+var_38], r15
0x1400ebe19  mov     edi, 7
0x1400ebe1e  cmp     eax, 4
0x1400ebe21  jbe     short loc_1400EBE83
0x1400ebe23  mov     rdx, r12
0x1400ebe26  lea     rcx, dword_1400876D0
0x1400ebe2d  call    _tlgKeywordOn
0x1400ebe32  test    al, al
0x1400ebe34  jz      short loc_1400EBE83
0x1400ebe36  test    rbx, rbx
0x1400ebe39  mov     [rbp+30h+var_98], edi
0x1400ebe3c  mov     rax, rsi
0x1400ebe3f  mov     dword ptr [rbp+30h+var_A8], r12d
0x1400ebe43  cmovnz  rax, rbx
0x1400ebe47  mov     [rbp+30h+var_B0], r15b
0x1400ebe4b  mov     [rbp+30h+var_A0], rax
0x1400ebe4f  lea     r8, [rbp+30h+ActivityId]
0x1400ebe53  lea     rax, [rbp+30h+var_98]
0x1400ebe57  mov     qword ptr [rsp+130h+Disposition], rax
0x1400ebe5c  lea     rdx, byte_14007CC49
0x1400ebe63  lea     rax, [rbp+30h+var_A8]
0x1400ebe67  mov     qword ptr [rsp+130h+ShareAccess], rax
0x1400ebe6c  lea     rax, [rbp+30h+var_B0]
0x1400ebe70  mov     qword ptr [rsp+130h+FileAttributes], rax
0x1400ebe75  lea     rax, [rbp+30h+var_A0]
0x1400ebe79  mov     [rsp+130h+AllocationSize], rax
0x1400ebe7e  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$00@@U?$_tlgWrapperByVal@$03@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$00@@AEBU?$_tlgWrapperByVal@$03@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1400ebe83  mov     [rsp+130h+DriverContext], r15; DriverContext
0x1400ebe88  lea     r9, [rbp+30h+IoStatusBlock]; IoStatusBlock
0x1400ebe8c  mov     [rsp+130h+Options], 101h; Options
0x1400ebe94  lea     r8, [rbp+30h+ObjectAttributes]; ObjectAttributes
0x1400ebe98  mov     [rsp+130h+InternalParameters], r15; InternalParameters
0x1400ebe9d  lea     rcx, [rbp+30h+FileHandle]; FileHandle
0x1400ebea1  mov     [rsp+130h+CreateFileType], r15d; CreateFileType
0x1400ebea6  mov     edx, r12d; DesiredAccess
0x1400ebea9  mov     [rsp+130h+EaLength], r15d; EaLength
0x1400ebeae  mov     [rsp+130h+EaBuffer], r15; EaBuffer
0x1400ebeb3  mov     [rsp+130h+CreateOptions], 1000h; CreateOptions
0x1400ebebb  mov     [rsp+130h+Disposition], 1; Disposition
0x1400ebec3  mov     [rsp+130h+ShareAccess], edi; ShareAccess
0x1400ebec7  mov     [rsp+130h+FileAttributes], 80h; FileAttributes
0x1400ebecf  mov     [rsp+130h+AllocationSize], r15; AllocationSize
0x1400ebed4  call    cs:__imp_IoCreateFileEx
0x1400ebedb  nop     dword ptr [rax+rax+00h]
0x1400ebee0  mov     edi, eax
0x1400ebee2  cmp     eax, 0C0000034h
0x1400ebee7  jnz     short loc_1400EBF4E
0x1400ebee9  mov     r8d, cs:dword_1400876D0
0x1400ebef0  cmp     r8d, 4
0x1400ebef4  jbe     loc_1400EC08C
0x1400ebefa  mov     rdx, r12
0x1400ebefd  lea     rcx, dword_1400876D0
0x1400ebf04  call    _tlgKeywordOn
0x1400ebf09  test    al, al
0x1400ebf0b  jz      loc_1400EC08C
0x1400ebf11  mov     r9, [rbp+30h+var_38]
0x1400ebf15  lea     rax, [rbp+30h+var_A8]
0x1400ebf19  mov     qword ptr [rsp+130h+FileAttributes], rax
0x1400ebf1e  lea     r8, [rbp+30h+ActivityId]
0x1400ebf22  test    rbx, rbx
0x1400ebf25  mov     dword ptr [rbp+30h+var_A8], 0C0000034h
0x1400ebf2c  lea     rax, [rbp+30h+var_A0]
0x1400ebf30  cmovnz  rsi, rbx
0x1400ebf34  mov     [rsp+130h+AllocationSize], rax
0x1400ebf39  lea     rdx, byte_14007CCA5
0x1400ebf40  mov     [rbp+30h+var_A0], rsi
0x1400ebf44  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x1400ebf49  jmp     loc_1400EC08C
0x1400ebf4e  test    edi, edi
0x1400ebf50  jns     short loc_1400EBF90
0x1400ebf52  mov     eax, cs:dword_1400876D0
0x1400ebf58  cmp     eax, 2
0x1400ebf5b  jbe     short loc_1400EBF90
0x1400ebf5d  mov     rdx, r12
0x1400ebf60  lea     rcx, dword_1400876D0
0x1400ebf67  call    _tlgKeywordOn
0x1400ebf6c  test    al, al
0x1400ebf6e  jz      short loc_1400EBF90
0x1400ebf70  mov     r9, [rbp+30h+var_38]
0x1400ebf74  lea     rax, [rbp+30h+var_A8]
0x1400ebf78  lea     r8, [rbp+30h+ActivityId]
0x1400ebf7c  mov     [rsp+130h+AllocationSize], rax
0x1400ebf81  lea     rdx, word_14007CB9E
0x1400ebf88  mov     dword ptr [rbp+30h+var_A8], edi
0x1400ebf8b  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1400ebf90  mov     eax, cs:dword_1400876D0
0x1400ebf96  cmp     eax, 4
0x1400ebf99  jbe     short loc_1400EBFE2
0x1400ebf9b  mov     rdx, r12
0x1400ebf9e  lea     rcx, dword_1400876D0
0x1400ebfa5  call    _tlgKeywordOn
0x1400ebfaa  test    al, al
0x1400ebfac  jz      short loc_1400EBFE2
0x1400ebfae  mov     r9, [rbp+30h+var_38]
0x1400ebfb2  lea     rax, [rbp+30h+var_A8]
0x1400ebfb6  mov     qword ptr [rsp+130h+FileAttributes], rax
0x1400ebfbb  lea     r8, [rbp+30h+ActivityId]
0x1400ebfbf  test    rbx, rbx
0x1400ebfc2  mov     dword ptr [rbp+30h+var_A8], edi
0x1400ebfc5  lea     rax, [rbp+30h+var_A0]
0x1400ebfc9  cmovnz  rsi, rbx
0x1400ebfcd  mov     [rsp+130h+AllocationSize], rax
0x1400ebfd2  lea     rdx, word_14007CBC6
0x1400ebfd9  mov     [rbp+30h+var_A0], rsi
0x1400ebfdd  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x1400ebfe2  test    edi, edi
0x1400ebfe4  js      short loc_1400EC01A
0x1400ebfe6  test    rbx, rbx
0x1400ebfe9  jz      short loc_1400EC008
0x1400ebfeb  test    byte ptr cs:Microsoft_Windows_VHDMPEnableBits, 1
0x1400ebff2  jz      short loc_1400EC008
0x1400ebff4  mov     r9, rbx
0x1400ebff7  mov     dword ptr [rsp+130h+AllocationSize], r15d
0x1400ebffc  lea     rdx, FileWrapperHandleCreateEnd
0x1400ec003  call    McTemplateK0zq_EtwWriteTransfer
0x1400ec008  mov     rcx, [rbp+30h+FileHandle]; Handle
0x1400ec00c  call    cs:__imp_ZwClose
0x1400ec013  nop     dword ptr [rax+rax+00h]
0x1400ec018  jmp     short loc_1400EC08C
0x1400ec01a  mov     eax, cs:dword_140087708
0x1400ec020  cmp     eax, 2
0x1400ec023  jbe     short loc_1400EC06B
0x1400ec025  mov     edx, 800h
0x1400ec02a  lea     rcx, dword_140087708
0x1400ec031  call    _tlgKeywordOn
0x1400ec036  test    al, al
0x1400ec038  jz      short loc_1400EC06B
0x1400ec03a  mov     ecx, 23B3h
0x1400ec03f  mov     [rsp+130h+ShareAccess], edi
0x1400ec043  mov     r9d, edx; int
0x1400ec046  mov     qword ptr [rsp+130h+FileAttributes], r14; char
0x1400ec04b  mov     edx, ecx; int
0x1400ec04d  lea     rax, aVhdmpideletefi_0; "VhdmpiDeleteFile: Unable to delete file"...
0x1400ec054  lea     rcx, aVhdmpideletefi; "VhdmpiDeleteFile"
0x1400ec05b  mov     [rsp+130h+AllocationSize], rax; char *
0x1400ec060  mov     r8d, 2; int
0x1400ec066  call    TraceEvents
0x1400ec06b  test    rbx, rbx
0x1400ec06e  jz      short loc_1400EC0A5
0x1400ec070  test    byte ptr cs:Microsoft_Windows_VHDMPEnableBits, 1
0x1400ec077  jz      short loc_1400EC08C
0x1400ec079  mov     r9, rbx
0x1400ec07c  mov     dword ptr [rsp+130h+AllocationSize], edi
0x1400ec080  lea     rdx, FileWrapperHandleCreateEndFailure
0x1400ec087  call    McTemplateK0zq_EtwWriteTransfer
0x1400ec08c  test    rbx, rbx
0x1400ec08f  jz      short loc_1400EC0A5
0x1400ec091  mov     edx, 7A444856h; Tag
0x1400ec096  mov     rcx, rbx; P
0x1400ec099  call    cs:__imp_ExFreePoolWithTag
0x1400ec0a0  nop     dword ptr [rax+rax+00h]
0x1400ec0a5  mov     eax, edi
0x1400ec0a7  mov     rcx, [rbp+30h+var_30]
0x1400ec0ab  xor     rcx, rsp; StackCookie
0x1400ec0ae  call    __security_check_cookie
0x1400ec0b3  lea     r11, [rsp+130h+var_20]
0x1400ec0bb  mov     rbx, [r11+38h]
0x1400ec0bf  mov     rsi, [r11+40h]
0x1400ec0c3  mov     rsp, r11
0x1400ec0c6  pop     r15
0x1400ec0c8  pop     r14
0x1400ec0ca  pop     r12
0x1400ec0cc  pop     rdi
0x1400ec0cd  pop     rbp
0x1400ec0ce  retn
```
