# ATL::CRegParser::RegisterBuffer(ushort *,int)

- ea: `0x1800074dc`
- end: `0x180007646`
- name: `?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z`
- size: `362`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000764c`

## callees

- `0x180002570`
- `0x180003150`
- `0x180006f50`
- `0x180007120`
- `0x1800074dc`
- `0x1800078ec`
- `0x180008084`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000757a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000757a`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180007561`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180007561`

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
0x1800074dc  push    rbx
0x1800074de  push    rbp
0x1800074df  push    rsi
0x1800074e0  push    rdi
0x1800074e1  push    r13
0x1800074e3  push    r14
0x1800074e5  push    r15
0x1800074e7  mov     eax, 2050h
0x1800074ec  call    _alloca_probe
0x1800074f1  sub     rsp, rax
0x1800074f4  mov     rax, cs:__security_cookie
0x1800074fb  xor     rax, rsp
0x1800074fe  mov     [rsp+2088h+var_48], rax
0x180007506  mov     r15d, r8d
0x180007509  mov     [rsp+2088h+pv], 0
0x180007512  lea     r8, [rsp+2088h+pv]; unsigned __int16 **
0x180007517  mov     rdi, rcx
0x18000751a  call    ?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z; ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)
0x18000751f  mov     ebx, eax
0x180007521  test    eax, eax
0x180007523  js      short loc_180007582
0x180007525  mov     rbp, [rsp+2088h+pv]
0x18000752a  xor     eax, eax
0x18000752c  mov     [rdi], rbp
0x18000752f  cmp     ax, [rbp+0]
0x180007533  jz      short loc_180007577
0x180007535  lea     r13, ?map@?1??HKeyFromString@CRegParser@ATL@@KAPEAUHKEY__@@PEAG@Z@4QBUkeymap@?1??123@KAPEAU4@0@Z@B; `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::keymap const near * const `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::map
0x18000753c  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180007541  mov     rcx, rdi; this
0x180007544  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180007549  mov     ebx, eax
0x18000754b  test    eax, eax
0x18000754d  js      short loc_180007577
0x18000754f  xor     ebx, ebx
0x180007551  movsxd  rsi, ebx
0x180007554  lea     rcx, [rsp+2088h+String1]; lpString1
0x180007559  add     rsi, rsi
0x18000755c  mov     rdx, [r13+rsi*8+0]; lpString2
0x180007561  call    cs:__imp_lstrcmpiW
0x180007567  test    eax, eax
0x180007569  jz      short loc_1800075A4
0x18000756b  inc     ebx
0x18000756d  cmp     ebx, 0Eh
0x180007570  jb      short loc_180007551
0x180007572  mov     ebx, 80020009h
0x180007577  mov     rcx, rbp; pv
0x18000757a  call    cs:__imp_CoTaskMemFree
0x180007580  mov     eax, ebx
0x180007582  mov     rcx, [rsp+2088h+var_48]
0x18000758a  xor     rcx, rsp; StackCookie
0x18000758d  call    __security_check_cookie
0x180007592  add     rsp, 2050h
0x180007599  pop     r15
0x18000759b  pop     r14
0x18000759d  pop     r13
0x18000759f  pop     rdi
0x1800075a0  pop     rsi
0x1800075a1  pop     rbp
0x1800075a2  pop     rbx
0x1800075a3  retn
0x1800075a4  mov     rsi, [r13+rsi*8+8]
0x1800075a9  test    rsi, rsi
0x1800075ac  jz      short loc_180007572
0x1800075ae  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x1800075b3  mov     rcx, rdi; this
0x1800075b6  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800075bb  mov     ebx, eax
0x1800075bd  test    eax, eax
0x1800075bf  js      short loc_180007577
0x1800075c1  mov     eax, 7Bh ; '{'
0x1800075c6  cmp     ax, [rsp+2088h+String1]
0x1800075cb  jnz     short loc_180007572
0x1800075cd  mov     [rsp+2088h+var_2068], 0; int
0x1800075d5  mov     r8, rsi; HKEY
0x1800075d8  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x1800075dd  mov     rcx, rdi; this
0x1800075e0  test    r15d, r15d
0x1800075e3  jz      short loc_180007619
0x1800075e5  mov     r14, [rdi]
0x1800075e8  mov     r9d, r15d; int
0x1800075eb  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x1800075f0  mov     ebx, eax
0x1800075f2  test    eax, eax
0x1800075f4  jns     short loc_18000762B
0x1800075f6  xor     r9d, r9d; int
0x1800075f9  mov     [rdi], r14
0x1800075fc  mov     r8, rsi; HKEY
0x1800075ff  mov     [rsp+2088h+var_2068], 0; int
0x180007607  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x18000760c  mov     rcx, rdi; this
0x18000760f  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180007614  jmp     loc_180007577
0x180007619  xor     r9d, r9d; int
0x18000761c  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180007621  mov     ebx, eax
0x180007623  test    eax, eax
0x180007625  js      loc_180007577
0x18000762b  mov     rcx, rdi; this
0x18000762e  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x180007633  mov     rcx, [rdi]
0x180007636  xor     eax, eax
0x180007638  cmp     ax, [rcx]
0x18000763b  jnz     loc_18000753C
0x180007641  jmp     loc_180007577
```
