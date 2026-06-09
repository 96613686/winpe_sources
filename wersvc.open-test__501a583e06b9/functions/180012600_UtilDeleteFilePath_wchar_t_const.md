# UtilDeleteFilePath(wchar_t const *)

- ea: `0x180012600`
- end: `0x1800127a2`
- name: `?UtilDeleteFilePath@@YAJPEB_W@Z`
- size: `418`
- prototype: `__int64 __fastcall(const wchar_t *)`
- caller_count: `4`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180018e90`
- `0x180019004`
- `0x18001bccc`
- `0x180032c40`

## callees

- `0x18000134c`
- `0x1800106f4`
- `0x180012600`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001264c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012719`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001264c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012719`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x18001270f`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x18001270f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180012635`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180012635`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001278f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001278f`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall UtilDeleteFilePath(const wchar_t *a1)
{
  HANDLE FileW; // rax
  void *v3; // rsi
  unsigned __int64 v4; // r14
  signed int v5; // eax
  int v6; // r8d
  int v7; // r9d
  signed int v8; // ebx
  int v9; // ecx
  __int16 *v10; // rdx
  signed int LastError; // eax
  char FileInformation; // [rsp+78h] [rbp+38h] BYREF
  HANDLE v14; // [rsp+80h] [rbp+40h] BYREF
  const wchar_t *v15; // [rsp+88h] [rbp+48h] BYREF

  FileW = CreateFileW(a1, 0x10000u, 3u, 0, 3u, 0x2200080u, 0);
  v3 = FileW;
  v14 = FileW;
  v4 = (unsigned __int64)FileW + 1;
  if ( (unsigned __int64)FileW + 1 > 1 )
  {
    v8 = UtilVerifyFilePath(a1, FileW);
    if ( v8 >= 0 )
    {
      FileInformation = 1;
      if ( !SetFileInformationByHandle(v3, FileDispositionInfo, &FileInformation, 1u) )
      {
        LastError = GetLastError();
        v8 = LastError;
        if ( LastError > 0 )
          v8 = (unsigned __int16)LastError | 0x80070000;
        if ( v8 >= 0 )
          v8 = -2147467259;
        if ( (unsigned int)dword_180047000 > 2 )
        {
          v9 = qword_180047018;
          if ( (qword_180047010 & 8) != 0 && (qword_180047018 & 8) == qword_180047018 )
          {
            v10 = (__int16 *)&unk_18003F1B0;
            goto LABEL_24;
          }
        }
      }
    }
    else if ( (unsigned int)dword_180047000 > 2 )
    {
      v9 = qword_180047010;
      if ( (qword_180047010 & 8) != 0 && (qword_180047018 & 8) == qword_180047018 )
      {
        v10 = (__int16 *)byte_18003F1F3;
        goto LABEL_24;
      }
    }
  }
  else
  {
    v5 = GetLastError();
    v8 = v5;
    if ( v5 > 0 )
      v8 = (unsigned __int16)v5 | 0x80070000;
    if ( v8 >= 0 )
      v8 = -2147467259;
    if ( (unsigned int)dword_180047000 > 2 )
    {
      v9 = qword_180047018;
      if ( (qword_180047010 & 8) != 0 && (qword_180047018 & 8) == qword_180047018 )
      {
        v10 = &word_18003F22E;
LABEL_24:
        LODWORD(v14) = v8;
        v15 = a1;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(
          v9,
          (_DWORD)v10,
          v6,
          v7,
          (__int64)&v15,
          (__int64)&v14);
      }
    }
  }
  if ( v4 > 1 )
    CloseHandle(v3);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180012600  push    rbp
0x180012602  push    rbx
0x180012603  push    rsi
0x180012604  push    rdi
0x180012605  push    r14
0x180012607  mov     rbp, rsp
0x18001260a  sub     rsp, 40h
0x18001260e  mov     rdi, rcx
0x180012611  mov     [rsp+40h+hTemplateFile], 0; hTemplateFile
0x18001261a  mov     [rsp+40h+dwFlagsAndAttributes], 2200080h; dwFlagsAndAttributes
0x180012622  mov     r8d, 3; dwShareMode
0x180012628  mov     [rsp+40h+dwCreationDisposition], r8d; dwCreationDisposition
0x18001262d  xor     r9d, r9d; lpSecurityAttributes
0x180012630  mov     edx, 10000h; dwDesiredAccess
0x180012635  call    cs:__imp_CreateFileW
0x18001263b  mov     rsi, rax
0x18001263e  mov     [rbp+arg_10], rax
0x180012642  lea     r14, [rax+1]
0x180012646  cmp     r14, 1
0x18001264a  ja      short loc_1800126AB
0x18001264c  call    cs:__imp_GetLastError
0x180012652  mov     ebx, eax
0x180012654  test    eax, eax
0x180012656  jle     short loc_180012661
0x180012658  movzx   ebx, ax
0x18001265b  or      ebx, 80070000h
0x180012661  mov     eax, 80004005h
0x180012666  test    ebx, ebx
0x180012668  cmovns  ebx, eax
0x18001266b  mov     eax, cs:dword_180047000
0x180012671  cmp     eax, 2
0x180012674  jbe     loc_180012786
0x18001267a  mov     rcx, cs:qword_180047018
0x180012681  mov     rax, cs:qword_180047010
0x180012688  test    al, 8
0x18001268a  jz      loc_180012786
0x180012690  mov     rax, rcx
0x180012693  and     eax, 8
0x180012696  cmp     rax, rcx
0x180012699  jnz     loc_180012786
0x18001269f  lea     rdx, word_18003F22E
0x1800126a6  jmp     loc_180012767
0x1800126ab  mov     rdx, rsi; void *
0x1800126ae  mov     rcx, rdi; wchar_t *
0x1800126b1  call    ?UtilVerifyFilePath@@YAJPEB_WPEAX@Z; UtilVerifyFilePath(wchar_t const *,void *)
0x1800126b6  mov     ebx, eax
0x1800126b8  test    eax, eax
0x1800126ba  jns     short loc_1800126FA
0x1800126bc  mov     ecx, cs:dword_180047000
0x1800126c2  cmp     ecx, 2
0x1800126c5  jbe     loc_180012786
0x1800126cb  mov     rdx, cs:qword_180047018
0x1800126d2  mov     rcx, cs:qword_180047010
0x1800126d9  test    cl, 8
0x1800126dc  jz      loc_180012786
0x1800126e2  mov     rax, rdx
0x1800126e5  and     eax, 8
0x1800126e8  cmp     rax, rdx
0x1800126eb  jnz     loc_180012786
0x1800126f1  lea     rdx, byte_18003F1F3
0x1800126f8  jmp     short loc_180012767
0x1800126fa  mov     [rbp+FileInformation], 1
0x1800126fe  mov     r9d, 1; dwBufferSize
0x180012704  lea     r8, [rbp+FileInformation]; lpFileInformation
0x180012708  lea     edx, [r9+3]; FileInformationClass
0x18001270c  mov     rcx, rsi; hFile
0x18001270f  call    cs:__imp_SetFileInformationByHandle
0x180012715  test    eax, eax
0x180012717  jnz     short loc_180012786
0x180012719  call    cs:__imp_GetLastError
0x18001271f  mov     ebx, eax
0x180012721  test    eax, eax
0x180012723  jle     short loc_18001272E
0x180012725  movzx   ebx, ax
0x180012728  or      ebx, 80070000h
0x18001272e  mov     eax, 80004005h
0x180012733  test    ebx, ebx
0x180012735  cmovns  ebx, eax
0x180012738  mov     eax, cs:dword_180047000
0x18001273e  cmp     eax, 2
0x180012741  jbe     short loc_180012786
0x180012743  mov     rcx, cs:qword_180047018
0x18001274a  mov     rax, cs:qword_180047010
0x180012751  test    al, 8
0x180012753  jz      short loc_180012786
0x180012755  mov     rax, rcx
0x180012758  and     eax, 8
0x18001275b  cmp     rax, rcx
0x18001275e  jnz     short loc_180012786
0x180012760  lea     rdx, unk_18003F1B0
0x180012767  lea     rax, [rbp+arg_10]
0x18001276b  mov     qword ptr [rsp+40h+dwFlagsAndAttributes], rax
0x180012770  lea     rax, [rbp+arg_18]
0x180012774  mov     qword ptr [rsp+40h+dwCreationDisposition], rax
0x180012779  mov     dword ptr [rbp+arg_10], ebx
0x18001277c  mov     [rbp+arg_18], rdi
0x180012780  call    ??$Write@U?$_tlgWrapSz@_W@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &)
0x180012785  nop
0x180012786  cmp     r14, 1
0x18001278a  jbe     short loc_180012795
0x18001278c  mov     rcx, rsi; hObject
0x18001278f  call    cs:__imp_CloseHandle
0x180012795  mov     eax, ebx
0x180012797  add     rsp, 40h
0x18001279b  pop     r14
0x18001279d  pop     rdi
0x18001279e  pop     rsi
0x18001279f  pop     rbx
0x1800127a0  pop     rbp
0x1800127a1  retn
```
