# CElevatedFactoryServer::ServerCreateElevatedObject(_GUID const &,_GUID const &,void * *)

- ea: `0x180003060`
- end: `0x180003252`
- name: `?ServerCreateElevatedObject@CElevatedFactoryServer@@UEAAJAEBU_GUID@@0PEAPEAX@Z`
- size: `498`
- prototype: `int(CElevatedFactoryServer *__hidden this, const struct _GUID *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x180002340`
- `0x1800026ac`
- `0x1800026d4`
- `0x180003060`
- `0x180003258`
- `0x1800036c0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180003189`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180003189`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800031e7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800031e7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000314a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000314a`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1800030cc`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180003112`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1800030cc`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180003112`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800031f2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800031fd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800031f2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800031fd`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800031da`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800031da`

## string_xrefs

- `0x1800030e1`: `Software\Classes\CLSID\%s\VirtualServerObjects`

## pseudocode

```c
__int64 __fastcall CElevatedFactoryServer::ServerCreateElevatedObject(
        CElevatedFactoryServer *this,
        const struct _GUID *a2,
        const struct _GUID *a3,
        void **a4)
{
  int Instance; // ebx
  LSTATUS v9; // eax
  LSTATUS Value; // eax
  HKEY hKey; // [rsp+30h] [rbp-D0h] BYREF
  LPOLESTR v13; // [rsp+38h] [rbp-C8h] BYREF
  LPOLESTR lpsz; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR SubKey[256]; // [rsp+50h] [rbp-B0h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF__guid_(*((_QWORD *)WPP_GLOBAL_Control + 2), a2, a3, a2);
  lpsz = 0;
  Instance = StringFromCLSID((const IID *const)((char *)this + 8), &lpsz);
  if ( Instance < 0 )
    goto LABEL_21;
  Instance = StringCchPrintfW(SubKey, 0x100u, L"Software\\Classes\\CLSID\\%s\\VirtualServerObjects", lpsz);
  if ( Instance >= 0 )
  {
    v13 = 0;
    Instance = StringFromCLSID(a2, &v13);
    if ( Instance >= 0 )
    {
      hKey = 0;
      v9 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 1u, &hKey);
      Instance = v9;
      if ( v9 > 0 )
        Instance = (unsigned __int16)v9 | 0x80070000;
      if ( Instance >= 0 )
      {
        Value = RegQueryValueExW(hKey, v13, 0, 0, 0, 0);
        Instance = Value;
        if ( Value > 0 )
          Instance = (unsigned __int16)Value | 0x80070000;
        if ( Instance >= 0 )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_af1accad8eb7317774aa247aa557fa30_Traceguids);
          Instance = CoCreateInstance(a2, 0, 3u, a3, a4);
        }
        RegCloseKey(hKey);
      }
      CoTaskMemFree(v13);
    }
  }
  CoTaskMemFree(lpsz);
  if ( Instance < 0 )
  {
LABEL_21:
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        13,
        &WPP_af1accad8eb7317774aa247aa557fa30_Traceguids,
        (unsigned int)Instance);
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180003060  push    rbp
0x180003062  push    rbx
0x180003063  push    rsi
0x180003064  push    rdi
0x180003065  push    r13
0x180003067  push    r14
0x180003069  lea     rbp, [rsp-168h]
0x180003071  sub     rsp, 268h
0x180003078  mov     rax, cs:__security_cookie
0x18000307f  xor     rax, rsp
0x180003082  mov     [rbp+190h+var_40], rax
0x180003089  mov     r14, r9
0x18000308c  mov     rsi, r8
0x18000308f  mov     rdi, rdx
0x180003092  mov     rbx, rcx
0x180003095  mov     rcx, cs:WPP_GLOBAL_Control
0x18000309c  lea     r13, WPP_GLOBAL_Control
0x1800030a3  cmp     rcx, r13
0x1800030a6  jz      short loc_1800030BA
0x1800030a8  test    byte ptr [rcx+1Ch], 8
0x1800030ac  jz      short loc_1800030BA
0x1800030ae  mov     rcx, [rcx+10h]
0x1800030b2  mov     r9, rdx
0x1800030b5  call    WPP_SF__guid_
0x1800030ba  lea     rcx, [rbx+8]; rclsid
0x1800030be  mov     [rsp+290h+lpsz], 0
0x1800030c7  lea     rdx, [rsp+290h+lpsz]; lplpsz
0x1800030cc  call    cs:__imp_StringFromCLSID
0x1800030d2  mov     ebx, eax
0x1800030d4  test    eax, eax
0x1800030d6  js      loc_180003207
0x1800030dc  mov     r9, [rsp+290h+lpsz]
0x1800030e1  lea     r8, aSoftwareClasse; "Software\\Classes\\CLSID\\%s\\VirtualSe"...
0x1800030e8  mov     edx, 100h; unsigned __int64
0x1800030ed  lea     rcx, [rsp+290h+SubKey]; unsigned __int16 *
0x1800030f2  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800030f7  mov     ebx, eax
0x1800030f9  test    eax, eax
0x1800030fb  js      loc_1800031F8
0x180003101  lea     rdx, [rsp+290h+var_258]; lplpsz
0x180003106  mov     [rsp+290h+var_258], 0
0x18000310f  mov     rcx, rdi; rclsid
0x180003112  call    cs:__imp_StringFromCLSID
0x180003118  mov     ebx, eax
0x18000311a  test    eax, eax
0x18000311c  js      loc_1800031F8
0x180003122  lea     rax, [rsp+290h+hKey]
0x180003127  mov     [rsp+290h+hKey], 0
0x180003130  mov     r9d, 1; samDesired
0x180003136  mov     [rsp+290h+phkResult], rax; phkResult
0x18000313b  xor     r8d, r8d; ulOptions
0x18000313e  lea     rdx, [rsp+290h+SubKey]; lpSubKey
0x180003143  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000314a  call    cs:__imp_RegOpenKeyExW
0x180003150  mov     ebx, eax
0x180003152  test    eax, eax
0x180003154  jle     short loc_18000315F
0x180003156  movzx   ebx, ax
0x180003159  or      ebx, 80070000h
0x18000315f  test    ebx, ebx
0x180003161  js      loc_1800031ED
0x180003167  mov     rdx, [rsp+290h+var_258]; lpValueName
0x18000316c  xor     r9d, r9d; lpType
0x18000316f  mov     rcx, [rsp+290h+hKey]; hKey
0x180003174  xor     r8d, r8d; lpReserved
0x180003177  mov     [rsp+290h+lpcbData], 0; lpcbData
0x180003180  mov     [rsp+290h+phkResult], 0; lpData
0x180003189  call    cs:__imp_RegQueryValueExW
0x18000318f  mov     ebx, eax
0x180003191  test    eax, eax
0x180003193  jle     short loc_18000319E
0x180003195  movzx   ebx, ax
0x180003198  or      ebx, 80070000h
0x18000319e  test    ebx, ebx
0x1800031a0  js      short loc_1800031E2
0x1800031a2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800031a9  cmp     rcx, r13
0x1800031ac  jz      short loc_1800031C9
0x1800031ae  test    byte ptr [rcx+1Ch], 8
0x1800031b2  jz      short loc_1800031C9
0x1800031b4  mov     rcx, [rcx+10h]
0x1800031b8  lea     r8, WPP_af1accad8eb7317774aa247aa557fa30_Traceguids
0x1800031bf  mov     edx, 0Ch
0x1800031c4  call    WPP_SF_
0x1800031c9  xor     edx, edx; pUnkOuter
0x1800031cb  mov     [rsp+290h+phkResult], r14; ppv
0x1800031d0  mov     r9, rsi; riid
0x1800031d3  mov     rcx, rdi; rclsid
0x1800031d6  lea     r8d, [rdx+3]; dwClsContext
0x1800031da  call    cs:__imp_CoCreateInstance
0x1800031e0  mov     ebx, eax
0x1800031e2  mov     rcx, [rsp+290h+hKey]; hKey
0x1800031e7  call    cs:__imp_RegCloseKey
0x1800031ed  mov     rcx, [rsp+290h+var_258]; pv
0x1800031f2  call    cs:__imp_CoTaskMemFree
0x1800031f8  mov     rcx, [rsp+290h+lpsz]; pv
0x1800031fd  call    cs:__imp_CoTaskMemFree
0x180003203  test    ebx, ebx
0x180003205  jns     short loc_180003231
0x180003207  mov     rcx, cs:WPP_GLOBAL_Control
0x18000320e  cmp     rcx, r13
0x180003211  jz      short loc_180003231
0x180003213  test    byte ptr [rcx+1Ch], 4
0x180003217  jz      short loc_180003231
0x180003219  mov     rcx, [rcx+10h]
0x18000321d  lea     r8, WPP_af1accad8eb7317774aa247aa557fa30_Traceguids
0x180003224  mov     edx, 0Dh
0x180003229  mov     r9d, ebx
0x18000322c  call    WPP_SF_d
0x180003231  mov     eax, ebx
0x180003233  mov     rcx, [rbp+190h+var_40]
0x18000323a  xor     rcx, rsp; StackCookie
0x18000323d  call    __security_check_cookie
0x180003242  add     rsp, 268h
0x180003249  pop     r14
0x18000324b  pop     r13
0x18000324d  pop     rdi
0x18000324e  pop     rsi
0x18000324f  pop     rbx
0x180003250  pop     rbp
0x180003251  retn
```
