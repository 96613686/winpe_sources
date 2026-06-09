# FUserWantsDebugger

- ea: `0x18003a3c4`
- end: `0x18003a497`
- name: `FUserWantsDebugger`
- size: `211`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800401a0`

## callees

- `0x18003a3c4`

## import_xrefs

- `ADVAPI32!RegSetValueExA` at `0x18003a479`
- `ADVAPI32!RegSetValueExA` at `0x18003a479`
- `ADVAPI32!RegCreateKeyExA` at `0x18003a414`
- `ADVAPI32!RegCreateKeyExA` at `0x18003a414`
- `ADVAPI32!RegCloseKey` at `0x18003a488`
- `ADVAPI32!RegCloseKey` at `0x18003a488`
- `ADVAPI32!RegQueryValueExA` at `0x18003a442`
- `ADVAPI32!RegQueryValueExA` at `0x18003a442`

## pseudocode

```c
__int64 FUserWantsDebugger()
{
  unsigned int v0; // ebx
  int Data; // [rsp+70h] [rbp+18h] BYREF
  DWORD cbData; // [rsp+78h] [rbp+20h] BYREF
  DWORD Type; // [rsp+80h] [rbp+28h] BYREF
  HKEY hKey; // [rsp+88h] [rbp+30h] BYREF

  v0 = 0;
  cbData = 4;
  hKey = 0;
  Type = 0;
  Data = 0;
  if ( !RegCreateKeyExA(
          HKEY_CURRENT_USER,
          "Software\\Microsoft\\Windows Script\\Settings",
          0,
          0,
          0,
          0x2000000u,
          0,
          &hKey,
          0) )
  {
    if ( RegQueryValueExA(hKey, "JITDebug", 0, &Type, (LPBYTE)&Data, &cbData) )
      RegSetValueExA(hKey, "JITDebug", 0, 4u, (const BYTE *)&Data, 4u);
    else
      LOBYTE(v0) = Data != 0;
  }
  if ( hKey )
    RegCloseKey(hKey);
  return v0;
}

```

## disassembly

```asm
0x18003a3c4  push    rbp
0x18003a3c6  push    rbx
0x18003a3c7  mov     rbp, rsp
0x18003a3ca  sub     rsp, 58h
0x18003a3ce  xor     ebx, ebx
0x18003a3d0  mov     [rbp+cbData], 4
0x18003a3d7  mov     [rsp+58h+lpdwDisposition], rbx; lpdwDisposition
0x18003a3dc  lea     rax, [rbp+hKey]
0x18003a3e0  mov     [rsp+58h+phkResult], rax; phkResult
0x18003a3e5  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\Windows Script\\Se"...
0x18003a3ec  mov     [rsp+58h+lpSecurityAttributes], rbx; lpSecurityAttributes
0x18003a3f1  xor     r9d, r9d; lpClass
0x18003a3f4  mov     [rsp+58h+samDesired], 2000000h; samDesired
0x18003a3fc  xor     r8d, r8d; Reserved
0x18003a3ff  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18003a406  mov     [rsp+58h+dwOptions], ebx; dwOptions
0x18003a40a  mov     [rbp+hKey], rbx
0x18003a40e  mov     [rbp+Type], ebx
0x18003a411  mov     [rbp+Data], ebx
0x18003a414  call    cs:__imp_RegCreateKeyExA
0x18003a41a  test    eax, eax
0x18003a41c  jnz     short loc_18003A47F
0x18003a41e  mov     rcx, [rbp+hKey]; hKey
0x18003a422  lea     rax, [rbp+cbData]
0x18003a426  mov     qword ptr [rsp+58h+samDesired], rax; lpcbData
0x18003a42b  lea     r9, [rbp+Type]; lpType
0x18003a42f  lea     rax, [rbp+Data]
0x18003a433  xor     r8d, r8d; lpReserved
0x18003a436  lea     rdx, aJitdebug; "JITDebug"
0x18003a43d  mov     qword ptr [rsp+58h+dwOptions], rax; lpData
0x18003a442  call    cs:__imp_RegQueryValueExA
0x18003a448  test    eax, eax
0x18003a44a  jnz     short loc_18003A454
0x18003a44c  cmp     [rbp+Data], ebx
0x18003a44f  setnz   bl
0x18003a452  jmp     short loc_18003A47F
0x18003a454  mov     rcx, [rbp+hKey]; hKey
0x18003a458  lea     rax, [rbp+Data]
0x18003a45c  mov     [rsp+58h+samDesired], 4; cbData
0x18003a464  lea     rdx, aJitdebug; "JITDebug"
0x18003a46b  mov     r9d, 4; dwType
0x18003a471  mov     qword ptr [rsp+58h+dwOptions], rax; lpData
0x18003a476  xor     r8d, r8d; Reserved
0x18003a479  call    cs:__imp_RegSetValueExA
0x18003a47f  mov     rcx, [rbp+hKey]; hKey
0x18003a483  test    rcx, rcx
0x18003a486  jz      short loc_18003A48E
0x18003a488  call    cs:__imp_RegCloseKey
0x18003a48e  mov     eax, ebx
0x18003a490  add     rsp, 58h
0x18003a494  pop     rbx
0x18003a495  pop     rbp
0x18003a496  retn
```
