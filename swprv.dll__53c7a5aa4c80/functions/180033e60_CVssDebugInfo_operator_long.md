# CVssDebugInfo::operator<<(long)

- ea: `0x180033e60`
- end: `0x180033f89`
- name: `??6CVssDebugInfo@@QEAA?AU0@J@Z`
- size: `297`
- prototype: `CVssDebugInfo *__fastcall(struct CVssDebugInfo *, CVssDebugInfo *this, DWORD dwMessageId)`
- caller_count: `11`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180006910`
- `0x18001b130`
- `0x180034cfc`
- `0x180035f44`
- `0x180036c10`
- `0x180036f10`
- `0x180037080`
- `0x1800372e8`
- `0x18003750c`
- `0x1800377c4`
- `0x180040cb0`

## callees

- `0x180001580`
- `0x18001c208`
- `0x180033e60`
- `0x180034038`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180033e96`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180033e96`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180033f13`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180033f13`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180033ec9`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180033efb`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180033ec9`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180033efb`

## string_xrefs

- `0x180033e8b`: `vsstrace.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
CVssDebugInfo *__fastcall CVssDebugInfo::operator<<(struct CVssDebugInfo *a1, CVssDebugInfo *this, DWORD dwMessageId)
{
  HMODULE Library; // rbx
  WCHAR Buffer[520]; // [rsp+40h] [rbp-888h] BYREF
  unsigned __int16 v9[544]; // [rsp+450h] [rbp-478h] BYREF

  Library = LoadLibraryExW(L"vsstrace.dll", 0, 2u);
  if ( !FormatMessageW(0x1200u, 0, dwMessageId, 0x400u, Buffer, 0x200u, 0)
    && !FormatMessageW(0xA00u, Library, dwMessageId, 0x400u, Buffer, 0x200u, 0) )
  {
    Buffer[0] = 0;
  }
  if ( Library )
    FreeLibrary(Library);
  if ( Buffer[0] )
    StringCchPrintfW(v9, 0x21Fu, L"0x%08lx, %s", dwMessageId, Buffer);
  else
    StringCchPrintfW(v9, 0x21Fu, L"0x%08lx", dwMessageId);
  CVssDebugInfo::operator<<(a1, this, v9);
  return this;
}

```

## disassembly

```asm
0x180033e60  push    rbx
0x180033e62  push    rbp
0x180033e63  push    rsi
0x180033e64  push    rdi
0x180033e65  push    r14
0x180033e67  sub     rsp, 8A0h
0x180033e6e  mov     rax, cs:__security_cookie
0x180033e75  xor     rax, rsp
0x180033e78  mov     [rsp+8C8h+var_38], rax
0x180033e80  mov     rsi, rdx
0x180033e83  mov     edi, r8d
0x180033e86  xor     edx, edx; hFile
0x180033e88  mov     rbp, rcx
0x180033e8b  lea     rcx, aVsstraceDll_0; "vsstrace.dll"
0x180033e92  lea     r8d, [rdx+2]; dwFlags
0x180033e96  call    cs:__imp_LoadLibraryExW
0x180033e9c  xor     r14d, r14d
0x180033e9f  mov     r9d, 400h; dwLanguageId
0x180033ea5  mov     rbx, rax
0x180033ea8  mov     [rsp+8C8h+Arguments], r14; Arguments
0x180033ead  lea     rax, [rsp+8C8h+Buffer]
0x180033eb2  mov     [rsp+8C8h+nSize], 200h; nSize
0x180033eba  mov     r8d, edi; dwMessageId
0x180033ebd  mov     [rsp+8C8h+lpBuffer], rax; lpBuffer
0x180033ec2  xor     edx, edx; lpSource
0x180033ec4  mov     ecx, 1200h; dwFlags
0x180033ec9  call    cs:__imp_FormatMessageW
0x180033ecf  test    eax, eax
0x180033ed1  jnz     short loc_180033F0B
0x180033ed3  mov     [rsp+8C8h+Arguments], r14; Arguments
0x180033ed8  lea     rax, [rsp+8C8h+Buffer]
0x180033edd  mov     [rsp+8C8h+nSize], 200h; nSize
0x180033ee5  mov     r9d, 400h; dwLanguageId
0x180033eeb  mov     r8d, edi; dwMessageId
0x180033eee  mov     [rsp+8C8h+lpBuffer], rax; lpBuffer
0x180033ef3  mov     rdx, rbx; lpSource
0x180033ef6  mov     ecx, 0A00h; dwFlags
0x180033efb  call    cs:__imp_FormatMessageW
0x180033f01  test    eax, eax
0x180033f03  jnz     short loc_180033F0B
0x180033f05  mov     [rsp+8C8h+Buffer], r14w
0x180033f0b  test    rbx, rbx
0x180033f0e  jz      short loc_180033F19
0x180033f10  mov     rcx, rbx; hLibModule
0x180033f13  call    cs:__imp_FreeLibrary
0x180033f19  lea     rcx, [rsp+8C8h+var_478]; unsigned __int16 *
0x180033f21  mov     r9d, edi
0x180033f24  mov     edx, 21Fh; unsigned __int64
0x180033f29  cmp     [rsp+8C8h+Buffer], r14w
0x180033f2f  jz      short loc_180033F49
0x180033f31  lea     rax, [rsp+8C8h+Buffer]
0x180033f36  lea     r8, a0x08lxS; "0x%08lx, %s"
0x180033f3d  mov     [rsp+8C8h+lpBuffer], rax
0x180033f42  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180033f47  jmp     short loc_180033F55
0x180033f49  lea     r8, a0x08lx; "0x%08lx"
0x180033f50  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180033f55  lea     r8, [rsp+8C8h+var_478]; unsigned __int16 *
0x180033f5d  mov     rdx, rsi; this
0x180033f60  mov     rcx, rbp; struct CVssDebugInfo *
0x180033f63  call    ??6CVssDebugInfo@@QEAA?AU0@PEBG@Z; CVssDebugInfo::operator<<(ushort const *)
0x180033f68  mov     rax, rsi
0x180033f6b  mov     rcx, [rsp+8C8h+var_38]
0x180033f73  xor     rcx, rsp; StackCookie
0x180033f76  call    __security_check_cookie
0x180033f7b  add     rsp, 8A0h
0x180033f82  pop     r14
0x180033f84  pop     rdi
0x180033f85  pop     rsi
0x180033f86  pop     rbp
0x180033f87  pop     rbx
0x180033f88  retn
```
