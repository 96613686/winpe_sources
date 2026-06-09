# TAllocNewID

- ea: `0x18001c990`
- end: `0x18001cafc`
- name: `TAllocNewID`
- size: `364`
- prototype: `_DWORD *__fastcall(__int64, __int64, __int64, __int64, _DWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180028100`

## callees

- `0x18001c990`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001cad0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001cada`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001cad0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001cada`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001ca13`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001ca55`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001ca13`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001ca55`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001cac6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001cac6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001ca92`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001ca92`

## pseudocode

```c
_DWORD *__fastcall TAllocNewID(__int64 a1, __int64 a2, __int64 a3, __int64 a4, _DWORD *a5)
{
  BYTE *v6; // rbx
  LSTATUS v7; // edi
  _DWORD *result; // rax
  DWORD cbData; // [rsp+50h] [rbp-20h] BYREF
  BYTE Data[4]; // [rsp+54h] [rbp-1Ch] BYREF
  DWORD Type; // [rsp+58h] [rbp-18h] BYREF
  HKEY phkResult; // [rsp+60h] [rbp-10h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-8h] BYREF
  DWORD dwDisposition; // [rsp+88h] [rbp+18h] BYREF

  phkResult = 0;
  hKey = 0;
  Type = 0;
  *(_DWORD *)Data = 0;
  dwDisposition = 0;
  RegCreateKeyExW(
    HKEY_LOCAL_MACHINE,
    L"Software\\Microsoft\\Windows\\CurrentVersion\\Telephony",
    0,
    (LPWSTR)&Format,
    0,
    0xF003Fu,
    0,
    &hKey,
    &dwDisposition);
  v6 = (BYTE *)(a2 + 8);
  cbData = 4;
  v7 = RegCreateKeyExW(hKey, L"Locations", 0, (LPWSTR)&Format, 0, 0xF003Fu, 0, &phkResult, &dwDisposition);
  *(_DWORD *)v6 = 1;
  if ( !v7 )
    RegQueryValueExW(phkResult, L"NextID", 0, &Type, v6, &cbData);
  *(_DWORD *)Data = *(_DWORD *)v6 + 1;
  if ( !v7 )
  {
    RegSetValueExW(phkResult, L"NextID", 0, 4u, Data, 4u);
    RegCloseKey(phkResult);
    RegCloseKey(hKey);
  }
  result = a5;
  *a5 = 12;
  return result;
}

```

## disassembly

```asm
0x18001c990  mov     r11, rsp
0x18001c993  mov     [r11+8], rbx
0x18001c997  mov     [r11+18h], rdi
0x18001c99b  push    rbp
0x18001c99c  mov     rbp, rsp
0x18001c99f  sub     rsp, 70h
0x18001c9a3  lea     rax, [rbp+dwDisposition]
0x18001c9a7  mov     [rbp+var_10], 0
0x18001c9af  mov     [r11-38h], rax
0x18001c9b3  lea     r9, Format; lpClass
0x18001c9ba  lea     rax, [rbp+hKey]
0x18001c9be  mov     [rbp+hKey], 0
0x18001c9c6  mov     [r11-40h], rax
0x18001c9ca  mov     rbx, rdx
0x18001c9cd  mov     qword ptr [r11-48h], 0
0x18001c9d5  lea     rdx, gszRegKeyTelephony; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18001c9dc  mov     edi, 0F003Fh
0x18001c9e1  mov     [rbp+cbData], 0
0x18001c9e8  mov     [rsp+70h+samDesired], edi; samDesired
0x18001c9ec  xor     r8d, r8d; Reserved
0x18001c9ef  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001c9f6  mov     [rsp+70h+dwOptions], 0; dwOptions
0x18001c9fe  mov     [rbp+Type], 0
0x18001ca05  mov     dword ptr [rbp+Data], 0
0x18001ca0c  mov     [rbp+dwDisposition], 0
0x18001ca13  call    cs:__imp_RegCreateKeyExW
0x18001ca19  mov     rcx, [rbp+hKey]; hKey
0x18001ca1d  lea     rax, [rbp+dwDisposition]
0x18001ca21  mov     [rsp+70h+lpdwDisposition], rax; lpdwDisposition
0x18001ca26  lea     r9, Format; lpClass
0x18001ca2d  lea     rax, [rbp+var_10]
0x18001ca31  xor     r8d, r8d; Reserved
0x18001ca34  mov     [rsp+70h+phkResult], rax; phkResult
0x18001ca39  lea     rdx, gszLocations; "Locations"
0x18001ca40  mov     [rsp+70h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18001ca49  mov     [rsp+70h+samDesired], edi; samDesired
0x18001ca4d  mov     [rsp+70h+dwOptions], 0; dwOptions
0x18001ca55  call    cs:__imp_RegCreateKeyExW
0x18001ca5b  add     rbx, 8
0x18001ca5f  mov     [rbp+cbData], 4
0x18001ca66  mov     edi, eax
0x18001ca68  mov     dword ptr [rbx], 1
0x18001ca6e  test    eax, eax
0x18001ca70  jnz     short loc_18001CA98
0x18001ca72  mov     rcx, [rbp+var_10]; hKey
0x18001ca76  lea     rax, [rbp+cbData]
0x18001ca7a  mov     qword ptr [rsp+70h+samDesired], rax; lpcbData
0x18001ca7f  lea     r9, [rbp+Type]; lpType
0x18001ca83  xor     r8d, r8d; lpReserved
0x18001ca86  mov     qword ptr [rsp+70h+dwOptions], rbx; lpData
0x18001ca8b  lea     rdx, gszNextID; "NextID"
0x18001ca92  call    cs:__imp_RegQueryValueExW
0x18001ca98  mov     eax, [rbx]
0x18001ca9a  inc     eax
0x18001ca9c  mov     dword ptr [rbp+Data], eax
0x18001ca9f  test    edi, edi
0x18001caa1  jnz     short loc_18001CAE0
0x18001caa3  mov     rcx, [rbp+var_10]; hKey
0x18001caa7  lea     rax, [rbp+Data]
0x18001caab  mov     [rsp+70h+samDesired], 4; cbData
0x18001cab3  lea     r9d, [rdi+4]; dwType
0x18001cab7  xor     r8d, r8d; Reserved
0x18001caba  mov     qword ptr [rsp+70h+dwOptions], rax; lpData
0x18001cabf  lea     rdx, gszNextID; "NextID"
0x18001cac6  call    cs:__imp_RegSetValueExW
0x18001cacc  mov     rcx, [rbp+var_10]; hKey
0x18001cad0  call    cs:__imp_RegCloseKey
0x18001cad6  mov     rcx, [rbp+hKey]; hKey
0x18001cada  call    cs:__imp_RegCloseKey
0x18001cae0  mov     rax, [rbp+arg_20]
0x18001cae4  lea     r11, [rsp+70h+var_s0]
0x18001cae9  mov     rbx, [r11+10h]
0x18001caed  mov     rdi, [r11+20h]
0x18001caf1  mov     dword ptr [rax], 0Ch
0x18001caf7  mov     rsp, r11
0x18001cafa  pop     rbp
0x18001cafb  retn
```
