# CFindExtensionsMenu::_AddStatic(HMENU__ *,uint,uint,HKEY__ *)

- ea: `0x1802e6eb4`
- end: `0x1802e72b4`
- name: `?_AddStatic@CFindExtensionsMenu@@AEAAIPEAUHMENU__@@IIPEAUHKEY__@@@Z`
- size: `1024`
- prototype: `unsigned int __fastcall(CFindExtensionsMenu *__hidden this, HMENU, unsigned int, unsigned int, HKEY hKey)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1802e6b84`

## callees

- `0x18003eab0`
- `0x1800426e8`
- `0x18006b4d0`
- `0x180076fdc`
- `0x1800cacd0`
- `0x180233280`
- `0x1802342fc`
- `0x1802e6d84`
- `0x1802e6dec`
- `0x1802e6eb4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1802e6f46`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1802e6fa3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1802e7036`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1802e722e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1802e6f46`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1802e6fa3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1802e7036`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1802e722e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1802e71f1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1802e7246`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1802e727e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1802e71f1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1802e7246`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1802e727e`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x1802e6fbc`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x1802e6fbc`
- `USER32!InsertMenuItemW` at `0x1802e71b2`
- `USER32!InsertMenuItemW` at `0x1802e71df`
- `USER32!InsertMenuItemW` at `0x1802e71b2`
- `USER32!InsertMenuItemW` at `0x1802e71df`
- `api-ms-win-core-registry-l2-1-0!RegEnumKeyW` at `0x1802e6f70`
- `api-ms-win-core-registry-l2-1-0!RegEnumKeyW` at `0x1802e7266`
- `api-ms-win-core-registry-l2-1-0!RegEnumKeyW` at `0x1802e6f70`
- `api-ms-win-core-registry-l2-1-0!RegEnumKeyW` at `0x1802e7266`
- `Windows.Storage!__imp_SHRestricted` at `0x1802e70f1`
- `Windows.Storage!__imp_SHRestricted` at `0x1802e711a`
- `Windows.Storage!__imp_SHRestricted` at `0x1802e70f1`
- `Windows.Storage!__imp_SHRestricted` at `0x1802e711a`
- `Windows.Storage!__imp_SHCLSIDFromString` at `0x1802e707d`
- `Windows.Storage!__imp_SHCLSIDFromString` at `0x1802e70c4`
- `Windows.Storage!__imp_SHCLSIDFromString` at `0x1802e707d`
- `Windows.Storage!__imp_SHCLSIDFromString` at `0x1802e70c4`

## pseudocode

```c
__int64 __fastcall CFindExtensionsMenu::_AddStatic(CFindExtensionsMenu *this, HMENU a2, UINT a3, UINT a4, HKEY hKey)
{
  UINT v6; // ebx
  CFindExtensionsMenu *v7; // r13
  struct _DSA *v8; // rsi
  DWORD v9; // r12d
  BOOL inserted; // r14d
  unsigned int v11; // r13d
  const unsigned __int16 *v12; // rdx
  unsigned int v13; // r9d
  int v14; // edi
  int Icon; // eax
  UINT v16; // edx
  DWORD v18; // [rsp+30h] [rbp-D0h]
  int v19; // [rsp+34h] [rbp-CCh]
  HKEY v22; // [rsp+48h] [rbp-B8h] BYREF
  HKEY v23; // [rsp+50h] [rbp-B0h] BYREF
  HKEY phkResult; // [rsp+58h] [rbp-A8h] BYREF
  MENUITEMINFOW mi; // [rsp+60h] [rbp-A0h] BYREF
  CLSID pclsid; // [rsp+B0h] [rbp-50h] BYREF
  CLSID v27[2]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR SubKey[32]; // [rsp+E0h] [rbp-20h] BYREF
  WCHAR Name[264]; // [rsp+120h] [rbp+20h] BYREF
  WCHAR psz[264]; // [rsp+330h] [rbp+230h] BYREF
  WCHAR v31[264]; // [rsp+540h] [rbp+440h] BYREF
  unsigned __int16 v32[264]; // [rsp+750h] [rbp+650h] BYREF

  v6 = a3;
  v7 = this;
  if ( a3 <= a4 )
  {
    v8 = DSA_Create(36, 1);
    if ( v8 )
    {
      phkResult = 0;
      if ( !RegOpenKeyExW(hKey, L"Static", 0, 0x2000000u, &phkResult) )
      {
        v9 = 0;
        v18 = 0;
        inserted = 0;
        if ( !RegEnumKeyW(phkResult, 0, Name, 0x104u) )
        {
          do
          {
            v23 = 0;
            if ( !RegOpenKeyExW(phkResult, Name, 0, 0x2000000u, &v23) )
            {
              v19 = StrCmpICW(Name, L"WebSearch");
              if ( (int)SHRegGetStringEx(v23, 0, 0, 2, psz, 0x104u) >= 0 )
              {
                v11 = 0;
                v22 = 0;
                StringCchPrintfW(SubKey, 0x20u, L"%d", 0);
                if ( !RegOpenKeyExW(v23, SubKey, 0, 0x2000000u, &v22) )
                {
                  while ( 1 )
                  {
                    if ( (int)SHLoadLegacyRegUIStringW(v22, v12, v32, v13) >= 0 )
                    {
                      pclsid = 0;
                      memset(v27, 0, 20);
                      SHCLSIDFromString(psz, &pclsid);
                      v27[0].Data1 = v11;
                      if ( (int)SHRegGetStringEx(v22, L"SearchGUID", 0, 2, v31, 0x104u) < 0 )
                        *(GUID *)&v27[0].Data2 = GUID_NULL;
                      else
                        SHCLSIDFromString(v31, (CLSID *)&v27[0].Data2);
                      if ( (unsigned int)IsEqualGUID(&v27[0].Data2, &SRCID_SFindComputer)
                        && !SHRestricted(REST_HASFINDCOMPUTERS) )
                      {
                        goto LABEL_26;
                      }
                      v14 = IsEqualGUID(&v27[0].Data2, &GUID_169a0691_8df9_11d1_a1c4_00c04fd75d13);
                      if ( v14 )
                      {
                        if ( SHRestricted(REST_NOFIND) )
                          goto LABEL_26;
                      }
                      if ( (unsigned int)IsEqualGUID(&v27[0].Data2, &SRCID_SFindPrinter) )
                        goto LABEL_26;
                      if ( DSA_InsertItem(v8, 0x7FFFFFFF, &pclsid) != -1 )
                      {
                        memset_0(&mi, 0, sizeof(mi));
                        mi.cbSize = 80;
                        *(_QWORD *)&mi.fMask = 354;
                        mi.wID = v6;
                        Icon = Static_ExtractIcon(v22);
                        mi.dwTypeData = v32;
                        mi.dwItemData = Icon;
                        if ( inserted || !v14 )
                        {
                          v16 = 0x7FFFFFFF;
                          if ( !v19 )
                            v16 = inserted;
                          InsertMenuItemW(a2, v16, 1, &mi);
                        }
                        else
                        {
                          inserted = InsertMenuItemW(a2, 0, 1, &mi);
                        }
                        if ( ++v6 > a4 )
                        {
LABEL_27:
                          v9 = v18;
                          break;
                        }
                      }
                    }
                    RegCloseKey(v22);
LABEL_26:
                    StringCchPrintfW(SubKey, 0x20u, L"%d", ++v11);
                    if ( RegOpenKeyExW(v23, SubKey, 0, 0x2000000u, &v22) )
                      goto LABEL_27;
                  }
                }
              }
              RegCloseKey(v23);
            }
            v18 = ++v9;
          }
          while ( !RegEnumKeyW(phkResult, v9, Name, 0x104u) );
          v7 = this;
        }
        RegCloseKey(phkResult);
      }
      *((_QWORD *)v7 + 4) = v8;
    }
  }
  return v6;
}

```

## disassembly

```asm
0x1802e6eb4  mov     [rsp-8+arg_18], rbx
0x1802e6eb9  push    rbp
0x1802e6eba  push    rsi
0x1802e6ebb  push    rdi
0x1802e6ebc  push    r12
0x1802e6ebe  push    r13
0x1802e6ec0  push    r14
0x1802e6ec2  push    r15
0x1802e6ec4  lea     rbp, [rsp-870h]
0x1802e6ecc  sub     rsp, 970h
0x1802e6ed3  mov     rax, cs:__security_cookie
0x1802e6eda  xor     rax, rsp
0x1802e6edd  mov     [rbp+8A0h+var_40], rax
0x1802e6ee4  mov     rdi, [rbp+8A0h+hKey]
0x1802e6eeb  mov     r15d, r9d
0x1802e6eee  mov     [rsp+9A0h+hmenu], rdx
0x1802e6ef3  mov     ebx, r8d
0x1802e6ef6  mov     [rsp+9A0h+var_960], rcx
0x1802e6efb  mov     r13, rcx
0x1802e6efe  cmp     r8d, r9d
0x1802e6f01  ja      loc_1802E7288
0x1802e6f07  mov     edx, 1; cItemGrow
0x1802e6f0c  lea     ecx, [rdx+23h]; cbItem
0x1802e6f0f  call    DSA_Create
0x1802e6f14  mov     rsi, rax
0x1802e6f17  test    rax, rax
0x1802e6f1a  jz      loc_1802E7288
0x1802e6f20  lea     rax, [rsp+9A0h+var_948]
0x1802e6f25  mov     [rsp+9A0h+var_948], 0
0x1802e6f2e  mov     r9d, 2000000h; samDesired
0x1802e6f34  mov     [rsp+9A0h+phkResult], rax; phkResult
0x1802e6f39  xor     r8d, r8d; ulOptions
0x1802e6f3c  lea     rdx, aStatic_1; "Static"
0x1802e6f43  mov     rcx, rdi; hKey
0x1802e6f46  call    cs:__imp_RegOpenKeyExW
0x1802e6f4c  test    eax, eax
0x1802e6f4e  jnz     loc_1802E7284
0x1802e6f54  mov     rcx, [rsp+9A0h+var_948]; hKey
0x1802e6f59  lea     r8, [rbp+8A0h+Name]; lpName
0x1802e6f5d  xor     r12d, r12d
0x1802e6f60  mov     r9d, 104h; cchName
0x1802e6f66  xor     edx, edx; dwIndex
0x1802e6f68  mov     [rsp+9A0h+var_970], r12d
0x1802e6f6d  xor     r14d, r14d
0x1802e6f70  call    cs:__imp_RegEnumKeyW
0x1802e6f76  test    eax, eax
0x1802e6f78  jnz     loc_1802E7279
0x1802e6f7e  mov     rcx, [rsp+9A0h+var_948]; hKey
0x1802e6f83  lea     rax, [rsp+9A0h+var_950]
0x1802e6f88  mov     r9d, 2000000h; samDesired
0x1802e6f8e  mov     [rsp+9A0h+phkResult], rax; phkResult
0x1802e6f93  xor     r8d, r8d; ulOptions
0x1802e6f96  mov     [rsp+9A0h+var_950], 0
0x1802e6f9f  lea     rdx, [rbp+8A0h+Name]; lpSubKey
0x1802e6fa3  call    cs:__imp_RegOpenKeyExW
0x1802e6fa9  test    eax, eax
0x1802e6fab  jnz     loc_1802E724C
0x1802e6fb1  lea     rdx, aWebsearch; "WebSearch"
0x1802e6fb8  lea     rcx, [rbp+8A0h+Name]; pszStr1
0x1802e6fbc  call    cs:__imp_StrCmpICW
0x1802e6fc2  mov     rcx, [rsp+9A0h+var_950]; HKEY
0x1802e6fc7  mov     r9d, 2; int
0x1802e6fcd  mov     [rsp+9A0h+var_96C], eax
0x1802e6fd1  xor     r8d, r8d; unsigned __int16 *
0x1802e6fd4  lea     rax, [rbp+8A0h+psz]
0x1802e6fdb  mov     [rsp+9A0h+var_978], 104h; unsigned int
0x1802e6fe3  xor     edx, edx; unsigned __int16 *
0x1802e6fe5  mov     [rsp+9A0h+phkResult], rax; unsigned __int16 *
0x1802e6fea  call    ?SHRegGetStringEx@@YAJPEAUHKEY__@@PEBG1HPEAGK@Z; SHRegGetStringEx(HKEY__ *,ushort const *,ushort const *,int,ushort *,ulong)
0x1802e6fef  test    eax, eax
0x1802e6ff1  js      loc_1802E7241
0x1802e6ff7  xor     r13d, r13d
0x1802e6ffa  mov     [rsp+9A0h+var_958], 0
0x1802e7003  xor     r9d, r9d
0x1802e7006  lea     r8, aD; "%d"
0x1802e700d  lea     rcx, [rbp+8A0h+SubKey]; unsigned __int16 *
0x1802e7011  lea     edx, [r13+20h]; unsigned __int64
0x1802e7015  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1802e701a  mov     rcx, [rsp+9A0h+var_950]; hKey
0x1802e701f  lea     rax, [rsp+9A0h+var_958]
0x1802e7024  mov     r9d, 2000000h; samDesired
0x1802e702a  mov     [rsp+9A0h+phkResult], rax; phkResult
0x1802e702f  xor     r8d, r8d; ulOptions
0x1802e7032  lea     rdx, [rbp+8A0h+SubKey]; lpSubKey
0x1802e7036  call    cs:__imp_RegOpenKeyExW
0x1802e703c  test    eax, eax
0x1802e703e  jnz     loc_1802E7241
0x1802e7044  mov     r12, [rsp+9A0h+hmenu]
0x1802e7049  mov     rcx, [rsp+9A0h+var_958]; HKEY
0x1802e704e  lea     r8, [rbp+8A0h+var_250]; unsigned __int16 *
0x1802e7055  call    ?SHLoadLegacyRegUIStringW@@YAJPEAUHKEY__@@PEBGPEAGI@Z; SHLoadLegacyRegUIStringW(HKEY__ *,ushort const *,ushort *,uint)
0x1802e705a  test    eax, eax
0x1802e705c  js      loc_1802E71EC
0x1802e7062  xorps   xmm0, xmm0
0x1802e7065  lea     rdx, [rbp+8A0h+pclsid]; pclsid
0x1802e7069  xor     eax, eax
0x1802e706b  lea     rcx, [rbp+8A0h+psz]; psz
0x1802e7072  movups  xmmword ptr [rbp+8A0h+pclsid.Data1], xmm0
0x1802e7076  mov     [rbp+8A0h+var_8D0], eax
0x1802e7079  movups  xmmword ptr [rbp+8A0h+var_8E0.Data1], xmm0
0x1802e707d  call    cs:__imp_SHCLSIDFromString
0x1802e7083  mov     rcx, [rsp+9A0h+var_958]; HKEY
0x1802e7088  lea     rax, [rbp+8A0h+var_460]
0x1802e708f  mov     [rsp+9A0h+var_978], 104h; unsigned int
0x1802e7097  lea     rdx, aSearchguid; "SearchGUID"
0x1802e709e  mov     r9d, 2; int
0x1802e70a4  mov     [rsp+9A0h+phkResult], rax; unsigned __int16 *
0x1802e70a9  xor     r8d, r8d; unsigned __int16 *
0x1802e70ac  mov     [rbp+8A0h+var_8E0.Data1], r13d
0x1802e70b0  call    ?SHRegGetStringEx@@YAJPEAUHKEY__@@PEBG1HPEAGK@Z; SHRegGetStringEx(HKEY__ *,ushort const *,ushort const *,int,ushort *,ulong)
0x1802e70b5  test    eax, eax
0x1802e70b7  js      short loc_1802E70CC
0x1802e70b9  lea     rdx, [rbp+8A0h+var_8E0.Data2]; pclsid
0x1802e70bd  lea     rcx, [rbp+8A0h+var_460]; psz
0x1802e70c4  call    cs:__imp_SHCLSIDFromString
0x1802e70ca  jmp     short loc_1802E70D8
0x1802e70cc  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1802e70d3  movdqu  xmmword ptr [rbp+8A0h+var_8E0.Data2], xmm0
0x1802e70d8  lea     rdx, SRCID_SFindComputer
0x1802e70df  lea     rcx, [rbp+8A0h+var_8E0.Data2]
0x1802e70e3  call    IsEqualGUID
0x1802e70e8  test    eax, eax
0x1802e70ea  jz      short loc_1802E70FF
0x1802e70ec  mov     ecx, 40000022h; rest
0x1802e70f1  call    cs:__imp_SHRestricted
0x1802e70f7  test    eax, eax
0x1802e70f9  jz      loc_1802E71F7
0x1802e70ff  lea     rdx, _GUID_169a0691_8df9_11d1_a1c4_00c04fd75d13
0x1802e7106  lea     rcx, [rbp+8A0h+var_8E0.Data2]
0x1802e710a  call    IsEqualGUID
0x1802e710f  mov     edi, eax
0x1802e7111  test    eax, eax
0x1802e7113  jz      short loc_1802E7128
0x1802e7115  mov     ecx, 80h; rest
0x1802e711a  call    cs:__imp_SHRestricted
0x1802e7120  test    eax, eax
0x1802e7122  jnz     loc_1802E71F7
0x1802e7128  lea     rdx, SRCID_SFindPrinter
0x1802e712f  lea     rcx, [rbp+8A0h+var_8E0.Data2]
0x1802e7133  call    IsEqualGUID
0x1802e7138  test    eax, eax
0x1802e713a  jnz     loc_1802E71F7
0x1802e7140  lea     r8, [rbp+8A0h+pclsid]; pitem
0x1802e7144  mov     edx, 7FFFFFFFh; i
0x1802e7149  mov     rcx, rsi; hdsa
0x1802e714c  call    DSA_InsertItem
0x1802e7151  cmp     eax, 0FFFFFFFFh
0x1802e7154  jz      loc_1802E71EC
0x1802e715a  xor     edx, edx; Val
0x1802e715c  lea     rcx, [rsp+9A0h+mi]; void *
0x1802e7161  lea     r8d, [rdx+50h]; Size
0x1802e7165  call    memset_0
0x1802e716a  mov     rcx, [rsp+9A0h+var_958]; HKEY
0x1802e716f  mov     [rsp+9A0h+mi.cbSize], 50h ; 'P'
0x1802e7177  mov     qword ptr [rsp+9A0h+mi.fMask], 162h
0x1802e7180  mov     [rsp+9A0h+mi.wID], ebx
0x1802e7184  call    ?Static_ExtractIcon@@YAHPEAUHKEY__@@@Z; Static_ExtractIcon(HKEY__ *)
0x1802e7189  movsxd  rcx, eax
0x1802e718c  lea     rax, [rbp+8A0h+var_250]
0x1802e7193  mov     [rbp+8A0h+mi.dwTypeData], rax
0x1802e7197  mov     [rbp+8A0h+mi.dwItemData], rcx
0x1802e719b  test    r14d, r14d
0x1802e719e  jnz     short loc_1802E71BD
0x1802e71a0  test    edi, edi
0x1802e71a2  jz      short loc_1802E71BD
0x1802e71a4  lea     r9, [rsp+9A0h+mi]; lpmi
0x1802e71a9  xor     edx, edx; item
0x1802e71ab  lea     r8d, [r14+1]; fByPosition
0x1802e71af  mov     rcx, r12; hmenu
0x1802e71b2  call    cs:__imp_InsertMenuItemW
0x1802e71b8  mov     r14d, eax
0x1802e71bb  jmp     short loc_1802E71E5
0x1802e71bd  cmp     [rsp+9A0h+var_96C], 0
0x1802e71c2  mov     edx, 7FFFFFFFh
0x1802e71c7  jnz     short loc_1802E71D1
0x1802e71c9  xor     edx, edx
0x1802e71cb  test    r14d, r14d
0x1802e71ce  setnz   dl; item
0x1802e71d1  lea     r9, [rsp+9A0h+mi]; lpmi
0x1802e71d6  mov     r8d, 1; fByPosition
0x1802e71dc  mov     rcx, r12; hmenu
0x1802e71df  call    cs:__imp_InsertMenuItemW
0x1802e71e5  inc     ebx
0x1802e71e7  cmp     ebx, r15d
0x1802e71ea  ja      short loc_1802E723C
0x1802e71ec  mov     rcx, [rsp+9A0h+var_958]; hKey
0x1802e71f1  call    cs:__imp_RegCloseKey
0x1802e71f7  inc     r13d
0x1802e71fa  lea     r8, aD; "%d"
0x1802e7201  mov     r9d, r13d
0x1802e7204  lea     rcx, [rbp+8A0h+SubKey]; unsigned __int16 *
0x1802e7208  mov     edx, 20h ; ' '; unsigned __int64
0x1802e720d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1802e7212  mov     rcx, [rsp+9A0h+var_950]; hKey
0x1802e7217  lea     rax, [rsp+9A0h+var_958]
0x1802e721c  mov     r9d, 2000000h; samDesired
0x1802e7222  mov     [rsp+9A0h+phkResult], rax; phkResult
0x1802e7227  xor     r8d, r8d; ulOptions
0x1802e722a  lea     rdx, [rbp+8A0h+SubKey]; lpSubKey
0x1802e722e  call    cs:__imp_RegOpenKeyExW
0x1802e7234  test    eax, eax
0x1802e7236  jz      loc_1802E7049
0x1802e723c  mov     r12d, [rsp+9A0h+var_970]
0x1802e7241  mov     rcx, [rsp+9A0h+var_950]; hKey
0x1802e7246  call    cs:__imp_RegCloseKey
0x1802e724c  mov     rcx, [rsp+9A0h+var_948]; hKey
0x1802e7251  lea     r8, [rbp+8A0h+Name]; lpName
0x1802e7255  inc     r12d
0x1802e7258  mov     r9d, 104h; cchName
0x1802e725e  mov     edx, r12d; dwIndex
0x1802e7261  mov     [rsp+9A0h+var_970], r12d
0x1802e7266  call    cs:__imp_RegEnumKeyW
0x1802e726c  test    eax, eax
0x1802e726e  jz      loc_1802E6F7E
0x1802e7274  mov     r13, [rsp+9A0h+var_960]
0x1802e7279  mov     rcx, [rsp+9A0h+var_948]; hKey
0x1802e727e  call    cs:__imp_RegCloseKey
0x1802e7284  mov     [r13+20h], rsi
0x1802e7288  mov     eax, ebx
0x1802e728a  mov     rcx, [rbp+8A0h+var_40]
0x1802e7291  xor     rcx, rsp; StackCookie
0x1802e7294  call    __security_check_cookie
0x1802e7299  mov     rbx, [rsp+9A0h+arg_18]
0x1802e72a1  add     rsp, 970h
0x1802e72a8  pop     r15
0x1802e72aa  pop     r14
0x1802e72ac  pop     r13
0x1802e72ae  pop     r12
0x1802e72b0  pop     rdi
0x1802e72b1  pop     rsi
0x1802e72b2  pop     rbp
0x1802e72b3  retn
```
