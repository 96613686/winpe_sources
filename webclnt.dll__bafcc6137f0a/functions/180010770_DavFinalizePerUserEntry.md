# DavFinalizePerUserEntry

- ea: `0x180010770`
- end: `0x180010b00`
- name: `DavFinalizePerUserEntry`
- size: `912`
- prototype: `__int64 __fastcall(unsigned int **, __int64, __int64)`
- caller_count: `11`
- callee_count: `6`
- tags: ``

## callers

- `0x1800169d4`
- `0x18001a5a0`
- `0x18001ca70`
- `0x18001db70`
- `0x18001dfc0`
- `0x18001ead0`
- `0x18001f190`
- `0x180021c54`
- `0x180023360`
- `0x180023960`
- `0x180024190`

## callees

- `0x18000b7dc`
- `0x18000b89c`
- `0x18000bc5c`
- `0x180010770`
- `0x180014d34`
- `0x180014f50`

## import_xrefs

- `msvcrt!time` at `0x180010868`
- `msvcrt!time` at `0x180010868`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800108db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001091a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010959`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010a74`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800108db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001091a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010959`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010a74`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800108d1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800108d1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800109e3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180010ae1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800109e3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180010ae1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800107f6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800109a2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800107f6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800109a2`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800109ed`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800109ed`
- `KERNEL32!LocalFree` at `0x18001098e`
- `KERNEL32!LocalFree` at `0x1800109d5`
- `KERNEL32!LocalFree` at `0x1800109fc`
- `KERNEL32!LocalFree` at `0x180010a26`
- `KERNEL32!LocalFree` at `0x180010a59`
- `KERNEL32!LocalFree` at `0x180010a69`
- `KERNEL32!LocalFree` at `0x18001098e`
- `KERNEL32!LocalFree` at `0x1800109d5`
- `KERNEL32!LocalFree` at `0x1800109fc`
- `KERNEL32!LocalFree` at `0x180010a26`
- `KERNEL32!LocalFree` at `0x180010a59`
- `KERNEL32!LocalFree` at `0x180010a69`
- `WINHTTP!WinHttpCloseHandle` at `0x180010910`
- `WINHTTP!WinHttpCloseHandle` at `0x18001094f`
- `WINHTTP!WinHttpCloseHandle` at `0x180010910`
- `WINHTTP!WinHttpCloseHandle` at `0x18001094f`

## pseudocode

```c
__int64 __fastcall DavFinalizePerUserEntry(unsigned int **a1, __int64 a2, __int64 a3)
{
  unsigned int *v3; // rbx
  _QWORD *v5; // rcx
  bool v6; // zf
  __int64 v7; // rcx
  unsigned int **v8; // rdx
  __int64 v9; // rdi
  _QWORD *v10; // rax
  __int64 v11; // rdx
  _QWORD *v12; // rcx
  __int64 v13; // rcx
  void *v14; // rcx
  unsigned int v15; // esi
  DWORD LastError; // eax
  void *v17; // rcx
  DWORD v18; // eax
  void *v19; // rcx
  DWORD v20; // eax
  _BYTE *v21; // rax
  __int64 v22; // rdx
  __int64 i; // rdx
  void *v24; // rcx
  _BYTE *v25; // rax
  __int64 v26; // rcx
  _BYTE *v27; // rax
  __int64 v28; // rcx
  DWORD v29; // eax

  v3 = *a1;
  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 143, WPP_448ddb41b5843cea4b9dc965d1aba9af_Traceguids, v3);
      v5 = WPP_GLOBAL_Control;
    }
    if ( v5 != &WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 2) != 0 )
      WPP_SF_ddd(v5[2], a2, a3, v3[16], *v3, v3[1]);
  }
  EnterCriticalSection(&HashServerEntryTableLock);
  v6 = v3[16]-- == 1;
  if ( v6 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 145, WPP_448ddb41b5843cea4b9dc965d1aba9af_Traceguids, *v3, v3[1]);
    v7 = *((_QWORD *)v3 + 2);
    if ( *(unsigned int **)(v7 + 8) == v3 + 4 )
    {
      v8 = (unsigned int **)*((_QWORD *)v3 + 3);
      if ( *v8 == v3 + 4 )
      {
        v9 = *((_QWORD *)v3 + 1);
        *v8 = (unsigned int *)v7;
        *(_QWORD *)(v7 + 8) = v8;
        v6 = (*(_DWORD *)(v9 + 104))-- == 1;
        if ( !v6 )
          goto LABEL_18;
        *(_QWORD *)(v9 + 112) = time(0);
        v10 = (_QWORD *)(v9 + 88);
        v11 = *(_QWORD *)(v9 + 88);
        if ( *(_QWORD *)(v11 + 8) == v9 + 88 )
        {
          v12 = *(_QWORD **)(v9 + 96);
          if ( (_QWORD *)*v12 == v10 )
          {
            *v12 = v11;
            *(_QWORD *)(v11 + 8) = v12;
            v13 = ToBeFinalizedServerEntries;
            if ( *(__int64 **)(ToBeFinalizedServerEntries + 8) == &ToBeFinalizedServerEntries )
            {
              *v10 = ToBeFinalizedServerEntries;
              *(_QWORD *)(v9 + 96) = &ToBeFinalizedServerEntries;
              *(_QWORD *)(v13 + 8) = v10;
              ToBeFinalizedServerEntries = v9 + 88;
LABEL_18:
              v14 = (void *)*((_QWORD *)v3 + 7);
              v15 = 1;
              if ( v14 )
              {
                if ( !CloseHandle(v14) )
                {
                  LastError = GetLastError();
                  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                  {
                    WPP_SF_d(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      146,
                      WPP_448ddb41b5843cea4b9dc965d1aba9af_Traceguids,
                      LastError);
                  }
                }
              }
              v17 = (void *)*((_QWORD *)v3 + 5);
              if ( v17 )
              {
                if ( !WinHttpCloseHandle(v17) )
                {
                  v18 = GetLastError();
                  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                  {
                    WPP_SF_d(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      147,
                      WPP_448ddb41b5843cea4b9dc965d1aba9af_Traceguids,
                      v18);
                  }
                }
              }
              v19 = (void *)*((_QWORD *)v3 + 4);
              if ( v19 )
              {
                if ( !WinHttpCloseHandle(v19) )
                {
                  v20 = GetLastError();
                  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                  {
                    WPP_SF_d(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      148,
                      WPP_448ddb41b5843cea4b9dc965d1aba9af_Traceguids,
                      v20);
                  }
                }
              }
              if ( v3[24] )
              {
                LocalFree(*((HLOCAL *)v3 + 11));
                *((_QWORD *)v3 + 11) = 0;
              }
              if ( *((_QWORD *)v3 + 14) )
              {
                EnterCriticalSection((LPCRITICAL_SECTION)v3 + 3);
                v21 = (_BYTE *)*((_QWORD *)v3 + 14);
                v22 = -1;
                do
                  ++v22;
                while ( *(_WORD *)&v21[2 * v22] );
                for ( i = 2 * v22 + 2; i; --i )
                  *v21++ = 0;
                LocalFree(*((HLOCAL *)v3 + 14));
                *((_QWORD *)v3 + 14) = 0;
                LeaveCriticalSection((LPCRITICAL_SECTION)v3 + 3);
              }
              DeleteCriticalSection((LPCRITICAL_SECTION)v3 + 3);
              v24 = (void *)*((_QWORD *)v3 + 9);
              if ( v24 )
              {
                LocalFree(v24);
                *((_QWORD *)v3 + 9) = 0;
              }
              v25 = (_BYTE *)*((_QWORD *)v3 + 10);
              if ( v25 )
              {
                v26 = v3[27];
                if ( v3[27] )
                {
                  do
                  {
                    *v25++ = 0;
                    --v26;
                  }
                  while ( v26 );
                }
                LocalFree(*((HLOCAL *)v3 + 10));
                *((_QWORD *)v3 + 10) = 0;
              }
              v27 = (_BYTE *)*((_QWORD *)v3 + 20);
              if ( v27 )
              {
                v28 = v3[42];
                if ( v3[42] )
                {
                  do
                  {
                    *v27++ = 0;
                    --v28;
                  }
                  while ( v28 );
                }
                LocalFree(*((HLOCAL *)v3 + 20));
                *((_QWORD *)v3 + 20) = 0;
              }
              if ( LocalFree(v3) )
              {
                v29 = GetLastError();
                if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                {
                  WPP_SF_d(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    149,
                    WPP_448ddb41b5843cea4b9dc965d1aba9af_Traceguids,
                    v29);
                }
              }
              *a1 = 0;
              goto LABEL_61;
            }
          }
        }
      }
    }
    __fastfail(3u);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), 150, WPP_448ddb41b5843cea4b9dc965d1aba9af_Traceguids, v3, v3[16]);
  v15 = 0;
LABEL_61:
  LeaveCriticalSection(&HashServerEntryTableLock);
  return v15;
}

```

## disassembly

```asm
0x180010770  mov     [rsp+arg_8], rbx
0x180010775  mov     [rsp+arg_10], rbp
0x18001077a  push    rsi
0x18001077b  push    rdi
0x18001077c  push    r12
0x18001077e  push    r14
0x180010780  push    r15
0x180010782  sub     rsp, 30h
0x180010786  mov     rbx, [rcx]
0x180010789  mov     r14, rcx
0x18001078c  mov     rcx, cs:WPP_GLOBAL_Control
0x180010793  lea     r15, WPP_GLOBAL_Control
0x18001079a  lea     r12, WPP_448ddb41b5843cea4b9dc965d1aba9af_Traceguids
0x1800107a1  mov     dil, 2
0x1800107a4  cmp     rcx, r15
0x1800107a7  jz      short loc_1800107EF
0x1800107a9  test    [rcx+1Ch], dil
0x1800107ad  jz      short loc_1800107CA
0x1800107af  mov     rcx, [rcx+10h]
0x1800107b3  mov     edx, 8Fh
0x1800107b8  mov     r9, rbx
0x1800107bb  mov     r8, r12
0x1800107be  call    WPP_SF_q
0x1800107c3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800107ca  cmp     rcx, r15
0x1800107cd  jz      short loc_1800107EF
0x1800107cf  test    [rcx+1Ch], dil
0x1800107d3  jz      short loc_1800107EF
0x1800107d5  mov     eax, [rbx+4]
0x1800107d8  mov     r9d, [rbx+40h]
0x1800107dc  mov     rcx, [rcx+10h]
0x1800107e0  mov     [rsp+58h+var_30], eax
0x1800107e4  mov     eax, [rbx]
0x1800107e6  mov     [rsp+58h+var_38], eax
0x1800107ea  call    WPP_SF_ddd
0x1800107ef  lea     rcx, HashServerEntryTableLock; lpCriticalSection
0x1800107f6  call    cs:__imp_EnterCriticalSection
0x1800107fc  or      esi, 0FFFFFFFFh
0x1800107ff  add     [rbx+40h], esi
0x180010802  mov     eax, [rbx+40h]
0x180010805  jnz     loc_180010AAC
0x18001080b  mov     rcx, cs:WPP_GLOBAL_Control
0x180010812  cmp     rcx, r15
0x180010815  jz      short loc_180010838
0x180010817  test    [rcx+1Ch], dil
0x18001081b  jz      short loc_180010838
0x18001081d  mov     eax, [rbx+4]
0x180010820  mov     edx, 91h
0x180010825  mov     r9d, [rbx]
0x180010828  mov     r8, r12
0x18001082b  mov     rcx, [rcx+10h]
0x18001082f  mov     [rsp+58h+var_38], eax
0x180010833  call    WPP_SF_Dd
0x180010838  lea     rax, [rbx+10h]
0x18001083c  mov     rcx, [rax]
0x18001083f  cmp     [rcx+8], rax
0x180010843  jnz     loc_180010AA5
0x180010849  mov     rdx, [rax+8]
0x18001084d  cmp     [rdx], rax
0x180010850  jnz     loc_180010AA5
0x180010856  mov     rdi, [rbx+8]
0x18001085a  mov     [rdx], rcx
0x18001085d  mov     [rcx+8], rdx
0x180010861  add     [rdi+68h], esi
0x180010864  jnz     short loc_1800108C1
0x180010866  xor     ecx, ecx; Time
0x180010868  call    cs:__imp_time
0x18001086e  mov     [rdi+70h], rax
0x180010872  lea     rax, [rdi+58h]
0x180010876  mov     rdx, [rax]
0x180010879  cmp     [rdx+8], rax
0x18001087d  jnz     loc_180010AA5
0x180010883  mov     rcx, [rax+8]
0x180010887  cmp     [rcx], rax
0x18001088a  jnz     loc_180010AA5
0x180010890  mov     [rcx], rdx
0x180010893  mov     [rdx+8], rcx
0x180010897  lea     rdx, ToBeFinalizedServerEntries
0x18001089e  mov     rcx, cs:ToBeFinalizedServerEntries
0x1800108a5  cmp     [rcx+8], rdx
0x1800108a9  jnz     loc_180010AA5
0x1800108af  mov     [rax], rcx
0x1800108b2  mov     [rax+8], rdx
0x1800108b6  mov     [rcx+8], rax
0x1800108ba  mov     cs:ToBeFinalizedServerEntries, rax
0x1800108c1  mov     rcx, [rbx+38h]; hObject
0x1800108c5  xor     edi, edi
0x1800108c7  mov     esi, 1
0x1800108cc  test    rcx, rcx
0x1800108cf  jz      short loc_180010907
0x1800108d1  call    cs:__imp_CloseHandle
0x1800108d7  test    eax, eax
0x1800108d9  jnz     short loc_180010907
0x1800108db  call    cs:__imp_GetLastError
0x1800108e1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800108e8  cmp     rcx, r15
0x1800108eb  jz      short loc_180010907
0x1800108ed  test    [rcx+1Ch], sil
0x1800108f1  jz      short loc_180010907
0x1800108f3  mov     rcx, [rcx+10h]
0x1800108f7  mov     edx, 92h
0x1800108fc  mov     r9d, eax
0x1800108ff  mov     r8, r12
0x180010902  call    WPP_SF_d
0x180010907  mov     rcx, [rbx+28h]; hInternet
0x18001090b  test    rcx, rcx
0x18001090e  jz      short loc_180010946
0x180010910  call    cs:__imp_WinHttpCloseHandle
0x180010916  test    eax, eax
0x180010918  jnz     short loc_180010946
0x18001091a  call    cs:__imp_GetLastError
0x180010920  mov     rcx, cs:WPP_GLOBAL_Control
0x180010927  cmp     rcx, r15
0x18001092a  jz      short loc_180010946
0x18001092c  test    [rcx+1Ch], sil
0x180010930  jz      short loc_180010946
0x180010932  mov     rcx, [rcx+10h]
0x180010936  mov     edx, 93h
0x18001093b  mov     r9d, eax
0x18001093e  mov     r8, r12
0x180010941  call    WPP_SF_d
0x180010946  mov     rcx, [rbx+20h]; hInternet
0x18001094a  test    rcx, rcx
0x18001094d  jz      short loc_180010985
0x18001094f  call    cs:__imp_WinHttpCloseHandle
0x180010955  test    eax, eax
0x180010957  jnz     short loc_180010985
0x180010959  call    cs:__imp_GetLastError
0x18001095f  mov     rcx, cs:WPP_GLOBAL_Control
0x180010966  cmp     rcx, r15
0x180010969  jz      short loc_180010985
0x18001096b  test    [rcx+1Ch], sil
0x18001096f  jz      short loc_180010985
0x180010971  mov     rcx, [rcx+10h]
0x180010975  mov     edx, 94h
0x18001097a  mov     r9d, eax
0x18001097d  mov     r8, r12
0x180010980  call    WPP_SF_d
0x180010985  cmp     [rbx+60h], edi
0x180010988  jz      short loc_180010998
0x18001098a  mov     rcx, [rbx+58h]; hMem
0x18001098e  call    cs:__imp_LocalFree
0x180010994  mov     [rbx+58h], rdi
0x180010998  cmp     [rbx+70h], rdi
0x18001099c  jz      short loc_1800109E9
0x18001099e  lea     rcx, [rbx+78h]; lpCriticalSection
0x1800109a2  call    cs:__imp_EnterCriticalSection
0x1800109a8  mov     rax, [rbx+70h]
0x1800109ac  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800109b0  inc     rdx
0x1800109b3  cmp     [rax+rdx*2], di
0x1800109b7  jnz     short loc_1800109B0
0x1800109b9  lea     rdx, ds:2[rdx*2]
0x1800109c1  test    rdx, rdx
0x1800109c4  jz      short loc_1800109D1
0x1800109c6  mov     [rax], dil
0x1800109c9  add     rax, rsi
0x1800109cc  sub     rdx, rsi
0x1800109cf  jnz     short loc_1800109C6
0x1800109d1  mov     rcx, [rbx+70h]; hMem
0x1800109d5  call    cs:__imp_LocalFree
0x1800109db  lea     rcx, [rbx+78h]; lpCriticalSection
0x1800109df  mov     [rbx+70h], rdi
0x1800109e3  call    cs:__imp_LeaveCriticalSection
0x1800109e9  lea     rcx, [rbx+78h]; lpCriticalSection
0x1800109ed  call    cs:__imp_DeleteCriticalSection
0x1800109f3  mov     rcx, [rbx+48h]; hMem
0x1800109f7  test    rcx, rcx
0x1800109fa  jz      short loc_180010A06
0x1800109fc  call    cs:__imp_LocalFree
0x180010a02  mov     [rbx+48h], rdi
0x180010a06  mov     rax, [rbx+50h]
0x180010a0a  test    rax, rax
0x180010a0d  jz      short loc_180010A30
0x180010a0f  mov     ecx, [rbx+6Ch]
0x180010a12  test    rcx, rcx
0x180010a15  jz      short loc_180010A22
0x180010a17  mov     [rax], dil
0x180010a1a  add     rax, rsi
0x180010a1d  sub     rcx, rsi
0x180010a20  jnz     short loc_180010A17
0x180010a22  mov     rcx, [rbx+50h]; hMem
0x180010a26  call    cs:__imp_LocalFree
0x180010a2c  mov     [rbx+50h], rdi
0x180010a30  mov     rax, [rbx+0A0h]
0x180010a37  test    rax, rax
0x180010a3a  jz      short loc_180010A66
0x180010a3c  mov     ecx, [rbx+0A8h]
0x180010a42  test    rcx, rcx
0x180010a45  jz      short loc_180010A52
0x180010a47  mov     [rax], dil
0x180010a4a  add     rax, rsi
0x180010a4d  sub     rcx, rsi
0x180010a50  jnz     short loc_180010A47
0x180010a52  mov     rcx, [rbx+0A0h]; hMem
0x180010a59  call    cs:__imp_LocalFree
0x180010a5f  mov     [rbx+0A0h], rdi
0x180010a66  mov     rcx, rbx; hMem
0x180010a69  call    cs:__imp_LocalFree
0x180010a6f  test    rax, rax
0x180010a72  jz      short loc_180010AA0
0x180010a74  call    cs:__imp_GetLastError
0x180010a7a  mov     rcx, cs:WPP_GLOBAL_Control
0x180010a81  cmp     rcx, r15
0x180010a84  jz      short loc_180010AA0
0x180010a86  test    [rcx+1Ch], sil
0x180010a8a  jz      short loc_180010AA0
0x180010a8c  mov     rcx, [rcx+10h]
0x180010a90  mov     edx, 95h
0x180010a95  mov     r9d, eax
0x180010a98  mov     r8, r12
0x180010a9b  call    WPP_SF_d
0x180010aa0  mov     [r14], rdi
0x180010aa3  jmp     short loc_180010ADA
0x180010aa5  mov     ecx, 3
0x180010aaa  int     29h; Win8: RtlFailFast(ecx)
0x180010aac  mov     rcx, cs:WPP_GLOBAL_Control
0x180010ab3  cmp     rcx, r15
0x180010ab6  jz      short loc_180010AD6
0x180010ab8  test    [rcx+1Ch], dil
0x180010abc  jz      short loc_180010AD6
0x180010abe  mov     rcx, [rcx+10h]
0x180010ac2  mov     edx, 96h
0x180010ac7  mov     r9, rbx
0x180010aca  mov     [rsp+58h+var_38], eax
0x180010ace  mov     r8, r12
0x180010ad1  call    WPP_SF_qd
0x180010ad6  xor     edi, edi
0x180010ad8  mov     esi, edi
0x180010ada  lea     rcx, HashServerEntryTableLock; lpCriticalSection
0x180010ae1  call    cs:__imp_LeaveCriticalSection
0x180010ae7  mov     rbx, [rsp+58h+arg_8]
0x180010aec  mov     eax, esi
0x180010aee  mov     rbp, [rsp+58h+arg_10]
0x180010af3  add     rsp, 30h
0x180010af7  pop     r15
0x180010af9  pop     r14
0x180010afb  pop     r12
0x180010afd  pop     rdi
0x180010afe  pop     rsi
0x180010aff  retn
```
