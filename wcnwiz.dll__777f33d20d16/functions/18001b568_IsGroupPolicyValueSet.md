# IsGroupPolicyValueSet

- ea: `0x18001b568`
- end: `0x18001b611`
- name: `IsGroupPolicyValueSet`
- size: `169`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18001b880`

## callees

- `0x18001b568`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001b5ab`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001b5ab`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001b5f9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001b5f9`
- `KERNEL32!RegQueryValueExW` at `0x18001b5d7`
- `KERNEL32!RegQueryValueExW` at `0x18001b5d7`

## pseudocode

```c
char __fastcall IsGroupPolicyValueSet(char a1, const WCHAR *a2, const WCHAR *a3)
{
  HKEY hKey; // [rsp+30h] [rbp-18h] BYREF
  DWORD cbData; // [rsp+50h] [rbp+8h] BYREF
  int Data; // [rsp+68h] [rbp+20h] BYREF

  hKey = 0;
  Data = 1;
  cbData = 4;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, a2, 0, 1u, &hKey)
    && !RegQueryValueExW(hKey, a3, 0, 0, (LPBYTE)&Data, &cbData)
    && cbData == 4
    && Data )
  {
    a1 = 1;
  }
  if ( hKey )
    RegCloseKey(hKey);
  return a1;
}

```

## disassembly

```asm
0x18001b568  mov     rax, rsp
0x18001b56b  mov     [rax+10h], rbx
0x18001b56f  mov     [rax+18h], rsi
0x18001b573  push    rdi
0x18001b574  sub     rsp, 40h
0x18001b578  mov     esi, 1
0x18001b57d  mov     qword ptr [rax-18h], 0
0x18001b585  mov     [rax+20h], esi
0x18001b588  mov     rdi, r8
0x18001b58b  mov     dword ptr [rax+8], 4
0x18001b592  lea     rax, [rax-18h]
0x18001b596  movzx   ebx, cl
0x18001b599  mov     r9d, esi; samDesired
0x18001b59c  xor     r8d, r8d; ulOptions
0x18001b59f  mov     [rsp+48h+phkResult], rax; phkResult
0x18001b5a4  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001b5ab  call    cs:__imp_RegOpenKeyExW
0x18001b5b1  test    eax, eax
0x18001b5b3  jnz     short loc_18001B5EF
0x18001b5b5  mov     rcx, [rsp+48h+hKey]; hKey
0x18001b5ba  lea     rax, [rsp+48h+cbData]
0x18001b5bf  mov     [rsp+48h+lpcbData], rax; lpcbData
0x18001b5c4  xor     r9d, r9d; lpType
0x18001b5c7  lea     rax, [rsp+48h+Data]
0x18001b5cc  xor     r8d, r8d; lpReserved
0x18001b5cf  mov     rdx, rdi; lpValueName
0x18001b5d2  mov     [rsp+48h+phkResult], rax; lpData
0x18001b5d7  call    cs:__imp_RegQueryValueExW
0x18001b5dd  test    eax, eax
0x18001b5df  jnz     short loc_18001B5EF
0x18001b5e1  cmp     [rsp+48h+cbData], 4
0x18001b5e6  jnz     short loc_18001B5EF
0x18001b5e8  cmp     [rsp+48h+Data], eax
0x18001b5ec  cmovnz  ebx, esi
0x18001b5ef  mov     rcx, [rsp+48h+hKey]; hKey
0x18001b5f4  test    rcx, rcx
0x18001b5f7  jz      short loc_18001B5FF
0x18001b5f9  call    cs:__imp_RegCloseKey
0x18001b5ff  mov     rsi, [rsp+48h+arg_10]
0x18001b604  mov     al, bl
0x18001b606  mov     rbx, [rsp+48h+arg_8]
0x18001b60b  add     rsp, 40h
0x18001b60f  pop     rdi
0x18001b610  retn
```
