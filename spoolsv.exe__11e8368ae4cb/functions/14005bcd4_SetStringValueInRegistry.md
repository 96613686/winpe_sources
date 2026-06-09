# SetStringValueInRegistry

- ea: `0x14005bcd4`
- end: `0x14005bdc0`
- name: `SetStringValueInRegistry`
- size: `236`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey, LPCWSTR lpValueName, LPCVOID lpData, LPCWSTR, int)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x14005b930`
- `0x14005bba0`

## callees

- `0x14005b8c0`
- `0x14005bcd4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x14005bd59`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x14005bd59`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14005bd9b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14005bdab`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14005bd9b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14005bdab`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x14005bd89`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x14005bd89`

## pseudocode

```c
__int64 __fastcall SetStringValueInRegistry(LPCWSTR lpSubKey, LPCWSTR lpValueName, _WORD *lpData, LPCWSTR a4, int a5)
{
  __int64 v5; // rdi
  unsigned int v9; // ebx
  HKEY v10; // rcx
  HKEY hKey; // [rsp+50h] [rbp-48h] BYREF
  HKEY phkResult; // [rsp+58h] [rbp-40h] BYREF

  v5 = -1;
  do
    ++v5;
  while ( lpData[v5] );
  hKey = 0;
  phkResult = 0;
  v9 = OpenCurrentUserKey(a4, 0x20006u, &hKey);
  if ( !v9 )
  {
    v10 = hKey;
    if ( a5 )
    {
      v9 = RegCreateKeyExW(hKey, lpSubKey, 0, 0, 1u, 0x20006u, 0, &phkResult, 0);
      if ( v9 )
        goto LABEL_8;
      v10 = phkResult;
      lpSubKey = 0;
    }
    v9 = RegSetKeyValueW(v10, lpSubKey, lpValueName, 1u, lpData, 2 * v5 + 2);
  }
LABEL_8:
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( hKey )
    RegCloseKey(hKey);
  return v9;
}

```

## disassembly

```asm
0x14005bcd4  push    rbx
0x14005bcd6  push    rbp
0x14005bcd7  push    rsi
0x14005bcd8  push    rdi
0x14005bcd9  push    r14
0x14005bcdb  push    r15
0x14005bcdd  sub     rsp, 68h
0x14005bce1  or      rdi, 0FFFFFFFFFFFFFFFFh
0x14005bce5  mov     rbp, r8
0x14005bce8  xor     r15d, r15d
0x14005bceb  mov     r14, rdx
0x14005bcee  mov     rsi, rcx
0x14005bcf1  inc     rdi
0x14005bcf4  cmp     [r8+rdi*2], r15w
0x14005bcf9  jnz     short loc_14005BCF1
0x14005bcfb  lea     r8, [rsp+98h+hKey]; phkResult
0x14005bd00  mov     [rsp+98h+hKey], r15
0x14005bd05  mov     edx, 20006h; samDesired
0x14005bd0a  mov     [rsp+98h+var_40], r15
0x14005bd0f  mov     rcx, r9; lpSubKey
0x14005bd12  call    OpenCurrentUserKey
0x14005bd17  mov     ebx, eax
0x14005bd19  test    eax, eax
0x14005bd1b  jnz     short loc_14005BD91
0x14005bd1d  mov     rcx, [rsp+98h+hKey]; hKey
0x14005bd22  cmp     [rsp+98h+arg_20], r15d
0x14005bd2a  jz      short loc_14005BD6D
0x14005bd2c  mov     [rsp+98h+lpdwDisposition], r15; lpdwDisposition
0x14005bd31  lea     rax, [rsp+98h+var_40]
0x14005bd36  mov     [rsp+98h+phkResult], rax; phkResult
0x14005bd3b  xor     r9d, r9d; lpClass
0x14005bd3e  mov     [rsp+98h+lpSecurityAttributes], r15; lpSecurityAttributes
0x14005bd43  xor     r8d, r8d; Reserved
0x14005bd46  mov     [rsp+98h+samDesired], 20006h; samDesired
0x14005bd4e  mov     rdx, rsi; lpSubKey
0x14005bd51  mov     [rsp+98h+dwOptions], 1; dwOptions
0x14005bd59  call    cs:__imp_RegCreateKeyExW
0x14005bd5f  mov     ebx, eax
0x14005bd61  test    eax, eax
0x14005bd63  jnz     short loc_14005BD91
0x14005bd65  mov     rcx, [rsp+98h+var_40]; hKey
0x14005bd6a  mov     rsi, r15
0x14005bd6d  lea     eax, ds:2[rdi*2]
0x14005bd74  mov     r9d, 1; dwType
0x14005bd7a  mov     [rsp+98h+samDesired], eax; cbData
0x14005bd7e  mov     r8, r14; lpValueName
0x14005bd81  mov     rdx, rsi; lpSubKey
0x14005bd84  mov     qword ptr [rsp+98h+dwOptions], rbp; lpData
0x14005bd89  call    cs:__imp_RegSetKeyValueW
0x14005bd8f  mov     ebx, eax
0x14005bd91  mov     rcx, [rsp+98h+var_40]; hKey
0x14005bd96  test    rcx, rcx
0x14005bd99  jz      short loc_14005BDA1
0x14005bd9b  call    cs:__imp_RegCloseKey
0x14005bda1  mov     rcx, [rsp+98h+hKey]; hKey
0x14005bda6  test    rcx, rcx
0x14005bda9  jz      short loc_14005BDB1
0x14005bdab  call    cs:__imp_RegCloseKey
0x14005bdb1  mov     eax, ebx
0x14005bdb3  add     rsp, 68h
0x14005bdb7  pop     r15
0x14005bdb9  pop     r14
0x14005bdbb  pop     rdi
0x14005bdbc  pop     rsi
0x14005bdbd  pop     rbp
0x14005bdbe  pop     rbx
0x14005bdbf  retn
```
