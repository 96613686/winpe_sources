# ATL::CRegParser::RegisterBuffer(ushort *,int)

- ea: `0x1800147c0`
- end: `0x18001494a`
- name: `?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z`
- size: `394`
- prototype: `__int64 __fastcall(LPCWSTR *this, unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x180014950`

## callees

- `0x180014050`
- `0x1800141f0`
- `0x1800147c0`
- `0x180014b28`
- `0x18001b420`
- `0x18001b4e0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001485e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001485e`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18001492f`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18001492f`
- `KERNEL32!lstrcmpiW` at `0x180014845`
- `KERNEL32!lstrcmpiW` at `0x180014845`

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
0x1800147c0  push    rbx
0x1800147c2  push    rbp
0x1800147c3  push    rsi
0x1800147c4  push    rdi
0x1800147c5  push    r13
0x1800147c7  push    r14
0x1800147c9  push    r15
0x1800147cb  mov     eax, 2050h
0x1800147d0  call    _alloca_probe
0x1800147d5  sub     rsp, rax
0x1800147d8  mov     rax, cs:__security_cookie
0x1800147df  xor     rax, rsp
0x1800147e2  mov     [rsp+2088h+var_48], rax
0x1800147ea  mov     r15d, r8d
0x1800147ed  mov     [rsp+2088h+pv], 0
0x1800147f6  lea     r8, [rsp+2088h+pv]; unsigned __int16 **
0x1800147fb  mov     rdi, rcx
0x1800147fe  call    ?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z; ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)
0x180014803  mov     ebx, eax
0x180014805  test    eax, eax
0x180014807  js      short loc_180014866
0x180014809  mov     rbp, [rsp+2088h+pv]
0x18001480e  xor     eax, eax
0x180014810  mov     [rdi], rbp
0x180014813  cmp     ax, [rbp+0]
0x180014817  jz      short loc_18001485B
0x180014819  lea     r13, ?map@?1??HKeyFromString@CRegParser@ATL@@KAPEAUHKEY__@@PEAG@Z@4QBUkeymap@?1??123@KAPEAU4@0@Z@B; `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::keymap const near * const `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::map
0x180014820  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180014825  mov     rcx, rdi; this
0x180014828  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18001482d  mov     ebx, eax
0x18001482f  test    eax, eax
0x180014831  js      short loc_18001485B
0x180014833  xor     ebx, ebx
0x180014835  movsxd  rsi, ebx
0x180014838  lea     rcx, [rsp+2088h+String1]; lpString1
0x18001483d  add     rsi, rsi
0x180014840  mov     rdx, [r13+rsi*8+0]; lpString2
0x180014845  call    cs:__imp_lstrcmpiW
0x18001484b  test    eax, eax
0x18001484d  jz      short loc_180014888
0x18001484f  inc     ebx
0x180014851  cmp     ebx, 0Eh
0x180014854  jb      short loc_180014835
0x180014856  mov     ebx, 80020009h
0x18001485b  mov     rcx, rbp; pv
0x18001485e  call    cs:__imp_CoTaskMemFree
0x180014864  mov     eax, ebx
0x180014866  mov     rcx, [rsp+2088h+var_48]
0x18001486e  xor     rcx, rsp; StackCookie
0x180014871  call    __security_check_cookie
0x180014876  add     rsp, 2050h
0x18001487d  pop     r15
0x18001487f  pop     r14
0x180014881  pop     r13
0x180014883  pop     rdi
0x180014884  pop     rsi
0x180014885  pop     rbp
0x180014886  pop     rbx
0x180014887  retn
0x180014888  mov     rsi, [r13+rsi*8+8]
0x18001488d  test    rsi, rsi
0x180014890  jz      short loc_180014856
0x180014892  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180014897  mov     rcx, rdi; this
0x18001489a  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18001489f  mov     ebx, eax
0x1800148a1  test    eax, eax
0x1800148a3  js      short loc_18001485B
0x1800148a5  mov     eax, 7Bh ; '{'
0x1800148aa  cmp     ax, [rsp+2088h+String1]
0x1800148af  jnz     short loc_180014856
0x1800148b1  mov     [rsp+2088h+var_2068], 0; int
0x1800148b9  mov     r8, rsi; HKEY
0x1800148bc  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x1800148c1  mov     rcx, rdi; this
0x1800148c4  test    r15d, r15d
0x1800148c7  jz      short loc_1800148FD
0x1800148c9  mov     r14, [rdi]
0x1800148cc  mov     r9d, r15d; int
0x1800148cf  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x1800148d4  mov     ebx, eax
0x1800148d6  test    eax, eax
0x1800148d8  jns     short loc_18001490F
0x1800148da  xor     r9d, r9d; int
0x1800148dd  mov     [rdi], r14
0x1800148e0  mov     r8, rsi; HKEY
0x1800148e3  mov     [rsp+2088h+var_2068], 0; int
0x1800148eb  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x1800148f0  mov     rcx, rdi; this
0x1800148f3  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x1800148f8  jmp     loc_18001485B
0x1800148fd  xor     r9d, r9d; int
0x180014900  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180014905  mov     ebx, eax
0x180014907  test    eax, eax
0x180014909  js      loc_18001485B
0x18001490f  mov     r8, [rdi]
0x180014912  movzx   edx, word ptr [r8]
0x180014916  mov     ecx, edx
0x180014918  sub     ecx, 9
0x18001491b  jz      short loc_18001492C
0x18001491d  sub     ecx, 1
0x180014920  jz      short loc_18001492C
0x180014922  sub     ecx, 3
0x180014925  jz      short loc_18001492C
0x180014927  cmp     ecx, 13h
0x18001492a  jnz     short loc_18001493A
0x18001492c  mov     rcx, r8; lpsz
0x18001492f  call    cs:__imp_CharNextW
0x180014935  mov     [rdi], rax
0x180014938  jmp     short loc_18001490F
0x18001493a  xor     eax, eax
0x18001493c  cmp     ax, dx
0x18001493f  jnz     loc_180014820
0x180014945  jmp     loc_18001485B
```
