# QuerySecurityPackageInfoW

- ea: `0x180009c40`
- end: `0x180009c7d`
- name: `QuerySecurityPackageInfoW`
- size: `61`
- prototype: `SECURITY_STATUS __stdcall(LPWSTR pszPackageName, PSecPkgInfoW *ppPackageInfo)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180009c40`
- `0x180009c90`
- `0x180012fd8`

## pseudocode

```c
SECURITY_STATUS __stdcall QuerySecurityPackageInfoW(LPWSTR pszPackageName, PSecPkgInfoW *ppPackageInfo)
{
  SECURITY_STATUS result; // eax
  __int64 v4; // [rsp+40h] [rbp+18h] BYREF

  v4 = 0;
  result = SecLocatePackageExW(0, pszPackageName, &v4);
  if ( result >= 0 )
    return SecCopyPackageInfoToUserW(v4, ppPackageInfo);
  return result;
}

```

## disassembly

```asm
0x180009c40  push    rbx
0x180009c42  sub     rsp, 20h
0x180009c46  mov     rbx, rdx
0x180009c49  mov     [rsp+28h+arg_10], 0
0x180009c52  mov     rdx, rcx
0x180009c55  lea     r8, [rsp+28h+arg_10]
0x180009c5a  xor     ecx, ecx
0x180009c5c  call    SecLocatePackageExW
0x180009c61  test    eax, eax
0x180009c63  jns     short loc_180009C6B
0x180009c65  add     rsp, 20h
0x180009c69  pop     rbx
0x180009c6a  retn
0x180009c6b  mov     rcx, [rsp+28h+arg_10]
0x180009c70  mov     rdx, rbx
0x180009c73  add     rsp, 20h
0x180009c77  pop     rbx
0x180009c78  jmp     SecCopyPackageInfoToUserW
```
