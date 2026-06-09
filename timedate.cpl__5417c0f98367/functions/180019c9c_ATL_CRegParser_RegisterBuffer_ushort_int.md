# ATL::CRegParser::RegisterBuffer(ushort *,int)

- ea: `0x180019c9c`
- end: `0x180019e06`
- name: `?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z`
- size: `362`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x180019e0c`

## callees

- `0x180019720`
- `0x1800198f0`
- `0x180019c9c`
- `0x180019fa0`
- `0x18001a80c`
- `0x180028f60`
- `0x180028ff0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019d3a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019d3a`
- `KERNEL32!lstrcmpiW` at `0x180019d21`
- `KERNEL32!lstrcmpiW` at `0x180019d21`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::RegisterBuffer(ATL::CRegParser *this, unsigned __int16 *a2, int a3)
{
  __int64 result; // rax
  int Token; // ebx
  _WORD *v7; // rbp
  int v8; // ebx
  HKEY v9; // rsi
  __int64 v10; // r14
  LPVOID pv; // [rsp+30h] [rbp-2058h] BYREF
  WCHAR String1[4096]; // [rsp+40h] [rbp-2048h] BYREF

  pv = 0;
  result = ATL::CRegParser::PreProcessBuffer(this, a2, (unsigned __int16 **)&pv);
  Token = result;
  if ( (int)result >= 0 )
  {
    v7 = pv;
    *(_QWORD *)this = pv;
    if ( *v7 )
    {
      do
      {
        Token = ATL::CRegParser::NextToken(this, String1);
        if ( Token < 0 )
          break;
        v8 = 0;
        while ( lstrcmpiW(String1, (&`ATL::CRegParser::HKeyFromString'::`2'::map)[2 * v8]) )
        {
          if ( (unsigned int)++v8 >= 0xE )
            goto LABEL_7;
        }
        v9 = (HKEY)*(&`ATL::CRegParser::HKeyFromString'::`2'::map + 2 * v8 + 1);
        if ( !v9 )
          goto LABEL_7;
        Token = ATL::CRegParser::NextToken(this, String1);
        if ( Token < 0 )
          break;
        if ( String1[0] != 123 )
        {
LABEL_7:
          Token = -2147352567;
          break;
        }
        if ( a3 )
        {
          v10 = *(_QWORD *)this;
          Token = ATL::CRegParser::RegisterSubkeys(this, String1, v9, a3, 0);
          if ( Token < 0 )
          {
            *(_QWORD *)this = v10;
            ATL::CRegParser::RegisterSubkeys(this, String1, v9, 0, 0);
            break;
          }
        }
        else
        {
          Token = ATL::CRegParser::RegisterSubkeys(this, String1, v9, 0, 0);
          if ( Token < 0 )
            break;
        }
        ATL::CRegParser::SkipWhiteSpace(this);
      }
      while ( **(_WORD **)this );
    }
    CoTaskMemFree(v7);
    return (unsigned int)Token;
  }
  return result;
}

```

## disassembly

```asm
0x180019c9c  push    rbx
0x180019c9e  push    rbp
0x180019c9f  push    rsi
0x180019ca0  push    rdi
0x180019ca1  push    r13
0x180019ca3  push    r14
0x180019ca5  push    r15
0x180019ca7  mov     eax, 2050h
0x180019cac  call    _alloca_probe
0x180019cb1  sub     rsp, rax
0x180019cb4  mov     rax, cs:__security_cookie
0x180019cbb  xor     rax, rsp
0x180019cbe  mov     [rsp+2088h+var_48], rax
0x180019cc6  mov     r15d, r8d
0x180019cc9  mov     [rsp+2088h+pv], 0
0x180019cd2  lea     r8, [rsp+2088h+pv]; unsigned __int16 **
0x180019cd7  mov     rdi, rcx
0x180019cda  call    ?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z; ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)
0x180019cdf  mov     ebx, eax
0x180019ce1  test    eax, eax
0x180019ce3  js      short loc_180019D42
0x180019ce5  mov     rbp, [rsp+2088h+pv]
0x180019cea  xor     eax, eax
0x180019cec  mov     [rdi], rbp
0x180019cef  cmp     ax, [rbp+0]
0x180019cf3  jz      short loc_180019D37
0x180019cf5  lea     r13, ?map@?1??HKeyFromString@CRegParser@ATL@@KAPEAUHKEY__@@PEAG@Z@4QBUkeymap@?1??123@KAPEAU4@0@Z@B; `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::keymap const near * const `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::map
0x180019cfc  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180019d01  mov     rcx, rdi; this
0x180019d04  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180019d09  mov     ebx, eax
0x180019d0b  test    eax, eax
0x180019d0d  js      short loc_180019D37
0x180019d0f  xor     ebx, ebx
0x180019d11  movsxd  rsi, ebx
0x180019d14  lea     rcx, [rsp+2088h+String1]; lpString1
0x180019d19  add     rsi, rsi
0x180019d1c  mov     rdx, [r13+rsi*8+0]; lpString2
0x180019d21  call    cs:__imp_lstrcmpiW
0x180019d27  test    eax, eax
0x180019d29  jz      short loc_180019D64
0x180019d2b  inc     ebx
0x180019d2d  cmp     ebx, 0Eh
0x180019d30  jb      short loc_180019D11
0x180019d32  mov     ebx, 80020009h
0x180019d37  mov     rcx, rbp; pv
0x180019d3a  call    cs:__imp_CoTaskMemFree
0x180019d40  mov     eax, ebx
0x180019d42  mov     rcx, [rsp+2088h+var_48]
0x180019d4a  xor     rcx, rsp; StackCookie
0x180019d4d  call    __security_check_cookie
0x180019d52  add     rsp, 2050h
0x180019d59  pop     r15
0x180019d5b  pop     r14
0x180019d5d  pop     r13
0x180019d5f  pop     rdi
0x180019d60  pop     rsi
0x180019d61  pop     rbp
0x180019d62  pop     rbx
0x180019d63  retn
0x180019d64  mov     rsi, [r13+rsi*8+8]
0x180019d69  test    rsi, rsi
0x180019d6c  jz      short loc_180019D32
0x180019d6e  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180019d73  mov     rcx, rdi; this
0x180019d76  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180019d7b  mov     ebx, eax
0x180019d7d  test    eax, eax
0x180019d7f  js      short loc_180019D37
0x180019d81  mov     eax, 7Bh ; '{'
0x180019d86  cmp     ax, [rsp+2088h+String1]
0x180019d8b  jnz     short loc_180019D32
0x180019d8d  mov     [rsp+2088h+var_2068], 0; int
0x180019d95  mov     r8, rsi; HKEY
0x180019d98  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180019d9d  mov     rcx, rdi; this
0x180019da0  test    r15d, r15d
0x180019da3  jz      short loc_180019DD9
0x180019da5  mov     r14, [rdi]
0x180019da8  mov     r9d, r15d; int
0x180019dab  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180019db0  mov     ebx, eax
0x180019db2  test    eax, eax
0x180019db4  jns     short loc_180019DEB
0x180019db6  xor     r9d, r9d; int
0x180019db9  mov     [rdi], r14
0x180019dbc  mov     r8, rsi; HKEY
0x180019dbf  mov     [rsp+2088h+var_2068], 0; int
0x180019dc7  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180019dcc  mov     rcx, rdi; this
0x180019dcf  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180019dd4  jmp     loc_180019D37
0x180019dd9  xor     r9d, r9d; int
0x180019ddc  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180019de1  mov     ebx, eax
0x180019de3  test    eax, eax
0x180019de5  js      loc_180019D37
0x180019deb  mov     rcx, rdi; this
0x180019dee  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x180019df3  mov     rcx, [rdi]
0x180019df6  xor     eax, eax
0x180019df8  cmp     ax, [rcx]
0x180019dfb  jnz     loc_180019CFC
0x180019e01  jmp     loc_180019D37
```
