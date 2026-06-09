# StartHWCMode(APPHOST_CONFIG *)

- ea: `0x14000215c`
- end: `0x140002620`
- name: `?StartHWCMode@@YAJPEAUAPPHOST_CONFIG@@@Z`
- size: `1220`
- prototype: `__int64 __fastcall(struct APPHOST_CONFIG *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1400027b0`

## callees

- `0x140001ee8`
- `0x140001fa0`
- `0x140001ff8`
- `0x14000215c`
- `0x1400038b6`
- `0x1400038e0`
- `0x140004010`

## import_xrefs

- `msvcrt!towupper` at `0x1400025a0`
- `msvcrt!towupper` at `0x1400025a0`
- `msvcrt!_getwch` at `0x140002597`
- `msvcrt!_getwch` at `0x140002597`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140002271`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140002324`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400023c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000242b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140002471`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140002536`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140002554`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140002271`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140002324`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400023c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000242b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140002471`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140002536`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140002554`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1400023a7`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1400023a7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140002410`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140002456`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140002410`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140002456`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x140002265`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1400022c8`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x140002265`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1400022c8`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x14000231a`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x140002377`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x14000231a`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x140002377`
- `api-ms-win-core-console-l1-1-0!SetConsoleCtrlHandler` at `0x14000252c`
- `api-ms-win-core-console-l1-1-0!SetConsoleCtrlHandler` at `0x1400025bf`
- `api-ms-win-core-console-l1-1-0!SetConsoleCtrlHandler` at `0x14000252c`
- `api-ms-win-core-console-l1-1-0!SetConsoleCtrlHandler` at `0x1400025bf`
- `iisutil!MakePathCanonicalizationProof` at `0x14000234d`
- `iisutil!MakePathCanonicalizationProof` at `0x14000238c`
- `iisutil!MakePathCanonicalizationProof` at `0x14000234d`
- `iisutil!MakePathCanonicalizationProof` at `0x14000238c`
- `iisutil!??1STRU@@QEAA@XZ` at `0x14000228b`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1400022e8`
- `iisutil!??1STRU@@QEAA@XZ` at `0x140002301`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1400025e1`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1400025eb`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1400025f5`
- `iisutil!??1STRU@@QEAA@XZ` at `0x14000228b`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1400022e8`
- `iisutil!??1STRU@@QEAA@XZ` at `0x140002301`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1400025e1`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1400025eb`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1400025f5`
- `iisutil!?Resize@STRU@@QEAAJK@Z` at `0x1400022a8`
- `iisutil!?Resize@STRU@@QEAAJK@Z` at `0x1400022a8`
- `iisutil!PuDbgPrint` at `0x1400023f8`
- `iisutil!PuDbgPrint` at `0x140002585`
- `iisutil!PuDbgPrint` at `0x1400023f8`
- `iisutil!PuDbgPrint` at `0x140002585`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1400021c9`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1400021f3`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x140002218`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x14000224b`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1400021c9`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1400021f3`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x140002218`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x14000224b`

## string_xrefs

- `0x1400023ec`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wp\w3wp.cxx`
- `0x14000256c`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wp\w3wp.cxx`
- `0x140002398`: `hwebcore.dll`
- `0x140002256`: `%windir%\system32\inetsrv\config\applicationhost.config`
- `0x1400022b9`: `%windir%\system32\inetsrv\config\applicationhost.config`
- `0x1400023d7`: `Error loading hwebcore dll '%ws'.  Error = %d\n`

## pseudocode

```c
__int64 __fastcall StartHWCMode(struct APPHOST_CONFIG *a1)
{
  const WCHAR *v2; // rcx
  DWORD v3; // edx
  signed int v4; // eax
  signed int PathCanonicalizationProof; // ebx
  DWORD v6; // ecx
  WCHAR *v7; // r14
  signed int LastError; // eax
  const WCHAR *v9; // rcx
  HMODULE Library; // rax
  HMODULE v11; // rdi
  FARPROC ProcAddress; // r15
  FARPROC v13; // rdi
  __int64 v14; // r8
  unsigned __int64 v15; // rcx
  unsigned int v16; // edx
  WCHAR *v17; // rdx
  signed int v18; // eax
  DWORD v19; // eax
  wint_t v20; // ax
  DWORD v22; // [rsp+30h] [rbp-D0h]
  DWORD v23; // [rsp+30h] [rbp-D0h]
  DWORD v24; // [rsp+30h] [rbp-D0h]
  LPWSTR FilePart; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v26[32]; // [rsp+48h] [rbp-B8h] BYREF
  LPWSTR lpDst; // [rsp+68h] [rbp-98h]
  unsigned int v28; // [rsp+70h] [rbp-90h]
  _BYTE v29[32]; // [rsp+80h] [rbp-80h] BYREF
  __int64 v30; // [rsp+A0h] [rbp-60h]
  _BYTE v31[56]; // [rsp+B8h] [rbp-48h] BYREF
  _BYTE v32[64]; // [rsp+F0h] [rbp-10h] BYREF
  unsigned __int16 v33[128]; // [rsp+130h] [rbp+30h] BYREF
  WCHAR Buffer[264]; // [rsp+230h] [rbp+130h] BYREF
  WCHAR v35[264]; // [rsp+440h] [rbp+340h] BYREF
  unsigned __int16 v36[264]; // [rsp+650h] [rbp+550h] BYREF
  unsigned __int16 v37[264]; // [rsp+860h] [rbp+760h] BYREF
  unsigned __int16 v38[264]; // [rsp+A70h] [rbp+970h] BYREF

  memset_0(Buffer, 0, 0x208u);
  FilePart = 0;
  memset_0(v33, 0, sizeof(v33));
  STRU::STRU((STRU *)v29, v33, 0x80u);
  memset_0(v36, 0, 0x208u);
  STRU::STRU((STRU *)v32, v36, 0x104u);
  memset_0(v37, 0, 0x208u);
  STRU::STRU((STRU *)v31, v37, 0x104u);
  v2 = (const WCHAR *)*((_QWORD *)a1 + 8);
  if ( v2 )
  {
    if ( !GetFullPathNameW(v2, 0x104u, Buffer, &FilePart)
      || (PathCanonicalizationProof = MakePathCanonicalizationProof(Buffer, (struct STRU *)v32),
          PathCanonicalizationProof < 0)
      || (v9 = (const WCHAR *)*((_QWORD *)a1 + 9), v7 = Buffer, v9)
      && (!GetFullPathNameW(v9, 0x104u, v35, &FilePart)
       || (PathCanonicalizationProof = MakePathCanonicalizationProof(v35, (struct STRU *)v31),
           PathCanonicalizationProof < 0)) )
    {
      LastError = GetLastError();
      PathCanonicalizationProof = LastError;
      if ( LastError > 0 )
        PathCanonicalizationProof = (unsigned __int16)LastError | 0x80070000;
      goto LABEL_50;
    }
  }
  else
  {
    memset_0(v38, 0, 0x208u);
    STRU::STRU((STRU *)v26, v38, 0x104u);
    v3 = ExpandEnvironmentStringsW(L"%windir%\\system32\\inetsrv\\config\\applicationhost.config", lpDst, v28 >> 1);
    if ( !v3 )
    {
LABEL_3:
      v4 = GetLastError();
      PathCanonicalizationProof = v4;
      if ( v4 > 0 )
        PathCanonicalizationProof = (unsigned __int16)v4 | 0x80070000;
      STRU::~STRU((STRU *)v26);
      goto LABEL_50;
    }
    PathCanonicalizationProof = 0;
    if ( v3 > v28 >> 1 )
    {
      PathCanonicalizationProof = STRU::Resize((STRU *)v26, v3);
      if ( PathCanonicalizationProof < 0 )
        goto LABEL_3;
      v6 = ExpandEnvironmentStringsW(L"%windir%\\system32\\inetsrv\\config\\applicationhost.config", lpDst, v28 >> 1);
      if ( !v6 )
        goto LABEL_3;
      if ( v6 > v28 >> 1 )
      {
        PathCanonicalizationProof = -2147467259;
        STRU::~STRU((STRU *)v26);
LABEL_51:
        PrintErrorMessage(PathCanonicalizationProof);
        goto LABEL_52;
      }
    }
    v7 = lpDst;
    *((_QWORD *)a1 + 8) = lpDst;
    STRU::~STRU((STRU *)v26);
  }
  Library = LoadLibraryExW(L"hwebcore.dll", 0, 0);
  v11 = Library;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "WebCoreActivate");
    if ( ProcAddress )
    {
      v13 = GetProcAddress(v11, "WebCoreShutdown");
      if ( v13 )
      {
        v14 = *((_QWORD *)a1 + 10);
        if ( v14 )
        {
          v15 = -1;
          do
            ++v15;
          while ( *(_WORD *)(v14 + 2 * v15) );
          if ( !v15 )
          {
LABEL_37:
            PathCanonicalizationProof = -2147024809;
            goto LABEL_51;
          }
          v16 = 0;
          while ( *(_WORD *)(v14 + 2LL * v16) == 32 || *(_WORD *)(v14 + 2LL * v16) == 9 )
          {
            if ( ++v16 >= v15 )
              goto LABEL_37;
          }
        }
        PathCanonicalizationProof = MakeInstanceName((struct STRU *)v29, *((const unsigned __int16 **)a1 + 10));
        if ( PathCanonicalizationProof < 0 )
          goto LABEL_51;
        v17 = v35;
        if ( !*((_QWORD *)a1 + 9) )
          v17 = (WCHAR *)&qword_140005BC8;
        PathCanonicalizationProof = ((__int64 (__fastcall *)(WCHAR *, WCHAR *, __int64))ProcAddress)(v7, v17, v30);
        if ( PathCanonicalizationProof < 0 )
          goto LABEL_51;
        if ( SetConsoleCtrlHandler(CtrlHandle, 1) )
        {
          PrintResourceString(0x61AAu);
          do
            v20 = _getwch();
          while ( towupper(v20) != 81 );
          PrintResourceString(0x61ABu);
          SetConsoleCtrlHandler(CtrlHandle, 0);
          PathCanonicalizationProof = ((__int64 (__fastcall *)(__int64))v13)(1);
        }
        else
        {
          v18 = GetLastError();
          PathCanonicalizationProof = v18;
          if ( v18 > 0 )
            PathCanonicalizationProof = (unsigned __int16)v18 | 0x80070000;
          if ( (g_dwDebugFlags & 3) != 0 )
          {
            v19 = GetLastError();
            PuDbgPrint(
              g_pDebug,
              "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wp\\w3wp.cxx",
              1329,
              "StartHWCMode",
              "Could set console Ctrl handle.  Error = %d\n",
              v19);
          }
        }
      }
      else if ( (g_dwDebugFlags & 3) != 0 )
      {
        v24 = GetLastError();
        PuDbgPrint(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wp\\w3wp.cxx",
          1276,
          "StartHWCMode",
          "Could not find entry point '%s'.  Error = %d\n",
          "WebCoreShutdown",
          v24);
      }
    }
    else if ( (g_dwDebugFlags & 3) != 0 )
    {
      v23 = GetLastError();
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wp\\w3wp.cxx",
        1264,
        "StartHWCMode",
        "Could not find entry point '%s'.  Error = %d\n",
        "WebCoreActivate",
        v23);
    }
  }
  else if ( (g_dwDebugFlags & 3) != 0 )
  {
    v22 = GetLastError();
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wp\\w3wp.cxx",
      1252,
      "StartHWCMode",
      "Error loading hwebcore dll '%ws'.  Error = %d\n",
      L"hwebcore.dll",
      v22);
  }
LABEL_50:
  if ( PathCanonicalizationProof < 0 )
    goto LABEL_51;
LABEL_52:
  STRU::~STRU((STRU *)v31);
  STRU::~STRU((STRU *)v32);
  STRU::~STRU((STRU *)v29);
  return (unsigned int)PathCanonicalizationProof;
}

```

## disassembly

```asm
0x14000215c  push    rbp
0x14000215e  push    rbx
0x14000215f  push    rsi
0x140002160  push    rdi
0x140002161  push    r12
0x140002163  push    r13
0x140002165  push    r14
0x140002167  push    r15
0x140002169  lea     rbp, [rsp-0B98h]
0x140002171  sub     rsp, 0C98h
0x140002178  mov     rax, cs:__security_cookie
0x14000217f  xor     rax, rsp
0x140002182  mov     [rbp+0BD0h+var_50], rax
0x140002189  mov     rsi, rcx
0x14000218c  mov     ebx, 208h
0x140002191  mov     r8d, ebx; Size
0x140002194  lea     rcx, [rbp+0BD0h+Buffer]; void *
0x14000219b  xor     edx, edx; Val
0x14000219d  call    memset_0
0x1400021a2  xor     r12d, r12d
0x1400021a5  lea     rcx, [rbp+0BD0h+var_BA0]; void *
0x1400021a9  xor     edx, edx; Val
0x1400021ab  mov     [rsp+0CD0h+FilePart], r12
0x1400021b0  mov     r8d, 100h; Size
0x1400021b6  call    memset_0
0x1400021bb  mov     r8d, 80h
0x1400021c1  lea     rdx, [rbp+0BD0h+var_BA0]
0x1400021c5  lea     rcx, [rbp+0BD0h+var_C50]
0x1400021c9  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x1400021cf  mov     r8d, ebx; Size
0x1400021d2  lea     rcx, [rbp+0BD0h+var_680]; void *
0x1400021d9  xor     edx, edx; Val
0x1400021db  call    memset_0
0x1400021e0  mov     edi, 104h
0x1400021e5  lea     rdx, [rbp+0BD0h+var_680]
0x1400021ec  mov     r8d, edi
0x1400021ef  lea     rcx, [rbp+0BD0h+var_BE0]
0x1400021f3  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x1400021f9  mov     r8d, ebx; Size
0x1400021fc  lea     rcx, [rbp+0BD0h+var_470]; void *
0x140002203  xor     edx, edx; Val
0x140002205  call    memset_0
0x14000220a  mov     r8d, edi
0x14000220d  lea     rdx, [rbp+0BD0h+var_470]
0x140002214  lea     rcx, [rbp+0BD0h+var_C18]
0x140002218  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x14000221e  mov     rcx, [rsi+40h]; lpFileName
0x140002222  test    rcx, rcx
0x140002225  jnz     loc_14000230C
0x14000222b  mov     r8d, ebx; Size
0x14000222e  lea     rcx, [rbp+0BD0h+var_260]; void *
0x140002235  xor     edx, edx; Val
0x140002237  call    memset_0
0x14000223c  mov     r8d, edi
0x14000223f  lea     rdx, [rbp+0BD0h+var_260]
0x140002246  lea     rcx, [rsp+0CD0h+var_C88]
0x14000224b  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x140002251  mov     r8d, [rsp+0CD0h+var_C60]
0x140002256  lea     rcx, Src; "%windir%\\system32\\inetsrv\\config\\ap"...
0x14000225d  mov     rdx, [rsp+0CD0h+lpDst]; lpDst
0x140002262  shr     r8d, 1; nSize
0x140002265  call    cs:__imp_ExpandEnvironmentStringsW
0x14000226b  mov     edx, eax
0x14000226d  test    eax, eax
0x14000226f  jnz     short loc_140002296
0x140002271  call    cs:__imp_GetLastError
0x140002277  mov     ebx, eax
0x140002279  test    eax, eax
0x14000227b  jle     short loc_140002286
0x14000227d  movzx   ebx, ax
0x140002280  or      ebx, 80070000h
0x140002286  lea     rcx, [rsp+0CD0h+var_C88]
0x14000228b  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x140002291  jmp     loc_1400025D2
0x140002296  mov     eax, [rsp+0CD0h+var_C60]
0x14000229a  mov     ebx, r12d
0x14000229d  shr     eax, 1
0x14000229f  cmp     edx, eax
0x1400022a1  jbe     short loc_1400022F3
0x1400022a3  lea     rcx, [rsp+0CD0h+var_C88]
0x1400022a8  call    cs:__imp_?Resize@STRU@@QEAAJK@Z; STRU::Resize(ulong)
0x1400022ae  mov     ebx, eax
0x1400022b0  test    eax, eax
0x1400022b2  js      short loc_140002271
0x1400022b4  mov     r8d, [rsp+0CD0h+var_C60]
0x1400022b9  lea     rcx, Src; "%windir%\\system32\\inetsrv\\config\\ap"...
0x1400022c0  mov     rdx, [rsp+0CD0h+lpDst]; lpDst
0x1400022c5  shr     r8d, 1; nSize
0x1400022c8  call    cs:__imp_ExpandEnvironmentStringsW
0x1400022ce  mov     ecx, eax
0x1400022d0  test    eax, eax
0x1400022d2  jz      short loc_140002271
0x1400022d4  mov     eax, [rsp+0CD0h+var_C60]
0x1400022d8  shr     eax, 1
0x1400022da  cmp     ecx, eax
0x1400022dc  jbe     short loc_1400022F3
0x1400022de  lea     rcx, [rsp+0CD0h+var_C88]
0x1400022e3  mov     ebx, 80004005h
0x1400022e8  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x1400022ee  jmp     loc_1400025D6
0x1400022f3  mov     r14, [rsp+0CD0h+lpDst]
0x1400022f8  lea     rcx, [rsp+0CD0h+var_C88]
0x1400022fd  mov     [rsi+40h], r14
0x140002301  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x140002307  jmp     loc_140002398
0x14000230c  lea     r9, [rsp+0CD0h+FilePart]; lpFilePart
0x140002311  mov     edx, edi; nBufferLength
0x140002313  lea     r8, [rbp+0BD0h+Buffer]; lpBuffer
0x14000231a  call    cs:__imp_GetFullPathNameW
0x140002320  test    eax, eax
0x140002322  jnz     short loc_140002342
0x140002324  call    cs:__imp_GetLastError
0x14000232a  mov     ebx, eax
0x14000232c  test    eax, eax
0x14000232e  jle     loc_1400025D2
0x140002334  movzx   ebx, ax
0x140002337  or      ebx, 80070000h
0x14000233d  jmp     loc_1400025D2
0x140002342  lea     rdx, [rbp+0BD0h+var_BE0]
0x140002346  lea     rcx, [rbp+0BD0h+Buffer]
0x14000234d  call    cs:__imp_?MakePathCanonicalizationProof@@YAJPEBGPEAVSTRU@@@Z; MakePathCanonicalizationProof(ushort const *,STRU *)
0x140002353  mov     ebx, eax
0x140002355  test    eax, eax
0x140002357  js      short loc_140002324
0x140002359  mov     rcx, [rsi+48h]; lpFileName
0x14000235d  lea     r14, [rbp+0BD0h+Buffer]
0x140002364  test    rcx, rcx
0x140002367  jz      short loc_140002398
0x140002369  lea     r9, [rsp+0CD0h+FilePart]; lpFilePart
0x14000236e  mov     edx, edi; nBufferLength
0x140002370  lea     r8, [rbp+0BD0h+var_890]; lpBuffer
0x140002377  call    cs:__imp_GetFullPathNameW
0x14000237d  test    eax, eax
0x14000237f  jz      short loc_140002324
0x140002381  lea     rdx, [rbp+0BD0h+var_C18]
0x140002385  lea     rcx, [rbp+0BD0h+var_890]
0x14000238c  call    cs:__imp_?MakePathCanonicalizationProof@@YAJPEBGPEAVSTRU@@@Z; MakePathCanonicalizationProof(ushort const *,STRU *)
0x140002392  mov     ebx, eax
0x140002394  test    eax, eax
0x140002396  js      short loc_140002324
0x140002398  lea     r15, LibFileName; "hwebcore.dll"
0x14000239f  xor     r8d, r8d; dwFlags
0x1400023a2  mov     rcx, r15; lpLibFileName
0x1400023a5  xor     edx, edx; hFile
0x1400023a7  call    cs:__imp_LoadLibraryExW
0x1400023ad  mov     rdi, rax
0x1400023b0  test    rax, rax
0x1400023b3  jnz     short loc_140002403
0x1400023b5  test    byte ptr cs:g_dwDebugFlags, 3
0x1400023bc  jz      loc_1400025D2
0x1400023c2  call    cs:__imp_GetLastError
0x1400023c8  mov     [rsp+0CD0h+var_CA0], eax
0x1400023cc  mov     r8d, 4E4h
0x1400023d2  mov     [rsp+0CD0h+var_CA8], r15
0x1400023d7  lea     rax, aErrorLoadingHw; "Error loading hwebcore dll '%ws'.  Erro"...
0x1400023de  mov     rcx, cs:g_pDebug
0x1400023e5  lea     r9, aStarthwcmode; "StartHWCMode"
0x1400023ec  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x1400023f3  mov     [rsp+0CD0h+var_CB0], rax
0x1400023f8  call    cs:__imp_PuDbgPrint
0x1400023fe  jmp     loc_1400025D2
0x140002403  lea     r13, aWebcoreactivat; "WebCoreActivate"
0x14000240a  mov     rcx, rdi; hModule
0x14000240d  mov     rdx, r13; lpProcName
0x140002410  call    cs:__imp_GetProcAddress
0x140002416  mov     r15, rax
0x140002419  test    rax, rax
0x14000241c  jnz     short loc_140002449
0x14000241e  test    byte ptr cs:g_dwDebugFlags, 3
0x140002425  jz      loc_1400025D2
0x14000242b  call    cs:__imp_GetLastError
0x140002431  mov     [rsp+0CD0h+var_CA0], eax
0x140002435  mov     r8d, 4F0h
0x14000243b  mov     [rsp+0CD0h+var_CA8], r13
0x140002440  lea     rax, aCouldNotFindEn_0; "Could not find entry point '%s'.  Error"...
0x140002447  jmp     short loc_1400023DE
0x140002449  lea     r13, ProcName; "WebCoreShutdown"
0x140002450  mov     rcx, rdi; hModule
0x140002453  mov     rdx, r13; lpProcName
0x140002456  call    cs:__imp_GetProcAddress
0x14000245c  mov     rdi, rax
0x14000245f  test    rax, rax
0x140002462  jnz     short loc_140002492
0x140002464  test    byte ptr cs:g_dwDebugFlags, 3
0x14000246b  jz      loc_1400025D2
0x140002471  call    cs:__imp_GetLastError
0x140002477  mov     [rsp+0CD0h+var_CA0], eax
0x14000247b  mov     r8d, 4FCh
0x140002481  mov     [rsp+0CD0h+var_CA8], r13
0x140002486  lea     rax, aCouldNotFindEn_0; "Could not find entry point '%s'.  Error"...
0x14000248d  jmp     loc_1400023DE
0x140002492  mov     r8, [rsi+50h]
0x140002496  mov     r13d, 1
0x14000249c  test    r8, r8
0x14000249f  jz      short loc_1400024DD
0x1400024a1  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1400024a5  inc     rcx
0x1400024a8  cmp     [r8+rcx*2], r12w
0x1400024ad  jnz     short loc_1400024A5
0x1400024af  test    rcx, rcx
0x1400024b2  jz      short loc_1400024D3
0x1400024b4  mov     edx, r12d
0x1400024b7  mov     eax, edx
0x1400024b9  cmp     word ptr [r8+rax*2], 20h ; ' '
0x1400024bf  jz      short loc_1400024C9
0x1400024c1  cmp     word ptr [r8+rax*2], 9
0x1400024c7  jnz     short loc_1400024DD
0x1400024c9  add     edx, r13d
0x1400024cc  mov     eax, edx
0x1400024ce  cmp     rax, rcx
0x1400024d1  jb      short loc_1400024B7
0x1400024d3  mov     ebx, 80070057h
0x1400024d8  jmp     loc_1400025D6
0x1400024dd  mov     rdx, r8; unsigned __int16 *
0x1400024e0  lea     rcx, [rbp+0BD0h+var_C50]; struct STRU *
0x1400024e4  call    ?MakeInstanceName@@YAJPEAVSTRU@@PEBG@Z; MakeInstanceName(STRU *,ushort const *)
0x1400024e9  mov     ebx, eax
0x1400024eb  test    eax, eax
0x1400024ed  js      loc_1400025D6
0x1400024f3  cmp     [rsi+48h], r12
0x1400024f7  lea     rax, qword_140005BC8
0x1400024fe  mov     r8, [rbp+0BD0h+var_C30]
0x140002502  lea     rdx, [rbp+0BD0h+var_890]
0x140002509  cmovz   rdx, rax
0x14000250d  mov     rcx, r14
0x140002510  mov     rax, r15
0x140002513  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002518  mov     ebx, eax
0x14000251a  test    eax, eax
0x14000251c  js      loc_1400025D6
0x140002522  mov     edx, r13d; Add
0x140002525  lea     rcx, ?CtrlHandle@@YAXK@Z; HandlerRoutine
0x14000252c  call    cs:__imp_SetConsoleCtrlHandler
0x140002532  test    eax, eax
0x140002534  jnz     short loc_14000258D
0x140002536  call    cs:__imp_GetLastError
0x14000253c  mov     ebx, eax
0x14000253e  test    eax, eax
0x140002540  jle     short loc_14000254B
0x140002542  movzx   ebx, ax
0x140002545  or      ebx, 80070000h
0x14000254b  test    byte ptr cs:g_dwDebugFlags, 3
0x140002552  jz      short loc_1400025D2
0x140002554  call    cs:__imp_GetLastError
0x14000255a  mov     rcx, cs:g_pDebug
0x140002561  lea     r9, aStarthwcmode; "StartHWCMode"
0x140002568  mov     dword ptr [rsp+0CD0h+var_CA8], eax
0x14000256c  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x140002573  lea     rax, aCouldSetConsol; "Could set console Ctrl handle.  Error ="...
0x14000257a  mov     r8d, 531h
0x140002580  mov     [rsp+0CD0h+var_CB0], rax
0x140002585  call    cs:__imp_PuDbgPrint
0x14000258b  jmp     short loc_1400025D2
0x14000258d  mov     ecx, 61AAh; uID
0x140002592  call    ?PrintResourceString@@YAXK@Z; PrintResourceString(ulong)
0x140002597  call    cs:__imp__getwch
0x14000259d  movzx   ecx, ax; C
0x1400025a0  call    cs:__imp_towupper
0x1400025a6  cmp     ax, 51h ; 'Q'
0x1400025aa  jnz     short loc_140002597
0x1400025ac  mov     ecx, 61ABh; uID
0x1400025b1  call    ?PrintResourceString@@YAXK@Z; PrintResourceString(ulong)
0x1400025b6  xor     edx, edx; Add
0x1400025b8  lea     rcx, ?CtrlHandle@@YAXK@Z; HandlerRoutine
0x1400025bf  call    cs:__imp_SetConsoleCtrlHandler
0x1400025c5  mov     ecx, r13d
0x1400025c8  mov     rax, rdi
0x1400025cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400025d0  mov     ebx, eax
0x1400025d2  test    ebx, ebx
0x1400025d4  jns     short loc_1400025DD
0x1400025d6  mov     ecx, ebx; int
0x1400025d8  call    ?PrintErrorMessage@@YAXJ@Z; PrintErrorMessage(long)
0x1400025dd  lea     rcx, [rbp+0BD0h+var_C18]
0x1400025e1  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x1400025e7  lea     rcx, [rbp+0BD0h+var_BE0]
0x1400025eb  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x1400025f1  lea     rcx, [rbp+0BD0h+var_C50]
0x1400025f5  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x1400025fb  mov     eax, ebx
0x1400025fd  mov     rcx, [rbp+0BD0h+var_50]
0x140002604  xor     rcx, rsp; StackCookie
0x140002607  call    __security_check_cookie
0x14000260c  add     rsp, 0C98h
0x140002613  pop     r15
0x140002615  pop     r14
0x140002617  pop     r13
0x140002619  pop     r12
0x14000261b  pop     rdi
0x14000261c  pop     rsi
0x14000261d  pop     rbx
0x14000261e  pop     rbp
0x14000261f  retn
```
