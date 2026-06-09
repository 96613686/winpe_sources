# FormatErrorMessage

- ea: `0x14001eed0`
- end: `0x14001ef61`
- name: `FormatErrorMessage`
- size: `145`
- prototype: `__int64 __fastcall(DWORD dwMessageId, LPCWSTR lpLibFileName, LPWSTR lpBuffer)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1400192b4`

## callees

- `0x14001eed0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001ef33`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001ef33`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x14001ef29`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x14001ef29`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14001ef50`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14001ef50`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x14001eef3`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x14001eef3`

## pseudocode

```c
__int64 __fastcall FormatErrorMessage(DWORD dwMessageId, LPCWSTR lpLibFileName, LPWSTR lpBuffer)
{
  HMODULE Library; // rdi
  unsigned int v6; // ebx
  DWORD v7; // ecx
  signed int LastError; // eax

  Library = 0;
  if ( lpLibFileName )
    Library = LoadLibraryExW(lpLibFileName, 0, 0x800u);
  v6 = 0;
  v7 = 2560;
  if ( !Library )
    v7 = 4608;
  if ( !FormatMessageW(v7, Library, dwMessageId, 0x400u, lpBuffer, 0x400u, 0) )
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
  }
  if ( Library )
    FreeLibrary(Library);
  return v6;
}

```

## disassembly

```asm
0x14001eed0  push    rbx
0x14001eed2  push    rbp
0x14001eed3  push    rsi
0x14001eed4  push    rdi
0x14001eed5  sub     rsp, 48h
0x14001eed9  xor     edi, edi
0x14001eedb  mov     rsi, r8
0x14001eede  mov     rax, rdx
0x14001eee1  mov     ebp, ecx
0x14001eee3  test    rdx, rdx
0x14001eee6  jz      short loc_14001EEFC
0x14001eee8  xor     edx, edx; hFile
0x14001eeea  mov     r8d, 800h; dwFlags
0x14001eef0  mov     rcx, rax; lpLibFileName
0x14001eef3  call    cs:__imp_LoadLibraryExW
0x14001eef9  mov     rdi, rax
0x14001eefc  xor     ebx, ebx
0x14001eefe  mov     ecx, 0A00h
0x14001ef03  mov     eax, 1200h
0x14001ef08  mov     [rsp+68h+Arguments], rbx; Arguments
0x14001ef0d  mov     r9d, 400h; dwLanguageId
0x14001ef13  test    rdi, rdi
0x14001ef16  mov     [rsp+68h+nSize], r9d; nSize
0x14001ef1b  mov     r8d, ebp; dwMessageId
0x14001ef1e  cmovz   ecx, eax; dwFlags
0x14001ef21  mov     [rsp+68h+lpBuffer], rsi; lpBuffer
0x14001ef26  mov     rdx, rdi; lpSource
0x14001ef29  call    cs:__imp_FormatMessageW
0x14001ef2f  test    eax, eax
0x14001ef31  jnz     short loc_14001EF48
0x14001ef33  call    cs:__imp_GetLastError
0x14001ef39  mov     ebx, eax
0x14001ef3b  test    eax, eax
0x14001ef3d  jle     short loc_14001EF48
0x14001ef3f  movzx   ebx, ax
0x14001ef42  or      ebx, 80070000h
0x14001ef48  test    rdi, rdi
0x14001ef4b  jz      short loc_14001EF56
0x14001ef4d  mov     rcx, rdi; hLibModule
0x14001ef50  call    cs:__imp_FreeLibrary
0x14001ef56  mov     eax, ebx
0x14001ef58  add     rsp, 48h
0x14001ef5c  pop     rdi
0x14001ef5d  pop     rsi
0x14001ef5e  pop     rbp
0x14001ef5f  pop     rbx
0x14001ef60  retn
```
