# LoadGPSettings(ulong *)

- ea: `0x18008a780`
- end: `0x18008a94f`
- name: `?LoadGPSettings@@YAJPEAK@Z`
- size: `463`
- prototype: `__int64 __fastcall(unsigned int *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18004172c`
- `0x180041b90`

## callees

- `0x18006fe84`
- `0x18006ff8c`
- `0x18008a780`
- `0x18008a958`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008a874`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008a908`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008a924`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008a874`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008a908`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008a924`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18008a859`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18008a89b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18008a859`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18008a89b`

## pseudocode

```c
__int64 __fastcall LoadGPSettings(unsigned int *a1)
{
  HKEY v2; // r12
  HKEY v3; // r15
  LSTATUS v4; // eax
  int v5; // esi
  unsigned int i; // ebx
  LPCWSTR lpValueName; // [rsp+30h] [rbp-79h]
  _DWORD v9[2]; // [rsp+38h] [rbp-71h]
  const wchar_t *v10; // [rsp+40h] [rbp-69h]
  int v11; // [rsp+48h] [rbp-61h]
  const wchar_t *v12; // [rsp+50h] [rbp-59h]
  int v13; // [rsp+58h] [rbp-51h]
  const wchar_t *v14; // [rsp+60h] [rbp-49h]
  int v15; // [rsp+68h] [rbp-41h]
  const wchar_t *v16; // [rsp+70h] [rbp-39h]
  int v17; // [rsp+78h] [rbp-31h]
  const wchar_t *v18; // [rsp+80h] [rbp-29h]
  int v19; // [rsp+88h] [rbp-21h]
  int v20; // [rsp+90h] [rbp-19h] BYREF
  __int16 v21; // [rsp+94h] [rbp-15h]
  __int16 v22; // [rsp+96h] [rbp-13h]
  int v23; // [rsp+110h] [rbp+67h] BYREF
  HKEY hKey; // [rsp+118h] [rbp+6Fh] BYREF
  HKEY phkResult; // [rsp+120h] [rbp+77h] BYREF

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v20, "LoadGPSettings", 56, 1);
  v9[0] = 1;
  lpValueName = L"DisableBackupUI";
  phkResult = 0;
  v10 = L"DisableRestoreUI";
  hKey = 0;
  v12 = L"DisableSystemBackupUI";
  v2 = 0;
  v11 = 2;
  v14 = L"DisableBackupToNetwork";
  v13 = 4;
  v16 = L"DisableBackupToOptical";
  v15 = 8;
  v18 = L"DisableBackupToDisk";
  v17 = 16;
  v3 = 0;
  v19 = 32;
  *a1 = 0;
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"SOFTWARE\\Policies\\Microsoft\\Windows\\Backup\\Client",
          0,
          0x20019u,
          &phkResult) )
    v2 = phkResult;
  if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  v4 = RegOpenKeyExW(HKEY_CURRENT_USER, L"SOFTWARE\\Policies\\Microsoft\\Windows\\Backup\\Client", 0, 0x20019u, &hKey);
  v5 = v20;
  if ( !v4 )
    v3 = hKey;
  for ( i = 0; i < 6; ++i )
  {
    v23 = 0;
    v5 = QueryGroupPolicySetting(v2, v3, *(LPCWSTR *)&v9[4 * i - 2], &v23);
    v20 = v5;
    if ( v5 < 0 )
    {
      v22 = 101;
      break;
    }
    v21 = 101;
    if ( v23 )
      *a1 |= v9[4 * i];
  }
  if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( (unsigned __int64)phkResult - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    RegCloseKey(phkResult);
    phkResult = 0;
  }
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v20);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18008a780  push    rbp
0x18008a782  push    rbx
0x18008a783  push    rsi
0x18008a784  push    rdi
0x18008a785  push    r12
0x18008a787  push    r14
0x18008a789  push    r15
0x18008a78b  lea     rbp, [rsp-27h]
0x18008a790  sub     rsp, 0D0h
0x18008a797  mov     ebx, 1
0x18008a79c  lea     rdx, aLoadgpsettings; "LoadGPSettings"
0x18008a7a3  mov     r14, rcx
0x18008a7a6  mov     r9d, ebx; unsigned __int16
0x18008a7a9  lea     rcx, [rbp+57h+var_70]; this
0x18008a7ad  lea     r8d, [rbx+37h]; unsigned __int16
0x18008a7b1  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18008a7b6  lea     rax, c_wszDisableBackup; "DisableBackupUI"
0x18008a7bd  mov     [rbp+57h+var_C8], ebx
0x18008a7c0  mov     [rbp+57h+lpValueName], rax
0x18008a7c4  lea     rdx, c_wszSdGroupPolicyKey; "SOFTWARE\\Policies\\Microsoft\\Windows"...
0x18008a7cb  lea     rax, c_wszDisableRestore; "DisableRestoreUI"
0x18008a7d2  mov     [rbp+57h+arg_10], 0
0x18008a7da  mov     [rbp+57h+var_C0], rax
0x18008a7de  mov     ebx, 20019h
0x18008a7e3  lea     rax, c_wszDisableSystemBackup; "DisableSystemBackupUI"
0x18008a7ea  mov     [rbp+57h+hKey], 0
0x18008a7f2  mov     [rbp+57h+var_B0], rax
0x18008a7f6  xor     r12d, r12d
0x18008a7f9  lea     rax, c_wszDisableBackupToNetwork; "DisableBackupToNetwork"
0x18008a800  mov     [rbp+57h+var_B8], 2
0x18008a807  mov     [rbp+57h+var_A0], rax
0x18008a80b  mov     r9d, ebx; samDesired
0x18008a80e  lea     rax, c_wszDisableBackupToOptical; "DisableBackupToOptical"
0x18008a815  mov     [rbp+57h+var_A8], 4
0x18008a81c  mov     [rbp+57h+var_90], rax
0x18008a820  xor     r8d, r8d; ulOptions
0x18008a823  lea     rax, c_wszDisableBackupToDisk; "DisableBackupToDisk"
0x18008a82a  mov     [rbp+57h+var_98], 8
0x18008a831  mov     [rbp+57h+var_80], rax
0x18008a835  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18008a83c  lea     rax, [rbp+57h+arg_10]
0x18008a840  mov     [rbp+57h+var_88], 10h
0x18008a847  mov     [rsp+100h+phkResult], rax; phkResult
0x18008a84c  xor     r15d, r15d
0x18008a84f  mov     [rbp+57h+var_78], 20h ; ' '
0x18008a856  mov     [r14], r12d
0x18008a859  call    cs:__imp_RegOpenKeyExW
0x18008a85f  mov     rcx, [rbp+57h+hKey]; hKey
0x18008a863  test    eax, eax
0x18008a865  cmovz   r12, [rbp+57h+arg_10]
0x18008a86a  lea     rax, [rcx-1]
0x18008a86e  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18008a872  ja      short loc_18008A87E
0x18008a874  call    cs:__imp_RegCloseKey
0x18008a87a  mov     [rbp+57h+hKey], r15
0x18008a87e  lea     rax, [rbp+57h+hKey]
0x18008a882  mov     r9d, ebx; samDesired
0x18008a885  xor     r8d, r8d; ulOptions
0x18008a888  mov     [rsp+100h+phkResult], rax; phkResult
0x18008a88d  lea     rdx, c_wszSdGroupPolicyKey; "SOFTWARE\\Policies\\Microsoft\\Windows"...
0x18008a894  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18008a89b  call    cs:__imp_RegOpenKeyExW
0x18008a8a1  mov     esi, [rbp+57h+var_70]
0x18008a8a4  test    eax, eax
0x18008a8a6  cmovz   r15, [rbp+57h+hKey]
0x18008a8ab  xor     ebx, ebx
0x18008a8ad  cmp     ebx, 6
0x18008a8b0  jnb     short loc_18008A8FA
0x18008a8b2  movsxd  rdi, ebx
0x18008a8b5  lea     r9, [rbp+57h+arg_0]; int *
0x18008a8b9  add     rdi, rdi
0x18008a8bc  mov     [rbp+57h+arg_0], 0
0x18008a8c3  mov     rdx, r15; HKEY
0x18008a8c6  mov     rcx, r12; hKey
0x18008a8c9  mov     r8, [rbp+rdi*8+57h+lpValueName]; lpValueName
0x18008a8ce  call    ?QueryGroupPolicySetting@@YAJPEAUHKEY__@@0PEBGPEAH@Z; QueryGroupPolicySetting(HKEY__ *,HKEY__ *,ushort const *,int *)
0x18008a8d3  mov     esi, eax
0x18008a8d5  mov     [rbp+57h+var_70], eax
0x18008a8d8  test    eax, eax
0x18008a8da  mov     eax, 65h ; 'e'
0x18008a8df  js      short loc_18008A8F6
0x18008a8e1  cmp     [rbp+57h+arg_0], 0
0x18008a8e5  mov     [rbp+57h+var_6C], ax
0x18008a8e9  jz      short loc_18008A8F2
0x18008a8eb  mov     eax, [rbp+rdi*8+57h+var_C8]
0x18008a8ef  or      [r14], eax
0x18008a8f2  inc     ebx
0x18008a8f4  jmp     short loc_18008A8AD
0x18008a8f6  mov     [rbp+57h+var_6A], ax
0x18008a8fa  mov     rcx, [rbp+57h+hKey]; hKey
0x18008a8fe  lea     rax, [rcx-1]
0x18008a902  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18008a906  ja      short loc_18008A916
0x18008a908  call    cs:__imp_RegCloseKey
0x18008a90e  mov     [rbp+57h+hKey], 0
0x18008a916  mov     rcx, [rbp+57h+arg_10]; hKey
0x18008a91a  lea     rdx, [rcx-1]
0x18008a91e  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18008a922  ja      short loc_18008A932
0x18008a924  call    cs:__imp_RegCloseKey
0x18008a92a  mov     [rbp+57h+arg_10], 0
0x18008a932  lea     rcx, [rbp+57h+var_70]; this
0x18008a936  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18008a93b  mov     eax, esi
0x18008a93d  add     rsp, 0D0h
0x18008a944  pop     r15
0x18008a946  pop     r14
0x18008a948  pop     r12
0x18008a94a  pop     rdi
0x18008a94b  pop     rsi
0x18008a94c  pop     rbx
0x18008a94d  pop     rbp
0x18008a94e  retn
```
