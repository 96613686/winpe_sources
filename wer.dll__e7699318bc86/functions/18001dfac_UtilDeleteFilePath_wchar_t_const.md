# UtilDeleteFilePath(wchar_t const *)

- ea: `0x18001dfac`
- end: `0x18001e116`
- name: `?UtilDeleteFilePath@@YAJPEB_W@Z`
- size: `362`
- prototype: `__int64 __fastcall(const wchar_t *)`
- caller_count: `11`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x18001abd8`
- `0x18001dad8`
- `0x18003b590`
- `0x180044598`
- `0x180049588`
- `0x18004a370`
- `0x180066710`
- `0x180076b00`
- `0x180079790`
- `0x18007f868`
- `0x18008d960`

## callees

- `0x18000716c`
- `0x1800072cc`
- `0x180007e10`
- `0x180007e34`
- `0x18001dfac`
- `0x180023e8c`
- `0x1800303dc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e009`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e0a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e009`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e0a9`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x18001e09f`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x18001e09f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001dfe9`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001dfe9`

## pseudocode

```c
__int64 __fastcall UtilDeleteFilePath(const wchar_t *a1)
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
  const wchar_t *v12; // [rsp+40h] [rbp-10h] BYREF
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
        if ( (unsigned int)dword_1800D9000 > 2 )
        {
          if ( (unsigned __int8)tlgKeywordOn(&dword_1800D9000, 8) )
          {
            v9 = byte_1800C7F21;
            goto LABEL_13;
          }
        }
      }
    }
    else if ( (unsigned int)dword_1800D9000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1800D9000, 8) )
    {
      v9 = (char *)&word_1800C7EE6;
      goto LABEL_13;
    }
  }
  else
  {
    v4 = GetLastError();
    v5 = ERROR_HR_FROM_WIN32(v4);
    if ( (unsigned int)dword_1800D9000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1800D9000, 8) )
    {
      v9 = &byte_1800C7EA7;
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
0x18001dfac  mov     rax, rsp
0x18001dfaf  mov     [rax+8], rbx
0x18001dfb3  push    rbp
0x18001dfb4  push    rsi
0x18001dfb5  push    rdi
0x18001dfb6  mov     rbp, rsp
0x18001dfb9  sub     rsp, 50h
0x18001dfbd  mov     rsi, rcx
0x18001dfc0  mov     [rbp+hFile], 0
0x18001dfc8  mov     qword ptr [rax-38h], 0
0x18001dfd0  mov     dword ptr [rax-40h], 2200080h
0x18001dfd7  mov     r8d, 3; dwShareMode
0x18001dfdd  mov     [rax-48h], r8d
0x18001dfe1  xor     r9d, r9d; lpSecurityAttributes
0x18001dfe4  mov     edx, 10000h; dwDesiredAccess
0x18001dfe9  call    cs:__imp_CreateFileW
0x18001dfef  mov     rdx, rax
0x18001dff2  lea     rcx, [rbp+hFile]
0x18001dff6  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x18001dffb  mov     rbx, [rbp+hFile]
0x18001dfff  lea     rax, [rbx+1]
0x18001e003  cmp     rax, 1
0x18001e007  ja      short loc_18001E04C
0x18001e009  call    cs:__imp_GetLastError
0x18001e00f  mov     ecx, eax; unsigned int
0x18001e011  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x18001e016  mov     edi, eax
0x18001e018  mov     eax, cs:dword_1800D9000
0x18001e01e  cmp     eax, 2
0x18001e021  jbe     loc_18001E0FE
0x18001e027  mov     edx, 8
0x18001e02c  lea     rcx, dword_1800D9000
0x18001e033  call    _tlgKeywordOn
0x18001e038  test    al, al
0x18001e03a  jz      loc_18001E0FE
0x18001e040  lea     rdx, byte_1800C7EA7
0x18001e047  jmp     loc_18001E0DF
0x18001e04c  mov     rdx, rbx; void *
0x18001e04f  mov     rcx, rsi; wchar_t *
0x18001e052  call    ?UtilVerifyFilePath@@YAJPEB_WPEAX@Z; UtilVerifyFilePath(wchar_t const *,void *)
0x18001e057  mov     edi, eax
0x18001e059  test    eax, eax
0x18001e05b  jns     short loc_18001E08A
0x18001e05d  mov     ecx, cs:dword_1800D9000
0x18001e063  cmp     ecx, 2
0x18001e066  jbe     loc_18001E0FE
0x18001e06c  mov     edx, 8
0x18001e071  lea     rcx, dword_1800D9000
0x18001e078  call    _tlgKeywordOn
0x18001e07d  test    al, al
0x18001e07f  jz      short loc_18001E0FE
0x18001e081  lea     rdx, word_1800C7EE6
0x18001e088  jmp     short loc_18001E0DF
0x18001e08a  mov     [rbp+FileInformation], 1
0x18001e08e  mov     r9d, 1; dwBufferSize
0x18001e094  lea     r8, [rbp+FileInformation]; lpFileInformation
0x18001e098  lea     edx, [r9+3]; FileInformationClass
0x18001e09c  mov     rcx, rbx; hFile
0x18001e09f  call    cs:__imp_SetFileInformationByHandle
0x18001e0a5  test    eax, eax
0x18001e0a7  jnz     short loc_18001E0FE
0x18001e0a9  call    cs:__imp_GetLastError
0x18001e0af  mov     ecx, eax; unsigned int
0x18001e0b1  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x18001e0b6  mov     edi, eax
0x18001e0b8  mov     eax, cs:dword_1800D9000
0x18001e0be  cmp     eax, 2
0x18001e0c1  jbe     short loc_18001E0FE
0x18001e0c3  mov     edx, 8
0x18001e0c8  lea     rcx, dword_1800D9000
0x18001e0cf  call    _tlgKeywordOn
0x18001e0d4  test    al, al
0x18001e0d6  jz      short loc_18001E0FE
0x18001e0d8  lea     rdx, byte_1800C7F21
0x18001e0df  lea     rax, [rbp+arg_10]
0x18001e0e3  mov     [rsp+50h+var_28], rax
0x18001e0e8  lea     rax, [rbp+var_10]
0x18001e0ec  mov     [rsp+50h+var_30], rax
0x18001e0f1  mov     [rbp+arg_10], edi
0x18001e0f4  mov     [rbp+var_10], rsi
0x18001e0f8  call    ??$Write@U?$_tlgWrapSz@_W@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &)
0x18001e0fd  nop
0x18001e0fe  lea     rcx, [rbp+hFile]
0x18001e102  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x18001e107  mov     eax, edi
0x18001e109  mov     rbx, [rsp+50h+arg_0]
0x18001e10e  add     rsp, 50h
0x18001e112  pop     rdi
0x18001e113  pop     rsi
0x18001e114  pop     rbp
0x18001e115  retn
```
