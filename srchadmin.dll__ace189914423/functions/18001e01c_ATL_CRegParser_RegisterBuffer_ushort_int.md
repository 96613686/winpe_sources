# ATL::CRegParser::RegisterBuffer(ushort *,int)

- ea: `0x18001e01c`
- end: `0x18001e189`
- name: `?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z`
- size: `365`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001e190`

## callees

- `0x180005cc0`
- `0x18001d3b0`
- `0x18001d958`
- `0x18001e01c`
- `0x18001e340`
- `0x18001ef88`
- `0x180030350`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e15f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e15f`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18001e0b8`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18001e0b8`

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
0x18001e01c  push    rbx
0x18001e01e  push    rbp
0x18001e01f  push    rsi
0x18001e020  push    rdi
0x18001e021  push    r13
0x18001e023  push    r14
0x18001e025  push    r15
0x18001e027  mov     eax, 2050h
0x18001e02c  call    _alloca_probe
0x18001e031  sub     rsp, rax
0x18001e034  mov     rax, cs:__security_cookie
0x18001e03b  xor     rax, rsp
0x18001e03e  mov     [rsp+2088h+var_48], rax
0x18001e046  mov     r15d, r8d
0x18001e049  mov     [rsp+2088h+pv], 0
0x18001e052  lea     r8, [rsp+2088h+pv]; unsigned __int16 **
0x18001e057  mov     rdi, rcx
0x18001e05a  call    ?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z; ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)
0x18001e05f  mov     ebx, eax
0x18001e061  test    eax, eax
0x18001e063  js      loc_18001E167
0x18001e069  mov     rbp, [rsp+2088h+pv]
0x18001e06e  lea     r13, ?map@?1??HKeyFromString@CRegParser@ATL@@KAPEAUHKEY__@@PEAG@Z@4QBUkeymap@?1??123@KAPEAU4@0@Z@B; `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::keymap const near * const `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::map
0x18001e075  mov     [rdi], rbp
0x18001e078  mov     rcx, [rdi]
0x18001e07b  xor     eax, eax
0x18001e07d  cmp     ax, [rcx]
0x18001e080  jz      loc_18001E15C
0x18001e086  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x18001e08b  mov     rcx, rdi; this
0x18001e08e  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18001e093  mov     ebx, eax
0x18001e095  test    eax, eax
0x18001e097  js      loc_18001E15C
0x18001e09d  xor     ebx, ebx
0x18001e09f  cmp     ebx, 0Eh
0x18001e0a2  jnb     loc_18001E157
0x18001e0a8  movsxd  rsi, ebx
0x18001e0ab  lea     rcx, [rsp+2088h+String1]; lpString1
0x18001e0b0  add     rsi, rsi
0x18001e0b3  mov     rdx, [r13+rsi*8+0]; lpString2
0x18001e0b8  call    cs:__imp_lstrcmpiW
0x18001e0be  test    eax, eax
0x18001e0c0  jz      short loc_18001E0C6
0x18001e0c2  inc     ebx
0x18001e0c4  jmp     short loc_18001E09F
0x18001e0c6  mov     rsi, [r13+rsi*8+8]
0x18001e0cb  test    rsi, rsi
0x18001e0ce  jz      loc_18001E157
0x18001e0d4  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x18001e0d9  mov     rcx, rdi; this
0x18001e0dc  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18001e0e1  mov     ebx, eax
0x18001e0e3  test    eax, eax
0x18001e0e5  js      short loc_18001E15C
0x18001e0e7  mov     eax, 7Bh ; '{'
0x18001e0ec  cmp     ax, [rsp+2088h+String1]
0x18001e0f1  jnz     short loc_18001E157
0x18001e0f3  mov     [rsp+2088h+var_2068], 0; int
0x18001e0fb  mov     r8, rsi; HKEY
0x18001e0fe  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x18001e103  mov     rcx, rdi; this
0x18001e106  test    r15d, r15d
0x18001e109  jz      short loc_18001E13C
0x18001e10b  mov     r14, [rdi]
0x18001e10e  mov     r9d, r15d; int
0x18001e111  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x18001e116  mov     ebx, eax
0x18001e118  test    eax, eax
0x18001e11a  jns     short loc_18001E14A
0x18001e11c  xor     r9d, r9d; int
0x18001e11f  mov     [rdi], r14
0x18001e122  mov     r8, rsi; HKEY
0x18001e125  mov     [rsp+2088h+var_2068], 0; int
0x18001e12d  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x18001e132  mov     rcx, rdi; this
0x18001e135  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x18001e13a  jmp     short loc_18001E15C
0x18001e13c  xor     r9d, r9d; int
0x18001e13f  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x18001e144  mov     ebx, eax
0x18001e146  test    eax, eax
0x18001e148  js      short loc_18001E15C
0x18001e14a  mov     rcx, rdi; this
0x18001e14d  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x18001e152  jmp     loc_18001E078
0x18001e157  mov     ebx, 80020009h
0x18001e15c  mov     rcx, rbp; pv
0x18001e15f  call    cs:__imp_CoTaskMemFree
0x18001e165  mov     eax, ebx
0x18001e167  mov     rcx, [rsp+2088h+var_48]
0x18001e16f  xor     rcx, rsp; StackCookie
0x18001e172  call    __security_check_cookie
0x18001e177  add     rsp, 2050h
0x18001e17e  pop     r15
0x18001e180  pop     r14
0x18001e182  pop     r13
0x18001e184  pop     rdi
0x18001e185  pop     rsi
0x18001e186  pop     rbp
0x18001e187  pop     rbx
0x18001e188  retn
```
