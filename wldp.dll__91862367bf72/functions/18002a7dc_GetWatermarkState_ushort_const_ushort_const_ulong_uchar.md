# GetWatermarkState(ushort const *,ushort const *,ulong,uchar *)

- ea: `0x18002a7dc`
- end: `0x18002a8f5`
- name: `?GetWatermarkState@@YAJPEBG0KPEAE@Z`
- size: `281`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, DWORD nNumberOfBytesToRead, unsigned __int8 *lpBuffer)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x18001d220`
- `0x18002af60`

## callees

- `0x180008320`
- `0x180012ef0`
- `0x180021ec0`
- `0x180022a10`
- `0x18002a7dc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a888`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a888`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002a8cf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002a8cf`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18002a8b6`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18002a8b6`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002a879`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002a879`

## pseudocode

```c
__int64 __fastcall GetWatermarkState(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        DWORD nNumberOfBytesToRead,
        unsigned __int8 *lpBuffer)
{
  void *v7; // rdi
  unsigned __int64 v9; // rdx
  signed int v10; // ebx
  HANDLE FileW; // rax
  signed int LastError; // eax
  DWORD NumberOfBytesRead; // [rsp+40h] [rbp-258h] BYREF
  WCHAR FileName[264]; // [rsp+50h] [rbp-248h] BYREF

  v7 = 0;
  NumberOfBytesRead = 0;
  memset_0(FileName, 0, 0x208u);
  if ( !a2 || (v10 = StringCchCopyW(FileName, 0x104u, a2), v10 >= 0) )
  {
    v10 = StringCchCatW(FileName, v9, a1);
    if ( v10 >= 0 )
    {
      FileW = CreateFileW(FileName, 0x80000000, 0, 0, 3u, 0x80u, 0);
      v7 = FileW;
      if ( FileW == (HANDLE)-1LL || !ReadFile(FileW, lpBuffer, nNumberOfBytesToRead, &NumberOfBytesRead, 0) )
      {
        LastError = GetLastError();
        v10 = LastError;
        if ( LastError > 0 )
          v10 = (unsigned __int16)LastError | 0x80070000;
      }
      else if ( NumberOfBytesRead != nNumberOfBytesToRead )
      {
        v10 = 1;
      }
    }
  }
  CloseHandle(v7);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18002a7dc  push    rbx
0x18002a7de  push    rbp
0x18002a7df  push    rsi
0x18002a7e0  push    rdi
0x18002a7e1  push    r14
0x18002a7e3  sub     rsp, 270h
0x18002a7ea  mov     rax, cs:__security_cookie
0x18002a7f1  xor     rax, rsp
0x18002a7f4  mov     [rsp+298h+var_38], rax
0x18002a7fc  mov     esi, r8d
0x18002a7ff  mov     rbx, rdx
0x18002a802  mov     rbp, rcx
0x18002a805  xor     edi, edi
0x18002a807  xor     edx, edx; Val
0x18002a809  mov     [rsp+298h+NumberOfBytesRead], edi
0x18002a80d  mov     r8d, 208h; Size
0x18002a813  lea     rcx, [rsp+298h+FileName]; void *
0x18002a818  mov     r14, r9
0x18002a81b  call    memset_0
0x18002a820  test    rbx, rbx
0x18002a823  jz      short loc_18002A841
0x18002a825  mov     r8, rbx; unsigned __int16 *
0x18002a828  lea     rcx, [rsp+298h+FileName]; unsigned __int16 *
0x18002a82d  mov     edx, 104h; unsigned __int64
0x18002a832  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002a837  mov     ebx, eax
0x18002a839  test    eax, eax
0x18002a83b  js      loc_18002A8CC
0x18002a841  mov     r8, rbp; unsigned __int16 *
0x18002a844  lea     rcx, [rsp+298h+FileName]; unsigned __int16 *
0x18002a849  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002a84e  mov     ebx, eax
0x18002a850  test    eax, eax
0x18002a852  js      short loc_18002A8CC
0x18002a854  mov     [rsp+298h+hTemplateFile], rdi; hTemplateFile
0x18002a859  lea     rcx, [rsp+298h+FileName]; lpFileName
0x18002a85e  mov     [rsp+298h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18002a866  xor     r9d, r9d; lpSecurityAttributes
0x18002a869  xor     r8d, r8d; dwShareMode
0x18002a86c  mov     [rsp+298h+dwCreationDisposition], 3; dwCreationDisposition
0x18002a874  mov     edx, 80000000h; dwDesiredAccess
0x18002a879  call    cs:__imp_CreateFileW
0x18002a87f  mov     rdi, rax
0x18002a882  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002a886  jnz     short loc_18002A89F
0x18002a888  call    cs:__imp_GetLastError
0x18002a88e  mov     ebx, eax
0x18002a890  test    eax, eax
0x18002a892  jle     short loc_18002A8CC
0x18002a894  movzx   ebx, ax
0x18002a897  or      ebx, 80070000h
0x18002a89d  jmp     short loc_18002A8CC
0x18002a89f  lea     r9, [rsp+298h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18002a8a4  mov     qword ptr [rsp+298h+dwCreationDisposition], 0; lpOverlapped
0x18002a8ad  mov     r8d, esi; nNumberOfBytesToRead
0x18002a8b0  mov     rdx, r14; lpBuffer
0x18002a8b3  mov     rcx, rax; hFile
0x18002a8b6  call    cs:__imp_ReadFile
0x18002a8bc  test    eax, eax
0x18002a8be  jz      short loc_18002A888
0x18002a8c0  cmp     [rsp+298h+NumberOfBytesRead], esi
0x18002a8c4  mov     eax, 1
0x18002a8c9  cmovnz  ebx, eax
0x18002a8cc  mov     rcx, rdi; hObject
0x18002a8cf  call    cs:__imp_CloseHandle
0x18002a8d5  mov     eax, ebx
0x18002a8d7  mov     rcx, [rsp+298h+var_38]
0x18002a8df  xor     rcx, rsp; StackCookie
0x18002a8e2  call    __security_check_cookie
0x18002a8e7  add     rsp, 270h
0x18002a8ee  pop     r14
0x18002a8f0  pop     rdi
0x18002a8f1  pop     rsi
0x18002a8f2  pop     rbp
0x18002a8f3  pop     rbx
0x18002a8f4  retn
```
