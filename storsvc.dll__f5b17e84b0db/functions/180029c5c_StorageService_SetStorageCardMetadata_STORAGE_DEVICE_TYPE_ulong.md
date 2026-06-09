# StorageService::SetStorageCardMetadata(_STORAGE_DEVICE_TYPE,ulong)

- ea: `0x180029c5c`
- end: `0x180029e60`
- name: `?SetStorageCardMetadata@StorageService@@IEAAJW4_STORAGE_DEVICE_TYPE@@K@Z`
- size: `516`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, service_task`

## callers

- `0x180020f10`

## callees

- `0x180001cf0`
- `0x18000d030`
- `0x18000dd8c`
- `0x180021d8c`
- `0x180022c28`
- `0x180023f10`
- `0x180029c5c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180029d71`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180029d71`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180029da7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180029da7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180029dea`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180029dea`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180029cba`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180029cba`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180029d22`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180029d22`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180029dd1`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180029dd1`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180029ccf`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180029ccf`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180029cda`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180029cda`

## pseudocode

```c
__int64 __fastcall StorageService::SetStorageCardMetadata(__int64 a1, unsigned int a2, __int64 a3)
{
  __int64 v3; // rsi
  __int64 v4; // r14
  signed int MetadataFilePath; // edi
  int v7; // r8d
  int v8; // r9d
  HANDLE FileW; // r15
  int v10; // edi
  DWORD NumberOfBytesWritten; // [rsp+40h] [rbp-C0h] BYREF
  signed int v13; // [rsp+44h] [rbp-BCh] BYREF
  int v14; // [rsp+48h] [rbp-B8h] BYREF
  int v15; // [rsp+4Ch] [rbp-B4h] BYREF
  __int64 Buffer; // [rsp+50h] [rbp-B0h] BYREF
  int v17; // [rsp+58h] [rbp-A8h]
  WCHAR FileName[264]; // [rsp+60h] [rbp-A0h] BYREF

  v3 = (int)a2;
  v4 = (unsigned int)a3;
  Buffer = 0;
  v17 = 0;
  NumberOfBytesWritten = 0;
  MetadataFilePath = StorageService::GetMetadataFilePath(a1, a2, a3, FileName);
  if ( MetadataFilePath < 0 )
  {
LABEL_13:
    if ( (unsigned int)dword_1800BF000 > 5 )
    {
      v13 = MetadataFilePath;
      v14 = v4;
      v15 = v3;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (unsigned int)&dword_1800BF000,
        (unsigned int)&byte_1800A6E67,
        v7,
        v8,
        (__int64)&v15,
        (__int64)&v14,
        (__int64)&v13);
    }
    return (unsigned int)MetadataFilePath;
  }
  if ( GetFileAttributesW(FileName) == -1 )
  {
    MetadataFilePath = StorageService::EnsureSystemVolumeInformationFolder(a1, (unsigned int)v3, (unsigned int)v4);
    if ( MetadataFilePath < 0 )
      goto LABEL_13;
  }
  else
  {
    SetFileAttributesW(FileName, 0x80u);
    DeleteFileW(FileName);
  }
  FileW = CreateFileW(FileName, 0x40000000u, 0, 0, 2u, 0, 0);
  if ( FileW == (HANDLE)-1LL )
  {
    MetadataFilePath = -2147467259;
    goto LABEL_13;
  }
  LODWORD(Buffer) = 12;
  MetadataFilePath = StorageService::GenerateStorageId(a1, (unsigned int)v3, (unsigned int)v4, (char *)&Buffer + 4, 1);
  if ( MetadataFilePath >= 0 )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 1624));
    v10 = -(memcmp_0(&GUID_NULL, (const void *)(*(_QWORD *)(a1 + 8 * v3 + 40) + 548LL + 1112 * v4), 0x10u) == 0);
    LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 1624));
    MetadataFilePath = v10 & 0x80004005;
    if ( MetadataFilePath >= 0
      && (!WriteFile(FileW, &Buffer, 0xCu, &NumberOfBytesWritten, 0) || NumberOfBytesWritten != 12) )
    {
      MetadataFilePath = -2147467259;
    }
  }
  CloseHandle(FileW);
  if ( MetadataFilePath < 0 )
    goto LABEL_13;
  return (unsigned int)MetadataFilePath;
}

```

## disassembly

```asm
0x180029c5c  push    rbp
0x180029c5e  push    rbx
0x180029c5f  push    rsi
0x180029c60  push    rdi
0x180029c61  push    r13
0x180029c63  push    r14
0x180029c65  push    r15
0x180029c67  lea     rbp, [rsp-180h]
0x180029c6f  sub     rsp, 280h
0x180029c76  mov     rax, cs:__security_cookie
0x180029c7d  xor     rax, rsp
0x180029c80  mov     [rbp+1B0h+var_40], rax
0x180029c87  xor     eax, eax
0x180029c89  movsxd  rsi, edx
0x180029c8c  mov     edx, esi
0x180029c8e  mov     r14d, r8d
0x180029c91  lea     r9, [rsp+2B0h+FileName]
0x180029c96  mov     [rsp+2B0h+Buffer], rax
0x180029c9b  mov     r13, rcx
0x180029c9e  mov     [rsp+2B0h+var_258], eax
0x180029ca2  mov     [rsp+2B0h+NumberOfBytesWritten], eax
0x180029ca6  call    ?GetMetadataFilePath@StorageService@@IEAAJW4_STORAGE_DEVICE_TYPE@@KPEAG@Z; StorageService::GetMetadataFilePath(_STORAGE_DEVICE_TYPE,ulong,ushort *)
0x180029cab  mov     edi, eax
0x180029cad  test    eax, eax
0x180029caf  js      loc_180029DF4
0x180029cb5  lea     rcx, [rsp+2B0h+FileName]; lpFileName
0x180029cba  call    cs:__imp_GetFileAttributesW
0x180029cc0  cmp     eax, 0FFFFFFFFh
0x180029cc3  jz      short loc_180029CE2
0x180029cc5  mov     edx, 80h; dwFileAttributes
0x180029cca  lea     rcx, [rsp+2B0h+FileName]; lpFileName
0x180029ccf  call    cs:__imp_SetFileAttributesW
0x180029cd5  lea     rcx, [rsp+2B0h+FileName]; lpFileName
0x180029cda  call    cs:__imp_DeleteFileW
0x180029ce0  jmp     short loc_180029CF9
0x180029ce2  mov     r8d, r14d
0x180029ce5  mov     edx, esi
0x180029ce7  mov     rcx, r13
0x180029cea  call    ?EnsureSystemVolumeInformationFolder@StorageService@@IEAAJW4_STORAGE_DEVICE_TYPE@@K@Z; StorageService::EnsureSystemVolumeInformationFolder(_STORAGE_DEVICE_TYPE,ulong)
0x180029cef  mov     edi, eax
0x180029cf1  test    eax, eax
0x180029cf3  js      loc_180029DF4
0x180029cf9  mov     [rsp+2B0h+hTemplateFile], 0; hTemplateFile
0x180029d02  lea     rcx, [rsp+2B0h+FileName]; lpFileName
0x180029d07  mov     [rsp+2B0h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x180029d0f  xor     r9d, r9d; lpSecurityAttributes
0x180029d12  xor     r8d, r8d; dwShareMode
0x180029d15  mov     [rsp+2B0h+dwCreationDisposition], 2; dwCreationDisposition
0x180029d1d  mov     edx, 40000000h; dwDesiredAccess
0x180029d22  call    cs:__imp_CreateFileW
0x180029d28  mov     r15, rax
0x180029d2b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180029d2f  jnz     short loc_180029D3B
0x180029d31  mov     edi, 80004005h
0x180029d36  jmp     loc_180029DF4
0x180029d3b  lea     r9, [rsp+2B0h+Buffer+4]
0x180029d40  mov     dword ptr [rsp+2B0h+Buffer], 0Ch
0x180029d48  mov     r8d, r14d
0x180029d4b  mov     [rsp+2B0h+dwCreationDisposition], 1
0x180029d53  mov     edx, esi
0x180029d55  mov     rcx, r13
0x180029d58  call    ?GenerateStorageId@StorageService@@IEAAJW4_STORAGE_DEVICE_TYPE@@KPEAEH@Z; StorageService::GenerateStorageId(_STORAGE_DEVICE_TYPE,ulong,uchar *,int)
0x180029d5d  mov     edi, eax
0x180029d5f  test    eax, eax
0x180029d61  js      loc_180029DE7
0x180029d67  lea     rbx, [r13+658h]
0x180029d6e  mov     rcx, rbx; lpCriticalSection
0x180029d71  call    cs:__imp_EnterCriticalSection
0x180029d77  mov     rax, [r13+rsi*8+28h]
0x180029d7c  lea     rcx, GUID_NULL; Buf1
0x180029d83  add     rax, 224h
0x180029d89  mov     r8d, 10h; Size
0x180029d8f  imul    rdx, r14, 458h
0x180029d96  add     rdx, rax; Buf2
0x180029d99  call    memcmp_0
0x180029d9e  neg     eax
0x180029da0  mov     rcx, rbx; lpCriticalSection
0x180029da3  sbb     edi, edi
0x180029da5  not     edi
0x180029da7  call    cs:__imp_LeaveCriticalSection
0x180029dad  and     edi, 80004005h
0x180029db3  js      short loc_180029DE7
0x180029db5  lea     r9, [rsp+2B0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180029dba  mov     qword ptr [rsp+2B0h+dwCreationDisposition], 0; lpOverlapped
0x180029dc3  mov     r8d, 0Ch; nNumberOfBytesToWrite
0x180029dc9  lea     rdx, [rsp+2B0h+Buffer]; lpBuffer
0x180029dce  mov     rcx, r15; hFile
0x180029dd1  call    cs:__imp_WriteFile
0x180029dd7  test    eax, eax
0x180029dd9  jz      short loc_180029DE2
0x180029ddb  cmp     [rsp+2B0h+NumberOfBytesWritten], 0Ch
0x180029de0  jz      short loc_180029DE7
0x180029de2  mov     edi, 80004005h
0x180029de7  mov     rcx, r15; hObject
0x180029dea  call    cs:__imp_CloseHandle
0x180029df0  test    edi, edi
0x180029df2  jns     short loc_180029E3D
0x180029df4  mov     eax, cs:dword_1800BF000
0x180029dfa  cmp     eax, 5
0x180029dfd  jbe     short loc_180029E3D
0x180029dff  lea     rax, [rsp+2B0h+var_26C]
0x180029e04  mov     [rsp+2B0h+var_26C], edi
0x180029e08  mov     [rsp+2B0h+hTemplateFile], rax
0x180029e0d  lea     rdx, byte_1800A6E67
0x180029e14  lea     rax, [rsp+2B0h+var_268]
0x180029e19  mov     [rsp+2B0h+var_268], r14d
0x180029e1e  mov     qword ptr [rsp+2B0h+dwFlagsAndAttributes], rax
0x180029e23  lea     rcx, dword_1800BF000
0x180029e2a  lea     rax, [rsp+2B0h+var_264]
0x180029e2f  mov     [rsp+2B0h+var_264], esi
0x180029e33  mov     qword ptr [rsp+2B0h+dwCreationDisposition], rax
0x180029e38  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180029e3d  mov     eax, edi
0x180029e3f  mov     rcx, [rbp+1B0h+var_40]
0x180029e46  xor     rcx, rsp; StackCookie
0x180029e49  call    __security_check_cookie
0x180029e4e  add     rsp, 280h
0x180029e55  pop     r15
0x180029e57  pop     r14
0x180029e59  pop     r13
0x180029e5b  pop     rdi
0x180029e5c  pop     rsi
0x180029e5d  pop     rbx
0x180029e5e  pop     rbp
0x180029e5f  retn
```
