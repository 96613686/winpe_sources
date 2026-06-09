# MakeMMCPointToV2(void)

- ea: `0x18003acf0`
- end: `0x18003af82`
- name: `?MakeMMCPointToV2@@YAJXZ`
- size: `658`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18003ef38`

## callees

- `0x18003acf0`
- `0x18004d030`
- `0x18004d350`
- `0x1800653c0`

## import_xrefs

- `KERNEL32!lstrlenW` at `0x18003ae24`
- `KERNEL32!lstrlenW` at `0x18003ae6f`
- `KERNEL32!lstrlenW` at `0x18003aef2`
- `KERNEL32!lstrlenW` at `0x18003ae24`
- `KERNEL32!lstrlenW` at `0x18003ae6f`
- `KERNEL32!lstrlenW` at `0x18003aef2`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x18003ad53`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x18003ad53`
- `ADVAPI32!RegCloseKey` at `0x18003ad98`
- `ADVAPI32!RegCloseKey` at `0x18003af2f`
- `ADVAPI32!RegCloseKey` at `0x18003af3f`
- `ADVAPI32!RegCloseKey` at `0x18003af4f`
- `ADVAPI32!RegCloseKey` at `0x18003ad98`
- `ADVAPI32!RegCloseKey` at `0x18003af2f`
- `ADVAPI32!RegCloseKey` at `0x18003af3f`
- `ADVAPI32!RegCloseKey` at `0x18003af4f`
- `ADVAPI32!RegOpenKeyExW` at `0x18003ad85`
- `ADVAPI32!RegOpenKeyExW` at `0x18003adbc`
- `ADVAPI32!RegOpenKeyExW` at `0x18003adef`
- `ADVAPI32!RegOpenKeyExW` at `0x18003ae16`
- `ADVAPI32!RegOpenKeyExW` at `0x18003ad85`
- `ADVAPI32!RegOpenKeyExW` at `0x18003adbc`
- `ADVAPI32!RegOpenKeyExW` at `0x18003adef`
- `ADVAPI32!RegOpenKeyExW` at `0x18003ae16`
- `ADVAPI32!RegSetValueExW` at `0x18003ae4e`
- `ADVAPI32!RegSetValueExW` at `0x18003ae99`
- `ADVAPI32!RegSetValueExW` at `0x18003af1d`
- `ADVAPI32!RegSetValueExW` at `0x18003ae4e`
- `ADVAPI32!RegSetValueExW` at `0x18003ae99`
- `ADVAPI32!RegSetValueExW` at `0x18003af1d`

## string_xrefs

- `0x18003ad4c`: `%windir%\Microsoft.NET\Framework64\v2.0.50727\MmcAspExt.dll`
- `0x18003adb1`: `CLSID\{FEDB2179-2335-48F1-AA28-5CDA35A2B36D}\InprocServer32`
- `0x18003ade5`: `SOFTWARE\Classes\CLSID\{FEDB2179-2335-48F1-AA28-5CDA35A2B36D}\InprocServer32`

## pseudocode

```c
__int64 MakeMMCPointToV2(void)
{
  unsigned int LastWin32Error; // ebx
  int v1; // eax
  LSTATUS v2; // eax
  int v3; // eax
  __int64 v4; // rdx
  WCHAR *v5; // rcx
  WCHAR v6; // ax
  WCHAR *v7; // rax
  int v8; // eax
  HKEY v10; // [rsp+30h] [rbp-D0h] BYREF
  HKEY v11; // [rsp+38h] [rbp-C8h] BYREF
  HKEY phkResult; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR String[104]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR Dst[264]; // [rsp+120h] [rbp+20h] BYREF

  hKey = 0;
  phkResult = 0;
  v11 = 0;
  v10 = 0;
  memset_0(Dst, 0, 0x208u);
  if ( !ExpandEnvironmentStringsW(L"%windir%\\Microsoft.NET\\Framework64\\v2.0.50727\\MmcAspExt.dll", Dst, 0x104u)
    || RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\ASP.NET\\2.0.50727.0", 0, 0x20019u, &hKey) )
  {
    return 1;
  }
  RegCloseKey(hKey);
  if ( RegOpenKeyExW(
         HKEY_CLASSES_ROOT,
         L"CLSID\\{FEDB2179-2335-48F1-AA28-5CDA35A2B36D}\\InprocServer32",
         0,
         0x20006u,
         &phkResult)
    || RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Classes\\CLSID\\{FEDB2179-2335-48F1-AA28-5CDA35A2B36D}\\InprocServer32",
         0,
         0x20006u,
         &v11)
    || RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\MMC\\SnapIns\\{fedb2179-2335-48f1-aa28-5cda35a2b36d}",
         0,
         0x20006u,
         &v10) )
  {
    LastWin32Error = GetLastWin32Error();
  }
  else
  {
    v1 = lstrlenW(Dst);
    v2 = RegSetValueExW(phkResult, &Class, 0, 1u, (const BYTE *)Dst, 2 * v1);
    if ( v2 || (v3 = lstrlenW(Dst), (v2 = RegSetValueExW(v11, &Class, 0, 1u, (const BYTE *)Dst, 2 * v3)) != 0) )
    {
      LastWin32Error = (unsigned __int16)v2 | 0x80070000;
      if ( v2 <= 0 )
        LastWin32Error = v2;
    }
    else
    {
      v4 = 100;
      v5 = String;
      do
      {
        if ( v4 == -2147483546 )
          break;
        v6 = *(WCHAR *)((char *)v5 + (char *)L"7d23ccc6-a390-406e-ab67-2f8b7558f6f7" - (char *)String);
        if ( !v6 )
          break;
        *v5++ = v6;
        --v4;
      }
      while ( v4 );
      v7 = v5 - 1;
      if ( v4 )
        v7 = v5;
      *v7 = 0;
      if ( v4 )
      {
        v8 = lstrlenW(String);
        RegSetValueExW(v10, L"About", 0, 1u, (const BYTE *)String, 2 * v8);
      }
      LastWin32Error = 0;
    }
  }
  if ( v10 )
    RegCloseKey(v10);
  if ( v11 )
    RegCloseKey(v11);
  if ( phkResult )
    RegCloseKey(phkResult);
  return LastWin32Error;
}

```

## disassembly

```asm
0x18003acf0  mov     [rsp-8+arg_0], rbx
0x18003acf5  mov     [rsp-8+arg_8], rdi
0x18003acfa  push    rbp
0x18003acfb  lea     rbp, [rsp-240h]
0x18003ad03  sub     rsp, 340h
0x18003ad0a  mov     rax, cs:__security_cookie
0x18003ad11  xor     rax, rsp
0x18003ad14  mov     [rbp+240h+var_10], rax
0x18003ad1b  xor     edi, edi
0x18003ad1d  lea     rcx, [rbp+240h+Dst]; void *
0x18003ad21  xor     edx, edx; Val
0x18003ad23  mov     [rsp+340h+hKey], rdi
0x18003ad28  mov     r8d, 208h; Size
0x18003ad2e  mov     [rsp+340h+var_300], rdi
0x18003ad33  mov     [rsp+340h+var_308], rdi
0x18003ad38  mov     [rsp+340h+var_310], rdi
0x18003ad3d  call    memset_0
0x18003ad42  mov     r8d, 104h; nSize
0x18003ad48  lea     rdx, [rbp+240h+Dst]; lpDst
0x18003ad4c  lea     rcx, aWindirMicrosof; "%windir%\\Microsoft.NET\\Framework64\\v"...
0x18003ad53  call    cs:__imp_ExpandEnvironmentStringsW
0x18003ad59  test    eax, eax
0x18003ad5b  jz      loc_18003AF59
0x18003ad61  lea     rax, [rsp+340h+hKey]
0x18003ad66  mov     rbx, 0FFFFFFFF80000002h
0x18003ad6d  mov     rcx, rbx; hKey
0x18003ad70  mov     [rsp+340h+phkResult], rax; phkResult
0x18003ad75  mov     r9d, 20019h; samDesired
0x18003ad7b  lea     rdx, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\ASP.NET\\2.0.50727"...
0x18003ad82  xor     r8d, r8d; ulOptions
0x18003ad85  call    cs:__imp_RegOpenKeyExW
0x18003ad8b  test    eax, eax
0x18003ad8d  jnz     loc_18003AF59
0x18003ad93  mov     rcx, [rsp+340h+hKey]; hKey
0x18003ad98  call    cs:__imp_RegCloseKey
0x18003ad9e  lea     rax, [rsp+340h+var_300]
0x18003ada3  mov     r9d, 20006h; samDesired
0x18003ada9  xor     r8d, r8d; ulOptions
0x18003adac  mov     [rsp+340h+phkResult], rax; phkResult
0x18003adb1  lea     rdx, aClsidFedb21792; "CLSID\\{FEDB2179-2335-48F1-AA28-5CDA35A"...
0x18003adb8  lea     rcx, [rbx-2]; hKey
0x18003adbc  call    cs:__imp_RegOpenKeyExW
0x18003adc2  test    eax, eax
0x18003adc4  jz      short loc_18003ADD2
0x18003adc6  call    ?GetLastWin32Error@@YAJXZ; GetLastWin32Error(void)
0x18003adcb  mov     ebx, eax
0x18003adcd  jmp     loc_18003AF25
0x18003add2  lea     rax, [rsp+340h+var_308]
0x18003add7  mov     r9d, 20006h; samDesired
0x18003addd  xor     r8d, r8d; ulOptions
0x18003ade0  mov     [rsp+340h+phkResult], rax; phkResult
0x18003ade5  lea     rdx, aSoftwareClasse; "SOFTWARE\\Classes\\CLSID\\{FEDB2179-233"...
0x18003adec  mov     rcx, rbx; hKey
0x18003adef  call    cs:__imp_RegOpenKeyExW
0x18003adf5  test    eax, eax
0x18003adf7  jnz     short loc_18003ADC6
0x18003adf9  lea     rax, [rsp+340h+var_310]
0x18003adfe  mov     r9d, 20006h; samDesired
0x18003ae04  xor     r8d, r8d; ulOptions
0x18003ae07  mov     [rsp+340h+phkResult], rax; phkResult
0x18003ae0c  lea     rdx, aSoftwareMicros_5; "SOFTWARE\\Microsoft\\MMC\\SnapIns\\{fed"...
0x18003ae13  mov     rcx, rbx; hKey
0x18003ae16  call    cs:__imp_RegOpenKeyExW
0x18003ae1c  test    eax, eax
0x18003ae1e  jnz     short loc_18003ADC6
0x18003ae20  lea     rcx, [rbp+240h+Dst]; lpString
0x18003ae24  call    cs:__imp_lstrlenW
0x18003ae2a  mov     rcx, [rsp+340h+var_300]; hKey
0x18003ae2f  lea     rdx, Class; lpValueName
0x18003ae36  add     eax, eax
0x18003ae38  mov     r9d, 1; dwType
0x18003ae3e  mov     [rsp+340h+cbData], eax; cbData
0x18003ae42  xor     r8d, r8d; Reserved
0x18003ae45  lea     rax, [rbp+240h+Dst]
0x18003ae49  mov     [rsp+340h+phkResult], rax; lpData
0x18003ae4e  call    cs:__imp_RegSetValueExW
0x18003ae54  test    eax, eax
0x18003ae56  jz      short loc_18003AE6B
0x18003ae58  movzx   ebx, ax
0x18003ae5b  or      ebx, 80070000h
0x18003ae61  test    eax, eax
0x18003ae63  cmovle  ebx, eax
0x18003ae66  jmp     loc_18003AF25
0x18003ae6b  lea     rcx, [rbp+240h+Dst]; lpString
0x18003ae6f  call    cs:__imp_lstrlenW
0x18003ae75  mov     rcx, [rsp+340h+var_308]; hKey
0x18003ae7a  lea     rdx, Class; lpValueName
0x18003ae81  add     eax, eax
0x18003ae83  mov     r9d, 1; dwType
0x18003ae89  mov     [rsp+340h+cbData], eax; cbData
0x18003ae8d  xor     r8d, r8d; Reserved
0x18003ae90  lea     rax, [rbp+240h+Dst]
0x18003ae94  mov     [rsp+340h+phkResult], rax; lpData
0x18003ae99  call    cs:__imp_RegSetValueExW
0x18003ae9f  test    eax, eax
0x18003aea1  jnz     short loc_18003AE58
0x18003aea3  lea     edx, [rax+64h]
0x18003aea6  lea     rax, [rsp+340h+String]
0x18003aeab  lea     r8, a7d23ccc6A39040; "7d23ccc6-a390-406e-ab67-2f8b7558f6f7"
0x18003aeb2  sub     r8, rax
0x18003aeb5  lea     rcx, [rsp+340h+String]
0x18003aeba  lea     rax, [rdx+7FFFFF9Ah]
0x18003aec1  test    rax, rax
0x18003aec4  jz      short loc_18003AEDD
0x18003aec6  movzx   eax, word ptr [r8+rcx]
0x18003aecb  test    ax, ax
0x18003aece  jz      short loc_18003AEDD
0x18003aed0  mov     [rcx], ax
0x18003aed3  add     rcx, 2
0x18003aed7  sub     rdx, 1
0x18003aedb  jnz     short loc_18003AEBA
0x18003aedd  test    rdx, rdx
0x18003aee0  lea     rax, [rcx-2]
0x18003aee4  cmovnz  rax, rcx
0x18003aee8  mov     [rax], di
0x18003aeeb  jz      short loc_18003AF23
0x18003aeed  lea     rcx, [rsp+340h+String]; lpString
0x18003aef2  call    cs:__imp_lstrlenW
0x18003aef8  mov     rcx, [rsp+340h+var_310]; hKey
0x18003aefd  lea     rdx, aAbout; "About"
0x18003af04  add     eax, eax
0x18003af06  mov     r9d, 1; dwType
0x18003af0c  mov     [rsp+340h+cbData], eax; cbData
0x18003af10  xor     r8d, r8d; Reserved
0x18003af13  lea     rax, [rsp+340h+String]
0x18003af18  mov     [rsp+340h+phkResult], rax; lpData
0x18003af1d  call    cs:__imp_RegSetValueExW
0x18003af23  mov     ebx, edi
0x18003af25  mov     rcx, [rsp+340h+var_310]; hKey
0x18003af2a  test    rcx, rcx
0x18003af2d  jz      short loc_18003AF35
0x18003af2f  call    cs:__imp_RegCloseKey
0x18003af35  mov     rcx, [rsp+340h+var_308]; hKey
0x18003af3a  test    rcx, rcx
0x18003af3d  jz      short loc_18003AF45
0x18003af3f  call    cs:__imp_RegCloseKey
0x18003af45  mov     rcx, [rsp+340h+var_300]; hKey
0x18003af4a  test    rcx, rcx
0x18003af4d  jz      short loc_18003AF55
0x18003af4f  call    cs:__imp_RegCloseKey
0x18003af55  mov     eax, ebx
0x18003af57  jmp     short loc_18003AF5E
0x18003af59  mov     eax, 1
0x18003af5e  mov     rcx, [rbp+240h+var_10]
0x18003af65  xor     rcx, rsp; StackCookie
0x18003af68  call    __security_check_cookie
0x18003af6d  lea     r11, [rsp+340h+var_s0]
0x18003af75  mov     rbx, [r11+10h]
0x18003af79  mov     rdi, [r11+18h]
0x18003af7d  mov     rsp, r11
0x18003af80  pop     rbp
0x18003af81  retn
```
