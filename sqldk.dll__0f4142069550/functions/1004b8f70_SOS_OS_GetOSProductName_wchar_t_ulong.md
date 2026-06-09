# SOS_OS::GetOSProductName(wchar_t *,ulong)

- ea: `0x1004b8f70`
- end: `0x1004b9005`
- name: `?GetOSProductName@SOS_OS@@SAHPEA_WK@Z`
- size: `149`
- prototype: `__int64 __fastcall(LPBYTE lpData, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1004b8f70`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x1004b8fdd`
- `ADVAPI32!RegQueryValueExW` at `0x1004b8fdd`
- `ADVAPI32!RegOpenKeyExW` at `0x1004b8fb2`
- `ADVAPI32!RegOpenKeyExW` at `0x1004b8fb2`
- `ADVAPI32!RegCloseKey` at `0x1004b8ff2`
- `ADVAPI32!RegCloseKey` at `0x1004b8ff2`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SOS_OS::GetOSProductName(LPBYTE lpData, DWORD a2)
{
  unsigned int v3; // ebx
  LSTATUS v4; // eax
  bool v5; // zf
  DWORD cbData; // [rsp+58h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+60h] [rbp+18h] BYREF

  cbData = a2;
  v3 = 0;
  hKey = 0;
  v4 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion", 0, 0x20019u, &hKey);
  v5 = v4 == 0;
  if ( !v4 )
    v5 = RegQueryValueExW(hKey, L"ProductName", 0, 0, lpData, &cbData) == 0;
  LOBYTE(v3) = v5;
  if ( hKey )
    RegCloseKey(hKey);
  return v3;
}

```

## disassembly

```asm
0x1004b8f70  mov     [rsp+cbData], edx
0x1004b8f74  push    rdi
0x1004b8f75  sub     rsp, 40h
0x1004b8f79  mov     [rsp+48h+var_18], 0FFFFFFFFFFFFFFFEh
0x1004b8f82  mov     [rsp+48h+arg_0], rbx
0x1004b8f87  mov     rdi, rcx
0x1004b8f8a  xor     ebx, ebx
0x1004b8f8c  mov     [rsp+48h+hKey], rbx
0x1004b8f91  lea     rax, [rsp+48h+hKey]
0x1004b8f96  mov     [rsp+48h+phkResult], rax; phkResult
0x1004b8f9b  mov     r9d, 20019h; samDesired
0x1004b8fa1  xor     r8d, r8d; ulOptions
0x1004b8fa4  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x1004b8fab  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1004b8fb2  call    cs:__imp_RegOpenKeyExW
0x1004b8fb8  test    eax, eax
0x1004b8fba  jnz     short loc_1004B8FE5
0x1004b8fbc  lea     rax, [rsp+48h+cbData]
0x1004b8fc1  mov     [rsp+48h+lpcbData], rax; lpcbData
0x1004b8fc6  mov     [rsp+48h+phkResult], rdi; lpData
0x1004b8fcb  xor     r9d, r9d; lpType
0x1004b8fce  xor     r8d, r8d; lpReserved
0x1004b8fd1  lea     rdx, aProductname; "ProductName"
0x1004b8fd8  mov     rcx, [rsp+48h+hKey]; hKey
0x1004b8fdd  call    cs:__imp_RegQueryValueExW
0x1004b8fe3  test    eax, eax
0x1004b8fe5  setz    bl
0x1004b8fe8  mov     rcx, [rsp+48h+hKey]; hKey
0x1004b8fed  test    rcx, rcx
0x1004b8ff0  jz      short loc_1004B8FF8
0x1004b8ff2  call    cs:__imp_RegCloseKey
0x1004b8ff8  mov     eax, ebx
0x1004b8ffa  mov     rbx, [rsp+48h+arg_0]
0x1004b8fff  add     rsp, 40h
0x1004b9003  pop     rdi
0x1004b9004  retn
```
