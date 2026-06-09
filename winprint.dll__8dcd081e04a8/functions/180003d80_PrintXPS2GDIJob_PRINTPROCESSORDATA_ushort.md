# PrintXPS2GDIJob(_PRINTPROCESSORDATA *,ushort *)

- ea: `0x180003d80`
- end: `0x180004295`
- name: `?PrintXPS2GDIJob@@YAHPEAU_PRINTPROCESSORDATA@@PEAG@Z`
- size: `1301`
- prototype: `int(struct _PRINTPROCESSORDATA *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800061f0`

## callees

- `0x180001510`
- `0x180003d80`
- `0x180004c80`
- `0x180005600`
- `0x18000757c`
- `0x1800075e0`
- `0x180008010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180003e86`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180003e86`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x180003fee`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x180003fee`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800041ff`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800041ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003eed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003eed`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004234`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004234`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalAlloc` at `0x180003dba`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalAlloc` at `0x180003e45`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalAlloc` at `0x180003f04`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalAlloc` at `0x180003dba`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalAlloc` at `0x180003e45`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalAlloc` at `0x180003f04`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180003f66`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18000423d`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180004246`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180003f66`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18000423d`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180004246`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180003ffa`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180004266`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180003ffa`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180004266`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180003de1`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180003de1`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800040dc`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180004149`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800040dc`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180004149`
- `WINSPOOL!ClosePrinter` at `0x180003f70`
- `WINSPOOL!ClosePrinter` at `0x1800041e1`
- `WINSPOOL!ClosePrinter` at `0x180004255`
- `WINSPOOL!ClosePrinter` at `0x180003f70`
- `WINSPOOL!ClosePrinter` at `0x1800041e1`
- `WINSPOOL!ClosePrinter` at `0x180004255`
- `WINSPOOL!OpenPrinterW` at `0x180003e05`
- `WINSPOOL!OpenPrinterW` at `0x180003ea6`
- `WINSPOOL!OpenPrinterW` at `0x1800041a3`
- `WINSPOOL!OpenPrinterW` at `0x180003e05`
- `WINSPOOL!OpenPrinterW` at `0x180003ea6`
- `WINSPOOL!OpenPrinterW` at `0x1800041a3`
- `WINSPOOL!ReadPrinter` at `0x1800040ba`
- `WINSPOOL!ReadPrinter` at `0x1800040ba`
- `WINSPOOL!GetPrinterW` at `0x180003edb`
- `WINSPOOL!GetPrinterW` at `0x180003f32`
- `WINSPOOL!GetPrinterW` at `0x180003edb`
- `WINSPOOL!GetPrinterW` at `0x180003f32`
- `WINSPOOL!SetJobW` at `0x1800041d0`
- `WINSPOOL!SetJobW` at `0x1800041d0`
- `XPSPRINT!StartXpsPrintJob` at `0x180004046`
- `XPSPRINT!StartXpsPrintJob` at `0x180004046`

## string_xrefs

- `0x180003f88`: `%ws,LinkedJob %u`

## pseudocode

```c
_BOOL8 __fastcall PrintXPS2GDIJob(struct _PRINTPROCESSORDATA *a1, unsigned __int16 *a2)
{
  HLOCAL v4; // rsi
  BOOL v5; // eax
  const unsigned __int16 **v6; // r12
  BOOL v7; // ebx
  __int64 v8; // rcx
  unsigned __int64 v10; // rbx
  unsigned __int16 *v11; // r13
  __int64 v12; // rcx
  WCHAR *v13; // rcx
  BOOL v14; // eax
  bool v15; // r15
  DWORD v16; // r15d
  const wchar_t **v17; // r14
  int v18; // eax
  DWORD Wow64TlsIndex; // r15d
  int v20; // eax
  BOOL v21; // r14d
  __int64 v22; // r8
  HANDLE v23; // r12
  int v24; // eax
  DWORD v25; // ecx
  DWORD v26; // edx
  LPDWORD pcbNeeded; // [rsp+20h] [rbp-79h]
  char v29; // [rsp+50h] [rbp-49h]
  DWORD cbBuf; // [rsp+54h] [rbp-45h] BYREF
  HANDLE completionEvent; // [rsp+58h] [rbp-41h]
  DWORD pNoBytesRead; // [rsp+60h] [rbp-39h] BYREF
  IXpsPrintJob *xpsPrintJob; // [rsp+68h] [rbp-31h] BYREF
  IXpsPrintJobStream *documentStream; // [rsp+70h] [rbp-29h] BYREF
  HANDLE phPrinter; // [rsp+78h] [rbp-21h] BYREF
  BYTE pJob[8]; // [rsp+80h] [rbp-19h] BYREF
  int v37; // [rsp+88h] [rbp-11h]
  __int128 v38; // [rsp+90h] [rbp-9h] BYREF
  __int64 v39; // [rsp+A0h] [rbp+7h]
  HANDLE hPrinter; // [rsp+A8h] [rbp+Fh] BYREF
  int v41; // [rsp+B0h] [rbp+17h]
  wchar_t v42; // [rsp+B4h] [rbp+1Bh]

  v4 = LocalAlloc(0x40u, 0x40000u);
  documentStream = 0;
  xpsPrintJob = 0;
  if ( !v4 )
  {
    completionEvent = 0;
    phPrinter = 0;
    goto LABEL_32;
  }
  completionEvent = CreateEventW(0, 0, 0, 0);
  phPrinter = 0;
  if ( !completionEvent )
  {
LABEL_32:
    v11 = 0;
    *(_QWORD *)pJob = (char *)a1 + 120;
    goto LABEL_33;
  }
  v5 = OpenPrinterW(a2, &phPrinter, 0);
  v6 = (const unsigned __int16 **)((char *)a1 + 120);
  v7 = v5;
  v8 = -1;
  while ( *(_WORD *)(*((_QWORD *)a1 + 15) + 2 * v8++ + 2) != 0 )
    ;
  if ( v5 )
  {
    v10 = v8 + 22;
    v11 = (unsigned __int16 *)LocalAlloc(0x40u, 2 * (v8 + 22));
    if ( v11 )
    {
      v41 = *(_DWORD *)L"R|";
      v42 = aCsr[6];
      v12 = *((_QWORD *)a1 + 6);
      hPrinter = *(HANDLE *)L"\\\\CSR|";
      if ( (unsigned int)_o__wcsnicmp(v12, &hPrinter, 6) )
      {
        v13 = (WCHAR *)*v6;
        hPrinter = 0;
        v14 = OpenPrinterW(v13, &hPrinter, 0);
        *(_QWORD *)pJob = (char *)a1 + 120;
        if ( v14 )
        {
          cbBuf = 0;
          v15 = 1;
          v29 = 1;
          if ( !GetPrinterW(hPrinter, 2u, 0, 0, &cbBuf) )
          {
            v29 = 1;
            if ( GetLastError() == 122 )
            {
              v16 = cbBuf;
              v17 = (const wchar_t **)LocalAlloc(0x40u, cbBuf);
              v29 = 1;
              if ( v17 && (v29 = 1, GetPrinterW(hPrinter, 2u, (LPBYTE)v17, v16, &cbBuf)) )
              {
                v15 = wcschr(v17[3], 0x2Cu) == 0;
                v29 = v15;
              }
              else
              {
                v15 = 1;
              }
              LocalFree(v17);
            }
          }
          ClosePrinter(hPrinter);
          if ( !v15 )
          {
LABEL_22:
            if ( (int)StringCchCopyW(v11, v10, *v6) >= 0 )
            {
              v7 = 1;
              goto LABEL_24;
            }
            goto LABEL_34;
          }
        }
        else
        {
          v29 = 1;
        }
        LODWORD(pcbNeeded) = *((_DWORD *)a1 + 22);
        v18 = StringCchPrintfW(v11, v10, L"%ws,LinkedJob %u", *v6, pcbNeeded);
        Wow64TlsIndex = -1;
        v7 = v18 >= 0;
        if ( v18 < 0 )
        {
LABEL_26:
          v21 = 0;
          if ( v7 )
          {
            v7 = StartXpsPrintJob(
                   v11,
                   *((LPCWSTR *)a1 + 7),
                   *((LPCWSTR *)a1 + 8),
                   0,
                   completionEvent,
                   0,
                   0,
                   &xpsPrintJob,
                   &documentStream,
                   0) >= 0;
            v21 = v7;
          }
          goto LABEL_36;
        }
LABEL_24:
        Wow64TlsIndex = GetWow64TlsIndex();
        if ( Wow64TlsIndex != -1 )
        {
          v20 = _o__wtoi(*((_QWORD *)a1 + 10));
          TlsSetValue(Wow64TlsIndex, (LPVOID)v20);
        }
        goto LABEL_26;
      }
      *(_QWORD *)pJob = (char *)a1 + 120;
      v29 = 0;
      goto LABEL_22;
    }
    *(_QWORD *)pJob = (char *)a1 + 120;
LABEL_33:
    v29 = 1;
LABEL_34:
    v7 = 0;
    goto LABEL_35;
  }
  v11 = 0;
  *(_QWORD *)pJob = (char *)a1 + 120;
  v29 = 1;
LABEL_35:
  Wow64TlsIndex = -1;
  v21 = 0;
LABEL_36:
  pNoBytesRead = 0;
  while ( v7 )
  {
    if ( !ReadPrinter(phPrinter, v4, 0x40000u, &pNoBytesRead) )
      break;
    v22 = pNoBytesRead;
    if ( !pNoBytesRead )
      break;
    if ( (*((_BYTE *)a1 + 16) & 8) != 0 )
    {
      WaitForSingleObject(*((HANDLE *)a1 + 3), 0xFFFFFFFF);
      v22 = pNoBytesRead;
    }
    if ( (*((_BYTE *)a1 + 16) & 1) != 0 )
    {
      ((void (__fastcall *)(IXpsPrintJob *))xpsPrintJob->lpVtbl->Cancel)(xpsPrintJob);
      break;
    }
    cbBuf = 0;
    v7 = ((int (__fastcall *)(IXpsPrintJobStream *, HLOCAL, __int64, DWORD *))documentStream->lpVtbl->Write)(
           documentStream,
           v4,
           v22,
           &cbBuf) >= 0;
  }
  if ( v21 )
    ((void (__fastcall *)(IXpsPrintJobStream *))documentStream->lpVtbl->Close)(documentStream);
  v23 = completionEvent;
  if ( v7 )
  {
    if ( WaitForSingleObject(completionEvent, 0xFFFFFFFF) )
    {
      v25 = 1223;
    }
    else
    {
      if ( !v29 )
        goto LABEL_61;
      v39 = 0;
      v38 = 0;
      v24 = ((__int64 (__fastcall *)(IXpsPrintJob *, __int128 *))xpsPrintJob->lpVtbl->GetJobStatus)(xpsPrintJob, &v38);
      v25 = v24;
      if ( v24 >= 0 )
      {
        if ( !(_DWORD)v38 )
          goto LABEL_61;
        hPrinter = 0;
        if ( OpenPrinterW(**(LPWSTR **)pJob, &hPrinter, 0) )
        {
          v26 = *((_DWORD *)a1 + 22);
          v37 = 0;
          *(_DWORD *)pJob = v26;
          *(_DWORD *)&pJob[4] = v38;
          if ( !SetJobW(hPrinter, v26, 3u, pJob, 0) )
            v7 = 0;
          ClosePrinter(hPrinter);
          goto LABEL_61;
        }
LABEL_60:
        v7 = 0;
        goto LABEL_61;
      }
      if ( (v24 & 0x1FFF0000) == 0x70000 )
        v25 = (unsigned __int16)v24;
    }
    SetLastError(v25);
    goto LABEL_60;
  }
LABEL_61:
  if ( v21 )
  {
    ((void (__fastcall *)(IXpsPrintJob *))xpsPrintJob->lpVtbl->Release)(xpsPrintJob);
    ((void (__fastcall *)(IXpsPrintJobStream *))documentStream->lpVtbl->Release)(documentStream);
  }
  if ( v23 )
    CloseHandle(v23);
  LocalFree(v4);
  LocalFree(v11);
  if ( phPrinter )
    ClosePrinter(phPrinter);
  if ( Wow64TlsIndex != -1 )
    TlsSetValue(Wow64TlsIndex, 0);
  return v7;
}

```

## disassembly

```asm
0x180003d80  mov     [rsp-8+arg_10], rbx
0x180003d85  push    rbp
0x180003d86  push    rsi
0x180003d87  push    rdi
0x180003d88  push    r12
0x180003d8a  push    r13
0x180003d8c  push    r14
0x180003d8e  push    r15
0x180003d90  lea     rbp, [rsp-27h]
0x180003d95  sub     rsp, 0C0h
0x180003d9c  mov     rax, cs:__security_cookie
0x180003da3  xor     rax, rsp
0x180003da6  mov     [rbp+57h+var_38], rax
0x180003daa  mov     rbx, rdx
0x180003dad  mov     rdi, rcx
0x180003db0  mov     edx, 40000h; uBytes
0x180003db5  mov     ecx, 40h ; '@'; uFlags
0x180003dba  call    cs:__imp_LocalAlloc
0x180003dc0  xor     r12d, r12d
0x180003dc3  mov     rsi, rax
0x180003dc6  mov     [rbp+57h+var_80], r12
0x180003dca  mov     [rbp+57h+var_88], r12
0x180003dce  test    rax, rax
0x180003dd1  jz      loc_18000407E
0x180003dd7  xor     r9d, r9d; lpName
0x180003dda  xor     r8d, r8d; bInitialState
0x180003ddd  xor     edx, edx; bManualReset
0x180003ddf  xor     ecx, ecx; lpEventAttributes
0x180003de1  call    cs:__imp_CreateEventW
0x180003de7  mov     [rbp+57h+completionEvent], rax
0x180003deb  mov     r14, rax
0x180003dee  mov     [rbp+57h+phPrinter], r12
0x180003df2  test    rax, rax
0x180003df5  jz      loc_180004086
0x180003dfb  xor     r8d, r8d; pDefault
0x180003dfe  lea     rdx, [rbp+57h+phPrinter]; phPrinter
0x180003e02  mov     rcx, rbx; pPrinterName
0x180003e05  call    cs:__imp_OpenPrinterW
0x180003e0b  mov     rdx, [rdi+78h]
0x180003e0f  lea     r12, [rdi+78h]
0x180003e13  mov     ebx, eax
0x180003e15  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180003e1c  nop     dword ptr [rax+00h]
0x180003e20  cmp     word ptr [rdx+rcx*2+2], 0
0x180003e26  lea     rcx, [rcx+1]
0x180003e2a  jnz     short loc_180003E20
0x180003e2c  test    eax, eax
0x180003e2e  jz      loc_18000406E
0x180003e34  lea     rbx, [rcx+16h]
0x180003e38  mov     [rbp+57h+completionEvent], r14
0x180003e3c  lea     rdx, [rbx+rbx]; uBytes
0x180003e40  mov     ecx, 40h ; '@'; uFlags
0x180003e45  call    cs:__imp_LocalAlloc
0x180003e4b  mov     r13, rax
0x180003e4e  test    rax, rax
0x180003e51  jz      loc_18000405D
0x180003e57  mov     ecx, dword ptr cs:aCsr+8; "R|"
0x180003e5d  lea     rdx, [rbp+57h+hPrinter]
0x180003e61  movsd   xmm0, qword ptr cs:aCsr; "\\\\CSR|"
0x180003e69  mov     r8d, 6
0x180003e6f  mov     [rbp+57h+var_40], ecx
0x180003e72  movzx   ecx, word ptr cs:aCsr+0Ch; ""
0x180003e79  mov     [rbp+57h+var_3C], cx
0x180003e7d  mov     rcx, [rdi+30h]
0x180003e81  movsd   [rbp+57h+hPrinter], xmm0
0x180003e86  call    cs:__imp__o__wcsnicmp
0x180003e8c  test    eax, eax
0x180003e8e  jz      loc_180003FB5
0x180003e94  mov     rcx, [r12]; pPrinterName
0x180003e98  lea     rdx, [rbp+57h+hPrinter]; phPrinter
0x180003e9c  xor     r15d, r15d
0x180003e9f  xor     r8d, r8d; pDefault
0x180003ea2  mov     [rbp+57h+hPrinter], r15
0x180003ea6  call    cs:__imp_OpenPrinterW
0x180003eac  mov     qword ptr [rbp+57h+pJob], r12
0x180003eb0  test    eax, eax
0x180003eb2  jz      loc_180003F7D
0x180003eb8  mov     rcx, [rbp+57h+hPrinter]; hPrinter
0x180003ebc  lea     rax, [rbp+57h+cbBuf]
0x180003ec0  mov     [rbp+57h+cbBuf], r15d
0x180003ec4  xor     r9d, r9d; cbBuf
0x180003ec7  mov     r15b, 1
0x180003eca  mov     [rsp+0F0h+pcbNeeded], rax; pcbNeeded
0x180003ecf  xor     r8d, r8d; pPrinter
0x180003ed2  mov     [rbp+57h+var_A0], r15d
0x180003ed6  mov     edx, 2; Level
0x180003edb  call    cs:__imp_GetPrinterW
0x180003ee1  test    eax, eax
0x180003ee3  jnz     loc_180003F6C
0x180003ee9  mov     [rbp+57h+var_A0], r15d
0x180003eed  call    cs:__imp_GetLastError
0x180003ef3  cmp     eax, 7Ah ; 'z'
0x180003ef6  jnz     short loc_180003F6C
0x180003ef8  mov     r15d, [rbp+57h+cbBuf]
0x180003efc  mov     ecx, 40h ; '@'; uFlags
0x180003f01  mov     edx, r15d; uBytes
0x180003f04  call    cs:__imp_LocalAlloc
0x180003f0a  mov     r14, rax
0x180003f0d  mov     al, 1
0x180003f0f  mov     [rbp+57h+var_A0], eax
0x180003f12  test    r14, r14
0x180003f15  jz      short loc_180003F5F
0x180003f17  lea     rcx, [rbp+57h+cbBuf]
0x180003f1b  mov     [rbp+57h+var_A0], eax
0x180003f1e  mov     [rsp+0F0h+pcbNeeded], rcx; pcbNeeded
0x180003f23  mov     r9d, r15d; cbBuf
0x180003f26  mov     rcx, [rbp+57h+hPrinter]; hPrinter
0x180003f2a  mov     r8, r14; pPrinter
0x180003f2d  mov     edx, 2; Level
0x180003f32  call    cs:__imp_GetPrinterW
0x180003f38  test    eax, eax
0x180003f3a  jz      short loc_180003F5F
0x180003f3c  mov     rcx, [r14+18h]; Str
0x180003f40  mov     dx, 2Ch ; ','; Ch
0x180003f44  mov     r15b, 1
0x180003f47  call    ?wcschr@@YAPEAGPEAGG@Z; wcschr(ushort *,ushort)
0x180003f4c  xor     ecx, ecx
0x180003f4e  movzx   r15d, r15b
0x180003f52  test    rax, rax
0x180003f55  cmovnz  r15d, ecx
0x180003f59  mov     [rbp+57h+var_A0], r15d
0x180003f5d  jmp     short loc_180003F63
0x180003f5f  mov     r15d, [rbp+57h+var_A0]
0x180003f63  mov     rcx, r14; hMem
0x180003f66  call    cs:__imp_LocalFree
0x180003f6c  mov     rcx, [rbp+57h+hPrinter]; hPrinter
0x180003f70  call    cs:__imp_ClosePrinter
0x180003f76  test    r15b, r15b
0x180003f79  jnz     short loc_180003F85
0x180003f7b  jmp     short loc_180003FC1
0x180003f7d  mov     byte ptr [rbp+57h+var_A0], 1
0x180003f81  mov     [rbp+57h+completionEvent], r14
0x180003f85  mov     eax, [rdi+58h]
0x180003f88  lea     r8, aWsLinkedjobU; "%ws,LinkedJob %u"
0x180003f8f  mov     r9, [r12]
0x180003f93  mov     rdx, rbx; unsigned __int64
0x180003f96  mov     rcx, r13; unsigned __int16 *
0x180003f99  mov     dword ptr [rsp+0F0h+pcbNeeded], eax
0x180003f9d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180003fa2  mov     ebx, eax
0x180003fa4  mov     r15d, 0FFFFFFFFh
0x180003faa  not     ebx
0x180003fac  shr     ebx, 1Fh
0x180003faf  test    ebx, ebx
0x180003fb1  jnz     short loc_180003FDD
0x180003fb3  jmp     short loc_180004000
0x180003fb5  mov     qword ptr [rbp+57h+pJob], r12
0x180003fb9  mov     byte ptr [rbp+57h+var_A0], 0
0x180003fbd  mov     [rbp+57h+completionEvent], r14
0x180003fc1  mov     r8, [r12]; unsigned __int16 *
0x180003fc5  mov     rdx, rbx; unsigned __int64
0x180003fc8  mov     rcx, r13; unsigned __int16 *
0x180003fcb  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180003fd0  test    eax, eax
0x180003fd2  js      loc_180004058
0x180003fd8  mov     ebx, 1
0x180003fdd  call    ?GetWow64TlsIndex@@YAKXZ; GetWow64TlsIndex(void)
0x180003fe2  mov     r15d, eax
0x180003fe5  cmp     eax, 0FFFFFFFFh
0x180003fe8  jz      short loc_180004000
0x180003fea  mov     rcx, [rdi+50h]
0x180003fee  call    cs:__imp__o__wtoi
0x180003ff4  movsxd  rdx, eax; lpTlsValue
0x180003ff7  mov     ecx, r15d; dwTlsIndex
0x180003ffa  call    cs:__imp_TlsSetValue
0x180004000  xor     r12d, r12d
0x180004003  mov     r14d, r12d
0x180004006  test    ebx, ebx
0x180004008  jz      loc_1800040A1
0x18000400e  mov     r8, [rdi+40h]; outputFileName
0x180004012  lea     rax, [rbp+57h+var_80]
0x180004016  mov     rdx, [rdi+38h]; jobName
0x18000401a  xor     r9d, r9d; progressEvent
0x18000401d  mov     [rsp+0F0h+printTicketStream], r12; printTicketStream
0x180004022  mov     rcx, r13; printerName
0x180004025  mov     [rsp+0F0h+documentStream], rax; documentStream
0x18000402a  lea     rax, [rbp+57h+var_88]
0x18000402e  mov     [rsp+0F0h+xpsPrintJob], rax; xpsPrintJob
0x180004033  mov     rax, [rbp+57h+completionEvent]
0x180004037  mov     [rsp+0F0h+printablePagesOnCount], r12d; printablePagesOnCount
0x18000403c  mov     [rsp+0F0h+printablePagesOn], r12; printablePagesOn
0x180004041  mov     [rsp+0F0h+pcbNeeded], rax; completionEvent
0x180004046  call    cs:__imp_StartXpsPrintJob
0x18000404c  mov     ebx, eax
0x18000404e  not     ebx
0x180004050  shr     ebx, 1Fh
0x180004053  mov     r14d, ebx
0x180004056  jmp     short loc_1800040A1
0x180004058  xor     r12d, r12d
0x18000405b  jmp     short loc_180004095
0x18000405d  mov     rax, [rbp+57h+completionEvent]
0x180004061  mov     qword ptr [rbp+57h+pJob], r12
0x180004065  xor     r12d, r12d
0x180004068  mov     [rbp+57h+completionEvent], rax
0x18000406c  jmp     short loc_180004091
0x18000406e  xor     r13d, r13d
0x180004071  mov     qword ptr [rbp+57h+pJob], r12
0x180004075  xor     r12d, r12d
0x180004078  mov     byte ptr [rbp+57h+var_A0], 1
0x18000407c  jmp     short loc_180004098
0x18000407e  mov     [rbp+57h+completionEvent], r12
0x180004082  mov     [rbp+57h+phPrinter], r12
0x180004086  lea     rax, [rdi+78h]
0x18000408a  mov     r13, r12
0x18000408d  mov     qword ptr [rbp+57h+pJob], rax
0x180004091  mov     byte ptr [rbp+57h+var_A0], 1
0x180004095  mov     ebx, r12d
0x180004098  mov     r15d, 0FFFFFFFFh
0x18000409e  mov     r14d, r12d
0x1800040a1  mov     [rbp+57h+pNoBytesRead], r12d
0x1800040a5  test    ebx, ebx
0x1800040a7  jz      short loc_180004120
0x1800040a9  mov     rcx, [rbp+57h+phPrinter]; hPrinter
0x1800040ad  lea     r9, [rbp+57h+pNoBytesRead]; pNoBytesRead
0x1800040b1  mov     r8d, 40000h; cbBuf
0x1800040b7  mov     rdx, rsi; pBuf
0x1800040ba  call    cs:__imp_ReadPrinter
0x1800040c0  test    eax, eax
0x1800040c2  jz      short loc_180004120
0x1800040c4  mov     r8d, [rbp+57h+pNoBytesRead]
0x1800040c8  test    r8d, r8d
0x1800040cb  jz      short loc_180004120
0x1800040cd  test    byte ptr [rdi+10h], 8
0x1800040d1  jz      short loc_1800040E6
0x1800040d3  mov     rcx, [rdi+18h]; hHandle
0x1800040d7  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x1800040dc  call    cs:__imp_WaitForSingleObject
0x1800040e2  mov     r8d, [rbp+57h+pNoBytesRead]
0x1800040e6  test    byte ptr [rdi+10h], 1
0x1800040ea  jnz     short loc_180004110
0x1800040ec  mov     rcx, [rbp+57h+var_80]
0x1800040f0  lea     r9, [rbp+57h+cbBuf]
0x1800040f4  mov     [rbp+57h+cbBuf], r12d
0x1800040f8  mov     rdx, rsi
0x1800040fb  mov     rax, [rcx]
0x1800040fe  mov     rax, [rax+20h]
0x180004102  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004107  mov     ebx, eax
0x180004109  not     ebx
0x18000410b  shr     ebx, 1Fh
0x18000410e  jmp     short loc_1800040A5
0x180004110  mov     rcx, [rbp+57h+var_88]
0x180004114  mov     rax, [rcx]
0x180004117  mov     rax, [rax+18h]
0x18000411b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004120  test    r14d, r14d
0x180004123  jz      short loc_180004135
0x180004125  mov     rcx, [rbp+57h+var_80]
0x180004129  mov     rax, [rcx]
0x18000412c  mov     rax, [rax+28h]
0x180004130  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004135  mov     r12, [rbp+57h+completionEvent]
0x180004139  test    ebx, ebx
0x18000413b  jz      loc_180004207
0x180004141  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x180004146  mov     rcx, r12; hHandle
0x180004149  call    cs:__imp_WaitForSingleObject
0x18000414f  test    eax, eax
0x180004151  jnz     loc_1800041FA
0x180004157  cmp     byte ptr [rbp+57h+var_A0], al
0x18000415a  jz      loc_180004207
0x180004160  mov     rcx, [rbp+57h+var_88]
0x180004164  lea     rdx, [rbp+57h+var_60]
0x180004168  xor     eax, eax
0x18000416a  xorps   xmm0, xmm0
0x18000416d  mov     [rbp+57h+var_50], rax
0x180004171  movups  [rbp+57h+var_60], xmm0
0x180004175  mov     rax, [rcx]
0x180004178  mov     rax, [rax+20h]
0x18000417c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004181  mov     ecx, eax
0x180004183  test    eax, eax
0x180004185  js      short loc_1800041E9
0x180004187  cmp     dword ptr [rbp+57h+var_60], 0
0x18000418b  jz      short loc_180004207
0x18000418d  mov     rcx, qword ptr [rbp+57h+pJob]
0x180004191  lea     rdx, [rbp+57h+hPrinter]; phPrinter
0x180004195  xor     r8d, r8d; pDefault
0x180004198  mov     [rbp+57h+hPrinter], 0
0x1800041a0  mov     rcx, [rcx]; pPrinterName
0x1800041a3  call    cs:__imp_OpenPrinterW
0x1800041a9  test    eax, eax
0x1800041ab  jz      short loc_180004205
0x1800041ad  mov     edx, [rdi+58h]; JobId
0x1800041b0  lea     r9, [rbp+57h+pJob]; pJob
0x1800041b4  mov     eax, dword ptr [rbp+57h+var_60]
0x1800041b7  xor     ecx, ecx
0x1800041b9  mov     [rbp+57h+var_68], ecx
0x1800041bc  mov     r8d, 3; Level
0x1800041c2  mov     dword ptr [rsp+0F0h+pcbNeeded], ecx; Command
0x1800041c6  mov     rcx, [rbp+57h+hPrinter]; hPrinter
0x1800041ca  mov     dword ptr [rbp+57h+pJob], edx
0x1800041cd  mov     dword ptr [rbp+57h+pJob+4], eax
0x1800041d0  call    cs:__imp_SetJobW
0x1800041d6  xor     ecx, ecx
0x1800041d8  test    eax, eax
0x1800041da  cmovz   ebx, ecx
0x1800041dd  mov     rcx, [rbp+57h+hPrinter]; hPrinter
0x1800041e1  call    cs:__imp_ClosePrinter
0x1800041e7  jmp     short loc_180004207
  ... truncated ...
```
