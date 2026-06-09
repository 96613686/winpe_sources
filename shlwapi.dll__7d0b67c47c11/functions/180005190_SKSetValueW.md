# SKSetValueW

- ea: `0x180005190`
- end: `0x180005211`
- name: `SKSetValueW`
- size: `129`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x180005190`
- `0x180005220`
- `0x18000eaf0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800051e5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800051e5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800051da`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800051da`

## pseudocode

```c
__int64 __fastcall SKSetValueW(int a1, const WCHAR *a2, const WCHAR *a3, DWORD a4, BYTE *lpData, DWORD cbData)
{
  HKEY v8; // rax
  HKEY v9; // rdi
  LSTATUS v10; // ebx

  v8 = SHGetShellKeyEx(a1, a2, 1, 2u);
  v9 = v8;
  if ( !v8 )
    return ResultFromKnownLastError();
  v10 = RegSetValueExW(v8, a3, 0, a4, lpData, cbData);
  RegCloseKey(v9);
  if ( v10 > 0 )
    return (unsigned __int16)v10 | 0x80070000;
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180005190  mov     [rsp+arg_0], rbx
0x180005195  mov     [rsp+arg_8], rsi
0x18000519a  push    rdi
0x18000519b  sub     rsp, 30h
0x18000519f  mov     ebx, r9d
0x1800051a2  mov     rsi, r8
0x1800051a5  mov     r9d, 2
0x1800051ab  lea     r8d, [r9-1]
0x1800051af  call    SHGetShellKeyEx
0x1800051b4  mov     rdi, rax
0x1800051b7  test    rax, rax
0x1800051ba  jz      short loc_18000520A
0x1800051bc  mov     ecx, [rsp+38h+arg_28]
0x1800051c0  mov     r9d, ebx; dwType
0x1800051c3  mov     [rsp+38h+cbData], ecx; cbData
0x1800051c7  xor     r8d, r8d; Reserved
0x1800051ca  mov     rcx, [rsp+38h+arg_20]
0x1800051cf  mov     rdx, rsi; lpValueName
0x1800051d2  mov     [rsp+38h+lpData], rcx; lpData
0x1800051d7  mov     rcx, rax; hKey
0x1800051da  call    cs:__imp_RegSetValueExW
0x1800051e0  mov     rcx, rdi; hKey
0x1800051e3  mov     ebx, eax
0x1800051e5  call    cs:__imp_RegCloseKey
0x1800051eb  test    ebx, ebx
0x1800051ed  jle     short loc_1800051F8
0x1800051ef  movzx   ebx, bx
0x1800051f2  or      ebx, 80070000h
0x1800051f8  mov     eax, ebx
0x1800051fa  mov     rbx, [rsp+38h+arg_0]
0x1800051ff  mov     rsi, [rsp+38h+arg_8]
0x180005204  add     rsp, 30h
0x180005208  pop     rdi
0x180005209  retn
0x18000520a  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18000520f  jmp     short loc_1800051FA
```
