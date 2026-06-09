# OpenItemKey(_GUID const *,int,ulong,HKEY__ * *)

- ea: `0x180019948`
- end: `0x1800199f1`
- name: `?OpenItemKey@@YAHPEBU_GUID@@HKPEAPEAUHKEY__@@@Z`
- size: `169`
- prototype: `int(const struct _GUID *, int, unsigned int, HKEY *)`
- caller_count: `7`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180015cf0`
- `0x1800161b4`
- `0x180016270`
- `0x1800163a0`
- `0x1800165d0`
- `0x180016660`
- `0x180019ae0`

## callees

- `0x180019858`
- `0x180019948`
- `0x180029280`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x1800199cc`
- `ADVAPI32!RegOpenKeyExW` at `0x1800199cc`
- `ADVAPI32!RegCreateKeyExW` at `0x1800199b3`
- `ADVAPI32!RegCreateKeyExW` at `0x1800199b3`

## pseudocode

```c
_BOOL8 __fastcall OpenItemKey(const struct _GUID *a1, int a2, unsigned int a3, HKEY *a4)
{
  LSTATUS Key; // eax
  DWORD dwDisposition[4]; // [rsp+50h] [rbp-248h] BYREF
  WCHAR SubKey[264]; // [rsp+60h] [rbp-238h] BYREF

  if ( !ItemKeyNameFromCookie(a1, SubKey, a3) )
    return 0;
  if ( a2 )
  {
    dwDisposition[0] = 0;
    Key = RegCreateKeyExW(HKEY_CURRENT_USER, SubKey, 0, 0, 0, a3, 0, a4, dwDisposition);
  }
  else
  {
    Key = RegOpenKeyExW(HKEY_CURRENT_USER, SubKey, 0, a3, a4);
  }
  return Key == 0;
}

```

## disassembly

```asm
0x180019948  push    rbx
0x18001994a  push    rsi
0x18001994b  push    rdi
0x18001994c  sub     rsp, 280h
0x180019953  mov     rax, cs:__security_cookie
0x18001995a  xor     rax, rsp
0x18001995d  mov     [rsp+298h+var_28], rax
0x180019965  mov     esi, edx
0x180019967  mov     rdi, r9
0x18001996a  lea     rdx, [rsp+298h+SubKey]; unsigned __int16 *
0x18001996f  mov     ebx, r8d
0x180019972  call    ?ItemKeyNameFromCookie@@YAHPEBU_GUID@@PEAGK@Z; ItemKeyNameFromCookie(_GUID const *,ushort *,ulong)
0x180019977  test    eax, eax
0x180019979  jz      short loc_1800199D4
0x18001997b  xor     r8d, r8d; ulOptions
0x18001997e  lea     rdx, [rsp+298h+SubKey]; lpSubKey
0x180019983  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18001998a  test    esi, esi
0x18001998c  jz      short loc_1800199C4
0x18001998e  lea     rax, [rsp+298h+dwDisposition]
0x180019993  mov     [rsp+298h+dwDisposition], r8d
0x180019998  mov     [rsp+298h+lpdwDisposition], rax; lpdwDisposition
0x18001999d  xor     r9d, r9d; lpClass
0x1800199a0  mov     [rsp+298h+phkResult], rdi; phkResult
0x1800199a5  mov     [rsp+298h+lpSecurityAttributes], r8; lpSecurityAttributes
0x1800199aa  mov     [rsp+298h+samDesired], ebx; samDesired
0x1800199ae  mov     [rsp+298h+dwOptions], r8d; dwOptions
0x1800199b3  call    cs:__imp_RegCreateKeyExW
0x1800199b9  xor     ecx, ecx
0x1800199bb  test    eax, eax
0x1800199bd  setz    cl
0x1800199c0  mov     eax, ecx
0x1800199c2  jmp     short loc_1800199D6
0x1800199c4  mov     r9d, ebx; samDesired
0x1800199c7  mov     qword ptr [rsp+298h+dwOptions], rdi; phkResult
0x1800199cc  call    cs:__imp_RegOpenKeyExW
0x1800199d2  jmp     short loc_1800199B9
0x1800199d4  xor     eax, eax
0x1800199d6  mov     rcx, [rsp+298h+var_28]
0x1800199de  xor     rcx, rsp; StackCookie
0x1800199e1  call    __security_check_cookie
0x1800199e6  add     rsp, 280h
0x1800199ed  pop     rdi
0x1800199ee  pop     rsi
0x1800199ef  pop     rbx
0x1800199f0  retn
```
