# UbpmpSetConsumerDisabledForUser(ushort const *,void *,uchar)

- ea: `0x180033340`
- end: `0x180033429`
- name: `?UbpmpSetConsumerDisabledForUser@@YAKPEBGPEAXE@Z`
- size: `233`
- prototype: `unsigned int __fastcall(const unsigned __int16 *, void *, unsigned __int8)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180033280`

## callees

- `0x180005a60`
- `0x18000fbf0`
- `0x180033340`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800333b1`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800333b1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003340a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003340a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800333f4`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800333f4`

## pseudocode

```c
__int64 __fastcall UbpmpSetConsumerDisabledForUser(const unsigned __int16 *a1, void *a2, char a3)
{
  __int64 v4; // rdx
  __int64 v5; // r8
  __int64 v6; // r9
  HKEY hKey; // [rsp+50h] [rbp-18h] BYREF
  LPCWSTR lpSubKey; // [rsp+58h] [rbp-10h] BYREF
  BOOL Data; // [rsp+88h] [rbp+20h] BYREF

  hKey = 0;
  lpSubKey = 0;
  Data = 0;
  if ( !(unsigned int)UbpmpGetConsumerUserPropertiesKeyName(a1, a2, (unsigned __int16 **)&lpSubKey)
    && !RegCreateKeyExW(HKEY_USERS, lpSubKey, 0, 0, 0, 0x20006u, 0, &hKey, 0) )
  {
    Data = a3 != 0;
    RegSetValueExW(hKey, L"Disabled", 0, 4u, (const BYTE *)&Data, 4u);
  }
  if ( hKey )
    RegCloseKey(hKey);
  UBPM_MIDL_user_free(lpSubKey, v4, v5, v6);
  return 0;
}

```

## disassembly

```asm
0x180033340  mov     rax, rsp
0x180033343  push    rbx
0x180033344  sub     rsp, 60h
0x180033348  mov     bl, r8b
0x18003334b  mov     qword ptr [rax-18h], 0
0x180033353  lea     r8, [rax-10h]; unsigned __int16 **
0x180033357  mov     qword ptr [rax-10h], 0
0x18003335f  mov     dword ptr [rax+20h], 0
0x180033366  call    ?UbpmpGetConsumerUserPropertiesKeyName@@YAKPEBGPEAXPEAPEAG@Z; UbpmpGetConsumerUserPropertiesKeyName(ushort const *,void *,ushort * *)
0x18003336b  test    eax, eax
0x18003336d  jnz     loc_180033400
0x180033373  mov     rdx, [rsp+68h+lpSubKey]; lpSubKey
0x180033378  lea     rax, [rsp+68h+hKey]
0x18003337d  mov     [rsp+68h+lpdwDisposition], 0; lpdwDisposition
0x180033386  xor     r9d, r9d; lpClass
0x180033389  mov     [rsp+68h+phkResult], rax; phkResult
0x18003338e  xor     r8d, r8d; Reserved
0x180033391  mov     [rsp+68h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18003339a  mov     rcx, 0FFFFFFFF80000003h; hKey
0x1800333a1  mov     [rsp+68h+samDesired], 20006h; samDesired
0x1800333a9  mov     [rsp+68h+dwOptions], 0; dwOptions
0x1800333b1  call    cs:__imp_RegCreateKeyExW
0x1800333b8  nop     dword ptr [rax+rax+00h]
0x1800333bd  test    eax, eax
0x1800333bf  jnz     short loc_180033400
0x1800333c1  mov     rcx, [rsp+68h+hKey]; hKey
0x1800333c6  lea     rdx, ValueName; "Disabled"
0x1800333cd  test    bl, bl
0x1800333cf  mov     r9d, 4; dwType
0x1800333d5  mov     [rsp+68h+samDesired], r9d; cbData
0x1800333da  setnz   al
0x1800333dd  xor     r8d, r8d; Reserved
0x1800333e0  mov     [rsp+68h+Data], eax
0x1800333e7  lea     rax, [rsp+68h+Data]
0x1800333ef  mov     qword ptr [rsp+68h+dwOptions], rax; lpData
0x1800333f4  call    cs:__imp_RegSetValueExW
0x1800333fb  nop     dword ptr [rax+rax+00h]
0x180033400  mov     rcx, [rsp+68h+hKey]; hKey
0x180033405  test    rcx, rcx
0x180033408  jz      short loc_180033416
0x18003340a  call    cs:__imp_RegCloseKey
0x180033411  nop     dword ptr [rax+rax+00h]
0x180033416  mov     rcx, [rsp+68h+lpSubKey]
0x18003341b  call    UBPM_MIDL_user_free
0x180033420  xor     eax, eax
0x180033422  add     rsp, 60h
0x180033426  pop     rbx
0x180033427  retn
```
