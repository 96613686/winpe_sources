# SaslGetProfilePackageA

- ea: `0x180019d70`
- end: `0x180019dd2`
- name: `SaslGetProfilePackageA`
- size: `98`
- prototype: `SECURITY_STATUS __stdcall(LPSTR ProfileName, PSecPkgInfoA *PackageInfo)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180019d70`
- `0x18001ca00`
- `0x18001d060`

## import_xrefs

- `ntdll!RtlCreateUnicodeStringFromAsciiz` at `0x180019d8d`
- `ntdll!RtlCreateUnicodeStringFromAsciiz` at `0x180019d8d`
- `ntdll!RtlFreeUnicodeString` at `0x180019da9`
- `ntdll!RtlFreeUnicodeString` at `0x180019da9`

## pseudocode

```c
SECURITY_STATUS __stdcall SaslGetProfilePackageA(LPSTR ProfileName, PSecPkgInfoA *PackageInfo)
{
  struct _SASL_PROFILE *v3; // rbx
  struct _UNICODE_STRING Destination; // [rsp+20h] [rbp-18h] BYREF

  Destination = 0;
  if ( RtlCreateUnicodeStringFromAsciiz(&Destination, ProfileName)
    && (v3 = SecpScanProfileList(&Destination), RtlFreeUnicodeString(&Destination), v3) )
  {
    return SecCopyPackageInfoToUserA(*((_QWORD *)v3 + 2), PackageInfo);
  }
  else
  {
    return -2146893051;
  }
}

```

## disassembly

```asm
0x180019d70  mov     [rsp+arg_0], rbx
0x180019d75  push    rdi
0x180019d76  sub     rsp, 30h
0x180019d7a  mov     rdi, rdx
0x180019d7d  xorps   xmm0, xmm0
0x180019d80  mov     rdx, rcx; Source
0x180019d83  lea     rcx, [rsp+38h+Destination]; Destination
0x180019d88  movups  xmmword ptr [rsp+38h+Destination.Length], xmm0
0x180019d8d  call    cs:__imp_RtlCreateUnicodeStringFromAsciiz
0x180019d93  test    al, al
0x180019d95  jz      short loc_180019DC2
0x180019d97  lea     rcx, [rsp+38h+Destination]; String1
0x180019d9c  call    ?SecpScanProfileList@@YAPEAU_SASL_PROFILE@@PEAU_UNICODE_STRING@@@Z; SecpScanProfileList(_UNICODE_STRING *)
0x180019da1  lea     rcx, [rsp+38h+Destination]; UnicodeString
0x180019da6  mov     rbx, rax
0x180019da9  call    cs:__imp_RtlFreeUnicodeString
0x180019daf  test    rbx, rbx
0x180019db2  jz      short loc_180019DC2
0x180019db4  mov     rcx, [rbx+10h]
0x180019db8  mov     rdx, rdi
0x180019dbb  call    SecCopyPackageInfoToUserA
0x180019dc0  jmp     short loc_180019DC7
0x180019dc2  mov     eax, 80090305h
0x180019dc7  mov     rbx, [rsp+38h+arg_0]
0x180019dcc  add     rsp, 30h
0x180019dd0  pop     rdi
0x180019dd1  retn
```
