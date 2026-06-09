# hresMumbleKeyEx

- ea: `0x18000e510`
- end: `0x18000e5ae`
- name: `hresMumbleKeyEx`
- size: `158`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18000e330`

## callees

- `0x18000e510`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000e539`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000e539`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000e57e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000e57e`

## pseudocode

```c
__int64 hresMumbleKeyEx()
{
  LSTATUS Key; // eax

  if ( !RegOpenKeyExW(HKEY_CURRENT_USER, aSystemCurrentc, 0, 0x2001Fu, &phkResult) )
    return 0;
  Key = RegCreateKeyExW(HKEY_CURRENT_USER, aSystemCurrentc, 0, 0, 0, 0x2001Fu, 0, &phkResult, 0);
  if ( !Key )
    return 0;
  if ( ((Key - 1010) & 0xFFFFFFF7) == 0 )
    LOWORD(Key) = 2;
  return (unsigned __int16)Key | 0x80070000;
}

```

## disassembly

```asm
0x18000e510  push    rbp
0x18000e512  sub     rsp, 50h
0x18000e516  lea     rbp, phkResult
0x18000e51d  mov     r9d, 2001Fh; samDesired
0x18000e523  xor     r8d, r8d; ulOptions
0x18000e526  mov     [rsp+58h+phkResult], rbp; phkResult
0x18000e52b  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Control\\Med"...
0x18000e532  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18000e539  call    cs:__imp_RegOpenKeyExW
0x18000e53f  test    eax, eax
0x18000e541  jz      short loc_18000E5A6
0x18000e543  mov     [rsp+58h+lpdwDisposition], 0; lpdwDisposition
0x18000e54c  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Control\\Med"...
0x18000e553  mov     [rsp+58h+var_20], rbp; phkResult
0x18000e558  xor     r9d, r9d; lpClass
0x18000e55b  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18000e564  xor     r8d, r8d; Reserved
0x18000e567  mov     [rsp+58h+samDesired], 2001Fh; samDesired
0x18000e56f  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18000e576  mov     dword ptr [rsp+58h+phkResult], 0; dwOptions
0x18000e57e  call    cs:__imp_RegCreateKeyExW
0x18000e584  test    eax, eax
0x18000e586  jz      short loc_18000E5A6
0x18000e588  lea     ecx, [rax-3F2h]
0x18000e58e  test    ecx, 0FFFFFFF7h
0x18000e594  mov     ecx, 2
0x18000e599  cmovz   eax, ecx
0x18000e59c  movzx   eax, ax
0x18000e59f  or      eax, 80070000h
0x18000e5a4  jmp     short loc_18000E5A8
0x18000e5a6  xor     eax, eax
0x18000e5a8  add     rsp, 50h
0x18000e5ac  pop     rbp
0x18000e5ad  retn
```
