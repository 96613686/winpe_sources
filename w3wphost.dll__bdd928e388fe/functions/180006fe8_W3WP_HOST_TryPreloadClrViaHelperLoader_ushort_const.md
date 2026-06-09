# W3WP_HOST::TryPreloadClrViaHelperLoader(ushort const *)

- ea: `0x180006fe8`
- end: `0x1800073b8`
- name: `?TryPreloadClrViaHelperLoader@W3WP_HOST@@QEAAJPEBG@Z`
- size: `976`
- prototype: `__int64 __fastcall(W3WP_HOST *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180005d44`

## callees

- `0x180006fe8`
- `0x18000c3d0`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800070f9`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800070f9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800071b6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007217`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800071b6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007217`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800072c9`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800072c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007112`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007153`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007226`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007246`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007268`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007286`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007112`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007153`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007226`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007246`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007268`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007286`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180007060`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800070ea`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000714a`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180007351`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180007060`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800070ea`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000714a`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180007351`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800070d6`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800070d6`
- `iisutil!?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z` at `0x180007372`
- `iisutil!?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z` at `0x180007372`
- `iisutil!PuDbgPrintError` at `0x180007189`
- `iisutil!PuDbgPrintError` at `0x1800072bc`
- `iisutil!PuDbgPrintError` at `0x180007331`
- `iisutil!PuDbgPrintError` at `0x180007189`
- `iisutil!PuDbgPrintError` at `0x1800072bc`
- `iisutil!PuDbgPrintError` at `0x180007331`
- `iisutil!??0STRU_PATH@@QEAA@G@Z` at `0x180007021`
- `iisutil!??0STRU_PATH@@QEAA@G@Z` at `0x180007021`
- `iisutil!??1STRU_PATH@@QEAA@XZ` at `0x18000737c`
- `iisutil!??1STRU_PATH@@QEAA@XZ` at `0x18000738a`
- `iisutil!??1STRU_PATH@@QEAA@XZ` at `0x18000737c`
- `iisutil!??1STRU_PATH@@QEAA@XZ` at `0x18000738a`
- `iisutil!?ExpandEnvironmentVariables@STRU_PATH@@QEAAJPEAG@Z` at `0x18000704c`
- `iisutil!?ExpandEnvironmentVariables@STRU_PATH@@QEAAJPEAG@Z` at `0x18000704c`
- `iisutil!?Reset@STRU@@QEAAXXZ` at `0x180007093`
- `iisutil!?Reset@STRU@@QEAAXXZ` at `0x180007093`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800070a0`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800070a0`
- `iisutil!?Append@STRU@@QEAAJG@Z` at `0x1800070b7`
- `iisutil!?Append@STRU@@QEAAJG@Z` at `0x1800070b7`

## string_xrefs

- `0x180007178`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\w3wphost.cxx`
- `0x1800072b1`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\w3wphost.cxx`
- `0x180007326`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\w3wphost.cxx`
- `0x180007159`: `Error loading clr helper module dll '%ws'.\n`

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
0x180006fe8  mov     [rsp-8+arg_10], rbx
0x180006fed  push    rbp
0x180006fee  push    rsi
0x180006fef  push    rdi
0x180006ff0  push    r14
0x180006ff2  push    r15
0x180006ff4  lea     rbp, [rsp-37h]
0x180006ff9  sub     rsp, 0A0h
0x180007000  mov     rax, cs:__security_cookie
0x180007007  xor     rax, rsp
0x18000700a  mov     [rbp+57h+var_30], rax
0x18000700e  mov     rbx, rdx
0x180007011  mov     rsi, rcx
0x180007014  mov     r14d, 5Ch ; '\'
0x18000701a  lea     rcx, [rbp+57h+var_70]
0x18000701e  mov     edx, r14d
0x180007021  call    cs:__imp_??0STRU_PATH@@QEAA@G@Z; STRU_PATH::STRU_PATH(ushort)
0x180007027  mov     rax, [rsi+138h]
0x18000702e  xor     r15d, r15d
0x180007031  mov     rdx, [rax+68h]
0x180007035  test    rdx, rdx
0x180007038  jz      loc_180007386
0x18000703e  cmp     [rdx], r15w
0x180007042  jz      loc_180007386
0x180007048  lea     rcx, [rbp+57h+var_70]
0x18000704c  call    cs:__imp_?ExpandEnvironmentVariables@STRU_PATH@@QEAAJPEAG@Z; STRU_PATH::ExpandEnvironmentVariables(ushort *)
0x180007052  mov     edi, eax
0x180007054  test    eax, eax
0x180007056  js      loc_180007337
0x18000705c  lea     rcx, [rbp+57h+var_70]
0x180007060  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180007066  test    rax, rax
0x180007069  jz      short loc_18000708F
0x18000706b  movzx   edx, word ptr [rax]
0x18000706e  lea     ecx, [rdx-42h]
0x180007071  cmp     cx, 17h
0x180007075  jbe     short loc_180007081
0x180007077  sub     dx, 62h ; 'b'
0x18000707b  cmp     dx, 17h
0x18000707f  ja      short loc_18000708F
0x180007081  cmp     word ptr [rax+2], 3Ah ; ':'
0x180007086  jnz     short loc_18000708F
0x180007088  cmp     [rax+4], r14w
0x18000708d  jz      short loc_1800070E6
0x18000708f  lea     rcx, [rbp+57h+var_70]
0x180007093  call    cs:__imp_?Reset@STRU@@QEAAXXZ; STRU::Reset(void)
0x180007099  mov     rdx, rbx
0x18000709c  lea     rcx, [rbp+57h+var_70]
0x1800070a0  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x1800070a6  mov     edi, eax
0x1800070a8  test    eax, eax
0x1800070aa  js      loc_180007337
0x1800070b0  mov     edx, r14d
0x1800070b3  lea     rcx, [rbp+57h+var_70]
0x1800070b7  call    cs:__imp_?Append@STRU@@QEAAJG@Z; STRU::Append(ushort)
0x1800070bd  mov     edi, eax
0x1800070bf  test    eax, eax
0x1800070c1  js      loc_180007337
0x1800070c7  mov     rdx, [rsi+138h]
0x1800070ce  lea     rcx, [rbp+57h+var_70]
0x1800070d2  mov     rdx, [rdx+68h]
0x1800070d6  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x1800070dc  mov     edi, eax
0x1800070de  test    eax, eax
0x1800070e0  js      loc_180007337
0x1800070e6  lea     rcx, [rbp+57h+var_70]
0x1800070ea  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x1800070f0  xor     edx, edx; hFile
0x1800070f2  mov     rcx, rax; lpLibFileName
0x1800070f5  lea     r8d, [rdx+8]; dwFlags
0x1800070f9  call    cs:__imp_LoadLibraryExW
0x1800070ff  mov     [rsi+620h], rax
0x180007106  mov     rcx, rax; hModule
0x180007109  test    rax, rax
0x18000710c  jnz     loc_180007194
0x180007112  call    cs:__imp_GetLastError
0x180007118  mov     edi, eax
0x18000711a  test    eax, eax
0x18000711c  jle     short loc_180007127
0x18000711e  movzx   edi, ax
0x180007121  or      edi, 80070000h
0x180007127  cmp     edi, 8007007Eh
0x18000712d  jnz     short loc_180007139
0x18000712f  mov     edi, 1
0x180007134  jmp     loc_180007378
0x180007139  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180007140  jz      loc_1800072D6
0x180007146  lea     rcx, [rbp+57h+var_70]
0x18000714a  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180007150  mov     rbx, rax
0x180007153  call    cs:__imp_GetLastError
0x180007159  lea     rcx, aErrorLoadingCl; "Error loading clr helper module dll '%w"...
0x180007160  mov     qword ptr [rsp+0C0h+var_90], rbx
0x180007165  mov     [rsp+0C0h+var_98], rcx
0x18000716a  lea     r9, aW3wpHostTrypre; "W3WP_HOST::TryPreloadClrViaHelperLoader"
0x180007171  mov     rcx, cs:g_pDebug
0x180007178  lea     rdx, aServercommonIn_3; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x18000717f  mov     r8d, 0A5Ah
0x180007185  mov     [rsp+0C0h+var_A0], eax
0x180007189  call    cs:__imp_PuDbgPrintError
0x18000718f  jmp     loc_1800072D6
0x180007194  mov     rax, [rsi+138h]
0x18000719b  mov     ebx, 80070000h
0x1800071a0  mov     rdx, [rax+30h]
0x1800071a4  test    rdx, rdx
0x1800071a7  jz      short loc_180007206
0x1800071a9  cmp     [rdx], r15w
0x1800071ad  jz      short loc_180007206
0x1800071af  lea     rdx, ProcName; "LoadManagedRuntimeEx"
0x1800071b6  call    cs:__imp_GetProcAddress
0x1800071bc  test    rax, rax
0x1800071bf  jz      loc_180007246
0x1800071c5  mov     rcx, [rsi+138h]
0x1800071cc  lea     r8, [rsi+130h]
0x1800071d3  mov     rdx, [rcx+30h]
0x1800071d7  mov     rcx, [rcx+28h]
0x1800071db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800071e0  mov     edi, eax
0x1800071e2  test    eax, eax
0x1800071e4  jns     short loc_1800071FE
0x1800071e6  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x1800071ed  jz      loc_180007337
0x1800071f3  mov     r8d, 0A71h
0x1800071f9  jmp     loc_18000730C
0x1800071fe  test    edi, edi
0x180007200  jz      loc_180007378
0x180007206  mov     rcx, [rsi+620h]; hModule
0x18000720d  lea     r14, aLoadmanagedrun; "LoadManagedRuntime"
0x180007214  mov     rdx, r14; lpProcName
0x180007217  call    cs:__imp_GetProcAddress
0x18000721d  test    rax, rax
0x180007220  jnz     loc_1800072E0
0x180007226  call    cs:__imp_GetLastError
0x18000722c  mov     edi, eax
0x18000722e  test    eax, eax
0x180007230  jle     short loc_180007237
0x180007232  movzx   edi, ax
0x180007235  or      edi, ebx
0x180007237  cmp     edi, 8007007Fh
0x18000723d  jnz     short loc_18000727D
0x18000723f  mov     edi, 1
0x180007244  jmp     short loc_1800072C2
0x180007246  call    cs:__imp_GetLastError
0x18000724c  mov     edi, eax
0x18000724e  test    eax, eax
0x180007250  jle     short loc_180007257
0x180007252  movzx   edi, ax
0x180007255  or      edi, ebx
0x180007257  cmp     edi, 8007007Fh
0x18000725d  jz      short loc_180007206
0x18000725f  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180007266  jz      short loc_1800072C2
0x180007268  call    cs:__imp_GetLastError
0x18000726e  mov     r8d, 0A84h
0x180007274  lea     r14, aLoadmanagedrun; "LoadManagedRuntime"
0x18000727b  jmp     short loc_180007292
0x18000727d  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180007284  jz      short loc_1800072C2
0x180007286  call    cs:__imp_GetLastError
0x18000728c  mov     r8d, 0AA7h
0x180007292  lea     rcx, aCouldNotFindEn; "Could not find entry point '%s'.\n"
0x180007299  mov     qword ptr [rsp+0C0h+var_90], r14
0x18000729e  mov     [rsp+0C0h+var_98], rcx
0x1800072a3  lea     r9, aW3wpHostTrypre; "W3WP_HOST::TryPreloadClrViaHelperLoader"
0x1800072aa  mov     rcx, cs:g_pDebug
0x1800072b1  lea     rdx, aServercommonIn_3; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x1800072b8  mov     [rsp+0C0h+var_A0], eax
0x1800072bc  call    cs:__imp_PuDbgPrintError
0x1800072c2  mov     rcx, [rsi+620h]; hLibModule
0x1800072c9  call    cs:__imp_FreeLibrary
0x1800072cf  mov     [rsi+620h], r15
0x1800072d6  test    edi, edi
0x1800072d8  jns     loc_180007378
0x1800072de  jmp     short loc_180007337
0x1800072e0  mov     rcx, [rsi+138h]
0x1800072e7  lea     rdx, [rsi+130h]
0x1800072ee  mov     rcx, [rcx+28h]
0x1800072f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800072f7  mov     edi, eax
0x1800072f9  test    eax, eax
0x1800072fb  jns     short loc_180007378
0x1800072fd  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180007304  jz      short loc_180007337
0x180007306  mov     r8d, 0AB7h
0x18000730c  mov     rcx, cs:g_pDebug
0x180007313  lea     rax, aErrorGettingTh; "Error getting the managed runtime loade"...
0x18000731a  mov     [rsp+0C0h+var_98], rax
0x18000731f  lea     r9, aW3wpHostTrypre; "W3WP_HOST::TryPreloadClrViaHelperLoader"
0x180007326  lea     rdx, aServercommonIn_3; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x18000732d  mov     [rsp+0C0h+var_A0], edi
0x180007331  call    cs:__imp_PuDbgPrintError
0x180007337  mov     rax, [rsi+138h]
0x18000733e  xorps   xmm0, xmm0
0x180007341  movups  [rbp+57h+var_80], xmm0
0x180007345  mov     rcx, [rax+28h]
0x180007349  mov     qword ptr [rbp+57h+var_80], rcx
0x18000734d  lea     rcx, [rbp+57h+var_70]
0x180007351  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180007357  mov     r8d, 2
0x18000735d  mov     [rsp+0C0h+var_A0], edi
0x180007361  lea     rcx, [rsi+50h]
0x180007365  mov     qword ptr [rbp+57h+var_80+8], rax
0x180007369  lea     r9, [rbp+57h+var_80]
0x18000736d  mov     edx, 0C0000900h
0x180007372  call    cs:__imp_?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z; EVENT_LOG::LogEvent(ulong,ushort,ushort const * * const,ulong)
0x180007378  lea     rcx, [rbp+57h+var_70]
0x18000737c  call    cs:__imp_??1STRU_PATH@@QEAA@XZ; STRU_PATH::~STRU_PATH(void)
0x180007382  mov     eax, edi
0x180007384  jmp     short loc_180007395
0x180007386  lea     rcx, [rbp+57h+var_70]
0x18000738a  call    cs:__imp_??1STRU_PATH@@QEAA@XZ; STRU_PATH::~STRU_PATH(void)
0x180007390  mov     eax, 1
0x180007395  mov     rcx, [rbp+57h+var_30]
0x180007399  xor     rcx, rsp; StackCookie
0x18000739c  call    __security_check_cookie
0x1800073a1  mov     rbx, [rsp+0C0h+arg_10]
0x1800073a9  add     rsp, 0A0h
0x1800073b0  pop     r15
0x1800073b2  pop     r14
0x1800073b4  pop     rdi
0x1800073b5  pop     rsi
0x1800073b6  pop     rbp
0x1800073b7  retn
```
