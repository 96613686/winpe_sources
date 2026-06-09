# ATL::CRegParser::RegisterBuffer(ushort *,int)

- ea: `0x18000758c`
- end: `0x1800076f9`
- name: `?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z`
- size: `365`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x180007700`

## callees

- `0x180006b10`
- `0x180006cc8`
- `0x18000758c`
- `0x1800078b0`
- `0x18000851c`
- `0x180032a30`
- `0x180032af0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800076cf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800076cf`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180007628`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180007628`

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
0x18000758c  push    rbx
0x18000758e  push    rbp
0x18000758f  push    rsi
0x180007590  push    rdi
0x180007591  push    r13
0x180007593  push    r14
0x180007595  push    r15
0x180007597  mov     eax, 2050h
0x18000759c  call    _alloca_probe
0x1800075a1  sub     rsp, rax
0x1800075a4  mov     rax, cs:__security_cookie
0x1800075ab  xor     rax, rsp
0x1800075ae  mov     [rsp+2088h+var_48], rax
0x1800075b6  mov     r15d, r8d
0x1800075b9  mov     [rsp+2088h+pv], 0
0x1800075c2  lea     r8, [rsp+2088h+pv]; unsigned __int16 **
0x1800075c7  mov     rdi, rcx
0x1800075ca  call    ?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z; ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)
0x1800075cf  mov     ebx, eax
0x1800075d1  test    eax, eax
0x1800075d3  js      loc_1800076D7
0x1800075d9  mov     rbp, [rsp+2088h+pv]
0x1800075de  lea     r13, ?map@?1??HKeyFromString@CRegParser@ATL@@KAPEAUHKEY__@@PEAG@Z@4QBUkeymap@?1??123@KAPEAU4@0@Z@B; `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::keymap const near * const `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::map
0x1800075e5  mov     [rdi], rbp
0x1800075e8  mov     rcx, [rdi]
0x1800075eb  xor     eax, eax
0x1800075ed  cmp     ax, [rcx]
0x1800075f0  jz      loc_1800076CC
0x1800075f6  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x1800075fb  mov     rcx, rdi; this
0x1800075fe  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180007603  mov     ebx, eax
0x180007605  test    eax, eax
0x180007607  js      loc_1800076CC
0x18000760d  xor     ebx, ebx
0x18000760f  cmp     ebx, 0Eh
0x180007612  jnb     loc_1800076C7
0x180007618  movsxd  rsi, ebx
0x18000761b  lea     rcx, [rsp+2088h+String1]; lpString1
0x180007620  add     rsi, rsi
0x180007623  mov     rdx, [r13+rsi*8+0]; lpString2
0x180007628  call    cs:__imp_lstrcmpiW
0x18000762e  test    eax, eax
0x180007630  jz      short loc_180007636
0x180007632  inc     ebx
0x180007634  jmp     short loc_18000760F
0x180007636  mov     rsi, [r13+rsi*8+8]
0x18000763b  test    rsi, rsi
0x18000763e  jz      loc_1800076C7
0x180007644  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180007649  mov     rcx, rdi; this
0x18000764c  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180007651  mov     ebx, eax
0x180007653  test    eax, eax
0x180007655  js      short loc_1800076CC
0x180007657  mov     eax, 7Bh ; '{'
0x18000765c  cmp     ax, [rsp+2088h+String1]
0x180007661  jnz     short loc_1800076C7
0x180007663  mov     [rsp+2088h+var_2068], 0; int
0x18000766b  mov     r8, rsi; HKEY
0x18000766e  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180007673  mov     rcx, rdi; this
0x180007676  test    r15d, r15d
0x180007679  jz      short loc_1800076AC
0x18000767b  mov     r14, [rdi]
0x18000767e  mov     r9d, r15d; int
0x180007681  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180007686  mov     ebx, eax
0x180007688  test    eax, eax
0x18000768a  jns     short loc_1800076BA
0x18000768c  xor     r9d, r9d; int
0x18000768f  mov     [rdi], r14
0x180007692  mov     r8, rsi; HKEY
0x180007695  mov     [rsp+2088h+var_2068], 0; int
0x18000769d  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x1800076a2  mov     rcx, rdi; this
0x1800076a5  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x1800076aa  jmp     short loc_1800076CC
0x1800076ac  xor     r9d, r9d; int
0x1800076af  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x1800076b4  mov     ebx, eax
0x1800076b6  test    eax, eax
0x1800076b8  js      short loc_1800076CC
0x1800076ba  mov     rcx, rdi; this
0x1800076bd  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x1800076c2  jmp     loc_1800075E8
0x1800076c7  mov     ebx, 80020009h
0x1800076cc  mov     rcx, rbp; pv
0x1800076cf  call    cs:__imp_CoTaskMemFree
0x1800076d5  mov     eax, ebx
0x1800076d7  mov     rcx, [rsp+2088h+var_48]
0x1800076df  xor     rcx, rsp; StackCookie
0x1800076e2  call    __security_check_cookie
0x1800076e7  add     rsp, 2050h
0x1800076ee  pop     r15
0x1800076f0  pop     r14
0x1800076f2  pop     r13
0x1800076f4  pop     rdi
0x1800076f5  pop     rsi
0x1800076f6  pop     rbp
0x1800076f7  pop     rbx
0x1800076f8  retn
```
