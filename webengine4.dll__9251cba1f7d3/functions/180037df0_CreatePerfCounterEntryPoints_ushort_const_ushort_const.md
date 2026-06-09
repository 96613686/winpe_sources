# CreatePerfCounterEntryPoints(ushort const *,ushort const * *)

- ea: `0x180037df0`
- end: `0x180037f52`
- name: `?CreatePerfCounterEntryPoints@@YAJPEBGPEAPEBG@Z`
- size: `354`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey, const unsigned __int16 **)`
- caller_count: `5`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callers

- `0x1800382f0`
- `0x1800397d4`
- `0x180039b1c`
- `0x18003bcd0`
- `0x18003bf1c`

## callees

- `0x180037df0`

## import_xrefs

- `KERNEL32!lstrlenW` at `0x180037e7b`
- `KERNEL32!lstrlenW` at `0x180037eb5`
- `KERNEL32!lstrlenW` at `0x180037ef0`
- `KERNEL32!lstrlenW` at `0x180037e7b`
- `KERNEL32!lstrlenW` at `0x180037eb5`
- `KERNEL32!lstrlenW` at `0x180037ef0`
- `ADVAPI32!RegCloseKey` at `0x180037f3f`
- `ADVAPI32!RegCloseKey` at `0x180037f3f`
- `ADVAPI32!RegCreateKeyExW` at `0x180037e35`
- `ADVAPI32!RegCreateKeyExW` at `0x180037e35`
- `ADVAPI32!RegSetValueExW` at `0x180037e6a`
- `ADVAPI32!RegSetValueExW` at `0x180037ea7`
- `ADVAPI32!RegSetValueExW` at `0x180037ee2`
- `ADVAPI32!RegSetValueExW` at `0x180037f1d`
- `ADVAPI32!RegSetValueExW` at `0x180037e6a`
- `ADVAPI32!RegSetValueExW` at `0x180037ea7`
- `ADVAPI32!RegSetValueExW` at `0x180037ee2`
- `ADVAPI32!RegSetValueExW` at `0x180037f1d`

## string_xrefs

- `0x180037e48`: `aspnet_counters.dll`

## pseudocode

```c
__int64 __fastcall CreatePerfCounterEntryPoints(LPCWSTR lpSubKey, const unsigned __int16 **a2)
{
  unsigned int v2; // ebx
  LSTATUS v4; // eax
  int v5; // eax
  int v6; // eax
  int v7; // eax
  DWORD v9; // [rsp+70h] [rbp+18h] BYREF
  HKEY hKey; // [rsp+78h] [rbp+20h] BYREF

  v2 = 0;
  hKey = 0;
  v4 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0, 0, 0x20006u, 0, &hKey, &v9);
  if ( v4
    || (v4 = RegSetValueExW(hKey, L"Library", 0, 1u, L"aspnet_counters.dll", 0x28u)) != 0
    || (v5 = lstrlenW(*a2), (v4 = RegSetValueExW(hKey, L"Open", 0, 1u, (const BYTE *)*a2, 2 * v5 + 2)) != 0)
    || (v6 = lstrlenW(a2[1]), (v4 = RegSetValueExW(hKey, L"Close", 0, 1u, (const BYTE *)a2[1], 2 * v6 + 2)) != 0)
    || (v7 = lstrlenW(a2[2]), (v4 = RegSetValueExW(hKey, L"Collect", 0, 1u, (const BYTE *)a2[2], 2 * v7 + 2)) != 0) )
  {
    v2 = (unsigned __int16)v4 | 0x80070000;
    if ( v4 <= 0 )
      v2 = v4;
  }
  if ( hKey )
    RegCloseKey(hKey);
  return v2;
}

```

## disassembly

```asm
0x180037df0  mov     r11, rsp
0x180037df3  mov     [r11+8], rbx
0x180037df7  push    rdi
0x180037df8  sub     rsp, 50h
0x180037dfc  lea     rax, [r11+18h]
0x180037e00  xor     ebx, ebx
0x180037e02  and     [r11+20h], rbx
0x180037e06  mov     rdi, rdx
0x180037e09  mov     [r11-18h], rax
0x180037e0d  mov     rdx, rcx; lpSubKey
0x180037e10  lea     rax, [r11+20h]
0x180037e14  xor     r9d, r9d; lpClass
0x180037e17  mov     [r11-20h], rax
0x180037e1b  xor     r8d, r8d; Reserved
0x180037e1e  and     [r11-28h], rbx
0x180037e22  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180037e29  mov     [rsp+58h+samDesired], 20006h; samDesired
0x180037e31  and     dword ptr [rsp+58h+lpData], ebx
0x180037e35  call    cs:__imp_RegCreateKeyExW
0x180037e3b  test    eax, eax
0x180037e3d  jnz     loc_180037F27
0x180037e43  mov     rcx, [rsp+58h+hKey]; hKey
0x180037e48  lea     rax, Data; "aspnet_counters.dll"
0x180037e4f  mov     [rsp+58h+samDesired], 28h ; '('; cbData
0x180037e57  lea     r9d, [rbx+1]; dwType
0x180037e5b  xor     r8d, r8d; Reserved
0x180037e5e  mov     [rsp+58h+lpData], rax; lpData
0x180037e63  lea     rdx, aLibrary; "Library"
0x180037e6a  call    cs:__imp_RegSetValueExW
0x180037e70  test    eax, eax
0x180037e72  jnz     loc_180037F27
0x180037e78  mov     rcx, [rdi]; lpString
0x180037e7b  call    cs:__imp_lstrlenW
0x180037e81  mov     rcx, [rsp+58h+hKey]; hKey
0x180037e86  lea     r9d, [rbx+1]; dwType
0x180037e8a  xor     r8d, r8d; Reserved
0x180037e8d  lea     rdx, aOpen; "Open"
0x180037e94  lea     eax, ds:2[rax*2]
0x180037e9b  mov     [rsp+58h+samDesired], eax; cbData
0x180037e9f  mov     rax, [rdi]
0x180037ea2  mov     [rsp+58h+lpData], rax; lpData
0x180037ea7  call    cs:__imp_RegSetValueExW
0x180037ead  test    eax, eax
0x180037eaf  jnz     short loc_180037F27
0x180037eb1  mov     rcx, [rdi+8]; lpString
0x180037eb5  call    cs:__imp_lstrlenW
0x180037ebb  mov     rcx, [rsp+58h+hKey]; hKey
0x180037ec0  lea     r9d, [rbx+1]; dwType
0x180037ec4  xor     r8d, r8d; Reserved
0x180037ec7  lea     rdx, aClose; "Close"
0x180037ece  lea     eax, ds:2[rax*2]
0x180037ed5  mov     [rsp+58h+samDesired], eax; cbData
0x180037ed9  mov     rax, [rdi+8]
0x180037edd  mov     [rsp+58h+lpData], rax; lpData
0x180037ee2  call    cs:__imp_RegSetValueExW
0x180037ee8  test    eax, eax
0x180037eea  jnz     short loc_180037F27
0x180037eec  mov     rcx, [rdi+10h]; lpString
0x180037ef0  call    cs:__imp_lstrlenW
0x180037ef6  mov     rcx, [rsp+58h+hKey]; hKey
0x180037efb  lea     r9d, [rbx+1]; dwType
0x180037eff  xor     r8d, r8d; Reserved
0x180037f02  lea     rdx, aCollect; "Collect"
0x180037f09  lea     eax, ds:2[rax*2]
0x180037f10  mov     [rsp+58h+samDesired], eax; cbData
0x180037f14  mov     rax, [rdi+10h]
0x180037f18  mov     [rsp+58h+lpData], rax; lpData
0x180037f1d  call    cs:__imp_RegSetValueExW
0x180037f23  test    eax, eax
0x180037f25  jz      short loc_180037F35
0x180037f27  movzx   ebx, ax
0x180037f2a  or      ebx, 80070000h
0x180037f30  test    eax, eax
0x180037f32  cmovle  ebx, eax
0x180037f35  mov     rcx, [rsp+58h+hKey]; hKey
0x180037f3a  test    rcx, rcx
0x180037f3d  jz      short loc_180037F45
0x180037f3f  call    cs:__imp_RegCloseKey
0x180037f45  mov     eax, ebx
0x180037f47  mov     rbx, [rsp+58h+arg_0]
0x180037f4c  add     rsp, 50h
0x180037f50  pop     rdi
0x180037f51  retn
```
