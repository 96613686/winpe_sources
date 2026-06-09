# CWshNetwork::SetDefaultPrinterA(ushort *)

- ea: `0x180008930`
- end: `0x180008eed`
- name: `?SetDefaultPrinterA@CWshNetwork@@UEAAJPEAG@Z`
- size: `1469`
- prototype: `__int64 __fastcall(CWshNetwork *__hidden this, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x180005850`
- `0x180005d20`
- `0x1800060e4`
- `0x180006124`
- `0x180008930`
- `0x18000f178`
- `0x18000f2cc`
- `0x180010250`
- `0x1800102e0`

## import_xrefs

- `msvcrt!strcpy_s` at `0x180008c2a`
- `msvcrt!strcpy_s` at `0x180008c2a`
- `msvcrt!wcscat_s` at `0x180008aed`
- `msvcrt!wcscat_s` at `0x180008b02`
- `msvcrt!wcscat_s` at `0x180008cf9`
- `msvcrt!wcscat_s` at `0x180008d0c`
- `msvcrt!wcscat_s` at `0x180008d21`
- `msvcrt!wcscat_s` at `0x180008d34`
- `msvcrt!wcscat_s` at `0x180008aed`
- `msvcrt!wcscat_s` at `0x180008b02`
- `msvcrt!wcscat_s` at `0x180008cf9`
- `msvcrt!wcscat_s` at `0x180008d0c`
- `msvcrt!wcscat_s` at `0x180008d21`
- `msvcrt!wcscat_s` at `0x180008d34`
- `msvcrt!wcscpy_s` at `0x180008ad6`
- `msvcrt!wcscpy_s` at `0x180008ce4`
- `msvcrt!wcscpy_s` at `0x180008ad6`
- `msvcrt!wcscpy_s` at `0x180008ce4`
- `msvcrt!strcat_s` at `0x180008c43`
- `msvcrt!strcat_s` at `0x180008c5a`
- `msvcrt!strcat_s` at `0x180008c43`
- `msvcrt!strcat_s` at `0x180008c5a`
- `ADVAPI32!RegCloseKey` at `0x180008d6c`
- `ADVAPI32!RegCloseKey` at `0x180008eb2`
- `ADVAPI32!RegCloseKey` at `0x180008d6c`
- `ADVAPI32!RegCloseKey` at `0x180008eb2`
- `KERNEL32!GetLastError` at `0x1800089ef`
- `KERNEL32!GetLastError` at `0x180008e07`
- `KERNEL32!GetLastError` at `0x180008e57`
- `KERNEL32!GetLastError` at `0x1800089ef`
- `KERNEL32!GetLastError` at `0x180008e07`
- `KERNEL32!GetLastError` at `0x180008e57`
- `KERNEL32!MultiByteToWideChar` at `0x180008b41`
- `KERNEL32!MultiByteToWideChar` at `0x180008b9e`
- `KERNEL32!MultiByteToWideChar` at `0x180008c81`
- `KERNEL32!MultiByteToWideChar` at `0x180008b41`
- `KERNEL32!MultiByteToWideChar` at `0x180008b9e`
- `KERNEL32!MultiByteToWideChar` at `0x180008c81`
- `USER32!SendMessageTimeoutW` at `0x180008da8`
- `USER32!SendMessageTimeoutW` at `0x180008da8`
- `WINSPOOL!EnumPrintersW` at `0x1800089dd`
- `WINSPOOL!EnumPrintersW` at `0x1800089dd`
- `WINSPOOL!GetPrinterA` at `0x180008dfd`
- `WINSPOOL!GetPrinterA` at `0x180008dfd`
- `WINSPOOL!EnumPrintersA` at `0x1800089e5`
- `WINSPOOL!EnumPrintersA` at `0x1800089e5`
- `WINSPOOL!ClosePrinter` at `0x180008e4d`
- `WINSPOOL!ClosePrinter` at `0x180008ec2`
- `WINSPOOL!ClosePrinter` at `0x180008e4d`
- `WINSPOOL!ClosePrinter` at `0x180008ec2`
- `WINSPOOL!SetPrinterA` at `0x180008e38`
- `WINSPOOL!SetPrinterA` at `0x180008e38`
- `WINSPOOL!OpenPrinterA` at `0x180008dbb`
- `WINSPOOL!OpenPrinterA` at `0x180008dbb`

## pseudocode

```c
__int64 __fastcall CWshNetwork::SetDefaultPrinterA(CWshNetwork *this, unsigned __int16 *a2)
{
  BYTE *v4; // rsi
  DWORD cbBuf; // ebx
  int v6; // r12d
  BYTE *v7; // rax
  BYTE *v8; // rdi
  signed int LastError; // eax
  int v11; // ebx
  DWORD i; // r15d
  __int64 v13; // rbx
  const CHAR *v14; // rax
  const unsigned __int16 *v15; // rdx
  const wchar_t *v16; // r8
  __int64 v17; // rdx
  __int64 v18; // rax
  __int64 v19; // rcx
  __int64 v20; // rcx
  const CHAR *v21; // r8
  __int64 v22; // rax
  const char *v23; // r8
  __int64 v24; // rcx
  __int64 v25; // rdx
  __int64 v26; // rax
  const unsigned __int16 *v27; // rdx
  HKEY v28; // rcx
  __int64 v29; // r8
  const unsigned __int16 *v30; // rdx
  DWORD v31; // ebx
  DWORD pcbNeeded; // [rsp+40h] [rbp-C0h] BYREF
  DWORD pcReturned; // [rsp+44h] [rbp-BCh] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  HANDLE phPrinter; // [rsp+50h] [rbp-B0h] BYREF
  ULONG_PTR dwResult; // [rsp+58h] [rbp-A8h] BYREF
  wchar_t Destination[4096]; // [rsp+60h] [rbp-A0h] BYREF
  CHAR MultiByteStr[4096]; // [rsp+2060h] [rbp+1F60h] BYREF

  if ( !a2 )
    return 2147500035LL;
  pcbNeeded = 0;
  v4 = 0;
  pcReturned = 0;
  cbBuf = 1360;
  phPrinter = 0;
  v6 = 0;
  hKey = 0;
  while ( 1 )
  {
    v7 = (BYTE *)operator new(cbBuf);
    v8 = v7;
    if ( !v7 )
    {
      v11 = -2147024882;
      goto LABEL_71;
    }
    if ( Global::g_fWindowsNT
       ? EnumPrintersW(6u, 0, 2u, v7, cbBuf, &pcbNeeded, &pcReturned)
       : EnumPrintersA(6u, 0, 2u, v7, cbBuf, &pcbNeeded, &pcReturned) )
    {
      break;
    }
    LastError = GetLastError();
    v11 = LastError;
    if ( LastError != 122 )
    {
LABEL_11:
      if ( LastError > 0 )
        v11 = (unsigned __int16)LastError | 0x80070000;
      goto LABEL_68;
    }
    operator delete(v8);
    cbBuf = pcbNeeded;
  }
  for ( i = 0; ; ++i )
  {
    if ( i >= pcReturned )
      goto LABEL_67;
    v13 = 136LL * i;
    v14 = *(const CHAR **)&v8[v13 + 8];
    if ( !Global::g_fWindowsNT )
      break;
    if ( v14
      && !(unsigned int)CompareStrsCaseInsensitive(a2, *(const unsigned __int16 **)&v8[v13 + 8], 0xFFFFFFFFFFFFFFFFuLL) )
    {
      goto LABEL_52;
    }
    v15 = *(const unsigned __int16 **)&v8[v13 + 24];
    if ( v15 )
    {
      if ( !(unsigned int)CompareStrsCaseInsensitive(a2, v15, 0xFFFFFFFFFFFFFFFFuLL) )
        goto LABEL_52;
    }
    v16 = *(const wchar_t **)&v8[v13];
    if ( v16 )
    {
      v17 = *(_QWORD *)&v8[v13 + 16];
      if ( v17 )
      {
        v18 = -1;
        v19 = -1;
        do
          ++v19;
        while ( v16[v19] );
        do
          ++v18;
        while ( *(_WORD *)(v17 + 2 * v18) );
        if ( (unsigned __int64)(v19 + 2 + v18) > 0x1000 )
        {
LABEL_51:
          v11 = -2147467259;
          goto LABEL_68;
        }
        wcscpy_s(Destination, 0x1000u, v16);
        wcscat_s(Destination, 0x1000u, L"\\");
        wcscat_s(Destination, 0x1000u, *(const wchar_t **)&v8[v13 + 16]);
LABEL_49:
        if ( !(unsigned int)CompareStrsCaseInsensitive(a2, Destination, 0xFFFFFFFFFFFFFFFFuLL) )
          goto LABEL_52;
        continue;
      }
    }
LABEL_50:
    ;
  }
  if ( !v14 )
    goto LABEL_78;
  v20 = -1;
  do
    ++v20;
  while ( v14[v20] );
  if ( !v20 )
    goto LABEL_78;
  if ( !MultiByteToWideChar(0, 0, v14, -1, Destination, 4096) )
    goto LABEL_65;
  if ( (unsigned int)CompareStrsCaseInsensitive(a2, Destination, 0xFFFFFFFFFFFFFFFFuLL) )
  {
LABEL_78:
    v21 = *(const CHAR **)&v8[v13 + 24];
    if ( !v21 )
      goto LABEL_39;
    v22 = -1;
    do
      ++v22;
    while ( v21[v22] );
    if ( !v22 )
      goto LABEL_39;
    if ( !MultiByteToWideChar(0, 0, v21, -1, Destination, 4096) )
      goto LABEL_65;
    if ( (unsigned int)CompareStrsCaseInsensitive(a2, Destination, 0xFFFFFFFFFFFFFFFFuLL) )
    {
LABEL_39:
      v23 = *(const char **)&v8[v13];
      if ( !v23 )
        goto LABEL_50;
      v24 = -1;
      do
        ++v24;
      while ( v23[v24] );
      if ( !v24 )
        goto LABEL_50;
      v25 = *(_QWORD *)&v8[v13 + 16];
      if ( !v25 )
        goto LABEL_50;
      v26 = -1;
      do
        ++v26;
      while ( *(_BYTE *)(v25 + v26) );
      if ( !v26 )
        goto LABEL_50;
      if ( (unsigned __int64)(v24 + 2 + v26) > 0x1000 )
        goto LABEL_51;
      strcpy_s(MultiByteStr, 0x1000u, v23);
      strcat_s(MultiByteStr, 0x1000u, "\\");
      strcat_s(MultiByteStr, 0x1000u, *(const char **)&v8[v13 + 16]);
      if ( !MultiByteToWideChar(0, 0, MultiByteStr, -1, Destination, 4096) )
        goto LABEL_65;
      goto LABEL_49;
    }
  }
LABEL_52:
  if ( pcReturned <= i )
  {
LABEL_67:
    Signal_Exception(&IID_IWshNetwork, L"WSHNetwork.SetDefaultPrinter", 0x1005u, a2);
    v11 = -2147352567;
    goto LABEL_68;
  }
  if ( Global::g_fWindowsNT )
  {
    wcscpy_s(Destination, 0x1000u, *(const wchar_t **)&v8[v13 + 8]);
    wcscat_s(Destination, 0x1000u, L",");
    wcscat_s(Destination, 0x1000u, *(const wchar_t **)&v8[v13 + 32]);
    wcscat_s(Destination, 0x1000u, L",");
    wcscat_s(Destination, 0x1000u, *(const wchar_t **)&v8[v13 + 24]);
    v11 = OpenRegSettings(v28, v27, v29, &hKey);
    if ( v11 >= 0 )
    {
      v11 = PutRegSettingsString(hKey, v30, (const BYTE *)Destination);
      if ( v11 >= 0 )
      {
        RegCloseKey(hKey);
        hKey = 0;
        dwResult = 0;
        SendMessageTimeoutW(
          HWND_BROADCAST,
          0x1Au,
          2u,
          (LPARAM)L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Windows",
          0,
          0x3E8u,
          &dwResult);
      }
    }
  }
  else
  {
    if ( !OpenPrinterA(*(LPSTR *)&v8[v13 + 8], &phPrinter, 0) )
      goto LABEL_65;
    v31 = 32;
    v6 = 1;
    while ( 1 )
    {
      v4 = (BYTE *)operator new(v31);
      if ( !v4 )
      {
        v11 = -2147024882;
        goto LABEL_68;
      }
      if ( GetPrinterA(phPrinter, 5u, v4, v31, &pcbNeeded) )
        break;
      LastError = GetLastError();
      v11 = LastError;
      if ( LastError != 122 )
        goto LABEL_11;
      operator delete(v4);
      v31 = pcbNeeded;
    }
    *((_DWORD *)v4 + 4) |= 4u;
    if ( !SetPrinterA(phPrinter, 5u, v4, 0) || (v11 = 0, v6 = 0, !ClosePrinter(phPrinter)) )
    {
LABEL_65:
      LastError = GetLastError();
      v11 = LastError;
      goto LABEL_11;
    }
  }
LABEL_68:
  operator delete(v8);
  if ( v4 )
    operator delete(v4);
LABEL_71:
  if ( hKey )
    RegCloseKey(hKey);
  if ( v6 )
    ClosePrinter(phPrinter);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180008930  push    rbp
0x180008932  push    rbx
0x180008933  push    rsi
0x180008934  push    rdi
0x180008935  push    r12
0x180008937  push    r13
0x180008939  push    r14
0x18000893b  push    r15
0x18000893d  lea     rbp, [rsp-2F78h]
0x180008945  mov     eax, 3078h
0x18000894a  call    _alloca_probe
0x18000894f  sub     rsp, rax
0x180008952  mov     rax, cs:__security_cookie
0x180008959  xor     rax, rsp
0x18000895c  mov     [rbp+2FB0h+var_50], rax
0x180008963  xor     r13d, r13d
0x180008966  mov     r14, rdx
0x180008969  test    rdx, rdx
0x18000896c  jnz     short loc_180008978
0x18000896e  mov     eax, 80004003h
0x180008973  jmp     loc_180008ECA
0x180008978  mov     [rsp+30B0h+var_3070], r13d
0x18000897d  mov     rsi, r13
0x180008980  mov     [rsp+30B0h+var_306C], r13d
0x180008985  mov     ebx, 550h
0x18000898a  mov     [rsp+30B0h+phPrinter], r13
0x18000898f  mov     r12d, r13d
0x180008992  mov     [rsp+30B0h+hKey], r13
0x180008997  mov     r15d, 6
0x18000899d  mov     ecx, ebx; Size
0x18000899f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800089a4  mov     rdi, rax
0x1800089a7  test    rax, rax
0x1800089aa  jz      loc_180008EA3
0x1800089b0  lea     rax, [rsp+30B0h+var_306C]
0x1800089b5  xor     edx, edx; Name
0x1800089b7  cmp     cs:?g_fWindowsNT@Global@@2_NA, r13b; bool Global::g_fWindowsNT
0x1800089be  mov     r9, rdi; pPrinterEnum
0x1800089c1  mov     [rsp+30B0h+pcReturned], rax; pcReturned
0x1800089c6  mov     ecx, r15d; Flags
0x1800089c9  lea     rax, [rsp+30B0h+var_3070]
0x1800089ce  mov     [rsp+30B0h+pcbNeeded], rax; pcbNeeded
0x1800089d3  lea     r8d, [rdx+2]; Level
0x1800089d7  mov     [rsp+30B0h+cbBuf], ebx; cbBuf
0x1800089db  jz      short loc_1800089E5
0x1800089dd  call    cs:__imp_EnumPrintersW
0x1800089e3  jmp     short loc_1800089EB
0x1800089e5  call    cs:__imp_EnumPrintersA
0x1800089eb  test    eax, eax
0x1800089ed  jnz     short loc_180008A20
0x1800089ef  call    cs:__imp_GetLastError
0x1800089f5  mov     ebx, eax
0x1800089f7  cmp     eax, 7Ah ; 'z'
0x1800089fa  jnz     short loc_180008A0A
0x1800089fc  mov     rcx, rdi; Block
0x1800089ff  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180008a04  mov     ebx, [rsp+30B0h+var_3070]
0x180008a08  jmp     short loc_18000899D
0x180008a0a  test    eax, eax
0x180008a0c  jle     loc_180008E8C
0x180008a12  movzx   ebx, ax
0x180008a15  or      ebx, 80070000h
0x180008a1b  jmp     loc_180008E8C
0x180008a20  mov     r15d, r13d
0x180008a23  cmp     r15d, [rsp+30B0h+var_306C]
0x180008a28  jnb     loc_180008E6B
0x180008a2e  mov     eax, r15d
0x180008a31  imul    rbx, rax, 88h
0x180008a38  cmp     cs:?g_fWindowsNT@Global@@2_NA, r13b; bool Global::g_fWindowsNT
0x180008a3f  mov     rax, [rbx+rdi+8]
0x180008a44  jz      loc_180008B0D
0x180008a4a  test    rax, rax
0x180008a4d  jz      short loc_180008A66
0x180008a4f  or      r8, 0FFFFFFFFFFFFFFFFh; unsigned __int64
0x180008a53  mov     rdx, rax; unsigned __int16 *
0x180008a56  mov     rcx, r14; unsigned __int16 *
0x180008a59  call    ?CompareStrsCaseInsensitive@@YAHPEBG0_K@Z; CompareStrsCaseInsensitive(ushort const *,ushort const *,unsigned __int64)
0x180008a5e  test    eax, eax
0x180008a60  jz      loc_180008CB6
0x180008a66  mov     rdx, [rbx+rdi+18h]; unsigned __int16 *
0x180008a6b  test    rdx, rdx
0x180008a6e  jz      short loc_180008A84
0x180008a70  or      r8, 0FFFFFFFFFFFFFFFFh; unsigned __int64
0x180008a74  mov     rcx, r14; unsigned __int16 *
0x180008a77  call    ?CompareStrsCaseInsensitive@@YAHPEBG0_K@Z; CompareStrsCaseInsensitive(ushort const *,ushort const *,unsigned __int64)
0x180008a7c  test    eax, eax
0x180008a7e  jz      loc_180008CB6
0x180008a84  mov     r8, [rbx+rdi]; Source
0x180008a88  test    r8, r8
0x180008a8b  jz      loc_180008CA4
0x180008a91  mov     rdx, [rbx+rdi+10h]
0x180008a96  test    rdx, rdx
0x180008a99  jz      loc_180008CA4
0x180008a9f  or      rax, 0FFFFFFFFFFFFFFFFh
0x180008aa3  mov     rcx, rax
0x180008aa6  inc     rcx
0x180008aa9  cmp     [r8+rcx*2], r13w
0x180008aae  jnz     short loc_180008AA6
0x180008ab0  inc     rax
0x180008ab3  cmp     [rdx+rax*2], r13w
0x180008ab8  jnz     short loc_180008AB0
0x180008aba  add     rcx, 2
0x180008abe  add     rax, rcx
0x180008ac1  mov     ecx, 1000h
0x180008ac6  cmp     rax, rcx
0x180008ac9  ja      loc_180008CAC
0x180008acf  mov     edx, ecx; SizeInWords
0x180008ad1  lea     rcx, [rsp+30B0h+Destination]; Destination
0x180008ad6  call    cs:__imp_wcscpy_s
0x180008adc  lea     r8, asc_18001404C; "\\"
0x180008ae3  mov     edx, 1000h; SizeInWords
0x180008ae8  lea     rcx, [rsp+30B0h+Destination]; Destination
0x180008aed  call    cs:__imp_wcscat_s
0x180008af3  mov     r8, [rbx+rdi+10h]; Source
0x180008af8  lea     rcx, [rsp+30B0h+Destination]; Destination
0x180008afd  mov     edx, 1000h; SizeInWords
0x180008b02  call    cs:__imp_wcscat_s
0x180008b08  jmp     loc_180008C8F
0x180008b0d  test    rax, rax
0x180008b10  jz      short loc_180008B68
0x180008b12  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180008b16  inc     rcx
0x180008b19  cmp     [rax+rcx], r13b
0x180008b1d  jnz     short loc_180008B16
0x180008b1f  test    rcx, rcx
0x180008b22  jz      short loc_180008B68
0x180008b24  lea     rcx, [rsp+30B0h+Destination]
0x180008b29  mov     dword ptr [rsp+30B0h+pcbNeeded], 1000h; cchWideChar
0x180008b31  mov     qword ptr [rsp+30B0h+cbBuf], rcx; lpWideCharStr
0x180008b36  or      r9d, 0FFFFFFFFh; cbMultiByte
0x180008b3a  xor     ecx, ecx; CodePage
0x180008b3c  mov     r8, rax; lpMultiByteStr
0x180008b3f  xor     edx, edx; dwFlags
0x180008b41  call    cs:__imp_MultiByteToWideChar
0x180008b47  test    eax, eax
0x180008b49  jz      loc_180008E57
0x180008b4f  or      r8, 0FFFFFFFFFFFFFFFFh; unsigned __int64
0x180008b53  lea     rdx, [rsp+30B0h+Destination]; unsigned __int16 *
0x180008b58  mov     rcx, r14; unsigned __int16 *
0x180008b5b  call    ?CompareStrsCaseInsensitive@@YAHPEBG0_K@Z; CompareStrsCaseInsensitive(ushort const *,ushort const *,unsigned __int64)
0x180008b60  test    eax, eax
0x180008b62  jz      loc_180008CB6
0x180008b68  mov     r8, [rbx+rdi+18h]; lpMultiByteStr
0x180008b6d  test    r8, r8
0x180008b70  jz      short loc_180008BC5
0x180008b72  or      rax, 0FFFFFFFFFFFFFFFFh
0x180008b76  inc     rax
0x180008b79  cmp     [r8+rax], r13b
0x180008b7d  jnz     short loc_180008B76
0x180008b7f  test    rax, rax
0x180008b82  jz      short loc_180008BC5
0x180008b84  lea     rax, [rsp+30B0h+Destination]
0x180008b89  mov     dword ptr [rsp+30B0h+pcbNeeded], 1000h; cchWideChar
0x180008b91  or      r9d, 0FFFFFFFFh; cbMultiByte
0x180008b95  mov     qword ptr [rsp+30B0h+cbBuf], rax; lpWideCharStr
0x180008b9a  xor     edx, edx; dwFlags
0x180008b9c  xor     ecx, ecx; CodePage
0x180008b9e  call    cs:__imp_MultiByteToWideChar
0x180008ba4  test    eax, eax
0x180008ba6  jz      loc_180008E57
0x180008bac  or      r8, 0FFFFFFFFFFFFFFFFh; unsigned __int64
0x180008bb0  lea     rdx, [rsp+30B0h+Destination]; unsigned __int16 *
0x180008bb5  mov     rcx, r14; unsigned __int16 *
0x180008bb8  call    ?CompareStrsCaseInsensitive@@YAHPEBG0_K@Z; CompareStrsCaseInsensitive(ushort const *,ushort const *,unsigned __int64)
0x180008bbd  test    eax, eax
0x180008bbf  jz      loc_180008CB6
0x180008bc5  mov     r8, [rbx+rdi]; Source
0x180008bc9  test    r8, r8
0x180008bcc  jz      loc_180008CA4
0x180008bd2  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180008bd6  inc     rcx
0x180008bd9  cmp     [r8+rcx], r13b
0x180008bdd  jnz     short loc_180008BD6
0x180008bdf  test    rcx, rcx
0x180008be2  jz      loc_180008CA4
0x180008be8  mov     rdx, [rbx+rdi+10h]
0x180008bed  test    rdx, rdx
0x180008bf0  jz      loc_180008CA4
0x180008bf6  or      rax, 0FFFFFFFFFFFFFFFFh
0x180008bfa  inc     rax
0x180008bfd  cmp     [rdx+rax], r13b
0x180008c01  jnz     short loc_180008BFA
0x180008c03  test    rax, rax
0x180008c06  jz      loc_180008CA4
0x180008c0c  add     rcx, 2
0x180008c10  add     rax, rcx
0x180008c13  mov     ecx, 1000h
0x180008c18  cmp     rax, rcx
0x180008c1b  ja      loc_180008CAC
0x180008c21  mov     edx, ecx; SizeInBytes
0x180008c23  lea     rcx, [rbp+2FB0h+MultiByteStr]; Destination
0x180008c2a  call    cs:__imp_strcpy_s
0x180008c30  lea     r8, asc_180014050; "\\"
0x180008c37  mov     edx, 1000h; SizeInBytes
0x180008c3c  lea     rcx, [rbp+2FB0h+MultiByteStr]; Destination
0x180008c43  call    cs:__imp_strcat_s
0x180008c49  mov     r8, [rbx+rdi+10h]; Source
0x180008c4e  lea     rcx, [rbp+2FB0h+MultiByteStr]; Destination
0x180008c55  mov     edx, 1000h; SizeInBytes
0x180008c5a  call    cs:__imp_strcat_s
0x180008c60  lea     rax, [rsp+30B0h+Destination]
0x180008c65  mov     dword ptr [rsp+30B0h+pcbNeeded], 1000h; cchWideChar
0x180008c6d  or      r9d, 0FFFFFFFFh; cbMultiByte
0x180008c71  mov     qword ptr [rsp+30B0h+cbBuf], rax; lpWideCharStr
0x180008c76  lea     r8, [rbp+2FB0h+MultiByteStr]; lpMultiByteStr
0x180008c7d  xor     edx, edx; dwFlags
0x180008c7f  xor     ecx, ecx; CodePage
0x180008c81  call    cs:__imp_MultiByteToWideChar
0x180008c87  test    eax, eax
0x180008c89  jz      loc_180008E57
0x180008c8f  or      r8, 0FFFFFFFFFFFFFFFFh; unsigned __int64
0x180008c93  lea     rdx, [rsp+30B0h+Destination]; unsigned __int16 *
0x180008c98  mov     rcx, r14; unsigned __int16 *
0x180008c9b  call    ?CompareStrsCaseInsensitive@@YAHPEBG0_K@Z; CompareStrsCaseInsensitive(ushort const *,ushort const *,unsigned __int64)
0x180008ca0  test    eax, eax
0x180008ca2  jz      short loc_180008CB6
0x180008ca4  inc     r15d
0x180008ca7  jmp     loc_180008A23
0x180008cac  mov     ebx, 80004005h
0x180008cb1  jmp     loc_180008E8C
0x180008cb6  cmp     [rsp+30B0h+var_306C], r15d
0x180008cbb  jbe     loc_180008E6B
0x180008cc1  cmp     cs:?g_fWindowsNT@Global@@2_NA, r13b; bool Global::g_fWindowsNT
0x180008cc8  mov     rcx, [rbx+rdi+8]; pPrinterName
0x180008ccd  jz      loc_180008DB3
0x180008cd3  mov     r8, rcx; Source
0x180008cd6  mov     r14d, 1000h
0x180008cdc  mov     edx, r14d; SizeInWords
0x180008cdf  lea     rcx, [rsp+30B0h+Destination]; Destination
0x180008ce4  call    cs:__imp_wcscpy_s
0x180008cea  lea     r8, asc_180014094; ","
0x180008cf1  mov     edx, r14d; SizeInWords
0x180008cf4  lea     rcx, [rsp+30B0h+Destination]; Destination
0x180008cf9  call    cs:__imp_wcscat_s
0x180008cff  mov     r8, [rbx+rdi+20h]; Source
0x180008d04  lea     rcx, [rsp+30B0h+Destination]; Destination
0x180008d09  mov     edx, r14d; SizeInWords
0x180008d0c  call    cs:__imp_wcscat_s
0x180008d12  lea     r8, asc_180014094; ","
0x180008d19  mov     edx, r14d; SizeInWords
0x180008d1c  lea     rcx, [rsp+30B0h+Destination]; Destination
0x180008d21  call    cs:__imp_wcscat_s
0x180008d27  mov     r8, [rbx+rdi+18h]; Source
0x180008d2c  lea     rcx, [rsp+30B0h+Destination]; Destination
0x180008d31  mov     edx, r14d; SizeInWords
0x180008d34  call    cs:__imp_wcscat_s
0x180008d3a  lea     r9, [rsp+30B0h+hKey]; HKEY *
0x180008d3f  call    ?OpenRegSettings@@YAJPEAUHKEY__@@PEBGKPEAPEAU1@@Z; OpenRegSettings(HKEY__ *,ushort const *,ulong,HKEY__ * *)
0x180008d44  mov     ebx, eax
0x180008d46  test    eax, eax
0x180008d48  js      loc_180008E8C
0x180008d4e  mov     rcx, [rsp+30B0h+hKey]; hKey
0x180008d53  lea     r8, [rsp+30B0h+Destination]; unsigned __int16 *
0x180008d58  call    ?PutRegSettingsString@@YAJPEAUHKEY__@@PEBG1_N@Z; PutRegSettingsString(HKEY__ *,ushort const *,ushort const *,bool)
0x180008d5d  mov     ebx, eax
0x180008d5f  test    eax, eax
0x180008d61  js      loc_180008E8C
0x180008d67  mov     rcx, [rsp+30B0h+hKey]; hKey
0x180008d6c  call    cs:__imp_RegCloseKey
0x180008d72  mov     edx, 1Ah; Msg
0x180008d77  mov     [rsp+30B0h+hKey], r13
0x180008d7c  lea     rax, [rsp+30B0h+dwResult]
0x180008d81  mov     [rsp+30B0h+dwResult], r13
0x180008d86  mov     [rsp+30B0h+pcReturned], rax; lpdwResult
0x180008d8b  lea     r9, WideCharStr; "Software\\Microsoft\\Windows NT\\Curren"...
0x180008d92  mov     dword ptr [rsp+30B0h+pcbNeeded], 3E8h; uTimeout
0x180008d9a  mov     ecx, 0FFFFh; hWnd
0x180008d9f  lea     r8d, [rdx-18h]; wParam
0x180008da3  mov     [rsp+30B0h+cbBuf], r13d; fuFlags
0x180008da8  call    cs:__imp_SendMessageTimeoutW
0x180008dae  jmp     loc_180008E8C
0x180008db3  xor     r8d, r8d; pDefault
0x180008db6  lea     rdx, [rsp+30B0h+phPrinter]; phPrinter
0x180008dbb  call    cs:__imp_OpenPrinterA
0x180008dc1  test    eax, eax
0x180008dc3  jz      loc_180008E57
0x180008dc9  mov     ebx, 20h ; ' '
0x180008dce  lea     r12d, [rbx-1Fh]
0x180008dd2  lea     r14d, [rbx-1Bh]
0x180008dd6  mov     ecx, ebx; Size
0x180008dd8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180008ddd  mov     rsi, rax
0x180008de0  test    rax, rax
0x180008de3  jz      short loc_180008E64
0x180008de5  mov     rcx, [rsp+30B0h+phPrinter]; hPrinter
0x180008dea  lea     rax, [rsp+30B0h+var_3070]
0x180008def  mov     r9d, ebx; cbBuf
0x180008df2  mov     qword ptr [rsp+30B0h+cbBuf], rax; pcbNeeded
0x180008df7  mov     r8, rsi; pPrinter
0x180008dfa  mov     edx, r14d; Level
0x180008dfd  call    cs:__imp_GetPrinterA
0x180008e03  test    eax, eax
0x180008e05  jnz     short loc_180008E26
0x180008e07  call    cs:__imp_GetLastError
0x180008e0d  mov     ebx, eax
0x180008e0f  cmp     eax, 7Ah ; 'z'
0x180008e12  jnz     loc_180008A0A
0x180008e18  mov     rcx, rsi; Block
0x180008e1b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180008e20  mov     ebx, [rsp+30B0h+var_3070]
  ... truncated ...
```
