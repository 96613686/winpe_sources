# NCoreLibrary::TRegistry::DeleteKeyRecursive(HKEY__ *,ushort const *)

- ea: `0x140070b04`
- end: `0x140070c13`
- name: `?DeleteKeyRecursive@TRegistry@NCoreLibrary@@CAJPEAUHKEY__@@PEBG@Z`
- size: `271`
- prototype: `__int64 __fastcall(HKEY, const unsigned __int16 *)`
- caller_count: `4`
- callee_count: `3`
- tags: `file_ops, registry_config`

## callers

- `0x140029898`
- `0x140061280`
- `0x140061cfc`
- `0x140070b04`

## callees

- `0x14002a870`
- `0x140070b04`
- `0x140070e90`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140070b34`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140070b34`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x140070bf3`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x140070bf3`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x140070b9c`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x140070b9c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140070bd2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140070bd2`

## pseudocode

```c
LSTATUS __fastcall NCoreLibrary::TRegistry::DeleteKeyRecursive(HKEY a1, const unsigned __int16 *a2)
{
  const unsigned __int16 *v4; // rdx
  LSTATUS SubkeyBuffer; // ebx
  unsigned __int64 v6; // rdx
  LSTATUS result; // eax
  bool v8; // cc
  LPWSTR lpName; // [rsp+40h] [rbp-10h] BYREF
  DWORD cchName; // [rsp+80h] [rbp+30h] BYREF
  HKEY hKey; // [rsp+88h] [rbp+38h] BYREF

  hKey = 0;
  SubkeyBuffer = RegOpenKeyExW(a1, a2, 0, 0xF003Fu, &hKey);
  while ( !SubkeyBuffer )
  {
    lpName = 0;
    cchName = 0;
    SubkeyBuffer = NCoreLibrary::TRegistry::GetSubkeyBuffer(hKey, v4, &lpName, &cchName);
    if ( SubkeyBuffer )
      break;
    SubkeyBuffer = RegEnumKeyExW(hKey, 0, lpName, &cchName, 0, 0, 0, 0);
    if ( !SubkeyBuffer )
      SubkeyBuffer = (unsigned __int16)NCoreLibrary::TRegistry::DeleteKeyRecursive(hKey, lpName);
    operator delete(lpName, v6);
  }
  if ( hKey )
    RegCloseKey(hKey);
  result = 0;
  if ( SubkeyBuffer != 259 )
    result = SubkeyBuffer;
  v8 = result <= 0;
  if ( !result )
  {
    result = RegDeleteKeyExW(a1, a2, 0, 0);
    v8 = result <= 0;
  }
  if ( !v8 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x140070b04  mov     [rsp-18h+arg_0], rbx
0x140070b09  push    rbp
0x140070b0a  push    rsi
0x140070b0b  push    r14
0x140070b0d  mov     rbp, rsp
0x140070b10  sub     rsp, 50h
0x140070b14  lea     rax, [rbp+hKey]
0x140070b18  mov     [rbp+hKey], 0
0x140070b20  mov     r9d, 0F003Fh; samDesired
0x140070b26  mov     [rsp+50h+phkResult], rax; phkResult
0x140070b2b  xor     r8d, r8d; ulOptions
0x140070b2e  mov     rsi, rdx
0x140070b31  mov     r14, rcx
0x140070b34  call    cs:__imp_RegOpenKeyExW
0x140070b3a  mov     ebx, eax
0x140070b3c  test    eax, eax
0x140070b3e  jnz     loc_140070BC9
0x140070b44  mov     rcx, [rbp+hKey]; HKEY
0x140070b48  lea     r9, [rbp+cchName]; unsigned int *
0x140070b4c  lea     r8, [rbp+lpName]; unsigned __int16 **
0x140070b50  mov     [rbp+lpName], 0
0x140070b58  mov     [rbp+cchName], 0
0x140070b5f  call    ?GetSubkeyBuffer@TRegistry@NCoreLibrary@@CAJPEAUHKEY__@@PEBGPEAPEAGPEAK@Z; NCoreLibrary::TRegistry::GetSubkeyBuffer(HKEY__ *,ushort const *,ushort * *,ulong *)
0x140070b64  mov     ebx, eax
0x140070b66  test    eax, eax
0x140070b68  jnz     short loc_140070BC9
0x140070b6a  mov     r8, [rbp+lpName]; lpName
0x140070b6e  lea     r9, [rbp+cchName]; lpcchName
0x140070b72  mov     rcx, [rbp+hKey]; hKey
0x140070b76  xor     edx, edx; dwIndex
0x140070b78  mov     [rsp+50h+lpftLastWriteTime], 0; lpftLastWriteTime
0x140070b81  mov     [rsp+50h+lpcchClass], 0; lpcchClass
0x140070b8a  mov     [rsp+50h+lpClass], 0; lpClass
0x140070b93  mov     [rsp+50h+phkResult], 0; lpReserved
0x140070b9c  call    cs:__imp_RegEnumKeyExW
0x140070ba2  mov     ebx, eax
0x140070ba4  test    eax, eax
0x140070ba6  jnz     short loc_140070BB8
0x140070ba8  mov     rdx, [rbp+lpName]; unsigned __int16 *
0x140070bac  mov     rcx, [rbp+hKey]; HKEY
0x140070bb0  call    ?DeleteKeyRecursive@TRegistry@NCoreLibrary@@CAJPEAUHKEY__@@PEBG@Z; NCoreLibrary::TRegistry::DeleteKeyRecursive(HKEY__ *,ushort const *)
0x140070bb5  movzx   ebx, ax
0x140070bb8  mov     rcx, [rbp+lpName]; void *
0x140070bbc  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140070bc1  test    ebx, ebx
0x140070bc3  jz      loc_140070B44
0x140070bc9  mov     rcx, [rbp+hKey]; hKey
0x140070bcd  test    rcx, rcx
0x140070bd0  jz      short loc_140070BD8
0x140070bd2  call    cs:__imp_RegCloseKey
0x140070bd8  xor     eax, eax
0x140070bda  cmp     ebx, 103h
0x140070be0  cmovnz  eax, ebx
0x140070be3  test    eax, eax
0x140070be5  jnz     short loc_140070BFB
0x140070be7  xor     r9d, r9d; Reserved
0x140070bea  xor     r8d, r8d; samDesired
0x140070bed  mov     rdx, rsi; lpSubKey
0x140070bf0  mov     rcx, r14; hKey
0x140070bf3  call    cs:__imp_RegDeleteKeyExW
0x140070bf9  test    eax, eax
0x140070bfb  jle     short loc_140070C05
0x140070bfd  movzx   eax, ax
0x140070c00  or      eax, 80070000h
0x140070c05  mov     rbx, [rsp+50h+arg_0]
0x140070c0a  add     rsp, 50h
0x140070c0e  pop     r14
0x140070c10  pop     rsi
0x140070c11  pop     rbp
0x140070c12  retn
```
