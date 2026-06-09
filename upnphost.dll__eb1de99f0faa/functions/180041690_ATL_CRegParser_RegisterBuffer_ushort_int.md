# ATL::CRegParser::RegisterBuffer(ushort *,int)

- ea: `0x180041690`
- end: `0x1800417fa`
- name: `?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z`
- size: `362`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x180041918`

## callees

- `0x18003a560`
- `0x180040630`
- `0x180040a04`
- `0x180041690`
- `0x180041ab0`
- `0x180042e7c`
- `0x1800542a0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004172e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004172e`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180041715`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180041715`

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
0x180041690  push    rbx
0x180041692  push    rbp
0x180041693  push    rsi
0x180041694  push    rdi
0x180041695  push    r13
0x180041697  push    r14
0x180041699  push    r15
0x18004169b  mov     eax, 2050h
0x1800416a0  call    _alloca_probe
0x1800416a5  sub     rsp, rax
0x1800416a8  mov     rax, cs:__security_cookie
0x1800416af  xor     rax, rsp
0x1800416b2  mov     [rsp+2088h+var_48], rax
0x1800416ba  mov     r15d, r8d
0x1800416bd  mov     [rsp+2088h+pv], 0
0x1800416c6  lea     r8, [rsp+2088h+pv]; unsigned __int16 **
0x1800416cb  mov     rdi, rcx
0x1800416ce  call    ?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z; ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)
0x1800416d3  mov     ebx, eax
0x1800416d5  test    eax, eax
0x1800416d7  js      short loc_180041736
0x1800416d9  mov     rbp, [rsp+2088h+pv]
0x1800416de  xor     eax, eax
0x1800416e0  mov     [rdi], rbp
0x1800416e3  cmp     ax, [rbp+0]
0x1800416e7  jz      short loc_18004172B
0x1800416e9  lea     r13, ?map@?1??HKeyFromString@CRegParser@ATL@@KAPEAUHKEY__@@PEAG@Z@4QBUkeymap@?1??123@KAPEAU4@0@Z@B; `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::keymap const near * const `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::map
0x1800416f0  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x1800416f5  mov     rcx, rdi; this
0x1800416f8  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800416fd  mov     ebx, eax
0x1800416ff  test    eax, eax
0x180041701  js      short loc_18004172B
0x180041703  xor     ebx, ebx
0x180041705  movsxd  rsi, ebx
0x180041708  lea     rcx, [rsp+2088h+String1]; lpString1
0x18004170d  add     rsi, rsi
0x180041710  mov     rdx, [r13+rsi*8+0]; lpString2
0x180041715  call    cs:__imp_lstrcmpiW
0x18004171b  test    eax, eax
0x18004171d  jz      short loc_180041758
0x18004171f  inc     ebx
0x180041721  cmp     ebx, 0Eh
0x180041724  jb      short loc_180041705
0x180041726  mov     ebx, 80020009h
0x18004172b  mov     rcx, rbp; pv
0x18004172e  call    cs:__imp_CoTaskMemFree
0x180041734  mov     eax, ebx
0x180041736  mov     rcx, [rsp+2088h+var_48]
0x18004173e  xor     rcx, rsp; StackCookie
0x180041741  call    __security_check_cookie
0x180041746  add     rsp, 2050h
0x18004174d  pop     r15
0x18004174f  pop     r14
0x180041751  pop     r13
0x180041753  pop     rdi
0x180041754  pop     rsi
0x180041755  pop     rbp
0x180041756  pop     rbx
0x180041757  retn
0x180041758  mov     rsi, [r13+rsi*8+8]
0x18004175d  test    rsi, rsi
0x180041760  jz      short loc_180041726
0x180041762  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180041767  mov     rcx, rdi; this
0x18004176a  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18004176f  mov     ebx, eax
0x180041771  test    eax, eax
0x180041773  js      short loc_18004172B
0x180041775  mov     eax, 7Bh ; '{'
0x18004177a  cmp     ax, [rsp+2088h+String1]
0x18004177f  jnz     short loc_180041726
0x180041781  mov     [rsp+2088h+var_2068], 0; int
0x180041789  mov     r8, rsi; HKEY
0x18004178c  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180041791  mov     rcx, rdi; this
0x180041794  test    r15d, r15d
0x180041797  jz      short loc_1800417CD
0x180041799  mov     r14, [rdi]
0x18004179c  mov     r9d, r15d; int
0x18004179f  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x1800417a4  mov     ebx, eax
0x1800417a6  test    eax, eax
0x1800417a8  jns     short loc_1800417DF
0x1800417aa  xor     r9d, r9d; int
0x1800417ad  mov     [rdi], r14
0x1800417b0  mov     r8, rsi; HKEY
0x1800417b3  mov     [rsp+2088h+var_2068], 0; int
0x1800417bb  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x1800417c0  mov     rcx, rdi; this
0x1800417c3  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x1800417c8  jmp     loc_18004172B
0x1800417cd  xor     r9d, r9d; int
0x1800417d0  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x1800417d5  mov     ebx, eax
0x1800417d7  test    eax, eax
0x1800417d9  js      loc_18004172B
0x1800417df  mov     rcx, rdi; this
0x1800417e2  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x1800417e7  mov     rcx, [rdi]
0x1800417ea  xor     eax, eax
0x1800417ec  cmp     ax, [rcx]
0x1800417ef  jnz     loc_1800416F0
0x1800417f5  jmp     loc_18004172B
```
