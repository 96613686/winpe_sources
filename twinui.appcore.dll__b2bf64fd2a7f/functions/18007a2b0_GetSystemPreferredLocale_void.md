# GetSystemPreferredLocale(void)

- ea: `0x18007a2b0`
- end: `0x18007a35b`
- name: `?GetSystemPreferredLocale@@YAKXZ`
- size: `171`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18007a1e0`

## callees

- `0x18002b1b0`
- `0x18007a2b0`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!GetSystemDefaultLCID` at `0x18007a33d`
- `api-ms-win-core-localization-l1-2-0!GetSystemDefaultLCID` at `0x18007a33d`
- `api-ms-win-core-localization-l1-2-0!ResolveLocaleName` at `0x18007a314`
- `api-ms-win-core-localization-l1-2-0!ResolveLocaleName` at `0x18007a314`
- `api-ms-win-core-localization-l1-2-0!GetSystemPreferredUILanguages` at `0x18007a2f0`
- `api-ms-win-core-localization-l1-2-0!GetSystemPreferredUILanguages` at `0x18007a2f0`
- `api-ms-win-core-localization-l1-2-0!LocaleNameToLCID` at `0x18007a325`
- `api-ms-win-core-localization-l1-2-0!LocaleNameToLCID` at `0x18007a325`

## pseudocode

```c
unsigned int GetSystemPreferredLocale(void)
{
  unsigned int result; // eax
  ULONG pulNumLanguages; // [rsp+20h] [rbp-2D8h] BYREF
  ULONG pcchLanguagesBuffer[3]; // [rsp+24h] [rbp-2D4h] BYREF
  WCHAR LocaleName[88]; // [rsp+30h] [rbp-2C8h] BYREF
  WCHAR pwszLanguagesBuffer[256]; // [rsp+E0h] [rbp-218h] BYREF

  pulNumLanguages = 0;
  pcchLanguagesBuffer[0] = 256;
  if ( !GetSystemPreferredUILanguages(8u, &pulNumLanguages, pwszLanguagesBuffer, pcchLanguagesBuffer)
    || !pulNumLanguages
    || ResolveLocaleName(pwszLanguagesBuffer, LocaleName, 85) <= 0 )
  {
    return GetSystemDefaultLCID();
  }
  result = LocaleNameToLCID(LocaleName, 0);
  if ( result == 4096 )
    return 127;
  if ( !result )
    return GetSystemDefaultLCID();
  return result;
}

```

## disassembly

```asm
0x18007a2b0  sub     rsp, 2F8h
0x18007a2b7  mov     rax, cs:__security_cookie
0x18007a2be  xor     rax, rsp
0x18007a2c1  mov     [rsp+2F8h+var_18], rax
0x18007a2c9  lea     r9, [rsp+2F8h+pcchLanguagesBuffer]; pcchLanguagesBuffer
0x18007a2ce  mov     [rsp+2F8h+pulNumLanguages], 0
0x18007a2d6  lea     r8, [rsp+2F8h+pwszLanguagesBuffer]; pwszLanguagesBuffer
0x18007a2de  mov     [rsp+2F8h+pcchLanguagesBuffer], 100h
0x18007a2e6  lea     rdx, [rsp+2F8h+pulNumLanguages]; pulNumLanguages
0x18007a2eb  mov     ecx, 8; dwFlags
0x18007a2f0  call    cs:__imp_GetSystemPreferredUILanguages
0x18007a2f6  test    eax, eax
0x18007a2f8  jz      short loc_18007A33D
0x18007a2fa  cmp     [rsp+2F8h+pulNumLanguages], 0
0x18007a2ff  jbe     short loc_18007A33D
0x18007a301  mov     r8d, 55h ; 'U'; cchLocaleName
0x18007a307  lea     rdx, [rsp+2F8h+LocaleName]; lpLocaleName
0x18007a30c  lea     rcx, [rsp+2F8h+pwszLanguagesBuffer]; lpNameToResolve
0x18007a314  call    cs:__imp_ResolveLocaleName
0x18007a31a  test    eax, eax
0x18007a31c  jle     short loc_18007A33D
0x18007a31e  xor     edx, edx; dwFlags
0x18007a320  lea     rcx, [rsp+2F8h+LocaleName]; lpName
0x18007a325  call    cs:__imp_LocaleNameToLCID
0x18007a32b  cmp     eax, 1000h
0x18007a330  jnz     short loc_18007A339
0x18007a332  mov     eax, 7Fh
0x18007a337  jmp     short loc_18007A343
0x18007a339  test    eax, eax
0x18007a33b  jnz     short loc_18007A343
0x18007a33d  call    cs:__imp_GetSystemDefaultLCID
0x18007a343  mov     rcx, [rsp+2F8h+var_18]
0x18007a34b  xor     rcx, rsp; StackCookie
0x18007a34e  call    __security_check_cookie
0x18007a353  add     rsp, 2F8h
0x18007a35a  retn
```
