# ReadMultiSzFromRegistry(ushort const *,ushort const *,ushort * *)

- ea: `0x1800589e4`
- end: `0x180058b08`
- name: `?ReadMultiSzFromRegistry@@YAJPEBG0PEAPEAG@Z`
- size: `292`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18004d47c`

## callees

- `0x180014240`
- `0x180021eb0`
- `0x1800589e4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180058ae9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180058ae9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180058a71`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180058ab6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180058a71`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180058ab6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180058a41`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180058a41`

## pseudocode

```c
__int64 __fastcall ReadMultiSzFromRegistry(LPCWSTR lpSubKey, const unsigned __int16 *a2, BYTE **a3)
{
  unsigned int v4; // edi
  BYTE *v5; // rbx
  DWORD cbData; // [rsp+58h] [rbp+28h] BYREF
  int v8; // [rsp+5Ch] [rbp+2Ch]
  DWORD Type; // [rsp+60h] [rbp+30h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+38h] BYREF

  v8 = HIDWORD(a2);
  hKey = 0;
  cbData = 0;
  Type = 0;
  if ( !a3 )
    return (unsigned int)-1073741811;
  v5 = 0;
  *a3 = 0;
  v4 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0x20119u, &hKey);
  if ( v4 )
    goto LABEL_10;
  v4 = RegQueryValueExW(hKey, L"EccCurves", 0, &Type, 0, &cbData);
  if ( !v4 && Type == 7 )
  {
    v5 = (BYTE *)SPExternalAlloc(cbData + 4);
    if ( v5 )
    {
      v4 = RegQueryValueExW(hKey, L"EccCurves", 0, &Type, v5, &cbData);
      if ( !v4 && Type == 7 )
      {
        *(_WORD *)&v5[2 * ((unsigned __int64)cbData >> 1)] = 0;
        *(_WORD *)&v5[2 * ((unsigned __int64)cbData >> 1) + 2] = 0;
LABEL_10:
        *a3 = v5;
        goto LABEL_11;
      }
      SPExternalFree(v5);
    }
  }
LABEL_11:
  if ( hKey )
    RegCloseKey(hKey);
  return v4;
}

```

## disassembly

```asm
0x1800589e4  mov     [rsp-18h+arg_0], rbx
0x1800589e9  mov     qword ptr [rsp-18h+cbData], rdx
0x1800589ee  push    rbp
0x1800589ef  push    rsi
0x1800589f0  push    rdi
0x1800589f1  mov     rbp, rsp
0x1800589f4  sub     rsp, 30h
0x1800589f8  mov     [rbp+hKey], 0
0x180058a00  mov     rsi, r8
0x180058a03  mov     [rbp+cbData], 0
0x180058a0a  mov     [rbp+Type], 0
0x180058a11  test    r8, r8
0x180058a14  jnz     short loc_180058A20
0x180058a16  mov     edi, 0C000000Dh
0x180058a1b  jmp     loc_180058AEF
0x180058a20  lea     rax, [rbp+hKey]
0x180058a24  mov     rdx, rcx; lpSubKey
0x180058a27  xor     ebx, ebx
0x180058a29  mov     [rsp+30h+phkResult], rax; phkResult
0x180058a2e  mov     [r8], rbx
0x180058a31  mov     r9d, 20119h; samDesired
0x180058a37  xor     r8d, r8d; ulOptions
0x180058a3a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180058a41  call    cs:__imp_RegOpenKeyExW
0x180058a47  mov     edi, eax
0x180058a49  test    eax, eax
0x180058a4b  jnz     loc_180058ADD
0x180058a51  mov     rcx, [rbp+hKey]; hKey
0x180058a55  lea     rax, [rbp+cbData]
0x180058a59  mov     [rsp+30h+lpcbData], rax; lpcbData
0x180058a5e  lea     r9, [rbp+Type]; lpType
0x180058a62  xor     r8d, r8d; lpReserved
0x180058a65  mov     [rsp+30h+phkResult], rbx; lpData
0x180058a6a  lea     rdx, aEcccurves; "EccCurves"
0x180058a71  call    cs:__imp_RegQueryValueExW
0x180058a77  mov     edi, eax
0x180058a79  test    eax, eax
0x180058a7b  jnz     short loc_180058AE0
0x180058a7d  cmp     [rbp+Type], 7
0x180058a81  jnz     short loc_180058AE0
0x180058a83  mov     ecx, [rbp+cbData]
0x180058a86  add     ecx, 4; uBytes
0x180058a89  call    ?SPExternalAlloc@@YAPEAXK@Z; SPExternalAlloc(ulong)
0x180058a8e  mov     rbx, rax
0x180058a91  test    rax, rax
0x180058a94  jz      short loc_180058AE0
0x180058a96  mov     rcx, [rbp+hKey]; hKey
0x180058a9a  lea     rax, [rbp+cbData]
0x180058a9e  mov     [rsp+30h+lpcbData], rax; lpcbData
0x180058aa3  lea     r9, [rbp+Type]; lpType
0x180058aa7  xor     r8d, r8d; lpReserved
0x180058aaa  mov     [rsp+30h+phkResult], rbx; lpData
0x180058aaf  lea     rdx, aEcccurves; "EccCurves"
0x180058ab6  call    cs:__imp_RegQueryValueExW
0x180058abc  mov     edi, eax
0x180058abe  test    eax, eax
0x180058ac0  jnz     short loc_180058AFE
0x180058ac2  cmp     [rbp+Type], 7
0x180058ac6  jnz     short loc_180058AFE
0x180058ac8  mov     ecx, [rbp+cbData]
0x180058acb  shr     rcx, 1
0x180058ace  mov     [rbx+rcx*2], ax
0x180058ad2  mov     ecx, [rbp+cbData]
0x180058ad5  shr     rcx, 1
0x180058ad8  mov     [rbx+rcx*2+2], ax
0x180058add  mov     [rsi], rbx
0x180058ae0  mov     rcx, [rbp+hKey]; hKey
0x180058ae4  test    rcx, rcx
0x180058ae7  jz      short loc_180058AEF
0x180058ae9  call    cs:__imp_RegCloseKey
0x180058aef  mov     rbx, [rsp+30h+arg_0]
0x180058af4  mov     eax, edi
0x180058af6  add     rsp, 30h
0x180058afa  pop     rdi
0x180058afb  pop     rsi
0x180058afc  pop     rbp
0x180058afd  retn
0x180058afe  mov     rcx, rbx; void *
0x180058b01  call    ?SPExternalFree@@YAXPEAX@Z; SPExternalFree(void *)
0x180058b06  jmp     short loc_180058AE0
```
