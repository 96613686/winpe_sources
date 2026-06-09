# ATL::CRegParser::RegisterBuffer(ushort *,int)

- ea: `0x180004698`
- end: `0x180004822`
- name: `?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z`
- size: `394`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x180004828`

## callees

- `0x180003fe0`
- `0x18000418c`
- `0x180004698`
- `0x1800049ec`
- `0x18001bf40`
- `0x18001c000`

## import_xrefs

- `KERNEL32!lstrcmpiW` at `0x18000471d`
- `KERNEL32!lstrcmpiW` at `0x18000471d`
- `ole32!CoTaskMemFree` at `0x180004736`
- `ole32!CoTaskMemFree` at `0x180004736`
- `USER32!CharNextW` at `0x180004807`
- `USER32!CharNextW` at `0x180004807`

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
0x180004698  push    rbx
0x18000469a  push    rbp
0x18000469b  push    rsi
0x18000469c  push    rdi
0x18000469d  push    r13
0x18000469f  push    r14
0x1800046a1  push    r15
0x1800046a3  mov     eax, 2050h
0x1800046a8  call    _alloca_probe
0x1800046ad  sub     rsp, rax
0x1800046b0  mov     rax, cs:__security_cookie
0x1800046b7  xor     rax, rsp
0x1800046ba  mov     [rsp+2088h+var_48], rax
0x1800046c2  mov     r15d, r8d
0x1800046c5  mov     [rsp+2088h+pv], 0
0x1800046ce  lea     r8, [rsp+2088h+pv]; unsigned __int16 **
0x1800046d3  mov     rdi, rcx
0x1800046d6  call    ?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z; ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)
0x1800046db  mov     ebx, eax
0x1800046dd  test    eax, eax
0x1800046df  js      short loc_18000473E
0x1800046e1  mov     rbp, [rsp+2088h+pv]
0x1800046e6  xor     eax, eax
0x1800046e8  mov     [rdi], rbp
0x1800046eb  cmp     ax, [rbp+0]
0x1800046ef  jz      short loc_180004733
0x1800046f1  lea     r13, ?map@?1??HKeyFromString@CRegParser@ATL@@KAPEAUHKEY__@@PEAG@Z@4QBUkeymap@?1??123@KAPEAU4@0@Z@B; `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::keymap const near * const `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::map
0x1800046f8  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x1800046fd  mov     rcx, rdi; this
0x180004700  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180004705  mov     ebx, eax
0x180004707  test    eax, eax
0x180004709  js      short loc_180004733
0x18000470b  xor     ebx, ebx
0x18000470d  movsxd  rsi, ebx
0x180004710  lea     rcx, [rsp+2088h+String1]; lpString1
0x180004715  add     rsi, rsi
0x180004718  mov     rdx, [r13+rsi*8+0]; lpString2
0x18000471d  call    cs:__imp_lstrcmpiW
0x180004723  test    eax, eax
0x180004725  jz      short loc_180004760
0x180004727  inc     ebx
0x180004729  cmp     ebx, 0Eh
0x18000472c  jb      short loc_18000470D
0x18000472e  mov     ebx, 80020009h
0x180004733  mov     rcx, rbp; pv
0x180004736  call    cs:__imp_CoTaskMemFree
0x18000473c  mov     eax, ebx
0x18000473e  mov     rcx, [rsp+2088h+var_48]
0x180004746  xor     rcx, rsp; StackCookie
0x180004749  call    __security_check_cookie
0x18000474e  add     rsp, 2050h
0x180004755  pop     r15
0x180004757  pop     r14
0x180004759  pop     r13
0x18000475b  pop     rdi
0x18000475c  pop     rsi
0x18000475d  pop     rbp
0x18000475e  pop     rbx
0x18000475f  retn
0x180004760  mov     rsi, [r13+rsi*8+8]
0x180004765  test    rsi, rsi
0x180004768  jz      short loc_18000472E
0x18000476a  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x18000476f  mov     rcx, rdi; this
0x180004772  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180004777  mov     ebx, eax
0x180004779  test    eax, eax
0x18000477b  js      short loc_180004733
0x18000477d  mov     eax, 7Bh ; '{'
0x180004782  cmp     ax, [rsp+2088h+String1]
0x180004787  jnz     short loc_18000472E
0x180004789  mov     [rsp+2088h+var_2068], 0; int
0x180004791  mov     r8, rsi; HKEY
0x180004794  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180004799  mov     rcx, rdi; this
0x18000479c  test    r15d, r15d
0x18000479f  jz      short loc_1800047D5
0x1800047a1  mov     r14, [rdi]
0x1800047a4  mov     r9d, r15d; int
0x1800047a7  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x1800047ac  mov     ebx, eax
0x1800047ae  test    eax, eax
0x1800047b0  jns     short loc_1800047E7
0x1800047b2  xor     r9d, r9d; int
0x1800047b5  mov     [rdi], r14
0x1800047b8  mov     r8, rsi; HKEY
0x1800047bb  mov     [rsp+2088h+var_2068], 0; int
0x1800047c3  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x1800047c8  mov     rcx, rdi; this
0x1800047cb  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x1800047d0  jmp     loc_180004733
0x1800047d5  xor     r9d, r9d; int
0x1800047d8  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x1800047dd  mov     ebx, eax
0x1800047df  test    eax, eax
0x1800047e1  js      loc_180004733
0x1800047e7  mov     r8, [rdi]
0x1800047ea  movzx   edx, word ptr [r8]
0x1800047ee  mov     ecx, edx
0x1800047f0  sub     ecx, 9
0x1800047f3  jz      short loc_180004804
0x1800047f5  sub     ecx, 1
0x1800047f8  jz      short loc_180004804
0x1800047fa  sub     ecx, 3
0x1800047fd  jz      short loc_180004804
0x1800047ff  cmp     ecx, 13h
0x180004802  jnz     short loc_180004812
0x180004804  mov     rcx, r8; lpsz
0x180004807  call    cs:__imp_CharNextW
0x18000480d  mov     [rdi], rax
0x180004810  jmp     short loc_1800047E7
0x180004812  xor     eax, eax
0x180004814  cmp     ax, dx
0x180004817  jnz     loc_1800046F8
0x18000481d  jmp     loc_180004733
```
