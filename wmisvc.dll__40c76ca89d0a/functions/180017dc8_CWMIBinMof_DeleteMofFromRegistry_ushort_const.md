# CWMIBinMof::DeleteMofFromRegistry(ushort const *)

- ea: `0x180017dc8`
- end: `0x180017e36`
- name: `?DeleteMofFromRegistry@CWMIBinMof@@QEAAJPEBG@Z`
- size: `110`
- prototype: `__int64 __fastcall(CWMIBinMof *this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180002478`
- `0x180017fd8`

## callees

- `0x180017dc8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180017e02`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180017e02`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180017e16`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180017e16`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180017e23`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180017e23`

## pseudocode

```c
__int64 __fastcall CWMIBinMof::DeleteMofFromRegistry(CWMIBinMof *this, const unsigned __int16 *a2)
{
  unsigned int v3; // ebx
  HKEY hKey; // [rsp+40h] [rbp+8h] BYREF

  hKey = 0;
  v3 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\WBEM\\WDM", 0, 0x2000000u, &hKey);
  if ( !v3 )
  {
    v3 = RegDeleteValueW(hKey, a2);
    RegCloseKey(hKey);
  }
  return v3;
}

```

## disassembly

```asm
0x180017dc8  mov     r11, rsp
0x180017dcb  mov     [r11+10h], rbx
0x180017dcf  mov     [r11+8], rcx
0x180017dd3  push    rdi
0x180017dd4  sub     rsp, 30h
0x180017dd8  mov     rdi, rdx
0x180017ddb  mov     qword ptr [r11+8], 0
0x180017de3  lea     rax, [r11+8]
0x180017de7  mov     r9d, 2000000h; samDesired
0x180017ded  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\WBEM\\WDM"
0x180017df4  mov     [r11-18h], rax
0x180017df8  xor     r8d, r8d; ulOptions
0x180017dfb  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180017e02  call    cs:__imp_RegOpenKeyExW
0x180017e08  mov     ebx, eax
0x180017e0a  test    eax, eax
0x180017e0c  jnz     short loc_180017E29
0x180017e0e  mov     rcx, [rsp+38h+hKey]; hKey
0x180017e13  mov     rdx, rdi; lpValueName
0x180017e16  call    cs:__imp_RegDeleteValueW
0x180017e1c  mov     rcx, [rsp+38h+hKey]; hKey
0x180017e21  mov     ebx, eax
0x180017e23  call    cs:__imp_RegCloseKey
0x180017e29  mov     eax, ebx
0x180017e2b  mov     rbx, [rsp+38h+arg_8]
0x180017e30  add     rsp, 30h
0x180017e34  pop     rdi
0x180017e35  retn
```
