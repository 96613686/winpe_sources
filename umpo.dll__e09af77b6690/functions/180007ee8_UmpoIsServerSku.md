# UmpoIsServerSku

- ea: `0x180007ee8`
- end: `0x180007f5f`
- name: `UmpoIsServerSku`
- size: `119`
- prototype: `bool()`
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x180007650`
- `0x1800088b0`
- `0x18000deb0`
- `0x18000ed10`
- `0x180015280`

## callees

- `0x180007ee8`
- `0x180010070`
- `0x180010946`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x180007f24`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x180007f24`

## pseudocode

```c
bool UmpoIsServerSku()
{
  char v0; // bl
  _OSVERSIONINFOW VersionInformation; // [rsp+20h] [rbp-138h] BYREF
  char v3; // [rsp+13Ah] [rbp-1Eh]

  v0 = 0;
  memset_0(&VersionInformation.dwMajorVersion, 0, 0x118u);
  VersionInformation.dwOSVersionInfoSize = 284;
  if ( GetVersionExW(&VersionInformation) )
    return (unsigned __int8)(v3 - 2) <= 1u;
  return v0;
}

```

## disassembly

```asm
0x180007ee8  push    rbx
0x180007eea  sub     rsp, 150h
0x180007ef1  mov     rax, cs:__security_cookie
0x180007ef8  xor     rax, rsp
0x180007efb  mov     [rsp+158h+var_18], rax
0x180007f03  xor     edx, edx; Val
0x180007f05  lea     rcx, [rsp+158h+VersionInformation.dwMajorVersion]; void *
0x180007f0a  mov     r8d, 118h; Size
0x180007f10  xor     bl, bl
0x180007f12  call    memset_0
0x180007f17  lea     rcx, [rsp+158h+VersionInformation]; lpVersionInformation
0x180007f1c  mov     [rsp+158h+VersionInformation.dwOSVersionInfoSize], 11Ch
0x180007f24  call    cs:__imp_GetVersionExW
0x180007f2a  test    eax, eax
0x180007f2c  jz      short loc_180007F44
0x180007f2e  mov     al, [rsp+158h+var_1E]
0x180007f35  mov     ecx, 1
0x180007f3a  sub     al, 2
0x180007f3c  movzx   ebx, bl
0x180007f3f  cmp     al, cl
0x180007f41  cmovbe  ebx, ecx
0x180007f44  mov     al, bl
0x180007f46  mov     rcx, [rsp+158h+var_18]
0x180007f4e  xor     rcx, rsp; StackCookie
0x180007f51  call    __security_check_cookie
0x180007f56  add     rsp, 150h
0x180007f5d  pop     rbx
0x180007f5e  retn
```
