# CSdBackupConfigImpl::_ReadRules(HKEY__ *,ulong *,_SD_BACKUP_ROOT * *)

- ea: `0x1800595a4`
- end: `0x18005991c`
- name: `?_ReadRules@CSdBackupConfigImpl@@AEAAJPEAUHKEY__@@PEAKPEAPEAU_SD_BACKUP_ROOT@@@Z`
- size: `888`
- prototype: `__int64 __fastcall(CSdBackupConfigImpl *__hidden this, HKEY hKey, unsigned int *, struct _SD_BACKUP_ROOT **)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task`

## callers

- `0x180058eb4`

## callees

- `0x180008240`
- `0x1800587e8`
- `0x1800593d8`
- `0x1800595a4`
- `0x18006fe84`
- `0x18006ff8c`
- `0x1800c97da`

## import_xrefs

- `msvcrt!_wtoi` at `0x180059834`
- `msvcrt!_wtoi` at `0x180059834`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800597d3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800597ea`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800598d4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800598ec`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800597d3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800597ea`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800598d4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800598ec`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180059668`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005980d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180059668`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005980d`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180059764`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180059764`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800596ce`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800596ce`
- `ole32!CoTaskMemFree` at `0x1800598bd`
- `ole32!CoTaskMemFree` at `0x1800598bd`
- `ole32!CoTaskMemAlloc` at `0x1800596fa`
- `ole32!CoTaskMemAlloc` at `0x1800596fa`

## string_xrefs

- `0x1800595d8`: `CSdBackupConfigImpl::_ReadRules`

## pseudocode

```c
__int64 __fastcall CSdBackupConfigImpl::_ReadRules(
        CSdBackupConfigImpl *this,
        HKEY hKey,
        unsigned int *a3,
        struct _SD_BACKUP_ROOT **a4)
{
  WCHAR *v8; // rdi
  __int16 v9; // ax
  int v10; // eax
  bool v11; // sf
  int v12; // eax
  WCHAR *v13; // rax
  DWORD i; // ebx
  DWORD v15; // edx
  int v16; // eax
  HKEY v17; // rcx
  int v18; // eax
  unsigned int v19; // eax
  unsigned int v20; // ebx
  HKEY phkResult; // [rsp+60h] [rbp-29h] BYREF
  HKEY hKeya; // [rsp+68h] [rbp-21h] BYREF
  int RuleFromRegistry; // [rsp+70h] [rbp-19h] BYREF
  __int16 v25; // [rsp+74h] [rbp-15h]
  __int16 v26; // [rsp+76h] [rbp-13h]
  DWORD cbMaxSubKeyLen; // [rsp+F8h] [rbp+6Fh] BYREF
  DWORD cSubKeys; // [rsp+100h] [rbp+77h] BYREF
  DWORD cchName; // [rsp+108h] [rbp+7Fh] BYREF

  CSxFunctionTracer::CSxFunctionTracer(
    (CSxFunctionTracer *)&RuleFromRegistry,
    "CSdBackupConfigImpl::_ReadRules",
    251,
    1);
  hKeya = 0;
  phkResult = 0;
  cSubKeys = 0;
  cbMaxSubKeyLen = 0;
  cchName = 0;
  v8 = 0;
  if ( a3 )
    *a3 = 0;
  if ( a4 )
    *a4 = 0;
  v9 = 266;
  if ( hKey && (v25 = 266, v9 = 267, a3) && (v25 = 267, v9 = 268, a4) )
  {
    RuleFromRegistry = 0;
    v25 = 268;
    v10 = RegOpenKeyExW(hKey, L"Rules", 0, 0x20019u, &hKeya);
    if ( v10 > 0 )
      v10 = (unsigned __int16)v10 | 0x80070000;
    RuleFromRegistry = v10;
    v11 = v10 < 0;
    v9 = 273;
    if ( !v11 )
    {
      v25 = 273;
      v12 = RegQueryInfoKeyW(hKeya, 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0);
      if ( v12 > 0 )
        v12 = (unsigned __int16)v12 | 0x80070000;
      RuleFromRegistry = v12;
      v11 = v12 < 0;
      v9 = 274;
      if ( !v11 )
      {
        v25 = 274;
        v13 = (WCHAR *)CoTaskMemAlloc(2LL * (cbMaxSubKeyLen + 1));
        v8 = v13;
        if ( !v13 )
        {
          RuleFromRegistry = -2147024882;
          v26 = 277;
          goto LABEL_42;
        }
        RuleFromRegistry = 0;
        v25 = 277;
        memset_0(v13, 0, 2LL * (cbMaxSubKeyLen + 1));
        for ( i = 0; ; ++i )
        {
          v15 = cSubKeys;
          if ( i >= cSubKeys )
            break;
          cchName = cbMaxSubKeyLen + 1;
          v16 = RegEnumKeyExW(hKeya, i, v8, &cchName, 0, 0, 0, 0);
          if ( v16 == 259 )
          {
            v15 = cSubKeys;
            break;
          }
          if ( v16 > 0 )
            v16 = (unsigned __int16)v16 | 0x80070000;
          RuleFromRegistry = v16;
          v11 = v16 < 0;
          v9 = 291;
          if ( v11 )
            goto LABEL_41;
          v25 = 291;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_fea9f066dab43d30b7e95d3387edc116_Traceguids, v8);
          v17 = phkResult;
          if ( phkResult )
          {
            if ( phkResult != HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
            {
              RegCloseKey(phkResult);
              v17 = 0;
              phkResult = 0;
            }
            if ( (unsigned __int64)v17 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
            {
              RegCloseKey(v17);
              phkResult = 0;
            }
          }
          v18 = RegOpenKeyExW(hKeya, v8, 0, 0x20019u, &phkResult);
          if ( v18 > 0 )
            v18 = (unsigned __int16)v18 | 0x80070000;
          RuleFromRegistry = v18;
          v11 = v18 < 0;
          v9 = 295;
          if ( v11 )
            goto LABEL_41;
          v25 = 295;
          v19 = _wtoi(v8);
          if ( !v19 )
          {
            RuleFromRegistry = -2130706378;
            v9 = 298;
            goto LABEL_41;
          }
          RuleFromRegistry = 0;
          v25 = 298;
          RuleFromRegistry = CSdBackupConfigImpl::_ReadRuleFromRegistry(this, phkResult, v19);
          v9 = 303;
          if ( RuleFromRegistry < 0 )
            goto LABEL_41;
          v25 = 303;
        }
        RuleFromRegistry = CSdBackupConfigImpl::_GetAllRules(this, v15, a3, a4);
        v9 = 307;
        if ( RuleFromRegistry >= 0 )
        {
          v25 = 307;
          goto LABEL_42;
        }
      }
    }
  }
  else
  {
    RuleFromRegistry = -2147024809;
  }
LABEL_41:
  v26 = v9;
LABEL_42:
  CoTaskMemFree(v8);
  v20 = RuleFromRegistry;
  if ( (unsigned __int64)phkResult - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    RegCloseKey(phkResult);
    phkResult = 0;
  }
  if ( (unsigned __int64)hKeya - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    RegCloseKey(hKeya);
    hKeya = 0;
  }
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&RuleFromRegistry);
  return v20;
}

```

## disassembly

```asm
0x1800595a4  mov     [rsp-8+arg_0], rbx
0x1800595a9  push    rbp
0x1800595aa  push    rsi
0x1800595ab  push    rdi
0x1800595ac  push    r12
0x1800595ae  push    r13
0x1800595b0  push    r14
0x1800595b2  push    r15
0x1800595b4  lea     rbp, [rsp-27h]
0x1800595b9  sub     rsp, 0B0h
0x1800595c0  mov     rsi, r9
0x1800595c3  mov     r14, r8
0x1800595c6  mov     rbx, rdx
0x1800595c9  mov     r15, rcx
0x1800595cc  mov     r9d, 1; unsigned __int16
0x1800595d2  mov     r8d, 0FBh; unsigned __int16
0x1800595d8  lea     rdx, aCsdbackupconfi_8; "CSdBackupConfigImpl::_ReadRules"
0x1800595df  lea     rcx, [rbp+57h+var_70]; this
0x1800595e3  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x1800595e8  xor     r12d, r12d
0x1800595eb  mov     [rbp+57h+hKey], r12
0x1800595ef  mov     [rbp+57h+var_80], r12
0x1800595f3  mov     [rbp+57h+cSubKeys], r12d
0x1800595f7  mov     [rbp+57h+cbMaxSubKeyLen], r12d
0x1800595fb  mov     [rbp+57h+cchName], r12d
0x1800595ff  mov     edi, r12d
0x180059602  test    r14, r14
0x180059605  jz      short loc_18005960A
0x180059607  mov     [r14], r12d
0x18005960a  test    rsi, rsi
0x18005960d  jz      short loc_180059612
0x18005960f  mov     [rsi], r12
0x180059612  mov     eax, 10Ah
0x180059617  test    rbx, rbx
0x18005961a  jz      loc_1800598AF
0x180059620  mov     [rbp+57h+var_6C], ax
0x180059624  mov     eax, 10Bh
0x180059629  test    r14, r14
0x18005962c  jz      loc_1800598AF
0x180059632  mov     [rbp+57h+var_6C], ax
0x180059636  mov     eax, 10Ch
0x18005963b  test    rsi, rsi
0x18005963e  jz      loc_1800598AF
0x180059644  mov     [rbp+57h+var_70], r12d
0x180059648  mov     [rbp+57h+var_6C], ax
0x18005964c  lea     rax, [rbp+57h+hKey]
0x180059650  mov     [rsp+0E0h+phkResult], rax; phkResult
0x180059655  mov     r9d, 20019h; samDesired
0x18005965b  xor     r8d, r8d; ulOptions
0x18005965e  lea     rdx, c_wszSafedocsScheduleRules; "Rules"
0x180059665  mov     rcx, rbx; hKey
0x180059668  call    cs:__imp_RegOpenKeyExW
0x18005966e  mov     r13d, 80070000h
0x180059674  test    eax, eax
0x180059676  jle     short loc_18005967E
0x180059678  movzx   eax, ax
0x18005967b  or      eax, r13d
0x18005967e  mov     [rbp+57h+var_70], eax
0x180059681  test    eax, eax
0x180059683  mov     eax, 111h
0x180059688  js      loc_1800598B6
0x18005968e  mov     [rbp+57h+var_6C], ax
0x180059692  mov     [rsp+0E0h+lpftLastWriteTime], r12; lpftLastWriteTime
0x180059697  mov     [rsp+0E0h+lpcbSecurityDescriptor], r12; lpcbSecurityDescriptor
0x18005969c  mov     [rsp+0E0h+lpcbMaxValueLen], r12; lpcbMaxValueLen
0x1800596a1  mov     [rsp+0E0h+lpcbMaxValueNameLen], r12; lpcbMaxValueNameLen
0x1800596a6  mov     [rsp+0E0h+lpcValues], r12; lpcValues
0x1800596ab  mov     [rsp+0E0h+lpcbMaxClassLen], r12; lpcbMaxClassLen
0x1800596b0  lea     rax, [rbp+57h+cbMaxSubKeyLen]
0x1800596b4  mov     [rsp+0E0h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x1800596b9  lea     rax, [rbp+57h+cSubKeys]
0x1800596bd  mov     [rsp+0E0h+phkResult], rax; lpcSubKeys
0x1800596c2  xor     r9d, r9d; lpReserved
0x1800596c5  xor     r8d, r8d; lpcchClass
0x1800596c8  xor     edx, edx; lpClass
0x1800596ca  mov     rcx, [rbp+57h+hKey]; hKey
0x1800596ce  call    cs:__imp_RegQueryInfoKeyW
0x1800596d4  test    eax, eax
0x1800596d6  jle     short loc_1800596DE
0x1800596d8  movzx   eax, ax
0x1800596db  or      eax, r13d
0x1800596de  mov     [rbp+57h+var_70], eax
0x1800596e1  test    eax, eax
0x1800596e3  mov     eax, 112h
0x1800596e8  js      loc_1800598B6
0x1800596ee  mov     [rbp+57h+var_6C], ax
0x1800596f2  mov     ecx, [rbp+57h+cbMaxSubKeyLen]
0x1800596f5  inc     ecx
0x1800596f7  add     rcx, rcx; cb
0x1800596fa  call    cs:__imp_CoTaskMemAlloc
0x180059700  mov     rdi, rax
0x180059703  mov     ecx, 115h
0x180059708  test    rax, rax
0x18005970b  jz      loc_1800598A2
0x180059711  mov     [rbp+57h+var_70], r12d
0x180059715  mov     [rbp+57h+var_6C], cx
0x180059719  mov     r8d, [rbp+57h+cbMaxSubKeyLen]
0x18005971d  inc     r8d
0x180059720  add     r8, r8; Size
0x180059723  xor     edx, edx; Val
0x180059725  mov     rcx, rax; void *
0x180059728  call    memset_0
0x18005972d  mov     ebx, r12d
0x180059730  mov     edx, [rbp+57h+cSubKeys]
0x180059733  cmp     ebx, edx
0x180059735  jnb     loc_180059882
0x18005973b  mov     eax, [rbp+57h+cbMaxSubKeyLen]
0x18005973e  inc     eax
0x180059740  mov     [rbp+57h+cchName], eax
0x180059743  mov     [rsp+0E0h+lpcValues], r12; lpftLastWriteTime
0x180059748  mov     [rsp+0E0h+lpcbMaxClassLen], r12; lpcchClass
0x18005974d  mov     [rsp+0E0h+lpcbMaxSubKeyLen], r12; lpClass
0x180059752  mov     [rsp+0E0h+phkResult], r12; lpReserved
0x180059757  lea     r9, [rbp+57h+cchName]; lpcchName
0x18005975b  mov     r8, rdi; lpName
0x18005975e  mov     edx, ebx; dwIndex
0x180059760  mov     rcx, [rbp+57h+hKey]; hKey
0x180059764  call    cs:__imp_RegEnumKeyExW
0x18005976a  cmp     eax, 103h
0x18005976f  jz      loc_18005987F
0x180059775  test    eax, eax
0x180059777  jle     short loc_18005977F
0x180059779  movzx   eax, ax
0x18005977c  or      eax, r13d
0x18005977f  mov     [rbp+57h+var_70], eax
0x180059782  test    eax, eax
0x180059784  mov     eax, 123h
0x180059789  js      loc_1800598B6
0x18005978f  mov     [rbp+57h+var_6C], ax
0x180059793  lea     rax, WPP_GLOBAL_Control
0x18005979a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800597a1  cmp     rcx, rax
0x1800597a4  jz      short loc_1800597C4
0x1800597a6  test    byte ptr [rcx+1Ch], 2
0x1800597aa  jz      short loc_1800597C4
0x1800597ac  mov     edx, 0Ah
0x1800597b1  mov     r9, rdi
0x1800597b4  lea     r8, WPP_fea9f066dab43d30b7e95d3387edc116_Traceguids
0x1800597bb  mov     rcx, [rcx+10h]
0x1800597bf  call    WPP_SF_S
0x1800597c4  mov     rcx, [rbp+57h+var_80]; hKey
0x1800597c8  test    rcx, rcx
0x1800597cb  jz      short loc_1800597F4
0x1800597cd  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800597d1  jz      short loc_1800597E0
0x1800597d3  call    cs:__imp_RegCloseKey
0x1800597d9  mov     rcx, r12; hKey
0x1800597dc  mov     [rbp+57h+var_80], rcx
0x1800597e0  lea     rax, [rcx-1]
0x1800597e4  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800597e8  ja      short loc_1800597F4
0x1800597ea  call    cs:__imp_RegCloseKey
0x1800597f0  mov     [rbp+57h+var_80], r12
0x1800597f4  lea     rax, [rbp+57h+var_80]
0x1800597f8  mov     [rsp+0E0h+phkResult], rax; phkResult
0x1800597fd  mov     r9d, 20019h; samDesired
0x180059803  xor     r8d, r8d; ulOptions
0x180059806  mov     rdx, rdi; lpSubKey
0x180059809  mov     rcx, [rbp+57h+hKey]; hKey
0x18005980d  call    cs:__imp_RegOpenKeyExW
0x180059813  test    eax, eax
0x180059815  jle     short loc_18005981D
0x180059817  movzx   eax, ax
0x18005981a  or      eax, r13d
0x18005981d  mov     [rbp+57h+var_70], eax
0x180059820  test    eax, eax
0x180059822  mov     eax, 127h
0x180059827  js      loc_1800598B6
0x18005982d  mov     [rbp+57h+var_6C], ax
0x180059831  mov     rcx, rdi; String
0x180059834  call    cs:__imp__wtoi
0x18005983a  test    eax, eax
0x18005983c  jz      short loc_180059871
0x18005983e  mov     [rbp+57h+var_70], r12d
0x180059842  mov     ecx, 12Ah
0x180059847  mov     [rbp+57h+var_6C], cx
0x18005984b  mov     r8d, eax; unsigned int
0x18005984e  mov     rdx, [rbp+57h+var_80]; hKey
0x180059852  mov     rcx, r15; this
0x180059855  call    ?_ReadRuleFromRegistry@CSdBackupConfigImpl@@AEAAJPEAUHKEY__@@K@Z; CSdBackupConfigImpl::_ReadRuleFromRegistry(HKEY__ *,ulong)
0x18005985a  mov     [rbp+57h+var_70], eax
0x18005985d  test    eax, eax
0x18005985f  mov     eax, 12Fh
0x180059864  js      short loc_1800598B6
0x180059866  mov     [rbp+57h+var_6C], ax
0x18005986a  inc     ebx
0x18005986c  jmp     loc_180059730
0x180059871  mov     [rbp+57h+var_70], 81000036h
0x180059878  mov     eax, 12Ah
0x18005987d  jmp     short loc_1800598B6
0x18005987f  mov     edx, [rbp+57h+cSubKeys]; unsigned int
0x180059882  mov     r9, rsi; struct _SD_BACKUP_ROOT **
0x180059885  mov     r8, r14; unsigned int *
0x180059888  mov     rcx, r15; this
0x18005988b  call    ?_GetAllRules@CSdBackupConfigImpl@@AEAAJKPEAKPEAPEAU_SD_BACKUP_ROOT@@@Z; CSdBackupConfigImpl::_GetAllRules(ulong,ulong *,_SD_BACKUP_ROOT * *)
0x180059890  mov     [rbp+57h+var_70], eax
0x180059893  test    eax, eax
0x180059895  mov     eax, 133h
0x18005989a  js      short loc_1800598B6
0x18005989c  mov     [rbp+57h+var_6C], ax
0x1800598a0  jmp     short loc_1800598BA
0x1800598a2  mov     [rbp+57h+var_70], 8007000Eh
0x1800598a9  mov     [rbp+57h+var_6A], cx
0x1800598ad  jmp     short loc_1800598BA
0x1800598af  mov     [rbp+57h+var_70], 80070057h
0x1800598b6  mov     [rbp+57h+var_6A], ax
0x1800598ba  mov     rcx, rdi; pv
0x1800598bd  call    cs:__imp_CoTaskMemFree
0x1800598c3  mov     ebx, [rbp+57h+var_70]
0x1800598c6  mov     rcx, [rbp+57h+var_80]; hKey
0x1800598ca  lea     rax, [rcx-1]
0x1800598ce  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800598d2  ja      short loc_1800598DE
0x1800598d4  call    cs:__imp_RegCloseKey
0x1800598da  mov     [rbp+57h+var_80], r12
0x1800598de  mov     rcx, [rbp+57h+hKey]; hKey
0x1800598e2  lea     rdx, [rcx-1]
0x1800598e6  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x1800598ea  ja      short loc_1800598F6
0x1800598ec  call    cs:__imp_RegCloseKey
0x1800598f2  mov     [rbp+57h+hKey], r12
0x1800598f6  lea     rcx, [rbp+57h+var_70]; this
0x1800598fa  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x1800598ff  mov     eax, ebx
0x180059901  mov     rbx, [rsp+0E0h+arg_0]
0x180059909  add     rsp, 0B0h
0x180059910  pop     r15
0x180059912  pop     r14
0x180059914  pop     r13
0x180059916  pop     r12
0x180059918  pop     rdi
0x180059919  pop     rsi
0x18005991a  pop     rbp
0x18005991b  retn
```
