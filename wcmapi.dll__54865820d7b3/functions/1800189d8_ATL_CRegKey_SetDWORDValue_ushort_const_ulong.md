# ATL::CRegKey::SetDWORDValue(ushort const *,ulong)

- ea: `0x1800189d8`
- end: `0x180018a29`
- name: `?SetDWORDValue@CRegKey@ATL@@QEAAJPEBGK@Z`
- size: `81`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *, unsigned int)`
- caller_count: `6`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180006b4c`
- `0x180018b14`
- `0x18001b420`
- `0x18001b770`
- `0x18001bad0`
- `0x18001be50`

## callees

- `0x180008a90`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180018a0a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180018a0a`

## pseudocode

```c
LSTATUS __fastcall ATL::CRegKey::SetDWORDValue(HKEY *this, const unsigned __int16 *a2, int a3)
{
  BYTE v4[8]; // [rsp+30h] [rbp-18h] BYREF

  *(_DWORD *)v4 = a3;
  return RegSetValueExW(*this, a2, 0, 4u, v4, 4u);
}

```

## disassembly

```asm
0x1800189d8  mov     r11, rsp
0x1800189db  sub     rsp, 48h
0x1800189df  mov     rax, cs:__security_cookie
0x1800189e6  xor     rax, rsp
0x1800189e9  mov     [rsp+48h+var_10], rax
0x1800189ee  mov     [r11-18h], r8d
0x1800189f2  lea     rax, [r11-18h]
0x1800189f6  mov     rcx, [rcx]; hKey
0x1800189f9  mov     r9d, 4; dwType
0x1800189ff  mov     [r11-20h], r9d
0x180018a03  xor     r8d, r8d; Reserved
0x180018a06  mov     [r11-28h], rax
0x180018a0a  call    cs:__imp_RegSetValueExW
0x180018a11  nop     dword ptr [rax+rax+00h]
0x180018a16  mov     rcx, [rsp+48h+var_10]
0x180018a1b  xor     rcx, rsp; StackCookie
0x180018a1e  call    __security_check_cookie
0x180018a23  add     rsp, 48h
0x180018a27  retn
```
