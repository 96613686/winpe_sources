# GetTempPaths(FOLDER_NAME_GENERATOR_ARGS,std::vector<std::pair<DirQueItem,ushort const *>,std::allocator<std::pair<DirQueItem,ushort const *>>> &)

- ea: `0x180021f50`
- end: `0x1800222a0`
- name: `?GetTempPaths@@YAJUFOLDER_NAME_GENERATOR_ARGS@@AEAV?$vector@U?$pair@UDirQueItem@@PEBG@std@@V?$allocator@U?$pair@UDirQueItem@@PEBG@std@@@2@@std@@@Z`
- size: `848`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800050f0`
- `0x180013b48`
- `0x1800204e4`
- `0x180020fa0`
- `0x180021f50`

## string_xrefs

- `0x180021fa3`: `%ALLUSERSPROFILE%\Microsoft\Windows Defender\LocalCopy`
- `0x180021faa`: `DefenderLocalCopy`
- `0x180022000`: `%LOCALAPPDATA%\Microsoft\Windows\Temporary Internet File`
- `0x180022007`: `TempInternetFile`
- `0x1800220c1`: `%SystemDrive%\Windows.old`
- `0x1800220db`: `%TEMP%`
- `0x1800220f5`: `%USERPROFILE%\AppData\Local\D3DSCache`
- `0x1800220fc`: `D3DSCache`
- `0x1800221f9`: `%WINDIR%\ServiceProfiles\NetworkService\AppData\Local\Microsoft\Windows\DeliveryOptimization\Cache`
- `0x180022200`: `DeliveryOptimizationCache`
- `0x180022213`: `%WINDIR%\System32\logfiles`
- `0x18002222d`: `%WINDIR%\Temp`
- `0x180022234`: `WinDirTemp`

## pseudocode

```c
__int64 __fastcall GetTempPaths(__int64 a1, __int64 a2)
{
  __int64 *v3; // rbx
  __int128 v4; // xmm1
  _OWORD v6[2]; // [rsp+20h] [rbp-E0h] BYREF
  _BYTE v7[32]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v8[32]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v9[32]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v10[32]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v11[32]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v12[32]; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v13[32]; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v14[32]; // [rsp+120h] [rbp+20h] BYREF
  _BYTE v15[32]; // [rsp+140h] [rbp+40h] BYREF
  _BYTE v16[32]; // [rsp+160h] [rbp+60h] BYREF
  _BYTE v17[32]; // [rsp+180h] [rbp+80h] BYREF
  _BYTE v18[32]; // [rsp+1A0h] [rbp+A0h] BYREF
  _BYTE v19[32]; // [rsp+1C0h] [rbp+C0h] BYREF
  _BYTE v20[32]; // [rsp+1E0h] [rbp+E0h] BYREF
  _BYTE v21[32]; // [rsp+200h] [rbp+100h] BYREF
  _BYTE v22[32]; // [rsp+220h] [rbp+120h] BYREF
  _BYTE v23[32]; // [rsp+240h] [rbp+140h] BYREF
  _BYTE v24[32]; // [rsp+260h] [rbp+160h] BYREF
  _BYTE v25[32]; // [rsp+280h] [rbp+180h] BYREF
  _BYTE v26[32]; // [rsp+2A0h] [rbp+1A0h] BYREF
  _BYTE v27[32]; // [rsp+2C0h] [rbp+1C0h] BYREF
  _BYTE v28[32]; // [rsp+2E0h] [rbp+1E0h] BYREF
  _BYTE v29[32]; // [rsp+300h] [rbp+200h] BYREF
  _BYTE v30[32]; // [rsp+320h] [rbp+220h] BYREF
  _BYTE v31[32]; // [rsp+340h] [rbp+240h] BYREF
  _BYTE v32[32]; // [rsp+360h] [rbp+260h] BYREF
  _BYTE v33[32]; // [rsp+380h] [rbp+280h] BYREF
  _BYTE v34[32]; // [rsp+3A0h] [rbp+2A0h] BYREF
  __int64 v35; // [rsp+3C0h] [rbp+2C0h] BYREF

  if ( IsContainer() )
  {
    GetTempPaths_::_19_::WCOS_GUEST_TEMP_PATH::WCOS_GUEST_TEMP_PATH(
      v7,
      L"EventTranscript",
      L"%ALLUSERSPROFILE%\\Microsoft\\Diagnosis\\EventTranscript");
    GetTempPaths_::_19_::WCOS_GUEST_TEMP_PATH::WCOS_GUEST_TEMP_PATH(
      v8,
      L"DefenderLocalCopy",
      L"%ALLUSERSPROFILE%\\Microsoft\\Windows Defender\\LocalCopy");
    GetTempPaths_::_19_::WCOS_GUEST_TEMP_PATH::WCOS_GUEST_TEMP_PATH(
      v9,
      L"DefenderSupport",
      L"%ALLUSERSPROFILE%\\Microsoft\\Windows Defender\\Support");
    GetTempPaths_::_19_::WCOS_GUEST_TEMP_PATH::WCOS_GUEST_TEMP_PATH(
      v10,
      L"RetailDemo",
      L"%ALLUSERSPROFILE%\\Microsoft\\Windows\\RetailDemo");
    GetTempPaths_::_19_::WCOS_GUEST_TEMP_PATH::WCOS_GUEST_TEMP_PATH(
      v11,
      L"WER",
      L"%ALLUSERSPROFILE%\\Microsoft\\Windows\\WER");
    GetTempPaths_::_19_::WCOS_GUEST_TEMP_PATH::WCOS_GUEST_TEMP_PATH(
      v12,
      L"TempInternetFile",
      L"%LOCALAPPDATA%\\Microsoft\\Windows\\Temporary Internet File");
    GetTempPaths_::_19_::WCOS_GUEST_TEMP_PATH::WCOS_GUEST_TEMP_PATH(
      v13,
      L"$INPLACE.~TR",
      L"%SystemDrive%\\$INPLACE.~TR");
    GetTempPaths_::_19_::WCOS_GUEST_TEMP_PATH::WCOS_GUEST_TEMP_PATH(
      v14,
      L"$Windows.~BT",
      L"%SystemDrive%\\$Windows.~BT");
    GetTempPaths_::_19_::WCOS_GUEST_TEMP_PATH::WCOS_GUEST_TEMP_PATH(
      v15,
      L"$Windows.~LS",
      L"%SystemDrive%\\$Windows.~LS");
    GetTempPaths_::_19_::WCOS_GUEST_TEMP_PATH::WCOS_GUEST_TEMP_PATH(v16, L"$Windows.~Q", L"%SystemDrive%\\$Windows.~Q");
    GetTempPaths_::_19_::WCOS_GUEST_TEMP_PATH::WCOS_GUEST_TEMP_PATH(
      v17,
      L"$Windows.~WS",
      L"%SystemDrive%\\$Windows.~WS");
    GetTempPaths_::_19_::WCOS_GUEST_TEMP_PATH::WCOS_GUEST_TEMP_PATH(
      v18,
      L"ESDDownload",
      L"%SystemDrive%\\ESD\\Download");
    GetTempPaths_::_19_::WCOS_GUEST_TEMP_PATH::WCOS_GUEST_TEMP_PATH(v19, L"ESDWindows", L"%SystemDrive%\\ESD\\Windows");
    GetTempPaths_::_19_::WCOS_GUEST_TEMP_PATH::WCOS_GUEST_TEMP_PATH(v20, L"WinOld", L"%SystemDrive%\\Windows.old");
    GetTempPaths_::_19_::WCOS_GUEST_TEMP_PATH::WCOS_GUEST_TEMP_PATH(v21, L"TEMP", L"%TEMP%");
    GetTempPaths_::_19_::WCOS_GUEST_TEMP_PATH::WCOS_GUEST_TEMP_PATH(
      v22,
      L"D3DSCache",
      L"%USERPROFILE%\\AppData\\Local\\D3DSCache");
    GetTempPaths_::_19_::WCOS_GUEST_TEMP_PATH::WCOS_GUEST_TEMP_PATH(
      v23,
      L"Explorer",
      L"%USERPROFILE%\\AppData\\Local\\Microsoft\\Windows\\Explorer");
    GetTempPaths_::_19_::WCOS_GUEST_TEMP_PATH::WCOS_GUEST_TEMP_PATH(
      v24,
      L"INetCace",
      L"%USERPROFILE%\\AppData\\Local\\Microsoft\\Windows\\INetCace");
    GetTempPaths_::_19_::WCOS_GUEST_TEMP_PATH::WCOS_GUEST_TEMP_PATH(
      v25,
      L"PeerDistRepub",
      L"%USERPROFILE%\\AppData\\Local\\PeerDistRepub");
    GetTempPaths_::_19_::WCOS_GUEST_TEMP_PATH::WCOS_GUEST_TEMP_PATH(v26, L"Downloads", L"%USERPROFILE%\\Downloads");
    GetTempPaths_::_19_::WCOS_GUEST_TEMP_PATH::WCOS_GUEST_TEMP_PATH(
      v27,
      L"LiveKernelReports",
      L"%WINDIR%\\LiveKernelReports");
    GetTempPaths_::_19_::WCOS_GUEST_TEMP_PATH::WCOS_GUEST_TEMP_PATH(v28, L"WinDirLogs", L"%WINDIR%\\Logs");
    GetTempPaths_::_19_::WCOS_GUEST_TEMP_PATH::WCOS_GUEST_TEMP_PATH(v29, L"Minidump", L"%WINDIR%\\Minidump");
    GetTempPaths_::_19_::WCOS_GUEST_TEMP_PATH::WCOS_GUEST_TEMP_PATH(
      v30,
      L"OfflineWebPages",
      L"%WINDIR%\\Offline Web Pages");
    GetTempPaths_::_19_::WCOS_GUEST_TEMP_PATH::WCOS_GUEST_TEMP_PATH(v31, L"Panther", L"%WINDIR%\\Panther");
    GetTempPaths_::_19_::WCOS_GUEST_TEMP_PATH::WCOS_GUEST_TEMP_PATH(
      v32,
      L"DeliveryOptimizationCache",
      L"%WINDIR%\\ServiceProfiles\\NetworkService\\AppData\\Local\\Microsoft\\Windows\\DeliveryOptimization\\Cache");
    GetTempPaths_::_19_::WCOS_GUEST_TEMP_PATH::WCOS_GUEST_TEMP_PATH(
      v33,
      L"Sys32logfiles",
      L"%WINDIR%\\System32\\logfiles");
    GetTempPaths_::_19_::WCOS_GUEST_TEMP_PATH::WCOS_GUEST_TEMP_PATH(v34, L"WinDirTemp", L"%WINDIR%\\Temp");
    v3 = (__int64 *)v7;
    do
    {
      v4 = *((_OWORD *)v3 + 1);
      v6[0] = *(_OWORD *)v3;
      v6[1] = v4;
      ExpandEnvironmentVarString(v6, a2);
      v3 += 4;
    }
    while ( v3 != &v35 );
  }
  return 0;
}

```

## disassembly

```asm
0x180021f50  mov     [rsp-8+arg_0], rbx
0x180021f55  mov     [rsp-8+arg_10], rdi
0x180021f5a  push    rbp
0x180021f5b  lea     rbp, [rsp-2D0h]
0x180021f63  sub     rsp, 3D0h
0x180021f6a  mov     rax, cs:__security_cookie
0x180021f71  xor     rax, rsp
0x180021f74  mov     [rbp+2D0h+var_10], rax
0x180021f7b  mov     rdi, rdx
0x180021f7e  call    ?IsContainer@@YA_NXZ; IsContainer(void)
0x180021f83  test    al, al
0x180021f85  jz      loc_18002227A
0x180021f8b  lea     r8, aAllusersprofil_3; "%ALLUSERSPROFILE%\\Microsoft\\Diagnosis"...
0x180021f92  lea     rdx, aEventtranscrip; "EventTranscript"
0x180021f99  lea     rcx, [rsp+3D0h+var_390]
0x180021f9e  call    _GetTempPaths____19___WCOS_GUEST_TEMP_PATH__WCOS_GUEST_TEMP_PATH
0x180021fa3  lea     r8, aAllusersprofil_0; "%ALLUSERSPROFILE%\\Microsoft\\Windows D"...
0x180021faa  lea     rdx, aDefenderlocalc; "DefenderLocalCopy"
0x180021fb1  lea     rcx, [rsp+3D0h+var_370]
0x180021fb6  call    _GetTempPaths____19___WCOS_GUEST_TEMP_PATH__WCOS_GUEST_TEMP_PATH
0x180021fbb  lea     r8, aAllusersprofil; "%ALLUSERSPROFILE%\\Microsoft\\Windows D"...
0x180021fc2  lea     rdx, aDefendersuppor; "DefenderSupport"
0x180021fc9  lea     rcx, [rbp+2D0h+var_350]
0x180021fcd  call    _GetTempPaths____19___WCOS_GUEST_TEMP_PATH__WCOS_GUEST_TEMP_PATH
0x180021fd2  lea     r8, aAllusersprofil_2; "%ALLUSERSPROFILE%\\Microsoft\\Windows\\"...
0x180021fd9  lea     rdx, aRetaildemo; "RetailDemo"
0x180021fe0  lea     rcx, [rbp+2D0h+var_330]
0x180021fe4  call    _GetTempPaths____19___WCOS_GUEST_TEMP_PATH__WCOS_GUEST_TEMP_PATH
0x180021fe9  lea     r8, aAllusersprofil_1; "%ALLUSERSPROFILE%\\Microsoft\\Windows\\"...
0x180021ff0  lea     rdx, aWer; "WER"
0x180021ff7  lea     rcx, [rbp+2D0h+var_310]
0x180021ffb  call    _GetTempPaths____19___WCOS_GUEST_TEMP_PATH__WCOS_GUEST_TEMP_PATH
0x180022000  lea     r8, aLocalappdataMi; "%LOCALAPPDATA%\\Microsoft\\Windows\\Tem"...
0x180022007  lea     rdx, aTempinternetfi; "TempInternetFile"
0x18002200e  lea     rcx, [rbp+2D0h+var_2F0]
0x180022012  call    _GetTempPaths____19___WCOS_GUEST_TEMP_PATH__WCOS_GUEST_TEMP_PATH
0x180022017  lea     r8, aSystemdriveInp; "%SystemDrive%\\$INPLACE.~TR"
0x18002201e  lea     rdx, aInplaceTr; "$INPLACE.~TR"
0x180022025  lea     rcx, [rbp+2D0h+var_2D0]
0x180022029  call    _GetTempPaths____19___WCOS_GUEST_TEMP_PATH__WCOS_GUEST_TEMP_PATH
0x18002202e  lea     r8, aSystemdriveWin_2; "%SystemDrive%\\$Windows.~BT"
0x180022035  lea     rdx, aWindowsBt; "$Windows.~BT"
0x18002203c  lea     rcx, [rbp+2D0h+var_2B0]
0x180022040  call    _GetTempPaths____19___WCOS_GUEST_TEMP_PATH__WCOS_GUEST_TEMP_PATH
0x180022045  lea     r8, aSystemdriveWin_5; "%SystemDrive%\\$Windows.~LS"
0x18002204c  lea     rdx, aWindowsLs; "$Windows.~LS"
0x180022053  lea     rcx, [rbp+2D0h+var_290]
0x180022057  call    _GetTempPaths____19___WCOS_GUEST_TEMP_PATH__WCOS_GUEST_TEMP_PATH
0x18002205c  lea     r8, aSystemdriveWin_3; "%SystemDrive%\\$Windows.~Q"
0x180022063  lea     rdx, aWindowsQ; "$Windows.~Q"
0x18002206a  lea     rcx, [rbp+2D0h+var_270]
0x18002206e  call    _GetTempPaths____19___WCOS_GUEST_TEMP_PATH__WCOS_GUEST_TEMP_PATH
0x180022073  lea     r8, aSystemdriveWin_1; "%SystemDrive%\\$Windows.~WS"
0x18002207a  lea     rdx, aWindowsWs; "$Windows.~WS"
0x180022081  lea     rcx, [rbp+2D0h+var_250]
0x180022088  call    _GetTempPaths____19___WCOS_GUEST_TEMP_PATH__WCOS_GUEST_TEMP_PATH
0x18002208d  lea     r8, aSystemdriveEsd_0; "%SystemDrive%\\ESD\\Download"
0x180022094  lea     rdx, aEsddownload; "ESDDownload"
0x18002209b  lea     rcx, [rbp+2D0h+var_230]
0x1800220a2  call    _GetTempPaths____19___WCOS_GUEST_TEMP_PATH__WCOS_GUEST_TEMP_PATH
0x1800220a7  lea     r8, aSystemdriveEsd; "%SystemDrive%\\ESD\\Windows"
0x1800220ae  lea     rdx, aEsdwindows; "ESDWindows"
0x1800220b5  lea     rcx, [rbp+2D0h+var_210]
0x1800220bc  call    _GetTempPaths____19___WCOS_GUEST_TEMP_PATH__WCOS_GUEST_TEMP_PATH
0x1800220c1  lea     r8, aSystemdriveWin_4; "%SystemDrive%\\Windows.old"
0x1800220c8  lea     rdx, aWinold; "WinOld"
0x1800220cf  lea     rcx, [rbp+2D0h+var_1F0]
0x1800220d6  call    _GetTempPaths____19___WCOS_GUEST_TEMP_PATH__WCOS_GUEST_TEMP_PATH
0x1800220db  lea     r8, aTemp_0; "%TEMP%"
0x1800220e2  lea     rdx, aTemp; "TEMP"
0x1800220e9  lea     rcx, [rbp+2D0h+var_1D0]
0x1800220f0  call    _GetTempPaths____19___WCOS_GUEST_TEMP_PATH__WCOS_GUEST_TEMP_PATH
0x1800220f5  lea     r8, aUserprofileApp_0; "%USERPROFILE%\\AppData\\Local\\D3DSCach"...
0x1800220fc  lea     rdx, aD3dscache; "D3DSCache"
0x180022103  lea     rcx, [rbp+2D0h+var_1B0]
0x18002210a  call    _GetTempPaths____19___WCOS_GUEST_TEMP_PATH__WCOS_GUEST_TEMP_PATH
0x18002210f  lea     r8, aUserprofileApp_1; "%USERPROFILE%\\AppData\\Local\\Microsof"...
0x180022116  lea     rdx, aExplorer; "Explorer"
0x18002211d  lea     rcx, [rbp+2D0h+var_190]
0x180022124  call    _GetTempPaths____19___WCOS_GUEST_TEMP_PATH__WCOS_GUEST_TEMP_PATH
0x180022129  lea     r8, aUserprofileApp; "%USERPROFILE%\\AppData\\Local\\Microsof"...
0x180022130  lea     rdx, aInetcace; "INetCace"
0x180022137  lea     rcx, [rbp+2D0h+var_170]
0x18002213e  call    _GetTempPaths____19___WCOS_GUEST_TEMP_PATH__WCOS_GUEST_TEMP_PATH
0x180022143  lea     r8, aUserprofileApp_2; "%USERPROFILE%\\AppData\\Local\\PeerDist"...
0x18002214a  lea     rdx, aPeerdistrepub; "PeerDistRepub"
0x180022151  lea     rcx, [rbp+2D0h+var_150]
0x180022158  call    _GetTempPaths____19___WCOS_GUEST_TEMP_PATH__WCOS_GUEST_TEMP_PATH
0x18002215d  lea     r8, aUserprofileDow; "%USERPROFILE%\\Downloads"
0x180022164  lea     rdx, aDownloads; "Downloads"
0x18002216b  lea     rcx, [rbp+2D0h+var_130]
0x180022172  call    _GetTempPaths____19___WCOS_GUEST_TEMP_PATH__WCOS_GUEST_TEMP_PATH
0x180022177  lea     r8, aWindirLivekern; "%WINDIR%\\LiveKernelReports"
0x18002217e  lea     rdx, aLivekernelrepo; "LiveKernelReports"
0x180022185  lea     rcx, [rbp+2D0h+var_110]
0x18002218c  call    _GetTempPaths____19___WCOS_GUEST_TEMP_PATH__WCOS_GUEST_TEMP_PATH
0x180022191  lea     r8, aWindirLogs; "%WINDIR%\\Logs"
0x180022198  lea     rdx, aWindirlogs; "WinDirLogs"
0x18002219f  lea     rcx, [rbp+2D0h+var_F0]
0x1800221a6  call    _GetTempPaths____19___WCOS_GUEST_TEMP_PATH__WCOS_GUEST_TEMP_PATH
0x1800221ab  lea     r8, aWindirMinidump; "%WINDIR%\\Minidump"
0x1800221b2  lea     rdx, aMinidump; "Minidump"
0x1800221b9  lea     rcx, [rbp+2D0h+var_D0]
0x1800221c0  call    _GetTempPaths____19___WCOS_GUEST_TEMP_PATH__WCOS_GUEST_TEMP_PATH
0x1800221c5  lea     r8, aWindirOfflineW; "%WINDIR%\\Offline Web Pages"
0x1800221cc  lea     rdx, aOfflinewebpage; "OfflineWebPages"
0x1800221d3  lea     rcx, [rbp+2D0h+var_B0]
0x1800221da  call    _GetTempPaths____19___WCOS_GUEST_TEMP_PATH__WCOS_GUEST_TEMP_PATH
0x1800221df  lea     r8, aWindirPanther; "%WINDIR%\\Panther"
0x1800221e6  lea     rdx, aPanther; "Panther"
0x1800221ed  lea     rcx, [rbp+2D0h+var_90]
0x1800221f4  call    _GetTempPaths____19___WCOS_GUEST_TEMP_PATH__WCOS_GUEST_TEMP_PATH
0x1800221f9  lea     r8, aWindirServicep; "%WINDIR%\\ServiceProfiles\\NetworkServi"...
0x180022200  lea     rdx, aDeliveryoptimi; "DeliveryOptimizationCache"
0x180022207  lea     rcx, [rbp+2D0h+var_70]
0x18002220e  call    _GetTempPaths____19___WCOS_GUEST_TEMP_PATH__WCOS_GUEST_TEMP_PATH
0x180022213  lea     r8, aWindirSystem32; "%WINDIR%\\System32\\logfiles"
0x18002221a  lea     rdx, aSys32logfiles; "Sys32logfiles"
0x180022221  lea     rcx, [rbp+2D0h+var_50]
0x180022228  call    _GetTempPaths____19___WCOS_GUEST_TEMP_PATH__WCOS_GUEST_TEMP_PATH
0x18002222d  lea     r8, aWindirTemp; "%WINDIR%\\Temp"
0x180022234  lea     rdx, aWindirtemp; "WinDirTemp"
0x18002223b  lea     rcx, [rbp+2D0h+var_30]
0x180022242  call    _GetTempPaths____19___WCOS_GUEST_TEMP_PATH__WCOS_GUEST_TEMP_PATH
0x180022247  lea     rbx, [rsp+3D0h+var_390]
0x18002224c  movups  xmm0, xmmword ptr [rbx]
0x18002224f  mov     rdx, rdi
0x180022252  lea     rcx, [rsp+3D0h+var_3B0]
0x180022257  movups  xmm1, xmmword ptr [rbx+10h]
0x18002225b  movaps  [rsp+3D0h+var_3B0], xmm0
0x180022260  movaps  [rsp+3D0h+var_3A0], xmm1
0x180022265  call    ?ExpandEnvironmentVarString@@YAJUFOLDER_NAME_GENERATOR_ARGS@@AEAV?$vector@U?$pair@UDirQueItem@@PEBG@std@@V?$allocator@U?$pair@UDirQueItem@@PEBG@std@@@2@@std@@@Z; ExpandEnvironmentVarString(FOLDER_NAME_GENERATOR_ARGS,std::vector<std::pair<DirQueItem,ushort const *>> &)
0x18002226a  lea     rax, [rbp+2D0h+var_10]
0x180022271  add     rbx, 20h ; ' '
0x180022275  cmp     rbx, rax
0x180022278  jnz     short loc_18002224C
0x18002227a  xor     eax, eax
0x18002227c  mov     rcx, [rbp+2D0h+var_10]
0x180022283  xor     rcx, rsp; StackCookie
0x180022286  call    __security_check_cookie
0x18002228b  lea     r11, [rsp+3D0h+var_s0]
0x180022293  mov     rbx, [r11+10h]
0x180022297  mov     rdi, [r11+20h]
0x18002229b  mov     rsp, r11
0x18002229e  pop     rbp
0x18002229f  retn
```
