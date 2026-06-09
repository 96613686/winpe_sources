# UmpoInternalCreateSetting

- ea: `0x180012a7c`
- end: `0x180012ba2`
- name: `UmpoInternalCreateSetting`
- size: `294`
- prototype: `__int64 __fastcall(__int64, UUID *, UUID *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180014790`

## callees

- `0x180005480`
- `0x180012a7c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012b72`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012b8c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012b72`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012b8c`
- `RPCRT4!UuidEqual` at `0x180012acf`
- `RPCRT4!UuidEqual` at `0x180012acf`

## pseudocode

```c
__int64 __fastcall UmpoInternalCreateSetting(__int64 a1, UUID *a2, UUID *a3)
{
  HKEY v5; // rdi
  unsigned int v6; // ebx
  RPC_STATUS v8; // [rsp+50h] [rbp+8h] BYREF
  int v9; // [rsp+54h] [rbp+Ch]
  HKEY hKey; // [rsp+60h] [rbp+18h] BYREF
  HKEY phkResult; // [rsp+68h] [rbp+20h] BYREF

  v9 = HIDWORD(a1);
  v8 = 0;
  phkResult = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  hKey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  if ( a3 && a2 )
  {
    v5 = UmpoSystemPowerRootKey;
    if ( !UuidEqual(a2, (UUID *)&NO_SUBGROUP_GUID, &v8) )
    {
      v6 = UmpoInternalOpenGUIDSubKey(v5, a2, &hKey, 0x20006u, 0, 0);
      if ( v6 )
        goto LABEL_10;
      v5 = hKey;
    }
    if ( (unsigned int)UmpoInternalOpenGUIDSubKey(v5, a3, &phkResult, 0x20019u, 1, 0) )
      v6 = UmpoInternalOpenGUIDSubKey(v5, a3, &phkResult, 0x20006u, 0, 0);
    else
      v6 = 183;
  }
  else
  {
    v6 = 87;
  }
LABEL_10:
  if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    RegCloseKey(hKey);
    hKey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  }
  if ( (unsigned __int64)phkResult - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    RegCloseKey(phkResult);
  return v6;
}

```

## disassembly

```asm
0x180012a7c  mov     rax, rsp
0x180012a7f  mov     [rax+10h], rbx
0x180012a83  mov     [rax+8], rcx
0x180012a87  push    rsi
0x180012a88  push    rdi
0x180012a89  push    r14
0x180012a8b  sub     rsp, 30h
0x180012a8f  or      r14, 0FFFFFFFFFFFFFFFFh
0x180012a93  mov     dword ptr [rax+8], 0
0x180012a9a  mov     [rax+20h], r14
0x180012a9e  mov     rsi, r8
0x180012aa1  mov     [rax+18h], r14
0x180012aa5  mov     rbx, rdx
0x180012aa8  test    r8, r8
0x180012aab  jz      loc_180012B5E
0x180012ab1  test    rdx, rdx
0x180012ab4  jz      loc_180012B5E
0x180012aba  mov     rdi, cs:UmpoSystemPowerRootKey
0x180012ac1  lea     r8, [rax+8]; Status
0x180012ac5  lea     rdx, NO_SUBGROUP_GUID; Uuid2
0x180012acc  mov     rcx, rbx; Uuid1
0x180012acf  call    cs:__imp_UuidEqual
0x180012ad5  test    eax, eax
0x180012ad7  jnz     short loc_180012B07
0x180012ad9  mov     [rsp+48h+var_20], 0; __int64
0x180012ae2  lea     r8, [rsp+48h+hKey]; phkResult
0x180012ae7  mov     r9d, 20006h; samDesired
0x180012aed  mov     [rsp+48h+var_28], al; char
0x180012af1  mov     rdx, rbx; Uuid2
0x180012af4  mov     rcx, rdi; hKey
0x180012af7  call    UmpoInternalOpenGUIDSubKey
0x180012afc  mov     ebx, eax
0x180012afe  test    eax, eax
0x180012b00  jnz     short loc_180012B63
0x180012b02  mov     rdi, [rsp+48h+hKey]
0x180012b07  mov     [rsp+48h+var_20], 0; __int64
0x180012b10  lea     r8, [rsp+48h+phkResult]; phkResult
0x180012b15  mov     r9d, 20019h; samDesired
0x180012b1b  mov     [rsp+48h+var_28], 1; char
0x180012b20  mov     rdx, rsi; Uuid2
0x180012b23  mov     rcx, rdi; hKey
0x180012b26  call    UmpoInternalOpenGUIDSubKey
0x180012b2b  test    eax, eax
0x180012b2d  jnz     short loc_180012B36
0x180012b2f  mov     ebx, 0B7h
0x180012b34  jmp     short loc_180012B63
0x180012b36  mov     [rsp+48h+var_20], 0; __int64
0x180012b3f  lea     r8, [rsp+48h+phkResult]; phkResult
0x180012b44  mov     r9d, 20006h; samDesired
0x180012b4a  mov     [rsp+48h+var_28], 0; char
0x180012b4f  mov     rdx, rsi; Uuid2
0x180012b52  mov     rcx, rdi; hKey
0x180012b55  call    UmpoInternalOpenGUIDSubKey
0x180012b5a  mov     ebx, eax
0x180012b5c  jmp     short loc_180012B63
0x180012b5e  mov     ebx, 57h ; 'W'
0x180012b63  mov     rcx, [rsp+48h+hKey]; hKey
0x180012b68  lea     rax, [rcx-1]
0x180012b6c  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180012b70  ja      short loc_180012B7D
0x180012b72  call    cs:__imp_RegCloseKey
0x180012b78  mov     [rsp+48h+hKey], r14
0x180012b7d  mov     rcx, [rsp+48h+phkResult]; hKey
0x180012b82  lea     rax, [rcx-1]
0x180012b86  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180012b8a  ja      short loc_180012B92
0x180012b8c  call    cs:__imp_RegCloseKey
0x180012b92  mov     eax, ebx
0x180012b94  mov     rbx, [rsp+48h+arg_8]
0x180012b99  add     rsp, 30h
0x180012b9d  pop     r14
0x180012b9f  pop     rdi
0x180012ba0  pop     rsi
0x180012ba1  retn
```
