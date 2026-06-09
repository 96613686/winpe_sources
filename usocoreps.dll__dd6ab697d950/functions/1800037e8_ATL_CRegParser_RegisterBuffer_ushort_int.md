# ATL::CRegParser::RegisterBuffer(ushort *,int)

- ea: `0x1800037e8`
- end: `0x180003972`
- name: `?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z`
- size: `394`
- prototype: `__int64 __fastcall(LPCWSTR *this, unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x180003978`

## callees

- `0x180001510`
- `0x1800031f4`
- `0x180003394`
- `0x1800037e8`
- `0x180003b5c`
- `0x180004e40`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003886`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003886`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180003957`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180003957`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000386d`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000386d`

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
0x1800037e8  push    rbx
0x1800037ea  push    rbp
0x1800037eb  push    rsi
0x1800037ec  push    rdi
0x1800037ed  push    r13
0x1800037ef  push    r14
0x1800037f1  push    r15
0x1800037f3  mov     eax, 2050h
0x1800037f8  call    _alloca_probe
0x1800037fd  sub     rsp, rax
0x180003800  mov     rax, cs:__security_cookie
0x180003807  xor     rax, rsp
0x18000380a  mov     [rsp+2088h+var_48], rax
0x180003812  mov     r15d, r8d
0x180003815  mov     [rsp+2088h+pv], 0
0x18000381e  lea     r8, [rsp+2088h+pv]; unsigned __int16 **
0x180003823  mov     rdi, rcx
0x180003826  call    ?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z; ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)
0x18000382b  mov     ebx, eax
0x18000382d  test    eax, eax
0x18000382f  js      short loc_18000388E
0x180003831  mov     rbp, [rsp+2088h+pv]
0x180003836  xor     eax, eax
0x180003838  mov     [rdi], rbp
0x18000383b  cmp     ax, [rbp+0]
0x18000383f  jz      short loc_180003883
0x180003841  lea     r13, ?map@?1??HKeyFromString@CRegParser@ATL@@KAPEAUHKEY__@@PEAG@Z@4QBUkeymap@?1??123@KAPEAU4@0@Z@B; `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::keymap const near * const `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::map
0x180003848  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x18000384d  mov     rcx, rdi; this
0x180003850  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180003855  mov     ebx, eax
0x180003857  test    eax, eax
0x180003859  js      short loc_180003883
0x18000385b  xor     ebx, ebx
0x18000385d  movsxd  rsi, ebx
0x180003860  lea     rcx, [rsp+2088h+String1]; lpString1
0x180003865  add     rsi, rsi
0x180003868  mov     rdx, [r13+rsi*8+0]; lpString2
0x18000386d  call    cs:__imp_lstrcmpiW
0x180003873  test    eax, eax
0x180003875  jz      short loc_1800038B0
0x180003877  inc     ebx
0x180003879  cmp     ebx, 0Eh
0x18000387c  jb      short loc_18000385D
0x18000387e  mov     ebx, 80020009h
0x180003883  mov     rcx, rbp; pv
0x180003886  call    cs:__imp_CoTaskMemFree
0x18000388c  mov     eax, ebx
0x18000388e  mov     rcx, [rsp+2088h+var_48]
0x180003896  xor     rcx, rsp; StackCookie
0x180003899  call    __security_check_cookie
0x18000389e  add     rsp, 2050h
0x1800038a5  pop     r15
0x1800038a7  pop     r14
0x1800038a9  pop     r13
0x1800038ab  pop     rdi
0x1800038ac  pop     rsi
0x1800038ad  pop     rbp
0x1800038ae  pop     rbx
0x1800038af  retn
0x1800038b0  mov     rsi, [r13+rsi*8+8]
0x1800038b5  test    rsi, rsi
0x1800038b8  jz      short loc_18000387E
0x1800038ba  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x1800038bf  mov     rcx, rdi; this
0x1800038c2  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800038c7  mov     ebx, eax
0x1800038c9  test    eax, eax
0x1800038cb  js      short loc_180003883
0x1800038cd  mov     eax, 7Bh ; '{'
0x1800038d2  cmp     ax, [rsp+2088h+String1]
0x1800038d7  jnz     short loc_18000387E
0x1800038d9  mov     [rsp+2088h+var_2068], 0; int
0x1800038e1  mov     r8, rsi; HKEY
0x1800038e4  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x1800038e9  mov     rcx, rdi; this
0x1800038ec  test    r15d, r15d
0x1800038ef  jz      short loc_180003925
0x1800038f1  mov     r14, [rdi]
0x1800038f4  mov     r9d, r15d; int
0x1800038f7  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x1800038fc  mov     ebx, eax
0x1800038fe  test    eax, eax
0x180003900  jns     short loc_180003937
0x180003902  xor     r9d, r9d; int
0x180003905  mov     [rdi], r14
0x180003908  mov     r8, rsi; HKEY
0x18000390b  mov     [rsp+2088h+var_2068], 0; int
0x180003913  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180003918  mov     rcx, rdi; this
0x18000391b  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180003920  jmp     loc_180003883
0x180003925  xor     r9d, r9d; int
0x180003928  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x18000392d  mov     ebx, eax
0x18000392f  test    eax, eax
0x180003931  js      loc_180003883
0x180003937  mov     r8, [rdi]
0x18000393a  movzx   edx, word ptr [r8]
0x18000393e  mov     ecx, edx
0x180003940  sub     ecx, 9
0x180003943  jz      short loc_180003954
0x180003945  sub     ecx, 1
0x180003948  jz      short loc_180003954
0x18000394a  sub     ecx, 3
0x18000394d  jz      short loc_180003954
0x18000394f  cmp     ecx, 13h
0x180003952  jnz     short loc_180003962
0x180003954  mov     rcx, r8; lpsz
0x180003957  call    cs:__imp_CharNextW
0x18000395d  mov     [rdi], rax
0x180003960  jmp     short loc_180003937
0x180003962  xor     eax, eax
0x180003964  cmp     ax, dx
0x180003967  jnz     loc_180003848
0x18000396d  jmp     loc_180003883
```
