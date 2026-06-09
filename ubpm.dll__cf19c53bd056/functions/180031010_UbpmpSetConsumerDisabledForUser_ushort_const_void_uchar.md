# UbpmpSetConsumerDisabledForUser(ushort const *,void *,uchar)

- ea: `0x180031010`
- end: `0x1800310e6`
- name: `?UbpmpSetConsumerDisabledForUser@@YAKPEBGPEAXE@Z`
- size: `214`
- prototype: `__int64 __fastcall(const unsigned __int16 *, void *, char)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180030f60`

## callees

- `0x1800051b0`
- `0x180019d90`
- `0x180031010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180031081`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180031081`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800310ce`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800310ce`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800310be`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800310be`

## pseudocode

```c
__int64 __fastcall UbpmpSetConsumerDisabledForUser(const unsigned __int16 *a1, void *a2, char a3)
{
  HKEY hKey; // [rsp+50h] [rbp-18h] BYREF
  LPCWSTR lpSubKey; // [rsp+58h] [rbp-10h] BYREF
  BOOL Data; // [rsp+88h] [rbp+20h] BYREF

  hKey = 0;
  lpSubKey = 0;
  Data = 0;
  if ( !UbpmpGetConsumerUserPropertiesKeyName(a1, a2, (unsigned __int16 **)&lpSubKey)
    && !RegCreateKeyExW(HKEY_USERS, lpSubKey, 0, 0, 0, 0x20006u, 0, &hKey, 0) )
  {
    Data = a3 != 0;
    RegSetValueExW(hKey, L"Disabled", 0, 4u, (const BYTE *)&Data, 4u);
  }
  if ( hKey )
    RegCloseKey(hKey);
  UBPM_MIDL_user_free(lpSubKey);
  return 0;
}

```

## disassembly

```asm
0x180031010  mov     rax, rsp
0x180031013  push    rbx
0x180031014  sub     rsp, 60h
0x180031018  mov     bl, r8b
0x18003101b  mov     qword ptr [rax-18h], 0
0x180031023  lea     r8, [rax-10h]; unsigned __int16 **
0x180031027  mov     qword ptr [rax-10h], 0
0x18003102f  mov     dword ptr [rax+20h], 0
0x180031036  call    ?UbpmpGetConsumerUserPropertiesKeyName@@YAKPEBGPEAXPEAPEAG@Z; UbpmpGetConsumerUserPropertiesKeyName(ushort const *,void *,ushort * *)
0x18003103b  test    eax, eax
0x18003103d  jnz     loc_1800310C4
0x180031043  mov     rdx, [rsp+68h+lpSubKey]; lpSubKey
0x180031048  lea     rax, [rsp+68h+hKey]
0x18003104d  mov     [rsp+68h+lpdwDisposition], 0; lpdwDisposition
0x180031056  xor     r9d, r9d; lpClass
0x180031059  mov     [rsp+68h+phkResult], rax; phkResult
0x18003105e  xor     r8d, r8d; Reserved
0x180031061  mov     [rsp+68h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18003106a  mov     rcx, 0FFFFFFFF80000003h; hKey
0x180031071  mov     [rsp+68h+samDesired], 20006h; samDesired
0x180031079  mov     [rsp+68h+dwOptions], 0; dwOptions
0x180031081  call    cs:__imp_RegCreateKeyExW
0x180031087  test    eax, eax
0x180031089  jnz     short loc_1800310C4
0x18003108b  mov     rcx, [rsp+68h+hKey]; hKey
0x180031090  lea     rdx, ValueName; "Disabled"
0x180031097  test    bl, bl
0x180031099  mov     r9d, 4; dwType
0x18003109f  mov     [rsp+68h+samDesired], r9d; cbData
0x1800310a4  setnz   al
0x1800310a7  xor     r8d, r8d; Reserved
0x1800310aa  mov     [rsp+68h+Data], eax
0x1800310b1  lea     rax, [rsp+68h+Data]
0x1800310b9  mov     qword ptr [rsp+68h+dwOptions], rax; lpData
0x1800310be  call    cs:__imp_RegSetValueExW
0x1800310c4  mov     rcx, [rsp+68h+hKey]; hKey
0x1800310c9  test    rcx, rcx
0x1800310cc  jz      short loc_1800310D4
0x1800310ce  call    cs:__imp_RegCloseKey
0x1800310d4  mov     rcx, [rsp+68h+lpSubKey]
0x1800310d9  call    UBPM_MIDL_user_free
0x1800310de  xor     eax, eax
0x1800310e0  add     rsp, 60h
0x1800310e4  pop     rbx
0x1800310e5  retn
```
