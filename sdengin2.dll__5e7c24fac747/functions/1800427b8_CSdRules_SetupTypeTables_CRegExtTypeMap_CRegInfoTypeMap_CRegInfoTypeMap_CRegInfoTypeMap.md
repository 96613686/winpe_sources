# CSdRules::_SetupTypeTables(CRegExtTypeMap *,CRegInfoTypeMap *,CRegInfoTypeMap *,CRegInfoTypeMap *)

- ea: `0x1800427b8`
- end: `0x180042c1a`
- name: `?_SetupTypeTables@CSdRules@@AEAAJPEAVCRegExtTypeMap@@PEAVCRegInfoTypeMap@@11@Z`
- size: `1122`
- prototype: `int(CSdRules *__hidden this, struct CRegExtTypeMap *, struct CRegInfoTypeMap *, struct CRegInfoTypeMap *, struct CRegInfoTypeMap *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, installer_update`

## callers

- `0x18003dd0c`

## callees

- `0x18003e630`
- `0x1800427b8`
- `0x18006fe84`
- `0x18006ff8c`
- `0x180094b8c`
- `0x1800998c8`
- `0x180099bdc`
- `0x180099c84`
- `0x18009ae34`
- `0x1800c97ce`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180042a13`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180042a29`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180042bd2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180042bea`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180042a13`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180042a29`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180042bd2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180042bea`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800428a5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180042a50`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800428a5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180042a50`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800429b5`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800429b5`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180042903`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180042903`

## pseudocode

```c
__int64 __fastcall CSdRules::_SetupTypeTables(
        CSdRules *this,
        struct CRegExtTypeMap *a2,
        struct CRegInfoTypeMap *a3,
        struct CRegInfoTypeMap *a4,
        struct CRegInfoTypeMap *a5)
{
  __int16 v8; // ax
  int v9; // ebx
  struct CRegInfoTypeMap *v10; // r14
  LSTATUS v11; // eax
  LSTATUS v12; // eax
  DWORD i; // esi
  WCHAR *v14; // rdi
  HKEY v15; // rcx
  LSTATUS v16; // eax
  WCHAR *j; // rdx
  unsigned int v18; // ebx
  HKEY phkResult; // [rsp+60h] [rbp-71h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-69h] BYREF
  int String; // [rsp+70h] [rbp-61h] BYREF
  __int16 v23; // [rsp+74h] [rbp-5Dh]
  __int16 v24; // [rsp+76h] [rbp-5Bh]
  DWORD cchName; // [rsp+A8h] [rbp-29h] BYREF
  LPWSTR lpName; // [rsp+B0h] [rbp-21h] BYREF
  unsigned int v27[2]; // [rsp+B8h] [rbp-19h]
  unsigned __int16 *v28; // [rsp+C0h] [rbp-11h] BYREF
  __int64 v29; // [rsp+C8h] [rbp-9h]
  unsigned __int16 *v30; // [rsp+D0h] [rbp-1h] BYREF
  __int64 v31; // [rsp+D8h] [rbp+7h]
  unsigned __int16 *v32; // [rsp+E0h] [rbp+Fh] BYREF
  __int64 v33; // [rsp+E8h] [rbp+17h]
  DWORD cbMaxSubKeyLen; // [rsp+138h] [rbp+67h] BYREF

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&String, "CSdRules::_SetupTypeTables", 1742, 1);
  hKey = 0;
  phkResult = 0;
  cbMaxSubKeyLen = 0;
  cchName = 0;
  lpName = (LPWSTR)qword_1800E8530;
  *(_QWORD *)v27 = 0;
  v32 = (unsigned __int16 *)qword_1800E8530;
  v33 = 0;
  v30 = (unsigned __int16 *)qword_1800E8530;
  v31 = 0;
  v28 = (unsigned __int16 *)qword_1800E8530;
  v29 = 0;
  v8 = 1754;
  if ( !a2 || (v23 = 1754, v8 = 1755, !a3) || (v23 = 1755, v8 = 1756, !a4) || (v23 = 1756, v10 = a5, v8 = 1757, !a5) )
  {
    v9 = -2147024809;
LABEL_3:
    String = v9;
LABEL_4:
    v24 = v8;
    goto LABEL_50;
  }
  String = 0;
  v23 = 1757;
  v11 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Classes", 0, 0x20019u, &hKey);
  v9 = v11;
  if ( v11 > 0 )
    v9 = (unsigned __int16)v11 | 0x80070000;
  String = v9;
  v8 = 1760;
  if ( v9 < 0 )
    goto LABEL_4;
  v23 = 1760;
  v12 = RegQueryInfoKeyW(hKey, 0, 0, 0, 0, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0);
  v9 = v12;
  if ( v12 > 0 )
    v9 = (unsigned __int16)v12 | 0x80070000;
  String = v9;
  v8 = 1761;
  if ( v9 < 0 )
    goto LABEL_4;
  v23 = 1761;
  v8 = 1763;
  if ( cbMaxSubKeyLen == -1 )
  {
    v9 = -2147024362;
    goto LABEL_3;
  }
  String = 0;
  v23 = 1763;
  v9 = CBsString::ExtendBuffer((CBsString *)&lpName, cbMaxSubKeyLen + 1);
  String = v9;
  v8 = 1764;
  if ( v9 < 0 )
    goto LABEL_4;
  v23 = 1764;
  for ( i = 0; ; ++i )
  {
    CBsString::Empty((CBsString *)&lpName);
    CBsString::Empty((CBsString *)&v32);
    CBsString::Empty((CBsString *)&v30);
    CBsString::Empty((CBsString *)&v28);
    cchName = cbMaxSubKeyLen + 1;
    v9 = RegEnumKeyExW(hKey, i, lpName, &cchName, 0, 0, 0, 0);
    CBsString::BoundUpdateLength((CBsString *)&lpName, v27[1]);
    if ( v9 == 259 )
      break;
    if ( v9 > 0 )
      v9 = (unsigned __int16)v9 | 0x80070000;
    String = v9;
    v8 = 1781;
    if ( v9 < 0 )
      goto LABEL_4;
    v23 = 1781;
    v14 = lpName;
    if ( *lpName == 46 )
    {
      v15 = phkResult;
      if ( phkResult )
      {
        if ( phkResult != HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
        {
          RegCloseKey(phkResult);
          v15 = 0;
          phkResult = 0;
        }
        if ( (unsigned __int64)v15 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
        {
          RegCloseKey(v15);
          phkResult = 0;
        }
      }
      v16 = RegOpenKeyExW(hKey, v14, 0, 0x20019u, &phkResult);
      v9 = v16;
      if ( v16 > 0 )
        v9 = (unsigned __int16)v16 | 0x80070000;
      String = v9;
      if ( v9 < 0 )
      {
        v24 = 1789;
        goto LABEL_50;
      }
      v23 = 1789;
      String = SxRegReadString(phkResult, L"Content Type", (struct CBsString *)&v32);
      if ( String < 0 )
      {
        CBsString::Empty((CBsString *)&v32);
        String = 0;
      }
      String = SxRegReadString(phkResult, L"PerceivedType", (struct CBsString *)&v30);
      if ( String < 0 )
      {
        CBsString::Empty((CBsString *)&v30);
        String = 0;
      }
      String = SxRegReadString(phkResult, (LPCWSTR)&Data, (struct CBsString *)&v28);
      if ( String < 0 )
      {
        CBsString::Empty((CBsString *)&v28);
        String = 0;
      }
      for ( j = v14; *j == 46; ++j )
        ;
      v18 = v27[0];
      if ( j != v14 )
      {
        v18 = v27[0] - (j - v14);
        memmove_0(v14, j, 2LL * (v18 + 1));
        v27[0] = v18;
      }
      if ( v18 && ((_DWORD)v33 || (_DWORD)v31 || (_DWORD)v29) )
      {
        v9 = CSdRules::_AddRegInfoToTable(this, a2, a3, a4, v10, v14, v32, v30, v28);
        String = v9;
        v8 = 1824;
        if ( v9 < 0 )
          goto LABEL_4;
        v23 = 1824;
      }
    }
  }
  v9 = String;
LABEL_50:
  CBsString::_Release((CBsString *)&v28);
  CBsString::_Release((CBsString *)&v30);
  CBsString::_Release((CBsString *)&v32);
  CBsString::_Release((CBsString *)&lpName);
  if ( (unsigned __int64)phkResult - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    RegCloseKey(phkResult);
    phkResult = 0;
  }
  if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&String);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800427b8  mov     [rsp-8+arg_10], rbx
0x1800427bd  mov     [rsp-8+arg_0], rcx
0x1800427c2  push    rbp
0x1800427c3  push    rsi
0x1800427c4  push    rdi
0x1800427c5  push    r12
0x1800427c7  push    r13
0x1800427c9  push    r14
0x1800427cb  push    r15
0x1800427cd  lea     rbp, [rsp-1Fh]
0x1800427d2  sub     rsp, 0F0h
0x1800427d9  mov     r15, r9
0x1800427dc  mov     r12, r8
0x1800427df  mov     r13, rdx
0x1800427e2  mov     r9d, 1; unsigned __int16
0x1800427e8  mov     r8d, 6CEh; unsigned __int16
0x1800427ee  lea     rdx, aCsdrulesSetupt; "CSdRules::_SetupTypeTables"
0x1800427f5  lea     rcx, [rbp+4Fh+var_B0]; this
0x1800427f9  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x1800427fe  xor     edi, edi
0x180042800  mov     [rbp+4Fh+hKey], rdi
0x180042804  mov     [rbp+4Fh+var_C0], rdi
0x180042808  mov     [rbp+4Fh+cbMaxSubKeyLen], edi
0x18004280b  mov     [rbp+4Fh+cchName], edi
0x18004280e  lea     rax, qword_1800E8530
0x180042815  mov     [rbp+4Fh+lpName], rax
0x180042819  mov     qword ptr [rbp+4Fh+var_68], rdi
0x18004281d  mov     [rbp+4Fh+var_40], rax
0x180042821  mov     [rbp+4Fh+var_38], rdi
0x180042825  mov     [rbp+4Fh+var_50], rax
0x180042829  mov     [rbp+4Fh+var_48], rdi
0x18004282d  mov     [rbp+4Fh+var_60], rax
0x180042831  mov     [rbp+4Fh+var_58], rdi
0x180042835  mov     eax, 6DAh
0x18004283a  test    r13, r13
0x18004283d  jnz     short loc_180042850
0x18004283f  mov     ebx, 80070057h
0x180042844  mov     [rbp+4Fh+var_B0], ebx
0x180042847  mov     [rbp+4Fh+var_AA], ax
0x18004284b  jmp     loc_180042BA0
0x180042850  mov     [rbp+4Fh+var_AC], ax
0x180042854  mov     eax, 6DBh
0x180042859  test    r12, r12
0x18004285c  jz      short loc_18004283F
0x18004285e  mov     [rbp+4Fh+var_AC], ax
0x180042862  mov     eax, 6DCh
0x180042867  test    r15, r15
0x18004286a  jz      short loc_18004283F
0x18004286c  mov     [rbp+4Fh+var_AC], ax
0x180042870  mov     r14, [rbp+4Fh+arg_20]
0x180042874  mov     eax, 6DDh
0x180042879  test    r14, r14
0x18004287c  jz      short loc_18004283F
0x18004287e  mov     [rbp+4Fh+var_B0], edi
0x180042881  mov     [rbp+4Fh+var_AC], ax
0x180042885  lea     rax, [rbp+4Fh+hKey]
0x180042889  mov     [rsp+120h+phkResult], rax; phkResult
0x18004288e  mov     r9d, 20019h; samDesired
0x180042894  xor     r8d, r8d; ulOptions
0x180042897  lea     rdx, c_wszHKLMClasses; "SOFTWARE\\Classes"
0x18004289e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800428a5  call    cs:__imp_RegOpenKeyExW
0x1800428ab  mov     ebx, eax
0x1800428ad  mov     esi, 80070000h
0x1800428b2  test    eax, eax
0x1800428b4  jle     short loc_1800428BB
0x1800428b6  movzx   ebx, ax
0x1800428b9  or      ebx, esi
0x1800428bb  mov     [rbp+4Fh+var_B0], ebx
0x1800428be  mov     eax, 6E0h
0x1800428c3  test    ebx, ebx
0x1800428c5  js      short loc_180042847
0x1800428c7  mov     [rbp+4Fh+var_AC], ax
0x1800428cb  mov     [rsp+120h+lpftLastWriteTime], rdi; lpftLastWriteTime
0x1800428d0  mov     [rsp+120h+lpcbSecurityDescriptor], rdi; lpcbSecurityDescriptor
0x1800428d5  mov     [rsp+120h+lpcbMaxValueLen], rdi; lpcbMaxValueLen
0x1800428da  mov     [rsp+120h+lpcbMaxValueNameLen], rdi; lpcbMaxValueNameLen
0x1800428df  mov     [rsp+120h+lpcValues], rdi; lpcValues
0x1800428e4  mov     [rsp+120h+lpcbMaxClassLen], rdi; lpcbMaxClassLen
0x1800428e9  lea     rax, [rbp+4Fh+cbMaxSubKeyLen]
0x1800428ed  mov     [rsp+120h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x1800428f2  mov     [rsp+120h+phkResult], rdi; lpcSubKeys
0x1800428f7  xor     r9d, r9d; lpReserved
0x1800428fa  xor     r8d, r8d; lpcchClass
0x1800428fd  xor     edx, edx; lpClass
0x1800428ff  mov     rcx, [rbp+4Fh+hKey]; hKey
0x180042903  call    cs:__imp_RegQueryInfoKeyW
0x180042909  mov     ebx, eax
0x18004290b  test    eax, eax
0x18004290d  jle     short loc_180042914
0x18004290f  movzx   ebx, ax
0x180042912  or      ebx, esi
0x180042914  mov     [rbp+4Fh+var_B0], ebx
0x180042917  mov     eax, 6E1h
0x18004291c  test    ebx, ebx
0x18004291e  js      loc_180042847
0x180042924  mov     [rbp+4Fh+var_AC], ax
0x180042928  mov     edx, [rbp+4Fh+cbMaxSubKeyLen]
0x18004292b  add     edx, 1; unsigned int
0x18004292e  mov     eax, 6E3h
0x180042933  jnz     short loc_18004293F
0x180042935  mov     ebx, 80070216h
0x18004293a  jmp     loc_180042844
0x18004293f  mov     [rbp+4Fh+var_B0], edi
0x180042942  mov     [rbp+4Fh+var_AC], ax
0x180042946  lea     rcx, [rbp+4Fh+lpName]; this
0x18004294a  call    ?ExtendBuffer@CBsString@@QEAAJK@Z; CBsString::ExtendBuffer(ulong)
0x18004294f  mov     ebx, eax
0x180042951  mov     [rbp+4Fh+var_B0], eax
0x180042954  test    eax, eax
0x180042956  mov     eax, 6E4h
0x18004295b  js      loc_180042847
0x180042961  mov     [rbp+4Fh+var_AC], ax
0x180042965  mov     esi, edi
0x180042967  lea     rcx, [rbp+4Fh+lpName]; this
0x18004296b  call    ?Empty@CBsString@@QEAAXXZ; CBsString::Empty(void)
0x180042970  lea     rcx, [rbp+4Fh+var_40]; this
0x180042974  call    ?Empty@CBsString@@QEAAXXZ; CBsString::Empty(void)
0x180042979  lea     rcx, [rbp+4Fh+var_50]; this
0x18004297d  call    ?Empty@CBsString@@QEAAXXZ; CBsString::Empty(void)
0x180042982  lea     rcx, [rbp+4Fh+var_60]; this
0x180042986  call    ?Empty@CBsString@@QEAAXXZ; CBsString::Empty(void)
0x18004298b  mov     edx, [rbp+4Fh+cbMaxSubKeyLen]
0x18004298e  inc     edx
0x180042990  mov     [rbp+4Fh+cchName], edx
0x180042993  mov     [rsp+120h+lpcValues], rdi; lpftLastWriteTime
0x180042998  mov     [rsp+120h+lpcbMaxClassLen], rdi; lpcchClass
0x18004299d  mov     [rsp+120h+lpcbMaxSubKeyLen], rdi; lpClass
0x1800429a2  mov     [rsp+120h+phkResult], rdi; lpReserved
0x1800429a7  lea     r9, [rbp+4Fh+cchName]; lpcchName
0x1800429ab  mov     r8, [rbp+4Fh+lpName]; lpName
0x1800429af  mov     edx, esi; dwIndex
0x1800429b1  mov     rcx, [rbp+4Fh+hKey]; hKey
0x1800429b5  call    cs:__imp_RegEnumKeyExW
0x1800429bb  mov     ebx, eax
0x1800429bd  mov     edx, [rbp+4Fh+var_68+4]; unsigned int
0x1800429c0  lea     rcx, [rbp+4Fh+lpName]; this
0x1800429c4  call    ?BoundUpdateLength@CBsString@@QEAAXK@Z; CBsString::BoundUpdateLength(ulong)
0x1800429c9  cmp     ebx, 103h
0x1800429cf  jz      loc_180042B9D
0x1800429d5  test    ebx, ebx
0x1800429d7  jle     short loc_1800429E2
0x1800429d9  movzx   ebx, bx
0x1800429dc  or      ebx, 80070000h
0x1800429e2  mov     [rbp+4Fh+var_B0], ebx
0x1800429e5  mov     eax, 6F5h
0x1800429ea  test    ebx, ebx
0x1800429ec  js      loc_180042847
0x1800429f2  mov     [rbp+4Fh+var_AC], ax
0x1800429f6  mov     rdi, [rbp+4Fh+lpName]
0x1800429fa  cmp     word ptr [rdi], 2Eh ; '.'
0x1800429fe  jnz     loc_180042B8C
0x180042a04  mov     rcx, [rbp+4Fh+var_C0]; hKey
0x180042a08  test    rcx, rcx
0x180042a0b  jz      short loc_180042A37
0x180042a0d  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180042a11  jz      short loc_180042A1F
0x180042a13  call    cs:__imp_RegCloseKey
0x180042a19  xor     ecx, ecx; hKey
0x180042a1b  mov     [rbp+4Fh+var_C0], rcx
0x180042a1f  lea     rax, [rcx-1]
0x180042a23  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180042a27  ja      short loc_180042A37
0x180042a29  call    cs:__imp_RegCloseKey
0x180042a2f  mov     [rbp+4Fh+var_C0], 0
0x180042a37  lea     rax, [rbp+4Fh+var_C0]
0x180042a3b  mov     [rsp+120h+phkResult], rax; phkResult
0x180042a40  mov     r9d, 20019h; samDesired
0x180042a46  xor     r8d, r8d; ulOptions
0x180042a49  mov     rdx, rdi; lpSubKey
0x180042a4c  mov     rcx, [rbp+4Fh+hKey]; hKey
0x180042a50  call    cs:__imp_RegOpenKeyExW
0x180042a56  mov     ebx, eax
0x180042a58  test    eax, eax
0x180042a5a  jle     short loc_180042A65
0x180042a5c  movzx   ebx, ax
0x180042a5f  or      ebx, 80070000h
0x180042a65  mov     [rbp+4Fh+var_B0], ebx
0x180042a68  mov     eax, 6FDh
0x180042a6d  test    ebx, ebx
0x180042a6f  js      loc_180042B95
0x180042a75  mov     [rbp+4Fh+var_AC], ax
0x180042a79  lea     r8, [rbp+4Fh+var_40]; this
0x180042a7d  lea     rdx, c_wszContentType; "Content Type"
0x180042a84  mov     rcx, [rbp+4Fh+var_C0]; hKey
0x180042a88  call    ?SxRegReadString@@YAJPEAUHKEY__@@PEBGPEAVCBsString@@@Z; SxRegReadString(HKEY__ *,ushort const *,CBsString *)
0x180042a8d  mov     [rbp+4Fh+var_B0], eax
0x180042a90  xor     ebx, ebx
0x180042a92  test    eax, eax
0x180042a94  jns     short loc_180042AA2
0x180042a96  lea     rcx, [rbp+4Fh+var_40]; this
0x180042a9a  call    ?Empty@CBsString@@QEAAXXZ; CBsString::Empty(void)
0x180042a9f  mov     [rbp+4Fh+var_B0], ebx
0x180042aa2  lea     r8, [rbp+4Fh+var_50]; this
0x180042aa6  lea     rdx, c_wszPerceived; "PerceivedType"
0x180042aad  mov     rcx, [rbp+4Fh+var_C0]; hKey
0x180042ab1  call    ?SxRegReadString@@YAJPEAUHKEY__@@PEBGPEAVCBsString@@@Z; SxRegReadString(HKEY__ *,ushort const *,CBsString *)
0x180042ab6  mov     [rbp+4Fh+var_B0], eax
0x180042ab9  test    eax, eax
0x180042abb  jns     short loc_180042AC9
0x180042abd  lea     rcx, [rbp+4Fh+var_50]; this
0x180042ac1  call    ?Empty@CBsString@@QEAAXXZ; CBsString::Empty(void)
0x180042ac6  mov     [rbp+4Fh+var_B0], ebx
0x180042ac9  lea     r8, [rbp+4Fh+var_60]; this
0x180042acd  lea     rdx, Data; lpValueName
0x180042ad4  mov     rcx, [rbp+4Fh+var_C0]; hKey
0x180042ad8  call    ?SxRegReadString@@YAJPEAUHKEY__@@PEBGPEAVCBsString@@@Z; SxRegReadString(HKEY__ *,ushort const *,CBsString *)
0x180042add  mov     [rbp+4Fh+var_B0], eax
0x180042ae0  test    eax, eax
0x180042ae2  jns     short loc_180042AF0
0x180042ae4  lea     rcx, [rbp+4Fh+var_60]; this
0x180042ae8  call    ?Empty@CBsString@@QEAAXXZ; CBsString::Empty(void)
0x180042aed  mov     [rbp+4Fh+var_B0], ebx
0x180042af0  mov     rdx, rdi
0x180042af3  cmp     word ptr [rdi], 2Eh ; '.'
0x180042af7  jnz     short loc_180042B03
0x180042af9  add     rdx, 2; Src
0x180042afd  cmp     word ptr [rdx], 2Eh ; '.'
0x180042b01  jz      short loc_180042AF9
0x180042b03  mov     ebx, [rbp+4Fh+var_68]
0x180042b06  cmp     rdx, rdi
0x180042b09  jz      short loc_180042B28
0x180042b0b  mov     rax, rdx
0x180042b0e  sub     rax, rdi
0x180042b11  sar     rax, 1
0x180042b14  sub     ebx, eax
0x180042b16  lea     r8d, [rbx+1]
0x180042b1a  add     r8, r8; Size
0x180042b1d  mov     rcx, rdi; void *
0x180042b20  call    memmove_0
0x180042b25  mov     [rbp+4Fh+var_68], ebx
0x180042b28  xor     eax, eax
0x180042b2a  test    ebx, ebx
0x180042b2c  jz      short loc_180042B8C
0x180042b2e  cmp     dword ptr [rbp+4Fh+var_38], eax
0x180042b31  jnz     short loc_180042B3D
0x180042b33  cmp     dword ptr [rbp+4Fh+var_48], eax
0x180042b36  jnz     short loc_180042B3D
0x180042b38  cmp     dword ptr [rbp+4Fh+var_58], eax
0x180042b3b  jz      short loc_180042B8C
0x180042b3d  mov     rax, [rbp+4Fh+var_60]
0x180042b41  mov     [rsp+120h+lpcbMaxValueNameLen], rax; unsigned __int16 *
0x180042b46  mov     rax, [rbp+4Fh+var_50]
0x180042b4a  mov     [rsp+120h+lpcValues], rax; unsigned __int16 *
0x180042b4f  mov     rax, [rbp+4Fh+var_40]
0x180042b53  mov     [rsp+120h+lpcbMaxClassLen], rax; unsigned __int16 *
0x180042b58  mov     [rsp+120h+lpcbMaxSubKeyLen], rdi; unsigned __int16 *
0x180042b5d  mov     [rsp+120h+phkResult], r14; struct CRegInfoTypeMap *
0x180042b62  mov     r9, r15; struct CRegInfoTypeMap *
0x180042b65  mov     r8, r12; struct CRegInfoTypeMap *
0x180042b68  mov     rdx, r13; struct CRegExtTypeMap *
0x180042b6b  mov     rcx, [rbp+4Fh+arg_0]; this
0x180042b6f  call    ?_AddRegInfoToTable@CSdRules@@AEAAJPEAVCRegExtTypeMap@@PEAVCRegInfoTypeMap@@11PEBG222@Z; CSdRules::_AddRegInfoToTable(CRegExtTypeMap *,CRegInfoTypeMap *,CRegInfoTypeMap *,CRegInfoTypeMap *,ushort const *,ushort const *,ushort const *,ushort const *)
0x180042b74  mov     ebx, eax
0x180042b76  mov     [rbp+4Fh+var_B0], eax
0x180042b79  xor     edi, edi
0x180042b7b  test    eax, eax
0x180042b7d  mov     eax, 720h
0x180042b82  js      loc_180042847
0x180042b88  mov     [rbp+4Fh+var_AC], ax
0x180042b8c  inc     esi
0x180042b8e  xor     edi, edi
0x180042b90  jmp     loc_180042967
0x180042b95  mov     [rbp+4Fh+var_AA], ax
0x180042b99  xor     edi, edi
0x180042b9b  jmp     short loc_180042BA0
0x180042b9d  mov     ebx, [rbp+4Fh+var_B0]
0x180042ba0  lea     rcx, [rbp+4Fh+var_60]; this
0x180042ba4  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x180042ba9  lea     rcx, [rbp+4Fh+var_50]; this
0x180042bad  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x180042bb2  lea     rcx, [rbp+4Fh+var_40]; this
0x180042bb6  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x180042bbb  lea     rcx, [rbp+4Fh+lpName]; this
0x180042bbf  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x180042bc4  mov     rcx, [rbp+4Fh+var_C0]; hKey
0x180042bc8  lea     rax, [rcx-1]
0x180042bcc  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180042bd0  ja      short loc_180042BDC
0x180042bd2  call    cs:__imp_RegCloseKey
0x180042bd8  mov     [rbp+4Fh+var_C0], rdi
0x180042bdc  mov     rcx, [rbp+4Fh+hKey]; hKey
0x180042be0  lea     rdx, [rcx-1]
0x180042be4  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180042be8  ja      short loc_180042BF4
0x180042bea  call    cs:__imp_RegCloseKey
0x180042bf0  mov     [rbp+4Fh+hKey], rdi
0x180042bf4  lea     rcx, [rbp+4Fh+var_B0]; this
0x180042bf8  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180042bfd  mov     eax, ebx
0x180042bff  mov     rbx, [rsp+120h+arg_10]
0x180042c07  add     rsp, 0F0h
0x180042c0e  pop     r15
0x180042c10  pop     r14
0x180042c12  pop     r13
0x180042c14  pop     r12
0x180042c16  pop     rdi
0x180042c17  pop     rsi
0x180042c18  pop     rbp
0x180042c19  retn
  ... truncated ...
```
