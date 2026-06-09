# CThumbnailCacheDataFile::_RemapOrGrowMapping(ulong)

- ea: `0x180010ba0`
- end: `0x180010da7`
- name: `?_RemapOrGrowMapping@CThumbnailCacheDataFile@@AEAAJK@Z`
- size: `519`
- prototype: `int(CThumbnailCacheDataFile *__hidden this, unsigned int)`
- caller_count: `6`
- callee_count: `9`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x18000cc10`
- `0x18001048c`
- `0x1800108b4`
- `0x180012448`
- `0x180028b90`
- `0x180045114`

## callees

- `0x18000b33c`
- `0x18000b3c0`
- `0x18000bfd8`
- `0x18000c190`
- `0x180010ba0`
- `0x180011300`
- `0x18001290c`
- `0x180033f48`
- `0x18003470c`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180010bda`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180010c0f`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180010c7d`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180010c92`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180010d73`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180010bda`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180010c0f`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180010c7d`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180010c92`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180010d73`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180010c66`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180010c66`

## string_xrefs

- `0x180010d23`: `onecoreuap\shell\ext\thumbnailcache\lib\thumbfile.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CThumbnailCacheDataFile::_RemapOrGrowMapping(CThumbnailCacheDataFile *this, DWORD a2)
{
  CThumbnailCacheDataFile *v5; // rbx
  void *v6; // rbp
  HANDLE FileMappingW; // rax
  DWORD FileSize; // eax
  __int64 v9; // rbp
  DWORD v10; // r15d
  __int64 v11; // r12
  bool v12; // dl
  int v13; // esi
  __int64 v14; // rcx
  int Error; // eax
  __int64 v16; // rdx
  unsigned __int64 v17; // r9
  DWORD dwMaximumSizeLow; // [rsp+20h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  char v20; // [rsp+70h] [rbp+8h] BYREF

  if ( a2 )
  {
    if ( !*((_BYTE *)this + 16) )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    if ( *((_QWORD *)this + 52) == -1 )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    if ( a2 <= GetFileSize(*((HANDLE *)this + 52), 0) )
      MicrosoftTelemetryAssertTriggeredNoArgs();
  }
  if ( *((_QWORD *)this + 9) && !a2 && *((_QWORD *)this + 120) == GetFileSize(*((HANDLE *)this + 52), 0) )
    return 0;
  if ( *((_QWORD *)this + 120) > (__int64)GetFileSize(*((HANDLE *)this + 52), 0) )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  CThumbnailCacheDataFile::_CloseMapping(this);
  v5 = *(CThumbnailCacheDataFile **)wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(
                                      &v20,
                                      this);
  v6 = (void *)*((_QWORD *)this + 52);
  FileMappingW = CreateFileMappingW(v6, 0, 4u, 0, a2, 0);
  if ( FileMappingW )
  {
    *((_QWORD *)this + 9) = FileMappingW;
    *((_QWORD *)this + 10) = GetFileSize(v6, 0);
LABEL_10:
    FileSize = GetFileSize(*((HANDLE *)this + 52), 0);
    *((_QWORD *)this + 120) = FileSize;
    v9 = *((_QWORD *)this + 4);
    v10 = FileSize;
    v11 = *((int *)this + 106);
    v12 = 0;
    if ( !*(_DWORD *)(v9 + 60) && !*(_DWORD *)(v9 + 56) )
    {
      v13 = CReadersWriterLock::AcquireReaderLock((CReadersWriterLock *)(v9 + 8), 0xFAu);
      if ( v13 < 0 )
        goto LABEL_24;
      v12 = 1;
    }
    v14 = *(_QWORD *)(v9 + 72);
    if ( v14 )
    {
      v13 = 0;
      *(_DWORD *)(v14 + 4 * v11 + 28) = v10;
    }
    else
    {
      v13 = -2147467259;
    }
    CThumbnailCacheIndex::_ReleaseReaderLockIfNeeded((CThumbnailCacheIndex *)v9, v12);
    if ( v13 >= 0 )
    {
      Error = CSmartMappedView<DataFileHeader>::MapPartialViewAtOffset((char *)this + 40, (char *)this + 72);
      v13 = Error;
      if ( Error >= 0 )
        return 0;
      v16 = 638;
      goto LABEL_21;
    }
LABEL_24:
    v17 = (unsigned int)v13;
    v16 = 636;
    goto LABEL_22;
  }
  Error = ResultFromKnownLastError();
  v13 = Error;
  if ( Error >= 0 )
    goto LABEL_10;
  v16 = 633;
LABEL_21:
  v17 = (unsigned int)Error;
LABEL_22:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v16,
    (unsigned int)"onecoreuap\\shell\\ext\\thumbnailcache\\lib\\thumbfile.cpp",
    (const char *)v17,
    dwMaximumSizeLow);
  CThumbnailCacheDataFile::_CloseMapping(v5);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x180010ba0  mov     [rsp+arg_8], rbx
0x180010ba5  mov     [rsp+arg_10], rbp
0x180010baa  push    rsi
0x180010bab  push    rdi
0x180010bac  push    r12
0x180010bae  push    r14
0x180010bb0  push    r15
0x180010bb2  sub     rsp, 40h
0x180010bb6  mov     esi, edx
0x180010bb8  mov     rdi, rcx
0x180010bbb  test    edx, edx
0x180010bbd  jnz     loc_180010D55
0x180010bc3  lea     r14, [rdi+48h]
0x180010bc7  cmp     qword ptr [r14], 0
0x180010bcb  jz      short loc_180010C06
0x180010bcd  test    esi, esi
0x180010bcf  jnz     short loc_180010C06
0x180010bd1  xor     edx, edx; lpFileSizeHigh
0x180010bd3  mov     rcx, [rdi+1A0h]; hFile
0x180010bda  call    cs:__imp_GetFileSize
0x180010be0  mov     ecx, eax
0x180010be2  cmp     [rdi+3C0h], rcx
0x180010be9  jnz     short loc_180010C06
0x180010beb  xor     eax, eax
0x180010bed  lea     r11, [rsp+68h+var_28]
0x180010bf2  mov     rbx, [r11+38h]
0x180010bf6  mov     rbp, [r11+40h]
0x180010bfa  mov     rsp, r11
0x180010bfd  pop     r15
0x180010bff  pop     r14
0x180010c01  pop     r12
0x180010c03  pop     rdi
0x180010c04  pop     rsi
0x180010c05  retn
0x180010c06  xor     edx, edx; lpFileSizeHigh
0x180010c08  mov     rcx, [rdi+1A0h]; hFile
0x180010c0f  call    cs:__imp_GetFileSize
0x180010c15  mov     eax, eax
0x180010c17  cmp     [rdi+3C0h], rax
0x180010c1e  jg      loc_180010D92
0x180010c24  mov     rcx, rdi; this
0x180010c27  call    ?_CloseMapping@CThumbnailCacheDataFile@@AEAAXXZ; CThumbnailCacheDataFile::_CloseMapping(void)
0x180010c2c  mov     rdx, rdi
0x180010c2f  lea     rcx, [rsp+68h+arg_0]
0x180010c34  call    ??0?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@PEAU_RTL_SRWLOCK@@@Z; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(_RTL_SRWLOCK *)
0x180010c39  mov     rbx, [rax]
0x180010c3c  mov     [rsp+68h+var_38], rbx
0x180010c41  mov     [rsp+68h+var_30], 1
0x180010c46  mov     rbp, [rdi+1A0h]
0x180010c4d  mov     [rsp+68h+lpName], 0; lpName
0x180010c56  mov     [rsp+68h+dwMaximumSizeLow], esi; int
0x180010c5a  xor     r9d, r9d; dwMaximumSizeHigh
0x180010c5d  xor     edx, edx; lpFileMappingAttributes
0x180010c5f  lea     r8d, [r9+4]; flProtect
0x180010c63  mov     rcx, rbp; hFile
0x180010c66  call    cs:__imp_CreateFileMappingW
0x180010c6c  test    rax, rax
0x180010c6f  jz      loc_180010D0C
0x180010c75  mov     [r14], rax
0x180010c78  xor     edx, edx; lpFileSizeHigh
0x180010c7a  mov     rcx, rbp; hFile
0x180010c7d  call    cs:__imp_GetFileSize
0x180010c83  mov     eax, eax
0x180010c85  mov     [r14+8], rax
0x180010c89  xor     edx, edx; lpFileSizeHigh
0x180010c8b  mov     rcx, [rdi+1A0h]; hFile
0x180010c92  call    cs:__imp_GetFileSize
0x180010c98  mov     eax, eax
0x180010c9a  mov     [rdi+3C0h], rax
0x180010ca1  mov     rbp, [rdi+20h]
0x180010ca5  mov     r15d, eax
0x180010ca8  movsxd  r12, dword ptr [rdi+1A8h]
0x180010caf  xor     dl, dl
0x180010cb1  lea     rcx, [rbp+8]; this
0x180010cb5  mov     eax, [rcx+34h]
0x180010cb8  test    eax, eax
0x180010cba  jnz     short loc_180010CD5
0x180010cbc  mov     eax, [rcx+30h]
0x180010cbf  test    eax, eax
0x180010cc1  jnz     short loc_180010CD5
0x180010cc3  mov     edx, 0FAh; unsigned int
0x180010cc8  call    ?AcquireReaderLock@CReadersWriterLock@@QEAAJK@Z; CReadersWriterLock::AcquireReaderLock(ulong)
0x180010ccd  mov     esi, eax
0x180010ccf  test    eax, eax
0x180010cd1  js      short loc_180010D4B
0x180010cd3  mov     dl, 1; bool
0x180010cd5  mov     rcx, [rbp+48h]
0x180010cd9  test    rcx, rcx
0x180010cdc  jz      short loc_180010D44
0x180010cde  xor     esi, esi
0x180010ce0  mov     [rcx+r12*4+1Ch], r15d
0x180010ce5  mov     rcx, rbp; this
0x180010ce8  call    ?_ReleaseReaderLockIfNeeded@CThumbnailCacheIndex@@AEAAX_N@Z; CThumbnailCacheIndex::_ReleaseReaderLockIfNeeded(bool)
0x180010ced  test    esi, esi
0x180010cef  js      short loc_180010D4B
0x180010cf1  lea     rcx, [rdi+28h]
0x180010cf5  mov     rdx, r14
0x180010cf8  call    ?MapPartialViewAtOffset@?$CSmartMappedView@UDataFileHeader@@@@QEAAJPEAVCMappingManager@@HKK@Z; CSmartMappedView<DataFileHeader>::MapPartialViewAtOffset(CMappingManager *,int,ulong,ulong)
0x180010cfd  mov     esi, eax
0x180010cff  test    eax, eax
0x180010d01  js      loc_180010D9C
0x180010d07  jmp     loc_180010BEB
0x180010d0c  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180010d11  mov     esi, eax
0x180010d13  test    eax, eax
0x180010d15  jns     loc_180010C89
0x180010d1b  mov     edx, 279h; void *
0x180010d20  mov     r9d, eax; char *
0x180010d23  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\ext\\thumbnailcache"...
0x180010d2a  mov     rcx, [rsp+68h]; this
0x180010d2f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010d34  nop
0x180010d35  mov     rcx, rbx; this
0x180010d38  call    ?_CloseMapping@CThumbnailCacheDataFile@@AEAAXXZ; CThumbnailCacheDataFile::_CloseMapping(void)
0x180010d3d  mov     eax, esi
0x180010d3f  jmp     loc_180010BED
0x180010d44  mov     esi, 80004005h
0x180010d49  jmp     short loc_180010CE5
0x180010d4b  mov     r9d, esi
0x180010d4e  mov     edx, 27Ch
0x180010d53  jmp     short loc_180010D23
0x180010d55  cmp     byte ptr [rcx+10h], 0
0x180010d59  jz      short loc_180010D8B
0x180010d5b  cmp     qword ptr [rdi+1A0h], 0FFFFFFFFFFFFFFFFh
0x180010d63  jnz     short loc_180010D6A
0x180010d65  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "IsOpened()")
0x180010d6a  xor     edx, edx; lpFileSizeHigh
0x180010d6c  mov     rcx, [rdi+1A0h]; hFile
0x180010d73  call    cs:__imp_GetFileSize
0x180010d79  cmp     esi, eax
0x180010d7b  ja      loc_180010BC3
0x180010d81  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "cbNewFileSize > _GetFileSize()")
0x180010d86  jmp     loc_180010BC3
0x180010d8b  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "_mtxMaintainer.IsHeldLocally()")
0x180010d90  jmp     short loc_180010D5B
0x180010d92  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "_cbLastKnownFileSize <= _GetFileSize()")
0x180010d97  jmp     loc_180010C24
0x180010d9c  mov     edx, 27Eh
0x180010da1  jmp     loc_180010D20
```
