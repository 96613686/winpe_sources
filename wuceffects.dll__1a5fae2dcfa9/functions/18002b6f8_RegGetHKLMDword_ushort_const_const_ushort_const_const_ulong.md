# RegGetHKLMDword(ushort const * const,ushort const * const,ulong *)

- ea: `0x18002b6f8`
- end: `0x18002b765`
- name: `?RegGetHKLMDword@@YA_NQEBG0PEAK@Z`
- size: `109`
- prototype: `bool(const unsigned __int16 *const, const unsigned __int16 *const, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002b5cc`

## callees

- `0x18002b67c`
- `0x18002b6f8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002b734`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002b734`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002b752`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002b752`

## pseudocode

```c
bool __fastcall RegGetHKLMDword(const unsigned __int16 *const a1, const unsigned __int16 *const a2, unsigned int *a3)
{
  bool Dword; // bl
  const unsigned __int16 *v5; // rdx
  HKEY hKey; // [rsp+48h] [rbp+10h] BYREF

  hKey = 0;
  Dword = 0;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Avalon.Graphics", 0, 0x20019u, &hKey) )
  {
    Dword = RegGetDword(hKey, v5, a3);
    RegCloseKey(hKey);
  }
  return Dword;
}

```

## disassembly

```asm
0x18002b6f8  mov     r11, rsp
0x18002b6fb  mov     [r11+8], rbx
0x18002b6ff  mov     [r11+10h], rdx
0x18002b703  push    rdi
0x18002b704  sub     rsp, 30h
0x18002b708  mov     rdi, r8
0x18002b70b  mov     qword ptr [r11+10h], 0
0x18002b713  lea     rax, [r11+10h]
0x18002b717  xor     r8d, r8d; ulOptions
0x18002b71a  mov     r9d, 20019h; samDesired
0x18002b720  mov     [r11-18h], rax
0x18002b724  lea     rdx, SubKey; "Software\\Microsoft\\Avalon.Graphics"
0x18002b72b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002b732  xor     bl, bl
0x18002b734  call    cs:__imp_RegOpenKeyExW
0x18002b73a  test    eax, eax
0x18002b73c  jnz     short loc_18002B758
0x18002b73e  mov     rcx, [rsp+38h+hKey]; HKEY
0x18002b743  mov     r8, rdi; unsigned int *
0x18002b746  call    ?RegGetDword@@YA_NQEAUHKEY__@@QEBGPEAK@Z; RegGetDword(HKEY__ * const,ushort const * const,ulong *)
0x18002b74b  mov     rcx, [rsp+38h+hKey]; hKey
0x18002b750  mov     bl, al
0x18002b752  call    cs:__imp_RegCloseKey
0x18002b758  mov     al, bl
0x18002b75a  mov     rbx, [rsp+38h+arg_0]
0x18002b75f  add     rsp, 30h
0x18002b763  pop     rdi
0x18002b764  retn
```
