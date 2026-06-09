# ArgPrintError(long,ushort const *)

- ea: `0x14003d124`
- end: `0x14003d24e`
- name: `?ArgPrintError@@YAJJPEBG@Z`
- size: `298`
- prototype: `__int64 __fastcall(DWORD dwMessageId, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x14002ec00`

## callees

- `0x14003d124`
- `0x14003d254`
- `0x14003d4f0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003d153`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003d153`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x14003d1bd`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x14003d1ef`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x14003d1bd`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x14003d1ef`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14003d23b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14003d23b`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14003d22b`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14003d22b`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x14003d145`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x14003d145`

## string_xrefs

- `0x14003d13e`: `pdh.dll`

## pseudocode

```c
__int64 __fastcall ArgPrintError(DWORD dwMessageId, const unsigned __int16 *a2)
{
  HMODULE LibraryW; // rdi
  signed int LastError; // eax
  unsigned int v5; // ebx
  const unsigned __int16 *v6; // rdx
  unsigned __int16 *Buffer; // [rsp+58h] [rbp+10h] BYREF

  Buffer = 0;
  LibraryW = LoadLibraryW(L"pdh.dll");
  if ( LibraryW )
  {
    if ( g_Debug )
      ArgPrintMessage(0, 0x3B64u, dwMessageId);
    else
      ArgPrintMessage(0, 0x3B61u);
    FormatMessageW(0xB00u, LibraryW, dwMessageId, 0, (LPWSTR)&Buffer, 0x400u, 0);
    v6 = Buffer;
    if ( Buffer || (FormatMessageW(0x1300u, 0, dwMessageId, 0, (LPWSTR)&Buffer, 0x400u, 0), (v6 = Buffer) != 0) )
      ArgPrintEx(0, v6);
    else
      ArgPrintMessage(0, 0x3B63u);
    if ( (_WORD)dwMessageId == 5 )
      ArgPrintMessage(0, 0x3B62u);
    v5 = 0;
    FreeLibrary(LibraryW);
  }
  else
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
  }
  if ( Buffer )
    LocalFree(Buffer);
  return v5;
}

```

## disassembly

```asm
0x14003d124  mov     [rsp+arg_0], rbx
0x14003d129  mov     [rsp+Buffer], rdx
0x14003d12e  push    rdi
0x14003d12f  sub     rsp, 40h
0x14003d133  mov     ebx, ecx
0x14003d135  mov     [rsp+48h+Buffer], 0
0x14003d13e  lea     rcx, aPdhDll_0; "pdh.dll"
0x14003d145  call    cs:__imp_LoadLibraryW
0x14003d14b  mov     rdi, rax
0x14003d14e  test    rax, rax
0x14003d151  jnz     short loc_14003D171
0x14003d153  call    cs:__imp_GetLastError
0x14003d159  mov     ebx, eax
0x14003d15b  test    eax, eax
0x14003d15d  jle     loc_14003D231
0x14003d163  movzx   ebx, ax
0x14003d166  or      ebx, 80070000h
0x14003d16c  jmp     loc_14003D231
0x14003d171  xor     ecx, ecx; unsigned int *
0x14003d173  cmp     cs:?g_Debug@@3HA, ecx; int g_Debug
0x14003d179  jz      short loc_14003D18A
0x14003d17b  mov     r8d, ebx
0x14003d17e  mov     edx, 3B64h; uID
0x14003d183  call    ?ArgPrintMessage@@YAJPEAKIZZ; ArgPrintMessage(ulong *,uint,...)
0x14003d188  jmp     short loc_14003D194
0x14003d18a  mov     edx, 3B61h; uID
0x14003d18f  call    ?ArgPrintMessage@@YAJPEAKIZZ; ArgPrintMessage(ulong *,uint,...)
0x14003d194  mov     [rsp+48h+Arguments], 0; Arguments
0x14003d19d  lea     rax, [rsp+48h+Buffer]
0x14003d1a2  mov     [rsp+48h+nSize], 400h; nSize
0x14003d1aa  xor     r9d, r9d; dwLanguageId
0x14003d1ad  mov     r8d, ebx; dwMessageId
0x14003d1b0  mov     [rsp+48h+lpBuffer], rax; lpBuffer
0x14003d1b5  mov     rdx, rdi; lpSource
0x14003d1b8  mov     ecx, 0B00h; dwFlags
0x14003d1bd  call    cs:__imp_FormatMessageW
0x14003d1c3  mov     rdx, [rsp+48h+Buffer]; unsigned __int16 *
0x14003d1c8  test    rdx, rdx
0x14003d1cb  jnz     short loc_14003D20D
0x14003d1cd  mov     [rsp+48h+Arguments], rdx; Arguments
0x14003d1d2  lea     rax, [rsp+48h+Buffer]
0x14003d1d7  mov     [rsp+48h+nSize], 400h; nSize
0x14003d1df  xor     r9d, r9d; dwLanguageId
0x14003d1e2  mov     r8d, ebx; dwMessageId
0x14003d1e5  mov     [rsp+48h+lpBuffer], rax; lpBuffer
0x14003d1ea  mov     ecx, 1300h; dwFlags
0x14003d1ef  call    cs:__imp_FormatMessageW
0x14003d1f5  mov     rdx, [rsp+48h+Buffer]
0x14003d1fa  test    rdx, rdx
0x14003d1fd  jnz     short loc_14003D20D
0x14003d1ff  mov     edx, 3B63h; uID
0x14003d204  xor     ecx, ecx; unsigned int *
0x14003d206  call    ?ArgPrintMessage@@YAJPEAKIZZ; ArgPrintMessage(ulong *,uint,...)
0x14003d20b  jmp     short loc_14003D214
0x14003d20d  xor     ecx, ecx; unsigned int *
0x14003d20f  call    ?ArgPrintEx@@YAJPEAKPEBG@Z; ArgPrintEx(ulong *,ushort const *)
0x14003d214  cmp     bx, 5
0x14003d218  jnz     short loc_14003D226
0x14003d21a  mov     edx, 3B62h; uID
0x14003d21f  xor     ecx, ecx; unsigned int *
0x14003d221  call    ?ArgPrintMessage@@YAJPEAKIZZ; ArgPrintMessage(ulong *,uint,...)
0x14003d226  xor     ebx, ebx
0x14003d228  mov     rcx, rdi; hLibModule
0x14003d22b  call    cs:__imp_FreeLibrary
0x14003d231  mov     rcx, [rsp+48h+Buffer]; hMem
0x14003d236  test    rcx, rcx
0x14003d239  jz      short loc_14003D241
0x14003d23b  call    cs:__imp_LocalFree
0x14003d241  mov     eax, ebx
0x14003d243  mov     rbx, [rsp+48h+arg_0]
0x14003d248  add     rsp, 40h
0x14003d24c  pop     rdi
0x14003d24d  retn
```
