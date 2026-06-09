# mlib::RstringReg::writeIt(void)

- ea: `0x18002ca60`
- end: `0x18002caae`
- name: `?writeIt@RstringReg@mlib@@MEAAHXZ`
- size: `78`
- prototype: `__int64 __fastcall(mlib::RstringReg *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002ca91`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002ca91`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002ca9b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002ca9b`

## pseudocode

```c
_BOOL8 __fastcall mlib::RstringReg::writeIt(HKEY *this)
{
  LSTATUS v1; // ebx

  v1 = RegSetValueExW(this[1], *((LPCWSTR *)this[6] + 3), 0, 1u, *((const BYTE **)this[9] + 3), 2 * *(_DWORD *)this[9]);
  SetLastError(v1);
  return v1 != 0;
}

```

## disassembly

```asm
0x18002ca60  push    rbx
0x18002ca62  sub     rsp, 30h
0x18002ca66  mov     r8, [rcx+48h]
0x18002ca6a  mov     r9d, 1; dwType
0x18002ca70  mov     rdx, [rcx+30h]
0x18002ca74  mov     rcx, [rcx+8]; hKey
0x18002ca78  mov     eax, [r8]
0x18002ca7b  mov     rdx, [rdx+18h]; lpValueName
0x18002ca7f  add     eax, eax
0x18002ca81  mov     [rsp+38h+cbData], eax; cbData
0x18002ca85  mov     rax, [r8+18h]
0x18002ca89  xor     r8d, r8d; Reserved
0x18002ca8c  mov     [rsp+38h+lpData], rax; lpData
0x18002ca91  call    cs:__imp_RegSetValueExW
0x18002ca97  mov     ecx, eax; dwErrCode
0x18002ca99  mov     ebx, eax
0x18002ca9b  call    cs:__imp_SetLastError
0x18002caa1  xor     eax, eax
0x18002caa3  test    ebx, ebx
0x18002caa5  setnz   al
0x18002caa8  add     rsp, 30h
0x18002caac  pop     rbx
0x18002caad  retn
```
