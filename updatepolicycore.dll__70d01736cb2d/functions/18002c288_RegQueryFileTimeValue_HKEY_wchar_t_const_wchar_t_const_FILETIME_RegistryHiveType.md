# RegQueryFileTimeValue(HKEY__ *,wchar_t const *,wchar_t const *,_FILETIME *,RegistryHiveType)

- ea: `0x18002c288`
- end: `0x18002c36c`
- name: `?RegQueryFileTimeValue@@YAJPEAUHKEY__@@PEB_W1PEAU_FILETIME@@W4RegistryHiveType@@@Z`
- size: `228`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18001f560`

## callees

- `0x18002bee8`
- `0x18002c288`
- `0x18002c898`
- `0x18002d318`
- `0x18002ffd0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002c2ff`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002c2ff`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002c349`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002c349`

## pseudocode

```c
__int64 __fastcall RegQueryFileTimeValue(__int64 a1, const WCHAR *a2, __int64 a3, _QWORD *a4)
{
  __int64 result; // rax
  LSTATUS v8; // eax
  int v9; // ecx
  int ValueCchHelper; // ebx
  REGSAM samDesired; // [rsp+40h] [rbp-68h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-60h] BYREF
  _BYTE v13[48]; // [rsp+50h] [rbp-58h] BYREF

  hKey = 0;
  samDesired = 1;
  if ( !a4 )
    return 2147942487LL;
  *a4 = 0;
  result = SetRegistryType(a1, &samDesired);
  if ( (int)result >= 0 )
  {
    v8 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, a2, 0, samDesired, &hKey);
    v9 = v8;
    if ( v8 )
    {
      result = (unsigned __int16)v8 | 0x80070000;
      if ( v9 <= 0 )
        return (unsigned int)v9;
    }
    else
    {
      ValueCchHelper = SafeRegQueryValueCchHelper(0, hKey, a3, v13);
      if ( ValueCchHelper >= 0 )
        ValueCchHelper = StringToFileTime(v13, a4, 0);
      RegCloseKey(hKey);
      return (unsigned int)ValueCchHelper;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18002c288  push    rbx
0x18002c28a  push    rsi
0x18002c28b  push    rdi
0x18002c28c  sub     rsp, 90h
0x18002c293  mov     rax, cs:__security_cookie
0x18002c29a  xor     rax, rsp
0x18002c29d  mov     [rsp+0A8h+var_28], rax
0x18002c2a5  mov     [rsp+0A8h+hKey], 0
0x18002c2ae  mov     rdi, r9
0x18002c2b1  mov     [rsp+0A8h+samDesired], 1
0x18002c2b9  mov     rbx, r8
0x18002c2bc  mov     rsi, rdx
0x18002c2bf  test    r9, r9
0x18002c2c2  jnz     short loc_18002C2CE
0x18002c2c4  mov     eax, 80070057h
0x18002c2c9  jmp     loc_18002C351
0x18002c2ce  lea     rdx, [rsp+0A8h+samDesired]
0x18002c2d3  mov     qword ptr [r9], 0
0x18002c2da  call    ?SetRegistryType@@YAJW4RegistryHiveType@@PEAK@Z; SetRegistryType(RegistryHiveType,ulong *)
0x18002c2df  test    eax, eax
0x18002c2e1  js      short loc_18002C351
0x18002c2e3  mov     r9d, [rsp+0A8h+samDesired]; samDesired
0x18002c2e8  lea     rax, [rsp+0A8h+hKey]
0x18002c2ed  xor     r8d, r8d; ulOptions
0x18002c2f0  mov     [rsp+0A8h+phkResult], rax; phkResult
0x18002c2f5  mov     rdx, rsi; lpSubKey
0x18002c2f8  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002c2ff  call    cs:__imp_RegOpenKeyExW
0x18002c305  mov     ecx, eax
0x18002c307  test    eax, eax
0x18002c309  jz      short loc_18002C31A
0x18002c30b  movzx   eax, cx
0x18002c30e  or      eax, 80070000h
0x18002c313  test    ecx, ecx
0x18002c315  cmovle  eax, ecx
0x18002c318  jmp     short loc_18002C351
0x18002c31a  mov     rdx, [rsp+0A8h+hKey]
0x18002c31f  lea     r9, [rsp+0A8h+var_58]
0x18002c324  mov     r8, rbx
0x18002c327  call    SafeRegQueryValueCchHelper
0x18002c32c  mov     ebx, eax
0x18002c32e  test    eax, eax
0x18002c330  js      short loc_18002C344
0x18002c332  xor     r8d, r8d
0x18002c335  lea     rcx, [rsp+0A8h+var_58]
0x18002c33a  mov     rdx, rdi
0x18002c33d  call    StringToFileTime
0x18002c342  mov     ebx, eax
0x18002c344  mov     rcx, [rsp+0A8h+hKey]; hKey
0x18002c349  call    cs:__imp_RegCloseKey
0x18002c34f  mov     eax, ebx
0x18002c351  mov     rcx, [rsp+0A8h+var_28]
0x18002c359  xor     rcx, rsp; StackCookie
0x18002c35c  call    __security_check_cookie
0x18002c361  add     rsp, 90h
0x18002c368  pop     rdi
0x18002c369  pop     rsi
0x18002c36a  pop     rbx
0x18002c36b  retn
```
