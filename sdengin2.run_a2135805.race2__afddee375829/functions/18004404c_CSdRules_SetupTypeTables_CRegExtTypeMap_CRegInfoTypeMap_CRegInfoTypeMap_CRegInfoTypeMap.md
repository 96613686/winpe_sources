# CSdRules::_SetupTypeTables(CRegExtTypeMap *,CRegInfoTypeMap *,CRegInfoTypeMap *,CRegInfoTypeMap *)

- ea: `0x18004404c`
- end: `0x1800444e3`
- name: `?_SetupTypeTables@CSdRules@@AEAAJPEAVCRegExtTypeMap@@PEAVCRegInfoTypeMap@@11@Z`
- size: `1175`
- prototype: `int(CSdRules *__hidden this, struct CRegExtTypeMap *, struct CRegInfoTypeMap *, struct CRegInfoTypeMap *, struct CRegInfoTypeMap *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, installer_update`

## callers

- `0x18003f41c`

## callees

- `0x18003fd64`
- `0x18004404c`
- `0x180072e08`
- `0x180072f14`
- `0x180098ebc`
- `0x18009dee8`
- `0x18009e234`
- `0x18009e2e8`
- `0x18009f560`
- `0x1800cf55e`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800442bd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800442d9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004448e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800444ac`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800442bd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800442d9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004448e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800444ac`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180044139`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180044306`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180044139`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180044306`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180044259`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180044259`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800441a1`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800441a1`

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

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&String, "CSdRules::_SetupTypeTables", 0x6CEu, 1u);
  hKey = 0;
  phkResult = 0;
  cbMaxSubKeyLen = 0;
  cchName = 0;
  lpName = (LPWSTR)qword_1800EE510;
  *(_QWORD *)v27 = 0;
  v32 = (unsigned __int16 *)qword_1800EE510;
  v33 = 0;
  v30 = (unsigned __int16 *)qword_1800EE510;
  v31 = 0;
  v28 = (unsigned __int16 *)qword_1800EE510;
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
0x18004404c  mov     [rsp-8+arg_10], rbx
0x180044051  mov     [rsp-8+arg_0], rcx
0x180044056  push    rbp
0x180044057  push    rsi
0x180044058  push    rdi
0x180044059  push    r12
0x18004405b  push    r13
0x18004405d  push    r14
0x18004405f  push    r15
0x180044061  lea     rbp, [rsp-1Fh]
0x180044066  sub     rsp, 0F0h
0x18004406d  mov     r15, r9
0x180044070  mov     r12, r8
0x180044073  mov     r13, rdx
0x180044076  mov     r9d, 1; unsigned __int16
0x18004407c  mov     r8d, 6CEh; unsigned __int16
0x180044082  lea     rdx, aCsdrulesSetupt; "CSdRules::_SetupTypeTables"
0x180044089  lea     rcx, [rbp+4Fh+var_B0]; this
0x18004408d  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180044092  xor     edi, edi
0x180044094  mov     [rbp+4Fh+hKey], rdi
0x180044098  mov     [rbp+4Fh+var_C0], rdi
0x18004409c  mov     [rbp+4Fh+cbMaxSubKeyLen], edi
0x18004409f  mov     [rbp+4Fh+cchName], edi
0x1800440a2  lea     rax, qword_1800EE510
0x1800440a9  mov     [rbp+4Fh+lpName], rax
0x1800440ad  mov     qword ptr [rbp+4Fh+var_68], rdi
0x1800440b1  mov     [rbp+4Fh+var_40], rax
0x1800440b5  mov     [rbp+4Fh+var_38], rdi
0x1800440b9  mov     [rbp+4Fh+var_50], rax
0x1800440bd  mov     [rbp+4Fh+var_48], rdi
0x1800440c1  mov     [rbp+4Fh+var_60], rax
0x1800440c5  mov     [rbp+4Fh+var_58], rdi
0x1800440c9  mov     eax, 6DAh
0x1800440ce  test    r13, r13
0x1800440d1  jnz     short loc_1800440E4
0x1800440d3  mov     ebx, 80070057h
0x1800440d8  mov     [rbp+4Fh+var_B0], ebx
0x1800440db  mov     [rbp+4Fh+var_AA], ax
0x1800440df  jmp     loc_18004445C
0x1800440e4  mov     [rbp+4Fh+var_AC], ax
0x1800440e8  mov     eax, 6DBh
0x1800440ed  test    r12, r12
0x1800440f0  jz      short loc_1800440D3
0x1800440f2  mov     [rbp+4Fh+var_AC], ax
0x1800440f6  mov     eax, 6DCh
0x1800440fb  test    r15, r15
0x1800440fe  jz      short loc_1800440D3
0x180044100  mov     [rbp+4Fh+var_AC], ax
0x180044104  mov     r14, [rbp+4Fh+arg_20]
0x180044108  mov     eax, 6DDh
0x18004410d  test    r14, r14
0x180044110  jz      short loc_1800440D3
0x180044112  mov     [rbp+4Fh+var_B0], edi
0x180044115  mov     [rbp+4Fh+var_AC], ax
0x180044119  lea     rax, [rbp+4Fh+hKey]
0x18004411d  mov     [rsp+120h+phkResult], rax; phkResult
0x180044122  mov     r9d, 20019h; samDesired
0x180044128  xor     r8d, r8d; ulOptions
0x18004412b  lea     rdx, c_wszHKLMClasses; "SOFTWARE\\Classes"
0x180044132  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180044139  call    cs:__imp_RegOpenKeyExW
0x180044140  nop     dword ptr [rax+rax+00h]
0x180044145  mov     ebx, eax
0x180044147  mov     esi, 80070000h
0x18004414c  test    eax, eax
0x18004414e  jle     short loc_180044155
0x180044150  movzx   ebx, ax
0x180044153  or      ebx, esi
0x180044155  mov     [rbp+4Fh+var_B0], ebx
0x180044158  mov     eax, 6E0h
0x18004415d  test    ebx, ebx
0x18004415f  js      loc_1800440DB
0x180044165  mov     [rbp+4Fh+var_AC], ax
0x180044169  mov     [rsp+120h+lpftLastWriteTime], rdi; lpftLastWriteTime
0x18004416e  mov     [rsp+120h+lpcbSecurityDescriptor], rdi; lpcbSecurityDescriptor
0x180044173  mov     [rsp+120h+lpcbMaxValueLen], rdi; lpcbMaxValueLen
0x180044178  mov     [rsp+120h+lpcbMaxValueNameLen], rdi; lpcbMaxValueNameLen
0x18004417d  mov     [rsp+120h+lpcValues], rdi; lpcValues
0x180044182  mov     [rsp+120h+lpcbMaxClassLen], rdi; lpcbMaxClassLen
0x180044187  lea     rax, [rbp+4Fh+cbMaxSubKeyLen]
0x18004418b  mov     [rsp+120h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x180044190  mov     [rsp+120h+phkResult], rdi; lpcSubKeys
0x180044195  xor     r9d, r9d; lpReserved
0x180044198  xor     r8d, r8d; lpcchClass
0x18004419b  xor     edx, edx; lpClass
0x18004419d  mov     rcx, [rbp+4Fh+hKey]; hKey
0x1800441a1  call    cs:__imp_RegQueryInfoKeyW
0x1800441a8  nop     dword ptr [rax+rax+00h]
0x1800441ad  mov     ebx, eax
0x1800441af  test    eax, eax
0x1800441b1  jle     short loc_1800441B8
0x1800441b3  movzx   ebx, ax
0x1800441b6  or      ebx, esi
0x1800441b8  mov     [rbp+4Fh+var_B0], ebx
0x1800441bb  mov     eax, 6E1h
0x1800441c0  test    ebx, ebx
0x1800441c2  js      loc_1800440DB
0x1800441c8  mov     [rbp+4Fh+var_AC], ax
0x1800441cc  mov     edx, [rbp+4Fh+cbMaxSubKeyLen]
0x1800441cf  add     edx, 1; unsigned int
0x1800441d2  mov     eax, 6E3h
0x1800441d7  jnz     short loc_1800441E3
0x1800441d9  mov     ebx, 80070216h
0x1800441de  jmp     loc_1800440D8
0x1800441e3  mov     [rbp+4Fh+var_B0], edi
0x1800441e6  mov     [rbp+4Fh+var_AC], ax
0x1800441ea  lea     rcx, [rbp+4Fh+lpName]; this
0x1800441ee  call    ?ExtendBuffer@CBsString@@QEAAJK@Z; CBsString::ExtendBuffer(ulong)
0x1800441f3  mov     ebx, eax
0x1800441f5  mov     [rbp+4Fh+var_B0], eax
0x1800441f8  test    eax, eax
0x1800441fa  mov     eax, 6E4h
0x1800441ff  js      loc_1800440DB
0x180044205  mov     [rbp+4Fh+var_AC], ax
0x180044209  mov     esi, edi
0x18004420b  lea     rcx, [rbp+4Fh+lpName]; this
0x18004420f  call    ?Empty@CBsString@@QEAAXXZ; CBsString::Empty(void)
0x180044214  lea     rcx, [rbp+4Fh+var_40]; this
0x180044218  call    ?Empty@CBsString@@QEAAXXZ; CBsString::Empty(void)
0x18004421d  lea     rcx, [rbp+4Fh+var_50]; this
0x180044221  call    ?Empty@CBsString@@QEAAXXZ; CBsString::Empty(void)
0x180044226  lea     rcx, [rbp+4Fh+var_60]; this
0x18004422a  call    ?Empty@CBsString@@QEAAXXZ; CBsString::Empty(void)
0x18004422f  mov     edx, [rbp+4Fh+cbMaxSubKeyLen]
0x180044232  inc     edx
0x180044234  mov     [rbp+4Fh+cchName], edx
0x180044237  mov     [rsp+120h+lpcValues], rdi; lpftLastWriteTime
0x18004423c  mov     [rsp+120h+lpcbMaxClassLen], rdi; lpcchClass
0x180044241  mov     [rsp+120h+lpcbMaxSubKeyLen], rdi; lpClass
0x180044246  mov     [rsp+120h+phkResult], rdi; lpReserved
0x18004424b  lea     r9, [rbp+4Fh+cchName]; lpcchName
0x18004424f  mov     r8, [rbp+4Fh+lpName]; lpName
0x180044253  mov     edx, esi; dwIndex
0x180044255  mov     rcx, [rbp+4Fh+hKey]; hKey
0x180044259  call    cs:__imp_RegEnumKeyExW
0x180044260  nop     dword ptr [rax+rax+00h]
0x180044265  mov     ebx, eax
0x180044267  mov     edx, [rbp+4Fh+var_68+4]; unsigned int
0x18004426a  lea     rcx, [rbp+4Fh+lpName]; this
0x18004426e  call    ?BoundUpdateLength@CBsString@@QEAAXK@Z; CBsString::BoundUpdateLength(ulong)
0x180044273  cmp     ebx, 103h
0x180044279  jz      loc_180044459
0x18004427f  test    ebx, ebx
0x180044281  jle     short loc_18004428C
0x180044283  movzx   ebx, bx
0x180044286  or      ebx, 80070000h
0x18004428c  mov     [rbp+4Fh+var_B0], ebx
0x18004428f  mov     eax, 6F5h
0x180044294  test    ebx, ebx
0x180044296  js      loc_1800440DB
0x18004429c  mov     [rbp+4Fh+var_AC], ax
0x1800442a0  mov     rdi, [rbp+4Fh+lpName]
0x1800442a4  cmp     word ptr [rdi], 2Eh ; '.'
0x1800442a8  jnz     loc_180044448
0x1800442ae  mov     rcx, [rbp+4Fh+var_C0]; hKey
0x1800442b2  test    rcx, rcx
0x1800442b5  jz      short loc_1800442ED
0x1800442b7  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800442bb  jz      short loc_1800442CF
0x1800442bd  call    cs:__imp_RegCloseKey
0x1800442c4  nop     dword ptr [rax+rax+00h]
0x1800442c9  xor     ecx, ecx; hKey
0x1800442cb  mov     [rbp+4Fh+var_C0], rcx
0x1800442cf  lea     rax, [rcx-1]
0x1800442d3  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800442d7  ja      short loc_1800442ED
0x1800442d9  call    cs:__imp_RegCloseKey
0x1800442e0  nop     dword ptr [rax+rax+00h]
0x1800442e5  mov     [rbp+4Fh+var_C0], 0
0x1800442ed  lea     rax, [rbp+4Fh+var_C0]
0x1800442f1  mov     [rsp+120h+phkResult], rax; phkResult
0x1800442f6  mov     r9d, 20019h; samDesired
0x1800442fc  xor     r8d, r8d; ulOptions
0x1800442ff  mov     rdx, rdi; lpSubKey
0x180044302  mov     rcx, [rbp+4Fh+hKey]; hKey
0x180044306  call    cs:__imp_RegOpenKeyExW
0x18004430d  nop     dword ptr [rax+rax+00h]
0x180044312  mov     ebx, eax
0x180044314  test    eax, eax
0x180044316  jle     short loc_180044321
0x180044318  movzx   ebx, ax
0x18004431b  or      ebx, 80070000h
0x180044321  mov     [rbp+4Fh+var_B0], ebx
0x180044324  mov     eax, 6FDh
0x180044329  test    ebx, ebx
0x18004432b  js      loc_180044451
0x180044331  mov     [rbp+4Fh+var_AC], ax
0x180044335  lea     r8, [rbp+4Fh+var_40]; this
0x180044339  lea     rdx, c_wszContentType; "Content Type"
0x180044340  mov     rcx, [rbp+4Fh+var_C0]; hKey
0x180044344  call    ?SxRegReadString@@YAJPEAUHKEY__@@PEBGPEAVCBsString@@@Z; SxRegReadString(HKEY__ *,ushort const *,CBsString *)
0x180044349  mov     [rbp+4Fh+var_B0], eax
0x18004434c  xor     ebx, ebx
0x18004434e  test    eax, eax
0x180044350  jns     short loc_18004435E
0x180044352  lea     rcx, [rbp+4Fh+var_40]; this
0x180044356  call    ?Empty@CBsString@@QEAAXXZ; CBsString::Empty(void)
0x18004435b  mov     [rbp+4Fh+var_B0], ebx
0x18004435e  lea     r8, [rbp+4Fh+var_50]; this
0x180044362  lea     rdx, c_wszPerceived; "PerceivedType"
0x180044369  mov     rcx, [rbp+4Fh+var_C0]; hKey
0x18004436d  call    ?SxRegReadString@@YAJPEAUHKEY__@@PEBGPEAVCBsString@@@Z; SxRegReadString(HKEY__ *,ushort const *,CBsString *)
0x180044372  mov     [rbp+4Fh+var_B0], eax
0x180044375  test    eax, eax
0x180044377  jns     short loc_180044385
0x180044379  lea     rcx, [rbp+4Fh+var_50]; this
0x18004437d  call    ?Empty@CBsString@@QEAAXXZ; CBsString::Empty(void)
0x180044382  mov     [rbp+4Fh+var_B0], ebx
0x180044385  lea     r8, [rbp+4Fh+var_60]; this
0x180044389  lea     rdx, Data; lpValueName
0x180044390  mov     rcx, [rbp+4Fh+var_C0]; hKey
0x180044394  call    ?SxRegReadString@@YAJPEAUHKEY__@@PEBGPEAVCBsString@@@Z; SxRegReadString(HKEY__ *,ushort const *,CBsString *)
0x180044399  mov     [rbp+4Fh+var_B0], eax
0x18004439c  test    eax, eax
0x18004439e  jns     short loc_1800443AC
0x1800443a0  lea     rcx, [rbp+4Fh+var_60]; this
0x1800443a4  call    ?Empty@CBsString@@QEAAXXZ; CBsString::Empty(void)
0x1800443a9  mov     [rbp+4Fh+var_B0], ebx
0x1800443ac  mov     rdx, rdi
0x1800443af  cmp     word ptr [rdi], 2Eh ; '.'
0x1800443b3  jnz     short loc_1800443BF
0x1800443b5  add     rdx, 2; Src
0x1800443b9  cmp     word ptr [rdx], 2Eh ; '.'
0x1800443bd  jz      short loc_1800443B5
0x1800443bf  mov     ebx, [rbp+4Fh+var_68]
0x1800443c2  cmp     rdx, rdi
0x1800443c5  jz      short loc_1800443E4
0x1800443c7  mov     rax, rdx
0x1800443ca  sub     rax, rdi
0x1800443cd  sar     rax, 1
0x1800443d0  sub     ebx, eax
0x1800443d2  lea     r8d, [rbx+1]
0x1800443d6  add     r8, r8; Size
0x1800443d9  mov     rcx, rdi; void *
0x1800443dc  call    memmove_0
0x1800443e1  mov     [rbp+4Fh+var_68], ebx
0x1800443e4  xor     eax, eax
0x1800443e6  test    ebx, ebx
0x1800443e8  jz      short loc_180044448
0x1800443ea  cmp     dword ptr [rbp+4Fh+var_38], eax
0x1800443ed  jnz     short loc_1800443F9
0x1800443ef  cmp     dword ptr [rbp+4Fh+var_48], eax
0x1800443f2  jnz     short loc_1800443F9
0x1800443f4  cmp     dword ptr [rbp+4Fh+var_58], eax
0x1800443f7  jz      short loc_180044448
0x1800443f9  mov     rax, [rbp+4Fh+var_60]
0x1800443fd  mov     [rsp+120h+lpcbMaxValueNameLen], rax; unsigned __int16 *
0x180044402  mov     rax, [rbp+4Fh+var_50]
0x180044406  mov     [rsp+120h+lpcValues], rax; unsigned __int16 *
0x18004440b  mov     rax, [rbp+4Fh+var_40]
0x18004440f  mov     [rsp+120h+lpcbMaxClassLen], rax; unsigned __int16 *
0x180044414  mov     [rsp+120h+lpcbMaxSubKeyLen], rdi; unsigned __int16 *
0x180044419  mov     [rsp+120h+phkResult], r14; struct CRegInfoTypeMap *
0x18004441e  mov     r9, r15; struct CRegInfoTypeMap *
0x180044421  mov     r8, r12; struct CRegInfoTypeMap *
0x180044424  mov     rdx, r13; struct CRegExtTypeMap *
0x180044427  mov     rcx, [rbp+4Fh+arg_0]; this
0x18004442b  call    ?_AddRegInfoToTable@CSdRules@@AEAAJPEAVCRegExtTypeMap@@PEAVCRegInfoTypeMap@@11PEBG222@Z; CSdRules::_AddRegInfoToTable(CRegExtTypeMap *,CRegInfoTypeMap *,CRegInfoTypeMap *,CRegInfoTypeMap *,ushort const *,ushort const *,ushort const *,ushort const *)
0x180044430  mov     ebx, eax
0x180044432  mov     [rbp+4Fh+var_B0], eax
0x180044435  xor     edi, edi
0x180044437  test    eax, eax
0x180044439  mov     eax, 720h
0x18004443e  js      loc_1800440DB
0x180044444  mov     [rbp+4Fh+var_AC], ax
0x180044448  inc     esi
0x18004444a  xor     edi, edi
0x18004444c  jmp     loc_18004420B
0x180044451  mov     [rbp+4Fh+var_AA], ax
0x180044455  xor     edi, edi
0x180044457  jmp     short loc_18004445C
0x180044459  mov     ebx, [rbp+4Fh+var_B0]
0x18004445c  lea     rcx, [rbp+4Fh+var_60]; this
0x180044460  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x180044465  lea     rcx, [rbp+4Fh+var_50]; this
0x180044469  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x18004446e  lea     rcx, [rbp+4Fh+var_40]; this
0x180044472  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x180044477  lea     rcx, [rbp+4Fh+lpName]; this
0x18004447b  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x180044480  mov     rcx, [rbp+4Fh+var_C0]; hKey
0x180044484  lea     rax, [rcx-1]
0x180044488  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18004448c  ja      short loc_18004449E
0x18004448e  call    cs:__imp_RegCloseKey
0x180044495  nop     dword ptr [rax+rax+00h]
0x18004449a  mov     [rbp+4Fh+var_C0], rdi
0x18004449e  mov     rcx, [rbp+4Fh+hKey]; hKey
0x1800444a2  lea     rdx, [rcx-1]
0x1800444a6  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x1800444aa  ja      short loc_1800444BC
0x1800444ac  call    cs:__imp_RegCloseKey
0x1800444b3  nop     dword ptr [rax+rax+00h]
0x1800444b8  mov     [rbp+4Fh+hKey], rdi
0x1800444bc  lea     rcx, [rbp+4Fh+var_B0]; this
0x1800444c0  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x1800444c5  mov     eax, ebx
0x1800444c7  mov     rbx, [rsp+120h+arg_10]
0x1800444cf  add     rsp, 0F0h
  ... truncated ...
```
