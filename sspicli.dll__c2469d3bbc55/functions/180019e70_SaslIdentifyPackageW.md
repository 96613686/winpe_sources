# SaslIdentifyPackageW

- ea: `0x180019e70`
- end: `0x180019ea2`
- name: `SaslIdentifyPackageW`
- size: `50`
- prototype: `SECURITY_STATUS __stdcall(PSecBufferDesc pInput, PSecPkgInfoW *PackageInfo)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180019634`
- `0x180019e70`

## pseudocode

```c
SECURITY_STATUS __stdcall SaslIdentifyPackageW(PSecBufferDesc pInput, PSecPkgInfoW *PackageInfo)
{
  SECURITY_STATUS result; // eax
  struct _NEGOTIATE_PACKAGE_PREFIX *v4; // [rsp+40h] [rbp+18h] BYREF

  v4 = 0;
  result = SaslIdentifyPackageHelper(pInput, &v4);
  if ( result >= 0 )
    *PackageInfo = (PSecPkgInfoW)v4->PackageDataW;
  return result;
}

```

## disassembly

```asm
0x180019e70  push    rbx
0x180019e72  sub     rsp, 20h
0x180019e76  mov     rbx, rdx
0x180019e79  mov     [rsp+28h+arg_10], 0
0x180019e82  lea     rdx, [rsp+28h+arg_10]; struct _NEGOTIATE_PACKAGE_PREFIX **
0x180019e87  call    ?SaslIdentifyPackageHelper@@YAJPEAU_SecBufferDesc@@PEAPEAU_NEGOTIATE_PACKAGE_PREFIX@@@Z; SaslIdentifyPackageHelper(_SecBufferDesc *,_NEGOTIATE_PACKAGE_PREFIX * *)
0x180019e8c  test    eax, eax
0x180019e8e  js      short loc_180019E9C
0x180019e90  mov     rcx, [rsp+28h+arg_10]
0x180019e95  mov     r8, [rcx+10h]
0x180019e99  mov     [rbx], r8
0x180019e9c  add     rsp, 20h
0x180019ea0  pop     rbx
0x180019ea1  retn
```
