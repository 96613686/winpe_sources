# ClCertRegContainsValue

- ea: `0x180038ff0`
- end: `0x1800390de`
- name: `ClCertRegContainsValue`
- size: `238`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey, LPCWSTR lpValue, _QWORD *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180036fb8`
- `0x1800395a4`

## callees

- `0x1800389ac`
- `0x180038d98`
- `0x180038e20`
- `0x180038ff0`
- `0x1800390e4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003905a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003905a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180039037`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180039037`

## pseudocode

```c
__int64 __fastcall ClCertRegContainsValue(LPCWSTR lpSubKey, LPCWSTR lpValue, _QWORD *a3)
{
  wchar_t *v3; // rdi
  void *v6; // rsi
  unsigned int Value; // ebx
  unsigned int ValueData; // eax
  unsigned int StringByPrefixFromMultiString; // eax
  HKEY hKey; // [rsp+30h] [rbp-28h] BYREF
  void *v12; // [rsp+38h] [rbp-20h]
  wchar_t *String1; // [rsp+40h] [rbp-18h]
  __int64 v14; // [rsp+A8h] [rbp+50h] BYREF

  v3 = 0;
  LODWORD(v14) = 0;
  String1 = 0;
  v6 = 0;
  v12 = 0;
  hKey = 0;
  Value = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 1u, &hKey);
  if ( !Value )
  {
    Value = RegQueryValueExW(hKey, lpValue, 0, 0, 0, 0);
    if ( !Value )
    {
      if ( a3 )
      {
        ValueData = ClCertRegGetValueData(hKey, lpValue, (__int64)&v14);
        v3 = String1;
        Value = ValueData;
        if ( !ValueData )
        {
          if ( !String1
            || (StringByPrefixFromMultiString = ClCertGetStringByPrefixFromMultiString(String1),
                v6 = v12,
                (Value = StringByPrefixFromMultiString) == 0) )
          {
            *a3 = v6;
            v6 = 0;
          }
        }
      }
    }
  }
  if ( hKey )
    ClCertRegCloseKey();
  ClCertLocalFree(v3);
  ClCertLocalFree(v6);
  return Value;
}

```

## disassembly

```asm
0x180038ff0  push    rbp
0x180038ff2  push    rbx
0x180038ff3  push    rsi
0x180038ff4  push    rdi
0x180038ff5  push    r14
0x180038ff7  push    r15
0x180038ff9  mov     rbp, rsp
0x180038ffc  sub     rsp, 58h
0x180039000  xor     edi, edi
0x180039002  mov     dword ptr [rbp+arg_18], 0
0x180039009  mov     r15, rdx
0x18003900c  mov     [rbp+String1], rdi
0x180039010  mov     r14, r8
0x180039013  lea     rax, [rbp+hKey]
0x180039017  xor     esi, esi
0x180039019  mov     [rsp+58h+phkResult], rax; phkResult
0x18003901e  mov     rdx, rcx; lpSubKey
0x180039021  mov     [rbp+var_20], rsi
0x180039025  lea     r9d, [rdi+1]; samDesired
0x180039029  mov     [rbp+hKey], rsi
0x18003902d  xor     r8d, r8d; ulOptions
0x180039030  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180039037  call    cs:__imp_RegOpenKeyExW
0x18003903d  mov     ebx, eax
0x18003903f  test    eax, eax
0x180039041  jnz     short loc_1800390B1
0x180039043  mov     rcx, [rbp+hKey]; hKey
0x180039047  xor     r9d, r9d; lpType
0x18003904a  mov     [rsp+58h+lpcbData], rsi; lpcbData
0x18003904f  xor     r8d, r8d; lpReserved
0x180039052  mov     rdx, r15; lpValueName
0x180039055  mov     [rsp+58h+phkResult], rsi; lpData
0x18003905a  call    cs:__imp_RegQueryValueExW
0x180039060  mov     ebx, eax
0x180039062  test    eax, eax
0x180039064  jnz     short loc_1800390B1
0x180039066  test    r14, r14
0x180039069  jz      short loc_1800390B1
0x18003906b  mov     rcx, [rbp+hKey]; hkey
0x18003906f  lea     rax, [rbp+arg_18]
0x180039073  lea     r9, [rbp+String1]
0x180039077  mov     [rsp+58h+phkResult], rax; __int64
0x18003907c  mov     rdx, r15; lpValue
0x18003907f  call    ClCertRegGetValueData
0x180039084  mov     rdi, [rbp+String1]
0x180039088  mov     ebx, eax
0x18003908a  test    eax, eax
0x18003908c  jnz     short loc_1800390B1
0x18003908e  test    rdi, rdi
0x180039091  jz      short loc_1800390AC
0x180039093  mov     edx, dword ptr [rbp+arg_18]
0x180039096  lea     r9, [rbp+var_20]
0x18003909a  mov     rcx, rdi; String1
0x18003909d  call    ClCertGetStringByPrefixFromMultiString
0x1800390a2  mov     rsi, [rbp+var_20]
0x1800390a6  mov     ebx, eax
0x1800390a8  test    eax, eax
0x1800390aa  jnz     short loc_1800390B1
0x1800390ac  mov     [r14], rsi
0x1800390af  xor     esi, esi
0x1800390b1  mov     rcx, [rbp+hKey]
0x1800390b5  test    rcx, rcx
0x1800390b8  jz      short loc_1800390BF
0x1800390ba  call    ClCertRegCloseKey
0x1800390bf  mov     rcx, rdi
0x1800390c2  call    ClCertLocalFree
0x1800390c7  mov     rcx, rsi
0x1800390ca  call    ClCertLocalFree
0x1800390cf  mov     eax, ebx
0x1800390d1  add     rsp, 58h
0x1800390d5  pop     r15
0x1800390d7  pop     r14
0x1800390d9  pop     rdi
0x1800390da  pop     rsi
0x1800390db  pop     rbx
0x1800390dc  pop     rbp
0x1800390dd  retn
```
