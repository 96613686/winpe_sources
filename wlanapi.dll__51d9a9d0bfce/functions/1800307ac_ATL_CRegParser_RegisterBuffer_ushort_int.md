# ATL::CRegParser::RegisterBuffer(ushort *,int)

- ea: `0x1800307ac`
- end: `0x180030916`
- name: `?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z`
- size: `362`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x18003091c`

## callees

- `0x180019a20`
- `0x180030264`
- `0x180030434`
- `0x1800307ac`
- `0x180030acc`
- `0x180031288`
- `0x1800600d0`

## import_xrefs

- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180030831`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180030831`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003084a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003084a`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::RegisterBuffer(ATL::CRegParser *this, unsigned __int16 *a2, int a3)
{
  __int64 result; // rax
  int Token; // ebx
  _WORD *v7; // rbp
  int v8; // ebx
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
      while ( **(_WORD **)this );
    }
    CoTaskMemFree(v7);
    return (unsigned int)Token;
  }
  return result;
}

```

## disassembly

```asm
0x1800307ac  push    rbx
0x1800307ae  push    rbp
0x1800307af  push    rsi
0x1800307b0  push    rdi
0x1800307b1  push    r13
0x1800307b3  push    r14
0x1800307b5  push    r15
0x1800307b7  mov     eax, 2050h
0x1800307bc  call    _alloca_probe
0x1800307c1  sub     rsp, rax
0x1800307c4  mov     rax, cs:__security_cookie
0x1800307cb  xor     rax, rsp
0x1800307ce  mov     [rsp+2088h+var_48], rax
0x1800307d6  mov     r15d, r8d
0x1800307d9  mov     [rsp+2088h+pv], 0
0x1800307e2  lea     r8, [rsp+2088h+pv]; unsigned __int16 **
0x1800307e7  mov     rdi, rcx
0x1800307ea  call    ?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z; ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)
0x1800307ef  mov     ebx, eax
0x1800307f1  test    eax, eax
0x1800307f3  js      short loc_180030852
0x1800307f5  mov     rbp, [rsp+2088h+pv]
0x1800307fa  xor     eax, eax
0x1800307fc  mov     [rdi], rbp
0x1800307ff  cmp     ax, [rbp+0]
0x180030803  jz      short loc_180030847
0x180030805  lea     r13, ?map@?1??HKeyFromString@CRegParser@ATL@@KAPEAUHKEY__@@PEAG@Z@4QBUkeymap@?1??123@KAPEAU4@0@Z@B; `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::keymap const near * const `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::map
0x18003080c  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180030811  mov     rcx, rdi; this
0x180030814  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180030819  mov     ebx, eax
0x18003081b  test    eax, eax
0x18003081d  js      short loc_180030847
0x18003081f  xor     ebx, ebx
0x180030821  movsxd  rsi, ebx
0x180030824  lea     rcx, [rsp+2088h+String1]; lpString1
0x180030829  add     rsi, rsi
0x18003082c  mov     rdx, [r13+rsi*8+0]; lpString2
0x180030831  call    cs:__imp_lstrcmpiW
0x180030837  test    eax, eax
0x180030839  jz      short loc_180030874
0x18003083b  inc     ebx
0x18003083d  cmp     ebx, 0Eh
0x180030840  jb      short loc_180030821
0x180030842  mov     ebx, 80020009h
0x180030847  mov     rcx, rbp; pv
0x18003084a  call    cs:__imp_CoTaskMemFree
0x180030850  mov     eax, ebx
0x180030852  mov     rcx, [rsp+2088h+var_48]
0x18003085a  xor     rcx, rsp; StackCookie
0x18003085d  call    __security_check_cookie
0x180030862  add     rsp, 2050h
0x180030869  pop     r15
0x18003086b  pop     r14
0x18003086d  pop     r13
0x18003086f  pop     rdi
0x180030870  pop     rsi
0x180030871  pop     rbp
0x180030872  pop     rbx
0x180030873  retn
0x180030874  mov     rsi, [r13+rsi*8+8]
0x180030879  test    rsi, rsi
0x18003087c  jz      short loc_180030842
0x18003087e  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180030883  mov     rcx, rdi; this
0x180030886  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18003088b  mov     ebx, eax
0x18003088d  test    eax, eax
0x18003088f  js      short loc_180030847
0x180030891  mov     eax, 7Bh ; '{'
0x180030896  cmp     ax, [rsp+2088h+String1]
0x18003089b  jnz     short loc_180030842
0x18003089d  mov     [rsp+2088h+var_2068], 0; int
0x1800308a5  mov     r8, rsi; HKEY
0x1800308a8  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x1800308ad  mov     rcx, rdi; this
0x1800308b0  test    r15d, r15d
0x1800308b3  jz      short loc_1800308E9
0x1800308b5  mov     r14, [rdi]
0x1800308b8  mov     r9d, r15d; int
0x1800308bb  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x1800308c0  mov     ebx, eax
0x1800308c2  test    eax, eax
0x1800308c4  jns     short loc_1800308FB
0x1800308c6  xor     r9d, r9d; int
0x1800308c9  mov     [rdi], r14
0x1800308cc  mov     r8, rsi; HKEY
0x1800308cf  mov     [rsp+2088h+var_2068], 0; int
0x1800308d7  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x1800308dc  mov     rcx, rdi; this
0x1800308df  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x1800308e4  jmp     loc_180030847
0x1800308e9  xor     r9d, r9d; int
0x1800308ec  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x1800308f1  mov     ebx, eax
0x1800308f3  test    eax, eax
0x1800308f5  js      loc_180030847
0x1800308fb  mov     rcx, rdi; this
0x1800308fe  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x180030903  mov     rcx, [rdi]
0x180030906  xor     eax, eax
0x180030908  cmp     ax, [rcx]
0x18003090b  jnz     loc_18003080C
0x180030911  jmp     loc_180030847
```
