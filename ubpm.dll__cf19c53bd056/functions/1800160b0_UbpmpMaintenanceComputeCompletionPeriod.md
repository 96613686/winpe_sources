# UbpmpMaintenanceComputeCompletionPeriod

- ea: `0x1800160b0`
- end: `0x180016616`
- name: `UbpmpMaintenanceComputeCompletionPeriod`
- size: `1382`
- prototype: `__int64 __usercall@<rax>(FILETIME *lpFileTime2@<rcx>, FILETIME *lpFileTime@<rdx>, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180014db0`
- `0x18002cd60`

## callees

- `0x1800160b0`
- `0x18003d810`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016353`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016441`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016465`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800165ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016353`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016441`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016465`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800165ed`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180016332`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180016332`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x1800161ff`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x1800162f5`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180016437`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18001650f`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x1800161ff`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x1800162f5`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180016437`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18001650f`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18001623b`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180016307`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18001631d`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180016393`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180016457`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x1800164f1`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x1800165b0`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18001623b`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180016307`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18001631d`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180016393`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180016457`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x1800164f1`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x1800165b0`

## pseudocode

```c
DWORD __fastcall UbpmpMaintenanceComputeCompletionPeriod(
        FILETIME *lpFileTime2,
        FILETIME *lpFileTime,
        __int16 *a3,
        FILETIME *a4,
        FILETIME *a5)
{
  _WORD *v7; // rdi
  unsigned __int16 *v9; // r14
  unsigned __int64 v10; // rdx
  unsigned __int64 v11; // r8
  DWORD result; // eax
  unsigned __int64 v13; // rdx
  unsigned __int64 v14; // r8
  unsigned __int64 v15; // r9
  unsigned __int64 v16; // rdx
  __int16 v17; // r8
  unsigned __int16 *v18; // rdx
  unsigned __int64 v19; // rdx
  unsigned __int64 v20; // rcx
  unsigned __int64 v21; // rdx
  unsigned __int64 v22; // r8
  __int16 v23; // r8
  SYSTEMTIME v24; // xmm0
  unsigned __int64 v25; // rdx
  unsigned __int64 v26; // rcx
  unsigned __int64 v27; // rdx
  unsigned __int64 v28; // r8
  int v29; // r9d
  WORD v30; // r8
  int v31; // r9d
  WORD v32; // cx
  WORD v33; // r8
  FILETIME v34; // [rsp+20h] [rbp-50h] BYREF
  FILETIME FileTime; // [rsp+28h] [rbp-48h] BYREF
  FILETIME FileTime1; // [rsp+30h] [rbp-40h] BYREF
  FILETIME v37; // [rsp+38h] [rbp-38h]
  SYSTEMTIME v38; // [rsp+40h] [rbp-30h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+50h] [rbp-20h] BYREF

  FileTime = 0;
  FileTime1 = 0;
  v7 = a3 + 1;
  SystemTime = 0;
  v38 = 0;
  if ( *(_DWORD *)a3 )
  {
    if ( !FileTimeToSystemTime(lpFileTime, &SystemTime) )
      return GetLastError();
    v9 = (unsigned __int16 *)(a3 + 2);
  }
  else
  {
    v9 = (unsigned __int16 *)(a3 + 2);
    v34 = *lpFileTime;
    v37 = *lpFileTime2;
    v10 = 6048000000000LL * (unsigned __int16)a3[2];
    v11 = v10 + 864000000000LL * (unsigned __int16)a3[3];
    if ( v11 < v10 )
      return 534;
    v13 = v11 + 36000000000LL * (unsigned __int16)a3[4];
    if ( v13 < v11 )
      return 534;
    v14 = v13 + 600000000LL * (unsigned __int16)a3[5];
    if ( v14 < v13 )
      return 534;
    v15 = v14 + 10000000LL * (unsigned __int16)a3[6];
    if ( v15 < v14 )
      return 534;
    v16 = (*(_QWORD *)&v37 - *(_QWORD *)&v34) % v15;
    if ( *(_QWORD *)&v37 - v16 < *(_QWORD *)&v34 )
      return 534;
    v34 = (FILETIME)(*(_QWORD *)&v37 - v16);
    FileTime = (FILETIME)(*(_QWORD *)&v37 - v16);
    if ( !FileTimeToSystemTime(&FileTime, &SystemTime) )
      return GetLastError();
    v7 = a3 + 1;
  }
  v17 = *a3;
  v34 = 0;
  if ( v17 || *v7 )
  {
    v29 = SystemTime.wMonth - 1 + (unsigned __int16)*v7;
    v30 = SystemTime.wYear + v29 / 12 + v17;
    if ( v30 < SystemTime.wYear )
      return 534;
    v38.wYear = v30;
    v38.wDay = SystemTime.wDay;
    v38.wHour = SystemTime.wHour;
    v38.wMinute = SystemTime.wMinute;
    v38.wSecond = SystemTime.wSecond;
    v38.wMilliseconds = SystemTime.wMilliseconds;
    v38.wMonth = v29 % 12 + 1;
    while ( !SystemTimeToFileTime(&v38, &v34) )
    {
      if ( v38.wDay <= 0x1Cu )
        return 87;
      --v38.wDay;
    }
    v18 = (unsigned __int16 *)(a3 + 2);
  }
  else
  {
    if ( !SystemTimeToFileTime(&SystemTime, &v34) )
      goto LABEL_25;
    v18 = v9;
  }
  v19 = *(_QWORD *)&v34 + 6048000000000LL * *v18;
  if ( v19 < *(_QWORD *)&v34 )
    return 534;
  v20 = v19 + 864000000000LL * (unsigned __int16)a3[3];
  if ( v20 < v19 )
    return 534;
  v21 = v20 + 36000000000LL * (unsigned __int16)a3[4];
  if ( v21 < v20 )
    return 534;
  v22 = v21 + 600000000LL * (unsigned __int16)a3[5];
  if ( v22 < v21 || v22 + 10000000LL * (unsigned __int16)a3[6] < v22 )
    return 534;
  v34 = (FILETIME)(v22 + 10000000LL * (unsigned __int16)a3[6]);
  if ( FileTimeToSystemTime(&v34, &v38) )
    goto LABEL_21;
LABEL_25:
  result = GetLastError();
  if ( !result )
  {
LABEL_21:
    while ( SystemTimeToFileTime(&SystemTime, &FileTime) )
    {
      if ( !SystemTimeToFileTime(&v38, &FileTime1) )
        return GetLastError();
      if ( CompareFileTime(&FileTime1, lpFileTime2) >= 0 )
      {
        *a4 = FileTime;
        *a5 = FileTime1;
        return 0;
      }
      v23 = *a3;
      v24 = v38;
      SystemTime = v38;
      v34 = 0;
      if ( v23 || a3[1] )
      {
        v31 = _mm_extract_epi16((__m128i)v38, 1) - 1 + (unsigned __int16)a3[1];
        v32 = _mm_cvtsi128_si32((__m128i)v38);
        v33 = v32 + v31 / 12 + v23;
        if ( v33 < v32 )
          return 534;
        v38.wYear = v33;
        v38.wMonth = v31 % 12 + 1;
        v38.wDay = _mm_extract_epi16((__m128i)v24, 3);
        v38.wHour = _mm_extract_epi16((__m128i)v24, 4);
        v38.wMinute = _mm_extract_epi16((__m128i)v24, 5);
        v38.wSecond = _mm_extract_epi16((__m128i)v24, 6);
        v38.wMilliseconds = _mm_extract_epi16((__m128i)v24, 7);
        while ( !SystemTimeToFileTime(&v38, &v34) )
        {
          if ( v38.wDay <= 0x1Cu )
            return 87;
          --v38.wDay;
        }
      }
      else if ( !SystemTimeToFileTime(&SystemTime, &v34) )
      {
        goto LABEL_36;
      }
      v25 = *(_QWORD *)&v34 + 6048000000000LL * *v9;
      if ( v25 < *(_QWORD *)&v34 )
        return 534;
      v26 = v25 + 864000000000LL * (unsigned __int16)a3[3];
      if ( v26 < v25 )
        return 534;
      v27 = v26 + 36000000000LL * (unsigned __int16)a3[4];
      if ( v27 < v26 )
        return 534;
      v28 = v27 + 600000000LL * (unsigned __int16)a3[5];
      if ( v28 < v27 || v28 + 10000000LL * (unsigned __int16)a3[6] < v28 )
        return 534;
      v34 = (FILETIME)(v28 + 10000000LL * (unsigned __int16)a3[6]);
      if ( !FileTimeToSystemTime(&v34, &v38) )
      {
LABEL_36:
        result = GetLastError();
        if ( result )
          return result;
      }
    }
    return GetLastError();
  }
  return result;
}

```

## disassembly

```asm
0x1800160b0  mov     [rsp-38h+arg_10], rbx
0x1800160b5  push    rbp
0x1800160b6  push    rsi
0x1800160b7  push    rdi
0x1800160b8  push    r12
0x1800160ba  push    r13
0x1800160bc  push    r14
0x1800160be  push    r15
0x1800160c0  mov     rbp, rsp
0x1800160c3  sub     rsp, 70h
0x1800160c7  mov     rax, cs:__security_cookie
0x1800160ce  xor     rax, rsp
0x1800160d1  mov     [rbp+var_10], rax
0x1800160d5  mov     r13, [rbp+arg_20]
0x1800160d9  mov     rbx, r8
0x1800160dc  xor     r15d, r15d
0x1800160df  xorps   xmm0, xmm0
0x1800160e2  xorps   xmm1, xmm1
0x1800160e5  mov     qword ptr [rbp+FileTime.dwLowDateTime], r15
0x1800160e9  mov     r12, r9
0x1800160ec  mov     qword ptr [rbp+FileTime1.dwLowDateTime], r15
0x1800160f0  lea     rdi, [rbx+2]
0x1800160f4  mov     r8, rdx
0x1800160f7  mov     rsi, rcx
0x1800160fa  mov     r9, 861C46800h
0x180016104  movups  xmmword ptr [rbp+SystemTime.wYear], xmm0
0x180016108  movups  xmmword ptr [rbp+var_30.wYear], xmm1
0x18001610c  cmp     [rbx], r15w
0x180016110  jnz     loc_180016508
0x180016116  cmp     [rdi], r15w
0x18001611a  jnz     loc_180016508
0x180016120  mov     eax, [rdx+4]
0x180016123  lea     r14, [rbx+4]
0x180016127  mov     [rbp+var_50.dwHighDateTime], eax
0x18001612a  mov     eax, [rdx]
0x18001612c  mov     [rbp+var_50.dwLowDateTime], eax
0x18001612f  mov     eax, [rcx+4]
0x180016132  mov     dword ptr [rbp+var_38+4], eax
0x180016135  mov     eax, [rcx]
0x180016137  mov     dword ptr [rbp+var_38], eax
0x18001613a  movzx   eax, word ptr [r14]
0x18001613e  imul    eax, 93A80h
0x180016144  cdqe
0x180016146  imul    rdx, rax, 989680h
0x18001614d  movzx   eax, word ptr [rbx+6]
0x180016151  imul    eax, 15180h
0x180016157  cdqe
0x180016159  imul    r8, rax, 989680h
0x180016160  add     r8, rdx
0x180016163  cmp     r8, rdx
0x180016166  jnb     short loc_180016191
0x180016168  mov     eax, 216h
0x18001616d  mov     rcx, [rbp+var_10]
0x180016171  xor     rcx, rsp; StackCookie
0x180016174  call    __security_check_cookie
0x180016179  mov     rbx, [rsp+70h+arg_10]
0x180016181  add     rsp, 70h
0x180016185  pop     r15
0x180016187  pop     r14
0x180016189  pop     r13
0x18001618b  pop     r12
0x18001618d  pop     rdi
0x18001618e  pop     rsi
0x18001618f  pop     rbp
0x180016190  retn
0x180016191  movzx   edx, word ptr [rbx+8]
0x180016195  imul    rdx, r9
0x180016199  add     rdx, r8
0x18001619c  cmp     rdx, r8
0x18001619f  jb      short loc_180016168
0x1800161a1  movzx   eax, word ptr [rbx+0Ah]
0x1800161a5  imul    r8, rax, 23C34600h
0x1800161ac  add     r8, rdx
0x1800161af  cmp     r8, rdx
0x1800161b2  jb      short loc_180016168
0x1800161b4  movzx   eax, word ptr [rbx+0Ch]
0x1800161b8  imul    r9, rax, 989680h
0x1800161bf  add     r9, r8
0x1800161c2  cmp     r9, r8
0x1800161c5  jb      short loc_180016168
0x1800161c7  mov     rcx, qword ptr [rbp+var_50.dwLowDateTime]
0x1800161cb  xor     edx, edx
0x1800161cd  mov     r8, [rbp+var_38]
0x1800161d1  sub     r8, rcx
0x1800161d4  mov     rax, r8
0x1800161d7  div     r9
0x1800161da  sub     r8, rdx
0x1800161dd  lea     rax, [r8+rcx]
0x1800161e1  cmp     rax, rcx
0x1800161e4  jb      short loc_180016168
0x1800161e6  mov     qword ptr [rbp+var_50.dwLowDateTime], rax
0x1800161ea  lea     rdx, [rbp+SystemTime]; lpSystemTime
0x1800161ee  shr     rax, 20h
0x1800161f2  lea     rcx, [rbp+FileTime]; lpFileTime
0x1800161f6  mov     [rbp+FileTime.dwHighDateTime], eax
0x1800161f9  mov     eax, [rbp+var_50.dwLowDateTime]
0x1800161fc  mov     [rbp+FileTime.dwLowDateTime], eax
0x1800161ff  call    cs:__imp_FileTimeToSystemTime
0x180016205  test    eax, eax
0x180016207  jz      loc_180016465
0x18001620d  lea     rdi, [rbx+2]
0x180016211  movzx   r8d, word ptr [rbx]
0x180016215  mov     qword ptr [rbp+var_50.dwLowDateTime], r15
0x180016219  mov     r15d, 0FFFFh
0x18001621f  test    r8w, r8w
0x180016223  jnz     loc_180016470
0x180016229  cmp     [rdi], r8w
0x18001622d  jnz     loc_180016470
0x180016233  lea     rdx, [rbp+var_50]; lpFileTime
0x180016237  lea     rcx, [rbp+SystemTime]; lpSystemTime
0x18001623b  call    cs:__imp_SystemTimeToFileTime
0x180016241  test    eax, eax
0x180016243  jz      loc_1800165ED
0x180016249  mov     rdx, r14
0x18001624c  movzx   edx, word ptr [rdx]
0x18001624f  mov     r15, 58028E44000h
0x180016259  mov     ecx, [rbp+var_50.dwHighDateTime]
0x18001625c  mov     eax, [rbp+var_50.dwLowDateTime]
0x18001625f  imul    rdx, r15
0x180016263  shl     rcx, 20h
0x180016267  or      rcx, rax
0x18001626a  add     rdx, rcx
0x18001626d  cmp     rdx, rcx
0x180016270  jb      loc_180016168
0x180016276  movzx   ecx, word ptr [rbx+6]
0x18001627a  mov     rdi, 0C92A69C000h
0x180016284  imul    rcx, rdi
0x180016288  add     rcx, rdx
0x18001628b  cmp     rcx, rdx
0x18001628e  jb      loc_180016168
0x180016294  movzx   eax, word ptr [rbx+8]
0x180016298  mov     rdx, 861C46800h
0x1800162a2  imul    rdx, rax
0x1800162a6  add     rdx, rcx
0x1800162a9  cmp     rdx, rcx
0x1800162ac  jb      loc_180016168
0x1800162b2  movzx   eax, word ptr [rbx+0Ah]
0x1800162b6  imul    r8, rax, 23C34600h
0x1800162bd  add     r8, rdx
0x1800162c0  cmp     r8, rdx
0x1800162c3  jb      loc_180016168
0x1800162c9  movzx   eax, word ptr [rbx+0Ch]
0x1800162cd  imul    rax, 989680h
0x1800162d4  add     rax, r8
0x1800162d7  cmp     rax, r8
0x1800162da  jb      loc_180016168
0x1800162e0  mov     rcx, rax
0x1800162e3  mov     [rbp+var_50.dwLowDateTime], eax
0x1800162e6  shr     rcx, 20h
0x1800162ea  lea     rdx, [rbp+var_30]; lpSystemTime
0x1800162ee  mov     [rbp+var_50.dwHighDateTime], ecx
0x1800162f1  lea     rcx, [rbp+var_50]; lpFileTime
0x1800162f5  call    cs:__imp_FileTimeToSystemTime
0x1800162fb  test    eax, eax
0x1800162fd  jz      short loc_180016353
0x1800162ff  lea     rdx, [rbp+FileTime]; lpFileTime
0x180016303  lea     rcx, [rbp+SystemTime]; lpSystemTime
0x180016307  call    cs:__imp_SystemTimeToFileTime
0x18001630d  test    eax, eax
0x18001630f  jz      loc_180016465
0x180016315  lea     rdx, [rbp+FileTime1]; lpFileTime
0x180016319  lea     rcx, [rbp+var_30]; lpSystemTime
0x18001631d  call    cs:__imp_SystemTimeToFileTime
0x180016323  test    eax, eax
0x180016325  jz      loc_180016465
0x18001632b  mov     rdx, rsi; lpFileTime2
0x18001632e  lea     rcx, [rbp+FileTime1]; lpFileTime1
0x180016332  call    cs:__imp_CompareFileTime
0x180016338  test    eax, eax
0x18001633a  js      short loc_180016362
0x18001633c  mov     rax, qword ptr [rbp+FileTime.dwLowDateTime]
0x180016340  mov     [r12], rax
0x180016344  mov     rax, qword ptr [rbp+FileTime1.dwLowDateTime]
0x180016348  mov     [r13+0], rax
0x18001634c  xor     eax, eax
0x18001634e  jmp     loc_18001616D
0x180016353  call    cs:__imp_GetLastError
0x180016359  test    eax, eax
0x18001635b  jz      short loc_1800162FF
0x18001635d  jmp     loc_18001616D
0x180016362  movzx   r8d, word ptr [rbx]
0x180016366  movaps  xmm0, xmmword ptr [rbp+var_30.wYear]
0x18001636a  movaps  xmmword ptr [rbp+SystemTime.wYear], xmm0
0x18001636e  mov     qword ptr [rbp+var_50.dwLowDateTime], 0
0x180016376  test    r8w, r8w
0x18001637a  jnz     loc_180016526
0x180016380  cmp     [rbx+2], r8w
0x180016385  jnz     loc_180016526
0x18001638b  lea     rdx, [rbp+var_50]; lpFileTime
0x18001638f  lea     rcx, [rbp+SystemTime]; lpSystemTime
0x180016393  call    cs:__imp_SystemTimeToFileTime
0x180016399  test    eax, eax
0x18001639b  jz      loc_180016441
0x1800163a1  movzx   edx, word ptr [r14]
0x1800163a5  mov     ecx, [rbp+var_50.dwHighDateTime]
0x1800163a8  mov     eax, [rbp+var_50.dwLowDateTime]
0x1800163ab  imul    rdx, r15
0x1800163af  shl     rcx, 20h
0x1800163b3  or      rcx, rax
0x1800163b6  add     rdx, rcx
0x1800163b9  cmp     rdx, rcx
0x1800163bc  jb      loc_180016168
0x1800163c2  movzx   ecx, word ptr [rbx+6]
0x1800163c6  imul    rcx, rdi
0x1800163ca  add     rcx, rdx
0x1800163cd  cmp     rcx, rdx
0x1800163d0  jb      loc_180016168
0x1800163d6  movzx   eax, word ptr [rbx+8]
0x1800163da  mov     rdx, 861C46800h
0x1800163e4  imul    rdx, rax
0x1800163e8  add     rdx, rcx
0x1800163eb  cmp     rdx, rcx
0x1800163ee  jb      loc_180016168
0x1800163f4  movzx   eax, word ptr [rbx+0Ah]
0x1800163f8  imul    r8, rax, 23C34600h
0x1800163ff  add     r8, rdx
0x180016402  cmp     r8, rdx
0x180016405  jb      loc_180016168
0x18001640b  movzx   eax, word ptr [rbx+0Ch]
0x18001640f  imul    rax, 989680h
0x180016416  add     rax, r8
0x180016419  cmp     rax, r8
0x18001641c  jb      loc_180016168
0x180016422  mov     rcx, rax
0x180016425  mov     [rbp+var_50.dwLowDateTime], eax
0x180016428  shr     rcx, 20h
0x18001642c  lea     rdx, [rbp+var_30]; lpSystemTime
0x180016430  mov     [rbp+var_50.dwHighDateTime], ecx
0x180016433  lea     rcx, [rbp+var_50]; lpFileTime
0x180016437  call    cs:__imp_FileTimeToSystemTime
0x18001643d  test    eax, eax
0x18001643f  jnz     short loc_18001644F
0x180016441  call    cs:__imp_GetLastError
0x180016447  test    eax, eax
0x180016449  jnz     loc_18001616D
0x18001644f  lea     rdx, [rbp+FileTime]; lpFileTime
0x180016453  lea     rcx, [rbp+SystemTime]; lpSystemTime
0x180016457  call    cs:__imp_SystemTimeToFileTime
0x18001645d  test    eax, eax
0x18001645f  jnz     loc_180016315
0x180016465  call    cs:__imp_GetLastError
0x18001646b  jmp     loc_18001616D
0x180016470  movzx   ecx, [rbp+SystemTime.wMonth]
0x180016474  mov     eax, 2AAAAAABh
0x180016479  movzx   r9d, word ptr [rdi]
0x18001647d  dec     ecx
0x18001647f  add     r9d, ecx
0x180016482  imul    r9d
0x180016485  sar     edx, 1
0x180016487  mov     eax, edx
0x180016489  shr     eax, 1Fh
0x18001648c  add     edx, eax
0x18001648e  add     r8w, dx
0x180016492  add     r8w, [rbp+SystemTime.wYear]
0x180016497  cmp     r8w, [rbp+SystemTime.wYear]
0x18001649c  jb      loc_180016168
0x1800164a2  movzx   eax, dx
0x1800164a5  mov     [rbp+var_30.wYear], r8w
0x1800164aa  add     dx, dx
0x1800164ad  add     ax, dx
0x1800164b0  shl     ax, 2
0x1800164b4  sub     r9w, ax
0x1800164b8  movzx   eax, [rbp+SystemTime.wDay]
0x1800164bc  mov     [rbp+var_30.wDay], ax
0x1800164c0  inc     r9w
0x1800164c4  movzx   eax, [rbp+SystemTime.wHour]
0x1800164c8  mov     [rbp+var_30.wHour], ax
0x1800164cc  movzx   eax, [rbp+SystemTime.wMinute]
0x1800164d0  mov     [rbp+var_30.wMinute], ax
0x1800164d4  movzx   eax, [rbp+SystemTime.wSecond]
0x1800164d8  mov     [rbp+var_30.wSecond], ax
0x1800164dc  movzx   eax, [rbp+SystemTime.wMilliseconds]
0x1800164e0  mov     [rbp+var_30.wMilliseconds], ax
0x1800164e4  mov     [rbp+var_30.wMonth], r9w
0x1800164e9  lea     rdx, [rbp+var_50]; lpFileTime
0x1800164ed  lea     rcx, [rbp+var_30]; lpSystemTime
0x1800164f1  call    cs:__imp_SystemTimeToFileTime
0x1800164f7  test    eax, eax
0x1800164f9  jz      loc_1800165D6
0x1800164ff  lea     rdx, [rbx+4]
0x180016503  jmp     loc_18001624C
0x180016508  lea     rdx, [rbp+SystemTime]; lpSystemTime
0x18001650c  mov     rcx, r8; lpFileTime
0x18001650f  call    cs:__imp_FileTimeToSystemTime
0x180016515  test    eax, eax
0x180016517  jz      loc_180016465
0x18001651d  lea     r14, [rbx+4]
0x180016521  jmp     loc_180016211
0x180016526  movzx   r9d, word ptr [rbx+2]
0x18001652b  mov     eax, 2AAAAAABh
0x180016530  pextrw  ecx, xmm0, 1
0x180016535  dec     ecx
0x180016537  add     r9d, ecx
0x18001653a  movd    ecx, xmm0
0x18001653e  imul    r9d
0x180016541  sar     edx, 1
0x180016543  mov     eax, edx
0x180016545  shr     eax, 1Fh
0x180016548  add     edx, eax
0x18001654a  add     r8w, dx
  ... truncated ...
```
