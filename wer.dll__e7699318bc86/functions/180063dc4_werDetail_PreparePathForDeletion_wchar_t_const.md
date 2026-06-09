# _werDetail::PreparePathForDeletion(wchar_t const *)

- ea: `0x180063dc4`
- end: `0x180063eed`
- name: `?PreparePathForDeletion@_werDetail@@YAJPEB_W@Z`
- size: `297`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, const wchar_t *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x18001abd8`

## callees

- `0x18000716c`
- `0x180023dc4`
- `0x180023e8c`
- `0x1800303dc`
- `0x180063dc4`
- `0x18006498c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180063e36`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180063e88`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180063e36`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180063e88`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180063e7e`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180063e7e`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180063e2b`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180063e2b`

## pseudocode

```c
__int64 __fastcall _werDetail::PreparePathForDeletion(WCHAR *lpFileName, const wchar_t *a2)
{
  unsigned int v3; // ebx
  __int64 v4; // rcx
  __int64 v5; // r8
  __int64 v6; // r9
  DWORD FileAttributesW; // eax
  DWORD LastError; // eax
  __int64 v9; // rcx
  __int64 v10; // r8
  __int64 v11; // r9
  unsigned __int8 *v12; // rdx
  DWORD v13; // eax
  unsigned int v15; // [rsp+48h] [rbp+10h] BYREF
  WCHAR *v16; // [rsp+50h] [rbp+18h] BYREF

  v3 = UtilAddAccessToPath(lpFileName, 0x10140u);
  if ( (v3 & 0x80000000) == 0 )
  {
    FileAttributesW = GetFileAttributesW(lpFileName);
    if ( FileAttributesW == -1 )
    {
      LastError = GetLastError();
      v3 = ERROR_HR_FROM_WIN32(LastError);
      if ( (unsigned int)dword_1800D9000 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_1800D9000, 8) )
        return v3;
      v12 = (unsigned __int8 *)&unk_1800C7910;
    }
    else
    {
      if ( (FileAttributesW & 1) == 0 )
        return v3;
      if ( SetFileAttributesW(lpFileName, FileAttributesW & 0xFFFFFFFE) )
        return v3;
      v13 = GetLastError();
      v3 = ERROR_HR_FROM_WIN32(v13);
      if ( (unsigned int)dword_1800D9000 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_1800D9000, 8) )
        return v3;
      v12 = (unsigned __int8 *)byte_1800C7953;
    }
    v15 = v3;
    v16 = lpFileName;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(
      v9,
      v12,
      v10,
      v11,
      (const size_t **)&v16,
      (__int64)&v15);
    return v3;
  }
  if ( (unsigned int)dword_1800D9000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1800D9000, 8) )
  {
    v15 = v3;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      v4,
      (unsigned __int8 *)byte_1800C78DB,
      v5,
      v6,
      (__int64)&v15);
  }
  return v3;
}

```

## disassembly

```asm
0x180063dc4  mov     [rsp+arg_0], rbx
0x180063dc9  push    rdi
0x180063dca  sub     rsp, 30h
0x180063dce  mov     edx, 10140h; unsigned int
0x180063dd3  mov     rdi, rcx
0x180063dd6  call    ?UtilAddAccessToPath@@YAJPEB_WK@Z; UtilAddAccessToPath(wchar_t const *,ulong)
0x180063ddb  mov     ebx, eax
0x180063ddd  test    eax, eax
0x180063ddf  jns     short loc_180063E28
0x180063de1  mov     ecx, cs:dword_1800D9000
0x180063de7  cmp     ecx, 2
0x180063dea  jbe     loc_180063EE0
0x180063df0  mov     edx, 8
0x180063df5  lea     rcx, dword_1800D9000
0x180063dfc  call    _tlgKeywordOn
0x180063e01  test    al, al
0x180063e03  jz      loc_180063EE0
0x180063e09  lea     rax, [rsp+38h+arg_8]
0x180063e0e  mov     [rsp+38h+arg_8], ebx
0x180063e12  lea     rdx, byte_1800C78DB
0x180063e19  mov     [rsp+38h+var_18], rax
0x180063e1e  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180063e23  jmp     loc_180063EE0
0x180063e28  mov     rcx, rdi; lpFileName
0x180063e2b  call    cs:__imp_GetFileAttributesW
0x180063e31  cmp     eax, 0FFFFFFFFh
0x180063e34  jnz     short loc_180063E72
0x180063e36  call    cs:__imp_GetLastError
0x180063e3c  mov     ecx, eax; unsigned int
0x180063e3e  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x180063e43  mov     ebx, eax
0x180063e45  mov     eax, cs:dword_1800D9000
0x180063e4b  cmp     eax, 2
0x180063e4e  jbe     loc_180063EE0
0x180063e54  mov     edx, 8
0x180063e59  lea     rcx, dword_1800D9000
0x180063e60  call    _tlgKeywordOn
0x180063e65  test    al, al
0x180063e67  jz      short loc_180063EE0
0x180063e69  lea     rdx, unk_1800C7910
0x180063e70  jmp     short loc_180063EBE
0x180063e72  test    al, 1
0x180063e74  jz      short loc_180063EE0
0x180063e76  and     eax, 0FFFFFFFEh
0x180063e79  mov     rcx, rdi; lpFileName
0x180063e7c  mov     edx, eax; dwFileAttributes
0x180063e7e  call    cs:__imp_SetFileAttributesW
0x180063e84  test    eax, eax
0x180063e86  jnz     short loc_180063EE0
0x180063e88  call    cs:__imp_GetLastError
0x180063e8e  mov     ecx, eax; unsigned int
0x180063e90  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x180063e95  mov     ebx, eax
0x180063e97  mov     eax, cs:dword_1800D9000
0x180063e9d  cmp     eax, 2
0x180063ea0  jbe     short loc_180063EE0
0x180063ea2  mov     edx, 8
0x180063ea7  lea     rcx, dword_1800D9000
0x180063eae  call    _tlgKeywordOn
0x180063eb3  test    al, al
0x180063eb5  jz      short loc_180063EE0
0x180063eb7  lea     rdx, byte_1800C7953
0x180063ebe  lea     rax, [rsp+38h+arg_8]
0x180063ec3  mov     [rsp+38h+var_10], rax
0x180063ec8  lea     rax, [rsp+38h+arg_10]
0x180063ecd  mov     [rsp+38h+var_18], rax
0x180063ed2  mov     [rsp+38h+arg_8], ebx
0x180063ed6  mov     [rsp+38h+arg_10], rdi
0x180063edb  call    ??$Write@U?$_tlgWrapSz@_W@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &)
0x180063ee0  mov     eax, ebx
0x180063ee2  mov     rbx, [rsp+38h+arg_0]
0x180063ee7  add     rsp, 30h
0x180063eeb  pop     rdi
0x180063eec  retn
```
