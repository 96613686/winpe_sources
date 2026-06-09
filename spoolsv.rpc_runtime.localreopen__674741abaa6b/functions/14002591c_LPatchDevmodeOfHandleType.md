# LPatchDevmodeOfHandleType

- ea: `0x14002591c`
- end: `0x140025c35`
- name: `LPatchDevmodeOfHandleType`
- size: `793`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x140006160`

## callees

- `0x14000645c`
- `0x14000d060`
- `0x14000f270`
- `0x1400177c4`
- `0x140019380`
- `0x140019410`
- `0x14002591c`
- `0x14002d0a0`
- `0x14007ed18`
- `0x14007ee50`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x140025bcd`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x140025be1`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x140025bcd`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x140025be1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140025af3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140025af3`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140025ba2`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140025ba2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400259ff`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140025a51`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140025abc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400259ff`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140025a51`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140025abc`

## string_xrefs

- `0x140025b32`: `Read devmode %ws. Status : %d`
- `0x140025b04`: `Opened handle. Status : %d`

## pseudocode

```c
__int64 __fastcall LPatchDevmodeOfHandleType(int a1, const unsigned __int16 *a2)
{
  __int64 v4; // rdx
  const WCHAR *v6; // r14
  WCHAR *v7; // rdx
  __int64 v8; // rcx
  __int64 v9; // rbx
  unsigned int v10; // eax
  void *v11; // rsi
  int v12; // eax
  BYTE *v13; // rdi
  HKEY hKey; // [rsp+30h] [rbp-D0h] BYREF
  int v15; // [rsp+38h] [rbp-C8h] BYREF
  void *Block; // [rsp+48h] [rbp-B8h] BYREF
  BYTE *lpData; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR SubKey[264]; // [rsp+60h] [rbp-A0h] BYREF

  Block = 0;
  lpData = 0;
  hKey = 0;
  v15 = 0;
  if ( !a2 )
    goto LABEL_25;
  v4 = -1;
  do
    ++v4;
  while ( a2[v4] );
  if ( !(unsigned int)IsValidPrinterName(a2, v4) )
  {
LABEL_25:
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    return 1801;
  }
  DevmodeSizePatchTelemetry::WriteDbgTraceInfo("LPatchDevmodeOfHandleType", L"START INDIVIDUAL PATCH:  %ws", a2);
  if ( a1 )
  {
    if ( a1 == 1 )
    {
      DevmodeSizePatchTelemetry::WriteDbgTraceInfo("LPatchDevmodeOfHandleType", L"PerUser Devmode");
      v6 = a2;
      v7 = L"Printers\\DevModePerUser";
    }
    else
    {
      if ( a1 != 2 )
      {
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
        return 87;
      }
      DevmodeSizePatchTelemetry::WriteDbgTraceInfo("LPatchDevmodeOfHandleType", L"Devmode2");
      v6 = a2;
      v7 = L"Printers\\DevModes2";
    }
    v8 = -2147483647;
    goto LABEL_14;
  }
  DevmodeSizePatchTelemetry::WriteDbgTraceInfo("LPatchDevmodeOfHandleType", L"Default Devmode");
  v6 = L"Default DevMode";
  LODWORD(v9) = StringCchPrintfW(
                  SubKey,
                  0x104u,
                  L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Print\\Printers\\%s",
                  a2);
  if ( !(_DWORD)v9 )
  {
    v7 = SubKey;
    v8 = -2147483646;
LABEL_14:
    hKey = 0;
    LODWORD(v9) = RegOpenKeyExW((HKEY)v8, v7, 0, 3u, &hKey);
  }
  DevmodeSizePatchTelemetry::WriteDbgTraceInfo(
    "LPatchDevmodeOfHandleType",
    L"Opened handle. Status : %d",
    (unsigned int)v9);
  if ( !(_DWORD)v9 )
  {
    v10 = LGetDevMode(hKey, v6, (struct _devicemodeW **)&Block);
    v11 = Block;
    LODWORD(v9) = v10;
    DevmodeSizePatchTelemetry::WriteDbgTraceInfo(
      "LPatchDevmodeOfHandleType",
      L"Read devmode %ws. Status : %d",
      Block,
      v10);
    if ( !(_DWORD)v9 )
    {
      v12 = LVerifyAndCorrectDevMode(v11, &lpData, &v15, a2, a1);
      v13 = lpData;
      LODWORD(v9) = v12;
      if ( !v12 && !v15 )
      {
        v9 = (unsigned int)RegSetValueExW(
                             hKey,
                             v6,
                             0,
                             3u,
                             lpData,
                             *((unsigned __int16 *)lpData + 34) + *((unsigned __int16 *)lpData + 35));
        DevmodeSizePatchTelemetry::WriteDbgTraceInfo(
          "LPatchDevmodeOfHandleType",
          L"Set devmode %ws. Status : %d",
          v11,
          v9);
      }
      if ( v13 )
        free(v13);
    }
    if ( v11 )
      free(v11);
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x14002591c  mov     [rsp-8+arg_10], rbx
0x140025921  push    rbp
0x140025922  push    rsi
0x140025923  push    rdi
0x140025924  push    r12
0x140025926  push    r13
0x140025928  push    r14
0x14002592a  push    r15
0x14002592c  lea     rbp, [rsp-180h]
0x140025934  sub     rsp, 280h
0x14002593b  mov     rax, cs:__security_cookie
0x140025942  xor     rax, rsp
0x140025945  mov     [rbp+1B0h+var_40], rax
0x14002594c  xor     r12d, r12d
0x14002594f  mov     rdi, rdx
0x140025952  mov     [rsp+2B0h+Block], r12
0x140025957  mov     r15d, ecx
0x14002595a  mov     [rsp+2B0h+lpData], r12
0x14002595f  mov     [rsp+2B0h+hKey], r12
0x140025964  mov     [rsp+2B0h+var_278], r12d
0x140025969  test    rdx, rdx
0x14002596c  jz      loc_140025BFB
0x140025972  or      rdx, 0FFFFFFFFFFFFFFFFh
0x140025976  inc     rdx; unsigned int
0x140025979  cmp     [rdi+rdx*2], r12w
0x14002597e  jnz     short loc_140025976
0x140025980  mov     rcx, rdi; unsigned __int16 *
0x140025983  call    ?IsValidPrinterName@@YAHPEBGK@Z; IsValidPrinterName(ushort const *,ulong)
0x140025988  test    eax, eax
0x14002598a  jz      loc_140025BFB
0x140025990  lea     r13, aLpatchdevmodeo; "LPatchDevmodeOfHandleType"
0x140025997  mov     r8, rdi
0x14002599a  mov     rcx, r13; char *
0x14002599d  lea     rdx, aStartIndividua; "START INDIVIDUAL PATCH:  %ws"
0x1400259a4  call    ?WriteDbgTraceInfo@DevmodeSizePatchTelemetry@@SAXPEADPEAGZZ; DevmodeSizePatchTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1400259a9  mov     ecx, r15d
0x1400259ac  mov     esi, 3
0x1400259b1  test    r15d, r15d
0x1400259b4  jz      loc_140025A70
0x1400259ba  sub     ecx, 1
0x1400259bd  jz      short loc_140025A28
0x1400259bf  cmp     ecx, 1
0x1400259c2  jz      short loc_1400259D6
0x1400259c4  lea     rcx, [rsp+2B0h+hKey]
0x1400259c9  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1400259ce  lea     eax, [rsi+54h]
0x1400259d1  jmp     loc_140025C0A
0x1400259d6  lea     rdx, aDevmode2; "Devmode2"
0x1400259dd  mov     rcx, r13; char *
0x1400259e0  call    ?WriteDbgTraceInfo@DevmodeSizePatchTelemetry@@SAXPEADPEAGZZ; DevmodeSizePatchTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1400259e5  mov     rbx, [rsp+2B0h+hKey]
0x1400259ea  mov     r14, rdi
0x1400259ed  test    rbx, rbx
0x1400259f0  jz      short loc_140025A15
0x1400259f2  lea     rcx, [rsp+2B0h+var_270]; this
0x1400259f7  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1400259fc  mov     rcx, rbx; hKey
0x1400259ff  call    cs:__imp_RegCloseKey
0x140025a06  nop     dword ptr [rax+rax+00h]
0x140025a0b  lea     rcx, [rsp+2B0h+var_270]; this
0x140025a10  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x140025a15  lea     rdx, aPrintersDevmod_0; "Printers\\DevModes2"
0x140025a1c  mov     rcx, 0FFFFFFFF80000001h
0x140025a23  jmp     loc_140025ADE
0x140025a28  lea     rdx, aPeruserDevmode; "PerUser Devmode"
0x140025a2f  mov     rcx, r13; char *
0x140025a32  call    ?WriteDbgTraceInfo@DevmodeSizePatchTelemetry@@SAXPEADPEAGZZ; DevmodeSizePatchTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x140025a37  mov     rbx, [rsp+2B0h+hKey]
0x140025a3c  mov     r14, rdi
0x140025a3f  test    rbx, rbx
0x140025a42  jz      short loc_140025A67
0x140025a44  lea     rcx, [rsp+2B0h+var_270]; this
0x140025a49  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x140025a4e  mov     rcx, rbx; hKey
0x140025a51  call    cs:__imp_RegCloseKey
0x140025a58  nop     dword ptr [rax+rax+00h]
0x140025a5d  lea     rcx, [rsp+2B0h+var_270]; this
0x140025a62  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x140025a67  lea     rdx, aPrintersDevmod; "Printers\\DevModePerUser"
0x140025a6e  jmp     short loc_140025A1C
0x140025a70  lea     rdx, aDefaultDevmode; "Default Devmode"
0x140025a77  mov     rcx, r13; char *
0x140025a7a  call    ?WriteDbgTraceInfo@DevmodeSizePatchTelemetry@@SAXPEADPEAGZZ; DevmodeSizePatchTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x140025a7f  mov     r9, rdi
0x140025a82  lea     r8, aSoftwareMicros_1; "Software\\Microsoft\\Windows NT\\Curren"...
0x140025a89  mov     edx, 104h; unsigned __int64
0x140025a8e  lea     rcx, [rsp+2B0h+SubKey]; unsigned __int16 *
0x140025a93  lea     r14, ValueName; "Default DevMode"
0x140025a9a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140025a9f  mov     ebx, eax
0x140025aa1  test    eax, eax
0x140025aa3  jnz     short loc_140025B01
0x140025aa5  mov     rbx, [rsp+2B0h+hKey]
0x140025aaa  test    rbx, rbx
0x140025aad  jz      short loc_140025AD2
0x140025aaf  lea     rcx, [rsp+2B0h+var_270]; this
0x140025ab4  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x140025ab9  mov     rcx, rbx; hKey
0x140025abc  call    cs:__imp_RegCloseKey
0x140025ac3  nop     dword ptr [rax+rax+00h]
0x140025ac8  lea     rcx, [rsp+2B0h+var_270]; this
0x140025acd  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x140025ad2  lea     rdx, [rsp+2B0h+SubKey]; lpSubKey
0x140025ad7  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140025ade  lea     rax, [rsp+2B0h+hKey]
0x140025ae3  mov     [rsp+2B0h+hKey], r12
0x140025ae8  mov     r9d, esi; samDesired
0x140025aeb  mov     [rsp+2B0h+phkResult], rax; phkResult
0x140025af0  xor     r8d, r8d; ulOptions
0x140025af3  call    cs:__imp_RegOpenKeyExW
0x140025afa  nop     dword ptr [rax+rax+00h]
0x140025aff  mov     ebx, eax
0x140025b01  mov     r8d, ebx
0x140025b04  lea     rdx, aOpenedHandleSt; "Opened handle. Status : %d"
0x140025b0b  mov     rcx, r13; char *
0x140025b0e  call    ?WriteDbgTraceInfo@DevmodeSizePatchTelemetry@@SAXPEADPEAGZZ; DevmodeSizePatchTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x140025b13  test    ebx, ebx
0x140025b15  jnz     loc_140025BED
0x140025b1b  mov     rcx, [rsp+2B0h+hKey]; hKey
0x140025b20  lea     r8, [rsp+2B0h+Block]; struct _devicemodeW **
0x140025b25  mov     rdx, r14; lpValueName
0x140025b28  call    ?LGetDevMode@@YAJPEAUHKEY__@@PEBGPEAPEAU_devicemodeW@@@Z; LGetDevMode(HKEY__ *,ushort const *,_devicemodeW * *)
0x140025b2d  mov     rsi, [rsp+2B0h+Block]
0x140025b32  lea     rdx, aReadDevmodeWsS; "Read devmode %ws. Status : %d"
0x140025b39  mov     r8, rsi
0x140025b3c  mov     r9d, eax
0x140025b3f  mov     rcx, r13; char *
0x140025b42  mov     ebx, eax
0x140025b44  call    ?WriteDbgTraceInfo@DevmodeSizePatchTelemetry@@SAXPEADPEAGZZ; DevmodeSizePatchTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x140025b49  test    ebx, ebx
0x140025b4b  jnz     loc_140025BD9
0x140025b51  mov     r9, rdi
0x140025b54  mov     dword ptr [rsp+2B0h+phkResult], r15d
0x140025b59  lea     r8, [rsp+2B0h+var_278]
0x140025b5e  mov     rcx, rsi
0x140025b61  lea     rdx, [rsp+2B0h+lpData]
0x140025b66  call    ?LVerifyAndCorrectDevMode@@YAJPEAU_devicemodeW@@PEAPEAU1@PEAHPEBGW4_DEVMODEHANDLETYPE@@@Z; LVerifyAndCorrectDevMode(_devicemodeW *,_devicemodeW * *,int *,ushort const *,_DEVMODEHANDLETYPE)
0x140025b6b  mov     rdi, [rsp+2B0h+lpData]
0x140025b70  mov     ebx, eax
0x140025b72  test    eax, eax
0x140025b74  jnz     short loc_140025BC5
0x140025b76  cmp     [rsp+2B0h+var_278], r12d
0x140025b7b  jnz     short loc_140025BC5
0x140025b7d  movzx   r8d, word ptr [rdi+46h]
0x140025b82  lea     r9d, [rbx+3]; dwType
0x140025b86  movzx   eax, word ptr [rdi+44h]
0x140025b8a  mov     rdx, r14; lpValueName
0x140025b8d  mov     rcx, [rsp+2B0h+hKey]; hKey
0x140025b92  add     r8d, eax
0x140025b95  mov     [rsp+2B0h+cbData], r8d; cbData
0x140025b9a  xor     r8d, r8d; Reserved
0x140025b9d  mov     [rsp+2B0h+phkResult], rdi; lpData
0x140025ba2  call    cs:__imp_RegSetValueExW
0x140025ba9  nop     dword ptr [rax+rax+00h]
0x140025bae  mov     r8, rsi
0x140025bb1  lea     rdx, aSetDevmodeWsSt; "Set devmode %ws. Status : %d"
0x140025bb8  mov     r9d, eax
0x140025bbb  mov     rcx, r13; char *
0x140025bbe  mov     ebx, eax
0x140025bc0  call    ?WriteDbgTraceInfo@DevmodeSizePatchTelemetry@@SAXPEADPEAGZZ; DevmodeSizePatchTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x140025bc5  test    rdi, rdi
0x140025bc8  jz      short loc_140025BD9
0x140025bca  mov     rcx, rdi; Block
0x140025bcd  call    cs:__imp_free
0x140025bd4  nop     dword ptr [rax+rax+00h]
0x140025bd9  test    rsi, rsi
0x140025bdc  jz      short loc_140025BED
0x140025bde  mov     rcx, rsi; Block
0x140025be1  call    cs:__imp_free
0x140025be8  nop     dword ptr [rax+rax+00h]
0x140025bed  lea     rcx, [rsp+2B0h+hKey]
0x140025bf2  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x140025bf7  mov     eax, ebx
0x140025bf9  jmp     short loc_140025C0A
0x140025bfb  lea     rcx, [rsp+2B0h+hKey]
0x140025c00  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x140025c05  mov     eax, 709h
0x140025c0a  mov     rcx, [rbp+1B0h+var_40]
0x140025c11  xor     rcx, rsp; StackCookie
0x140025c14  call    __security_check_cookie
0x140025c19  mov     rbx, [rsp+2B0h+arg_10]
0x140025c21  add     rsp, 280h
0x140025c28  pop     r15
0x140025c2a  pop     r14
0x140025c2c  pop     r13
0x140025c2e  pop     r12
0x140025c30  pop     rdi
0x140025c31  pop     rsi
0x140025c32  pop     rbp
0x140025c33  retn
```
