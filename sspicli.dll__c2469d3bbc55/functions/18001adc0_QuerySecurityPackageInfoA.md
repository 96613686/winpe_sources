# QuerySecurityPackageInfoA

- ea: `0x18001adc0`
- end: `0x18001adf8`
- name: `QuerySecurityPackageInfoA`
- size: `56`
- prototype: `SECURITY_STATUS __stdcall(LPSTR pszPackageName, PSecPkgInfoA *ppPackageInfo)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180007b58`
- `0x18001adc0`
- `0x18001d060`

## pseudocode

```c
SECURITY_STATUS __stdcall QuerySecurityPackageInfoA(LPSTR pszPackageName, PSecPkgInfoA *ppPackageInfo)
{
  SECURITY_STATUS result; // eax
  struct _DLL_SECURITY_PACKAGE *v4; // [rsp+40h] [rbp+18h] BYREF

  v4 = 0;
  result = SecLocatePackageExA(0, pszPackageName, &v4);
  if ( result >= 0 )
    return SecCopyPackageInfoToUserA((__int64)v4, ppPackageInfo);
  return result;
}

```

## disassembly

```asm
0x18001adc0  push    rbx
0x18001adc2  sub     rsp, 20h
0x18001adc6  mov     rbx, rdx
0x18001adc9  mov     [rsp+28h+arg_10], 0
0x18001add2  mov     rdx, rcx
0x18001add5  lea     r8, [rsp+28h+arg_10]
0x18001adda  xor     ecx, ecx; int
0x18001addc  call    SecLocatePackageExA
0x18001ade1  test    eax, eax
0x18001ade3  js      short loc_18001ADF2
0x18001ade5  mov     rcx, [rsp+28h+arg_10]
0x18001adea  mov     rdx, rbx
0x18001aded  call    SecCopyPackageInfoToUserA
0x18001adf2  add     rsp, 20h
0x18001adf6  pop     rbx
0x18001adf7  retn
```
