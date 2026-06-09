# CSrmDebugInfo::operator<<(long)

- ea: `0x18007023c`
- end: `0x180070379`
- name: `??6CSrmDebugInfo@@QEAA?AU0@J@Z`
- size: `317`
- prototype: `CSrmDebugInfo *__fastcall(struct CSrmDebugInfo *, CSrmDebugInfo *this, DWORD dwMessageId)`
- caller_count: `7`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180064400`
- `0x1800660b0`
- `0x180067600`
- `0x180069dc0`
- `0x180070d7c`
- `0x1800745d0`
- `0x180074874`

## callees

- `0x180017fd8`
- `0x18007023c`
- `0x180070380`
- `0x1800b07d0`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x1800702f9`
- `KERNEL32!FreeLibrary` at `0x1800702f9`
- `KERNEL32!LoadLibraryExW` at `0x18007027f`
- `KERNEL32!LoadLibraryExW` at `0x18007027f`
- `KERNEL32!FormatMessageW` at `0x1800702af`
- `KERNEL32!FormatMessageW` at `0x1800702e1`
- `KERNEL32!FormatMessageW` at `0x1800702af`
- `KERNEL32!FormatMessageW` at `0x1800702e1`

## string_xrefs

- `0x180070278`: `srm.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
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
  CSrmDebugInfo::operator<<(a1, this, v9);
  return this;
}

```

## disassembly

```asm
0x18007023c  push    rbx
0x18007023e  push    rbp
0x18007023f  push    rsi
0x180070240  push    rdi
0x180070241  push    r14
0x180070243  sub     rsp, 8B0h
0x18007024a  mov     rax, cs:__security_cookie
0x180070251  xor     rax, rsp
0x180070254  mov     [rsp+8D8h+var_38], rax
0x18007025c  mov     edi, r8d
0x18007025f  mov     rsi, rdx
0x180070262  mov     rbp, rcx
0x180070265  mov     [rsp+8D8h+var_890], rdx
0x18007026a  xor     r14d, r14d
0x18007026d  mov     [rsp+8D8h+var_898], r14d
0x180070272  xor     edx, edx; hFile
0x180070274  lea     r8d, [r14+2]; dwFlags
0x180070278  lea     rcx, aSrmDll_0; "srm.dll"
0x18007027f  call    cs:__imp_LoadLibraryExW
0x180070285  mov     rbx, rax
0x180070288  mov     [rsp+8D8h+Arguments], r14; Arguments
0x18007028d  mov     [rsp+8D8h+nSize], 200h; nSize
0x180070295  lea     rax, [rsp+8D8h+Buffer]
0x18007029a  mov     [rsp+8D8h+lpBuffer], rax; lpBuffer
0x18007029f  mov     r9d, 400h; dwLanguageId
0x1800702a5  mov     r8d, edi; dwMessageId
0x1800702a8  xor     edx, edx; lpSource
0x1800702aa  mov     ecx, 1200h; dwFlags
0x1800702af  call    cs:__imp_FormatMessageW
0x1800702b5  test    eax, eax
0x1800702b7  jnz     short loc_1800702F1
0x1800702b9  mov     [rsp+8D8h+Arguments], r14; Arguments
0x1800702be  mov     [rsp+8D8h+nSize], 200h; nSize
0x1800702c6  lea     rax, [rsp+8D8h+Buffer]
0x1800702cb  mov     [rsp+8D8h+lpBuffer], rax; lpBuffer
0x1800702d0  mov     r9d, 400h; dwLanguageId
0x1800702d6  mov     r8d, edi; dwMessageId
0x1800702d9  mov     rdx, rbx; lpSource
0x1800702dc  mov     ecx, 0A00h; dwFlags
0x1800702e1  call    cs:__imp_FormatMessageW
0x1800702e7  test    eax, eax
0x1800702e9  jnz     short loc_1800702F1
0x1800702eb  mov     [rsp+8D8h+Buffer], r14w
0x1800702f1  test    rbx, rbx
0x1800702f4  jz      short loc_1800702FF
0x1800702f6  mov     rcx, rbx; hLibModule
0x1800702f9  call    cs:__imp_FreeLibrary
0x1800702ff  mov     r9d, edi
0x180070302  mov     edx, 21Fh; unsigned __int64
0x180070307  lea     rcx, [rsp+8D8h+var_478]; unsigned __int16 *
0x18007030f  cmp     [rsp+8D8h+Buffer], r14w
0x180070315  jz      short loc_18007032F
0x180070317  lea     rax, [rsp+8D8h+Buffer]
0x18007031c  mov     [rsp+8D8h+lpBuffer], rax
0x180070321  lea     r8, a0x08lxS; "0x%08lx, %s"
0x180070328  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18007032d  jmp     short loc_18007033B
0x18007032f  lea     r8, a0x08lx; "0x%08lx"
0x180070336  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18007033b  lea     r8, [rsp+8D8h+var_478]; unsigned __int16 *
0x180070343  mov     rdx, rsi; this
0x180070346  mov     rcx, rbp; struct CSrmDebugInfo *
0x180070349  call    ??6CSrmDebugInfo@@QEAA?AU0@PEBG@Z; CSrmDebugInfo::operator<<(ushort const *)
0x18007034e  nop
0x18007034f  mov     [rsp+8D8h+var_898], 1
0x180070357  mov     rax, rsi
0x18007035a  mov     rcx, [rsp+8D8h+var_38]
0x180070362  xor     rcx, rsp; StackCookie
0x180070365  call    __security_check_cookie
0x18007036a  add     rsp, 8B0h
0x180070371  pop     r14
0x180070373  pop     rdi
0x180070374  pop     rsi
0x180070375  pop     rbp
0x180070376  pop     rbx
0x180070377  retn
```
