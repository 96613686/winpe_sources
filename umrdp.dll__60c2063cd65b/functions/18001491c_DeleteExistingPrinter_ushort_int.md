# DeleteExistingPrinter(ushort *,int *)

- ea: `0x18001491c`
- end: `0x1800149a8`
- name: `?DeleteExistingPrinter@@YAKPEAGPEAH@Z`
- size: `140`
- prototype: `__int64 __fastcall(unsigned __int16 *, int *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800032f0`

## callees

- `0x18001491c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014984`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014984`
- `WINSPOOL!OpenPrinterW` at `0x18001494d`
- `WINSPOOL!OpenPrinterW` at `0x18001494d`
- `WINSPOOL!SetPrinterW` at `0x18001496b`
- `WINSPOOL!SetPrinterW` at `0x18001496b`
- `WINSPOOL!DeletePrinter` at `0x18001497a`
- `WINSPOOL!DeletePrinter` at `0x18001497a`
- `WINSPOOL!ClosePrinter` at `0x180014991`
- `WINSPOOL!ClosePrinter` at `0x180014991`

## pseudocode

```c
__int64 __fastcall DeleteExistingPrinter(unsigned __int16 *a1, int *a2)
{
  DWORD LastError; // ebx
  HANDLE v4; // rcx
  struct _PRINTER_DEFAULTSW v6; // [rsp+20h] [rbp-28h] BYREF
  HANDLE hPrinter; // [rsp+60h] [rbp+18h] BYREF

  hPrinter = (HANDLE)-1LL;
  *(_QWORD *)&v6.DesiredAccess = 983052;
  LastError = 0;
  *(_OWORD *)&v6.pDatatype = 0;
  if ( OpenPrinterW(a1, &hPrinter, &v6) )
  {
    v4 = hPrinter;
    *a2 = 1;
    if ( !SetPrinterW(v4, 0, 0, 3u) || !DeletePrinter(hPrinter) )
      LastError = GetLastError();
    ClosePrinter(hPrinter);
  }
  else
  {
    *a2 = 0;
  }
  return LastError;
}

```

## disassembly

```asm
0x18001491c  mov     rax, rsp
0x18001491f  mov     [rax+8], rbx
0x180014923  push    rdi
0x180014924  sub     rsp, 40h
0x180014928  mov     rdi, rdx
0x18001492b  mov     qword ptr [rax+18h], 0FFFFFFFFFFFFFFFFh
0x180014933  xorps   xmm0, xmm0
0x180014936  mov     qword ptr [rax-18h], 0F000Ch
0x18001493e  lea     rdx, [rax+18h]; phPrinter
0x180014942  xor     ebx, ebx
0x180014944  lea     r8, [rax-28h]; pDefault
0x180014948  movdqu  xmmword ptr [rax-28h], xmm0
0x18001494d  call    cs:__imp_OpenPrinterW
0x180014953  test    eax, eax
0x180014955  jz      short loc_180014999
0x180014957  mov     rcx, [rsp+48h+hPrinter]; hPrinter
0x18001495c  lea     r9d, [rbx+3]; Command
0x180014960  xor     r8d, r8d; pPrinter
0x180014963  mov     dword ptr [rdi], 1
0x180014969  xor     edx, edx; Level
0x18001496b  call    cs:__imp_SetPrinterW
0x180014971  test    eax, eax
0x180014973  jz      short loc_180014984
0x180014975  mov     rcx, [rsp+48h+hPrinter]; hPrinter
0x18001497a  call    cs:__imp_DeletePrinter
0x180014980  test    eax, eax
0x180014982  jnz     short loc_18001498C
0x180014984  call    cs:__imp_GetLastError
0x18001498a  mov     ebx, eax
0x18001498c  mov     rcx, [rsp+48h+hPrinter]; hPrinter
0x180014991  call    cs:__imp_ClosePrinter
0x180014997  jmp     short loc_18001499B
0x180014999  mov     [rdi], ebx
0x18001499b  mov     eax, ebx
0x18001499d  mov     rbx, [rsp+48h+arg_0]
0x1800149a2  add     rsp, 40h
0x1800149a6  pop     rdi
0x1800149a7  retn
```
