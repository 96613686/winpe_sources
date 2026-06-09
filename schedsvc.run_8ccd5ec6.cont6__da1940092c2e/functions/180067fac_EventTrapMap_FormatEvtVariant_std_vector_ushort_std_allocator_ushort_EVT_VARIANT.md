# EventTrapMap::FormatEvtVariant(std::vector<ushort,std::allocator<ushort>> &,_EVT_VARIANT *)

- ea: `0x180067fac`
- end: `0x1800685db`
- name: `?FormatEvtVariant@EventTrapMap@@CAJAEAV?$vector@GV?$allocator@G@std@@@std@@PEAU_EVT_VARIANT@@@Z`
- size: `1583`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002dd30`

## callees

- `0x180001e10`
- `0x180027910`
- `0x1800678cc`
- `0x180067fac`
- `0x180068ab4`
- `0x180069214`
- `0x180069290`
- `0x180082a40`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180068299`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180068299`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180068289`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180068289`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180068086`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800680c1`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800684e8`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180068551`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180068086`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800680c1`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800684e8`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180068551`
- `RPCRT4!UuidToStringW` at `0x180068323`
- `RPCRT4!UuidToStringW` at `0x180068323`
- `RPCRT4!RpcStringFreeW` at `0x18006835f`
- `RPCRT4!RpcStringFreeW` at `0x18006835f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180068238`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180068238`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800681fc`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800681fc`

## pseudocode

```c
// Hidden C++ exception states: #try_helpers=1
signed int __fastcall EventTrapMap::FormatEvtVariant(__int64 a1, LPCCH *a2)
{
  __int64 v3; // rdi
  unsigned int v4; // r13d
  int v5; // ebx
  unsigned __int64 cchWideChar; // r15
  unsigned int v7; // eax
  unsigned int v8; // eax
  unsigned int v9; // eax
  unsigned int v10; // eax
  unsigned int v11; // eax
  int v12; // eax
  int v13; // eax
  const unsigned __int16 *v14; // rdx
  __int64 v15; // rsi
  unsigned int v16; // eax
  unsigned int v17; // eax
  unsigned int v18; // eax
  double v19; // xmm2_8
  unsigned int v20; // eax
  unsigned int v21; // eax
  unsigned int v22; // eax
  unsigned int v23; // eax
  unsigned int v24; // eax
  unsigned int v25; // eax
  unsigned int v26; // eax
  unsigned int v27; // eax
  CHAR *v28; // rcx
  __int64 v29; // rsi
  unsigned __int16 *v30; // r8
  int wMilliseconds; // eax
  int wSecond; // ecx
  int wMinute; // edx
  int wHour; // r10d
  int wDay; // r11d
  __int64 wMonth; // r9
  __int64 wYear; // r8
  signed int result; // eax
  __int64 v39; // rsi
  unsigned int v40; // ecx
  __int64 v41; // rsi
  __int64 v42; // rax
  WCHAR *lpWideCharStr; // r12
  const unsigned __int16 *v44; // r8
  unsigned int v45; // r12d
  const CHAR *v46; // r8
  _WORD v47[2]; // [rsp+50h] [rbp-58h] BYREF
  int v48; // [rsp+54h] [rbp-54h]
  LPWSTR StringSid; // [rsp+58h] [rbp-50h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+60h] [rbp-48h] BYREF

  v3 = a1;
  v4 = 0;
  v5 = 0;
  v48 = 0;
  cchWideChar = 0;
  v7 = *((_DWORD *)a2 + 3);
  if ( v7 > 0x81 )
  {
    if ( v7 != 130 )
      goto LABEL_22;
    std::vector<unsigned short>::resize(a1, 0);
    v47[0] = 0;
    std::vector<unsigned short>::push_back(v3, v47);
    v45 = 0;
    if ( !*((_DWORD *)a2 + 2) )
      goto LABEL_90;
    v41 = -1;
    do
      cchWideChar += MultiByteToWideChar(0, 0, *(LPCCH *)&(*a2)[8 * v45++], -1, 0, 0) + 1;
    while ( v45 < *((_DWORD *)a2 + 2) );
    if ( cchWideChar <= 2 )
      goto LABEL_90;
    lpWideCharStr = (WCHAR *)operator new(saturated_mul(cchWideChar, 2u));
    *lpWideCharStr = 0;
    if ( *((_DWORD *)a2 + 2) )
    {
      do
      {
        v46 = *(const CHAR **)&(*a2)[8 * v4];
        if ( v46 )
        {
          MultiByteToWideChar(0, 0, v46, -1, lpWideCharStr, cchWideChar);
          if ( v4 < *((_DWORD *)a2 + 2) - 1 )
            StringCchCatW(lpWideCharStr, cchWideChar, L",");
        }
        ++v4;
      }
      while ( v4 < *((_DWORD *)a2 + 2) );
    }
    do
      ++v41;
    while ( lpWideCharStr[v41] );
LABEL_77:
    std::vector<unsigned short>::assign<unsigned short *>(v3, lpWideCharStr, &lpWideCharStr[v41 + 1]);
    return v5;
  }
  if ( v7 == 129 )
  {
    std::vector<unsigned short>::resize(a1, 0);
    v47[0] = 0;
    std::vector<unsigned short>::push_back(v3, v47);
    if ( !*((_DWORD *)a2 + 2) )
      goto LABEL_90;
    v40 = 0;
    v41 = -1;
    do
    {
      v42 = -1;
      do
        ++v42;
      while ( *(_WORD *)(*(_QWORD *)&(*a2)[8 * v40] + 2 * v42) );
      cchWideChar += v42 + 1;
      ++v40;
    }
    while ( v40 < *((_DWORD *)a2 + 2) );
    if ( cchWideChar <= 2 )
      goto LABEL_90;
    lpWideCharStr = (WCHAR *)operator new(saturated_mul(cchWideChar, 2u));
    *lpWideCharStr = 0;
    if ( *((_DWORD *)a2 + 2) )
    {
      do
      {
        v44 = *(const unsigned __int16 **)&(*a2)[8 * v4];
        if ( v44 )
        {
          StringCchCatW(lpWideCharStr, cchWideChar, v44);
          if ( v4 < *((_DWORD *)a2 + 2) - 1 )
            StringCchCatW(lpWideCharStr, cchWideChar, L",");
        }
        ++v4;
      }
      while ( v4 < *((_DWORD *)a2 + 2) );
    }
    do
      ++v41;
    while ( lpWideCharStr[v41] );
    goto LABEL_77;
  }
  if ( v7 <= 0xB )
  {
    if ( v7 != 11 )
    {
      if ( v7 > 6 )
      {
        v16 = v7 - 7;
        if ( !v16 )
          goto LABEL_15;
        v17 = v16 - 1;
        if ( !v17 )
          goto LABEL_13;
        v18 = v17 - 1;
        if ( !v18 )
        {
          v12 = EventTrapMap::StringPrintf(a1, L"%I64i", *a2);
          goto LABEL_14;
        }
        if ( v18 == 1 )
        {
          v12 = EventTrapMap::StringPrintf(a1, L"%I64u", *a2);
          goto LABEL_14;
        }
        goto LABEL_22;
      }
      if ( v7 == 6 )
        goto LABEL_13;
      v8 = v7 - 1;
      if ( v8 )
      {
        v9 = v8 - 1;
        if ( v9 )
        {
          v10 = v9 - 1;
          if ( v10 )
          {
            v11 = v10 - 1;
            if ( v11 )
            {
              if ( v11 == 1 )
                goto LABEL_15;
              goto LABEL_22;
            }
LABEL_13:
            v12 = EventTrapMap::StringPrintf(a1, L"%u");
LABEL_14:
            v5 = v12;
            v48 = v12;
            return v5;
          }
LABEL_15:
          v12 = EventTrapMap::StringPrintf(a1, L"%i");
          goto LABEL_14;
        }
        v13 = MultiByteToWideChar(0, 0, *a2, -1, 0, 0);
        a1 = v3;
        if ( v13 )
        {
          std::vector<unsigned short>::resize(v3, v13);
          MultiByteToWideChar(0, 0, *a2, -1, *(LPWSTR *)v3, (__int64)(*(_QWORD *)(v3 + 8) - *(_QWORD *)v3) >> 1);
          return v5;
        }
LABEL_22:
        std::vector<unsigned short>::resize(a1, 0);
LABEL_90:
        v47[0] = 0;
        std::vector<unsigned short>::push_back(v3, v47);
        return v5;
      }
      v14 = (const unsigned __int16 *)*a2;
      if ( !v14 )
        goto LABEL_22;
      v15 = -1;
      do
        ++v15;
      while ( v14[v15] );
LABEL_63:
      std::vector<unsigned short>::assign<unsigned short *>(a1, v14, &v14[v15 + 1]);
      return v5;
    }
    v19 = *(float *)a2;
LABEL_30:
    v12 = EventTrapMap::StringPrintf(a1, L"%f", v19);
    goto LABEL_14;
  }
  v20 = v7 - 12;
  if ( !v20 )
  {
    v19 = *(double *)a2;
    goto LABEL_30;
  }
  v21 = v20 - 1;
  if ( !v21 )
  {
    v14 = L"true";
    if ( !*(_DWORD *)a2 )
      v14 = L"false";
    v15 = -1;
    do
      ++v15;
    while ( v14[v15] );
    goto LABEL_63;
  }
  v22 = v21 - 2;
  if ( !v22 )
  {
    StringSid = 0;
    result = UuidToStringW((const UUID *)*a2, &StringSid);
    if ( result )
      return result;
    v39 = -1;
    do
      ++v39;
    while ( StringSid[v39] );
    std::vector<unsigned short>::assign<unsigned short *>(v3, StringSid, &StringSid[v39 + 1]);
    RpcStringFreeW(&StringSid);
    return v5;
  }
  v23 = v22 - 1;
  if ( !v23 )
  {
    v12 = EventTrapMap::StringPrintf(a1, L"%u", *a2);
    goto LABEL_14;
  }
  v24 = v23 - 1;
  if ( v24 )
  {
    v25 = v24 - 1;
    if ( v25 )
    {
      v26 = v25 - 1;
      if ( !v26 )
      {
        v28 = (CHAR *)*a2;
        if ( *a2 )
        {
          StringSid = 0;
          if ( ConvertSidToStringSidW(v28, &StringSid) )
          {
            v29 = -1;
            do
              ++v29;
            while ( StringSid[v29] );
            std::vector<unsigned short>::assign<unsigned short *>(v3, StringSid, &StringSid[v29 + 1]);
            LocalFree(StringSid);
          }
        }
        return v5;
      }
      v27 = v26 - 1;
      if ( !v27 )
      {
        v12 = EventTrapMap::StringPrintf(a1, L"0x%X");
        goto LABEL_14;
      }
      if ( v27 == 1 )
      {
        v12 = EventTrapMap::StringPrintf(a1, L"0x%I64X", *a2);
        goto LABEL_14;
      }
      goto LABEL_22;
    }
    v30 = (unsigned __int16 *)*a2;
    if ( !*a2 )
      return v5;
    wMilliseconds = v30[7];
    wSecond = v30[6];
    wMinute = v30[5];
    wHour = v30[4];
    wDay = v30[3];
    wMonth = v30[1];
    wYear = *v30;
LABEL_53:
    v12 = EventTrapMap::StringPrintf(
            v3,
            L"%4.4hd-%2.2hd-%2.2hdT%2.2hd:%2.2hd:%2.2hd.%3.3hdZ",
            wYear,
            wMonth,
            wDay,
            wHour,
            wMinute,
            wSecond,
            wMilliseconds);
    goto LABEL_14;
  }
  SystemTime = 0;
  if ( FileTimeToSystemTime((const FILETIME *)a2, &SystemTime) )
  {
    wMilliseconds = SystemTime.wMilliseconds;
    wSecond = SystemTime.wSecond;
    wMinute = SystemTime.wMinute;
    wHour = SystemTime.wHour;
    wDay = SystemTime.wDay;
    wMonth = SystemTime.wMonth;
    wYear = SystemTime.wYear;
    goto LABEL_53;
  }
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180067fac  mov     [rsp+arg_10], rbx
0x180067fb1  mov     [rsp+arg_18], rsi
0x180067fb6  push    rdi
0x180067fb7  push    r12
0x180067fb9  push    r13
0x180067fbb  push    r14
0x180067fbd  push    r15
0x180067fbf  sub     rsp, 80h
0x180067fc6  mov     rax, cs:__security_cookie
0x180067fcd  xor     rax, rsp
0x180067fd0  mov     [rsp+0A8h+var_38], rax
0x180067fd5  mov     r14, rdx
0x180067fd8  mov     rdi, rcx
0x180067fdb  xor     r13d, r13d
0x180067fde  mov     ebx, r13d
0x180067fe1  mov     [rsp+0A8h+var_54], ebx
0x180067fe5  mov     r15d, r13d
0x180067fe8  mov     eax, [rdx+0Ch]
0x180067feb  mov     ecx, 81h
0x180067ff0  cmp     eax, ecx
0x180067ff2  ja      loc_180068494
0x180067ff8  jz      loc_1800683B1
0x180067ffe  cmp     eax, 0Bh
0x180068001  ja      loc_18006817F
0x180068007  jz      loc_18006815F
0x18006800d  cmp     eax, 6
0x180068010  ja      loc_180068118
0x180068016  jz      loc_18006810F
0x18006801c  sub     eax, 1
0x18006801f  jz      loc_1800680D2
0x180068025  sub     eax, 1
0x180068028  jz      short loc_18006806E
0x18006802a  sub     eax, 1
0x18006802d  jz      short loc_180068061
0x18006802f  sub     eax, 1
0x180068032  jz      short loc_180068043
0x180068034  cmp     eax, 1
0x180068037  jnz     loc_1800680ED
0x18006803d  movsx   r8d, word ptr [rdx]
0x180068041  jmp     short loc_180068065
0x180068043  movzx   r8d, byte ptr [rdx]
0x180068047  lea     rdx, aU; "%u"
0x18006804e  mov     rcx, rdi
0x180068051  call    ?StringPrintf@EventTrapMap@@CAJAEAV?$vector@GV?$allocator@G@std@@@std@@PEBGZZ; EventTrapMap::StringPrintf(std::vector<ushort> &,ushort const *,...)
0x180068056  mov     ebx, eax
0x180068058  mov     [rsp+0A8h+var_54], eax
0x18006805c  jmp     loc_1800685A8
0x180068061  movsx   r8d, byte ptr [rdx]
0x180068065  lea     rdx, aI; "%i"
0x18006806c  jmp     short loc_18006804E
0x18006806e  mov     [rsp+0A8h+cchWideChar], r13d; cchWideChar
0x180068073  mov     [rsp+0A8h+lpWideCharStr], r13; lpWideCharStr
0x180068078  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18006807c  mov     r9d, esi; cbMultiByte
0x18006807f  mov     r8, [rdx]; lpMultiByteStr
0x180068082  xor     edx, edx; dwFlags
0x180068084  xor     ecx, ecx; CodePage
0x180068086  call    cs:__imp_MultiByteToWideChar
0x18006808d  nop     dword ptr [rax+rax+00h]
0x180068092  mov     rcx, rdi
0x180068095  test    eax, eax
0x180068097  jz      short loc_1800680F0
0x180068099  movsxd  rdx, eax
0x18006809c  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x1800680a1  mov     rcx, [rdi]
0x1800680a4  mov     rax, [rdi+8]
0x1800680a8  sub     rax, rcx
0x1800680ab  sar     rax, 1
0x1800680ae  mov     [rsp+0A8h+cchWideChar], eax; cchWideChar
0x1800680b2  mov     [rsp+0A8h+lpWideCharStr], rcx; lpWideCharStr
0x1800680b7  mov     r9d, esi; cbMultiByte
0x1800680ba  mov     r8, [r14]; lpMultiByteStr
0x1800680bd  xor     edx, edx; dwFlags
0x1800680bf  xor     ecx, ecx; CodePage
0x1800680c1  call    cs:__imp_MultiByteToWideChar
0x1800680c8  nop     dword ptr [rax+rax+00h]
0x1800680cd  jmp     loc_1800685A8
0x1800680d2  mov     rdx, [rdx]
0x1800680d5  test    rdx, rdx
0x1800680d8  jz      short loc_1800680ED
0x1800680da  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800680de  inc     rsi
0x1800680e1  cmp     [rdx+rsi*2], r13w
0x1800680e6  jnz     short loc_1800680DE
0x1800680e8  jmp     loc_180068393
0x1800680ed  mov     rcx, rdi
0x1800680f0  xor     edx, edx
0x1800680f2  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x1800680f7  mov     [rsp+0A8h+var_58], r13w
0x1800680fd  lea     rdx, [rsp+0A8h+var_58]
0x180068102  mov     rcx, rdi
0x180068105  call    ?push_back@?$vector@GV?$allocator@G@std@@@std@@QEAAX$$QEAG@Z; std::vector<ushort>::push_back(ushort &&)
0x18006810a  jmp     loc_1800683A3
0x18006810f  movzx   r8d, word ptr [rdx]
0x180068113  jmp     loc_180068047
0x180068118  sub     eax, 7
0x18006811b  jz      short loc_180068157
0x18006811d  sub     eax, 1
0x180068120  jz      short loc_18006814F
0x180068122  sub     eax, 1
0x180068125  jz      short loc_180068143
0x180068127  cmp     eax, 1
0x18006812a  jnz     short loc_1800680ED
0x18006812c  mov     r8, [rdx]
0x18006812f  lea     rdx, aI64u; "%I64u"
0x180068136  mov     rcx, rdi
0x180068139  call    ?StringPrintf@EventTrapMap@@CAJAEAV?$vector@GV?$allocator@G@std@@@std@@PEBGZZ; EventTrapMap::StringPrintf(std::vector<ushort> &,ushort const *,...)
0x18006813e  jmp     loc_180068056
0x180068143  mov     r8, [rdx]
0x180068146  lea     rdx, aI64i; "%I64i"
0x18006814d  jmp     short loc_180068136
0x18006814f  mov     r8d, [rdx]
0x180068152  jmp     loc_180068047
0x180068157  mov     r8d, [rdx]
0x18006815a  jmp     loc_180068065
0x18006815f  movss   xmm2, dword ptr [rdx]
0x180068163  cvtps2pd xmm2, xmm2
0x180068166  movq    r8, xmm2
0x18006816b  lea     rdx, asc_1800AAE44; "%f"
0x180068172  mov     rcx, rdi
0x180068175  call    ?StringPrintf@EventTrapMap@@CAJAEAV?$vector@GV?$allocator@G@std@@@std@@PEBGZZ; EventTrapMap::StringPrintf(std::vector<ushort> &,ushort const *,...)
0x18006817a  jmp     loc_180068056
0x18006817f  sub     eax, 0Ch
0x180068182  jz      loc_1800683A8
0x180068188  sub     eax, 1
0x18006818b  jz      loc_180068370
0x180068191  sub     eax, 2
0x180068194  jz      loc_180068316
0x18006819a  sub     eax, 1
0x18006819d  jz      loc_180068307
0x1800681a3  sub     eax, 1
0x1800681a6  jz      loc_180068279
0x1800681ac  sub     eax, 1
0x1800681af  jz      loc_180068249
0x1800681b5  sub     eax, 1
0x1800681b8  jz      short loc_1800681E6
0x1800681ba  sub     eax, 1
0x1800681bd  jz      short loc_1800681D7
0x1800681bf  cmp     eax, 1
0x1800681c2  jnz     loc_1800680ED
0x1800681c8  mov     r8, [rdx]
0x1800681cb  lea     rdx, a0xI64x; "0x%I64X"
0x1800681d2  jmp     loc_180068136
0x1800681d7  mov     r8d, [rdx]
0x1800681da  lea     rdx, a0xX; "0x%X"
0x1800681e1  jmp     loc_18006804E
0x1800681e6  mov     rcx, [rdx]; Sid
0x1800681e9  test    rcx, rcx
0x1800681ec  jz      loc_1800685A8
0x1800681f2  mov     [rsp+0A8h+StringSid], r13
0x1800681f7  lea     rdx, [rsp+0A8h+StringSid]; StringSid
0x1800681fc  call    cs:__imp_ConvertSidToStringSidW
0x180068203  nop     dword ptr [rax+rax+00h]
0x180068208  test    eax, eax
0x18006820a  jz      loc_1800685A8
0x180068210  mov     rdx, [rsp+0A8h+StringSid]
0x180068215  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180068219  inc     rsi
0x18006821c  cmp     [rdx+rsi*2], r13w
0x180068221  jnz     short loc_180068219
0x180068223  lea     r8, [rdx+2]
0x180068227  lea     r8, [r8+rsi*2]
0x18006822b  mov     rcx, rdi
0x18006822e  call    ??$assign@PEAG@?$vector@GV?$allocator@G@std@@@std@@QEAAXPEAG0@Z; std::vector<ushort>::assign<ushort *>(ushort *,ushort *)
0x180068233  mov     rcx, [rsp+0A8h+StringSid]; hMem
0x180068238  call    cs:__imp_LocalFree
0x18006823f  nop     dword ptr [rax+rax+00h]
0x180068244  jmp     loc_1800685A8
0x180068249  mov     r8, [rdx]
0x18006824c  test    r8, r8
0x18006824f  jz      loc_1800685A8
0x180068255  movzx   eax, word ptr [r8+0Eh]
0x18006825a  movzx   ecx, word ptr [r8+0Ch]
0x18006825f  movzx   edx, word ptr [r8+0Ah]
0x180068264  movzx   r10d, word ptr [r8+8]
0x180068269  movzx   r11d, word ptr [r8+6]
0x18006826e  movzx   r9d, word ptr [r8+2]
0x180068273  movzx   r8d, word ptr [r8]
0x180068277  jmp     short loc_1800682DD
0x180068279  xorps   xmm0, xmm0
0x18006827c  movups  xmmword ptr [rsp+0A8h+SystemTime.wYear], xmm0
0x180068281  lea     rdx, [rsp+0A8h+SystemTime]; lpSystemTime
0x180068286  mov     rcx, r14; lpFileTime
0x180068289  call    cs:__imp_FileTimeToSystemTime
0x180068290  nop     dword ptr [rax+rax+00h]
0x180068295  test    eax, eax
0x180068297  jnz     short loc_1800682B6
0x180068299  call    cs:__imp_GetLastError
0x1800682a0  nop     dword ptr [rax+rax+00h]
0x1800682a5  test    eax, eax
0x1800682a7  jle     short loc_1800682B1
0x1800682a9  movzx   eax, ax
0x1800682ac  or      eax, 80070000h
0x1800682b1  jmp     loc_1800685B0
0x1800682b6  movzx   eax, [rsp+0A8h+SystemTime.wMilliseconds]
0x1800682bb  movzx   ecx, [rsp+0A8h+SystemTime.wSecond]
0x1800682c0  movzx   edx, [rsp+0A8h+SystemTime.wMinute]
0x1800682c5  movzx   r10d, [rsp+0A8h+SystemTime.wHour]
0x1800682cb  movzx   r11d, [rsp+0A8h+SystemTime.wDay]
0x1800682d1  movzx   r9d, [rsp+0A8h+SystemTime.wMonth]
0x1800682d7  movzx   r8d, [rsp+0A8h+SystemTime.wYear]
0x1800682dd  mov     [rsp+0A8h+var_68], eax
0x1800682e1  mov     [rsp+0A8h+var_70], ecx
0x1800682e5  mov     [rsp+0A8h+var_78], edx
0x1800682e9  mov     [rsp+0A8h+cchWideChar], r10d
0x1800682ee  mov     dword ptr [rsp+0A8h+lpWideCharStr], r11d
0x1800682f3  lea     rdx, a44hd22hd22hdt2; "%4.4hd-%2.2hd-%2.2hdT%2.2hd:%2.2hd:%2.2"...
0x1800682fa  mov     rcx, rdi
0x1800682fd  call    ?StringPrintf@EventTrapMap@@CAJAEAV?$vector@GV?$allocator@G@std@@@std@@PEBGZZ; EventTrapMap::StringPrintf(std::vector<ushort> &,ushort const *,...)
0x180068302  jmp     loc_180068056
0x180068307  mov     r8, [rdx]
0x18006830a  lea     rdx, aU; "%u"
0x180068311  jmp     loc_180068136
0x180068316  mov     [rsp+0A8h+StringSid], r13
0x18006831b  lea     rdx, [rsp+0A8h+StringSid]; StringUuid
0x180068320  mov     rcx, [r14]; Uuid
0x180068323  call    cs:__imp_UuidToStringW
0x18006832a  nop     dword ptr [rax+rax+00h]
0x18006832f  test    eax, eax
0x180068331  jnz     loc_1800685B0
0x180068337  mov     rdx, [rsp+0A8h+StringSid]
0x18006833c  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180068340  inc     rsi
0x180068343  cmp     [rdx+rsi*2], r13w
0x180068348  jnz     short loc_180068340
0x18006834a  lea     r8, [rdx+2]
0x18006834e  lea     r8, [r8+rsi*2]
0x180068352  mov     rcx, rdi
0x180068355  call    ??$assign@PEAG@?$vector@GV?$allocator@G@std@@@std@@QEAAXPEAG0@Z; std::vector<ushort>::assign<ushort *>(ushort *,ushort *)
0x18006835a  lea     rcx, [rsp+0A8h+StringSid]; String
0x18006835f  call    cs:__imp_RpcStringFreeW
0x180068366  nop     dword ptr [rax+rax+00h]
0x18006836b  jmp     loc_1800685A8
0x180068370  lea     rax, aFalse; "false"
0x180068377  lea     rdx, aTrue; "true"
0x18006837e  cmp     [r14], r13d
0x180068381  cmovz   rdx, rax
0x180068385  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180068389  inc     rsi
0x18006838c  cmp     [rdx+rsi*2], r13w
0x180068391  jnz     short loc_180068389
0x180068393  lea     r8, [rdx+2]
0x180068397  lea     r8, [r8+rsi*2]
0x18006839b  mov     rcx, rdi
0x18006839e  call    ??$assign@PEAG@?$vector@GV?$allocator@G@std@@@std@@QEAAXPEAG0@Z; std::vector<ushort>::assign<ushort *>(ushort *,ushort *)
0x1800683a3  jmp     loc_1800685A8
0x1800683a8  movsd   xmm2, qword ptr [rdx]
0x1800683ac  jmp     loc_180068166
0x1800683b1  xor     edx, edx
0x1800683b3  mov     rcx, rdi
0x1800683b6  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x1800683bb  mov     [rsp+0A8h+var_58], r13w
0x1800683c1  lea     rdx, [rsp+0A8h+var_58]
0x1800683c6  mov     rcx, rdi
0x1800683c9  call    ?push_back@?$vector@GV?$allocator@G@std@@@std@@QEAAX$$QEAG@Z; std::vector<ushort>::push_back(ushort &&)
0x1800683ce  cmp     [r14+8], r13d
0x1800683d2  jbe     loc_1800680F7
0x1800683d8  mov     ecx, r13d
0x1800683db  mov     r8, [r14]
0x1800683de  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800683e2  mov     eax, ecx
0x1800683e4  mov     rdx, [r8+rax*8]
0x1800683e8  mov     rax, rsi
0x1800683eb  inc     rax
0x1800683ee  cmp     [rdx+rax*2], r13w
0x1800683f3  jnz     short loc_1800683EB
0x1800683f5  inc     r15
0x1800683f8  add     r15, rax
0x1800683fb  inc     ecx
0x1800683fd  cmp     ecx, [r14+8]
0x180068401  jb      short loc_1800683E2
0x180068403  cmp     r15, 2
0x180068407  jbe     loc_1800680F7
0x18006840d  mov     eax, 2
0x180068412  mul     r15
0x180068415  cmovb   rax, rsi
0x180068419  mov     rcx, rax; dwBytes
0x18006841c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180068421  mov     r12, rax
0x180068424  mov     [rax], r13w
0x180068428  xor     edx, edx
0x18006842a  cmp     [r14+8], edx
0x18006842e  jbe     short loc_180068472
0x180068430  mov     ecx, r13d
0x180068433  mov     rax, [r14]
0x180068436  mov     r8, [rax+rcx*8]; unsigned __int16 *
0x18006843a  test    r8, r8
0x18006843d  jz      short loc_180068469
0x18006843f  mov     rdx, r15; unsigned __int64
0x180068442  mov     rcx, r12; unsigned __int16 *
0x180068445  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18006844a  mov     eax, [r14+8]
0x18006844e  dec     eax
0x180068450  cmp     r13d, eax
0x180068453  jnb     short loc_180068467
0x180068455  lea     r8, asc_1800AADF4; ","
0x18006845c  mov     rdx, r15; unsigned __int64
0x18006845f  mov     rcx, r12; unsigned __int16 *
0x180068462  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180068467  xor     edx, edx
  ... truncated ...
```
