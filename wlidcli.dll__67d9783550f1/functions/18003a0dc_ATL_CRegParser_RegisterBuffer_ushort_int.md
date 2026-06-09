# ATL::CRegParser::RegisterBuffer(ushort *,int)

- ea: `0x18003a0dc`
- end: `0x18003a249`
- name: `?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z`
- size: `365`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x18003a250`

## callees

- `0x180002da0`
- `0x1800397ac`
- `0x180039c54`
- `0x18003a0dc`
- `0x18003a3fc`
- `0x18003abe4`
- `0x18005b890`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a21f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a21f`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18003a178`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18003a178`

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
0x18003a0dc  push    rbx
0x18003a0de  push    rbp
0x18003a0df  push    rsi
0x18003a0e0  push    rdi
0x18003a0e1  push    r13
0x18003a0e3  push    r14
0x18003a0e5  push    r15
0x18003a0e7  mov     eax, 2050h
0x18003a0ec  call    _alloca_probe
0x18003a0f1  sub     rsp, rax
0x18003a0f4  mov     rax, cs:__security_cookie
0x18003a0fb  xor     rax, rsp
0x18003a0fe  mov     [rsp+2088h+var_48], rax
0x18003a106  mov     r15d, r8d
0x18003a109  mov     [rsp+2088h+pv], 0
0x18003a112  lea     r8, [rsp+2088h+pv]; unsigned __int16 **
0x18003a117  mov     rdi, rcx
0x18003a11a  call    ?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z; ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)
0x18003a11f  mov     ebx, eax
0x18003a121  test    eax, eax
0x18003a123  js      loc_18003A227
0x18003a129  mov     rbp, [rsp+2088h+pv]
0x18003a12e  lea     r13, ?map@?1??HKeyFromString@CRegParser@ATL@@KAPEAUHKEY__@@PEAG@Z@4QBUkeymap@?1??123@KAPEAU4@0@Z@B; `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::keymap const near * const `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::map
0x18003a135  mov     [rdi], rbp
0x18003a138  mov     rcx, [rdi]
0x18003a13b  xor     eax, eax
0x18003a13d  cmp     ax, [rcx]
0x18003a140  jz      loc_18003A21C
0x18003a146  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x18003a14b  mov     rcx, rdi; this
0x18003a14e  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18003a153  mov     ebx, eax
0x18003a155  test    eax, eax
0x18003a157  js      loc_18003A21C
0x18003a15d  xor     ebx, ebx
0x18003a15f  cmp     ebx, 0Eh
0x18003a162  jnb     loc_18003A217
0x18003a168  movsxd  rsi, ebx
0x18003a16b  lea     rcx, [rsp+2088h+String1]; lpString1
0x18003a170  add     rsi, rsi
0x18003a173  mov     rdx, [r13+rsi*8+0]; lpString2
0x18003a178  call    cs:__imp_lstrcmpiW
0x18003a17e  test    eax, eax
0x18003a180  jz      short loc_18003A186
0x18003a182  inc     ebx
0x18003a184  jmp     short loc_18003A15F
0x18003a186  mov     rsi, [r13+rsi*8+8]
0x18003a18b  test    rsi, rsi
0x18003a18e  jz      loc_18003A217
0x18003a194  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x18003a199  mov     rcx, rdi; this
0x18003a19c  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18003a1a1  mov     ebx, eax
0x18003a1a3  test    eax, eax
0x18003a1a5  js      short loc_18003A21C
0x18003a1a7  mov     eax, 7Bh ; '{'
0x18003a1ac  cmp     ax, [rsp+2088h+String1]
0x18003a1b1  jnz     short loc_18003A217
0x18003a1b3  mov     [rsp+2088h+var_2068], 0; int
0x18003a1bb  mov     r8, rsi; HKEY
0x18003a1be  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x18003a1c3  mov     rcx, rdi; this
0x18003a1c6  test    r15d, r15d
0x18003a1c9  jz      short loc_18003A1FC
0x18003a1cb  mov     r14, [rdi]
0x18003a1ce  mov     r9d, r15d; int
0x18003a1d1  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x18003a1d6  mov     ebx, eax
0x18003a1d8  test    eax, eax
0x18003a1da  jns     short loc_18003A20A
0x18003a1dc  xor     r9d, r9d; int
0x18003a1df  mov     [rdi], r14
0x18003a1e2  mov     r8, rsi; HKEY
0x18003a1e5  mov     [rsp+2088h+var_2068], 0; int
0x18003a1ed  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x18003a1f2  mov     rcx, rdi; this
0x18003a1f5  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x18003a1fa  jmp     short loc_18003A21C
0x18003a1fc  xor     r9d, r9d; int
0x18003a1ff  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x18003a204  mov     ebx, eax
0x18003a206  test    eax, eax
0x18003a208  js      short loc_18003A21C
0x18003a20a  mov     rcx, rdi; this
0x18003a20d  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x18003a212  jmp     loc_18003A138
0x18003a217  mov     ebx, 80020009h
0x18003a21c  mov     rcx, rbp; pv
0x18003a21f  call    cs:__imp_CoTaskMemFree
0x18003a225  mov     eax, ebx
0x18003a227  mov     rcx, [rsp+2088h+var_48]
0x18003a22f  xor     rcx, rsp; StackCookie
0x18003a232  call    __security_check_cookie
0x18003a237  add     rsp, 2050h
0x18003a23e  pop     r15
0x18003a240  pop     r14
0x18003a242  pop     r13
0x18003a244  pop     rdi
0x18003a245  pop     rsi
0x18003a246  pop     rbp
0x18003a247  pop     rbx
0x18003a248  retn
```
