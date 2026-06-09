# DllRegisterServer

- ea: `0x180036fe0`
- end: `0x180037cfa`
- name: `DllRegisterServer`
- size: `3354`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x180035e50`
- `0x180036ba4`
- `0x180036cf8`
- `0x180036e38`
- `0x180036efc`
- `0x180036f54`
- `0x180036fe0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180037170`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180037170`
- `api-ms-win-core-com-l1-1-0!StringFromIID` at `0x1800370cd`
- `api-ms-win-core-com-l1-1-0!StringFromIID` at `0x180037100`
- `api-ms-win-core-com-l1-1-0!StringFromIID` at `0x180037133`
- `api-ms-win-core-com-l1-1-0!StringFromIID` at `0x1800370cd`
- `api-ms-win-core-com-l1-1-0!StringFromIID` at `0x180037100`
- `api-ms-win-core-com-l1-1-0!StringFromIID` at `0x180037133`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800370ee`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180037121`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180037154`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800370ee`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180037121`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180037154`
- `ext-ms-win-shell-shell32-l1-2-0!SHChangeNotify` at `0x180037ccf`
- `ext-ms-win-shell-shell32-l1-2-0!SHChangeNotify` at `0x180037ccf`

## string_xrefs

- `0x18003717f`: `CLSID\%38s`
- `0x18003759d`: `CLSID\%38s`
- `0x180037220`: `FileExtensions`
- `0x180037633`: `FileExtensions`
- `0x18003738d`: `CLSID\%38s\InprocServer32`
- `0x1800377cc`: `CLSID\%38s\InprocServer32`
- `0x1800373c7`: `ThreadingModel`
- `0x180037807`: `ThreadingModel`
- `0x1800373f9`: `CLSID\%38s\Patterns\0`
- `0x180037495`: `CLSID\%38s\Patterns\1`
- `0x18003752b`: `CLSID\{7ED96837-96F0-4812-B211-F13C24117ED3}\Instance\%38s`
- `0x18003754d`: `CLSID`
- `0x180037851`: `CLSID`
- `0x18003782d`: `CLSID\{AC757296-3522-4e11-9862-C17BE5A1767E}\Instance\%38s`
- `0x180037880`: `CLSID\{FAE3D380-FEA4-4623-8C75-C6B61110B681}\Namespaces`
- `0x1800379a4`: `.wdp\OpenWithProgids`
- `0x180037a19`: `@wmphoto.dll,-500`
- `0x180037a5e`: `wdpfile\shell\printto\command`
- `0x180037a71`: `rundll32.exe %SystemRoot%\system32\shimgvw.dll,ImageView_PrintTo /pt "%1" "%2" "%3" "%4"`
- `0x180037a99`: `wdpfile\shell\print\command`
- `0x180037aac`: `rundll32.exe %SystemRoot%\system32\shimgvw.dll,ImageView_Fullscreen %1`
- `0x180037b77`: `Clsid`
- `0x180037c3e`: `CLSID\%38s\Formats\{6FDDC324-4E03-4BFE-B185-3D77768DC9%02X}`
- `0x180037c79`: `CLSID\%38s\Formats\{6FDDC324-4E03-4BFE-B185-3D77768DC9%02X}`

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
  RegisterKey(HKEY_CLASSES_ROOT, v18, L"wdpfile", 0, &word_18004808A, 0);
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
    LODWORD(v5) = *((unsigned __int8 *)qword_180048E30 + i);
    StringCchPrintfW(v18, 0x104u, L"CLSID\\%38s\\Formats\\{6FDDC324-4E03-4BFE-B185-3D77768DC9%02X}", v23, v5);
    RegisterKey(HKEY_CLASSES_ROOT, v18, 0, 1u, &dword_18004808C, 0);
    LODWORD(v6) = *((unsigned __int8 *)qword_180048E30 + i);
    StringCchPrintfW(v18, 0x104u, L"CLSID\\%38s\\Formats\\{6FDDC324-4E03-4BFE-B185-3D77768DC9%02X}", v24, v6);
    RegisterKey(HKEY_CLASSES_ROOT, v18, 0, 1u, &dword_18004808C, 0);
  }
  if ( (unsigned __int8)IsSHChangeNotifyPresent() )
    SHChangeNotify(0x8000000, 0, 0, 0);
  return 0;
}

```

## disassembly

```asm
0x180036fe0  push    rbp
0x180036fe2  push    rbx
0x180036fe3  push    rsi
0x180036fe4  push    rdi
0x180036fe5  push    r12
0x180036fe7  push    r13
0x180036fe9  push    r14
0x180036feb  push    r15
0x180036fed  lea     rbp, [rsp-0AB8h]
0x180036ff5  sub     rsp, 0BB8h
0x180036ffc  mov     rax, cs:__security_cookie
0x180037003  xor     rax, rsp
0x180037006  mov     [rbp+0AF0h+var_50], rax
0x18003700d  movups  xmm0, xmmword ptr cs:aImageVndMsPhot; "image/vnd.ms-photo"
0x180037014  xor     esi, esi
0x180037016  mov     ebx, 208h
0x18003701b  movups  xmm1, xmmword ptr cs:aImageVndMsPhot+10h; "d.ms-photo"
0x180037022  mov     r8d, ebx; Size
0x180037025  xor     edx, edx; Val
0x180037027  movups  [rsp+0BF0h+var_B90], xmm0
0x18003702c  lea     rcx, [rbp+0AF0h+Filename]; void *
0x180037033  mov     [rsp+0BF0h+var_BC0], 0FFFFFFFFh
0x18003703b  movsd   xmm0, qword ptr cs:aImageVndMsPhot+1Eh; "oto"
0x180037043  movups  xmmword ptr [rsp+0BF0h+var_B80], xmm1
0x180037048  mov     [rsp+0BF0h+var_BBC], 0BC4949h
0x180037050  movsd   qword ptr [rsp+0BF0h+var_B80+0Eh], xmm0
0x180037056  mov     [rsp+0BF0h+var_BB8], 1BC4949h
0x18003705e  mov     [rsp+0BF0h+var_BA8], esi
0x180037062  mov     [rsp+0BF0h+var_BA4], esi
0x180037066  mov     [rsp+0BF0h+var_BA0], esi
0x18003706a  mov     [rsp+0BF0h+var_B9C], 1
0x180037072  mov     [rsp+0BF0h+var_B98], esi
0x180037076  call    memset_0
0x18003707b  mov     r8d, ebx; Size
0x18003707e  lea     rcx, [rbp+0AF0h+var_B60]; void *
0x180037082  xor     edx, edx; Val
0x180037084  call    memset_0
0x180037089  mov     r8d, ebx; Size
0x18003708c  mov     [rsp+0BF0h+lpsz], rsi
0x180037091  xor     edx, edx; Val
0x180037093  lea     rcx, [rbp+0AF0h+var_890]; void *
0x18003709a  call    memset_0
0x18003709f  mov     r8d, ebx; Size
0x1800370a2  lea     rcx, [rbp+0AF0h+var_680]; void *
0x1800370a9  xor     edx, edx; Val
0x1800370ab  call    memset_0
0x1800370b0  mov     r8d, ebx; Size
0x1800370b3  lea     rcx, [rbp+0AF0h+var_260]; void *
0x1800370ba  xor     edx, edx; Val
0x1800370bc  call    memset_0
0x1800370c1  lea     rdx, [rsp+0BF0h+lpsz]; lplpsz
0x1800370c6  lea     rcx, CLSID_WICWmpDecoder; rclsid
0x1800370cd  call    cs:__imp_StringFromIID
0x1800370d3  mov     r8, [rsp+0BF0h+lpsz]; unsigned __int16 *
0x1800370d8  test    r8, r8
0x1800370db  jz      short loc_1800370F4
0x1800370dd  lea     rcx, [rbp+0AF0h+var_890]; unsigned __int16 *
0x1800370e4  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800370e9  mov     rcx, [rsp+0BF0h+lpsz]; pv
0x1800370ee  call    cs:__imp_CoTaskMemFree
0x1800370f4  lea     rdx, [rsp+0BF0h+lpsz]; lplpsz
0x1800370f9  lea     rcx, CLSID_WICWmpEncoder; rclsid
0x180037100  call    cs:__imp_StringFromIID
0x180037106  mov     r8, [rsp+0BF0h+lpsz]; unsigned __int16 *
0x18003710b  test    r8, r8
0x18003710e  jz      short loc_180037127
0x180037110  lea     rcx, [rbp+0AF0h+var_680]; unsigned __int16 *
0x180037117  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18003711c  mov     rcx, [rsp+0BF0h+lpsz]; pv
0x180037121  call    cs:__imp_CoTaskMemFree
0x180037127  lea     rdx, [rsp+0BF0h+lpsz]; lplpsz
0x18003712c  lea     rcx, CLSID_WmpImageDecodeFilter; rclsid
0x180037133  call    cs:__imp_StringFromIID
0x180037139  mov     r8, [rsp+0BF0h+lpsz]; unsigned __int16 *
0x18003713e  test    r8, r8
0x180037141  jz      short loc_18003715A
0x180037143  lea     rcx, [rbp+0AF0h+var_260]; unsigned __int16 *
0x18003714a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18003714f  mov     rcx, [rsp+0BF0h+lpsz]; pv
0x180037154  call    cs:__imp_CoTaskMemFree
0x18003715a  mov     rcx, cs:?g_hInstWMPCodec@@3PEAUHINSTANCE__@@EA; hModule
0x180037161  lea     rdx, [rbp+0AF0h+Filename]; lpFilename
0x180037168  mov     ebx, 104h
0x18003716d  mov     r8d, ebx; nSize
0x180037170  call    cs:__imp_GetModuleFileNameW
0x180037176  lea     r9, [rbp+0AF0h+var_890]
0x18003717d  mov     edx, ebx; unsigned __int64
0x18003717f  lea     r8, aClsid38s; "CLSID\\%38s"
0x180037186  lea     rcx, [rbp+0AF0h+var_B60]; unsigned __int16 *
0x18003718a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003718f  mov     ebx, 1
0x180037194  mov     [rsp+0BF0h+var_BC8], esi; unsigned int
0x180037198  mov     r14, 0FFFFFFFF80000000h
0x18003719f  lea     r15, aMicrosoft; "Microsoft"
0x1800371a6  mov     r9d, ebx; unsigned int
0x1800371a9  mov     [rsp+0BF0h+var_BD0], r15; void *
0x1800371ae  mov     rcx, r14; HKEY
0x1800371b1  lea     r8, aAuthor; "Author"
0x1800371b8  lea     rdx, [rbp+0AF0h+var_B60]; unsigned __int16 *
0x1800371bc  call    ?RegisterKey@@YAHPEAUHKEY__@@PEBG1KPEBXK@Z; RegisterKey(HKEY__ *,ushort const *,ushort const *,ulong,void const *,ulong)
0x1800371c1  lea     r13, a1000; "1.0.0.0"
0x1800371c8  mov     [rsp+0BF0h+var_BC8], esi; unsigned int
0x1800371cc  mov     r9d, ebx; unsigned int
0x1800371cf  mov     [rsp+0BF0h+var_BD0], r13; void *
0x1800371d4  lea     r8, aColormanagemen; "ColorManagementVersion"
0x1800371db  mov     rcx, r14; HKEY
0x1800371de  lea     rdx, [rbp+0AF0h+var_B60]; unsigned __int16 *
0x1800371e2  call    ?RegisterKey@@YAHPEAUHKEY__@@PEBG1KPEBXK@Z; RegisterKey(HKEY__ *,ushort const *,ushort const *,ulong,void const *,ulong)
0x1800371e7  lea     rax, a57a37caa367a45; "{57A37CAA-367A-4540-916B-F183C5093A4B}"
0x1800371ee  mov     [rsp+0BF0h+var_BC8], esi; unsigned int
0x1800371f2  mov     r9d, ebx; unsigned int
0x1800371f5  mov     [rsp+0BF0h+var_BD0], rax; void *
0x1800371fa  lea     r8, aContainerforma; "ContainerFormat"
0x180037201  mov     rcx, r14; HKEY
0x180037204  lea     rdx, [rbp+0AF0h+var_B60]; unsigned __int16 *
0x180037208  call    ?RegisterKey@@YAHPEAUHKEY__@@PEBG1KPEBXK@Z; RegisterKey(HKEY__ *,ushort const *,ushort const *,ulong,void const *,ulong)
0x18003720d  lea     rax, aWdp_0; ".wdp"
0x180037214  mov     [rsp+0BF0h+var_BC8], esi; unsigned int
0x180037218  mov     r9d, ebx; unsigned int
0x18003721b  mov     [rsp+0BF0h+var_BD0], rax; void *
0x180037220  lea     r8, aFileextensions; "FileExtensions"
0x180037227  mov     rcx, r14; HKEY
0x18003722a  lea     rdx, [rbp+0AF0h+var_B60]; unsigned __int16 *
0x18003722e  call    ?RegisterKey@@YAHPEAUHKEY__@@PEBG1KPEBXK@Z; RegisterKey(HKEY__ *,ushort const *,ushort const *,ulong,void const *,ulong)
0x180037233  lea     rdi, aWmphotoDecoder; "WMPhoto Decoder"
0x18003723a  mov     [rsp+0BF0h+var_BC8], esi; unsigned int
0x18003723e  mov     r9d, ebx; unsigned int
0x180037241  mov     [rsp+0BF0h+var_BD0], rdi; void *
0x180037246  lea     r8, aFriendlyname; "FriendlyName"
0x18003724d  mov     rcx, r14; HKEY
0x180037250  lea     rdx, [rbp+0AF0h+var_B60]; unsigned __int16 *
0x180037254  call    ?RegisterKey@@YAHPEAUHKEY__@@PEBG1KPEBXK@Z; RegisterKey(HKEY__ *,ushort const *,ushort const *,ulong,void const *,ulong)
0x180037259  lea     rax, [rsp+0BF0h+var_B90]
0x18003725e  mov     [rsp+0BF0h+var_BC8], esi; unsigned int
0x180037262  mov     r9d, ebx; unsigned int
0x180037265  mov     [rsp+0BF0h+var_BD0], rax; void *
0x18003726a  lea     r8, aMimetypes; "MimeTypes"
0x180037271  mov     rcx, r14; HKEY
0x180037274  lea     rdx, [rbp+0AF0h+var_B60]; unsigned __int16 *
0x180037278  call    ?RegisterKey@@YAHPEAUHKEY__@@PEBG1KPEBXK@Z; RegisterKey(HKEY__ *,ushort const *,ushort const *,ulong,void const *,ulong)
0x18003727d  mov     r9d, ebx; unsigned int
0x180037280  mov     [rsp+0BF0h+var_BC8], esi; unsigned int
0x180037284  lea     r8, aSpecversion; "SpecVersion"
0x18003728b  mov     [rsp+0BF0h+var_BD0], r13; void *
0x180037290  lea     rdx, [rbp+0AF0h+var_B60]; unsigned __int16 *
0x180037294  mov     rcx, r14; HKEY
0x180037297  call    ?RegisterKey@@YAHPEAUHKEY__@@PEBG1KPEBXK@Z; RegisterKey(HKEY__ *,ushort const *,ushort const *,ulong,void const *,ulong)
0x18003729c  lea     r12d, [rbx+3]
0x1800372a0  mov     rcx, r14; HKEY
0x1800372a3  lea     rax, [rsp+0BF0h+var_BA4]
0x1800372a8  mov     [rsp+0BF0h+var_BC8], r12d; unsigned int
0x1800372ad  mov     r9d, r12d; unsigned int
0x1800372b0  mov     [rsp+0BF0h+var_BD0], rax; void *
0x1800372b5  lea     r8, aSupportanimati; "SupportAnimation"
0x1800372bc  lea     rdx, [rbp+0AF0h+var_B60]; unsigned __int16 *
0x1800372c0  call    ?RegisterKey@@YAHPEAUHKEY__@@PEBG1KPEBXK@Z; RegisterKey(HKEY__ *,ushort const *,ushort const *,ulong,void const *,ulong)
0x1800372c5  lea     rax, [rsp+0BF0h+var_BA0]
0x1800372ca  mov     [rsp+0BF0h+var_BC8], r12d; unsigned int
0x1800372cf  mov     [rsp+0BF0h+var_BD0], rax; void *
0x1800372d4  lea     r8, aSupportchromak; "SupportChromakey"
0x1800372db  mov     r9d, r12d; unsigned int
0x1800372de  lea     rdx, [rbp+0AF0h+var_B60]; unsigned __int16 *
0x1800372e2  mov     rcx, r14; HKEY
0x1800372e5  call    ?RegisterKey@@YAHPEAUHKEY__@@PEBG1KPEBXK@Z; RegisterKey(HKEY__ *,ushort const *,ushort const *,ulong,void const *,ulong)
0x1800372ea  lea     rax, [rsp+0BF0h+var_B9C]
0x1800372ef  mov     [rsp+0BF0h+var_BC8], r12d; unsigned int
0x1800372f4  mov     r9d, r12d; unsigned int
0x1800372f7  mov     [rsp+0BF0h+var_BD0], rax; void *
0x1800372fc  lea     r8, aSupportlossles; "SupportLossless"
0x180037303  mov     rcx, r14; HKEY
0x180037306  lea     rdx, [rbp+0AF0h+var_B60]; unsigned __int16 *
0x18003730a  call    ?RegisterKey@@YAHPEAUHKEY__@@PEBG1KPEBXK@Z; RegisterKey(HKEY__ *,ushort const *,ushort const *,ulong,void const *,ulong)
0x18003730f  lea     rax, [rsp+0BF0h+var_B98]
0x180037314  mov     [rsp+0BF0h+var_BC8], r12d; unsigned int
0x180037319  mov     r9d, r12d; unsigned int
0x18003731c  mov     [rsp+0BF0h+var_BD0], rax; void *
0x180037321  lea     r8, aSupportmultifr; "SupportMultiframe"
0x180037328  mov     rcx, r14; HKEY
0x18003732b  lea     rdx, [rbp+0AF0h+var_B60]; unsigned __int16 *
0x18003732f  call    ?RegisterKey@@YAHPEAUHKEY__@@PEBG1KPEBXK@Z; RegisterKey(HKEY__ *,ushort const *,ushort const *,ulong,void const *,ulong)
0x180037334  lea     r14, aF0e749caEdef45; "{F0E749CA-EDEF-4589-A73A-EE0E626A2A2B}"
0x18003733b  mov     [rsp+0BF0h+var_BC8], esi; unsigned int
0x18003733f  mov     r9d, ebx; unsigned int
0x180037342  mov     [rsp+0BF0h+var_BD0], r14; void *
0x180037347  lea     r8, aVendor; "Vendor"
0x18003734e  mov     rcx, 0FFFFFFFF80000000h; HKEY
0x180037355  lea     rdx, [rbp+0AF0h+var_B60]; unsigned __int16 *
0x180037359  call    ?RegisterKey@@YAHPEAUHKEY__@@PEBG1KPEBXK@Z; RegisterKey(HKEY__ *,ushort const *,ushort const *,ulong,void const *,ulong)
0x18003735e  mov     r9d, ebx; unsigned int
0x180037361  mov     [rsp+0BF0h+var_BC8], esi; unsigned int
0x180037365  lea     r8, aVersion; "Version"
0x18003736c  mov     [rsp+0BF0h+var_BD0], r13; void *
0x180037371  lea     rdx, [rbp+0AF0h+var_B60]; unsigned __int16 *
0x180037375  mov     rcx, 0FFFFFFFF80000000h; HKEY
0x18003737c  call    ?RegisterKey@@YAHPEAUHKEY__@@PEBG1KPEBXK@Z; RegisterKey(HKEY__ *,ushort const *,ushort const *,ulong,void const *,ulong)
0x180037381  lea     r9, [rbp+0AF0h+var_890]
0x180037388  mov     edx, 104h; unsigned __int64
0x18003738d  lea     r8, aClsid38sInproc; "CLSID\\%38s\\InprocServer32"
0x180037394  lea     rcx, [rbp+0AF0h+var_B60]; unsigned __int16 *
0x180037398  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003739d  lea     rax, [rbp+0AF0h+Filename]
0x1800373a4  mov     [rsp+0BF0h+var_BC8], esi; unsigned int
0x1800373a8  mov     r9d, ebx; unsigned int
0x1800373ab  mov     [rsp+0BF0h+var_BD0], rax; void *
0x1800373b0  xor     r8d, r8d; unsigned __int16 *
0x1800373b3  lea     rdx, [rbp+0AF0h+var_B60]; unsigned __int16 *
0x1800373b7  mov     rcx, 0FFFFFFFF80000000h; HKEY
0x1800373be  call    ?RegisterKey@@YAHPEAUHKEY__@@PEBG1KPEBXK@Z; RegisterKey(HKEY__ *,ushort const *,ushort const *,ulong,void const *,ulong)
0x1800373c3  mov     [rsp+0BF0h+var_BC8], esi; unsigned int
0x1800373c7  lea     r8, aThreadingmodel; "ThreadingModel"
0x1800373ce  lea     rsi, aBoth; "Both"
0x1800373d5  mov     r9d, ebx; unsigned int
0x1800373d8  lea     rdx, [rbp+0AF0h+var_B60]; unsigned __int16 *
0x1800373dc  mov     [rsp+0BF0h+var_BD0], rsi; void *
0x1800373e1  mov     rcx, 0FFFFFFFF80000000h; HKEY
0x1800373e8  call    ?RegisterKey@@YAHPEAUHKEY__@@PEBG1KPEBXK@Z; RegisterKey(HKEY__ *,ushort const *,ushort const *,ulong,void const *,ulong)
0x1800373ed  lea     r9, [rbp+0AF0h+var_890]
0x1800373f4  mov     edx, 104h; unsigned __int64
0x1800373f9  lea     r8, aClsid38sPatter; "CLSID\\%38s\\Patterns\\0"
0x180037400  lea     rcx, [rbp+0AF0h+var_B60]; unsigned __int16 *
0x180037404  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180037409  lea     rax, [rsp+0BF0h+var_BC0]
0x18003740e  mov     [rsp+0BF0h+var_BC8], r12d; unsigned int
0x180037413  lea     ebx, [r12-1]
0x180037418  mov     [rsp+0BF0h+var_BD0], rax; void *
0x18003741d  mov     r9d, ebx; unsigned int
0x180037420  lea     r8, aMask; "Mask"
0x180037427  lea     rdx, [rbp+0AF0h+var_B60]; unsigned __int16 *
0x18003742b  mov     rcx, 0FFFFFFFF80000000h; HKEY
0x180037432  call    ?RegisterKey@@YAHPEAUHKEY__@@PEBG1KPEBXK@Z; RegisterKey(HKEY__ *,ushort const *,ushort const *,ulong,void const *,ulong)
0x180037437  lea     rax, [rsp+0BF0h+var_BBC]
0x18003743c  mov     [rsp+0BF0h+var_BC8], r12d; unsigned int
0x180037441  mov     r9d, ebx; unsigned int
0x180037444  mov     [rsp+0BF0h+var_BD0], rax; void *
0x180037449  lea     r8, aPattern; "Pattern"
0x180037450  mov     rcx, 0FFFFFFFF80000000h; HKEY
0x180037457  lea     rdx, [rbp+0AF0h+var_B60]; unsigned __int16 *
0x18003745b  call    ?RegisterKey@@YAHPEAUHKEY__@@PEBG1KPEBXK@Z; RegisterKey(HKEY__ *,ushort const *,ushort const *,ulong,void const *,ulong)
0x180037460  lea     rax, [rsp+0BF0h+var_BA8]
0x180037465  mov     [rsp+0BF0h+var_BC8], r12d; unsigned int
0x18003746a  mov     [rsp+0BF0h+var_BD0], rax; void *
0x18003746f  mov     r9d, r12d; unsigned int
0x180037472  lea     r8, aPosition; "Position"
0x180037479  mov     rcx, 0FFFFFFFF80000000h; HKEY
0x180037480  lea     rdx, [rbp+0AF0h+var_B60]; unsigned __int16 *
0x180037484  call    ?RegisterKey@@YAHPEAUHKEY__@@PEBG1KPEBXK@Z; RegisterKey(HKEY__ *,ushort const *,ushort const *,ulong,void const *,ulong)
0x180037489  lea     r9, [rbp+0AF0h+var_890]
0x180037490  mov     edx, 104h; unsigned __int64
0x180037495  lea     r8, aClsid38sPatter_0; "CLSID\\%38s\\Patterns\\1"
0x18003749c  lea     rcx, [rbp+0AF0h+var_B60]; unsigned __int16 *
0x1800374a0  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800374a5  lea     rax, [rsp+0BF0h+var_BC0]
0x1800374aa  mov     [rsp+0BF0h+var_BC8], r12d; unsigned int
0x1800374af  mov     r9d, ebx; unsigned int
0x1800374b2  mov     [rsp+0BF0h+var_BD0], rax; void *
0x1800374b7  lea     r8, aMask; "Mask"
0x1800374be  mov     rcx, 0FFFFFFFF80000000h; HKEY
0x1800374c5  lea     rdx, [rbp+0AF0h+var_B60]; unsigned __int16 *
0x1800374c9  call    ?RegisterKey@@YAHPEAUHKEY__@@PEBG1KPEBXK@Z; RegisterKey(HKEY__ *,ushort const *,ushort const *,ulong,void const *,ulong)
0x1800374ce  mov     r9d, ebx; unsigned int
0x1800374d1  mov     [rsp+0BF0h+var_BC8], r12d; unsigned int
0x1800374d6  lea     rax, [rsp+0BF0h+var_BB8]
0x1800374db  mov     rbx, 0FFFFFFFF80000000h
0x1800374e2  mov     rcx, rbx; HKEY
0x1800374e5  mov     [rsp+0BF0h+var_BD0], rax; void *
0x1800374ea  lea     r8, aPattern; "Pattern"
0x1800374f1  lea     rdx, [rbp+0AF0h+var_B60]; unsigned __int16 *
0x1800374f5  call    ?RegisterKey@@YAHPEAUHKEY__@@PEBG1KPEBXK@Z; RegisterKey(HKEY__ *,ushort const *,ushort const *,ulong,void const *,ulong)
0x1800374fa  lea     rax, [rsp+0BF0h+var_BA8]
0x1800374ff  mov     [rsp+0BF0h+var_BC8], r12d; unsigned int
0x180037504  mov     r9d, r12d; unsigned int
0x180037507  mov     [rsp+0BF0h+var_BD0], rax; void *
0x18003750c  lea     r8, aPosition; "Position"
0x180037513  mov     rcx, rbx; HKEY
0x180037516  lea     rdx, [rbp+0AF0h+var_B60]; unsigned __int16 *
0x18003751a  call    ?RegisterKey@@YAHPEAUHKEY__@@PEBG1KPEBXK@Z; RegisterKey(HKEY__ *,ushort const *,ushort const *,ulong,void const *,ulong)
0x18003751f  lea     r9, [rbp+0AF0h+var_890]
0x180037526  mov     edx, 104h; unsigned __int64
0x18003752b  lea     r8, aClsid7ed968379; "CLSID\\{7ED96837-96F0-4812-B211-F13C241"...
0x180037532  lea     rcx, [rbp+0AF0h+var_B60]; unsigned __int16 *
0x180037536  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003753b  lea     rax, [rbp+0AF0h+var_890]
0x180037542  xor     ebx, ebx
0x180037544  mov     [rsp+0BF0h+var_BC8], ebx; unsigned int
0x180037548  lea     r9d, [r12-3]; unsigned int
0x18003754d  lea     r8, aClsid_0; "CLSID"
0x180037554  mov     [rsp+0BF0h+var_BD0], rax; void *
0x180037559  lea     rdx, [rbp+0AF0h+var_B60]; unsigned __int16 *
0x18003755d  mov     rcx, 0FFFFFFFF80000000h; HKEY
0x180037564  call    ?RegisterKey@@YAHPEAUHKEY__@@PEBG1KPEBXK@Z; RegisterKey(HKEY__ *,ushort const *,ushort const *,ulong,void const *,ulong)
0x180037569  mov     [rsp+0BF0h+var_BC8], ebx; unsigned int
0x18003756d  lea     r9d, [r12-3]; unsigned int
0x180037572  mov     [rsp+0BF0h+var_BD0], rdi; void *
0x180037577  lea     rdx, [rbp+0AF0h+var_B60]; unsigned __int16 *
0x18003757b  lea     rdi, aFriendlyname; "FriendlyName"
0x180037582  mov     rcx, 0FFFFFFFF80000000h; HKEY
0x180037589  mov     r8, rdi; unsigned __int16 *
0x18003758c  call    ?RegisterKey@@YAHPEAUHKEY__@@PEBG1KPEBXK@Z; RegisterKey(HKEY__ *,ushort const *,ushort const *,ulong,void const *,ulong)
0x180037591  lea     r9, [rbp+0AF0h+var_680]
0x180037598  mov     edx, 104h; unsigned __int64
  ... truncated ...
```
