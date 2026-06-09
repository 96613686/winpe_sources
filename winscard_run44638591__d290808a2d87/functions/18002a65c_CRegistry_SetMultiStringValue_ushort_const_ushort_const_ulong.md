# CRegistry::SetMultiStringValue(ushort const *,ushort const *,ulong)

- ea: `0x18002a65c`
- end: `0x18002a6d3`
- name: `?SetMultiStringValue@CRegistry@@QEBAXPEBG0K@Z`
- size: `119`
- prototype: `void(CRegistry *__hidden this, const unsigned __int16 *, const unsigned __int16 *, unsigned int)`
- caller_count: `4`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18002aaf8`
- `0x18002ad8c`
- `0x18002b0ec`
- `0x18002b2d8`

## callees

- `0x180005150`
- `0x18002a65c`
- `0x18002ef20`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002a6ae`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002a6ae`

## pseudocode

```c
void __fastcall CRegistry::SetMultiStringValue(
        CRegistry *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        ulong a4)
{
  unsigned int v4; // eax
  HKEY *v5; // r10
  const BYTE *lpData; // r11
  LSTATUS v7; // eax
  ulong pExceptionObject; // [rsp+58h] [rbp+20h] BYREF

  pExceptionObject = a4;
  if ( *((_DWORD *)this + 10) )
  {
    pExceptionObject = *((_DWORD *)this + 10);
    throw &pExceptionObject;
  }
  v4 = MStrLen(a3);
  v7 = RegSetValueExW(*v5, L"Groups", 0, 7u, lpData, 2 * v4);
  if ( v7 )
  {
    pExceptionObject = v7;
    throw &pExceptionObject;
  }
}

```

## disassembly

```asm
0x18002a65c  mov     [rsp+pExceptionObject], r9d
0x18002a661  sub     rsp, 38h
0x18002a665  mov     eax, [rcx+28h]
0x18002a668  mov     r11, r8
0x18002a66b  mov     r10, rcx
0x18002a66e  test    eax, eax
0x18002a670  jz      short loc_18002A688
0x18002a672  lea     rdx, _TI1K; pThrowInfo
0x18002a679  mov     [rsp+38h+pExceptionObject], eax
0x18002a67d  lea     rcx, [rsp+38h+pExceptionObject]; pExceptionObject
0x18002a682  call    _CxxThrowException_0
0x18002a688  mov     rcx, r11; unsigned __int16 *
0x18002a68b  call    ?MStrLen@@YAKPEBG@Z; MStrLen(ushort const *)
0x18002a690  mov     rcx, [r10]; hKey
0x18002a693  lea     rdx, aGroups_1; "Groups"
0x18002a69a  add     eax, eax
0x18002a69c  mov     r9d, 7; dwType
0x18002a6a2  mov     [rsp+38h+cbData], eax; cbData
0x18002a6a6  xor     r8d, r8d; Reserved
0x18002a6a9  mov     [rsp+38h+lpData], r11; lpData
0x18002a6ae  call    cs:__imp_RegSetValueExW
0x18002a6b4  test    eax, eax
0x18002a6b6  jz      short loc_18002A6CE
0x18002a6b8  lea     rdx, _TI1K; pThrowInfo
0x18002a6bf  mov     [rsp+38h+pExceptionObject], eax
0x18002a6c3  lea     rcx, [rsp+38h+pExceptionObject]; pExceptionObject
0x18002a6c8  call    _CxxThrowException_0
0x18002a6ce  add     rsp, 38h
0x18002a6d2  retn
```
