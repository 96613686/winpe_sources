# EventTrapMap::FormatEvtVariant(std::vector<ushort,std::allocator<ushort>> &,_EVT_VARIANT *)

- ea: `0x180064ec0`
- end: `0x1800654b3`
- name: `?FormatEvtVariant@EventTrapMap@@CAJAEAV?$vector@GV?$allocator@G@std@@@std@@PEAU_EVT_VARIANT@@@Z`
- size: `1523`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800329cc`

## callees

- `0x18002ae80`
- `0x180030f80`
- `0x180064824`
- `0x180064ec0`
- `0x180065944`
- `0x180066090`
- `0x18006610c`
- `0x18007e6d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006518f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006518f`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180065185`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180065185`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180064f9a`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180064fcf`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800653cc`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18006542f`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180064f9a`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180064fcf`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800653cc`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18006542f`
- `RPCRT4!UuidToStringW` at `0x180065213`
- `RPCRT4!UuidToStringW` at `0x180065213`
- `RPCRT4!RpcStringFreeW` at `0x180065249`
- `RPCRT4!RpcStringFreeW` at `0x180065249`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006513a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006513a`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180065104`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180065104`

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
0x180064ec0  mov     [rsp+arg_10], rbx
0x180064ec5  mov     [rsp+arg_18], rsi
0x180064eca  push    rdi
0x180064ecb  push    r12
0x180064ecd  push    r13
0x180064ecf  push    r14
0x180064ed1  push    r15
0x180064ed3  sub     rsp, 80h
0x180064eda  mov     rax, cs:__security_cookie
0x180064ee1  xor     rax, rsp
0x180064ee4  mov     [rsp+0A8h+var_38], rax
0x180064ee9  mov     r14, rdx
0x180064eec  mov     rdi, rcx
0x180064eef  xor     r13d, r13d
0x180064ef2  mov     ebx, r13d
0x180064ef5  mov     [rsp+0A8h+var_54], ebx
0x180064ef9  mov     r15d, r13d
0x180064efc  mov     eax, [rdx+0Ch]
0x180064eff  mov     ecx, 81h
0x180064f04  cmp     eax, ecx
0x180064f06  ja      loc_180065378
0x180064f0c  jz      loc_180065295
0x180064f12  cmp     eax, 0Bh
0x180064f15  ja      loc_180065087
0x180064f1b  jz      loc_180065067
0x180064f21  cmp     eax, 6
0x180064f24  ja      loc_180065020
0x180064f2a  jz      loc_180065017
0x180064f30  sub     eax, 1
0x180064f33  jz      loc_180064FDA
0x180064f39  sub     eax, 1
0x180064f3c  jz      short loc_180064F82
0x180064f3e  sub     eax, 1
0x180064f41  jz      short loc_180064F75
0x180064f43  sub     eax, 1
0x180064f46  jz      short loc_180064F57
0x180064f48  cmp     eax, 1
0x180064f4b  jnz     loc_180064FF5
0x180064f51  movsx   r8d, word ptr [rdx]
0x180064f55  jmp     short loc_180064F79
0x180064f57  movzx   r8d, byte ptr [rdx]
0x180064f5b  lea     rdx, aU; "%u"
0x180064f62  mov     rcx, rdi
0x180064f65  call    ?StringPrintf@EventTrapMap@@CAJAEAV?$vector@GV?$allocator@G@std@@@std@@PEBGZZ; EventTrapMap::StringPrintf(std::vector<ushort> &,ushort const *,...)
0x180064f6a  mov     ebx, eax
0x180064f6c  mov     [rsp+0A8h+var_54], eax
0x180064f70  jmp     loc_180065480
0x180064f75  movsx   r8d, byte ptr [rdx]
0x180064f79  lea     rdx, aI; "%i"
0x180064f80  jmp     short loc_180064F62
0x180064f82  mov     [rsp+0A8h+cchWideChar], r13d; cchWideChar
0x180064f87  mov     [rsp+0A8h+lpWideCharStr], r13; lpWideCharStr
0x180064f8c  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180064f90  mov     r9d, esi; cbMultiByte
0x180064f93  mov     r8, [rdx]; lpMultiByteStr
0x180064f96  xor     edx, edx; dwFlags
0x180064f98  xor     ecx, ecx; CodePage
0x180064f9a  call    cs:__imp_MultiByteToWideChar
0x180064fa0  mov     rcx, rdi
0x180064fa3  test    eax, eax
0x180064fa5  jz      short loc_180064FF8
0x180064fa7  movsxd  rdx, eax
0x180064faa  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x180064faf  mov     rcx, [rdi]
0x180064fb2  mov     rax, [rdi+8]
0x180064fb6  sub     rax, rcx
0x180064fb9  sar     rax, 1
0x180064fbc  mov     [rsp+0A8h+cchWideChar], eax; cchWideChar
0x180064fc0  mov     [rsp+0A8h+lpWideCharStr], rcx; lpWideCharStr
0x180064fc5  mov     r9d, esi; cbMultiByte
0x180064fc8  mov     r8, [r14]; lpMultiByteStr
0x180064fcb  xor     edx, edx; dwFlags
0x180064fcd  xor     ecx, ecx; CodePage
0x180064fcf  call    cs:__imp_MultiByteToWideChar
0x180064fd5  jmp     loc_180065480
0x180064fda  mov     rdx, [rdx]
0x180064fdd  test    rdx, rdx
0x180064fe0  jz      short loc_180064FF5
0x180064fe2  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180064fe6  inc     rsi
0x180064fe9  cmp     [rdx+rsi*2], r13w
0x180064fee  jnz     short loc_180064FE6
0x180064ff0  jmp     loc_180065277
0x180064ff5  mov     rcx, rdi
0x180064ff8  xor     edx, edx
0x180064ffa  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x180064fff  mov     [rsp+0A8h+var_58], r13w
0x180065005  lea     rdx, [rsp+0A8h+var_58]
0x18006500a  mov     rcx, rdi
0x18006500d  call    ?push_back@?$vector@GV?$allocator@G@std@@@std@@QEAAX$$QEAG@Z; std::vector<ushort>::push_back(ushort &&)
0x180065012  jmp     loc_180065287
0x180065017  movzx   r8d, word ptr [rdx]
0x18006501b  jmp     loc_180064F5B
0x180065020  sub     eax, 7
0x180065023  jz      short loc_18006505F
0x180065025  sub     eax, 1
0x180065028  jz      short loc_180065057
0x18006502a  sub     eax, 1
0x18006502d  jz      short loc_18006504B
0x18006502f  cmp     eax, 1
0x180065032  jnz     short loc_180064FF5
0x180065034  mov     r8, [rdx]
0x180065037  lea     rdx, aI64u; "%I64u"
0x18006503e  mov     rcx, rdi
0x180065041  call    ?StringPrintf@EventTrapMap@@CAJAEAV?$vector@GV?$allocator@G@std@@@std@@PEBGZZ; EventTrapMap::StringPrintf(std::vector<ushort> &,ushort const *,...)
0x180065046  jmp     loc_180064F6A
0x18006504b  mov     r8, [rdx]
0x18006504e  lea     rdx, aI64i; "%I64i"
0x180065055  jmp     short loc_18006503E
0x180065057  mov     r8d, [rdx]
0x18006505a  jmp     loc_180064F5B
0x18006505f  mov     r8d, [rdx]
0x180065062  jmp     loc_180064F79
0x180065067  movss   xmm2, dword ptr [rdx]
0x18006506b  cvtps2pd xmm2, xmm2
0x18006506e  movq    r8, xmm2
0x180065073  lea     rdx, asc_1800A6E34; "%f"
0x18006507a  mov     rcx, rdi
0x18006507d  call    ?StringPrintf@EventTrapMap@@CAJAEAV?$vector@GV?$allocator@G@std@@@std@@PEBGZZ; EventTrapMap::StringPrintf(std::vector<ushort> &,ushort const *,...)
0x180065082  jmp     loc_180064F6A
0x180065087  sub     eax, 0Ch
0x18006508a  jz      loc_18006528C
0x180065090  sub     eax, 1
0x180065093  jz      loc_180065254
0x180065099  sub     eax, 2
0x18006509c  jz      loc_180065206
0x1800650a2  sub     eax, 1
0x1800650a5  jz      loc_1800651F7
0x1800650ab  sub     eax, 1
0x1800650ae  jz      loc_180065175
0x1800650b4  sub     eax, 1
0x1800650b7  jz      loc_180065145
0x1800650bd  sub     eax, 1
0x1800650c0  jz      short loc_1800650EE
0x1800650c2  sub     eax, 1
0x1800650c5  jz      short loc_1800650DF
0x1800650c7  cmp     eax, 1
0x1800650ca  jnz     loc_180064FF5
0x1800650d0  mov     r8, [rdx]
0x1800650d3  lea     rdx, a0xI64x; "0x%I64X"
0x1800650da  jmp     loc_18006503E
0x1800650df  mov     r8d, [rdx]
0x1800650e2  lea     rdx, a0xX; "0x%X"
0x1800650e9  jmp     loc_180064F62
0x1800650ee  mov     rcx, [rdx]; Sid
0x1800650f1  test    rcx, rcx
0x1800650f4  jz      loc_180065480
0x1800650fa  mov     [rsp+0A8h+StringSid], r13
0x1800650ff  lea     rdx, [rsp+0A8h+StringSid]; StringSid
0x180065104  call    cs:__imp_ConvertSidToStringSidW
0x18006510a  test    eax, eax
0x18006510c  jz      loc_180065480
0x180065112  mov     rdx, [rsp+0A8h+StringSid]
0x180065117  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18006511b  inc     rsi
0x18006511e  cmp     [rdx+rsi*2], r13w
0x180065123  jnz     short loc_18006511B
0x180065125  lea     r8, [rdx+2]
0x180065129  lea     r8, [r8+rsi*2]
0x18006512d  mov     rcx, rdi
0x180065130  call    ??$assign@PEAG@?$vector@GV?$allocator@G@std@@@std@@QEAAXPEAG0@Z; std::vector<ushort>::assign<ushort *>(ushort *,ushort *)
0x180065135  mov     rcx, [rsp+0A8h+StringSid]; hMem
0x18006513a  call    cs:__imp_LocalFree
0x180065140  jmp     loc_180065480
0x180065145  mov     r8, [rdx]
0x180065148  test    r8, r8
0x18006514b  jz      loc_180065480
0x180065151  movzx   eax, word ptr [r8+0Eh]
0x180065156  movzx   ecx, word ptr [r8+0Ch]
0x18006515b  movzx   edx, word ptr [r8+0Ah]
0x180065160  movzx   r10d, word ptr [r8+8]
0x180065165  movzx   r11d, word ptr [r8+6]
0x18006516a  movzx   r9d, word ptr [r8+2]
0x18006516f  movzx   r8d, word ptr [r8]
0x180065173  jmp     short loc_1800651CD
0x180065175  xorps   xmm0, xmm0
0x180065178  movups  xmmword ptr [rsp+0A8h+SystemTime.wYear], xmm0
0x18006517d  lea     rdx, [rsp+0A8h+SystemTime]; lpSystemTime
0x180065182  mov     rcx, r14; lpFileTime
0x180065185  call    cs:__imp_FileTimeToSystemTime
0x18006518b  test    eax, eax
0x18006518d  jnz     short loc_1800651A6
0x18006518f  call    cs:__imp_GetLastError
0x180065195  test    eax, eax
0x180065197  jle     short loc_1800651A1
0x180065199  movzx   eax, ax
0x18006519c  or      eax, 80070000h
0x1800651a1  jmp     loc_180065488
0x1800651a6  movzx   eax, [rsp+0A8h+SystemTime.wMilliseconds]
0x1800651ab  movzx   ecx, [rsp+0A8h+SystemTime.wSecond]
0x1800651b0  movzx   edx, [rsp+0A8h+SystemTime.wMinute]
0x1800651b5  movzx   r10d, [rsp+0A8h+SystemTime.wHour]
0x1800651bb  movzx   r11d, [rsp+0A8h+SystemTime.wDay]
0x1800651c1  movzx   r9d, [rsp+0A8h+SystemTime.wMonth]
0x1800651c7  movzx   r8d, [rsp+0A8h+SystemTime.wYear]
0x1800651cd  mov     [rsp+0A8h+var_68], eax
0x1800651d1  mov     [rsp+0A8h+var_70], ecx
0x1800651d5  mov     [rsp+0A8h+var_78], edx
0x1800651d9  mov     [rsp+0A8h+cchWideChar], r10d
0x1800651de  mov     dword ptr [rsp+0A8h+lpWideCharStr], r11d
0x1800651e3  lea     rdx, a44hd22hd22hdt2; "%4.4hd-%2.2hd-%2.2hdT%2.2hd:%2.2hd:%2.2"...
0x1800651ea  mov     rcx, rdi
0x1800651ed  call    ?StringPrintf@EventTrapMap@@CAJAEAV?$vector@GV?$allocator@G@std@@@std@@PEBGZZ; EventTrapMap::StringPrintf(std::vector<ushort> &,ushort const *,...)
0x1800651f2  jmp     loc_180064F6A
0x1800651f7  mov     r8, [rdx]
0x1800651fa  lea     rdx, aU; "%u"
0x180065201  jmp     loc_18006503E
0x180065206  mov     [rsp+0A8h+StringSid], r13
0x18006520b  lea     rdx, [rsp+0A8h+StringSid]; StringUuid
0x180065210  mov     rcx, [r14]; Uuid
0x180065213  call    cs:__imp_UuidToStringW
0x180065219  test    eax, eax
0x18006521b  jnz     loc_180065488
0x180065221  mov     rdx, [rsp+0A8h+StringSid]
0x180065226  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18006522a  inc     rsi
0x18006522d  cmp     [rdx+rsi*2], r13w
0x180065232  jnz     short loc_18006522A
0x180065234  lea     r8, [rdx+2]
0x180065238  lea     r8, [r8+rsi*2]
0x18006523c  mov     rcx, rdi
0x18006523f  call    ??$assign@PEAG@?$vector@GV?$allocator@G@std@@@std@@QEAAXPEAG0@Z; std::vector<ushort>::assign<ushort *>(ushort *,ushort *)
0x180065244  lea     rcx, [rsp+0A8h+StringSid]; String
0x180065249  call    cs:__imp_RpcStringFreeW
0x18006524f  jmp     loc_180065480
0x180065254  lea     rax, aFalse; "false"
0x18006525b  lea     rdx, aTrue; "true"
0x180065262  cmp     [r14], r13d
0x180065265  cmovz   rdx, rax
0x180065269  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18006526d  inc     rsi
0x180065270  cmp     [rdx+rsi*2], r13w
0x180065275  jnz     short loc_18006526D
0x180065277  lea     r8, [rdx+2]
0x18006527b  lea     r8, [r8+rsi*2]
0x18006527f  mov     rcx, rdi
0x180065282  call    ??$assign@PEAG@?$vector@GV?$allocator@G@std@@@std@@QEAAXPEAG0@Z; std::vector<ushort>::assign<ushort *>(ushort *,ushort *)
0x180065287  jmp     loc_180065480
0x18006528c  movsd   xmm2, qword ptr [rdx]
0x180065290  jmp     loc_18006506E
0x180065295  xor     edx, edx
0x180065297  mov     rcx, rdi
0x18006529a  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18006529f  mov     [rsp+0A8h+var_58], r13w
0x1800652a5  lea     rdx, [rsp+0A8h+var_58]
0x1800652aa  mov     rcx, rdi
0x1800652ad  call    ?push_back@?$vector@GV?$allocator@G@std@@@std@@QEAAX$$QEAG@Z; std::vector<ushort>::push_back(ushort &&)
0x1800652b2  cmp     [r14+8], r13d
0x1800652b6  jbe     loc_180064FFF
0x1800652bc  mov     ecx, r13d
0x1800652bf  mov     r8, [r14]
0x1800652c2  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800652c6  mov     eax, ecx
0x1800652c8  mov     rdx, [r8+rax*8]
0x1800652cc  mov     rax, rsi
0x1800652cf  inc     rax
0x1800652d2  cmp     [rdx+rax*2], r13w
0x1800652d7  jnz     short loc_1800652CF
0x1800652d9  inc     r15
0x1800652dc  add     r15, rax
0x1800652df  inc     ecx
0x1800652e1  cmp     ecx, [r14+8]
0x1800652e5  jb      short loc_1800652C6
0x1800652e7  cmp     r15, 2
0x1800652eb  jbe     loc_180064FFF
0x1800652f1  mov     eax, 2
0x1800652f6  mul     r15
0x1800652f9  cmovb   rax, rsi
0x1800652fd  mov     rcx, rax; dwBytes
0x180065300  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180065305  mov     r12, rax
0x180065308  mov     [rax], r13w
0x18006530c  xor     edx, edx
0x18006530e  cmp     [r14+8], edx
0x180065312  jbe     short loc_180065356
0x180065314  mov     ecx, r13d
0x180065317  mov     rax, [r14]
0x18006531a  mov     r8, [rax+rcx*8]; unsigned __int16 *
0x18006531e  test    r8, r8
0x180065321  jz      short loc_18006534D
0x180065323  mov     rdx, r15; unsigned __int64
0x180065326  mov     rcx, r12; unsigned __int16 *
0x180065329  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18006532e  mov     eax, [r14+8]
0x180065332  dec     eax
0x180065334  cmp     r13d, eax
0x180065337  jnb     short loc_18006534B
0x180065339  lea     r8, asc_1800A6DE4; ","
0x180065340  mov     rdx, r15; unsigned __int64
0x180065343  mov     rcx, r12; unsigned __int16 *
0x180065346  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18006534b  xor     edx, edx
0x18006534d  inc     r13d
0x180065350  cmp     r13d, [r14+8]
0x180065354  jb      short loc_180065314
0x180065356  inc     rsi
0x180065359  cmp     [r12+rsi*2], dx
0x18006535e  jnz     short loc_180065356
0x180065360  lea     r8, [rsi+1]
0x180065364  lea     r8, [r12+r8*2]
  ... truncated ...
```
