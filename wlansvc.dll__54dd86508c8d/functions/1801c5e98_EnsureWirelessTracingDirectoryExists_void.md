# EnsureWirelessTracingDirectoryExists(void)

- ea: `0x1801c5e98`
- end: `0x1801c5fb1`
- name: `?EnsureWirelessTracingDirectoryExists@@YAHXZ`
- size: `281`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1801c9040`

## callees

- `0x180106340`
- `0x180106860`
- `0x1801c5e98`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801c5ef7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801c5f41`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801c5f78`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801c5ef7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801c5f41`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801c5f78`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1801c5ee7`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1801c5f37`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1801c5f6e`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1801c5ee7`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1801c5f37`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1801c5f6e`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1801c5ec9`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1801c5ec9`

## pseudocode

```c
__int64 EnsureWirelessTracingDirectoryExists(void)
{
  DWORD v0; // edi
  DWORD v1; // edi
  DWORD i; // ebx
  WCHAR Dst[264]; // [rsp+20h] [rbp-248h] BYREF

  v0 = ExpandEnvironmentStringsW(&g_etlPath, Dst, 0x104u);
  if ( v0 - 2 <= 0x101 )
  {
    if ( CreateDirectoryW(Dst, 0) || GetLastError() == 183 )
      return 1;
    v1 = v0 - 1;
    for ( i = v1; i; --i )
    {
      if ( Dst[i] == 92 )
      {
        if ( 2 * (unsigned __int64)i >= 0x208 )
          _report_rangecheckfailure();
        Dst[i] = 0;
        if ( CreateDirectoryW(Dst, 0) || GetLastError() == 183 )
          break;
      }
    }
    while ( 1 )
    {
      if ( !Dst[i] )
      {
        Dst[i] = 92;
        if ( !CreateDirectoryW(Dst, 0) && GetLastError() != 183 )
          break;
      }
      if ( ++i >= v1 )
        return 1;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1801c5e98  push    rbx
0x1801c5e9a  push    rsi
0x1801c5e9b  push    rdi
0x1801c5e9c  push    r15
0x1801c5e9e  sub     rsp, 248h
0x1801c5ea5  mov     rax, cs:__security_cookie
0x1801c5eac  xor     rax, rsp
0x1801c5eaf  mov     [rsp+268h+var_38], rax
0x1801c5eb7  mov     r8d, 104h; nSize
0x1801c5ebd  lea     rdx, [rsp+268h+Dst]; lpDst
0x1801c5ec2  lea     rcx, ?g_etlPath@@3PAGA; lpSrc
0x1801c5ec9  call    cs:__imp_ExpandEnvironmentStringsW
0x1801c5ecf  mov     edi, eax
0x1801c5ed1  lea     ecx, [rax-2]
0x1801c5ed4  cmp     ecx, 101h
0x1801c5eda  ja      loc_1801C5F92
0x1801c5ee0  xor     edx, edx; lpSecurityAttributes
0x1801c5ee2  lea     rcx, [rsp+268h+Dst]; lpPathName
0x1801c5ee7  call    cs:__imp_CreateDirectoryW
0x1801c5eed  xor     esi, esi
0x1801c5eef  test    eax, eax
0x1801c5ef1  jnz     loc_1801C5F8B
0x1801c5ef7  call    cs:__imp_GetLastError
0x1801c5efd  cmp     eax, 0B7h
0x1801c5f02  jz      loc_1801C5F8B
0x1801c5f08  dec     edi
0x1801c5f0a  lea     r15d, [rsi+5Ch]
0x1801c5f0e  mov     ebx, edi
0x1801c5f10  test    ebx, ebx
0x1801c5f12  jz      short loc_1801C5F58
0x1801c5f14  mov     eax, ebx
0x1801c5f16  lea     rcx, [rax+rax]
0x1801c5f1a  cmp     [rsp+rcx+268h+Dst], r15w
0x1801c5f20  jnz     short loc_1801C5F4E
0x1801c5f22  cmp     rcx, 208h
0x1801c5f29  jnb     short loc_1801C5F52
0x1801c5f2b  mov     [rsp+rcx+268h+Dst], si
0x1801c5f30  xor     edx, edx; lpSecurityAttributes
0x1801c5f32  lea     rcx, [rsp+268h+Dst]; lpPathName
0x1801c5f37  call    cs:__imp_CreateDirectoryW
0x1801c5f3d  test    eax, eax
0x1801c5f3f  jnz     short loc_1801C5F58
0x1801c5f41  call    cs:__imp_GetLastError
0x1801c5f47  cmp     eax, 0B7h
0x1801c5f4c  jz      short loc_1801C5F58
0x1801c5f4e  dec     ebx
0x1801c5f50  jmp     short loc_1801C5F10
0x1801c5f52  call    __report_rangecheckfailure
0x1801c5f58  mov     eax, ebx
0x1801c5f5a  cmp     [rsp+rax*2+268h+Dst], si
0x1801c5f5f  jnz     short loc_1801C5F85
0x1801c5f61  xor     edx, edx; lpSecurityAttributes
0x1801c5f63  mov     [rsp+rax*2+268h+Dst], r15w
0x1801c5f69  lea     rcx, [rsp+268h+Dst]; lpPathName
0x1801c5f6e  call    cs:__imp_CreateDirectoryW
0x1801c5f74  test    eax, eax
0x1801c5f76  jnz     short loc_1801C5F85
0x1801c5f78  call    cs:__imp_GetLastError
0x1801c5f7e  cmp     eax, 0B7h
0x1801c5f83  jnz     short loc_1801C5F92
0x1801c5f85  inc     ebx
0x1801c5f87  cmp     ebx, edi
0x1801c5f89  jb      short loc_1801C5F58
0x1801c5f8b  mov     eax, 1
0x1801c5f90  jmp     short loc_1801C5F94
0x1801c5f92  xor     eax, eax
0x1801c5f94  mov     rcx, [rsp+268h+var_38]
0x1801c5f9c  xor     rcx, rsp; StackCookie
0x1801c5f9f  call    __security_check_cookie
0x1801c5fa4  add     rsp, 248h
0x1801c5fab  pop     r15
0x1801c5fad  pop     rdi
0x1801c5fae  pop     rsi
0x1801c5faf  pop     rbx
0x1801c5fb0  retn
```
