# enum_connections

- ea: `0x180009354`
- end: `0x18000975d`
- name: `enum_connections`
- size: `1033`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180007f90`
- `0x180008080`

## callees

- `0x1800060e4`
- `0x180006124`
- `0x180009354`
- `0x180010250`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180009522`
- `OLEAUT32!__imp_SysAllocString` at `0x18000959f`
- `OLEAUT32!__imp_SysAllocString` at `0x1800095fe`
- `OLEAUT32!__imp_SysAllocString` at `0x180009522`
- `OLEAUT32!__imp_SysAllocString` at `0x18000959f`
- `OLEAUT32!__imp_SysAllocString` at `0x1800095fe`
- `OLEAUT32!__imp_SysFreeString` at `0x18000966e`
- `OLEAUT32!__imp_SysFreeString` at `0x180009677`
- `OLEAUT32!__imp_SysFreeString` at `0x1800096ec`
- `OLEAUT32!__imp_SysFreeString` at `0x1800096f5`
- `OLEAUT32!__imp_SysFreeString` at `0x18000966e`
- `OLEAUT32!__imp_SysFreeString` at `0x180009677`
- `OLEAUT32!__imp_SysFreeString` at `0x1800096ec`
- `OLEAUT32!__imp_SysFreeString` at `0x1800096f5`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180009427`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180009427`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x180009636`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x180009657`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x180009636`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x180009657`
- `OLEAUT32!__imp_SafeArrayRedim` at `0x1800094e8`
- `OLEAUT32!__imp_SafeArrayRedim` at `0x1800096db`
- `OLEAUT32!__imp_SafeArrayRedim` at `0x1800094e8`
- `OLEAUT32!__imp_SafeArrayRedim` at `0x1800096db`
- `KERNEL32!GetLastError` at `0x180009689`
- `KERNEL32!GetLastError` at `0x1800096a0`
- `KERNEL32!GetLastError` at `0x180009689`
- `KERNEL32!GetLastError` at `0x1800096a0`
- `KERNEL32!MultiByteToWideChar` at `0x18000958d`
- `KERNEL32!MultiByteToWideChar` at `0x1800095e9`
- `KERNEL32!MultiByteToWideChar` at `0x18000958d`
- `KERNEL32!MultiByteToWideChar` at `0x1800095e9`
- `MPR!WNetEnumResourceW` at `0x180009489`
- `MPR!WNetEnumResourceW` at `0x180009489`
- `MPR!WNetOpenEnumA` at `0x1800093ee`
- `MPR!WNetOpenEnumA` at `0x1800093ee`
- `MPR!WNetCloseEnum` at `0x180009712`
- `MPR!WNetCloseEnum` at `0x180009712`
- `MPR!WNetEnumResourceA` at `0x180009491`
- `MPR!WNetEnumResourceA` at `0x180009491`

## pseudocode

```c
__int64 __fastcall enum_connections(__int64 a1, DWORD a2, SAFEARRAY **a3)
{
  void *v5; // r14
  OLECHAR *v6; // rsi
  OLECHAR *v7; // rdi
  signed int LastError; // eax
  int v9; // ebx
  bool v10; // cc
  SAFEARRAY *v11; // rax
  DWORD v12; // edi
  signed int v13; // eax
  SAFEARRAY *v14; // rcx
  const CHAR *v15; // r8
  __int64 v16; // rax
  WCHAR *v17; // rcx
  __int64 v18; // rax
  __int64 v19; // rax
  const CHAR *v20; // r8
  __int64 v21; // rax
  SAFEARRAY *v22; // rcx
  SAFEARRAY *v23; // rcx
  signed int v24; // eax
  SAFEARRAY *v25; // rcx
  signed int v26; // eax
  LONG rgIndices; // [rsp+30h] [rbp-D0h] BYREF
  DWORD BufferSize; // [rsp+34h] [rbp-CCh] BYREF
  SAFEARRAYBOUND rgsabound; // [rsp+38h] [rbp-C8h] BYREF
  DWORD cCount; // [rsp+40h] [rbp-C0h] BYREF
  HANDLE hEnum; // [rsp+48h] [rbp-B8h] BYREF
  __int128 pv; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v33; // [rsp+60h] [rbp-A0h]
  __int128 v34; // [rsp+68h] [rbp-98h] BYREF
  __int64 v35; // [rsp+78h] [rbp-88h]
  WCHAR WideCharStr[264]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR psz[264]; // [rsp+290h] [rbp+190h] BYREF

  if ( !a3 )
    return 2147500035LL;
  rgsabound = 0;
  v33 = 0;
  v35 = 0;
  rgIndices = 0;
  BufferSize = 0;
  cCount = 0;
  hEnum = 0;
  pv = 0;
  v5 = 0;
  v6 = 0;
  v34 = 0;
  v7 = 0;
  LastError = WNetOpenEnumA(1u, a2, 0, 0, &hEnum);
  v9 = LastError;
  v10 = LastError <= 0;
  if ( LastError )
  {
LABEL_4:
    if ( !v10 )
      v9 = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_55;
  }
  rgsabound = (SAFEARRAYBOUND)100LL;
  v9 = 0;
  v11 = SafeArrayCreate(0xCu, 1u, &rgsabound);
  *a3 = v11;
  if ( !v11 )
    goto LABEL_55;
  rgIndices = 0;
  BufferSize = 0x4000;
  v5 = operator new(0x4000u);
  if ( !v5 )
  {
LABEL_8:
    v9 = -2147024882;
    goto LABEL_55;
  }
  while ( 1 )
  {
    while ( 1 )
    {
      v12 = BufferSize;
      cCount = 1;
      v13 = Global::g_fWindowsNT
          ? WNetEnumResourceW(hEnum, &cCount, v5, &BufferSize)
          : WNetEnumResourceA(hEnum, &cCount, v5, &BufferSize);
      v9 = v13;
      if ( v12 >= BufferSize )
        break;
      operator delete(v5);
      v5 = operator new(BufferSize);
      if ( !v5 )
      {
        v9 = -2147024882;
LABEL_53:
        v6 = 0;
        goto LABEL_54;
      }
    }
    if ( v13 )
    {
      if ( v13 == 259 )
      {
        v25 = *a3;
        rgsabound.cElements = rgIndices;
        rgsabound.lLbound = 0;
        v9 = SafeArrayRedim(v25, &rgsabound);
      }
      else if ( v13 > 0 )
      {
        v9 = (unsigned __int16)v13 | 0x80070000;
      }
      goto LABEL_53;
    }
    if ( rgIndices >= (int)rgsabound.cElements )
    {
      v14 = *a3;
      rgsabound.lLbound = 0;
      rgsabound.cElements += 100;
      v9 = SafeArrayRedim(v14, &rgsabound);
      if ( v9 < 0 )
        goto LABEL_53;
    }
    v6 = 0;
    v15 = (const CHAR *)*((_QWORD *)v5 + 2);
    if ( !Global::g_fWindowsNT )
      break;
    if ( v15 )
    {
      v16 = -1;
      do
        ++v16;
      while ( *(_WORD *)&v15[2 * v16] );
      if ( v16 )
      {
        v6 = SysAllocString(*((const OLECHAR **)v5 + 2));
        if ( !v6 )
        {
LABEL_45:
          v9 = -2147024882;
          goto LABEL_54;
        }
      }
    }
    v17 = (WCHAR *)*((_QWORD *)v5 + 3);
    v7 = 0;
    if ( v17 )
    {
      v18 = -1;
      do
        ++v18;
      while ( v17[v18] );
      if ( v18 )
        goto LABEL_41;
    }
LABEL_42:
    v22 = *a3;
    *((_QWORD *)&pv + 1) = v6;
    LOWORD(pv) = 8;
    LOWORD(v34) = 8;
    *((_QWORD *)&v34 + 1) = v7;
    v9 = SafeArrayPutElement(v22, &rgIndices, &pv);
    if ( v9 < 0 )
      goto LABEL_55;
    v23 = *a3;
    ++rgIndices;
    v9 = SafeArrayPutElement(v23, &rgIndices, &v34);
    if ( v9 < 0 )
      goto LABEL_55;
    ++rgIndices;
    SysFreeString(v6);
    SysFreeString(v7);
  }
  if ( !v15 )
    goto LABEL_35;
  v19 = -1;
  do
    ++v19;
  while ( v15[v19] );
  if ( !v19 )
  {
LABEL_35:
    v20 = (const CHAR *)*((_QWORD *)v5 + 3);
    v7 = 0;
    if ( !v20 )
      goto LABEL_42;
    v21 = -1;
    do
      ++v21;
    while ( v20[v21] );
    if ( !v21 )
      goto LABEL_42;
    if ( !MultiByteToWideChar(0, 0, v20, -1, psz, 260) )
    {
      LastError = GetLastError();
      v9 = LastError;
      v10 = LastError <= 0;
      goto LABEL_4;
    }
    v17 = psz;
LABEL_41:
    v7 = SysAllocString(v17);
    if ( !v7 )
      goto LABEL_8;
    goto LABEL_42;
  }
  if ( MultiByteToWideChar(0, 0, v15, -1, WideCharStr, 260) )
  {
    v6 = SysAllocString(WideCharStr);
    if ( !v6 )
      goto LABEL_45;
    goto LABEL_35;
  }
  v24 = GetLastError();
  v9 = v24;
  if ( v24 > 0 )
    v9 = (unsigned __int16)v24 | 0x80070000;
LABEL_54:
  v7 = 0;
LABEL_55:
  SysFreeString(v6);
  SysFreeString(v7);
  if ( v5 )
    operator delete(v5);
  if ( hEnum )
  {
    v26 = WNetCloseEnum(hEnum);
    if ( v26 )
    {
      if ( v9 >= 0 )
      {
        if ( v26 > 0 )
          return (unsigned __int16)v26 | 0x80070000;
        else
          return (unsigned int)v26;
      }
    }
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180009354  mov     [rsp-8+arg_0], rbx
0x180009359  push    rbp
0x18000935a  push    rsi
0x18000935b  push    rdi
0x18000935c  push    r12
0x18000935e  push    r13
0x180009360  push    r14
0x180009362  push    r15
0x180009364  lea     rbp, [rsp-3B0h]
0x18000936c  sub     rsp, 4B0h
0x180009373  mov     rax, cs:__security_cookie
0x18000937a  xor     rax, rsp
0x18000937d  mov     [rbp+3E0h+var_40], rax
0x180009384  xor     r12d, r12d
0x180009387  mov     r15, r8
0x18000938a  test    r8, r8
0x18000938d  jnz     short loc_180009399
0x18000938f  mov     eax, 80004003h
0x180009394  jmp     loc_180009733
0x180009399  xor     eax, eax
0x18000939b  mov     qword ptr [rsp+4E0h+rgsabound.cElements], r12
0x1800093a0  xor     r9d, r9d; lpNetResource
0x1800093a3  mov     [rsp+4E0h+var_480], rax
0x1800093a8  mov     [rsp+4E0h+var_468], rax
0x1800093ad  xorps   xmm0, xmm0
0x1800093b0  xorps   xmm1, xmm1
0x1800093b3  mov     [rsp+4E0h+rgIndices], r12d
0x1800093b8  lea     rax, [rsp+4E0h+hEnum]
0x1800093bd  mov     [rsp+4E0h+BufferSize], r12d
0x1800093c2  lea     r13d, [r9+1]
0x1800093c6  mov     [rsp+4E0h+cCount], r12d
0x1800093cb  mov     ecx, r13d; dwScope
0x1800093ce  mov     [rsp+4E0h+hEnum], r12
0x1800093d3  xor     r8d, r8d; dwUsage
0x1800093d6  mov     [rsp+4E0h+lphEnum], rax; lphEnum
0x1800093db  movups  [rsp+4E0h+pv], xmm0
0x1800093e0  mov     r14, r12
0x1800093e3  mov     rsi, r12
0x1800093e6  movups  [rsp+4E0h+var_478], xmm1
0x1800093eb  mov     rdi, r12
0x1800093ee  call    cs:__imp_WNetOpenEnumA
0x1800093f4  mov     ebx, eax
0x1800093f6  test    eax, eax
0x1800093f8  jz      short loc_18000940E
0x1800093fa  jle     loc_1800096E9
0x180009400  movzx   ebx, ax
0x180009403  or      ebx, 80070000h
0x180009409  jmp     loc_1800096E9
0x18000940e  mov     ecx, 0Ch; vt
0x180009413  mov     qword ptr [rsp+4E0h+rgsabound.cElements], 64h ; 'd'
0x18000941c  lea     r8, [rsp+4E0h+rgsabound]; rgsabound
0x180009421  mov     edx, r13d; cDims
0x180009424  mov     ebx, r12d
0x180009427  call    cs:__imp_SafeArrayCreate
0x18000942d  mov     [r15], rax
0x180009430  test    rax, rax
0x180009433  jz      loc_1800096E9
0x180009439  mov     ecx, 4000h; Size
0x18000943e  mov     [rsp+4E0h+rgIndices], r12d
0x180009443  mov     [rsp+4E0h+BufferSize], ecx
0x180009447  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000944c  mov     r14, rax
0x18000944f  test    rax, rax
0x180009452  jnz     short loc_18000945E
0x180009454  mov     ebx, 8007000Eh
0x180009459  jmp     loc_1800096E9
0x18000945e  or      r13, 0FFFFFFFFFFFFFFFFh
0x180009462  cmp     cs:?g_fWindowsNT@Global@@2_NA, r12b; bool Global::g_fWindowsNT
0x180009469  lea     r9, [rsp+4E0h+BufferSize]; lpBufferSize
0x18000946e  mov     edi, [rsp+4E0h+BufferSize]
0x180009472  lea     rdx, [rsp+4E0h+cCount]; lpcCount
0x180009477  mov     rcx, [rsp+4E0h+hEnum]; hEnum
0x18000947c  mov     r8, r14; lpBuffer
0x18000947f  mov     [rsp+4E0h+cCount], 1
0x180009487  jz      short loc_180009491
0x180009489  call    cs:__imp_WNetEnumResourceW
0x18000948f  jmp     short loc_180009497
0x180009491  call    cs:__imp_WNetEnumResourceA
0x180009497  mov     ebx, eax
0x180009499  cmp     edi, [rsp+4E0h+BufferSize]
0x18000949d  jnb     short loc_1800094C2
0x18000949f  mov     rcx, r14; Block
0x1800094a2  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800094a7  mov     ecx, [rsp+4E0h+BufferSize]; Size
0x1800094ab  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800094b0  mov     r14, rax
0x1800094b3  test    rax, rax
0x1800094b6  jnz     short loc_180009462
0x1800094b8  mov     ebx, 8007000Eh
0x1800094bd  jmp     loc_1800096E3
0x1800094c2  test    ebx, ebx
0x1800094c4  jnz     loc_1800096AF
0x1800094ca  mov     eax, [rsp+4E0h+rgsabound.cElements]
0x1800094ce  cmp     [rsp+4E0h+rgIndices], eax
0x1800094d2  jl      short loc_1800094F8
0x1800094d4  mov     rcx, [r15]; psa
0x1800094d7  lea     rdx, [rsp+4E0h+rgsabound]; psaboundNew
0x1800094dc  add     eax, 64h ; 'd'
0x1800094df  mov     [rsp+4E0h+rgsabound.lLbound], r12d
0x1800094e4  mov     [rsp+4E0h+rgsabound.cElements], eax
0x1800094e8  call    cs:__imp_SafeArrayRedim
0x1800094ee  mov     ebx, eax
0x1800094f0  test    eax, eax
0x1800094f2  js      loc_1800096E3
0x1800094f8  cmp     cs:?g_fWindowsNT@Global@@2_NA, r12b; bool Global::g_fWindowsNT
0x1800094ff  mov     rsi, r12
0x180009502  mov     r8, [r14+10h]; lpMultiByteStr
0x180009506  jz      short loc_18000955F
0x180009508  test    r8, r8
0x18000950b  jz      short loc_180009534
0x18000950d  mov     rax, r13
0x180009510  inc     rax
0x180009513  cmp     [r8+rax*2], r12w
0x180009518  jnz     short loc_180009510
0x18000951a  test    rax, rax
0x18000951d  jz      short loc_180009534
0x18000951f  mov     rcx, r8; psz
0x180009522  call    cs:__imp_SysAllocString
0x180009528  mov     rsi, rax
0x18000952b  test    rax, rax
0x18000952e  jz      loc_180009682
0x180009534  mov     rcx, [r14+18h]
0x180009538  mov     rdi, r12
0x18000953b  test    rcx, rcx
0x18000953e  jz      loc_180009610
0x180009544  mov     rax, r13
0x180009547  inc     rax
0x18000954a  cmp     [rcx+rax*2], r12w
0x18000954f  jnz     short loc_180009547
0x180009551  test    rax, rax
0x180009554  jz      loc_180009610
0x18000955a  jmp     loc_1800095FE
0x18000955f  test    r8, r8
0x180009562  jz      short loc_1800095B1
0x180009564  mov     rax, r13
0x180009567  inc     rax
0x18000956a  cmp     [r8+rax], r12b
0x18000956e  jnz     short loc_180009567
0x180009570  test    rax, rax
0x180009573  jz      short loc_1800095B1
0x180009575  lea     rax, [rbp+3E0h+WideCharStr]
0x180009579  mov     [rsp+4E0h+cchWideChar], 104h; cchWideChar
0x180009581  mov     r9d, r13d; cbMultiByte
0x180009584  mov     [rsp+4E0h+lphEnum], rax; lpWideCharStr
0x180009589  xor     edx, edx; dwFlags
0x18000958b  xor     ecx, ecx; CodePage
0x18000958d  call    cs:__imp_MultiByteToWideChar
0x180009593  test    eax, eax
0x180009595  jz      loc_180009689
0x18000959b  lea     rcx, [rbp+3E0h+WideCharStr]; psz
0x18000959f  call    cs:__imp_SysAllocString
0x1800095a5  mov     rsi, rax
0x1800095a8  test    rax, rax
0x1800095ab  jz      loc_180009682
0x1800095b1  mov     r8, [r14+18h]; lpMultiByteStr
0x1800095b5  mov     rdi, r12
0x1800095b8  test    r8, r8
0x1800095bb  jz      short loc_180009610
0x1800095bd  mov     rax, r13
0x1800095c0  inc     rax
0x1800095c3  cmp     [r8+rax], r12b
0x1800095c7  jnz     short loc_1800095C0
0x1800095c9  test    rax, rax
0x1800095cc  jz      short loc_180009610
0x1800095ce  lea     rax, [rbp+3E0h+psz]
0x1800095d5  mov     [rsp+4E0h+cchWideChar], 104h; cchWideChar
0x1800095dd  mov     r9d, r13d; cbMultiByte
0x1800095e0  mov     [rsp+4E0h+lphEnum], rax; lpWideCharStr
0x1800095e5  xor     edx, edx; dwFlags
0x1800095e7  xor     ecx, ecx; CodePage
0x1800095e9  call    cs:__imp_MultiByteToWideChar
0x1800095ef  test    eax, eax
0x1800095f1  jz      loc_1800096A0
0x1800095f7  lea     rcx, [rbp+3E0h+psz]; psz
0x1800095fe  call    cs:__imp_SysAllocString
0x180009604  mov     rdi, rax
0x180009607  test    rax, rax
0x18000960a  jz      loc_180009454
0x180009610  mov     rcx, [r15]; psa
0x180009613  lea     r8, [rsp+4E0h+pv]; pv
0x180009618  mov     eax, 8
0x18000961d  mov     qword ptr [rsp+4E0h+pv+8], rsi
0x180009622  lea     rdx, [rsp+4E0h+rgIndices]; rgIndices
0x180009627  mov     word ptr [rsp+4E0h+pv], ax
0x18000962c  mov     word ptr [rsp+4E0h+var_478], ax
0x180009631  mov     qword ptr [rsp+4E0h+var_478+8], rdi
0x180009636  call    cs:__imp_SafeArrayPutElement
0x18000963c  mov     ebx, eax
0x18000963e  test    eax, eax
0x180009640  js      loc_1800096E9
0x180009646  mov     rcx, [r15]; psa
0x180009649  lea     r8, [rsp+4E0h+var_478]; pv
0x18000964e  inc     [rsp+4E0h+rgIndices]
0x180009652  lea     rdx, [rsp+4E0h+rgIndices]; rgIndices
0x180009657  call    cs:__imp_SafeArrayPutElement
0x18000965d  mov     ebx, eax
0x18000965f  test    eax, eax
0x180009661  js      loc_1800096E9
0x180009667  inc     [rsp+4E0h+rgIndices]
0x18000966b  mov     rcx, rsi; bstrString
0x18000966e  call    cs:__imp_SysFreeString
0x180009674  mov     rcx, rdi; bstrString
0x180009677  call    cs:__imp_SysFreeString
0x18000967d  jmp     loc_180009462
0x180009682  mov     ebx, 8007000Eh
0x180009687  jmp     short loc_1800096E6
0x180009689  call    cs:__imp_GetLastError
0x18000968f  mov     ebx, eax
0x180009691  test    eax, eax
0x180009693  jle     short loc_1800096E6
0x180009695  movzx   ebx, ax
0x180009698  or      ebx, 80070000h
0x18000969e  jmp     short loc_1800096E6
0x1800096a0  call    cs:__imp_GetLastError
0x1800096a6  mov     ebx, eax
0x1800096a8  test    eax, eax
0x1800096aa  jmp     loc_1800093FA
0x1800096af  cmp     ebx, 103h
0x1800096b5  jz      short loc_1800096C6
0x1800096b7  test    ebx, ebx
0x1800096b9  jle     short loc_1800096E3
0x1800096bb  movzx   ebx, bx
0x1800096be  or      ebx, 80070000h
0x1800096c4  jmp     short loc_1800096E3
0x1800096c6  mov     eax, [rsp+4E0h+rgIndices]
0x1800096ca  lea     rdx, [rsp+4E0h+rgsabound]; psaboundNew
0x1800096cf  mov     rcx, [r15]; psa
0x1800096d2  mov     [rsp+4E0h+rgsabound.cElements], eax
0x1800096d6  mov     [rsp+4E0h+rgsabound.lLbound], r12d
0x1800096db  call    cs:__imp_SafeArrayRedim
0x1800096e1  mov     ebx, eax
0x1800096e3  mov     rsi, r12
0x1800096e6  mov     rdi, r12
0x1800096e9  mov     rcx, rsi; bstrString
0x1800096ec  call    cs:__imp_SysFreeString
0x1800096f2  mov     rcx, rdi; bstrString
0x1800096f5  call    cs:__imp_SysFreeString
0x1800096fb  test    r14, r14
0x1800096fe  jz      short loc_180009708
0x180009700  mov     rcx, r14; Block
0x180009703  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180009708  mov     rcx, [rsp+4E0h+hEnum]; hEnum
0x18000970d  test    rcx, rcx
0x180009710  jz      short loc_180009731
0x180009712  call    cs:__imp_WNetCloseEnum
0x180009718  test    eax, eax
0x18000971a  jz      short loc_180009731
0x18000971c  test    ebx, ebx
0x18000971e  js      short loc_180009731
0x180009720  test    eax, eax
0x180009722  jg      short loc_180009728
0x180009724  mov     ebx, eax
0x180009726  jmp     short loc_180009731
0x180009728  movzx   ebx, ax
0x18000972b  or      ebx, 80070000h
0x180009731  mov     eax, ebx
0x180009733  mov     rcx, [rbp+3E0h+var_40]
0x18000973a  xor     rcx, rsp; StackCookie
0x18000973d  call    __security_check_cookie
0x180009742  mov     rbx, [rsp+4E0h+arg_0]
0x18000974a  add     rsp, 4B0h
0x180009751  pop     r15
0x180009753  pop     r14
0x180009755  pop     r13
0x180009757  pop     r12
0x180009759  pop     rdi
0x18000975a  pop     rsi
0x18000975b  pop     rbp
0x18000975c  retn
```
