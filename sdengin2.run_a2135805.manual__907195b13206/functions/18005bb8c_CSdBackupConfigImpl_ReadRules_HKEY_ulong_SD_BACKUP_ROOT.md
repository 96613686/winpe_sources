# CSdBackupConfigImpl::_ReadRules(HKEY__ *,ulong *,_SD_BACKUP_ROOT * *)

- ea: `0x18005bb8c`
- end: `0x18005bf47`
- name: `?_ReadRules@CSdBackupConfigImpl@@AEAAJPEAUHKEY__@@PEAKPEAPEAU_SD_BACKUP_ROOT@@@Z`
- size: `955`
- prototype: `__int64 __fastcall(CSdBackupConfigImpl *__hidden this, HKEY hKey, unsigned int *, struct _SD_BACKUP_ROOT **)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task`

## callers

- `0x18005b46c`

## callees

- `0x1800083e4`
- `0x18005ad64`
- `0x18005b9b0`
- `0x18005bb8c`
- `0x180072e08`
- `0x180072f14`
- `0x1800cf56a`

## import_xrefs

- `msvcrt!_wtoi` at `0x18005be46`
- `msvcrt!_wtoi` at `0x18005be46`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005bdd3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005bdf0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005bef2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005bf10`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005bdd3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005bdf0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005bef2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005bf10`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005bc50`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005be19`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005bc50`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005be19`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18005bd5e`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18005bd5e`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18005bcbc`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18005bcbc`
- `ole32!CoTaskMemFree` at `0x18005bed5`
- `ole32!CoTaskMemFree` at `0x18005bed5`
- `ole32!CoTaskMemAlloc` at `0x18005bcee`
- `ole32!CoTaskMemAlloc` at `0x18005bcee`

## string_xrefs

- `0x18005bbc0`: `CSdBackupConfigImpl::_ReadRules`

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
    0xFBu,
    1u);
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
0x18005bb8c  mov     [rsp-8+arg_0], rbx
0x18005bb91  push    rbp
0x18005bb92  push    rsi
0x18005bb93  push    rdi
0x18005bb94  push    r12
0x18005bb96  push    r13
0x18005bb98  push    r14
0x18005bb9a  push    r15
0x18005bb9c  lea     rbp, [rsp-27h]
0x18005bba1  sub     rsp, 0B0h
0x18005bba8  mov     rsi, r9
0x18005bbab  mov     r14, r8
0x18005bbae  mov     rbx, rdx
0x18005bbb1  mov     r15, rcx
0x18005bbb4  mov     r9d, 1; unsigned __int16
0x18005bbba  mov     r8d, 0FBh; unsigned __int16
0x18005bbc0  lea     rdx, aCsdbackupconfi_8; "CSdBackupConfigImpl::_ReadRules"
0x18005bbc7  lea     rcx, [rbp+57h+var_70]; this
0x18005bbcb  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18005bbd0  xor     r12d, r12d
0x18005bbd3  mov     [rbp+57h+hKey], r12
0x18005bbd7  mov     [rbp+57h+var_80], r12
0x18005bbdb  mov     [rbp+57h+cSubKeys], r12d
0x18005bbdf  mov     [rbp+57h+cbMaxSubKeyLen], r12d
0x18005bbe3  mov     [rbp+57h+cchName], r12d
0x18005bbe7  mov     edi, r12d
0x18005bbea  test    r14, r14
0x18005bbed  jz      short loc_18005BBF2
0x18005bbef  mov     [r14], r12d
0x18005bbf2  test    rsi, rsi
0x18005bbf5  jz      short loc_18005BBFA
0x18005bbf7  mov     [rsi], r12
0x18005bbfa  mov     eax, 10Ah
0x18005bbff  test    rbx, rbx
0x18005bc02  jz      loc_18005BEC7
0x18005bc08  mov     [rbp+57h+var_6C], ax
0x18005bc0c  mov     eax, 10Bh
0x18005bc11  test    r14, r14
0x18005bc14  jz      loc_18005BEC7
0x18005bc1a  mov     [rbp+57h+var_6C], ax
0x18005bc1e  mov     eax, 10Ch
0x18005bc23  test    rsi, rsi
0x18005bc26  jz      loc_18005BEC7
0x18005bc2c  mov     [rbp+57h+var_70], r12d
0x18005bc30  mov     [rbp+57h+var_6C], ax
0x18005bc34  lea     rax, [rbp+57h+hKey]
0x18005bc38  mov     [rsp+0E0h+phkResult], rax; phkResult
0x18005bc3d  mov     r9d, 20019h; samDesired
0x18005bc43  xor     r8d, r8d; ulOptions
0x18005bc46  lea     rdx, c_wszSafedocsScheduleRules; "Rules"
0x18005bc4d  mov     rcx, rbx; hKey
0x18005bc50  call    cs:__imp_RegOpenKeyExW
0x18005bc57  nop     dword ptr [rax+rax+00h]
0x18005bc5c  mov     r13d, 80070000h
0x18005bc62  test    eax, eax
0x18005bc64  jle     short loc_18005BC6C
0x18005bc66  movzx   eax, ax
0x18005bc69  or      eax, r13d
0x18005bc6c  mov     [rbp+57h+var_70], eax
0x18005bc6f  test    eax, eax
0x18005bc71  mov     eax, 111h
0x18005bc76  js      loc_18005BECE
0x18005bc7c  mov     [rbp+57h+var_6C], ax
0x18005bc80  mov     [rsp+0E0h+lpftLastWriteTime], r12; lpftLastWriteTime
0x18005bc85  mov     [rsp+0E0h+lpcbSecurityDescriptor], r12; lpcbSecurityDescriptor
0x18005bc8a  mov     [rsp+0E0h+lpcbMaxValueLen], r12; lpcbMaxValueLen
0x18005bc8f  mov     [rsp+0E0h+lpcbMaxValueNameLen], r12; lpcbMaxValueNameLen
0x18005bc94  mov     [rsp+0E0h+lpcValues], r12; lpcValues
0x18005bc99  mov     [rsp+0E0h+lpcbMaxClassLen], r12; lpcbMaxClassLen
0x18005bc9e  lea     rax, [rbp+57h+cbMaxSubKeyLen]
0x18005bca2  mov     [rsp+0E0h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x18005bca7  lea     rax, [rbp+57h+cSubKeys]
0x18005bcab  mov     [rsp+0E0h+phkResult], rax; lpcSubKeys
0x18005bcb0  xor     r9d, r9d; lpReserved
0x18005bcb3  xor     r8d, r8d; lpcchClass
0x18005bcb6  xor     edx, edx; lpClass
0x18005bcb8  mov     rcx, [rbp+57h+hKey]; hKey
0x18005bcbc  call    cs:__imp_RegQueryInfoKeyW
0x18005bcc3  nop     dword ptr [rax+rax+00h]
0x18005bcc8  test    eax, eax
0x18005bcca  jle     short loc_18005BCD2
0x18005bccc  movzx   eax, ax
0x18005bccf  or      eax, r13d
0x18005bcd2  mov     [rbp+57h+var_70], eax
0x18005bcd5  test    eax, eax
0x18005bcd7  mov     eax, 112h
0x18005bcdc  js      loc_18005BECE
0x18005bce2  mov     [rbp+57h+var_6C], ax
0x18005bce6  mov     ecx, [rbp+57h+cbMaxSubKeyLen]
0x18005bce9  inc     ecx
0x18005bceb  add     rcx, rcx; cb
0x18005bcee  call    cs:__imp_CoTaskMemAlloc
0x18005bcf5  nop     dword ptr [rax+rax+00h]
0x18005bcfa  mov     rdi, rax
0x18005bcfd  mov     ecx, 115h
0x18005bd02  test    rax, rax
0x18005bd05  jz      loc_18005BEBA
0x18005bd0b  mov     [rbp+57h+var_70], r12d
0x18005bd0f  mov     [rbp+57h+var_6C], cx
0x18005bd13  mov     r8d, [rbp+57h+cbMaxSubKeyLen]
0x18005bd17  inc     r8d
0x18005bd1a  add     r8, r8; Size
0x18005bd1d  xor     edx, edx; Val
0x18005bd1f  mov     rcx, rax; void *
0x18005bd22  call    memset_0
0x18005bd27  mov     ebx, r12d
0x18005bd2a  mov     edx, [rbp+57h+cSubKeys]
0x18005bd2d  cmp     ebx, edx
0x18005bd2f  jnb     loc_18005BE9A
0x18005bd35  mov     eax, [rbp+57h+cbMaxSubKeyLen]
0x18005bd38  inc     eax
0x18005bd3a  mov     [rbp+57h+cchName], eax
0x18005bd3d  mov     [rsp+0E0h+lpcValues], r12; lpftLastWriteTime
0x18005bd42  mov     [rsp+0E0h+lpcbMaxClassLen], r12; lpcchClass
0x18005bd47  mov     [rsp+0E0h+lpcbMaxSubKeyLen], r12; lpClass
0x18005bd4c  mov     [rsp+0E0h+phkResult], r12; lpReserved
0x18005bd51  lea     r9, [rbp+57h+cchName]; lpcchName
0x18005bd55  mov     r8, rdi; lpName
0x18005bd58  mov     edx, ebx; dwIndex
0x18005bd5a  mov     rcx, [rbp+57h+hKey]; hKey
0x18005bd5e  call    cs:__imp_RegEnumKeyExW
0x18005bd65  nop     dword ptr [rax+rax+00h]
0x18005bd6a  cmp     eax, 103h
0x18005bd6f  jz      loc_18005BE97
0x18005bd75  test    eax, eax
0x18005bd77  jle     short loc_18005BD7F
0x18005bd79  movzx   eax, ax
0x18005bd7c  or      eax, r13d
0x18005bd7f  mov     [rbp+57h+var_70], eax
0x18005bd82  test    eax, eax
0x18005bd84  mov     eax, 123h
0x18005bd89  js      loc_18005BECE
0x18005bd8f  mov     [rbp+57h+var_6C], ax
0x18005bd93  lea     rax, WPP_GLOBAL_Control
0x18005bd9a  mov     rcx, cs:WPP_GLOBAL_Control
0x18005bda1  cmp     rcx, rax
0x18005bda4  jz      short loc_18005BDC4
0x18005bda6  test    byte ptr [rcx+1Ch], 2
0x18005bdaa  jz      short loc_18005BDC4
0x18005bdac  mov     edx, 0Ah
0x18005bdb1  mov     r9, rdi
0x18005bdb4  lea     r8, WPP_fea9f066dab43d30b7e95d3387edc116_Traceguids
0x18005bdbb  mov     rcx, [rcx+10h]
0x18005bdbf  call    WPP_SF_S
0x18005bdc4  mov     rcx, [rbp+57h+var_80]; hKey
0x18005bdc8  test    rcx, rcx
0x18005bdcb  jz      short loc_18005BE00
0x18005bdcd  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18005bdd1  jz      short loc_18005BDE6
0x18005bdd3  call    cs:__imp_RegCloseKey
0x18005bdda  nop     dword ptr [rax+rax+00h]
0x18005bddf  mov     rcx, r12; hKey
0x18005bde2  mov     [rbp+57h+var_80], rcx
0x18005bde6  lea     rax, [rcx-1]
0x18005bdea  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18005bdee  ja      short loc_18005BE00
0x18005bdf0  call    cs:__imp_RegCloseKey
0x18005bdf7  nop     dword ptr [rax+rax+00h]
0x18005bdfc  mov     [rbp+57h+var_80], r12
0x18005be00  lea     rax, [rbp+57h+var_80]
0x18005be04  mov     [rsp+0E0h+phkResult], rax; phkResult
0x18005be09  mov     r9d, 20019h; samDesired
0x18005be0f  xor     r8d, r8d; ulOptions
0x18005be12  mov     rdx, rdi; lpSubKey
0x18005be15  mov     rcx, [rbp+57h+hKey]; hKey
0x18005be19  call    cs:__imp_RegOpenKeyExW
0x18005be20  nop     dword ptr [rax+rax+00h]
0x18005be25  test    eax, eax
0x18005be27  jle     short loc_18005BE2F
0x18005be29  movzx   eax, ax
0x18005be2c  or      eax, r13d
0x18005be2f  mov     [rbp+57h+var_70], eax
0x18005be32  test    eax, eax
0x18005be34  mov     eax, 127h
0x18005be39  js      loc_18005BECE
0x18005be3f  mov     [rbp+57h+var_6C], ax
0x18005be43  mov     rcx, rdi; String
0x18005be46  call    cs:__imp__wtoi
0x18005be4d  nop     dword ptr [rax+rax+00h]
0x18005be52  test    eax, eax
0x18005be54  jz      short loc_18005BE89
0x18005be56  mov     [rbp+57h+var_70], r12d
0x18005be5a  mov     ecx, 12Ah
0x18005be5f  mov     [rbp+57h+var_6C], cx
0x18005be63  mov     r8d, eax; unsigned int
0x18005be66  mov     rdx, [rbp+57h+var_80]; hKey
0x18005be6a  mov     rcx, r15; this
0x18005be6d  call    ?_ReadRuleFromRegistry@CSdBackupConfigImpl@@AEAAJPEAUHKEY__@@K@Z; CSdBackupConfigImpl::_ReadRuleFromRegistry(HKEY__ *,ulong)
0x18005be72  mov     [rbp+57h+var_70], eax
0x18005be75  test    eax, eax
0x18005be77  mov     eax, 12Fh
0x18005be7c  js      short loc_18005BECE
0x18005be7e  mov     [rbp+57h+var_6C], ax
0x18005be82  inc     ebx
0x18005be84  jmp     loc_18005BD2A
0x18005be89  mov     [rbp+57h+var_70], 81000036h
0x18005be90  mov     eax, 12Ah
0x18005be95  jmp     short loc_18005BECE
0x18005be97  mov     edx, [rbp+57h+cSubKeys]; unsigned int
0x18005be9a  mov     r9, rsi; struct _SD_BACKUP_ROOT **
0x18005be9d  mov     r8, r14; unsigned int *
0x18005bea0  mov     rcx, r15; this
0x18005bea3  call    ?_GetAllRules@CSdBackupConfigImpl@@AEAAJKPEAKPEAPEAU_SD_BACKUP_ROOT@@@Z; CSdBackupConfigImpl::_GetAllRules(ulong,ulong *,_SD_BACKUP_ROOT * *)
0x18005bea8  mov     [rbp+57h+var_70], eax
0x18005beab  test    eax, eax
0x18005bead  mov     eax, 133h
0x18005beb2  js      short loc_18005BECE
0x18005beb4  mov     [rbp+57h+var_6C], ax
0x18005beb8  jmp     short loc_18005BED2
0x18005beba  mov     [rbp+57h+var_70], 8007000Eh
0x18005bec1  mov     [rbp+57h+var_6A], cx
0x18005bec5  jmp     short loc_18005BED2
0x18005bec7  mov     [rbp+57h+var_70], 80070057h
0x18005bece  mov     [rbp+57h+var_6A], ax
0x18005bed2  mov     rcx, rdi; pv
0x18005bed5  call    cs:__imp_CoTaskMemFree
0x18005bedc  nop     dword ptr [rax+rax+00h]
0x18005bee1  mov     ebx, [rbp+57h+var_70]
0x18005bee4  mov     rcx, [rbp+57h+var_80]; hKey
0x18005bee8  lea     rax, [rcx-1]
0x18005beec  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18005bef0  ja      short loc_18005BF02
0x18005bef2  call    cs:__imp_RegCloseKey
0x18005bef9  nop     dword ptr [rax+rax+00h]
0x18005befe  mov     [rbp+57h+var_80], r12
0x18005bf02  mov     rcx, [rbp+57h+hKey]; hKey
0x18005bf06  lea     rdx, [rcx-1]
0x18005bf0a  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18005bf0e  ja      short loc_18005BF20
0x18005bf10  call    cs:__imp_RegCloseKey
0x18005bf17  nop     dword ptr [rax+rax+00h]
0x18005bf1c  mov     [rbp+57h+hKey], r12
0x18005bf20  lea     rcx, [rbp+57h+var_70]; this
0x18005bf24  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18005bf29  mov     eax, ebx
0x18005bf2b  mov     rbx, [rsp+0E0h+arg_0]
0x18005bf33  add     rsp, 0B0h
0x18005bf3a  pop     r15
0x18005bf3c  pop     r14
0x18005bf3e  pop     r13
0x18005bf40  pop     r12
0x18005bf42  pop     rdi
0x18005bf43  pop     rsi
0x18005bf44  pop     rbp
0x18005bf45  retn
```
