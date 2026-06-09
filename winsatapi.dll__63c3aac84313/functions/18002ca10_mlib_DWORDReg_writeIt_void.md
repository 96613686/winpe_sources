# mlib::DWORDReg::writeIt(void)

- ea: `0x18002ca10`
- end: `0x18002ca56`
- name: `?writeIt@DWORDReg@mlib@@MEAAHXZ`
- size: `70`
- prototype: `__int64 __fastcall(mlib::DWORDReg *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002ca39`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002ca39`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002ca43`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002ca43`

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
0x18002ca10  push    rbx
0x18002ca12  sub     rsp, 30h
0x18002ca16  mov     rdx, [rcx+30h]
0x18002ca1a  lea     rax, [rcx+48h]
0x18002ca1e  mov     rcx, [rcx+8]; hKey
0x18002ca22  mov     r9d, 4; dwType
0x18002ca28  mov     [rsp+38h+cbData], r9d; cbData
0x18002ca2d  xor     r8d, r8d; Reserved
0x18002ca30  mov     [rsp+38h+lpData], rax; lpData
0x18002ca35  mov     rdx, [rdx+18h]; lpValueName
0x18002ca39  call    cs:__imp_RegSetValueExW
0x18002ca3f  mov     ecx, eax; dwErrCode
0x18002ca41  mov     ebx, eax
0x18002ca43  call    cs:__imp_SetLastError
0x18002ca49  xor     eax, eax
0x18002ca4b  test    ebx, ebx
0x18002ca4d  setnz   al
0x18002ca50  add     rsp, 30h
0x18002ca54  pop     rbx
0x18002ca55  retn
```
