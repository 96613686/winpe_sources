# ATL::CRegParser::RegisterBuffer(ushort *,int)

- ea: `0x18000ab4c`
- end: `0x18000acb9`
- name: `?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z`
- size: `365`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000acc0`

## callees

- `0x1800085e0`
- `0x180009274`
- `0x18000ab4c`
- `0x18000af10`
- `0x18000ba60`
- `0x18002d840`
- `0x18002d900`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ac8f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ac8f`
- `KERNEL32!lstrcmpiW` at `0x18000abe8`
- `KERNEL32!lstrcmpiW` at `0x18000abe8`

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
0x18000ab4c  push    rbx
0x18000ab4e  push    rbp
0x18000ab4f  push    rsi
0x18000ab50  push    rdi
0x18000ab51  push    r13
0x18000ab53  push    r14
0x18000ab55  push    r15
0x18000ab57  mov     eax, 2050h
0x18000ab5c  call    _alloca_probe
0x18000ab61  sub     rsp, rax
0x18000ab64  mov     rax, cs:__security_cookie
0x18000ab6b  xor     rax, rsp
0x18000ab6e  mov     [rsp+2088h+var_48], rax
0x18000ab76  mov     r15d, r8d
0x18000ab79  mov     [rsp+2088h+pv], 0
0x18000ab82  lea     r8, [rsp+2088h+pv]; unsigned __int16 **
0x18000ab87  mov     rdi, rcx
0x18000ab8a  call    ?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z; ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)
0x18000ab8f  mov     ebx, eax
0x18000ab91  test    eax, eax
0x18000ab93  js      loc_18000AC97
0x18000ab99  mov     rbp, [rsp+2088h+pv]
0x18000ab9e  lea     r13, ?map@?1??HKeyFromString@CRegParser@ATL@@KAPEAUHKEY__@@PEAG@Z@4QBUkeymap@?1??123@KAPEAU4@0@Z@B; `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::keymap const near * const `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::map
0x18000aba5  mov     [rdi], rbp
0x18000aba8  mov     rcx, [rdi]
0x18000abab  xor     eax, eax
0x18000abad  cmp     ax, [rcx]
0x18000abb0  jz      loc_18000AC8C
0x18000abb6  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x18000abbb  mov     rcx, rdi; this
0x18000abbe  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000abc3  mov     ebx, eax
0x18000abc5  test    eax, eax
0x18000abc7  js      loc_18000AC8C
0x18000abcd  xor     ebx, ebx
0x18000abcf  cmp     ebx, 0Eh
0x18000abd2  jnb     loc_18000AC87
0x18000abd8  movsxd  rsi, ebx
0x18000abdb  lea     rcx, [rsp+2088h+String1]; lpString1
0x18000abe0  add     rsi, rsi
0x18000abe3  mov     rdx, [r13+rsi*8+0]; lpString2
0x18000abe8  call    cs:__imp_lstrcmpiW
0x18000abee  test    eax, eax
0x18000abf0  jz      short loc_18000ABF6
0x18000abf2  inc     ebx
0x18000abf4  jmp     short loc_18000ABCF
0x18000abf6  mov     rsi, [r13+rsi*8+8]
0x18000abfb  test    rsi, rsi
0x18000abfe  jz      loc_18000AC87
0x18000ac04  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x18000ac09  mov     rcx, rdi; this
0x18000ac0c  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000ac11  mov     ebx, eax
0x18000ac13  test    eax, eax
0x18000ac15  js      short loc_18000AC8C
0x18000ac17  mov     eax, 7Bh ; '{'
0x18000ac1c  cmp     ax, [rsp+2088h+String1]
0x18000ac21  jnz     short loc_18000AC87
0x18000ac23  mov     [rsp+2088h+var_2068], 0; int
0x18000ac2b  mov     r8, rsi; HKEY
0x18000ac2e  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x18000ac33  mov     rcx, rdi; this
0x18000ac36  test    r15d, r15d
0x18000ac39  jz      short loc_18000AC6C
0x18000ac3b  mov     r14, [rdi]
0x18000ac3e  mov     r9d, r15d; int
0x18000ac41  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x18000ac46  mov     ebx, eax
0x18000ac48  test    eax, eax
0x18000ac4a  jns     short loc_18000AC7A
0x18000ac4c  xor     r9d, r9d; int
0x18000ac4f  mov     [rdi], r14
0x18000ac52  mov     r8, rsi; HKEY
0x18000ac55  mov     [rsp+2088h+var_2068], 0; int
0x18000ac5d  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x18000ac62  mov     rcx, rdi; this
0x18000ac65  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x18000ac6a  jmp     short loc_18000AC8C
0x18000ac6c  xor     r9d, r9d; int
0x18000ac6f  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x18000ac74  mov     ebx, eax
0x18000ac76  test    eax, eax
0x18000ac78  js      short loc_18000AC8C
0x18000ac7a  mov     rcx, rdi; this
0x18000ac7d  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x18000ac82  jmp     loc_18000ABA8
0x18000ac87  mov     ebx, 80020009h
0x18000ac8c  mov     rcx, rbp; pv
0x18000ac8f  call    cs:__imp_CoTaskMemFree
0x18000ac95  mov     eax, ebx
0x18000ac97  mov     rcx, [rsp+2088h+var_48]
0x18000ac9f  xor     rcx, rsp; StackCookie
0x18000aca2  call    __security_check_cookie
0x18000aca7  add     rsp, 2050h
0x18000acae  pop     r15
0x18000acb0  pop     r14
0x18000acb2  pop     r13
0x18000acb4  pop     rdi
0x18000acb5  pop     rsi
0x18000acb6  pop     rbp
0x18000acb7  pop     rbx
0x18000acb8  retn
```
