# UmpoInternalCreatePossibleSetting

- ea: `0x1800128e4`
- end: `0x180012a75`
- name: `UmpoInternalCreatePossibleSetting`
- size: `401`
- prototype: `__int64 __fastcall(__int64, UUID *, UUID *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180014770`

## callees

- `0x180005480`
- `0x180010070`
- `0x1800128e4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__ultow_s` at `0x1800129c2`
- `api-ms-win-crt-private-l1-1-0!_o__ultow_s` at `0x1800129c2`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800129fd`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800129fd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012a1a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012a32`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012a4a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012a1a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012a32`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012a4a`
- `RPCRT4!UuidEqual` at `0x180012954`
- `RPCRT4!UuidEqual` at `0x180012954`

## pseudocode

```c
__int64 __fastcall UmpoInternalCreatePossibleSetting(__int64 a1, UUID *a2, UUID *a3, unsigned int a4)
{
  HKEY v4; // rcx
  HKEY v8; // rbx
  unsigned int v9; // ebx
  HKEY v11; // [rsp+50h] [rbp-9h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-1h] BYREF
  RPC_STATUS Status; // [rsp+60h] [rbp+7h] BYREF
  HKEY phkResult; // [rsp+68h] [rbp+Fh] BYREF
  WCHAR SubKey[12]; // [rsp+70h] [rbp+17h] BYREF

  Status = 0;
  hKey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  v4 = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  v11 = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  phkResult = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  if ( a3 && a2 )
  {
    v8 = UmpoSystemPowerRootKey;
    if ( !UuidEqual(a2, (UUID *)&NO_SUBGROUP_GUID, &Status) )
    {
      v9 = UmpoInternalOpenGUIDSubKey(v8, a2, &v11, 0x20006u, 0, 0);
      if ( v9 )
      {
LABEL_8:
        v4 = v11;
        goto LABEL_10;
      }
      v8 = v11;
    }
    v9 = UmpoInternalOpenGUIDSubKey(v8, a3, &hKey, 0x20006u, 0, 0);
    if ( !v9 )
    {
      _o__ultow_s(a4, SubKey, 11, 10);
      v9 = RegCreateKeyExW(hKey, SubKey, 0, 0, 0, 0x20006u, 0, &phkResult, 0);
    }
    goto LABEL_8;
  }
  v9 = 87;
LABEL_10:
  if ( (unsigned __int64)v4 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    RegCloseKey(v4);
    v11 = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  }
  if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    RegCloseKey(hKey);
    hKey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  }
  if ( (unsigned __int64)phkResult - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    RegCloseKey(phkResult);
  return v9;
}

```

## disassembly

```asm
0x1800128e4  mov     [rsp-8+arg_0], rbx
0x1800128e9  push    rbp
0x1800128ea  push    rsi
0x1800128eb  push    rdi
0x1800128ec  push    r12
0x1800128ee  push    r14
0x1800128f0  lea     rbp, [rsp-37h]
0x1800128f5  sub     rsp, 90h
0x1800128fc  mov     rax, cs:__security_cookie
0x180012903  xor     rax, rsp
0x180012906  mov     [rbp+57h+var_28], rax
0x18001290a  or      r12, 0FFFFFFFFFFFFFFFFh
0x18001290e  mov     [rbp+57h+Status], 0
0x180012915  mov     [rbp+57h+hKey], r12
0x180012919  mov     rcx, r12; hKey
0x18001291c  mov     [rbp+57h+var_60], rcx
0x180012920  mov     r14d, r9d
0x180012923  mov     [rbp+57h+var_48], r12
0x180012927  mov     rsi, r8
0x18001292a  mov     rdi, rdx
0x18001292d  test    r8, r8
0x180012930  jz      loc_180012A0B
0x180012936  test    rdx, rdx
0x180012939  jz      loc_180012A0B
0x18001293f  mov     rbx, cs:UmpoSystemPowerRootKey
0x180012946  lea     r8, [rbp+57h+Status]; Status
0x18001294a  lea     rdx, NO_SUBGROUP_GUID; Uuid2
0x180012951  mov     rcx, rdi; Uuid1
0x180012954  call    cs:__imp_UuidEqual
0x18001295a  test    eax, eax
0x18001295c  jnz     short loc_18001298A
0x18001295e  mov     qword ptr [rsp+0B0h+samDesired], 0; __int64
0x180012967  lea     r8, [rbp+57h+var_60]; phkResult
0x18001296b  mov     r9d, 20006h; samDesired
0x180012971  mov     byte ptr [rsp+0B0h+dwOptions], al; char
0x180012975  mov     rdx, rdi; Uuid2
0x180012978  mov     rcx, rbx; hKey
0x18001297b  call    UmpoInternalOpenGUIDSubKey
0x180012980  mov     ebx, eax
0x180012982  test    eax, eax
0x180012984  jnz     short loc_180012A05
0x180012986  mov     rbx, [rbp+57h+var_60]
0x18001298a  mov     qword ptr [rsp+0B0h+samDesired], 0; __int64
0x180012993  lea     r8, [rbp+57h+hKey]; phkResult
0x180012997  mov     r9d, 20006h; samDesired
0x18001299d  mov     byte ptr [rsp+0B0h+dwOptions], 0; char
0x1800129a2  mov     rdx, rsi; Uuid2
0x1800129a5  mov     rcx, rbx; hKey
0x1800129a8  call    UmpoInternalOpenGUIDSubKey
0x1800129ad  mov     ebx, eax
0x1800129af  test    eax, eax
0x1800129b1  jnz     short loc_180012A05
0x1800129b3  lea     r9d, [rax+0Ah]
0x1800129b7  mov     ecx, r14d
0x1800129ba  lea     r8d, [rax+0Bh]
0x1800129be  lea     rdx, [rbp+57h+SubKey]
0x1800129c2  call    cs:__imp__o__ultow_s
0x1800129c8  mov     rcx, [rbp+57h+hKey]; hKey
0x1800129cc  lea     rax, [rbp+57h+var_48]
0x1800129d0  mov     [rsp+0B0h+lpdwDisposition], 0; lpdwDisposition
0x1800129d9  lea     rdx, [rbp+57h+SubKey]; lpSubKey
0x1800129dd  mov     [rsp+0B0h+phkResult], rax; phkResult
0x1800129e2  xor     r9d, r9d; lpClass
0x1800129e5  mov     [rsp+0B0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800129ee  xor     r8d, r8d; Reserved
0x1800129f1  mov     [rsp+0B0h+samDesired], 20006h; samDesired
0x1800129f9  mov     [rsp+0B0h+dwOptions], ebx; dwOptions
0x1800129fd  call    cs:__imp_RegCreateKeyExW
0x180012a03  mov     ebx, eax
0x180012a05  mov     rcx, [rbp+57h+var_60]
0x180012a09  jmp     short loc_180012A10
0x180012a0b  mov     ebx, 57h ; 'W'
0x180012a10  lea     rax, [rcx-1]
0x180012a14  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180012a18  ja      short loc_180012A24
0x180012a1a  call    cs:__imp_RegCloseKey
0x180012a20  mov     [rbp+57h+var_60], r12
0x180012a24  mov     rcx, [rbp+57h+hKey]; hKey
0x180012a28  lea     rax, [rcx-1]
0x180012a2c  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180012a30  ja      short loc_180012A3C
0x180012a32  call    cs:__imp_RegCloseKey
0x180012a38  mov     [rbp+57h+hKey], r12
0x180012a3c  mov     rcx, [rbp+57h+var_48]; hKey
0x180012a40  lea     rax, [rcx-1]
0x180012a44  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180012a48  ja      short loc_180012A50
0x180012a4a  call    cs:__imp_RegCloseKey
0x180012a50  mov     eax, ebx
0x180012a52  mov     rcx, [rbp+57h+var_28]
0x180012a56  xor     rcx, rsp; StackCookie
0x180012a59  call    __security_check_cookie
0x180012a5e  mov     rbx, [rsp+0B0h+arg_0]
0x180012a66  add     rsp, 90h
0x180012a6d  pop     r14
0x180012a6f  pop     r12
0x180012a71  pop     rdi
0x180012a72  pop     rsi
0x180012a73  pop     rbp
0x180012a74  retn
```
