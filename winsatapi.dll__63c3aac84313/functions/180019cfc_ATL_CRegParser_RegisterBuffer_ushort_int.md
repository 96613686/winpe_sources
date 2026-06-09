# ATL::CRegParser::RegisterBuffer(ushort *,int)

- ea: `0x180019cfc`
- end: `0x180019e69`
- name: `?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z`
- size: `365`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x180019e70`

## callees

- `0x180019370`
- `0x1800194d0`
- `0x180019cfc`
- `0x18001a0e0`
- `0x18001abbc`
- `0x18002dec0`
- `0x18002df80`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019e3f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019e3f`
- `KERNEL32!lstrcmpiW` at `0x180019d98`
- `KERNEL32!lstrcmpiW` at `0x180019d98`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::RegisterBuffer(const wchar_t **this, unsigned __int16 *a2, int a3)
{
  __int64 result; // rax
  int Token; // ebx
  void *v7; // rbp
  unsigned int i; // ebx
  HKEY v9; // rsi
  const wchar_t *v10; // r14
  LPVOID pv; // [rsp+30h] [rbp-2058h] BYREF
  WCHAR String1[4096]; // [rsp+40h] [rbp-2048h] BYREF

  pv = 0;
  result = ATL::CRegParser::PreProcessBuffer(this, a2, (unsigned __int16 **)&pv);
  Token = result;
  if ( (int)result >= 0 )
  {
    v7 = pv;
    *this = (const wchar_t *)pv;
    while ( **this )
    {
      Token = ATL::CRegParser::NextToken((ATL::CRegParser *)this, String1);
      if ( Token < 0 )
        break;
      for ( i = 0; ; ++i )
      {
        if ( i >= 0xE )
          goto LABEL_17;
        if ( !lstrcmpiW(String1, (&`ATL::CRegParser::HKeyFromString'::`2'::map)[2 * (int)i]) )
          break;
      }
      v9 = (HKEY)*(&`ATL::CRegParser::HKeyFromString'::`2'::map + 2 * (int)i + 1);
      if ( !v9 )
        goto LABEL_17;
      Token = ATL::CRegParser::NextToken((ATL::CRegParser *)this, String1);
      if ( Token < 0 )
        break;
      if ( String1[0] != 123 )
      {
LABEL_17:
        Token = -2147352567;
        break;
      }
      if ( a3 )
      {
        v10 = *this;
        Token = ATL::CRegParser::RegisterSubkeys((ATL::CRegParser *)this, String1, v9, a3, 0);
        if ( Token < 0 )
        {
          *this = v10;
          ATL::CRegParser::RegisterSubkeys((ATL::CRegParser *)this, String1, v9, 0, 0);
          break;
        }
      }
      else
      {
        Token = ATL::CRegParser::RegisterSubkeys((ATL::CRegParser *)this, String1, v9, 0, 0);
        if ( Token < 0 )
          break;
      }
      ATL::CRegParser::SkipWhiteSpace((ATL::CRegParser *)this);
    }
    CoTaskMemFree(v7);
    return (unsigned int)Token;
  }
  return result;
}

```

## disassembly

```asm
0x180019cfc  push    rbx
0x180019cfe  push    rbp
0x180019cff  push    rsi
0x180019d00  push    rdi
0x180019d01  push    r13
0x180019d03  push    r14
0x180019d05  push    r15
0x180019d07  mov     eax, 2050h
0x180019d0c  call    _alloca_probe
0x180019d11  sub     rsp, rax
0x180019d14  mov     rax, cs:__security_cookie
0x180019d1b  xor     rax, rsp
0x180019d1e  mov     [rsp+2088h+var_48], rax
0x180019d26  mov     r15d, r8d
0x180019d29  mov     [rsp+2088h+pv], 0
0x180019d32  lea     r8, [rsp+2088h+pv]; unsigned __int16 **
0x180019d37  mov     rdi, rcx
0x180019d3a  call    ?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z; ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)
0x180019d3f  mov     ebx, eax
0x180019d41  test    eax, eax
0x180019d43  js      loc_180019E47
0x180019d49  mov     rbp, [rsp+2088h+pv]
0x180019d4e  lea     r13, ?map@?1??HKeyFromString@CRegParser@ATL@@KAPEAUHKEY__@@PEAG@Z@4QBUkeymap@?1??123@KAPEAU4@0@Z@B; `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::keymap const near * const `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::map
0x180019d55  mov     [rdi], rbp
0x180019d58  mov     rcx, [rdi]
0x180019d5b  xor     eax, eax
0x180019d5d  cmp     ax, [rcx]
0x180019d60  jz      loc_180019E3C
0x180019d66  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180019d6b  mov     rcx, rdi; this
0x180019d6e  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180019d73  mov     ebx, eax
0x180019d75  test    eax, eax
0x180019d77  js      loc_180019E3C
0x180019d7d  xor     ebx, ebx
0x180019d7f  cmp     ebx, 0Eh
0x180019d82  jnb     loc_180019E37
0x180019d88  movsxd  rsi, ebx
0x180019d8b  lea     rcx, [rsp+2088h+String1]; lpString1
0x180019d90  add     rsi, rsi
0x180019d93  mov     rdx, [r13+rsi*8+0]; lpString2
0x180019d98  call    cs:__imp_lstrcmpiW
0x180019d9e  test    eax, eax
0x180019da0  jz      short loc_180019DA6
0x180019da2  inc     ebx
0x180019da4  jmp     short loc_180019D7F
0x180019da6  mov     rsi, [r13+rsi*8+8]
0x180019dab  test    rsi, rsi
0x180019dae  jz      loc_180019E37
0x180019db4  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180019db9  mov     rcx, rdi; this
0x180019dbc  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180019dc1  mov     ebx, eax
0x180019dc3  test    eax, eax
0x180019dc5  js      short loc_180019E3C
0x180019dc7  mov     eax, 7Bh ; '{'
0x180019dcc  cmp     ax, [rsp+2088h+String1]
0x180019dd1  jnz     short loc_180019E37
0x180019dd3  mov     [rsp+2088h+var_2068], 0; int
0x180019ddb  mov     r8, rsi; HKEY
0x180019dde  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180019de3  mov     rcx, rdi; this
0x180019de6  test    r15d, r15d
0x180019de9  jz      short loc_180019E1C
0x180019deb  mov     r14, [rdi]
0x180019dee  mov     r9d, r15d; int
0x180019df1  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180019df6  mov     ebx, eax
0x180019df8  test    eax, eax
0x180019dfa  jns     short loc_180019E2A
0x180019dfc  xor     r9d, r9d; int
0x180019dff  mov     [rdi], r14
0x180019e02  mov     r8, rsi; HKEY
0x180019e05  mov     [rsp+2088h+var_2068], 0; int
0x180019e0d  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180019e12  mov     rcx, rdi; this
0x180019e15  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180019e1a  jmp     short loc_180019E3C
0x180019e1c  xor     r9d, r9d; int
0x180019e1f  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180019e24  mov     ebx, eax
0x180019e26  test    eax, eax
0x180019e28  js      short loc_180019E3C
0x180019e2a  mov     rcx, rdi; this
0x180019e2d  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x180019e32  jmp     loc_180019D58
0x180019e37  mov     ebx, 80020009h
0x180019e3c  mov     rcx, rbp; pv
0x180019e3f  call    cs:__imp_CoTaskMemFree
0x180019e45  mov     eax, ebx
0x180019e47  mov     rcx, [rsp+2088h+var_48]
0x180019e4f  xor     rcx, rsp; StackCookie
0x180019e52  call    __security_check_cookie
0x180019e57  add     rsp, 2050h
0x180019e5e  pop     r15
0x180019e60  pop     r14
0x180019e62  pop     r13
0x180019e64  pop     rdi
0x180019e65  pop     rsi
0x180019e66  pop     rbp
0x180019e67  pop     rbx
0x180019e68  retn
```
