# ConstructToastXmlString(ushort const *,ushort * *,...)

- ea: `0x180015e2c`
- end: `0x180015e9f`
- name: `?ConstructToastXmlString@@YAJPEBGPEAPEAGZZ`
- size: `115`
- prototype: `signed int(LPCVOID lpSource, WCHAR *, ...)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180015f68`

## callees

- `0x180015e2c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015e84`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015e84`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180015e71`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180015e71`

## pseudocode

```c
signed int ConstructToastXmlString(LPCVOID lpSource, WCHAR *a2, ...)
{
  DWORD v2; // eax
  signed int result; // eax
  va_list v4; // [rsp+40h] [rbp-18h] BYREF
  va_list va; // [rsp+70h] [rbp+18h] BYREF

  va_start(va, a2);
  va_copy(v4, va);
  v2 = FormatMessageW(0x500u, lpSource, 0, 0, a2, 0, &v4);
  v4 = 0;
  if ( v2 )
    return 0;
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180015e2c  mov     r11, rsp
0x180015e2f  mov     [r11+10h], rdx
0x180015e33  mov     [r11+18h], r8
0x180015e37  mov     [r11+20h], r9
0x180015e3b  sub     rsp, 58h
0x180015e3f  lea     rax, [r11+18h]
0x180015e43  mov     qword ptr [r11-18h], 0
0x180015e4b  mov     [r11-18h], rax
0x180015e4f  xor     r9d, r9d; dwLanguageId
0x180015e52  lea     rax, [r11-18h]
0x180015e56  xor     r8d, r8d; dwMessageId
0x180015e59  mov     [r11-28h], rax
0x180015e5d  mov     [rsp+58h+nSize], 0; nSize
0x180015e65  mov     [r11-38h], rdx
0x180015e69  mov     rdx, rcx; lpSource
0x180015e6c  mov     ecx, 500h; dwFlags
0x180015e71  call    cs:__imp_FormatMessageW
0x180015e77  mov     [rsp+58h+var_18], 0
0x180015e80  test    eax, eax
0x180015e82  jnz     short loc_180015E98
0x180015e84  call    cs:__imp_GetLastError
0x180015e8a  test    eax, eax
0x180015e8c  jle     short loc_180015E9A
0x180015e8e  movzx   eax, ax
0x180015e91  or      eax, 80070000h
0x180015e96  jmp     short loc_180015E9A
0x180015e98  xor     eax, eax
0x180015e9a  add     rsp, 58h
0x180015e9e  retn
```
