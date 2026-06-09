# ATL::CRegParser::RegisterBuffer(ushort *,int)

- ea: `0x18001aa9c`
- end: `0x18001ac09`
- name: `?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z`
- size: `365`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001ac10`

## callees

- `0x1800034b0`
- `0x180019d40`
- `0x180019f20`
- `0x18001aa9c`
- `0x18001ae58`
- `0x18001b950`
- `0x1800ff490`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001abdf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001abdf`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18001ab38`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18001ab38`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::RegisterBuffer(ATL::CRegParser *this, unsigned __int16 *a2, int a3)
{
  __int64 result; // rax
  int Token; // ebx
  void *v7; // rbp
  unsigned int i; // ebx
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
    while ( **(_WORD **)this )
    {
      Token = ATL::CRegParser::NextToken(this, String1);
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
      Token = ATL::CRegParser::NextToken(this, String1);
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
    CoTaskMemFree(v7);
    return (unsigned int)Token;
  }
  return result;
}

```

## disassembly

```asm
0x18001aa9c  push    rbx
0x18001aa9e  push    rbp
0x18001aa9f  push    rsi
0x18001aaa0  push    rdi
0x18001aaa1  push    r13
0x18001aaa3  push    r14
0x18001aaa5  push    r15
0x18001aaa7  mov     eax, 2050h
0x18001aaac  call    _alloca_probe
0x18001aab1  sub     rsp, rax
0x18001aab4  mov     rax, cs:__security_cookie
0x18001aabb  xor     rax, rsp
0x18001aabe  mov     [rsp+2088h+var_48], rax
0x18001aac6  mov     r15d, r8d
0x18001aac9  mov     [rsp+2088h+pv], 0
0x18001aad2  lea     r8, [rsp+2088h+pv]; unsigned __int16 **
0x18001aad7  mov     rdi, rcx
0x18001aada  call    ?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z; ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)
0x18001aadf  mov     ebx, eax
0x18001aae1  test    eax, eax
0x18001aae3  js      loc_18001ABE7
0x18001aae9  mov     rbp, [rsp+2088h+pv]
0x18001aaee  lea     r13, ?map@?1??HKeyFromString@CRegParser@ATL@@KAPEAUHKEY__@@PEAG@Z@4QBUkeymap@?1??123@KAPEAU4@0@Z@B; `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::keymap const near * const `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::map
0x18001aaf5  mov     [rdi], rbp
0x18001aaf8  mov     rcx, [rdi]
0x18001aafb  xor     eax, eax
0x18001aafd  cmp     ax, [rcx]
0x18001ab00  jz      loc_18001ABDC
0x18001ab06  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x18001ab0b  mov     rcx, rdi; this
0x18001ab0e  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18001ab13  mov     ebx, eax
0x18001ab15  test    eax, eax
0x18001ab17  js      loc_18001ABDC
0x18001ab1d  xor     ebx, ebx
0x18001ab1f  cmp     ebx, 0Eh
0x18001ab22  jnb     loc_18001ABD7
0x18001ab28  movsxd  rsi, ebx
0x18001ab2b  lea     rcx, [rsp+2088h+String1]; lpString1
0x18001ab30  add     rsi, rsi
0x18001ab33  mov     rdx, [r13+rsi*8+0]; lpString2
0x18001ab38  call    cs:__imp_lstrcmpiW
0x18001ab3e  test    eax, eax
0x18001ab40  jz      short loc_18001AB46
0x18001ab42  inc     ebx
0x18001ab44  jmp     short loc_18001AB1F
0x18001ab46  mov     rsi, [r13+rsi*8+8]
0x18001ab4b  test    rsi, rsi
0x18001ab4e  jz      loc_18001ABD7
0x18001ab54  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x18001ab59  mov     rcx, rdi; this
0x18001ab5c  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18001ab61  mov     ebx, eax
0x18001ab63  test    eax, eax
0x18001ab65  js      short loc_18001ABDC
0x18001ab67  mov     eax, 7Bh ; '{'
0x18001ab6c  cmp     ax, [rsp+2088h+String1]
0x18001ab71  jnz     short loc_18001ABD7
0x18001ab73  mov     [rsp+2088h+var_2068], 0; int
0x18001ab7b  mov     r8, rsi; HKEY
0x18001ab7e  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x18001ab83  mov     rcx, rdi; this
0x18001ab86  test    r15d, r15d
0x18001ab89  jz      short loc_18001ABBC
0x18001ab8b  mov     r14, [rdi]
0x18001ab8e  mov     r9d, r15d; int
0x18001ab91  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x18001ab96  mov     ebx, eax
0x18001ab98  test    eax, eax
0x18001ab9a  jns     short loc_18001ABCA
0x18001ab9c  xor     r9d, r9d; int
0x18001ab9f  mov     [rdi], r14
0x18001aba2  mov     r8, rsi; HKEY
0x18001aba5  mov     [rsp+2088h+var_2068], 0; int
0x18001abad  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x18001abb2  mov     rcx, rdi; this
0x18001abb5  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x18001abba  jmp     short loc_18001ABDC
0x18001abbc  xor     r9d, r9d; int
0x18001abbf  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x18001abc4  mov     ebx, eax
0x18001abc6  test    eax, eax
0x18001abc8  js      short loc_18001ABDC
0x18001abca  mov     rcx, rdi; this
0x18001abcd  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x18001abd2  jmp     loc_18001AAF8
0x18001abd7  mov     ebx, 80020009h
0x18001abdc  mov     rcx, rbp; pv
0x18001abdf  call    cs:__imp_CoTaskMemFree
0x18001abe5  mov     eax, ebx
0x18001abe7  mov     rcx, [rsp+2088h+var_48]
0x18001abef  xor     rcx, rsp; StackCookie
0x18001abf2  call    __security_check_cookie
0x18001abf7  add     rsp, 2050h
0x18001abfe  pop     r15
0x18001ac00  pop     r14
0x18001ac02  pop     r13
0x18001ac04  pop     rdi
0x18001ac05  pop     rsi
0x18001ac06  pop     rbp
0x18001ac07  pop     rbx
0x18001ac08  retn
```
