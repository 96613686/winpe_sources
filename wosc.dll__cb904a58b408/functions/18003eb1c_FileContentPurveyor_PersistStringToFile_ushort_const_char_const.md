# FileContentPurveyor::PersistStringToFile(ushort const *,char const *)

- ea: `0x18003eb1c`
- end: `0x18003ee22`
- name: `?PersistStringToFile@FileContentPurveyor@@SAXPEBGPEBD@Z`
- size: `774`
- prototype: `void __fastcall(LPCWSTR lpNewFileName, BYTE *pbData)`
- caller_count: `2`
- callee_count: `14`
- tags: `file_ops, registry_config, loader_planting`

## callers

- `0x18003e8f0`
- `0x18003ee28`

## callees

- `0x180003110`
- `0x1800101e0`
- `0x1800101fc`
- `0x180010278`
- `0x180014928`
- `0x180014d60`
- `0x180019e68`
- `0x180019efc`
- `0x18001a128`
- `0x1800283a8`
- `0x18003cbd4`
- `0x18003cd0c`
- `0x18003eb1c`
- `0x18003ffec`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003eb5d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003eb5d`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18003ec5a`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18003ec5a`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18003ed09`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18003ed09`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003ec1e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003ecd2`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003ec1e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003ecd2`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18003eb4f`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18003eb4f`
- `api-ms-win-core-file-l1-1-0!FlushFileBuffers` at `0x18003ec7b`
- `api-ms-win-core-file-l1-1-0!FlushFileBuffers` at `0x18003ec7b`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x18003edcd`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x18003edcd`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall FileContentPurveyor::PersistStringToFile(LPCWSTR lpNewFileName, BYTE *pbData)
{
  DWORD LastError; // eax
  __int64 v5; // rdi
  int Sha256Hash; // eax
  const WCHAR *v7; // rax
  HANDLE FileW; // rax
  const char *v9; // r9
  void *v10; // rbx
  const char *v11; // r9
  const char *v12; // r9
  const WCHAR *v13; // rax
  HANDLE v14; // rbx
  const char *v15; // r9
  int v16; // eax
  const WCHAR *v17; // rax
  const char *v18; // r9
  unsigned int dwCreationDisposition; // [rsp+20h] [rbp-59h]
  int dwCreationDispositiona; // [rsp+20h] [rbp-59h]
  DWORD NumberOfBytesRead[2]; // [rsp+40h] [rbp-39h] BYREF
  HANDLE v22; // [rsp+48h] [rbp-31h] BYREF
  BYTE *v23; // [rsp+50h] [rbp-29h] BYREF
  __int64 v24; // [rsp+58h] [rbp-21h]
  BYTE *v25; // [rsp+68h] [rbp-11h] BYREF
  int v26; // [rsp+70h] [rbp-9h]
  LPVOID lpBuffer[3]; // [rsp+80h] [rbp+7h] BYREF
  _BYTE v28[32]; // [rsp+98h] [rbp+1Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  if ( pbData )
  {
    v5 = -1;
    do
      ++v5;
    while ( pbData[v5] );
    std::wstring::wstring(v28, lpNewFileName);
    std::wstring::append(v28, L".tmp");
    std::vector<unsigned char>::vector<unsigned char>(&v23, 32);
    Sha256Hash = EncryptionHelper::GetSha256Hash(pbData, v5, v23, (int)v24 - (int)v23);
    if ( Sha256Hash < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x39,
        (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\payloadhandlers\\FileContentPurveyor.h",
        (const char *)(unsigned int)Sha256Hash,
        dwCreationDisposition);
    v7 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v28);
    FileW = CreateFileW(v7, 0x120116u, 0, 0, 2u, 0x80000000, 0);
    v10 = FileW;
    *(_QWORD *)NumberOfBytesRead = FileW;
    if ( FileW == (HANDLE)-1LL )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x47,
        (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\payloadhandlers\\FileContentPurveyor.h",
        v9);
    if ( !WriteFile(FileW, pbData, v5, 0, 0) )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x4A,
        (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\payloadhandlers\\FileContentPurveyor.h",
        v11);
    if ( !FlushFileBuffers(v10) )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x4C,
        (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\payloadhandlers\\FileContentPurveyor.h",
        v12);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(NumberOfBytesRead);
    v13 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v28);
    v14 = CreateFileW(v13, 0x120089u, 0, 0, 3u, 0x80u, 0);
    v22 = v14;
    std::vector<unsigned char>::vector<unsigned char>(lpBuffer, (unsigned int)v5);
    NumberOfBytesRead[0] = 0;
    if ( !ReadFile(v14, lpBuffer[0], v5, NumberOfBytesRead, 0) )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x5D,
        (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\payloadhandlers\\FileContentPurveyor.h",
        v15);
    std::vector<unsigned char>::vector<unsigned char>(&v25, 32);
    v16 = EncryptionHelper::GetSha256Hash((BYTE *)lpBuffer[0], NumberOfBytesRead[0], v25, v26 - (int)v25);
    if ( v16 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x62,
        (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\payloadhandlers\\FileContentPurveyor.h",
        (const char *)(unsigned int)v16,
        dwCreationDispositiona);
    if ( !(unsigned __int8)std::equal<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<unsigned char>>>,std::_Vector_iterator<std::_Vector_val<std::_Simple_types<unsigned char>>>,std::equal_to<void>>(
                             v23,
                             v24,
                             v25) )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x65,
        (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\payloadhandlers\\FileContentPurveyor.h",
        (const char *)0x80070570LL,
        dwCreationDispositiona);
    std::vector<unsigned char>::_Tidy(&v25);
    std::vector<unsigned char>::_Tidy(lpBuffer);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v22);
    v17 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v28);
    if ( !MoveFileExW(v17, lpNewFileName, 1u) )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x69,
        (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\payloadhandlers\\FileContentPurveyor.h",
        v18);
    std::vector<unsigned char>::_Tidy(&v23);
    std::wstring::_Tidy_deallocate(v28);
  }
  else if ( !DeleteFileW(lpNewFileName) )
  {
    LastError = GetLastError();
    if ( LastError != 2 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x26,
        (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\payloadhandlers\\FileContentPurveyor.h",
        (const char *)LastError,
        dwCreationDisposition);
  }
}

```

## disassembly

```asm
0x18003eb1c  mov     [rsp-8+arg_10], rbx
0x18003eb21  mov     [rsp-8+arg_18], rsi
0x18003eb26  push    rbp
0x18003eb27  push    rdi
0x18003eb28  push    r14
0x18003eb2a  lea     rbp, [rsp-47h]
0x18003eb2f  sub     rsp, 0C0h
0x18003eb36  mov     rax, cs:__security_cookie
0x18003eb3d  xor     rax, rsp
0x18003eb40  mov     [rbp+57h+var_18], rax
0x18003eb44  mov     rsi, rdx
0x18003eb47  mov     r14, rcx
0x18003eb4a  test    rdx, rdx
0x18003eb4d  jnz     short loc_18003EB83
0x18003eb4f  call    cs:__imp_DeleteFileW
0x18003eb55  test    eax, eax
0x18003eb57  jnz     loc_18003EDFE
0x18003eb5d  call    cs:__imp_GetLastError
0x18003eb63  cmp     eax, 2
0x18003eb66  jz      loc_18003EDFE
0x18003eb6c  mov     rcx, [rbp+5Fh]; this
0x18003eb70  mov     r9d, eax; char *
0x18003eb73  lea     r8, aOnecoreBaseFli_34; "onecore\\base\\flighting\\onesettings\\"...
0x18003eb7a  lea     edx, [rsi+26h]; void *
0x18003eb7d  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18003eb83  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18003eb87  inc     rdi
0x18003eb8a  cmp     byte ptr [rdx+rdi], 0
0x18003eb8e  jnz     short loc_18003EB87
0x18003eb90  mov     rdx, r14
0x18003eb93  lea     rcx, [rbp+57h+var_38]
0x18003eb97  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18003eb9c  nop
0x18003eb9d  lea     rdx, aTmp; ".tmp"
0x18003eba4  lea     rcx, [rbp+57h+var_38]
0x18003eba8  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18003ebad  mov     edx, 20h ; ' '
0x18003ebb2  lea     rcx, [rbp+57h+var_80]
0x18003ebb6  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@_KAEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(unsigned __int64,std::allocator<uchar> const &)
0x18003ebbb  nop
0x18003ebbc  mov     r8, [rbp+57h+var_80]; BYTE *
0x18003ebc0  mov     r9d, dword ptr [rbp+57h+var_78]
0x18003ebc4  sub     r9d, r8d; unsigned int
0x18003ebc7  mov     edx, edi; dwDataLen
0x18003ebc9  mov     rcx, rsi; pbData
0x18003ebcc  call    ?GetSha256Hash@EncryptionHelper@@SAJPEBEKPEAEK@Z; EncryptionHelper::GetSha256Hash(uchar const *,ulong,uchar *,ulong)
0x18003ebd1  mov     rcx, [rbp+5Fh]; this
0x18003ebd5  test    eax, eax
0x18003ebd7  jns     short loc_18003EBEE
0x18003ebd9  mov     r9d, eax; char *
0x18003ebdc  lea     r8, aOnecoreBaseFli_34; "onecore\\base\\flighting\\onesettings\\"...
0x18003ebe3  mov     edx, 39h ; '9'; void *
0x18003ebe8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003ebee  lea     rcx, [rbp+57h+var_38]
0x18003ebf2  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18003ebf7  mov     rcx, rax; lpFileName
0x18003ebfa  mov     [rsp+0D0h+hTemplateFile], 0; hTemplateFile
0x18003ec03  mov     [rsp+0D0h+dwFlagsAndAttributes], 80000000h; dwFlagsAndAttributes
0x18003ec0b  mov     [rsp+0D0h+dwCreationDisposition], 2; dwCreationDisposition
0x18003ec13  xor     r9d, r9d; lpSecurityAttributes
0x18003ec16  xor     r8d, r8d; dwShareMode
0x18003ec19  mov     edx, 120116h; dwDesiredAccess
0x18003ec1e  call    cs:__imp_CreateFileW
0x18003ec24  mov     rbx, rax
0x18003ec27  mov     qword ptr [rbp+57h+NumberOfBytesRead], rax
0x18003ec2b  mov     rcx, [rbp+5Fh]; this
0x18003ec2f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18003ec33  jnz     short loc_18003EC45
0x18003ec35  lea     r8, aOnecoreBaseFli_34; "onecore\\base\\flighting\\onesettings\\"...
0x18003ec3c  lea     edx, [rax+48h]; void *
0x18003ec3f  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18003ec45  mov     qword ptr [rsp+0D0h+dwCreationDisposition], 0; lpOverlapped
0x18003ec4e  xor     r9d, r9d; lpNumberOfBytesWritten
0x18003ec51  mov     r8d, edi; nNumberOfBytesToWrite
0x18003ec54  mov     rdx, rsi; lpBuffer
0x18003ec57  mov     rcx, rbx; hFile
0x18003ec5a  call    cs:__imp_WriteFile
0x18003ec60  mov     rcx, [rbp+5Fh]; this
0x18003ec64  test    eax, eax
0x18003ec66  jnz     short loc_18003EC78
0x18003ec68  lea     r8, aOnecoreBaseFli_34; "onecore\\base\\flighting\\onesettings\\"...
0x18003ec6f  lea     edx, [rax+4Ah]; void *
0x18003ec72  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18003ec78  mov     rcx, rbx; hFile
0x18003ec7b  call    cs:__imp_FlushFileBuffers
0x18003ec81  mov     rcx, [rbp+5Fh]; this
0x18003ec85  test    eax, eax
0x18003ec87  jnz     short loc_18003EC99
0x18003ec89  lea     r8, aOnecoreBaseFli_34; "onecore\\base\\flighting\\onesettings\\"...
0x18003ec90  lea     edx, [rax+4Ch]; void *
0x18003ec93  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18003ec99  lea     rcx, [rbp+57h+NumberOfBytesRead]
0x18003ec9d  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18003eca2  lea     rcx, [rbp+57h+var_38]
0x18003eca6  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18003ecab  mov     rcx, rax; lpFileName
0x18003ecae  mov     [rsp+0D0h+hTemplateFile], 0; hTemplateFile
0x18003ecb7  mov     [rsp+0D0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18003ecbf  mov     [rsp+0D0h+dwCreationDisposition], 3; dwCreationDisposition
0x18003ecc7  xor     r9d, r9d; lpSecurityAttributes
0x18003ecca  xor     r8d, r8d; dwShareMode
0x18003eccd  mov     edx, 120089h; dwDesiredAccess
0x18003ecd2  call    cs:__imp_CreateFileW
0x18003ecd8  mov     rbx, rax
0x18003ecdb  mov     [rbp+57h+var_88], rax
0x18003ecdf  mov     edx, edi
0x18003ece1  lea     rcx, [rbp+57h+lpBuffer]
0x18003ece5  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@_KAEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(unsigned __int64,std::allocator<uchar> const &)
0x18003ecea  nop
0x18003eceb  mov     [rbp+57h+NumberOfBytesRead], 0
0x18003ecf2  mov     qword ptr [rsp+0D0h+dwCreationDisposition], 0; int
0x18003ecfb  lea     r9, [rbp+57h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18003ecff  mov     r8d, edi; nNumberOfBytesToRead
0x18003ed02  mov     rdx, [rbp+57h+lpBuffer]; lpBuffer
0x18003ed06  mov     rcx, rbx; hFile
0x18003ed09  call    cs:__imp_ReadFile
0x18003ed0f  mov     rcx, [rbp+5Fh]; this
0x18003ed13  test    eax, eax
0x18003ed15  jnz     short loc_18003ED27
0x18003ed17  lea     r8, aOnecoreBaseFli_34; "onecore\\base\\flighting\\onesettings\\"...
0x18003ed1e  lea     edx, [rax+5Dh]; void *
0x18003ed21  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18003ed27  mov     edx, 20h ; ' '
0x18003ed2c  lea     rcx, [rbp+57h+var_68]
0x18003ed30  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@_KAEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(unsigned __int64,std::allocator<uchar> const &)
0x18003ed35  nop
0x18003ed36  mov     r8, [rbp+57h+var_68]; BYTE *
0x18003ed3a  mov     r9d, [rbp+57h+var_60]
0x18003ed3e  sub     r9d, r8d; unsigned int
0x18003ed41  mov     edx, [rbp+57h+NumberOfBytesRead]; dwDataLen
0x18003ed44  mov     rcx, [rbp+57h+lpBuffer]; pbData
0x18003ed48  call    ?GetSha256Hash@EncryptionHelper@@SAJPEBEKPEAEK@Z; EncryptionHelper::GetSha256Hash(uchar const *,ulong,uchar *,ulong)
0x18003ed4d  mov     rcx, [rbp+5Fh]; this
0x18003ed51  test    eax, eax
0x18003ed53  jns     short loc_18003ED6A
0x18003ed55  mov     r9d, eax; char *
0x18003ed58  lea     r8, aOnecoreBaseFli_34; "onecore\\base\\flighting\\onesettings\\"...
0x18003ed5f  mov     edx, 62h ; 'b'; void *
0x18003ed64  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003ed6a  mov     r8, [rbp+57h+var_68]
0x18003ed6e  mov     rdx, [rbp+57h+var_78]
0x18003ed72  mov     rcx, [rbp+57h+var_80]
0x18003ed76  call    ??$equal@V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@E@std@@@std@@@std@@V12@U?$equal_to@X@2@@std@@YA_NV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@E@std@@@std@@@0@00U?$equal_to@X@0@@Z; std::equal<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<uchar>>>,std::_Vector_iterator<std::_Vector_val<std::_Simple_types<uchar>>>,std::equal_to<void>>(std::_Vector_iterator<std::_Vector_val<std::_Simple_types<uchar>>>,std::_Vector_iterator<std::_Vector_val<std::_Simple_types<uchar>>>,std::_Vector_iterator<std::_Vector_val<std::_Simple_types<uchar>>>,std::equal_to<void>)
0x18003ed7b  mov     rcx, [rbp+5Fh]; this
0x18003ed7f  test    al, al
0x18003ed81  jnz     short loc_18003ED9B
0x18003ed83  mov     r9d, 80070570h; char *
0x18003ed89  lea     r8, aOnecoreBaseFli_34; "onecore\\base\\flighting\\onesettings\\"...
0x18003ed90  mov     edx, 65h ; 'e'; void *
0x18003ed95  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003ed9b  lea     rcx, [rbp+57h+var_68]
0x18003ed9f  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18003eda4  nop
0x18003eda5  lea     rcx, [rbp+57h+lpBuffer]
0x18003eda9  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18003edae  nop
0x18003edaf  lea     rcx, [rbp+57h+var_88]
0x18003edb3  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18003edb8  lea     rcx, [rbp+57h+var_38]
0x18003edbc  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18003edc1  mov     rcx, rax; lpExistingFileName
0x18003edc4  mov     r8d, 1; dwFlags
0x18003edca  mov     rdx, r14; lpNewFileName
0x18003edcd  call    cs:__imp_MoveFileExW
0x18003edd3  mov     rcx, [rbp+5Fh]; this
0x18003edd7  test    eax, eax
0x18003edd9  jnz     short loc_18003EDEB
0x18003eddb  lea     r8, aOnecoreBaseFli_34; "onecore\\base\\flighting\\onesettings\\"...
0x18003ede2  lea     edx, [rax+69h]; void *
0x18003ede5  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18003edeb  lea     rcx, [rbp+57h+var_80]
0x18003edef  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18003edf4  nop
0x18003edf5  lea     rcx, [rbp+57h+var_38]
0x18003edf9  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003edfe  mov     rcx, [rbp+57h+var_18]
0x18003ee02  xor     rcx, rsp; StackCookie
0x18003ee05  call    __security_check_cookie
0x18003ee0a  lea     r11, [rsp+0D0h+var_10]
0x18003ee12  mov     rbx, [r11+30h]
0x18003ee16  mov     rsi, [r11+38h]
0x18003ee1a  mov     rsp, r11
0x18003ee1d  pop     r14
0x18003ee1f  pop     rdi
0x18003ee20  pop     rbp
0x18003ee21  retn
```
