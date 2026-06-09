# AddSecurityPackageA

- ea: `0x18001fda0`
- end: `0x18001fe12`
- name: `AddSecurityPackageA`
- size: `114`
- prototype: `SECURITY_STATUS __stdcall(LPSTR pszPackageName, PSECURITY_PACKAGE_OPTIONS pOptions)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18001fda0`
- `0x180021018`

## import_xrefs

- `ntdll!RtlCreateUnicodeStringFromAsciiz` at `0x18001fddf`
- `ntdll!RtlCreateUnicodeStringFromAsciiz` at `0x18001fddf`
- `ntdll!RtlFreeUnicodeString` at `0x18001fdfd`
- `ntdll!RtlFreeUnicodeString` at `0x18001fdfd`

## pseudocode

```c
SECURITY_STATUS __stdcall AddSecurityPackageA(LPSTR pszPackageName, PSECURITY_PACKAGE_OPTIONS pOptions)
{
  PSECURITY_PACKAGE_OPTIONS v2; // rbx
  SECURITY_STATUS v3; // ebx
  struct _UNICODE_STRING Destination; // [rsp+20h] [rbp-38h] BYREF
  __int128 v6; // [rsp+30h] [rbp-28h] BYREF
  __int64 v7; // [rsp+40h] [rbp-18h]

  v7 = 0;
  v6 = 0;
  Destination = 0;
  if ( !pOptions )
  {
    LODWORD(v6) = 24;
    DWORD2(v6) = 0;
  }
  v2 = (PSECURITY_PACKAGE_OPTIONS)&v6;
  if ( pOptions )
    v2 = pOptions;
  if ( !RtlCreateUnicodeStringFromAsciiz(&Destination, pszPackageName) )
    return -2146893056;
  v3 = SecpAddPackage(&Destination, v2);
  RtlFreeUnicodeString(&Destination);
  return v3;
}

```

## disassembly

```asm
0x18001fda0  push    rbx
0x18001fda2  sub     rsp, 50h
0x18001fda6  xor     eax, eax
0x18001fda8  xorps   xmm0, xmm0
0x18001fdab  mov     [rsp+58h+var_18], rax
0x18001fdb0  movups  [rsp+58h+var_28], xmm0
0x18001fdb5  movups  xmmword ptr [rsp+58h+Destination.Length], xmm0
0x18001fdba  test    rdx, rdx
0x18001fdbd  jnz     short loc_18001FDCB
0x18001fdbf  mov     dword ptr [rsp+58h+var_28], 18h
0x18001fdc7  mov     dword ptr [rsp+58h+var_28+8], eax
0x18001fdcb  test    rdx, rdx
0x18001fdce  lea     rbx, [rsp+58h+var_28]
0x18001fdd3  cmovnz  rbx, rdx
0x18001fdd7  mov     rdx, rcx; Source
0x18001fdda  lea     rcx, [rsp+58h+Destination]; Destination
0x18001fddf  call    cs:__imp_RtlCreateUnicodeStringFromAsciiz
0x18001fde5  test    al, al
0x18001fde7  jz      short loc_18001FE05
0x18001fde9  mov     rdx, rbx
0x18001fdec  lea     rcx, [rsp+58h+Destination]
0x18001fdf1  call    SecpAddPackage
0x18001fdf6  lea     rcx, [rsp+58h+Destination]; UnicodeString
0x18001fdfb  mov     ebx, eax
0x18001fdfd  call    cs:__imp_RtlFreeUnicodeString
0x18001fe03  jmp     short loc_18001FE0A
0x18001fe05  mov     ebx, 80090300h
0x18001fe0a  mov     eax, ebx
0x18001fe0c  add     rsp, 50h
0x18001fe10  pop     rbx
0x18001fe11  retn
```
