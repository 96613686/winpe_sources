# HostWCharToCharEx

- ea: `0x1800da530`
- end: `0x1800dada5`
- name: `HostWCharToCharEx`
- size: `2165`
- prototype: `__int64 __usercall@<rax>(LPCWSTR lpUnicodeCharStr@<rcx>, int cchUnicodeChar@<edx>, __int64)`
- caller_count: `19`
- callee_count: `7`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180008560`
- `0x1800bf62c`
- `0x1800c1cc0`
- `0x1800c8014`
- `0x1800d8680`
- `0x1800d8bf0`
- `0x1800d943c`
- `0x1800d9d20`
- `0x1800da348`
- `0x1801226b0`
- `0x180140980`
- `0x180157e90`
- `0x18015cdd4`
- `0x18015e27c`
- `0x18015fea8`
- `0x18017c9b0`
- `0x18017f3c0`
- `0x18017f510`
- `0x180180e80`

## callees

- `0x1800701d0`
- `0x1800da530`
- `0x18014a7a0`
- `0x18014b360`
- `0x18014b3b4`
- `0x1801e0700`
- `0x1801e1790`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800daa6d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800daa6d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800da7a2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800da878`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800da7a2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800da878`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800da80c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800daab1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800da80c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800daab1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800dab6c`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800dab6c`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800da760`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800da7d8`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800dabd1`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800da760`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800da7d8`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800dabd1`
- `api-ms-win-core-localization-l1-2-0!IdnToAscii` at `0x1800da6eb`
- `api-ms-win-core-localization-l1-2-0!IdnToAscii` at `0x1800da899`
- `api-ms-win-core-localization-l1-2-0!IdnToAscii` at `0x1800da6eb`
- `api-ms-win-core-localization-l1-2-0!IdnToAscii` at `0x1800da899`
- `ntdll!RtlGetLastNtStatus` at `0x1800dab7d`
- `ntdll!RtlGetLastNtStatus` at `0x1800dab7d`
- `ntdll!RtlNtStatusToDosError` at `0x1800dacc0`
- `ntdll!RtlNtStatusToDosError` at `0x1800dacc0`
- `ntdll!RtlIpv6StringToAddressExW` at `0x1800da6c9`
- `ntdll!RtlIpv6StringToAddressExW` at `0x1800da937`
- `ntdll!RtlIpv6StringToAddressExW` at `0x1800da6c9`
- `ntdll!RtlIpv6StringToAddressExW` at `0x1800da937`
- `ntdll!RtlIpv4StringToAddressExW` at `0x1800da6a0`
- `ntdll!RtlIpv4StringToAddressExW` at `0x1800da90c`
- `ntdll!RtlIpv4StringToAddressExW` at `0x1800da6a0`
- `ntdll!RtlIpv4StringToAddressExW` at `0x1800da90c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800da84a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800dac2b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800dac4a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800da84a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800dac2b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800dac4a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800da5b1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800da9db`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800da5b1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800da9db`

## pseudocode

```c
__int64 __fastcall HostWCharToCharEx(LPCWSTR lpUnicodeCharStr, unsigned int cchUnicodeChar, int a3, LPSTR *a4, int *a5)
{
  unsigned int v5; // ebp
  wchar_t *v6; // rdi
  unsigned __int64 v9; // r15
  unsigned int v10; // esi
  _WORD *v11; // rax
  _WORD *v12; // rbx
  __int64 v13; // r8
  __int64 v14; // rax
  LPCWSTR v15; // rdx
  _WORD *v16; // r9
  _WORD *v17; // rax
  int v18; // esi
  int v19; // ebx
  int v20; // eax
  __int64 v21; // rdx
  __int64 v22; // rcx
  unsigned int cchASCIIChar; // ebx
  __int64 v24; // rax
  unsigned __int64 v25; // rax
  const WCHAR *v26; // rbx
  WCHAR *v27; // r12
  int *v28; // rax
  CHAR *v29; // rsi
  __int64 v30; // rdx
  __int64 v31; // rcx
  __int64 v32; // r14
  unsigned int cbMultiByte; // r15d
  LPSTR *v34; // rax
  CHAR *v35; // rax
  WCHAR *v37; // rax
  unsigned int v38; // eax
  __int64 v39; // rdx
  __int64 v40; // rcx
  WCHAR *v41; // rbx
  unsigned int v42; // esi
  __int64 v43; // rax
  __int64 v44; // rsi
  bool v45; // zf
  wchar_t *v46; // rax
  wchar_t *v47; // rbx
  unsigned __int64 v48; // r9
  wchar_t *v49; // rax
  __int64 v50; // rcx
  LPCWSTR v51; // r8
  wchar_t *v52; // rcx
  DWORD LastError; // eax
  __int64 v54; // rbx
  __int64 v55; // rax
  USHORT Port; // [rsp+50h] [rbp-98h] BYREF
  _OWORD v58[3]; // [rsp+58h] [rbp-90h] BYREF
  struct in6_addr v59[2]; // [rsp+88h] [rbp-60h] BYREF

  v5 = 0;
  v6 = 0;
  v9 = cchUnicodeChar;
  DWORD1(v58[0]) = 0;
  if ( cchUnicodeChar != -1 )
  {
    if ( !lpUnicodeCharStr )
    {
      DWORD1(v58[0]) = 596;
      v18 = -2147024809;
      goto LABEL_16;
    }
    DWORD1(v58[0]) = 0;
    v10 = 2 * cchUnicodeChar + 2;
    v11 = CoTaskMemAlloc(v10);
    v12 = v11;
    if ( !v11 )
    {
      v18 = -2147024882;
      DWORD1(v58[0]) = 600;
      goto LABEL_16;
    }
    memset_0(v11, 0, v10);
    v13 = (unsigned int)(v9 + 1);
    if ( (_DWORD)v9 == -1 )
    {
      v18 = -2147024809;
    }
    else
    {
      if ( (unsigned int)(v9 + 1) > 0x7FFFFFFFuLL || (v14 = (unsigned int)v9, v9 > 0x7FFFFFFE) )
      {
        *v12 = 0;
        v18 = -2147024809;
LABEL_94:
        DWORD1(v58[0]) = 605;
        if ( v12 )
          CoTaskMemFree(v12);
        goto LABEL_16;
      }
      v15 = lpUnicodeCharStr;
      v16 = v12;
      do
      {
        if ( !v14 )
          break;
        if ( !*v15 )
          break;
        *v16++ = *v15++;
        --v14;
        --v13;
      }
      while ( v13 );
      v17 = v16 - 1;
      v18 = -2147024774;
      if ( v13 )
      {
        v17 = v16;
        v18 = 0;
      }
      *v17 = 0;
    }
    if ( v18 >= 0 )
    {
      v6 = v12;
      goto LABEL_16;
    }
    goto LABEL_94;
  }
  if ( !lpUnicodeCharStr )
  {
    DWORD1(v58[0]) = 538;
    v18 = -2147024809;
    goto LABEL_16;
  }
  v44 = -1;
  do
    v45 = lpUnicodeCharStr[++v44] == 0;
  while ( !v45 );
  DWORD1(v58[0]) = 0;
  v46 = (wchar_t *)CoTaskMemAlloc((unsigned int)(2 * v44 + 2));
  v47 = v46;
  if ( !v46 )
  {
    v18 = -2147024882;
    DWORD1(v58[0]) = 544;
    v5 = 0;
    goto LABEL_16;
  }
  memset_0(v46, 0, (unsigned int)(2 * v44 + 2));
  v48 = (unsigned int)(v44 + 1);
  v49 = v47;
  if ( (_DWORD)v44 == -1 )
  {
    v18 = -2147024809;
    v5 = 0;
    goto LABEL_72;
  }
  if ( v48 <= 0x7FFFFFFF )
  {
    v50 = 2147483646;
    v51 = lpUnicodeCharStr;
    do
    {
      if ( !v50 )
        break;
      if ( !*v51 )
        break;
      *v47++ = *v51++;
      --v50;
      --v48;
    }
    while ( v48 );
    v52 = v47 - 1;
    v18 = -2147024774;
    if ( v48 )
      v52 = v47;
    v5 = 0;
    if ( v48 )
      v18 = 0;
    *v52 = 0;
LABEL_72:
    if ( v18 >= 0 )
    {
      v6 = v49;
      goto LABEL_16;
    }
    goto LABEL_96;
  }
  v5 = 0;
  v18 = -2147024809;
  *v47 = 0;
LABEL_96:
  DWORD1(v58[0]) = 548;
  if ( v49 )
    CoTaskMemFree(v49);
LABEL_16:
  if ( v18 < 0 )
  {
    v5 = (unsigned __int16)v18;
    goto LABEL_38;
  }
  DWORD1(v58[0]) = 0;
  memset(&v58[1], 0, 28);
  v19 = 0;
  if ( !wcsicmp(v6, L"localhost") || !wcsicmp(v6, L"loopback") )
    goto LABEL_22;
  LOWORD(v58[1]) = 2;
  if ( !RtlIpv4StringToAddressExW(v6, 1u, (struct in_addr *)&v58[1] + 1, (PUSHORT)&v58[1] + 1)
    || (LOWORD(v58[1]) = 23,
        !RtlIpv6StringToAddressExW(
           v6,
           (struct in6_addr *)((char *)&v58[1] + 8),
           (PULONG)&v58[2] + 2,
           (PUSHORT)&v58[1] + 1)) )
  {
    v19 = 1;
LABEL_22:
    if ( v19 )
    {
      v26 = v6;
      v27 = 0;
      if ( !v6 )
      {
        v28 = a5;
        goto LABEL_120;
      }
LABEL_28:
      v28 = a5;
      v29 = 0;
      if ( a5 )
      {
        LODWORD(v32) = WideCharToMultiByte(0xFDE9u, 0, v26, -1, 0, 0, 0, 0);
        if ( (_DWORD)v32 )
        {
          cbMultiByte = v32;
          v32 = (unsigned int)(v32 - 1);
          v34 = a4;
          if ( !a4 )
          {
LABEL_77:
            *a5 = v32;
            if ( v5 )
            {
              if ( v29 )
                HeapFree(g_hWxProcessHeap, 0, v29);
              goto LABEL_36;
            }
            if ( !v34 )
              goto LABEL_36;
LABEL_99:
            if ( v29 )
              goto LABEL_35;
LABEL_36:
            if ( !v27 )
              goto LABEL_38;
            goto LABEL_37;
          }
          if ( !*a4 )
          {
            v35 = (CHAR *)HeapAlloc(g_hWxProcessHeap, 0, cbMultiByte);
            v29 = v35;
            if ( !v35 )
            {
              v5 = 8;
              *a5 = v32;
              goto LABEL_36;
            }
            if ( WideCharToMultiByte(0xFDE9u, 0, v26, -1, v35, cbMultiByte, 0, 0) )
            {
              v29[v32] = 0;
              *a5 = v32;
              v34 = a4;
LABEL_35:
              *v34 = v29;
              goto LABEL_36;
            }
            LastError = GetLastError();
            v5 = LastError;
            if ( qword_180269EA8
              && LastError
              && LastError != 997
              && LastError != 12150
              && LastError != 12028
              && LastError != 122 )
            {
              v54 = 16LL * (unsigned __int8)_InterlockedIncrement(&dword_180269EA4);
              GetSystemTimeAsFileTime((LPFILETIME)(v54 + qword_180269EA8));
              *(_DWORD *)(v54 + qword_180269EA8 + 8) = v5;
              *(_DWORD *)(v54 + qword_180269EA8 + 12) = RtlGetLastNtStatus();
            }
            goto LABEL_76;
          }
          if ( *a5 < cbMultiByte )
          {
            v5 = 122;
            *a5 = v32;
            goto LABEL_36;
          }
          if ( WideCharToMultiByte(0xFDE9u, 0, v26, -1, *a4, *a5, 0, 0) )
          {
            (*a4)[v32] = 0;
            *a5 = v32;
            v34 = a4;
            goto LABEL_99;
          }
        }
        v5 = WxGetLastError(v31, v30);
LABEL_76:
        v34 = a4;
        goto LABEL_77;
      }
LABEL_120:
      v5 = 87;
      *v28 = 0;
      goto LABEL_36;
    }
  }
  v20 = IdnToAscii(0, lpUnicodeCharStr, v9, 0, 0);
  cchASCIIChar = v20;
  if ( v20 )
  {
    v24 = (unsigned int)(v20 + 1);
    if ( (unsigned int)v24 < cchASCIIChar || (v25 = 2 * v24, v25 > 0xFFFFFFFF) )
    {
      v5 = 534;
      goto LABEL_38;
    }
    v37 = (WCHAR *)HeapAlloc(g_hWxProcessHeap, 0, (unsigned int)v25);
    v27 = v37;
    if ( v37 )
    {
      v38 = IdnToAscii(0, lpUnicodeCharStr, v9, v37, cchASCIIChar);
      if ( v38 )
      {
        v27[v38] = 0;
        if ( !a3 )
          goto LABEL_56;
        Port = 0;
        memset(v59, 0, 28);
        v41 = v27;
        v58[0] = 0;
        if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
          WPP_SF_Sd(1036, 10, (unsigned int)WPP_e4a583e537b33e4222dcc118c6822267_Traceguids, (_DWORD)v27, 0);
        if ( RtlIpv4StringToAddressExW(v27, 1u, (struct in_addr *)v58 + 1, &Port) )
        {
          v42 = 0;
          if ( RtlIpv6StringToAddressExW(
                 v27,
                 (struct in6_addr *)&v59[0].u.Word[4],
                 (PULONG)&v59[1].u.Word[4],
                 &v59[0].u.Word[1]) )
          {
            while ( 1 )
            {
              v43 = *v41;
              if ( !(_WORD)v43 )
                break;
              if ( (unsigned __int16)(v43 - 33) > 0x5Du || (*((_BYTE *)&qword_180226CB0[-4] + v43 - 1) & 0x88) != 0 )
                goto LABEL_53;
              ++v41;
            }
            v42 = 1;
          }
          else if ( *v27 == 91 )
          {
            v55 = -1;
            do
              v45 = v27[++v55] == 0;
            while ( !v45 );
            if ( v27[v55 - 1] == 93 )
              v42 = 1;
          }
        }
        else
        {
          v42 = 1;
        }
LABEL_53:
        if ( (BYTE1(xmmword_180266B60) & 0x40) != 0 )
          WPP_SF_d(1038, 11, WPP_e4a583e537b33e4222dcc118c6822267_Traceguids, v42);
        if ( v42 )
        {
LABEL_56:
          v26 = v27;
          goto LABEL_28;
        }
        v5 = 12005;
      }
      else
      {
        v5 = WxGetLastError(v40, v39);
      }
LABEL_37:
      HeapFree(g_hWxProcessHeap, 0, v27);
      goto LABEL_38;
    }
    v5 = 8;
  }
  else
  {
    v5 = WxGetLastError(v22, v21);
  }
LABEL_38:
  if ( v6 )
    CoTaskMemFree(v6);
  return v5;
}

```

## disassembly

```asm
0x1800da530  mov     r11, rsp
0x1800da533  push    rbp
0x1800da534  push    rdi
0x1800da535  sub     rsp, 0D8h
0x1800da53c  mov     rax, cs:__security_cookie
0x1800da543  xor     rax, rsp
0x1800da546  mov     [rsp+0E8h+var_40], rax
0x1800da54e  mov     rax, [rsp+0E8h+arg_20]
0x1800da556  xor     ebp, ebp
0x1800da558  mov     [r11+18h], rbx
0x1800da55c  mov     edi, ebp
0x1800da55e  mov     [r11-18h], rsi
0x1800da562  mov     [r11-20h], r12
0x1800da566  mov     r12d, 0FFFFFFFFh
0x1800da56c  mov     [r11-28h], r13
0x1800da570  mov     r13d, r8d
0x1800da573  mov     [r11-30h], r14
0x1800da577  mov     r14, rcx
0x1800da57a  mov     [r11-38h], r15
0x1800da57e  mov     r15d, edx
0x1800da581  mov     [rsp+0E8h+var_A8], r9
0x1800da586  mov     [rsp+0E8h+var_A0], rax
0x1800da58b  mov     dword ptr [rsp+0E8h+var_8C.S_un], ebp
0x1800da58f  cmp     edx, r12d
0x1800da592  jz      loc_1800DA9B1
0x1800da598  test    rcx, rcx
0x1800da59b  jz      loc_1800DAC84
0x1800da5a1  lea     eax, ds:2[r15*2]
0x1800da5a9  mov     dword ptr [rsp+0E8h+var_8C.S_un], ebp
0x1800da5ad  mov     ecx, eax; cb
0x1800da5af  mov     esi, eax
0x1800da5b1  call    cs:__imp_CoTaskMemAlloc
0x1800da5b7  mov     rbx, rax
0x1800da5ba  test    rax, rax
0x1800da5bd  jz      loc_1800DAABC
0x1800da5c3  mov     r8d, esi; Size
0x1800da5c6  xor     edx, edx; Val
0x1800da5c8  mov     rcx, rax; void *
0x1800da5cb  call    memset_0
0x1800da5d0  lea     eax, [r15+1]
0x1800da5d4  mov     r8d, eax
0x1800da5d7  test    eax, eax
0x1800da5d9  jz      loc_1800DACA3
0x1800da5df  cmp     r8, 7FFFFFFFh
0x1800da5e6  ja      loc_1800DAC96
0x1800da5ec  mov     ecx, 7FFFFFFEh
0x1800da5f1  mov     eax, r15d
0x1800da5f4  cmp     r15, rcx
0x1800da5f7  ja      loc_1800DAC96
0x1800da5fd  mov     rdx, r14
0x1800da600  mov     r9, rbx
0x1800da603  test    rax, rax
0x1800da606  jz      short loc_1800DA625
0x1800da608  movzx   ecx, word ptr [rdx]
0x1800da60b  test    cx, cx
0x1800da60e  jz      short loc_1800DA625
0x1800da610  mov     [r9], cx
0x1800da614  add     rdx, 2
0x1800da618  add     r9, 2
0x1800da61c  dec     rax
0x1800da61f  sub     r8, 1
0x1800da623  jnz     short loc_1800DA603
0x1800da625  test    r8, r8
0x1800da628  lea     rax, [r9-2]
0x1800da62c  mov     esi, 8007007Ah
0x1800da631  cmovnz  rax, r9
0x1800da635  cmovnz  esi, ebp
0x1800da638  mov     [rax], bp
0x1800da63b  test    esi, esi
0x1800da63d  js      loc_1800DAC17
0x1800da643  mov     rdi, rbx
0x1800da646  test    esi, esi
0x1800da648  js      loc_1800DAAD6
0x1800da64e  xorps   xmm0, xmm0
0x1800da651  mov     dword ptr [rsp+0E8h+var_8C.S_un], ebp
0x1800da655  movups  xmmword ptr [rsp+0E8h+Address.S_un], xmm0
0x1800da65a  lea     rdx, aLocalhost; "localhost"
0x1800da661  mov     rcx, rdi; String1
0x1800da664  movups  xmmword ptr [rsp+0E8h+Address.S_un+0Ch], xmm0
0x1800da669  mov     ebx, ebp
0x1800da66b  call    _wcsicmp
0x1800da670  test    eax, eax
0x1800da672  jz      short loc_1800DA6D8
0x1800da674  lea     rdx, aLoopback; "loopback"
0x1800da67b  mov     rcx, rdi; String1
0x1800da67e  call    _wcsicmp
0x1800da683  test    eax, eax
0x1800da685  jz      short loc_1800DA6D8
0x1800da687  mov     eax, 2
0x1800da68c  lea     r9, [rsp+0E8h+Address.S_un+2]; Port
0x1800da691  lea     r8, [rsp+0E8h+Address.S_un+4]; Address
0x1800da696  mov     word ptr [rsp+0E8h+Address.S_un], ax
0x1800da69b  mov     dl, 1; Strict
0x1800da69d  mov     rcx, rdi; AddressString
0x1800da6a0  call    cs:__imp_RtlIpv4StringToAddressExW
0x1800da6a6  test    eax, eax
0x1800da6a8  jz      short loc_1800DA6D3
0x1800da6aa  mov     eax, 17h
0x1800da6af  lea     r9, [rsp+0E8h+Address.S_un+2]; Port
0x1800da6b4  lea     r8, [rsp+0E8h+ScopeId]; ScopeId
0x1800da6bc  mov     word ptr [rsp+0E8h+Address.S_un], ax
0x1800da6c1  lea     rdx, [rsp+0E8h+Address.S_un+8]; Address
0x1800da6c6  mov     rcx, rdi; AddressString
0x1800da6c9  call    cs:__imp_RtlIpv6StringToAddressExW
0x1800da6cf  test    eax, eax
0x1800da6d1  jnz     short loc_1800DA6DC
0x1800da6d3  mov     ebx, 1
0x1800da6d8  test    ebx, ebx
0x1800da6da  jnz     short loc_1800DA717
0x1800da6dc  xor     r9d, r9d; lpASCIICharStr
0x1800da6df  mov     [rsp+0E8h+cchASCIIChar], ebp; cchASCIIChar
0x1800da6e3  mov     r8d, r15d; cchUnicodeChar
0x1800da6e6  mov     rdx, r14; lpUnicodeCharStr
0x1800da6e9  xor     ecx, ecx; dwFlags
0x1800da6eb  call    cs:__imp_IdnToAscii
0x1800da6f1  mov     ebx, eax
0x1800da6f3  test    eax, eax
0x1800da6f5  jz      loc_1800DACE7
0x1800da6fb  inc     eax
0x1800da6fd  cmp     eax, ebx
0x1800da6ff  jb      short loc_1800DA70D
0x1800da701  add     rax, rax
0x1800da704  cmp     rax, r12
0x1800da707  jbe     loc_1800DA86C
0x1800da70d  mov     ebp, 216h
0x1800da712  jmp     loc_1800DA812
0x1800da717  mov     rbx, rdi
0x1800da71a  mov     r12, rbp
0x1800da71d  test    rdi, rdi
0x1800da720  jz      loc_1800DAD92
0x1800da726  mov     r13d, 1
0x1800da72c  mov     rax, [rsp+0E8h+var_A0]
0x1800da731  mov     rsi, rbp
0x1800da734  test    rax, rax
0x1800da737  jz      loc_1800DAD97
0x1800da73d  mov     [rsp+0E8h+lpUsedDefaultChar], rbp; lpUsedDefaultChar
0x1800da742  mov     r9d, 0FFFFFFFFh; cchWideChar
0x1800da748  mov     [rsp+0E8h+lpDefaultChar], rbp; lpDefaultChar
0x1800da74d  mov     r8, rbx; lpWideCharStr
0x1800da750  mov     [rsp+0E8h+cbMultiByte], ebp; cbMultiByte
0x1800da754  xor     edx, edx; dwFlags
0x1800da756  mov     ecx, 0FDE9h; CodePage
0x1800da75b  mov     qword ptr [rsp+0E8h+cchASCIIChar], rbp; lpMultiByteStr
0x1800da760  call    cs:__imp_WideCharToMultiByte
0x1800da766  mov     r14d, eax
0x1800da769  test    eax, eax
0x1800da76b  jz      loc_1800DABDF
0x1800da771  mov     eax, 0FFFFFFFFh
0x1800da776  mov     r15d, r14d
0x1800da779  add     r14d, eax
0x1800da77c  mov     rax, [rsp+0E8h+var_A8]
0x1800da781  test    rax, rax
0x1800da784  jz      loc_1800DAA8C
0x1800da78a  mov     rax, [rax]
0x1800da78d  test    rax, rax
0x1800da790  jnz     loc_1800DAB9E
0x1800da796  mov     rcx, cs:g_hWxProcessHeap; hHeap
0x1800da79d  mov     r8d, r15d; dwBytes
0x1800da7a0  xor     edx, edx; dwFlags
0x1800da7a2  call    cs:__imp_HeapAlloc
0x1800da7a8  mov     rsi, rax
0x1800da7ab  test    rax, rax
0x1800da7ae  jz      loc_1800DAC05
0x1800da7b4  xor     edx, edx; dwFlags
0x1800da7b6  mov     r9d, 0FFFFFFFFh; cchWideChar
0x1800da7bc  mov     [rsp+0E8h+lpUsedDefaultChar], rdx; lpUsedDefaultChar
0x1800da7c1  mov     r8, rbx; lpWideCharStr
0x1800da7c4  mov     [rsp+0E8h+lpDefaultChar], rdx; lpDefaultChar
0x1800da7c9  mov     ecx, 0FDE9h; CodePage
0x1800da7ce  mov     [rsp+0E8h+cbMultiByte], r15d; cbMultiByte
0x1800da7d3  mov     qword ptr [rsp+0E8h+cchASCIIChar], rax; lpMultiByteStr
0x1800da7d8  call    cs:__imp_WideCharToMultiByte
0x1800da7de  test    eax, eax
0x1800da7e0  jz      loc_1800DAA6D
0x1800da7e6  mov     rax, [rsp+0E8h+var_A0]
0x1800da7eb  mov     byte ptr [r14+rsi], 0
0x1800da7f0  mov     [rax], r14d
0x1800da7f3  mov     rax, [rsp+0E8h+var_A8]
0x1800da7f8  mov     [rax], rsi
0x1800da7fb  test    r12, r12
0x1800da7fe  jz      short loc_1800DA812
0x1800da800  mov     rcx, cs:g_hWxProcessHeap; hHeap
0x1800da807  mov     r8, r12; lpMem
0x1800da80a  xor     edx, edx; dwFlags
0x1800da80c  call    cs:__imp_HeapFree
0x1800da812  mov     r15, [rsp+0E8h+var_38]
0x1800da81a  mov     r14, [rsp+0E8h+var_30]
0x1800da822  mov     r13, [rsp+0E8h+var_28]
0x1800da82a  mov     r12, [rsp+0E8h+var_20]
0x1800da832  mov     rsi, [rsp+0E8h+var_18]
0x1800da83a  mov     rbx, [rsp+0E8h+arg_10]
0x1800da842  test    rdi, rdi
0x1800da845  jz      short loc_1800DA850
0x1800da847  mov     rcx, rdi; pv
0x1800da84a  call    cs:__imp_CoTaskMemFree
0x1800da850  mov     eax, ebp
0x1800da852  mov     rcx, [rsp+0E8h+var_40]
0x1800da85a  xor     rcx, rsp; StackCookie
0x1800da85d  call    __security_check_cookie
0x1800da862  add     rsp, 0D8h
0x1800da869  pop     rdi
0x1800da86a  pop     rbp
0x1800da86b  retn
0x1800da86c  mov     rcx, cs:g_hWxProcessHeap; hHeap
0x1800da873  xor     edx, edx; dwFlags
0x1800da875  mov     r8d, eax; dwBytes
0x1800da878  call    cs:__imp_HeapAlloc
0x1800da87e  mov     r12, rax
0x1800da881  test    rax, rax
0x1800da884  jz      loc_1800DACF3
0x1800da88a  mov     r9, rax; lpASCIICharStr
0x1800da88d  mov     [rsp+0E8h+cchASCIIChar], ebx; cchASCIIChar
0x1800da891  mov     r8d, r15d; cchUnicodeChar
0x1800da894  mov     rdx, r14; lpUnicodeCharStr
0x1800da897  xor     ecx, ecx; dwFlags
0x1800da899  call    cs:__imp_IdnToAscii
0x1800da89f  test    eax, eax
0x1800da8a1  jz      loc_1800DACFD
0x1800da8a7  mov     eax, eax
0x1800da8a9  mov     [r12+rax*2], bp
0x1800da8ae  test    r13d, r13d
0x1800da8b1  jz      loc_1800DAD5B
0x1800da8b7  xorps   xmm0, xmm0
0x1800da8ba  mov     [rsp+0E8h+Port], bp
0x1800da8bf  movups  xmmword ptr [rsp+0E8h+var_60.u], xmm0
0x1800da8c7  mov     rbx, r12
0x1800da8ca  movups  xmmword ptr [rsp+0E8h+var_60.u+0Ch], xmm0
0x1800da8d2  movups  xmmword ptr [rsp+58h], xmm0
0x1800da8d7  test    byte ptr cs:xmmword_180266B60+1, 10h
0x1800da8de  jz      short loc_1800DA8FD
0x1800da8e0  mov     edx, 0Ah
0x1800da8e5  mov     [rsp+0E8h+cchASCIIChar], ebp
0x1800da8e9  mov     ecx, 40Ch
0x1800da8ee  lea     r8, WPP_e4a583e537b33e4222dcc118c6822267_Traceguids
0x1800da8f5  mov     r9, rbx
0x1800da8f8  call    WPP_SF_Sd
0x1800da8fd  lea     r9, [rsp+0E8h+Port]; Port
0x1800da902  mov     dl, 1; Strict
0x1800da904  lea     r8, [rsp+0E8h+var_8C]; Address
0x1800da909  mov     rcx, rbx; AddressString
0x1800da90c  call    cs:__imp_RtlIpv4StringToAddressExW
0x1800da912  test    eax, eax
0x1800da914  jz      loc_1800DAD09
0x1800da91a  lea     r9, [rsp+0E8h+var_60.u+2]; Port
0x1800da922  mov     rcx, rbx; AddressString
0x1800da925  lea     r8, [rsp+0E8h+var_48]; ScopeId
0x1800da92d  mov     esi, ebp
0x1800da92f  lea     rdx, [rsp+0E8h+var_60.u+8]; Address
0x1800da937  call    cs:__imp_RtlIpv6StringToAddressExW
0x1800da93d  test    eax, eax
0x1800da93f  jz      loc_1800DAD16
0x1800da945  lea     rdx, qword_180226CB0
0x1800da94c  nop     dword ptr [rax+00h]
0x1800da950  movzx   eax, word ptr [rbx]
0x1800da953  test    ax, ax
0x1800da956  jz      short loc_1800DA976
0x1800da958  lea     ecx, [rax-21h]
0x1800da95b  cmp     cx, 5Dh ; ']'
0x1800da95f  ja      loc_1800DAB93
0x1800da965  test    byte ptr [rax+rdx-21h], 88h
0x1800da96a  jnz     loc_1800DAB93
0x1800da970  add     rbx, 2
0x1800da974  jmp     short loc_1800DA950
0x1800da976  mov     r13d, 1
0x1800da97c  mov     esi, r13d
0x1800da97f  test    byte ptr cs:xmmword_180266B60+1, 40h
0x1800da986  jz      short loc_1800DA9A1
0x1800da988  mov     edx, 0Bh
0x1800da98d  lea     r8, WPP_e4a583e537b33e4222dcc118c6822267_Traceguids
0x1800da994  mov     ecx, 40Eh
0x1800da999  mov     r9d, esi
0x1800da99c  call    WPP_SF_d
0x1800da9a1  test    esi, esi
0x1800da9a3  jz      loc_1800DAD51
0x1800da9a9  mov     rbx, r12
0x1800da9ac  jmp     loc_1800DA72C
0x1800da9b1  test    r14, r14
0x1800da9b4  jz      loc_1800DABF3
0x1800da9ba  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x1800da9c1  cmp     [rcx+rsi*2+2], di
0x1800da9c6  lea     rsi, [rsi+1]
0x1800da9ca  jnz     short loc_1800DA9C1
0x1800da9cc  lea     eax, ds:2[rsi*2]
0x1800da9d3  mov     dword ptr [rsp+0E8h+var_8C.S_un], ebp
0x1800da9d7  mov     ecx, eax; cb
0x1800da9d9  mov     ebp, eax
0x1800da9db  call    cs:__imp_CoTaskMemAlloc
0x1800da9e1  mov     rbx, rax
0x1800da9e4  test    rax, rax
0x1800da9e7  jz      loc_1800DAB05
0x1800da9ed  mov     r8d, ebp; Size
0x1800da9f0  xor     edx, edx; Val
0x1800da9f2  mov     rcx, rax; void *
0x1800da9f5  call    memset_0
0x1800da9fa  lea     eax, [rsi+1]
0x1800da9fd  mov     r9d, eax
0x1800daa00  test    eax, eax
0x1800daa02  mov     rax, rbx
0x1800daa05  jz      loc_1800DAC78
0x1800daa0b  cmp     r9, 7FFFFFFFh
  ... truncated ...
```
