# _werDetail::PreparePathForDeletion(wchar_t const *)

- ea: `0x180066ba8`
- end: `0x180066cee`
- name: `?PreparePathForDeletion@_werDetail@@YAJPEB_W@Z`
- size: `326`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, const wchar_t *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x1800062bc`

## callees

- `0x18001c368`
- `0x1800235c8`
- `0x180023d28`
- `0x180031cd0`
- `0x180066ba8`
- `0x1800678d4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180066c20`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180066c82`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180066c20`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180066c82`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180066c72`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180066c72`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180066c0f`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180066c0f`

## pseudocode

```c
__int64 __fastcall _werDetail::PreparePathForDeletion(LPCWSTR lpFileName, const wchar_t *a2)
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
  const size_t *v16; // [rsp+50h] [rbp+18h] BYREF

  v3 = UtilAddAccessToPath(lpFileName, 0x10140u);
  if ( (v3 & 0x80000000) == 0 )
  {
    FileAttributesW = GetFileAttributesW(lpFileName);
    if ( FileAttributesW == -1 )
    {
      LastError = GetLastError();
      v3 = ERROR_HR_FROM_WIN32(LastError);
      if ( (unsigned int)dword_1800DE000 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_1800DE000, 8) )
        return v3;
      v12 = (unsigned __int8 *)&unk_1800CC9C0;
    }
    else
    {
      if ( (FileAttributesW & 1) == 0 )
        return v3;
      if ( SetFileAttributesW(lpFileName, FileAttributesW & 0xFFFFFFFE) )
        return v3;
      v13 = GetLastError();
      v3 = ERROR_HR_FROM_WIN32(v13);
      if ( (unsigned int)dword_1800DE000 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_1800DE000, 8) )
        return v3;
      v12 = (unsigned __int8 *)byte_1800CCA03;
    }
    v15 = v3;
    v16 = (const size_t *)lpFileName;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(
      v9,
      v12,
      v10,
      v11,
      &v16,
      (__int64)&v15);
    return v3;
  }
  if ( (unsigned int)dword_1800DE000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1800DE000, 8) )
  {
    v15 = v3;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      v4,
      (unsigned __int8 *)byte_1800CC98B,
      v5,
      v6,
      (__int64)&v15);
  }
  return v3;
}

```

## disassembly

```asm
0x180066ba8  mov     [rsp+arg_0], rbx
0x180066bad  push    rdi
0x180066bae  sub     rsp, 30h
0x180066bb2  mov     edx, 10140h; unsigned int
0x180066bb7  mov     rdi, rcx
0x180066bba  call    ?UtilAddAccessToPath@@YAJPEB_WK@Z; UtilAddAccessToPath(wchar_t const *,ulong)
0x180066bbf  mov     ebx, eax
0x180066bc1  test    eax, eax
0x180066bc3  jns     short loc_180066C0C
0x180066bc5  mov     ecx, cs:dword_1800DE000
0x180066bcb  cmp     ecx, 2
0x180066bce  jbe     loc_180066CE0
0x180066bd4  mov     edx, 8
0x180066bd9  lea     rcx, dword_1800DE000
0x180066be0  call    _tlgKeywordOn
0x180066be5  test    al, al
0x180066be7  jz      loc_180066CE0
0x180066bed  lea     rax, [rsp+38h+arg_8]
0x180066bf2  mov     [rsp+38h+arg_8], ebx
0x180066bf6  lea     rdx, byte_1800CC98B
0x180066bfd  mov     [rsp+38h+var_18], rax
0x180066c02  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180066c07  jmp     loc_180066CE0
0x180066c0c  mov     rcx, rdi; lpFileName
0x180066c0f  call    cs:__imp_GetFileAttributesW
0x180066c16  nop     dword ptr [rax+rax+00h]
0x180066c1b  cmp     eax, 0FFFFFFFFh
0x180066c1e  jnz     short loc_180066C66
0x180066c20  call    cs:__imp_GetLastError
0x180066c27  nop     dword ptr [rax+rax+00h]
0x180066c2c  mov     ecx, eax; unsigned int
0x180066c2e  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x180066c33  mov     ebx, eax
0x180066c35  mov     eax, cs:dword_1800DE000
0x180066c3b  cmp     eax, 2
0x180066c3e  jbe     loc_180066CE0
0x180066c44  mov     edx, 8
0x180066c49  lea     rcx, dword_1800DE000
0x180066c50  call    _tlgKeywordOn
0x180066c55  test    al, al
0x180066c57  jz      loc_180066CE0
0x180066c5d  lea     rdx, unk_1800CC9C0
0x180066c64  jmp     short loc_180066CBE
0x180066c66  test    al, 1
0x180066c68  jz      short loc_180066CE0
0x180066c6a  and     eax, 0FFFFFFFEh
0x180066c6d  mov     rcx, rdi; lpFileName
0x180066c70  mov     edx, eax; dwFileAttributes
0x180066c72  call    cs:__imp_SetFileAttributesW
0x180066c79  nop     dword ptr [rax+rax+00h]
0x180066c7e  test    eax, eax
0x180066c80  jnz     short loc_180066CE0
0x180066c82  call    cs:__imp_GetLastError
0x180066c89  nop     dword ptr [rax+rax+00h]
0x180066c8e  mov     ecx, eax; unsigned int
0x180066c90  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x180066c95  mov     ebx, eax
0x180066c97  mov     eax, cs:dword_1800DE000
0x180066c9d  cmp     eax, 2
0x180066ca0  jbe     short loc_180066CE0
0x180066ca2  mov     edx, 8
0x180066ca7  lea     rcx, dword_1800DE000
0x180066cae  call    _tlgKeywordOn
0x180066cb3  test    al, al
0x180066cb5  jz      short loc_180066CE0
0x180066cb7  lea     rdx, byte_1800CCA03
0x180066cbe  lea     rax, [rsp+38h+arg_8]
0x180066cc3  mov     [rsp+38h+var_10], rax
0x180066cc8  lea     rax, [rsp+38h+arg_10]
0x180066ccd  mov     [rsp+38h+var_18], rax
0x180066cd2  mov     [rsp+38h+arg_8], ebx
0x180066cd6  mov     [rsp+38h+arg_10], rdi
0x180066cdb  call    ??$Write@U?$_tlgWrapSz@_W@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &)
0x180066ce0  mov     eax, ebx
0x180066ce2  mov     rbx, [rsp+38h+arg_0]
0x180066ce7  add     rsp, 30h
0x180066ceb  pop     rdi
0x180066cec  retn
```
