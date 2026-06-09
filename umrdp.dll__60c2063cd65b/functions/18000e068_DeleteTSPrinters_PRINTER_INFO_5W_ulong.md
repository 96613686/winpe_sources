# DeleteTSPrinters(_PRINTER_INFO_5W *,ulong)

- ea: `0x18000e068`
- end: `0x18000e139`
- name: `?DeleteTSPrinters@@YAXPEAU_PRINTER_INFO_5W@@K@Z`
- size: `209`
- prototype: `void __fastcall(struct _PRINTER_INFO_5W *, unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800199f8`

## callees

- `0x18000e068`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e119`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e119`
- `WINSPOOL!OpenPrinterW` at `0x18000e0dd`
- `WINSPOOL!OpenPrinterW` at `0x18000e0dd`
- `WINSPOOL!SetPrinterW` at `0x18000e0f7`
- `WINSPOOL!SetPrinterW` at `0x18000e0f7`
- `WINSPOOL!DeletePrinter` at `0x18000e106`
- `WINSPOOL!DeletePrinter` at `0x18000e106`
- `WINSPOOL!ClosePrinter` at `0x18000e111`
- `WINSPOOL!ClosePrinter` at `0x18000e111`

## pseudocode

```c
void __fastcall DeleteTSPrinters(struct _PRINTER_INFO_5W *a1, unsigned int a2)
{
  unsigned int i; // ebx
  __int64 v5; // rax
  WCHAR *pPrinterName; // rcx
  LPWSTR pPortName; // rax
  struct _PRINTER_DEFAULTSW pDefault; // [rsp+20h] [rbp-28h] BYREF
  HANDLE phPrinter; // [rsp+60h] [rbp+18h] BYREF

  if ( a2 )
  {
    phPrinter = 0;
    *(_OWORD *)&pDefault.pDatatype = 0;
    *(_QWORD *)&pDefault.DesiredAccess = 983052;
    for ( i = 0; i < a2; ++i )
    {
      v5 = i;
      pPrinterName = a1[v5].pPrinterName;
      if ( pPrinterName )
      {
        pPortName = a1[v5].pPortName;
        if ( pPortName )
        {
          if ( *pPortName == 84 && pPortName[1] == 83 && (unsigned __int16)(pPortName[2] - 48) <= 9u )
          {
            if ( OpenPrinterW(pPrinterName, &phPrinter, &pDefault) )
            {
              if ( SetPrinterW(phPrinter, 0, 0, 3u) )
                DeletePrinter(phPrinter);
              ClosePrinter(phPrinter);
            }
            else
            {
              GetLastError();
            }
          }
        }
      }
    }
  }
}

```

## disassembly

```asm
0x18000e068  test    edx, edx
0x18000e06a  jz      locret_18000E138
0x18000e070  mov     rax, rsp
0x18000e073  mov     [rax+8], rbx
0x18000e077  mov     [rax+10h], rsi
0x18000e07b  push    rdi
0x18000e07c  sub     rsp, 40h
0x18000e080  xorps   xmm0, xmm0
0x18000e083  mov     qword ptr [rax+18h], 0
0x18000e08b  movdqu  xmmword ptr [rax-28h], xmm0
0x18000e090  mov     esi, edx
0x18000e092  mov     qword ptr [rax-18h], 0F000Ch
0x18000e09a  mov     rdi, rcx
0x18000e09d  xor     ebx, ebx
0x18000e09f  mov     eax, ebx
0x18000e0a1  shl     rax, 5
0x18000e0a5  mov     rcx, [rax+rdi]; pPrinterName
0x18000e0a9  test    rcx, rcx
0x18000e0ac  jz      short loc_18000E11F
0x18000e0ae  mov     rax, [rax+rdi+8]
0x18000e0b3  test    rax, rax
0x18000e0b6  jz      short loc_18000E11F
0x18000e0b8  cmp     word ptr [rax], 54h ; 'T'
0x18000e0bc  jnz     short loc_18000E11F
0x18000e0be  cmp     word ptr [rax+2], 53h ; 'S'
0x18000e0c3  jnz     short loc_18000E11F
0x18000e0c5  movzx   eax, word ptr [rax+4]
0x18000e0c9  sub     ax, 30h ; '0'
0x18000e0cd  cmp     ax, 9
0x18000e0d1  ja      short loc_18000E11F
0x18000e0d3  lea     r8, [rsp+48h+pDefault]; pDefault
0x18000e0d8  lea     rdx, [rsp+48h+phPrinter]; phPrinter
0x18000e0dd  call    cs:__imp_OpenPrinterW
0x18000e0e3  test    eax, eax
0x18000e0e5  jz      short loc_18000E119
0x18000e0e7  mov     rcx, [rsp+48h+phPrinter]; hPrinter
0x18000e0ec  mov     r9d, 3; Command
0x18000e0f2  xor     r8d, r8d; pPrinter
0x18000e0f5  xor     edx, edx; Level
0x18000e0f7  call    cs:__imp_SetPrinterW
0x18000e0fd  test    eax, eax
0x18000e0ff  jz      short loc_18000E10C
0x18000e101  mov     rcx, [rsp+48h+phPrinter]; hPrinter
0x18000e106  call    cs:__imp_DeletePrinter
0x18000e10c  mov     rcx, [rsp+48h+phPrinter]; hPrinter
0x18000e111  call    cs:__imp_ClosePrinter
0x18000e117  jmp     short loc_18000E11F
0x18000e119  call    cs:__imp_GetLastError
0x18000e11f  inc     ebx
0x18000e121  cmp     ebx, esi
0x18000e123  jb      loc_18000E09F
0x18000e129  mov     rbx, [rsp+48h+arg_0]
0x18000e12e  mov     rsi, [rsp+48h+arg_8]
0x18000e133  add     rsp, 40h
0x18000e137  pop     rdi
0x18000e138  retn
```
