# ATL::CRegParser::RegisterBuffer(ushort *,int)

- ea: `0x18000bcbc`
- end: `0x18000be46`
- name: `?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z`
- size: `394`
- prototype: `__int64 __fastcall(LPCWSTR *this, unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000bfbc`

## callees

- `0x18000b130`
- `0x18000b2d0`
- `0x18000bcbc`
- `0x18000c254`
- `0x180021740`
- `0x1800217d0`

## import_xrefs

- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000be2b`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000be2b`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000bd41`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000bd41`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000bd5a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000bd5a`

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
0x18000bcbc  push    rbx
0x18000bcbe  push    rbp
0x18000bcbf  push    rsi
0x18000bcc0  push    rdi
0x18000bcc1  push    r13
0x18000bcc3  push    r14
0x18000bcc5  push    r15
0x18000bcc7  mov     eax, 2050h
0x18000bccc  call    _alloca_probe
0x18000bcd1  sub     rsp, rax
0x18000bcd4  mov     rax, cs:__security_cookie
0x18000bcdb  xor     rax, rsp
0x18000bcde  mov     [rsp+2088h+var_48], rax
0x18000bce6  mov     r15d, r8d
0x18000bce9  mov     [rsp+2088h+pv], 0
0x18000bcf2  lea     r8, [rsp+2088h+pv]; unsigned __int16 **
0x18000bcf7  mov     rdi, rcx
0x18000bcfa  call    ?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z; ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)
0x18000bcff  mov     ebx, eax
0x18000bd01  test    eax, eax
0x18000bd03  js      short loc_18000BD62
0x18000bd05  mov     rbp, [rsp+2088h+pv]
0x18000bd0a  xor     eax, eax
0x18000bd0c  mov     [rdi], rbp
0x18000bd0f  cmp     ax, [rbp+0]
0x18000bd13  jz      short loc_18000BD57
0x18000bd15  lea     r13, ?map@?1??HKeyFromString@CRegParser@ATL@@KAPEAUHKEY__@@PEAG@Z@4QBUkeymap@?1??123@KAPEAU4@0@Z@B; `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::keymap const near * const `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::map
0x18000bd1c  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x18000bd21  mov     rcx, rdi; this
0x18000bd24  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000bd29  mov     ebx, eax
0x18000bd2b  test    eax, eax
0x18000bd2d  js      short loc_18000BD57
0x18000bd2f  xor     ebx, ebx
0x18000bd31  movsxd  rsi, ebx
0x18000bd34  lea     rcx, [rsp+2088h+String1]; lpString1
0x18000bd39  add     rsi, rsi
0x18000bd3c  mov     rdx, [r13+rsi*8+0]; lpString2
0x18000bd41  call    cs:__imp_lstrcmpiW
0x18000bd47  test    eax, eax
0x18000bd49  jz      short loc_18000BD84
0x18000bd4b  inc     ebx
0x18000bd4d  cmp     ebx, 0Eh
0x18000bd50  jb      short loc_18000BD31
0x18000bd52  mov     ebx, 80020009h
0x18000bd57  mov     rcx, rbp; pv
0x18000bd5a  call    cs:__imp_CoTaskMemFree
0x18000bd60  mov     eax, ebx
0x18000bd62  mov     rcx, [rsp+2088h+var_48]
0x18000bd6a  xor     rcx, rsp; StackCookie
0x18000bd6d  call    __security_check_cookie
0x18000bd72  add     rsp, 2050h
0x18000bd79  pop     r15
0x18000bd7b  pop     r14
0x18000bd7d  pop     r13
0x18000bd7f  pop     rdi
0x18000bd80  pop     rsi
0x18000bd81  pop     rbp
0x18000bd82  pop     rbx
0x18000bd83  retn
0x18000bd84  mov     rsi, [r13+rsi*8+8]
0x18000bd89  test    rsi, rsi
0x18000bd8c  jz      short loc_18000BD52
0x18000bd8e  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x18000bd93  mov     rcx, rdi; this
0x18000bd96  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000bd9b  mov     ebx, eax
0x18000bd9d  test    eax, eax
0x18000bd9f  js      short loc_18000BD57
0x18000bda1  mov     eax, 7Bh ; '{'
0x18000bda6  cmp     ax, [rsp+2088h+String1]
0x18000bdab  jnz     short loc_18000BD52
0x18000bdad  mov     [rsp+2088h+var_2068], 0; int
0x18000bdb5  mov     r8, rsi; HKEY
0x18000bdb8  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x18000bdbd  mov     rcx, rdi; this
0x18000bdc0  test    r15d, r15d
0x18000bdc3  jz      short loc_18000BDF9
0x18000bdc5  mov     r14, [rdi]
0x18000bdc8  mov     r9d, r15d; int
0x18000bdcb  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x18000bdd0  mov     ebx, eax
0x18000bdd2  test    eax, eax
0x18000bdd4  jns     short loc_18000BE0B
0x18000bdd6  xor     r9d, r9d; int
0x18000bdd9  mov     [rdi], r14
0x18000bddc  mov     r8, rsi; HKEY
0x18000bddf  mov     [rsp+2088h+var_2068], 0; int
0x18000bde7  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x18000bdec  mov     rcx, rdi; this
0x18000bdef  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x18000bdf4  jmp     loc_18000BD57
0x18000bdf9  xor     r9d, r9d; int
0x18000bdfc  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x18000be01  mov     ebx, eax
0x18000be03  test    eax, eax
0x18000be05  js      loc_18000BD57
0x18000be0b  mov     r8, [rdi]
0x18000be0e  movzx   edx, word ptr [r8]
0x18000be12  mov     ecx, edx
0x18000be14  sub     ecx, 9
0x18000be17  jz      short loc_18000BE28
0x18000be19  sub     ecx, 1
0x18000be1c  jz      short loc_18000BE28
0x18000be1e  sub     ecx, 3
0x18000be21  jz      short loc_18000BE28
0x18000be23  cmp     ecx, 13h
0x18000be26  jnz     short loc_18000BE36
0x18000be28  mov     rcx, r8; lpsz
0x18000be2b  call    cs:__imp_CharNextW
0x18000be31  mov     [rdi], rax
0x18000be34  jmp     short loc_18000BE0B
0x18000be36  xor     eax, eax
0x18000be38  cmp     ax, dx
0x18000be3b  jnz     loc_18000BD1C
0x18000be41  jmp     loc_18000BD57
```
