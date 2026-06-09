# ATL::CRegParser::RegisterBuffer(ushort *,int)

- ea: `0x18000d27c`
- end: `0x18000d3e6`
- name: `?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z`
- size: `362`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000d3ec`

## callees

- `0x18000ccc4`
- `0x18000cea4`
- `0x18000d27c`
- `0x18000d678`
- `0x18000f7f4`
- `0x180035bd0`
- `0x180035c60`

## import_xrefs

- `KERNEL32!lstrcmpiW` at `0x18000d301`
- `KERNEL32!lstrcmpiW` at `0x18000d301`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d31a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d31a`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::RegisterBuffer(LPCWSTR *this, unsigned __int16 *a2, int a3)
{
  __int64 result; // rax
  int Token; // ebx
  _WORD *v7; // rbp
  int v8; // ebx
  HKEY v9; // rsi
  LPCWSTR v10; // r14
  LPVOID pv; // [rsp+30h] [rbp-2058h] BYREF
  WCHAR String1[4096]; // [rsp+40h] [rbp-2048h] BYREF

  pv = 0;
  result = ATL::CRegParser::PreProcessBuffer(this, a2, (unsigned __int16 **)&pv);
  Token = result;
  if ( (int)result >= 0 )
  {
    v7 = pv;
    *this = (LPCWSTR)pv;
    if ( *v7 )
    {
      do
      {
        Token = ATL::CRegParser::NextToken((ATL::CRegParser *)this, String1);
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
        Token = ATL::CRegParser::NextToken((ATL::CRegParser *)this, String1);
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
      while ( **this );
    }
    CoTaskMemFree(v7);
    return (unsigned int)Token;
  }
  return result;
}

```

## disassembly

```asm
0x18000d27c  push    rbx
0x18000d27e  push    rbp
0x18000d27f  push    rsi
0x18000d280  push    rdi
0x18000d281  push    r13
0x18000d283  push    r14
0x18000d285  push    r15
0x18000d287  mov     eax, 2050h
0x18000d28c  call    _alloca_probe
0x18000d291  sub     rsp, rax
0x18000d294  mov     rax, cs:__security_cookie
0x18000d29b  xor     rax, rsp
0x18000d29e  mov     [rsp+2088h+var_48], rax
0x18000d2a6  mov     r15d, r8d
0x18000d2a9  mov     [rsp+2088h+pv], 0
0x18000d2b2  lea     r8, [rsp+2088h+pv]; unsigned __int16 **
0x18000d2b7  mov     rdi, rcx
0x18000d2ba  call    ?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z; ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)
0x18000d2bf  mov     ebx, eax
0x18000d2c1  test    eax, eax
0x18000d2c3  js      short loc_18000D322
0x18000d2c5  mov     rbp, [rsp+2088h+pv]
0x18000d2ca  xor     eax, eax
0x18000d2cc  mov     [rdi], rbp
0x18000d2cf  cmp     ax, [rbp+0]
0x18000d2d3  jz      short loc_18000D317
0x18000d2d5  lea     r13, ?map@?1??HKeyFromString@CRegParser@ATL@@KAPEAUHKEY__@@PEAG@Z@4QBUkeymap@?1??123@KAPEAU4@0@Z@B; `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::keymap const near * const `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::map
0x18000d2dc  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x18000d2e1  mov     rcx, rdi; this
0x18000d2e4  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000d2e9  mov     ebx, eax
0x18000d2eb  test    eax, eax
0x18000d2ed  js      short loc_18000D317
0x18000d2ef  xor     ebx, ebx
0x18000d2f1  movsxd  rsi, ebx
0x18000d2f4  lea     rcx, [rsp+2088h+String1]; lpString1
0x18000d2f9  add     rsi, rsi
0x18000d2fc  mov     rdx, [r13+rsi*8+0]; lpString2
0x18000d301  call    cs:__imp_lstrcmpiW
0x18000d307  test    eax, eax
0x18000d309  jz      short loc_18000D344
0x18000d30b  inc     ebx
0x18000d30d  cmp     ebx, 0Eh
0x18000d310  jb      short loc_18000D2F1
0x18000d312  mov     ebx, 80020009h
0x18000d317  mov     rcx, rbp; pv
0x18000d31a  call    cs:__imp_CoTaskMemFree
0x18000d320  mov     eax, ebx
0x18000d322  mov     rcx, [rsp+2088h+var_48]
0x18000d32a  xor     rcx, rsp; StackCookie
0x18000d32d  call    __security_check_cookie
0x18000d332  add     rsp, 2050h
0x18000d339  pop     r15
0x18000d33b  pop     r14
0x18000d33d  pop     r13
0x18000d33f  pop     rdi
0x18000d340  pop     rsi
0x18000d341  pop     rbp
0x18000d342  pop     rbx
0x18000d343  retn
0x18000d344  mov     rsi, [r13+rsi*8+8]
0x18000d349  test    rsi, rsi
0x18000d34c  jz      short loc_18000D312
0x18000d34e  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x18000d353  mov     rcx, rdi; this
0x18000d356  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000d35b  mov     ebx, eax
0x18000d35d  test    eax, eax
0x18000d35f  js      short loc_18000D317
0x18000d361  mov     eax, 7Bh ; '{'
0x18000d366  cmp     ax, [rsp+2088h+String1]
0x18000d36b  jnz     short loc_18000D312
0x18000d36d  mov     [rsp+2088h+var_2068], 0; int
0x18000d375  mov     r8, rsi; HKEY
0x18000d378  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x18000d37d  mov     rcx, rdi; this
0x18000d380  test    r15d, r15d
0x18000d383  jz      short loc_18000D3B9
0x18000d385  mov     r14, [rdi]
0x18000d388  mov     r9d, r15d; int
0x18000d38b  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x18000d390  mov     ebx, eax
0x18000d392  test    eax, eax
0x18000d394  jns     short loc_18000D3CB
0x18000d396  xor     r9d, r9d; int
0x18000d399  mov     [rdi], r14
0x18000d39c  mov     r8, rsi; HKEY
0x18000d39f  mov     [rsp+2088h+var_2068], 0; int
0x18000d3a7  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x18000d3ac  mov     rcx, rdi; this
0x18000d3af  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x18000d3b4  jmp     loc_18000D317
0x18000d3b9  xor     r9d, r9d; int
0x18000d3bc  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x18000d3c1  mov     ebx, eax
0x18000d3c3  test    eax, eax
0x18000d3c5  js      loc_18000D317
0x18000d3cb  mov     rcx, rdi; this
0x18000d3ce  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x18000d3d3  mov     rcx, [rdi]
0x18000d3d6  xor     eax, eax
0x18000d3d8  cmp     ax, [rcx]
0x18000d3db  jnz     loc_18000D2DC
0x18000d3e1  jmp     loc_18000D317
```
