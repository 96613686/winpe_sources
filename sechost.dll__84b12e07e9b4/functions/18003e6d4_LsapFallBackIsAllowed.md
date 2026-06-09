# LsapFallBackIsAllowed

- ea: `0x18003e6d4`
- end: `0x18003e787`
- name: `LsapFallBackIsAllowed`
- size: `179`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18003d610`
- `0x18003da50`
- `0x18003ddf0`
- `0x18003e000`

## callees

- `0x18003e6d4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003e711`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003e711`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003e74c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003e74c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003e758`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003e758`

## pseudocode

```c
__int64 __fastcall LsapFallBackIsAllowed(__int64 a1)
{
  LSTATUS v1; // ebx
  DWORD Type; // [rsp+50h] [rbp+18h] BYREF
  DWORD cbData; // [rsp+58h] [rbp+20h] BYREF
  int Data; // [rsp+60h] [rbp+28h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+30h] BYREF

  if ( *(_QWORD *)(a1 + 16)
    && (hKey = 0, !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SYSTEM\\CurrentControlSet\\Control\\Lsa", 0, 1u, &hKey))
    && (Type = 0,
        Data = 0,
        cbData = 4,
        v1 = RegQueryValueExW(hKey, L"LsarpcClientAllowRemotedSecretOperations", 0, &Type, (LPBYTE)&Data, &cbData),
        RegCloseKey(hKey),
        !v1)
    && Type == 4
    && cbData == 4 )
  {
    return Data == 0 ? 0xC00000BB : 0;
  }
  else
  {
    return 0;
  }
}

```

## disassembly

```asm
0x18003e6d4  push    rbp
0x18003e6d6  push    rbx
0x18003e6d7  mov     rbp, rsp
0x18003e6da  sub     rsp, 38h
0x18003e6de  cmp     qword ptr [rcx+10h], 0
0x18003e6e3  jz      loc_18003E77E
0x18003e6e9  lea     rax, [rbp+hKey]
0x18003e6ed  mov     [rbp+hKey], 0
0x18003e6f5  mov     r9d, 1; samDesired
0x18003e6fb  mov     [rsp+38h+phkResult], rax; phkResult
0x18003e700  xor     r8d, r8d; ulOptions
0x18003e703  lea     rdx, aSystemCurrentc_1; "SYSTEM\\CurrentControlSet\\Control\\Lsa"
0x18003e70a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003e711  call    cs:__imp_RegOpenKeyExW
0x18003e717  test    eax, eax
0x18003e719  jnz     short loc_18003E77E
0x18003e71b  mov     rcx, [rbp+hKey]; hKey
0x18003e71f  lea     r9, [rbp+Type]; lpType
0x18003e723  mov     [rbp+Type], eax
0x18003e726  lea     rdx, aLsarpccliental; "LsarpcClientAllowRemotedSecretOperation"...
0x18003e72d  mov     [rbp+Data], eax
0x18003e730  xor     r8d, r8d; lpReserved
0x18003e733  lea     rax, [rbp+cbData]
0x18003e737  mov     [rbp+cbData], 4
0x18003e73e  mov     [rsp+38h+lpcbData], rax; lpcbData
0x18003e743  lea     rax, [rbp+Data]
0x18003e747  mov     [rsp+38h+phkResult], rax; lpData
0x18003e74c  call    cs:__imp_RegQueryValueExW
0x18003e752  mov     rcx, [rbp+hKey]; hKey
0x18003e756  mov     ebx, eax
0x18003e758  call    cs:__imp_RegCloseKey
0x18003e75e  test    ebx, ebx
0x18003e760  jnz     short loc_18003E77E
0x18003e762  cmp     [rbp+Type], 4
0x18003e766  jnz     short loc_18003E77E
0x18003e768  cmp     [rbp+cbData], 4
0x18003e76c  jnz     short loc_18003E77E
0x18003e76e  mov     eax, [rbp+Data]
0x18003e771  neg     eax
0x18003e773  sbb     eax, eax
0x18003e775  not     eax
0x18003e777  and     eax, 0C00000BBh
0x18003e77c  jmp     short loc_18003E780
0x18003e77e  xor     eax, eax
0x18003e780  add     rsp, 38h
0x18003e784  pop     rbx
0x18003e785  pop     rbp
0x18003e786  retn
```
