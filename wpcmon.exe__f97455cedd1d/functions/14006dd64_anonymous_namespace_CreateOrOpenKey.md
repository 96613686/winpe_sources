# _anonymous_namespace_::CreateOrOpenKey

- ea: `0x14006dd64`
- end: `0x14006ddc0`
- name: `_anonymous_namespace_::CreateOrOpenKey`
- size: `92`
- prototype: `__int64 __fastcall(_DWORD, _DWORD, _DWORD, _DWORD)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x14006d0c4`

## callees

- `0x14006dd64`

## import_xrefs

- `ADVAPI32!RegCreateKeyExW` at `0x14006dd95`
- `ADVAPI32!RegCreateKeyExW` at `0x14006dd95`
- `ADVAPI32!RegOpenKeyExW` at `0x14006dda5`
- `ADVAPI32!RegOpenKeyExW` at `0x14006dda5`
- `KERNEL32!SetLastError` at `0x14006ddad`
- `KERNEL32!SetLastError` at `0x14006ddad`

## pseudocode

```c
HKEY __fastcall anonymous_namespace_::CreateOrOpenKey(HKEY a1, const WCHAR *a2, char a3, REGSAM a4, HKEY phkResult)
{
  LSTATUS v5; // eax

  phkResult = 0;
  if ( a3 )
    v5 = RegCreateKeyExW(a1, a2, 0, 0, 0, a4, 0, &phkResult, 0);
  else
    v5 = RegOpenKeyExW(a1, a2, 0, a4, &phkResult);
  SetLastError(v5);
  return phkResult;
}

```

## disassembly

```asm
0x14006dd64  mov     r11, rsp
0x14006dd67  sub     rsp, 58h
0x14006dd6b  xor     r10d, r10d
0x14006dd6e  lea     rax, [r11+28h]
0x14006dd72  mov     [r11+28h], r10
0x14006dd76  test    r8b, r8b
0x14006dd79  jz      short loc_14006DD9D
0x14006dd7b  mov     [r11-18h], r10
0x14006dd7f  xor     r8d, r8d; Reserved
0x14006dd82  mov     [r11-20h], rax
0x14006dd86  mov     [r11-28h], r10
0x14006dd8a  mov     [r11-30h], r9d
0x14006dd8e  xor     r9d, r9d; lpClass
0x14006dd91  mov     [r11-38h], r10d
0x14006dd95  call    cs:__imp_RegCreateKeyExW
0x14006dd9b  jmp     short loc_14006DDAB
0x14006dd9d  xor     r8d, r8d; ulOptions
0x14006dda0  mov     [rsp+58h+phkResult], rax; phkResult
0x14006dda5  call    cs:__imp_RegOpenKeyExW
0x14006ddab  mov     ecx, eax; dwErrCode
0x14006ddad  call    cs:__imp_SetLastError
0x14006ddb3  mov     rax, [rsp+58h+arg_20]
0x14006ddbb  add     rsp, 58h
0x14006ddbf  retn
```
