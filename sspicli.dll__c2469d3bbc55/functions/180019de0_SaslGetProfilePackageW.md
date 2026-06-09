# SaslGetProfilePackageW

- ea: `0x180019de0`
- end: `0x180019e2a`
- name: `SaslGetProfilePackageW`
- size: `74`
- prototype: `SECURITY_STATUS __stdcall(LPWSTR ProfileName, PSecPkgInfoW *PackageInfo)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180012fd8`
- `0x180019de0`
- `0x18001ca00`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x180019df9`
- `ntdll!RtlInitUnicodeString` at `0x180019df9`

## pseudocode

```c
SECURITY_STATUS __stdcall SaslGetProfilePackageW(LPWSTR ProfileName, PSecPkgInfoW *PackageInfo)
{
  struct _SASL_PROFILE *v3; // rax
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-18h] BYREF

  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, ProfileName);
  v3 = SecpScanProfileList(&DestinationString);
  if ( v3 )
    return SecCopyPackageInfoToUserW(*((_QWORD *)v3 + 2), PackageInfo);
  else
    return -2146893051;
}

```

## disassembly

```asm
0x180019de0  push    rbx
0x180019de2  sub     rsp, 30h
0x180019de6  mov     rbx, rdx
0x180019de9  xorps   xmm0, xmm0
0x180019dec  mov     rdx, rcx; SourceString
0x180019def  lea     rcx, [rsp+38h+DestinationString]; DestinationString
0x180019df4  movups  xmmword ptr [rsp+38h+DestinationString.Length], xmm0
0x180019df9  call    cs:__imp_RtlInitUnicodeString
0x180019dff  lea     rcx, [rsp+38h+DestinationString]; String1
0x180019e04  call    ?SecpScanProfileList@@YAPEAU_SASL_PROFILE@@PEAU_UNICODE_STRING@@@Z; SecpScanProfileList(_UNICODE_STRING *)
0x180019e09  test    rax, rax
0x180019e0c  jz      short loc_180019E1F
0x180019e0e  mov     rcx, [rax+10h]
0x180019e12  mov     rdx, rbx
0x180019e15  add     rsp, 30h
0x180019e19  pop     rbx
0x180019e1a  jmp     SecCopyPackageInfoToUserW
0x180019e1f  mov     eax, 80090305h
0x180019e24  add     rsp, 30h
0x180019e28  pop     rbx
0x180019e29  retn
```
