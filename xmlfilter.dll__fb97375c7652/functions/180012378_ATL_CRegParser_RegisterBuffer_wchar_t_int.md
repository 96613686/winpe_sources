# ATL::CRegParser::RegisterBuffer(wchar_t *,int)

- ea: `0x180012378`
- end: `0x180012502`
- name: `?RegisterBuffer@CRegParser@ATL@@QEAAJPEA_WH@Z`
- size: `394`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, wchar_t *, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x180012508`

## callees

- `0x1800020e0`
- `0x180011ca0`
- `0x180011e40`
- `0x180012378`
- `0x1800126ec`
- `0x180014400`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012416`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012416`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800124e7`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800124e7`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800123fd`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800123fd`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::RegisterBuffer(ATL::CRegParser *this, wchar_t *a2, int a3)
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
  result = ATL::CRegParser::PreProcessBuffer(this, a2, (wchar_t **)&pv);
  Token = result;
  if ( (int)result >= 0 )
  {
    v7 = pv;
    *(_QWORD *)this = pv;
    if ( *v7 )
    {
      do
      {
        Token = ATL::CRegParser::NextToken((LPCWSTR *)this, String1);
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
        Token = ATL::CRegParser::NextToken((LPCWSTR *)this, String1);
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
        while ( **(_WORD **)this == 9 || **(_WORD **)this == 10 || **(_WORD **)this == 13 || **(_WORD **)this == 32 )
          *(_QWORD *)this = CharNextW(*(LPCWSTR *)this);
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
0x180012378  push    rbx
0x18001237a  push    rbp
0x18001237b  push    rsi
0x18001237c  push    rdi
0x18001237d  push    r13
0x18001237f  push    r14
0x180012381  push    r15
0x180012383  mov     eax, 2050h
0x180012388  call    _alloca_probe
0x18001238d  sub     rsp, rax
0x180012390  mov     rax, cs:__security_cookie
0x180012397  xor     rax, rsp
0x18001239a  mov     [rsp+2088h+var_48], rax
0x1800123a2  mov     r15d, r8d
0x1800123a5  mov     [rsp+2088h+pv], 0
0x1800123ae  lea     r8, [rsp+2088h+pv]; wchar_t **
0x1800123b3  mov     rdi, rcx
0x1800123b6  call    ?PreProcessBuffer@CRegParser@ATL@@QEAAJPEA_WPEAPEA_W@Z; ATL::CRegParser::PreProcessBuffer(wchar_t *,wchar_t * *)
0x1800123bb  mov     ebx, eax
0x1800123bd  test    eax, eax
0x1800123bf  js      short loc_18001241E
0x1800123c1  mov     rbp, [rsp+2088h+pv]
0x1800123c6  xor     eax, eax
0x1800123c8  mov     [rdi], rbp
0x1800123cb  cmp     ax, [rbp+0]
0x1800123cf  jz      short loc_180012413
0x1800123d1  lea     r13, ?map@?1??HKeyFromString@CRegParser@ATL@@KAPEAUHKEY__@@PEA_W@Z@4QBUkeymap@?1??123@KAPEAU4@0@Z@B; `ATL::CRegParser::HKeyFromString(wchar_t *)'::`2'::keymap const near * const `ATL::CRegParser::HKeyFromString(wchar_t *)'::`2'::map
0x1800123d8  lea     rdx, [rsp+2088h+String1]; wchar_t *
0x1800123dd  mov     rcx, rdi; this
0x1800123e0  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x1800123e5  mov     ebx, eax
0x1800123e7  test    eax, eax
0x1800123e9  js      short loc_180012413
0x1800123eb  xor     ebx, ebx
0x1800123ed  movsxd  rsi, ebx
0x1800123f0  lea     rcx, [rsp+2088h+String1]; lpString1
0x1800123f5  add     rsi, rsi
0x1800123f8  mov     rdx, [r13+rsi*8+0]; lpString2
0x1800123fd  call    cs:__imp_lstrcmpiW
0x180012403  test    eax, eax
0x180012405  jz      short loc_180012440
0x180012407  inc     ebx
0x180012409  cmp     ebx, 0Eh
0x18001240c  jb      short loc_1800123ED
0x18001240e  mov     ebx, 80020009h
0x180012413  mov     rcx, rbp; pv
0x180012416  call    cs:__imp_CoTaskMemFree
0x18001241c  mov     eax, ebx
0x18001241e  mov     rcx, [rsp+2088h+var_48]
0x180012426  xor     rcx, rsp; StackCookie
0x180012429  call    __security_check_cookie
0x18001242e  add     rsp, 2050h
0x180012435  pop     r15
0x180012437  pop     r14
0x180012439  pop     r13
0x18001243b  pop     rdi
0x18001243c  pop     rsi
0x18001243d  pop     rbp
0x18001243e  pop     rbx
0x18001243f  retn
0x180012440  mov     rsi, [r13+rsi*8+8]
0x180012445  test    rsi, rsi
0x180012448  jz      short loc_18001240E
0x18001244a  lea     rdx, [rsp+2088h+String1]; wchar_t *
0x18001244f  mov     rcx, rdi; this
0x180012452  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x180012457  mov     ebx, eax
0x180012459  test    eax, eax
0x18001245b  js      short loc_180012413
0x18001245d  mov     eax, 7Bh ; '{'
0x180012462  cmp     ax, [rsp+2088h+String1]
0x180012467  jnz     short loc_18001240E
0x180012469  mov     [rsp+2088h+var_2068], 0; int
0x180012471  mov     r8, rsi; HKEY
0x180012474  lea     rdx, [rsp+2088h+String1]; wchar_t *
0x180012479  mov     rcx, rdi; this
0x18001247c  test    r15d, r15d
0x18001247f  jz      short loc_1800124B5
0x180012481  mov     r14, [rdi]
0x180012484  mov     r9d, r15d; int
0x180012487  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEA_WPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(wchar_t *,HKEY__ *,int,int)
0x18001248c  mov     ebx, eax
0x18001248e  test    eax, eax
0x180012490  jns     short loc_1800124C7
0x180012492  xor     r9d, r9d; int
0x180012495  mov     [rdi], r14
0x180012498  mov     r8, rsi; HKEY
0x18001249b  mov     [rsp+2088h+var_2068], 0; int
0x1800124a3  lea     rdx, [rsp+2088h+String1]; wchar_t *
0x1800124a8  mov     rcx, rdi; this
0x1800124ab  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEA_WPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(wchar_t *,HKEY__ *,int,int)
0x1800124b0  jmp     loc_180012413
0x1800124b5  xor     r9d, r9d; int
0x1800124b8  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEA_WPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(wchar_t *,HKEY__ *,int,int)
0x1800124bd  mov     ebx, eax
0x1800124bf  test    eax, eax
0x1800124c1  js      loc_180012413
0x1800124c7  mov     r8, [rdi]
0x1800124ca  movzx   edx, word ptr [r8]
0x1800124ce  mov     ecx, edx
0x1800124d0  sub     ecx, 9
0x1800124d3  jz      short loc_1800124E4
0x1800124d5  sub     ecx, 1
0x1800124d8  jz      short loc_1800124E4
0x1800124da  sub     ecx, 3
0x1800124dd  jz      short loc_1800124E4
0x1800124df  cmp     ecx, 13h
0x1800124e2  jnz     short loc_1800124F2
0x1800124e4  mov     rcx, r8; lpsz
0x1800124e7  call    cs:__imp_CharNextW
0x1800124ed  mov     [rdi], rax
0x1800124f0  jmp     short loc_1800124C7
0x1800124f2  xor     eax, eax
0x1800124f4  cmp     ax, dx
0x1800124f7  jnz     loc_1800123D8
0x1800124fd  jmp     loc_180012413
```
