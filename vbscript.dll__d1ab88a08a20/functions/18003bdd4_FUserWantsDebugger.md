# FUserWantsDebugger

- ea: `0x18003bdd4`
- end: `0x18003bec0`
- name: `FUserWantsDebugger`
- size: `236`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180041864`

## callees

- `0x18003bdd4`

## import_xrefs

- `ADVAPI32!RegSetValueExA` at `0x18003be95`
- `ADVAPI32!RegSetValueExA` at `0x18003be95`
- `ADVAPI32!RegCreateKeyExA` at `0x18003be24`
- `ADVAPI32!RegCreateKeyExA` at `0x18003be24`
- `ADVAPI32!RegCloseKey` at `0x18003beaa`
- `ADVAPI32!RegCloseKey` at `0x18003beaa`
- `ADVAPI32!RegQueryValueExA` at `0x18003be58`
- `ADVAPI32!RegQueryValueExA` at `0x18003be58`

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
0x18003bdd4  push    rbp
0x18003bdd6  push    rbx
0x18003bdd7  mov     rbp, rsp
0x18003bdda  sub     rsp, 58h
0x18003bdde  xor     ebx, ebx
0x18003bde0  mov     [rbp+cbData], 4
0x18003bde7  mov     [rsp+58h+lpdwDisposition], rbx; lpdwDisposition
0x18003bdec  lea     rax, [rbp+hKey]
0x18003bdf0  mov     [rsp+58h+phkResult], rax; phkResult
0x18003bdf5  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\Windows Script\\Se"...
0x18003bdfc  mov     [rsp+58h+lpSecurityAttributes], rbx; lpSecurityAttributes
0x18003be01  xor     r9d, r9d; lpClass
0x18003be04  mov     [rsp+58h+samDesired], 2000000h; samDesired
0x18003be0c  xor     r8d, r8d; Reserved
0x18003be0f  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18003be16  mov     [rsp+58h+dwOptions], ebx; dwOptions
0x18003be1a  mov     [rbp+hKey], rbx
0x18003be1e  mov     [rbp+Type], ebx
0x18003be21  mov     [rbp+Data], ebx
0x18003be24  call    cs:__imp_RegCreateKeyExA
0x18003be2b  nop     dword ptr [rax+rax+00h]
0x18003be30  test    eax, eax
0x18003be32  jnz     short loc_18003BEA1
0x18003be34  mov     rcx, [rbp+hKey]; hKey
0x18003be38  lea     rax, [rbp+cbData]
0x18003be3c  mov     qword ptr [rsp+58h+samDesired], rax; lpcbData
0x18003be41  lea     r9, [rbp+Type]; lpType
0x18003be45  lea     rax, [rbp+Data]
0x18003be49  xor     r8d, r8d; lpReserved
0x18003be4c  lea     rdx, aJitdebug; "JITDebug"
0x18003be53  mov     qword ptr [rsp+58h+dwOptions], rax; lpData
0x18003be58  call    cs:__imp_RegQueryValueExA
0x18003be5f  nop     dword ptr [rax+rax+00h]
0x18003be64  test    eax, eax
0x18003be66  jnz     short loc_18003BE70
0x18003be68  cmp     [rbp+Data], ebx
0x18003be6b  setnz   bl
0x18003be6e  jmp     short loc_18003BEA1
0x18003be70  mov     rcx, [rbp+hKey]; hKey
0x18003be74  lea     rax, [rbp+Data]
0x18003be78  mov     [rsp+58h+samDesired], 4; cbData
0x18003be80  lea     rdx, aJitdebug; "JITDebug"
0x18003be87  mov     r9d, 4; dwType
0x18003be8d  mov     qword ptr [rsp+58h+dwOptions], rax; lpData
0x18003be92  xor     r8d, r8d; Reserved
0x18003be95  call    cs:__imp_RegSetValueExA
0x18003be9c  nop     dword ptr [rax+rax+00h]
0x18003bea1  mov     rcx, [rbp+hKey]; hKey
0x18003bea5  test    rcx, rcx
0x18003bea8  jz      short loc_18003BEB6
0x18003beaa  call    cs:__imp_RegCloseKey
0x18003beb1  nop     dword ptr [rax+rax+00h]
0x18003beb6  mov     eax, ebx
0x18003beb8  add     rsp, 58h
0x18003bebc  pop     rbx
0x18003bebd  pop     rbp
0x18003bebe  retn
```
