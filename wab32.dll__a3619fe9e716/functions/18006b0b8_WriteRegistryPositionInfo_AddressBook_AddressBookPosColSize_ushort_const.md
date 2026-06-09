# WriteRegistryPositionInfo(AddressBook *,_AddressBookPosColSize *,ushort const *)

- ea: `0x18006b0b8`
- end: `0x18006b17b`
- name: `?WriteRegistryPositionInfo@@YAHPEAVAddressBook@@PEAU_AddressBookPosColSize@@PEBG@Z`
- size: `195`
- prototype: `int(struct AddressBook *, struct _AddressBookPosColSize *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18005f994`

## callees

- `0x18006b0b8`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x18006b168`
- `ADVAPI32!RegCloseKey` at `0x18006b168`
- `ADVAPI32!RegCreateKeyExW` at `0x18006b124`
- `ADVAPI32!RegCreateKeyExW` at `0x18006b124`
- `ADVAPI32!RegSetValueExW` at `0x18006b14e`
- `ADVAPI32!RegSetValueExW` at `0x18006b14e`

## pseudocode

```c
__int64 __fastcall WriteRegistryPositionInfo(struct AddressBook *a1, const BYTE *a2, const unsigned __int16 *a3)
{
  unsigned int v3; // ebx
  __int64 v5; // rcx
  HKEY hKey; // [rsp+60h] [rbp+8h] BYREF
  const unsigned __int16 *dwDisposition; // [rsp+70h] [rbp+18h] BYREF

  dwDisposition = a3;
  v3 = 0;
  hKey = 0;
  if ( !a1 || (v5 = *((_QWORD *)a1 + 132)) == 0 )
    v5 = -2147483647;
  LODWORD(dwDisposition) = 0;
  if ( a2 )
  {
    if ( !RegCreateKeyExW(
            (HKEY)v5,
            L"Software\\Microsoft\\WAB\\WAB Sort State",
            0,
            0,
            0,
            0xF003Fu,
            0,
            &hKey,
            (LPDWORD)&dwDisposition)
      && !RegSetValueExW(hKey, L"FindPosition", 0, 3u, a2, 0x4Cu) )
    {
      v3 = 1;
    }
    if ( hKey )
      RegCloseKey(hKey);
  }
  return v3;
}

```

## disassembly

```asm
0x18006b0b8  mov     [rsp+arg_8], rbx
0x18006b0bd  mov     [rsp+dwDisposition], r8
0x18006b0c2  push    rdi
0x18006b0c3  sub     rsp, 50h
0x18006b0c7  xor     ebx, ebx
0x18006b0c9  mov     rdi, rdx
0x18006b0cc  mov     [rsp+58h+hKey], rbx
0x18006b0d1  test    rcx, rcx
0x18006b0d4  jz      short loc_18006B0E2
0x18006b0d6  mov     rcx, [rcx+420h]
0x18006b0dd  test    rcx, rcx
0x18006b0e0  jnz     short loc_18006B0E9
0x18006b0e2  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18006b0e9  mov     dword ptr [rsp+58h+dwDisposition], ebx
0x18006b0ed  test    rdi, rdi
0x18006b0f0  jz      short loc_18006B16E
0x18006b0f2  lea     rax, [rsp+58h+dwDisposition]
0x18006b0f7  xor     r9d, r9d; lpClass
0x18006b0fa  mov     [rsp+58h+lpdwDisposition], rax; lpdwDisposition
0x18006b0ff  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\WAB\\WAB Sort Stat"...
0x18006b106  lea     rax, [rsp+58h+hKey]
0x18006b10b  xor     r8d, r8d; Reserved
0x18006b10e  mov     [rsp+58h+phkResult], rax; phkResult
0x18006b113  mov     [rsp+58h+lpSecurityAttributes], rbx; lpSecurityAttributes
0x18006b118  mov     [rsp+58h+samDesired], 0F003Fh; samDesired
0x18006b120  mov     [rsp+58h+dwOptions], ebx; dwOptions
0x18006b124  call    cs:__imp_RegCreateKeyExW
0x18006b12a  test    eax, eax
0x18006b12c  jnz     short loc_18006B15E
0x18006b12e  mov     rcx, [rsp+58h+hKey]; hKey
0x18006b133  lea     r9d, [rax+3]; dwType
0x18006b137  mov     [rsp+58h+samDesired], 4Ch ; 'L'; cbData
0x18006b13f  lea     rdx, aFindposition; "FindPosition"
0x18006b146  xor     r8d, r8d; Reserved
0x18006b149  mov     qword ptr [rsp+58h+dwOptions], rdi; lpData
0x18006b14e  call    cs:__imp_RegSetValueExW
0x18006b154  test    eax, eax
0x18006b156  mov     ecx, 1
0x18006b15b  cmovz   ebx, ecx
0x18006b15e  mov     rcx, [rsp+58h+hKey]; hKey
0x18006b163  test    rcx, rcx
0x18006b166  jz      short loc_18006B16E
0x18006b168  call    cs:__imp_RegCloseKey
0x18006b16e  mov     eax, ebx
0x18006b170  mov     rbx, [rsp+58h+arg_8]
0x18006b175  add     rsp, 50h
0x18006b179  pop     rdi
0x18006b17a  retn
```
