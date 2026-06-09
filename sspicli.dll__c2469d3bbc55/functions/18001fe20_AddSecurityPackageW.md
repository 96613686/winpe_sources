# AddSecurityPackageW

- ea: `0x18001fe20`
- end: `0x18001fe78`
- name: `AddSecurityPackageW`
- size: `88`
- prototype: `SECURITY_STATUS __stdcall(LPWSTR pszPackageName, PSECURITY_PACKAGE_OPTIONS pOptions)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18001fe20`
- `0x180021018`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x18001fe56`
- `ntdll!RtlInitUnicodeString` at `0x18001fe56`

## pseudocode

```c
SECURITY_STATUS __stdcall AddSecurityPackageW(LPWSTR pszPackageName, PSECURITY_PACKAGE_OPTIONS pOptions)
{
  PSECURITY_PACKAGE_OPTIONS v3; // rdx
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-38h] BYREF
  __int128 v6; // [rsp+30h] [rbp-28h] BYREF
  __int64 v7; // [rsp+40h] [rbp-18h]

  v7 = 0;
  v6 = 0;
  DestinationString = 0;
  if ( !pOptions )
  {
    LODWORD(v6) = 24;
    DWORD2(v6) = 0;
  }
  RtlInitUnicodeString(&DestinationString, pszPackageName);
  v3 = (PSECURITY_PACKAGE_OPTIONS)&v6;
  if ( pOptions )
    v3 = pOptions;
  return SecpAddPackage(&DestinationString, v3);
}

```

## disassembly

```asm
0x18001fe20  push    rbx
0x18001fe22  sub     rsp, 50h
0x18001fe26  xor     eax, eax
0x18001fe28  xorps   xmm0, xmm0
0x18001fe2b  mov     [rsp+58h+var_18], rax
0x18001fe30  mov     rbx, rdx
0x18001fe33  movups  [rsp+58h+var_28], xmm0
0x18001fe38  movups  xmmword ptr [rsp+58h+DestinationString.Length], xmm0
0x18001fe3d  test    rdx, rdx
0x18001fe40  jnz     short loc_18001FE4E
0x18001fe42  mov     dword ptr [rsp+58h+var_28], 18h
0x18001fe4a  mov     dword ptr [rsp+58h+var_28+8], eax
0x18001fe4e  mov     rdx, rcx; SourceString
0x18001fe51  lea     rcx, [rsp+58h+DestinationString]; DestinationString
0x18001fe56  call    cs:__imp_RtlInitUnicodeString
0x18001fe5c  test    rbx, rbx
0x18001fe5f  lea     rdx, [rsp+58h+var_28]
0x18001fe64  lea     rcx, [rsp+58h+DestinationString]
0x18001fe69  cmovnz  rdx, rbx
0x18001fe6d  call    SecpAddPackage
0x18001fe72  add     rsp, 50h
0x18001fe76  pop     rbx
0x18001fe77  retn
```
