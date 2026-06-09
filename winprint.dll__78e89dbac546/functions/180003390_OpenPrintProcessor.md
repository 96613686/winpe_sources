# OpenPrintProcessor

- ea: `0x180003390`
- end: `0x180003854`
- name: `OpenPrintProcessor`
- size: `1220`
- prototype: `HANDLE __stdcall(LPWSTR pPrinterName, PPRINTPROCESSOROPENDATA pPrintProcessorOpenData)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting`

## callees

- `0x180002ee0`
- `0x180003390`
- `0x1800042a0`
- `0x180006100`
- `0x1800077b5`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800033f1`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800033f1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800035da`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003821`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800035da`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003821`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000353a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000353a`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalAlloc` at `0x180003414`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalAlloc` at `0x1800034a2`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalAlloc` at `0x180003414`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalAlloc` at `0x1800034a2`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18000351c`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18000352b`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180003549`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180003558`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180003567`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180003576`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180003585`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x1800035b0`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x1800037f2`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18000351c`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18000352b`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180003549`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180003558`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180003567`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180003576`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180003585`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x1800035b0`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x1800037f2`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000362d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000362d`
- `GDI32!CreateDCW` at `0x1800034e0`
- `GDI32!CreateDCW` at `0x1800034e0`
- `GDI32!DeleteDC` at `0x18000350d`
- `GDI32!DeleteDC` at `0x18000350d`
- `WINSPOOL!ClosePrinter` at `0x1800034fe`
- `WINSPOOL!ClosePrinter` at `0x180003805`
- `WINSPOOL!ClosePrinter` at `0x1800034fe`
- `WINSPOOL!ClosePrinter` at `0x180003805`
- `WINSPOOL!OpenPrinterW` at `0x1800035f3`
- `WINSPOOL!OpenPrinterW` at `0x1800037b2`
- `WINSPOOL!OpenPrinterW` at `0x1800035f3`
- `WINSPOOL!OpenPrinterW` at `0x1800037b2`

## pseudocode

```c
HANDLE __stdcall OpenPrintProcessor(LPWSTR pPrinterName, PPRINTPROCESSOROPENDATA pPrintProcessorOpenData)
{
  LPWSTR pDatatype; // rax
  unsigned __int16 * near *v5; // rax
  unsigned __int16 * near **v6; // rbx
  unsigned int i; // esi
  HANDLE result; // rax
  HANDLE v9; // rbx
  HDC DCW; // r15
  HLOCAL v11; // r14
  PDEVMODE pDevMode; // rax
  unsigned int dmCollate; // edx
  unsigned int v14; // r8d
  HLOCAL v15; // rax
  void *v16; // rcx
  HDC v17; // rcx
  void *v18; // rcx
  void *v19; // rcx
  void *v20; // rcx
  void *v21; // rcx
  void *v22; // rcx
  void *v23; // rcx
  void *v24; // rcx
  void *v25; // rcx
  unsigned __int16 *v26; // rax
  unsigned int v27; // edx
  unsigned __int16 v28; // r8
  wchar_t *v29; // rcx
  unsigned __int16 v30; // r8
  wchar_t *v31; // rcx
  unsigned __int8 *PrinterInfo; // rax
  unsigned int v33; // [rsp+78h] [rbp+10h] BYREF
  int v34; // [rsp+80h] [rbp+18h] BYREF
  HANDLE phPrinter; // [rsp+88h] [rbp+20h] BYREF

  phPrinter = 0;
  if ( !pPrintProcessorOpenData || (pDatatype = pPrintProcessorOpenData->pDatatype) == 0 || !*pDatatype )
  {
    SetLastError(0x57u);
    return 0;
  }
  v5 = Datatypes;
  v6 = &Datatypes;
  for ( i = 0; v5; ++i )
  {
    if ( !(unsigned int)_o__wcsicmp(v5, pPrintProcessorOpenData->pDatatype) )
      break;
    v5 = v6[1];
    ++v6;
  }
  result = LocalAlloc(0x40u, 0x80u);
  v9 = result;
  if ( result )
  {
    DCW = 0;
    v11 = 0;
    *(_OWORD *)result = 0;
    *((_OWORD *)result + 1) = 0;
    *((_OWORD *)result + 2) = 0;
    *((_OWORD *)result + 3) = 0;
    *((_OWORD *)result + 4) = 0;
    *((_OWORD *)result + 5) = 0;
    *((_OWORD *)result + 6) = 0;
    *((_OWORD *)result + 7) = 0;
    if ( i == 2 )
    {
LABEL_38:
      if ( !OpenPrinterW(pPrinterName, &phPrinter, 0) )
      {
LABEL_15:
        v16 = (void *)*((_QWORD *)v9 + 5);
        *(_DWORD *)v9 = 0;
        if ( v16 )
          ClosePrinter(v16);
        v17 = (HDC)*((_QWORD *)v9 + 13);
        if ( v17 )
          DeleteDC(v17);
        v18 = (void *)*((_QWORD *)v9 + 14);
        if ( v18 )
          LocalFree(v18);
        v19 = (void *)*((_QWORD *)v9 + 15);
        if ( v19 )
          LocalFree(v19);
        v20 = (void *)*((_QWORD *)v9 + 3);
        if ( v20 )
          CloseHandle(v20);
        v21 = (void *)*((_QWORD *)v9 + 6);
        if ( v21 )
          LocalFree(v21);
        v22 = (void *)*((_QWORD *)v9 + 9);
        if ( v22 )
          LocalFree(v22);
        v23 = (void *)*((_QWORD *)v9 + 7);
        if ( v23 )
          LocalFree(v23);
        v24 = (void *)*((_QWORD *)v9 + 8);
        if ( v24 )
          LocalFree(v24);
        v25 = (void *)*((_QWORD *)v9 + 10);
        if ( v25 )
          LocalFree(v25);
        *(_OWORD *)v9 = 0;
        *((_OWORD *)v9 + 1) = 0;
        *((_OWORD *)v9 + 2) = 0;
        *((_OWORD *)v9 + 3) = 0;
        *((_OWORD *)v9 + 4) = 0;
        *((_OWORD *)v9 + 5) = 0;
        *((_OWORD *)v9 + 6) = 0;
        *((_OWORD *)v9 + 7) = 0;
        LocalFree(v9);
        return 0;
      }
    }
    else
    {
      switch ( i )
      {
        case 0u:
        case 1u:
          goto LABEL_38;
        case 4u:
        case 5u:
        case 6u:
          pDevMode = pPrintProcessorOpenData->pDevMode;
          if ( !pPrintProcessorOpenData->pDevMode )
            break;
          dmCollate = (unsigned __int16)pDevMode->dmCollate;
          v14 = dmCollate + *(unsigned __int16 *)pDevMode->dmFormName;
          if ( v14 < dmCollate )
            goto LABEL_15;
          v15 = LocalAlloc(0x40u, v14);
          v11 = v15;
          if ( !v15 )
            goto LABEL_15;
          memcpy_0(
            v15,
            pPrintProcessorOpenData->pDevMode,
            (unsigned __int16)pPrintProcessorOpenData->pDevMode->dmCollate
          + (unsigned __int64)*(unsigned __int16 *)pPrintProcessorOpenData->pDevMode->dmFormName);
          break;
        case 7u:
          DCW = CreateDCW(&pszPort, pPrinterName, &pszPort, (const DEVMODEW *)pPrintProcessorOpenData->pDevMode);
          if ( !DCW )
            goto LABEL_15;
          break;
        case 8u:
          break;
        default:
          SetLastError(0x70Cu);
          goto LABEL_15;
      }
    }
    *((_DWORD *)v9 + 1) = 128;
    *(_DWORD *)v9 = 20561;
    *((_DWORD *)v9 + 22) = pPrintProcessorOpenData->JobId;
    *((_QWORD *)v9 + 5) = phPrinter;
    *((_QWORD *)v9 + 3) = CreateEventW(0, 1, 1, 0);
    *((_DWORD *)v9 + 8) = i;
    *((_QWORD *)v9 + 13) = DCW;
    *((_DWORD *)v9 + 23) = 1;
    *((_DWORD *)v9 + 24) = 8;
    *((_QWORD *)v9 + 6) = AllocSplStr(pPrinterName);
    *((_QWORD *)v9 + 9) = AllocSplStr(pPrintProcessorOpenData->pDatatype);
    *((_QWORD *)v9 + 7) = AllocSplStr(pPrintProcessorOpenData->pDocumentName);
    *((_QWORD *)v9 + 8) = AllocSplStr(pPrintProcessorOpenData->pOutputFile);
    *((_QWORD *)v9 + 10) = AllocSplStr(pPrintProcessorOpenData->pParameters);
    *((_QWORD *)v9 + 14) = v11;
    v26 = AllocSplStr(pPrintProcessorOpenData->pPrinterName);
    *((_QWORD *)v9 + 15) = v26;
    if ( *((_QWORD *)v9 + 3)
      && (!pPrinterName || *((_QWORD *)v9 + 6))
      && (!pPrintProcessorOpenData->pDatatype || *((_QWORD *)v9 + 9))
      && (!pPrintProcessorOpenData->pDocumentName || *((_QWORD *)v9 + 7))
      && (!pPrintProcessorOpenData->pOutputFile || *((_QWORD *)v9 + 8))
      && (!pPrintProcessorOpenData->pParameters || *((_QWORD *)v9 + 10))
      && (!pPrintProcessorOpenData->pPrinterName || v26) )
    {
      v29 = (wchar_t *)*((_QWORD *)v9 + 10);
      if ( v29 )
      {
        v34 = 0;
        LOWORD(v33) = 4;
        GetKeyValue(v29, L"COPIES", v28, (unsigned __int16 *)&v33, &v34);
        if ( (_WORD)v33 == 4 )
          *((_DWORD *)v9 + 23) = v34;
        if ( i == 7 )
        {
          v31 = (wchar_t *)*((_QWORD *)v9 + 10);
          LOWORD(v33) = 4;
          GetKeyValue(v31, L"TABS", v30, (unsigned __int16 *)&v33, &v34);
          if ( (_WORD)v33 == 4 )
          {
            if ( v34 )
              *((_DWORD *)v9 + 24) = v34;
          }
        }
      }
      if ( *((_DWORD *)v9 + 23) > 1u )
      {
        v33 = 0;
        if ( i >= 3 )
          OpenPrinterW(pPrinterName, &phPrinter, 0);
        if ( (char *)phPrinter - 1 > (char *)0xFFFFFFFFFFFFFFFDLL )
        {
          *((_DWORD *)v9 + 23) = 1;
        }
        else
        {
          PrinterInfo = GetPrinterInfo(phPrinter, v27, &v33);
          if ( PrinterInfo )
          {
            if ( (PrinterInfo[104] & 2) != 0 )
              *((_DWORD *)v9 + 23) = 1;
            LocalFree(PrinterInfo);
          }
          else
          {
            *((_DWORD *)v9 + 23) = 1;
          }
          if ( i >= 3 )
            ClosePrinter(phPrinter);
        }
      }
      return v9;
    }
    goto LABEL_15;
  }
  return result;
}

```

## disassembly

```asm
0x180003390  push    rbp
0x180003392  push    rdi
0x180003393  push    r12
0x180003395  sub     rsp, 50h
0x180003399  xor     r12d, r12d
0x18000339c  mov     rdi, rdx
0x18000339f  mov     [rsp+68h+phPrinter], r12
0x1800033a7  mov     rbp, rcx
0x1800033aa  test    rdx, rdx
0x1800033ad  jz      loc_18000381C
0x1800033b3  mov     rax, [rdx+8]
0x1800033b7  test    rax, rax
0x1800033ba  jz      loc_18000381C
0x1800033c0  cmp     [rax], r12w
0x1800033c4  jz      loc_18000381C
0x1800033ca  mov     rax, cs:?Datatypes@@3PAPEAGA; ushort * near * Datatypes
0x1800033d1  mov     [rsp+68h+var_20], rbx
0x1800033d6  lea     rbx, ?Datatypes@@3PAPEAGA; ushort * near * Datatypes
0x1800033dd  mov     [rsp+68h+var_28], rsi
0x1800033e2  mov     esi, r12d
0x1800033e5  test    rax, rax
0x1800033e8  jz      short loc_18000340A
0x1800033ea  mov     rdx, [rdi+8]
0x1800033ee  mov     rcx, rax
0x1800033f1  call    cs:__imp__o__wcsicmp
0x1800033f7  test    eax, eax
0x1800033f9  jz      short loc_18000340A
0x1800033fb  mov     rax, [rbx+8]
0x1800033ff  add     rbx, 8
0x180003403  inc     esi
0x180003405  test    rax, rax
0x180003408  jnz     short loc_1800033EA
0x18000340a  mov     edx, 80h; uBytes
0x18000340f  mov     ecx, 40h ; '@'; uFlags
0x180003414  call    cs:__imp_LocalAlloc
0x18000341a  mov     rbx, rax
0x18000341d  test    rax, rax
0x180003420  jz      loc_1800035C2
0x180003426  mov     [rsp+68h+var_30], r14
0x18000342b  xorps   xmm0, xmm0
0x18000342e  mov     [rsp+68h+var_38], r15
0x180003433  mov     r15, r12
0x180003436  mov     r14, r12
0x180003439  movups  xmmword ptr [rax], xmm0
0x18000343c  movups  xmmword ptr [rax+10h], xmm0
0x180003440  movups  xmmword ptr [rax+20h], xmm0
0x180003444  movups  xmmword ptr [rax+30h], xmm0
0x180003448  movups  xmmword ptr [rax+40h], xmm0
0x18000344c  movups  xmmword ptr [rax+50h], xmm0
0x180003450  movups  xmmword ptr [rax+60h], xmm0
0x180003454  movups  xmmword ptr [rax+70h], xmm0
0x180003458  cmp     esi, 2
0x18000345b  jz      loc_1800035E5; jumptable 000000018000347B cases 0,1
0x180003461  cmp     esi, 8; switch 9 cases
0x180003464  ja      def_18000347B; jumptable 000000018000347B default case, cases 2,3
0x18000346a  lea     rcx, __ImageBase
0x180003471  mov     eax, ds:(jpt_18000347B - 180000000h)[rcx+rsi*4]
0x180003478  add     rax, rcx
0x18000347b  jmp     rax; switch jump
0x18000347d  mov     rax, [rdi]; jumptable 000000018000347B cases 4-6
0x180003480  test    rax, rax
0x180003483  jz      loc_180003601; jumptable 000000018000347B case 8
0x180003489  movzx   edx, word ptr [rax+44h]
0x18000348d  movzx   r8d, word ptr [rax+46h]
0x180003492  add     r8d, edx
0x180003495  cmp     r8d, edx
0x180003498  jb      short loc_1800034F2
0x18000349a  mov     edx, r8d; uBytes
0x18000349d  mov     ecx, 40h ; '@'; uFlags
0x1800034a2  call    cs:__imp_LocalAlloc
0x1800034a8  mov     r14, rax
0x1800034ab  test    rax, rax
0x1800034ae  jz      short loc_1800034F2
0x1800034b0  mov     rdx, [rdi]; Src
0x1800034b3  movzx   ecx, word ptr [rdx+44h]
0x1800034b7  movzx   r8d, word ptr [rdx+46h]
0x1800034bc  add     r8, rcx; Size
0x1800034bf  mov     rcx, rax; void *
0x1800034c2  call    memcpy_0
0x1800034c7  jmp     loc_180003601; jumptable 000000018000347B case 8
0x1800034cc  mov     r9, [rdi]; jumptable 000000018000347B case 7
0x1800034cf  lea     r8, pszPort; pszPort
0x1800034d6  mov     rdx, rbp; pwszDevice
0x1800034d9  lea     rcx, pszPort; pwszDriver
0x1800034e0  call    cs:__imp_CreateDCW
0x1800034e6  mov     r15, rax
0x1800034e9  test    rax, rax
0x1800034ec  jnz     loc_180003601; jumptable 000000018000347B case 8
0x1800034f2  mov     rcx, [rbx+28h]; hPrinter
0x1800034f6  mov     [rbx], r12d
0x1800034f9  test    rcx, rcx
0x1800034fc  jz      short loc_180003504
0x1800034fe  call    cs:__imp_ClosePrinter
0x180003504  mov     rcx, [rbx+68h]; hdc
0x180003508  test    rcx, rcx
0x18000350b  jz      short loc_180003513
0x18000350d  call    cs:__imp_DeleteDC
0x180003513  mov     rcx, [rbx+70h]; hMem
0x180003517  test    rcx, rcx
0x18000351a  jz      short loc_180003522
0x18000351c  call    cs:__imp_LocalFree
0x180003522  mov     rcx, [rbx+78h]; hMem
0x180003526  test    rcx, rcx
0x180003529  jz      short loc_180003531
0x18000352b  call    cs:__imp_LocalFree
0x180003531  mov     rcx, [rbx+18h]; hObject
0x180003535  test    rcx, rcx
0x180003538  jz      short loc_180003540
0x18000353a  call    cs:__imp_CloseHandle
0x180003540  mov     rcx, [rbx+30h]; hMem
0x180003544  test    rcx, rcx
0x180003547  jz      short loc_18000354F
0x180003549  call    cs:__imp_LocalFree
0x18000354f  mov     rcx, [rbx+48h]; hMem
0x180003553  test    rcx, rcx
0x180003556  jz      short loc_18000355E
0x180003558  call    cs:__imp_LocalFree
0x18000355e  mov     rcx, [rbx+38h]; hMem
0x180003562  test    rcx, rcx
0x180003565  jz      short loc_18000356D
0x180003567  call    cs:__imp_LocalFree
0x18000356d  mov     rcx, [rbx+40h]; hMem
0x180003571  test    rcx, rcx
0x180003574  jz      short loc_18000357C
0x180003576  call    cs:__imp_LocalFree
0x18000357c  mov     rcx, [rbx+50h]; hMem
0x180003580  test    rcx, rcx
0x180003583  jz      short loc_18000358B
0x180003585  call    cs:__imp_LocalFree
0x18000358b  xorps   xmm0, xmm0
0x18000358e  mov     rcx, rbx; hMem
0x180003591  movups  xmmword ptr [rbx], xmm0
0x180003594  movups  xmmword ptr [rbx+10h], xmm0
0x180003598  movups  xmmword ptr [rbx+20h], xmm0
0x18000359c  movups  xmmword ptr [rbx+30h], xmm0
0x1800035a0  movups  xmmword ptr [rbx+40h], xmm0
0x1800035a4  movups  xmmword ptr [rbx+50h], xmm0
0x1800035a8  movups  xmmword ptr [rbx+60h], xmm0
0x1800035ac  movups  xmmword ptr [rbx+70h], xmm0
0x1800035b0  call    cs:__imp_LocalFree
0x1800035b6  xor     eax, eax
0x1800035b8  mov     r14, [rsp+68h+var_30]
0x1800035bd  mov     r15, [rsp+68h+var_38]
0x1800035c2  mov     rbx, [rsp+68h+var_20]
0x1800035c7  mov     rsi, [rsp+68h+var_28]
0x1800035cc  add     rsp, 50h
0x1800035d0  pop     r12
0x1800035d2  pop     rdi
0x1800035d3  pop     rbp
0x1800035d4  retn
0x1800035d5  mov     ecx, 70Ch; jumptable 000000018000347B default case, cases 2,3
0x1800035da  call    cs:__imp_SetLastError
0x1800035e0  jmp     loc_1800034F2
0x1800035e5  xor     r8d, r8d; jumptable 000000018000347B cases 0,1
0x1800035e8  lea     rdx, [rsp+68h+phPrinter]; phPrinter
0x1800035f0  mov     rcx, rbp; pPrinterName
0x1800035f3  call    cs:__imp_OpenPrinterW
0x1800035f9  test    eax, eax
0x1800035fb  jz      loc_1800034F2
0x180003601  mov     dword ptr [rbx+4], 80h; jumptable 000000018000347B case 8
0x180003608  mov     edx, 1; bManualReset
0x18000360d  mov     dword ptr [rbx], 5051h
0x180003613  xor     r9d, r9d; lpName
0x180003616  mov     eax, [rdi+20h]
0x180003619  xor     ecx, ecx; lpEventAttributes
0x18000361b  mov     [rbx+58h], eax
0x18000361e  mov     r8d, edx; bInitialState
0x180003621  mov     rax, [rsp+68h+phPrinter]
0x180003629  mov     [rbx+28h], rax
0x18000362d  call    cs:__imp_CreateEventW
0x180003633  mov     [rbx+18h], rax
0x180003637  mov     rcx, rbp; unsigned __int16 *
0x18000363a  mov     [rbx+20h], esi
0x18000363d  mov     [rbx+68h], r15
0x180003641  mov     dword ptr [rbx+5Ch], 1
0x180003648  mov     dword ptr [rbx+60h], 8
0x18000364f  call    ?AllocSplStr@@YAPEAGPEBG@Z; AllocSplStr(ushort const *)
0x180003654  mov     [rbx+30h], rax
0x180003658  mov     rcx, [rdi+8]; unsigned __int16 *
0x18000365c  call    ?AllocSplStr@@YAPEAGPEBG@Z; AllocSplStr(ushort const *)
0x180003661  mov     [rbx+48h], rax
0x180003665  mov     rcx, [rdi+18h]; unsigned __int16 *
0x180003669  call    ?AllocSplStr@@YAPEAGPEBG@Z; AllocSplStr(ushort const *)
0x18000366e  mov     [rbx+38h], rax
0x180003672  mov     rcx, [rdi+28h]; unsigned __int16 *
0x180003676  call    ?AllocSplStr@@YAPEAGPEBG@Z; AllocSplStr(ushort const *)
0x18000367b  mov     [rbx+40h], rax
0x18000367f  mov     rcx, [rdi+10h]; unsigned __int16 *
0x180003683  call    ?AllocSplStr@@YAPEAGPEBG@Z; AllocSplStr(ushort const *)
0x180003688  mov     [rbx+50h], rax
0x18000368c  mov     [rbx+70h], r14
0x180003690  mov     rcx, [rdi+30h]; unsigned __int16 *
0x180003694  call    ?AllocSplStr@@YAPEAGPEBG@Z; AllocSplStr(ushort const *)
0x180003699  mov     [rbx+78h], rax
0x18000369d  cmp     [rbx+18h], r12
0x1800036a1  jz      loc_1800034F2
0x1800036a7  test    rbp, rbp
0x1800036aa  jz      short loc_1800036B6
0x1800036ac  cmp     [rbx+30h], r12
0x1800036b0  jz      loc_1800034F2
0x1800036b6  cmp     [rdi+8], r12
0x1800036ba  jz      short loc_1800036C6
0x1800036bc  cmp     [rbx+48h], r12
0x1800036c0  jz      loc_1800034F2
0x1800036c6  cmp     [rdi+18h], r12
0x1800036ca  jz      short loc_1800036D6
0x1800036cc  cmp     [rbx+38h], r12
0x1800036d0  jz      loc_1800034F2
0x1800036d6  cmp     [rdi+28h], r12
0x1800036da  jz      short loc_1800036E6
0x1800036dc  cmp     [rbx+40h], r12
0x1800036e0  jz      loc_1800034F2
0x1800036e6  cmp     [rdi+10h], r12
0x1800036ea  jz      short loc_1800036F6
0x1800036ec  cmp     [rbx+50h], r12
0x1800036f0  jz      loc_1800034F2
0x1800036f6  cmp     [rdi+30h], r12
0x1800036fa  jz      short loc_180003705
0x1800036fc  test    rax, rax
0x1800036ff  jz      loc_1800034F2
0x180003705  mov     rcx, [rbx+50h]; Str
0x180003709  test    rcx, rcx
0x18000370c  jz      loc_180003794
0x180003712  lea     rax, [rsp+68h+arg_10]
0x18000371a  mov     [rsp+68h+arg_10], r12d
0x180003722  mov     edi, 4
0x180003727  mov     [rsp+68h+var_48], rax; void *
0x18000372c  lea     r9, [rsp+68h+arg_8]; unsigned __int16 *
0x180003731  mov     word ptr [rsp+68h+arg_8], di
0x180003736  lea     rdx, aCopies; "COPIES"
0x18000373d  call    ?GetKeyValue@@YAGPEAG0G0PEAX@Z; GetKeyValue(ushort *,ushort *,ushort,ushort *,void *)
0x180003742  cmp     word ptr [rsp+68h+arg_8], di
0x180003747  jnz     short loc_180003753
0x180003749  mov     eax, [rsp+68h+arg_10]
0x180003750  mov     [rbx+5Ch], eax
0x180003753  cmp     esi, 7
0x180003756  jnz     short loc_180003794
0x180003758  mov     rcx, [rbx+50h]; Str
0x18000375c  lea     rax, [rsp+68h+arg_10]
0x180003764  lea     r9, [rsp+68h+arg_8]; unsigned __int16 *
0x180003769  mov     [rsp+68h+var_48], rax; void *
0x18000376e  lea     rdx, aTabs; "TABS"
0x180003775  mov     word ptr [rsp+68h+arg_8], di
0x18000377a  call    ?GetKeyValue@@YAGPEAG0G0PEAX@Z; GetKeyValue(ushort *,ushort *,ushort,ushort *,void *)
0x18000377f  cmp     word ptr [rsp+68h+arg_8], di
0x180003784  jnz     short loc_180003794
0x180003786  mov     eax, [rsp+68h+arg_10]
0x18000378d  test    eax, eax
0x18000378f  jz      short loc_180003794
0x180003791  mov     [rbx+60h], eax
0x180003794  cmp     dword ptr [rbx+5Ch], 1
0x180003798  jbe     short loc_180003814
0x18000379a  mov     [rsp+68h+arg_8], r12d
0x18000379f  cmp     esi, 3
0x1800037a2  jb      short loc_1800037B8
0x1800037a4  xor     r8d, r8d; pDefault
0x1800037a7  lea     rdx, [rsp+68h+phPrinter]; phPrinter
0x1800037af  mov     rcx, rbp; pPrinterName
0x1800037b2  call    cs:__imp_OpenPrinterW
0x1800037b8  mov     rcx, [rsp+68h+phPrinter]; hPrinter
0x1800037c0  lea     rax, [rcx-1]
0x1800037c4  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800037c8  ja      short loc_18000380D
0x1800037ca  lea     r8, [rsp+68h+arg_8]; unsigned int *
0x1800037cf  call    ?GetPrinterInfo@@YAPEAEPEAXKPEAK@Z; GetPrinterInfo(void *,ulong,ulong *)
0x1800037d4  test    rax, rax
0x1800037d7  jnz     short loc_1800037E2
0x1800037d9  mov     dword ptr [rbx+5Ch], 1
0x1800037e0  jmp     short loc_1800037F8
0x1800037e2  test    byte ptr [rax+68h], 2
0x1800037e6  jz      short loc_1800037EF
0x1800037e8  mov     dword ptr [rbx+5Ch], 1
0x1800037ef  mov     rcx, rax; hMem
0x1800037f2  call    cs:__imp_LocalFree
0x1800037f8  cmp     esi, 3
0x1800037fb  jb      short loc_180003814
0x1800037fd  mov     rcx, [rsp+68h+phPrinter]; hPrinter
0x180003805  call    cs:__imp_ClosePrinter
0x18000380b  jmp     short loc_180003814
0x18000380d  mov     dword ptr [rbx+5Ch], 1
0x180003814  mov     rax, rbx
0x180003817  jmp     loc_1800035B8
0x18000381c  mov     ecx, 57h ; 'W'; dwErrCode
0x180003821  call    cs:__imp_SetLastError
0x180003827  xor     eax, eax
0x180003829  jmp     loc_1800035CC
```
