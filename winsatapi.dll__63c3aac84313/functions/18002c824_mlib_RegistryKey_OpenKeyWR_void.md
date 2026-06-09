# mlib::RegistryKey::OpenKeyWR(void)

- ea: `0x18002c824`
- end: `0x18002c8a1`
- name: `?OpenKeyWR@RegistryKey@mlib@@QEAAHXZ`
- size: `125`
- prototype: `__int64 __fastcall(mlib::RegistryKey *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18002c9a0`

## callees

- `0x18002c824`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002c872`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002c872`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002c87c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002c87c`

## pseudocode

```c
__int64 __fastcall mlib::RegistryKey::OpenKeyWR(mlib::RegistryKey *this)
{
  __int64 v1; // rdx
  HKEY *v2; // rdi
  HKEY v3; // rcx
  LSTATUS v4; // ebx
  DWORD v6; // [rsp+60h] [rbp+8h] BYREF

  v1 = *((_QWORD *)this + 3);
  v2 = (HKEY *)((char *)this + 8);
  v3 = (HKEY)*((_QWORD *)this + 4);
  v6 = 0;
  v4 = RegCreateKeyExW(v3, *(LPCWSTR *)(v1 + 24), 0, 0, 0, 0x20006u, 0, v2, &v6);
  SetLastError(v4);
  if ( !v4 )
    return 0;
  *v2 = 0;
  return 1;
}

```

## disassembly

```asm
0x18002c824  mov     r11, rsp
0x18002c827  mov     [r11+10h], rbx
0x18002c82b  push    rdi
0x18002c82c  sub     rsp, 50h
0x18002c830  mov     rdx, [rcx+18h]
0x18002c834  lea     rdi, [rcx+8]
0x18002c838  mov     rcx, [rcx+20h]; hKey
0x18002c83c  lea     rax, [r11+8]
0x18002c840  mov     [r11-18h], rax
0x18002c844  xor     r9d, r9d; lpClass
0x18002c847  mov     [r11-20h], rdi
0x18002c84b  xor     r8d, r8d; Reserved
0x18002c84e  mov     qword ptr [r11-28h], 0
0x18002c856  mov     [rsp+58h+arg_0], 0
0x18002c85e  mov     rdx, [rdx+18h]; lpSubKey
0x18002c862  mov     [rsp+58h+samDesired], 20006h; samDesired
0x18002c86a  mov     [rsp+58h+dwOptions], 0; dwOptions
0x18002c872  call    cs:__imp_RegCreateKeyExW
0x18002c878  mov     ecx, eax; dwErrCode
0x18002c87a  mov     ebx, eax
0x18002c87c  call    cs:__imp_SetLastError
0x18002c882  test    ebx, ebx
0x18002c884  jnz     short loc_18002C88A
0x18002c886  xor     eax, eax
0x18002c888  jmp     short loc_18002C896
0x18002c88a  mov     qword ptr [rdi], 0
0x18002c891  mov     eax, 1
0x18002c896  mov     rbx, [rsp+58h+arg_8]
0x18002c89b  add     rsp, 50h
0x18002c89f  pop     rdi
0x18002c8a0  retn
```
