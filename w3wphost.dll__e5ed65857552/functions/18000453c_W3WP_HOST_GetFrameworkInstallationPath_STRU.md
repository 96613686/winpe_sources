# W3WP_HOST::GetFrameworkInstallationPath(STRU *)

- ea: `0x18000453c`
- end: `0x18000474e`
- name: `?GetFrameworkInstallationPath@W3WP_HOST@@AEAAJPEAVSTRU@@@Z`
- size: `530`
- prototype: `__int64 __fastcall(W3WP_HOST *__hidden this, struct STRU *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800062bc`

## callees

- `0x18000453c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004734`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004734`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000459d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000459d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800045f5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180004653`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800045f5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180004653`
- `iisutil!?Resize@STRU@@QEAAJK@Z` at `0x18000460e`
- `iisutil!?Resize@STRU@@QEAAJK@Z` at `0x1800046ad`
- `iisutil!?Resize@STRU@@QEAAJK@Z` at `0x18000460e`
- `iisutil!?Resize@STRU@@QEAAJK@Z` at `0x1800046ad`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x18000456a`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x18000456a`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800045c9`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180004627`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000468b`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800046c2`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800046ec`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800045c9`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180004627`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000468b`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800046c2`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800046ec`
- `iisutil!?SyncWithBuffer@STRU@@QEAAXXZ` at `0x1800046dd`
- `iisutil!?SyncWithBuffer@STRU@@QEAAXXZ` at `0x1800046dd`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18000471d`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18000471d`
- `iisutil!?QueryBuffer@STRU@@QEAAPEAVBUFFER@@XZ` at `0x18000455b`
- `iisutil!?QueryBuffer@STRU@@QEAAPEAVBUFFER@@XZ` at `0x18000455b`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x1800046fe`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x1800046fe`

## string_xrefs

- `0x1800045e9`: `InstallRoot`
- `0x180004647`: `InstallRoot`

## pseudocode

```c
__int64 __fastcall W3WP_HOST::GetFrameworkInstallationPath(W3WP_HOST *this, struct STRU *a2)
{
  BUFFER *Buffer; // rax
  unsigned int Size; // eax
  LSTATUS v5; // eax
  signed int v6; // edi
  BYTE *Str; // rax
  BYTE *v8; // rax
  unsigned __int16 *v9; // rax
  unsigned __int16 *v10; // rax
  unsigned __int16 *v11; // rbx
  W3WP_HOST *cbData; // [rsp+60h] [rbp+30h] BYREF
  DWORD Type; // [rsp+70h] [rbp+40h] BYREF
  HKEY hKey; // [rsp+78h] [rbp+48h] BYREF

  cbData = this;
  hKey = 0;
  Buffer = STRU::QueryBuffer(a2);
  Size = BUFFER::QuerySize(Buffer);
  Type = 0;
  LODWORD(cbData) = Size;
  v5 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\.NETFramework", 0, 0x20019u, &hKey);
  v6 = v5;
  if ( v5 )
  {
    if ( v5 <= 0 )
      goto LABEL_19;
    goto LABEL_3;
  }
  v6 = 0;
  Str = (BYTE *)STRU::QueryStr(a2);
  v5 = RegQueryValueExW(hKey, L"InstallRoot", 0, &Type, Str, (LPDWORD)&cbData);
  if ( v5 == 234 )
  {
    v6 = STRU::Resize(a2, (unsigned int)cbData);
    if ( v6 < 0 )
      goto LABEL_19;
    v8 = (BYTE *)STRU::QueryStr(a2);
    v5 = RegQueryValueExW(hKey, L"InstallRoot", 0, &Type, v8, (LPDWORD)&cbData);
  }
  if ( v5 )
  {
    if ( v5 > 0 )
    {
LABEL_3:
      v6 = (unsigned __int16)v5 | 0x80070000;
      goto LABEL_19;
    }
    goto LABEL_18;
  }
  if ( Type - 1 > 1 || (unsigned int)cbData < 2 )
  {
    v6 = -2147024883;
    goto LABEL_19;
  }
  v9 = STRU::QueryStr(a2);
  if ( v9[((unsigned __int64)(unsigned int)cbData >> 1) - 1] )
  {
    v6 = STRU::Resize(a2, (_DWORD)cbData + 2);
    if ( v6 < 0 )
      goto LABEL_19;
    v10 = STRU::QueryStr(a2);
    v10[((unsigned __int64)(unsigned int)cbData >> 1) - 1] = 0;
  }
  STRU::SyncWithBuffer(a2);
  v11 = STRU::QueryStr(a2);
  if ( v11[STRU::QueryCCH(a2) - 1] != 92 )
  {
    v5 = STRU::Append(a2, L"\\");
LABEL_18:
    v6 = v5;
  }
LABEL_19:
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18000453c  mov     [rsp-28h+cbData], rcx
0x180004541  push    rbp
0x180004542  push    rbx
0x180004543  push    rsi
0x180004544  push    rdi
0x180004545  push    r14
0x180004547  mov     rbp, rsp
0x18000454a  sub     rsp, 30h
0x18000454e  xor     r14d, r14d
0x180004551  mov     rcx, rdx
0x180004554  mov     [rbp+hKey], r14
0x180004558  mov     rsi, rdx
0x18000455b  call    cs:__imp_?QueryBuffer@STRU@@QEAAPEAVBUFFER@@XZ; STRU::QueryBuffer(void)
0x180004562  nop     dword ptr [rax+rax+00h]
0x180004567  mov     rcx, rax
0x18000456a  call    cs:__imp_?QuerySize@BUFFER@@QEBAKXZ; BUFFER::QuerySize(void)
0x180004571  nop     dword ptr [rax+rax+00h]
0x180004576  mov     r9d, 20019h; samDesired
0x18000457c  mov     [rbp+Type], r14d
0x180004580  mov     dword ptr [rbp+cbData], eax
0x180004583  lea     rdx, SubKey; "Software\\Microsoft\\.NETFramework"
0x18000458a  lea     rax, [rbp+hKey]
0x18000458e  xor     r8d, r8d; ulOptions
0x180004591  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180004598  mov     [rsp+30h+phkResult], rax; phkResult
0x18000459d  call    cs:__imp_RegOpenKeyExW
0x1800045a4  nop     dword ptr [rax+rax+00h]
0x1800045a9  mov     edi, eax
0x1800045ab  test    eax, eax
0x1800045ad  jz      short loc_1800045C3
0x1800045af  jle     loc_18000472B
0x1800045b5  movzx   edi, ax
0x1800045b8  or      edi, 80070000h
0x1800045be  jmp     loc_18000472B
0x1800045c3  mov     rcx, rsi
0x1800045c6  mov     edi, r14d
0x1800045c9  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x1800045d0  nop     dword ptr [rax+rax+00h]
0x1800045d5  lea     rcx, [rbp+cbData]
0x1800045d9  xor     r8d, r8d; lpReserved
0x1800045dc  mov     [rsp+30h+lpcbData], rcx; lpcbData
0x1800045e1  lea     r9, [rbp+Type]; lpType
0x1800045e5  mov     rcx, [rbp+hKey]; hKey
0x1800045e9  lea     rdx, ValueName; "InstallRoot"
0x1800045f0  mov     [rsp+30h+phkResult], rax; lpData
0x1800045f5  call    cs:__imp_RegQueryValueExW
0x1800045fc  nop     dword ptr [rax+rax+00h]
0x180004601  cmp     eax, 0EAh
0x180004606  jnz     short loc_18000465F
0x180004608  mov     edx, dword ptr [rbp+cbData]
0x18000460b  mov     rcx, rsi
0x18000460e  call    cs:__imp_?Resize@STRU@@QEAAJK@Z; STRU::Resize(ulong)
0x180004615  nop     dword ptr [rax+rax+00h]
0x18000461a  mov     edi, eax
0x18000461c  test    eax, eax
0x18000461e  js      loc_18000472B
0x180004624  mov     rcx, rsi
0x180004627  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000462e  nop     dword ptr [rax+rax+00h]
0x180004633  lea     rcx, [rbp+cbData]
0x180004637  xor     r8d, r8d; lpReserved
0x18000463a  mov     [rsp+30h+lpcbData], rcx; lpcbData
0x18000463f  lea     r9, [rbp+Type]; lpType
0x180004643  mov     rcx, [rbp+hKey]; hKey
0x180004647  lea     rdx, ValueName; "InstallRoot"
0x18000464e  mov     [rsp+30h+phkResult], rax; lpData
0x180004653  call    cs:__imp_RegQueryValueExW
0x18000465a  nop     dword ptr [rax+rax+00h]
0x18000465f  test    eax, eax
0x180004661  jz      short loc_18000466E
0x180004663  jle     loc_180004729
0x180004669  jmp     loc_1800045B5
0x18000466e  mov     eax, [rbp+Type]
0x180004671  dec     eax
0x180004673  cmp     eax, 1
0x180004676  jbe     short loc_180004682
0x180004678  mov     edi, 8007000Dh
0x18000467d  jmp     loc_18000472B
0x180004682  cmp     dword ptr [rbp+cbData], 2
0x180004686  jb      short loc_180004678
0x180004688  mov     rcx, rsi
0x18000468b  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180004692  nop     dword ptr [rax+rax+00h]
0x180004697  mov     edx, dword ptr [rbp+cbData]
0x18000469a  mov     ecx, edx
0x18000469c  shr     rcx, 1
0x18000469f  cmp     [rax+rcx*2-2], r14w
0x1800046a5  jz      short loc_1800046DA
0x1800046a7  add     edx, 2
0x1800046aa  mov     rcx, rsi
0x1800046ad  call    cs:__imp_?Resize@STRU@@QEAAJK@Z; STRU::Resize(ulong)
0x1800046b4  nop     dword ptr [rax+rax+00h]
0x1800046b9  mov     edi, eax
0x1800046bb  test    eax, eax
0x1800046bd  js      short loc_18000472B
0x1800046bf  mov     rcx, rsi
0x1800046c2  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x1800046c9  nop     dword ptr [rax+rax+00h]
0x1800046ce  mov     edx, dword ptr [rbp+cbData]
0x1800046d1  shr     rdx, 1
0x1800046d4  mov     [rax+rdx*2-2], r14w
0x1800046da  mov     rcx, rsi
0x1800046dd  call    cs:__imp_?SyncWithBuffer@STRU@@QEAAXXZ; STRU::SyncWithBuffer(void)
0x1800046e4  nop     dword ptr [rax+rax+00h]
0x1800046e9  mov     rcx, rsi
0x1800046ec  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x1800046f3  nop     dword ptr [rax+rax+00h]
0x1800046f8  mov     rcx, rsi
0x1800046fb  mov     rbx, rax
0x1800046fe  call    cs:__imp_?QueryCCH@STRU@@QEBAKXZ; STRU::QueryCCH(void)
0x180004705  nop     dword ptr [rax+rax+00h]
0x18000470a  dec     eax
0x18000470c  cmp     word ptr [rbx+rax*2], 5Ch ; '\'
0x180004711  jz      short loc_18000472B
0x180004713  lea     rdx, asc_18000FCB8; "\\"
0x18000471a  mov     rcx, rsi
0x18000471d  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180004724  nop     dword ptr [rax+rax+00h]
0x180004729  mov     edi, eax
0x18000472b  mov     rcx, [rbp+hKey]; hKey
0x18000472f  test    rcx, rcx
0x180004732  jz      short loc_180004740
0x180004734  call    cs:__imp_RegCloseKey
0x18000473b  nop     dword ptr [rax+rax+00h]
0x180004740  mov     eax, edi
0x180004742  add     rsp, 30h
0x180004746  pop     r14
0x180004748  pop     rdi
0x180004749  pop     rsi
0x18000474a  pop     rbx
0x18000474b  pop     rbp
0x18000474c  retn
```
