# SetUserVaultCDSMigrationRegKey(void)

- ea: `0x1800384ec`
- end: `0x180038659`
- name: `?SetUserVaultCDSMigrationRegKey@@YAKXZ`
- size: `365`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18001cecc`

## callees

- `0x180003140`
- `0x1800384ec`
- `0x18003a580`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800385e3`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800385e3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003851f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180038620`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180038620`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 SetUserVaultCDSMigrationRegKey(void)
{
  __int64 v0; // rax
  const wchar_t *v1; // rcx
  __int64 v2; // r8
  WCHAR *v3; // r9
  wchar_t v4; // dx
  WCHAR *v5; // rcx
  unsigned int v6; // ebx
  BYTE Data[8]; // [rsp+50h] [rbp-B0h] BYREF
  LSTATUS (__stdcall *v9)(HKEY); // [rsp+58h] [rbp-A8h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-A0h] BYREF
  int v11; // [rsp+68h] [rbp-98h]
  WCHAR SubKey[264]; // [rsp+70h] [rbp-90h] BYREF

  *(_DWORD *)Data = 1;
  v9 = RegCloseKey;
  hKey = 0;
  v11 = 0;
  v0 = 2147483646;
  v1 = L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Vault\\";
  v2 = 260;
  v3 = SubKey;
  do
  {
    if ( !v0 )
      break;
    v4 = *v1;
    if ( !*v1 )
      break;
    ++v1;
    *v3++ = v4;
    --v0;
    --v2;
  }
  while ( v2 );
  v5 = v3 - 1;
  if ( v2 )
    v5 = v3;
  *v5 = 0;
  if ( v2 )
  {
    v6 = RegCreateKeyExW(HKEY_CURRENT_USER, SubKey, 0, 0, 0, 0x20006u, 0, &hKey, 0);
    if ( !v6 )
    {
      v6 = RegSetValueExW(hKey, L"VaultCDSMigration", 0, 4u, Data, 4u);
      CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v9);
      return v6;
    }
  }
  else
  {
    v6 = v2 == 0 ? 0x7A : 0;
  }
  CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v9);
  return v6;
}

```

## disassembly

```asm
0x1800384ec  mov     [rsp-8+arg_0], rbx
0x1800384f1  mov     [rsp-8+arg_8], rdi
0x1800384f6  push    rbp
0x1800384f7  lea     rbp, [rsp-190h]
0x1800384ff  sub     rsp, 290h
0x180038506  mov     rax, cs:__security_cookie
0x18003850d  xor     rax, rsp
0x180038510  mov     [rbp+190h+var_10], rax
0x180038517  mov     dword ptr [rsp+290h+Data], 1
0x18003851f  mov     rax, cs:__imp_RegCloseKey
0x180038526  mov     [rsp+290h+var_238], rax
0x18003852b  xor     edi, edi
0x18003852d  mov     [rsp+290h+hKey], rdi
0x180038532  mov     [rsp+290h+var_228], edi
0x180038536  mov     eax, 7FFFFFFEh
0x18003853b  lea     rcx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180038542  mov     r8d, 104h
0x180038548  lea     r9, [rsp+290h+SubKey]
0x18003854d  test    rax, rax
0x180038550  jz      short loc_18003856F
0x180038552  movzx   edx, word ptr [rcx]
0x180038555  test    dx, dx
0x180038558  jz      short loc_18003856F
0x18003855a  add     rcx, 2
0x18003855e  mov     [r9], dx
0x180038562  add     r9, 2
0x180038566  dec     rax
0x180038569  sub     r8, 1
0x18003856d  jnz     short loc_18003854D
0x18003856f  mov     rax, r8
0x180038572  neg     rax
0x180038575  sbb     edx, edx
0x180038577  not     edx
0x180038579  and     edx, 8007007Ah
0x18003857f  lea     rcx, [r9-2]
0x180038583  test    r8, r8
0x180038586  cmovnz  rcx, r9
0x18003858a  mov     [rcx], di
0x18003858d  jnz     short loc_1800385B1
0x18003858f  mov     eax, edx
0x180038591  and     eax, 1FFF0000h
0x180038596  movzx   ebx, dx
0x180038599  cmp     eax, 70000h
0x18003859e  cmovnz  ebx, edx
0x1800385a1  lea     rcx, [rsp+290h+var_238]
0x1800385a6  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x1800385ab  nop
0x1800385ac  jmp     loc_180038633
0x1800385b1  mov     [rsp+290h+lpdwDisposition], rdi; lpdwDisposition
0x1800385b6  lea     rax, [rsp+290h+hKey]
0x1800385bb  mov     [rsp+290h+phkResult], rax; phkResult
0x1800385c0  mov     [rsp+290h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x1800385c5  mov     [rsp+290h+samDesired], 20006h; samDesired
0x1800385cd  mov     [rsp+290h+dwOptions], edi; dwOptions
0x1800385d1  xor     r9d, r9d; lpClass
0x1800385d4  xor     r8d, r8d; Reserved
0x1800385d7  lea     rdx, [rsp+290h+SubKey]; lpSubKey
0x1800385dc  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1800385e3  call    cs:__imp_RegCreateKeyExW
0x1800385e9  mov     ebx, eax
0x1800385eb  test    eax, eax
0x1800385ed  jz      short loc_1800385FC
0x1800385ef  lea     rcx, [rsp+290h+var_238]
0x1800385f4  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x1800385f9  nop
0x1800385fa  jmp     short loc_180038633
0x1800385fc  mov     r9d, 4; dwType
0x180038602  mov     [rsp+290h+samDesired], r9d; cbData
0x180038607  lea     rax, [rsp+290h+Data]
0x18003860c  mov     qword ptr [rsp+290h+dwOptions], rax; lpData
0x180038611  xor     r8d, r8d; Reserved
0x180038614  lea     rdx, ValueName; "VaultCDSMigration"
0x18003861b  mov     rcx, [rsp+290h+hKey]; hKey
0x180038620  call    cs:__imp_RegSetValueExW
0x180038626  mov     ebx, eax
0x180038628  lea     rcx, [rsp+290h+var_238]
0x18003862d  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180038632  nop
0x180038633  mov     eax, ebx
0x180038635  mov     rcx, [rbp+190h+var_10]
0x18003863c  xor     rcx, rsp; StackCookie
0x18003863f  call    __security_check_cookie
0x180038644  lea     r11, [rsp+290h+var_s0]
0x18003864c  mov     rbx, [r11+10h]
0x180038650  mov     rdi, [r11+18h]
0x180038654  mov     rsp, r11
0x180038657  pop     rbp
0x180038658  retn
```
