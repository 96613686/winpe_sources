# CSrmDebugInfo::operator<<(long)

- ea: `0x1800166ec`
- end: `0x180016829`
- name: `??6CSrmDebugInfo@@QEAA?AU0@J@Z`
- size: `317`
- prototype: `CSrmDebugInfo *__fastcall(struct CSrmDebugInfo *, CSrmDebugInfo *this, DWORD dwMessageId)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1800198e0`

## callees

- `0x18000f424`
- `0x1800166ec`
- `0x180016830`
- `0x18001b420`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800167a9`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800167a9`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001672f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001672f`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18001675f`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180016791`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18001675f`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180016791`

## string_xrefs

- `0x180016728`: `srm.dll`

## pseudocode

```c
CSrmDebugInfo *__fastcall CSrmDebugInfo::operator<<(struct CSrmDebugInfo *a1, CSrmDebugInfo *this, DWORD dwMessageId)
{
  HMODULE Library; // rbx
  WCHAR Buffer[520]; // [rsp+50h] [rbp-888h] BYREF
  unsigned __int16 v9[544]; // [rsp+460h] [rbp-478h] BYREF

  Library = LoadLibraryExW(L"srm.dll", 0, 2u);
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
  CSrmDebugInfo::operator<<(a1, this);
  return this;
}

```

## disassembly

```asm
0x1800166ec  push    rbx
0x1800166ee  push    rbp
0x1800166ef  push    rsi
0x1800166f0  push    rdi
0x1800166f1  push    r14
0x1800166f3  sub     rsp, 8B0h
0x1800166fa  mov     rax, cs:__security_cookie
0x180016701  xor     rax, rsp
0x180016704  mov     [rsp+8D8h+var_38], rax
0x18001670c  mov     edi, r8d
0x18001670f  mov     rsi, rdx
0x180016712  mov     rbp, rcx
0x180016715  mov     [rsp+8D8h+var_890], rdx
0x18001671a  xor     r14d, r14d
0x18001671d  mov     [rsp+8D8h+var_898], r14d
0x180016722  xor     edx, edx; hFile
0x180016724  lea     r8d, [r14+2]; dwFlags
0x180016728  lea     rcx, aSrmDll_0; "srm.dll"
0x18001672f  call    cs:__imp_LoadLibraryExW
0x180016735  mov     rbx, rax
0x180016738  mov     [rsp+8D8h+Arguments], r14; Arguments
0x18001673d  mov     [rsp+8D8h+nSize], 200h; nSize
0x180016745  lea     rax, [rsp+8D8h+Buffer]
0x18001674a  mov     [rsp+8D8h+lpBuffer], rax; lpBuffer
0x18001674f  mov     r9d, 400h; dwLanguageId
0x180016755  mov     r8d, edi; dwMessageId
0x180016758  xor     edx, edx; lpSource
0x18001675a  mov     ecx, 1200h; dwFlags
0x18001675f  call    cs:__imp_FormatMessageW
0x180016765  test    eax, eax
0x180016767  jnz     short loc_1800167A1
0x180016769  mov     [rsp+8D8h+Arguments], r14; Arguments
0x18001676e  mov     [rsp+8D8h+nSize], 200h; nSize
0x180016776  lea     rax, [rsp+8D8h+Buffer]
0x18001677b  mov     [rsp+8D8h+lpBuffer], rax; lpBuffer
0x180016780  mov     r9d, 400h; dwLanguageId
0x180016786  mov     r8d, edi; dwMessageId
0x180016789  mov     rdx, rbx; lpSource
0x18001678c  mov     ecx, 0A00h; dwFlags
0x180016791  call    cs:__imp_FormatMessageW
0x180016797  test    eax, eax
0x180016799  jnz     short loc_1800167A1
0x18001679b  mov     [rsp+8D8h+Buffer], r14w
0x1800167a1  test    rbx, rbx
0x1800167a4  jz      short loc_1800167AF
0x1800167a6  mov     rcx, rbx; hLibModule
0x1800167a9  call    cs:__imp_FreeLibrary
0x1800167af  mov     r9d, edi
0x1800167b2  mov     edx, 21Fh; unsigned __int64
0x1800167b7  lea     rcx, [rsp+8D8h+var_478]; unsigned __int16 *
0x1800167bf  cmp     [rsp+8D8h+Buffer], r14w
0x1800167c5  jz      short loc_1800167DF
0x1800167c7  lea     rax, [rsp+8D8h+Buffer]
0x1800167cc  mov     [rsp+8D8h+lpBuffer], rax
0x1800167d1  lea     r8, a0x08lxS; "0x%08lx, %s"
0x1800167d8  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800167dd  jmp     short loc_1800167EB
0x1800167df  lea     r8, a0x08lx; "0x%08lx"
0x1800167e6  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800167eb  lea     r8, [rsp+8D8h+var_478]
0x1800167f3  mov     rdx, rsi; this
0x1800167f6  mov     rcx, rbp; struct CSrmDebugInfo *
0x1800167f9  call    ??6CSrmDebugInfo@@QEAA?AU0@PEBG@Z; CSrmDebugInfo::operator<<(ushort const *)
0x1800167fe  nop
0x1800167ff  mov     [rsp+8D8h+var_898], 1
0x180016807  mov     rax, rsi
0x18001680a  mov     rcx, [rsp+8D8h+var_38]
0x180016812  xor     rcx, rsp; StackCookie
0x180016815  call    __security_check_cookie
0x18001681a  add     rsp, 8B0h
0x180016821  pop     r14
0x180016823  pop     rdi
0x180016824  pop     rsi
0x180016825  pop     rbp
0x180016826  pop     rbx
0x180016827  retn
```
