# CRegKey::Create(HKEY__ *,ushort const *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)

- ea: `0x180003f60`
- end: `0x180003ff8`
- name: `?Create@CRegKey@@QEAAKPEAUHKEY__@@PEBGKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z`
- size: `152`
- prototype: `unsigned int __usercall@<eax>(PHKEY phkResult@<rcx>, HKEY hKey@<rdx>, LPCWSTR lpSubKey@<r8>, unsigned int@<r9d>, DWORD, LPSECURITY_ATTRIBUTES, unsigned int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000f810`

## callees

- `0x180003f60`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x180003f88`
- `ADVAPI32!RegCloseKey` at `0x180003f88`
- `ADVAPI32!RegCreateKeyExW` at `0x180003fd6`
- `ADVAPI32!RegCreateKeyExW` at `0x180003fd6`

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
0x180003f60  mov     [rsp+arg_0], rbx
0x180003f65  mov     [rsp+arg_8], rbp
0x180003f6a  mov     [rsp+arg_10], rsi
0x180003f6f  push    rdi
0x180003f70  sub     rsp, 50h
0x180003f74  mov     rbx, rcx
0x180003f77  mov     edi, r9d
0x180003f7a  mov     rcx, [rcx]; hKey
0x180003f7d  mov     rsi, r8
0x180003f80  mov     rbp, rdx
0x180003f83  test    rcx, rcx
0x180003f86  jz      short loc_180003F98
0x180003f88  call    cs:__imp_RegCloseKey
0x180003f8f  nop     dword ptr [rax+rax+00h]
0x180003f94  and     qword ptr [rbx], 0
0x180003f98  mov     rax, [rsp+58h+arg_30]
0x180003fa0  bts     edi, 8
0x180003fa4  mov     [rsp+58h+lpdwDisposition], rax; lpdwDisposition
0x180003fa9  xor     r9d, r9d; lpClass
0x180003fac  mov     rax, [rsp+58h+arg_28]
0x180003fb4  xor     r8d, r8d; Reserved
0x180003fb7  mov     [rsp+58h+phkResult], rbx; phkResult
0x180003fbc  mov     rdx, rsi; lpSubKey
0x180003fbf  mov     [rsp+58h+lpSecurityAttributes], rax; lpSecurityAttributes
0x180003fc4  mov     rcx, rbp; hKey
0x180003fc7  mov     eax, [rsp+58h+arg_20]
0x180003fce  mov     [rsp+58h+samDesired], edi; samDesired
0x180003fd2  mov     [rsp+58h+dwOptions], eax; dwOptions
0x180003fd6  call    cs:__imp_RegCreateKeyExW
0x180003fdd  nop     dword ptr [rax+rax+00h]
0x180003fe2  mov     rbx, [rsp+58h+arg_0]
0x180003fe7  mov     rbp, [rsp+58h+arg_8]
0x180003fec  mov     rsi, [rsp+58h+arg_10]
0x180003ff1  add     rsp, 50h
0x180003ff5  pop     rdi
0x180003ff6  retn
```
