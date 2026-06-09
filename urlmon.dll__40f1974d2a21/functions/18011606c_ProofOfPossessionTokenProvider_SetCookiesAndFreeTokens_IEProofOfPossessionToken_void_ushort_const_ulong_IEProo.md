# ProofOfPossessionTokenProvider::SetCookiesAndFreeTokens<_IEProofOfPossessionToken>(void *,ushort const *,ulong,_IEProofOfPossessionToken *)

- ea: `0x18011606c`
- end: `0x180116274`
- name: `??$SetCookiesAndFreeTokens@U_IEProofOfPossessionToken@@@ProofOfPossessionTokenProvider@@YAXPEAXPEBGKPEAU_IEProofOfPossessionToken@@@Z`
- size: `520`
- prototype: `void __fastcall(void *, const WCHAR *, unsigned int, unsigned int *)`
- caller_count: `2`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x180002b34`
- `0x180003520`

## callees

- `0x180003440`
- `0x18001054c`
- `0x18008b160`
- `0x1800a5a88`
- `0x18011606c`
- `0x18011627c`
- `0x1801164ac`

## import_xrefs

- `msvcrt!wcschr` at `0x180116186`
- `msvcrt!wcschr` at `0x180116186`
- `msvcrt!wcscpy_s` at `0x18011619f`
- `msvcrt!wcscpy_s` at `0x18011619f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180116223`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18011622e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180116239`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180116256`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180116223`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18011622e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180116239`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180116256`
- `WININET!HttpAddRequestHeadersW` at `0x1801161c1`
- `WININET!HttpAddRequestHeadersW` at `0x1801161c1`
- `WININET!InternetSetCookieExW` at `0x180116211`
- `WININET!InternetSetCookieExW` at `0x180116211`

## pseudocode

```c
void __fastcall ProofOfPossessionTokenProvider::SetCookiesAndFreeTokens<_IEProofOfPossessionToken>(
        void *a1,
        const WCHAR *a2,
        unsigned int a3,
        unsigned int *a4)
{
  void *v6; // rbx
  unsigned int v7; // r15d
  __int64 v8; // r14
  __int64 v9; // rsi
  ProofOfPossessionTokenProvider *v10; // rcx
  unsigned int *v11; // r9
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // rax
  unsigned int v15; // ebx
  WCHAR *v16; // rbp
  wchar_t *v17; // rax
  DWORD v18; // ebx
  bool IsEdgeCookiesFeatureEnabled; // al
  DWORD v20; // r9d
  DWORD dwSize; // [rsp+30h] [rbp-58h] BYREF
  WCHAR *v22; // [rsp+38h] [rbp-50h] BYREF
  unsigned int v23; // [rsp+40h] [rbp-48h]

  dwSize = 0;
  v6 = a1;
  v7 = 0;
  if ( a3 )
  {
    v8 = 0;
    do
    {
      v9 = 8 * v8;
      if ( ProofOfPossessionTokenProvider::ShouldSetCookie(a2, *(wchar_t **)&a4[8 * v8], &dwSize, a4)
        || ProofOfPossessionTokenProvider::ShouldSetDeviceCookie(a2, *(wchar_t **)&a4[v9], &dwSize, v11) )
      {
        if ( v6 )
        {
          v12 = *(_QWORD *)&a4[v9 + 2];
          if ( v12 )
          {
            v13 = -1;
            do
              ++v13;
            while ( *(_WORD *)(*(_QWORD *)&a4[v9] + 2 * v13) );
            v14 = -1;
            do
              ++v14;
            while ( *(_WORD *)(v12 + 2 * v14) );
            v22 = 0;
            v15 = v14 + v13 + 5;
            v23 = 0;
            v16 = (WCHAR *)operator new[](saturated_mul(v15, 2u));
            AutoArray<unsigned short *,AutoTypedArrayFunctor<unsigned short>>::Clear(&v22);
            v22 = v16;
            v23 = v15;
            if ( !v16
              || (int)StringCchPrintfW(v16, v15, L"%s: %s\r\n", *(_QWORD *)&a4[v9], *(_QWORD *)&a4[v9 + 2]) < 0
              || (v17 = wcschr(v16, 0x3Bu)) != 0 && wcscpy_s(v17, 3u, L"\r\n") )
            {
              v6 = a1;
            }
            else
            {
              v6 = a1;
              HttpAddRequestHeadersW(a1, v16, 0xFFFFFFFF, 0x10000000u);
            }
            AutoArray<unsigned short *,AutoTypedArrayFunctor<unsigned short>>::Clear(&v22);
          }
        }
        else
        {
          v18 = a4[v9 + 6];
          IsEdgeCookiesFeatureEnabled = ProofOfPossessionTokenProvider::IsEdgeCookiesFeatureEnabled(v10);
          v20 = v18 | 0x8000;
          if ( !IsEdgeCookiesFeatureEnabled )
            v20 = v18;
          InternetSetCookieExW(a2, *(LPCWSTR *)&a4[v9], *(LPCWSTR *)&a4[v9 + 2], v20, *(_QWORD *)&a4[v9 + 4]);
          v6 = a1;
        }
      }
      CoTaskMemFree(*(LPVOID *)&a4[v9]);
      CoTaskMemFree(*(LPVOID *)&a4[v9 + 2]);
      CoTaskMemFree(*(LPVOID *)&a4[v9 + 4]);
      ++v7;
      ++v8;
    }
    while ( v7 < a3 );
  }
  CoTaskMemFree(a4);
}

```

## disassembly

```asm
0x18011606c  mov     rax, rsp
0x18011606f  mov     [rax+10h], rbx
0x180116073  mov     [rax+18h], r8d
0x180116077  mov     [rax+8], rcx
0x18011607b  push    rbp
0x18011607c  push    rsi
0x18011607d  push    rdi
0x18011607e  push    r12
0x180116080  push    r13
0x180116082  push    r14
0x180116084  push    r15
0x180116086  sub     rsp, 50h
0x18011608a  xor     r13d, r13d
0x18011608d  mov     rdi, r9
0x180116090  mov     [rax-58h], r13d
0x180116094  mov     r12, rdx
0x180116097  mov     rbx, rcx
0x18011609a  mov     r15d, r13d
0x18011609d  test    r8d, r8d
0x1801160a0  jz      loc_180116253
0x1801160a6  mov     r14d, r13d
0x1801160a9  or      rbp, 0FFFFFFFFFFFFFFFFh
0x1801160ad  mov     rsi, r14
0x1801160b0  lea     r8, [rsp+88h+dwSize]; lpdwSize
0x1801160b5  shl     rsi, 5
0x1801160b9  mov     rcx, r12; lpszUrl
0x1801160bc  mov     rdx, [rsi+rdi]; String1
0x1801160c0  call    ?ShouldSetCookie@ProofOfPossessionTokenProvider@@YA_NPEBG0PEAK@Z; ProofOfPossessionTokenProvider::ShouldSetCookie(ushort const *,ushort const *,ulong *)
0x1801160c5  test    al, al
0x1801160c7  jnz     short loc_1801160E2
0x1801160c9  mov     rdx, [rsi+rdi]; String1
0x1801160cd  lea     r8, [rsp+88h+dwSize]; lpdwSize
0x1801160d2  mov     rcx, r12; lpszUrl
0x1801160d5  call    ?ShouldSetDeviceCookie@ProofOfPossessionTokenProvider@@YA_NPEBG0PEAK@Z; ProofOfPossessionTokenProvider::ShouldSetDeviceCookie(ushort const *,ushort const *,ulong *)
0x1801160da  test    al, al
0x1801160dc  jz      loc_18011621F
0x1801160e2  test    rbx, rbx
0x1801160e5  jz      loc_1801161E4
0x1801160eb  mov     rdx, [rsi+rdi+8]
0x1801160f0  test    rdx, rdx
0x1801160f3  jz      loc_18011621F
0x1801160f9  mov     rax, [rsi+rdi]
0x1801160fd  mov     rcx, rbp
0x180116100  inc     rcx
0x180116103  cmp     [rax+rcx*2], r13w
0x180116108  jnz     short loc_180116100
0x18011610a  mov     rax, rbp
0x18011610d  inc     rax
0x180116110  cmp     [rdx+rax*2], r13w
0x180116115  jnz     short loc_18011610D
0x180116117  lea     ebx, [rcx+5]
0x18011611a  mov     [rsp+88h+var_50], r13
0x18011611f  add     ebx, eax
0x180116121  mov     [rsp+88h+var_48], r13d
0x180116126  mov     r13d, ebx
0x180116129  mov     eax, 2
0x18011612e  mul     r13
0x180116131  cmovb   rax, rbp
0x180116135  mov     rcx, rax; unsigned __int64
0x180116138  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18011613d  lea     rcx, [rsp+88h+var_50]
0x180116142  mov     rbp, rax
0x180116145  call    ?Clear@?$AutoArray@PEAGV?$AutoTypedArrayFunctor@G@@@@QEAAXXZ; AutoArray<ushort *,AutoTypedArrayFunctor<ushort>>::Clear(void)
0x18011614a  mov     [rsp+88h+var_50], rbp
0x18011614f  mov     [rsp+88h+var_48], ebx
0x180116153  test    rbp, rbp
0x180116156  jz      short loc_1801161C9
0x180116158  mov     rcx, [rsi+rdi+8]
0x18011615d  lea     r8, aSS_4; "%s: %s\r\n"
0x180116164  mov     r9, [rsi+rdi]
0x180116168  mov     edx, r13d; unsigned __int64
0x18011616b  mov     [rsp+88h+dwReserved], rcx
0x180116170  mov     rcx, rbp; unsigned __int16 *
0x180116173  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180116178  xor     r13d, r13d
0x18011617b  test    eax, eax
0x18011617d  js      short loc_1801161CC
0x18011617f  lea     edx, [r13+3Bh]; Ch
0x180116183  mov     rcx, rbp; Str
0x180116186  call    cs:__imp_wcschr
0x18011618c  test    rax, rax
0x18011618f  jz      short loc_1801161A9
0x180116191  lea     r8, Source; "\r\n"
0x180116198  mov     rcx, rax; Destination
0x18011619b  lea     edx, [r13+3]; SizeInWords
0x18011619f  call    cs:__imp_wcscpy_s
0x1801161a5  test    eax, eax
0x1801161a7  jnz     short loc_1801161CC
0x1801161a9  mov     rbx, [rsp+88h+hRequest]
0x1801161b1  mov     r9d, 10000000h; dwModifiers
0x1801161b7  mov     rcx, rbx; hRequest
0x1801161ba  or      r8d, 0FFFFFFFFh; dwHeadersLength
0x1801161be  mov     rdx, rbp; lpszHeaders
0x1801161c1  call    cs:__imp_HttpAddRequestHeadersW
0x1801161c7  jmp     short loc_1801161D4
0x1801161c9  xor     r13d, r13d
0x1801161cc  mov     rbx, [rsp+88h+hRequest]
0x1801161d4  lea     rcx, [rsp+88h+var_50]
0x1801161d9  call    ?Clear@?$AutoArray@PEAGV?$AutoTypedArrayFunctor@G@@@@QEAAXXZ; AutoArray<ushort *,AutoTypedArrayFunctor<ushort>>::Clear(void)
0x1801161de  or      rbp, 0FFFFFFFFFFFFFFFFh
0x1801161e2  jmp     short loc_18011621F
0x1801161e4  mov     ebx, [rsi+rdi+18h]
0x1801161e8  call    ?IsEdgeCookiesFeatureEnabled@ProofOfPossessionTokenProvider@@YA_NXZ; ProofOfPossessionTokenProvider::IsEdgeCookiesFeatureEnabled(void)
0x1801161ed  mov     r8, [rsi+rdi+8]; lpszCookieData
0x1801161f2  mov     r9d, ebx
0x1801161f5  mov     rdx, [rsi+rdi]; lpszCookieName
0x1801161f9  bts     r9d, 0Fh
0x1801161fe  test    al, al
0x180116200  mov     rcx, r12; lpszUrl
0x180116203  mov     rax, [rsi+rdi+10h]
0x180116208  cmovz   r9d, ebx; dwFlags
0x18011620c  mov     [rsp+88h+dwReserved], rax; dwReserved
0x180116211  call    cs:__imp_InternetSetCookieExW
0x180116217  mov     rbx, [rsp+88h+hRequest]
0x18011621f  mov     rcx, [rsi+rdi]; pv
0x180116223  call    cs:__imp_CoTaskMemFree
0x180116229  mov     rcx, [rsi+rdi+8]; pv
0x18011622e  call    cs:__imp_CoTaskMemFree
0x180116234  mov     rcx, [rsi+rdi+10h]; pv
0x180116239  call    cs:__imp_CoTaskMemFree
0x18011623f  inc     r15d
0x180116242  inc     r14
0x180116245  cmp     r15d, [rsp+88h+arg_10]
0x18011624d  jb      loc_1801160AD
0x180116253  mov     rcx, rdi; pv
0x180116256  call    cs:__imp_CoTaskMemFree
0x18011625c  mov     rbx, [rsp+88h+arg_8]
0x180116264  add     rsp, 50h
0x180116268  pop     r15
0x18011626a  pop     r14
0x18011626c  pop     r13
0x18011626e  pop     r12
0x180116270  pop     rdi
0x180116271  pop     rsi
0x180116272  pop     rbp
0x180116273  retn
```
