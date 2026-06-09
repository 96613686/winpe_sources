# CEtwSession::FlushBuffered(wchar_t const *)

- ea: `0x180032c40`
- end: `0x180032e24`
- name: `?FlushBuffered@CEtwSession@@AEAAJPEB_W@Z`
- size: `484`
- prototype: `__int64 __fastcall(CEtwSession *this, wchar_t *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x180031d14`

## callees

- `0x1800029f4`
- `0x180004a44`
- `0x180006134`
- `0x1800101dc`
- `0x180012600`
- `0x180032c40`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032d1b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032da2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032d1b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032da2`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180032d0b`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180032d0b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180032d42`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180032ddc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180032d42`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180032ddc`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MoveFileW` at `0x180032d98`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MoveFileW` at `0x180032d98`
- `api-ms-win-eventing-controller-l1-1-0!ControlTraceW` at `0x180032d76`
- `api-ms-win-eventing-controller-l1-1-0!ControlTraceW` at `0x180032d76`

## pseudocode

```c
__int64 __fastcall CEtwSession::FlushBuffered(CEtwSession *this, wchar_t *a2)
{
  int v4; // ebx
  HANDLE FileW; // rax
  signed int LastError; // eax
  signed int v7; // eax
  LPCWSTR lpFileName[2]; // [rsp+40h] [rbp-9h] BYREF
  _WORD v10[8]; // [rsp+50h] [rbp+7h] BYREF
  LPCWSTR lpNewFileName[2]; // [rsp+60h] [rbp+17h] BYREF
  _WORD v12[24]; // [rsp+70h] [rbp+27h] BYREF
  HANDLE hObject; // [rsp+C0h] [rbp+77h] BYREF

  lpFileName[0] = v10;
  lpFileName[1] = v10;
  v10[0] = 0;
  lpNewFileName[0] = v12;
  lpNewFileName[1] = v12;
  v12[0] = 0;
  hObject = 0;
  v4 = UtilVerifyAndLockDirectory(a2, &hObject);
  if ( v4 < 0 )
    goto LABEL_23;
  if ( (int)tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
              lpFileName,
              L"%s\\%s.buf.etl",
              a2,
              *((_QWORD *)this + 529)) < 0
    || (int)tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
              lpNewFileName,
              L"%s\\%s.etl",
              a2,
              *((_QWORD *)this + 529)) < 0 )
  {
    goto LABEL_3;
  }
  FileW = CreateFileW(lpFileName[0], 0xC0000000, 0, 0, 1u, 0x80u, 0);
  if ( (unsigned __int64)FileW + 1 <= 1 )
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError <= 0 )
      goto LABEL_9;
    v4 = (unsigned __int16)LastError;
    goto LABEL_8;
  }
  CloseHandle(FileW);
  if ( (int)StringCchPrintfW((wchar_t *)this + 1089, 0x401u, lpFileName[0]) < 0 )
  {
LABEL_3:
    v4 = -2147024690;
    goto LABEL_23;
  }
  v4 = ControlTraceW(0, (LPCWSTR)this + 64, (PEVENT_TRACE_PROPERTIES)((char *)this + 8), 3u);
  if ( v4 )
  {
    UtilDeleteFilePath(lpFileName[0]);
    if ( v4 <= 0 )
    {
LABEL_9:
      if ( v4 >= 0 )
        v4 = -2147467259;
      goto LABEL_23;
    }
    v4 = (unsigned __int16)v4;
LABEL_8:
    v4 |= 0x80070000;
    goto LABEL_9;
  }
  if ( MoveFileW(lpFileName[0], lpNewFileName[0]) )
  {
    v4 = 0;
  }
  else
  {
    v7 = GetLastError();
    v4 = v7;
    if ( v7 > 0 )
      v4 = (unsigned __int16)v7 | 0x80070000;
    if ( v4 >= 0 )
      v4 = -2147467259;
    UtilDeleteFilePath(lpFileName[0]);
  }
LABEL_23:
  if ( (unsigned __int64)hObject + 1 > 1 )
    CloseHandle(hObject);
  if ( lpNewFileName[0] != v12 )
    operator delete((void *)lpNewFileName[0], (const struct std::nothrow_t *)&std::nothrow);
  if ( lpFileName[0] != v10 )
    operator delete((void *)lpFileName[0], (const struct std::nothrow_t *)&std::nothrow);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180032c40  push    rbp
0x180032c42  push    rbx
0x180032c43  push    rsi
0x180032c44  push    rdi
0x180032c45  lea     rbp, [rsp-3Fh]
0x180032c4a  sub     rsp, 88h
0x180032c51  mov     rsi, rdx
0x180032c54  mov     rdi, rcx
0x180032c57  lea     rax, [rbp+57h+var_50]
0x180032c5b  mov     [rbp+57h+lpFileName], rax
0x180032c5f  lea     rax, [rbp+57h+var_50]
0x180032c63  mov     [rbp+57h+var_58], rax
0x180032c67  xor     eax, eax
0x180032c69  mov     [rbp+57h+var_50], ax
0x180032c6d  lea     rax, [rbp+57h+var_30]
0x180032c71  mov     [rbp+57h+lpNewFileName], rax
0x180032c75  lea     rax, [rbp+57h+var_30]
0x180032c79  mov     [rbp+57h+var_38], rax
0x180032c7d  xor     eax, eax
0x180032c7f  mov     [rbp+57h+var_30], ax
0x180032c83  mov     [rbp+57h+hObject], rax
0x180032c87  lea     rdx, [rbp+57h+hObject]
0x180032c8b  mov     rcx, rsi; wchar_t *
0x180032c8e  call    ?UtilVerifyAndLockDirectory@@YAJPEB_WPEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@@Z; UtilVerifyAndLockDirectory(wchar_t const *,tlx::unique_any<tlx::file_handle_traits> *)
0x180032c93  mov     ebx, eax
0x180032c95  test    eax, eax
0x180032c97  js      loc_180032DCE
0x180032c9d  mov     r9, [rdi+1088h]
0x180032ca4  mov     r8, rsi
0x180032ca7  lea     rdx, aSSBufEtl; "%s\\%s.buf.etl"
0x180032cae  lea     rcx, [rbp+57h+lpFileName]
0x180032cb2  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x180032cb7  test    eax, eax
0x180032cb9  jns     short loc_180032CC5
0x180032cbb  mov     ebx, 800700CEh
0x180032cc0  jmp     loc_180032DCE
0x180032cc5  mov     r9, [rdi+1088h]
0x180032ccc  mov     r8, rsi
0x180032ccf  lea     rdx, aSSEtl_0; "%s\\%s.etl"
0x180032cd6  lea     rcx, [rbp+57h+lpNewFileName]
0x180032cda  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x180032cdf  test    eax, eax
0x180032ce1  js      short loc_180032CBB
0x180032ce3  mov     [rsp+0A0h+hTemplateFile], 0; hTemplateFile
0x180032cec  mov     [rsp+0A0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180032cf4  mov     [rsp+0A0h+dwCreationDisposition], 1; dwCreationDisposition
0x180032cfc  xor     r9d, r9d; lpSecurityAttributes
0x180032cff  xor     r8d, r8d; dwShareMode
0x180032d02  mov     edx, 0C0000000h; dwDesiredAccess
0x180032d07  mov     rcx, [rbp+57h+lpFileName]; lpFileName
0x180032d0b  call    cs:__imp_CreateFileW
0x180032d11  lea     rcx, [rax+1]
0x180032d15  cmp     rcx, 1
0x180032d19  ja      short loc_180032D3F
0x180032d1b  call    cs:__imp_GetLastError
0x180032d21  mov     ebx, eax
0x180032d23  test    eax, eax
0x180032d25  jle     short loc_180032D30
0x180032d27  movzx   ebx, ax
0x180032d2a  or      ebx, 80070000h
0x180032d30  mov     eax, 80004005h
0x180032d35  test    ebx, ebx
0x180032d37  cmovns  ebx, eax
0x180032d3a  jmp     loc_180032DCE
0x180032d3f  mov     rcx, rax; hObject
0x180032d42  call    cs:__imp_CloseHandle
0x180032d48  lea     rcx, [rdi+882h]; wchar_t *
0x180032d4f  mov     r8, [rbp+57h+lpFileName]; wchar_t *
0x180032d53  mov     edx, 401h; unsigned __int64
0x180032d58  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x180032d5d  test    eax, eax
0x180032d5f  js      loc_180032CBB
0x180032d65  lea     r8, [rdi+8]; Properties
0x180032d69  lea     rdx, [rdi+80h]; InstanceName
0x180032d70  xor     ecx, ecx; TraceHandle
0x180032d72  lea     r9d, [rcx+3]; ControlCode
0x180032d76  call    cs:__imp_ControlTraceW
0x180032d7c  mov     ebx, eax
0x180032d7e  mov     rcx, [rbp+57h+lpFileName]; wchar_t *
0x180032d82  test    eax, eax
0x180032d84  jz      short loc_180032D94
0x180032d86  call    ?UtilDeleteFilePath@@YAJPEB_W@Z; UtilDeleteFilePath(wchar_t const *)
0x180032d8b  test    ebx, ebx
0x180032d8d  jle     short loc_180032D30
0x180032d8f  movzx   ebx, bx
0x180032d92  jmp     short loc_180032D2A
0x180032d94  mov     rdx, [rbp+57h+lpNewFileName]; lpNewFileName
0x180032d98  call    cs:__imp_MoveFileW
0x180032d9e  test    eax, eax
0x180032da0  jnz     short loc_180032DCC
0x180032da2  call    cs:__imp_GetLastError
0x180032da8  mov     ebx, eax
0x180032daa  test    eax, eax
0x180032dac  jle     short loc_180032DB7
0x180032dae  movzx   ebx, ax
0x180032db1  or      ebx, 80070000h
0x180032db7  mov     eax, 80004005h
0x180032dbc  test    ebx, ebx
0x180032dbe  cmovns  ebx, eax
0x180032dc1  mov     rcx, [rbp+57h+lpFileName]; wchar_t *
0x180032dc5  call    ?UtilDeleteFilePath@@YAJPEB_W@Z; UtilDeleteFilePath(wchar_t const *)
0x180032dca  jmp     short loc_180032DCE
0x180032dcc  xor     ebx, ebx
0x180032dce  mov     rcx, [rbp+57h+hObject]; hObject
0x180032dd2  lea     rax, [rcx+1]
0x180032dd6  cmp     rax, 1
0x180032dda  jbe     short loc_180032DE3
0x180032ddc  call    cs:__imp_CloseHandle
0x180032de2  nop
0x180032de3  lea     rax, [rbp+57h+var_30]
0x180032de7  mov     rcx, [rbp+57h+lpNewFileName]; void *
0x180032deb  cmp     rcx, rax
0x180032dee  jz      short loc_180032DFD
0x180032df0  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180032df7  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180032dfc  nop
0x180032dfd  lea     rax, [rbp+57h+var_50]
0x180032e01  mov     rcx, [rbp+57h+lpFileName]; void *
0x180032e05  cmp     rcx, rax
0x180032e08  jz      short loc_180032E16
0x180032e0a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180032e11  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180032e16  mov     eax, ebx
0x180032e18  add     rsp, 88h
0x180032e1f  pop     rdi
0x180032e20  pop     rsi
0x180032e21  pop     rbx
0x180032e22  pop     rbp
0x180032e23  retn
```
