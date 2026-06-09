# W3WP_HOST::GetFrameworkInstallationPath(STRU *)

- ea: `0x1800041ec`
- end: `0x18000439a`
- name: `?GetFrameworkInstallationPath@W3WP_HOST@@AEAAJPEAVSTRU@@@Z`
- size: `430`
- prototype: `__int64 __fastcall(W3WP_HOST *__hidden this, struct STRU *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180005d44`

## callees

- `0x1800041ec`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004387`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004387`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180004241`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180004241`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000428d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800042d9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000428d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800042d9`
- `iisutil!?Resize@STRU@@QEAAJK@Z` at `0x1800042a0`
- `iisutil!?Resize@STRU@@QEAAJK@Z` at `0x180004324`
- `iisutil!?Resize@STRU@@QEAAJK@Z` at `0x1800042a0`
- `iisutil!?Resize@STRU@@QEAAJK@Z` at `0x180004324`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x180004214`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x180004214`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180004267`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800042b3`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180004308`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180004333`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180004351`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180004267`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800042b3`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180004308`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180004333`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180004351`
- `iisutil!?SyncWithBuffer@STRU@@QEAAXXZ` at `0x180004348`
- `iisutil!?SyncWithBuffer@STRU@@QEAAXXZ` at `0x180004348`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180004376`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180004376`
- `iisutil!?QueryBuffer@STRU@@QEAAPEAVBUFFER@@XZ` at `0x18000420b`
- `iisutil!?QueryBuffer@STRU@@QEAAPEAVBUFFER@@XZ` at `0x18000420b`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x18000435d`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x18000435d`

## string_xrefs

- `0x180004281`: `InstallRoot`
- `0x1800042cd`: `InstallRoot`

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
0x1800041ec  mov     [rsp-28h+cbData], rcx
0x1800041f1  push    rbp
0x1800041f2  push    rbx
0x1800041f3  push    rsi
0x1800041f4  push    rdi
0x1800041f5  push    r14
0x1800041f7  mov     rbp, rsp
0x1800041fa  sub     rsp, 30h
0x1800041fe  xor     r14d, r14d
0x180004201  mov     rcx, rdx
0x180004204  mov     [rbp+hKey], r14
0x180004208  mov     rsi, rdx
0x18000420b  call    cs:__imp_?QueryBuffer@STRU@@QEAAPEAVBUFFER@@XZ; STRU::QueryBuffer(void)
0x180004211  mov     rcx, rax
0x180004214  call    cs:__imp_?QuerySize@BUFFER@@QEBAKXZ; BUFFER::QuerySize(void)
0x18000421a  mov     r9d, 20019h; samDesired
0x180004220  mov     [rbp+Type], r14d
0x180004224  mov     dword ptr [rbp+cbData], eax
0x180004227  lea     rdx, SubKey; "Software\\Microsoft\\.NETFramework"
0x18000422e  lea     rax, [rbp+hKey]
0x180004232  xor     r8d, r8d; ulOptions
0x180004235  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000423c  mov     [rsp+30h+phkResult], rax; phkResult
0x180004241  call    cs:__imp_RegOpenKeyExW
0x180004247  mov     edi, eax
0x180004249  test    eax, eax
0x18000424b  jz      short loc_180004261
0x18000424d  jle     loc_18000437E
0x180004253  movzx   edi, ax
0x180004256  or      edi, 80070000h
0x18000425c  jmp     loc_18000437E
0x180004261  mov     rcx, rsi
0x180004264  mov     edi, r14d
0x180004267  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000426d  lea     rcx, [rbp+cbData]
0x180004271  xor     r8d, r8d; lpReserved
0x180004274  mov     [rsp+30h+lpcbData], rcx; lpcbData
0x180004279  lea     r9, [rbp+Type]; lpType
0x18000427d  mov     rcx, [rbp+hKey]; hKey
0x180004281  lea     rdx, ValueName; "InstallRoot"
0x180004288  mov     [rsp+30h+phkResult], rax; lpData
0x18000428d  call    cs:__imp_RegQueryValueExW
0x180004293  cmp     eax, 0EAh
0x180004298  jnz     short loc_1800042DF
0x18000429a  mov     edx, dword ptr [rbp+cbData]
0x18000429d  mov     rcx, rsi
0x1800042a0  call    cs:__imp_?Resize@STRU@@QEAAJK@Z; STRU::Resize(ulong)
0x1800042a6  mov     edi, eax
0x1800042a8  test    eax, eax
0x1800042aa  js      loc_18000437E
0x1800042b0  mov     rcx, rsi
0x1800042b3  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x1800042b9  lea     rcx, [rbp+cbData]
0x1800042bd  xor     r8d, r8d; lpReserved
0x1800042c0  mov     [rsp+30h+lpcbData], rcx; lpcbData
0x1800042c5  lea     r9, [rbp+Type]; lpType
0x1800042c9  mov     rcx, [rbp+hKey]; hKey
0x1800042cd  lea     rdx, ValueName; "InstallRoot"
0x1800042d4  mov     [rsp+30h+phkResult], rax; lpData
0x1800042d9  call    cs:__imp_RegQueryValueExW
0x1800042df  test    eax, eax
0x1800042e1  jz      short loc_1800042EE
0x1800042e3  jle     loc_18000437C
0x1800042e9  jmp     loc_180004253
0x1800042ee  mov     eax, [rbp+Type]
0x1800042f1  dec     eax
0x1800042f3  cmp     eax, 1
0x1800042f6  jbe     short loc_1800042FF
0x1800042f8  mov     edi, 8007000Dh
0x1800042fd  jmp     short loc_18000437E
0x1800042ff  cmp     dword ptr [rbp+cbData], 2
0x180004303  jb      short loc_1800042F8
0x180004305  mov     rcx, rsi
0x180004308  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000430e  mov     edx, dword ptr [rbp+cbData]
0x180004311  mov     ecx, edx
0x180004313  shr     rcx, 1
0x180004316  cmp     [rax+rcx*2-2], r14w
0x18000431c  jz      short loc_180004345
0x18000431e  add     edx, 2
0x180004321  mov     rcx, rsi
0x180004324  call    cs:__imp_?Resize@STRU@@QEAAJK@Z; STRU::Resize(ulong)
0x18000432a  mov     edi, eax
0x18000432c  test    eax, eax
0x18000432e  js      short loc_18000437E
0x180004330  mov     rcx, rsi
0x180004333  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180004339  mov     edx, dword ptr [rbp+cbData]
0x18000433c  shr     rdx, 1
0x18000433f  mov     [rax+rdx*2-2], r14w
0x180004345  mov     rcx, rsi
0x180004348  call    cs:__imp_?SyncWithBuffer@STRU@@QEAAXXZ; STRU::SyncWithBuffer(void)
0x18000434e  mov     rcx, rsi
0x180004351  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180004357  mov     rcx, rsi
0x18000435a  mov     rbx, rax
0x18000435d  call    cs:__imp_?QueryCCH@STRU@@QEBAKXZ; STRU::QueryCCH(void)
0x180004363  dec     eax
0x180004365  cmp     word ptr [rbx+rax*2], 5Ch ; '\'
0x18000436a  jz      short loc_18000437E
0x18000436c  lea     rdx, asc_18000ECA8; "\\"
0x180004373  mov     rcx, rsi
0x180004376  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18000437c  mov     edi, eax
0x18000437e  mov     rcx, [rbp+hKey]; hKey
0x180004382  test    rcx, rcx
0x180004385  jz      short loc_18000438D
0x180004387  call    cs:__imp_RegCloseKey
0x18000438d  mov     eax, edi
0x18000438f  add     rsp, 30h
0x180004393  pop     r14
0x180004395  pop     rdi
0x180004396  pop     rsi
0x180004397  pop     rbx
0x180004398  pop     rbp
0x180004399  retn
```
