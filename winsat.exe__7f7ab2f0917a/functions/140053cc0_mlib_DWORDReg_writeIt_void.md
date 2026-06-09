# mlib::DWORDReg::writeIt(void)

- ea: `0x140053cc0`
- end: `0x140053d06`
- name: `?writeIt@DWORDReg@mlib@@MEAAHXZ`
- size: `70`
- prototype: `__int64 __fastcall(mlib::DWORDReg *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x140053ce9`
- `ADVAPI32!RegSetValueExW` at `0x140053ce9`
- `KERNEL32!SetLastError` at `0x140053cf3`
- `KERNEL32!SetLastError` at `0x140053cf3`

## pseudocode

```c
_BOOL8 __fastcall mlib::DWORDReg::writeIt(mlib::DWORDReg *this)
{
  LSTATUS v1; // ebx

  v1 = RegSetValueExW(
         *((HKEY *)this + 1),
         *(LPCWSTR *)(*((_QWORD *)this + 6) + 24LL),
         0,
         4u,
         (const BYTE *)this + 72,
         4u);
  SetLastError(v1);
  return v1 != 0;
}

```

## disassembly

```asm
0x140053cc0  push    rbx
0x140053cc2  sub     rsp, 30h
0x140053cc6  mov     rdx, [rcx+30h]
0x140053cca  lea     rax, [rcx+48h]
0x140053cce  mov     rcx, [rcx+8]; hKey
0x140053cd2  mov     r9d, 4; dwType
0x140053cd8  mov     [rsp+38h+cbData], r9d; cbData
0x140053cdd  xor     r8d, r8d; Reserved
0x140053ce0  mov     [rsp+38h+lpData], rax; lpData
0x140053ce5  mov     rdx, [rdx+18h]; lpValueName
0x140053ce9  call    cs:__imp_RegSetValueExW
0x140053cef  mov     ecx, eax; dwErrCode
0x140053cf1  mov     ebx, eax
0x140053cf3  call    cs:__imp_SetLastError
0x140053cf9  xor     eax, eax
0x140053cfb  test    ebx, ebx
0x140053cfd  setnz   al
0x140053d00  add     rsp, 30h
0x140053d04  pop     rbx
0x140053d05  retn
```
