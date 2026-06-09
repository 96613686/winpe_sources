# ATL::CRegParser::RegisterBuffer(ushort *,int)

- ea: `0x180044058`
- end: `0x1800441cf`
- name: `?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z`
- size: `375`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x180044270`

## callees

- `0x18003cb60`
- `0x180042f30`
- `0x180043358`
- `0x180044058`
- `0x18004442c`
- `0x18004589c`
- `0x180057c40`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800440fc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800440fc`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800440dd`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800440dd`

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
0x180044058  push    rbx
0x18004405a  push    rbp
0x18004405b  push    rsi
0x18004405c  push    rdi
0x18004405d  push    r13
0x18004405f  push    r14
0x180044061  push    r15
0x180044063  mov     eax, 2050h
0x180044068  call    _alloca_probe
0x18004406d  sub     rsp, rax
0x180044070  mov     rax, cs:__security_cookie
0x180044077  xor     rax, rsp
0x18004407a  mov     [rsp+2088h+var_48], rax
0x180044082  mov     r15d, r8d
0x180044085  mov     [rsp+2088h+pv], 0
0x18004408e  lea     r8, [rsp+2088h+pv]; unsigned __int16 **
0x180044093  mov     rdi, rcx
0x180044096  call    ?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z; ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)
0x18004409b  mov     ebx, eax
0x18004409d  test    eax, eax
0x18004409f  js      short loc_18004410A
0x1800440a1  mov     rbp, [rsp+2088h+pv]
0x1800440a6  xor     eax, eax
0x1800440a8  mov     [rdi], rbp
0x1800440ab  cmp     ax, [rbp+0]
0x1800440af  jz      short loc_1800440F9
0x1800440b1  lea     r13, ?map@?1??HKeyFromString@CRegParser@ATL@@KAPEAUHKEY__@@PEAG@Z@4QBUkeymap@?1??123@KAPEAU4@0@Z@B; `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::keymap const near * const `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::map
0x1800440b8  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x1800440bd  mov     rcx, rdi; this
0x1800440c0  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800440c5  mov     ebx, eax
0x1800440c7  test    eax, eax
0x1800440c9  js      short loc_1800440F9
0x1800440cb  xor     ebx, ebx
0x1800440cd  movsxd  rsi, ebx
0x1800440d0  lea     rcx, [rsp+2088h+String1]; lpString1
0x1800440d5  add     rsi, rsi
0x1800440d8  mov     rdx, [r13+rsi*8+0]; lpString2
0x1800440dd  call    cs:__imp_lstrcmpiW
0x1800440e4  nop     dword ptr [rax+rax+00h]
0x1800440e9  test    eax, eax
0x1800440eb  jz      short loc_18004412D
0x1800440ed  inc     ebx
0x1800440ef  cmp     ebx, 0Eh
0x1800440f2  jb      short loc_1800440CD
0x1800440f4  mov     ebx, 80020009h
0x1800440f9  mov     rcx, rbp; pv
0x1800440fc  call    cs:__imp_CoTaskMemFree
0x180044103  nop     dword ptr [rax+rax+00h]
0x180044108  mov     eax, ebx
0x18004410a  mov     rcx, [rsp+2088h+var_48]
0x180044112  xor     rcx, rsp; StackCookie
0x180044115  call    __security_check_cookie
0x18004411a  add     rsp, 2050h
0x180044121  pop     r15
0x180044123  pop     r14
0x180044125  pop     r13
0x180044127  pop     rdi
0x180044128  pop     rsi
0x180044129  pop     rbp
0x18004412a  pop     rbx
0x18004412b  retn
0x18004412d  mov     rsi, [r13+rsi*8+8]
0x180044132  test    rsi, rsi
0x180044135  jz      short loc_1800440F4
0x180044137  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x18004413c  mov     rcx, rdi; this
0x18004413f  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180044144  mov     ebx, eax
0x180044146  test    eax, eax
0x180044148  js      short loc_1800440F9
0x18004414a  mov     eax, 7Bh ; '{'
0x18004414f  cmp     ax, [rsp+2088h+String1]
0x180044154  jnz     short loc_1800440F4
0x180044156  mov     [rsp+2088h+var_2068], 0; int
0x18004415e  mov     r8, rsi; HKEY
0x180044161  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180044166  mov     rcx, rdi; this
0x180044169  test    r15d, r15d
0x18004416c  jz      short loc_1800441A2
0x18004416e  mov     r14, [rdi]
0x180044171  mov     r9d, r15d; int
0x180044174  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180044179  mov     ebx, eax
0x18004417b  test    eax, eax
0x18004417d  jns     short loc_1800441B4
0x18004417f  xor     r9d, r9d; int
0x180044182  mov     [rdi], r14
0x180044185  mov     r8, rsi; HKEY
0x180044188  mov     [rsp+2088h+var_2068], 0; int
0x180044190  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180044195  mov     rcx, rdi; this
0x180044198  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x18004419d  jmp     loc_1800440F9
0x1800441a2  xor     r9d, r9d; int
0x1800441a5  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x1800441aa  mov     ebx, eax
0x1800441ac  test    eax, eax
0x1800441ae  js      loc_1800440F9
0x1800441b4  mov     rcx, rdi; this
0x1800441b7  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x1800441bc  mov     rcx, [rdi]
0x1800441bf  xor     eax, eax
0x1800441c1  cmp     ax, [rcx]
0x1800441c4  jnz     loc_1800440B8
0x1800441ca  jmp     loc_1800440F9
```
