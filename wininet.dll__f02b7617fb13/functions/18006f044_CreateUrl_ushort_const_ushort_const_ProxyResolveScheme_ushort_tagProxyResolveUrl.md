# CreateUrl(ushort const *,ushort const *,ProxyResolveScheme,ushort,tagProxyResolveUrl * *)

- ea: `0x18006f044`
- end: `0x18006f5d4`
- name: `?CreateUrl@@YAJPEBG0W4ProxyResolveScheme@@GPEAPEAUtagProxyResolveUrl@@@Z`
- size: `1424`
- prototype: ``
- caller_count: `5`
- callee_count: `7`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180068eb4`
- `0x1800bf320`
- `0x1800bf5a4`
- `0x1800bfb9c`
- `0x180100e40`

## callees

- `0x18006f044`
- `0x1800701d0`
- `0x1800708d0`
- `0x1800c005c`
- `0x18014a7a0`
- `0x18014b3b4`
- `0x1801e875c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006f2c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006f2c1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18006f3c8`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18006f3c8`
- `ntdll!RtlGetLastNtStatus` at `0x18006f3da`
- `ntdll!RtlGetLastNtStatus` at `0x18006f3da`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006f2f8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006f306`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006f314`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006f44c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006f46b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006f2f8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006f306`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006f314`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006f44c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006f46b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18006f0f9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18006f1e1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18006f48e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18006f4ce`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18006f0f9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18006f1e1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18006f48e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18006f4ce`

## pseudocode

```c
__int64 __fastcall CreateUrl(_WORD *a1, const wchar_t *a2, __int32 a3, __int16 a4, _QWORD *a5)
{
  WCHAR *v7; // rdi
  WCHAR *v8; // rbx
  __int64 v9; // rsi
  _WORD *v10; // rax
  _WORD *v11; // r12
  signed int v12; // r15d
  unsigned int v13; // eax
  __int64 v14; // r8
  __int64 v15; // rcx
  void *v16; // rax
  _WORD *v17; // rdx
  signed int v18; // esi
  const wchar_t *v19; // r13
  void *v20; // rsi
  __int64 v21; // rax
  _WORD *v22; // rax
  _WORD *v23; // r12
  unsigned __int64 v24; // r8
  void *v25; // rax
  __int64 v26; // rdx
  _WORD *v27; // rdx
  DWORD LastError; // r12d
  __int64 v30; // r15
  WCHAR *v31; // rax
  __int64 v32; // rdx
  __int64 v33; // rcx
  int v34; // r8d
  _WORD *v35; // rax
  int v36; // eax
  int v37; // [rsp+40h] [rbp-A1h]
  size_t Sizea; // [rsp+48h] [rbp-99h]
  $2B4FDC4BF487E67F052937EE78FAE255 UrlComponents; // [rsp+70h] [rbp-71h] BYREF
  DWORD dwUrlLength; // [rsp+E0h] [rbp-1h] BYREF

  dwUrlLength = 0;
  memset_0(&UrlComponents, 0, sizeof(UrlComponents));
  if ( !a5 )
    return (unsigned int)-2147024809;
  *a5 = 0;
  if ( !a1 || !a2 )
    return (unsigned int)-2147024809;
  v7 = 0;
  v8 = 0;
  v9 = -1;
  do
    ++v9;
  while ( a1[v9] );
  v10 = CoTaskMemAlloc((unsigned int)(2 * v9 + 2));
  v11 = v10;
  v12 = -2147024809;
  if ( !v10 )
  {
    v18 = -2147024882;
    goto LABEL_18;
  }
  memset_0(v10, 0, (unsigned int)(2 * v9 + 2));
  v13 = v9 + 1;
  v14 = (unsigned int)(v9 + 1);
  if ( (_DWORD)v9 != -1 )
  {
    if ( v13 <= 0x7FFFFFFFuLL )
    {
      v15 = 2147483646;
      v16 = v11;
      do
      {
        if ( !v15 )
          break;
        if ( !*a1 )
          break;
        *v11++ = *a1++;
        --v15;
        --v14;
      }
      while ( v14 );
      v17 = v11 - 1;
      if ( v14 )
        v17 = v11;
      *v17 = 0;
      v18 = v14 == 0 ? 0x8007007A : 0;
      goto LABEL_16;
    }
    v18 = -2147024809;
    goto LABEL_78;
  }
  v18 = -2147024809;
  if ( v13 )
LABEL_78:
    *v11 = 0;
  v16 = v11;
LABEL_16:
  if ( v18 < 0 )
  {
    if ( v16 )
      CoTaskMemFree(v16);
  }
  else
  {
    v8 = (WCHAR *)v16;
  }
LABEL_18:
  if ( v18 >= 0 )
  {
    v19 = L"/";
    v20 = 0;
    if ( *a2 )
      v19 = a2;
    v21 = -1;
    do
      ++v21;
    while ( v19[v21] );
    v37 = v21;
    Sizea = (unsigned int)(2 * v21 + 2);
    v22 = CoTaskMemAlloc((unsigned int)Sizea);
    v23 = v22;
    if ( !v22 )
    {
      v12 = -2147024882;
      goto LABEL_35;
    }
    memset_0(v22, 0, Sizea);
    v24 = (unsigned int)(v37 + 1);
    if ( v37 != -1 )
    {
      if ( v24 <= 0x7FFFFFFF )
      {
        v25 = v23;
        v26 = 2147483646;
        do
        {
          if ( !v26 )
            break;
          if ( !*v19 )
            break;
          *v23++ = *v19++;
          --v26;
          --v24;
        }
        while ( v24 );
        v27 = v23 - 1;
        if ( v24 )
          v27 = v23;
        *v27 = 0;
        v12 = v24 == 0 ? 0x8007007A : 0;
        goto LABEL_33;
      }
      *v23 = 0;
    }
    v25 = v23;
LABEL_33:
    if ( v12 < 0 )
    {
      if ( v25 )
        CoTaskMemFree(v25);
    }
    else
    {
      v20 = v25;
    }
LABEL_35:
    if ( v12 < 0 )
    {
LABEL_40:
      if ( v20 )
        CoTaskMemFree(v20);
      goto LABEL_42;
    }
    UrlComponents.nPort = a4;
    UrlComponents.dwStructSize = 104;
    UrlComponents.nScheme = a3;
    UrlComponents.lpszHostName = v8;
    UrlComponents.lpszUrlPath = (LPWSTR)v20;
    if ( !InternetCreateUrlW(&UrlComponents, 0, 0, &dwUrlLength) )
    {
      LastError = GetLastError();
      if ( qword_180269EA8 )
      {
        if ( !LastError || LastError == 997 || LastError == 12150 || LastError == 12028 )
          goto LABEL_39;
        if ( LastError != 122 )
        {
          v30 = 16LL * (unsigned __int8)(_InterlockedExchangeAdd(&dword_180269EA4, 1u) + 1);
          GetSystemTimeAsFileTime((LPFILETIME)(v30 + qword_180269EA8));
          *(_DWORD *)(v30 + qword_180269EA8 + 8) = LastError;
          *(_DWORD *)(v30 + qword_180269EA8 + 12) = RtlGetLastNtStatus();
          goto LABEL_39;
        }
      }
      else if ( LastError != 122 )
      {
        goto LABEL_39;
      }
      v31 = (WCHAR *)CoTaskMemAlloc(2 * dwUrlLength);
      v7 = v31;
      if ( v31 )
      {
        if ( InternetCreateUrlW(&UrlComponents, 0, v31, &dwUrlLength) )
        {
          if ( (xmmword_180266B60 & 0x20) != 0 )
            WPP_SF_SSSdd(v33, 12, v34, (_DWORD)v7, (__int64)v8, (__int64)v20, a3, a4);
          v35 = CoTaskMemAlloc(0x20u);
          if ( v35 )
          {
            v35[15] = 0;
            *(_QWORD *)v35 = v7;
            *((_QWORD *)v35 + 1) = v8;
            *((_QWORD *)v35 + 2) = v20;
            *((_DWORD *)v35 + 6) = a3;
            v12 = 0;
            v35[14] = a4;
            *a5 = v35;
            return (unsigned int)v12;
          }
          v12 = -2147024882;
        }
        else
        {
          v36 = WxGetLastError(v33, v32);
          v12 = v36;
          if ( v36 > 0 )
            v12 = (unsigned __int16)v36 | 0x80070000;
          if ( v12 >= 0 )
            v12 = -2147418113;
        }
      }
      else
      {
        v12 = -2147024882;
        v7 = 0;
      }
      goto LABEL_40;
    }
LABEL_39:
    v12 = -2147418113;
    goto LABEL_40;
  }
  v12 = v18;
LABEL_42:
  if ( v8 )
    CoTaskMemFree(v8);
  if ( v7 )
    CoTaskMemFree(v7);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18006f044  push    rbp
0x18006f046  push    rbx
0x18006f047  push    rsi
0x18006f048  push    rdi
0x18006f049  push    r12
0x18006f04b  push    r13
0x18006f04d  push    r14
0x18006f04f  push    r15
0x18006f051  lea     rbp, [rsp-17h]
0x18006f056  sub     rsp, 0F8h
0x18006f05d  mov     rax, cs:__security_cookie
0x18006f064  xor     rax, rsp
0x18006f067  mov     [rbp+4Fh+var_48], rax
0x18006f06b  mov     rdi, [rbp+4Fh+arg_20]
0x18006f06f  xor     r12d, r12d
0x18006f072  mov     [rsp+130h+var_DC], r8d
0x18006f077  mov     rbx, rdx
0x18006f07a  mov     [rsp+130h+Size], rdx
0x18006f07f  mov     r13, rcx
0x18006f082  xor     edx, edx; Val
0x18006f084  mov     [rsp+130h+var_E0], r9w
0x18006f08a  lea     r8d, [r12+68h]; Size
0x18006f08f  mov     [rsp+130h+var_D0], rdi
0x18006f094  lea     rcx, [rbp+4Fh+UrlComponents]; void *
0x18006f098  mov     [rsp+130h+var_EC], r12d
0x18006f09d  mov     r14d, r12d
0x18006f0a0  mov     [rsp+130h+var_D8], r12
0x18006f0a5  mov     [rbp+4Fh+dwUrlLength], r12d
0x18006f0a9  call    memset_0
0x18006f0ae  test    rdi, rdi
0x18006f0b1  jz      loc_18006F41B
0x18006f0b7  mov     [rdi], r12
0x18006f0ba  test    r13, r13
0x18006f0bd  jz      loc_18006F559
0x18006f0c3  test    rbx, rbx
0x18006f0c6  jz      loc_18006F42E
0x18006f0cc  mov     edi, r12d
0x18006f0cf  mov     [rsp+130h+var_EC], r12d
0x18006f0d4  mov     ebx, r12d
0x18006f0d7  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18006f0db  inc     rsi
0x18006f0de  cmp     [r13+rsi*2+0], r12w
0x18006f0e4  jnz     short loc_18006F0DB
0x18006f0e6  lea     eax, ds:2[rsi*2]
0x18006f0ed  mov     [rsp+130h+var_EC], r12d
0x18006f0f2  mov     ecx, eax; cb
0x18006f0f4  mov     [rsp+40h], rax
0x18006f0f9  call    cs:__imp_CoTaskMemAlloc
0x18006f0ff  mov     r12, rax
0x18006f102  mov     r15d, 80070057h
0x18006f108  test    rax, rax
0x18006f10b  jz      loc_18006F359
0x18006f111  mov     r8, [rsp+40h]; Size
0x18006f116  xor     edx, edx; Val
0x18006f118  mov     rcx, rax; void *
0x18006f11b  call    memset_0
0x18006f120  lea     eax, [rsi+1]
0x18006f123  xor     r9d, r9d
0x18006f126  mov     r8d, eax
0x18006f129  test    eax, eax
0x18006f12b  jz      loc_18006F56B
0x18006f131  cmp     r8, 7FFFFFFFh
0x18006f138  ja      loc_18006F566
0x18006f13e  mov     ecx, 7FFFFFFEh
0x18006f143  mov     rax, r12
0x18006f146  test    rcx, rcx
0x18006f149  jz      short loc_18006F16B
0x18006f14b  movzx   edx, word ptr [r13+0]
0x18006f150  test    dx, dx
0x18006f153  jz      short loc_18006F16B
0x18006f155  mov     [r12], dx
0x18006f15a  add     r13, 2
0x18006f15e  add     r12, 2
0x18006f162  dec     rcx
0x18006f165  sub     r8, 1
0x18006f169  jnz     short loc_18006F146
0x18006f16b  test    r8, r8
0x18006f16e  lea     rdx, [r12-2]
0x18006f173  cmovnz  rdx, r12
0x18006f177  xor     r12d, r12d
0x18006f17a  neg     r8
0x18006f17d  sbb     esi, esi
0x18006f17f  not     esi
0x18006f181  mov     [rdx], r12w
0x18006f185  and     esi, 8007007Ah
0x18006f18b  test    esi, esi
0x18006f18d  js      loc_18006F438
0x18006f193  mov     rbx, rax
0x18006f196  test    esi, esi
0x18006f198  js      loc_18006F34C
0x18006f19e  mov     rax, [rsp+130h+Size]
0x18006f1a3  lea     r13, asc_1802223C8; "/"
0x18006f1aa  mov     rsi, r12
0x18006f1ad  cmp     [rax], r12w
0x18006f1b1  mov     [rsp+130h+var_EC], r12d
0x18006f1b6  cmovnz  r13, rax
0x18006f1ba  or      rax, 0FFFFFFFFFFFFFFFFh
0x18006f1be  inc     rax
0x18006f1c1  cmp     [r13+rax*2+0], r12w
0x18006f1c7  jnz     short loc_18006F1BE
0x18006f1c9  mov     [rsp+40h], rax
0x18006f1ce  lea     eax, ds:2[rax*2]
0x18006f1d5  mov     ecx, eax; cb
0x18006f1d7  mov     dword ptr [rsp+130h+Size+4], r12d
0x18006f1dc  mov     [rsp+130h+Size], rax
0x18006f1e1  call    cs:__imp_CoTaskMemAlloc
0x18006f1e7  mov     r12, rax
0x18006f1ea  test    rax, rax
0x18006f1ed  jz      loc_18006F3F3
0x18006f1f3  mov     r8, [rsp+130h+Size]; Size
0x18006f1f8  xor     edx, edx; Val
0x18006f1fa  mov     rcx, rax; void *
0x18006f1fd  call    memset_0
0x18006f202  mov     rax, [rsp+40h]
0x18006f207  xor     r9d, r9d
0x18006f20a  add     eax, 1
0x18006f20d  mov     r8d, eax
0x18006f210  jz      loc_18006F582
0x18006f216  cmp     r8, 7FFFFFFFh
0x18006f21d  ja      loc_18006F586
0x18006f223  mov     rax, r12
0x18006f226  mov     edx, 7FFFFFFEh
0x18006f22b  test    rdx, rdx
0x18006f22e  jz      short loc_18006F250
0x18006f230  movzx   ecx, word ptr [r13+0]
0x18006f235  test    cx, cx
0x18006f238  jz      short loc_18006F250
0x18006f23a  mov     [r12], cx
0x18006f23f  add     r13, 2
0x18006f243  add     r12, 2
0x18006f247  dec     rdx
0x18006f24a  sub     r8, 1
0x18006f24e  jnz     short loc_18006F22B
0x18006f250  test    r8, r8
0x18006f253  lea     rdx, [r12-2]
0x18006f258  cmovnz  rdx, r12
0x18006f25c  xor     r12d, r12d
0x18006f25f  neg     r8
0x18006f262  sbb     r15d, r15d
0x18006f265  not     r15d
0x18006f268  mov     [rdx], r12w
0x18006f26c  and     r15d, 8007007Ah
0x18006f273  test    r15d, r15d
0x18006f276  js      loc_18006F457
0x18006f27c  mov     rsi, rax
0x18006f27f  test    r15d, r15d
0x18006f282  js      loc_18006F40E
0x18006f288  movzx   r13d, [rsp+130h+var_E0]
0x18006f28e  lea     r9, [rbp+4Fh+dwUrlLength]; lpdwUrlLength
0x18006f292  mov     r15d, [rsp+130h+var_DC]
0x18006f297  lea     rcx, [rbp+4Fh+UrlComponents]; lpUrlComponents
0x18006f29b  xor     r8d, r8d; lpszUrl
0x18006f29e  mov     [rbp+4Fh+UrlComponents.nPort], r13w
0x18006f2a3  xor     edx, edx; dwFlags
0x18006f2a5  mov     [rbp+4Fh+UrlComponents.dwStructSize], 68h ; 'h'
0x18006f2ac  mov     [rbp+4Fh+UrlComponents.nScheme], r15d
0x18006f2b0  mov     [rbp+4Fh+UrlComponents.lpszHostName], rbx
0x18006f2b4  mov     [rbp+4Fh+UrlComponents.lpszUrlPath], rsi
0x18006f2b8  call    InternetCreateUrlW
0x18006f2bd  test    eax, eax
0x18006f2bf  jnz     short loc_18006F2E2
0x18006f2c1  call    cs:__imp_GetLastError
0x18006f2c7  mov     r12d, eax
0x18006f2ca  xor     eax, eax
0x18006f2cc  cmp     cs:qword_180269EA8, rax
0x18006f2d3  jz      loc_18006F476
0x18006f2d9  test    r12d, r12d
0x18006f2dc  jnz     loc_18006F376
0x18006f2e2  mov     [rsp+130h+var_EC], 1E2h
0x18006f2ea  mov     r15d, 8000FFFFh
0x18006f2f0  test    rsi, rsi
0x18006f2f3  jz      short loc_18006F2FE
0x18006f2f5  mov     rcx, rsi; pv
0x18006f2f8  call    cs:__imp_CoTaskMemFree
0x18006f2fe  test    rbx, rbx
0x18006f301  jz      short loc_18006F30C
0x18006f303  mov     rcx, rbx; pv
0x18006f306  call    cs:__imp_CoTaskMemFree
0x18006f30c  test    rdi, rdi
0x18006f30f  jz      short loc_18006F31A
0x18006f311  mov     rcx, rdi; pv
0x18006f314  call    cs:__imp_CoTaskMemFree
0x18006f31a  test    r14, r14
0x18006f31d  jz      short loc_18006F329
0x18006f31f  lea     rcx, [rsp+130h+var_D8]; struct tagProxyResolveUrl **
0x18006f324  call    ?FreeProxyResolveUrl@@YAXPEAPEAUtagProxyResolveUrl@@@Z; FreeProxyResolveUrl(tagProxyResolveUrl * *)
0x18006f329  mov     eax, r15d
0x18006f32c  mov     rcx, [rbp+4Fh+var_48]
0x18006f330  xor     rcx, rsp; StackCookie
0x18006f333  call    __security_check_cookie
0x18006f338  add     rsp, 0F8h
0x18006f33f  pop     r15
0x18006f341  pop     r14
0x18006f343  pop     r13
0x18006f345  pop     r12
0x18006f347  pop     rdi
0x18006f348  pop     rsi
0x18006f349  pop     rbx
0x18006f34a  pop     rbp
0x18006f34b  retn
0x18006f34c  mov     [rsp+130h+var_EC], 1CEh
0x18006f354  mov     r15d, esi
0x18006f357  jmp     short loc_18006F2FE
0x18006f359  mov     [rsp+130h+var_EC], 4Ch ; 'L'
0x18006f361  mov     esi, 8007000Eh
0x18006f366  mov     [rsp+130h+var_EC], 220h
0x18006f36e  xor     r12d, r12d
0x18006f371  jmp     loc_18006F196
0x18006f376  cmp     r12d, 3E5h
0x18006f37d  jz      loc_18006F2E2
0x18006f383  cmp     r12d, 2F76h
0x18006f38a  jz      loc_18006F2E2
0x18006f390  cmp     r12d, 2EFCh
0x18006f397  jz      loc_18006F2E2
0x18006f39d  cmp     r12d, 7Ah ; 'z'
0x18006f3a1  jz      loc_18006F480
0x18006f3a7  mov     eax, 1
0x18006f3ac  lock xadd cs:dword_180269EA4, eax
0x18006f3b4  mov     rcx, cs:qword_180269EA8
0x18006f3bb  inc     eax
0x18006f3bd  movzx   r15d, al
0x18006f3c1  shl     r15, 4
0x18006f3c5  add     rcx, r15; lpSystemTimeAsFileTime
0x18006f3c8  call    cs:__imp_GetSystemTimeAsFileTime
0x18006f3ce  mov     rax, cs:qword_180269EA8
0x18006f3d5  mov     [r15+rax+8], r12d
0x18006f3da  call    cs:__imp_RtlGetLastNtStatus
0x18006f3e0  mov     ecx, eax
0x18006f3e2  mov     rax, cs:qword_180269EA8
0x18006f3e9  mov     [r15+rax+0Ch], ecx
0x18006f3ee  jmp     loc_18006F2E2
0x18006f3f3  mov     dword ptr [rsp+130h+Size+4], 4Ch ; 'L'
0x18006f3fb  mov     r15d, 8007000Eh
0x18006f401  mov     [rsp+130h+var_EC], 220h
0x18006f409  jmp     loc_18006F27F
0x18006f40e  mov     [rsp+130h+var_EC], 1D5h
0x18006f416  jmp     loc_18006F2F0
0x18006f41b  mov     [rsp+130h+var_EC], 1C7h
0x18006f423  mov     r15d, 80070057h
0x18006f429  jmp     loc_18006F31A
0x18006f42e  mov     [rsp+130h+var_EC], 1CBh
0x18006f436  jmp     short loc_18006F423
0x18006f438  mov     [rsp+130h+var_EC], 224h
0x18006f440  test    rax, rax
0x18006f443  jz      loc_18006F196
0x18006f449  mov     rcx, rax; pv
0x18006f44c  call    cs:__imp_CoTaskMemFree
0x18006f452  jmp     loc_18006F196
0x18006f457  mov     [rsp+130h+var_EC], 224h
0x18006f45f  test    rax, rax
0x18006f462  jz      loc_18006F27F
0x18006f468  mov     rcx, rax; pv
0x18006f46b  call    cs:__imp_CoTaskMemFree
0x18006f471  jmp     loc_18006F27F
0x18006f476  cmp     r12d, 7Ah ; 'z'
0x18006f47a  jnz     loc_18006F2E2
0x18006f480  mov     eax, [rbp+4Fh+dwUrlLength]
0x18006f483  xor     r12d, r12d
0x18006f486  mov     dword ptr [rsp+130h+Size+4], r12d
0x18006f48b  lea     ecx, [rax+rax]; cb
0x18006f48e  call    cs:__imp_CoTaskMemAlloc
0x18006f494  mov     rdi, rax
0x18006f497  test    rax, rax
0x18006f49a  jz      short loc_18006F50B
0x18006f49c  lea     r9, [rbp+4Fh+dwUrlLength]; lpdwUrlLength
0x18006f4a0  mov     r8, rax; lpszUrl
0x18006f4a3  xor     edx, edx; dwFlags
0x18006f4a5  lea     rcx, [rbp+4Fh+UrlComponents]; lpUrlComponents
0x18006f4a9  call    InternetCreateUrlW
0x18006f4ae  test    eax, eax
0x18006f4b0  jz      short loc_18006F529
0x18006f4b2  test    byte ptr cs:xmmword_180266B60, 20h
0x18006f4b9  jnz     loc_18006F593
0x18006f4bf  mov     ecx, 20h ; ' '; cb
0x18006f4c4  mov     dword ptr [rsp+130h+Size+4], r12d
0x18006f4c9  mov     [rsp+130h+var_D8], r12
0x18006f4ce  call    cs:__imp_CoTaskMemAlloc
0x18006f4d4  test    rax, rax
0x18006f4d7  jz      loc_18006F5B9
0x18006f4dd  mov     [rax+1Eh], r12w
0x18006f4e2  mov     rcx, [rsp+130h+var_D0]
0x18006f4e7  mov     [rax], rdi
0x18006f4ea  mov     [rax+8], rbx
0x18006f4ee  mov     [rax+10h], rsi
0x18006f4f2  mov     [rax+18h], r15d
0x18006f4f6  mov     r15d, r12d
0x18006f4f9  mov     [rax+1Ch], r13w
0x18006f4fe  mov     [rcx], rax
0x18006f501  mov     [rsp+130h+var_D8], r12
0x18006f506  jmp     loc_18006F31A
0x18006f50b  mov     dword ptr [rsp+130h+Size+4], 34h ; '4'
0x18006f513  mov     r15d, 8007000Eh
0x18006f519  mov     [rsp+130h+var_EC], 1E4h
0x18006f521  mov     rdi, r12
0x18006f524  jmp     loc_18006F2F0
0x18006f529  call    WxGetLastError
0x18006f52e  mov     r15d, eax
0x18006f531  test    eax, eax
0x18006f533  jle     short loc_18006F540
0x18006f535  movzx   r15d, ax
  ... truncated ...
```
