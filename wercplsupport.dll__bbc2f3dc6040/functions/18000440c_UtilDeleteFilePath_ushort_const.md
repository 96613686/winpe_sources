# UtilDeleteFilePath(ushort const *)

- ea: `0x18000440c`
- end: `0x1800045c3`
- name: `?UtilDeleteFilePath@@YAJPEBG@Z`
- size: `439`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18000576c`

## callees

- `0x180001270`
- `0x18000440c`
- `0x180005e04`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x180004535`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x180004535`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180004441`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180004441`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004454`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000453f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004454`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000453f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800045ae`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800045ae`

## pseudocode

```c
__int64 __fastcall UtilDeleteFilePath(WCHAR *a1)
{
  HANDLE FileW; // rax
  int v3; // r8d
  int v4; // r9d
  void *v5; // rsi
  signed int v6; // eax
  int v7; // r8d
  int v8; // r9d
  int v9; // ebx
  int v10; // r8d
  int v11; // r9d
  int v12; // ecx
  __int16 *v13; // rdx
  signed int LastError; // eax
  char FileInformation; // [rsp+68h] [rbp+28h] BYREF
  int v17; // [rsp+70h] [rbp+30h] BYREF
  WCHAR *v18; // [rsp+78h] [rbp+38h] BYREF

  FileW = CreateFileW(a1, 0x10000u, 3u, 0, 3u, 0x2200080u, 0);
  v5 = FileW;
  if ( (unsigned __int64)FileW + 1 > 1 )
  {
    v9 = UtilVerifyFilePath(a1, FileW, v3, v4);
    if ( v9 >= 0 )
    {
      FileInformation = 1;
      if ( SetFileInformationByHandle(v5, FileDispositionInfo, &FileInformation, 1u) )
        goto LABEL_25;
      LastError = GetLastError();
      v9 = LastError;
      if ( LastError > 0 )
        v9 = (unsigned __int16)LastError | 0x80070000;
      if ( v9 >= 0 )
        v9 = -2147467259;
      if ( (unsigned int)dword_18001C008 <= 2 )
        goto LABEL_25;
      v12 = qword_18001C020;
      if ( (qword_18001C018 & 8) == 0 || (qword_18001C020 & 8) != qword_18001C020 )
        goto LABEL_25;
      v13 = &word_18001895E;
    }
    else
    {
      if ( (unsigned int)dword_18001C008 <= 2 )
        goto LABEL_25;
      v12 = qword_18001C018;
      if ( (qword_18001C018 & 8) == 0 || (qword_18001C020 & 8) != qword_18001C020 )
        goto LABEL_25;
      v13 = (__int16 *)byte_1800189A1;
    }
    v17 = v9;
    v18 = a1;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
      v12,
      (_DWORD)v13,
      v10,
      v11,
      (__int64)&v18,
      (__int64)&v17);
LABEL_25:
    CloseHandle(v5);
    return (unsigned int)v9;
  }
  v6 = GetLastError();
  v9 = v6;
  if ( v6 > 0 )
    v9 = (unsigned __int16)v6 | 0x80070000;
  if ( v9 >= 0 )
    v9 = -2147467259;
  if ( (unsigned int)dword_18001C008 > 2 && (qword_18001C018 & 8) != 0 && (qword_18001C020 & 8) == qword_18001C020 )
  {
    v17 = v9;
    v18 = a1;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
      qword_18001C020,
      (unsigned int)&dword_18001878C,
      v7,
      v8,
      (__int64)&v18,
      (__int64)&v17);
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18000440c  mov     rax, rsp
0x18000440f  mov     [rax+8], rbx
0x180004413  push    rbp
0x180004414  push    rsi
0x180004415  push    rdi
0x180004416  mov     rbp, rsp
0x180004419  sub     rsp, 40h
0x18000441d  mov     qword ptr [rax-28h], 0
0x180004425  mov     r8d, 3; dwShareMode
0x18000442b  mov     dword ptr [rax-30h], 2200080h
0x180004432  xor     r9d, r9d; lpSecurityAttributes
0x180004435  mov     edx, 10000h; dwDesiredAccess
0x18000443a  mov     [rax-38h], r8d
0x18000443e  mov     rdi, rcx
0x180004441  call    cs:__imp_CreateFileW
0x180004447  mov     rsi, rax
0x18000444a  lea     rdx, [rax+1]
0x18000444e  cmp     rdx, 1
0x180004452  ja      short loc_1800044D1
0x180004454  call    cs:__imp_GetLastError
0x18000445a  mov     ebx, eax
0x18000445c  test    eax, eax
0x18000445e  jle     short loc_180004469
0x180004460  movzx   ebx, ax
0x180004463  or      ebx, 80070000h
0x180004469  test    ebx, ebx
0x18000446b  mov     eax, 80004005h
0x180004470  cmovns  ebx, eax
0x180004473  mov     eax, cs:dword_18001C008
0x180004479  cmp     eax, 2
0x18000447c  jbe     loc_1800045B4
0x180004482  mov     rcx, cs:qword_18001C020
0x180004489  mov     rax, cs:qword_18001C018
0x180004490  test    al, 8
0x180004492  jz      loc_1800045B4
0x180004498  mov     rax, rcx
0x18000449b  and     eax, 8
0x18000449e  cmp     rax, rcx
0x1800044a1  jnz     loc_1800045B4
0x1800044a7  lea     rax, [rbp+arg_10]
0x1800044ab  mov     [rbp+arg_10], ebx
0x1800044ae  mov     [rsp+40h+var_18], rax
0x1800044b3  lea     rdx, dword_18001878C
0x1800044ba  lea     rax, [rbp+arg_18]
0x1800044be  mov     [rbp+arg_18], rdi
0x1800044c2  mov     [rsp+40h+var_20], rax
0x1800044c7  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x1800044cc  jmp     loc_1800045B4
0x1800044d1  mov     rdx, rsi; void *
0x1800044d4  mov     rcx, rdi; unsigned __int16 *
0x1800044d7  call    ?UtilVerifyFilePath@@YAJPEBGPEAX@Z; UtilVerifyFilePath(ushort const *,void *)
0x1800044dc  mov     ebx, eax
0x1800044de  test    eax, eax
0x1800044e0  jns     short loc_180004520
0x1800044e2  mov     ecx, cs:dword_18001C008
0x1800044e8  cmp     ecx, 2
0x1800044eb  jbe     loc_1800045AB
0x1800044f1  mov     rdx, cs:qword_18001C020
0x1800044f8  mov     rcx, cs:qword_18001C018
0x1800044ff  test    cl, 8
0x180004502  jz      loc_1800045AB
0x180004508  mov     rax, rdx
0x18000450b  and     eax, 8
0x18000450e  cmp     rax, rdx
0x180004511  jnz     loc_1800045AB
0x180004517  lea     rdx, byte_1800189A1
0x18000451e  jmp     short loc_18000458D
0x180004520  mov     r9d, 1; dwBufferSize
0x180004526  mov     [rbp+FileInformation], 1
0x18000452a  lea     r8, [rbp+FileInformation]; lpFileInformation
0x18000452e  mov     rcx, rsi; hFile
0x180004531  lea     edx, [r9+3]; FileInformationClass
0x180004535  call    cs:__imp_SetFileInformationByHandle
0x18000453b  test    eax, eax
0x18000453d  jnz     short loc_1800045AB
0x18000453f  call    cs:__imp_GetLastError
0x180004545  mov     ebx, eax
0x180004547  test    eax, eax
0x180004549  jle     short loc_180004554
0x18000454b  movzx   ebx, ax
0x18000454e  or      ebx, 80070000h
0x180004554  test    ebx, ebx
0x180004556  mov     eax, 80004005h
0x18000455b  cmovns  ebx, eax
0x18000455e  mov     eax, cs:dword_18001C008
0x180004564  cmp     eax, 2
0x180004567  jbe     short loc_1800045AB
0x180004569  mov     rcx, cs:qword_18001C020
0x180004570  mov     rax, cs:qword_18001C018
0x180004577  test    al, 8
0x180004579  jz      short loc_1800045AB
0x18000457b  mov     rax, rcx
0x18000457e  and     eax, 8
0x180004581  cmp     rax, rcx
0x180004584  jnz     short loc_1800045AB
0x180004586  lea     rdx, word_18001895E
0x18000458d  lea     rax, [rbp+arg_10]
0x180004591  mov     [rsp+40h+var_18], rax
0x180004596  lea     rax, [rbp+arg_18]
0x18000459a  mov     [rsp+40h+var_20], rax
0x18000459f  mov     [rbp+arg_10], ebx
0x1800045a2  mov     [rbp+arg_18], rdi
0x1800045a6  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x1800045ab  mov     rcx, rsi; hObject
0x1800045ae  call    cs:__imp_CloseHandle
0x1800045b4  mov     eax, ebx
0x1800045b6  mov     rbx, [rsp+40h+arg_0]
0x1800045bb  add     rsp, 40h
0x1800045bf  pop     rdi
0x1800045c0  pop     rsi
0x1800045c1  pop     rbp
0x1800045c2  retn
```
