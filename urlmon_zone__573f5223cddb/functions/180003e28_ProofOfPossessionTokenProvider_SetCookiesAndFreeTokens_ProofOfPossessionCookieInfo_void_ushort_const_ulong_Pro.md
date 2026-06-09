# ProofOfPossessionTokenProvider::SetCookiesAndFreeTokens<ProofOfPossessionCookieInfo>(void *,ushort const *,ulong,ProofOfPossessionCookieInfo *)

- ea: `0x180003e28`
- end: `0x180004037`
- name: `??$SetCookiesAndFreeTokens@UProofOfPossessionCookieInfo@@@ProofOfPossessionTokenProvider@@YAXPEAXPEBGKPEAUProofOfPossessionCookieInfo@@@Z`
- size: `527`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180002b8c`
- `0x18000367c`

## callees

- `0x180003578`
- `0x180003e28`
- `0x1800162d4`
- `0x1800ac8c8`
- `0x1800ac8d4`
- `0x180122750`
- `0x1801229ac`

## import_xrefs

- `msvcrt!wcschr` at `0x180003f7e`
- `msvcrt!wcschr` at `0x180003f7e`
- `msvcrt!wcscpy_s` at `0x180003f9d`
- `msvcrt!wcscpy_s` at `0x180003f9d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003eee`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003eff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003f10`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003f2e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003eee`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003eff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003f10`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003f2e`
- `WININET!HttpAddRequestHeadersW` at `0x180003fbf`
- `WININET!HttpAddRequestHeadersW` at `0x180003fbf`
- `WININET!InternetSetCookieExW` at `0x180004026`
- `WININET!InternetSetCookieExW` at `0x180004026`

## pseudocode

```c
void __fastcall ProofOfPossessionTokenProvider::SetCookiesAndFreeTokens<ProofOfPossessionCookieInfo>(
        void *a1,
        const WCHAR *a2,
        unsigned int a3,
        unsigned int *a4)
{
  void *v7; // rbx
  unsigned int v8; // r14d
  __int64 v9; // rbp
  __int64 v10; // rsi
  ProofOfPossessionTokenProvider *v11; // rcx
  unsigned int *v12; // r9
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // rax
  unsigned __int64 v16; // r15
  unsigned __int16 *v17; // rax
  wchar_t *v18; // rbx
  wchar_t *v19; // rax
  DWORD v20; // ebx
  bool IsEdgeCookiesFeatureEnabled; // al
  DWORD v22; // r9d
  DWORD dwSize; // [rsp+80h] [rbp+18h] BYREF

  dwSize = 0;
  v7 = a1;
  v8 = 0;
  if ( a3 )
  {
    v9 = 0;
    while ( 1 )
    {
      v10 = 8 * v9;
      if ( !ProofOfPossessionTokenProvider::ShouldSetCookie(a2, *(wchar_t **)&a4[8 * v9], &dwSize, a4)
        && !ProofOfPossessionTokenProvider::ShouldSetDeviceCookie(a2, *(wchar_t **)&a4[v10], &dwSize, v12) )
      {
        goto LABEL_12;
      }
      if ( !v7 )
        break;
      v13 = *(_QWORD *)&a4[v10 + 2];
      if ( v13 )
      {
        v14 = -1;
        do
          ++v14;
        while ( *(_WORD *)(*(_QWORD *)&a4[v10] + 2 * v14) );
        v15 = -1;
        do
          ++v15;
        while ( *(_WORD *)(v13 + 2 * v15) );
        v16 = (unsigned int)(v15 + v14 + 5);
        v17 = (unsigned __int16 *)operator new[](saturated_mul((unsigned int)v16, 2u));
        v18 = v17;
        if ( v17 )
        {
          if ( (int)StringCchPrintfW(v17, v16, L"%s: %s\r\n", *(_QWORD *)&a4[v10], *(_QWORD *)&a4[v10 + 2]) >= 0 )
          {
            v19 = wcschr(v18, 0x3Bu);
            if ( !v19 || !wcscpy_s(v19, 3u, L"\r\n") )
              HttpAddRequestHeadersW(a1, v18, 0xFFFFFFFF, 0x10000000u);
          }
          operator delete[](v18);
        }
LABEL_11:
        v7 = a1;
      }
LABEL_12:
      CoTaskMemFree(*(LPVOID *)&a4[v10]);
      CoTaskMemFree(*(LPVOID *)&a4[v10 + 2]);
      CoTaskMemFree(*(LPVOID *)&a4[v10 + 6]);
      ++v8;
      ++v9;
      if ( v8 >= a3 )
        goto LABEL_13;
    }
    v20 = a4[v10 + 4];
    IsEdgeCookiesFeatureEnabled = ProofOfPossessionTokenProvider::IsEdgeCookiesFeatureEnabled(v11);
    v22 = v20 | 0x8000;
    if ( !IsEdgeCookiesFeatureEnabled )
      v22 = v20;
    InternetSetCookieExW(a2, *(LPCWSTR *)&a4[v10], *(LPCWSTR *)&a4[v10 + 2], v22, *(_QWORD *)&a4[v10 + 6]);
    goto LABEL_11;
  }
LABEL_13:
  CoTaskMemFree(a4);
}

```

## disassembly

```asm
0x180003e28  mov     rax, rsp
0x180003e2b  mov     [rax+10h], rbx
0x180003e2f  mov     [rax+8], rcx
0x180003e33  push    rbp
0x180003e34  push    rsi
0x180003e35  push    rdi
0x180003e36  push    r12
0x180003e38  push    r13
0x180003e3a  push    r14
0x180003e3c  push    r15
0x180003e3e  sub     rsp, 30h
0x180003e42  xor     r15d, r15d
0x180003e45  mov     rdi, r9
0x180003e48  mov     [rax+18h], r15d
0x180003e4c  mov     r13d, r8d
0x180003e4f  mov     r12, rdx
0x180003e52  mov     rbx, rcx
0x180003e55  mov     r14d, r15d
0x180003e58  test    r8d, r8d
0x180003e5b  jz      loc_180003F2B
0x180003e61  mov     ebp, r15d
0x180003e64  mov     rsi, rbp
0x180003e67  lea     r8, [rsp+68h+dwSize]; lpdwSize
0x180003e6f  shl     rsi, 5
0x180003e73  mov     rcx, r12; lpszUrl
0x180003e76  mov     rdx, [rsi+rdi]; String1
0x180003e7a  call    ?ShouldSetCookie@ProofOfPossessionTokenProvider@@YA_NPEBG0PEAK@Z; ProofOfPossessionTokenProvider::ShouldSetCookie(ushort const *,ushort const *,ulong *)
0x180003e7f  test    al, al
0x180003e81  jz      loc_180003FD8
0x180003e87  test    rbx, rbx
0x180003e8a  jz      loc_180003FF9
0x180003e90  mov     rdx, [rsi+rdi+8]
0x180003e95  test    rdx, rdx
0x180003e98  jz      short loc_180003EEA
0x180003e9a  mov     rax, [rsi+rdi]
0x180003e9e  or      r8, 0FFFFFFFFFFFFFFFFh
0x180003ea2  mov     rcx, r8
0x180003ea5  inc     rcx
0x180003ea8  cmp     [rax+rcx*2], r15w
0x180003ead  jnz     short loc_180003EA5
0x180003eaf  mov     rax, r8
0x180003eb2  inc     rax
0x180003eb5  cmp     [rdx+rax*2], r15w
0x180003eba  jnz     short loc_180003EB2
0x180003ebc  lea     r15, [rcx+5]
0x180003ec0  add     r15, rax
0x180003ec3  mov     eax, 2
0x180003ec8  mov     r15d, r15d
0x180003ecb  mul     r15
0x180003ece  cmovb   rax, r8
0x180003ed2  mov     rcx, rax; unsigned __int64
0x180003ed5  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180003eda  mov     rbx, rax
0x180003edd  test    rax, rax
0x180003ee0  jnz     short loc_180003F50
0x180003ee2  xor     r15d, r15d
0x180003ee5  mov     rbx, [rsp+68h+hRequest]
0x180003eea  mov     rcx, [rsi+rdi]; pv
0x180003eee  call    cs:__imp_CoTaskMemFree
0x180003ef5  nop     dword ptr [rax+rax+00h]
0x180003efa  mov     rcx, [rsi+rdi+8]; pv
0x180003eff  call    cs:__imp_CoTaskMemFree
0x180003f06  nop     dword ptr [rax+rax+00h]
0x180003f0b  mov     rcx, [rsi+rdi+18h]; pv
0x180003f10  call    cs:__imp_CoTaskMemFree
0x180003f17  nop     dword ptr [rax+rax+00h]
0x180003f1c  inc     r14d
0x180003f1f  inc     rbp
0x180003f22  cmp     r14d, r13d
0x180003f25  jb      loc_180003E64
0x180003f2b  mov     rcx, rdi; pv
0x180003f2e  call    cs:__imp_CoTaskMemFree
0x180003f35  nop     dword ptr [rax+rax+00h]
0x180003f3a  mov     rbx, [rsp+68h+arg_8]
0x180003f3f  add     rsp, 30h
0x180003f43  pop     r15
0x180003f45  pop     r14
0x180003f47  pop     r13
0x180003f49  pop     r12
0x180003f4b  pop     rdi
0x180003f4c  pop     rsi
0x180003f4d  pop     rbp
0x180003f4e  retn
0x180003f50  mov     rcx, [rsi+rdi+8]
0x180003f55  lea     r8, aSS_4; "%s: %s\r\n"
0x180003f5c  mov     r9, [rsi+rdi]
0x180003f60  mov     rdx, r15; unsigned __int64
0x180003f63  mov     [rsp+68h+dwReserved], rcx
0x180003f68  mov     rcx, rbx; unsigned __int16 *
0x180003f6b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180003f70  xor     r15d, r15d
0x180003f73  test    eax, eax
0x180003f75  js      short loc_180003FCB
0x180003f77  lea     edx, [r15+3Bh]; Ch
0x180003f7b  mov     rcx, rbx; Str
0x180003f7e  call    cs:__imp_wcschr
0x180003f85  nop     dword ptr [rax+rax+00h]
0x180003f8a  test    rax, rax
0x180003f8d  jz      short loc_180003FAD
0x180003f8f  lea     r8, Source; "\r\n"
0x180003f96  mov     rcx, rax; Destination
0x180003f99  lea     edx, [r15+3]; SizeInWords
0x180003f9d  call    cs:__imp_wcscpy_s
0x180003fa4  nop     dword ptr [rax+rax+00h]
0x180003fa9  test    eax, eax
0x180003fab  jnz     short loc_180003FCB
0x180003fad  mov     rcx, [rsp+68h+hRequest]; hRequest
0x180003fb2  mov     r9d, 10000000h; dwModifiers
0x180003fb8  or      r8d, 0FFFFFFFFh; dwHeadersLength
0x180003fbc  mov     rdx, rbx; lpszHeaders
0x180003fbf  call    cs:__imp_HttpAddRequestHeadersW
0x180003fc6  nop     dword ptr [rax+rax+00h]
0x180003fcb  mov     rcx, rbx; void *
0x180003fce  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x180003fd3  jmp     loc_180003EE5
0x180003fd8  mov     rdx, [rsi+rdi]; String1
0x180003fdc  lea     r8, [rsp+68h+dwSize]; lpdwSize
0x180003fe4  mov     rcx, r12; lpszUrl
0x180003fe7  call    ?ShouldSetDeviceCookie@ProofOfPossessionTokenProvider@@YA_NPEBG0PEAK@Z; ProofOfPossessionTokenProvider::ShouldSetDeviceCookie(ushort const *,ushort const *,ulong *)
0x180003fec  test    al, al
0x180003fee  jz      loc_180003EEA
0x180003ff4  jmp     loc_180003E87
0x180003ff9  mov     ebx, [rsi+rdi+10h]
0x180003ffd  call    ?IsEdgeCookiesFeatureEnabled@ProofOfPossessionTokenProvider@@YA_NXZ; ProofOfPossessionTokenProvider::IsEdgeCookiesFeatureEnabled(void)
0x180004002  mov     r8, [rsi+rdi+8]; lpszCookieData
0x180004007  mov     r9d, ebx
0x18000400a  mov     rdx, [rsi+rdi]; lpszCookieName
0x18000400e  bts     r9d, 0Fh
0x180004013  test    al, al
0x180004015  mov     rcx, r12; lpszUrl
0x180004018  mov     rax, [rsi+rdi+18h]
0x18000401d  cmovz   r9d, ebx; dwFlags
0x180004021  mov     [rsp+68h+dwReserved], rax; dwReserved
0x180004026  call    cs:__imp_InternetSetCookieExW
0x18000402d  nop     dword ptr [rax+rax+00h]
0x180004032  jmp     loc_180003EE5
```
