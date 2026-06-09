# ATL::CRegParser::RegisterBuffer(ushort *,int)

- ea: `0x18002a25c`
- end: `0x18002a3c9`
- name: `?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z`
- size: `365`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x18002a3d0`

## callees

- `0x180029ac0`
- `0x180029c78`
- `0x18002a25c`
- `0x18002a62c`
- `0x18002c1a4`
- `0x180055030`
- `0x1800550f0`

## import_xrefs

- `KERNEL32!lstrcmpiW` at `0x18002a2f8`
- `KERNEL32!lstrcmpiW` at `0x18002a2f8`
- `ole32!CoTaskMemFree` at `0x18002a39f`
- `ole32!CoTaskMemFree` at `0x18002a39f`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::RegisterBuffer(LPCWSTR *this, unsigned __int16 *a2, int a3)
{
  __int64 result; // rax
  int Token; // ebx
  void *v7; // rbp
  unsigned int i; // ebx
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
0x18002a25c  push    rbx
0x18002a25e  push    rbp
0x18002a25f  push    rsi
0x18002a260  push    rdi
0x18002a261  push    r13
0x18002a263  push    r14
0x18002a265  push    r15
0x18002a267  mov     eax, 2050h
0x18002a26c  call    _alloca_probe
0x18002a271  sub     rsp, rax
0x18002a274  mov     rax, cs:__security_cookie
0x18002a27b  xor     rax, rsp
0x18002a27e  mov     [rsp+2088h+var_48], rax
0x18002a286  mov     r15d, r8d
0x18002a289  mov     [rsp+2088h+pv], 0
0x18002a292  lea     r8, [rsp+2088h+pv]; unsigned __int16 **
0x18002a297  mov     rdi, rcx
0x18002a29a  call    ?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z; ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)
0x18002a29f  mov     ebx, eax
0x18002a2a1  test    eax, eax
0x18002a2a3  js      loc_18002A3A7
0x18002a2a9  mov     rbp, [rsp+2088h+pv]
0x18002a2ae  lea     r13, ?map@?1??HKeyFromString@CRegParser@ATL@@KAPEAUHKEY__@@PEAG@Z@4QBUkeymap@?1??123@KAPEAU4@0@Z@B; `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::keymap const near * const `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::map
0x18002a2b5  mov     [rdi], rbp
0x18002a2b8  mov     rcx, [rdi]
0x18002a2bb  xor     eax, eax
0x18002a2bd  cmp     ax, [rcx]
0x18002a2c0  jz      loc_18002A39C
0x18002a2c6  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x18002a2cb  mov     rcx, rdi; this
0x18002a2ce  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18002a2d3  mov     ebx, eax
0x18002a2d5  test    eax, eax
0x18002a2d7  js      loc_18002A39C
0x18002a2dd  xor     ebx, ebx
0x18002a2df  cmp     ebx, 0Eh
0x18002a2e2  jnb     loc_18002A397
0x18002a2e8  movsxd  rsi, ebx
0x18002a2eb  lea     rcx, [rsp+2088h+String1]; lpString1
0x18002a2f0  add     rsi, rsi
0x18002a2f3  mov     rdx, [r13+rsi*8+0]; lpString2
0x18002a2f8  call    cs:__imp_lstrcmpiW
0x18002a2fe  test    eax, eax
0x18002a300  jz      short loc_18002A306
0x18002a302  inc     ebx
0x18002a304  jmp     short loc_18002A2DF
0x18002a306  mov     rsi, [r13+rsi*8+8]
0x18002a30b  test    rsi, rsi
0x18002a30e  jz      loc_18002A397
0x18002a314  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x18002a319  mov     rcx, rdi; this
0x18002a31c  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18002a321  mov     ebx, eax
0x18002a323  test    eax, eax
0x18002a325  js      short loc_18002A39C
0x18002a327  mov     eax, 7Bh ; '{'
0x18002a32c  cmp     ax, [rsp+2088h+String1]
0x18002a331  jnz     short loc_18002A397
0x18002a333  mov     [rsp+2088h+var_2068], 0; int
0x18002a33b  mov     r8, rsi; HKEY
0x18002a33e  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x18002a343  mov     rcx, rdi; this
0x18002a346  test    r15d, r15d
0x18002a349  jz      short loc_18002A37C
0x18002a34b  mov     r14, [rdi]
0x18002a34e  mov     r9d, r15d; int
0x18002a351  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x18002a356  mov     ebx, eax
0x18002a358  test    eax, eax
0x18002a35a  jns     short loc_18002A38A
0x18002a35c  xor     r9d, r9d; int
0x18002a35f  mov     [rdi], r14
0x18002a362  mov     r8, rsi; HKEY
0x18002a365  mov     [rsp+2088h+var_2068], 0; int
0x18002a36d  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x18002a372  mov     rcx, rdi; this
0x18002a375  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x18002a37a  jmp     short loc_18002A39C
0x18002a37c  xor     r9d, r9d; int
0x18002a37f  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x18002a384  mov     ebx, eax
0x18002a386  test    eax, eax
0x18002a388  js      short loc_18002A39C
0x18002a38a  mov     rcx, rdi; this
0x18002a38d  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x18002a392  jmp     loc_18002A2B8
0x18002a397  mov     ebx, 80020009h
0x18002a39c  mov     rcx, rbp; pv
0x18002a39f  call    cs:__imp_CoTaskMemFree
0x18002a3a5  mov     eax, ebx
0x18002a3a7  mov     rcx, [rsp+2088h+var_48]
0x18002a3af  xor     rcx, rsp; StackCookie
0x18002a3b2  call    __security_check_cookie
0x18002a3b7  add     rsp, 2050h
0x18002a3be  pop     r15
0x18002a3c0  pop     r14
0x18002a3c2  pop     r13
0x18002a3c4  pop     rdi
0x18002a3c5  pop     rsi
0x18002a3c6  pop     rbp
0x18002a3c7  pop     rbx
0x18002a3c8  retn
```
