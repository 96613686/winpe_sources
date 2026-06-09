# dunzip

- ea: `0x18000fe10`
- end: `0x1800106b0`
- name: `dunzip`
- size: `2208`
- prototype: ``
- caller_count: `7`
- callee_count: `18`
- tags: `broker_com_uri`

## callers

- `0x18000b0bc`
- `0x18000f990`
- `0x18001111c`
- `0x18001f13c`
- `0x180023244`
- `0x18003fde0`
- `0x180040340`

## callees

- `0x18000dd10`
- `0x18000fe10`
- `0x18001584c`
- `0x180015dac`
- `0x180016160`
- `0x180016aa0`
- `0x180016d80`
- `0x18001833c`
- `0x1800210f0`
- `0x18002115c`
- `0x1800211a0`
- `0x18002b5e4`
- `0x18002f584`
- `0x180036f50`
- `0x180037958`
- `0x18006a7b8`
- `0x18006a914`
- `0x18006e9a0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000fe6a`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000fe87`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800101a3`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800101b4`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180010271`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001034f`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180010360`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800103a6`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180010425`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800104e1`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001054a`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001061f`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180010634`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000fe6a`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000fe87`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800101a3`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800101b4`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180010271`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001034f`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180010360`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800103a6`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180010425`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800104e1`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001054a`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001061f`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180010634`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800101cf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001037b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010657`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800101cf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001037b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010657`
- `api-ms-win-core-processenvironment-l1-1-0!GetCurrentDirectoryW` at `0x180010068`
- `api-ms-win-core-processenvironment-l1-1-0!GetCurrentDirectoryW` at `0x180010068`
- `KERNEL32!lstrlenA` at `0x18000ffc9`
- `KERNEL32!lstrlenA` at `0x18000ffc9`
- `KERNEL32!lstrlenW` at `0x18001031d`
- `KERNEL32!lstrlenW` at `0x18001031d`

## pseudocode

```c
__int64 __fastcall dunzip(_DWORD *a1)
{
  char *Value; // rbx
  int v4; // eax
  bool v5; // zf
  int v6; // eax
  __int64 v7; // rsi
  _BYTE *v8; // rdi
  __int64 v9; // rcx
  _BYTE *v10; // rax
  __int64 v11; // r14
  LPCSTR v12; // rdx
  __int64 v13; // rax
  _BYTE *v14; // rax
  _WORD *v15; // rax
  _WORD *v16; // rcx
  int v17; // r8d
  __int64 v18; // r8
  _WORD *v19; // r9
  __int64 v20; // r10
  __int64 v21; // rax
  _WORD *v22; // rdx
  _WORD *v23; // rcx
  _WORD *v24; // rdx
  _WORD *v25; // rax
  _WORD *v26; // rcx
  DWORD v27; // ecx
  _QWORD *v28; // rax
  _QWORD *v29; // rbx
  void *v30; // rcx
  unsigned int NextNamedZipInfo; // edi
  unsigned int IndexedZipInfo; // eax
  unsigned int NextZipInfo; // eax
  _WORD *v34; // rax
  _WORD *v35; // rcx
  int v36; // r8d
  __int16 v37; // ax
  DWORD v38; // ecx
  _QWORD *v39; // rax
  _QWORD *v40; // rbx
  void *v41; // rcx
  DWORD v42; // ecx
  DWORD v43; // ecx
  unsigned int v44; // eax
  int v45; // r14d
  DWORD v46; // ecx
  DWORD v47; // ecx
  int v48; // esi
  unsigned int IndexedItem; // eax
  _QWORD *v50; // rax
  _QWORD *v51; // rbx
  void *v52; // rcx
  int Src; // [rsp+30h] [rbp-D0h] BYREF
  int v54; // [rsp+34h] [rbp-CCh]
  _WORD *v55; // [rsp+38h] [rbp-C8h]
  _WORD *v56; // [rsp+40h] [rbp-C0h]
  int v57; // [rsp+48h] [rbp-B8h]
  _WORD *v58; // [rsp+4Ch] [rbp-B4h]
  int v59; // [rsp+5Ch] [rbp-A4h]
  __int64 v60; // [rsp+68h] [rbp-98h]
  __int64 v61; // [rsp+70h] [rbp-90h]
  int v62; // [rsp+78h] [rbp-88h]
  int v63; // [rsp+7Ch] [rbp-84h]
  LPCSTR lpString; // [rsp+80h] [rbp-80h]
  __int64 v65; // [rsp+88h] [rbp-78h]
  __int64 v66; // [rsp+90h] [rbp-70h]
  __int64 v67; // [rsp+98h] [rbp-68h]
  unsigned int v68; // [rsp+A0h] [rbp-60h]
  _BYTE *v69; // [rsp+A4h] [rbp-5Ch]
  __int64 v70; // [rsp+ACh] [rbp-54h]
  _BYTE v71[4]; // [rsp+7E0h] [rbp+6E0h] BYREF
  int v72; // [rsp+7E4h] [rbp+6E4h]

  memset_0(v71, 0, 0x1086u);
  memset_0(&Src, 0, 0x7A4u);
  Value = (char *)TlsGetValue(dwUnZIPTlsIndex);
  if ( !Value )
  {
    if ( !(unsigned int)DunzipThreadInit() )
      return 4;
    Value = (char *)TlsGetValue(dwUnZIPTlsIndex);
    if ( !Value )
      return 4;
  }
  if ( *((_DWORD *)Value + 21) )
    return 45;
  *((_DWORD *)Value + 21) = 1;
  *((_QWORD *)Value + 405) = -1;
  v4 = 10240;
  *(_QWORD *)Value = 0;
  *((_QWORD *)Value + 1) = 0;
  *((_DWORD *)Value + 4) = 0;
  *((_QWORD *)Value + 5) = 0;
  *((_QWORD *)Value + 6) = 0;
  *((_QWORD *)Value + 7) = 0;
  *((_QWORD *)Value + 8) = 0;
  *((_QWORD *)Value + 475) = 0;
  *((_QWORD *)Value + 477) = 0;
  v5 = a1[1] == 9;
  if ( a1[1] == 9 )
    v4 = 0x2000;
  *((_DWORD *)Value + 18) = v4;
  v6 = 61440;
  if ( v5 )
    v6 = 0x2000;
  *((_DWORD *)Value + 19) = v6;
  Src = 1956;
  if ( (unsigned int)CopyUCS(&Src, a1) || Src != 1956 )
  {
    *((_DWORD *)Value + 21) = 0;
    return 47;
  }
  *((_QWORD *)Value + 475) = v65;
  *((_QWORD *)Value + 476) = v70;
  *((_QWORD *)Value + 477) = v66;
  if ( !v55 || !*v55 )
    goto LABEL_140;
  v7 = 66;
  v8 = Value + 4808;
  v9 = 66;
  v10 = Value + 4808;
  do
  {
    *v10++ = 0;
    --v9;
  }
  while ( v9 );
  v11 = 2147483646;
  if ( !v63 )
    goto LABEL_27;
  if ( !lpString || lstrlenA(lpString) > 65 )
  {
LABEL_140:
    *((_DWORD *)Value + 21) = 0;
    return 47;
  }
  v12 = lpString;
  v13 = 2147483646;
  do
  {
    if ( !v13 )
      break;
    if ( !*v12 )
      break;
    *v8++ = *v12++;
    --v13;
    --v7;
  }
  while ( v7 );
  v14 = v8 - 1;
  if ( v7 )
    v14 = v8;
  *v14 = 0;
LABEL_27:
  *((_DWORD *)Value + 1) = v59 != 0;
  *((_QWORD *)Value + 5) = v68;
  if ( v67 )
  {
    if ( (*((_QWORD *)Value + 6) = v67, v56) && *v56 && (unsigned int)IsSingleFileSpec() || v57 >= 0 )
      *((_DWORD *)Value + 4) = 1;
  }
  GetCurrentDirectoryW(0x103u, (LPWSTR)Value + 824);
  v15 = v55;
  if ( v55 )
  {
    v16 = Value + 88;
    if ( Value != (char *)-88LL )
    {
      v17 = 0;
      if ( *v55 )
      {
        do
        {
          if ( v17 >= 259 )
            break;
          if ( *v15 != 34 )
          {
            *v16++ = *v15;
            ++v17;
          }
          ++v15;
        }
        while ( *v15 );
      }
      *v16 = 0;
    }
  }
  v18 = 260;
  v19 = Value + 70496;
  v20 = 260;
  v21 = 2147483646;
  v22 = Value + 88;
  do
  {
    if ( !v21 )
      break;
    if ( !*v22 )
      break;
    *v19++ = *v22++;
    --v21;
    --v20;
  }
  while ( v20 );
  v23 = v19 - 1;
  v24 = Value + 88;
  v25 = Value + 608;
  if ( v20 )
    v23 = v19;
  *v23 = 0;
  do
  {
    if ( !v11 )
      break;
    if ( !*v24 )
      break;
    *v25++ = *v24++;
    --v11;
    --v18;
  }
  while ( v18 );
  v26 = v25 - 1;
  if ( v18 )
    v26 = v25;
  *v26 = 0;
  if ( !*((_DWORD *)Value + 1102) || ((v54 - 2) & 0xFFFFFFFD) != 0 )
  {
    if ( !OpenCurrentZIP(v26, v24) )
    {
      v27 = dwUnZIPTlsIndex;
      *((_DWORD *)Value + 21) = 0;
      if ( TlsGetValue(v27) )
      {
        v28 = TlsGetValue(dwUnZIPTlsIndex);
        v29 = v28;
        if ( v28 )
        {
          v30 = (void *)v28[405];
          if ( v30 != (void *)-1LL )
          {
            CloseHandle(v30);
            v29[405] = -1;
          }
        }
      }
      return 9;
    }
  }
  else
  {
    *((_QWORD *)Value + 405) = -1;
  }
  if ( v54 == 7 )
  {
    IndexedZipInfo = GetIndexedZipInfo(&Src);
LABEL_134:
    NextNamedZipInfo = IndexedZipInfo;
LABEL_135:
    CopyUCS(a1, &Src);
    *((_DWORD *)Value + 21) = 0;
    goto LABEL_136;
  }
  switch ( v54 )
  {
    case 1:
      *((_DWORD *)Value + 1076) = 0;
      if ( !(unsigned int)DeAllocCDirCache(Value) )
      {
        NextNamedZipInfo = 5;
        goto LABEL_135;
      }
      IndexedZipInfo = CountAllZipMembers(&Src);
      goto LABEL_134;
    case 2:
      NextZipInfo = GetNextZipInfo(&Src);
      goto LABEL_72;
    case 3:
      *((_DWORD *)Value + 1076) = 0;
      if ( !(unsigned int)DeAllocCDirCache(Value) )
      {
        NextNamedZipInfo = 5;
        goto LABEL_135;
      }
      IndexedZipInfo = CountNamedZipMembers(&Src);
      goto LABEL_134;
    case 4:
      NextZipInfo = GetNextNamedZipInfo(&Src);
LABEL_72:
      NextNamedZipInfo = NextZipInfo;
      goto LABEL_73;
    case 8:
      v34 = v58;
      if ( !v58 )
        goto LABEL_96;
      v35 = Value + 1128;
      if ( Value != (char *)-1128LL )
      {
        v36 = 0;
        if ( *v58 )
        {
          do
          {
            if ( v36 >= 259 )
              break;
            if ( *v34 != 34 )
            {
              *v35++ = *v34;
              ++v36;
            }
            ++v34;
          }
          while ( *v34 );
        }
        *v35 = 0;
      }
      if ( lstrlenW((LPCWSTR)Value + 564) < 2 )
        goto LABEL_96;
      v37 = *((_WORD *)Value + 565);
      if ( v37 != 58 && (*((_WORD *)Value + 564) != 92 || v37 != 92) )
        goto LABEL_90;
      goto LABEL_98;
    case 9:
      if ( !*((_DWORD *)Value + 4) )
      {
LABEL_96:
        v42 = dwUnZIPTlsIndex;
        *((_DWORD *)Value + 21) = 0;
        if ( TlsGetValue(v42) )
        {
          CloseCurrentZIP();
          return 47;
        }
        return 47;
      }
LABEL_98:
      *((_QWORD *)Value + 536) = v60;
      *((_QWORD *)Value + 537) = v61;
      if ( v56 )
      {
        NextNamedZipInfo = CountNamedZipMembers(&Src);
        if ( !NextNamedZipInfo )
        {
          v45 = v62;
          if ( !v62 )
          {
            CopyUCS(a1, &Src);
            v46 = dwUnZIPTlsIndex;
            *((_DWORD *)Value + 21) = 0;
            if ( TlsGetValue(v46) )
              CloseCurrentZIP();
            return 11;
          }
          if ( *((_DWORD *)Value + 1199)
            && !*((_DWORD *)Value + 4)
            && !*((_DWORD *)Value + 3)
            && (unsigned int)duzCompareDrivePaths((wchar_t *)Value + 564, (wchar_t *)Value + 44) == 1 )
          {
LABEL_122:
            MsgCB(*((_QWORD *)Value + 476), 6, 0, 0, 0);
            v47 = dwUnZIPTlsIndex;
            *((_DWORD *)Value + 21) = 0;
            if ( TlsGetValue(v47) )
              CloseCurrentZIP();
            return 12;
          }
          *((_DWORD *)Value + 20) = 1;
          v48 = 0;
          if ( v45 > 0 )
          {
            while ( 1 )
            {
              v69 = v71;
              NextNamedZipInfo = GetNextNamedZipInfo(&Src);
              if ( NextNamedZipInfo )
                break;
              v57 = v72;
              IndexedItem = extractIndexedItem((__int64)&Src);
              NextNamedZipInfo = IndexedItem;
              if ( IndexedItem && IndexedItem != 49 )
              {
                *((_DWORD *)Value + 1200) = -1;
                goto LABEL_130;
              }
              if ( ++v48 >= v45 )
                goto LABEL_130;
            }
            v69 = 0;
            *((_QWORD *)Value + 10) = 0;
            CopyUCS(a1, &Src);
            goto LABEL_74;
          }
LABEL_130:
          *((_DWORD *)Value + 20) = 0;
          *((_WORD *)Value + 35248) = 0;
          v69 = 0;
        }
LABEL_73:
        CopyUCS(a1, &Src);
        *((_DWORD *)Value + 21) = 0;
LABEL_74:
        if ( TlsGetValue(dwUnZIPTlsIndex) )
          CloseCurrentZIP();
        return NextNamedZipInfo;
      }
      if ( v57 < 0 )
      {
LABEL_90:
        v38 = dwUnZIPTlsIndex;
        *((_DWORD *)Value + 21) = 0;
        if ( TlsGetValue(v38) )
        {
          v39 = TlsGetValue(dwUnZIPTlsIndex);
          v40 = v39;
          if ( v39 )
          {
            v41 = (void *)v39[405];
            if ( v41 != (void *)-1LL )
            {
              CloseHandle(v41);
              v40[405] = -1;
            }
          }
        }
        return 47;
      }
      NextNamedZipInfo = CountAllZipMembers(&Src);
      if ( NextNamedZipInfo )
        goto LABEL_135;
      if ( v57 > v62 - 1 )
      {
        CopyUCS(a1, &Src);
        v43 = dwUnZIPTlsIndex;
        *((_DWORD *)Value + 21) = 0;
        if ( TlsGetValue(v43) )
          CloseCurrentZIP();
        return 25;
      }
      if ( *((_DWORD *)Value + 1199)
        && !*((_DWORD *)Value + 4)
        && !*((_DWORD *)Value + 3)
        && (unsigned int)duzCompareDrivePaths((wchar_t *)Value + 564, (wchar_t *)Value + 44) == 1 )
      {
        goto LABEL_122;
      }
      v44 = extractIndexedItem((__int64)&Src);
      NextNamedZipInfo = v44;
      if ( v44 && v44 - 48 > 1 )
        *((_DWORD *)Value + 1200) = -1;
      *((_WORD *)Value + 35248) = 0;
      *((_DWORD *)Value + 21) = 0;
      CopyUCS(a1, &Src);
LABEL_136:
      if ( TlsGetValue(dwUnZIPTlsIndex) )
      {
        v50 = TlsGetValue(dwUnZIPTlsIndex);
        v51 = v50;
        if ( v50 )
        {
          v52 = (void *)v50[405];
          if ( v52 != (void *)-1LL )
          {
            CloseHandle(v52);
            v51[405] = -1;
          }
        }
      }
      return NextNamedZipInfo;
    default:
      goto LABEL_90;
  }
}

```

## disassembly

```asm
0x18000fe10  push    rbp
0x18000fe12  push    rbx
0x18000fe13  push    r15
0x18000fe15  lea     rbp, [rsp-1790h]
0x18000fe1d  mov     eax, 1890h
0x18000fe22  call    _alloca_probe
0x18000fe27  sub     rsp, rax
0x18000fe2a  mov     rax, cs:__security_cookie
0x18000fe31  xor     rax, rsp
0x18000fe34  mov     [rbp+17A0h+var_30], rax
0x18000fe3b  mov     r15, rcx
0x18000fe3e  xor     edx, edx; Val
0x18000fe40  lea     rcx, [rbp+17A0h+var_10C0]; void *
0x18000fe47  mov     r8d, 1086h; Size
0x18000fe4d  call    memset_0
0x18000fe52  xor     edx, edx; Val
0x18000fe54  lea     rcx, [rsp+18A0h+Src]; void *
0x18000fe59  mov     r8d, 7A4h; Size
0x18000fe5f  call    memset_0
0x18000fe64  mov     ecx, cs:dwUnZIPTlsIndex; dwTlsIndex
0x18000fe6a  call    cs:__imp_TlsGetValue
0x18000fe70  mov     rbx, rax
0x18000fe73  test    rax, rax
0x18000fe76  jnz     short loc_18000FE9F
0x18000fe78  call    DunzipThreadInit
0x18000fe7d  test    eax, eax
0x18000fe7f  jz      short loc_18000FE95
0x18000fe81  mov     ecx, cs:dwUnZIPTlsIndex; dwTlsIndex
0x18000fe87  call    cs:__imp_TlsGetValue
0x18000fe8d  mov     rbx, rax
0x18000fe90  test    rax, rax
0x18000fe93  jnz     short loc_18000FE9F
0x18000fe95  mov     eax, 4
0x18000fe9a  jmp     loc_1800102AB
0x18000fe9f  cmp     dword ptr [rbx+54h], 0
0x18000fea3  jz      short loc_18000FEAF
0x18000fea5  mov     eax, 2Dh ; '-'
0x18000feaa  jmp     loc_1800102AB
0x18000feaf  mov     dword ptr [rbx+54h], 1
0x18000feb6  lea     rcx, [rsp+18A0h+Src]; void *
0x18000febb  mov     qword ptr [rbx+0CA8h], 0FFFFFFFFFFFFFFFFh
0x18000fec6  mov     edx, 2000h
0x18000fecb  mov     [rsp+18A0h+var_18], r13
0x18000fed3  mov     eax, 2800h
0x18000fed8  xor     r13d, r13d
0x18000fedb  mov     [rbx], r13
0x18000fede  mov     [rbx+8], r13
0x18000fee2  mov     [rbx+10h], r13d
0x18000fee6  mov     [rbx+28h], r13
0x18000feea  mov     [rbx+30h], r13
0x18000feee  mov     [rbx+38h], r13
0x18000fef2  mov     [rbx+40h], r13
0x18000fef6  mov     [rbx+0ED8h], r13
0x18000fefd  mov     [rbx+0EE8h], r13
0x18000ff04  cmp     dword ptr [r15+4], 9
0x18000ff09  cmovz   eax, edx
0x18000ff0c  mov     [rbx+48h], eax
0x18000ff0f  mov     eax, 0F000h
0x18000ff14  cmovz   eax, edx
0x18000ff17  mov     rdx, r15; Src
0x18000ff1a  mov     [rbx+4Ch], eax
0x18000ff1d  mov     [rsp+18A0h+Src], 7A4h
0x18000ff25  call    CopyUCS
0x18000ff2a  test    eax, eax
0x18000ff2c  jnz     loc_18001067B
0x18000ff32  cmp     [rsp+18A0h+Src], 7A4h
0x18000ff3a  jnz     loc_18001067B
0x18000ff40  mov     rax, [rbp+17A0h+var_1818]
0x18000ff44  mov     [rbx+0ED8h], rax
0x18000ff4b  mov     rax, [rbp+17A0h+var_17F4]
0x18000ff4f  mov     [rbx+0EE0h], rax
0x18000ff56  mov     rax, [rbp+17A0h+var_1810]
0x18000ff5a  mov     [rsp+18A0h+arg_8], rsi
0x18000ff62  mov     [rbx+0EE8h], rax
0x18000ff69  mov     rax, [rsp+18A0h+var_1868]
0x18000ff6e  mov     [rsp+18A0h+arg_10], rdi
0x18000ff76  mov     [rsp+18A0h+var_20], r14
0x18000ff7e  test    rax, rax
0x18000ff81  jz      loc_18001066D
0x18000ff87  cmp     [rax], r13w
0x18000ff8b  jz      loc_18001066D
0x18000ff91  mov     esi, 42h ; 'B'
0x18000ff96  lea     rdi, [rbx+12C8h]
0x18000ff9d  mov     ecx, esi
0x18000ff9f  mov     rax, rdi
0x18000ffa2  mov     [rax], r13b
0x18000ffa5  lea     rax, [rax+1]
0x18000ffa9  sub     rcx, 1
0x18000ffad  jnz     short loc_18000FFA2
0x18000ffaf  mov     r14d, 7FFFFFFEh
0x18000ffb5  cmp     [rsp+18A0h+var_1824], r13d
0x18000ffba  jz      short loc_18001000B
0x18000ffbc  mov     rcx, [rbp+17A0h+lpString]; lpString
0x18000ffc0  test    rcx, rcx
0x18000ffc3  jz      loc_18001066D
0x18000ffc9  call    cs:__imp_lstrlenA
0x18000ffcf  cmp     eax, 41h ; 'A'
0x18000ffd2  jg      loc_18001066D
0x18000ffd8  mov     rdx, [rbp+17A0h+lpString]
0x18000ffdc  mov     eax, r14d
0x18000ffdf  nop
0x18000ffe0  test    rax, rax
0x18000ffe3  jz      short loc_18000FFFD
0x18000ffe5  movzx   ecx, byte ptr [rdx]
0x18000ffe8  test    cl, cl
0x18000ffea  jz      short loc_18000FFFD
0x18000ffec  mov     [rdi], cl
0x18000ffee  inc     rdx
0x18000fff1  inc     rdi
0x18000fff4  dec     rax
0x18000fff7  sub     rsi, 1
0x18000fffb  jnz     short loc_18000FFE0
0x18000fffd  test    rsi, rsi
0x180010000  lea     rax, [rdi-1]
0x180010004  cmovnz  rax, rdi
0x180010008  mov     [rax], r13b
0x18001000b  cmp     [rsp+18A0h+var_1844], r13d
0x180010010  mov     eax, r13d
0x180010013  mov     [rsp+18A0h+arg_18], r12
0x18001001b  setnz   al
0x18001001e  mov     [rbx+4], eax
0x180010021  mov     eax, [rbp+17A0h+var_1800]
0x180010024  mov     [rbx+28h], rax
0x180010028  mov     rax, [rbp+17A0h+var_1808]
0x18001002c  test    rax, rax
0x18001002f  jz      short loc_18001005C
0x180010031  mov     [rbx+30h], rax
0x180010035  mov     rcx, [rsp+18A0h+var_1860]
0x18001003a  test    rcx, rcx
0x18001003d  jz      short loc_18001004E
0x18001003f  cmp     [rcx], r13w
0x180010043  jz      short loc_18001004E
0x180010045  call    IsSingleFileSpec
0x18001004a  test    eax, eax
0x18001004c  jnz     short loc_180010055
0x18001004e  cmp     [rsp+18A0h+var_1858], r13d
0x180010053  jl      short loc_18001005C
0x180010055  mov     dword ptr [rbx+10h], 1
0x18001005c  lea     rdx, [rbx+670h]; lpBuffer
0x180010063  mov     ecx, 103h; nBufferLength
0x180010068  call    cs:__imp_GetCurrentDirectoryW
0x18001006e  mov     rax, [rsp+18A0h+var_1868]
0x180010073  lea     rsi, [rbx+58h]
0x180010077  test    rax, rax
0x18001007a  jz      short loc_1800100BA
0x18001007c  mov     rcx, rsi
0x18001007f  test    rsi, rsi
0x180010082  jz      short loc_1800100BA
0x180010084  mov     r8d, r13d
0x180010087  cmp     [rax], r13w
0x18001008b  jz      short loc_1800100B6
0x18001008d  nop     dword ptr [rax]
0x180010090  cmp     r8d, 103h
0x180010097  jge     short loc_1800100B6
0x180010099  movzx   edx, word ptr [rax]
0x18001009c  cmp     dx, 22h ; '"'
0x1800100a0  jz      short loc_1800100AC
0x1800100a2  mov     [rcx], dx
0x1800100a5  add     rcx, 2
0x1800100a9  inc     r8d
0x1800100ac  add     rax, 2
0x1800100b0  cmp     [rax], r13w
0x1800100b4  jnz     short loc_180010090
0x1800100b6  mov     [rcx], r13w
0x1800100ba  mov     r8d, 104h
0x1800100c0  lea     r9, [rbx+11360h]
0x1800100c7  mov     r10d, r8d
0x1800100ca  mov     rax, r14
0x1800100cd  mov     rdx, rsi
0x1800100d0  test    rax, rax
0x1800100d3  jz      short loc_1800100F2
0x1800100d5  movzx   ecx, word ptr [rdx]
0x1800100d8  test    cx, cx
0x1800100db  jz      short loc_1800100F2
0x1800100dd  mov     [r9], cx
0x1800100e1  add     rdx, 2
0x1800100e5  add     r9, 2
0x1800100e9  dec     rax
0x1800100ec  sub     r10, 1
0x1800100f0  jnz     short loc_1800100D0
0x1800100f2  test    r10, r10
0x1800100f5  lea     rcx, [r9-2]
0x1800100f9  mov     rdx, rsi
0x1800100fc  lea     rax, [rbx+260h]
0x180010103  cmovnz  rcx, r9
0x180010107  mov     [rcx], r13w
0x18001010b  nop     dword ptr [rax+rax+00h]
0x180010110  test    r14, r14
0x180010113  jz      short loc_180010131
0x180010115  movzx   ecx, word ptr [rdx]
0x180010118  test    cx, cx
0x18001011b  jz      short loc_180010131
0x18001011d  mov     [rax], cx
0x180010120  add     rdx, 2
0x180010124  add     rax, 2
0x180010128  dec     r14
0x18001012b  sub     r8, 1
0x18001012f  jnz     short loc_180010110
0x180010131  test    r8, r8
0x180010134  lea     rcx, [rax-2]
0x180010138  cmovnz  rcx, rax
0x18001013c  mov     [rcx], r13w
0x180010140  cmp     [rbx+1138h], r13d
0x180010147  jz      short loc_18001018F
0x180010149  mov     eax, [rsp+18A0h+var_186C]
0x18001014d  add     eax, 0FFFFFFFEh
0x180010150  test    eax, 0FFFFFFFDh
0x180010155  jnz     short loc_18001018F
0x180010157  mov     qword ptr [rbx+0CA8h], 0FFFFFFFFFFFFFFFFh
0x180010162  mov     eax, [rsp+18A0h+var_186C]
0x180010166  cmp     eax, 7
0x180010169  jz      loc_1800105FC
0x18001016f  dec     eax; switch 9 cases
0x180010171  cmp     eax, 8
0x180010174  ja      def_18001018D; jumptable 000000018001018D default case, cases 5-7
0x18001017a  lea     rdx, __ImageBase
0x180010181  cdqe
0x180010183  mov     ecx, ds:(jpt_18001018D - 180000000h)[rdx+rax*4]
0x18001018a  add     rcx, rdx
0x18001018d  jmp     rcx; switch jump
0x18001018f  call    OpenCurrentZIP
0x180010194  test    rax, rax
0x180010197  jnz     short loc_180010162
0x180010199  mov     ecx, cs:dwUnZIPTlsIndex; dwTlsIndex
0x18001019f  mov     [rbx+54h], r13d
0x1800101a3  call    cs:__imp_TlsGetValue
0x1800101a9  test    rax, rax
0x1800101ac  jz      short loc_1800101E0
0x1800101ae  mov     ecx, cs:dwUnZIPTlsIndex; dwTlsIndex
0x1800101b4  call    cs:__imp_TlsGetValue
0x1800101ba  mov     rbx, rax
0x1800101bd  test    rax, rax
0x1800101c0  jz      short loc_1800101E0
0x1800101c2  mov     rcx, [rax+0CA8h]; hObject
0x1800101c9  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800101cd  jz      short loc_1800101E0
0x1800101cf  call    cs:__imp_CloseHandle
0x1800101d5  mov     qword ptr [rbx+0CA8h], 0FFFFFFFFFFFFFFFFh
0x1800101e0  mov     eax, 9
0x1800101e5  jmp     loc_180010283
0x1800101ea  mov     rcx, rbx; jumptable 000000018001018D case 1
0x1800101ed  mov     [rbx+10D0h], r13d
0x1800101f4  call    DeAllocCDirCache
0x1800101f9  test    eax, eax
0x1800101fb  jnz     short loc_180010207
0x1800101fd  mov     edi, 5
0x180010202  jmp     loc_180010608
0x180010207  lea     rcx, [rsp+18A0h+Src]
0x18001020c  call    CountAllZipMembers
0x180010211  jmp     loc_180010606
0x180010216  lea     rcx, [rsp+18A0h+Src]; jumptable 000000018001018D case 2
0x18001021b  call    GetNextZipInfo
0x180010220  jmp     short loc_180010258
0x180010222  mov     rcx, rbx; jumptable 000000018001018D case 3
0x180010225  mov     [rbx+10D0h], r13d
0x18001022c  call    DeAllocCDirCache
0x180010231  test    eax, eax
0x180010233  jnz     short loc_18001023F
0x180010235  mov     edi, 5
0x18001023a  jmp     loc_180010608
0x18001023f  lea     rcx, [rsp+18A0h+Src]
0x180010244  call    CountNamedZipMembers
0x180010249  jmp     loc_180010606
0x18001024e  lea     rcx, [rsp+18A0h+Src]; jumptable 000000018001018D case 4
0x180010253  call    GetNextNamedZipInfo
0x180010258  mov     edi, eax
0x18001025a  lea     rdx, [rsp+18A0h+Src]; Src
0x18001025f  mov     rcx, r15; void *
0x180010262  call    CopyUCS
0x180010267  mov     [rbx+54h], r13d
0x18001026b  mov     ecx, cs:dwUnZIPTlsIndex; dwTlsIndex
0x180010271  call    cs:__imp_TlsGetValue
0x180010277  test    rax, rax
0x18001027a  jz      short loc_180010281
0x18001027c  call    CloseCurrentZIP
0x180010281  mov     eax, edi
0x180010283  mov     r12, [rsp+18A0h+arg_18]
0x18001028b  mov     rsi, [rsp+18A0h+arg_8]
0x180010293  mov     rdi, [rsp+18A0h+arg_10]
0x18001029b  mov     r14, [rsp+18A0h+var_20]
0x1800102a3  mov     r13, [rsp+18A0h+var_18]
0x1800102ab  mov     rcx, [rbp+17A0h+var_30]
0x1800102b2  xor     rcx, rsp; StackCookie
0x1800102b5  call    __security_check_cookie
0x1800102ba  add     rsp, 1890h
0x1800102c1  pop     r15
0x1800102c3  pop     rbx
0x1800102c4  pop     rbp
0x1800102c5  retn
0x1800102c6  mov     rax, [rsp+18A0h+var_1854]; jumptable 000000018001018D case 8
0x1800102cb  test    rax, rax
0x1800102ce  jz      loc_18001039C
0x1800102d4  lea     rdi, [rbx+468h]
0x1800102db  mov     rcx, rdi
0x1800102de  test    rdi, rdi
0x1800102e1  jz      short loc_18001031A
0x1800102e3  mov     r8d, r13d
0x1800102e6  cmp     [rax], r13w
0x1800102ea  jz      short loc_180010316
0x1800102ec  nop     dword ptr [rax+00h]
  ... truncated ...
```
