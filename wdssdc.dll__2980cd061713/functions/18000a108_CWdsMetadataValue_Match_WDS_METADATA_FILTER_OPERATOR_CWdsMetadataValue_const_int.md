# CWdsMetadataValue::Match(WDS_METADATA_FILTER_OPERATOR,CWdsMetadataValue const *,int *)

- ea: `0x18000a108`
- end: `0x18000a591`
- name: `?Match@CWdsMetadataValue@@QEBAKW4WDS_METADATA_FILTER_OPERATOR@@PEBV1@PEAH@Z`
- size: `1161`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000a068`
- `0x18000a108`
- `0x18000bc94`

## callees

- `0x18000a108`
- `0x18000c178`
- `0x18000c274`
- `0x18000cc04`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000a419`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000a561`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000a419`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000a561`
- `KERNEL32!SystemTimeToFileTime` at `0x18000a3a5`
- `KERNEL32!SystemTimeToFileTime` at `0x18000a3d4`
- `KERNEL32!SystemTimeToFileTime` at `0x18000a4da`
- `KERNEL32!SystemTimeToFileTime` at `0x18000a516`
- `KERNEL32!SystemTimeToFileTime` at `0x18000a3a5`
- `KERNEL32!SystemTimeToFileTime` at `0x18000a3d4`
- `KERNEL32!SystemTimeToFileTime` at `0x18000a4da`
- `KERNEL32!SystemTimeToFileTime` at `0x18000a516`
- `KERNEL32!CompareFileTime` at `0x18000a403`
- `KERNEL32!CompareFileTime` at `0x18000a542`
- `KERNEL32!CompareFileTime` at `0x18000a403`
- `KERNEL32!CompareFileTime` at `0x18000a542`
- `KERNEL32!GetLastError` at `0x18000a3b5`
- `KERNEL32!GetLastError` at `0x18000a3e4`
- `KERNEL32!GetLastError` at `0x18000a4ea`
- `KERNEL32!GetLastError` at `0x18000a526`
- `KERNEL32!GetLastError` at `0x18000a3b5`
- `KERNEL32!GetLastError` at `0x18000a3e4`
- `KERNEL32!GetLastError` at `0x18000a4ea`
- `KERNEL32!GetLastError` at `0x18000a526`
- `WdsCommonLib!?MatchWildcards@@YAJPEBG0AEAH@Z` at `0x18000a1be`
- `WdsCommonLib!?MatchWildcards@@YAJPEBG0AEAH@Z` at `0x18000a213`
- `WdsCommonLib!?MatchWildcards@@YAJPEBG0AEAH@Z` at `0x18000a1be`
- `WdsCommonLib!?MatchWildcards@@YAJPEBG0AEAH@Z` at `0x18000a213`
- `WdsCommonLib!?WIN32_FROM_HRESULT@@YAKJ@Z` at `0x18000a234`
- `WdsCommonLib!?WIN32_FROM_HRESULT@@YAKJ@Z` at `0x18000a234`

## pseudocode

```c
__int64 __fastcall CWdsMetadataValue::Match(int *a1, int a2, __int64 a3, DWORD *a4)
{
  DWORD v4; // ebx
  __int64 v8; // rdi
  int v9; // ecx
  int v10; // edx
  int v11; // edx
  int v12; // edx
  int v13; // edx
  int v14; // edx
  int v15; // edx
  __int64 v16; // rdx
  __int64 matched; // rsi
  __int64 v18; // rdx
  __int64 v19; // r8
  bool v20; // zf
  __int64 v21; // rdx
  __int64 v22; // r8
  DWORD dwLowDateTime; // eax
  unsigned int v24; // eax
  __int64 v25; // rdx
  __int64 v26; // r8
  __int64 v27; // r9
  __int64 v28; // rdx
  __int64 v29; // r8
  __int64 v30; // rdx
  __int64 v31; // r8
  __int64 v32; // rdx
  __int64 v33; // r8
  __int64 v34; // rdx
  __int64 v35; // r8
  int v36; // ecx
  int v37; // ecx
  int v38; // ecx
  __int64 v39; // rax
  bool v40; // zf
  bool v41; // sf
  bool v42; // of
  DWORD LastError; // eax
  __int64 v44; // rdx
  __int64 v45; // r8
  __int64 v46; // r9
  LONG v47; // eax
  int v48; // ecx
  int v49; // ecx
  int v50; // ecx
  int v51; // ecx
  int v52; // ecx
  int v53; // ecx
  size_t v54; // r8
  int v55; // eax
  __int64 v56; // rax
  FILETIME FileTime2; // [rsp+20h] [rbp-10h] BYREF
  struct _FILETIME FileTime; // [rsp+28h] [rbp-8h] BYREF
  DWORD v60; // [rsp+58h] [rbp+28h] BYREF

  v4 = 0;
  LODWORD(v8) = 0;
  if ( !a2 )
    goto LABEL_2;
  v9 = *a1;
  if ( v9 != *(_DWORD *)a3 )
  {
    LOBYTE(v4) = a2 == 2;
    *a4 = v4;
    return (unsigned int)v8;
  }
  v10 = a2 - 1;
  if ( !v10 )
  {
    v48 = v9 - 1;
    if ( !v48 )
    {
      v55 = _o__wcsicmp(*((_QWORD *)a1 + 1), *(_QWORD *)(a3 + 8));
      goto LABEL_73;
    }
    v49 = v48 - 1;
    if ( !v49 )
    {
      v20 = a1[2] == *(_DWORD *)(a3 + 8);
      goto LABEL_74;
    }
    v50 = v49 - 1;
    if ( v50 )
    {
      v51 = v50 - 1;
      if ( !v51 || (v52 = v51 - 1) == 0 )
      {
        v20 = *((_QWORD *)a1 + 1) == *(_QWORD *)(a3 + 8);
        goto LABEL_74;
      }
      v53 = v52 - 1;
      if ( !v53 )
      {
        v56 = *((_QWORD *)a1 + 1) - *(_QWORD *)(a3 + 8);
        if ( !v56 )
          v56 = *((_QWORD *)a1 + 2) - *(_QWORD *)(a3 + 16);
        v20 = v56 == 0;
        goto LABEL_74;
      }
      if ( v53 != 1 )
        goto LABEL_57;
      v54 = *((_QWORD *)a1 + 2);
      if ( v54 != *(_QWORD *)(a3 + 16) )
        goto LABEL_75;
      v55 = memcmp_0(*((const void **)a1 + 1), *(const void **)(a3 + 8), v54);
LABEL_73:
      v20 = v55 == 0;
      goto LABEL_74;
    }
    FileTime2 = 0;
    FileTime = 0;
    if ( SystemTimeToFileTime((const SYSTEMTIME *)(a1 + 2), &FileTime2) )
    {
      if ( SystemTimeToFileTime((const SYSTEMTIME *)(a3 + 8), &FileTime) )
      {
        v55 = CompareFileTime(&FileTime2, &FileTime);
        goto LABEL_73;
      }
      LastError = GetLastError();
      v46 = 1882;
    }
    else
    {
      LastError = GetLastError();
      v46 = 1877;
    }
LABEL_66:
    LODWORD(v8) = ElValidateWin32_1(LastError, v44, v45, v46);
    if ( !(_DWORD)v8 )
      LODWORD(v8) = 31;
    return (unsigned int)v8;
  }
  v11 = v10 - 1;
  if ( !v11 )
  {
    v60 = 0;
    v24 = CWdsMetadataValue::Match(a1, 1, a3, &v60);
    v27 = 1969;
LABEL_23:
    LODWORD(v8) = v24;
    if ( (unsigned int)ElValidateWin32_1(v24, v25, v26, v27) )
      return (unsigned int)v8;
    goto LABEL_16;
  }
  v12 = v11 - 1;
  if ( !v12 )
  {
    v36 = v9 - 1;
    if ( v36 )
    {
      v37 = v36 - 2;
      if ( v37 )
      {
        v38 = v37 - 1;
        if ( v38 )
        {
          if ( v38 == 1 )
          {
            LOBYTE(v4) = *((_QWORD *)a1 + 1) > *(_QWORD *)(a3 + 8);
            goto LABEL_75;
          }
LABEL_57:
          LODWORD(v8) = 13;
          return (unsigned int)v8;
        }
        v39 = *(_QWORD *)(a3 + 8);
        v42 = __OFSUB__(*((_QWORD *)a1 + 1), v39);
        v40 = *((_QWORD *)a1 + 1) == v39;
        v41 = *((_QWORD *)a1 + 1) - v39 < 0;
LABEL_48:
        LOBYTE(v4) = !(v41 ^ v42 | v40);
        goto LABEL_75;
      }
      FileTime = 0;
      FileTime2 = 0;
      if ( !SystemTimeToFileTime((const SYSTEMTIME *)(a1 + 2), &FileTime) )
      {
        LastError = GetLastError();
        v46 = 1938;
        goto LABEL_66;
      }
      if ( !SystemTimeToFileTime((const SYSTEMTIME *)(a3 + 8), &FileTime2) )
      {
        LastError = GetLastError();
        v46 = 1943;
        goto LABEL_66;
      }
      v47 = CompareFileTime(&FileTime, &FileTime2);
    }
    else
    {
      v47 = _o__wcsicmp(*((_QWORD *)a1 + 1), *(_QWORD *)(a3 + 8));
    }
    v42 = 0;
    v40 = v47 == 0;
    v41 = v47 < 0;
    goto LABEL_48;
  }
  v13 = v12 - 1;
  if ( !v13 )
  {
    v60 = 0;
    FileTime2.dwLowDateTime = 0;
    v8 = (unsigned int)CWdsMetadataValue::Match(a1, 3, a3, &v60);
    if ( (unsigned int)ElValidateWin32_1(v8, v32, v33, 1982) )
      return (unsigned int)v8;
    if ( !v60 )
    {
      v8 = (unsigned int)CWdsMetadataValue::Match(a1, 1, a3, &FileTime2);
      if ( (unsigned int)ElValidateWin32_1(v8, v34, v35, 1991) )
        return (unsigned int)v8;
      v20 = FileTime2.dwLowDateTime == 0;
      goto LABEL_74;
    }
LABEL_75:
    *a4 = v4;
    return (unsigned int)v8;
  }
  v14 = v13 - 1;
  if ( !v14 )
  {
    v60 = 0;
    FileTime2.dwLowDateTime = 0;
    v8 = (unsigned int)CWdsMetadataValue::Match(a1, 3, a3, &v60);
    if ( (unsigned int)ElValidateWin32_1(v8, v28, v29, 2004) )
      return (unsigned int)v8;
    if ( v60 )
    {
      *a4 = 1;
      return (unsigned int)v8;
    }
    v8 = (unsigned int)CWdsMetadataValue::Match(a1, 1, a3, &FileTime2);
    if ( (unsigned int)ElValidateWin32_1(v8, v30, v31, 2013) )
      return (unsigned int)v8;
    dwLowDateTime = FileTime2.dwLowDateTime;
    goto LABEL_30;
  }
  v15 = v14 - 1;
  if ( !v15 )
  {
    v60 = 0;
    v24 = CWdsMetadataValue::Match(a1, 3, a3, &v60);
    v27 = 2025;
    goto LABEL_23;
  }
  v16 = (unsigned int)(v15 - 1);
  if ( !(_DWORD)v16 )
  {
    v60 = 0;
    if ( v9 != 1 )
    {
      LODWORD(v8) = 87;
      if ( (unsigned int)ElValidateWin32_1(87, v16, a3, 2040) )
        return (unsigned int)v8;
    }
    matched = (unsigned int)MatchWildcards(
                              *((const unsigned __int16 **)a1 + 1),
                              *(const unsigned __int16 **)(a3 + 8),
                              (int *)&v60);
    if ( (int)ElValidateHr_1(matched, v21, v22, 2046) < 0 )
      goto LABEL_20;
    dwLowDateTime = v60;
LABEL_30:
    *a4 = dwLowDateTime;
    return (unsigned int)v8;
  }
  if ( (_DWORD)v16 != 1 )
  {
LABEL_2:
    LODWORD(v8) = 87;
    return (unsigned int)v8;
  }
  v60 = 0;
  if ( v9 == 1 || (LODWORD(v8) = 87, !(unsigned int)ElValidateWin32_1(87, v16, a3, 2061)) )
  {
    matched = (unsigned int)MatchWildcards(
                              *((const unsigned __int16 **)a1 + 1),
                              *(const unsigned __int16 **)(a3 + 8),
                              (int *)&v60);
    if ( (int)ElValidateHr_1(matched, v18, v19, 2067) >= 0 )
    {
LABEL_16:
      v20 = v60 == 0;
LABEL_74:
      LOBYTE(v4) = v20;
      goto LABEL_75;
    }
LABEL_20:
    LODWORD(v8) = WIN32_FROM_HRESULT(matched);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18000a108  mov     [rsp-18h+arg_0], rbx
0x18000a10d  mov     [rsp-18h+arg_10], rsi
0x18000a112  mov     [rsp-18h+arg_18], rdi
0x18000a117  push    rbp
0x18000a118  push    r14
0x18000a11a  push    r15
0x18000a11c  mov     rbp, rsp
0x18000a11f  sub     rsp, 30h
0x18000a123  xor     ebx, ebx
0x18000a125  mov     r15, r9
0x18000a128  mov     r14, r8
0x18000a12b  mov     rsi, rcx
0x18000a12e  mov     edi, ebx
0x18000a130  test    edx, edx
0x18000a132  jnz     short loc_18000A13E
0x18000a134  mov     edi, 57h ; 'W'
0x18000a139  jmp     loc_18000A575
0x18000a13e  mov     ecx, [rcx]
0x18000a140  cmp     ecx, [r8]
0x18000a143  jz      short loc_18000A153
0x18000a145  cmp     edx, 2
0x18000a148  setz    bl
0x18000a14b  mov     [r9], ebx
0x18000a14e  jmp     loc_18000A575
0x18000a153  sub     edx, 1
0x18000a156  jz      loc_18000A44E
0x18000a15c  sub     edx, 1
0x18000a15f  jz      loc_18000A42F
0x18000a165  sub     edx, 1
0x18000a168  jz      loc_18000A35C
0x18000a16e  sub     edx, 1
0x18000a171  jz      loc_18000A2F4
0x18000a177  sub     edx, 1
0x18000a17a  jz      loc_18000A27F
0x18000a180  sub     edx, 1
0x18000a183  jz      loc_18000A24F
0x18000a189  sub     edx, 1
0x18000a18c  jz      short loc_18000A1E5
0x18000a18e  cmp     edx, 1
0x18000a191  jnz     short loc_18000A134
0x18000a193  mov     [rbp+arg_8], ebx
0x18000a196  cmp     ecx, edx
0x18000a198  jz      short loc_18000A1B2
0x18000a19a  lea     edi, [rdx+56h]
0x18000a19d  mov     r9d, 80Dh
0x18000a1a3  mov     ecx, edi
0x18000a1a5  call    ElValidateWin32_1
0x18000a1aa  test    eax, eax
0x18000a1ac  jnz     loc_18000A575
0x18000a1b2  mov     rdx, [r14+8]
0x18000a1b6  lea     r8, [rbp+arg_8]
0x18000a1ba  mov     rcx, [rsi+8]
0x18000a1be  call    cs:__imp_?MatchWildcards@@YAJPEBG0AEAH@Z; MatchWildcards(ushort const *,ushort const *,int &)
0x18000a1c5  nop     dword ptr [rax+rax+00h]
0x18000a1ca  mov     ecx, eax
0x18000a1cc  mov     r9d, 813h
0x18000a1d2  mov     esi, eax
0x18000a1d4  call    ElValidateHr_1
0x18000a1d9  test    eax, eax
0x18000a1db  js      short loc_18000A232
0x18000a1dd  cmp     [rbp+arg_8], ebx
0x18000a1e0  jmp     loc_18000A56F
0x18000a1e5  mov     [rbp+arg_8], ebx
0x18000a1e8  cmp     ecx, 1
0x18000a1eb  jz      short loc_18000A207
0x18000a1ed  mov     edi, 57h ; 'W'
0x18000a1f2  mov     r9d, 7F8h
0x18000a1f8  mov     ecx, edi
0x18000a1fa  call    ElValidateWin32_1
0x18000a1ff  test    eax, eax
0x18000a201  jnz     loc_18000A575
0x18000a207  mov     rdx, [r14+8]
0x18000a20b  lea     r8, [rbp+arg_8]
0x18000a20f  mov     rcx, [rsi+8]
0x18000a213  call    cs:__imp_?MatchWildcards@@YAJPEBG0AEAH@Z; MatchWildcards(ushort const *,ushort const *,int &)
0x18000a21a  nop     dword ptr [rax+rax+00h]
0x18000a21f  mov     ecx, eax
0x18000a221  mov     r9d, 7FEh
0x18000a227  mov     esi, eax
0x18000a229  call    ElValidateHr_1
0x18000a22e  test    eax, eax
0x18000a230  jns     short loc_18000A247
0x18000a232  mov     ecx, esi
0x18000a234  call    cs:__imp_?WIN32_FROM_HRESULT@@YAKJ@Z; WIN32_FROM_HRESULT(long)
0x18000a23b  nop     dword ptr [rax+rax+00h]
0x18000a240  mov     edi, eax
0x18000a242  jmp     loc_18000A575
0x18000a247  mov     eax, [rbp+arg_8]
0x18000a24a  jmp     loc_18000A2EC
0x18000a24f  lea     r9, [rbp+arg_8]
0x18000a253  mov     [rbp+arg_8], ebx
0x18000a256  mov     edx, 3
0x18000a25b  mov     rcx, rsi
0x18000a25e  call    ?Match@CWdsMetadataValue@@QEBAKW4WDS_METADATA_FILTER_OPERATOR@@PEBV1@PEAH@Z; CWdsMetadataValue::Match(WDS_METADATA_FILTER_OPERATOR,CWdsMetadataValue const *,int *)
0x18000a263  mov     r9d, 7E9h
0x18000a269  mov     ecx, eax
0x18000a26b  mov     edi, eax
0x18000a26d  call    ElValidateWin32_1
0x18000a272  test    eax, eax
0x18000a274  jnz     loc_18000A575
0x18000a27a  jmp     loc_18000A1DD
0x18000a27f  lea     r9, [rbp+arg_8]
0x18000a283  mov     [rbp+arg_8], ebx
0x18000a286  mov     edx, 3
0x18000a28b  mov     [rbp+FileTime2.dwLowDateTime], ebx
0x18000a28e  mov     rcx, rsi
0x18000a291  call    ?Match@CWdsMetadataValue@@QEBAKW4WDS_METADATA_FILTER_OPERATOR@@PEBV1@PEAH@Z; CWdsMetadataValue::Match(WDS_METADATA_FILTER_OPERATOR,CWdsMetadataValue const *,int *)
0x18000a296  mov     r9d, 7D4h
0x18000a29c  mov     ecx, eax
0x18000a29e  mov     edi, eax
0x18000a2a0  call    ElValidateWin32_1
0x18000a2a5  test    eax, eax
0x18000a2a7  jnz     loc_18000A575
0x18000a2ad  cmp     [rbp+arg_8], ebx
0x18000a2b0  jz      short loc_18000A2BE
0x18000a2b2  mov     dword ptr [r15], 1
0x18000a2b9  jmp     loc_18000A575
0x18000a2be  lea     r9, [rbp+FileTime2]
0x18000a2c2  mov     r8, r14
0x18000a2c5  mov     edx, 1
0x18000a2ca  mov     rcx, rsi
0x18000a2cd  call    ?Match@CWdsMetadataValue@@QEBAKW4WDS_METADATA_FILTER_OPERATOR@@PEBV1@PEAH@Z; CWdsMetadataValue::Match(WDS_METADATA_FILTER_OPERATOR,CWdsMetadataValue const *,int *)
0x18000a2d2  mov     r9d, 7DDh
0x18000a2d8  mov     ecx, eax
0x18000a2da  mov     edi, eax
0x18000a2dc  call    ElValidateWin32_1
0x18000a2e1  test    eax, eax
0x18000a2e3  jnz     loc_18000A575
0x18000a2e9  mov     eax, [rbp+FileTime2.dwLowDateTime]
0x18000a2ec  mov     [r15], eax
0x18000a2ef  jmp     loc_18000A575
0x18000a2f4  lea     r9, [rbp+arg_8]
0x18000a2f8  mov     [rbp+arg_8], ebx
0x18000a2fb  mov     edx, 3
0x18000a300  mov     [rbp+FileTime2.dwLowDateTime], ebx
0x18000a303  mov     rcx, rsi
0x18000a306  call    ?Match@CWdsMetadataValue@@QEBAKW4WDS_METADATA_FILTER_OPERATOR@@PEBV1@PEAH@Z; CWdsMetadataValue::Match(WDS_METADATA_FILTER_OPERATOR,CWdsMetadataValue const *,int *)
0x18000a30b  mov     r9d, 7BEh
0x18000a311  mov     ecx, eax
0x18000a313  mov     edi, eax
0x18000a315  call    ElValidateWin32_1
0x18000a31a  test    eax, eax
0x18000a31c  jnz     loc_18000A575
0x18000a322  cmp     [rbp+arg_8], ebx
0x18000a325  jnz     loc_18000A572
0x18000a32b  lea     r9, [rbp+FileTime2]
0x18000a32f  mov     r8, r14
0x18000a332  lea     edx, [rax+1]
0x18000a335  mov     rcx, rsi
0x18000a338  call    ?Match@CWdsMetadataValue@@QEBAKW4WDS_METADATA_FILTER_OPERATOR@@PEBV1@PEAH@Z; CWdsMetadataValue::Match(WDS_METADATA_FILTER_OPERATOR,CWdsMetadataValue const *,int *)
0x18000a33d  mov     r9d, 7C7h
0x18000a343  mov     ecx, eax
0x18000a345  mov     edi, eax
0x18000a347  call    ElValidateWin32_1
0x18000a34c  test    eax, eax
0x18000a34e  jnz     loc_18000A575
0x18000a354  cmp     [rbp+FileTime2.dwLowDateTime], ebx
0x18000a357  jmp     loc_18000A56F
0x18000a35c  sub     ecx, 1
0x18000a35f  jz      loc_18000A411
0x18000a365  sub     ecx, 2
0x18000a368  jz      short loc_18000A395
0x18000a36a  sub     ecx, 1
0x18000a36d  jz      short loc_18000A388
0x18000a36f  cmp     ecx, 1
0x18000a372  jnz     loc_18000A479
0x18000a378  mov     rax, [r8+8]
0x18000a37c  cmp     [rsi+8], rax
0x18000a380  setnbe  bl
0x18000a383  jmp     loc_18000A572
0x18000a388  mov     rax, [r8+8]
0x18000a38c  cmp     [rsi+8], rax
0x18000a390  jmp     loc_18000A427
0x18000a395  lea     rcx, [rsi+8]; lpSystemTime
0x18000a399  mov     qword ptr [rbp+FileTime.dwLowDateTime], rbx
0x18000a39d  lea     rdx, [rbp+FileTime]; lpFileTime
0x18000a3a1  mov     qword ptr [rbp+FileTime2.dwLowDateTime], rbx
0x18000a3a5  call    cs:__imp_SystemTimeToFileTime
0x18000a3ac  nop     dword ptr [rax+rax+00h]
0x18000a3b1  test    eax, eax
0x18000a3b3  jnz     short loc_18000A3CC
0x18000a3b5  call    cs:__imp_GetLastError
0x18000a3bc  nop     dword ptr [rax+rax+00h]
0x18000a3c1  mov     r9d, 792h
0x18000a3c7  jmp     loc_18000A4FC
0x18000a3cc  lea     rcx, [r14+8]; lpSystemTime
0x18000a3d0  lea     rdx, [rbp+FileTime2]; lpFileTime
0x18000a3d4  call    cs:__imp_SystemTimeToFileTime
0x18000a3db  nop     dword ptr [rax+rax+00h]
0x18000a3e0  test    eax, eax
0x18000a3e2  jnz     short loc_18000A3FB
0x18000a3e4  call    cs:__imp_GetLastError
0x18000a3eb  nop     dword ptr [rax+rax+00h]
0x18000a3f0  mov     r9d, 797h
0x18000a3f6  jmp     loc_18000A4FC
0x18000a3fb  lea     rdx, [rbp+FileTime2]; lpFileTime2
0x18000a3ff  lea     rcx, [rbp+FileTime]; lpFileTime1
0x18000a403  call    cs:__imp_CompareFileTime
0x18000a40a  nop     dword ptr [rax+rax+00h]
0x18000a40f  jmp     short loc_18000A425
0x18000a411  mov     rdx, [r8+8]
0x18000a415  mov     rcx, [rsi+8]
0x18000a419  call    cs:__imp__o__wcsicmp
0x18000a420  nop     dword ptr [rax+rax+00h]
0x18000a425  test    eax, eax
0x18000a427  setnle  bl
0x18000a42a  jmp     loc_18000A572
0x18000a42f  lea     r9, [rbp+arg_8]
0x18000a433  mov     [rbp+arg_8], ebx
0x18000a436  mov     edx, 1
0x18000a43b  mov     rcx, rsi
0x18000a43e  call    ?Match@CWdsMetadataValue@@QEBAKW4WDS_METADATA_FILTER_OPERATOR@@PEBV1@PEAH@Z; CWdsMetadataValue::Match(WDS_METADATA_FILTER_OPERATOR,CWdsMetadataValue const *,int *)
0x18000a443  mov     r9d, 7B1h
0x18000a449  jmp     loc_18000A269
0x18000a44e  sub     ecx, 1
0x18000a451  jz      loc_18000A559
0x18000a457  sub     ecx, 1
0x18000a45a  jz      loc_18000A550
0x18000a460  sub     ecx, 1
0x18000a463  jz      short loc_18000A4CA
0x18000a465  sub     ecx, 1
0x18000a468  jz      short loc_18000A4BD
0x18000a46a  sub     ecx, 1
0x18000a46d  jz      short loc_18000A4BD
0x18000a46f  sub     ecx, 1
0x18000a472  jz      short loc_18000A4A3
0x18000a474  cmp     ecx, 1
0x18000a477  jz      short loc_18000A483
0x18000a479  mov     edi, 0Dh
0x18000a47e  jmp     loc_18000A575
0x18000a483  mov     r8, [rsi+10h]; Size
0x18000a487  cmp     r8, [r14+10h]
0x18000a48b  jnz     loc_18000A572
0x18000a491  mov     rdx, [r14+8]; Buf2
0x18000a495  mov     rcx, [rsi+8]; Buf1
0x18000a499  call    memcmp_0
0x18000a49e  jmp     loc_18000A56D
0x18000a4a3  mov     rax, [rsi+8]
0x18000a4a7  sub     rax, [r8+8]
0x18000a4ab  jnz     short loc_18000A4B5
0x18000a4ad  mov     rax, [rsi+10h]
0x18000a4b1  sub     rax, [r8+10h]
0x18000a4b5  test    rax, rax
0x18000a4b8  jmp     loc_18000A56F
0x18000a4bd  mov     rax, [r8+8]
0x18000a4c1  cmp     [rsi+8], rax
0x18000a4c5  jmp     loc_18000A56F
0x18000a4ca  lea     rcx, [rsi+8]; lpSystemTime
0x18000a4ce  mov     qword ptr [rbp+FileTime2.dwLowDateTime], rbx
0x18000a4d2  lea     rdx, [rbp+FileTime2]; lpFileTime
0x18000a4d6  mov     qword ptr [rbp+FileTime.dwLowDateTime], rbx
0x18000a4da  call    cs:__imp_SystemTimeToFileTime
0x18000a4e1  nop     dword ptr [rax+rax+00h]
0x18000a4e6  test    eax, eax
0x18000a4e8  jnz     short loc_18000A50E
0x18000a4ea  call    cs:__imp_GetLastError
0x18000a4f1  nop     dword ptr [rax+rax+00h]
0x18000a4f6  mov     r9d, 755h
0x18000a4fc  mov     ecx, eax
0x18000a4fe  call    ElValidateWin32_1
0x18000a503  mov     edi, eax
0x18000a505  test    eax, eax
0x18000a507  jnz     short loc_18000A575
0x18000a509  lea     edi, [rax+1Fh]
0x18000a50c  jmp     short loc_18000A575
0x18000a50e  lea     rcx, [r14+8]; lpSystemTime
0x18000a512  lea     rdx, [rbp+FileTime]; lpFileTime
0x18000a516  call    cs:__imp_SystemTimeToFileTime
0x18000a51d  nop     dword ptr [rax+rax+00h]
0x18000a522  test    eax, eax
0x18000a524  jnz     short loc_18000A53A
0x18000a526  call    cs:__imp_GetLastError
0x18000a52d  nop     dword ptr [rax+rax+00h]
0x18000a532  mov     r9d, 75Ah
0x18000a538  jmp     short loc_18000A4FC
0x18000a53a  lea     rdx, [rbp+FileTime]; lpFileTime2
0x18000a53e  lea     rcx, [rbp+FileTime2]; lpFileTime1
0x18000a542  call    cs:__imp_CompareFileTime
0x18000a549  nop     dword ptr [rax+rax+00h]
0x18000a54e  jmp     short loc_18000A56D
0x18000a550  mov     eax, [r8+8]
0x18000a554  cmp     [rsi+8], eax
0x18000a557  jmp     short loc_18000A56F
0x18000a559  mov     rdx, [r8+8]
0x18000a55d  mov     rcx, [rsi+8]
0x18000a561  call    cs:__imp__o__wcsicmp
0x18000a568  nop     dword ptr [rax+rax+00h]
0x18000a56d  test    eax, eax
0x18000a56f  setz    bl
0x18000a572  mov     [r15], ebx
0x18000a575  mov     rbx, [rsp+30h+arg_0]
0x18000a57a  mov     eax, edi
0x18000a57c  mov     rdi, [rsp+30h+arg_18]
0x18000a581  mov     rsi, [rsp+30h+arg_10]
0x18000a586  add     rsp, 30h
0x18000a58a  pop     r15
0x18000a58c  pop     r14
0x18000a58e  pop     rbp
0x18000a58f  retn
```
