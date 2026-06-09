# W3WP_HOST::TryPreloadClrViaHelperLoader(ushort const *)

- ea: `0x1800076cc`
- end: `0x180007b40`
- name: `?TryPreloadClrViaHelperLoader@W3WP_HOST@@QEAAJPEBG@Z`
- size: `1140`
- prototype: `__int64 __fastcall(W3WP_HOST *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x1800062bc`

## callees

- `0x1800076cc`
- `0x18000d2f0`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000780d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000780d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800078e8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000794f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800078e8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000794f`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180007a28`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180007a28`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000782c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007879`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007964`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000798d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800079b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800079d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000782c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007879`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007964`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000798d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800079b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800079d9`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180007750`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800077f8`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000786a`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180007ac0`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180007750`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800077f8`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000786a`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180007ac0`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800077de`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800077de`
- `iisutil!?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z` at `0x180007ae7`
- `iisutil!?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z` at `0x180007ae7`
- `iisutil!PuDbgPrintError` at `0x1800078b5`
- `iisutil!PuDbgPrintError` at `0x180007a15`
- `iisutil!PuDbgPrintError` at `0x180007a9a`
- `iisutil!PuDbgPrintError` at `0x1800078b5`
- `iisutil!PuDbgPrintError` at `0x180007a15`
- `iisutil!PuDbgPrintError` at `0x180007a9a`
- `iisutil!??0STRU_PATH@@QEAA@G@Z` at `0x180007705`
- `iisutil!??0STRU_PATH@@QEAA@G@Z` at `0x180007705`
- `iisutil!??1STRU_PATH@@QEAA@XZ` at `0x180007af7`
- `iisutil!??1STRU_PATH@@QEAA@XZ` at `0x180007b0b`
- `iisutil!??1STRU_PATH@@QEAA@XZ` at `0x180007af7`
- `iisutil!??1STRU_PATH@@QEAA@XZ` at `0x180007b0b`
- `iisutil!?ExpandEnvironmentVariables@STRU_PATH@@QEAAJPEAG@Z` at `0x180007736`
- `iisutil!?ExpandEnvironmentVariables@STRU_PATH@@QEAAJPEAG@Z` at `0x180007736`
- `iisutil!?Reset@STRU@@QEAAXXZ` at `0x180007789`
- `iisutil!?Reset@STRU@@QEAAXXZ` at `0x180007789`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000779c`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000779c`
- `iisutil!?Append@STRU@@QEAAJG@Z` at `0x1800077b9`
- `iisutil!?Append@STRU@@QEAAJG@Z` at `0x1800077b9`

## string_xrefs

- `0x1800078a4`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\w3wphost.cxx`
- `0x180007a0a`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\w3wphost.cxx`
- `0x180007a8f`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\w3wphost.cxx`
- `0x180007885`: `Error loading clr helper module dll '%ws'.\n`

## pseudocode

```c
__int64 __fastcall W3WP_HOST::TryPreloadClrViaHelperLoader(W3WP_HOST *this, const unsigned __int16 *a2)
{
  unsigned __int16 *v4; // rdx
  int v5; // edi
  unsigned __int16 *Str; // rax
  const WCHAR *v7; // rax
  HMODULE Library; // rax
  signed int LastError; // eax
  unsigned __int16 *v10; // rbx
  DWORD v11; // eax
  _WORD *v12; // rdx
  FARPROC ProcAddress; // rax
  __int64 v14; // r8
  FARPROC v15; // rax
  signed int v16; // eax
  signed int v17; // eax
  DWORD v18; // eax
  __int64 v19; // r8
  __int64 v20; // rax
  int v22; // [rsp+30h] [rbp-39h]
  __int128 v23; // [rsp+40h] [rbp-29h] BYREF
  _BYTE v24[64]; // [rsp+50h] [rbp-19h] BYREF

  STRU_PATH::STRU_PATH((STRU_PATH *)v24, 0x5Cu);
  v4 = *(unsigned __int16 **)(*((_QWORD *)this + 39) + 104LL);
  if ( v4 && *v4 )
  {
    v5 = STRU_PATH::ExpandEnvironmentVariables((STRU_PATH *)v24, v4);
    if ( v5 < 0 )
      goto LABEL_46;
    if ( (Str = STRU::QueryStr((STRU *)v24)) == 0
      || (unsigned __int16)(*Str - 66) > 0x17u && (unsigned __int16)(*Str - 98) > 0x17u
      || Str[1] != 58
      || Str[2] != 92 )
    {
      STRU::Reset((STRU *)v24);
      v5 = STRU::Copy((STRU *)v24, a2);
      if ( v5 < 0 )
        goto LABEL_46;
      v5 = STRU::Append((STRU *)v24, 0x5Cu);
      if ( v5 < 0 )
        goto LABEL_46;
      v5 = STRU::Append((STRU *)v24, *(const unsigned __int16 **)(*((_QWORD *)this + 39) + 104LL));
      if ( v5 < 0 )
        goto LABEL_46;
    }
    v7 = STRU::QueryStr((STRU *)v24);
    Library = LoadLibraryExW(v7, 0, 8u);
    *((_QWORD *)this + 196) = Library;
    if ( !Library )
    {
      LastError = GetLastError();
      v5 = LastError;
      if ( LastError > 0 )
        v5 = (unsigned __int16)LastError | 0x80070000;
      if ( v5 == -2147024770 )
      {
        v5 = 1;
LABEL_47:
        STRU_PATH::~STRU_PATH((STRU_PATH *)v24);
        return (unsigned int)v5;
      }
      if ( (g_dwDebugFlags & 0xF) != 0 )
      {
        v10 = STRU::QueryStr((STRU *)v24);
        v11 = GetLastError();
        PuDbgPrintError(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wphost\\w3wphost.cxx",
          2650,
          "W3WP_HOST::TryPreloadClrViaHelperLoader",
          v11,
          "Error loading clr helper module dll '%ws'.\n",
          v10);
      }
      goto LABEL_40;
    }
    v12 = *(_WORD **)(*((_QWORD *)this + 39) + 48LL);
    if ( v12 && *v12 )
    {
      ProcAddress = GetProcAddress(Library, "LoadManagedRuntimeEx");
      if ( ProcAddress )
      {
        v5 = ((__int64 (__fastcall *)(_QWORD, _QWORD, char *))ProcAddress)(
               *(_QWORD *)(*((_QWORD *)this + 39) + 40LL),
               *(_QWORD *)(*((_QWORD *)this + 39) + 48LL),
               (char *)this + 304);
        if ( v5 < 0 )
        {
          if ( (g_dwDebugFlags & 0xF) == 0 )
            goto LABEL_46;
          v14 = 2673;
          goto LABEL_45;
        }
        if ( !v5 )
          goto LABEL_47;
      }
      else
      {
        v17 = GetLastError();
        v5 = v17;
        if ( v17 > 0 )
          v5 = (unsigned __int16)v17 | 0x80070000;
        if ( v5 != -2147024769 )
        {
          if ( (g_dwDebugFlags & 0xF) == 0 )
            goto LABEL_39;
          v18 = GetLastError();
          v19 = 2692;
          goto LABEL_38;
        }
      }
    }
    v15 = GetProcAddress(*((HMODULE *)this + 196), "LoadManagedRuntime");
    if ( v15 )
    {
      v5 = ((__int64 (__fastcall *)(_QWORD, char *))v15)(*(_QWORD *)(*((_QWORD *)this + 39) + 40LL), (char *)this + 304);
      if ( v5 >= 0 )
        goto LABEL_47;
      if ( (g_dwDebugFlags & 0xF) == 0 )
        goto LABEL_46;
      v14 = 2743;
LABEL_45:
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wphost\\w3wphost.cxx",
        v14,
        "W3WP_HOST::TryPreloadClrViaHelperLoader",
        v5,
        "Error getting the managed runtime loaded.  hr = %x\n",
        v22);
      goto LABEL_46;
    }
    v16 = GetLastError();
    v5 = v16;
    if ( v16 > 0 )
      v5 = (unsigned __int16)v16 | 0x80070000;
    if ( v5 == -2147024769 )
    {
      v5 = 1;
LABEL_39:
      FreeLibrary(*((HMODULE *)this + 196));
      *((_QWORD *)this + 196) = 0;
LABEL_40:
      if ( v5 >= 0 )
        goto LABEL_47;
LABEL_46:
      v20 = *((_QWORD *)this + 39);
      v23 = 0;
      *(_QWORD *)&v23 = *(_QWORD *)(v20 + 40);
      *((_QWORD *)&v23 + 1) = STRU::QueryStr((STRU *)v24);
      EVENT_LOG::LogEvent((W3WP_HOST *)((char *)this + 80), 0xC0000900, 2u, (const unsigned __int16 **const)&v23, v5);
      goto LABEL_47;
    }
    if ( (g_dwDebugFlags & 0xF) == 0 )
      goto LABEL_39;
    v18 = GetLastError();
    v19 = 2727;
LABEL_38:
    PuDbgPrintError(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wphost\\w3wphost.cxx",
      v19,
      "W3WP_HOST::TryPreloadClrViaHelperLoader",
      v18,
      "Could not find entry point '%s'.\n",
      "LoadManagedRuntime");
    goto LABEL_39;
  }
  STRU_PATH::~STRU_PATH((STRU_PATH *)v24);
  return 1;
}

```

## disassembly

```asm
0x1800076cc  mov     [rsp-8+arg_10], rbx
0x1800076d1  push    rbp
0x1800076d2  push    rsi
0x1800076d3  push    rdi
0x1800076d4  push    r14
0x1800076d6  push    r15
0x1800076d8  lea     rbp, [rsp-37h]
0x1800076dd  sub     rsp, 0A0h
0x1800076e4  mov     rax, cs:__security_cookie
0x1800076eb  xor     rax, rsp
0x1800076ee  mov     [rbp+57h+var_30], rax
0x1800076f2  mov     rbx, rdx
0x1800076f5  mov     rsi, rcx
0x1800076f8  mov     r14d, 5Ch ; '\'
0x1800076fe  lea     rcx, [rbp+57h+var_70]
0x180007702  mov     edx, r14d
0x180007705  call    cs:__imp_??0STRU_PATH@@QEAA@G@Z; STRU_PATH::STRU_PATH(ushort)
0x18000770c  nop     dword ptr [rax+rax+00h]
0x180007711  mov     rax, [rsi+138h]
0x180007718  xor     r15d, r15d
0x18000771b  mov     rdx, [rax+68h]
0x18000771f  test    rdx, rdx
0x180007722  jz      loc_180007B07
0x180007728  cmp     [rdx], r15w
0x18000772c  jz      loc_180007B07
0x180007732  lea     rcx, [rbp+57h+var_70]
0x180007736  call    cs:__imp_?ExpandEnvironmentVariables@STRU_PATH@@QEAAJPEAG@Z; STRU_PATH::ExpandEnvironmentVariables(ushort *)
0x18000773d  nop     dword ptr [rax+rax+00h]
0x180007742  mov     edi, eax
0x180007744  test    eax, eax
0x180007746  js      loc_180007AA6
0x18000774c  lea     rcx, [rbp+57h+var_70]
0x180007750  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180007757  nop     dword ptr [rax+rax+00h]
0x18000775c  test    rax, rax
0x18000775f  jz      short loc_180007785
0x180007761  movzx   edx, word ptr [rax]
0x180007764  lea     ecx, [rdx-42h]
0x180007767  cmp     cx, 17h
0x18000776b  jbe     short loc_180007777
0x18000776d  sub     dx, 62h ; 'b'
0x180007771  cmp     dx, 17h
0x180007775  ja      short loc_180007785
0x180007777  cmp     word ptr [rax+2], 3Ah ; ':'
0x18000777c  jnz     short loc_180007785
0x18000777e  cmp     [rax+4], r14w
0x180007783  jz      short loc_1800077F4
0x180007785  lea     rcx, [rbp+57h+var_70]
0x180007789  call    cs:__imp_?Reset@STRU@@QEAAXXZ; STRU::Reset(void)
0x180007790  nop     dword ptr [rax+rax+00h]
0x180007795  mov     rdx, rbx
0x180007798  lea     rcx, [rbp+57h+var_70]
0x18000779c  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x1800077a3  nop     dword ptr [rax+rax+00h]
0x1800077a8  mov     edi, eax
0x1800077aa  test    eax, eax
0x1800077ac  js      loc_180007AA6
0x1800077b2  mov     edx, r14d
0x1800077b5  lea     rcx, [rbp+57h+var_70]
0x1800077b9  call    cs:__imp_?Append@STRU@@QEAAJG@Z; STRU::Append(ushort)
0x1800077c0  nop     dword ptr [rax+rax+00h]
0x1800077c5  mov     edi, eax
0x1800077c7  test    eax, eax
0x1800077c9  js      loc_180007AA6
0x1800077cf  mov     rdx, [rsi+138h]
0x1800077d6  lea     rcx, [rbp+57h+var_70]
0x1800077da  mov     rdx, [rdx+68h]
0x1800077de  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x1800077e5  nop     dword ptr [rax+rax+00h]
0x1800077ea  mov     edi, eax
0x1800077ec  test    eax, eax
0x1800077ee  js      loc_180007AA6
0x1800077f4  lea     rcx, [rbp+57h+var_70]
0x1800077f8  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x1800077ff  nop     dword ptr [rax+rax+00h]
0x180007804  xor     edx, edx; hFile
0x180007806  mov     rcx, rax; lpLibFileName
0x180007809  lea     r8d, [rdx+8]; dwFlags
0x18000780d  call    cs:__imp_LoadLibraryExW
0x180007814  nop     dword ptr [rax+rax+00h]
0x180007819  mov     [rsi+620h], rax
0x180007820  mov     rcx, rax; hModule
0x180007823  test    rax, rax
0x180007826  jnz     loc_1800078C6
0x18000782c  call    cs:__imp_GetLastError
0x180007833  nop     dword ptr [rax+rax+00h]
0x180007838  mov     edi, eax
0x18000783a  test    eax, eax
0x18000783c  jle     short loc_180007847
0x18000783e  movzx   edi, ax
0x180007841  or      edi, 80070000h
0x180007847  cmp     edi, 8007007Eh
0x18000784d  jnz     short loc_180007859
0x18000784f  mov     edi, 1
0x180007854  jmp     loc_180007AF3
0x180007859  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180007860  jz      loc_180007A3B
0x180007866  lea     rcx, [rbp+57h+var_70]
0x18000786a  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180007871  nop     dword ptr [rax+rax+00h]
0x180007876  mov     rbx, rax
0x180007879  call    cs:__imp_GetLastError
0x180007880  nop     dword ptr [rax+rax+00h]
0x180007885  lea     rcx, aErrorLoadingCl; "Error loading clr helper module dll '%w"...
0x18000788c  mov     qword ptr [rsp+0C0h+var_90], rbx
0x180007891  mov     [rsp+0C0h+var_98], rcx
0x180007896  lea     r9, aW3wpHostTrypre; "W3WP_HOST::TryPreloadClrViaHelperLoader"
0x18000789d  mov     rcx, cs:g_pDebug
0x1800078a4  lea     rdx, aServercommonIn_3; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x1800078ab  mov     r8d, 0A5Ah
0x1800078b1  mov     [rsp+0C0h+var_A0], eax
0x1800078b5  call    cs:__imp_PuDbgPrintError
0x1800078bc  nop     dword ptr [rax+rax+00h]
0x1800078c1  jmp     loc_180007A3B
0x1800078c6  mov     rax, [rsi+138h]
0x1800078cd  mov     ebx, 80070000h
0x1800078d2  mov     rdx, [rax+30h]
0x1800078d6  test    rdx, rdx
0x1800078d9  jz      short loc_18000793E
0x1800078db  cmp     [rdx], r15w
0x1800078df  jz      short loc_18000793E
0x1800078e1  lea     rdx, ProcName; "LoadManagedRuntimeEx"
0x1800078e8  call    cs:__imp_GetProcAddress
0x1800078ef  nop     dword ptr [rax+rax+00h]
0x1800078f4  test    rax, rax
0x1800078f7  jz      loc_18000798D
0x1800078fd  mov     rcx, [rsi+138h]
0x180007904  lea     r8, [rsi+130h]
0x18000790b  mov     rdx, [rcx+30h]
0x18000790f  mov     rcx, [rcx+28h]
0x180007913  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007918  mov     edi, eax
0x18000791a  test    eax, eax
0x18000791c  jns     short loc_180007936
0x18000791e  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180007925  jz      loc_180007AA6
0x18000792b  mov     r8d, 0A71h
0x180007931  jmp     loc_180007A75
0x180007936  test    edi, edi
0x180007938  jz      loc_180007AF3
0x18000793e  mov     rcx, [rsi+620h]; hModule
0x180007945  lea     r14, aLoadmanagedrun; "LoadManagedRuntime"
0x18000794c  mov     rdx, r14; lpProcName
0x18000794f  call    cs:__imp_GetProcAddress
0x180007956  nop     dword ptr [rax+rax+00h]
0x18000795b  test    rax, rax
0x18000795e  jnz     loc_180007A45
0x180007964  call    cs:__imp_GetLastError
0x18000796b  nop     dword ptr [rax+rax+00h]
0x180007970  mov     edi, eax
0x180007972  test    eax, eax
0x180007974  jle     short loc_18000797B
0x180007976  movzx   edi, ax
0x180007979  or      edi, ebx
0x18000797b  cmp     edi, 8007007Fh
0x180007981  jnz     short loc_1800079D0
0x180007983  mov     edi, 1
0x180007988  jmp     loc_180007A21
0x18000798d  call    cs:__imp_GetLastError
0x180007994  nop     dword ptr [rax+rax+00h]
0x180007999  mov     edi, eax
0x18000799b  test    eax, eax
0x18000799d  jle     short loc_1800079A4
0x18000799f  movzx   edi, ax
0x1800079a2  or      edi, ebx
0x1800079a4  cmp     edi, 8007007Fh
0x1800079aa  jz      short loc_18000793E
0x1800079ac  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x1800079b3  jz      short loc_180007A21
0x1800079b5  call    cs:__imp_GetLastError
0x1800079bc  nop     dword ptr [rax+rax+00h]
0x1800079c1  mov     r8d, 0A84h
0x1800079c7  lea     r14, aLoadmanagedrun; "LoadManagedRuntime"
0x1800079ce  jmp     short loc_1800079EB
0x1800079d0  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x1800079d7  jz      short loc_180007A21
0x1800079d9  call    cs:__imp_GetLastError
0x1800079e0  nop     dword ptr [rax+rax+00h]
0x1800079e5  mov     r8d, 0AA7h
0x1800079eb  lea     rcx, aCouldNotFindEn; "Could not find entry point '%s'.\n"
0x1800079f2  mov     qword ptr [rsp+0C0h+var_90], r14
0x1800079f7  mov     [rsp+0C0h+var_98], rcx
0x1800079fc  lea     r9, aW3wpHostTrypre; "W3WP_HOST::TryPreloadClrViaHelperLoader"
0x180007a03  mov     rcx, cs:g_pDebug
0x180007a0a  lea     rdx, aServercommonIn_3; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180007a11  mov     [rsp+0C0h+var_A0], eax
0x180007a15  call    cs:__imp_PuDbgPrintError
0x180007a1c  nop     dword ptr [rax+rax+00h]
0x180007a21  mov     rcx, [rsi+620h]; hLibModule
0x180007a28  call    cs:__imp_FreeLibrary
0x180007a2f  nop     dword ptr [rax+rax+00h]
0x180007a34  mov     [rsi+620h], r15
0x180007a3b  test    edi, edi
0x180007a3d  jns     loc_180007AF3
0x180007a43  jmp     short loc_180007AA6
0x180007a45  mov     rcx, [rsi+138h]
0x180007a4c  lea     rdx, [rsi+130h]
0x180007a53  mov     rcx, [rcx+28h]
0x180007a57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007a5c  mov     edi, eax
0x180007a5e  test    eax, eax
0x180007a60  jns     loc_180007AF3
0x180007a66  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180007a6d  jz      short loc_180007AA6
0x180007a6f  mov     r8d, 0AB7h
0x180007a75  mov     rcx, cs:g_pDebug
0x180007a7c  lea     rax, aErrorGettingTh; "Error getting the managed runtime loade"...
0x180007a83  mov     [rsp+0C0h+var_98], rax
0x180007a88  lea     r9, aW3wpHostTrypre; "W3WP_HOST::TryPreloadClrViaHelperLoader"
0x180007a8f  lea     rdx, aServercommonIn_3; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180007a96  mov     [rsp+0C0h+var_A0], edi
0x180007a9a  call    cs:__imp_PuDbgPrintError
0x180007aa1  nop     dword ptr [rax+rax+00h]
0x180007aa6  mov     rax, [rsi+138h]
0x180007aad  xorps   xmm0, xmm0
0x180007ab0  movups  [rbp+57h+var_80], xmm0
0x180007ab4  mov     rcx, [rax+28h]
0x180007ab8  mov     qword ptr [rbp+57h+var_80], rcx
0x180007abc  lea     rcx, [rbp+57h+var_70]
0x180007ac0  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180007ac7  nop     dword ptr [rax+rax+00h]
0x180007acc  mov     r8d, 2
0x180007ad2  mov     [rsp+0C0h+var_A0], edi
0x180007ad6  lea     rcx, [rsi+50h]
0x180007ada  mov     qword ptr [rbp+57h+var_80+8], rax
0x180007ade  lea     r9, [rbp+57h+var_80]
0x180007ae2  mov     edx, 0C0000900h
0x180007ae7  call    cs:__imp_?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z; EVENT_LOG::LogEvent(ulong,ushort,ushort const * * const,ulong)
0x180007aee  nop     dword ptr [rax+rax+00h]
0x180007af3  lea     rcx, [rbp+57h+var_70]
0x180007af7  call    cs:__imp_??1STRU_PATH@@QEAA@XZ; STRU_PATH::~STRU_PATH(void)
0x180007afe  nop     dword ptr [rax+rax+00h]
0x180007b03  mov     eax, edi
0x180007b05  jmp     short loc_180007B1C
0x180007b07  lea     rcx, [rbp+57h+var_70]
0x180007b0b  call    cs:__imp_??1STRU_PATH@@QEAA@XZ; STRU_PATH::~STRU_PATH(void)
0x180007b12  nop     dword ptr [rax+rax+00h]
0x180007b17  mov     eax, 1
0x180007b1c  mov     rcx, [rbp+57h+var_30]
0x180007b20  xor     rcx, rsp; StackCookie
0x180007b23  call    __security_check_cookie
0x180007b28  mov     rbx, [rsp+0C0h+arg_10]
0x180007b30  add     rsp, 0A0h
0x180007b37  pop     r15
0x180007b39  pop     r14
0x180007b3b  pop     rdi
0x180007b3c  pop     rsi
0x180007b3d  pop     rbp
0x180007b3e  retn
```
