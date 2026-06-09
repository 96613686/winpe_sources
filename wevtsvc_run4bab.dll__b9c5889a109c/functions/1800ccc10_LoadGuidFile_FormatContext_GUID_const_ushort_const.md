# LoadGuidFile(FormatContext *,_GUID const *,ushort const *)

- ea: `0x1800ccc10`
- end: `0x1800cce01`
- name: `?LoadGuidFile@@YAKPEAUFormatContext@@PEBU_GUID@@PEBG@Z`
- size: `497`
- prototype: `unsigned int __fastcall(struct FormatContext *, const struct _GUID *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x1800cc044`

## callees

- `0x180070d7c`
- `0x18009aee0`
- `0x1800c9258`
- `0x1800c9394`
- `0x1800ccc10`
- `0x1800cce68`
- `0x1800dd010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ccdd0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ccdd0`
- `api-ms-win-core-processenvironment-l1-1-0!SearchPathW` at `0x1800ccd3d`
- `api-ms-win-core-processenvironment-l1-1-0!SearchPathW` at `0x1800ccd3d`

## string_xrefs

- `0x1800ccd00`: `	Trying SearchPath for file %s.`
- `0x1800ccdb5`: `\nFile %s name was too Long? Max = %d(MAX_PATH), required = %d.\n`

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
0x1800ccc10  mov     [rsp+arg_18], rbx
0x1800ccc15  push    rbp
0x1800ccc16  push    rsi
0x1800ccc17  push    rdi
0x1800ccc18  push    r14
0x1800ccc1a  push    r15
0x1800ccc1c  sub     rsp, 4B0h
0x1800ccc23  mov     rax, cs:__security_cookie
0x1800ccc2a  xor     rax, rsp
0x1800ccc2d  mov     [rsp+4D8h+var_38], rax
0x1800ccc35  mov     [rsp+4D8h+FilePart], 0
0x1800ccc3e  mov     rbp, r8
0x1800ccc41  mov     r14, rdx
0x1800ccc44  mov     r15, rcx
0x1800ccc47  test    r8, r8
0x1800ccc4a  jnz     short loc_1800CCC5F
0x1800ccc4c  xor     ebx, ebx
0x1800ccc4e  call    GetTraceFormatSearchPathW
0x1800ccc53  mov     rbp, rax
0x1800ccc56  test    rax, rax
0x1800ccc59  jz      loc_1800CCDD8
0x1800ccc5f  movzx   ecx, byte ptr [r14+0Eh]
0x1800ccc64  movzx   edx, byte ptr [r14+0Dh]
0x1800ccc69  movzx   r8d, byte ptr [r14+0Ch]
0x1800ccc6e  movzx   r9d, byte ptr [r14+0Bh]
0x1800ccc73  movzx   ebx, byte ptr [r14+8]
0x1800ccc78  movzx   eax, byte ptr [r14+0Fh]
0x1800ccc7d  movzx   r10d, byte ptr [r14+0Ah]
0x1800ccc82  movzx   r11d, byte ptr [r14+9]
0x1800ccc87  movzx   edi, word ptr [r14+6]
0x1800ccc8c  movzx   esi, word ptr [r14+4]
0x1800ccc91  mov     [rsp+4D8h+var_470], eax
0x1800ccc95  mov     [rsp+4D8h+var_478], ecx
0x1800ccc99  lea     rcx, [rsp+4D8h+FileName]; unsigned __int16 *
0x1800ccca1  mov     [rsp+4D8h+var_480], edx
0x1800ccca5  mov     [rsp+4D8h+var_488], r8d
0x1800cccaa  lea     r8, a08x04x04x02x02_1; "%08x-%04x-%04x-%02x%02x-%02x%02x%02x%02"...
0x1800cccb1  mov     [rsp+4D8h+var_490], r9d
0x1800cccb6  mov     r9d, [r14]
0x1800cccb9  mov     [rsp+4D8h+var_498], r10d
0x1800cccbe  mov     [rsp+4D8h+var_4A0], r11d
0x1800cccc3  mov     [rsp+4D8h+var_4A8], ebx
0x1800cccc7  mov     ebx, 104h
0x1800ccccc  mov     edx, ebx; unsigned __int64
0x1800cccce  mov     dword ptr [rsp+4D8h+lpFilePart], edi
0x1800cccd2  mov     dword ptr [rsp+4D8h+lpBuffer], esi
0x1800cccd6  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800cccdb  xor     eax, eax
0x1800cccdd  mov     [rsp+4D8h+var_250], ax
0x1800ccce5  mov     rax, cs:?TracePrinter@@3P6AKPEAGZZEA; ulong (*TracePrinter)(ushort *,...)
0x1800cccec  test    rax, rax
0x1800cccef  jz      short loc_1800CCD15
0x1800cccf1  cmp     cs:?DebugExtPrint@@3HA, 0; int DebugExtPrint
0x1800cccf8  lea     rdx, [rsp+4D8h+FileName]
0x1800ccd00  lea     rcx, aTryingSearchpa; "\tTrying SearchPath for file %s."
0x1800ccd07  jnz     short loc_1800CCD10
0x1800ccd09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ccd0e  jmp     short loc_1800CCD15
0x1800ccd10  call    ?TracePrinterExt@@YAKPEBGZZ; TracePrinterExt(ushort const *,...)
0x1800ccd15  lea     rax, [rsp+4D8h+FilePart]
0x1800ccd1a  mov     r9d, ebx; nBufferLength
0x1800ccd1d  mov     [rsp+4D8h+lpFilePart], rax; lpFilePart
0x1800ccd22  lea     rdx, [rsp+4D8h+FileName]; lpFileName
0x1800ccd2a  lea     rax, [rsp+4D8h+Buffer]
0x1800ccd32  xor     r8d, r8d; lpExtension
0x1800ccd35  mov     rcx, rbp; lpPath
0x1800ccd38  mov     [rsp+4D8h+lpBuffer], rax; lpBuffer
0x1800ccd3d  call    cs:__imp_SearchPathW
0x1800ccd43  test    eax, eax
0x1800ccd45  jz      loc_1800CCDD0
0x1800ccd4b  cmp     eax, ebx
0x1800ccd4d  jg      short loc_1800CCD97
0x1800ccd4f  mov     rax, cs:?TracePrinter@@3P6AKPEAGZZEA; ulong (*TracePrinter)(ushort *,...)
0x1800ccd56  test    rax, rax
0x1800ccd59  jz      short loc_1800CCD77
0x1800ccd5b  cmp     cs:?DebugExtPrint@@3HA, 0; int DebugExtPrint
0x1800ccd62  lea     rcx, aSuccess; " - Success\n"
0x1800ccd69  jnz     short loc_1800CCD72
0x1800ccd6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ccd70  jmp     short loc_1800CCD77
0x1800ccd72  call    ?TracePrinterExt@@YAKPEBGZZ; TracePrinterExt(ushort const *,...)
0x1800ccd77  mov     rdx, r15; void *
0x1800ccd7a  lea     rcx, [rsp+4D8h+Buffer]; FileName
0x1800ccd82  call    GetTraceGuidsW
0x1800ccd87  mov     ecx, eax
0x1800ccd89  mov     ebx, 2
0x1800ccd8e  xor     eax, eax
0x1800ccd90  test    ecx, ecx
0x1800ccd92  cmovnz  ebx, eax
0x1800ccd95  jmp     short loc_1800CCDD8
0x1800ccd97  mov     r10, cs:?TracePrinter@@3P6AKPEAGZZEA; ulong (*TracePrinter)(ushort *,...)
0x1800ccd9e  test    r10, r10
0x1800ccda1  jz      short loc_1800CCDD0
0x1800ccda3  cmp     cs:?DebugExtPrint@@3HA, 0; int DebugExtPrint
0x1800ccdaa  lea     rdx, [rsp+4D8h+FileName]
0x1800ccdb2  mov     r9d, eax
0x1800ccdb5  lea     rcx, aFileSNameWasTo; "\nFile %s name was too Long? Max = %d(M"...
0x1800ccdbc  mov     r8d, ebx
0x1800ccdbf  jnz     short loc_1800CCDCB
0x1800ccdc1  mov     rax, r10
0x1800ccdc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ccdc9  jmp     short loc_1800CCDD0
0x1800ccdcb  call    ?TracePrinterExt@@YAKPEBGZZ; TracePrinterExt(ushort const *,...)
0x1800ccdd0  call    cs:__imp_GetLastError
0x1800ccdd6  mov     ebx, eax
0x1800ccdd8  mov     eax, ebx
0x1800ccdda  mov     rcx, [rsp+4D8h+var_38]
0x1800ccde2  xor     rcx, rsp; StackCookie
0x1800ccde5  call    __security_check_cookie
0x1800ccdea  mov     rbx, [rsp+4D8h+arg_18]
0x1800ccdf2  add     rsp, 4B0h
0x1800ccdf9  pop     r15
0x1800ccdfb  pop     r14
0x1800ccdfd  pop     rdi
0x1800ccdfe  pop     rsi
0x1800ccdff  pop     rbp
0x1800cce00  retn
```
