# CSdController::_EnsureTargetNotBlockedByGP(_SD_STORAGE_DEVICE_PROP *)

- ea: `0x18001199c`
- end: `0x180011b7b`
- name: `?_EnsureTargetNotBlockedByGP@CSdController@@AEAAJPEAU_SD_STORAGE_DEVICE_PROP@@@Z`
- size: `479`
- prototype: `__int64 __fastcall(CSdController *__hidden this, struct _SD_STORAGE_DEVICE_PROP *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180011760`

## callees

- `0x18001199c`
- `0x18001586c`
- `0x180015974`
- `0x18001e67c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011a7e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011b38`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011b54`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011a7e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011b38`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011b54`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180011a6a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180011aac`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180011a6a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180011aac`

## pseudocode

```c
__int64 __fastcall CSdController::_EnsureTargetNotBlockedByGP(CSdController *this, struct _SD_STORAGE_DEVICE_PROP *a2)
{
  unsigned int v3; // ebx
  int v4; // eax
  const WCHAR *v5; // rbx
  int v6; // eax
  HKEY v7; // rcx
  int v9; // [rsp+30h] [rbp-40h] BYREF
  __int16 v10; // [rsp+34h] [rbp-3Ch]
  __int16 v11; // [rsp+36h] [rbp-3Ah]
  CSdController *v12; // [rsp+80h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+88h] [rbp+18h] BYREF
  HKEY phkResult; // [rsp+90h] [rbp+20h] BYREF

  v12 = this;
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v9, "CSdController::_EnsureTargetNotBlockedByGP", 1770, 1);
  phkResult = 0;
  hKey = 0;
  LODWORD(v12) = 0;
  if ( !a2 )
  {
    v3 = -2147024809;
    v11 = 1779;
    v9 = -2147024809;
    goto LABEL_27;
  }
  v10 = 1779;
  v4 = *((_DWORD *)a2 + 14);
  v9 = 0;
  switch ( v4 )
  {
    case 11:
    case 6:
      v5 = L"DisableBackupToDisk";
      break;
    case 7:
      v5 = L"DisableBackupToNetwork";
      break;
    case 13:
      v5 = L"DisableBackupToOptical";
      break;
    default:
      v3 = 0;
      v10 = 1800;
      goto LABEL_27;
  }
  RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Policies\\Microsoft\\Windows\\Backup\\Client", 0, 0x20019u, &phkResult);
  if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  RegOpenKeyExW(HKEY_CURRENT_USER, L"SOFTWARE\\Policies\\Microsoft\\Windows\\Backup\\Client", 0, 0x20019u, &hKey);
  if ( (unsigned __int64)phkResult - 1 > 0xFFFFFFFFFFFFFFFDuLL
    || (int)SxRegReadDWORD(phkResult, v5, (unsigned int *)&v12, 0) < 0
    || (v6 = (int)v12, (unsigned int)v12 > 1) )
  {
    v7 = hKey;
    if ( (unsigned __int64)hKey - 1 > 0xFFFFFFFFFFFFFFFDuLL )
    {
LABEL_22:
      v3 = 0;
      v10 = 1838;
      goto LABEL_23;
    }
    if ( (int)SxRegReadDWORD(hKey, v5, (unsigned int *)&v12, 0) < 0 )
      goto LABEL_21;
    v6 = (int)v12;
    if ( (unsigned int)v12 > 1 )
      goto LABEL_21;
  }
  if ( !v6 )
  {
LABEL_21:
    v7 = hKey;
    goto LABEL_22;
  }
  v7 = hKey;
  v11 = 1833;
  v3 = -2130706187;
LABEL_23:
  v9 = v3;
  if ( (unsigned __int64)v7 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    RegCloseKey(v7);
    hKey = 0;
  }
  if ( (unsigned __int64)phkResult - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    RegCloseKey(phkResult);
    phkResult = 0;
  }
LABEL_27:
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v9);
  return v3;
}

```

## disassembly

```asm
0x18001199c  mov     [rsp-8+arg_18], rbx
0x1800119a1  mov     [rsp-8+arg_0], rcx
0x1800119a6  push    rbp
0x1800119a7  mov     rbp, rsp
0x1800119aa  sub     rsp, 70h
0x1800119ae  mov     rbx, rdx
0x1800119b1  lea     rcx, [rbp+var_40]; this
0x1800119b5  lea     rdx, aCsdcontrollerE_0; "CSdController::_EnsureTargetNotBlockedB"...
0x1800119bc  mov     r9d, 1; unsigned __int16
0x1800119c2  mov     r8d, 6EAh; unsigned __int16
0x1800119c8  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x1800119cd  mov     [rbp+arg_10], 0
0x1800119d5  mov     eax, 6F3h
0x1800119da  mov     [rbp+hKey], 0
0x1800119e2  mov     dword ptr [rbp+arg_0], 0
0x1800119e9  test    rbx, rbx
0x1800119ec  jnz     short loc_1800119FF
0x1800119ee  mov     ebx, 80070057h
0x1800119f3  mov     [rbp+var_3A], ax
0x1800119f7  mov     [rbp+var_40], ebx
0x1800119fa  jmp     loc_180011B62
0x1800119ff  mov     [rbp+var_3C], ax
0x180011a03  mov     eax, [rbx+38h]
0x180011a06  mov     [rbp+var_40], 0
0x180011a0d  cmp     eax, 0Bh
0x180011a10  jz      short loc_180011A43
0x180011a12  cmp     eax, 6
0x180011a15  jz      short loc_180011A43
0x180011a17  cmp     eax, 7
0x180011a1a  jnz     short loc_180011A25
0x180011a1c  lea     rbx, c_wszDisableBackupToNetwork; "DisableBackupToNetwork"
0x180011a23  jmp     short loc_180011A4A
0x180011a25  cmp     eax, 0Dh
0x180011a28  jnz     short loc_180011A33
0x180011a2a  lea     rbx, c_wszDisableBackupToOptical; "DisableBackupToOptical"
0x180011a31  jmp     short loc_180011A4A
0x180011a33  mov     eax, 708h
0x180011a38  xor     ebx, ebx
0x180011a3a  mov     [rbp+var_3C], ax
0x180011a3e  jmp     loc_180011B62
0x180011a43  lea     rbx, c_wszDisableBackupToDisk; "DisableBackupToDisk"
0x180011a4a  lea     rax, [rbp+arg_10]
0x180011a4e  mov     r9d, 20019h; samDesired
0x180011a54  xor     r8d, r8d; ulOptions
0x180011a57  mov     [rsp+70h+phkResult], rax; phkResult
0x180011a5c  lea     rdx, c_wszSdGroupPolicyKey; "SOFTWARE\\Policies\\Microsoft\\Windows"...
0x180011a63  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180011a6a  call    cs:__imp_RegOpenKeyExW
0x180011a70  mov     rcx, [rbp+hKey]; hKey
0x180011a74  lea     rax, [rcx-1]
0x180011a78  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180011a7c  ja      short loc_180011A8C
0x180011a7e  call    cs:__imp_RegCloseKey
0x180011a84  mov     [rbp+hKey], 0
0x180011a8c  lea     rax, [rbp+hKey]
0x180011a90  mov     r9d, 20019h; samDesired
0x180011a96  xor     r8d, r8d; ulOptions
0x180011a99  mov     [rsp+70h+phkResult], rax; phkResult
0x180011a9e  lea     rdx, c_wszSdGroupPolicyKey; "SOFTWARE\\Policies\\Microsoft\\Windows"...
0x180011aa5  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180011aac  call    cs:__imp_RegOpenKeyExW
0x180011ab2  mov     rcx, [rbp+arg_10]; hKey
0x180011ab6  lea     rax, [rcx-1]
0x180011aba  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180011abe  ja      short loc_180011ADB
0x180011ac0  xor     r9d, r9d; int
0x180011ac3  lea     r8, [rbp+arg_0]; unsigned int *
0x180011ac7  mov     rdx, rbx; lpValueName
0x180011aca  call    ?SxRegReadDWORD@@YAJPEAUHKEY__@@PEBGPEAKH@Z; SxRegReadDWORD(HKEY__ *,ushort const *,ulong *,int)
0x180011acf  test    eax, eax
0x180011ad1  js      short loc_180011ADB
0x180011ad3  mov     eax, dword ptr [rbp+arg_0]
0x180011ad6  cmp     eax, 1
0x180011ad9  jbe     short loc_180011B04
0x180011adb  mov     rcx, [rbp+hKey]; hKey
0x180011adf  lea     rax, [rcx-1]
0x180011ae3  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180011ae7  ja      short loc_180011B20
0x180011ae9  xor     r9d, r9d; int
0x180011aec  lea     r8, [rbp+arg_0]; unsigned int *
0x180011af0  mov     rdx, rbx; lpValueName
0x180011af3  call    ?SxRegReadDWORD@@YAJPEAUHKEY__@@PEBGPEAKH@Z; SxRegReadDWORD(HKEY__ *,ushort const *,ulong *,int)
0x180011af8  test    eax, eax
0x180011afa  js      short loc_180011B1C
0x180011afc  mov     eax, dword ptr [rbp+arg_0]
0x180011aff  cmp     eax, 1
0x180011b02  ja      short loc_180011B1C
0x180011b04  test    eax, eax
0x180011b06  jz      short loc_180011B1C
0x180011b08  mov     rcx, [rbp+hKey]
0x180011b0c  mov     eax, 729h
0x180011b11  mov     [rbp+var_3A], ax
0x180011b15  mov     ebx, 810000F5h
0x180011b1a  jmp     short loc_180011B2B
0x180011b1c  mov     rcx, [rbp+hKey]; hKey
0x180011b20  mov     eax, 72Eh
0x180011b25  xor     ebx, ebx
0x180011b27  mov     [rbp+var_3C], ax
0x180011b2b  mov     [rbp+var_40], ebx
0x180011b2e  lea     rax, [rcx-1]
0x180011b32  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180011b36  ja      short loc_180011B46
0x180011b38  call    cs:__imp_RegCloseKey
0x180011b3e  mov     [rbp+hKey], 0
0x180011b46  mov     rcx, [rbp+arg_10]; hKey
0x180011b4a  lea     rdx, [rcx-1]
0x180011b4e  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180011b52  ja      short loc_180011B62
0x180011b54  call    cs:__imp_RegCloseKey
0x180011b5a  mov     [rbp+arg_10], 0
0x180011b62  lea     rcx, [rbp+var_40]; this
0x180011b66  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180011b6b  mov     eax, ebx
0x180011b6d  mov     rbx, [rsp+70h+arg_18]
0x180011b75  add     rsp, 70h
0x180011b79  pop     rbp
0x180011b7a  retn
```
