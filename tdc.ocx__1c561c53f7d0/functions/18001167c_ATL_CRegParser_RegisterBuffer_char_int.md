# ATL::CRegParser::RegisterBuffer(char *,int)

- ea: `0x18001167c`
- end: `0x1800117fa`
- name: `?RegisterBuffer@CRegParser@ATL@@QEAAJPEADH@Z`
- size: `382`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, char *, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x180011800`

## callees

- `0x180011060`
- `0x1800111c8`
- `0x18001167c`
- `0x180011b0c`
- `0x180014270`
- `0x180014300`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180011718`
- `ole32!CoTaskMemFree` at `0x180011718`
- `USER32!CharNextA` at `0x1800117e1`
- `USER32!CharNextA` at `0x1800117e1`
- `KERNEL32!lstrcmpiA` at `0x1800116ff`
- `KERNEL32!lstrcmpiA` at `0x1800116ff`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::RegisterBuffer(LPCSTR *this, char *a2, int a3)
{
  __int64 result; // rax
  int Token; // ebx
  _BYTE *v7; // rbp
  int v8; // ebx
  HKEY v9; // rsi
  LPCSTR v10; // r14
  LPVOID pv; // [rsp+30h] [rbp-1058h] BYREF
  CHAR String1[4096]; // [rsp+40h] [rbp-1048h] BYREF

  pv = 0;
  result = ATL::CRegParser::PreProcessBuffer(this, a2, (char **)&pv);
  Token = result;
  if ( (int)result >= 0 )
  {
    v7 = pv;
    *this = (LPCSTR)pv;
    if ( *v7 )
    {
      do
      {
        Token = ATL::CRegParser::NextToken((ATL::CRegParser *)this, String1);
        if ( Token < 0 )
          break;
        v8 = 0;
        while ( lstrcmpiA(String1, (&`ATL::CRegParser::HKeyFromString'::`2'::map)[2 * v8]) )
        {
          if ( (unsigned int)++v8 >= 0xE )
            goto LABEL_7;
        }
        v9 = (HKEY)(&`ATL::CRegParser::HKeyFromString'::`2'::map)[2 * v8 + 1];
        if ( !v9 )
          goto LABEL_7;
        Token = ATL::CRegParser::NextToken((ATL::CRegParser *)this, String1);
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
          *this = CharNextA(*this);
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
0x18001167c  push    rbx
0x18001167e  push    rbp
0x18001167f  push    rsi
0x180011680  push    rdi
0x180011681  push    r13
0x180011683  push    r14
0x180011685  push    r15
0x180011687  mov     eax, 1050h
0x18001168c  call    _alloca_probe
0x180011691  sub     rsp, rax
0x180011694  mov     rax, cs:__security_cookie
0x18001169b  xor     rax, rsp
0x18001169e  mov     [rsp+1088h+var_48], rax
0x1800116a6  mov     r15d, r8d
0x1800116a9  mov     [rsp+1088h+pv], 0
0x1800116b2  lea     r8, [rsp+1088h+pv]; char **
0x1800116b7  mov     rdi, rcx
0x1800116ba  call    ?PreProcessBuffer@CRegParser@ATL@@QEAAJPEADPEAPEAD@Z; ATL::CRegParser::PreProcessBuffer(char *,char * *)
0x1800116bf  mov     ebx, eax
0x1800116c1  test    eax, eax
0x1800116c3  js      short loc_180011720
0x1800116c5  mov     rbp, [rsp+1088h+pv]
0x1800116ca  mov     [rdi], rbp
0x1800116cd  cmp     byte ptr [rbp+0], 0
0x1800116d1  jz      short loc_180011715
0x1800116d3  lea     r13, ?map@?1??HKeyFromString@CRegParser@ATL@@KAPEAUHKEY__@@PEAD@Z@4QBUkeymap@?1??123@KAPEAU4@0@Z@B; `ATL::CRegParser::HKeyFromString(char *)'::`2'::keymap const near * const `ATL::CRegParser::HKeyFromString(char *)'::`2'::map
0x1800116da  lea     rdx, [rsp+1088h+String1]; char *
0x1800116df  mov     rcx, rdi; this
0x1800116e2  call    ?NextToken@CRegParser@ATL@@IEAAJPEAD@Z; ATL::CRegParser::NextToken(char *)
0x1800116e7  mov     ebx, eax
0x1800116e9  test    eax, eax
0x1800116eb  js      short loc_180011715
0x1800116ed  xor     ebx, ebx
0x1800116ef  movsxd  rsi, ebx
0x1800116f2  lea     rcx, [rsp+1088h+String1]; lpString1
0x1800116f7  add     rsi, rsi
0x1800116fa  mov     rdx, [r13+rsi*8+0]; lpString2
0x1800116ff  call    cs:__imp_lstrcmpiA
0x180011705  test    eax, eax
0x180011707  jz      short loc_180011742
0x180011709  inc     ebx
0x18001170b  cmp     ebx, 0Eh
0x18001170e  jb      short loc_1800116EF
0x180011710  mov     ebx, 80020009h
0x180011715  mov     rcx, rbp; pv
0x180011718  call    cs:__imp_CoTaskMemFree
0x18001171e  mov     eax, ebx
0x180011720  mov     rcx, [rsp+1088h+var_48]
0x180011728  xor     rcx, rsp; StackCookie
0x18001172b  call    __security_check_cookie
0x180011730  add     rsp, 1050h
0x180011737  pop     r15
0x180011739  pop     r14
0x18001173b  pop     r13
0x18001173d  pop     rdi
0x18001173e  pop     rsi
0x18001173f  pop     rbp
0x180011740  pop     rbx
0x180011741  retn
0x180011742  mov     rsi, [r13+rsi*8+8]
0x180011747  test    rsi, rsi
0x18001174a  jz      short loc_180011710
0x18001174c  lea     rdx, [rsp+1088h+String1]; char *
0x180011751  mov     rcx, rdi; this
0x180011754  call    ?NextToken@CRegParser@ATL@@IEAAJPEAD@Z; ATL::CRegParser::NextToken(char *)
0x180011759  mov     ebx, eax
0x18001175b  test    eax, eax
0x18001175d  js      short loc_180011715
0x18001175f  cmp     [rsp+1088h+String1], 7Bh ; '{'
0x180011764  jnz     short loc_180011710
0x180011766  mov     [rsp+1088h+var_1068], 0; int
0x18001176e  mov     r8, rsi; HKEY
0x180011771  lea     rdx, [rsp+1088h+String1]; char *
0x180011776  mov     rcx, rdi; this
0x180011779  test    r15d, r15d
0x18001177c  jz      short loc_1800117B2
0x18001177e  mov     r14, [rdi]
0x180011781  mov     r9d, r15d; int
0x180011784  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEADPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(char *,HKEY__ *,int,int)
0x180011789  mov     ebx, eax
0x18001178b  test    eax, eax
0x18001178d  jns     short loc_1800117C4
0x18001178f  xor     r9d, r9d; int
0x180011792  mov     [rdi], r14
0x180011795  mov     r8, rsi; HKEY
0x180011798  mov     [rsp+1088h+var_1068], 0; int
0x1800117a0  lea     rdx, [rsp+1088h+String1]; char *
0x1800117a5  mov     rcx, rdi; this
0x1800117a8  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEADPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(char *,HKEY__ *,int,int)
0x1800117ad  jmp     loc_180011715
0x1800117b2  xor     r9d, r9d; int
0x1800117b5  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEADPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(char *,HKEY__ *,int,int)
0x1800117ba  mov     ebx, eax
0x1800117bc  test    eax, eax
0x1800117be  js      loc_180011715
0x1800117c4  mov     rdx, [rdi]
0x1800117c7  movsx   ecx, byte ptr [rdx]
0x1800117ca  sub     ecx, 9
0x1800117cd  jz      short loc_1800117DE
0x1800117cf  sub     ecx, 1
0x1800117d2  jz      short loc_1800117DE
0x1800117d4  sub     ecx, 3
0x1800117d7  jz      short loc_1800117DE
0x1800117d9  cmp     ecx, 13h
0x1800117dc  jnz     short loc_1800117EC
0x1800117de  mov     rcx, rdx; lpsz
0x1800117e1  call    cs:__imp_CharNextA
0x1800117e7  mov     [rdi], rax
0x1800117ea  jmp     short loc_1800117C4
0x1800117ec  cmp     byte ptr [rdx], 0
0x1800117ef  jnz     loc_1800116DA
0x1800117f5  jmp     loc_180011715
```
