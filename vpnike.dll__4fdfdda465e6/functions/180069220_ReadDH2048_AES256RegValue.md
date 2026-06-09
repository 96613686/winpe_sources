# ReadDH2048_AES256RegValue

- ea: `0x180069220`
- end: `0x1800692cd`
- name: `ReadDH2048_AES256RegValue`
- size: `173`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, service_task`

## callers

- `0x180032690`
- `0x18003afc0`

## callees

- `0x180069220`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180069294`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180069294`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800692be`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800692be`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180069266`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180069266`

## string_xrefs

- `0x18006924a`: `System\CurrentControlSet\Services\rasman\parameters`

## pseudocode

```c
__int64 __fastcall ReadDH2048_AES256RegValue()
{
  unsigned int Data; // [rsp+40h] [rbp+10h] BYREF
  DWORD Type; // [rsp+48h] [rbp+18h] BYREF
  DWORD cbData; // [rsp+50h] [rbp+20h] BYREF
  HKEY hKey; // [rsp+58h] [rbp+28h] BYREF

  hKey = 0;
  Type = 0;
  cbData = 4;
  Data = 0;
  if ( !RegOpenKeyExA(HKEY_LOCAL_MACHINE, "System\\CurrentControlSet\\Services\\rasman\\parameters", 0, 1u, &hKey)
    && (RegQueryValueExA(hKey, "NegotiateDH2048_AES256", 0, &Type, (LPBYTE)&Data, &cbData) || Type != 4 || Data - 1 > 1) )
  {
    Data = 0;
  }
  if ( hKey )
    RegCloseKey(hKey);
  return Data;
}

```

## disassembly

```asm
0x180069220  push    rbp
0x180069222  mov     rbp, rsp
0x180069225  sub     rsp, 30h
0x180069229  lea     rax, [rbp+hKey]
0x18006922d  mov     [rbp+hKey], 0
0x180069235  mov     r9d, 1; samDesired
0x18006923b  mov     [rsp+30h+phkResult], rax; phkResult
0x180069240  xor     r8d, r8d; ulOptions
0x180069243  mov     [rbp+Type], 0
0x18006924a  lea     rdx, aSystemCurrentc_0; "System\\CurrentControlSet\\Services\\ra"...
0x180069251  mov     [rbp+cbData], 4
0x180069258  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18006925f  mov     [rbp+Data], 0
0x180069266  call    cs:__imp_RegOpenKeyExA
0x18006926c  test    eax, eax
0x18006926e  jnz     short loc_1800692B5
0x180069270  mov     rcx, [rbp+hKey]; hKey
0x180069274  lea     rax, [rbp+cbData]
0x180069278  mov     [rsp+30h+lpcbData], rax; lpcbData
0x18006927d  lea     r9, [rbp+Type]; lpType
0x180069281  lea     rax, [rbp+Data]
0x180069285  xor     r8d, r8d; lpReserved
0x180069288  lea     rdx, aNegotiatedh204; "NegotiateDH2048_AES256"
0x18006928f  mov     [rsp+30h+phkResult], rax; lpData
0x180069294  call    cs:__imp_RegQueryValueExA
0x18006929a  test    eax, eax
0x18006929c  jnz     short loc_1800692AE
0x18006929e  cmp     [rbp+Type], 4
0x1800692a2  jnz     short loc_1800692AE
0x1800692a4  mov     eax, [rbp+Data]
0x1800692a7  dec     eax
0x1800692a9  cmp     eax, 1
0x1800692ac  jbe     short loc_1800692B5
0x1800692ae  mov     [rbp+Data], 0
0x1800692b5  mov     rcx, [rbp+hKey]; hKey
0x1800692b9  test    rcx, rcx
0x1800692bc  jz      short loc_1800692C4
0x1800692be  call    cs:__imp_RegCloseKey
0x1800692c4  mov     eax, [rbp+Data]
0x1800692c7  add     rsp, 30h
0x1800692cb  pop     rbp
0x1800692cc  retn
```
