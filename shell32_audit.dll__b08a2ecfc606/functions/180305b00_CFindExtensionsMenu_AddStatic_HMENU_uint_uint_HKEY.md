# CFindExtensionsMenu::_AddStatic(HMENU__ *,uint,uint,HKEY__ *)

- ea: `0x180305b00`
- end: `0x180305f61`
- name: `?_AddStatic@CFindExtensionsMenu@@AEAAIPEAUHMENU__@@IIPEAUHKEY__@@@Z`
- size: `1121`
- prototype: `unsigned int __fastcall(CFindExtensionsMenu *__hidden this, HMENU, unsigned int, unsigned int, HKEY hKey)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180305778`

## callees

- `0x18001e550`
- `0x18003a3e0`
- `0x18003e1e8`
- `0x1800585dc`
- `0x1800d1324`
- `0x180249490`
- `0x18024a53c`
- `0x1803059a4`
- `0x180305a18`
- `0x180305b00`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180305e7f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180305ee0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180305f24`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180305e7f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180305ee0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180305f24`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180305b92`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180305bfb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180305c9a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180305ec2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180305b92`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180305bfb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180305c9a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180305ec2`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180305c1a`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180305c1a`
- `USER32!InsertMenuItemW` at `0x180305e34`
- `USER32!InsertMenuItemW` at `0x180305e67`
- `USER32!InsertMenuItemW` at `0x180305e34`
- `USER32!InsertMenuItemW` at `0x180305e67`
- `api-ms-win-core-registry-l2-1-0!RegEnumKeyW` at `0x180305bc2`
- `api-ms-win-core-registry-l2-1-0!RegEnumKeyW` at `0x180305f06`
- `api-ms-win-core-registry-l2-1-0!RegEnumKeyW` at `0x180305bc2`
- `api-ms-win-core-registry-l2-1-0!RegEnumKeyW` at `0x180305f06`
- `Windows.Storage!__imp_SHRestricted` at `0x180305d67`
- `Windows.Storage!__imp_SHRestricted` at `0x180305d96`
- `Windows.Storage!__imp_SHRestricted` at `0x180305d67`
- `Windows.Storage!__imp_SHRestricted` at `0x180305d96`
- `Windows.Storage!__imp_SHCLSIDFromString` at `0x180305ce7`
- `Windows.Storage!__imp_SHCLSIDFromString` at `0x180305d34`
- `Windows.Storage!__imp_SHCLSIDFromString` at `0x180305ce7`
- `Windows.Storage!__imp_SHCLSIDFromString` at `0x180305d34`

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
0x180305b00  mov     [rsp-8+arg_18], rbx
0x180305b05  push    rbp
0x180305b06  push    rsi
0x180305b07  push    rdi
0x180305b08  push    r12
0x180305b0a  push    r13
0x180305b0c  push    r14
0x180305b0e  push    r15
0x180305b10  lea     rbp, [rsp-870h]
0x180305b18  sub     rsp, 970h
0x180305b1f  mov     rax, cs:__security_cookie
0x180305b26  xor     rax, rsp
0x180305b29  mov     [rbp+8A0h+var_40], rax
0x180305b30  mov     rdi, [rbp+8A0h+hKey]
0x180305b37  mov     r15d, r9d
0x180305b3a  mov     [rsp+9A0h+hmenu], rdx
0x180305b3f  mov     ebx, r8d
0x180305b42  mov     [rsp+9A0h+var_960], rcx
0x180305b47  mov     r13, rcx
0x180305b4a  cmp     r8d, r9d
0x180305b4d  ja      loc_180305F34
0x180305b53  mov     edx, 1; cItemGrow
0x180305b58  lea     ecx, [rdx+23h]; cbItem
0x180305b5b  call    DSA_Create
0x180305b60  mov     rsi, rax
0x180305b63  test    rax, rax
0x180305b66  jz      loc_180305F34
0x180305b6c  lea     rax, [rsp+9A0h+var_948]
0x180305b71  mov     [rsp+9A0h+var_948], 0
0x180305b7a  mov     r9d, 2000000h; samDesired
0x180305b80  mov     [rsp+9A0h+phkResult], rax; phkResult
0x180305b85  xor     r8d, r8d; ulOptions
0x180305b88  lea     rdx, aStatic_1; "Static"
0x180305b8f  mov     rcx, rdi; hKey
0x180305b92  call    cs:__imp_RegOpenKeyExW
0x180305b99  nop     dword ptr [rax+rax+00h]
0x180305b9e  test    eax, eax
0x180305ba0  jnz     loc_180305F30
0x180305ba6  mov     rcx, [rsp+9A0h+var_948]; hKey
0x180305bab  lea     r8, [rbp+8A0h+Name]; lpName
0x180305baf  xor     r12d, r12d
0x180305bb2  mov     r9d, 104h; cchName
0x180305bb8  xor     edx, edx; dwIndex
0x180305bba  mov     [rsp+9A0h+var_970], r12d
0x180305bbf  xor     r14d, r14d
0x180305bc2  call    cs:__imp_RegEnumKeyW
0x180305bc9  nop     dword ptr [rax+rax+00h]
0x180305bce  test    eax, eax
0x180305bd0  jnz     loc_180305F1F
0x180305bd6  mov     rcx, [rsp+9A0h+var_948]; hKey
0x180305bdb  lea     rax, [rsp+9A0h+var_950]
0x180305be0  mov     r9d, 2000000h; samDesired
0x180305be6  mov     [rsp+9A0h+phkResult], rax; phkResult
0x180305beb  xor     r8d, r8d; ulOptions
0x180305bee  mov     [rsp+9A0h+var_950], 0
0x180305bf7  lea     rdx, [rbp+8A0h+Name]; lpSubKey
0x180305bfb  call    cs:__imp_RegOpenKeyExW
0x180305c02  nop     dword ptr [rax+rax+00h]
0x180305c07  test    eax, eax
0x180305c09  jnz     loc_180305EEC
0x180305c0f  lea     rdx, aWebsearch; "WebSearch"
0x180305c16  lea     rcx, [rbp+8A0h+Name]; pszStr1
0x180305c1a  call    cs:__imp_StrCmpICW
0x180305c21  nop     dword ptr [rax+rax+00h]
0x180305c26  mov     rcx, [rsp+9A0h+var_950]; HKEY
0x180305c2b  mov     r9d, 2; int
0x180305c31  mov     [rsp+9A0h+var_96C], eax
0x180305c35  xor     r8d, r8d; unsigned __int16 *
0x180305c38  lea     rax, [rbp+8A0h+psz]
0x180305c3f  mov     [rsp+9A0h+var_978], 104h; unsigned int
0x180305c47  xor     edx, edx; unsigned __int16 *
0x180305c49  mov     [rsp+9A0h+phkResult], rax; unsigned __int16 *
0x180305c4e  call    ?SHRegGetStringEx@@YAJPEAUHKEY__@@PEBG1HPEAGK@Z; SHRegGetStringEx(HKEY__ *,ushort const *,ushort const *,int,ushort *,ulong)
0x180305c53  test    eax, eax
0x180305c55  js      loc_180305EDB
0x180305c5b  xor     r13d, r13d
0x180305c5e  mov     [rsp+9A0h+var_958], 0
0x180305c67  xor     r9d, r9d
0x180305c6a  lea     r8, aD; "%d"
0x180305c71  lea     rcx, [rbp+8A0h+SubKey]; unsigned __int16 *
0x180305c75  lea     edx, [r13+20h]; unsigned __int64
0x180305c79  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180305c7e  mov     rcx, [rsp+9A0h+var_950]; hKey
0x180305c83  lea     rax, [rsp+9A0h+var_958]
0x180305c88  mov     r9d, 2000000h; samDesired
0x180305c8e  mov     [rsp+9A0h+phkResult], rax; phkResult
0x180305c93  xor     r8d, r8d; ulOptions
0x180305c96  lea     rdx, [rbp+8A0h+SubKey]; lpSubKey
0x180305c9a  call    cs:__imp_RegOpenKeyExW
0x180305ca1  nop     dword ptr [rax+rax+00h]
0x180305ca6  test    eax, eax
0x180305ca8  jnz     loc_180305EDB
0x180305cae  mov     r12, [rsp+9A0h+hmenu]
0x180305cb3  mov     rcx, [rsp+9A0h+var_958]; HKEY
0x180305cb8  lea     r8, [rbp+8A0h+var_250]; unsigned __int16 *
0x180305cbf  call    ?SHLoadLegacyRegUIStringW@@YAJPEAUHKEY__@@PEBGPEAGI@Z; SHLoadLegacyRegUIStringW(HKEY__ *,ushort const *,ushort *,uint)
0x180305cc4  test    eax, eax
0x180305cc6  js      loc_180305E7A
0x180305ccc  xorps   xmm0, xmm0
0x180305ccf  lea     rdx, [rbp+8A0h+pclsid]; pclsid
0x180305cd3  xor     eax, eax
0x180305cd5  lea     rcx, [rbp+8A0h+psz]; psz
0x180305cdc  movups  xmmword ptr [rbp+8A0h+pclsid.Data1], xmm0
0x180305ce0  mov     [rbp+8A0h+var_8D0], eax
0x180305ce3  movups  xmmword ptr [rbp+8A0h+var_8E0.Data1], xmm0
0x180305ce7  call    cs:__imp_SHCLSIDFromString
0x180305cee  nop     dword ptr [rax+rax+00h]
0x180305cf3  mov     rcx, [rsp+9A0h+var_958]; HKEY
0x180305cf8  lea     rax, [rbp+8A0h+var_460]
0x180305cff  mov     [rsp+9A0h+var_978], 104h; unsigned int
0x180305d07  lea     rdx, aSearchguid; "SearchGUID"
0x180305d0e  mov     r9d, 2; int
0x180305d14  mov     [rsp+9A0h+phkResult], rax; unsigned __int16 *
0x180305d19  xor     r8d, r8d; unsigned __int16 *
0x180305d1c  mov     [rbp+8A0h+var_8E0.Data1], r13d
0x180305d20  call    ?SHRegGetStringEx@@YAJPEAUHKEY__@@PEBG1HPEAGK@Z; SHRegGetStringEx(HKEY__ *,ushort const *,ushort const *,int,ushort *,ulong)
0x180305d25  test    eax, eax
0x180305d27  js      short loc_180305D42
0x180305d29  lea     rdx, [rbp+8A0h+var_8E0.Data2]; pclsid
0x180305d2d  lea     rcx, [rbp+8A0h+var_460]; psz
0x180305d34  call    cs:__imp_SHCLSIDFromString
0x180305d3b  nop     dword ptr [rax+rax+00h]
0x180305d40  jmp     short loc_180305D4E
0x180305d42  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180305d49  movdqu  xmmword ptr [rbp+8A0h+var_8E0.Data2], xmm0
0x180305d4e  lea     rdx, SRCID_SFindComputer
0x180305d55  lea     rcx, [rbp+8A0h+var_8E0.Data2]
0x180305d59  call    IsEqualGUID
0x180305d5e  test    eax, eax
0x180305d60  jz      short loc_180305D7B
0x180305d62  mov     ecx, 40000022h; rest
0x180305d67  call    cs:__imp_SHRestricted
0x180305d6e  nop     dword ptr [rax+rax+00h]
0x180305d73  test    eax, eax
0x180305d75  jz      loc_180305E8B
0x180305d7b  lea     rdx, _GUID_169a0691_8df9_11d1_a1c4_00c04fd75d13
0x180305d82  lea     rcx, [rbp+8A0h+var_8E0.Data2]
0x180305d86  call    IsEqualGUID
0x180305d8b  mov     edi, eax
0x180305d8d  test    eax, eax
0x180305d8f  jz      short loc_180305DAA
0x180305d91  mov     ecx, 80h; rest
0x180305d96  call    cs:__imp_SHRestricted
0x180305d9d  nop     dword ptr [rax+rax+00h]
0x180305da2  test    eax, eax
0x180305da4  jnz     loc_180305E8B
0x180305daa  lea     rdx, SRCID_SFindPrinter
0x180305db1  lea     rcx, [rbp+8A0h+var_8E0.Data2]
0x180305db5  call    IsEqualGUID
0x180305dba  test    eax, eax
0x180305dbc  jnz     loc_180305E8B
0x180305dc2  lea     r8, [rbp+8A0h+pclsid]; pitem
0x180305dc6  mov     edx, 7FFFFFFFh; i
0x180305dcb  mov     rcx, rsi; hdsa
0x180305dce  call    DSA_InsertItem
0x180305dd3  cmp     eax, 0FFFFFFFFh
0x180305dd6  jz      loc_180305E7A
0x180305ddc  xor     edx, edx; Val
0x180305dde  lea     rcx, [rsp+9A0h+mi]; void *
0x180305de3  lea     r8d, [rdx+50h]; Size
0x180305de7  call    memset_0
0x180305dec  mov     rcx, [rsp+9A0h+var_958]; HKEY
0x180305df1  mov     [rsp+9A0h+mi.cbSize], 50h ; 'P'
0x180305df9  mov     qword ptr [rsp+9A0h+mi.fMask], 162h
0x180305e02  mov     [rsp+9A0h+mi.wID], ebx
0x180305e06  call    ?Static_ExtractIcon@@YAHPEAUHKEY__@@@Z; Static_ExtractIcon(HKEY__ *)
0x180305e0b  movsxd  rcx, eax
0x180305e0e  lea     rax, [rbp+8A0h+var_250]
0x180305e15  mov     [rbp+8A0h+mi.dwTypeData], rax
0x180305e19  mov     [rbp+8A0h+mi.dwItemData], rcx
0x180305e1d  test    r14d, r14d
0x180305e20  jnz     short loc_180305E45
0x180305e22  test    edi, edi
0x180305e24  jz      short loc_180305E45
0x180305e26  lea     r9, [rsp+9A0h+mi]; lpmi
0x180305e2b  xor     edx, edx; item
0x180305e2d  lea     r8d, [r14+1]; fByPosition
0x180305e31  mov     rcx, r12; hmenu
0x180305e34  call    cs:__imp_InsertMenuItemW
0x180305e3b  nop     dword ptr [rax+rax+00h]
0x180305e40  mov     r14d, eax
0x180305e43  jmp     short loc_180305E73
0x180305e45  cmp     [rsp+9A0h+var_96C], 0
0x180305e4a  mov     edx, 7FFFFFFFh
0x180305e4f  jnz     short loc_180305E59
0x180305e51  xor     edx, edx
0x180305e53  test    r14d, r14d
0x180305e56  setnz   dl; item
0x180305e59  lea     r9, [rsp+9A0h+mi]; lpmi
0x180305e5e  mov     r8d, 1; fByPosition
0x180305e64  mov     rcx, r12; hmenu
0x180305e67  call    cs:__imp_InsertMenuItemW
0x180305e6e  nop     dword ptr [rax+rax+00h]
0x180305e73  inc     ebx
0x180305e75  cmp     ebx, r15d
0x180305e78  ja      short loc_180305ED6
0x180305e7a  mov     rcx, [rsp+9A0h+var_958]; hKey
0x180305e7f  call    cs:__imp_RegCloseKey
0x180305e86  nop     dword ptr [rax+rax+00h]
0x180305e8b  inc     r13d
0x180305e8e  lea     r8, aD; "%d"
0x180305e95  mov     r9d, r13d
0x180305e98  lea     rcx, [rbp+8A0h+SubKey]; unsigned __int16 *
0x180305e9c  mov     edx, 20h ; ' '; unsigned __int64
0x180305ea1  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180305ea6  mov     rcx, [rsp+9A0h+var_950]; hKey
0x180305eab  lea     rax, [rsp+9A0h+var_958]
0x180305eb0  mov     r9d, 2000000h; samDesired
0x180305eb6  mov     [rsp+9A0h+phkResult], rax; phkResult
0x180305ebb  xor     r8d, r8d; ulOptions
0x180305ebe  lea     rdx, [rbp+8A0h+SubKey]; lpSubKey
0x180305ec2  call    cs:__imp_RegOpenKeyExW
0x180305ec9  nop     dword ptr [rax+rax+00h]
0x180305ece  test    eax, eax
0x180305ed0  jz      loc_180305CB3
0x180305ed6  mov     r12d, [rsp+9A0h+var_970]
0x180305edb  mov     rcx, [rsp+9A0h+var_950]; hKey
0x180305ee0  call    cs:__imp_RegCloseKey
0x180305ee7  nop     dword ptr [rax+rax+00h]
0x180305eec  mov     rcx, [rsp+9A0h+var_948]; hKey
0x180305ef1  lea     r8, [rbp+8A0h+Name]; lpName
0x180305ef5  inc     r12d
0x180305ef8  mov     r9d, 104h; cchName
0x180305efe  mov     edx, r12d; dwIndex
0x180305f01  mov     [rsp+9A0h+var_970], r12d
0x180305f06  call    cs:__imp_RegEnumKeyW
0x180305f0d  nop     dword ptr [rax+rax+00h]
0x180305f12  test    eax, eax
0x180305f14  jz      loc_180305BD6
0x180305f1a  mov     r13, [rsp+9A0h+var_960]
0x180305f1f  mov     rcx, [rsp+9A0h+var_948]; hKey
0x180305f24  call    cs:__imp_RegCloseKey
0x180305f2b  nop     dword ptr [rax+rax+00h]
0x180305f30  mov     [r13+20h], rsi
0x180305f34  mov     eax, ebx
0x180305f36  mov     rcx, [rbp+8A0h+var_40]
0x180305f3d  xor     rcx, rsp; StackCookie
0x180305f40  call    __security_check_cookie
0x180305f45  mov     rbx, [rsp+9A0h+arg_18]
0x180305f4d  add     rsp, 970h
0x180305f54  pop     r15
0x180305f56  pop     r14
0x180305f58  pop     r13
0x180305f5a  pop     r12
0x180305f5c  pop     rdi
0x180305f5d  pop     rsi
0x180305f5e  pop     rbp
0x180305f5f  retn
```
