# RegistrySetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)

- ea: `0x180067c1c`
- end: `0x180067ce8`
- name: `?RegistrySetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z`
- size: `204`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWSTR lpSubKey, LPCWSTR lpValueName, unsigned int)`
- caller_count: `20`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180002880`
- `0x1800029e0`
- `0x18000ab20`
- `0x18000b350`
- `0x18000d9d0`
- `0x18000e8b0`
- `0x18000ee10`
- `0x18000f2f0`
- `0x18000fac0`
- `0x18000fcb0`
- `0x180010030`
- `0x180010690`
- `0x180010ea0`
- `0x1800115a0`
- `0x180011ed0`
- `0x180012100`
- `0x18001a2c0`
- `0x18001d4a0`
- `0x180050bb0`
- `0x18009a6a0`

## callees

- `0x18001a6c4`
- `0x180067c1c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180067cb1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180067cb1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180067cd0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180067cd0`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180067c82`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180067c82`

## pseudocode

```c
__int64 __fastcall RegistrySetDWORD(HKEY hKey, LPCWSTR lpSubKey, LPCWSTR lpValueName, int a4)
{
  HKEY *phkResult; // rax
  LSTATUS Key; // eax
  unsigned int v9; // ebx
  bool v10; // cc
  HKEY hKeya; // [rsp+68h] [rbp+10h] BYREF
  int Data; // [rsp+78h] [rbp+20h] BYREF

  Data = a4;
  hKeya = 0;
  if ( lpSubKey )
  {
    phkResult = tlx::replace<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>(&hKeya);
    Key = RegCreateKeyExW(hKey, lpSubKey, 0, 0, 0, 0x20006u, 0, phkResult, 0);
    v9 = Key;
    v10 = Key <= 0;
    if ( Key )
      goto LABEL_5;
    hKey = hKeya;
  }
  Key = RegSetValueExW(hKey, lpValueName, 0, 4u, (const BYTE *)&Data, 4u);
  v9 = Key;
  v10 = Key <= 0;
LABEL_5:
  if ( !v10 )
    v9 = (unsigned __int16)Key | 0x80070000;
  if ( hKeya )
    RegCloseKey(hKeya);
  return v9;
}

```

## disassembly

```asm
0x180067c1c  mov     rax, rsp
0x180067c1f  mov     [rax+8], rbx
0x180067c23  mov     [rax+18h], rsi
0x180067c27  mov     [rax+20h], r9d
0x180067c2b  push    rdi
0x180067c2c  sub     rsp, 50h
0x180067c30  mov     qword ptr [rax+10h], 0
0x180067c38  mov     rsi, r8
0x180067c3b  mov     rdi, rdx
0x180067c3e  mov     rbx, rcx
0x180067c41  test    rdx, rdx
0x180067c44  jz      short loc_180067C93
0x180067c46  lea     rcx, [rax+10h]
0x180067c4a  call    ??$replace@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@YAPEAPEAUHKEY__@@AEAV?$auto_xxx@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@0@@Z; tlx::replace<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>(tlx::auto_xxx<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0> &)
0x180067c4f  mov     [rsp+58h+lpdwDisposition], 0; lpdwDisposition
0x180067c58  xor     r9d, r9d; lpClass
0x180067c5b  mov     [rsp+58h+phkResult], rax; phkResult
0x180067c60  xor     r8d, r8d; Reserved
0x180067c63  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180067c6c  mov     rdx, rdi; lpSubKey
0x180067c6f  mov     [rsp+58h+samDesired], 20006h; samDesired
0x180067c77  mov     rcx, rbx; hKey
0x180067c7a  mov     [rsp+58h+dwOptions], 0; dwOptions
0x180067c82  call    cs:__imp_RegCreateKeyExW
0x180067c88  mov     ebx, eax
0x180067c8a  test    eax, eax
0x180067c8c  jnz     short loc_180067CBB
0x180067c8e  mov     rbx, [rsp+58h+hKey]
0x180067c93  mov     r9d, 4; dwType
0x180067c99  lea     rax, [rsp+58h+Data]
0x180067c9e  mov     [rsp+58h+samDesired], r9d; cbData
0x180067ca3  xor     r8d, r8d; Reserved
0x180067ca6  mov     rdx, rsi; lpValueName
0x180067ca9  mov     qword ptr [rsp+58h+dwOptions], rax; lpData
0x180067cae  mov     rcx, rbx; hKey
0x180067cb1  call    cs:__imp_RegSetValueExW
0x180067cb7  mov     ebx, eax
0x180067cb9  test    eax, eax
0x180067cbb  jle     short loc_180067CC6
0x180067cbd  movzx   ebx, ax
0x180067cc0  or      ebx, 80070000h
0x180067cc6  mov     rcx, [rsp+58h+hKey]; hKey
0x180067ccb  test    rcx, rcx
0x180067cce  jz      short loc_180067CD6
0x180067cd0  call    cs:__imp_RegCloseKey
0x180067cd6  mov     rsi, [rsp+58h+arg_10]
0x180067cdb  mov     eax, ebx
0x180067cdd  mov     rbx, [rsp+58h+arg_0]
0x180067ce2  add     rsp, 50h
0x180067ce6  pop     rdi
0x180067ce7  retn
```
