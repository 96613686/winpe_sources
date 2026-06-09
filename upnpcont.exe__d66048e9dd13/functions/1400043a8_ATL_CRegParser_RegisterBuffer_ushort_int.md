# ATL::CRegParser::RegisterBuffer(ushort *,int)

- ea: `0x1400043a8`
- end: `0x140004532`
- name: `?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z`
- size: `394`
- prototype: `__int64 __fastcall(LPCWSTR *this, unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x140004698`

## callees

- `0x140001490`
- `0x140003d78`
- `0x140003f2c`
- `0x1400043a8`
- `0x140004954`
- `0x140006640`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140004446`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140004446`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x140004517`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x140004517`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x14000442d`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x14000442d`

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
0x1400043a8  push    rbx
0x1400043aa  push    rbp
0x1400043ab  push    rsi
0x1400043ac  push    rdi
0x1400043ad  push    r13
0x1400043af  push    r14
0x1400043b1  push    r15
0x1400043b3  mov     eax, 2050h
0x1400043b8  call    _alloca_probe
0x1400043bd  sub     rsp, rax
0x1400043c0  mov     rax, cs:__security_cookie
0x1400043c7  xor     rax, rsp
0x1400043ca  mov     [rsp+2088h+var_48], rax
0x1400043d2  mov     r15d, r8d
0x1400043d5  mov     [rsp+2088h+pv], 0
0x1400043de  lea     r8, [rsp+2088h+pv]; unsigned __int16 **
0x1400043e3  mov     rdi, rcx
0x1400043e6  call    ?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z; ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)
0x1400043eb  mov     ebx, eax
0x1400043ed  test    eax, eax
0x1400043ef  js      short loc_14000444E
0x1400043f1  mov     rbp, [rsp+2088h+pv]
0x1400043f6  xor     eax, eax
0x1400043f8  mov     [rdi], rbp
0x1400043fb  cmp     ax, [rbp+0]
0x1400043ff  jz      short loc_140004443
0x140004401  lea     r13, ?map@?1??HKeyFromString@CRegParser@ATL@@KAPEAUHKEY__@@PEAG@Z@4QBUkeymap@?1??123@KAPEAU4@0@Z@B; `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::keymap const near * const `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::map
0x140004408  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x14000440d  mov     rcx, rdi; this
0x140004410  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x140004415  mov     ebx, eax
0x140004417  test    eax, eax
0x140004419  js      short loc_140004443
0x14000441b  xor     ebx, ebx
0x14000441d  movsxd  rsi, ebx
0x140004420  lea     rcx, [rsp+2088h+String1]; lpString1
0x140004425  add     rsi, rsi
0x140004428  mov     rdx, [r13+rsi*8+0]; lpString2
0x14000442d  call    cs:__imp_lstrcmpiW
0x140004433  test    eax, eax
0x140004435  jz      short loc_140004470
0x140004437  inc     ebx
0x140004439  cmp     ebx, 0Eh
0x14000443c  jb      short loc_14000441D
0x14000443e  mov     ebx, 80020009h
0x140004443  mov     rcx, rbp; pv
0x140004446  call    cs:__imp_CoTaskMemFree
0x14000444c  mov     eax, ebx
0x14000444e  mov     rcx, [rsp+2088h+var_48]
0x140004456  xor     rcx, rsp; StackCookie
0x140004459  call    __security_check_cookie
0x14000445e  add     rsp, 2050h
0x140004465  pop     r15
0x140004467  pop     r14
0x140004469  pop     r13
0x14000446b  pop     rdi
0x14000446c  pop     rsi
0x14000446d  pop     rbp
0x14000446e  pop     rbx
0x14000446f  retn
0x140004470  mov     rsi, [r13+rsi*8+8]
0x140004475  test    rsi, rsi
0x140004478  jz      short loc_14000443E
0x14000447a  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x14000447f  mov     rcx, rdi; this
0x140004482  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x140004487  mov     ebx, eax
0x140004489  test    eax, eax
0x14000448b  js      short loc_140004443
0x14000448d  mov     eax, 7Bh ; '{'
0x140004492  cmp     ax, [rsp+2088h+String1]
0x140004497  jnz     short loc_14000443E
0x140004499  mov     [rsp+2088h+var_2068], 0; int
0x1400044a1  mov     r8, rsi; HKEY
0x1400044a4  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x1400044a9  mov     rcx, rdi; this
0x1400044ac  test    r15d, r15d
0x1400044af  jz      short loc_1400044E5
0x1400044b1  mov     r14, [rdi]
0x1400044b4  mov     r9d, r15d; int
0x1400044b7  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x1400044bc  mov     ebx, eax
0x1400044be  test    eax, eax
0x1400044c0  jns     short loc_1400044F7
0x1400044c2  xor     r9d, r9d; int
0x1400044c5  mov     [rdi], r14
0x1400044c8  mov     r8, rsi; HKEY
0x1400044cb  mov     [rsp+2088h+var_2068], 0; int
0x1400044d3  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x1400044d8  mov     rcx, rdi; this
0x1400044db  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x1400044e0  jmp     loc_140004443
0x1400044e5  xor     r9d, r9d; int
0x1400044e8  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x1400044ed  mov     ebx, eax
0x1400044ef  test    eax, eax
0x1400044f1  js      loc_140004443
0x1400044f7  mov     r8, [rdi]
0x1400044fa  movzx   edx, word ptr [r8]
0x1400044fe  mov     ecx, edx
0x140004500  sub     ecx, 9
0x140004503  jz      short loc_140004514
0x140004505  sub     ecx, 1
0x140004508  jz      short loc_140004514
0x14000450a  sub     ecx, 3
0x14000450d  jz      short loc_140004514
0x14000450f  cmp     ecx, 13h
0x140004512  jnz     short loc_140004522
0x140004514  mov     rcx, r8; lpsz
0x140004517  call    cs:__imp_CharNextW
0x14000451d  mov     [rdi], rax
0x140004520  jmp     short loc_1400044F7
0x140004522  xor     eax, eax
0x140004524  cmp     ax, dx
0x140004527  jnz     loc_140004408
0x14000452d  jmp     loc_140004443
```
