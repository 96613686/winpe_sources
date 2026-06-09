# GetTraceGuidsW

- ea: `0x1800c9394`
- end: `0x1800c9486`
- name: `GetTraceGuidsW`
- size: `242`
- prototype: `__int64 __fastcall(wchar_t *FileName, void *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800ccc10`

## callees

- `0x1800c9394`
- `0x1800c9db0`
- `0x1800cce68`
- `0x1800dd010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wfopen` at `0x1800c93de`
- `api-ms-win-crt-private-l1-1-0!_o__wfopen` at `0x1800c93de`
- `api-ms-win-crt-private-l1-1-0!_o_fclose` at `0x1800c946e`
- `api-ms-win-crt-private-l1-1-0!_o_fclose` at `0x1800c946e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c9400`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c9419`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c9400`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c9419`

## string_xrefs

- `0x1800c93bf`: `\n	Opening file %s`

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
0x1800c9394  mov     [rsp+arg_0], rbx
0x1800c9399  mov     [rsp+arg_8], rsi
0x1800c939e  push    rdi
0x1800c939f  sub     rsp, 20h
0x1800c93a3  mov     rax, cs:?TracePrinter@@3P6AKPEAGZZEA; ulong (*TracePrinter)(ushort *,...)
0x1800c93aa  mov     rsi, rdx
0x1800c93ad  mov     rbx, rcx
0x1800c93b0  test    rax, rax
0x1800c93b3  jz      short loc_1800C93D4
0x1800c93b5  cmp     cs:?DebugExtPrint@@3HA, 0; int DebugExtPrint
0x1800c93bc  mov     rdx, rcx
0x1800c93bf  lea     rcx, aOpeningFileS; "\n\tOpening file %s"
0x1800c93c6  jnz     short loc_1800C93CF
0x1800c93c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c93cd  jmp     short loc_1800C93D4
0x1800c93cf  call    ?TracePrinterExt@@YAKPEBGZZ; TracePrinterExt(ushort const *,...)
0x1800c93d4  lea     rdx, aR; "r"
0x1800c93db  mov     rcx, rbx; FileName
0x1800c93de  call    cs:__imp__wfopen
0x1800c93e4  mov     rdi, rax
0x1800c93e7  test    rax, rax
0x1800c93ea  jnz     short loc_1800C9431
0x1800c93ec  mov     rbx, cs:?TracePrinter@@3P6AKPEAGZZEA; ulong (*TracePrinter)(ushort *,...)
0x1800c93f3  test    rbx, rbx
0x1800c93f6  jz      short loc_1800C942D
0x1800c93f8  cmp     cs:?DebugExtPrint@@3HA, eax; int DebugExtPrint
0x1800c93fe  jnz     short loc_1800C9419
0x1800c9400  call    cs:__imp_GetLastError
0x1800c9406  mov     edx, eax
0x1800c9408  lea     rcx, aStatus0x08x; " (Status = 0x%08X)\n"
0x1800c940f  mov     rax, rbx
0x1800c9412  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c9417  jmp     short loc_1800C942D
0x1800c9419  call    cs:__imp_GetLastError
0x1800c941f  mov     edx, eax
0x1800c9421  lea     rcx, aStatus0x08x; " (Status = 0x%08X)\n"
0x1800c9428  call    ?TracePrinterExt@@YAKPEBGZZ; TracePrinterExt(ushort const *,...)
0x1800c942d  xor     eax, eax
0x1800c942f  jmp     short loc_1800C9476
0x1800c9431  mov     rax, cs:?TracePrinter@@3P6AKPEAGZZEA; ulong (*TracePrinter)(ushort *,...)
0x1800c9438  test    rax, rax
0x1800c943b  jz      short loc_1800C9459
0x1800c943d  cmp     cs:?DebugExtPrint@@3HA, 0; int DebugExtPrint
0x1800c9444  lea     rcx, aSuccess_0; " Success\n"
0x1800c944b  jnz     short loc_1800C9454
0x1800c944d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c9452  jmp     short loc_1800C9459
0x1800c9454  call    ?TracePrinterExt@@YAKPEBGZZ; TracePrinterExt(ushort const *,...)
0x1800c9459  mov     r9, rsi; void *
0x1800c945c  xor     r8d, r8d; unsigned int
0x1800c945f  xor     edx, edx; unsigned __int16 *
0x1800c9461  mov     rcx, rdi; struct _iobuf *
0x1800c9464  call    ?InternalParseTMForBuffer@@YAKPEAU_iobuf@@PEBGKPEAX@Z; InternalParseTMForBuffer(_iobuf *,ushort const *,ulong,void *)
0x1800c9469  mov     rcx, rdi; Stream
0x1800c946c  mov     ebx, eax
0x1800c946e  call    cs:__imp_fclose
0x1800c9474  mov     eax, ebx
0x1800c9476  mov     rbx, [rsp+28h+arg_0]
0x1800c947b  mov     rsi, [rsp+28h+arg_8]
0x1800c9480  add     rsp, 20h
0x1800c9484  pop     rdi
0x1800c9485  retn
```
