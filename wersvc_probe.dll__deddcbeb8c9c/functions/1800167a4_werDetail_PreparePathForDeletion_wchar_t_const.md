# _werDetail::PreparePathForDeletion(wchar_t const *)

- ea: `0x1800167a4`
- end: `0x180016960`
- name: `?PreparePathForDeletion@_werDetail@@YAJPEB_W@Z`
- size: `444`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, const wchar_t *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x18001bccc`

## callees

- `0x18000113c`
- `0x18000134c`
- `0x1800029d0`
- `0x1800167a4`
- `0x18001b3f8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001685f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800168d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001685f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800168d1`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180016854`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180016854`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1800168c7`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1800168c7`

## pseudocode

```c
__int64 __fastcall _werDetail::PreparePathForDeletion(LPCWSTR lpFileName, const wchar_t *a2)
{
  int v3; // ebx
  DWORD FileAttributesW; // eax
  signed int LastError; // eax
  int v6; // r8d
  int v7; // r9d
  int v8; // ecx
  void *v9; // rdx
  signed int v10; // eax
  int v12; // [rsp+30h] [rbp-50h] BYREF
  LPCWSTR v13; // [rsp+38h] [rbp-48h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v14; // [rsp+40h] [rbp-40h] BYREF
  int *v15; // [rsp+60h] [rbp-20h]
  __int64 v16; // [rsp+68h] [rbp-18h]

  v3 = UtilAddAccessToPath(lpFileName, (const struct std::nothrow_t *)0x10140);
  if ( v3 < 0 )
  {
    if ( (unsigned int)dword_180047000 > 2 && (qword_180047010 & 8) != 0 && (qword_180047018 & 8) == qword_180047018 )
    {
      v12 = v3;
      v15 = &v12;
      v16 = 4;
      tlgWriteTransfer_EventWriteTransfer((__int64)&dword_180047000, byte_18003F709, 0, 0, 3u, &v14);
    }
    return (unsigned int)v3;
  }
  FileAttributesW = GetFileAttributesW(lpFileName);
  if ( FileAttributesW == -1 )
  {
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError > 0 )
      v3 = (unsigned __int16)LastError | 0x80070000;
    if ( v3 >= 0 )
      v3 = -2147467259;
    if ( (unsigned int)dword_180047000 > 2 )
    {
      v8 = qword_180047018;
      if ( (qword_180047010 & 8) != 0 && (qword_180047018 & 8) == qword_180047018 )
      {
        v9 = &unk_18003F6C6;
LABEL_25:
        v12 = v3;
        v13 = lpFileName;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(
          v8,
          (_DWORD)v9,
          v6,
          v7,
          (__int64)&v13,
          (__int64)&v12);
      }
    }
  }
  else if ( (FileAttributesW & 1) != 0 && !SetFileAttributesW(lpFileName, FileAttributesW & 0xFFFFFFFE) )
  {
    v10 = GetLastError();
    v3 = v10;
    if ( v10 > 0 )
      v3 = (unsigned __int16)v10 | 0x80070000;
    if ( v3 >= 0 )
      v3 = -2147467259;
    if ( (unsigned int)dword_180047000 > 2 )
    {
      v8 = qword_180047018;
      if ( (qword_180047010 & 8) != 0 && (qword_180047018 & 8) == qword_180047018 )
      {
        v9 = &unk_18003F683;
        goto LABEL_25;
      }
    }
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800167a4  mov     [rsp-8+arg_8], rbx
0x1800167a9  mov     [rsp-8+arg_10], rdi
0x1800167ae  push    rbp
0x1800167af  mov     rbp, rsp
0x1800167b2  sub     rsp, 80h
0x1800167b9  mov     rax, cs:__security_cookie
0x1800167c0  xor     rax, rsp
0x1800167c3  mov     [rbp+var_10], rax
0x1800167c7  mov     edx, 10140h; unsigned int
0x1800167cc  mov     rdi, rcx
0x1800167cf  call    ?UtilAddAccessToPath@@YAJPEB_WK@Z; UtilAddAccessToPath(wchar_t const *,ulong)
0x1800167d4  mov     ebx, eax
0x1800167d6  test    eax, eax
0x1800167d8  jns     short loc_180016851
0x1800167da  mov     ecx, cs:dword_180047000
0x1800167e0  cmp     ecx, 2
0x1800167e3  jbe     loc_18001693D
0x1800167e9  mov     rdx, cs:qword_180047018
0x1800167f0  mov     rcx, cs:qword_180047010
0x1800167f7  test    cl, 8
0x1800167fa  jz      loc_18001693D
0x180016800  mov     rax, rdx
0x180016803  and     eax, 8
0x180016806  cmp     rax, rdx
0x180016809  jnz     loc_18001693D
0x18001680f  lea     rax, [rbp+var_50]
0x180016813  mov     [rbp+var_50], ebx
0x180016816  mov     [rbp+var_20], rax
0x18001681a  lea     rdx, byte_18003F709
0x180016821  lea     rax, [rbp+var_40]
0x180016825  mov     [rbp+var_18], 4
0x18001682d  mov     [rsp+80h+var_58], rax
0x180016832  lea     rcx, dword_180047000
0x180016839  xor     r9d, r9d
0x18001683c  mov     dword ptr [rsp+80h+var_60], 3
0x180016844  xor     r8d, r8d
0x180016847  call    _tlgWriteTransfer_EventWriteTransfer
0x18001684c  jmp     loc_18001693D
0x180016851  mov     rcx, rdi; lpFileName
0x180016854  call    cs:__imp_GetFileAttributesW
0x18001685a  cmp     eax, 0FFFFFFFFh
0x18001685d  jnz     short loc_1800168BB
0x18001685f  call    cs:__imp_GetLastError
0x180016865  mov     ebx, eax
0x180016867  test    eax, eax
0x180016869  jle     short loc_180016874
0x18001686b  movzx   ebx, ax
0x18001686e  or      ebx, 80070000h
0x180016874  test    ebx, ebx
0x180016876  mov     eax, 80004005h
0x18001687b  cmovns  ebx, eax
0x18001687e  mov     eax, cs:dword_180047000
0x180016884  cmp     eax, 2
0x180016887  jbe     loc_18001693D
0x18001688d  mov     rcx, cs:qword_180047018
0x180016894  mov     rax, cs:qword_180047010
0x18001689b  test    al, 8
0x18001689d  jz      loc_18001693D
0x1800168a3  mov     rax, rcx
0x1800168a6  and     eax, 8
0x1800168a9  cmp     rax, rcx
0x1800168ac  jnz     loc_18001693D
0x1800168b2  lea     rdx, unk_18003F6C6
0x1800168b9  jmp     short loc_18001691F
0x1800168bb  test    al, 1
0x1800168bd  jz      short loc_18001693D
0x1800168bf  and     eax, 0FFFFFFFEh
0x1800168c2  mov     rcx, rdi; lpFileName
0x1800168c5  mov     edx, eax; dwFileAttributes
0x1800168c7  call    cs:__imp_SetFileAttributesW
0x1800168cd  test    eax, eax
0x1800168cf  jnz     short loc_18001693D
0x1800168d1  call    cs:__imp_GetLastError
0x1800168d7  mov     ebx, eax
0x1800168d9  test    eax, eax
0x1800168db  jle     short loc_1800168E6
0x1800168dd  movzx   ebx, ax
0x1800168e0  or      ebx, 80070000h
0x1800168e6  test    ebx, ebx
0x1800168e8  mov     eax, 80004005h
0x1800168ed  cmovns  ebx, eax
0x1800168f0  mov     eax, cs:dword_180047000
0x1800168f6  cmp     eax, 2
0x1800168f9  jbe     short loc_18001693D
0x1800168fb  mov     rcx, cs:qword_180047018
0x180016902  mov     rax, cs:qword_180047010
0x180016909  test    al, 8
0x18001690b  jz      short loc_18001693D
0x18001690d  mov     rax, rcx
0x180016910  and     eax, 8
0x180016913  cmp     rax, rcx
0x180016916  jnz     short loc_18001693D
0x180016918  lea     rdx, unk_18003F683
0x18001691f  lea     rax, [rbp+var_50]
0x180016923  mov     [rsp+80h+var_58], rax
0x180016928  lea     rax, [rbp+var_48]
0x18001692c  mov     [rsp+80h+var_60], rax
0x180016931  mov     [rbp+var_50], ebx
0x180016934  mov     [rbp+var_48], rdi
0x180016938  call    ??$Write@U?$_tlgWrapSz@_W@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &)
0x18001693d  mov     eax, ebx
0x18001693f  mov     rcx, [rbp+var_10]
0x180016943  xor     rcx, rsp; StackCookie
0x180016946  call    __security_check_cookie
0x18001694b  lea     r11, [rsp+80h+var_s0]
0x180016953  mov     rbx, [r11+18h]
0x180016957  mov     rdi, [r11+20h]
0x18001695b  mov     rsp, r11
0x18001695e  pop     rbp
0x18001695f  retn
```
