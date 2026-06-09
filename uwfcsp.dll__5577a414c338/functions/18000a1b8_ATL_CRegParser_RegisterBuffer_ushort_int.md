# ATL::CRegParser::RegisterBuffer(ushort *,int)

- ea: `0x18000a1b8`
- end: `0x18000a342`
- name: `?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z`
- size: `394`
- prototype: `__int64 __fastcall(LPCWSTR *this, unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000a348`

## callees

- `0x1800096e4`
- `0x180009c8c`
- `0x18000a1b8`
- `0x18000a50c`
- `0x18001a210`
- `0x18001a2d0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a256`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a256`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000a327`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000a327`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000a23d`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000a23d`

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
0x18000a1b8  push    rbx
0x18000a1ba  push    rbp
0x18000a1bb  push    rsi
0x18000a1bc  push    rdi
0x18000a1bd  push    r13
0x18000a1bf  push    r14
0x18000a1c1  push    r15
0x18000a1c3  mov     eax, 2050h
0x18000a1c8  call    _alloca_probe
0x18000a1cd  sub     rsp, rax
0x18000a1d0  mov     rax, cs:__security_cookie
0x18000a1d7  xor     rax, rsp
0x18000a1da  mov     [rsp+2088h+var_48], rax
0x18000a1e2  mov     r15d, r8d
0x18000a1e5  mov     [rsp+2088h+pv], 0
0x18000a1ee  lea     r8, [rsp+2088h+pv]; unsigned __int16 **
0x18000a1f3  mov     rdi, rcx
0x18000a1f6  call    ?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z; ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)
0x18000a1fb  mov     ebx, eax
0x18000a1fd  test    eax, eax
0x18000a1ff  js      short loc_18000A25E
0x18000a201  mov     rbp, [rsp+2088h+pv]
0x18000a206  xor     eax, eax
0x18000a208  mov     [rdi], rbp
0x18000a20b  cmp     ax, [rbp+0]
0x18000a20f  jz      short loc_18000A253
0x18000a211  lea     r13, ?map@?1??HKeyFromString@CRegParser@ATL@@KAPEAUHKEY__@@PEAG@Z@4QBUkeymap@?1??123@KAPEAU4@0@Z@B; `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::keymap const near * const `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::map
0x18000a218  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x18000a21d  mov     rcx, rdi; this
0x18000a220  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000a225  mov     ebx, eax
0x18000a227  test    eax, eax
0x18000a229  js      short loc_18000A253
0x18000a22b  xor     ebx, ebx
0x18000a22d  movsxd  rsi, ebx
0x18000a230  lea     rcx, [rsp+2088h+String1]; lpString1
0x18000a235  add     rsi, rsi
0x18000a238  mov     rdx, [r13+rsi*8+0]; lpString2
0x18000a23d  call    cs:__imp_lstrcmpiW
0x18000a243  test    eax, eax
0x18000a245  jz      short loc_18000A280
0x18000a247  inc     ebx
0x18000a249  cmp     ebx, 0Eh
0x18000a24c  jb      short loc_18000A22D
0x18000a24e  mov     ebx, 80020009h
0x18000a253  mov     rcx, rbp; pv
0x18000a256  call    cs:__imp_CoTaskMemFree
0x18000a25c  mov     eax, ebx
0x18000a25e  mov     rcx, [rsp+2088h+var_48]
0x18000a266  xor     rcx, rsp; StackCookie
0x18000a269  call    __security_check_cookie
0x18000a26e  add     rsp, 2050h
0x18000a275  pop     r15
0x18000a277  pop     r14
0x18000a279  pop     r13
0x18000a27b  pop     rdi
0x18000a27c  pop     rsi
0x18000a27d  pop     rbp
0x18000a27e  pop     rbx
0x18000a27f  retn
0x18000a280  mov     rsi, [r13+rsi*8+8]
0x18000a285  test    rsi, rsi
0x18000a288  jz      short loc_18000A24E
0x18000a28a  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x18000a28f  mov     rcx, rdi; this
0x18000a292  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000a297  mov     ebx, eax
0x18000a299  test    eax, eax
0x18000a29b  js      short loc_18000A253
0x18000a29d  mov     eax, 7Bh ; '{'
0x18000a2a2  cmp     ax, [rsp+2088h+String1]
0x18000a2a7  jnz     short loc_18000A24E
0x18000a2a9  mov     [rsp+2088h+var_2068], 0; int
0x18000a2b1  mov     r8, rsi; HKEY
0x18000a2b4  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x18000a2b9  mov     rcx, rdi; this
0x18000a2bc  test    r15d, r15d
0x18000a2bf  jz      short loc_18000A2F5
0x18000a2c1  mov     r14, [rdi]
0x18000a2c4  mov     r9d, r15d; int
0x18000a2c7  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x18000a2cc  mov     ebx, eax
0x18000a2ce  test    eax, eax
0x18000a2d0  jns     short loc_18000A307
0x18000a2d2  xor     r9d, r9d; int
0x18000a2d5  mov     [rdi], r14
0x18000a2d8  mov     r8, rsi; HKEY
0x18000a2db  mov     [rsp+2088h+var_2068], 0; int
0x18000a2e3  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x18000a2e8  mov     rcx, rdi; this
0x18000a2eb  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x18000a2f0  jmp     loc_18000A253
0x18000a2f5  xor     r9d, r9d; int
0x18000a2f8  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x18000a2fd  mov     ebx, eax
0x18000a2ff  test    eax, eax
0x18000a301  js      loc_18000A253
0x18000a307  mov     r8, [rdi]
0x18000a30a  movzx   edx, word ptr [r8]
0x18000a30e  mov     ecx, edx
0x18000a310  sub     ecx, 9
0x18000a313  jz      short loc_18000A324
0x18000a315  sub     ecx, 1
0x18000a318  jz      short loc_18000A324
0x18000a31a  sub     ecx, 3
0x18000a31d  jz      short loc_18000A324
0x18000a31f  cmp     ecx, 13h
0x18000a322  jnz     short loc_18000A332
0x18000a324  mov     rcx, r8; lpsz
0x18000a327  call    cs:__imp_CharNextW
0x18000a32d  mov     [rdi], rax
0x18000a330  jmp     short loc_18000A307
0x18000a332  xor     eax, eax
0x18000a334  cmp     ax, dx
0x18000a337  jnz     loc_18000A218
0x18000a33d  jmp     loc_18000A253
```
