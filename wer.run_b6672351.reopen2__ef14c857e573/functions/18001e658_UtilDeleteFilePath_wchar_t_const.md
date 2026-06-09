# UtilDeleteFilePath(wchar_t const *)

- ea: `0x18001e658`
- end: `0x18001e7df`
- name: `?UtilDeleteFilePath@@YAJPEB_W@Z`
- size: `391`
- prototype: `__int64 __fastcall(const wchar_t *)`
- caller_count: `11`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x1800062bc`
- `0x18001e134`
- `0x18003d4f0`
- `0x1800464c4`
- `0x18004b858`
- `0x18004c6a0`
- `0x1800697d0`
- `0x18007a000`
- `0x18007cd68`
- `0x180083350`
- `0x180091940`

## callees

- `0x180007fd8`
- `0x180008004`
- `0x18001c368`
- `0x18001e658`
- `0x180023d28`
- `0x18002a758`
- `0x180031cd0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e6bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e76b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e6bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e76b`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x18001e75b`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x18001e75b`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001e695`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001e695`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall UtilDeleteFilePath(WCHAR *a1)
{
  HANDLE FileW; // rax
  HANDLE v3; // rbx
  DWORD v4; // eax
  int v5; // edi
  int v6; // ecx
  int v7; // r8d
  int v8; // r9d
  char *v9; // rdx
  DWORD LastError; // eax
  WCHAR *v12; // [rsp+40h] [rbp-10h] BYREF
  char FileInformation; // [rsp+78h] [rbp+28h] BYREF
  int v14; // [rsp+80h] [rbp+30h] BYREF
  HANDLE hFile; // [rsp+88h] [rbp+38h] BYREF

  hFile = 0;
  FileW = CreateFileW(a1, 0x10000u, 3u, 0, 3u, 0x2200080u, 0);
  tlx::unique_any<tlx::file_handle_traits>::reset(&hFile, FileW);
  v3 = hFile;
  if ( (unsigned __int64)hFile + 1 > 1 )
  {
    v5 = UtilVerifyFilePath(a1, hFile);
    if ( v5 >= 0 )
    {
      FileInformation = 1;
      if ( !SetFileInformationByHandle(v3, FileDispositionInfo, &FileInformation, 1u) )
      {
        LastError = GetLastError();
        v5 = ERROR_HR_FROM_WIN32(LastError);
        if ( (unsigned int)dword_1800DE000 > 2 )
        {
          if ( (unsigned __int8)tlgKeywordOn(&dword_1800DE000, 8) )
          {
            v9 = byte_1800CCFD1;
            goto LABEL_13;
          }
        }
      }
    }
    else if ( (unsigned int)dword_1800DE000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1800DE000, 8) )
    {
      v9 = (char *)&word_1800CCF96;
      goto LABEL_13;
    }
  }
  else
  {
    v4 = GetLastError();
    v5 = ERROR_HR_FROM_WIN32(v4);
    if ( (unsigned int)dword_1800DE000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1800DE000, 8) )
    {
      v9 = &byte_1800CCF57;
LABEL_13:
      v14 = v5;
      v12 = a1;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(
        v6,
        (_DWORD)v9,
        v7,
        v8,
        (__int64)&v12,
        (__int64)&v14);
    }
  }
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&hFile);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18001e658  mov     rax, rsp
0x18001e65b  mov     [rax+8], rbx
0x18001e65f  push    rbp
0x18001e660  push    rsi
0x18001e661  push    rdi
0x18001e662  mov     rbp, rsp
0x18001e665  sub     rsp, 50h
0x18001e669  mov     rsi, rcx
0x18001e66c  mov     [rbp+hFile], 0
0x18001e674  mov     qword ptr [rax-38h], 0
0x18001e67c  mov     dword ptr [rax-40h], 2200080h
0x18001e683  mov     r8d, 3; dwShareMode
0x18001e689  mov     [rax-48h], r8d
0x18001e68d  xor     r9d, r9d; lpSecurityAttributes
0x18001e690  mov     edx, 10000h; dwDesiredAccess
0x18001e695  call    cs:__imp_CreateFileW
0x18001e69c  nop     dword ptr [rax+rax+00h]
0x18001e6a1  mov     rdx, rax
0x18001e6a4  lea     rcx, [rbp+hFile]
0x18001e6a8  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x18001e6ad  mov     rbx, [rbp+hFile]
0x18001e6b1  lea     rax, [rbx+1]
0x18001e6b5  cmp     rax, 1
0x18001e6b9  ja      short loc_18001E704
0x18001e6bb  call    cs:__imp_GetLastError
0x18001e6c2  nop     dword ptr [rax+rax+00h]
0x18001e6c7  mov     ecx, eax; unsigned int
0x18001e6c9  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x18001e6ce  mov     edi, eax
0x18001e6d0  mov     eax, cs:dword_1800DE000
0x18001e6d6  cmp     eax, 2
0x18001e6d9  jbe     loc_18001E7C6
0x18001e6df  mov     edx, 8
0x18001e6e4  lea     rcx, dword_1800DE000
0x18001e6eb  call    _tlgKeywordOn
0x18001e6f0  test    al, al
0x18001e6f2  jz      loc_18001E7C6
0x18001e6f8  lea     rdx, byte_1800CCF57
0x18001e6ff  jmp     loc_18001E7A7
0x18001e704  mov     rdx, rbx; void *
0x18001e707  mov     rcx, rsi; wchar_t *
0x18001e70a  call    ?UtilVerifyFilePath@@YAJPEB_WPEAX@Z; UtilVerifyFilePath(wchar_t const *,void *)
0x18001e70f  mov     edi, eax
0x18001e711  test    eax, eax
0x18001e713  jns     short loc_18001E746
0x18001e715  mov     ecx, cs:dword_1800DE000
0x18001e71b  cmp     ecx, 2
0x18001e71e  jbe     loc_18001E7C6
0x18001e724  mov     edx, 8
0x18001e729  lea     rcx, dword_1800DE000
0x18001e730  call    _tlgKeywordOn
0x18001e735  test    al, al
0x18001e737  jz      loc_18001E7C6
0x18001e73d  lea     rdx, word_1800CCF96
0x18001e744  jmp     short loc_18001E7A7
0x18001e746  mov     [rbp+FileInformation], 1
0x18001e74a  mov     r9d, 1; dwBufferSize
0x18001e750  lea     r8, [rbp+FileInformation]; lpFileInformation
0x18001e754  lea     edx, [r9+3]; FileInformationClass
0x18001e758  mov     rcx, rbx; hFile
0x18001e75b  call    cs:__imp_SetFileInformationByHandle
0x18001e762  nop     dword ptr [rax+rax+00h]
0x18001e767  test    eax, eax
0x18001e769  jnz     short loc_18001E7C6
0x18001e76b  call    cs:__imp_GetLastError
0x18001e772  nop     dword ptr [rax+rax+00h]
0x18001e777  mov     ecx, eax; unsigned int
0x18001e779  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x18001e77e  mov     edi, eax
0x18001e780  mov     eax, cs:dword_1800DE000
0x18001e786  cmp     eax, 2
0x18001e789  jbe     short loc_18001E7C6
0x18001e78b  mov     edx, 8
0x18001e790  lea     rcx, dword_1800DE000
0x18001e797  call    _tlgKeywordOn
0x18001e79c  test    al, al
0x18001e79e  jz      short loc_18001E7C6
0x18001e7a0  lea     rdx, byte_1800CCFD1
0x18001e7a7  lea     rax, [rbp+arg_10]
0x18001e7ab  mov     [rsp+50h+var_28], rax
0x18001e7b0  lea     rax, [rbp+var_10]
0x18001e7b4  mov     [rsp+50h+var_30], rax
0x18001e7b9  mov     [rbp+arg_10], edi
0x18001e7bc  mov     [rbp+var_10], rsi
0x18001e7c0  call    ??$Write@U?$_tlgWrapSz@_W@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &)
0x18001e7c5  nop
0x18001e7c6  lea     rcx, [rbp+hFile]
0x18001e7ca  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x18001e7cf  mov     eax, edi
0x18001e7d1  mov     rbx, [rsp+50h+arg_0]
0x18001e7d6  add     rsp, 50h
0x18001e7da  pop     rdi
0x18001e7db  pop     rsi
0x18001e7dc  pop     rbp
0x18001e7dd  retn
```
