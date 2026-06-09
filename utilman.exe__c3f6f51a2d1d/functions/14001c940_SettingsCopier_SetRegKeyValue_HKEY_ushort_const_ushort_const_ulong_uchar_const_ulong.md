# SettingsCopier::SetRegKeyValue(HKEY__ *,ushort const *,ushort const *,ulong,uchar const *,ulong)

- ea: `0x14001c940`
- end: `0x14001cad4`
- name: `?SetRegKeyValue@SettingsCopier@@CAJPEAUHKEY__@@PEBG1KPEBEK@Z`
- size: `404`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWSTR lpSubKey, LPCWSTR lpValueName, DWORD dwType, BYTE *lpData, DWORD)`
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path, registry_config`

## callers

- `0x14001bcec`

## callees

- `0x14001c940`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x14001c9fe`
- `ADVAPI32!RegOpenKeyExW` at `0x14001c9fe`
- `ADVAPI32!RegCloseKey` at `0x14001c9d7`
- `ADVAPI32!RegCloseKey` at `0x14001ca4d`
- `ADVAPI32!RegCloseKey` at `0x14001ca74`
- `ADVAPI32!RegCloseKey` at `0x14001cab6`
- `ADVAPI32!RegCloseKey` at `0x14001c9d7`
- `ADVAPI32!RegCloseKey` at `0x14001ca4d`
- `ADVAPI32!RegCloseKey` at `0x14001ca74`
- `ADVAPI32!RegCloseKey` at `0x14001cab6`
- `ADVAPI32!RegSetValueExW` at `0x14001caa4`
- `ADVAPI32!RegSetValueExW` at `0x14001caa4`
- `ADVAPI32!RegQueryValueExW` at `0x14001ca32`
- `ADVAPI32!RegQueryValueExW` at `0x14001ca32`
- `ADVAPI32!RegCreateKeyExW` at `0x14001c9b0`
- `ADVAPI32!RegCreateKeyExW` at `0x14001c9b0`

## string_xrefs

- `0x14001ca2b`: `SymbolicLinkValue`

## pseudocode

```c
LSTATUS __fastcall SettingsCopier::SetRegKeyValue(
        HKEY hKey,
        LPCWSTR lpSubKey,
        LPCWSTR lpValueName,
        DWORD dwType,
        BYTE *lpData,
        DWORD a6)
{
  LSTATUS result; // eax
  bool v11; // cc
  LSTATUS v12; // eax
  LSTATUS v13; // ebx
  bool v14; // cc
  DWORD Type; // [rsp+50h] [rbp-20h] BYREF
  DWORD dwDisposition; // [rsp+54h] [rbp-1Ch] BYREF
  DWORD cbData; // [rsp+58h] [rbp-18h] BYREF
  HKEY v18; // [rsp+60h] [rbp-10h] BYREF
  HKEY hKeya; // [rsp+68h] [rbp-8h] BYREF

  hKeya = 0;
  v18 = 0;
  dwDisposition = 0;
  Type = 0;
  cbData = 0;
  result = RegCreateKeyExW(hKey, lpSubKey, 0, 0, 1u, 0x2001Fu, 0, &hKeya, &dwDisposition);
  v11 = result <= 0;
  if ( result
    || (RegCloseKey(hKeya), result = RegOpenKeyExW(hKey, lpSubKey, 8u, 0x2001Fu, &v18), v11 = result <= 0, result) )
  {
    if ( !v11 )
      return (unsigned __int16)result | 0x80070000;
    return result;
  }
  v12 = RegQueryValueExW(v18, L"SymbolicLinkValue", 0, &Type, 0, &cbData);
  v13 = v12;
  if ( !v12 )
  {
    if ( Type == 6 )
    {
      RegCloseKey(v18);
      return -2147023432;
    }
LABEL_13:
    v13 = RegSetValueExW(v18, lpValueName, 0, dwType, lpData, a6);
    RegCloseKey(v18);
    v14 = v13 <= 0;
    if ( !v13 )
      return 0;
    goto LABEL_8;
  }
  if ( v12 == 2 )
    goto LABEL_13;
  RegCloseKey(v18);
  v14 = v13 <= 0;
LABEL_8:
  if ( !v14 )
    return (unsigned __int16)v13 | 0x80070000;
  return v13;
}

```

## disassembly

```asm
0x14001c940  push    rbp
0x14001c942  push    rbx
0x14001c943  push    rsi
0x14001c944  push    rdi
0x14001c945  push    r14
0x14001c947  mov     rbp, rsp
0x14001c94a  sub     rsp, 70h
0x14001c94e  lea     rax, [rbp+dwDisposition]
0x14001c952  mov     [rbp+hKey], 0
0x14001c95a  mov     [rsp+70h+lpdwDisposition], rax; lpdwDisposition
0x14001c95f  mov     esi, r9d
0x14001c962  lea     rax, [rbp+hKey]
0x14001c966  mov     [rbp+var_10], 0
0x14001c96e  mov     [rsp+70h+phkResult], rax; phkResult
0x14001c973  mov     r14, r8
0x14001c976  mov     [rsp+70h+lpSecurityAttributes], 0; lpSecurityAttributes
0x14001c97f  xor     r9d, r9d; lpClass
0x14001c982  mov     [rsp+70h+samDesired], 2001Fh; samDesired
0x14001c98a  xor     r8d, r8d; Reserved
0x14001c98d  mov     [rsp+70h+dwOptions], 1; dwOptions
0x14001c995  mov     rbx, rdx
0x14001c998  mov     rdi, rcx
0x14001c99b  mov     [rbp+dwDisposition], 0
0x14001c9a2  mov     [rbp+Type], 0
0x14001c9a9  mov     [rbp+cbData], 0
0x14001c9b0  call    cs:__imp_RegCreateKeyExW
0x14001c9b7  nop     dword ptr [rax+rax+00h]
0x14001c9bc  test    eax, eax
0x14001c9be  jz      short loc_14001C9D3
0x14001c9c0  jle     loc_14001CAC8
0x14001c9c6  movzx   eax, ax
0x14001c9c9  or      eax, 80070000h
0x14001c9ce  jmp     loc_14001CAC8
0x14001c9d3  mov     rcx, [rbp+hKey]; hKey
0x14001c9d7  call    cs:__imp_RegCloseKey
0x14001c9de  nop     dword ptr [rax+rax+00h]
0x14001c9e3  lea     rax, [rbp+var_10]
0x14001c9e7  mov     r9d, 2001Fh; samDesired
0x14001c9ed  mov     r8d, 8; ulOptions
0x14001c9f3  mov     qword ptr [rsp+70h+dwOptions], rax; phkResult
0x14001c9f8  mov     rdx, rbx; lpSubKey
0x14001c9fb  mov     rcx, rdi; hKey
0x14001c9fe  call    cs:__imp_RegOpenKeyExW
0x14001ca05  nop     dword ptr [rax+rax+00h]
0x14001ca0a  test    eax, eax
0x14001ca0c  jnz     short loc_14001C9C0
0x14001ca0e  mov     rcx, [rbp+var_10]; hKey
0x14001ca12  lea     rax, [rbp+cbData]
0x14001ca16  mov     qword ptr [rsp+70h+samDesired], rax; lpcbData
0x14001ca1b  lea     r9, [rbp+Type]; lpType
0x14001ca1f  xor     r8d, r8d; lpReserved
0x14001ca22  mov     qword ptr [rsp+70h+dwOptions], 0; lpData
0x14001ca2b  lea     rdx, aSymboliclinkva; "SymbolicLinkValue"
0x14001ca32  call    cs:__imp_RegQueryValueExW
0x14001ca39  nop     dword ptr [rax+rax+00h]
0x14001ca3e  mov     ebx, eax
0x14001ca40  test    eax, eax
0x14001ca42  jz      short loc_14001CA6A
0x14001ca44  cmp     eax, 2
0x14001ca47  jz      short loc_14001CA87
0x14001ca49  mov     rcx, [rbp+var_10]; hKey
0x14001ca4d  call    cs:__imp_RegCloseKey
0x14001ca54  nop     dword ptr [rax+rax+00h]
0x14001ca59  test    ebx, ebx
0x14001ca5b  jle     short loc_14001CA66
0x14001ca5d  movzx   ebx, bx
0x14001ca60  or      ebx, 80070000h
0x14001ca66  mov     eax, ebx
0x14001ca68  jmp     short loc_14001CAC8
0x14001ca6a  cmp     [rbp+Type], 6
0x14001ca6e  jnz     short loc_14001CA87
0x14001ca70  mov     rcx, [rbp+var_10]; hKey
0x14001ca74  call    cs:__imp_RegCloseKey
0x14001ca7b  nop     dword ptr [rax+rax+00h]
0x14001ca80  mov     eax, 800705B8h
0x14001ca85  jmp     short loc_14001CAC8
0x14001ca87  mov     eax, [rbp+arg_28]
0x14001ca8a  mov     r9d, esi; dwType
0x14001ca8d  mov     rcx, [rbp+var_10]; hKey
0x14001ca91  xor     r8d, r8d; Reserved
0x14001ca94  mov     [rsp+70h+samDesired], eax; cbData
0x14001ca98  mov     rdx, r14; lpValueName
0x14001ca9b  mov     rax, [rbp+lpData]
0x14001ca9f  mov     qword ptr [rsp+70h+dwOptions], rax; lpData
0x14001caa4  call    cs:__imp_RegSetValueExW
0x14001caab  nop     dword ptr [rax+rax+00h]
0x14001cab0  mov     rcx, [rbp+var_10]; hKey
0x14001cab4  mov     ebx, eax
0x14001cab6  call    cs:__imp_RegCloseKey
0x14001cabd  nop     dword ptr [rax+rax+00h]
0x14001cac2  test    ebx, ebx
0x14001cac4  jnz     short loc_14001CA5B
0x14001cac6  xor     eax, eax
0x14001cac8  add     rsp, 70h
0x14001cacc  pop     r14
0x14001cace  pop     rdi
0x14001cacf  pop     rsi
0x14001cad0  pop     rbx
0x14001cad1  pop     rbp
0x14001cad2  retn
```
