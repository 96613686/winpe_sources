# ATL::CRegParser::RegisterBuffer(wchar_t *,int)

- ea: `0x18000862c`
- end: `0x1800087c0`
- name: `?RegisterBuffer@CRegParser@ATL@@QEAAJPEA_WH@Z`
- size: `404`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, wchar_t *, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800087c8`

## callees

- `0x180006d3c`
- `0x180007d34`
- `0x180007ee0`
- `0x18000862c`
- `0x18002ffd0`
- `0x1800369a0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800086cf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800086cf`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800087a6`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800087a6`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800086b0`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800086b0`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::RegisterBuffer(LPCWSTR *this, wchar_t *a2, int a3)
{
  __int64 result; // rax
  int Token; // ebx
  _WORD *v7; // rbp
  unsigned __int64 v8; // rbx
  LPCWSTR *v9; // rsi
  HKEY v10; // rsi
  LPCWSTR v11; // r14
  LPVOID pv; // [rsp+30h] [rbp-2058h] BYREF
  WCHAR String1[4096]; // [rsp+40h] [rbp-2048h] BYREF

  pv = 0;
  result = ATL::CRegParser::PreProcessBuffer(this, a2, (wchar_t **)&pv);
  Token = result;
  if ( (int)result >= 0 )
  {
    v7 = pv;
    *this = (LPCWSTR)pv;
    if ( *v7 )
    {
      do
      {
        Token = ATL::CRegParser::NextToken(this, String1);
        if ( Token < 0 )
          break;
        v8 = 0;
        v9 = (LPCWSTR *)&`ATL::CRegParser::HKeyFromString'::`2'::map;
        while ( lstrcmpiW(String1, *v9) )
        {
          ++v8;
          v9 += 2;
          if ( v8 >= 0xE )
            goto LABEL_7;
        }
        v10 = (HKEY)*(&`ATL::CRegParser::HKeyFromString'::`2'::map + 2 * v8 + 1);
        if ( !v10 )
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
          v11 = *this;
          Token = ATL::CRegParser::RegisterSubkeys(this, String1, v10, a3, 0);
          if ( Token < 0 )
          {
            *this = v11;
            ATL::CRegParser::RegisterSubkeys(this, String1, v10, 0, 0);
            break;
          }
        }
        else
        {
          Token = ATL::CRegParser::RegisterSubkeys(this, String1, v10, 0, 0);
          if ( Token < 0 )
            break;
        }
        while ( **this == 9 || **this == 10 || **this == 13 || **this == 32 )
          *this = CharNextW(*this);
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
0x18000862c  mov     [rsp+arg_18], rbx
0x180008631  push    rbp
0x180008632  push    rsi
0x180008633  push    rdi
0x180008634  push    r12
0x180008636  push    r13
0x180008638  push    r14
0x18000863a  push    r15
0x18000863c  mov     eax, 2050h
0x180008641  call    _alloca_probe
0x180008646  sub     rsp, rax
0x180008649  mov     rax, cs:__security_cookie
0x180008650  xor     rax, rsp
0x180008653  mov     [rsp+2088h+var_48], rax
0x18000865b  mov     r15d, r8d
0x18000865e  xor     r12d, r12d
0x180008661  lea     r8, [rsp+2088h+pv]; wchar_t **
0x180008666  mov     [rsp+2088h+pv], r12
0x18000866b  mov     rdi, rcx
0x18000866e  call    ?PreProcessBuffer@CRegParser@ATL@@QEAAJPEA_WPEAPEA_W@Z; ATL::CRegParser::PreProcessBuffer(wchar_t *,wchar_t * *)
0x180008673  mov     ebx, eax
0x180008675  test    eax, eax
0x180008677  js      short loc_1800086D7
0x180008679  mov     rbp, [rsp+2088h+pv]
0x18000867e  mov     [rdi], rbp
0x180008681  cmp     r12w, [rbp+0]
0x180008686  jz      short loc_1800086CC
0x180008688  lea     r13, ?map@?1??HKeyFromString@CRegParser@ATL@@KAPEAUHKEY__@@PEA_W@Z@4QBUkeymap@?1??123@KAPEAU4@0@Z@B; `ATL::CRegParser::HKeyFromString(wchar_t *)'::`2'::keymap const near * const `ATL::CRegParser::HKeyFromString(wchar_t *)'::`2'::map
0x18000868f  lea     rdx, [rsp+2088h+String1]; wchar_t *
0x180008694  mov     rcx, rdi; this
0x180008697  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x18000869c  mov     ebx, eax
0x18000869e  test    eax, eax
0x1800086a0  js      short loc_1800086CC
0x1800086a2  mov     rbx, r12
0x1800086a5  mov     rsi, r13
0x1800086a8  mov     rdx, [rsi]; lpString2
0x1800086ab  lea     rcx, [rsp+2088h+String1]; lpString1
0x1800086b0  call    cs:__imp_lstrcmpiW
0x1800086b6  test    eax, eax
0x1800086b8  jz      short loc_180008702
0x1800086ba  inc     rbx
0x1800086bd  add     rsi, 10h
0x1800086c1  cmp     rbx, 0Eh
0x1800086c5  jb      short loc_1800086A8
0x1800086c7  mov     ebx, 80020009h
0x1800086cc  mov     rcx, rbp; pv
0x1800086cf  call    cs:__imp_CoTaskMemFree
0x1800086d5  mov     eax, ebx
0x1800086d7  mov     rcx, [rsp+2088h+var_48]
0x1800086df  xor     rcx, rsp; StackCookie
0x1800086e2  call    __security_check_cookie
0x1800086e7  mov     rbx, [rsp+2088h+arg_18]
0x1800086ef  add     rsp, 2050h
0x1800086f6  pop     r15
0x1800086f8  pop     r14
0x1800086fa  pop     r13
0x1800086fc  pop     r12
0x1800086fe  pop     rdi
0x1800086ff  pop     rsi
0x180008700  pop     rbp
0x180008701  retn
0x180008702  add     rbx, rbx
0x180008705  mov     rsi, [r13+rbx*8+8]
0x18000870a  test    rsi, rsi
0x18000870d  jz      short loc_1800086C7
0x18000870f  lea     rdx, [rsp+2088h+String1]; wchar_t *
0x180008714  mov     rcx, rdi; this
0x180008717  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x18000871c  mov     ebx, eax
0x18000871e  test    eax, eax
0x180008720  js      short loc_1800086CC
0x180008722  mov     eax, 7Bh ; '{'
0x180008727  cmp     ax, [rsp+2088h+String1]
0x18000872c  jnz     short loc_1800086C7
0x18000872e  mov     [rsp+2088h+var_2068], r12d; int
0x180008733  mov     r8, rsi; HKEY
0x180008736  lea     rdx, [rsp+2088h+String1]; wchar_t *
0x18000873b  mov     rcx, rdi; this
0x18000873e  test    r15d, r15d
0x180008741  jz      short loc_180008774
0x180008743  mov     r14, [rdi]
0x180008746  mov     r9d, r15d; int
0x180008749  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEA_WPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(wchar_t *,HKEY__ *,int,int)
0x18000874e  mov     ebx, eax
0x180008750  test    eax, eax
0x180008752  jns     short loc_180008786
0x180008754  xor     r9d, r9d; int
0x180008757  mov     [rdi], r14
0x18000875a  mov     r8, rsi; HKEY
0x18000875d  mov     [rsp+2088h+var_2068], r12d; int
0x180008762  lea     rdx, [rsp+2088h+String1]; wchar_t *
0x180008767  mov     rcx, rdi; this
0x18000876a  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEA_WPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(wchar_t *,HKEY__ *,int,int)
0x18000876f  jmp     loc_1800086CC
0x180008774  xor     r9d, r9d; int
0x180008777  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEA_WPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(wchar_t *,HKEY__ *,int,int)
0x18000877c  mov     ebx, eax
0x18000877e  test    eax, eax
0x180008780  js      loc_1800086CC
0x180008786  mov     r8, [rdi]
0x180008789  movzx   edx, word ptr [r8]
0x18000878d  mov     ecx, edx
0x18000878f  sub     ecx, 9
0x180008792  jz      short loc_1800087A3
0x180008794  sub     ecx, 1
0x180008797  jz      short loc_1800087A3
0x180008799  sub     ecx, 3
0x18000879c  jz      short loc_1800087A3
0x18000879e  cmp     ecx, 13h
0x1800087a1  jnz     short loc_1800087B1
0x1800087a3  mov     rcx, r8; lpsz
0x1800087a6  call    cs:__imp_CharNextW
0x1800087ac  mov     [rdi], rax
0x1800087af  jmp     short loc_180008786
0x1800087b1  cmp     r12w, dx
0x1800087b5  jnz     loc_18000868F
0x1800087bb  jmp     loc_1800086CC
```
