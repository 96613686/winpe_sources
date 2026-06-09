# GetW32TimeErrorMessage(uint,ushort *,ulong)

- ea: `0x18001473c`
- end: `0x1800147bd`
- name: `?GetW32TimeErrorMessage@@YAXIPEAGK@Z`
- size: `129`
- prototype: `void __fastcall(DWORD dwMessageId, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180013ec4`

## callees

- `0x180013dd8`
- `0x18001473c`
- `0x1800166b0`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18001478b`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18001478b`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800147a7`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800147a7`

## string_xrefs

- `0x180014750`: `w32time.dll`

## pseudocode

```c
void __fastcall GetW32TimeErrorMessage(DWORD dwMessageId, unsigned __int16 *a2)
{
  HMODULE LibraryW; // rax
  HMODULE v5; // rdi

  LibraryW = IsolationAwareLoadLibraryW(L"w32time.dll");
  v5 = LibraryW;
  *a2 = 0;
  if ( LibraryW )
  {
    if ( FormatMessageW(0x800u, LibraryW, dwMessageId, 0, a2, 0x824u, 0) )
      CleanUpErrorString(a2);
    else
      *a2 = 0;
    FreeLibrary(v5);
  }
}

```

## disassembly

```asm
0x18001473c  mov     [rsp+arg_0], rbx
0x180014741  mov     [rsp+arg_8], rsi
0x180014746  push    rdi
0x180014747  sub     rsp, 40h
0x18001474b  mov     esi, ecx
0x18001474d  mov     rbx, rdx
0x180014750  lea     rcx, aW32timeDll_0; "w32time.dll"
0x180014757  call    IsolationAwareLoadLibraryW
0x18001475c  xor     r8d, r8d
0x18001475f  mov     rdi, rax
0x180014762  mov     [rbx], r8w
0x180014766  test    rax, rax
0x180014769  jz      short loc_1800147AD
0x18001476b  mov     [rsp+48h+Arguments], r8; Arguments
0x180014770  xor     r9d, r9d; dwLanguageId
0x180014773  mov     [rsp+48h+nSize], 824h; nSize
0x18001477b  mov     r8d, esi; dwMessageId
0x18001477e  mov     rdx, rax; lpSource
0x180014781  mov     [rsp+48h+lpBuffer], rbx; lpBuffer
0x180014786  mov     ecx, 800h; dwFlags
0x18001478b  call    cs:__imp_FormatMessageW
0x180014791  test    eax, eax
0x180014793  jz      short loc_18001479F
0x180014795  mov     rcx, rbx; unsigned __int16 *
0x180014798  call    ?CleanUpErrorString@@YAJPEAG@Z; CleanUpErrorString(ushort *)
0x18001479d  jmp     short loc_1800147A4
0x18001479f  xor     eax, eax
0x1800147a1  mov     [rbx], ax
0x1800147a4  mov     rcx, rdi; hLibModule
0x1800147a7  call    cs:__imp_FreeLibrary
0x1800147ad  mov     rbx, [rsp+48h+arg_0]
0x1800147b2  mov     rsi, [rsp+48h+arg_8]
0x1800147b7  add     rsp, 40h
0x1800147bb  pop     rdi
0x1800147bc  retn
```
