# CDlpActionLayoutUsb::CopyBootFiles(ushort const *)

- ea: `0x18000be9c`
- end: `0x18000c1ed`
- name: `?CopyBootFiles@CDlpActionLayoutUsb@@AEAAJPEBG@Z`
- size: `849`
- prototype: `__int64 __fastcall(CDlpActionLayoutUsb *this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000cad8`

## callees

- `0x18000aba4`
- `0x18000b9a8`
- `0x18000be9c`
- `0x180012f5c`
- `0x18001fd60`
- `0x180031e78`
- `0x180032518`
- `0x18007ec9a`
- `0x18007ed40`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x18000bf72`
- `msvcrt!wcscpy_s` at `0x18000c01e`
- `msvcrt!wcscpy_s` at `0x18000bf72`
- `msvcrt!wcscpy_s` at `0x18000c01e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x18000bf13`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x18000bf13`
- `ntdll!RtlNtStatusToDosError` at `0x18000c043`
- `ntdll!RtlNtStatusToDosError` at `0x18000c043`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c1a4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c1a4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c1b3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c1b3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c04b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c04b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bf1d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c0a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c0c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c126`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c13e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bf1d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c0a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c0c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c126`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c13e`

## string_xrefs

- `0x18000bedd`: `LayoutUsb: Recover usb. Using BfsServiceBootFilesEx to copy boot files`
- `0x18000bfac`: `CDlpActionLayoutUsb::CopyBootFiles`
- `0x18000c16f`: `CDlpActionLayoutUsb::CopyBootFiles`
- `0x18000c115`: `LayoutUsb: Failed to run BfsInitializeSystemVolume with path [%s], Firmware type [%s]`
- `0x18000c097`: `LayoutUsb: Failed to run BfsServiceBootFilesEx with source path [%s], Firmware type [%s]`

## pseudocode

```c
__int64 __fastcall CDlpActionLayoutUsb::CopyBootFiles(CDlpActionLayoutUsb *this, const unsigned __int16 *a2)
{
  __int64 v4; // rcx
  signed int v5; // eax
  signed int v6; // edi
  __int64 v7; // rcx
  __int64 v8; // rcx
  int v9; // eax
  __int64 v10; // rcx
  int v11; // eax
  __int64 v12; // rcx
  int v13; // ebx
  const wchar_t *v14; // r8
  NTSTATUS v15; // r15d
  ULONG v16; // eax
  __int64 v17; // rcx
  signed int LastError; // eax
  bool v19; // sf
  signed int v20; // eax
  __int64 v21; // rcx
  signed int v22; // eax
  bool v23; // sf
  signed int v24; // eax
  int v25; // eax
  __int64 v27; // [rsp+20h] [rbp-E0h]
  signed int v28; // [rsp+28h] [rbp-D8h]
  wchar_t v29[12]; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR Buffer[520]; // [rsp+50h] [rbp-B0h] BYREF
  wchar_t Destination[520]; // [rsp+460h] [rbp+360h] BYREF

  v4 = *((_QWORD *)this + 11);
  if ( v4 )
    CDlpLogT<CEmptyType>::DlpLogFormat(v4, 2, L"LayoutUsb: Recover usb. Using BfsServiceBootFilesEx to copy boot files");
  memset_0(Buffer, 0, sizeof(Buffer));
  if ( GetSystemWindowsDirectoryW(Buffer, 0x208u) )
  {
    wcscpy_s(Destination, 0x208u, a2);
    v9 = CMiscHelpersT<CEmptyType>::CombinePath((__int64)Buffer, (__int64)L"Boot", 0);
    v6 = v9;
    if ( v9 >= 0 )
    {
      v13 = 1;
      while ( 1 )
      {
        if ( v13 == 1 )
        {
          v14 = L"Bios";
        }
        else if ( v13 == 2 )
        {
          v14 = L"Uefi";
        }
        else
        {
          v14 = L"UnknownType";
        }
        wcscpy_s(v29, 0xAu, v14);
        v15 = BfspSetSystemVolumePath(Destination);
        if ( v15 >= 0 )
        {
          BfspFirmwareOverrideType = v13;
          v15 = 0;
        }
        v16 = RtlNtStatusToDosError(v15);
        SetLastError(v16);
        if ( v15 < 0 )
          break;
        if ( !(unsigned int)BfsServiceBootFilesEx2(0) )
        {
          v17 = *((_QWORD *)this + 11);
          if ( v17 )
            CDlpLogT<CEmptyType>::DlpLogFormat(
              v17,
              4,
              L"LayoutUsb: Failed to run BfsServiceBootFilesEx with source path [%s], Firmware type [%s]",
              0,
              v29);
          LastError = GetLastError();
          v19 = LastError < 0;
          if ( LastError > 0 )
            v19 = 1;
          if ( v19 )
          {
            v20 = GetLastError();
            v6 = v20;
            if ( v20 > 0 )
              v6 = (unsigned __int16)v20 | 0x80070000;
            if ( v6 >= 0 )
              goto LABEL_56;
          }
          else
          {
            v6 = -2147467259;
          }
          v8 = *((_QWORD *)this + 11);
          if ( !v8 )
            goto LABEL_56;
          v28 = v6;
          LODWORD(v27) = 1879;
          goto LABEL_53;
        }
        if ( ++v13 >= 3 )
          goto LABEL_56;
      }
      v21 = *((_QWORD *)this + 11);
      if ( v21 )
        CDlpLogT<CEmptyType>::DlpLogFormat(
          v21,
          4,
          L"LayoutUsb: Failed to run BfsInitializeSystemVolume with path [%s], Firmware type [%s]",
          Destination,
          v29);
      v22 = GetLastError();
      v23 = v22 < 0;
      if ( v22 > 0 )
        v23 = 1;
      if ( v23 )
      {
        v24 = GetLastError();
        v6 = v24;
        if ( v24 > 0 )
          v6 = (unsigned __int16)v24 | 0x80070000;
        if ( v6 >= 0 )
          goto LABEL_56;
      }
      else
      {
        v6 = -2147467259;
      }
      v8 = *((_QWORD *)this + 11);
      if ( !v8 )
        goto LABEL_56;
      v28 = v6;
      LODWORD(v27) = 1865;
      goto LABEL_53;
    }
    v10 = *((_QWORD *)this + 11);
    if ( v10 )
    {
      v11 = CDlpLogT<CEmptyType>::DlpLogFormat(
              v10,
              4,
              L"%s(%d): Result = 0x%X",
              L"CDlpActionLayoutUsb::CopyBootFiles",
              1841,
              v9);
      v12 = (unsigned int)v11;
      if ( v11 < 0 )
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v11);
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v12);
    }
  }
  else
  {
    v5 = GetLastError();
    v6 = v5;
    if ( v5 )
    {
      if ( v5 > 0 )
        v6 = (unsigned __int16)v5 | 0x80070000;
    }
    else
    {
      v6 = -2147467259;
    }
    if ( *((_QWORD *)this + 11) )
    {
      v7 = 0;
      if ( v6 >= 0 )
      {
LABEL_55:
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v7);
        goto LABEL_56;
      }
      v28 = v6;
      LODWORD(v27) = 1837;
      v8 = *((_QWORD *)this + 11);
LABEL_53:
      v25 = CDlpLogT<CEmptyType>::DlpLogFormat(
              v8,
              4,
              L"%s(%d): Result = 0x%X",
              L"CDlpActionLayoutUsb::CopyBootFiles",
              v27,
              v28);
      v7 = (unsigned int)v25;
      if ( v25 < 0 )
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v25);
      goto LABEL_55;
    }
  }
LABEL_56:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v6);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18000be9c  mov     [rsp-8+arg_10], rbx
0x18000bea1  mov     [rsp-8+arg_18], rsi
0x18000bea6  push    rbp
0x18000bea7  push    rdi
0x18000bea8  push    r12
0x18000beaa  push    r14
0x18000beac  push    r15
0x18000beae  lea     rbp, [rsp-780h]
0x18000beb6  sub     rsp, 880h
0x18000bebd  mov     rax, cs:__security_cookie
0x18000bec4  xor     rax, rsp
0x18000bec7  mov     [rbp+7A0h+var_30], rax
0x18000bece  mov     rbx, rdx
0x18000bed1  mov     r14, rcx
0x18000bed4  mov     rcx, [rcx+58h]
0x18000bed8  test    rcx, rcx
0x18000bedb  jz      short loc_18000BEEE
0x18000bedd  lea     r8, aLayoutusbRecov; "LayoutUsb: Recover usb. Using BfsServic"...
0x18000bee4  mov     edx, 2
0x18000bee9  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x18000beee  xor     esi, esi
0x18000bef0  mov     [rsp+8A0h+pszSrc], rsi
0x18000bef5  xor     edx, edx; Val
0x18000bef7  mov     r8d, 410h; Size
0x18000befd  lea     rcx, [rsp+8A0h+Buffer]; void *
0x18000bf02  call    memset_0
0x18000bf07  mov     edi, 208h
0x18000bf0c  mov     edx, edi; uSize
0x18000bf0e  lea     rcx, [rsp+8A0h+Buffer]; lpBuffer
0x18000bf13  call    cs:__imp_GetSystemWindowsDirectoryW
0x18000bf19  test    eax, eax
0x18000bf1b  jnz     short loc_18000BF65
0x18000bf1d  call    cs:__imp_GetLastError
0x18000bf23  mov     edi, eax
0x18000bf25  test    eax, eax
0x18000bf27  jnz     short loc_18000BF30
0x18000bf29  mov     edi, 80004005h
0x18000bf2e  jmp     short loc_18000BF3B
0x18000bf30  jle     short loc_18000BF3B
0x18000bf32  movzx   edi, ax
0x18000bf35  or      edi, 80070000h
0x18000bf3b  cmp     qword ptr [r14+58h], 0
0x18000bf40  jz      loc_18000C197
0x18000bf46  xor     ecx, ecx
0x18000bf48  test    edi, edi
0x18000bf4a  jns     loc_18000C192
0x18000bf50  mov     [rsp+8A0h+var_878], edi
0x18000bf54  mov     dword ptr [rsp+8A0h+var_880], 72Dh
0x18000bf5c  mov     rcx, [r14+58h]
0x18000bf60  jmp     loc_18000C16F
0x18000bf65  mov     r8, rbx; Source
0x18000bf68  mov     rdx, rdi; SizeInWords
0x18000bf6b  lea     rcx, [rbp+7A0h+Destination]; Destination
0x18000bf72  call    cs:__imp_wcscpy_s
0x18000bf78  lea     r9, [rsp+8A0h+pszSrc]
0x18000bf7d  xor     r8d, r8d
0x18000bf80  lea     rdx, aBoot; "Boot"
0x18000bf87  lea     rcx, [rsp+8A0h+Buffer]
0x18000bf8c  call    ?CombinePath@?$CMiscHelpersT@VCEmptyType@@@@SAJPEBG00PEAPEAG@Z; CMiscHelpersT<CEmptyType>::CombinePath(ushort const *,ushort const *,ushort const *,ushort * *)
0x18000bf91  mov     edi, eax
0x18000bf93  test    eax, eax
0x18000bf95  jns     short loc_18000BFDE
0x18000bf97  mov     rcx, [r14+58h]
0x18000bf9b  test    rcx, rcx
0x18000bf9e  jz      short loc_18000BFD4
0x18000bfa0  mov     [rsp+8A0h+var_878], eax
0x18000bfa4  mov     dword ptr [rsp+8A0h+var_880], 731h
0x18000bfac  lea     r9, aCdlpactionlayo_37; "CDlpActionLayoutUsb::CopyBootFiles"
0x18000bfb3  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x18000bfba  mov     edx, 4
0x18000bfbf  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x18000bfc4  mov     ecx, eax
0x18000bfc6  test    eax, eax
0x18000bfc8  jns     short loc_18000BFCF
0x18000bfca  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18000bfcf  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18000bfd4  mov     rsi, [rsp+8A0h+pszSrc]
0x18000bfd9  jmp     loc_18000C197
0x18000bfde  mov     ebx, 1
0x18000bfe3  lea     r12d, [rbx+9]
0x18000bfe7  mov     rsi, [rsp+8A0h+pszSrc]
0x18000bfec  mov     ecx, ebx
0x18000bfee  sub     ecx, 1
0x18000bff1  mov     rdx, r12; SizeInWords
0x18000bff4  jz      short loc_18000C012
0x18000bff6  cmp     ecx, 1
0x18000bff9  lea     rcx, [rsp+8A0h+var_868]
0x18000bffe  jz      short loc_18000C009
0x18000c000  lea     r8, aUnknowntype; "UnknownType"
0x18000c007  jmp     short loc_18000C01E
0x18000c009  lea     r8, aUefi; "Uefi"
0x18000c010  jmp     short loc_18000C01E
0x18000c012  lea     r8, Source; "Bios"
0x18000c019  lea     rcx, [rsp+8A0h+var_868]; Destination
0x18000c01e  call    cs:__imp_wcscpy_s
0x18000c024  lea     rcx, [rbp+7A0h+Destination]; lpszFileName
0x18000c02b  call    BfspSetSystemVolumePath
0x18000c030  mov     r15d, eax
0x18000c033  test    eax, eax
0x18000c035  js      short loc_18000C040
0x18000c037  mov     cs:BfspFirmwareOverrideType, ebx
0x18000c03d  xor     r15d, r15d
0x18000c040  mov     ecx, r15d; Status
0x18000c043  call    cs:__imp_RtlNtStatusToDosError
0x18000c049  mov     ecx, eax; dwErrCode
0x18000c04b  call    cs:__imp_SetLastError
0x18000c051  test    r15d, r15d
0x18000c054  js      loc_18000C0FB
0x18000c05a  xor     r9d, r9d
0x18000c05d  xor     r8d, r8d
0x18000c060  mov     edx, 55Ch
0x18000c065  mov     rcx, rsi; pszSrc
0x18000c068  call    BfsServiceBootFilesEx2
0x18000c06d  test    eax, eax
0x18000c06f  jz      short loc_18000C081
0x18000c071  inc     ebx
0x18000c073  cmp     ebx, 3
0x18000c076  jl      loc_18000BFEC
0x18000c07c  jmp     loc_18000C197
0x18000c081  mov     rcx, [r14+58h]
0x18000c085  test    rcx, rcx
0x18000c088  jz      short loc_18000C0A8
0x18000c08a  lea     rax, [rsp+8A0h+var_868]
0x18000c08f  mov     [rsp+8A0h+var_880], rax
0x18000c094  mov     r9, rsi
0x18000c097  lea     r8, aLayoutusbFaile_2; "LayoutUsb: Failed to run BfsServiceBoot"...
0x18000c09e  mov     edx, 4
0x18000c0a3  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x18000c0a8  call    cs:__imp_GetLastError
0x18000c0ae  mov     ebx, 80070000h
0x18000c0b3  test    eax, eax
0x18000c0b5  jle     short loc_18000C0BE
0x18000c0b7  movzx   eax, ax
0x18000c0ba  or      eax, ebx
0x18000c0bc  test    eax, eax
0x18000c0be  jns     short loc_18000C0DB
0x18000c0c0  call    cs:__imp_GetLastError
0x18000c0c6  mov     edi, eax
0x18000c0c8  test    eax, eax
0x18000c0ca  jle     short loc_18000C0D1
0x18000c0cc  movzx   edi, ax
0x18000c0cf  or      edi, ebx
0x18000c0d1  test    edi, edi
0x18000c0d3  jns     loc_18000C197
0x18000c0d9  jmp     short loc_18000C0E0
0x18000c0db  mov     edi, 80004005h
0x18000c0e0  mov     rcx, [r14+58h]
0x18000c0e4  test    rcx, rcx
0x18000c0e7  jz      loc_18000C197
0x18000c0ed  mov     [rsp+8A0h+var_878], edi
0x18000c0f1  mov     dword ptr [rsp+8A0h+var_880], 757h
0x18000c0f9  jmp     short loc_18000C16F
0x18000c0fb  mov     rcx, [r14+58h]
0x18000c0ff  test    rcx, rcx
0x18000c102  jz      short loc_18000C126
0x18000c104  lea     rax, [rsp+8A0h+var_868]
0x18000c109  mov     [rsp+8A0h+var_880], rax
0x18000c10e  lea     r9, [rbp+7A0h+Destination]
0x18000c115  lea     r8, aLayoutusbFaile_0; "LayoutUsb: Failed to run BfsInitializeS"...
0x18000c11c  mov     edx, 4
0x18000c121  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x18000c126  call    cs:__imp_GetLastError
0x18000c12c  mov     ebx, 80070000h
0x18000c131  test    eax, eax
0x18000c133  jle     short loc_18000C13C
0x18000c135  movzx   eax, ax
0x18000c138  or      eax, ebx
0x18000c13a  test    eax, eax
0x18000c13c  jns     short loc_18000C155
0x18000c13e  call    cs:__imp_GetLastError
0x18000c144  mov     edi, eax
0x18000c146  test    eax, eax
0x18000c148  jle     short loc_18000C14F
0x18000c14a  movzx   edi, ax
0x18000c14d  or      edi, ebx
0x18000c14f  test    edi, edi
0x18000c151  js      short loc_18000C15A
0x18000c153  jmp     short loc_18000C197
0x18000c155  mov     edi, 80004005h
0x18000c15a  mov     rcx, [r14+58h]
0x18000c15e  test    rcx, rcx
0x18000c161  jz      short loc_18000C197
0x18000c163  mov     [rsp+8A0h+var_878], edi
0x18000c167  mov     dword ptr [rsp+8A0h+var_880], 749h
0x18000c16f  lea     r9, aCdlpactionlayo_37; "CDlpActionLayoutUsb::CopyBootFiles"
0x18000c176  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x18000c17d  mov     edx, 4
0x18000c182  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x18000c187  mov     ecx, eax
0x18000c189  test    eax, eax
0x18000c18b  jns     short loc_18000C192
0x18000c18d  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18000c192  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18000c197  mov     ecx, edi
0x18000c199  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18000c19e  nop
0x18000c19f  test    rsi, rsi
0x18000c1a2  jz      short loc_18000C1C0
0x18000c1a4  call    cs:__imp_GetProcessHeap
0x18000c1aa  mov     rcx, rax; hHeap
0x18000c1ad  lea     r8, [rsi-4]; lpMem
0x18000c1b1  xor     edx, edx; dwFlags
0x18000c1b3  call    cs:__imp_HeapFree
0x18000c1b9  xor     ecx, ecx
0x18000c1bb  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18000c1c0  mov     eax, edi
0x18000c1c2  mov     rcx, [rbp+7A0h+var_30]
0x18000c1c9  xor     rcx, rsp; StackCookie
0x18000c1cc  call    __security_check_cookie
0x18000c1d1  lea     r11, [rsp+8A0h+var_20]
0x18000c1d9  mov     rbx, [r11+40h]
0x18000c1dd  mov     rsi, [r11+48h]
0x18000c1e1  mov     rsp, r11
0x18000c1e4  pop     r15
0x18000c1e6  pop     r14
0x18000c1e8  pop     r12
0x18000c1ea  pop     rdi
0x18000c1eb  pop     rbp
0x18000c1ec  retn
```
