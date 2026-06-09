# CRdpDrUtil::PrinterIsTS(ushort *)

- ea: `0x1800193e0`
- end: `0x180019486`
- name: `?PrinterIsTS@CRdpDrUtil@@QEAAHPEAG@Z`
- size: `166`
- prototype: `int(CRdpDrUtil *__hidden this, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180016e70`

## callees

- `0x1800193e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019473`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019473`
- `WINSPOOL!GetPrinterDataW` at `0x18001945a`
- `WINSPOOL!GetPrinterDataW` at `0x18001945a`
- `WINSPOOL!OpenPrinterW` at `0x18001942a`
- `WINSPOOL!OpenPrinterW` at `0x18001942a`
- `WINSPOOL!ClosePrinter` at `0x18001946b`
- `WINSPOOL!ClosePrinter` at `0x18001946b`

## pseudocode

```c
__int64 __fastcall CRdpDrUtil::PrinterIsTS(CRdpDrUtil *this, unsigned __int16 *a2)
{
  unsigned int v2; // ebx
  HANDLE phPrinter; // [rsp+30h] [rbp-20h] BYREF
  struct _PRINTER_DEFAULTSW pDefault; // [rsp+38h] [rbp-18h] BYREF
  DWORD pcbNeeded; // [rsp+60h] [rbp+10h] BYREF
  int v7; // [rsp+64h] [rbp+14h]
  int pData; // [rsp+70h] [rbp+20h] BYREF
  DWORD pType; // [rsp+78h] [rbp+28h] BYREF

  v7 = HIDWORD(this);
  pType = 0;
  pData = 0;
  pcbNeeded = 0;
  phPrinter = 0;
  *(_OWORD *)&pDefault.pDatatype = 0;
  *(_QWORD *)&pDefault.DesiredAccess = 983052;
  v2 = OpenPrinterW(a2, &phPrinter, &pDefault);
  if ( v2 )
  {
    v2 = GetPrinterDataW(phPrinter, (LPWSTR)L"TSSessionID", &pType, (LPBYTE)&pData, 4u, &pcbNeeded) == 0;
    ClosePrinter(phPrinter);
  }
  else
  {
    GetLastError();
  }
  return v2;
}

```

## disassembly

```asm
0x1800193e0  mov     [rsp-8+arg_8], rbx
0x1800193e5  mov     qword ptr [rsp-8+arg_0], rcx
0x1800193ea  push    rbp
0x1800193eb  mov     rbp, rsp
0x1800193ee  sub     rsp, 50h
0x1800193f2  mov     rcx, rdx; pPrinterName
0x1800193f5  mov     [rbp+pType], 0
0x1800193fc  xorps   xmm0, xmm0
0x1800193ff  mov     [rbp+pData], 0
0x180019406  lea     rdx, [rbp+phPrinter]; phPrinter
0x18001940a  mov     [rbp+arg_0], 0
0x180019411  lea     r8, [rbp+pDefault]; pDefault
0x180019415  mov     [rbp+phPrinter], 0
0x18001941d  movdqu  xmmword ptr [rbp+pDefault.pDatatype], xmm0
0x180019422  mov     qword ptr [rbp+pDefault.DesiredAccess], 0F000Ch
0x18001942a  call    cs:__imp_OpenPrinterW
0x180019430  mov     ebx, eax
0x180019432  test    eax, eax
0x180019434  jz      short loc_180019473
0x180019436  mov     rcx, [rbp+phPrinter]; hPrinter
0x18001943a  lea     rax, [rbp+arg_0]
0x18001943e  mov     [rsp+50h+pcbNeeded], rax; pcbNeeded
0x180019443  lea     r9, [rbp+pData]; pData
0x180019447  lea     r8, [rbp+pType]; pType
0x18001944b  mov     [rsp+50h+nSize], 4; nSize
0x180019453  lea     rdx, pValueName; "TSSessionID"
0x18001945a  call    cs:__imp_GetPrinterDataW
0x180019460  mov     rcx, [rbp+phPrinter]; hPrinter
0x180019464  xor     ebx, ebx
0x180019466  test    eax, eax
0x180019468  setz    bl
0x18001946b  call    cs:__imp_ClosePrinter
0x180019471  jmp     short loc_180019479
0x180019473  call    cs:__imp_GetLastError
0x180019479  mov     eax, ebx
0x18001947b  mov     rbx, [rsp+50h+arg_8]
0x180019480  add     rsp, 50h
0x180019484  pop     rbp
0x180019485  retn
```
