# ProcessIisRequest

- ea: `0x1400213a8`
- end: `0x140021d48`
- name: `ProcessIisRequest`
- size: `2464`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140022480`

## callees

- `0x14001b1b8`
- `0x14001ba48`
- `0x14001e3c8`
- `0x1400213a8`
- `0x1400400d6`

## import_xrefs

- `msvcrt!_stricmp` at `0x140021449`
- `msvcrt!_stricmp` at `0x140021449`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140021d31`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140021d31`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140021618`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140021d23`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140021618`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140021d23`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14002162a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14002162a`
- `ntdll!RtlEnterCriticalSection` at `0x14002142c`
- `ntdll!RtlEnterCriticalSection` at `0x14002154a`
- `ntdll!RtlEnterCriticalSection` at `0x1400215d8`
- `ntdll!RtlEnterCriticalSection` at `0x140021671`
- `ntdll!RtlEnterCriticalSection` at `0x14002142c`
- `ntdll!RtlEnterCriticalSection` at `0x14002154a`
- `ntdll!RtlEnterCriticalSection` at `0x1400215d8`
- `ntdll!RtlEnterCriticalSection` at `0x140021671`
- `ntdll!RtlLeaveCriticalSection` at `0x140021465`
- `ntdll!RtlLeaveCriticalSection` at `0x1400214c2`
- `ntdll!RtlLeaveCriticalSection` at `0x14002159c`
- `ntdll!RtlLeaveCriticalSection` at `0x1400215f5`
- `ntdll!RtlLeaveCriticalSection` at `0x140021612`
- `ntdll!RtlLeaveCriticalSection` at `0x14002164b`
- `ntdll!RtlLeaveCriticalSection` at `0x1400216a7`
- `ntdll!RtlLeaveCriticalSection` at `0x140021465`
- `ntdll!RtlLeaveCriticalSection` at `0x1400214c2`
- `ntdll!RtlLeaveCriticalSection` at `0x14002159c`
- `ntdll!RtlLeaveCriticalSection` at `0x1400215f5`
- `ntdll!RtlLeaveCriticalSection` at `0x140021612`
- `ntdll!RtlLeaveCriticalSection` at `0x14002164b`
- `ntdll!RtlLeaveCriticalSection` at `0x1400216a7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14002163d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14002163d`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x14002157a`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x14002157a`

## pseudocode

```c
void __fastcall ProcessIisRequest(__int64 a1)
{
  char *v2; // rcx
  __int64 v3; // rbp
  unsigned int v4; // r15d
  char *v5; // r8
  unsigned int v6; // edx
  char *v7; // r14
  __int64 v8; // rax
  __int64 v9; // r12
  char v10; // r13
  __int64 v11; // rbx
  __int64 v12; // rbx
  struct _URL_RECORD *v13; // rsi
  struct _URL_RECORD *v14; // rax
  struct _URL_RECORD **v15; // rcx
  struct _URL_RECORD *v16; // rax
  int v17; // ecx
  unsigned int v18; // ebp
  unsigned __int16 v19; // r15
  struct _CLIENT_RECORD *i; // r14
  int v21; // ebp
  LPVOID *j; // rbx
  HANDLE ProcessHeap; // rax
  LPVOID *v24; // rax
  _QWORD *v25; // rax
  __int16 v26; // ax
  unsigned __int64 v27; // rcx
  unsigned __int64 v28; // rdx
  unsigned __int64 v29; // rax
  unsigned __int64 v30; // rsi
  unsigned __int64 v31; // r8
  unsigned __int64 v32; // r10
  unsigned __int64 v33; // r9
  __int16 v34; // r11
  unsigned __int64 v35; // r11
  _QWORD *v36; // rcx
  unsigned __int64 v37; // r11
  unsigned __int64 v38; // rdx
  unsigned __int64 v39; // rax
  unsigned __int64 v40; // rax
  _DWORD *v41; // rdx
  __int64 v42; // r11
  __int16 v43; // ax
  __int64 v44; // rax
  unsigned __int64 v45; // r8
  unsigned __int64 v46; // rdx
  __int64 v47; // rax
  void *v48; // rbx
  HANDLE v49; // rax

  v2 = *(char **)(a1 + 712);
  if ( v2 )
  {
    v3 = -1;
    do
      ++v3;
    while ( v2[v3] );
    v4 = 0;
    v5 = &v2[(unsigned int)v3];
    v6 = 0;
    v7 = v2;
    while ( v2 != v5 && *v2 != 63 )
    {
      ++v6;
      ++v2;
    }
    v8 = v6 - 1;
    if ( *(v2 - 1) != 47 )
      v8 = v6;
    v9 = (unsigned int)v8;
    v10 = v7[v8];
    v7[v8] = 0;
    v11 = (unsigned __int16)UrlHashKey(v7, (unsigned int)v8);
    RtlEnterCriticalSection(&TLCritSect);
    v12 = qword_1400821F0 + 16 * v11;
    v13 = *(struct _URL_RECORD **)v12;
    while ( 1 )
    {
      if ( v13 == (struct _URL_RECORD *)v12 )
      {
        RtlLeaveCriticalSection(&TLCritSect);
        v7[v9] = v10;
        goto LABEL_23;
      }
      if ( !_stricmp(v7, *((const char **)v13 + 8)) )
        break;
      v13 = *(struct _URL_RECORD **)v13;
      ++v4;
    }
    if ( v4 <= 0x14 )
      goto LABEL_20;
    v14 = *(struct _URL_RECORD **)v13;
    if ( *(struct _URL_RECORD **)(*(_QWORD *)v13 + 8LL) != v13 )
      goto LABEL_47;
    v15 = (struct _URL_RECORD **)*((_QWORD *)v13 + 1);
    if ( *v15 != v13 )
      goto LABEL_47;
    *v15 = v14;
    *((_QWORD *)v14 + 1) = v15;
    v16 = *(struct _URL_RECORD **)v12;
    if ( *(_QWORD *)(*(_QWORD *)v12 + 8LL) != v12 )
      goto LABEL_47;
    *(_QWORD *)v13 = v16;
    *((_QWORD *)v13 + 1) = v12;
    *((_QWORD *)v16 + 1) = v13;
    *(_QWORD *)v12 = v13;
LABEL_20:
    RtlLeaveCriticalSection(&TLCritSect);
    if ( v13 )
    {
LABEL_24:
      v17 = *(_DWORD *)(a1 + 40);
      ++*((_DWORD *)v13 + 10);
      *((_DWORD *)v13 + 4) = v17;
      *((_QWORD *)v13 + 7) += *(_QWORD *)(a1 + 104);
      *((_DWORD *)v13 + 5) += *(_DWORD *)(a1 + 48);
      *((_DWORD *)v13 + 6) += *(_DWORD *)(a1 + 52);
      *((_DWORD *)v13 + 7) += *(_DWORD *)(a1 + 80);
      *((_DWORD *)v13 + 8) += *(_DWORD *)(a1 + 84);
      *((_DWORD *)v13 + 12) += *(_DWORD *)(a1 + 44);
      *((_DWORD *)v13 + 11) = *(__int16 *)(a1 + 188);
      goto LABEL_25;
    }
  }
  else
  {
    LODWORD(v3) = 0;
    v7 = 0;
  }
LABEL_23:
  v13 = AddUrlRecord(v7, v3);
  if ( v13 )
    goto LABEL_24;
LABEL_25:
  v18 = *(_DWORD *)(a1 + 688);
  v19 = *(_WORD *)(a1 + 684);
  if ( a1 != -692 )
  {
    RtlEnterCriticalSection(&TLCritSect);
    for ( i = (struct _CLIENT_RECORD *)qword_1400821F8; ; i = *(struct _CLIENT_RECORD **)i )
    {
      if ( i == (struct _CLIENT_RECORD *)&qword_1400821F8 )
      {
        RtlLeaveCriticalSection(&TLCritSect);
        goto LABEL_33;
      }
      if ( *((_WORD *)i + 20) == v19
        && *((_DWORD *)i + 11) == v18
        && RtlCompareMemory((const void *)(a1 + 692), (char *)i + 48, 0x10u) == 16 )
      {
        break;
      }
    }
    RtlLeaveCriticalSection(&TLCritSect);
    if ( i )
      goto LABEL_34;
  }
LABEL_33:
  i = AddClientRecord(v19, v18, (unsigned __int16 *)(a1 + 692));
  if ( i )
  {
LABEL_34:
    ++*((_DWORD *)i + 5);
    *((_QWORD *)i + 4) += *(_QWORD *)(a1 + 104);
    *((_DWORD *)i + 6) += *(_DWORD *)(a1 + 44);
  }
  v21 = *(_DWORD *)(a1 + 40);
  RtlEnterCriticalSection(&TLCritSect);
  for ( j = (LPVOID *)qword_140082208; ; j = (LPVOID *)*j )
  {
    if ( j == &qword_140082208 )
    {
      RtlLeaveCriticalSection(&TLCritSect);
      goto LABEL_42;
    }
    if ( *((_DWORD *)j + 4) == v21 )
      break;
  }
  RtlLeaveCriticalSection(&TLCritSect);
  if ( j )
  {
LABEL_50:
    ++*((_DWORD *)j + 10);
    j[6] = (char *)j[6] + *(_QWORD *)(a1 + 104);
    *((_DWORD *)j + 5) += *(_DWORD *)(a1 + 48);
    *((_DWORD *)j + 6) += *(_DWORD *)(a1 + 52);
    *((_DWORD *)j + 7) += *(_DWORD *)(a1 + 80);
    *((_DWORD *)j + 8) += *(_DWORD *)(a1 + 84);
    *((_DWORD *)j + 11) += *(_DWORD *)(a1 + 44);
    goto LABEL_51;
  }
LABEL_42:
  ProcessHeap = GetProcessHeap();
  v24 = (LPVOID *)HeapAlloc(ProcessHeap, 8u, 0x50u);
  j = v24;
  if ( !v24 )
  {
    SetLastError(0xEu);
    j = 0;
    goto LABEL_49;
  }
  memset_0(v24, 0, 0x50u);
  *((_DWORD *)j + 4) = v21;
  RtlEnterCriticalSection(&TLCritSect);
  v25 = qword_140082208;
  if ( *((LPVOID **)qword_140082208 + 1) != &qword_140082208 )
LABEL_47:
    __fastfail(3u);
  j[1] = &qword_140082208;
  *j = v25;
  v25[1] = j;
  qword_140082208 = j;
  RtlLeaveCriticalSection(&TLCritSect);
LABEL_49:
  if ( j )
    goto LABEL_50;
LABEL_51:
  if ( !*(_DWORD *)(a1 + 24) )
  {
    v26 = *(_WORD *)(a1 + 138);
    if ( v26 != 14 && v26 != 20 )
      goto LABEL_54;
LABEL_72:
    v36 = qword_1400846F8;
    ++*((_DWORD *)qword_1400846F8 + 1);
    v36[1] += *(_QWORD *)(a1 + 104);
    *((_DWORD *)v36 + 79) += *(_DWORD *)(a1 + 48) + *(_DWORD *)(a1 + 52);
    if ( v13 )
      ++*((_DWORD *)v13 + 9);
    if ( i )
      ++*((_DWORD *)i + 4);
    if ( j )
      ++*((_DWORD *)j + 9);
    goto LABEL_160;
  }
  if ( *(_DWORD *)(a1 + 24) == 1 && (unsigned __int16)(*(_WORD *)(a1 + 138) - 25) <= 1u )
    goto LABEL_72;
LABEL_54:
  v27 = *(_QWORD *)(a1 + 144);
  if ( v27 )
  {
    v28 = *(_QWORD *)(a1 + 152);
    if ( !v28 )
      goto LABEL_58;
    if ( v28 < v27 )
      goto LABEL_161;
    if ( v28 > *(_QWORD *)(a1 + 128) )
    {
LABEL_58:
      v28 = *(_QWORD *)(a1 + 128);
      *(_QWORD *)(a1 + 152) = v28;
      if ( !v28 || v28 < v27 )
        goto LABEL_161;
    }
    v29 = *(_QWORD *)(a1 + 160);
    v30 = *(_QWORD *)(a1 + 208);
    v31 = v28 - v27;
    v32 = *(_QWORD *)(a1 + 224);
    v33 = *(_QWORD *)(a1 + 248);
    if ( v28 - v27 < v29 )
    {
      *(_QWORD *)(a1 + 160) = v31;
      v29 = v28 - v27;
    }
    v34 = *(_WORD *)(a1 + 188);
    if ( v34 != 11 )
    {
      if ( v34 == 12 )
      {
        v37 = *(_QWORD *)(a1 + 216);
        if ( !v37 )
          goto LABEL_161;
        if ( !v32 || v32 > v28 )
        {
          if ( v37 > v28 )
            goto LABEL_161;
          v32 = v28;
        }
        if ( v37 >= v27 )
          v27 = *(_QWORD *)(a1 + 216);
        else
          *(_QWORD *)(a1 + 216) = v27;
        if ( v32 < v27 )
          v32 = v27;
        v38 = v32 - v27;
        if ( v32 - v27 + v29 > v31 )
          *(_QWORD *)(a1 + 160) = v27 + v31 - v32;
        v39 = *(_QWORD *)(a1 + 240);
        if ( v39 )
        {
          if ( !v33 )
          {
            if ( v39 > v32 )
              goto LABEL_161;
            v33 = v32;
          }
          if ( v39 >= v27 )
            v27 = *(_QWORD *)(a1 + 240);
          else
            *(_QWORD *)(a1 + 240) = v27;
          if ( v33 < v27 )
            v33 = v27;
          if ( v38 < v33 - v27 )
            v33 = v32;
        }
      }
      else if ( v34 == 1 )
      {
        if ( v29 > v31 )
          *(_QWORD *)(a1 + 160) = v31;
        v40 = *(_QWORD *)(a1 + 240);
        if ( v40 )
        {
          if ( !v33 || v33 > v28 )
          {
            if ( v40 > v28 )
              goto LABEL_161;
            v33 = v28;
          }
          if ( v40 >= v27 )
          {
            v32 = *(_QWORD *)(a1 + 240);
          }
          else
          {
            *(_QWORD *)(a1 + 240) = v27;
            v32 = v27;
          }
          *(_QWORD *)(a1 + 216) = v32;
          if ( v33 < v32 )
            v33 = v32;
          if ( v31 < v33 - v32 )
            v33 = v28;
        }
      }
LABEL_122:
      v41 = (_DWORD *)(a1 + 64);
      v36 = qword_1400846F8;
      *((_QWORD *)qword_1400846F8 + 2) += *(_QWORD *)(a1 + 104);
      *((_DWORD *)v36 + 80) += *(_DWORD *)(a1 + 48) + *(_DWORD *)(a1 + 52);
      if ( *(_QWORD *)(a1 + 160) )
      {
        *((_DWORD *)v36 + 11) += *(_DWORD *)(a1 + 184);
        v36[7] += *(_QWORD *)(a1 + 160);
        *((_DWORD *)v36 + 16) += *v41;
      }
      v42 = *(_QWORD *)(a1 + 216);
      if ( v42 )
        goto LABEL_131;
      if ( *(_DWORD *)(a1 + 24) )
      {
        if ( *(_DWORD *)(a1 + 24) != 1 || *(_WORD *)(a1 + 138) != 23 )
        {
LABEL_131:
          if ( *(_WORD *)(a1 + 272) < 0x190u )
          {
            v43 = *(_WORD *)(a1 + 188);
            if ( v43 == 10 )
            {
              ++*((_DWORD *)v36 + 6);
              v36[10] += *(_QWORD *)(a1 + 104);
              *((_DWORD *)v36 + 81) += *(_DWORD *)(a1 + 48) + *(_DWORD *)(a1 + 52);
              *((_DWORD *)v36 + 17) += *(_DWORD *)(a1 + 56);
              *((_DWORD *)v36 + 18) += *(_DWORD *)(a1 + 60);
              *((_DWORD *)v36 + 19) += *v41;
              if ( j )
                ++*((_DWORD *)j + 14);
              v36[12] += *(_QWORD *)(a1 + 152) - *(_QWORD *)(a1 + 160) - *(_QWORD *)(a1 + 144);
              v36[11] += *(_QWORD *)(a1 + 104) + *(_QWORD *)(a1 + 144) - *(_QWORD *)(a1 + 152);
              v36[13] += *(_QWORD *)(a1 + 160);
            }
            else if ( v43 == 11 )
            {
              ++*((_DWORD *)v36 + 7);
              v36[16] += *(_QWORD *)(a1 + 104);
              v36[17] += v30 - *(_QWORD *)(a1 + 200);
              *((_DWORD *)v36 + 82) += *(_DWORD *)(a1 + 48) + *(_DWORD *)(a1 + 52);
              *((_DWORD *)v36 + 28) += *(_DWORD *)(a1 + 76);
              *((_DWORD *)v36 + 29) += *(_DWORD *)(a1 + 56);
              *((_DWORD *)v36 + 30) += *(_DWORD *)(a1 + 60);
              *((_DWORD *)v36 + 31) += *v41;
              if ( j )
                ++*((_DWORD *)j + 15);
              v36[19] += *(_QWORD *)(a1 + 200)
                       + *(_QWORD *)(a1 + 152)
                       - *(_QWORD *)(a1 + 160)
                       - *(_QWORD *)(a1 + 144)
                       - v30;
              v36[18] += *(_QWORD *)(a1 + 104) + *(_QWORD *)(a1 + 144) - *(_QWORD *)(a1 + 152);
              v36[20] += *(_QWORD *)(a1 + 160);
            }
            else if ( *(_DWORD *)(a1 + 24) == 1 && v43 == 1 || v43 == 12 )
            {
              v44 = *(_QWORD *)(a1 + 240);
              v45 = 0;
              v46 = 0;
              if ( v44 && v33 )
                v45 = v33 - v44;
              if ( v42 && v32 )
              {
                if ( v45 <= v32 - v42 )
                  v46 = v32 - v42 - v45;
                else
                  v46 = 0;
              }
              ++*((_DWORD *)v36 + 8);
              v36[24] += *(_QWORD *)(a1 + 104);
              *((_DWORD *)v36 + 83) += *(_DWORD *)(a1 + 48) + *(_DWORD *)(a1 + 52);
              if ( j )
                ++*((_DWORD *)j + 16);
              v47 = *(_QWORD *)(a1 + 152) - *(_QWORD *)(a1 + 160) - *(_QWORD *)(a1 + 144);
              ++*((_DWORD *)v36 + 9);
              v36[28] += v47 - v46 - v45;
              v36[25] += *(_QWORD *)(a1 + 104);
              v36[26] += v45;
              *((_DWORD *)v36 + 84) += *(_DWORD *)(a1 + 48) + *(_DWORD *)(a1 + 52);
              *((_DWORD *)v36 + 42) += *(_DWORD *)(a1 + 72);
              *((_DWORD *)v36 + 43) += *(_DWORD *)(a1 + 56);
              *((_DWORD *)v36 + 44) += *(_DWORD *)(a1 + 60);
              *((_DWORD *)v36 + 46) += *(_DWORD *)(a1 + 64);
              *((_DWORD *)v36 + 45) += *(_DWORD *)(a1 + 68);
              if ( j )
                ++*((_DWORD *)j + 18);
              v36[29] += v46;
              v36[27] += *(_QWORD *)(a1 + 104) + *(_QWORD *)(a1 + 144) - *(_QWORD *)(a1 + 152);
              v36[30] += *(_QWORD *)(a1 + 160);
            }
            else if ( v43 == 13 )
            {
              ++*((_DWORD *)v36 + 10);
              v36[38] += *(_QWORD *)(a1 + 104);
              *((_DWORD *)v36 + 86) += *(_DWORD *)(a1 + 48) + *(_DWORD *)(a1 + 52);
              if ( j )
                ++*((_DWORD *)j + 17);
            }
          }
          else
          {
            ++*((_DWORD *)v36 + 12);
            v36[34] += *(_QWORD *)(a1 + 104);
            *((_DWORD *)v36 + 85) += *(_DWORD *)(a1 + 48) + *(_DWORD *)(a1 + 52);
            *((_DWORD *)v36 + 62) += *(_DWORD *)(a1 + 56);
            *((_DWORD *)v36 + 63) += *(_DWORD *)(a1 + 60);
            *((_DWORD *)v36 + 64) += *(_DWORD *)(a1 + 64);
            *((_DWORD *)v36 + 65) += *(_DWORD *)(a1 + 76);
            *((_DWORD *)v36 + 66) += *(_DWORD *)(a1 + 68);
            *((_DWORD *)v36 + 67) += *(_DWORD *)(a1 + 72);
            v36[36] += *(_QWORD *)(a1 + 152) - *(_QWORD *)(a1 + 160) - *(_QWORD *)(a1 + 144);
            v36[35] += *(_QWORD *)(a1 + 104) + *(_QWORD *)(a1 + 144) - *(_QWORD *)(a1 + 152);
            v36[37] += *(_QWORD *)(a1 + 160);
          }
LABEL_160:
          ++*(_DWORD *)v36;
          *((_DWORD *)v36 + 78) += *(_DWORD *)(a1 + 48) + *(_DWORD *)(a1 + 52);
          goto LABEL_162;
        }
      }
      else if ( *(_WORD *)(a1 + 138) != 19 )
      {
        v41 = (_DWORD *)(a1 + 64);
        goto LABEL_131;
      }
      ++dword_1400846EC;
      goto LABEL_131;
    }
    v35 = *(_QWORD *)(a1 + 200);
    if ( v35 )
    {
      if ( v30 && v30 <= v28 )
      {
LABEL_68:
        if ( v35 >= v27 )
          v27 = *(_QWORD *)(a1 + 200);
        else
          *(_QWORD *)(a1 + 200) = v27;
        if ( v30 < v27 )
          v30 = v27;
        if ( v30 + v29 - v27 > v31 )
          *(_QWORD *)(a1 + 160) = v27 + v31 - v30;
        goto LABEL_122;
      }
      if ( v35 <= v28 )
      {
        v30 = v28;
        goto LABEL_68;
      }
    }
  }
LABEL_161:
  ++dword_1400846F0;
LABEL_162:
  v48 = *(void **)(a1 + 712);
  if ( v48 )
  {
    v49 = GetProcessHeap();
    HeapFree(v49, 0, v48);
  }
}

```

## disassembly

```asm
0x1400213a8  push    rbx
0x1400213aa  push    rbp
0x1400213ab  push    rsi
0x1400213ac  push    rdi
0x1400213ad  push    r12
0x1400213af  push    r13
0x1400213b1  push    r14
0x1400213b3  push    r15
0x1400213b5  sub     rsp, 28h
0x1400213b9  mov     rdi, rcx
0x1400213bc  xor     r12d, r12d
0x1400213bf  mov     rcx, [rcx+2C8h]
0x1400213c6  mov     r13d, 1
0x1400213cc  test    rcx, rcx
0x1400213cf  jz      loc_1400214D7
0x1400213d5  or      rbp, 0FFFFFFFFFFFFFFFFh
0x1400213d9  inc     rbp
0x1400213dc  cmp     [rcx+rbp], r12b
0x1400213e0  jnz     short loc_1400213D9
0x1400213e2  mov     r8d, ebp
0x1400213e5  mov     r15d, r12d
0x1400213e8  add     r8, rcx
0x1400213eb  mov     edx, r12d
0x1400213ee  mov     r14, rcx
0x1400213f1  cmp     rcx, r8
0x1400213f4  jz      short loc_140021403
0x1400213f6  cmp     byte ptr [rcx], 3Fh ; '?'
0x1400213f9  jz      short loc_140021403
0x1400213fb  add     edx, r13d
0x1400213fe  add     rcx, r13
0x140021401  jmp     short loc_1400213F1
0x140021403  cmp     byte ptr [rcx-1], 2Fh ; '/'
0x140021407  lea     eax, [rdx-1]
0x14002140a  mov     rcx, r14
0x14002140d  cmovnz  eax, edx
0x140021410  mov     edx, eax
0x140021412  mov     r12d, eax
0x140021415  mov     r13b, [rax+r14]
0x140021419  mov     [rax+r14], r15b
0x14002141d  call    UrlHashKey
0x140021422  lea     rcx, ?TLCritSect@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x140021429  movzx   ebx, ax
0x14002142c  call    cs:__imp_RtlEnterCriticalSection
0x140021432  shl     rbx, 4
0x140021436  add     rbx, cs:qword_1400821F0
0x14002143d  mov     rsi, [rbx]
0x140021440  jmp     short loc_140021459
0x140021442  mov     rdx, [rsi+40h]; String2
0x140021446  mov     rcx, r14; String1
0x140021449  call    cs:__imp__stricmp
0x14002144f  test    eax, eax
0x140021451  jz      short loc_140021479
0x140021453  mov     rsi, [rsi]
0x140021456  inc     r15d
0x140021459  cmp     rsi, rbx
0x14002145c  jnz     short loc_140021442
0x14002145e  lea     rcx, ?TLCritSect@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x140021465  call    cs:__imp_RtlLeaveCriticalSection
0x14002146b  mov     [r12+r14], r13b
0x14002146f  xor     r12d, r12d
0x140021472  lea     r13d, [r12+1]
0x140021477  jmp     short loc_1400214DD
0x140021479  cmp     r15d, 14h
0x14002147d  jbe     short loc_1400214BB
0x14002147f  mov     rax, [rsi]
0x140021482  cmp     [rax+8], rsi
0x140021486  jnz     loc_14002168B
0x14002148c  mov     rcx, [rsi+8]
0x140021490  cmp     [rcx], rsi
0x140021493  jnz     loc_14002168B
0x140021499  mov     [rcx], rax
0x14002149c  mov     [rax+8], rcx
0x1400214a0  mov     rax, [rbx]
0x1400214a3  cmp     [rax+8], rbx
0x1400214a7  jnz     loc_14002168B
0x1400214ad  mov     [rsi], rax
0x1400214b0  mov     [rsi+8], rbx
0x1400214b4  mov     [rax+8], rsi
0x1400214b8  mov     [rbx], rsi
0x1400214bb  lea     rcx, ?TLCritSect@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x1400214c2  call    cs:__imp_RtlLeaveCriticalSection
0x1400214c8  xor     r12d, r12d
0x1400214cb  lea     r13d, [r12+1]
0x1400214d0  test    rsi, rsi
0x1400214d3  jz      short loc_1400214DD
0x1400214d5  jmp     short loc_1400214EF
0x1400214d7  mov     ebp, r12d
0x1400214da  mov     r14, rcx
0x1400214dd  mov     edx, ebp; unsigned int
0x1400214df  mov     rcx, r14; char *
0x1400214e2  call    ?AddUrlRecord@@YAPEAU_URL_RECORD@@PEADK@Z; AddUrlRecord(char *,ulong)
0x1400214e7  mov     rsi, rax
0x1400214ea  test    rax, rax
0x1400214ed  jz      short loc_140021529
0x1400214ef  mov     ecx, [rdi+28h]
0x1400214f2  add     [rsi+28h], r13d
0x1400214f6  mov     [rsi+10h], ecx
0x1400214f9  mov     rcx, [rdi+68h]
0x1400214fd  add     [rsi+38h], rcx
0x140021501  mov     eax, [rdi+30h]
0x140021504  add     [rsi+14h], eax
0x140021507  mov     eax, [rdi+34h]
0x14002150a  add     [rsi+18h], eax
0x14002150d  mov     eax, [rdi+50h]
0x140021510  add     [rsi+1Ch], eax
0x140021513  mov     eax, [rdi+54h]
0x140021516  add     [rsi+20h], eax
0x140021519  mov     eax, [rdi+2Ch]
0x14002151c  add     [rsi+30h], eax
0x14002151f  movsx   eax, word ptr [rdi+0BCh]
0x140021526  mov     [rsi+2Ch], eax
0x140021529  mov     ebp, [rdi+2B0h]
0x14002152f  lea     rbx, [rdi+2B4h]
0x140021536  movzx   r15d, word ptr [rdi+2ACh]
0x14002153e  test    rbx, rbx
0x140021541  jz      short loc_1400215A2
0x140021543  lea     rcx, ?TLCritSect@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x14002154a  call    cs:__imp_RtlEnterCriticalSection
0x140021550  mov     r14, cs:qword_1400821F8
0x140021557  lea     rax, qword_1400821F8
0x14002155e  jmp     short loc_140021590
0x140021560  cmp     [r14+28h], r15w
0x140021565  jnz     short loc_14002158D
0x140021567  cmp     [r14+2Ch], ebp
0x14002156b  jnz     short loc_14002158D
0x14002156d  lea     rdx, [r14+30h]; Source2
0x140021571  mov     r8d, 10h; Length
0x140021577  mov     rcx, rbx; Source1
0x14002157a  call    cs:__imp_RtlCompareMemory
0x140021580  cmp     rax, 10h
0x140021584  jz      short loc_1400215EE
0x140021586  lea     rax, qword_1400821F8
0x14002158d  mov     r14, [r14]
0x140021590  cmp     r14, rax
0x140021593  jnz     short loc_140021560
0x140021595  lea     rcx, ?TLCritSect@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x14002159c  call    cs:__imp_RtlLeaveCriticalSection
0x1400215a2  mov     r8, rbx; unsigned __int16 *
0x1400215a5  mov     edx, ebp; unsigned int
0x1400215a7  movzx   ecx, r15w; unsigned __int16
0x1400215ab  call    ?AddClientRecord@@YAPEAU_CLIENT_RECORD@@GKPEAG@Z; AddClientRecord(ushort,ulong,ushort *)
0x1400215b0  mov     r14, rax
0x1400215b3  test    rax, rax
0x1400215b6  jz      short loc_1400215CB
0x1400215b8  add     [r14+14h], r13d
0x1400215bc  mov     rcx, [rdi+68h]
0x1400215c0  add     [r14+20h], rcx
0x1400215c4  mov     ecx, [rdi+2Ch]
0x1400215c7  add     [r14+18h], ecx
0x1400215cb  mov     ebp, [rdi+28h]
0x1400215ce  lea     r15, ?TLCritSect@@3U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION TLCritSect
0x1400215d5  mov     rcx, r15; CriticalSection
0x1400215d8  call    cs:__imp_RtlEnterCriticalSection
0x1400215de  mov     rbx, cs:qword_140082208
0x1400215e5  lea     rax, qword_140082208
0x1400215ec  jmp     short loc_14002160A
0x1400215ee  lea     rcx, ?TLCritSect@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x1400215f5  call    cs:__imp_RtlLeaveCriticalSection
0x1400215fb  test    r14, r14
0x1400215fe  jz      short loc_1400215A2
0x140021600  jmp     short loc_1400215B8
0x140021602  cmp     [rbx+10h], ebp
0x140021605  jz      short loc_140021648
0x140021607  mov     rbx, [rbx]
0x14002160a  cmp     rbx, rax
0x14002160d  jnz     short loc_140021602
0x14002160f  mov     rcx, r15; CriticalSection
0x140021612  call    cs:__imp_RtlLeaveCriticalSection
0x140021618  call    cs:__imp_GetProcessHeap
0x14002161e  mov     edx, 8; dwFlags
0x140021623  mov     rcx, rax; hHeap
0x140021626  lea     r8d, [rdx+48h]; dwBytes
0x14002162a  call    cs:__imp_HeapAlloc
0x140021630  mov     rbx, rax
0x140021633  test    rax, rax
0x140021636  jnz     short loc_14002165D
0x140021638  lea     ebp, [rax+0Eh]
0x14002163b  mov     ecx, ebp; dwErrCode
0x14002163d  call    cs:__imp_SetLastError
0x140021643  mov     rbx, r12
0x140021646  jmp     short loc_1400216B2
0x140021648  mov     rcx, r15; CriticalSection
0x14002164b  call    cs:__imp_RtlLeaveCriticalSection
0x140021651  test    rbx, rbx
0x140021654  jz      short loc_140021618
0x140021656  mov     ebp, 0Eh
0x14002165b  jmp     short loc_1400216B7
0x14002165d  xor     edx, edx; Val
0x14002165f  mov     rcx, rbx; void *
0x140021662  lea     r8d, [rdx+50h]; Size
0x140021666  call    memset_0
0x14002166b  mov     rcx, r15; CriticalSection
0x14002166e  mov     [rbx+10h], ebp
0x140021671  call    cs:__imp_RtlEnterCriticalSection
0x140021677  mov     rax, cs:qword_140082208
0x14002167e  lea     rcx, qword_140082208
0x140021685  cmp     [rax+8], rcx
0x140021689  jz      short loc_140021692
0x14002168b  mov     ecx, 3
0x140021690  int     29h; Win8: RtlFailFast(ecx)
0x140021692  mov     [rbx+8], rcx
0x140021696  mov     rcx, r15; CriticalSection
0x140021699  mov     [rbx], rax
0x14002169c  mov     [rax+8], rbx
0x1400216a0  mov     cs:qword_140082208, rbx
0x1400216a7  call    cs:__imp_RtlLeaveCriticalSection
0x1400216ad  mov     ebp, 0Eh
0x1400216b2  test    rbx, rbx
0x1400216b5  jz      short loc_1400216E1
0x1400216b7  add     [rbx+28h], r13d
0x1400216bb  mov     rax, [rdi+68h]
0x1400216bf  add     [rbx+30h], rax
0x1400216c3  mov     eax, [rdi+30h]
0x1400216c6  add     [rbx+14h], eax
0x1400216c9  mov     eax, [rdi+34h]
0x1400216cc  add     [rbx+18h], eax
0x1400216cf  mov     eax, [rdi+50h]
0x1400216d2  add     [rbx+1Ch], eax
0x1400216d5  mov     eax, [rdi+54h]
0x1400216d8  add     [rbx+20h], eax
0x1400216db  mov     eax, [rdi+2Ch]
0x1400216de  add     [rbx+2Ch], eax
0x1400216e1  cmp     [rdi+18h], r12d
0x1400216e5  jnz     loc_1400217CF
0x1400216eb  movzx   eax, word ptr [rdi+8Ah]
0x1400216f2  cmp     ax, bp
0x1400216f5  jz      loc_1400217EE
0x1400216fb  mov     ecx, 14h
0x140021700  cmp     ax, cx
0x140021703  jz      loc_1400217EE
0x140021709  mov     rcx, [rdi+90h]
0x140021710  test    rcx, rcx
0x140021713  jz      loc_140021D10
0x140021719  mov     rdx, [rdi+98h]
0x140021720  test    rdx, rdx
0x140021723  jz      short loc_140021737
0x140021725  cmp     rdx, rcx
0x140021728  jb      loc_140021D10
0x14002172e  cmp     rdx, [rdi+80h]
0x140021735  jbe     short loc_140021757
0x140021737  mov     rdx, [rdi+80h]
0x14002173e  mov     [rdi+98h], rdx
0x140021745  test    rdx, rdx
0x140021748  jz      loc_140021D10
0x14002174e  cmp     rdx, rcx
0x140021751  jb      loc_140021D10
0x140021757  mov     rax, [rdi+0A0h]
0x14002175e  mov     r8, rdx
0x140021761  mov     rsi, [rdi+0D0h]
0x140021768  sub     r8, rcx
0x14002176b  mov     r10, [rdi+0E0h]
0x140021772  mov     r9, [rdi+0F8h]
0x140021779  cmp     r8, rax
0x14002177c  jnb     short loc_140021788
0x14002177e  mov     [rdi+0A0h], r8
0x140021785  mov     rax, r8
0x140021788  movzx   r11d, word ptr [rdi+0BCh]
0x140021790  cmp     r11w, 0Bh
0x140021795  jnz     loc_14002185C
0x14002179b  mov     r11, [rdi+0C8h]
0x1400217a2  test    r11, r11
0x1400217a5  jz      loc_140021D10
0x1400217ab  test    rsi, rsi
0x1400217ae  jz      short loc_1400217B5
0x1400217b0  cmp     rsi, rdx
0x1400217b3  jbe     short loc_1400217C1
0x1400217b5  cmp     r11, rdx
0x1400217b8  ja      loc_140021D10
0x1400217be  mov     rsi, rdx
0x1400217c1  cmp     r11, rcx
0x1400217c4  jnb     short loc_140021831
0x1400217c6  mov     [rdi+0C8h], rcx
0x1400217cd  jmp     short loc_140021834
0x1400217cf  cmp     [rdi+18h], r13d
0x1400217d3  jnz     loc_140021709
0x1400217d9  movzx   eax, word ptr [rdi+8Ah]
0x1400217e0  sub     ax, 19h
0x1400217e4  cmp     ax, r13w
0x1400217e8  ja      loc_140021709
0x1400217ee  mov     rcx, cs:qword_1400846F8
0x1400217f5  add     [rcx+4], r13d
0x1400217f9  mov     rax, [rdi+68h]
0x1400217fd  add     [rcx+8], rax
0x140021801  mov     eax, [rdi+34h]
0x140021804  add     eax, [rdi+30h]
0x140021807  add     [rcx+13Ch], eax
0x14002180d  test    rsi, rsi
0x140021810  jz      short loc_140021816
0x140021812  add     [rsi+24h], r13d
0x140021816  test    r14, r14
0x140021819  jz      short loc_14002181F
0x14002181b  add     [r14+10h], r13d
0x14002181f  test    rbx, rbx
0x140021822  jz      loc_140021CFF
0x140021828  add     [rbx+24h], r13d
0x14002182c  jmp     loc_140021CFF
0x140021831  mov     rcx, r11
0x140021834  cmp     rsi, rcx
0x140021837  cmovb   rsi, rcx
0x14002183b  sub     rax, rcx
  ... truncated ...
```
