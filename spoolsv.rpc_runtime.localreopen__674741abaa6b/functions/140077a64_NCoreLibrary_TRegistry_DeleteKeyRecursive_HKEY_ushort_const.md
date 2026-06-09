# NCoreLibrary::TRegistry::DeleteKeyRecursive(HKEY__ *,ushort const *)

- ea: `0x140077a64`
- end: `0x140077b8c`
- name: `?DeleteKeyRecursive@TRegistry@NCoreLibrary@@CAJPEAUHKEY__@@PEBG@Z`
- size: `296`
- prototype: `__int64 __fastcall(HKEY, const unsigned __int16 *)`
- caller_count: `4`
- callee_count: `3`
- tags: `file_ops, registry_config`

## callers

- `0x14002bd88`
- `0x1400671fc`
- `0x140067ca8`
- `0x140077a64`

## callees

- `0x14002cd50`
- `0x140077a64`
- `0x140077e08`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140077a94`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140077a94`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x140077b65`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x140077b65`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x140077b02`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x140077b02`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140077b3e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140077b3e`

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
0x140077a64  mov     [rsp-18h+arg_0], rbx
0x140077a69  push    rbp
0x140077a6a  push    rsi
0x140077a6b  push    r14
0x140077a6d  mov     rbp, rsp
0x140077a70  sub     rsp, 50h
0x140077a74  lea     rax, [rbp+hKey]
0x140077a78  mov     [rbp+hKey], 0
0x140077a80  mov     r9d, 0F003Fh; samDesired
0x140077a86  mov     [rsp+50h+phkResult], rax; phkResult
0x140077a8b  xor     r8d, r8d; ulOptions
0x140077a8e  mov     rsi, rdx
0x140077a91  mov     r14, rcx
0x140077a94  call    cs:__imp_RegOpenKeyExW
0x140077a9b  nop     dword ptr [rax+rax+00h]
0x140077aa0  mov     ebx, eax
0x140077aa2  test    eax, eax
0x140077aa4  jnz     loc_140077B35
0x140077aaa  mov     rcx, [rbp+hKey]; HKEY
0x140077aae  lea     r9, [rbp+cchName]; unsigned int *
0x140077ab2  lea     r8, [rbp+lpName]; unsigned __int16 **
0x140077ab6  mov     [rbp+lpName], 0
0x140077abe  mov     [rbp+cchName], 0
0x140077ac5  call    ?GetSubkeyBuffer@TRegistry@NCoreLibrary@@CAJPEAUHKEY__@@PEBGPEAPEAGPEAK@Z; NCoreLibrary::TRegistry::GetSubkeyBuffer(HKEY__ *,ushort const *,ushort * *,ulong *)
0x140077aca  mov     ebx, eax
0x140077acc  test    eax, eax
0x140077ace  jnz     short loc_140077B35
0x140077ad0  mov     r8, [rbp+lpName]; lpName
0x140077ad4  lea     r9, [rbp+cchName]; lpcchName
0x140077ad8  mov     rcx, [rbp+hKey]; hKey
0x140077adc  xor     edx, edx; dwIndex
0x140077ade  mov     [rsp+50h+lpftLastWriteTime], 0; lpftLastWriteTime
0x140077ae7  mov     [rsp+50h+lpcchClass], 0; lpcchClass
0x140077af0  mov     [rsp+50h+lpClass], 0; lpClass
0x140077af9  mov     [rsp+50h+phkResult], 0; lpReserved
0x140077b02  call    cs:__imp_RegEnumKeyExW
0x140077b09  nop     dword ptr [rax+rax+00h]
0x140077b0e  mov     ebx, eax
0x140077b10  test    eax, eax
0x140077b12  jnz     short loc_140077B24
0x140077b14  mov     rdx, [rbp+lpName]; unsigned __int16 *
0x140077b18  mov     rcx, [rbp+hKey]; HKEY
0x140077b1c  call    ?DeleteKeyRecursive@TRegistry@NCoreLibrary@@CAJPEAUHKEY__@@PEBG@Z; NCoreLibrary::TRegistry::DeleteKeyRecursive(HKEY__ *,ushort const *)
0x140077b21  movzx   ebx, ax
0x140077b24  mov     rcx, [rbp+lpName]; void *
0x140077b28  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140077b2d  test    ebx, ebx
0x140077b2f  jz      loc_140077AAA
0x140077b35  mov     rcx, [rbp+hKey]; hKey
0x140077b39  test    rcx, rcx
0x140077b3c  jz      short loc_140077B4A
0x140077b3e  call    cs:__imp_RegCloseKey
0x140077b45  nop     dword ptr [rax+rax+00h]
0x140077b4a  xor     eax, eax
0x140077b4c  cmp     ebx, 103h
0x140077b52  cmovnz  eax, ebx
0x140077b55  test    eax, eax
0x140077b57  jnz     short loc_140077B73
0x140077b59  xor     r9d, r9d; Reserved
0x140077b5c  xor     r8d, r8d; samDesired
0x140077b5f  mov     rdx, rsi; lpSubKey
0x140077b62  mov     rcx, r14; hKey
0x140077b65  call    cs:__imp_RegDeleteKeyExW
0x140077b6c  nop     dword ptr [rax+rax+00h]
0x140077b71  test    eax, eax
0x140077b73  jle     short loc_140077B7D
0x140077b75  movzx   eax, ax
0x140077b78  or      eax, 80070000h
0x140077b7d  mov     rbx, [rsp+50h+arg_0]
0x140077b82  add     rsp, 50h
0x140077b86  pop     r14
0x140077b88  pop     rsi
0x140077b89  pop     rbp
0x140077b8a  retn
```
