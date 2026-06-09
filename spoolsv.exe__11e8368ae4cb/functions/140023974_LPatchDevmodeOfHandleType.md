# LPatchDevmodeOfHandleType

- ea: `0x140023974`
- end: `0x140023c62`
- name: `LPatchDevmodeOfHandleType`
- size: `750`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1400058a0`

## callees

- `0x140005b68`
- `0x14000bf60`
- `0x1400163ec`
- `0x140017e74`
- `0x140017ef8`
- `0x140023974`
- `0x14002abc0`
- `0x1400779c4`
- `0x140077ae4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x140023c0b`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x140023c19`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x140023c0b`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x140023c19`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140023b41`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140023b41`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140023be6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140023be6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140023a26`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140023a5f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140023aab`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140023b10`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140023c29`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140023a26`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140023a5f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140023aab`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140023b10`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140023c29`

## string_xrefs

- `0x140023b4c`: `Opened handle. Status : %d`
- `0x140023b7a`: `Read devmode %ws. Status : %d`

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
    return 1801;
  v4 = -1;
  do
    ++v4;
  while ( a2[v4] );
  if ( !(unsigned int)IsValidPrinterName(a2, v4) )
    return 1801;
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
        return 87;
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
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x140023974  mov     [rsp-8+arg_10], rbx
0x140023979  push    rbp
0x14002397a  push    rsi
0x14002397b  push    rdi
0x14002397c  push    r12
0x14002397e  push    r13
0x140023980  push    r14
0x140023982  push    r15
0x140023984  lea     rbp, [rsp-180h]
0x14002398c  sub     rsp, 280h
0x140023993  mov     rax, cs:__security_cookie
0x14002399a  xor     rax, rsp
0x14002399d  mov     [rbp+1B0h+var_40], rax
0x1400239a4  xor     r12d, r12d
0x1400239a7  mov     rdi, rdx
0x1400239aa  mov     [rsp+2B0h+Block], r12
0x1400239af  mov     r15d, ecx
0x1400239b2  mov     [rsp+2B0h+lpData], r12
0x1400239b7  mov     [rsp+2B0h+hKey], r12
0x1400239bc  mov     [rsp+2B0h+var_278], r12d
0x1400239c1  test    rdx, rdx
0x1400239c4  jz      loc_140023C33
0x1400239ca  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1400239ce  inc     rdx; unsigned int
0x1400239d1  cmp     [rdi+rdx*2], r12w
0x1400239d6  jnz     short loc_1400239CE
0x1400239d8  mov     rcx, rdi; unsigned __int16 *
0x1400239db  call    ?IsValidPrinterName@@YAHPEBGK@Z; IsValidPrinterName(ushort const *,ulong)
0x1400239e0  test    eax, eax
0x1400239e2  jz      loc_140023C33
0x1400239e8  lea     r13, aLpatchdevmodeo; "LPatchDevmodeOfHandleType"
0x1400239ef  mov     r8, rdi
0x1400239f2  mov     rcx, r13; char *
0x1400239f5  lea     rdx, aStartIndividua; "START INDIVIDUAL PATCH:  %ws"
0x1400239fc  call    ?WriteDbgTraceInfo@DevmodeSizePatchTelemetry@@SAXPEADPEAGZZ; DevmodeSizePatchTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x140023a01  mov     ecx, r15d
0x140023a04  mov     esi, 3
0x140023a09  test    r15d, r15d
0x140023a0c  jz      loc_140023AC4
0x140023a12  sub     ecx, 1
0x140023a15  jz      short loc_140023A82
0x140023a17  cmp     ecx, 1
0x140023a1a  jz      short loc_140023A36
0x140023a1c  mov     rcx, [rsp+2B0h+hKey]; hKey
0x140023a21  test    rcx, rcx
0x140023a24  jz      short loc_140023A2C
0x140023a26  call    cs:__imp_RegCloseKey
0x140023a2c  mov     eax, 57h ; 'W'
0x140023a31  jmp     loc_140023C38
0x140023a36  lea     rdx, aDevmode2; "Devmode2"
0x140023a3d  mov     rcx, r13; char *
0x140023a40  call    ?WriteDbgTraceInfo@DevmodeSizePatchTelemetry@@SAXPEADPEAGZZ; DevmodeSizePatchTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x140023a45  mov     rbx, [rsp+2B0h+hKey]
0x140023a4a  mov     r14, rdi
0x140023a4d  test    rbx, rbx
0x140023a50  jz      short loc_140023A6F
0x140023a52  lea     rcx, [rsp+2B0h+var_270]; this
0x140023a57  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x140023a5c  mov     rcx, rbx; hKey
0x140023a5f  call    cs:__imp_RegCloseKey
0x140023a65  lea     rcx, [rsp+2B0h+var_270]; this
0x140023a6a  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x140023a6f  lea     rdx, aPrintersDevmod_0; "Printers\\DevModes2"
0x140023a76  mov     rcx, 0FFFFFFFF80000001h
0x140023a7d  jmp     loc_140023B2C
0x140023a82  lea     rdx, aPeruserDevmode; "PerUser Devmode"
0x140023a89  mov     rcx, r13; char *
0x140023a8c  call    ?WriteDbgTraceInfo@DevmodeSizePatchTelemetry@@SAXPEADPEAGZZ; DevmodeSizePatchTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x140023a91  mov     rbx, [rsp+2B0h+hKey]
0x140023a96  mov     r14, rdi
0x140023a99  test    rbx, rbx
0x140023a9c  jz      short loc_140023ABB
0x140023a9e  lea     rcx, [rsp+2B0h+var_270]; this
0x140023aa3  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x140023aa8  mov     rcx, rbx; hKey
0x140023aab  call    cs:__imp_RegCloseKey
0x140023ab1  lea     rcx, [rsp+2B0h+var_270]; this
0x140023ab6  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x140023abb  lea     rdx, aPrintersDevmod; "Printers\\DevModePerUser"
0x140023ac2  jmp     short loc_140023A76
0x140023ac4  lea     rdx, aDefaultDevmode; "Default Devmode"
0x140023acb  mov     rcx, r13; char *
0x140023ace  call    ?WriteDbgTraceInfo@DevmodeSizePatchTelemetry@@SAXPEADPEAGZZ; DevmodeSizePatchTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x140023ad3  mov     r9, rdi
0x140023ad6  lea     r8, aSoftwareMicros_1; "Software\\Microsoft\\Windows NT\\Curren"...
0x140023add  mov     edx, 104h; unsigned __int64
0x140023ae2  lea     rcx, [rsp+2B0h+SubKey]; unsigned __int16 *
0x140023ae7  lea     r14, ValueName; "Default DevMode"
0x140023aee  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140023af3  mov     ebx, eax
0x140023af5  test    eax, eax
0x140023af7  jnz     short loc_140023B49
0x140023af9  mov     rbx, [rsp+2B0h+hKey]
0x140023afe  test    rbx, rbx
0x140023b01  jz      short loc_140023B20
0x140023b03  lea     rcx, [rsp+2B0h+var_270]; this
0x140023b08  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x140023b0d  mov     rcx, rbx; hKey
0x140023b10  call    cs:__imp_RegCloseKey
0x140023b16  lea     rcx, [rsp+2B0h+var_270]; this
0x140023b1b  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x140023b20  lea     rdx, [rsp+2B0h+SubKey]; lpSubKey
0x140023b25  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140023b2c  lea     rax, [rsp+2B0h+hKey]
0x140023b31  mov     [rsp+2B0h+hKey], r12
0x140023b36  mov     r9d, esi; samDesired
0x140023b39  mov     [rsp+2B0h+phkResult], rax; phkResult
0x140023b3e  xor     r8d, r8d; ulOptions
0x140023b41  call    cs:__imp_RegOpenKeyExW
0x140023b47  mov     ebx, eax
0x140023b49  mov     r8d, ebx
0x140023b4c  lea     rdx, aOpenedHandleSt; "Opened handle. Status : %d"
0x140023b53  mov     rcx, r13; char *
0x140023b56  call    ?WriteDbgTraceInfo@DevmodeSizePatchTelemetry@@SAXPEADPEAGZZ; DevmodeSizePatchTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x140023b5b  test    ebx, ebx
0x140023b5d  jnz     loc_140023C1F
0x140023b63  mov     rcx, [rsp+2B0h+hKey]; hKey
0x140023b68  lea     r8, [rsp+2B0h+Block]; struct _devicemodeW **
0x140023b6d  mov     rdx, r14; lpValueName
0x140023b70  call    ?LGetDevMode@@YAJPEAUHKEY__@@PEBGPEAPEAU_devicemodeW@@@Z; LGetDevMode(HKEY__ *,ushort const *,_devicemodeW * *)
0x140023b75  mov     rsi, [rsp+2B0h+Block]
0x140023b7a  lea     rdx, aReadDevmodeWsS; "Read devmode %ws. Status : %d"
0x140023b81  mov     r8, rsi
0x140023b84  mov     r9d, eax
0x140023b87  mov     rcx, r13; char *
0x140023b8a  mov     ebx, eax
0x140023b8c  call    ?WriteDbgTraceInfo@DevmodeSizePatchTelemetry@@SAXPEADPEAGZZ; DevmodeSizePatchTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x140023b91  test    ebx, ebx
0x140023b93  jnz     short loc_140023C11
0x140023b95  mov     r9, rdi
0x140023b98  mov     dword ptr [rsp+2B0h+phkResult], r15d
0x140023b9d  lea     r8, [rsp+2B0h+var_278]
0x140023ba2  mov     rcx, rsi
0x140023ba5  lea     rdx, [rsp+2B0h+lpData]
0x140023baa  call    ?LVerifyAndCorrectDevMode@@YAJPEAU_devicemodeW@@PEAPEAU1@PEAHPEBGW4_DEVMODEHANDLETYPE@@@Z; LVerifyAndCorrectDevMode(_devicemodeW *,_devicemodeW * *,int *,ushort const *,_DEVMODEHANDLETYPE)
0x140023baf  mov     rdi, [rsp+2B0h+lpData]
0x140023bb4  mov     ebx, eax
0x140023bb6  test    eax, eax
0x140023bb8  jnz     short loc_140023C03
0x140023bba  cmp     [rsp+2B0h+var_278], r12d
0x140023bbf  jnz     short loc_140023C03
0x140023bc1  movzx   r8d, word ptr [rdi+46h]
0x140023bc6  lea     r9d, [rbx+3]; dwType
0x140023bca  movzx   eax, word ptr [rdi+44h]
0x140023bce  mov     rdx, r14; lpValueName
0x140023bd1  mov     rcx, [rsp+2B0h+hKey]; hKey
0x140023bd6  add     r8d, eax
0x140023bd9  mov     [rsp+2B0h+cbData], r8d; cbData
0x140023bde  xor     r8d, r8d; Reserved
0x140023be1  mov     [rsp+2B0h+phkResult], rdi; lpData
0x140023be6  call    cs:__imp_RegSetValueExW
0x140023bec  mov     r8, rsi
0x140023bef  lea     rdx, aSetDevmodeWsSt; "Set devmode %ws. Status : %d"
0x140023bf6  mov     r9d, eax
0x140023bf9  mov     rcx, r13; char *
0x140023bfc  mov     ebx, eax
0x140023bfe  call    ?WriteDbgTraceInfo@DevmodeSizePatchTelemetry@@SAXPEADPEAGZZ; DevmodeSizePatchTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x140023c03  test    rdi, rdi
0x140023c06  jz      short loc_140023C11
0x140023c08  mov     rcx, rdi; Block
0x140023c0b  call    cs:__imp_free
0x140023c11  test    rsi, rsi
0x140023c14  jz      short loc_140023C1F
0x140023c16  mov     rcx, rsi; Block
0x140023c19  call    cs:__imp_free
0x140023c1f  mov     rcx, [rsp+2B0h+hKey]; hKey
0x140023c24  test    rcx, rcx
0x140023c27  jz      short loc_140023C2F
0x140023c29  call    cs:__imp_RegCloseKey
0x140023c2f  mov     eax, ebx
0x140023c31  jmp     short loc_140023C38
0x140023c33  mov     eax, 709h
0x140023c38  mov     rcx, [rbp+1B0h+var_40]
0x140023c3f  xor     rcx, rsp; StackCookie
0x140023c42  call    __security_check_cookie
0x140023c47  mov     rbx, [rsp+2B0h+arg_10]
0x140023c4f  add     rsp, 280h
0x140023c56  pop     r15
0x140023c58  pop     r14
0x140023c5a  pop     r13
0x140023c5c  pop     r12
0x140023c5e  pop     rdi
0x140023c5f  pop     rsi
0x140023c60  pop     rbp
0x140023c61  retn
```
