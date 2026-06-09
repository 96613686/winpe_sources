# ProcessXMLFileW

- ea: `0x180009730`
- end: `0x180009c6a`
- name: `ProcessXMLFileW`
- size: `1338`
- prototype: `__int64 __fastcall(HWND hWnd, __int64, const WCHAR *)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180009680`

## callees

- `0x180004370`
- `0x180005ce8`
- `0x180005e30`
- `0x1800085a8`
- `0x180008634`
- `0x180008fd0`
- `0x1800095d0`
- `0x180009730`
- `0x18000ae04`
- `0x18000ae44`
- `0x18000ae90`
- `0x18000e87c`
- `0x18001a088`
- `0x180032a02`
- `0x180032a30`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180009a34`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180009aab`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180009b4e`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180009a34`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180009aab`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180009b4e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009b8a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009bfd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009c08`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009c11`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009b8a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009bfd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009c08`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009c11`
- `api-ms-win-shcore-obsolete-l1-1-0!CommandLineToArgvW` at `0x18000977a`
- `api-ms-win-shcore-obsolete-l1-1-0!CommandLineToArgvW` at `0x18000977a`
- `USER32!MessageBoxW` at `0x180009bf2`
- `USER32!MessageBoxW` at `0x180009bf2`
- `USER32!SetProcessDPIAware` at `0x1800097d7`
- `USER32!SetProcessDPIAware` at `0x1800097d7`
- `SHELL32!ShellExecuteExW` at `0x180009959`
- `SHELL32!ShellExecuteExW` at `0x180009959`

## string_xrefs

- `0x180009934`: `%systemroot%\system32\xwizard.exe`
- `0x1800098f4`: `ProcessXMLFile `

## pseudocode

```c
__int64 __fastcall ProcessXMLFileW(HWND hWnd, __int64 a2, const WCHAR *a3)
{
  LPWSTR *v4; // r13
  unsigned int LastErrorHRESULT; // eax
  unsigned int v6; // ebx
  DWORD v8; // edi
  unsigned int v9; // ebx
  int v10; // eax
  int v11; // ecx
  LPWSTR v12; // r9
  DWORD v13; // eax
  unsigned int v14; // r11d
  DWORD v15; // eax
  int v16; // ebx
  PVOID *v17; // rcx
  unsigned int v18; // eax
  const WCHAR *v19; // rdx
  unsigned int v20; // eax
  unsigned int v21; // eax
  int pNumArgs; // [rsp+40h] [rbp-C0h] BYREF
  DWORD v23[2]; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR Buffer[4]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR lpBuffer[4]; // [rsp+58h] [rbp-A8h] BYREF
  int v26; // [rsp+60h] [rbp-A0h]
  va_list Arguments[2]; // [rsp+68h] [rbp-98h] BYREF
  SHELLEXECUTEINFOW pExecInfo; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 v29[16]; // [rsp+F0h] [rbp-10h] BYREF
  unsigned __int16 v30[280]; // [rsp+110h] [rbp+10h] BYREF

  *(_QWORD *)Buffer = a3;
  pNumArgs = 0;
  v4 = CommandLineToArgvW(a3, &pNumArgs);
  if ( !v4 )
  {
    LastErrorHRESULT = GetLastErrorHRESULT();
    v6 = LastErrorHRESULT;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        42,
        WPP_68058977b0c233f043f68faaec20b8c5_Traceguids,
        LastErrorHRESULT);
    return v6;
  }
  v8 = 0;
  *(_QWORD *)lpBuffer = 0;
  v9 = 0;
  v26 = 0;
  SetProcessDPIAware();
  while ( 1 )
  {
    if ( v8 )
      goto LABEL_58;
    v10 = pNumArgs;
    v11 = --pNumArgs;
    if ( !v10 )
      break;
    v12 = v4[v11];
    if ( ((*v12 - 45) & 0xFFFD) != 0 )
    {
      *(_QWORD *)lpBuffer = v4[v11];
    }
    else
    {
      switch ( v12[1] )
      {
        case '?':
          DisplayUsage(hWnd, 1u, 3u);
LABEL_29:
          v8 = 1;
          break;
        case 'm':
          v23[0] = 0;
          if ( (unsigned int)LUAGetUserType(65533, v23) )
            goto LABEL_27;
          v13 = v23[0];
          if ( v23[0] >= 3 )
            v13 = v23[0] - 16;
          if ( v13 != 1 )
          {
LABEL_27:
            v9 |= 0x10000u;
          }
          else
          {
            memset_0(&pExecInfo, 0, sizeof(pExecInfo));
            v30[0] = 0;
            StringCchCopyW(v30, 0x115u, L"ProcessXMLFile ");
            StringCchCatW(v30, v14, *(const unsigned __int16 **)Buffer);
            pExecInfo.cbSize = 112;
            pExecInfo.lpVerb = L"runas";
            pExecInfo.hwnd = hWnd;
            pExecInfo.lpFile = L"%systemroot%\\system32\\xwizard.exe";
            pExecInfo.lpParameters = v30;
            pExecInfo.fMask = 512;
            pExecInfo.nShow = 1;
            if ( ShellExecuteExW(&pExecInfo) )
              goto LABEL_29;
            v15 = GetLastErrorHRESULT();
            v8 = v15;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, WPP_68058977b0c233f043f68faaec20b8c5_Traceguids, v15);
          }
          break;
        case 'u':
          v26 = 1;
          break;
        default:
          v8 = -2147024809;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
            WPP_SF_SD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              44,
              (unsigned int)WPP_68058977b0c233f043f68faaec20b8c5_Traceguids,
              (_DWORD)v12,
              87);
          DisplayInvalidOption(hWnd, 2u, v4[pNumArgs]);
          DisplayUsage(hWnd, 1u, 3u);
          break;
      }
    }
  }
  *(_QWORD *)v23 = 0;
  v8 = InternalProcessXMLFile(hWnd, *(_QWORD *)lpBuffer, v9, v23, 0);
  if ( (int)(v8 + 0x80000000) >= 0 && v8 != -2147023673 )
  {
    v16 = 0;
    *(_QWORD *)Buffer = 0;
    if ( FormatMessageW(0x900u, lpSource, 2u, 0, Buffer, 0, 0) )
      goto LABEL_37;
    v18 = GetLastErrorHRESULT();
    v16 = v18;
    v17 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, WPP_68058977b0c233f043f68faaec20b8c5_Traceguids, v18);
      v17 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v16 >= 0 )
    {
LABEL_37:
      v19 = *(const WCHAR **)v23;
      if ( !*(_QWORD *)v23 )
      {
        *(_QWORD *)lpBuffer = 0;
        if ( !FormatMessageW(0x1100u, 0, v8, 0, lpBuffer, 0, 0) )
        {
          v20 = GetLastErrorHRESULT();
          v16 = v20;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, WPP_68058977b0c233f043f68faaec20b8c5_Traceguids, v20);
        }
        if ( v16 >= 0 )
        {
          *(_OWORD *)Arguments = 0;
          swprintf_sfn(v29, 0xDu, L"%#X", v8);
          Arguments[0] = (va_list)v29;
          Arguments[1] = *(va_list *)lpBuffer;
          if ( !FormatMessageW(0x2900u, lpSource, 0xC0000005, 0, (LPWSTR)v23, 0, Arguments) )
          {
            v21 = GetLastErrorHRESULT();
            v16 = v21;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, WPP_68058977b0c233f043f68faaec20b8c5_Traceguids, v21);
          }
        }
        LocalFree(*(HLOCAL *)lpBuffer);
        if ( v16 < 0 )
        {
          v17 = (PVOID *)WPP_GLOBAL_Control;
          goto LABEL_49;
        }
        v19 = *(const WCHAR **)v23;
      }
      if ( v26 )
      {
        if ( (Microsoft_Windows_XWizardsEnableBits & 4) != 0 )
          McTemplateU0zz_EventWriteTransfer(v17, v19, *(_QWORD *)Buffer, v19);
      }
      else
      {
        MessageBoxW(hWnd, v19, *(LPCWSTR *)Buffer, 0x10u);
      }
    }
    else
    {
LABEL_49:
      if ( v17 != &WPP_GLOBAL_Control && (*((_BYTE *)v17 + 28) & 4) != 0 )
        WPP_SF_DD(v17[2], 48, WPP_68058977b0c233f043f68faaec20b8c5_Traceguids, (unsigned int)v16, v8);
    }
    LocalFree(*(HLOCAL *)Buffer);
    LocalFree(*(HLOCAL *)v23);
  }
LABEL_58:
  LocalFree(v4);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 49, WPP_68058977b0c233f043f68faaec20b8c5_Traceguids, v8);
  return v8;
}

```

## disassembly

```asm
0x180009730  mov     [rsp-8+arg_8], rbx
0x180009735  mov     [rsp-8+arg_18], rsi
0x18000973a  push    rbp
0x18000973b  push    rdi
0x18000973c  push    r12
0x18000973e  push    r13
0x180009740  push    r15
0x180009742  lea     rbp, [rsp-250h]
0x18000974a  sub     rsp, 350h
0x180009751  mov     rax, cs:__security_cookie
0x180009758  xor     rax, rsp
0x18000975b  mov     [rbp+270h+var_30], rax
0x180009762  mov     r12, rcx
0x180009765  mov     qword ptr [rsp+370h+Buffer], r8
0x18000976a  mov     rcx, r8; lpCmdLine
0x18000976d  mov     [rsp+370h+pNumArgs], 0
0x180009775  lea     rdx, [rsp+370h+pNumArgs]; pNumArgs
0x18000977a  call    cs:__imp_CommandLineToArgvW
0x180009780  mov     r13, rax
0x180009783  test    rax, rax
0x180009786  jnz     short loc_1800097C6
0x180009788  call    ?GetLastErrorHRESULT@@YAJXZ; GetLastErrorHRESULT(void)
0x18000978d  mov     ebx, eax
0x18000978f  mov     rcx, cs:WPP_GLOBAL_Control
0x180009796  lea     rsi, WPP_GLOBAL_Control
0x18000979d  cmp     rcx, rsi
0x1800097a0  jz      short loc_1800097BF
0x1800097a2  test    byte ptr [rcx+1Ch], 4
0x1800097a6  jz      short loc_1800097BF
0x1800097a8  mov     rcx, [rcx+10h]
0x1800097ac  lea     edx, [r13+2Ah]
0x1800097b0  mov     r9d, eax
0x1800097b3  lea     r8, WPP_68058977b0c233f043f68faaec20b8c5_Traceguids
0x1800097ba  call    WPP_SF_d
0x1800097bf  mov     eax, ebx
0x1800097c1  jmp     loc_180009C3F
0x1800097c6  xor     edx, edx
0x1800097c8  xor     eax, eax
0x1800097ca  xor     edi, edi
0x1800097cc  mov     qword ptr [rsp+370h+var_318], rdx
0x1800097d1  xor     ebx, ebx
0x1800097d3  mov     [rsp+370h+var_310], eax
0x1800097d7  call    cs:__imp_SetProcessDPIAware
0x1800097dd  lea     rsi, WPP_GLOBAL_Control
0x1800097e4  lea     r15, WPP_68058977b0c233f043f68faaec20b8c5_Traceguids
0x1800097eb  mov     edx, 2Dh ; '-'
0x1800097f0  test    edi, edi
0x1800097f2  jnz     loc_180009C0E
0x1800097f8  mov     eax, [rsp+370h+pNumArgs]
0x1800097fc  mov     ecx, eax
0x1800097fe  dec     ecx
0x180009800  mov     [rsp+370h+pNumArgs], ecx
0x180009804  test    eax, eax
0x180009806  jz      loc_1800099C1
0x18000980c  movsxd  rax, ecx
0x18000980f  mov     ecx, 0FFFDh
0x180009814  mov     r9, [r13+rax*8+0]
0x180009819  movzx   eax, word ptr [r9]
0x18000981d  sub     ax, dx
0x180009820  test    cx, ax
0x180009823  jz      short loc_18000982C
0x180009825  mov     qword ptr [rsp+370h+var_318], r9
0x18000982a  jmp     short loc_1800097F0
0x18000982c  cmp     word ptr [r9+2], 3Fh ; '?'
0x180009832  jz      loc_1800099A6
0x180009838  cmp     word ptr [r9+2], 6Dh ; 'm'
0x18000983e  jz      short loc_1800098B2
0x180009840  cmp     word ptr [r9+2], 75h ; 'u'
0x180009846  jz      short loc_1800098A5
0x180009848  mov     edi, 80070057h
0x18000984d  mov     rcx, cs:WPP_GLOBAL_Control
0x180009854  cmp     rcx, rsi
0x180009857  jz      short loc_180009878
0x180009859  test    byte ptr [rcx+1Ch], 10h
0x18000985d  jz      short loc_180009878
0x18000985f  mov     rcx, [rcx+10h]
0x180009863  mov     edx, 2Ch ; ','
0x180009868  mov     r8, r15
0x18000986b  mov     dword ptr [rsp+370h+lpBuffer], 80070057h
0x180009873  call    WPP_SF_SD
0x180009878  movsxd  r8, [rsp+370h+pNumArgs]
0x18000987d  mov     edx, 2; dwMessageId
0x180009882  mov     rcx, r12; hWnd
0x180009885  mov     r8, [r13+r8*8+0]; unsigned __int16 *
0x18000988a  call    ?DisplayInvalidOption@@YAXPEAUHWND__@@KPEAG@Z; DisplayInvalidOption(HWND__ *,ulong,ushort *)
0x18000988f  mov     edx, 1; dwMessageId
0x180009894  mov     rcx, r12; hWnd
0x180009897  lea     r8d, [rdx+2]; DWORD
0x18000989b  call    ?DisplayUsage@@YAXPEAUHWND__@@KK@Z; DisplayUsage(HWND__ *,ulong,ulong)
0x1800098a0  jmp     loc_1800097EB
0x1800098a5  mov     [rsp+370h+var_310], 1
0x1800098ad  jmp     loc_1800097F0
0x1800098b2  lea     rdx, [rsp+370h+var_328]
0x1800098b7  mov     [rsp+370h+var_328], 0
0x1800098bf  call    LUAGetUserType
0x1800098c4  test    eax, eax
0x1800098c6  jnz     loc_18000999D
0x1800098cc  mov     eax, [rsp+370h+var_328]
0x1800098d0  cmp     eax, 3
0x1800098d3  jb      short loc_1800098D8
0x1800098d5  add     eax, 0FFFFFFF0h
0x1800098d8  cmp     eax, 1
0x1800098db  jnz     loc_18000999D
0x1800098e1  lea     edi, [rax+6Fh]
0x1800098e4  xor     edx, edx; Val
0x1800098e6  mov     r8d, edi; Size
0x1800098e9  lea     rcx, [rbp+270h+pExecInfo]; void *
0x1800098ed  call    memset_0
0x1800098f2  xor     eax, eax
0x1800098f4  lea     r8, aProcessxmlfile_1; "ProcessXMLFile "
0x1800098fb  mov     r11d, 115h
0x180009901  mov     [rbp+270h+var_260], ax
0x180009905  mov     edx, r11d; unsigned __int64
0x180009908  lea     rcx, [rbp+270h+var_260]; unsigned __int16 *
0x18000990c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180009911  mov     r8, qword ptr [rsp+370h+Buffer]; unsigned __int16 *
0x180009916  lea     rcx, [rbp+270h+var_260]; unsigned __int16 *
0x18000991a  mov     edx, r11d; unsigned __int64
0x18000991d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180009922  lea     rax, aRunas; "runas"
0x180009929  mov     [rbp+270h+pExecInfo.cbSize], edi
0x18000992c  mov     [rbp+270h+pExecInfo.lpVerb], rax
0x180009930  lea     rcx, [rbp+270h+pExecInfo]; pExecInfo
0x180009934  lea     rax, aSystemrootSyst; "%systemroot%\\system32\\xwizard.exe"
0x18000993b  mov     [rbp+270h+pExecInfo.hwnd], r12
0x18000993f  mov     [rbp+270h+pExecInfo.lpFile], rax
0x180009943  lea     rax, [rbp+270h+var_260]
0x180009947  mov     [rbp+270h+pExecInfo.lpParameters], rax
0x18000994b  mov     [rbp+270h+pExecInfo.fMask], 200h
0x180009952  mov     [rbp+270h+pExecInfo.nShow], 1
0x180009959  call    cs:__imp_ShellExecuteExW
0x18000995f  test    eax, eax
0x180009961  jnz     short loc_1800099B7
0x180009963  call    ?GetLastErrorHRESULT@@YAJXZ; GetLastErrorHRESULT(void)
0x180009968  mov     edi, eax
0x18000996a  mov     rcx, cs:WPP_GLOBAL_Control
0x180009971  cmp     rcx, rsi
0x180009974  jz      loc_1800097EB
0x18000997a  test    byte ptr [rcx+1Ch], 4
0x18000997e  jz      loc_1800097EB
0x180009984  mov     rcx, [rcx+10h]
0x180009988  mov     edx, 2Bh ; '+'
0x18000998d  mov     r9d, eax
0x180009990  mov     r8, r15
0x180009993  call    WPP_SF_d
0x180009998  jmp     loc_1800097EB
0x18000999d  bts     ebx, 10h
0x1800099a1  jmp     loc_1800097EB
0x1800099a6  mov     edx, 1; dwMessageId
0x1800099ab  mov     rcx, r12; hWnd
0x1800099ae  lea     r8d, [rdx+2]; DWORD
0x1800099b2  call    ?DisplayUsage@@YAXPEAUHWND__@@KK@Z; DisplayUsage(HWND__ *,ulong,ulong)
0x1800099b7  mov     edi, 1
0x1800099bc  jmp     loc_1800097EB
0x1800099c1  mov     rdx, qword ptr [rsp+370h+var_318]
0x1800099c6  lea     r9, [rsp+370h+var_328]
0x1800099cb  mov     r8d, ebx
0x1800099ce  mov     qword ptr [rsp+370h+var_328], 0
0x1800099d7  mov     rcx, r12
0x1800099da  mov     [rsp+370h+lpBuffer], 0
0x1800099e3  call    InternalProcessXMLFile
0x1800099e8  mov     ecx, 80000000h
0x1800099ed  mov     edi, eax
0x1800099ef  add     eax, ecx
0x1800099f1  test    ecx, eax
0x1800099f3  jnz     loc_180009C0E
0x1800099f9  cmp     edi, 800704C7h
0x1800099ff  jz      loc_180009C0E
0x180009a05  mov     rdx, cs:lpSource; lpSource
0x180009a0c  xor     eax, eax
0x180009a0e  mov     [rsp+370h+Arguments], rax; Arguments
0x180009a13  xor     r9d, r9d; dwLanguageId
0x180009a16  mov     [rsp+370h+nSize], eax; nSize
0x180009a1a  mov     ebx, eax
0x180009a1c  mov     qword ptr [rsp+370h+Buffer], rax
0x180009a21  mov     ecx, 900h; dwFlags
0x180009a26  lea     rax, [rsp+370h+Buffer]
0x180009a2b  lea     r8d, [r9+2]; dwMessageId
0x180009a2f  mov     [rsp+370h+lpBuffer], rax; lpBuffer
0x180009a34  call    cs:__imp_FormatMessageW
0x180009a3a  test    eax, eax
0x180009a3c  jnz     short loc_180009A7A
0x180009a3e  call    ?GetLastErrorHRESULT@@YAJXZ; GetLastErrorHRESULT(void)
0x180009a43  mov     ebx, eax
0x180009a45  mov     rcx, cs:WPP_GLOBAL_Control
0x180009a4c  cmp     rcx, rsi
0x180009a4f  jz      short loc_180009A72
0x180009a51  test    byte ptr [rcx+1Ch], 4
0x180009a55  jz      short loc_180009A72
0x180009a57  mov     rcx, [rcx+10h]
0x180009a5b  mov     edx, 2Dh ; '-'
0x180009a60  mov     r9d, eax
0x180009a63  mov     r8, r15
0x180009a66  call    WPP_SF_d
0x180009a6b  mov     rcx, cs:WPP_GLOBAL_Control
0x180009a72  test    ebx, ebx
0x180009a74  js      loc_180009B9B
0x180009a7a  mov     rdx, qword ptr [rsp+370h+var_328]; lpSource
0x180009a7f  test    rdx, rdx
0x180009a82  jnz     loc_180009BC5
0x180009a88  mov     [rsp+370h+Arguments], rdx; Arguments
0x180009a8d  lea     rax, [rsp+370h+var_318]
0x180009a92  mov     [rsp+370h+nSize], edx; nSize
0x180009a96  xor     r9d, r9d; dwLanguageId
0x180009a99  mov     r8d, edi; dwMessageId
0x180009a9c  mov     [rsp+370h+lpBuffer], rax; lpBuffer
0x180009aa1  mov     ecx, 1100h; dwFlags
0x180009aa6  mov     qword ptr [rsp+370h+var_318], rdx
0x180009aab  call    cs:__imp_FormatMessageW
0x180009ab1  test    eax, eax
0x180009ab3  jnz     short loc_180009AE2
0x180009ab5  call    ?GetLastErrorHRESULT@@YAJXZ; GetLastErrorHRESULT(void)
0x180009aba  mov     ebx, eax
0x180009abc  mov     rcx, cs:WPP_GLOBAL_Control
0x180009ac3  cmp     rcx, rsi
0x180009ac6  jz      short loc_180009AE2
0x180009ac8  test    byte ptr [rcx+1Ch], 4
0x180009acc  jz      short loc_180009AE2
0x180009ace  mov     rcx, [rcx+10h]
0x180009ad2  mov     edx, 2Eh ; '.'
0x180009ad7  mov     r9d, eax
0x180009ada  mov     r8, r15
0x180009add  call    WPP_SF_d
0x180009ae2  test    ebx, ebx
0x180009ae4  js      loc_180009B85
0x180009aea  xorps   xmm0, xmm0
0x180009aed  lea     r8, asc_18003C1E8; "%#X"
0x180009af4  mov     r9d, edi
0x180009af7  lea     rcx, [rbp+270h+var_280]; unsigned __int16 *
0x180009afb  mov     edx, 0Dh; unsigned __int64
0x180009b00  movups  xmmword ptr [rsp+370h+var_308], xmm0
0x180009b05  call    ?swprintf_sfn@@YAXPEAG_KPEBGZZ; swprintf_sfn(ushort *,unsigned __int64,ushort const *,...)
0x180009b0a  mov     rdx, cs:lpSource; lpSource
0x180009b11  lea     rax, [rbp+270h+var_280]
0x180009b15  mov     [rsp+370h+var_308], rax
0x180009b1a  xor     r9d, r9d; dwLanguageId
0x180009b1d  mov     rax, qword ptr [rsp+370h+var_318]
0x180009b22  mov     r8d, 0C0000005h; dwMessageId
0x180009b28  mov     [rsp+370h+var_308+8], rax
0x180009b2d  mov     ecx, 2900h; dwFlags
0x180009b32  lea     rax, [rsp+370h+var_308]
0x180009b37  mov     [rsp+370h+Arguments], rax; Arguments
0x180009b3c  lea     rax, [rsp+370h+var_328]
0x180009b41  mov     [rsp+370h+nSize], 0; nSize
0x180009b49  mov     [rsp+370h+lpBuffer], rax; lpBuffer
0x180009b4e  call    cs:__imp_FormatMessageW
0x180009b54  test    eax, eax
0x180009b56  jnz     short loc_180009B85
0x180009b58  call    ?GetLastErrorHRESULT@@YAJXZ; GetLastErrorHRESULT(void)
0x180009b5d  mov     ebx, eax
0x180009b5f  mov     rcx, cs:WPP_GLOBAL_Control
0x180009b66  cmp     rcx, rsi
0x180009b69  jz      short loc_180009B85
0x180009b6b  test    byte ptr [rcx+1Ch], 4
0x180009b6f  jz      short loc_180009B85
0x180009b71  mov     rcx, [rcx+10h]
0x180009b75  mov     edx, 2Fh ; '/'
0x180009b7a  mov     r9d, eax
0x180009b7d  mov     r8, r15
0x180009b80  call    WPP_SF_d
0x180009b85  mov     rcx, qword ptr [rsp+370h+var_318]; hMem
0x180009b8a  call    cs:__imp_LocalFree
0x180009b90  test    ebx, ebx
0x180009b92  jns     short loc_180009BC0
0x180009b94  mov     rcx, cs:WPP_GLOBAL_Control
0x180009b9b  cmp     rcx, rsi
0x180009b9e  jz      short loc_180009BF8
0x180009ba0  test    byte ptr [rcx+1Ch], 4
0x180009ba4  jz      short loc_180009BF8
0x180009ba6  mov     rcx, [rcx+10h]
0x180009baa  mov     edx, 30h ; '0'
0x180009baf  mov     r9d, ebx
0x180009bb2  mov     dword ptr [rsp+370h+lpBuffer], edi
0x180009bb6  mov     r8, r15
0x180009bb9  call    WPP_SF_DD
0x180009bbe  jmp     short loc_180009BF8
0x180009bc0  mov     rdx, qword ptr [rsp+370h+var_328]; lpText
0x180009bc5  cmp     [rsp+370h+var_310], 0
0x180009bca  jz      short loc_180009BE4
0x180009bcc  test    cs:Microsoft_Windows_XWizardsEnableBits, 4
0x180009bd3  jz      short loc_180009BF8
0x180009bd5  mov     r8, qword ptr [rsp+370h+Buffer]
0x180009bda  mov     r9, rdx
0x180009bdd  call    McTemplateU0zz_EventWriteTransfer
0x180009be2  jmp     short loc_180009BF8
0x180009be4  mov     r8, qword ptr [rsp+370h+Buffer]; lpCaption
0x180009be9  mov     r9d, 10h; uType
0x180009bef  mov     rcx, r12; hWnd
0x180009bf2  call    cs:__imp_MessageBoxW
0x180009bf8  mov     rcx, qword ptr [rsp+370h+Buffer]; hMem
0x180009bfd  call    cs:__imp_LocalFree
0x180009c03  mov     rcx, qword ptr [rsp+370h+var_328]; hMem
0x180009c08  call    cs:__imp_LocalFree
0x180009c0e  mov     rcx, r13; hMem
0x180009c11  call    cs:__imp_LocalFree
0x180009c17  mov     rcx, cs:WPP_GLOBAL_Control
0x180009c1e  cmp     rcx, rsi
0x180009c21  jz      short loc_180009C3D
0x180009c23  test    byte ptr [rcx+1Ch], 10h
0x180009c27  jz      short loc_180009C3D
  ... truncated ...
```
