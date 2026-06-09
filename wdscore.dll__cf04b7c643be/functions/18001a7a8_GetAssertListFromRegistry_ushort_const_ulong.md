# GetAssertListFromRegistry(ushort * const,ulong)

- ea: `0x18001a7a8`
- end: `0x18001a853`
- name: `?GetAssertListFromRegistry@@YAHQEAGK@Z`
- size: `171`
- prototype: `__int64 __fastcall(LPBYTE lpData, unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, installer_update`

## callers

- `0x18001a940`

## callees

- `0x18001a7a8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001a839`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001a839`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001a7f2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001a7f2`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001a823`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001a823`

## pseudocode

```c
__int64 __fastcall GetAssertListFromRegistry(LPBYTE lpData)
{
  unsigned int v3; // ebx
  DWORD cbData[6]; // [rsp+30h] [rbp-18h] BYREF
  HKEY hKey; // [rsp+50h] [rbp+8h] BYREF

  cbData[0] = 520;
  hKey = 0;
  if ( !lpData )
    return 0;
  v3 = 0;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SYSTEM\\Setup\\Panther", 0, 0x20019u, &hKey) )
  {
    LOBYTE(v3) = RegQueryValueExW(hKey, L"TelemetryAssertList", 0, 0, lpData, cbData) == 0;
    RegCloseKey(hKey);
  }
  return v3;
}

```

## disassembly

```asm
0x18001a7a8  mov     [rsp+arg_8], rbx
0x18001a7ad  push    rdi
0x18001a7ae  sub     rsp, 40h
0x18001a7b2  mov     [rsp+48h+cbData], 208h
0x18001a7ba  mov     rdi, rcx
0x18001a7bd  mov     [rsp+48h+hKey], 0
0x18001a7c6  test    rcx, rcx
0x18001a7c9  jnz     short loc_18001A7CF
0x18001a7cb  xor     eax, eax
0x18001a7cd  jmp     short loc_18001A847
0x18001a7cf  lea     rax, [rsp+48h+hKey]
0x18001a7d4  mov     r9d, 20019h; samDesired
0x18001a7da  xor     r8d, r8d; ulOptions
0x18001a7dd  mov     [rsp+48h+phkResult], rax; phkResult
0x18001a7e2  lea     rdx, SubKey; "SYSTEM\\Setup\\Panther"
0x18001a7e9  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001a7f0  xor     ebx, ebx
0x18001a7f2  call    cs:__imp_RegOpenKeyExW
0x18001a7f9  nop     dword ptr [rax+rax+00h]
0x18001a7fe  test    eax, eax
0x18001a800  jnz     short loc_18001A845
0x18001a802  mov     rcx, [rsp+48h+hKey]; hKey
0x18001a807  lea     rax, [rsp+48h+cbData]
0x18001a80c  mov     [rsp+48h+lpcbData], rax; lpcbData
0x18001a811  lea     rdx, ValueName; "TelemetryAssertList"
0x18001a818  xor     r9d, r9d; lpType
0x18001a81b  mov     [rsp+48h+phkResult], rdi; lpData
0x18001a820  xor     r8d, r8d; lpReserved
0x18001a823  call    cs:__imp_RegQueryValueExW
0x18001a82a  nop     dword ptr [rax+rax+00h]
0x18001a82f  mov     rcx, [rsp+48h+hKey]; hKey
0x18001a834  test    eax, eax
0x18001a836  setz    bl
0x18001a839  call    cs:__imp_RegCloseKey
0x18001a840  nop     dword ptr [rax+rax+00h]
0x18001a845  mov     eax, ebx
0x18001a847  mov     rbx, [rsp+48h+arg_8]
0x18001a84c  add     rsp, 40h
0x18001a850  pop     rdi
0x18001a851  retn
```
