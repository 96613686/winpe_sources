# ATL::CRegParser::RegisterBuffer(ushort *,int)

- ea: `0x18000527c`
- end: `0x1800053e9`
- name: `?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z`
- size: `365`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800053f0`

## callees

- `0x180004b60`
- `0x180004d18`
- `0x18000527c`
- `0x1800055a0`
- `0x180005ef0`
- `0x180012800`
- `0x1800128c0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800053bf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800053bf`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180005318`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180005318`

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
0x18000527c  push    rbx
0x18000527e  push    rbp
0x18000527f  push    rsi
0x180005280  push    rdi
0x180005281  push    r13
0x180005283  push    r14
0x180005285  push    r15
0x180005287  mov     eax, 2050h
0x18000528c  call    _alloca_probe
0x180005291  sub     rsp, rax
0x180005294  mov     rax, cs:__security_cookie
0x18000529b  xor     rax, rsp
0x18000529e  mov     [rsp+2088h+var_48], rax
0x1800052a6  mov     r15d, r8d
0x1800052a9  mov     [rsp+2088h+pv], 0
0x1800052b2  lea     r8, [rsp+2088h+pv]; unsigned __int16 **
0x1800052b7  mov     rdi, rcx
0x1800052ba  call    ?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z; ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)
0x1800052bf  mov     ebx, eax
0x1800052c1  test    eax, eax
0x1800052c3  js      loc_1800053C7
0x1800052c9  mov     rbp, [rsp+2088h+pv]
0x1800052ce  lea     r13, ?map@?1??HKeyFromString@CRegParser@ATL@@KAPEAUHKEY__@@PEAG@Z@4QBUkeymap@?1??123@KAPEAU4@0@Z@B; `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::keymap const near * const `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::map
0x1800052d5  mov     [rdi], rbp
0x1800052d8  mov     rcx, [rdi]
0x1800052db  xor     eax, eax
0x1800052dd  cmp     ax, [rcx]
0x1800052e0  jz      loc_1800053BC
0x1800052e6  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x1800052eb  mov     rcx, rdi; this
0x1800052ee  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800052f3  mov     ebx, eax
0x1800052f5  test    eax, eax
0x1800052f7  js      loc_1800053BC
0x1800052fd  xor     ebx, ebx
0x1800052ff  cmp     ebx, 0Eh
0x180005302  jnb     loc_1800053B7
0x180005308  movsxd  rsi, ebx
0x18000530b  lea     rcx, [rsp+2088h+String1]; lpString1
0x180005310  add     rsi, rsi
0x180005313  mov     rdx, [r13+rsi*8+0]; lpString2
0x180005318  call    cs:__imp_lstrcmpiW
0x18000531e  test    eax, eax
0x180005320  jz      short loc_180005326
0x180005322  inc     ebx
0x180005324  jmp     short loc_1800052FF
0x180005326  mov     rsi, [r13+rsi*8+8]
0x18000532b  test    rsi, rsi
0x18000532e  jz      loc_1800053B7
0x180005334  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180005339  mov     rcx, rdi; this
0x18000533c  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180005341  mov     ebx, eax
0x180005343  test    eax, eax
0x180005345  js      short loc_1800053BC
0x180005347  mov     eax, 7Bh ; '{'
0x18000534c  cmp     ax, [rsp+2088h+String1]
0x180005351  jnz     short loc_1800053B7
0x180005353  mov     [rsp+2088h+var_2068], 0; int
0x18000535b  mov     r8, rsi; HKEY
0x18000535e  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180005363  mov     rcx, rdi; this
0x180005366  test    r15d, r15d
0x180005369  jz      short loc_18000539C
0x18000536b  mov     r14, [rdi]
0x18000536e  mov     r9d, r15d; int
0x180005371  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180005376  mov     ebx, eax
0x180005378  test    eax, eax
0x18000537a  jns     short loc_1800053AA
0x18000537c  xor     r9d, r9d; int
0x18000537f  mov     [rdi], r14
0x180005382  mov     r8, rsi; HKEY
0x180005385  mov     [rsp+2088h+var_2068], 0; int
0x18000538d  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180005392  mov     rcx, rdi; this
0x180005395  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x18000539a  jmp     short loc_1800053BC
0x18000539c  xor     r9d, r9d; int
0x18000539f  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x1800053a4  mov     ebx, eax
0x1800053a6  test    eax, eax
0x1800053a8  js      short loc_1800053BC
0x1800053aa  mov     rcx, rdi; this
0x1800053ad  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x1800053b2  jmp     loc_1800052D8
0x1800053b7  mov     ebx, 80020009h
0x1800053bc  mov     rcx, rbp; pv
0x1800053bf  call    cs:__imp_CoTaskMemFree
0x1800053c5  mov     eax, ebx
0x1800053c7  mov     rcx, [rsp+2088h+var_48]
0x1800053cf  xor     rcx, rsp; StackCookie
0x1800053d2  call    __security_check_cookie
0x1800053d7  add     rsp, 2050h
0x1800053de  pop     r15
0x1800053e0  pop     r14
0x1800053e2  pop     r13
0x1800053e4  pop     rdi
0x1800053e5  pop     rsi
0x1800053e6  pop     rbp
0x1800053e7  pop     rbx
0x1800053e8  retn
```
