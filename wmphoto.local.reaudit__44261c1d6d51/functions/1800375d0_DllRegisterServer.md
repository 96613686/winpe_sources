# DllRegisterServer

- ea: `0x1800375d0`
- end: `0x18003831b`
- name: `DllRegisterServer`
- size: `3403`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x180036420`
- `0x180037174`
- `0x1800372c8`
- `0x180037414`
- `0x1800374ec`
- `0x180037544`
- `0x1800375d0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180037784`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180037784`
- `api-ms-win-core-com-l1-1-0!StringFromIID` at `0x1800376bd`
- `api-ms-win-core-com-l1-1-0!StringFromIID` at `0x1800376fc`
- `api-ms-win-core-com-l1-1-0!StringFromIID` at `0x18003773b`
- `api-ms-win-core-com-l1-1-0!StringFromIID` at `0x1800376bd`
- `api-ms-win-core-com-l1-1-0!StringFromIID` at `0x1800376fc`
- `api-ms-win-core-com-l1-1-0!StringFromIID` at `0x18003773b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800376e4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180037723`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180037762`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800376e4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180037723`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180037762`
- `ext-ms-win-shell-shell32-l1-2-0!SHChangeNotify` at `0x1800382e9`
- `ext-ms-win-shell-shell32-l1-2-0!SHChangeNotify` at `0x1800382e9`

## string_xrefs

- `0x180037799`: `CLSID\%38s`
- `0x180037bb7`: `CLSID\%38s`
- `0x18003783a`: `FileExtensions`
- `0x180037c4d`: `FileExtensions`
- `0x1800379a7`: `CLSID\%38s\InprocServer32`
- `0x180037de6`: `CLSID\%38s\InprocServer32`
- `0x1800379e1`: `ThreadingModel`
- `0x180037e21`: `ThreadingModel`
- `0x180037a13`: `CLSID\%38s\Patterns\0`
- `0x180037aaf`: `CLSID\%38s\Patterns\1`
- `0x180037b45`: `CLSID\{7ED96837-96F0-4812-B211-F13C24117ED3}\Instance\%38s`
- `0x180037b67`: `CLSID`
- `0x180037e6b`: `CLSID`
- `0x180037e47`: `CLSID\{AC757296-3522-4e11-9862-C17BE5A1767E}\Instance\%38s`
- `0x180037e9a`: `CLSID\{FAE3D380-FEA4-4623-8C75-C6B61110B681}\Namespaces`
- `0x180037fbe`: `.wdp\OpenWithProgids`
- `0x180038033`: `@wmphoto.dll,-500`
- `0x180038078`: `wdpfile\shell\printto\command`
- `0x18003808b`: `rundll32.exe %SystemRoot%\system32\shimgvw.dll,ImageView_PrintTo /pt "%1" "%2" "%3" "%4"`
- `0x1800380b3`: `wdpfile\shell\print\command`
- `0x1800380c6`: `rundll32.exe %SystemRoot%\system32\shimgvw.dll,ImageView_Fullscreen %1`
- `0x180038191`: `Clsid`
- `0x180038258`: `CLSID\%38s\Formats\{6FDDC324-4E03-4BFE-B185-3D77768DC9%02X}`
- `0x180038293`: `CLSID\%38s\Formats\{6FDDC324-4E03-4BFE-B185-3D77768DC9%02X}`

## pseudocode

```c
HRESULT __stdcall DllRegisterServer()
{
  unsigned __int64 v0; // rdx
  unsigned __int64 v1; // rdx
  unsigned __int64 v2; // rdx
  unsigned __int64 i; // rbx
  void *v5; // [rsp+20h] [rbp-E0h]
  void *v6; // [rsp+20h] [rbp-E0h]
  int v7; // [rsp+30h] [rbp-D0h] BYREF
  int v8; // [rsp+34h] [rbp-CCh] BYREF
  int v9; // [rsp+38h] [rbp-C8h] BYREF
  LPOLESTR lpsz; // [rsp+40h] [rbp-C0h] BYREF
  int v11; // [rsp+48h] [rbp-B8h] BYREF
  int v12; // [rsp+4Ch] [rbp-B4h] BYREF
  int v13; // [rsp+50h] [rbp-B0h] BYREF
  int v14; // [rsp+54h] [rbp-ACh] BYREF
  int v15; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v16; // [rsp+60h] [rbp-A0h] BYREF
  _OWORD v17[2]; // [rsp+70h] [rbp-90h]
  unsigned __int16 v18[264]; // [rsp+90h] [rbp-70h] BYREF
  _OWORD v19[2]; // [rsp+2A0h] [rbp+1A0h] BYREF
  int v20; // [rsp+2C0h] [rbp+1C0h]
  _OWORD v21[7]; // [rsp+2D0h] [rbp+1D0h] BYREF
  _OWORD v22[2]; // [rsp+340h] [rbp+240h]
  unsigned __int16 v23[264]; // [rsp+360h] [rbp+260h] BYREF
  unsigned __int16 v24[264]; // [rsp+570h] [rbp+470h] BYREF
  WCHAR Filename[264]; // [rsp+780h] [rbp+680h] BYREF
  unsigned __int16 v26[264]; // [rsp+990h] [rbp+890h] BYREF

  v16 = *(_OWORD *)L"image/vnd.ms-photo";
  v7 = -1;
  v17[0] = *(_OWORD *)L"d.ms-photo";
  v8 = 12339529;
  *(_QWORD *)((char *)v17 + 14) = *(_QWORD *)L"oto";
  v9 = 29116745;
  v11 = 0;
  v12 = 0;
  v13 = 0;
  v14 = 1;
  v15 = 0;
  memset_0(Filename, 0, 0x208u);
  memset_0(v18, 0, 0x208u);
  lpsz = 0;
  memset_0(v23, 0, 0x208u);
  memset_0(v24, 0, 0x208u);
  memset_0(v26, 0, 0x208u);
  StringFromIID(&CLSID_WICWmpDecoder, &lpsz);
  if ( lpsz )
  {
    StringCchCopyW(v23, v0, lpsz);
    CoTaskMemFree(lpsz);
  }
  StringFromIID(&CLSID_WICWmpEncoder, &lpsz);
  if ( lpsz )
  {
    StringCchCopyW(v24, v1, lpsz);
    CoTaskMemFree(lpsz);
  }
  StringFromIID(&CLSID_WmpImageDecodeFilter, &lpsz);
  if ( lpsz )
  {
    StringCchCopyW(v26, v2, lpsz);
    CoTaskMemFree(lpsz);
  }
  GetModuleFileNameW(g_hInstWMPCodec, Filename, 0x104u);
  StringCchPrintfW(v18, 0x104u, L"CLSID\\%38s", v23);
  RegisterKey(HKEY_CLASSES_ROOT, v18, L"Author", 1u, L"Microsoft", 0);
  RegisterKey(HKEY_CLASSES_ROOT, v18, L"ColorManagementVersion", 1u, L"1.0.0.0", 0);
  RegisterKey(HKEY_CLASSES_ROOT, v18, L"ContainerFormat", 1u, L"{57A37CAA-367A-4540-916B-F183C5093A4B}", 0);
  RegisterKey(HKEY_CLASSES_ROOT, v18, L"FileExtensions", 1u, L".wdp", 0);
  RegisterKey(HKEY_CLASSES_ROOT, v18, L"FriendlyName", 1u, L"WMPhoto Decoder", 0);
  RegisterKey(HKEY_CLASSES_ROOT, v18, L"MimeTypes", 1u, &v16, 0);
  RegisterKey(HKEY_CLASSES_ROOT, v18, L"SpecVersion", 1u, L"1.0.0.0", 0);
  RegisterKey(HKEY_CLASSES_ROOT, v18, L"SupportAnimation", 4u, &v12, 4u);
  RegisterKey(HKEY_CLASSES_ROOT, v18, L"SupportChromakey", 4u, &v13, 4u);
  RegisterKey(HKEY_CLASSES_ROOT, v18, L"SupportLossless", 4u, &v14, 4u);
  RegisterKey(HKEY_CLASSES_ROOT, v18, L"SupportMultiframe", 4u, &v15, 4u);
  RegisterKey(HKEY_CLASSES_ROOT, v18, L"Vendor", 1u, L"{F0E749CA-EDEF-4589-A73A-EE0E626A2A2B}", 0);
  RegisterKey(HKEY_CLASSES_ROOT, v18, L"Version", 1u, L"1.0.0.0", 0);
  StringCchPrintfW(v18, 0x104u, L"CLSID\\%38s\\InprocServer32", v23);
  RegisterKey(HKEY_CLASSES_ROOT, v18, 0, 1u, Filename, 0);
  RegisterKey(HKEY_CLASSES_ROOT, v18, L"ThreadingModel", 1u, L"Both", 0);
  StringCchPrintfW(v18, 0x104u, L"CLSID\\%38s\\Patterns\\0", v23);
  RegisterKey(HKEY_CLASSES_ROOT, v18, L"Mask", 3u, &v7, 4u);
  RegisterKey(HKEY_CLASSES_ROOT, v18, L"Pattern", 3u, &v8, 4u);
  RegisterKey(HKEY_CLASSES_ROOT, v18, L"Position", 4u, &v11, 4u);
  StringCchPrintfW(v18, 0x104u, L"CLSID\\%38s\\Patterns\\1", v23);
  RegisterKey(HKEY_CLASSES_ROOT, v18, L"Mask", 3u, &v7, 4u);
  RegisterKey(HKEY_CLASSES_ROOT, v18, L"Pattern", 3u, &v9, 4u);
  RegisterKey(HKEY_CLASSES_ROOT, v18, L"Position", 4u, &v11, 4u);
  StringCchPrintfW(v18, 0x104u, L"CLSID\\{7ED96837-96F0-4812-B211-F13C24117ED3}\\Instance\\%38s", v23);
  RegisterKey(HKEY_CLASSES_ROOT, v18, L"CLSID", 1u, v23, 0);
  RegisterKey(HKEY_CLASSES_ROOT, v18, L"FriendlyName", 1u, L"WMPhoto Decoder", 0);
  StringCchPrintfW(v18, 0x104u, L"CLSID\\%38s", v24);
  RegisterKey(HKEY_CLASSES_ROOT, v18, L"Author", 1u, L"Microsoft", 0);
  RegisterKey(HKEY_CLASSES_ROOT, v18, L"ColorManagementVersion", 1u, L"1.0.0.0", 0);
  RegisterKey(HKEY_CLASSES_ROOT, v18, L"ContainerFormat", 1u, L"{57A37CAA-367A-4540-916B-F183C5093A4B}", 0);
  RegisterKey(HKEY_CLASSES_ROOT, v18, L"FileExtensions", 1u, L".wdp", 0);
  RegisterKey(HKEY_CLASSES_ROOT, v18, L"FriendlyName", 1u, L"WMPhoto Encoder", 0);
  RegisterKey(HKEY_CLASSES_ROOT, v18, L"MimeTypes", 1u, &v16, 0);
  RegisterKey(HKEY_CLASSES_ROOT, v18, L"SpecVersion", 1u, L"1.0.0.0", 0);
  RegisterKey(HKEY_CLASSES_ROOT, v18, L"SupportAnimation", 4u, &v12, 4u);
  RegisterKey(HKEY_CLASSES_ROOT, v18, L"SupportChromakey", 4u, &v13, 4u);
  RegisterKey(HKEY_CLASSES_ROOT, v18, L"SupportLossless", 4u, &v14, 4u);
  RegisterKey(HKEY_CLASSES_ROOT, v18, L"SupportMultiframe", 4u, &v15, 4u);
  RegisterKey(HKEY_CLASSES_ROOT, v18, L"Vendor", 1u, L"{F0E749CA-EDEF-4589-A73A-EE0E626A2A2B}", 0);
  RegisterKey(HKEY_CLASSES_ROOT, v18, L"Version", 1u, L"1.0.0.0", 0);
  StringCchPrintfW(v18, 0x104u, L"CLSID\\%38s\\InprocServer32", v24);
  RegisterKey(HKEY_CLASSES_ROOT, v18, 0, 1u, Filename, 0);
  RegisterKey(HKEY_CLASSES_ROOT, v18, L"ThreadingModel", 1u, L"Both", 0);
  StringCchPrintfW(v18, 0x104u, L"CLSID\\{AC757296-3522-4e11-9862-C17BE5A1767E}\\Instance\\%38s", v24);
  RegisterKey(HKEY_CLASSES_ROOT, v18, L"CLSID", 1u, v24, 0);
  RegisterKey(HKEY_CLASSES_ROOT, v18, L"FriendlyName", 1u, L"WMPhoto Encoder", 0);
  StringCchPrintfW(v18, 0x104u, L"CLSID\\{FAE3D380-FEA4-4623-8C75-C6B61110B681}\\Namespaces");
  RegisterKey(HKEY_CLASSES_ROOT, v18, L"wmphoto", 1u, L"{57A37CAA-367A-4540-916B-F183C5093A4B}", 0);
  StringCchPrintfW(v18, 0x104u, L".wdp");
  RegisterKey(HKEY_CLASSES_ROOT, v18, 0, 1u, L"wdpfile", 0);
  RegisterKey(HKEY_CLASSES_ROOT, v18, L"Content Type", 1u, &v16, 0);
  RegisterKey(HKEY_CLASSES_ROOT, v18, L"PerceivedType", 1u, L"image", 0);
  StringCchPrintfW(v18, 0x104u, L".wdp\\ShellEx\\{BB2E617C-0920-11d1-9A0B-00C04FC2D6C1}");
  RegisterKey(HKEY_CLASSES_ROOT, v18, 0, 1u, L"{3F30C968-480A-4C6C-862D-EFC0897BB84B}", 0);
  StringCchPrintfW(v18, 0x104u, L".wdp\\ShellEx\\{e357fccd-a995-4576-b01f-234630154e96}");
  RegisterKey(HKEY_CLASSES_ROOT, v18, 0, 1u, L"{C7657C4A-9F68-40fa-A4DF-96BC08EB3551}", 0);
  StringCchPrintfW(v18, 0x104u, L".wdp\\OpenWithProgids");
  RegisterKey(HKEY_CLASSES_ROOT, v18, L"wdpfile", 0, &word_18004908A, 0);
  StringCchPrintfW(v18, 0x104u, L"wdpfile");
  RegisterKey(HKEY_CLASSES_ROOT, v18, 0, 1u, L"Windows Media Photo", 0);
  v20 = *(_DWORD *)L"0";
  v19[0] = *(_OWORD *)L"@wmphoto.dll,-500";
  v19[1] = *(_OWORD *)L".dll,-500";
  RegisterKey(HKEY_CLASSES_ROOT, v18, L"FriendlyTypeName", 1u, v19, 0x24u);
  StringCchPrintfW(v18, 0x104u, L"wdpfile\\shell\\printto\\command");
  RegisterKey(
    HKEY_CLASSES_ROOT,
    v18,
    0,
    2u,
    L"rundll32.exe %SystemRoot%\\system32\\shimgvw.dll,ImageView_PrintTo /pt \"%1\" \"%2\" \"%3\" \"%4\"",
    0);
  StringCchPrintfW(v18, 0x104u, L"wdpfile\\shell\\print\\command");
  v21[0] = *(_OWORD *)L"rundll32.exe %SystemRoot%\\system32\\shimgvw.dll,ImageView_Fullscreen %1";
  v21[2] = *(_OWORD *)L"stemRoot%\\system32\\shimgvw.dll,ImageView_Fullscreen %1";
  v21[1] = *(_OWORD *)L".exe %SystemRoot%\\system32\\shimgvw.dll,ImageView_Fullscreen %1";
  v21[4] = *(_OWORD *)L"32\\shimgvw.dll,ImageView_Fullscreen %1";
  v21[3] = *(_OWORD *)L"%\\system32\\shimgvw.dll,ImageView_Fullscreen %1";
  v21[6] = *(_OWORD *)L"mageView_Fullscreen %1";
  v21[5] = *(_OWORD *)L"vw.dll,ImageView_Fullscreen %1";
  v22[0] = *(_OWORD *)L"_Fullscreen %1";
  *(_OWORD *)((char *)v22 + 14) = *(_OWORD *)L"reen %1";
  RegisterKey(HKEY_CLASSES_ROOT, v18, 0, 2u, v21, 0x8Eu);
  StringCchPrintfW(v18, 0x104u, L"wdpfile\\shell\\print\\DropTarget");
  RegisterKey(HKEY_CLASSES_ROOT, v18, L"Clsid", 1u, L"{60fd46de-f830-4894-a628-6fa81bc0190d}", 0);
  StringCchPrintfW(v18, 0x104u, L"SystemFileAssociations\\.wdp\\ShellEx\\{BB2E617C-0920-11d1-9A0B-00C04FC2D6C1}");
  RegisterKey(HKEY_CLASSES_ROOT, v18, 0, 1u, L"{3F30C968-480A-4C6C-862D-EFC0897BB84B}", 0);
  StringCchPrintfW(v18, 0x104u, L"SystemFileAssociations\\.wdp\\ShellEx\\{e357fccd-a995-4576-b01f-234630154e96}");
  RegisterKey(HKEY_CLASSES_ROOT, v18, 0, 1u, L"{C7657C4A-9F68-40fa-A4DF-96BC08EB3551}", 0);
  StringCchPrintfW(v18, 0x104u, L"Software\\Microsoft\\Windows\\CurrentVersion\\PropertySystem\\PropertyHandlers\\.wdp");
  RegisterKey(HKEY_LOCAL_MACHINE, v18, 0, 1u, L"{a38b883c-1682-497e-97b0-0a3a9e801682}", 0);
  for ( i = 0; i < 0x38; ++i )
  {
    LODWORD(v5) = *((unsigned __int8 *)qword_180049E28 + i);
    StringCchPrintfW(v18, 0x104u, L"CLSID\\%38s\\Formats\\{6FDDC324-4E03-4BFE-B185-3D77768DC9%02X}", v23, v5);
    RegisterKey(HKEY_CLASSES_ROOT, v18, 0, 1u, &dword_18004908C, 0);
    LODWORD(v6) = *((unsigned __int8 *)qword_180049E28 + i);
    StringCchPrintfW(v18, 0x104u, L"CLSID\\%38s\\Formats\\{6FDDC324-4E03-4BFE-B185-3D77768DC9%02X}", v24, v6);
    RegisterKey(HKEY_CLASSES_ROOT, v18, 0, 1u, &dword_18004908C, 0);
  }
  if ( (unsigned __int8)IsSHChangeNotifyPresent() )
    SHChangeNotify(0x8000000, 0, 0, 0);
  return 0;
}

```

## disassembly

```asm
0x1800375d0  push    rbp
0x1800375d2  push    rbx
0x1800375d3  push    rsi
0x1800375d4  push    rdi
0x1800375d5  push    r12
0x1800375d7  push    r13
0x1800375d9  push    r14
0x1800375db  push    r15
0x1800375dd  lea     rbp, [rsp-0AB8h]
0x1800375e5  sub     rsp, 0BB8h
0x1800375ec  mov     rax, cs:__security_cookie
0x1800375f3  xor     rax, rsp
0x1800375f6  mov     [rbp+0AF0h+var_50], rax
0x1800375fd  movups  xmm0, xmmword ptr cs:aImageVndMsPhot; "image/vnd.ms-photo"
0x180037604  xor     esi, esi
0x180037606  mov     ebx, 208h
0x18003760b  movups  xmm1, xmmword ptr cs:aImageVndMsPhot+10h; "d.ms-photo"
0x180037612  mov     r8d, ebx; Size
0x180037615  xor     edx, edx; Val
0x180037617  movups  [rsp+0BF0h+var_B90], xmm0
0x18003761c  lea     rcx, [rbp+0AF0h+Filename]; void *
0x180037623  mov     [rsp+0BF0h+var_BC0], 0FFFFFFFFh
0x18003762b  movsd   xmm0, qword ptr cs:aImageVndMsPhot+1Eh; "oto"
0x180037633  movups  xmmword ptr [rsp+0BF0h+var_B80], xmm1
0x180037638  mov     [rsp+0BF0h+var_BBC], 0BC4949h
0x180037640  movsd   qword ptr [rsp+0BF0h+var_B80+0Eh], xmm0
0x180037646  mov     [rsp+0BF0h+var_BB8], 1BC4949h
0x18003764e  mov     [rsp+0BF0h+var_BA8], esi
0x180037652  mov     [rsp+0BF0h+var_BA4], esi
0x180037656  mov     [rsp+0BF0h+var_BA0], esi
0x18003765a  mov     [rsp+0BF0h+var_B9C], 1
0x180037662  mov     [rsp+0BF0h+var_B98], esi
0x180037666  call    memset_0
0x18003766b  mov     r8d, ebx; Size
0x18003766e  lea     rcx, [rbp+0AF0h+var_B60]; void *
0x180037672  xor     edx, edx; Val
0x180037674  call    memset_0
0x180037679  mov     r8d, ebx; Size
0x18003767c  mov     [rsp+0BF0h+lpsz], rsi
0x180037681  xor     edx, edx; Val
0x180037683  lea     rcx, [rbp+0AF0h+var_890]; void *
0x18003768a  call    memset_0
0x18003768f  mov     r8d, ebx; Size
0x180037692  lea     rcx, [rbp+0AF0h+var_680]; void *
0x180037699  xor     edx, edx; Val
0x18003769b  call    memset_0
0x1800376a0  mov     r8d, ebx; Size
0x1800376a3  lea     rcx, [rbp+0AF0h+var_260]; void *
0x1800376aa  xor     edx, edx; Val
0x1800376ac  call    memset_0
0x1800376b1  lea     rdx, [rsp+0BF0h+lpsz]; lplpsz
0x1800376b6  lea     rcx, CLSID_WICWmpDecoder; rclsid
0x1800376bd  call    cs:__imp_StringFromIID
0x1800376c4  nop     dword ptr [rax+rax+00h]
0x1800376c9  mov     r8, [rsp+0BF0h+lpsz]; unsigned __int16 *
0x1800376ce  test    r8, r8
0x1800376d1  jz      short loc_1800376F0
0x1800376d3  lea     rcx, [rbp+0AF0h+var_890]; unsigned __int16 *
0x1800376da  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800376df  mov     rcx, [rsp+0BF0h+lpsz]; pv
0x1800376e4  call    cs:__imp_CoTaskMemFree
0x1800376eb  nop     dword ptr [rax+rax+00h]
0x1800376f0  lea     rdx, [rsp+0BF0h+lpsz]; lplpsz
0x1800376f5  lea     rcx, CLSID_WICWmpEncoder; rclsid
0x1800376fc  call    cs:__imp_StringFromIID
0x180037703  nop     dword ptr [rax+rax+00h]
0x180037708  mov     r8, [rsp+0BF0h+lpsz]; unsigned __int16 *
0x18003770d  test    r8, r8
0x180037710  jz      short loc_18003772F
0x180037712  lea     rcx, [rbp+0AF0h+var_680]; unsigned __int16 *
0x180037719  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18003771e  mov     rcx, [rsp+0BF0h+lpsz]; pv
0x180037723  call    cs:__imp_CoTaskMemFree
0x18003772a  nop     dword ptr [rax+rax+00h]
0x18003772f  lea     rdx, [rsp+0BF0h+lpsz]; lplpsz
0x180037734  lea     rcx, CLSID_WmpImageDecodeFilter; rclsid
0x18003773b  call    cs:__imp_StringFromIID
0x180037742  nop     dword ptr [rax+rax+00h]
0x180037747  mov     r8, [rsp+0BF0h+lpsz]; unsigned __int16 *
0x18003774c  test    r8, r8
0x18003774f  jz      short loc_18003776E
0x180037751  lea     rcx, [rbp+0AF0h+var_260]; unsigned __int16 *
0x180037758  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18003775d  mov     rcx, [rsp+0BF0h+lpsz]; pv
0x180037762  call    cs:__imp_CoTaskMemFree
0x180037769  nop     dword ptr [rax+rax+00h]
0x18003776e  mov     rcx, cs:?g_hInstWMPCodec@@3PEAUHINSTANCE__@@EA; hModule
0x180037775  lea     rdx, [rbp+0AF0h+Filename]; lpFilename
0x18003777c  mov     ebx, 104h
0x180037781  mov     r8d, ebx; nSize
0x180037784  call    cs:__imp_GetModuleFileNameW
0x18003778b  nop     dword ptr [rax+rax+00h]
0x180037790  lea     r9, [rbp+0AF0h+var_890]
0x180037797  mov     edx, ebx; unsigned __int64
0x180037799  lea     r8, aClsid38s; "CLSID\\%38s"
0x1800377a0  lea     rcx, [rbp+0AF0h+var_B60]; unsigned __int16 *
0x1800377a4  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800377a9  mov     ebx, 1
0x1800377ae  mov     [rsp+0BF0h+var_BC8], esi; unsigned int
0x1800377b2  mov     r14, 0FFFFFFFF80000000h
0x1800377b9  lea     r15, aMicrosoft; "Microsoft"
0x1800377c0  mov     r9d, ebx; unsigned int
0x1800377c3  mov     [rsp+0BF0h+var_BD0], r15; void *
0x1800377c8  mov     rcx, r14; HKEY
0x1800377cb  lea     r8, aAuthor; "Author"
0x1800377d2  lea     rdx, [rbp+0AF0h+var_B60]; unsigned __int16 *
0x1800377d6  call    ?RegisterKey@@YAHPEAUHKEY__@@PEBG1KPEBXK@Z; RegisterKey(HKEY__ *,ushort const *,ushort const *,ulong,void const *,ulong)
0x1800377db  lea     r13, a1000; "1.0.0.0"
0x1800377e2  mov     [rsp+0BF0h+var_BC8], esi; unsigned int
0x1800377e6  mov     r9d, ebx; unsigned int
0x1800377e9  mov     [rsp+0BF0h+var_BD0], r13; void *
0x1800377ee  lea     r8, aColormanagemen; "ColorManagementVersion"
0x1800377f5  mov     rcx, r14; HKEY
0x1800377f8  lea     rdx, [rbp+0AF0h+var_B60]; unsigned __int16 *
0x1800377fc  call    ?RegisterKey@@YAHPEAUHKEY__@@PEBG1KPEBXK@Z; RegisterKey(HKEY__ *,ushort const *,ushort const *,ulong,void const *,ulong)
0x180037801  lea     rax, a57a37caa367a45; "{57A37CAA-367A-4540-916B-F183C5093A4B}"
0x180037808  mov     [rsp+0BF0h+var_BC8], esi; unsigned int
0x18003780c  mov     r9d, ebx; unsigned int
0x18003780f  mov     [rsp+0BF0h+var_BD0], rax; void *
0x180037814  lea     r8, aContainerforma; "ContainerFormat"
0x18003781b  mov     rcx, r14; HKEY
0x18003781e  lea     rdx, [rbp+0AF0h+var_B60]; unsigned __int16 *
0x180037822  call    ?RegisterKey@@YAHPEAUHKEY__@@PEBG1KPEBXK@Z; RegisterKey(HKEY__ *,ushort const *,ushort const *,ulong,void const *,ulong)
0x180037827  lea     rax, aWdp_0; ".wdp"
0x18003782e  mov     [rsp+0BF0h+var_BC8], esi; unsigned int
0x180037832  mov     r9d, ebx; unsigned int
0x180037835  mov     [rsp+0BF0h+var_BD0], rax; void *
0x18003783a  lea     r8, aFileextensions; "FileExtensions"
0x180037841  mov     rcx, r14; HKEY
0x180037844  lea     rdx, [rbp+0AF0h+var_B60]; unsigned __int16 *
0x180037848  call    ?RegisterKey@@YAHPEAUHKEY__@@PEBG1KPEBXK@Z; RegisterKey(HKEY__ *,ushort const *,ushort const *,ulong,void const *,ulong)
0x18003784d  lea     rdi, aWmphotoDecoder; "WMPhoto Decoder"
0x180037854  mov     [rsp+0BF0h+var_BC8], esi; unsigned int
0x180037858  mov     r9d, ebx; unsigned int
0x18003785b  mov     [rsp+0BF0h+var_BD0], rdi; void *
0x180037860  lea     r8, aFriendlyname; "FriendlyName"
0x180037867  mov     rcx, r14; HKEY
0x18003786a  lea     rdx, [rbp+0AF0h+var_B60]; unsigned __int16 *
0x18003786e  call    ?RegisterKey@@YAHPEAUHKEY__@@PEBG1KPEBXK@Z; RegisterKey(HKEY__ *,ushort const *,ushort const *,ulong,void const *,ulong)
0x180037873  lea     rax, [rsp+0BF0h+var_B90]
0x180037878  mov     [rsp+0BF0h+var_BC8], esi; unsigned int
0x18003787c  mov     r9d, ebx; unsigned int
0x18003787f  mov     [rsp+0BF0h+var_BD0], rax; void *
0x180037884  lea     r8, aMimetypes; "MimeTypes"
0x18003788b  mov     rcx, r14; HKEY
0x18003788e  lea     rdx, [rbp+0AF0h+var_B60]; unsigned __int16 *
0x180037892  call    ?RegisterKey@@YAHPEAUHKEY__@@PEBG1KPEBXK@Z; RegisterKey(HKEY__ *,ushort const *,ushort const *,ulong,void const *,ulong)
0x180037897  mov     r9d, ebx; unsigned int
0x18003789a  mov     [rsp+0BF0h+var_BC8], esi; unsigned int
0x18003789e  lea     r8, aSpecversion; "SpecVersion"
0x1800378a5  mov     [rsp+0BF0h+var_BD0], r13; void *
0x1800378aa  lea     rdx, [rbp+0AF0h+var_B60]; unsigned __int16 *
0x1800378ae  mov     rcx, r14; HKEY
0x1800378b1  call    ?RegisterKey@@YAHPEAUHKEY__@@PEBG1KPEBXK@Z; RegisterKey(HKEY__ *,ushort const *,ushort const *,ulong,void const *,ulong)
0x1800378b6  lea     r12d, [rbx+3]
0x1800378ba  mov     rcx, r14; HKEY
0x1800378bd  lea     rax, [rsp+0BF0h+var_BA4]
0x1800378c2  mov     [rsp+0BF0h+var_BC8], r12d; unsigned int
0x1800378c7  mov     r9d, r12d; unsigned int
0x1800378ca  mov     [rsp+0BF0h+var_BD0], rax; void *
0x1800378cf  lea     r8, aSupportanimati; "SupportAnimation"
0x1800378d6  lea     rdx, [rbp+0AF0h+var_B60]; unsigned __int16 *
0x1800378da  call    ?RegisterKey@@YAHPEAUHKEY__@@PEBG1KPEBXK@Z; RegisterKey(HKEY__ *,ushort const *,ushort const *,ulong,void const *,ulong)
0x1800378df  lea     rax, [rsp+0BF0h+var_BA0]
0x1800378e4  mov     [rsp+0BF0h+var_BC8], r12d; unsigned int
0x1800378e9  mov     [rsp+0BF0h+var_BD0], rax; void *
0x1800378ee  lea     r8, aSupportchromak; "SupportChromakey"
0x1800378f5  mov     r9d, r12d; unsigned int
0x1800378f8  lea     rdx, [rbp+0AF0h+var_B60]; unsigned __int16 *
0x1800378fc  mov     rcx, r14; HKEY
0x1800378ff  call    ?RegisterKey@@YAHPEAUHKEY__@@PEBG1KPEBXK@Z; RegisterKey(HKEY__ *,ushort const *,ushort const *,ulong,void const *,ulong)
0x180037904  lea     rax, [rsp+0BF0h+var_B9C]
0x180037909  mov     [rsp+0BF0h+var_BC8], r12d; unsigned int
0x18003790e  mov     r9d, r12d; unsigned int
0x180037911  mov     [rsp+0BF0h+var_BD0], rax; void *
0x180037916  lea     r8, aSupportlossles; "SupportLossless"
0x18003791d  mov     rcx, r14; HKEY
0x180037920  lea     rdx, [rbp+0AF0h+var_B60]; unsigned __int16 *
0x180037924  call    ?RegisterKey@@YAHPEAUHKEY__@@PEBG1KPEBXK@Z; RegisterKey(HKEY__ *,ushort const *,ushort const *,ulong,void const *,ulong)
0x180037929  lea     rax, [rsp+0BF0h+var_B98]
0x18003792e  mov     [rsp+0BF0h+var_BC8], r12d; unsigned int
0x180037933  mov     r9d, r12d; unsigned int
0x180037936  mov     [rsp+0BF0h+var_BD0], rax; void *
0x18003793b  lea     r8, aSupportmultifr; "SupportMultiframe"
0x180037942  mov     rcx, r14; HKEY
0x180037945  lea     rdx, [rbp+0AF0h+var_B60]; unsigned __int16 *
0x180037949  call    ?RegisterKey@@YAHPEAUHKEY__@@PEBG1KPEBXK@Z; RegisterKey(HKEY__ *,ushort const *,ushort const *,ulong,void const *,ulong)
0x18003794e  lea     r14, aF0e749caEdef45; "{F0E749CA-EDEF-4589-A73A-EE0E626A2A2B}"
0x180037955  mov     [rsp+0BF0h+var_BC8], esi; unsigned int
0x180037959  mov     r9d, ebx; unsigned int
0x18003795c  mov     [rsp+0BF0h+var_BD0], r14; void *
0x180037961  lea     r8, aVendor; "Vendor"
0x180037968  mov     rcx, 0FFFFFFFF80000000h; HKEY
0x18003796f  lea     rdx, [rbp+0AF0h+var_B60]; unsigned __int16 *
0x180037973  call    ?RegisterKey@@YAHPEAUHKEY__@@PEBG1KPEBXK@Z; RegisterKey(HKEY__ *,ushort const *,ushort const *,ulong,void const *,ulong)
0x180037978  mov     r9d, ebx; unsigned int
0x18003797b  mov     [rsp+0BF0h+var_BC8], esi; unsigned int
0x18003797f  lea     r8, aVersion; "Version"
0x180037986  mov     [rsp+0BF0h+var_BD0], r13; void *
0x18003798b  lea     rdx, [rbp+0AF0h+var_B60]; unsigned __int16 *
0x18003798f  mov     rcx, 0FFFFFFFF80000000h; HKEY
0x180037996  call    ?RegisterKey@@YAHPEAUHKEY__@@PEBG1KPEBXK@Z; RegisterKey(HKEY__ *,ushort const *,ushort const *,ulong,void const *,ulong)
0x18003799b  lea     r9, [rbp+0AF0h+var_890]
0x1800379a2  mov     edx, 104h; unsigned __int64
0x1800379a7  lea     r8, aClsid38sInproc; "CLSID\\%38s\\InprocServer32"
0x1800379ae  lea     rcx, [rbp+0AF0h+var_B60]; unsigned __int16 *
0x1800379b2  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800379b7  lea     rax, [rbp+0AF0h+Filename]
0x1800379be  mov     [rsp+0BF0h+var_BC8], esi; unsigned int
0x1800379c2  mov     r9d, ebx; unsigned int
0x1800379c5  mov     [rsp+0BF0h+var_BD0], rax; void *
0x1800379ca  xor     r8d, r8d; unsigned __int16 *
0x1800379cd  lea     rdx, [rbp+0AF0h+var_B60]; unsigned __int16 *
0x1800379d1  mov     rcx, 0FFFFFFFF80000000h; HKEY
0x1800379d8  call    ?RegisterKey@@YAHPEAUHKEY__@@PEBG1KPEBXK@Z; RegisterKey(HKEY__ *,ushort const *,ushort const *,ulong,void const *,ulong)
0x1800379dd  mov     [rsp+0BF0h+var_BC8], esi; unsigned int
0x1800379e1  lea     r8, aThreadingmodel; "ThreadingModel"
0x1800379e8  lea     rsi, aBoth; "Both"
0x1800379ef  mov     r9d, ebx; unsigned int
0x1800379f2  lea     rdx, [rbp+0AF0h+var_B60]; unsigned __int16 *
0x1800379f6  mov     [rsp+0BF0h+var_BD0], rsi; void *
0x1800379fb  mov     rcx, 0FFFFFFFF80000000h; HKEY
0x180037a02  call    ?RegisterKey@@YAHPEAUHKEY__@@PEBG1KPEBXK@Z; RegisterKey(HKEY__ *,ushort const *,ushort const *,ulong,void const *,ulong)
0x180037a07  lea     r9, [rbp+0AF0h+var_890]
0x180037a0e  mov     edx, 104h; unsigned __int64
0x180037a13  lea     r8, aClsid38sPatter; "CLSID\\%38s\\Patterns\\0"
0x180037a1a  lea     rcx, [rbp+0AF0h+var_B60]; unsigned __int16 *
0x180037a1e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180037a23  lea     rax, [rsp+0BF0h+var_BC0]
0x180037a28  mov     [rsp+0BF0h+var_BC8], r12d; unsigned int
0x180037a2d  lea     ebx, [r12-1]
0x180037a32  mov     [rsp+0BF0h+var_BD0], rax; void *
0x180037a37  mov     r9d, ebx; unsigned int
0x180037a3a  lea     r8, aMask; "Mask"
0x180037a41  lea     rdx, [rbp+0AF0h+var_B60]; unsigned __int16 *
0x180037a45  mov     rcx, 0FFFFFFFF80000000h; HKEY
0x180037a4c  call    ?RegisterKey@@YAHPEAUHKEY__@@PEBG1KPEBXK@Z; RegisterKey(HKEY__ *,ushort const *,ushort const *,ulong,void const *,ulong)
0x180037a51  lea     rax, [rsp+0BF0h+var_BBC]
0x180037a56  mov     [rsp+0BF0h+var_BC8], r12d; unsigned int
0x180037a5b  mov     r9d, ebx; unsigned int
0x180037a5e  mov     [rsp+0BF0h+var_BD0], rax; void *
0x180037a63  lea     r8, aPattern; "Pattern"
0x180037a6a  mov     rcx, 0FFFFFFFF80000000h; HKEY
0x180037a71  lea     rdx, [rbp+0AF0h+var_B60]; unsigned __int16 *
0x180037a75  call    ?RegisterKey@@YAHPEAUHKEY__@@PEBG1KPEBXK@Z; RegisterKey(HKEY__ *,ushort const *,ushort const *,ulong,void const *,ulong)
0x180037a7a  lea     rax, [rsp+0BF0h+var_BA8]
0x180037a7f  mov     [rsp+0BF0h+var_BC8], r12d; unsigned int
0x180037a84  mov     [rsp+0BF0h+var_BD0], rax; void *
0x180037a89  mov     r9d, r12d; unsigned int
0x180037a8c  lea     r8, aPosition; "Position"
0x180037a93  mov     rcx, 0FFFFFFFF80000000h; HKEY
0x180037a9a  lea     rdx, [rbp+0AF0h+var_B60]; unsigned __int16 *
0x180037a9e  call    ?RegisterKey@@YAHPEAUHKEY__@@PEBG1KPEBXK@Z; RegisterKey(HKEY__ *,ushort const *,ushort const *,ulong,void const *,ulong)
0x180037aa3  lea     r9, [rbp+0AF0h+var_890]
0x180037aaa  mov     edx, 104h; unsigned __int64
0x180037aaf  lea     r8, aClsid38sPatter_0; "CLSID\\%38s\\Patterns\\1"
0x180037ab6  lea     rcx, [rbp+0AF0h+var_B60]; unsigned __int16 *
0x180037aba  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180037abf  lea     rax, [rsp+0BF0h+var_BC0]
0x180037ac4  mov     [rsp+0BF0h+var_BC8], r12d; unsigned int
0x180037ac9  mov     r9d, ebx; unsigned int
0x180037acc  mov     [rsp+0BF0h+var_BD0], rax; void *
0x180037ad1  lea     r8, aMask; "Mask"
0x180037ad8  mov     rcx, 0FFFFFFFF80000000h; HKEY
0x180037adf  lea     rdx, [rbp+0AF0h+var_B60]; unsigned __int16 *
0x180037ae3  call    ?RegisterKey@@YAHPEAUHKEY__@@PEBG1KPEBXK@Z; RegisterKey(HKEY__ *,ushort const *,ushort const *,ulong,void const *,ulong)
0x180037ae8  mov     r9d, ebx; unsigned int
0x180037aeb  mov     [rsp+0BF0h+var_BC8], r12d; unsigned int
0x180037af0  lea     rax, [rsp+0BF0h+var_BB8]
0x180037af5  mov     rbx, 0FFFFFFFF80000000h
0x180037afc  mov     rcx, rbx; HKEY
0x180037aff  mov     [rsp+0BF0h+var_BD0], rax; void *
0x180037b04  lea     r8, aPattern; "Pattern"
0x180037b0b  lea     rdx, [rbp+0AF0h+var_B60]; unsigned __int16 *
0x180037b0f  call    ?RegisterKey@@YAHPEAUHKEY__@@PEBG1KPEBXK@Z; RegisterKey(HKEY__ *,ushort const *,ushort const *,ulong,void const *,ulong)
0x180037b14  lea     rax, [rsp+0BF0h+var_BA8]
0x180037b19  mov     [rsp+0BF0h+var_BC8], r12d; unsigned int
0x180037b1e  mov     r9d, r12d; unsigned int
0x180037b21  mov     [rsp+0BF0h+var_BD0], rax; void *
0x180037b26  lea     r8, aPosition; "Position"
0x180037b2d  mov     rcx, rbx; HKEY
0x180037b30  lea     rdx, [rbp+0AF0h+var_B60]; unsigned __int16 *
0x180037b34  call    ?RegisterKey@@YAHPEAUHKEY__@@PEBG1KPEBXK@Z; RegisterKey(HKEY__ *,ushort const *,ushort const *,ulong,void const *,ulong)
0x180037b39  lea     r9, [rbp+0AF0h+var_890]
0x180037b40  mov     edx, 104h; unsigned __int64
0x180037b45  lea     r8, aClsid7ed968379; "CLSID\\{7ED96837-96F0-4812-B211-F13C241"...
0x180037b4c  lea     rcx, [rbp+0AF0h+var_B60]; unsigned __int16 *
0x180037b50  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180037b55  lea     rax, [rbp+0AF0h+var_890]
0x180037b5c  xor     ebx, ebx
0x180037b5e  mov     [rsp+0BF0h+var_BC8], ebx; unsigned int
0x180037b62  lea     r9d, [r12-3]; unsigned int
0x180037b67  lea     r8, aClsid_0; "CLSID"
0x180037b6e  mov     [rsp+0BF0h+var_BD0], rax; void *
0x180037b73  lea     rdx, [rbp+0AF0h+var_B60]; unsigned __int16 *
0x180037b77  mov     rcx, 0FFFFFFFF80000000h; HKEY
0x180037b7e  call    ?RegisterKey@@YAHPEAUHKEY__@@PEBG1KPEBXK@Z; RegisterKey(HKEY__ *,ushort const *,ushort const *,ulong,void const *,ulong)
0x180037b83  mov     [rsp+0BF0h+var_BC8], ebx; unsigned int
0x180037b87  lea     r9d, [r12-3]; unsigned int
0x180037b8c  mov     [rsp+0BF0h+var_BD0], rdi; void *
  ... truncated ...
```
