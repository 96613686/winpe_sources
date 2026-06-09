# mlib::BoolReg::writeIt(void)

- ea: `0x140053c60`
- end: `0x140053cb3`
- name: `?writeIt@BoolReg@mlib@@MEAAHXZ`
- size: `83`
- prototype: `__int64 __fastcall(mlib::BoolReg *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x140053c96`
- `ADVAPI32!RegSetValueExW` at `0x140053c96`
- `KERNEL32!SetLastError` at `0x140053ca0`
- `KERNEL32!SetLastError` at `0x140053ca0`

## pseudocode

```c
_BOOL8 __fastcall mlib::BoolReg::writeIt(mlib::BoolReg *this)
{
  __int64 v1; // rdx
  bool v2; // zf
  HKEY v3; // rcx
  LSTATUS v4; // ebx
  BOOL Data; // [rsp+40h] [rbp+8h] BYREF

  v1 = *((_QWORD *)this + 6);
  v2 = *((_BYTE *)this + 72) == 0;
  v3 = (HKEY)*((_QWORD *)this + 1);
  Data = !v2;
  v4 = RegSetValueExW(v3, *(LPCWSTR *)(v1 + 24), 0, 4u, (const BYTE *)&Data, 4u);
  SetLastError(v4);
  return v4 != 0;
}

```

## disassembly

```asm
0x140053c60  push    rbx
0x140053c62  sub     rsp, 30h
0x140053c66  mov     rdx, [rcx+30h]
0x140053c6a  xor     eax, eax
0x140053c6c  cmp     [rcx+48h], al
0x140053c6f  mov     r9d, 4; dwType
0x140053c75  mov     rcx, [rcx+8]; hKey
0x140053c79  setnz   al
0x140053c7c  mov     [rsp+38h+cbData], r9d; cbData
0x140053c81  mov     [rsp+38h+Data], eax
0x140053c85  xor     r8d, r8d; Reserved
0x140053c88  mov     rdx, [rdx+18h]; lpValueName
0x140053c8c  lea     rax, [rsp+38h+Data]
0x140053c91  mov     [rsp+38h+lpData], rax; lpData
0x140053c96  call    cs:__imp_RegSetValueExW
0x140053c9c  mov     ecx, eax; dwErrCode
0x140053c9e  mov     ebx, eax
0x140053ca0  call    cs:__imp_SetLastError
0x140053ca6  xor     eax, eax
0x140053ca8  test    ebx, ebx
0x140053caa  setnz   al
0x140053cad  add     rsp, 30h
0x140053cb1  pop     rbx
0x140053cb2  retn
```
