# AppModule::ParseCommandLine(ushort const *)

- ea: `0x14000fdf8`
- end: `0x1400107fa`
- name: `?ParseCommandLine@AppModule@@QEAAJPEBG@Z`
- size: `2562`
- prototype: `int(AppModule *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x14000f8f0`

## callees

- `0x140001264`
- `0x14000441c`
- `0x14000e280`
- `0x14000e360`
- `0x14000ec58`
- `0x14000f6f4`
- `0x14000fdf8`
- `0x140013490`

## import_xrefs

- `KERNEL32!LocalFree` at `0x14000ff3d`
- `KERNEL32!LocalFree` at `0x14000ff9d`
- `KERNEL32!LocalFree` at `0x14000ff3d`
- `KERNEL32!LocalFree` at `0x14000ff9d`
- `KERNEL32!GetLastError` at `0x14000fe36`
- `KERNEL32!GetLastError` at `0x14000fe36`
- `msvcrt!_wcsicmp` at `0x14000ffe2`
- `msvcrt!_wcsicmp` at `0x14000fffb`
- `msvcrt!_wcsicmp` at `0x140010014`
- `msvcrt!_wcsicmp` at `0x14001002d`
- `msvcrt!_wcsicmp` at `0x140010052`
- `msvcrt!_wcsicmp` at `0x140010077`
- `msvcrt!_wcsicmp` at `0x1400100a9`
- `msvcrt!_wcsicmp` at `0x1400100db`
- `msvcrt!_wcsicmp` at `0x140010478`
- `msvcrt!_wcsicmp` at `0x14000ffe2`
- `msvcrt!_wcsicmp` at `0x14000fffb`
- `msvcrt!_wcsicmp` at `0x140010014`
- `msvcrt!_wcsicmp` at `0x14001002d`
- `msvcrt!_wcsicmp` at `0x140010052`
- `msvcrt!_wcsicmp` at `0x140010077`
- `msvcrt!_wcsicmp` at `0x1400100a9`
- `msvcrt!_wcsicmp` at `0x1400100db`
- `msvcrt!_wcsicmp` at `0x140010478`
- `msvcrt!_wcsnicmp` at `0x140010113`
- `msvcrt!_wcsnicmp` at `0x1400101a5`
- `msvcrt!_wcsnicmp` at `0x14001026a`
- `msvcrt!_wcsnicmp` at `0x140010291`
- `msvcrt!_wcsnicmp` at `0x1400102ee`
- `msvcrt!_wcsnicmp` at `0x140010113`
- `msvcrt!_wcsnicmp` at `0x1400101a5`
- `msvcrt!_wcsnicmp` at `0x14001026a`
- `msvcrt!_wcsnicmp` at `0x140010291`
- `msvcrt!_wcsnicmp` at `0x1400102ee`
- `msvcrt!iswdigit` at `0x140010207`
- `msvcrt!iswdigit` at `0x140010207`
- `msvcrt!wcschr` at `0x140010351`
- `msvcrt!wcschr` at `0x140010351`
- `SHELL32!CommandLineToArgvW` at `0x14000fe28`
- `SHELL32!CommandLineToArgvW` at `0x14000fe28`
- `SHLWAPI!StrToIntExW` at `0x14001015f`
- `SHLWAPI!StrToIntExW` at `0x14001015f`
- `SHLWAPI!PathFindExtensionW` at `0x140010468`
- `SHLWAPI!PathFindExtensionW` at `0x140010468`
- `ServicingCommon!SczFree` at `0x14000ff2b`
- `ServicingCommon!SczFree` at `0x140010176`
- `ServicingCommon!SczFree` at `0x14001040d`
- `ServicingCommon!SczFree` at `0x14000ff2b`
- `ServicingCommon!SczFree` at `0x140010176`
- `ServicingCommon!SczFree` at `0x14001040d`
- `ServicingCommon!SczAlloc` at `0x14000fee6`
- `ServicingCommon!SczAlloc` at `0x14000fee6`
- `ServicingCommon!SczAllocPrefixSz` at `0x14001023c`
- `ServicingCommon!SczAllocPrefixSz` at `0x14001023c`

## string_xrefs

- `0x14000fe4d`: `CommandLineToArgvW() failed.`
- `0x14000fe61`: `AppModule::ParseCommandLine`
- `0x14000ff04`: `AppModule::ParseCommandLine`
- `0x14000ff56`: `AppModule::ParseCommandLine`
- `0x14000ff89`: `AppModule::ParseCommandLine`
- `0x14001064a`: `AppModule::ParseCommandLine`
- `0x140010667`: `AppModule::ParseCommandLine`
- `0x14001074b`: `AppModule::ParseCommandLine`
- `0x1400107e9`: `Failed to get command line length.`
- `0x14001079c`: `Failed: /uninstall with /kb and /quiet options is not supported`
- `0x14000ff4a`: `Command line is %ls`
- `0x140010026`: `/uninstall`

## pseudocode

```c
__int64 __fastcall AppModule::ParseCommandLine(AppModule *this, const unsigned __int16 *a2)
{
  const wchar_t *v2; // rbx
  LPWSTR *v4; // r12
  signed int LastError; // eax
  signed int ArgumentValue; // edi
  __int64 v7; // rdx
  __int64 v8; // r8
  const wchar_t *v9; // rax
  __int64 v10; // rcx
  unsigned __int64 v11; // r13
  unsigned __int16 **v12; // rbx
  HLOCAL v13; // rbx
  int v15; // eax
  int v16; // r15d
  int v17; // ecx
  __int64 v18; // rbx
  int v19; // eax
  int v20; // eax
  int v21; // eax
  __int64 v22; // rdx
  __int64 *v23; // r15
  __int64 v24; // rcx
  unsigned __int64 v25; // rax
  unsigned __int64 v26; // rbx
  unsigned __int64 v27; // rax
  AppModule *v28; // rcx
  AppModule *v29; // rcx
  unsigned __int16 **v30; // r8
  unsigned __int64 v31; // rax
  wchar_t *v32; // rax
  wchar_t *v33; // rbx
  _WORD *v34; // rax
  PCWSTR v35; // r8
  __int64 v36; // rdx
  __int64 v37; // rcx
  _WORD *v38; // rcx
  int v39; // eax
  const WCHAR *v40; // r9
  const wchar_t *ExtensionW; // rax
  int v42; // [rsp+30h] [rbp-18h]
  PCWSTR pszString[2]; // [rsp+38h] [rbp-10h] BYREF
  HLOCAL hMem; // [rsp+90h] [rbp+48h] BYREF
  const unsigned __int16 *v45; // [rsp+98h] [rbp+50h]
  unsigned int v46; // [rsp+A0h] [rbp+58h]
  int pNumArgs; // [rsp+A8h] [rbp+60h] BYREF

  v45 = a2;
  v2 = a2;
  pNumArgs = 0;
  pszString[0] = 0;
  v4 = CommandLineToArgvW(a2, &pNumArgs);
  if ( !v4 )
  {
    LastError = GetLastError();
    ArgumentValue = LastError;
    if ( LastError > 0 )
      ArgumentValue = (unsigned __int16)LastError | 0x80070000;
    if ( ArgumentValue >= 0 )
      ArgumentValue = -2147467259;
    WusaLogDebugEventA(L"AppModule::ParseCommandLine", 368, "CommandLineToArgvW() failed.");
    goto LABEL_17;
  }
  if ( pNumArgs < 2 )
  {
    ArgumentValue = -2147024809;
    WusaLogDebugEventA(L"AppModule::ParseCommandLine", 373, "Error: Too few arguments.");
    goto LABEL_17;
  }
  if ( !v2 )
  {
    ArgumentValue = -2147024809;
LABEL_150:
    WusaLogDebugEventA(L"AppModule::ParseCommandLine", 377, "Failed to get command line length.");
    goto LABEL_17;
  }
  v9 = v2;
  v10 = 0x7FFFFFFF;
  do
  {
    if ( !*v9 )
      break;
    ++v9;
    --v10;
  }
  while ( v10 );
  ArgumentValue = v10 == 0 ? 0x80070057 : 0;
  v11 = (0x7FFFFFFF - v10) & -(__int64)(v10 != 0);
  if ( !v10 )
    goto LABEL_150;
  v12 = (unsigned __int16 **)((char *)this + 224);
  ArgumentValue = SczAlloc((char *)this + 224, (0x7FFFFFFF - v10) & -(__int64)(v10 != 0));
  if ( ArgumentValue < 0 )
  {
    WusaLogDebugEventA(L"AppModule::ParseCommandLine", 380, "Failed to allocate memory for ignored arguments.");
    goto LABEL_16;
  }
  v15 = 0;
  LODWORD(hMem) = 0;
  v16 = 0;
  v46 = 0;
  v7 = 0;
  v17 = 1;
  v42 = 1;
  if ( pNumArgs <= 1 )
  {
LABEL_104:
    if ( *((_DWORD *)this + 23) )
    {
      if ( v15 )
      {
        if ( v16 )
          goto LABEL_108;
      }
      else if ( !v16 )
      {
        goto LABEL_108;
      }
      if ( (_DWORD)v7 )
        goto LABEL_108;
      if ( v16 && *((_DWORD *)this + 26) )
      {
        ArgumentValue = -2147024809;
        WusaLogDebugEventA(
          L"AppModule::ParseCommandLine",
          654,
          "Failed: /uninstall with /kb and /quiet options is not supported");
        goto LABEL_16;
      }
      goto LABEL_134;
    }
    if ( !v15 )
    {
LABEL_108:
      ArgumentValue = -2147024809;
      WusaLogDebugEventA(L"AppModule::ParseCommandLine", 647, "Failed to get MSU file name or KB number");
      goto LABEL_16;
    }
    if ( *((_DWORD *)this + 29) == 4 )
    {
      if ( !*((_DWORD *)this + 26) )
        goto LABEL_108;
    }
    else if ( *((_DWORD *)this + 29) == 2 )
    {
LABEL_133:
      if ( !*((_DWORD *)this + 26) )
        goto LABEL_108;
LABEL_134:
      if ( *((_DWORD *)this + 25) )
      {
        if ( (int)WusaMessageBox(0xEA7Eu, 0xEA60u, 1, (PCWSTR)0xFFFE, 0) < 0 )
          WusaLogDebugEventA(L"AppModule::ParseCommandLine", 663, "Failed to show /extract not supported message box");
        ArgumentValue = -2147024809;
        WusaLogDebugEventA(L"AppModule::ParseCommandLine", 667, "Failed: /extract is not a supported option");
      }
      else if ( *((_DWORD *)this + 26) )
      {
        ArgumentValue = StringCchCatW(*v12, v11, L"/quiet");
        if ( ArgumentValue < 0 )
          WusaLogDebugEventA(L"AppModule::ParseCommandLine", 676, "Failed to add an argument to the ignored list");
      }
      goto LABEL_16;
    }
    if ( *((_DWORD *)this + 29) != 3 )
      goto LABEL_134;
    goto LABEL_133;
  }
  while ( 1 )
  {
    v18 = v17;
    if ( !_wcsicmp(v4[v17], L"/?") || !_wcsicmp(v4[v18], L"/h") || !_wcsicmp(v4[v18], L"/help") )
    {
      *((_DWORD *)this + 30) |= 1u;
      *((_DWORD *)this + 22) = 1;
      goto LABEL_101;
    }
    if ( !_wcsicmp(v4[v18], L"/uninstall") )
    {
      *((_DWORD *)this + 30) |= 0x40u;
      *((_DWORD *)this + 23) = 1;
LABEL_101:
      v15 = (int)hMem;
LABEL_102:
      v7 = v46;
      v12 = (unsigned __int16 **)((char *)this + 224);
      goto LABEL_103;
    }
    if ( !_wcsicmp(v4[v18], L"/quiet") )
    {
      *((_DWORD *)this + 30) |= 2u;
      *((_DWORD *)this + 26) = 1;
      goto LABEL_101;
    }
    v19 = _wcsicmp(v4[v18], L"/norestart");
    v8 = 0;
    if ( !v19 )
    {
      if ( *((_DWORD *)this + 29) )
      {
        ArgumentValue = -2147024809;
        WusaLogDebugEventA(L"AppModule::ParseCommandLine", 422, "Failed. Restart mode was supplied multiple times");
        goto LABEL_16;
      }
      *((_DWORD *)this + 30) |= 4u;
      *((_DWORD *)this + 29) = 1;
      goto LABEL_101;
    }
    v20 = _wcsicmp(v4[v18], L"/promptrestart");
    v8 = 0;
    if ( !v20 )
    {
      if ( *((_DWORD *)this + 29) )
      {
        ArgumentValue = -2147024809;
        WusaLogDebugEventA(L"AppModule::ParseCommandLine", 437, "Failed. Restart mode was supplied multiple times");
        goto LABEL_16;
      }
      *((_DWORD *)this + 30) |= 0x20u;
      *((_DWORD *)this + 29) = 4;
      goto LABEL_101;
    }
    v21 = _wcsicmp(v4[v18], L"/forcerestart");
    v8 = 0;
    if ( !v21 )
    {
      if ( *((_DWORD *)this + 29) )
      {
        ArgumentValue = -2147024809;
        WusaLogDebugEventA(L"AppModule::ParseCommandLine", 452, "Failed. Restart mode was supplied multiple times");
        goto LABEL_16;
      }
      *((_DWORD *)this + 30) |= 8u;
      *((_DWORD *)this + 29) = 2;
      goto LABEL_101;
    }
    if ( !_wcsnicmp(v4[v18], L"/warnrestart", 0xCu) )
    {
      if ( *((_DWORD *)this + 29) )
      {
        ArgumentValue = -2147024809;
        WusaLogDebugEventA(L"AppModule::ParseCommandLine", 467, "Failed. Restart mode was supplied multiple times");
        goto LABEL_16;
      }
      ArgumentValue = AppModule::GetArgumentValue(0, L"/warnrestart", v4[v18], L"30", (unsigned __int16 **)pszString);
      if ( ArgumentValue < 0 )
      {
        WusaLogDebugEventA(L"AppModule::ParseCommandLine", 471, "Failed to parse switch");
        goto LABEL_16;
      }
      if ( !StrToIntExW(pszString[0], 0, (int *)this + 58) )
      {
        ArgumentValue = -2147024809;
        WusaLogDebugEventA(L"AppModule::ParseCommandLine", 476, "Failed. /warnrestart has invalid format");
        goto LABEL_16;
      }
      if ( pszString[0] )
      {
        SczFree(pszString[0], v22, v8);
        pszString[0] = 0;
      }
      *((_DWORD *)this + 30) |= 0x10u;
      *((_DWORD *)this + 29) = 3;
      goto LABEL_101;
    }
    if ( !_wcsnicmp(v4[v18], L"/kb", 3u) )
      break;
    if ( !_wcsnicmp(v4[v18], L"/extract", 8u) )
    {
      *((_DWORD *)this + 25) = 1;
      goto LABEL_101;
    }
    if ( !_wcsnicmp(v4[v18], L"/log", 4u) )
    {
      if ( *((_QWORD *)this + 27) )
      {
        ArgumentValue = -2147024809;
        WusaLogDebugEventA(L"AppModule::ParseCommandLine", 529, "Failed. /log was supplied multiple times");
        goto LABEL_16;
      }
      ArgumentValue = AppModule::GetArgumentValue(v28, L"/log", v4[v18], L"wusa.etl", (unsigned __int16 **)this + 27);
      if ( ArgumentValue < 0 )
      {
        WusaLogDebugEventA(L"AppModule::ParseCommandLine", 533, "Failed to parse switch");
        goto LABEL_16;
      }
      *((_DWORD *)this + 30) |= 0x80u;
      goto LABEL_101;
    }
    if ( !_wcsnicmp(v4[v18], L"/gpmode", 7u) )
    {
      if ( *((_DWORD *)this + 27) )
      {
        ArgumentValue = -2147024809;
        WusaLogDebugEventA(L"AppModule::ParseCommandLine", 546, "Failed. /gpmode was supplied multiple times");
        goto LABEL_16;
      }
      ArgumentValue = AppModule::GetArgumentValue(v29, L"/gpmode", v4[v18], 0, (unsigned __int16 **)pszString);
      if ( ArgumentValue < 0 )
      {
        WusaLogDebugEventA(L"AppModule::ParseCommandLine", 550, "Failed to parse switch");
        goto LABEL_16;
      }
      v31 = -1;
      do
        ++v31;
      while ( pszString[0][v31] );
      if ( v31 <= 1 || (v32 = wcschr(pszString[0] + 1, 0x3Au), (v33 = v32) == 0) )
      {
        ArgumentValue = -2147024809;
        WusaLogDebugEventA(L"AppModule::ParseCommandLine", 562, "Failed. /gpmode has invalid format");
        goto LABEL_16;
      }
      *v32 = 0;
      v34 = operator new(0x4Eu);
      *((_QWORD *)this + 25) = v34;
      if ( !v34 )
      {
        WusaLogDebugEventA(L"AppModule::ParseCommandLine", 568, "Failed to allocate memory for product code");
        ArgumentValue = -2147024882;
        goto LABEL_16;
      }
      v35 = pszString[0];
      v36 = 39;
      v37 = 2147483646;
      do
      {
        if ( !v37 )
          break;
        if ( !*v35 )
          break;
        *v34++ = *v35++;
        --v37;
        --v36;
      }
      while ( v36 );
      v38 = v34 - 1;
      if ( v36 )
        v38 = v34;
      *v38 = 0;
      v8 = 0;
      ArgumentValue = v36 == 0 ? 0x8007007A : 0;
      if ( !v36 )
      {
        WusaLogDebugEventA(L"AppModule::ParseCommandLine", 571, "Failed to set product code to %ls", pszString[0]);
        goto LABEL_16;
      }
      if ( v33[1] )
      {
        if ( v33[1] != 49 )
        {
          ArgumentValue = -2147024809;
          WusaLogDebugEventA(L"AppModule::ParseCommandLine", 584, "Failed. /gpmode has invalid format");
          goto LABEL_16;
        }
        v39 = 1;
      }
      else
      {
        v39 = 0;
      }
      *((_DWORD *)this + 28) = v39;
      if ( pszString[0] )
      {
        SczFree(pszString[0], 112, 0);
        pszString[0] = 0;
      }
      *((_DWORD *)this + 30) |= 0x402u;
      *((_DWORD *)this + 27) = 1;
      *((_DWORD *)this + 26) = 1;
      goto LABEL_101;
    }
    v40 = v4[v18];
    if ( ((*v40 - 45) & 0xFFFD) != 0 )
    {
      if ( (_DWORD)hMem )
      {
        ArgumentValue = -2147024809;
        WusaLogDebugEventA(L"AppModule::ParseCommandLine", 612, "Unrecognized argument %S", v40);
        goto LABEL_16;
      }
      ArgumentValue = WusaGetFullPathName(v40, (unsigned __int16 **)this + 21, v30);
      ExtensionW = PathFindExtensionW(*((LPCWSTR *)this + 21));
      if ( _wcsicmp(ExtensionW, L"msu2") )
        *((_DWORD *)this + 24) = 1;
      if ( ArgumentValue < 0 )
      {
        WusaLogDebugEventA(L"AppModule::ParseCommandLine", 625, "Failed to get MSU file name");
        goto LABEL_16;
      }
      v15 = 1;
      LODWORD(hMem) = 1;
      goto LABEL_102;
    }
    v12 = (unsigned __int16 **)((char *)this + 224);
    ArgumentValue = StringCchCatW(*((unsigned __int16 **)this + 28), v11, v40);
    if ( ArgumentValue < 0 )
    {
      WusaLogDebugEventA(L"AppModule::ParseCommandLine", 599, "Failed to add an argument to the ignored list");
      goto LABEL_16;
    }
    ArgumentValue = StringCchCatW(*v12, v11, L" ");
    if ( ArgumentValue < 0 )
    {
      WusaLogDebugEventA(
        L"AppModule::ParseCommandLine",
        603,
        "Failed to add a blank space to the ignored argument list");
      goto LABEL_16;
    }
    v15 = (int)hMem;
    v7 = 1;
    v46 = 1;
LABEL_103:
    v17 = v42 + 1;
    v42 = v17;
    if ( v17 >= pNumArgs )
      goto LABEL_104;
  }
  v23 = (__int64 *)((char *)this + 208);
  if ( *((_QWORD *)this + 26) )
  {
    ArgumentValue = -2147024809;
    WusaLogDebugEventA(L"AppModule::ParseCommandLine", 492, "Failed. /kb was supplied multiple times");
    goto LABEL_16;
  }
  ArgumentValue = AppModule::GetArgumentValue(0, L"/kb", v4[v18], 0, (unsigned __int16 **)this + 26);
  if ( ArgumentValue < 0 )
  {
    WusaLogDebugEventA(L"AppModule::ParseCommandLine", 496, "Failed to parse switch");
    goto LABEL_16;
  }
  v24 = *v23;
  v25 = -1;
  do
    ++v25;
  while ( *(_WORD *)(v24 + 2 * v25) );
  v26 = 1;
  if ( v25 <= 1 )
  {
LABEL_61:
    ArgumentValue = SczAllocPrefixSz((char *)this + 208, L"KB");
    if ( ArgumentValue < 0 )
    {
      WusaLogDebugEventA(L"AppModule::ParseCommandLine", 508, "Failed to prefix KB number");
      goto LABEL_16;
    }
    *((_DWORD *)this + 30) |= 0x200u;
    v16 = 1;
    goto LABEL_101;
  }
  while ( iswdigit(*(_WORD *)(v24 + 2 * v26)) )
  {
    v24 = *v23;
    ++v26;
    v27 = -1;
    do
      ++v27;
    while ( *(_WORD *)(v24 + 2 * v27) );
    if ( v26 >= v27 )
      goto LABEL_61;
  }
  ArgumentValue = -2147024809;
  WusaLogDebugEventA(L"AppModule::ParseCommandLine", 503, "Failed. /kb has invalid format");
LABEL_16:
  v2 = v45;
LABEL_17:
  if ( *((_DWORD *)this + 22) )
    ArgumentValue = 1;
  if ( pszString[0] )
  {
    SczFree(pszString[0], v7, v8);
    pszString[0] = 0;
  }
  if ( v4 )
    LocalFree(v4);
  if ( ArgumentValue < 0 )
  {
    WusaLogDebugEventA(L"AppModule::ParseCommandLine", 703, "Command line is %ls", v2);
    hMem = 0;
    WusaGetErrorMessage(ArgumentValue, (unsigned __int16 **)&hMem);
    v13 = hMem;
    WusaLogDebugEventA(
      L"AppModule::ParseCommandLine",
      705,
      "Exit with error code 0X%x (%ls)",
      ArgumentValue,
      (const wchar_t *)hMem);
    if ( v13 )
      LocalFree(v13);
  }
  return (unsigned int)ArgumentValue;
}

```

## disassembly

```asm
0x14000fdf8  mov     [rsp-40h+arg_8], rdx
0x14000fdfd  push    rbp
0x14000fdfe  push    rbx
0x14000fdff  push    rsi
0x14000fe00  push    rdi
0x14000fe01  push    r12
0x14000fe03  push    r13
0x14000fe05  push    r14
0x14000fe07  push    r15
0x14000fe09  mov     rbp, rsp
0x14000fe0c  sub     rsp, 48h
0x14000fe10  mov     rbx, rdx
0x14000fe13  mov     rsi, rcx
0x14000fe16  xor     r13d, r13d
0x14000fe19  lea     rdx, [rbp+pNumArgs]; pNumArgs
0x14000fe1d  mov     rcx, rbx; lpCmdLine
0x14000fe20  mov     [rbp+pNumArgs], r13d
0x14000fe24  mov     [rbp+pszString], r13
0x14000fe28  call    cs:__imp_CommandLineToArgvW
0x14000fe2e  mov     r12, rax
0x14000fe31  test    rax, rax
0x14000fe34  jnz     short loc_14000FE72
0x14000fe36  call    cs:__imp_GetLastError
0x14000fe3c  mov     edi, eax
0x14000fe3e  test    eax, eax
0x14000fe40  jle     short loc_14000FE4B
0x14000fe42  movzx   edi, ax
0x14000fe45  or      edi, 80070000h
0x14000fe4b  test    edi, edi
0x14000fe4d  lea     r8, aCommandlinetoa; "CommandLineToArgvW() failed."
0x14000fe54  mov     eax, 80004005h
0x14000fe59  mov     edx, 170h
0x14000fe5e  cmovns  edi, eax
0x14000fe61  lea     rcx, aAppmoduleParse; "AppModule::ParseCommandLine"
0x14000fe68  call    WusaLogDebugEventA
0x14000fe6d  jmp     loc_14000FF14
0x14000fe72  cmp     [rbp+pNumArgs], 2
0x14000fe76  jge     short loc_14000FE8B
0x14000fe78  mov     edi, 80070057h
0x14000fe7d  lea     r8, aErrorTooFewArg; "Error: Too few arguments."
0x14000fe84  mov     edx, 175h
0x14000fe89  jmp     short loc_14000FE61
0x14000fe8b  test    rbx, rbx
0x14000fe8e  jz      loc_1400107E4
0x14000fe94  mov     edx, 7FFFFFFFh
0x14000fe99  mov     rax, rbx
0x14000fe9c  mov     ecx, edx
0x14000fe9e  cmp     [rax], r13w
0x14000fea2  jz      short loc_14000FEAE
0x14000fea4  add     rax, 2
0x14000fea8  sub     rcx, 1
0x14000feac  jnz     short loc_14000FE9E
0x14000feae  mov     rax, rcx
0x14000feb1  mov     r14d, 80070057h
0x14000feb7  neg     rax
0x14000feba  mov     rax, rcx
0x14000febd  sbb     edi, edi
0x14000febf  sub     rdx, rcx
0x14000fec2  not     edi
0x14000fec4  and     edi, r14d
0x14000fec7  neg     rax
0x14000feca  sbb     r13, r13
0x14000fecd  and     r13, rdx
0x14000fed0  test    rcx, rcx
0x14000fed3  jz      loc_1400107E9
0x14000fed9  lea     rbx, [rsi+0E0h]
0x14000fee0  mov     rdx, r13
0x14000fee3  mov     rcx, rbx
0x14000fee6  call    cs:__imp_SczAlloc
0x14000feec  xor     ecx, ecx
0x14000feee  mov     edi, eax
0x14000fef0  test    eax, eax
0x14000fef2  jns     loc_14000FFB6
0x14000fef8  lea     r8, aFailedToAlloca_14; "Failed to allocate memory for ignored a"...
0x14000feff  mov     edx, 17Ch
0x14000ff04  lea     rcx, aAppmoduleParse; "AppModule::ParseCommandLine"
0x14000ff0b  call    WusaLogDebugEventA
0x14000ff10  mov     rbx, [rbp+arg_8]
0x14000ff14  cmp     dword ptr [rsi+58h], 0
0x14000ff18  mov     eax, 1
0x14000ff1d  mov     rcx, [rbp+pszString]
0x14000ff21  cmovnz  edi, eax
0x14000ff24  xor     esi, esi
0x14000ff26  test    rcx, rcx
0x14000ff29  jz      short loc_14000FF35
0x14000ff2b  call    cs:__imp_SczFree
0x14000ff31  mov     [rbp+pszString], rsi
0x14000ff35  test    r12, r12
0x14000ff38  jz      short loc_14000FF43
0x14000ff3a  mov     rcx, r12; hMem
0x14000ff3d  call    cs:__imp_LocalFree
0x14000ff43  test    edi, edi
0x14000ff45  jns     short loc_14000FFA3
0x14000ff47  mov     r9, rbx
0x14000ff4a  lea     r8, aCommandLineIsL; "Command line is %ls"
0x14000ff51  mov     edx, 2BFh
0x14000ff56  lea     rcx, aAppmoduleParse; "AppModule::ParseCommandLine"
0x14000ff5d  call    WusaLogDebugEventA
0x14000ff62  lea     rdx, [rbp+hMem]; unsigned __int16 **
0x14000ff66  mov     [rbp+hMem], rsi
0x14000ff6a  mov     ecx, edi; dwMessageId
0x14000ff6c  call    ?WusaGetErrorMessage@@YAJKPEAPEAG@Z; WusaGetErrorMessage(ulong,ushort * *)
0x14000ff71  mov     rbx, [rbp+hMem]
0x14000ff75  lea     r8, aExitWithErrorC; "Exit with error code 0X%x (%ls)"
0x14000ff7c  mov     r9d, edi
0x14000ff7f  mov     [rsp+48h+var_28], rbx
0x14000ff84  mov     edx, 2C1h
0x14000ff89  lea     rcx, aAppmoduleParse; "AppModule::ParseCommandLine"
0x14000ff90  call    WusaLogDebugEventA
0x14000ff95  test    rbx, rbx
0x14000ff98  jz      short loc_14000FFA3
0x14000ff9a  mov     rcx, rbx; hMem
0x14000ff9d  call    cs:__imp_LocalFree
0x14000ffa3  mov     eax, edi
0x14000ffa5  add     rsp, 48h
0x14000ffa9  pop     r15
0x14000ffab  pop     r14
0x14000ffad  pop     r13
0x14000ffaf  pop     r12
0x14000ffb1  pop     rdi
0x14000ffb2  pop     rsi
0x14000ffb3  pop     rbx
0x14000ffb4  pop     rbp
0x14000ffb5  retn
0x14000ffb6  mov     eax, ecx
0x14000ffb8  mov     dword ptr [rbp+hMem], ecx
0x14000ffbb  mov     r15d, ecx
0x14000ffbe  mov     [rbp+arg_10], ecx
0x14000ffc1  mov     edx, ecx
0x14000ffc3  mov     ecx, 1
0x14000ffc8  mov     [rbp+var_18], ecx
0x14000ffcb  cmp     [rbp+pNumArgs], ecx
0x14000ffce  jle     loc_14001050C
0x14000ffd4  movsxd  rbx, ecx
0x14000ffd7  lea     rdx, asc_14001B2B4; "/?"
0x14000ffde  mov     rcx, [r12+rbx*8]; String1
0x14000ffe2  call    cs:__imp__wcsicmp
0x14000ffe8  test    eax, eax
0x14000ffea  jz      loc_1400104E3
0x14000fff0  mov     rcx, [r12+rbx*8]; String1
0x14000fff4  lea     rdx, asc_14001B2AC; "/h"
0x14000fffb  call    cs:__imp__wcsicmp
0x140010001  test    eax, eax
0x140010003  jz      loc_1400104E3
0x140010009  mov     rcx, [r12+rbx*8]; String1
0x14001000d  lea     rdx, aHelp; "/help"
0x140010014  call    cs:__imp__wcsicmp
0x14001001a  test    eax, eax
0x14001001c  jz      loc_1400104E3
0x140010022  mov     rcx, [r12+rbx*8]; String1
0x140010026  lea     rdx, aUninstall; "/uninstall"
0x14001002d  call    cs:__imp__wcsicmp
0x140010033  test    eax, eax
0x140010035  jnz     short loc_140010047
0x140010037  or      dword ptr [rsi+78h], 40h
0x14001003b  mov     dword ptr [rsi+5Ch], 1
0x140010042  jmp     loc_1400104EE
0x140010047  mov     rcx, [r12+rbx*8]; String1
0x14001004b  lea     rdx, aQuiet; "/quiet"
0x140010052  call    cs:__imp__wcsicmp
0x140010058  test    eax, eax
0x14001005a  jnz     short loc_14001006C
0x14001005c  or      dword ptr [rsi+78h], 2
0x140010060  mov     dword ptr [rsi+68h], 1
0x140010067  jmp     loc_1400104EE
0x14001006c  mov     rcx, [r12+rbx*8]; String1
0x140010070  lea     rdx, aNorestart; "/norestart"
0x140010077  call    cs:__imp__wcsicmp
0x14001007d  xor     r8d, r8d
0x140010080  test    eax, eax
0x140010082  jnz     short loc_14001009E
0x140010084  cmp     [rsi+74h], r8d
0x140010088  jnz     loc_140010542
0x14001008e  or      dword ptr [rsi+78h], 4
0x140010092  mov     dword ptr [rsi+74h], 1
0x140010099  jmp     loc_1400104EE
0x14001009e  mov     rcx, [r12+rbx*8]; String1
0x1400100a2  lea     rdx, aPromptrestart; "/promptrestart"
0x1400100a9  call    cs:__imp__wcsicmp
0x1400100af  xor     r8d, r8d
0x1400100b2  test    eax, eax
0x1400100b4  jnz     short loc_1400100D0
0x1400100b6  cmp     [rsi+74h], r8d
0x1400100ba  jnz     loc_140010556
0x1400100c0  or      dword ptr [rsi+78h], 20h
0x1400100c4  mov     dword ptr [rsi+74h], 4
0x1400100cb  jmp     loc_1400104EE
0x1400100d0  mov     rcx, [r12+rbx*8]; String1
0x1400100d4  lea     rdx, aForcerestart; "/forcerestart"
0x1400100db  call    cs:__imp__wcsicmp
0x1400100e1  xor     r8d, r8d
0x1400100e4  test    eax, eax
0x1400100e6  jnz     short loc_140010102
0x1400100e8  cmp     [rsi+74h], r8d
0x1400100ec  jnz     loc_14001056A
0x1400100f2  or      dword ptr [rsi+78h], 8
0x1400100f6  mov     dword ptr [rsi+74h], 2
0x1400100fd  jmp     loc_1400104EE
0x140010102  mov     rcx, [r12+rbx*8]; String1
0x140010106  lea     rdx, aWarnrestart; "/warnrestart"
0x14001010d  mov     r8d, 0Ch; MaxCount
0x140010113  call    cs:__imp__wcsnicmp
0x140010119  xor     ecx, ecx; this
0x14001011b  test    eax, eax
0x14001011d  jnz     short loc_140010194
0x14001011f  cmp     [rsi+74h], ecx
0x140010122  jnz     loc_1400105A3
0x140010128  mov     r8, [r12+rbx*8]; unsigned __int16 *
0x14001012c  lea     rax, [rbp+pszString]
0x140010130  lea     r9, a30; "30"
0x140010137  mov     [rsp+48h+var_28], rax; unsigned __int16 **
0x14001013c  lea     rdx, aWarnrestart; "/warnrestart"
0x140010143  call    ?GetArgumentValue@AppModule@@AEAAJPEBG00PEAPEAG@Z; AppModule::GetArgumentValue(ushort const *,ushort const *,ushort const *,ushort * *)
0x140010148  mov     edi, eax
0x14001014a  test    eax, eax
0x14001014c  js      loc_140010592
0x140010152  mov     rcx, [rbp+pszString]; pszString
0x140010156  lea     r8, [rsi+0E8h]; piRet
0x14001015d  xor     edx, edx; dwFlags
0x14001015f  call    cs:__imp_StrToIntExW
0x140010165  test    eax, eax
0x140010167  jz      loc_14001057E
0x14001016d  mov     rcx, [rbp+pszString]
0x140010171  test    rcx, rcx
0x140010174  jz      short loc_140010184
0x140010176  call    cs:__imp_SczFree
0x14001017c  mov     [rbp+pszString], 0
0x140010184  or      dword ptr [rsi+78h], 10h
0x140010188  mov     dword ptr [rsi+74h], 3
0x14001018f  jmp     loc_1400104EE
0x140010194  mov     rcx, [r12+rbx*8]; String1
0x140010198  lea     rdx, aKb_0; "/kb"
0x14001019f  mov     r8d, 3; MaxCount
0x1400101a5  call    cs:__imp__wcsnicmp
0x1400101ab  xor     ecx, ecx; this
0x1400101ad  test    eax, eax
0x1400101af  jnz     loc_140010259
0x1400101b5  lea     r15, [rsi+0D0h]
0x1400101bc  cmp     [r15], rcx
0x1400101bf  jnz     loc_1400105ED
0x1400101c5  mov     r8, [r12+rbx*8]; unsigned __int16 *
0x1400101c9  lea     rdx, aKb_0; "/kb"
0x1400101d0  xor     r9d, r9d; unsigned __int16 *
0x1400101d3  mov     [rsp+48h+var_28], r15; unsigned __int16 **
0x1400101d8  call    ?GetArgumentValue@AppModule@@AEAAJPEBG00PEAPEAG@Z; AppModule::GetArgumentValue(ushort const *,ushort const *,ushort const *,ushort * *)
0x1400101dd  mov     edi, eax
0x1400101df  test    eax, eax
0x1400101e1  js      loc_1400105DC
0x1400101e7  mov     rcx, [r15]
0x1400101ea  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400101ee  xor     edi, edi
0x1400101f0  inc     rax
0x1400101f3  cmp     [rcx+rax*2], di
0x1400101f7  jnz     short loc_1400101F0
0x1400101f9  mov     ebx, 1
0x1400101fe  cmp     rax, rbx
0x140010201  jbe     short loc_140010232
0x140010203  movzx   ecx, word ptr [rcx+rbx*2]; C
0x140010207  call    cs:__imp_iswdigit
0x14001020d  test    eax, eax
0x14001020f  jz      loc_1400105B7
0x140010215  mov     rcx, [r15]
0x140010218  inc     rbx
0x14001021b  or      rax, 0FFFFFFFFFFFFFFFFh
0x14001021f  inc     rax
0x140010222  cmp     [rcx+rax*2], di
0x140010226  jnz     short loc_14001021F
0x140010228  cmp     rbx, rax
0x14001022b  jb      short loc_140010203
0x14001022d  mov     ebx, 1
0x140010232  lea     rdx, aKb; "KB"
0x140010239  mov     rcx, r15
0x14001023c  call    cs:__imp_SczAllocPrefixSz
0x140010242  mov     edi, eax
0x140010244  test    eax, eax
0x140010246  js      loc_1400105CB
0x14001024c  bts     dword ptr [rsi+78h], 9
0x140010251  mov     r15d, ebx
0x140010254  jmp     loc_1400104EE
0x140010259  mov     rcx, [r12+rbx*8]; String1
0x14001025d  lea     rdx, aExtract; "/extract"
0x140010264  mov     r8d, 8; MaxCount
0x14001026a  call    cs:__imp__wcsnicmp
0x140010270  test    eax, eax
0x140010272  jnz     short loc_140010280
0x140010274  mov     dword ptr [rsi+64h], 1
0x14001027b  jmp     loc_1400104EE
0x140010280  mov     rcx, [r12+rbx*8]; String1
0x140010284  lea     rdx, aLog; "/log"
0x14001028b  mov     r8d, 4; MaxCount
0x140010291  call    cs:__imp__wcsnicmp
0x140010297  xor     edi, edi
0x140010299  test    eax, eax
0x14001029b  jnz     short loc_1400102DD
0x14001029d  lea     rax, [rsi+0D8h]
0x1400102a4  cmp     [rax], rdi
0x1400102a7  jnz     loc_140010612
0x1400102ad  mov     r8, [r12+rbx*8]; unsigned __int16 *
0x1400102b1  lea     r9, aWusaEtl; "wusa.etl"
0x1400102b8  lea     rdx, aLog; "/log"
  ... truncated ...
```
