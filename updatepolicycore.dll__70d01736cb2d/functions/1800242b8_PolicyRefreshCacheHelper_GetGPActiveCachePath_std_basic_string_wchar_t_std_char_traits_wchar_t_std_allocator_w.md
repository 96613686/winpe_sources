# PolicyRefreshCacheHelper::GetGPActiveCachePath(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &)

- ea: `0x1800242b8`
- end: `0x180024363`
- name: `?GetGPActiveCachePath@PolicyRefreshCacheHelper@@SAJAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAV23@@Z`
- size: `171`
- prototype: `__int64 __fastcall(wchar_t **Src, __int64)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180011b2c`
- `0x18001bd30`

## callees

- `0x18000aac0`
- `0x180010260`
- `0x180022634`
- `0x180022788`
- `0x1800242b8`

## string_xrefs

- `0x180024332`: `C:\__w\1\s\src\Client\policy\src\helpers\PolicyRefreshCacheHelper.cpp`

## pseudocode

```c
__int64 __fastcall PolicyRefreshCacheHelper::GetGPActiveCachePath(wchar_t **Src, __int64 a2)
{
  int GPActiveCache; // eax
  unsigned int v5; // ebx
  unsigned __int64 v6; // r9
  __int64 v7; // rdx
  int GPCacheRegKeyPath; // eax
  int v10; // [rsp+20h] [rbp-48h] BYREF
  __m128i v11[4]; // [rsp+28h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v10 = 1;
  v11[0] = 0;
  v11[1] = _mm_load_si128((const __m128i *)&_xmm);
  v11[0].m128i_i16[0] = 0;
  GPActiveCache = PolicyRefreshCacheHelper::GetGPActiveCache((unsigned int *)&v10);
  v5 = GPActiveCache;
  if ( GPActiveCache >= 0 )
  {
    GPCacheRegKeyPath = PolicyRefreshCacheHelper::GetGPCacheRegKeyPath(Src, v10, a2, v11);
    v5 = GPCacheRegKeyPath;
    if ( GPCacheRegKeyPath >= 0 )
    {
      v5 = 0;
      goto LABEL_8;
    }
    v6 = (unsigned int)GPCacheRegKeyPath;
    v7 = 500;
    goto LABEL_6;
  }
  if ( (unsigned int)(GPActiveCache + 2147024894) > 1 )
  {
    v6 = (unsigned int)GPActiveCache;
    v7 = 498;
LABEL_6:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\policy\\src\\helpers\\PolicyRefreshCacheHelper.cpp",
      (const char *)v6,
      v10);
  }
LABEL_8:
  std::wstring::~wstring(v11);
  return v5;
}

```

## disassembly

```asm
0x1800242b8  mov     rax, rsp
0x1800242bb  mov     [rax+18h], rbx
0x1800242bf  push    rbp
0x1800242c0  push    rsi
0x1800242c1  push    rdi
0x1800242c2  sub     rsp, 50h
0x1800242c6  mov     rsi, rdx
0x1800242c9  mov     rdi, rcx
0x1800242cc  mov     dword ptr [rax-48h], 1
0x1800242d3  xorps   xmm0, xmm0
0x1800242d6  movups  xmmword ptr [rax-40h], xmm0
0x1800242da  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1800242e2  movdqu  xmmword ptr [rax-30h], xmm1
0x1800242e7  xor     ebp, ebp
0x1800242e9  mov     [rax-40h], bp
0x1800242ed  lea     rcx, [rax-48h]; unsigned int *
0x1800242f1  call    ?GetGPActiveCache@PolicyRefreshCacheHelper@@CAJAEAK@Z; PolicyRefreshCacheHelper::GetGPActiveCache(ulong &)
0x1800242f6  mov     ebx, eax
0x1800242f8  test    eax, eax
0x1800242fa  jns     short loc_180024310
0x1800242fc  add     eax, 7FF8FFFEh
0x180024301  cmp     eax, 1
0x180024304  jbe     short loc_180024347
0x180024306  mov     r9d, ebx
0x180024309  mov     edx, 1F2h
0x18002430e  jmp     short loc_180024332
0x180024310  lea     r9, [rsp+68h+var_40]
0x180024315  mov     r8, rsi
0x180024318  mov     edx, [rsp+68h+var_48]
0x18002431c  mov     rcx, rdi; Src
0x18002431f  call    ?GetGPCacheRegKeyPath@PolicyRefreshCacheHelper@@CAJAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@KAEAV23@1@Z; PolicyRefreshCacheHelper::GetGPCacheRegKeyPath(std::wstring const &,ulong,std::wstring &,std::wstring &)
0x180024324  mov     ebx, eax
0x180024326  test    eax, eax
0x180024328  jns     short loc_180024345
0x18002432a  mov     r9d, eax; char *
0x18002432d  mov     edx, 1F4h; void *
0x180024332  lea     r8, aCW1SSrcClientP_1; "C:\\__w\\1\\s\\src\\Client\\policy\\src"...
0x180024339  mov     rcx, [rsp+68h]; this
0x18002433e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180024343  jmp     short loc_180024347
0x180024345  mov     ebx, ebp
0x180024347  lea     rcx, [rsp+68h+var_40]; void *
0x18002434c  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180024351  mov     eax, ebx
0x180024353  mov     rbx, [rsp+68h+arg_10]
0x18002435b  add     rsp, 50h
0x18002435f  pop     rdi
0x180024360  pop     rsi
0x180024361  pop     rbp
0x180024362  retn
```
