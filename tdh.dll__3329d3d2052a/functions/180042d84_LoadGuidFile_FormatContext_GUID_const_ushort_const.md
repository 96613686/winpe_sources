# LoadGuidFile(FormatContext *,_GUID const *,ushort const *)

- ea: `0x180042d84`
- end: `0x180042f75`
- name: `?LoadGuidFile@@YAKPEAUFormatContext@@PEBU_GUID@@PEBG@Z`
- size: `497`
- prototype: `__int64 __fastcall(struct FormatContext *, const struct _GUID *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x18004260c`

## callees

- `0x1800113a8`
- `0x1800207c0`
- `0x18003f9ec`
- `0x18003fb28`
- `0x180042d84`
- `0x180042f7c`
- `0x18004c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042f44`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042f44`
- `api-ms-win-core-processenvironment-l1-1-0!SearchPathW` at `0x180042eb1`
- `api-ms-win-core-processenvironment-l1-1-0!SearchPathW` at `0x180042eb1`

## string_xrefs

- `0x180042e74`: `	Trying SearchPath for file %s.`
- `0x180042f29`: `\nFile %s name was too Long? Max = %d(MAX_PATH), required = %d.\n`

## pseudocode

```c
__int64 __fastcall LoadGuidFile(struct FormatContext *a1, const struct _GUID *a2, const unsigned __int16 *a3)
{
  const WCHAR *TraceFormatSearchPathW; // rbp
  unsigned int v6; // ebx
  DWORD v7; // eax
  LPWSTR FilePart; // [rsp+70h] [rbp-468h] BYREF
  WCHAR FileName[264]; // [rsp+80h] [rbp-458h] BYREF
  WCHAR Buffer[264]; // [rsp+290h] [rbp-248h] BYREF

  FilePart = 0;
  TraceFormatSearchPathW = a3;
  if ( !a3 )
  {
    v6 = 0;
    TraceFormatSearchPathW = (const WCHAR *)GetTraceFormatSearchPathW();
    if ( !TraceFormatSearchPathW )
      return v6;
  }
  StringCchPrintfW(
    FileName,
    0x104u,
    L"%08x-%04x-%04x-%02x%02x-%02x%02x%02x%02x%02x%02x.tmf",
    a2->Data1,
    a2->Data2,
    a2->Data3,
    a2->Data4[0],
    a2->Data4[1],
    a2->Data4[2],
    a2->Data4[3],
    a2->Data4[4],
    a2->Data4[5],
    a2->Data4[6],
    a2->Data4[7],
    FilePart);
  FileName[260] = 0;
  if ( TracePrinter )
  {
    if ( DebugExtPrint )
      TracePrinterExt((wchar_t *)L"\tTrying SearchPath for file %s.", FileName);
    else
      TracePrinter(L"\tTrying SearchPath for file %s.", FileName);
  }
  v7 = SearchPathW(TraceFormatSearchPathW, FileName, 0, 0x104u, Buffer, &FilePart);
  if ( !v7 )
    return GetLastError();
  if ( (int)v7 > 260 )
  {
    if ( TracePrinter )
    {
      if ( DebugExtPrint )
        TracePrinterExt(
          (wchar_t *)L"\nFile %s name was too Long? Max = %d(MAX_PATH), required = %d.\n",
          FileName,
          260,
          v7);
      else
        TracePrinter(L"\nFile %s name was too Long? Max = %d(MAX_PATH), required = %d.\n", FileName, 260, v7);
    }
    return GetLastError();
  }
  if ( TracePrinter )
  {
    if ( DebugExtPrint )
      TracePrinterExt((wchar_t *)L" - Success\n");
    else
      TracePrinter(L" - Success\n");
  }
  v6 = 2;
  if ( (unsigned int)GetTraceGuidsW(Buffer, a1) )
    return 0;
  return v6;
}

```

## disassembly

```asm
0x180042d84  mov     [rsp+arg_18], rbx
0x180042d89  push    rbp
0x180042d8a  push    rsi
0x180042d8b  push    rdi
0x180042d8c  push    r14
0x180042d8e  push    r15
0x180042d90  sub     rsp, 4B0h
0x180042d97  mov     rax, cs:__security_cookie
0x180042d9e  xor     rax, rsp
0x180042da1  mov     [rsp+4D8h+var_38], rax
0x180042da9  mov     [rsp+4D8h+FilePart], 0
0x180042db2  mov     rbp, r8
0x180042db5  mov     r14, rdx
0x180042db8  mov     r15, rcx
0x180042dbb  test    r8, r8
0x180042dbe  jnz     short loc_180042DD3
0x180042dc0  xor     ebx, ebx
0x180042dc2  call    GetTraceFormatSearchPathW
0x180042dc7  mov     rbp, rax
0x180042dca  test    rax, rax
0x180042dcd  jz      loc_180042F4C
0x180042dd3  movzx   ecx, byte ptr [r14+0Eh]
0x180042dd8  movzx   edx, byte ptr [r14+0Dh]
0x180042ddd  movzx   r8d, byte ptr [r14+0Ch]
0x180042de2  movzx   r9d, byte ptr [r14+0Bh]
0x180042de7  movzx   ebx, byte ptr [r14+8]
0x180042dec  movzx   eax, byte ptr [r14+0Fh]
0x180042df1  movzx   r10d, byte ptr [r14+0Ah]
0x180042df6  movzx   r11d, byte ptr [r14+9]
0x180042dfb  movzx   edi, word ptr [r14+6]
0x180042e00  movzx   esi, word ptr [r14+4]
0x180042e05  mov     [rsp+4D8h+var_470], eax
0x180042e09  mov     [rsp+4D8h+var_478], ecx
0x180042e0d  lea     rcx, [rsp+4D8h+FileName]; unsigned __int16 *
0x180042e15  mov     [rsp+4D8h+var_480], edx
0x180042e19  mov     [rsp+4D8h+var_488], r8d
0x180042e1e  lea     r8, a08x04x04x02x02; "%08x-%04x-%04x-%02x%02x-%02x%02x%02x%02"...
0x180042e25  mov     [rsp+4D8h+var_490], r9d
0x180042e2a  mov     r9d, [r14]
0x180042e2d  mov     [rsp+4D8h+var_498], r10d
0x180042e32  mov     [rsp+4D8h+var_4A0], r11d
0x180042e37  mov     [rsp+4D8h+var_4A8], ebx
0x180042e3b  mov     ebx, 104h
0x180042e40  mov     edx, ebx; unsigned __int64
0x180042e42  mov     dword ptr [rsp+4D8h+lpFilePart], edi
0x180042e46  mov     dword ptr [rsp+4D8h+lpBuffer], esi
0x180042e4a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180042e4f  xor     eax, eax
0x180042e51  mov     [rsp+4D8h+var_250], ax
0x180042e59  mov     rax, cs:?TracePrinter@@3P6AKPEAGZZEA; ulong (*TracePrinter)(ushort *,...)
0x180042e60  test    rax, rax
0x180042e63  jz      short loc_180042E89
0x180042e65  cmp     cs:?DebugExtPrint@@3HA, 0; int DebugExtPrint
0x180042e6c  lea     rdx, [rsp+4D8h+FileName]
0x180042e74  lea     rcx, aTryingSearchpa; "\tTrying SearchPath for file %s."
0x180042e7b  jnz     short loc_180042E84
0x180042e7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042e82  jmp     short loc_180042E89
0x180042e84  call    ?TracePrinterExt@@YAKPEBGZZ; TracePrinterExt(ushort const *,...)
0x180042e89  lea     rax, [rsp+4D8h+FilePart]
0x180042e8e  mov     r9d, ebx; nBufferLength
0x180042e91  mov     [rsp+4D8h+lpFilePart], rax; lpFilePart
0x180042e96  lea     rdx, [rsp+4D8h+FileName]; lpFileName
0x180042e9e  lea     rax, [rsp+4D8h+Buffer]
0x180042ea6  xor     r8d, r8d; lpExtension
0x180042ea9  mov     rcx, rbp; lpPath
0x180042eac  mov     [rsp+4D8h+lpBuffer], rax; lpBuffer
0x180042eb1  call    cs:__imp_SearchPathW
0x180042eb7  test    eax, eax
0x180042eb9  jz      loc_180042F44
0x180042ebf  cmp     eax, ebx
0x180042ec1  jg      short loc_180042F0B
0x180042ec3  mov     rax, cs:?TracePrinter@@3P6AKPEAGZZEA; ulong (*TracePrinter)(ushort *,...)
0x180042eca  test    rax, rax
0x180042ecd  jz      short loc_180042EEB
0x180042ecf  cmp     cs:?DebugExtPrint@@3HA, 0; int DebugExtPrint
0x180042ed6  lea     rcx, aSuccess; " - Success\n"
0x180042edd  jnz     short loc_180042EE6
0x180042edf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042ee4  jmp     short loc_180042EEB
0x180042ee6  call    ?TracePrinterExt@@YAKPEBGZZ; TracePrinterExt(ushort const *,...)
0x180042eeb  mov     rdx, r15; void *
0x180042eee  lea     rcx, [rsp+4D8h+Buffer]; FileName
0x180042ef6  call    GetTraceGuidsW
0x180042efb  mov     ecx, eax
0x180042efd  mov     ebx, 2
0x180042f02  xor     eax, eax
0x180042f04  test    ecx, ecx
0x180042f06  cmovnz  ebx, eax
0x180042f09  jmp     short loc_180042F4C
0x180042f0b  mov     r10, cs:?TracePrinter@@3P6AKPEAGZZEA; ulong (*TracePrinter)(ushort *,...)
0x180042f12  test    r10, r10
0x180042f15  jz      short loc_180042F44
0x180042f17  cmp     cs:?DebugExtPrint@@3HA, 0; int DebugExtPrint
0x180042f1e  lea     rdx, [rsp+4D8h+FileName]
0x180042f26  mov     r9d, eax
0x180042f29  lea     rcx, aFileSNameWasTo; "\nFile %s name was too Long? Max = %d(M"...
0x180042f30  mov     r8d, ebx
0x180042f33  jnz     short loc_180042F3F
0x180042f35  mov     rax, r10
0x180042f38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042f3d  jmp     short loc_180042F44
0x180042f3f  call    ?TracePrinterExt@@YAKPEBGZZ; TracePrinterExt(ushort const *,...)
0x180042f44  call    cs:__imp_GetLastError
0x180042f4a  mov     ebx, eax
0x180042f4c  mov     eax, ebx
0x180042f4e  mov     rcx, [rsp+4D8h+var_38]
0x180042f56  xor     rcx, rsp; StackCookie
0x180042f59  call    __security_check_cookie
0x180042f5e  mov     rbx, [rsp+4D8h+arg_18]
0x180042f66  add     rsp, 4B0h
0x180042f6d  pop     r15
0x180042f6f  pop     r14
0x180042f71  pop     rdi
0x180042f72  pop     rsi
0x180042f73  pop     rbp
0x180042f74  retn
```
