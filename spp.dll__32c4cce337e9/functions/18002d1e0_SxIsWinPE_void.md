# SxIsWinPE(void)

- ea: `0x18002d1e0`
- end: `0x18002d23a`
- name: `?SxIsWinPE@@YAHXZ`
- size: `90`
- prototype: `__int64(void)`
- caller_count: `6`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1800057e0`
- `0x180006730`
- `0x180007ad0`
- `0x18000e7b0`
- `0x180013c7c`
- `0x18001e508`

## callees

- `0x18002d1e0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002d22c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002d22c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002d210`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002d210`

## pseudocode

```c
_BOOL8 SxIsWinPE(void)
{
  BOOL v0; // ebx
  HKEY hKey; // [rsp+40h] [rbp+8h] BYREF

  hKey = 0;
  v0 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SYSTEM\\CurrentControlSet\\Control\\MiniNT", 0, 0x20019u, &hKey) == 0;
  if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    RegCloseKey(hKey);
  return v0;
}

```

## disassembly

```asm
0x18002d1e0  push    rbx
0x18002d1e2  sub     rsp, 30h
0x18002d1e6  lea     rax, [rsp+38h+hKey]
0x18002d1eb  mov     [rsp+38h+hKey], 0
0x18002d1f4  mov     r9d, 20019h; samDesired
0x18002d1fa  mov     [rsp+38h+phkResult], rax; phkResult
0x18002d1ff  xor     r8d, r8d; ulOptions
0x18002d202  lea     rdx, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Control\\Min"...
0x18002d209  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002d210  call    cs:__imp_RegOpenKeyExW
0x18002d216  mov     rcx, [rsp+38h+hKey]; hKey
0x18002d21b  xor     ebx, ebx
0x18002d21d  test    eax, eax
0x18002d21f  setz    bl
0x18002d222  lea     rdx, [rcx-1]
0x18002d226  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18002d22a  ja      short loc_18002D232
0x18002d22c  call    cs:__imp_RegCloseKey
0x18002d232  mov     eax, ebx
0x18002d234  add     rsp, 30h
0x18002d238  pop     rbx
0x18002d239  retn
```
