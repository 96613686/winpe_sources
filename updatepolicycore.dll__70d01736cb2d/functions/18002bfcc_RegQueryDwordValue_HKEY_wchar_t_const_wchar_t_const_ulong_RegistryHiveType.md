# RegQueryDwordValue(HKEY__ *,wchar_t const *,wchar_t const *,ulong *,RegistryHiveType)

- ea: `0x18002bfcc`
- end: `0x18002c08a`
- name: `?RegQueryDwordValue@@YAJPEAUHKEY__@@PEB_W1PEAKW4RegistryHiveType@@@Z`
- size: `190`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180022634`
- `0x180022a48`

## callees

- `0x18002bee8`
- `0x18002bfcc`
- `0x18002c090`
- `0x18002ffd0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002c03a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002c03a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002c06c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002c06c`

## pseudocode

```c
__int64 __fastcall RegQueryDwordValue(HKEY a1, const WCHAR *a2, const wchar_t *a3, unsigned int *a4)
{
  __int64 result; // rax
  LSTATUS v9; // ecx
  unsigned int DwordValue; // ebx
  REGSAM samDesired; // [rsp+30h] [rbp-48h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-40h] BYREF

  hKey = 0;
  samDesired = 1;
  if ( !a4 )
    return 2147942487LL;
  *a4 = 0;
  result = SetRegistryType(a1, &samDesired);
  if ( (int)result >= 0 )
  {
    v9 = RegOpenKeyExW(a1, a2, 0, samDesired, &hKey);
    if ( v9 )
    {
      result = (unsigned __int16)v9 | 0x80070000;
      if ( v9 <= 0 )
        return (unsigned int)v9;
    }
    else
    {
      DwordValue = RegQueryDwordValue(hKey, a3, a4);
      RegCloseKey(hKey);
      return DwordValue;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18002bfcc  push    rbx
0x18002bfce  push    rbp
0x18002bfcf  push    rsi
0x18002bfd0  push    rdi
0x18002bfd1  sub     rsp, 58h
0x18002bfd5  mov     rax, cs:__security_cookie
0x18002bfdc  xor     rax, rsp
0x18002bfdf  mov     [rsp+78h+var_38], rax
0x18002bfe4  mov     [rsp+78h+hKey], 0
0x18002bfed  mov     rbx, r9
0x18002bff0  mov     [rsp+78h+samDesired], 1
0x18002bff8  mov     rdi, r8
0x18002bffb  mov     rbp, rdx
0x18002bffe  mov     rsi, rcx
0x18002c001  test    r9, r9
0x18002c004  jnz     short loc_18002C00D
0x18002c006  mov     eax, 80070057h
0x18002c00b  jmp     short loc_18002C074
0x18002c00d  lea     rdx, [rsp+78h+samDesired]
0x18002c012  mov     dword ptr [r9], 0
0x18002c019  call    ?SetRegistryType@@YAJW4RegistryHiveType@@PEAK@Z; SetRegistryType(RegistryHiveType,ulong *)
0x18002c01e  test    eax, eax
0x18002c020  js      short loc_18002C074
0x18002c022  mov     r9d, [rsp+78h+samDesired]; samDesired
0x18002c027  lea     rax, [rsp+78h+hKey]
0x18002c02c  xor     r8d, r8d; ulOptions
0x18002c02f  mov     [rsp+78h+phkResult], rax; phkResult
0x18002c034  mov     rdx, rbp; lpSubKey
0x18002c037  mov     rcx, rsi; hKey
0x18002c03a  call    cs:__imp_RegOpenKeyExW
0x18002c040  mov     ecx, eax
0x18002c042  test    eax, eax
0x18002c044  jz      short loc_18002C055
0x18002c046  movzx   eax, cx
0x18002c049  or      eax, 80070000h
0x18002c04e  test    ecx, ecx
0x18002c050  cmovle  eax, ecx
0x18002c053  jmp     short loc_18002C074
0x18002c055  mov     rcx, [rsp+78h+hKey]; HKEY
0x18002c05a  mov     r8, rbx; unsigned int *
0x18002c05d  mov     rdx, rdi; wchar_t *
0x18002c060  call    ?RegQueryDwordValue@@YAJPEAUHKEY__@@PEB_WPEAK@Z; RegQueryDwordValue(HKEY__ *,wchar_t const *,ulong *)
0x18002c065  mov     rcx, [rsp+78h+hKey]; hKey
0x18002c06a  mov     ebx, eax
0x18002c06c  call    cs:__imp_RegCloseKey
0x18002c072  mov     eax, ebx
0x18002c074  mov     rcx, [rsp+78h+var_38]
0x18002c079  xor     rcx, rsp; StackCookie
0x18002c07c  call    __security_check_cookie
0x18002c081  add     rsp, 58h
0x18002c085  pop     rdi
0x18002c086  pop     rsi
0x18002c087  pop     rbp
0x18002c088  pop     rbx
0x18002c089  retn
```
