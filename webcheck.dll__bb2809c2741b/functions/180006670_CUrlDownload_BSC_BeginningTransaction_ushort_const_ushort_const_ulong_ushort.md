# CUrlDownload_BSC::BeginningTransaction(ushort const *,ushort const *,ulong,ushort * *)

- ea: `0x180006670`
- end: `0x1800067ef`
- name: `?BeginningTransaction@CUrlDownload_BSC@@UEAAJPEBG0KPEAPEAG@Z`
- size: `383`
- prototype: `__int64 __fastcall(CUrlDownload_BSC *__hidden this, const unsigned __int16 *, const unsigned __int16 *, unsigned int, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x180003950`
- `0x180006670`
- `0x18000703c`
- `0x180008648`

## import_xrefs

- `SHLWAPI!__imp_GetAcceptLanguagesW` at `0x1800066d7`
- `SHLWAPI!__imp_GetAcceptLanguagesW` at `0x1800066d7`
- `ole32!CoTaskMemAlloc` at `0x180006748`
- `ole32!CoTaskMemAlloc` at `0x180006748`

## string_xrefs

- `0x18000675e`: `User-Agent: `

## pseudocode

```c
__int64 __fastcall CUrlDownload_BSC::BeginningTransaction(
        CUrlDownload_BSC *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        __int64 a4,
        unsigned __int16 **a5)
{
  CUrlDownload *v6; // rcx
  int v7; // ebp
  int v8; // r14d
  const unsigned __int16 *UserAgent; // r15
  __int64 v10; // rdi
  int v11; // ecx
  const unsigned __int16 *v12; // rbx
  __int64 v13; // rax
  __int64 v14; // rcx
  unsigned __int64 v15; // rsi
  unsigned __int16 *v16; // rax
  unsigned __int16 *v17; // rdi
  DWORD pcchLanguages; // [rsp+50h] [rbp+8h] BYREF

  v6 = (CUrlDownload *)*((_QWORD *)this + 9);
  v7 = 0;
  v8 = 0;
  if ( v6 )
    UserAgent = CUrlDownload::GetUserAgent(v6);
  else
    UserAgent = 0;
  v10 = *((_QWORD *)this + 9);
  if ( v10 )
  {
    v11 = *(_DWORD *)(v10 + 708);
    v12 = (const unsigned __int16 *)(v10 + 196);
    if ( !v11 )
    {
      pcchLanguages = 256;
      if ( GetAcceptLanguagesW((LPWSTR)(v10 + 196), &pcchLanguages) < 0 )
      {
        v11 = 2;
        *(_DWORD *)(v10 + 708) = 2;
      }
      else
      {
        *(_DWORD *)(v10 + 708) = 1;
        v11 = 1;
      }
    }
    if ( v11 != 1 )
      v12 = 0;
  }
  else
  {
    v12 = 0;
  }
  v13 = -1;
  if ( UserAgent )
  {
    v14 = -1;
    do
      ++v14;
    while ( UserAgent[v14] );
    v7 = v14 + 14;
  }
  if ( v12 )
  {
    do
      ++v13;
    while ( v12[v13] );
    v8 = v13 + 19;
  }
  if ( !v7 && !v8 )
    return 2147942414LL;
  v15 = v8 + v7 + 1LL;
  v16 = (unsigned __int16 *)CoTaskMemAlloc(2 * v15);
  v17 = v16;
  if ( !v16 )
    return 2147942414LL;
  *v16 = 0;
  if ( v7 )
  {
    StringCchCopyW(v16, v15, L"User-Agent: ");
    StringCchCatW(v17, v15, UserAgent);
    StringCchCatW(v17, v15, L"\r\n");
  }
  if ( v8 )
  {
    StringCchCatW(v17, v15, L"Accept-Language: ");
    StringCchCatW(v17, v15, v12);
    StringCchCatW(v17, v15, L"\r\n");
  }
  *a5 = v17;
  return 0;
}

```

## disassembly

```asm
0x180006670  mov     [rsp+arg_8], rbx
0x180006675  mov     [rsp+arg_10], rbp
0x18000667a  push    rsi
0x18000667b  push    rdi
0x18000667c  push    r12
0x18000667e  push    r14
0x180006680  push    r15
0x180006682  sub     rsp, 20h
0x180006686  xor     r12d, r12d
0x180006689  mov     rdi, rcx
0x18000668c  mov     rcx, [rcx+48h]; this
0x180006690  mov     ebp, r12d
0x180006693  mov     r14d, r12d
0x180006696  test    rcx, rcx
0x180006699  jz      short loc_1800066A5
0x18000669b  call    ?GetUserAgent@CUrlDownload@@QEAAPEBGXZ; CUrlDownload::GetUserAgent(void)
0x1800066a0  mov     r15, rax
0x1800066a3  jmp     short loc_1800066A8
0x1800066a5  mov     r15, r12
0x1800066a8  mov     rdi, [rdi+48h]
0x1800066ac  test    rdi, rdi
0x1800066af  jz      short loc_1800066FE
0x1800066b1  mov     ecx, [rdi+2C4h]
0x1800066b7  lea     rbx, [rdi+0C4h]
0x1800066be  mov     esi, 1
0x1800066c3  test    ecx, ecx
0x1800066c5  jnz     short loc_1800066F6
0x1800066c7  lea     rdx, [rsp+48h+pcchLanguages]; pcchLanguages
0x1800066cc  mov     [rsp+48h+pcchLanguages], 100h
0x1800066d4  mov     rcx, rbx; pszLanguages
0x1800066d7  call    cs:__imp_GetAcceptLanguagesW
0x1800066dd  test    eax, eax
0x1800066df  js      short loc_1800066EB
0x1800066e1  mov     [rdi+2C4h], esi
0x1800066e7  mov     ecx, esi
0x1800066e9  jmp     short loc_1800066F6
0x1800066eb  mov     ecx, 2
0x1800066f0  mov     [rdi+2C4h], ecx
0x1800066f6  cmp     ecx, esi
0x1800066f8  cmovnz  rbx, r12
0x1800066fc  jmp     short loc_180006701
0x1800066fe  mov     rbx, r12
0x180006701  or      rax, 0FFFFFFFFFFFFFFFFh
0x180006705  test    r15, r15
0x180006708  jz      short loc_18000671A
0x18000670a  mov     rcx, rax
0x18000670d  inc     rcx
0x180006710  cmp     [r15+rcx*2], r12w
0x180006715  jnz     short loc_18000670D
0x180006717  lea     ebp, [rcx+0Eh]
0x18000671a  test    rbx, rbx
0x18000671d  jz      short loc_18000672D
0x18000671f  inc     rax
0x180006722  cmp     [rbx+rax*2], r12w
0x180006727  jnz     short loc_18000671F
0x180006729  lea     r14d, [rax+13h]
0x18000672d  test    ebp, ebp
0x18000672f  jnz     short loc_18000673A
0x180006731  test    r14d, r14d
0x180006734  jz      loc_1800067D3
0x18000673a  lea     eax, [r14+rbp]
0x18000673e  movsxd  rsi, eax
0x180006741  inc     rsi
0x180006744  lea     rcx, [rsi+rsi]; cb
0x180006748  call    cs:__imp_CoTaskMemAlloc
0x18000674e  mov     rdi, rax
0x180006751  test    rax, rax
0x180006754  jz      short loc_1800067D3
0x180006756  mov     [rax], r12w
0x18000675a  test    ebp, ebp
0x18000675c  jz      short loc_180006790
0x18000675e  lea     r8, aUserAgent; "User-Agent: "
0x180006765  mov     rdx, rsi; unsigned __int64
0x180006768  mov     rcx, rax; unsigned __int16 *
0x18000676b  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180006770  mov     r8, r15; unsigned __int16 *
0x180006773  mov     rdx, rsi; unsigned __int64
0x180006776  mov     rcx, rdi; unsigned __int16 *
0x180006779  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000677e  lea     r8, asc_18002D9D8; "\r\n"
0x180006785  mov     rdx, rsi; unsigned __int64
0x180006788  mov     rcx, rdi; unsigned __int16 *
0x18000678b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180006790  test    r14d, r14d
0x180006793  jz      short loc_1800067C7
0x180006795  lea     r8, aAcceptLanguage; "Accept-Language: "
0x18000679c  mov     rdx, rsi; unsigned __int64
0x18000679f  mov     rcx, rdi; unsigned __int16 *
0x1800067a2  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800067a7  mov     r8, rbx; unsigned __int16 *
0x1800067aa  mov     rdx, rsi; unsigned __int64
0x1800067ad  mov     rcx, rdi; unsigned __int16 *
0x1800067b0  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800067b5  lea     r8, asc_18002D9D8; "\r\n"
0x1800067bc  mov     rdx, rsi; unsigned __int64
0x1800067bf  mov     rcx, rdi; unsigned __int16 *
0x1800067c2  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800067c7  mov     rax, [rsp+48h+arg_20]
0x1800067cc  mov     [rax], rdi
0x1800067cf  xor     eax, eax
0x1800067d1  jmp     short loc_1800067D8
0x1800067d3  mov     eax, 8007000Eh
0x1800067d8  mov     rbx, [rsp+48h+arg_8]
0x1800067dd  mov     rbp, [rsp+48h+arg_10]
0x1800067e2  add     rsp, 20h
0x1800067e6  pop     r15
0x1800067e8  pop     r14
0x1800067ea  pop     r12
0x1800067ec  pop     rdi
0x1800067ed  pop     rsi
0x1800067ee  retn
```
