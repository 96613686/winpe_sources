# ReadOcspReadDirectoryRegistrySetting(HKEY__ *)

- ea: `0x180069980`
- end: `0x180069a33`
- name: `?ReadOcspReadDirectoryRegistrySetting@@YAXPEAUHKEY__@@@Z`
- size: `179`
- prototype: `void __fastcall(HKEY hKey)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180069a3c`

## callees

- `0x180069980`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180069a19`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180069a19`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800699dd`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800699dd`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800699bd`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180069a0c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800699bd`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180069a0c`

## string_xrefs

- `0x1800699ab`: `OcspReadDirectory`
- `0x1800699fd`: `OcspReadDirectory`

## pseudocode

```c
void __fastcall ReadOcspReadDirectoryRegistrySetting(HKEY hKey)
{
  HLOCAL lpData; // rbx
  SIZE_T uBytes; // [rsp+48h] [rbp+10h] BYREF
  DWORD Type; // [rsp+50h] [rbp+18h] BYREF

  LODWORD(uBytes) = 0;
  Type = 0;
  if ( !RegQueryValueExW(hKey, L"OcspReadDirectory", 0, &Type, 0, (LPDWORD)&uBytes) )
  {
    if ( (_DWORD)uBytes )
    {
      if ( Type == 1 )
      {
        lpData = LocalAlloc(0x40u, (unsigned int)uBytes);
        if ( lpData )
        {
          if ( RegQueryValueExW(hKey, L"OcspReadDirectory", 0, &Type, (LPBYTE)lpData, (LPDWORD)&uBytes) )
            LocalFree(lpData);
          else
            g_pszOcspReadDirectory = lpData;
        }
      }
    }
  }
}

```

## disassembly

```asm
0x180069980  mov     r11, rsp
0x180069983  mov     [r11+8], rbx
0x180069987  push    rdi
0x180069988  sub     rsp, 30h
0x18006998c  lea     rax, [r11+10h]
0x180069990  mov     dword ptr [rsp+38h+uBytes], 0
0x180069998  mov     [r11-10h], rax
0x18006999c  lea     r9, [r11+18h]; lpType
0x1800699a0  xor     r8d, r8d; lpReserved
0x1800699a3  mov     qword ptr [r11-18h], 0
0x1800699ab  lea     rdx, aOcspreaddirect; "OcspReadDirectory"
0x1800699b2  mov     [rsp+38h+Type], 0
0x1800699ba  mov     rdi, rcx
0x1800699bd  call    cs:__imp_RegQueryValueExW
0x1800699c3  test    eax, eax
0x1800699c5  jnz     short loc_180069A28
0x1800699c7  mov     eax, dword ptr [rsp+38h+uBytes]
0x1800699cb  test    eax, eax
0x1800699cd  jz      short loc_180069A28
0x1800699cf  cmp     [rsp+38h+Type], 1
0x1800699d4  jnz     short loc_180069A28
0x1800699d6  mov     edx, eax; uBytes
0x1800699d8  mov     ecx, 40h ; '@'; uFlags
0x1800699dd  call    cs:__imp_LocalAlloc
0x1800699e3  mov     rbx, rax
0x1800699e6  test    rax, rax
0x1800699e9  jz      short loc_180069A28
0x1800699eb  lea     rax, [rsp+38h+uBytes]
0x1800699f0  xor     r8d, r8d; lpReserved
0x1800699f3  mov     [rsp+38h+lpcbData], rax; lpcbData
0x1800699f8  lea     r9, [rsp+38h+Type]; lpType
0x1800699fd  lea     rdx, aOcspreaddirect; "OcspReadDirectory"
0x180069a04  mov     [rsp+38h+lpData], rbx; lpData
0x180069a09  mov     rcx, rdi; hKey
0x180069a0c  call    cs:__imp_RegQueryValueExW
0x180069a12  test    eax, eax
0x180069a14  jz      short loc_180069A21
0x180069a16  mov     rcx, rbx; hMem
0x180069a19  call    cs:__imp_LocalFree
0x180069a1f  jmp     short loc_180069A28
0x180069a21  mov     cs:?g_pszOcspReadDirectory@@3PEAGEA, rbx; ushort * g_pszOcspReadDirectory
0x180069a28  mov     rbx, [rsp+38h+arg_0]
0x180069a2d  add     rsp, 30h
0x180069a31  pop     rdi
0x180069a32  retn
```
