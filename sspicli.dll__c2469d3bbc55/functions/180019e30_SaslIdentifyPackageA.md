# SaslIdentifyPackageA

- ea: `0x180019e30`
- end: `0x180019e62`
- name: `SaslIdentifyPackageA`
- size: `50`
- prototype: `SECURITY_STATUS __stdcall(PSecBufferDesc pInput, PSecPkgInfoA *PackageInfo)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180019634`
- `0x180019e30`

## pseudocode

```c
SECURITY_STATUS __stdcall SaslIdentifyPackageA(PSecBufferDesc pInput, PSecPkgInfoA *PackageInfo)
{
  SECURITY_STATUS result; // eax
  struct _NEGOTIATE_PACKAGE_PREFIX *v4; // [rsp+40h] [rbp+18h] BYREF

  v4 = 0;
  result = SaslIdentifyPackageHelper(pInput, &v4);
  if ( result >= 0 )
    *PackageInfo = (PSecPkgInfoA)v4->PackageDataA;
  return result;
}

```

## disassembly

```asm
0x180019e30  push    rbx
0x180019e32  sub     rsp, 20h
0x180019e36  mov     rbx, rdx
0x180019e39  mov     [rsp+28h+arg_10], 0
0x180019e42  lea     rdx, [rsp+28h+arg_10]; struct _NEGOTIATE_PACKAGE_PREFIX **
0x180019e47  call    ?SaslIdentifyPackageHelper@@YAJPEAU_SecBufferDesc@@PEAPEAU_NEGOTIATE_PACKAGE_PREFIX@@@Z; SaslIdentifyPackageHelper(_SecBufferDesc *,_NEGOTIATE_PACKAGE_PREFIX * *)
0x180019e4c  test    eax, eax
0x180019e4e  js      short loc_180019E5C
0x180019e50  mov     rcx, [rsp+28h+arg_10]
0x180019e55  mov     r8, [rcx+8]
0x180019e59  mov     [rbx], r8
0x180019e5c  add     rsp, 20h
0x180019e60  pop     rbx
0x180019e61  retn
```
