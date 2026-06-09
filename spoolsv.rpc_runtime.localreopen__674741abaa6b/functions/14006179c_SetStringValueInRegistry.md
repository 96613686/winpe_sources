# SetStringValueInRegistry

- ea: `0x14006179c`
- end: `0x1400618a5`
- name: `SetStringValueInRegistry`
- size: `265`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey, LPCWSTR lpValueName, LPCVOID lpData, LPCWSTR, int)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1400613c4`
- `0x140061658`

## callees

- `0x140061340`
- `0x14006179c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140061825`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140061825`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140061873`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140061889`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140061873`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140061889`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x14006185b`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x14006185b`

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
0x14006179c  push    rbx
0x14006179e  push    rbp
0x14006179f  push    rsi
0x1400617a0  push    rdi
0x1400617a1  push    r14
0x1400617a3  push    r15
0x1400617a5  sub     rsp, 68h
0x1400617a9  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1400617ad  mov     rbp, r8
0x1400617b0  xor     r15d, r15d
0x1400617b3  mov     r14, rdx
0x1400617b6  mov     rsi, rcx
0x1400617b9  inc     rdi
0x1400617bc  cmp     [r8+rdi*2], r15w
0x1400617c1  jnz     short loc_1400617B9
0x1400617c3  lea     r8, [rsp+98h+hKey]; phkResult
0x1400617c8  mov     [rsp+98h+hKey], r15
0x1400617cd  mov     edx, 20006h; samDesired
0x1400617d2  mov     [rsp+98h+var_40], r15
0x1400617d7  mov     rcx, r9; lpSubKey
0x1400617da  call    OpenCurrentUserKey
0x1400617df  mov     ebx, eax
0x1400617e1  test    eax, eax
0x1400617e3  jnz     loc_140061869
0x1400617e9  mov     rcx, [rsp+98h+hKey]; hKey
0x1400617ee  cmp     [rsp+98h+arg_20], r15d
0x1400617f6  jz      short loc_14006183F
0x1400617f8  mov     [rsp+98h+lpdwDisposition], r15; lpdwDisposition
0x1400617fd  lea     rax, [rsp+98h+var_40]
0x140061802  mov     [rsp+98h+phkResult], rax; phkResult
0x140061807  xor     r9d, r9d; lpClass
0x14006180a  mov     [rsp+98h+lpSecurityAttributes], r15; lpSecurityAttributes
0x14006180f  xor     r8d, r8d; Reserved
0x140061812  mov     [rsp+98h+samDesired], 20006h; samDesired
0x14006181a  mov     rdx, rsi; lpSubKey
0x14006181d  mov     [rsp+98h+dwOptions], 1; dwOptions
0x140061825  call    cs:__imp_RegCreateKeyExW
0x14006182c  nop     dword ptr [rax+rax+00h]
0x140061831  mov     ebx, eax
0x140061833  test    eax, eax
0x140061835  jnz     short loc_140061869
0x140061837  mov     rcx, [rsp+98h+var_40]; hKey
0x14006183c  mov     rsi, r15
0x14006183f  lea     eax, ds:2[rdi*2]
0x140061846  mov     r9d, 1; dwType
0x14006184c  mov     [rsp+98h+samDesired], eax; cbData
0x140061850  mov     r8, r14; lpValueName
0x140061853  mov     rdx, rsi; lpSubKey
0x140061856  mov     qword ptr [rsp+98h+dwOptions], rbp; lpData
0x14006185b  call    cs:__imp_RegSetKeyValueW
0x140061862  nop     dword ptr [rax+rax+00h]
0x140061867  mov     ebx, eax
0x140061869  mov     rcx, [rsp+98h+var_40]; hKey
0x14006186e  test    rcx, rcx
0x140061871  jz      short loc_14006187F
0x140061873  call    cs:__imp_RegCloseKey
0x14006187a  nop     dword ptr [rax+rax+00h]
0x14006187f  mov     rcx, [rsp+98h+hKey]; hKey
0x140061884  test    rcx, rcx
0x140061887  jz      short loc_140061895
0x140061889  call    cs:__imp_RegCloseKey
0x140061890  nop     dword ptr [rax+rax+00h]
0x140061895  mov     eax, ebx
0x140061897  add     rsp, 68h
0x14006189b  pop     r15
0x14006189d  pop     r14
0x14006189f  pop     rdi
0x1400618a0  pop     rsi
0x1400618a1  pop     rbp
0x1400618a2  pop     rbx
0x1400618a3  retn
```
