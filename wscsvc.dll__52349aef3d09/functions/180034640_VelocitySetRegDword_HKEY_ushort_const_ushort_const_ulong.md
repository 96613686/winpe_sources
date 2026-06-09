# VelocitySetRegDword(HKEY__ *,ushort const *,ushort const *,ulong)

- ea: `0x180034640`
- end: `0x1800346dc`
- name: `?VelocitySetRegDword@@YAHPEAUHKEY__@@PEBG1K@Z`
- size: `156`
- prototype: `int(HKEY, const unsigned __int16 *, const unsigned __int16 *, unsigned int)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180034860`
- `0x1800348d0`

## callees

- `0x180034640`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003468e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003468e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800346c3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800346c3`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800346b6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800346b6`

## pseudocode

```c
__int64 __fastcall VelocitySetRegDword(HKEY a1, const unsigned __int16 *a2, const unsigned __int16 *a3)
{
  unsigned int v3; // edi
  LSTATUS v5; // ebx
  BYTE Data[24]; // [rsp+50h] [rbp-18h] BYREF
  HKEY hKey; // [rsp+70h] [rbp+8h] BYREF

  v3 = 0;
  *(_DWORD *)Data = 1;
  hKey = 0;
  if ( !RegCreateKeyExW(HKEY_LOCAL_MACHINE, a2, 0, 0, 0, 0xF003Fu, 0, &hKey, 0) )
  {
    v5 = RegSetValueExW(hKey, a3, 0, 4u, Data, 4u);
    RegCloseKey(hKey);
    LOBYTE(v3) = v5 == 0;
  }
  return v3;
}

```

## disassembly

```asm
0x180034640  mov     r11, rsp
0x180034643  mov     [r11+10h], rbx
0x180034647  mov     [r11+8], rcx
0x18003464b  push    rdi
0x18003464c  sub     rsp, 60h
0x180034650  xor     edi, edi
0x180034652  mov     dword ptr [rsp+68h+Data], 1
0x18003465a  mov     [r11-28h], rdi
0x18003465e  lea     rax, [r11+8]
0x180034662  mov     [r11-30h], rax
0x180034666  mov     rbx, r8
0x180034669  mov     [r11-38h], rdi
0x18003466d  xor     r9d, r9d; lpClass
0x180034670  mov     [rsp+68h+samDesired], 0F003Fh; samDesired
0x180034678  xor     r8d, r8d; Reserved
0x18003467b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180034682  mov     [rsp+68h+dwOptions], edi; dwOptions
0x180034686  mov     qword ptr [r11+8], 0
0x18003468e  call    cs:__imp_RegCreateKeyExW
0x180034694  test    eax, eax
0x180034696  jnz     short loc_1800346CF
0x180034698  mov     rcx, [rsp+68h+hKey]; hKey
0x18003469d  lea     r9d, [rdi+4]; dwType
0x1800346a1  lea     rax, [rsp+68h+Data]
0x1800346a6  mov     [rsp+68h+samDesired], r9d; cbData
0x1800346ab  xor     r8d, r8d; Reserved
0x1800346ae  mov     qword ptr [rsp+68h+dwOptions], rax; lpData
0x1800346b3  mov     rdx, rbx; lpValueName
0x1800346b6  call    cs:__imp_RegSetValueExW
0x1800346bc  mov     rcx, [rsp+68h+hKey]; hKey
0x1800346c1  mov     ebx, eax
0x1800346c3  call    cs:__imp_RegCloseKey
0x1800346c9  test    ebx, ebx
0x1800346cb  setz    dil
0x1800346cf  mov     rbx, [rsp+68h+arg_8]
0x1800346d4  mov     eax, edi
0x1800346d6  add     rsp, 60h
0x1800346da  pop     rdi
0x1800346db  retn
```
