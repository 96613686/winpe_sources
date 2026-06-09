# LoadProperSetupDLL

- ea: `0x383adc310`
- end: `0x383adc3a7`
- name: `LoadProperSetupDLL`
- size: `151`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x383adc3c0`

## callees

- `0x3838434c0`
- `0x383adc280`
- `0x383adc310`

## import_xrefs

- `KERNEL32!GetSystemDirectoryA` at `0x383adc333`
- `KERNEL32!GetSystemDirectoryA` at `0x383adc333`
- `KERNEL32!LoadLibraryA` at `0x383adc389`
- `KERNEL32!LoadLibraryA` at `0x383adc389`

## pseudocode

```c
HMODULE LoadProperSetupDLL()
{
  CHAR Buffer[272]; // [rsp+30h] [rbp-338h] BYREF
  char pszDest[528]; // [rsp+140h] [rbp-228h] BYREF

  if ( !GetSystemDirectoryA(Buffer, 0x105u) )
    return 0;
  StringCchPrintfA(pszDest, 0x20Au, "%s\\%s", Buffer, off_383B25CA0);
  return LoadLibraryA(pszDest);
}

```

## disassembly

```asm
0x383adc310  sub     rsp, 368h
0x383adc317  mov     rax, cs:__security_cookie
0x383adc31e  xor     rax, rsp
0x383adc321  mov     [rsp+368h+var_18], rax
0x383adc329  lea     rcx, [rsp+368h+Buffer]; lpBuffer
0x383adc32e  mov     edx, 105h; uSize
0x383adc333  call    cs:__imp_GetSystemDirectoryA
0x383adc339  test    eax, eax
0x383adc33b  jnz     short loc_383ADC357
0x383adc33d  xor     eax, eax
0x383adc33f  mov     rcx, [rsp+368h+var_18]
0x383adc347  xor     rcx, rsp; StackCookie
0x383adc34a  call    __security_check_cookie
0x383adc34f  add     rsp, 368h
0x383adc356  retn
0x383adc357  mov     rax, cs:off_383B25CA0; "odbccp32.dll"
0x383adc35e  lea     r9, [rsp+368h+Buffer]
0x383adc363  lea     r8, pszFormat; "%s\\%s"
0x383adc36a  lea     rcx, [rsp+368h+pszDest]; pszDest
0x383adc372  mov     edx, 20Ah; cchDest
0x383adc377  mov     [rsp+368h+var_348], rax
0x383adc37c  call    StringCchPrintfA
0x383adc381  lea     rcx, [rsp+368h+pszDest]; lpLibFileName
0x383adc389  call    cs:__imp_LoadLibraryA
0x383adc38f  mov     rcx, [rsp+368h+var_18]
0x383adc397  xor     rcx, rsp; StackCookie
0x383adc39a  call    __security_check_cookie
0x383adc39f  add     rsp, 368h
0x383adc3a6  retn
```
