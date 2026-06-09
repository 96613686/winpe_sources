# RegExists

- ea: `0x1800090b4`
- end: `0x180009125`
- name: `RegExists`
- size: `113`
- prototype: `__int64 __fastcall(HKEY, const WCHAR *)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1800035b0`
- `0x1800056c0`

## callees

- `0x1800090b4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800090cd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009117`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800090cd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009117`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800090ef`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800090ef`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009103`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009103`

## pseudocode

```c
__int64 __fastcall RegExists(HKEY a1, const WCHAR *a2)
{
  unsigned int v2; // ebx
  HKEY hKey; // [rsp+50h] [rbp+18h] BYREF

  v2 = 0;
  hKey = 0;
  if ( !a1 )
  {
    SetLastError(0x57u);
    return 0;
  }
  if ( a2 )
  {
    if ( RegOpenKeyExW(a1, a2, 0, 0x20019u, &hKey) || !hKey )
      goto LABEL_9;
    RegCloseKey(hKey);
  }
  else
  {
    hKey = a1;
  }
  v2 = 1;
LABEL_9:
  SetLastError(0);
  return v2;
}

```

## disassembly

```asm
0x1800090b4  mov     [rsp+hKey], r8
0x1800090b9  push    rbx
0x1800090ba  sub     rsp, 30h
0x1800090be  xor     ebx, ebx
0x1800090c0  mov     [rsp+38h+hKey], rbx
0x1800090c5  test    rcx, rcx
0x1800090c8  jnz     short loc_1800090D7
0x1800090ca  lea     ecx, [rbx+57h]; dwErrCode
0x1800090cd  call    cs:__imp_SetLastError
0x1800090d3  xor     eax, eax
0x1800090d5  jmp     short loc_18000911F
0x1800090d7  test    rdx, rdx
0x1800090da  jz      short loc_18000910B
0x1800090dc  lea     rax, [rsp+38h+hKey]
0x1800090e1  mov     r9d, 20019h; samDesired
0x1800090e7  xor     r8d, r8d; ulOptions
0x1800090ea  mov     [rsp+38h+phkResult], rax; phkResult
0x1800090ef  call    cs:__imp_RegOpenKeyExW
0x1800090f5  test    eax, eax
0x1800090f7  jnz     short loc_180009115
0x1800090f9  mov     rcx, [rsp+38h+hKey]; hKey
0x1800090fe  test    rcx, rcx
0x180009101  jz      short loc_180009115
0x180009103  call    cs:__imp_RegCloseKey
0x180009109  jmp     short loc_180009110
0x18000910b  mov     [rsp+38h+hKey], rcx
0x180009110  mov     ebx, 1
0x180009115  xor     ecx, ecx; dwErrCode
0x180009117  call    cs:__imp_SetLastError
0x18000911d  mov     eax, ebx
0x18000911f  add     rsp, 30h
0x180009123  pop     rbx
0x180009124  retn
```
