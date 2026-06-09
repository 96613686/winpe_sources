# LoadGPSettings(ulong *)

- ea: `0x18008e398`
- end: `0x18008e586`
- name: `?LoadGPSettings@@YAJPEAK@Z`
- size: `494`
- prototype: `__int64 __fastcall(unsigned int *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180042f68`
- `0x1800433d8`

## callees

- `0x180072e08`
- `0x180072f14`
- `0x18008e398`
- `0x18008e58c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008e492`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008e532`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008e554`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008e492`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008e532`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008e554`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18008e471`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18008e4bf`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18008e471`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18008e4bf`

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

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v20, "LoadGPSettings", 0x38u, 1u);
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
0x18008e398  push    rbp
0x18008e39a  push    rbx
0x18008e39b  push    rsi
0x18008e39c  push    rdi
0x18008e39d  push    r12
0x18008e39f  push    r14
0x18008e3a1  push    r15
0x18008e3a3  lea     rbp, [rsp-27h]
0x18008e3a8  sub     rsp, 0D0h
0x18008e3af  mov     ebx, 1
0x18008e3b4  lea     rdx, aLoadgpsettings; "LoadGPSettings"
0x18008e3bb  mov     r14, rcx
0x18008e3be  mov     r9d, ebx; unsigned __int16
0x18008e3c1  lea     rcx, [rbp+57h+var_70]; this
0x18008e3c5  lea     r8d, [rbx+37h]; unsigned __int16
0x18008e3c9  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18008e3ce  lea     rax, c_wszDisableBackup; "DisableBackupUI"
0x18008e3d5  mov     [rbp+57h+var_C8], ebx
0x18008e3d8  mov     [rbp+57h+lpValueName], rax
0x18008e3dc  lea     rdx, c_wszSdGroupPolicyKey; "SOFTWARE\\Policies\\Microsoft\\Windows"...
0x18008e3e3  lea     rax, c_wszDisableRestore; "DisableRestoreUI"
0x18008e3ea  mov     [rbp+57h+arg_10], 0
0x18008e3f2  mov     [rbp+57h+var_C0], rax
0x18008e3f6  mov     ebx, 20019h
0x18008e3fb  lea     rax, c_wszDisableSystemBackup; "DisableSystemBackupUI"
0x18008e402  mov     [rbp+57h+hKey], 0
0x18008e40a  mov     [rbp+57h+var_B0], rax
0x18008e40e  xor     r12d, r12d
0x18008e411  lea     rax, c_wszDisableBackupToNetwork; "DisableBackupToNetwork"
0x18008e418  mov     [rbp+57h+var_B8], 2
0x18008e41f  mov     [rbp+57h+var_A0], rax
0x18008e423  mov     r9d, ebx; samDesired
0x18008e426  lea     rax, c_wszDisableBackupToOptical; "DisableBackupToOptical"
0x18008e42d  mov     [rbp+57h+var_A8], 4
0x18008e434  mov     [rbp+57h+var_90], rax
0x18008e438  xor     r8d, r8d; ulOptions
0x18008e43b  lea     rax, c_wszDisableBackupToDisk; "DisableBackupToDisk"
0x18008e442  mov     [rbp+57h+var_98], 8
0x18008e449  mov     [rbp+57h+var_80], rax
0x18008e44d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18008e454  lea     rax, [rbp+57h+arg_10]
0x18008e458  mov     [rbp+57h+var_88], 10h
0x18008e45f  mov     [rsp+100h+phkResult], rax; phkResult
0x18008e464  xor     r15d, r15d
0x18008e467  mov     [rbp+57h+var_78], 20h ; ' '
0x18008e46e  mov     [r14], r12d
0x18008e471  call    cs:__imp_RegOpenKeyExW
0x18008e478  nop     dword ptr [rax+rax+00h]
0x18008e47d  mov     rcx, [rbp+57h+hKey]; hKey
0x18008e481  test    eax, eax
0x18008e483  cmovz   r12, [rbp+57h+arg_10]
0x18008e488  lea     rax, [rcx-1]
0x18008e48c  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18008e490  ja      short loc_18008E4A2
0x18008e492  call    cs:__imp_RegCloseKey
0x18008e499  nop     dword ptr [rax+rax+00h]
0x18008e49e  mov     [rbp+57h+hKey], r15
0x18008e4a2  lea     rax, [rbp+57h+hKey]
0x18008e4a6  mov     r9d, ebx; samDesired
0x18008e4a9  xor     r8d, r8d; ulOptions
0x18008e4ac  mov     [rsp+100h+phkResult], rax; phkResult
0x18008e4b1  lea     rdx, c_wszSdGroupPolicyKey; "SOFTWARE\\Policies\\Microsoft\\Windows"...
0x18008e4b8  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18008e4bf  call    cs:__imp_RegOpenKeyExW
0x18008e4c6  nop     dword ptr [rax+rax+00h]
0x18008e4cb  mov     esi, [rbp+57h+var_70]
0x18008e4ce  test    eax, eax
0x18008e4d0  cmovz   r15, [rbp+57h+hKey]
0x18008e4d5  xor     ebx, ebx
0x18008e4d7  cmp     ebx, 6
0x18008e4da  jnb     short loc_18008E524
0x18008e4dc  movsxd  rdi, ebx
0x18008e4df  lea     r9, [rbp+57h+arg_0]; int *
0x18008e4e3  add     rdi, rdi
0x18008e4e6  mov     [rbp+57h+arg_0], 0
0x18008e4ed  mov     rdx, r15; HKEY
0x18008e4f0  mov     rcx, r12; hKey
0x18008e4f3  mov     r8, [rbp+rdi*8+57h+lpValueName]; lpValueName
0x18008e4f8  call    ?QueryGroupPolicySetting@@YAJPEAUHKEY__@@0PEBGPEAH@Z; QueryGroupPolicySetting(HKEY__ *,HKEY__ *,ushort const *,int *)
0x18008e4fd  mov     esi, eax
0x18008e4ff  mov     [rbp+57h+var_70], eax
0x18008e502  test    eax, eax
0x18008e504  mov     eax, 65h ; 'e'
0x18008e509  js      short loc_18008E520
0x18008e50b  cmp     [rbp+57h+arg_0], 0
0x18008e50f  mov     [rbp+57h+var_6C], ax
0x18008e513  jz      short loc_18008E51C
0x18008e515  mov     eax, [rbp+rdi*8+57h+var_C8]
0x18008e519  or      [r14], eax
0x18008e51c  inc     ebx
0x18008e51e  jmp     short loc_18008E4D7
0x18008e520  mov     [rbp+57h+var_6A], ax
0x18008e524  mov     rcx, [rbp+57h+hKey]; hKey
0x18008e528  lea     rax, [rcx-1]
0x18008e52c  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18008e530  ja      short loc_18008E546
0x18008e532  call    cs:__imp_RegCloseKey
0x18008e539  nop     dword ptr [rax+rax+00h]
0x18008e53e  mov     [rbp+57h+hKey], 0
0x18008e546  mov     rcx, [rbp+57h+arg_10]; hKey
0x18008e54a  lea     rdx, [rcx-1]
0x18008e54e  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18008e552  ja      short loc_18008E568
0x18008e554  call    cs:__imp_RegCloseKey
0x18008e55b  nop     dword ptr [rax+rax+00h]
0x18008e560  mov     [rbp+57h+arg_10], 0
0x18008e568  lea     rcx, [rbp+57h+var_70]; this
0x18008e56c  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18008e571  mov     eax, esi
0x18008e573  add     rsp, 0D0h
0x18008e57a  pop     r15
0x18008e57c  pop     r14
0x18008e57e  pop     r12
0x18008e580  pop     rdi
0x18008e581  pop     rsi
0x18008e582  pop     rbx
0x18008e583  pop     rbp
0x18008e584  retn
```
