# DeleteRegistryKeyTree(HKEY__ *,ushort const *,int)

- ea: `0x18008723c`
- end: `0x180087668`
- name: `?DeleteRegistryKeyTree@@YAJPEAUHKEY__@@PEBGH@Z`
- size: `1068`
- prototype: `__int64 __fastcall(HKEY hKey, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task`

## callers

- `0x18005a49c`

## callees

- `0x180008240`
- `0x18006fe84`
- `0x18006ff8c`
- `0x18008723c`
- `0x1800996f4`
- `0x18009a08c`
- `0x18009a24c`
- `0x18009ae34`
- `0x1800c97da`
- `0x1800c9830`

## import_xrefs

- `msvcrt!wcschr` at `0x1800872e1`
- `msvcrt!wcschr` at `0x1800872e1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800874b5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180087604`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800874b5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180087604`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180087385`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180087385`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800873d0`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800874a8`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800873d0`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800874a8`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18008741d`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18008741d`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x180087528`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x180087528`
- `ole32!CoTaskMemFree` at `0x180087448`
- `ole32!CoTaskMemFree` at `0x180087626`
- `ole32!CoTaskMemFree` at `0x180087448`
- `ole32!CoTaskMemFree` at `0x180087626`
- `ole32!CoTaskMemAlloc` at `0x18008745c`
- `ole32!CoTaskMemAlloc` at `0x18008745c`

## string_xrefs

- `0x18008726c`: `DeleteRegistryKeyTree`

## pseudocode

```c
__int64 __fastcall DeleteRegistryKeyTree(HKEY hKey, const unsigned __int16 *a2)
{
  void *v3; // rsi
  bool v4; // zf
  __int16 v5; // ax
  WCHAR *v6; // r15
  DWORD v7; // r14d
  const WCHAR *v8; // rdi
  int v9; // eax
  int v10; // ebx
  int v11; // eax
  bool v12; // sf
  int v13; // eax
  int v14; // eax
  unsigned int v15; // eax
  __int16 v16; // ax
  unsigned int v17; // ebx
  DWORD cchName; // [rsp+60h] [rbp-A0h] BYREF
  HKEY hKeya; // [rsp+68h] [rbp-98h] BYREF
  DWORD cbMaxSubKeyLen; // [rsp+70h] [rbp-90h] BYREF
  int v22; // [rsp+78h] [rbp-88h] BYREF
  __int16 v23; // [rsp+7Ch] [rbp-84h]
  __int16 v24; // [rsp+7Eh] [rbp-82h]
  LPCWSTR lpSubKey; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v26; // [rsp+B8h] [rbp-48h]
  WCHAR Name[264]; // [rsp+C0h] [rbp-40h] BYREF

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v22, "DeleteRegistryKeyTree", 486, 2);
  lpSubKey = (LPCWSTR)qword_1800E8530;
  hKeya = 0;
  v26 = 0;
  cbMaxSubKeyLen = 0;
  v3 = 0;
  memset_0(Name, 0, 0x208u);
  cchName = 0;
  if ( !hKey )
  {
    v22 = -2147024809;
    v16 = 499;
LABEL_44:
    v24 = v16;
    goto LABEL_45;
  }
  v22 = 0;
  v23 = 501;
  v4 = wcschr(L"ScheduleParams", 0x5Cu) == 0;
  v5 = 502;
  if ( v4 )
  {
    v22 = 0;
    v23 = 502;
    v22 = CBsString::Set((CBsString *)&lpSubKey, L"ScheduleParams");
    v5 = 504;
    if ( v22 >= 0 )
    {
      v6 = Name;
      v7 = 260;
      do
      {
        v23 = v5;
        v8 = lpSubKey;
        while ( 1 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) != 0 )
            WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_955fb8e851b1303fac6deb5ef5879a46_Traceguids, v8);
          v9 = RegOpenKeyExW(hKey, v8, 0, 0x2001Fu, &hKeya);
          if ( v9 > 0 )
            v9 = (unsigned __int16)v9 | 0x80070000;
          v22 = v9;
          if ( v9 < 0 )
          {
            v24 = 519;
            goto LABEL_41;
          }
          v23 = 519;
          cchName = v7;
          v10 = RegEnumKeyExW(hKeya, 0, v6, &cchName, 0, 0, 0, 0);
          if ( v10 == 234 )
          {
            v11 = RegQueryInfoKeyW(hKeya, 0, 0, 0, 0, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0);
            if ( v11 > 0 )
              v11 = (unsigned __int16)v11 | 0x80070000;
            v22 = v11;
            v12 = v11 < 0;
            v5 = 529;
            if ( v12 )
              goto LABEL_40;
            v23 = 529;
            CoTaskMemFree(v3);
            v7 = cbMaxSubKeyLen + 1;
            v3 = CoTaskMemAlloc(2LL * (cbMaxSubKeyLen + 1));
            v5 = 537;
            if ( !v3 )
            {
              v22 = -2147024882;
              goto LABEL_40;
            }
            v6 = (WCHAR *)v3;
            v22 = 0;
            v23 = 537;
            cchName = v7;
            v10 = RegEnumKeyExW(hKeya, 0, (LPWSTR)v3, &cchName, 0, 0, 0, 0);
          }
          v13 = RegCloseKey(hKeya);
          if ( v13 > 0 )
            v13 = (unsigned __int16)v13 | 0x80070000;
          v22 = v13;
          v12 = v13 < 0;
          v5 = 548;
          if ( v12 )
            goto LABEL_40;
          v23 = 548;
          hKeya = 0;
          if ( v10 != 259 )
            break;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) != 0 )
            WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_955fb8e851b1303fac6deb5ef5879a46_Traceguids, v8);
          v14 = RegDeleteKeyW(hKey, v8);
          if ( v14 > 0 )
            v14 = (unsigned __int16)v14 | 0x80070000;
          v22 = v14;
          v12 = v14 < 0;
          v5 = 555;
          if ( v12 )
            goto LABEL_40;
          v23 = 555;
          v15 = CBsString::ReverseFind((CBsString *)&lpSubKey, 0x5Cu);
          if ( v15 == -1 )
          {
            v22 = 0;
            v23 = 561;
            goto LABEL_41;
          }
          if ( v15 < (unsigned int)v26 )
          {
            LODWORD(v26) = v15;
            v8[v15] = 0;
          }
        }
        if ( v10 > 0 )
          v10 = (unsigned __int16)v10 | 0x80070000;
        v22 = v10;
        v16 = 568;
        if ( v10 < 0 )
          goto LABEL_44;
        v23 = 568;
        v22 = CBsString::Append((CBsString *)&lpSubKey, L"\\", v6);
        v5 = 571;
      }
      while ( v22 >= 0 );
    }
  }
  else
  {
    v22 = -2147024809;
  }
LABEL_40:
  v24 = v5;
LABEL_41:
  if ( hKeya )
  {
    RegCloseKey(hKeya);
    hKeya = 0;
  }
LABEL_45:
  CoTaskMemFree(v3);
  v17 = v22;
  CBsString::_Release((CBsString *)&lpSubKey);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v22);
  return v17;
}

```

## disassembly

```asm
0x18008723c  push    rbp
0x18008723e  push    rbx
0x18008723f  push    rsi
0x180087240  push    rdi
0x180087241  push    r12
0x180087243  push    r13
0x180087245  push    r14
0x180087247  push    r15
0x180087249  lea     rbp, [rsp-1E8h]
0x180087251  sub     rsp, 2E8h
0x180087258  mov     rax, cs:__security_cookie
0x18008725f  xor     rax, rsp
0x180087262  mov     [rbp+220h+var_50], rax
0x180087269  mov     r12, rcx
0x18008726c  lea     rdx, aDeleteregistry; "DeleteRegistryKeyTree"
0x180087273  lea     rcx, [rsp+320h+var_2A8]; this
0x180087278  mov     r9d, 2; unsigned __int16
0x18008727e  mov     r8d, 1E6h; unsigned __int16
0x180087284  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180087289  xor     r13d, r13d
0x18008728c  lea     rax, qword_1800E8530
0x180087293  xor     edx, edx; Val
0x180087295  mov     [rbp+220h+lpSubKey], rax
0x180087299  mov     r8d, 208h; Size
0x18008729f  mov     [rsp+320h+hKey], r13
0x1800872a4  lea     rcx, [rbp+220h+Name]; void *
0x1800872a8  mov     [rbp+220h+var_268], r13
0x1800872ac  mov     [rsp+320h+cbMaxSubKeyLen], r13d
0x1800872b1  mov     esi, r13d
0x1800872b4  call    memset_0
0x1800872b9  mov     [rsp+320h+cchName], r13d
0x1800872be  test    r12, r12
0x1800872c1  jz      loc_180087611
0x1800872c7  mov     eax, 1F5h
0x1800872cc  mov     [rsp+320h+var_2A8], r13d
0x1800872d1  lea     edx, [r13+5Ch]; Ch
0x1800872d5  mov     [rsp+320h+var_2A4], ax
0x1800872da  lea     rcx, c_wszSafedocsSchedulingKeyName; "ScheduleParams"
0x1800872e1  call    cs:__imp_wcschr
0x1800872e7  test    rax, rax
0x1800872ea  mov     eax, 1F6h
0x1800872ef  jnz     loc_1800875ED
0x1800872f5  lea     rdx, c_wszSafedocsSchedulingKeyName; "ScheduleParams"
0x1800872fc  mov     [rsp+320h+var_2A8], r13d
0x180087301  lea     rcx, [rbp+220h+lpSubKey]; this
0x180087305  mov     [rsp+320h+var_2A4], ax
0x18008730a  call    ?Set@CBsString@@QEAAJPEBG@Z; CBsString::Set(ushort const *)
0x18008730f  mov     [rsp+320h+var_2A8], eax
0x180087313  test    eax, eax
0x180087315  mov     eax, 1F8h
0x18008731a  js      loc_1800875F5
0x180087320  lea     r15, [rbp+220h+Name]
0x180087324  mov     r14d, 104h
0x18008732a  mov     ebx, 207h
0x18008732f  mov     [rsp+320h+var_2A4], ax
0x180087334  mov     rdi, [rbp+220h+lpSubKey]
0x180087338  lea     rdx, WPP_GLOBAL_Control
0x18008733f  mov     rcx, cs:WPP_GLOBAL_Control
0x180087346  cmp     rcx, rdx
0x180087349  jz      short loc_18008736C
0x18008734b  test    dword ptr [rcx+1Ch], 800000h
0x180087352  jz      short loc_18008736C
0x180087354  mov     rcx, [rcx+10h]
0x180087358  lea     r8, WPP_955fb8e851b1303fac6deb5ef5879a46_Traceguids
0x18008735f  mov     edx, 0Ah
0x180087364  mov     r9, rdi
0x180087367  call    WPP_SF_S
0x18008736c  lea     rax, [rsp+320h+hKey]
0x180087371  mov     r9d, 2001Fh; samDesired
0x180087377  xor     r8d, r8d; ulOptions
0x18008737a  mov     [rsp+320h+phkResult], rax; phkResult
0x18008737f  mov     rdx, rdi; lpSubKey
0x180087382  mov     rcx, r12; hKey
0x180087385  call    cs:__imp_RegOpenKeyExW
0x18008738b  test    eax, eax
0x18008738d  jle     short loc_180087397
0x18008738f  movzx   eax, ax
0x180087392  or      eax, 80070000h
0x180087397  mov     [rsp+320h+var_2A8], eax
0x18008739b  test    eax, eax
0x18008739d  js      loc_1800875E6
0x1800873a3  mov     rcx, [rsp+320h+hKey]; hKey
0x1800873a8  lea     r9, [rsp+320h+cchName]; lpcchName
0x1800873ad  mov     [rsp+320h+lpftLastWriteTime], r13; lpftLastWriteTime
0x1800873b2  mov     r8, r15; lpName
0x1800873b5  mov     [rsp+320h+lpcchClass], r13; lpcchClass
0x1800873ba  xor     edx, edx; dwIndex
0x1800873bc  mov     [rsp+320h+lpClass], r13; lpClass
0x1800873c1  mov     [rsp+320h+phkResult], r13; lpReserved
0x1800873c6  mov     [rsp+320h+var_2A4], bx
0x1800873cb  mov     [rsp+320h+cchName], r14d
0x1800873d0  call    cs:__imp_RegEnumKeyExW
0x1800873d6  mov     ebx, eax
0x1800873d8  cmp     eax, 0EAh
0x1800873dd  jnz     loc_1800874B0
0x1800873e3  mov     rcx, [rsp+320h+hKey]; hKey
0x1800873e8  lea     rax, [rsp+320h+cbMaxSubKeyLen]
0x1800873ed  mov     [rsp+320h+var_2C8], r13; lpftLastWriteTime
0x1800873f2  xor     r9d, r9d; lpReserved
0x1800873f5  mov     [rsp+320h+lpcbSecurityDescriptor], r13; lpcbSecurityDescriptor
0x1800873fa  xor     r8d, r8d; lpcchClass
0x1800873fd  mov     [rsp+320h+lpcbMaxValueLen], r13; lpcbMaxValueLen
0x180087402  xor     edx, edx; lpClass
0x180087404  mov     [rsp+320h+lpcbMaxValueNameLen], r13; lpcbMaxValueNameLen
0x180087409  mov     [rsp+320h+lpftLastWriteTime], r13; lpcValues
0x18008740e  mov     [rsp+320h+lpcchClass], r13; lpcbMaxClassLen
0x180087413  mov     [rsp+320h+lpClass], rax; lpcbMaxSubKeyLen
0x180087418  mov     [rsp+320h+phkResult], r13; lpcSubKeys
0x18008741d  call    cs:__imp_RegQueryInfoKeyW
0x180087423  test    eax, eax
0x180087425  jle     short loc_18008742F
0x180087427  movzx   eax, ax
0x18008742a  or      eax, 80070000h
0x18008742f  mov     [rsp+320h+var_2A8], eax
0x180087433  test    eax, eax
0x180087435  mov     eax, 211h
0x18008743a  js      loc_1800875F5
0x180087440  mov     rcx, rsi; pv
0x180087443  mov     [rsp+320h+var_2A4], ax
0x180087448  call    cs:__imp_CoTaskMemFree
0x18008744e  mov     r14d, [rsp+320h+cbMaxSubKeyLen]
0x180087453  inc     r14d
0x180087456  mov     ecx, r14d
0x180087459  add     rcx, rcx; cb
0x18008745c  call    cs:__imp_CoTaskMemAlloc
0x180087462  mov     rsi, rax
0x180087465  test    rax, rax
0x180087468  mov     eax, 219h
0x18008746d  jz      loc_1800875CB
0x180087473  mov     rcx, [rsp+320h+hKey]; hKey
0x180087478  lea     r9, [rsp+320h+cchName]; lpcchName
0x18008747d  mov     [rsp+320h+lpftLastWriteTime], r13; lpftLastWriteTime
0x180087482  mov     r8, rsi; lpName
0x180087485  mov     [rsp+320h+lpcchClass], r13; lpcchClass
0x18008748a  xor     edx, edx; dwIndex
0x18008748c  mov     [rsp+320h+lpClass], r13; lpClass
0x180087491  mov     r15, rsi
0x180087494  mov     [rsp+320h+phkResult], r13; lpReserved
0x180087499  mov     [rsp+320h+var_2A8], r13d
0x18008749e  mov     [rsp+320h+var_2A4], ax
0x1800874a3  mov     [rsp+320h+cchName], r14d
0x1800874a8  call    cs:__imp_RegEnumKeyExW
0x1800874ae  mov     ebx, eax
0x1800874b0  mov     rcx, [rsp+320h+hKey]; hKey
0x1800874b5  call    cs:__imp_RegCloseKey
0x1800874bb  test    eax, eax
0x1800874bd  jle     short loc_1800874C7
0x1800874bf  movzx   eax, ax
0x1800874c2  or      eax, 80070000h
0x1800874c7  mov     [rsp+320h+var_2A8], eax
0x1800874cb  test    eax, eax
0x1800874cd  mov     eax, 224h
0x1800874d2  js      loc_1800875F5
0x1800874d8  mov     [rsp+320h+var_2A4], ax
0x1800874dd  mov     [rsp+320h+hKey], r13
0x1800874e2  cmp     ebx, 103h
0x1800874e8  jnz     loc_180087587
0x1800874ee  mov     rcx, cs:WPP_GLOBAL_Control
0x1800874f5  lea     rax, WPP_GLOBAL_Control
0x1800874fc  cmp     rcx, rax
0x1800874ff  jz      short loc_180087522
0x180087501  test    dword ptr [rcx+1Ch], 800000h
0x180087508  jz      short loc_180087522
0x18008750a  mov     rcx, [rcx+10h]
0x18008750e  lea     r8, WPP_955fb8e851b1303fac6deb5ef5879a46_Traceguids
0x180087515  mov     edx, 0Bh
0x18008751a  mov     r9, rdi
0x18008751d  call    WPP_SF_S
0x180087522  mov     rdx, rdi; lpSubKey
0x180087525  mov     rcx, r12; hKey
0x180087528  call    cs:__imp_RegDeleteKeyW
0x18008752e  test    eax, eax
0x180087530  jle     short loc_18008753A
0x180087532  movzx   eax, ax
0x180087535  or      eax, 80070000h
0x18008753a  mov     [rsp+320h+var_2A8], eax
0x18008753e  test    eax, eax
0x180087540  mov     eax, 22Bh
0x180087545  js      loc_1800875F5
0x18008754b  mov     edx, 5Ch ; '\'; unsigned __int16
0x180087550  mov     [rsp+320h+var_2A4], ax
0x180087555  lea     rcx, [rbp+220h+lpSubKey]; this
0x180087559  call    ?ReverseFind@CBsString@@QEBAJG@Z; CBsString::ReverseFind(ushort)
0x18008755e  cmp     eax, 0FFFFFFFFh
0x180087561  jz      short loc_1800875D5
0x180087563  lea     rdx, WPP_GLOBAL_Control
0x18008756a  mov     ebx, 207h
0x18008756f  cmp     eax, dword ptr [rbp+220h+var_268]
0x180087572  jnb     loc_18008733F
0x180087578  mov     ecx, eax
0x18008757a  mov     dword ptr [rbp+220h+var_268], eax
0x18008757d  mov     [rdi+rcx*2], r13w
0x180087582  jmp     loc_180087338
0x180087587  test    ebx, ebx
0x180087589  jle     short loc_180087594
0x18008758b  movzx   ebx, bx
0x18008758e  or      ebx, 80070000h
0x180087594  mov     [rsp+320h+var_2A8], ebx
0x180087598  mov     eax, 238h
0x18008759d  test    ebx, ebx
0x18008759f  js      short loc_18008761E
0x1800875a1  mov     r8, r15; unsigned __int16 *
0x1800875a4  mov     [rsp+320h+var_2A4], ax
0x1800875a9  lea     rdx, Str; "\\"
0x1800875b0  lea     rcx, [rbp+220h+lpSubKey]; this
0x1800875b4  call    ?Append@CBsString@@QEAAJPEBG0@Z; CBsString::Append(ushort const *,ushort const *)
0x1800875b9  mov     [rsp+320h+var_2A8], eax
0x1800875bd  test    eax, eax
0x1800875bf  mov     eax, 23Bh
0x1800875c4  js      short loc_1800875F5
0x1800875c6  jmp     loc_18008732A
0x1800875cb  mov     [rsp+320h+var_2A8], 8007000Eh
0x1800875d3  jmp     short loc_1800875F5
0x1800875d5  mov     eax, 231h
0x1800875da  mov     [rsp+320h+var_2A8], r13d
0x1800875df  mov     [rsp+320h+var_2A4], ax
0x1800875e4  jmp     short loc_1800875FA
0x1800875e6  mov     [rsp+320h+var_2A2], bx
0x1800875eb  jmp     short loc_1800875FA
0x1800875ed  mov     [rsp+320h+var_2A8], 80070057h
0x1800875f5  mov     [rsp+320h+var_2A2], ax
0x1800875fa  mov     rcx, [rsp+320h+hKey]; hKey
0x1800875ff  test    rcx, rcx
0x180087602  jz      short loc_180087623
0x180087604  call    cs:__imp_RegCloseKey
0x18008760a  mov     [rsp+320h+hKey], r13
0x18008760f  jmp     short loc_180087623
0x180087611  mov     [rsp+320h+var_2A8], 80070057h
0x180087619  mov     eax, 1F3h
0x18008761e  mov     [rsp+320h+var_2A2], ax
0x180087623  mov     rcx, rsi; pv
0x180087626  call    cs:__imp_CoTaskMemFree
0x18008762c  mov     ebx, [rsp+320h+var_2A8]
0x180087630  lea     rcx, [rbp+220h+lpSubKey]; this
0x180087634  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x180087639  lea     rcx, [rsp+320h+var_2A8]; this
0x18008763e  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180087643  mov     eax, ebx
0x180087645  mov     rcx, [rbp+220h+var_50]
0x18008764c  xor     rcx, rsp; StackCookie
0x18008764f  call    __security_check_cookie
0x180087654  add     rsp, 2E8h
0x18008765b  pop     r15
0x18008765d  pop     r14
0x18008765f  pop     r13
0x180087661  pop     r12
0x180087663  pop     rdi
0x180087664  pop     rsi
0x180087665  pop     rbx
0x180087666  pop     rbp
0x180087667  retn
```
