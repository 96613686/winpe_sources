# GetTraceGuidsW

- ea: `0x18003fb28`
- end: `0x18003fc1a`
- name: `GetTraceGuidsW`
- size: `242`
- prototype: `__int64 __fastcall(wchar_t *FileName, struct FormatContext *)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x18002b910`
- `0x18004260c`
- `0x180042d84`

## callees

- `0x18003fb28`
- `0x1800407d0`
- `0x180042f7c`
- `0x18004c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wfopen` at `0x18003fb72`
- `api-ms-win-crt-private-l1-1-0!_o__wfopen` at `0x18003fb72`
- `api-ms-win-crt-private-l1-1-0!_o_fclose` at `0x18003fc02`
- `api-ms-win-crt-private-l1-1-0!_o_fclose` at `0x18003fc02`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003fb94`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003fbad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003fb94`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003fbad`

## string_xrefs

- `0x18003fb53`: `\n	Opening file %s`

## pseudocode

```c
__int64 __fastcall GetTraceGuidsW(wchar_t *FileName, struct FormatContext *a2)
{
  FILE *v4; // rdi
  unsigned int (*v5)(unsigned __int16 *, ...); // rbx
  DWORD v6; // eax
  DWORD LastError; // eax
  unsigned int v9; // ebx

  if ( TracePrinter )
  {
    if ( DebugExtPrint )
      TracePrinterExt((wchar_t *)L"\n\tOpening file %s", FileName);
    else
      TracePrinter(L"\n\tOpening file %s", FileName);
  }
  v4 = _wfopen(FileName, L"r");
  if ( v4 )
  {
    if ( TracePrinter )
    {
      if ( DebugExtPrint )
        TracePrinterExt((wchar_t *)L" Success\n");
      else
        TracePrinter(L" Success\n");
    }
    v9 = InternalParseTMForBuffer(v4, 0, 0, a2);
    fclose(v4);
    return v9;
  }
  else
  {
    v5 = TracePrinter;
    if ( TracePrinter )
    {
      if ( DebugExtPrint )
      {
        LastError = GetLastError();
        TracePrinterExt((wchar_t *)L" (Status = 0x%08X)\n", LastError);
      }
      else
      {
        v6 = GetLastError();
        v5(L" (Status = 0x%08X)\n", v6);
      }
    }
    return 0;
  }
}

```

## disassembly

```asm
0x18003fb28  mov     [rsp+arg_0], rbx
0x18003fb2d  mov     [rsp+arg_8], rsi
0x18003fb32  push    rdi
0x18003fb33  sub     rsp, 20h
0x18003fb37  mov     rax, cs:?TracePrinter@@3P6AKPEAGZZEA; ulong (*TracePrinter)(ushort *,...)
0x18003fb3e  mov     rsi, rdx
0x18003fb41  mov     rbx, rcx
0x18003fb44  test    rax, rax
0x18003fb47  jz      short loc_18003FB68
0x18003fb49  cmp     cs:?DebugExtPrint@@3HA, 0; int DebugExtPrint
0x18003fb50  mov     rdx, rcx
0x18003fb53  lea     rcx, aOpeningFileS; "\n\tOpening file %s"
0x18003fb5a  jnz     short loc_18003FB63
0x18003fb5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fb61  jmp     short loc_18003FB68
0x18003fb63  call    ?TracePrinterExt@@YAKPEBGZZ; TracePrinterExt(ushort const *,...)
0x18003fb68  lea     rdx, aR; "r"
0x18003fb6f  mov     rcx, rbx; FileName
0x18003fb72  call    cs:__imp__wfopen
0x18003fb78  mov     rdi, rax
0x18003fb7b  test    rax, rax
0x18003fb7e  jnz     short loc_18003FBC5
0x18003fb80  mov     rbx, cs:?TracePrinter@@3P6AKPEAGZZEA; ulong (*TracePrinter)(ushort *,...)
0x18003fb87  test    rbx, rbx
0x18003fb8a  jz      short loc_18003FBC1
0x18003fb8c  cmp     cs:?DebugExtPrint@@3HA, eax; int DebugExtPrint
0x18003fb92  jnz     short loc_18003FBAD
0x18003fb94  call    cs:__imp_GetLastError
0x18003fb9a  mov     edx, eax
0x18003fb9c  lea     rcx, aStatus0x08x; " (Status = 0x%08X)\n"
0x18003fba3  mov     rax, rbx
0x18003fba6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fbab  jmp     short loc_18003FBC1
0x18003fbad  call    cs:__imp_GetLastError
0x18003fbb3  mov     edx, eax
0x18003fbb5  lea     rcx, aStatus0x08x; " (Status = 0x%08X)\n"
0x18003fbbc  call    ?TracePrinterExt@@YAKPEBGZZ; TracePrinterExt(ushort const *,...)
0x18003fbc1  xor     eax, eax
0x18003fbc3  jmp     short loc_18003FC0A
0x18003fbc5  mov     rax, cs:?TracePrinter@@3P6AKPEAGZZEA; ulong (*TracePrinter)(ushort *,...)
0x18003fbcc  test    rax, rax
0x18003fbcf  jz      short loc_18003FBED
0x18003fbd1  cmp     cs:?DebugExtPrint@@3HA, 0; int DebugExtPrint
0x18003fbd8  lea     rcx, aSuccess_0; " Success\n"
0x18003fbdf  jnz     short loc_18003FBE8
0x18003fbe1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fbe6  jmp     short loc_18003FBED
0x18003fbe8  call    ?TracePrinterExt@@YAKPEBGZZ; TracePrinterExt(ushort const *,...)
0x18003fbed  mov     r9, rsi; void *
0x18003fbf0  xor     r8d, r8d; unsigned int
0x18003fbf3  xor     edx, edx; unsigned __int16 *
0x18003fbf5  mov     rcx, rdi; struct _iobuf *
0x18003fbf8  call    ?InternalParseTMForBuffer@@YAKPEAU_iobuf@@PEBGKPEAX@Z; InternalParseTMForBuffer(_iobuf *,ushort const *,ulong,void *)
0x18003fbfd  mov     rcx, rdi; Stream
0x18003fc00  mov     ebx, eax
0x18003fc02  call    cs:__imp_fclose
0x18003fc08  mov     eax, ebx
0x18003fc0a  mov     rbx, [rsp+28h+arg_0]
0x18003fc0f  mov     rsi, [rsp+28h+arg_8]
0x18003fc14  add     rsp, 20h
0x18003fc18  pop     rdi
0x18003fc19  retn
```
