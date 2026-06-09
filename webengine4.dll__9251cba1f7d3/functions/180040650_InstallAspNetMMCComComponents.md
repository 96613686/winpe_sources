# InstallAspNetMMCComComponents

- ea: `0x180040650`
- end: `0x180040827`
- name: `InstallAspNetMMCComComponents`
- size: `471`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18003c1e8`

## callees

- `0x180007824`
- `0x180026634`
- `0x180036aa0`
- `0x180040650`
- `0x18004d030`
- `0x18004d754`
- `0x18004eaa8`

## import_xrefs

- `KERNEL32!lstrlenW` at `0x1800407b5`
- `KERNEL32!lstrlenW` at `0x1800407b5`
- `ADVAPI32!RegCloseKey` at `0x180040712`
- `ADVAPI32!RegCloseKey` at `0x1800407f0`
- `ADVAPI32!RegCloseKey` at `0x180040712`
- `ADVAPI32!RegCloseKey` at `0x1800407f0`
- `ADVAPI32!RegOpenKeyExW` at `0x1800406c5`
- `ADVAPI32!RegOpenKeyExW` at `0x18004073e`
- `ADVAPI32!RegOpenKeyExW` at `0x1800406c5`
- `ADVAPI32!RegOpenKeyExW` at `0x18004073e`
- `ADVAPI32!RegSetValueExW` at `0x1800407e0`
- `ADVAPI32!RegSetValueExW` at `0x1800407e0`

## string_xrefs

- `0x1800406b7`: `CLSID\{FEDB2179-2335-48F1-AA28-5CDA35A2B36D}\InprocServer32`
- `0x180040730`: `CLSID\{FEDB2179-2335-48F1-AA28-5CDA35A2B36D}\InprocServer32`
- `0x18004067d`: `MmcAspNetExtCOMComponents.Install`
- `0x18004079b`: `\MmcAspExt.dll`

## pseudocode

```c
__int64 InstallAspNetMMCComComponents()
{
  __int64 v0; // r8
  WCHAR *v1; // rcx
  WCHAR v2; // ax
  WCHAR *v3; // rax
  int v4; // eax
  HKEY hKey; // [rsp+30h] [rbp-D0h] BYREF
  void *lpMem; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR String[264]; // [rsp+40h] [rbp-C0h] BYREF

  lpMem = 0;
  hKey = 0;
  if ( (int)InstallInfSections(g_DllInstance, 1, L"MmcAspNetExtCOMComponents.Install", 1) < 0
    && !RegOpenKeyExW(
          HKEY_CLASSES_ROOT,
          L"CLSID\\{FEDB2179-2335-48F1-AA28-5CDA35A2B36D}\\InprocServer32",
          0,
          0x60019u,
          &hKey)
    && !(unsigned int)GetPrincipalSID((char *)L"administrators", &lpMem)
    && !(unsigned int)CRegAccount::SetAccessToRegKey(lpMem, hKey, 0xF003Fu, 1) )
  {
    RegCloseKey(hKey);
    hKey = 0;
    if ( !RegOpenKeyExW(
            HKEY_CLASSES_ROOT,
            L"CLSID\\{FEDB2179-2335-48F1-AA28-5CDA35A2B36D}\\InprocServer32",
            0,
            0x20006u,
            &hKey) )
    {
      v0 = 260;
      v1 = String;
      do
      {
        if ( v0 == -2147483386 )
          break;
        v2 = *(WCHAR *)((char *)v1 + (char *)&Names::s_wszInstallDirectory - (char *)String);
        if ( !v2 )
          break;
        *v1++ = v2;
        --v0;
      }
      while ( v0 );
      v3 = v1 - 1;
      if ( v0 )
        v3 = v1;
      *v3 = 0;
      if ( v0 && !(unsigned int)StringCchCatW(String, 0x104u, L"\\MmcAspExt.dll") )
      {
        v4 = lstrlenW(String);
        RegSetValueExW(hKey, &Class, 0, 1u, (const BYTE *)String, 2 * v4);
      }
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  if ( lpMem )
    MemFree(lpMem);
  return 0;
}

```

## disassembly

```asm
0x180040650  mov     [rsp-8+arg_0], rbx
0x180040655  push    rbp
0x180040656  lea     rbp, [rsp-160h]
0x18004065e  sub     rsp, 260h
0x180040665  mov     rax, cs:__security_cookie
0x18004066c  xor     rax, rsp
0x18004066f  mov     [rbp+160h+var_10], rax
0x180040676  mov     rcx, cs:?g_DllInstance@@3PEAUHINSTANCE__@@EA; hModule
0x18004067d  lea     r8, aMmcaspnetextco; "MmcAspNetExtCOMComponents.Install"
0x180040684  xor     ebx, ebx
0x180040686  mov     [rsp+260h+lpMem], rbx
0x18004068b  mov     [rsp+260h+hKey], rbx
0x180040690  lea     r9d, [rbx+1]
0x180040694  mov     dl, r9b
0x180040697  call    InstallInfSections
0x18004069c  test    eax, eax
0x18004069e  jns     loc_1800407E6
0x1800406a4  lea     rax, [rsp+260h+hKey]
0x1800406a9  mov     r9d, 60019h; samDesired
0x1800406af  xor     r8d, r8d; ulOptions
0x1800406b2  mov     [rsp+260h+phkResult], rax; phkResult
0x1800406b7  lea     rdx, aClsidFedb21792; "CLSID\\{FEDB2179-2335-48F1-AA28-5CDA35A"...
0x1800406be  mov     rcx, 0FFFFFFFF80000000h; hKey
0x1800406c5  call    cs:__imp_RegOpenKeyExW
0x1800406cb  test    eax, eax
0x1800406cd  jnz     loc_1800407E6
0x1800406d3  lea     rdx, [rsp+260h+lpMem]; void **
0x1800406d8  lea     rcx, aAdministrators; "administrators"
0x1800406df  call    ?GetPrincipalSID@@YAJPEBGPEAPEAX@Z; GetPrincipalSID(ushort const *,void * *)
0x1800406e4  test    eax, eax
0x1800406e6  jnz     loc_1800407E6
0x1800406ec  mov     rdx, [rsp+260h+hKey]; HKEY
0x1800406f1  lea     r9d, [rbx+1]; int
0x1800406f5  mov     rcx, [rsp+260h+lpMem]; void *
0x1800406fa  mov     r8d, 0F003Fh; unsigned int
0x180040700  call    ?SetAccessToRegKey@CRegAccount@@SAJPEAXPEAUHKEY__@@KH@Z; CRegAccount::SetAccessToRegKey(void *,HKEY__ *,ulong,int)
0x180040705  test    eax, eax
0x180040707  jnz     loc_1800407E6
0x18004070d  mov     rcx, [rsp+260h+hKey]; hKey
0x180040712  call    cs:__imp_RegCloseKey
0x180040718  lea     rax, [rsp+260h+hKey]
0x18004071d  mov     [rsp+260h+hKey], rbx
0x180040722  mov     r9d, 20006h; samDesired
0x180040728  mov     [rsp+260h+phkResult], rax; phkResult
0x18004072d  xor     r8d, r8d; ulOptions
0x180040730  lea     rdx, aClsidFedb21792; "CLSID\\{FEDB2179-2335-48F1-AA28-5CDA35A"...
0x180040737  mov     rcx, 0FFFFFFFF80000000h; hKey
0x18004073e  call    cs:__imp_RegOpenKeyExW
0x180040744  test    eax, eax
0x180040746  jnz     loc_1800407E6
0x18004074c  mov     edx, 104h; unsigned __int64
0x180040751  lea     r9, ?s_wszInstallDirectory@Names@@0PAGA; ushort near * Names::s_wszInstallDirectory
0x180040758  lea     rax, [rsp+260h+String]
0x18004075d  mov     r8d, edx
0x180040760  sub     r9, rax
0x180040763  lea     rcx, [rsp+260h+String]
0x180040768  lea     rax, [r8+7FFFFEFAh]
0x18004076f  test    rax, rax
0x180040772  jz      short loc_18004078B
0x180040774  movzx   eax, word ptr [r9+rcx]
0x180040779  test    ax, ax
0x18004077c  jz      short loc_18004078B
0x18004077e  mov     [rcx], ax
0x180040781  add     rcx, 2
0x180040785  sub     r8, 1
0x180040789  jnz     short loc_180040768
0x18004078b  test    r8, r8
0x18004078e  lea     rax, [rcx-2]
0x180040792  cmovnz  rax, rcx
0x180040796  mov     [rax], bx
0x180040799  jz      short loc_1800407E6
0x18004079b  lea     r8, aMmcaspextDll; "\\MmcAspExt.dll"
0x1800407a2  lea     rcx, [rsp+260h+String]; unsigned __int16 *
0x1800407a7  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800407ac  test    eax, eax
0x1800407ae  jnz     short loc_1800407E6
0x1800407b0  lea     rcx, [rsp+260h+String]; lpString
0x1800407b5  call    cs:__imp_lstrlenW
0x1800407bb  mov     rcx, [rsp+260h+hKey]; hKey
0x1800407c0  lea     rdx, Class; lpValueName
0x1800407c7  add     eax, eax
0x1800407c9  mov     r9d, 1; dwType
0x1800407cf  mov     [rsp+260h+cbData], eax; cbData
0x1800407d3  xor     r8d, r8d; Reserved
0x1800407d6  lea     rax, [rsp+260h+String]
0x1800407db  mov     [rsp+260h+phkResult], rax; lpData
0x1800407e0  call    cs:__imp_RegSetValueExW
0x1800407e6  mov     rcx, [rsp+260h+hKey]; hKey
0x1800407eb  test    rcx, rcx
0x1800407ee  jz      short loc_1800407F6
0x1800407f0  call    cs:__imp_RegCloseKey
0x1800407f6  mov     rcx, [rsp+260h+lpMem]; lpMem
0x1800407fb  test    rcx, rcx
0x1800407fe  jz      short loc_180040805
0x180040800  call    ?MemFree@@YAXPEAX@Z; MemFree(void *)
0x180040805  xor     eax, eax
0x180040807  mov     rcx, [rbp+160h+var_10]
0x18004080e  xor     rcx, rsp; StackCookie
0x180040811  call    __security_check_cookie
0x180040816  mov     rbx, [rsp+260h+arg_0]
0x18004081e  add     rsp, 260h
0x180040825  pop     rbp
0x180040826  retn
```
