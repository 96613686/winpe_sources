# UtilDeleteFilePath(wchar_t const *)

- ea: `0x14000b0d8`
- end: `0x14000b27a`
- name: `?UtilDeleteFilePath@@YAJPEB_W@Z`
- size: `418`
- prototype: `__int64 __fastcall(const wchar_t *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x14000be08`

## callees

- `0x140001270`
- `0x14000b0d8`
- `0x14000c798`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000b124`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000b1f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000b124`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000b1f1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000b267`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000b267`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x14000b1e7`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x14000b1e7`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x14000b10d`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x14000b10d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall UtilDeleteFilePath(WCHAR *a1)
{
  HANDLE FileW; // rax
  int v3; // r8d
  int v4; // r9d
  void *v5; // rsi
  unsigned __int64 v6; // r14
  signed int v7; // eax
  int v8; // r8d
  int v9; // r9d
  int v10; // ebx
  int v11; // ecx
  void *v12; // rdx
  signed int LastError; // eax
  char FileInformation; // [rsp+78h] [rbp+38h] BYREF
  HANDLE v16; // [rsp+80h] [rbp+40h] BYREF
  WCHAR *v17; // [rsp+88h] [rbp+48h] BYREF

  FileW = CreateFileW(a1, 0x10000u, 3u, 0, 3u, 0x2200080u, 0);
  v5 = FileW;
  v16 = FileW;
  v6 = (unsigned __int64)FileW + 1;
  if ( (unsigned __int64)FileW + 1 > 1 )
  {
    v10 = UtilVerifyFilePath(a1, FileW, v3, v4);
    if ( v10 >= 0 )
    {
      FileInformation = 1;
      if ( !SetFileInformationByHandle(v5, FileDispositionInfo, &FileInformation, 1u) )
      {
        LastError = GetLastError();
        v10 = LastError;
        if ( LastError > 0 )
          v10 = (unsigned __int16)LastError | 0x80070000;
        if ( v10 >= 0 )
          v10 = -2147467259;
        if ( (unsigned int)dword_14002C000 > 2 )
        {
          v11 = qword_14002C018;
          if ( (qword_14002C010 & 8) != 0 && (qword_14002C018 & 8) == qword_14002C018 )
          {
            v12 = &unk_140026627;
            goto LABEL_24;
          }
        }
      }
    }
    else if ( (unsigned int)dword_14002C000 > 2 )
    {
      v11 = qword_14002C010;
      if ( (qword_14002C010 & 8) != 0 && (qword_14002C018 & 8) == qword_14002C018 )
      {
        v12 = &unk_14002666A;
        goto LABEL_24;
      }
    }
  }
  else
  {
    v7 = GetLastError();
    v10 = v7;
    if ( v7 > 0 )
      v10 = (unsigned __int16)v7 | 0x80070000;
    if ( v10 >= 0 )
      v10 = -2147467259;
    if ( (unsigned int)dword_14002C000 > 2 )
    {
      v11 = qword_14002C018;
      if ( (qword_14002C010 & 8) != 0 && (qword_14002C018 & 8) == qword_14002C018 )
      {
        v12 = &unk_1400266A5;
LABEL_24:
        LODWORD(v16) = v10;
        v17 = a1;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(
          v11,
          (_DWORD)v12,
          v8,
          v9,
          (__int64)&v17,
          (__int64)&v16);
      }
    }
  }
  if ( v6 > 1 )
    CloseHandle(v5);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x14000b0d8  push    rbp
0x14000b0da  push    rbx
0x14000b0db  push    rsi
0x14000b0dc  push    rdi
0x14000b0dd  push    r14
0x14000b0df  mov     rbp, rsp
0x14000b0e2  sub     rsp, 40h
0x14000b0e6  mov     rdi, rcx
0x14000b0e9  mov     [rsp+40h+hTemplateFile], 0; hTemplateFile
0x14000b0f2  mov     [rsp+40h+dwFlagsAndAttributes], 2200080h; dwFlagsAndAttributes
0x14000b0fa  mov     r8d, 3; dwShareMode
0x14000b100  mov     [rsp+40h+dwCreationDisposition], r8d; dwCreationDisposition
0x14000b105  xor     r9d, r9d; lpSecurityAttributes
0x14000b108  mov     edx, 10000h; dwDesiredAccess
0x14000b10d  call    cs:__imp_CreateFileW
0x14000b113  mov     rsi, rax
0x14000b116  mov     [rbp+arg_10], rax
0x14000b11a  lea     r14, [rax+1]
0x14000b11e  cmp     r14, 1
0x14000b122  ja      short loc_14000B183
0x14000b124  call    cs:__imp_GetLastError
0x14000b12a  mov     ebx, eax
0x14000b12c  test    eax, eax
0x14000b12e  jle     short loc_14000B139
0x14000b130  movzx   ebx, ax
0x14000b133  or      ebx, 80070000h
0x14000b139  mov     eax, 80004005h
0x14000b13e  test    ebx, ebx
0x14000b140  cmovns  ebx, eax
0x14000b143  mov     eax, cs:dword_14002C000
0x14000b149  cmp     eax, 2
0x14000b14c  jbe     loc_14000B25E
0x14000b152  mov     rcx, cs:qword_14002C018
0x14000b159  mov     rax, cs:qword_14002C010
0x14000b160  test    al, 8
0x14000b162  jz      loc_14000B25E
0x14000b168  mov     rax, rcx
0x14000b16b  and     eax, 8
0x14000b16e  cmp     rax, rcx
0x14000b171  jnz     loc_14000B25E
0x14000b177  lea     rdx, unk_1400266A5
0x14000b17e  jmp     loc_14000B23F
0x14000b183  mov     rdx, rsi; void *
0x14000b186  mov     rcx, rdi; wchar_t *
0x14000b189  call    ?UtilVerifyFilePath@@YAJPEB_WPEAX@Z; UtilVerifyFilePath(wchar_t const *,void *)
0x14000b18e  mov     ebx, eax
0x14000b190  test    eax, eax
0x14000b192  jns     short loc_14000B1D2
0x14000b194  mov     ecx, cs:dword_14002C000
0x14000b19a  cmp     ecx, 2
0x14000b19d  jbe     loc_14000B25E
0x14000b1a3  mov     rdx, cs:qword_14002C018
0x14000b1aa  mov     rcx, cs:qword_14002C010
0x14000b1b1  test    cl, 8
0x14000b1b4  jz      loc_14000B25E
0x14000b1ba  mov     rax, rdx
0x14000b1bd  and     eax, 8
0x14000b1c0  cmp     rax, rdx
0x14000b1c3  jnz     loc_14000B25E
0x14000b1c9  lea     rdx, unk_14002666A
0x14000b1d0  jmp     short loc_14000B23F
0x14000b1d2  mov     [rbp+FileInformation], 1
0x14000b1d6  mov     r9d, 1; dwBufferSize
0x14000b1dc  lea     r8, [rbp+FileInformation]; lpFileInformation
0x14000b1e0  lea     edx, [r9+3]; FileInformationClass
0x14000b1e4  mov     rcx, rsi; hFile
0x14000b1e7  call    cs:__imp_SetFileInformationByHandle
0x14000b1ed  test    eax, eax
0x14000b1ef  jnz     short loc_14000B25E
0x14000b1f1  call    cs:__imp_GetLastError
0x14000b1f7  mov     ebx, eax
0x14000b1f9  test    eax, eax
0x14000b1fb  jle     short loc_14000B206
0x14000b1fd  movzx   ebx, ax
0x14000b200  or      ebx, 80070000h
0x14000b206  mov     eax, 80004005h
0x14000b20b  test    ebx, ebx
0x14000b20d  cmovns  ebx, eax
0x14000b210  mov     eax, cs:dword_14002C000
0x14000b216  cmp     eax, 2
0x14000b219  jbe     short loc_14000B25E
0x14000b21b  mov     rcx, cs:qword_14002C018
0x14000b222  mov     rax, cs:qword_14002C010
0x14000b229  test    al, 8
0x14000b22b  jz      short loc_14000B25E
0x14000b22d  mov     rax, rcx
0x14000b230  and     eax, 8
0x14000b233  cmp     rax, rcx
0x14000b236  jnz     short loc_14000B25E
0x14000b238  lea     rdx, unk_140026627
0x14000b23f  lea     rax, [rbp+arg_10]
0x14000b243  mov     qword ptr [rsp+40h+dwFlagsAndAttributes], rax
0x14000b248  lea     rax, [rbp+arg_18]
0x14000b24c  mov     qword ptr [rsp+40h+dwCreationDisposition], rax
0x14000b251  mov     dword ptr [rbp+arg_10], ebx
0x14000b254  mov     [rbp+arg_18], rdi
0x14000b258  call    ??$Write@U?$_tlgWrapSz@_W@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &)
0x14000b25d  nop
0x14000b25e  cmp     r14, 1
0x14000b262  jbe     short loc_14000B26D
0x14000b264  mov     rcx, rsi; hObject
0x14000b267  call    cs:__imp_CloseHandle
0x14000b26d  mov     eax, ebx
0x14000b26f  add     rsp, 40h
0x14000b273  pop     r14
0x14000b275  pop     rdi
0x14000b276  pop     rsi
0x14000b277  pop     rbx
0x14000b278  pop     rbp
0x14000b279  retn
```
