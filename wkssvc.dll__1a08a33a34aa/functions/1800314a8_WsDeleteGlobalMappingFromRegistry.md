# WsDeleteGlobalMappingFromRegistry

- ea: `0x1800314a8`
- end: `0x18003152f`
- name: `WsDeleteGlobalMappingFromRegistry`
- size: `135`
- prototype: `__int64 __fastcall(PCWSTR SourceString)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800012a0`
- `0x180001750`

## callees

- `0x18003097c`
- `0x1800314a8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800314e6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800314e6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180031515`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180031515`

## pseudocode

```c
__int64 __fastcall WsDeleteGlobalMappingFromRegistry(wint_t *SourceString)
{
  unsigned int v2; // ebx
  HKEY hKey; // [rsp+48h] [rbp+10h] BYREF
  HKEY v5; // [rsp+50h] [rbp+18h] BYREF

  hKey = 0;
  v5 = 0;
  v2 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"System\\CurrentControlSet\\Control\\NetworkProvider\\GlobalMappings",
         0,
         0x2001Fu,
         &hKey);
  if ( !v2 )
  {
    v2 = FindCreateOrDeleteConnectionKey(hKey, SourceString, 2, &v5);
    RegCloseKey(hKey);
  }
  return v2;
}

```

## disassembly

```asm
0x1800314a8  mov     r11, rsp
0x1800314ab  mov     [r11+8], rbx
0x1800314af  push    rdi
0x1800314b0  sub     rsp, 30h
0x1800314b4  mov     rdi, rcx
0x1800314b7  mov     qword ptr [r11+10h], 0
0x1800314bf  lea     rax, [r11+10h]
0x1800314c3  mov     qword ptr [r11+18h], 0
0x1800314cb  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800314d2  mov     [r11-18h], rax
0x1800314d6  mov     r9d, 2001Fh; samDesired
0x1800314dc  lea     rdx, aSystemCurrentc_1; "System\\CurrentControlSet\\Control\\Net"...
0x1800314e3  xor     r8d, r8d; ulOptions
0x1800314e6  call    cs:__imp_RegOpenKeyExW
0x1800314ed  nop     dword ptr [rax+rax+00h]
0x1800314f2  mov     ebx, eax
0x1800314f4  test    eax, eax
0x1800314f6  jnz     short loc_180031521
0x1800314f8  mov     rcx, [rsp+38h+hKey]; hKey
0x1800314fd  lea     r9, [rsp+38h+arg_10]
0x180031502  lea     r8d, [rax+2]
0x180031506  mov     rdx, rdi; SourceString
0x180031509  call    FindCreateOrDeleteConnectionKey
0x18003150e  mov     rcx, [rsp+38h+hKey]; hKey
0x180031513  mov     ebx, eax
0x180031515  call    cs:__imp_RegCloseKey
0x18003151c  nop     dword ptr [rax+rax+00h]
0x180031521  mov     eax, ebx
0x180031523  mov     rbx, [rsp+38h+arg_0]
0x180031528  add     rsp, 30h
0x18003152c  pop     rdi
0x18003152d  retn
```
