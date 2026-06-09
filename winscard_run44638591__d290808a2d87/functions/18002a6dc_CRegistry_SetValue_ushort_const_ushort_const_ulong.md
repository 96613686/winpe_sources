# CRegistry::SetValue(ushort const *,ushort const *,ulong)

- ea: `0x18002a6dc`
- end: `0x18002a76d`
- name: `?SetValue@CRegistry@@QEBAXPEBG0K@Z`
- size: `145`
- prototype: `void(CRegistry *__hidden this, const unsigned __int16 *, const unsigned __int16 *, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18001b044`
- `0x18002b0ec`

## callees

- `0x18002a6dc`
- `0x18002ef20`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002a73d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002a73d`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18002a718`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18002a718`

## pseudocode

```c
void __fastcall CRegistry::SetValue(CRegistry *this, const unsigned __int16 *a2, const unsigned __int16 *a3, ulong a4)
{
  int v7; // eax
  LSTATUS v8; // eax
  ulong pExceptionObject; // [rsp+58h] [rbp+20h] BYREF

  pExceptionObject = a4;
  if ( *((_DWORD *)this + 10) )
  {
    pExceptionObject = *((_DWORD *)this + 10);
    throw &pExceptionObject;
  }
  v7 = lstrlenW(a3);
  v8 = RegSetValueExW(*(HKEY *)this, a2, 0, 1u, (const BYTE *)a3, 2 * v7 + 2);
  if ( v8 )
  {
    pExceptionObject = v8;
    throw &pExceptionObject;
  }
}

```

## disassembly

```asm
0x18002a6dc  mov     r11, rsp
0x18002a6df  mov     [r11+8], rbx
0x18002a6e3  mov     [r11+10h], rsi
0x18002a6e7  mov     [r11+20h], r9d
0x18002a6eb  push    rdi
0x18002a6ec  sub     rsp, 30h
0x18002a6f0  mov     eax, [rcx+28h]
0x18002a6f3  mov     rdi, r8
0x18002a6f6  mov     rsi, rdx
0x18002a6f9  mov     rbx, rcx
0x18002a6fc  test    eax, eax
0x18002a6fe  jz      short loc_18002A715
0x18002a700  lea     rdx, _TI1K; pThrowInfo
0x18002a707  mov     [rsp+38h+pExceptionObject], eax
0x18002a70b  lea     rcx, [r11+20h]; pExceptionObject
0x18002a70f  call    _CxxThrowException_0
0x18002a715  mov     rcx, rdi; lpString
0x18002a718  call    cs:__imp_lstrlenW
0x18002a71e  mov     rcx, [rbx]; hKey
0x18002a721  mov     r9d, 1; dwType
0x18002a727  xor     r8d, r8d; Reserved
0x18002a72a  mov     rdx, rsi; lpValueName
0x18002a72d  lea     eax, ds:2[rax*2]
0x18002a734  mov     [rsp+38h+cbData], eax; cbData
0x18002a738  mov     [rsp+38h+lpData], rdi; lpData
0x18002a73d  call    cs:__imp_RegSetValueExW
0x18002a743  test    eax, eax
0x18002a745  jz      short loc_18002A75D
0x18002a747  lea     rdx, _TI1K; pThrowInfo
0x18002a74e  mov     [rsp+38h+pExceptionObject], eax
0x18002a752  lea     rcx, [rsp+38h+pExceptionObject]; pExceptionObject
0x18002a757  call    _CxxThrowException_0
0x18002a75d  mov     rbx, [rsp+38h+arg_0]
0x18002a762  mov     rsi, [rsp+38h+arg_8]
0x18002a767  add     rsp, 30h
0x18002a76b  pop     rdi
0x18002a76c  retn
```
