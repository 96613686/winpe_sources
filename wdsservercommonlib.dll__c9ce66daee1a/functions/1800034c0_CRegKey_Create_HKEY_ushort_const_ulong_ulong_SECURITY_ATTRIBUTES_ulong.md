# CRegKey::Create(HKEY__ *,ushort const *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)

- ea: `0x1800034c0`
- end: `0x180003558`
- name: `?Create@CRegKey@@QEAAKPEAUHKEY__@@PEBGKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z`
- size: `152`
- prototype: `unsigned int __usercall@<eax>(PHKEY phkResult@<rcx>, HKEY hKey@<rdx>, LPCWSTR lpSubKey@<r8>, unsigned int@<r9d>, DWORD, LPSECURITY_ATTRIBUTES, unsigned int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000ec80`

## callees

- `0x1800034c0`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x1800034e8`
- `ADVAPI32!RegCloseKey` at `0x1800034e8`
- `ADVAPI32!RegCreateKeyExW` at `0x180003536`
- `ADVAPI32!RegCreateKeyExW` at `0x180003536`

## pseudocode

```c
LSTATUS __fastcall CRegKey::Create(
        PHKEY phkResult,
        HKEY hKey,
        LPCWSTR lpSubKey,
        int a4,
        DWORD dwOptions,
        LPSECURITY_ATTRIBUTES lpSecurityAttributes,
        unsigned int *lpdwDisposition)
{
  HKEY v9; // rcx

  v9 = *phkResult;
  if ( v9 )
  {
    RegCloseKey(v9);
    *phkResult = 0;
  }
  return RegCreateKeyExW(hKey, lpSubKey, 0, 0, dwOptions, a4 | 0x100, lpSecurityAttributes, phkResult, lpdwDisposition);
}

```

## disassembly

```asm
0x1800034c0  mov     [rsp+arg_0], rbx
0x1800034c5  mov     [rsp+arg_8], rbp
0x1800034ca  mov     [rsp+arg_10], rsi
0x1800034cf  push    rdi
0x1800034d0  sub     rsp, 50h
0x1800034d4  mov     rbx, rcx
0x1800034d7  mov     edi, r9d
0x1800034da  mov     rcx, [rcx]; hKey
0x1800034dd  mov     rsi, r8
0x1800034e0  mov     rbp, rdx
0x1800034e3  test    rcx, rcx
0x1800034e6  jz      short loc_1800034F8
0x1800034e8  call    cs:__imp_RegCloseKey
0x1800034ef  nop     dword ptr [rax+rax+00h]
0x1800034f4  and     qword ptr [rbx], 0
0x1800034f8  mov     rax, [rsp+58h+arg_30]
0x180003500  bts     edi, 8
0x180003504  mov     [rsp+58h+lpdwDisposition], rax; lpdwDisposition
0x180003509  xor     r9d, r9d; lpClass
0x18000350c  mov     rax, [rsp+58h+arg_28]
0x180003514  xor     r8d, r8d; Reserved
0x180003517  mov     [rsp+58h+phkResult], rbx; phkResult
0x18000351c  mov     rdx, rsi; lpSubKey
0x18000351f  mov     [rsp+58h+lpSecurityAttributes], rax; lpSecurityAttributes
0x180003524  mov     rcx, rbp; hKey
0x180003527  mov     eax, [rsp+58h+arg_20]
0x18000352e  mov     [rsp+58h+samDesired], edi; samDesired
0x180003532  mov     [rsp+58h+dwOptions], eax; dwOptions
0x180003536  call    cs:__imp_RegCreateKeyExW
0x18000353d  nop     dword ptr [rax+rax+00h]
0x180003542  mov     rbx, [rsp+58h+arg_0]
0x180003547  mov     rbp, [rsp+58h+arg_8]
0x18000354c  mov     rsi, [rsp+58h+arg_10]
0x180003551  add     rsp, 50h
0x180003555  pop     rdi
0x180003556  retn
```
