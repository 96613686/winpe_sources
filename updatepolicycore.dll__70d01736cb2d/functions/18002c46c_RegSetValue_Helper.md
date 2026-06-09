# RegSetValue_Helper

- ea: `0x18002c46c`
- end: `0x18002c4fb`
- name: `RegSetValue_Helper`
- size: `143`
- prototype: `__int64 __fastcall(__int64, const WCHAR *, __int64, const WCHAR *, DWORD dwType, BYTE *lpData, DWORD cbData)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18002c504`
- `0x18002c554`

## callees

- `0x18002c374`
- `0x18002c46c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002c4e8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002c4e8`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002c4b8`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002c4b8`

## pseudocode

```c
__int64 __fastcall RegSetValue_Helper(
        __int64 a1,
        const WCHAR *a2,
        __int64 a3,
        const WCHAR *a4,
        DWORD dwType,
        BYTE *lpData,
        DWORD cbData)
{
  int v8; // ebx
  LSTATUS v9; // eax
  HKEY hKey; // [rsp+50h] [rbp+18h] BYREF

  hKey = 0;
  v8 = RegCreateKeyHelperPrivate(a1, a2, a3, &hKey);
  if ( v8 >= 0 )
  {
    v9 = RegSetValueExW(hKey, a4, 0, dwType, lpData, cbData);
    if ( v9 )
    {
      v8 = (unsigned __int16)v9 | 0x80070000;
      if ( v9 <= 0 )
        v8 = v9;
    }
  }
  if ( hKey != HKEY_LOCAL_MACHINE && hKey )
    RegCloseKey(hKey);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18002c46c  mov     rax, rsp
0x18002c46f  mov     [rax+8], rbx
0x18002c473  mov     [rax+18h], r8
0x18002c477  push    rsi
0x18002c478  sub     rsp, 30h
0x18002c47c  mov     rsi, r9
0x18002c47f  mov     qword ptr [rax+18h], 0
0x18002c487  lea     r9, [rax+18h]
0x18002c48b  call    RegCreateKeyHelperPrivate
0x18002c490  mov     ebx, eax
0x18002c492  test    eax, eax
0x18002c494  js      short loc_18002C4D0
0x18002c496  mov     ecx, [rsp+38h+arg_30]
0x18002c49a  xor     r8d, r8d; Reserved
0x18002c49d  mov     r9d, [rsp+38h+dwType]; dwType
0x18002c4a2  mov     rdx, rsi; lpValueName
0x18002c4a5  mov     [rsp+38h+cbData], ecx; cbData
0x18002c4a9  mov     rcx, [rsp+38h+arg_28]
0x18002c4ae  mov     [rsp+38h+lpData], rcx; lpData
0x18002c4b3  mov     rcx, [rsp+38h+hKey]; hKey
0x18002c4b8  call    cs:__imp_RegSetValueExW
0x18002c4be  test    eax, eax
0x18002c4c0  jz      short loc_18002C4D0
0x18002c4c2  movzx   ebx, ax
0x18002c4c5  or      ebx, 80070000h
0x18002c4cb  test    eax, eax
0x18002c4cd  cmovle  ebx, eax
0x18002c4d0  cmp     [rsp+38h+hKey], 0FFFFFFFF80000002h
0x18002c4d9  jz      short loc_18002C4EE
0x18002c4db  cmp     [rsp+38h+hKey], 0
0x18002c4e1  jz      short loc_18002C4EE
0x18002c4e3  mov     rcx, [rsp+38h+hKey]; hKey
0x18002c4e8  call    cs:__imp_RegCloseKey
0x18002c4ee  mov     eax, ebx
0x18002c4f0  mov     rbx, [rsp+38h+arg_0]
0x18002c4f5  add     rsp, 30h
0x18002c4f9  pop     rsi
0x18002c4fa  retn
```
