# RegQueryDwordValue(HKEY__ *,wchar_t const *,wchar_t const *,ulong *,RegistryHiveType)

- ea: `0x18000fba8`
- end: `0x18000fc65`
- name: `?RegQueryDwordValue@@YAJPEAUHKEY__@@PEB_W1PEAKW4RegistryHiveType@@@Z`
- size: `189`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180022a8c`
- `0x18003e5ac`

## callees

- `0x18000fac4`
- `0x18000fba8`
- `0x18000fc6c`
- `0x180042630`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000fc48`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000fc48`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000fc16`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000fc16`

## pseudocode

```c
__int64 __fastcall RegQueryDwordValue(int a1, const WCHAR *a2, const wchar_t *a3, unsigned int *a4)
{
  __int64 result; // rax
  LSTATUS v8; // ecx
  unsigned int DwordValue; // ebx
  REGSAM samDesired; // [rsp+30h] [rbp-38h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-30h] BYREF

  hKey = 0;
  samDesired = 1;
  if ( !a4 )
    return 2147942487LL;
  *a4 = 0;
  result = SetRegistryType(a1, &samDesired);
  if ( (int)result >= 0 )
  {
    v8 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, a2, 0, samDesired, &hKey);
    if ( v8 )
    {
      result = (unsigned __int16)v8 | 0x80070000;
      if ( v8 <= 0 )
        return (unsigned int)v8;
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
0x18000fba8  push    rbx
0x18000fbaa  push    rsi
0x18000fbab  push    rdi
0x18000fbac  sub     rsp, 50h
0x18000fbb0  mov     rax, cs:__security_cookie
0x18000fbb7  xor     rax, rsp
0x18000fbba  mov     [rsp+68h+var_28], rax
0x18000fbbf  mov     [rsp+68h+hKey], 0
0x18000fbc8  mov     rbx, r9
0x18000fbcb  mov     [rsp+68h+samDesired], 1
0x18000fbd3  mov     rdi, r8
0x18000fbd6  mov     rsi, rdx
0x18000fbd9  test    r9, r9
0x18000fbdc  jnz     short loc_18000FBE5
0x18000fbde  mov     eax, 80070057h
0x18000fbe3  jmp     short loc_18000FC50
0x18000fbe5  lea     rdx, [rsp+68h+samDesired]
0x18000fbea  mov     dword ptr [r9], 0
0x18000fbf1  call    ?SetRegistryType@@YAJW4RegistryHiveType@@PEAK@Z; SetRegistryType(RegistryHiveType,ulong *)
0x18000fbf6  test    eax, eax
0x18000fbf8  js      short loc_18000FC50
0x18000fbfa  mov     r9d, [rsp+68h+samDesired]; samDesired
0x18000fbff  lea     rax, [rsp+68h+hKey]
0x18000fc04  xor     r8d, r8d; ulOptions
0x18000fc07  mov     [rsp+68h+phkResult], rax; phkResult
0x18000fc0c  mov     rdx, rsi; lpSubKey
0x18000fc0f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000fc16  call    cs:__imp_RegOpenKeyExW
0x18000fc1c  mov     ecx, eax
0x18000fc1e  test    eax, eax
0x18000fc20  jz      short loc_18000FC31
0x18000fc22  movzx   eax, cx
0x18000fc25  or      eax, 80070000h
0x18000fc2a  test    ecx, ecx
0x18000fc2c  cmovle  eax, ecx
0x18000fc2f  jmp     short loc_18000FC50
0x18000fc31  mov     rcx, [rsp+68h+hKey]; HKEY
0x18000fc36  mov     r8, rbx; unsigned int *
0x18000fc39  mov     rdx, rdi; wchar_t *
0x18000fc3c  call    ?RegQueryDwordValue@@YAJPEAUHKEY__@@PEB_WPEAK@Z; RegQueryDwordValue(HKEY__ *,wchar_t const *,ulong *)
0x18000fc41  mov     rcx, [rsp+68h+hKey]; hKey
0x18000fc46  mov     ebx, eax
0x18000fc48  call    cs:__imp_RegCloseKey
0x18000fc4e  mov     eax, ebx
0x18000fc50  mov     rcx, [rsp+68h+var_28]
0x18000fc55  xor     rcx, rsp; StackCookie
0x18000fc58  call    __security_check_cookie
0x18000fc5d  add     rsp, 50h
0x18000fc61  pop     rdi
0x18000fc62  pop     rsi
0x18000fc63  pop     rbx
0x18000fc64  retn
```
