# DllRegisterServer

- ea: `0x180003080`
- end: `0x1800035a4`
- name: `DllRegisterServer`
- size: `1316`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180002fe8`
- `0x180003080`
- `0x18000932c`
- `0x180009418`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800034df`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800034f5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003567`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800034df`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800034f5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003567`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800034a4`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800034d5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800034a4`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800034d5`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180003477`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180003477`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800034b3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800034b3`

## string_xrefs

- `0x1800030cd`: `CLSID\{84e04a55-2d42-4909-86e3-62fd11483e8b}`
- `0x1800030f5`: `Temporary Setup Files Cleanup`
- `0x1800030ba`: `CLSID\{84e04a55-2d42-4909-86e3-62fd11483e8b}\InProcServer32`
- `0x18000310c`: `%systemroot%\system32\setupcln.dll`
- `0x180003122`: `ThreadingModel`
- `0x1800030e1`: `Software\Microsoft\Windows\CurrentVersion\Explorer\VolumeCaches\Temporary Setup Files`
- `0x18000311b`: `IconPath`
- `0x180003131`: `%systemroot%\system32\setupcln.dll,0`
- `0x18000314e`: `@%systemroot%\system32\setupcln.dll,-1000`
- `0x180003164`: `@%systemroot%\system32\setupcln.dll,-1001`
- `0x180003197`: `RemoveUninstall`
- `0x180003176`: `Software\Microsoft\Windows\CurrentVersion\Explorer\VolumeCaches\Previous Installations`
- `0x18000326f`: `@%systemroot%\system32\setupcln.dll,-1002`
- `0x180003284`: `@%systemroot%\system32\setupcln.dll,-1003`
- `0x1800032d1`: `Software\Microsoft\Windows\CurrentVersion\Explorer\VolumeCaches\Upgrade Discarded Files`
- `0x1800032a0`: `@%systemroot%\system32\setupcln.dll,-1004`
- `0x1800032ae`: `@%systemroot%\system32\setupcln.dll,-1005`

## pseudocode

```c
HRESULT __stdcall DllRegisterServer()
{
  HRESULT result; // eax
  unsigned __int64 v1; // rdi
  HKEY v2; // rax
  const WCHAR *v3; // rdx
  const WCHAR *v4; // rsi
  LSTATUS v5; // ebx
  _BOOL8 v6; // rcx
  int v7; // eax
  __int64 v8; // r10
  __int64 v9; // rdx
  __int64 v10; // rax
  HKEY hKey; // [rsp+50h] [rbp-B0h]
  LPCWSTR lpSubKey; // [rsp+58h] [rbp-A8h]
  LPCWSTR lpValueName; // [rsp+60h] [rbp-A0h]
  __int64 v14; // [rsp+68h] [rbp-98h]
  _QWORD v15[39]; // [rsp+70h] [rbp-90h]
  int v16; // [rsp+1A8h] [rbp+A8h]
  int v17; // [rsp+1ACh] [rbp+ACh]
  __m128i si128; // [rsp+1B0h] [rbp+B0h]
  const wchar_t *v19; // [rsp+1C0h] [rbp+C0h]
  const wchar_t *v20; // [rsp+1C8h] [rbp+C8h]
  __int64 v21; // [rsp+1D0h] [rbp+D0h]
  const wchar_t *v22; // [rsp+1D8h] [rbp+D8h]
  __int64 v23; // [rsp+1E0h] [rbp+E0h]
  const wchar_t *v24; // [rsp+1E8h] [rbp+E8h]
  const wchar_t *v25; // [rsp+1F0h] [rbp+F0h]
  __int64 v26; // [rsp+1F8h] [rbp+F8h]
  const wchar_t *v27; // [rsp+200h] [rbp+100h]
  __int64 v28; // [rsp+208h] [rbp+108h]
  const wchar_t *v29; // [rsp+210h] [rbp+110h]
  const wchar_t *v30; // [rsp+218h] [rbp+118h]
  __int64 v31; // [rsp+220h] [rbp+120h]
  const wchar_t *v32; // [rsp+228h] [rbp+128h]
  __int64 v33; // [rsp+230h] [rbp+130h]
  const wchar_t *v34; // [rsp+238h] [rbp+138h]
  const wchar_t *v35; // [rsp+240h] [rbp+140h]
  __int64 v36; // [rsp+248h] [rbp+148h]
  const wchar_t *v37; // [rsp+250h] [rbp+150h]
  __int64 v38; // [rsp+258h] [rbp+158h]
  const wchar_t *v39; // [rsp+260h] [rbp+160h]
  const wchar_t *v40; // [rsp+268h] [rbp+168h]
  int v41; // [rsp+270h] [rbp+170h]
  int v42; // [rsp+274h] [rbp+174h]
  __int64 v43; // [rsp+278h] [rbp+178h]
  __int64 v44; // [rsp+280h] [rbp+180h]
  const wchar_t *v45; // [rsp+288h] [rbp+188h]
  const wchar_t *v46; // [rsp+290h] [rbp+190h]
  __int64 v47; // [rsp+298h] [rbp+198h]
  const wchar_t *v48; // [rsp+2A0h] [rbp+1A0h]
  __int64 v49; // [rsp+2A8h] [rbp+1A8h]
  const wchar_t *v50; // [rsp+2B0h] [rbp+1B0h]
  const wchar_t *v51; // [rsp+2B8h] [rbp+1B8h]
  __int64 v52; // [rsp+2C0h] [rbp+1C0h]
  const wchar_t *v53; // [rsp+2C8h] [rbp+1C8h]
  __int64 v54; // [rsp+2D0h] [rbp+1D0h]
  const wchar_t *v55; // [rsp+2D8h] [rbp+1D8h]
  const wchar_t *v56; // [rsp+2E0h] [rbp+1E0h]
  __int64 v57; // [rsp+2E8h] [rbp+1E8h]
  const wchar_t *v58; // [rsp+2F0h] [rbp+1F0h]
  __int64 v59; // [rsp+2F8h] [rbp+1F8h]
  const wchar_t *v60; // [rsp+300h] [rbp+200h]
  const wchar_t *v61; // [rsp+308h] [rbp+208h]
  __int64 v62; // [rsp+310h] [rbp+210h]
  const wchar_t *v63; // [rsp+318h] [rbp+218h]
  __int64 v64; // [rsp+320h] [rbp+220h]
  const wchar_t *v65; // [rsp+328h] [rbp+228h]
  const wchar_t *v66; // [rsp+330h] [rbp+230h]
  __int64 v67; // [rsp+338h] [rbp+238h]
  const wchar_t *v68; // [rsp+340h] [rbp+240h]
  int Data; // [rsp+390h] [rbp+290h] BYREF
  DWORD dwDisposition; // [rsp+398h] [rbp+298h] BYREF
  HKEY phkResult; // [rsp+3A0h] [rbp+2A0h] BYREF

  lpValueName = &dword_180017A6C;
  hKey = HKEY_CLASSES_ROOT;
  v15[2] = L"CLSID\\{84e04a55-2d42-4909-86e3-62fd11483e8b}\\InProcServer32";
  v15[7] = L"CLSID\\{84e04a55-2d42-4909-86e3-62fd11483e8b}\\InProcServer32";
  lpSubKey = L"CLSID\\{84e04a55-2d42-4909-86e3-62fd11483e8b}";
  v15[1] = 0xFFFFFFFF80000000uLL;
  v15[6] = 0xFFFFFFFF80000000uLL;
  v15[12] = L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\VolumeCaches\\Temporary Setup Files";
  v15[0] = L"Temporary Setup Files Cleanup";
  v15[17] = L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\VolumeCaches\\Temporary Setup Files";
  v15[5] = L"%systemroot%\\system32\\setupcln.dll";
  v15[22] = L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\VolumeCaches\\Temporary Setup Files";
  v15[8] = L"ThreadingModel";
  v15[27] = L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\VolumeCaches\\Temporary Setup Files";
  v15[10] = L"Apartment";
  v15[32] = L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\VolumeCaches\\Temporary Setup Files";
  v15[25] = L"@%systemroot%\\system32\\setupcln.dll,-1000";
  v15[37] = L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\VolumeCaches\\Temporary Setup Files";
  v15[30] = L"@%systemroot%\\system32\\setupcln.dll,-1001";
  v14 = 1;
  v15[35] = L"$WINDOWS.~BT;$WINDOWS.~LS";
  v15[3] = &dword_180017A6C;
  v15[38] = L"RemoveUninstall";
  result = 0;
  v15[4] = 2;
  v15[9] = 1;
  v15[11] = -2147483646;
  v15[13] = &dword_180017A6C;
  v15[14] = 1;
  v15[15] = L"{84e04a55-2d42-4909-86e3-62fd11483e8b}";
  v15[16] = -2147483646;
  v15[18] = L"IconPath";
  v15[19] = 2;
  v15[20] = L"%systemroot%\\system32\\setupcln.dll,0";
  v15[21] = -2147483646;
  v15[23] = L"Display";
  v15[24] = 2;
  v15[26] = -2147483646;
  v15[28] = L"Description";
  v15[29] = 2;
  v15[31] = -2147483646;
  v15[33] = L"SetupDirectories";
  v15[34] = 1;
  v15[36] = -2147483646;
  v16 = 4;
  v17 = 1;
  si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffff800000020000000000000000);
  v19 = L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\VolumeCaches\\Previous Installations";
  v20 = &dword_180017A6C;
  v21 = 1;
  v22 = L"{84e04a55-2d42-4909-86e3-62fd11483e8b}";
  v23 = -2147483646;
  v24 = L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\VolumeCaches\\Previous Installations";
  v25 = L"IconPath";
  v26 = 2;
  v27 = L"%systemroot%\\system32\\setupcln.dll,0";
  v29 = L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\VolumeCaches\\Previous Installations";
  v32 = L"@%systemroot%\\system32\\setupcln.dll,-1002";
  v37 = L"@%systemroot%\\system32\\setupcln.dll,-1003";
  v40 = L"SetupPrevInst";
  v58 = L"@%systemroot%\\system32\\setupcln.dll,-1004";
  v63 = L"@%systemroot%\\system32\\setupcln.dll,-1005";
  v34 = L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\VolumeCaches\\Previous Installations";
  v39 = L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\VolumeCaches\\Previous Installations";
  v28 = -2147483646;
  v33 = -2147483646;
  v38 = -2147483646;
  v44 = -2147483646;
  v48 = L"{84e04a55-2d42-4909-86e3-62fd11483e8b}";
  v1 = 0;
  v49 = -2147483646;
  v54 = -2147483646;
  v59 = -2147483646;
  v64 = -2147483646;
  v68 = L"$WINDOWS.~Q;$INPLACE.~TR";
  v30 = L"Display";
  v31 = 2;
  v35 = L"Description";
  v36 = 2;
  v41 = 4;
  v42 = 1;
  v43 = 0;
  v45 = L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\VolumeCaches\\Upgrade Discarded Files";
  v46 = &dword_180017A6C;
  v47 = 1;
  v50 = L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\VolumeCaches\\Upgrade Discarded Files";
  v51 = L"IconPath";
  v52 = 2;
  v53 = L"%systemroot%\\system32\\setupcln.dll,0";
  v55 = L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\VolumeCaches\\Upgrade Discarded Files";
  v56 = L"Display";
  v57 = 2;
  v60 = L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\VolumeCaches\\Upgrade Discarded Files";
  v61 = L"Description";
  v62 = 2;
  v65 = L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\VolumeCaches\\Upgrade Discarded Files";
  v66 = L"SetupDirectories";
  v67 = 1;
  while ( v1 < 0x13 )
  {
    if ( LODWORD(v15[5 * v1 - 1]) == 1 )
    {
      v8 = (__int64)*(&hKey + 5 * v1);
      if ( v8 && (v9 = v15[5 * v1]) != 0 )
      {
        v10 = -1;
        do
          ++v10;
        while ( *(_WORD *)(v9 + 2 * v10) );
        v7 = RegSetBinEx(v8, (&lpSubKey)[5 * v1], (&lpValueName)[5 * v1], 1, v9, 2 * (int)v10 + 2);
      }
      else
      {
        SetLastError(0x57u);
        v7 = 0;
      }
      goto LABEL_20;
    }
    if ( LODWORD(v15[5 * v1 - 1]) == 2 )
    {
      v7 = RegSetExpand(*(&hKey + 5 * v1), (&lpSubKey)[5 * v1], (&lpValueName)[5 * v1], v15[5 * v1]);
LABEL_20:
      LODWORD(v6) = v7;
      goto LABEL_21;
    }
    if ( LODWORD(v15[5 * v1 - 1]) != 4 )
      return -2147024809;
    Data = *((_DWORD *)&v14 + 10 * v1 + 1);
    v2 = *(&hKey + 5 * v1);
    if ( v2 )
    {
      v3 = (&lpSubKey)[5 * v1];
      v4 = (&lpValueName)[5 * v1];
      if ( v3 )
      {
        phkResult = 0;
        dwDisposition = 0;
        v5 = RegCreateKeyExW(v2, v3, 0, (LPWSTR)&Class, 0, 0x20006u, 0, &phkResult, &dwDisposition);
        if ( !v5 )
        {
          v5 = RegSetValueExW(phkResult, v4, 0, 4u, (const BYTE *)&Data, 4u);
          RegCloseKey(phkResult);
        }
      }
      else
      {
        v5 = RegSetValueExW(v2, v4, 0, 4u, (const BYTE *)&Data, 4u);
      }
      SetLastError(v5);
      v6 = v5 == 0;
    }
    else
    {
      SetLastError(0x57u);
      LODWORD(v6) = 0;
    }
LABEL_21:
    result = HrBool(v6);
    ++v1;
    if ( result < 0 )
      return result;
  }
  return result;
}

```

## disassembly

```asm
0x180003080  mov     [rsp-8+arg_18], rbx
0x180003085  push    rbp
0x180003086  push    rsi
0x180003087  push    rdi
0x180003088  push    r12
0x18000308a  push    r13
0x18000308c  push    r14
0x18000308e  push    r15
0x180003090  lea     rbp, [rsp-250h]
0x180003098  sub     rsp, 350h
0x18000309f  movdqa  xmm0, cs:__xmm@ffffffff800000020000000000000000
0x1800030a7  lea     rsi, dword_180017A6C
0x1800030ae  mov     r8, 0FFFFFFFF80000000h
0x1800030b5  mov     [rsp+380h+lpValueName], rsi
0x1800030ba  lea     rdx, aClsid84e04a552; "CLSID\\{84e04a55-2d42-4909-86e3-62fd114"...
0x1800030c1  mov     [rsp+380h+hKey], r8
0x1800030c6  xor     r15d, r15d
0x1800030c9  mov     [rbp+280h+var_300], rdx
0x1800030cd  lea     rcx, aClsid84e04a552_0; "CLSID\\{84e04a55-2d42-4909-86e3-62fd114"...
0x1800030d4  mov     [rbp+280h+var_2D8], rdx
0x1800030d8  mov     [rsp+380h+lpSubKey], rcx
0x1800030dd  lea     r14, [r8+2]
0x1800030e1  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800030e8  mov     [rsp+380h+var_308], r8
0x1800030ed  lea     r13d, [r15+1]
0x1800030f1  mov     [rbp+280h+var_2E0], r8
0x1800030f5  lea     rcx, aTemporarySetup; "Temporary Setup Files Cleanup"
0x1800030fc  mov     [rbp+280h+var_2B0], rdx
0x180003100  mov     [rsp+380h+var_310], rcx
0x180003105  lea     rdi, a84e04a552d4249; "{84e04a55-2d42-4909-86e3-62fd11483e8b}"
0x18000310c  lea     rcx, aSystemrootSyst_6; "%systemroot%\\system32\\setupcln.dll"
0x180003113  mov     [rbp+280h+var_288], rdx
0x180003117  mov     [rbp+280h+var_2E8], rcx
0x18000311b  lea     rbx, aIconpath; "IconPath"
0x180003122  lea     rcx, aThreadingmodel; "ThreadingModel"
0x180003129  mov     [rbp+280h+var_260], rdx
0x18000312d  mov     [rbp+280h+var_2D0], rcx
0x180003131  lea     r11, aSystemrootSyst_1; "%systemroot%\\system32\\setupcln.dll,0"
0x180003138  lea     rcx, aApartment; "Apartment"
0x18000313f  mov     [rbp+280h+var_238], rdx
0x180003143  mov     [rbp+280h+var_2C0], rcx
0x180003147  lea     r10, aDisplay; "Display"
0x18000314e  lea     rcx, aSystemrootSyst_7; "@%systemroot%\\system32\\setupcln.dll,-"...
0x180003155  mov     [rbp+280h+var_210], rdx
0x180003159  mov     [rbp+280h+var_248], rcx
0x18000315d  lea     r9, aDescription; "Description"
0x180003164  lea     rcx, aSystemrootSyst_2; "@%systemroot%\\system32\\setupcln.dll,-"...
0x18000316b  mov     [rbp+280h+var_1E8], rdx
0x180003172  mov     [rbp+280h+var_220], rcx
0x180003176  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18000317d  lea     rcx, aWindowsBtWindo; "$WINDOWS.~BT;$WINDOWS.~LS"
0x180003184  mov     [rsp+380h+var_318], r13
0x180003189  mov     [rbp+280h+var_1F8], rcx
0x180003190  lea     r8, aSetupdirectori; "SetupDirectories"
0x180003197  lea     rcx, aRemoveuninstal; "RemoveUninstall"
0x18000319e  mov     [rbp+280h+var_2F8], rsi
0x1800031a2  lea     r12d, [r15+4]
0x1800031a6  mov     [rbp+280h+var_1E0], rcx
0x1800031ad  mov     eax, r15d
0x1800031b0  mov     [rbp+280h+var_2F0], 2
0x1800031b8  mov     [rbp+280h+var_2C8], r13
0x1800031bc  mov     [rbp+280h+var_2B8], r14
0x1800031c0  mov     [rbp+280h+var_2A8], rsi
0x1800031c4  mov     [rbp+280h+var_2A0], r13
0x1800031c8  mov     [rbp+280h+var_298], rdi
0x1800031cc  mov     [rbp+280h+var_290], r14
0x1800031d0  mov     [rbp+280h+var_280], rbx
0x1800031d4  mov     [rbp+280h+var_278], 2
0x1800031dc  mov     [rbp+280h+var_270], r11
0x1800031e0  mov     [rbp+280h+var_268], r14
0x1800031e4  mov     [rbp+280h+var_258], r10
0x1800031e8  mov     [rbp+280h+var_250], 2
0x1800031f0  mov     [rbp+280h+var_240], r14
0x1800031f4  mov     [rbp+280h+var_230], r9
0x1800031f8  mov     [rbp+280h+var_228], 2
0x180003200  mov     [rbp+280h+var_218], r14
0x180003204  mov     [rbp+280h+var_208], r8
0x180003208  mov     [rbp+280h+var_200], r13
0x18000320f  mov     [rbp+280h+var_1F0], r14
0x180003216  mov     [rbp+280h+var_1D8], r12d
0x18000321d  mov     [rbp+280h+var_1D4], r13d
0x180003224  movdqa  [rbp+280h+var_1D0], xmm0
0x18000322c  mov     [rbp+280h+var_1C0], rdx
0x180003233  mov     [rbp+280h+var_1B8], rsi
0x18000323a  mov     [rbp+280h+var_1B0], r13
0x180003241  mov     [rbp+280h+var_1A8], rdi
0x180003248  mov     [rbp+280h+var_1A0], r14
0x18000324f  mov     [rbp+280h+var_198], rdx
0x180003256  mov     [rbp+280h+var_190], rbx
0x18000325d  mov     [rbp+280h+var_188], 2
0x180003268  mov     [rbp+280h+var_180], r11
0x18000326f  lea     rcx, aSystemrootSyst_0; "@%systemroot%\\system32\\setupcln.dll,-"...
0x180003276  mov     [rbp+280h+var_170], rdx
0x18000327d  mov     [rbp+280h+var_158], rcx
0x180003284  lea     rcx, aSystemrootSyst_5; "@%systemroot%\\system32\\setupcln.dll,-"...
0x18000328b  mov     [rbp+280h+var_130], rcx
0x180003292  lea     rcx, aSetupprevinst; "SetupPrevInst"
0x180003299  mov     [rbp+280h+var_118], rcx
0x1800032a0  lea     rcx, aSystemrootSyst; "@%systemroot%\\system32\\setupcln.dll,-"...
0x1800032a7  mov     [rbp+280h+var_90], rcx
0x1800032ae  lea     rcx, aSystemrootSyst_3; "@%systemroot%\\system32\\setupcln.dll,-"...
0x1800032b5  mov     [rbp+280h+var_68], rcx
0x1800032bc  lea     rcx, aWindowsQInplac; "$WINDOWS.~Q;$INPLACE.~TR"
0x1800032c3  mov     [rbp+280h+var_148], rdx
0x1800032ca  mov     [rbp+280h+var_120], rdx
0x1800032d1  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800032d8  mov     [rbp+280h+var_178], r14
0x1800032df  mov     [rbp+280h+var_150], r14
0x1800032e6  mov     [rbp+280h+var_128], r14
0x1800032ed  mov     [rbp+280h+var_100], r14
0x1800032f4  mov     [rbp+280h+var_E0], rdi
0x1800032fb  mov     edi, r15d
0x1800032fe  mov     [rbp+280h+var_D8], r14
0x180003305  mov     [rbp+280h+var_B0], r14
0x18000330c  mov     [rbp+280h+var_88], r14
0x180003313  mov     [rbp+280h+var_60], r14
0x18000331a  lea     r14d, [r15+57h]
0x18000331e  mov     [rbp+280h+var_40], rcx
0x180003325  mov     [rbp+280h+var_168], r10
0x18000332c  mov     [rbp+280h+var_160], 2
0x180003337  mov     [rbp+280h+var_140], r9
0x18000333e  mov     [rbp+280h+var_138], 2
0x180003349  mov     [rbp+280h+var_110], r12d
0x180003350  mov     [rbp+280h+var_10C], r13d
0x180003357  mov     [rbp+280h+var_108], r15
0x18000335e  mov     [rbp+280h+var_F8], rdx
0x180003365  mov     [rbp+280h+var_F0], rsi
0x18000336c  mov     [rbp+280h+var_E8], r13
0x180003373  mov     [rbp+280h+var_D0], rdx
0x18000337a  mov     [rbp+280h+var_C8], rbx
0x180003381  mov     [rbp+280h+var_C0], 2
0x18000338c  mov     [rbp+280h+var_B8], r11
0x180003393  mov     [rbp+280h+var_A8], rdx
0x18000339a  mov     [rbp+280h+var_A0], r10
0x1800033a1  mov     [rbp+280h+var_98], 2
0x1800033ac  mov     [rbp+280h+var_80], rdx
0x1800033b3  mov     [rbp+280h+var_78], r9
0x1800033ba  mov     [rbp+280h+var_70], 2
0x1800033c5  mov     [rbp+280h+var_58], rdx
0x1800033cc  mov     [rbp+280h+var_50], r8
0x1800033d3  mov     [rbp+280h+var_48], r13
0x1800033da  cmp     rdi, 13h
0x1800033de  jnb     loc_180003589
0x1800033e4  lea     rcx, [rdi+rdi*4]
0x1800033e8  mov     edx, dword ptr [rsp+rcx*8+380h+var_318]
0x1800033ec  sub     edx, r13d
0x1800033ef  jz      loc_18000351B
0x1800033f5  sub     edx, r13d
0x1800033f8  jz      loc_180003500
0x1800033fe  cmp     edx, 2
0x180003401  jnz     loc_180003584
0x180003407  mov     eax, dword ptr [rsp+rcx*8+380h+var_318+4]
0x18000340b  mov     [rbp+280h+Data], eax
0x180003411  mov     rax, [rsp+rcx*8+380h+hKey]
0x180003416  test    rax, rax
0x180003419  jz      loc_1800034F2
0x18000341f  mov     rdx, [rsp+rcx*8+380h+lpSubKey]; lpSubKey
0x180003424  xor     r8d, r8d; Reserved
0x180003427  mov     rsi, [rsp+rcx*8+380h+lpValueName]
0x18000342c  test    rdx, rdx
0x18000342f  jz      loc_1800034BB
0x180003435  lea     rcx, [rbp+280h+dwDisposition]
0x18000343c  mov     [rbp+280h+arg_10], r15
0x180003443  mov     [rsp+380h+lpdwDisposition], rcx; lpdwDisposition
0x180003448  lea     r9, Class; lpClass
0x18000344f  lea     rcx, [rbp+280h+arg_10]
0x180003456  mov     [rbp+280h+dwDisposition], r15d
0x18000345d  mov     [rsp+380h+phkResult], rcx; phkResult
0x180003462  mov     rcx, rax; hKey
0x180003465  mov     [rsp+380h+lpSecurityAttributes], r15; lpSecurityAttributes
0x18000346a  mov     [rsp+380h+samDesired], 20006h; samDesired
0x180003472  mov     [rsp+380h+dwOptions], r15d; dwOptions
0x180003477  call    cs:__imp_RegCreateKeyExW
0x18000347d  mov     ebx, eax
0x18000347f  test    eax, eax
0x180003481  jnz     short loc_1800034DD
0x180003483  mov     rcx, [rbp+280h+arg_10]; hKey
0x18000348a  lea     rax, [rbp+280h+Data]
0x180003491  mov     [rsp+380h+samDesired], r12d; cbData
0x180003496  mov     r9d, r12d; dwType
0x180003499  xor     r8d, r8d; Reserved
0x18000349c  mov     qword ptr [rsp+380h+dwOptions], rax; lpData
0x1800034a1  mov     rdx, rsi; lpValueName
0x1800034a4  call    cs:__imp_RegSetValueExW
0x1800034aa  mov     rcx, [rbp+280h+arg_10]; hKey
0x1800034b1  mov     ebx, eax
0x1800034b3  call    cs:__imp_RegCloseKey
0x1800034b9  jmp     short loc_1800034DD
0x1800034bb  lea     rcx, [rbp+280h+Data]
0x1800034c2  mov     [rsp+380h+samDesired], r12d; cbData
0x1800034c7  mov     qword ptr [rsp+380h+dwOptions], rcx; lpData
0x1800034cc  mov     r9d, r12d; dwType
0x1800034cf  mov     rcx, rax; hKey
0x1800034d2  mov     rdx, rsi; lpValueName
0x1800034d5  call    cs:__imp_RegSetValueExW
0x1800034db  mov     ebx, eax
0x1800034dd  mov     ecx, ebx; dwErrCode
0x1800034df  call    cs:__imp_SetLastError
0x1800034e5  test    ebx, ebx
0x1800034e7  mov     ecx, r15d
0x1800034ea  setz    cl
0x1800034ed  jmp     loc_180003572
0x1800034f2  mov     ecx, r14d; dwErrCode
0x1800034f5  call    cs:__imp_SetLastError
0x1800034fb  mov     ecx, r15d
0x1800034fe  jmp     short loc_180003572
0x180003500  mov     r9, [rsp+rcx*8+380h+var_310]
0x180003505  mov     r8, [rsp+rcx*8+380h+lpValueName]
0x18000350a  mov     rdx, [rsp+rcx*8+380h+lpSubKey]
0x18000350f  mov     rcx, [rsp+rcx*8+380h+hKey]
0x180003514  call    RegSetExpand
0x180003519  jmp     short loc_180003570
0x18000351b  mov     r10, [rsp+rcx*8+380h+hKey]
0x180003520  test    r10, r10
0x180003523  jz      short loc_180003564
0x180003525  mov     rdx, [rsp+rcx*8+380h+var_310]
0x18000352a  test    rdx, rdx
0x18000352d  jz      short loc_180003564
0x18000352f  or      rax, 0FFFFFFFFFFFFFFFFh
0x180003533  inc     rax
0x180003536  cmp     [rdx+rax*2], r15w
0x18000353b  jnz     short loc_180003533
0x18000353d  mov     r8, [rsp+rcx*8+380h+lpValueName]
0x180003542  lea     eax, ds:2[rax*2]
0x180003549  mov     [rsp+380h+samDesired], eax
0x18000354d  mov     r9d, r13d
0x180003550  mov     qword ptr [rsp+380h+dwOptions], rdx
0x180003555  mov     rdx, [rsp+rcx*8+380h+lpSubKey]
0x18000355a  mov     rcx, r10
0x18000355d  call    RegSetBinEx
0x180003562  jmp     short loc_180003570
0x180003564  mov     ecx, r14d; dwErrCode
0x180003567  call    cs:__imp_SetLastError
0x18000356d  mov     eax, r15d
0x180003570  mov     ecx, eax; int
0x180003572  call    ?HrBool@@YAJH@Z; HrBool(int)
0x180003577  add     rdi, r13
0x18000357a  test    eax, eax
0x18000357c  jns     loc_1800033DA
0x180003582  jmp     short loc_180003589
0x180003584  mov     eax, 80070057h
0x180003589  mov     rbx, [rsp+380h+arg_18]
0x180003591  add     rsp, 350h
0x180003598  pop     r15
0x18000359a  pop     r14
0x18000359c  pop     r13
0x18000359e  pop     r12
0x1800035a0  pop     rdi
0x1800035a1  pop     rsi
0x1800035a2  pop     rbp
0x1800035a3  retn
```
