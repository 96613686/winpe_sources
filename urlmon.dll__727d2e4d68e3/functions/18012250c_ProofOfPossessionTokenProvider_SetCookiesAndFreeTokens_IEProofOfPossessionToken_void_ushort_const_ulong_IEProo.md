# ProofOfPossessionTokenProvider::SetCookiesAndFreeTokens<_IEProofOfPossessionToken>(void *,ushort const *,ulong,_IEProofOfPossessionToken *)

- ea: `0x18012250c`
- end: `0x180122749`
- name: `??$SetCookiesAndFreeTokens@U_IEProofOfPossessionToken@@@ProofOfPossessionTokenProvider@@YAXPEAXPEBGKPEAU_IEProofOfPossessionToken@@@Z`
- size: `573`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x180002b8c`
- `0x18000367c`

## callees

- `0x180003578`
- `0x1800162d4`
- `0x180090b3c`
- `0x1800ac8c8`
- `0x18012250c`
- `0x180122750`
- `0x1801229ac`

## import_xrefs

- `msvcrt!wcschr` at `0x18012262a`
- `msvcrt!wcschr` at `0x18012262a`
- `msvcrt!wcscpy_s` at `0x180122649`
- `msvcrt!wcscpy_s` at `0x180122649`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801226df`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801226f0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180122701`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180122724`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801226df`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801226f0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180122701`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180122724`
- `WININET!HttpAddRequestHeadersW` at `0x180122671`
- `WININET!HttpAddRequestHeadersW` at `0x180122671`
- `WININET!InternetSetCookieExW` at `0x1801226c7`
- `WININET!InternetSetCookieExW` at `0x1801226c7`

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
0x18012250c  mov     rax, rsp
0x18012250f  mov     [rax+10h], rbx
0x180122513  mov     [rax+18h], r8d
0x180122517  mov     [rax+8], rcx
0x18012251b  push    rbp
0x18012251c  push    rsi
0x18012251d  push    rdi
0x18012251e  push    r12
0x180122520  push    r13
0x180122522  push    r14
0x180122524  push    r15
0x180122526  sub     rsp, 50h
0x18012252a  xor     r13d, r13d
0x18012252d  mov     rdi, r9
0x180122530  mov     [rax-58h], r13d
0x180122534  mov     r12, rdx
0x180122537  mov     rbx, rcx
0x18012253a  mov     r15d, r13d
0x18012253d  test    r8d, r8d
0x180122540  jz      loc_180122721
0x180122546  mov     r14d, r13d
0x180122549  or      rbp, 0FFFFFFFFFFFFFFFFh
0x18012254d  mov     rsi, r14
0x180122550  lea     r8, [rsp+88h+dwSize]; lpdwSize
0x180122555  shl     rsi, 5
0x180122559  mov     rcx, r12; lpszUrl
0x18012255c  mov     rdx, [rsi+rdi]; String1
0x180122560  call    ?ShouldSetCookie@ProofOfPossessionTokenProvider@@YA_NPEBG0PEAK@Z; ProofOfPossessionTokenProvider::ShouldSetCookie(ushort const *,ushort const *,ulong *)
0x180122565  test    al, al
0x180122567  jnz     short loc_180122582
0x180122569  mov     rdx, [rsi+rdi]; String1
0x18012256d  lea     r8, [rsp+88h+dwSize]; lpdwSize
0x180122572  mov     rcx, r12; lpszUrl
0x180122575  call    ?ShouldSetDeviceCookie@ProofOfPossessionTokenProvider@@YA_NPEBG0PEAK@Z; ProofOfPossessionTokenProvider::ShouldSetDeviceCookie(ushort const *,ushort const *,ulong *)
0x18012257a  test    al, al
0x18012257c  jz      loc_1801226DB
0x180122582  test    rbx, rbx
0x180122585  jz      loc_18012269A
0x18012258b  mov     rdx, [rsi+rdi+8]
0x180122590  test    rdx, rdx
0x180122593  jz      loc_1801226DB
0x180122599  mov     rax, [rsi+rdi]
0x18012259d  mov     rcx, rbp
0x1801225a0  inc     rcx
0x1801225a3  cmp     [rax+rcx*2], r13w
0x1801225a8  jnz     short loc_1801225A0
0x1801225aa  mov     rax, rbp
0x1801225ad  inc     rax
0x1801225b0  cmp     [rdx+rax*2], r13w
0x1801225b5  jnz     short loc_1801225AD
0x1801225b7  lea     ebx, [rcx+5]
0x1801225ba  mov     [rsp+88h+var_50], r13
0x1801225bf  add     ebx, eax
0x1801225c1  mov     [rsp+88h+var_48], r13d
0x1801225c6  mov     r13d, ebx
0x1801225c9  mov     eax, 2
0x1801225ce  mul     r13
0x1801225d1  cmovb   rax, rbp
0x1801225d5  mov     rcx, rax; unsigned __int64
0x1801225d8  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1801225dd  lea     rcx, [rsp+88h+var_50]
0x1801225e2  mov     rbp, rax
0x1801225e5  call    ?Clear@?$AutoArray@PEAGV?$AutoTypedArrayFunctor@G@@@@QEAAXXZ; AutoArray<ushort *,AutoTypedArrayFunctor<ushort>>::Clear(void)
0x1801225ea  mov     [rsp+88h+var_50], rbp
0x1801225ef  mov     [rsp+88h+var_48], ebx
0x1801225f3  test    rbp, rbp
0x1801225f6  jz      loc_18012267F
0x1801225fc  mov     rcx, [rsi+rdi+8]
0x180122601  lea     r8, aSS_4; "%s: %s\r\n"
0x180122608  mov     r9, [rsi+rdi]
0x18012260c  mov     edx, r13d; unsigned __int64
0x18012260f  mov     [rsp+88h+dwReserved], rcx
0x180122614  mov     rcx, rbp; unsigned __int16 *
0x180122617  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18012261c  xor     r13d, r13d
0x18012261f  test    eax, eax
0x180122621  js      short loc_180122682
0x180122623  lea     edx, [r13+3Bh]; Ch
0x180122627  mov     rcx, rbp; Str
0x18012262a  call    cs:__imp_wcschr
0x180122631  nop     dword ptr [rax+rax+00h]
0x180122636  test    rax, rax
0x180122639  jz      short loc_180122659
0x18012263b  lea     r8, Source; "\r\n"
0x180122642  mov     rcx, rax; Destination
0x180122645  lea     edx, [r13+3]; SizeInWords
0x180122649  call    cs:__imp_wcscpy_s
0x180122650  nop     dword ptr [rax+rax+00h]
0x180122655  test    eax, eax
0x180122657  jnz     short loc_180122682
0x180122659  mov     rbx, [rsp+88h+hRequest]
0x180122661  mov     r9d, 10000000h; dwModifiers
0x180122667  mov     rcx, rbx; hRequest
0x18012266a  or      r8d, 0FFFFFFFFh; dwHeadersLength
0x18012266e  mov     rdx, rbp; lpszHeaders
0x180122671  call    cs:__imp_HttpAddRequestHeadersW
0x180122678  nop     dword ptr [rax+rax+00h]
0x18012267d  jmp     short loc_18012268A
0x18012267f  xor     r13d, r13d
0x180122682  mov     rbx, [rsp+88h+hRequest]
0x18012268a  lea     rcx, [rsp+88h+var_50]
0x18012268f  call    ?Clear@?$AutoArray@PEAGV?$AutoTypedArrayFunctor@G@@@@QEAAXXZ; AutoArray<ushort *,AutoTypedArrayFunctor<ushort>>::Clear(void)
0x180122694  or      rbp, 0FFFFFFFFFFFFFFFFh
0x180122698  jmp     short loc_1801226DB
0x18012269a  mov     ebx, [rsi+rdi+18h]
0x18012269e  call    ?IsEdgeCookiesFeatureEnabled@ProofOfPossessionTokenProvider@@YA_NXZ; ProofOfPossessionTokenProvider::IsEdgeCookiesFeatureEnabled(void)
0x1801226a3  mov     r8, [rsi+rdi+8]; lpszCookieData
0x1801226a8  mov     r9d, ebx
0x1801226ab  mov     rdx, [rsi+rdi]; lpszCookieName
0x1801226af  bts     r9d, 0Fh
0x1801226b4  test    al, al
0x1801226b6  mov     rcx, r12; lpszUrl
0x1801226b9  mov     rax, [rsi+rdi+10h]
0x1801226be  cmovz   r9d, ebx; dwFlags
0x1801226c2  mov     [rsp+88h+dwReserved], rax; dwReserved
0x1801226c7  call    cs:__imp_InternetSetCookieExW
0x1801226ce  nop     dword ptr [rax+rax+00h]
0x1801226d3  mov     rbx, [rsp+88h+hRequest]
0x1801226db  mov     rcx, [rsi+rdi]; pv
0x1801226df  call    cs:__imp_CoTaskMemFree
0x1801226e6  nop     dword ptr [rax+rax+00h]
0x1801226eb  mov     rcx, [rsi+rdi+8]; pv
0x1801226f0  call    cs:__imp_CoTaskMemFree
0x1801226f7  nop     dword ptr [rax+rax+00h]
0x1801226fc  mov     rcx, [rsi+rdi+10h]; pv
0x180122701  call    cs:__imp_CoTaskMemFree
0x180122708  nop     dword ptr [rax+rax+00h]
0x18012270d  inc     r15d
0x180122710  inc     r14
0x180122713  cmp     r15d, [rsp+88h+arg_10]
0x18012271b  jb      loc_18012254D
0x180122721  mov     rcx, rdi; pv
0x180122724  call    cs:__imp_CoTaskMemFree
0x18012272b  nop     dword ptr [rax+rax+00h]
0x180122730  mov     rbx, [rsp+88h+arg_8]
0x180122738  add     rsp, 50h
0x18012273c  pop     r15
0x18012273e  pop     r14
0x180122740  pop     r13
0x180122742  pop     r12
0x180122744  pop     rdi
0x180122745  pop     rsi
0x180122746  pop     rbp
0x180122747  retn
```
