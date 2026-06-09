# PrintStatistics(sqlperf *,void *,ushort const *)

- ea: `0x3839630d0`
- end: `0x383963569`
- name: `?PrintStatistics@@YAFPEAUsqlperf@@PEAXPEBG@Z`
- size: `1177`
- prototype: `__int16 __fastcall(struct sqlperf *, void *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x38386d8d0`
- `0x3838bac20`

## callees

- `0x3838434c0`
- `0x383893160`
- `0x38391aed0`
- `0x383962c20`
- `0x3839630d0`

## import_xrefs

- `MSVCR100!_wctime64` at `0x38396311c`
- `MSVCR100!_wctime64` at `0x38396311c`
- `MSVCR100!_time64` at `0x383963111`
- `MSVCR100!_time64` at `0x383963111`
- `KERNEL32!WriteFile` at `0x38396321f`
- `KERNEL32!WriteFile` at `0x383963303`
- `KERNEL32!WriteFile` at `0x3839633d1`
- `KERNEL32!WriteFile` at `0x3839634a4`
- `KERNEL32!WriteFile` at `0x38396321f`
- `KERNEL32!WriteFile` at `0x383963303`
- `KERNEL32!WriteFile` at `0x3839633d1`
- `KERNEL32!WriteFile` at `0x3839634a4`

## pseudocode

```c
__int64 __fastcall PrintStatistics(const OLECHAR *a1, void *a2, const unsigned __int16 *a3)
{
  HANDLE v4; // rdi
  __int16 v5; // bx
  wchar_t *v6; // rax
  __int64 v7; // rax
  char *v8; // rcx
  __int64 v9; // r9
  __int64 v10; // rdx
  __int64 v11; // rax
  __int64 v12; // rax
  const OLECHAR *v13; // rax
  __int64 v14; // rax
  __int64 v15; // rdx
  LPOVERLAPPED lpOverlapped; // [rsp+28h] [rbp-E0h]
  LPOVERLAPPED lpOverlappeda; // [rsp+28h] [rbp-E0h]
  LPOVERLAPPED lpOverlappedb; // [rsp+28h] [rbp-E0h]
  __int64 v20; // [rsp+30h] [rbp-D8h]
  __int64 v21; // [rsp+30h] [rbp-D8h]
  __int64 v22; // [rsp+30h] [rbp-D8h]
  __int64 v23; // [rsp+38h] [rbp-D0h]
  __int64 v24; // [rsp+38h] [rbp-D0h]
  __int64 v25; // [rsp+40h] [rbp-C8h]
  __int64 v26; // [rsp+40h] [rbp-C8h]
  __int64 v27; // [rsp+48h] [rbp-C0h]
  __int64 v28; // [rsp+48h] [rbp-C0h]
  __int64 v29; // [rsp+50h] [rbp-B8h]
  __int64 v30; // [rsp+50h] [rbp-B8h]
  __int64 v31; // [rsp+58h] [rbp-B0h]
  __int64 v32; // [rsp+60h] [rbp-A8h]
  DWORD NumberOfBytesWritten; // [rsp+78h] [rbp-90h] BYREF
  __time64_t Time; // [rsp+80h] [rbp-88h] BYREF
  _QWORD v35[4]; // [rsp+88h] [rbp-80h] BYREF
  __int64 v36; // [rsp+A8h] [rbp-60h]
  unsigned __int16 Buffer[256]; // [rsp+B8h] [rbp-50h] BYREF

  v4 = g_hPerfDataFile;
  v5 = 0;
  NumberOfBytesWritten = 0;
  _time64(&Time);
  v6 = _wctime64(&Time);
  v35[0] = *(_QWORD *)v6;
  v35[1] = *((_QWORD *)v6 + 1);
  v35[2] = *((_QWORD *)v6 + 2);
  v35[3] = *((_QWORD *)v6 + 3);
  v36 = *((_QWORD *)v6 + 4);
  HIWORD(v36) = 0;
  ReCalcStatistics();
  (*(void (__fastcall **)(__int64))(*(_QWORD *)(g_csSQLPerf + 32LL) + 8LL))(g_csSQLPerf + 32LL);
  if ( g_fPerfStatLogEnabled )
  {
    StringCchPrintfW(
      Buffer,
      0xFFu,
      L"%s\t%ld\t%ld\t%ld\t%ld\t%ld\t%ld\t%ld\t%ld\t%ld\t",
      v35,
      g_SQLPerfData.TimerResolution,
      dword_383B25644,
      dword_383B25648,
      dword_383B2564C,
      dword_383B25650,
      dword_383B25654,
      dword_383B25658,
      dword_383B2565C,
      dword_383B25660);
    v7 = -1;
    do
      ++v7;
    while ( Buffer[v7] );
    if ( WriteFile(v4, Buffer, 2 * v7, &NumberOfBytesWritten, 0) )
    {
      LODWORD(v32) = dword_383B25694;
      LODWORD(v31) = dword_383B25690;
      LODWORD(v20) = dword_383B2566C;
      LODWORD(lpOverlapped) = dword_383B25668;
      StringCchPrintfW(
        Buffer,
        0xFFu,
        L"%ld\t%ld\t%ld\t%f\t%f\t%f\t%f\t%ld\t%ld\t",
        (unsigned int)dword_383B25664,
        lpOverlapped,
        v20,
        qword_383B25670,
        xmmword_383B25678,
        unk_383B25688,
        v31,
        v32);
      v11 = -1;
      do
        ++v11;
      while ( Buffer[v11] );
      if ( WriteFile(v4, Buffer, 2 * v11, &NumberOfBytesWritten, 0) )
      {
        LODWORD(v29) = dword_383B256B0;
        LODWORD(v27) = dword_383B256AC;
        LODWORD(v25) = dword_383B256A8;
        LODWORD(v23) = dword_383B256A4;
        LODWORD(v21) = dword_383B256A0;
        LODWORD(lpOverlappeda) = dword_383B2569C;
        StringCchPrintfW(
          Buffer,
          0xFFu,
          L"%ld\t%ld\t%ld\t%ld\t%ld\t%ld\t%ld\t%f\t",
          (unsigned int)dword_383B25698,
          lpOverlappeda,
          v21,
          v23,
          v25,
          v27,
          v29,
          qword_383B256B8);
        v12 = -1;
        do
          ++v12;
        while ( Buffer[v12] );
        if ( WriteFile(v4, Buffer, 2 * v12, &NumberOfBytesWritten, 0) )
        {
          v13 = &WideCharStr;
          if ( a1 )
            v13 = a1;
          LODWORD(v30) = dword_383B256D8;
          LODWORD(v28) = dword_383B256D4;
          LODWORD(v26) = dword_383B256D0;
          LODWORD(v24) = dword_383B256CC;
          LODWORD(v22) = dword_383B256C8;
          LODWORD(lpOverlappedb) = dword_383B256C4;
          StringCchPrintfW(
            Buffer,
            0xFFu,
            L"%ld\t%ld\t%ld\t%ld\t%ld\t%ld\t%ld\t%s\r\n",
            (unsigned int)dword_383B256C0,
            lpOverlappedb,
            v22,
            v24,
            v26,
            v28,
            v30,
            v13);
          v14 = -1;
          do
            ++v14;
          while ( Buffer[v14] );
          if ( !WriteFile(v4, Buffer, 2 * v14, &NumberOfBytesWritten, 0) )
          {
            v5 = -1;
            if ( (bidGblFlags & 2) != 0 )
            {
              v8 = off_383B43218[0];
              if ( off_383B49120[0] )
              {
                v9 = 582;
                v10 = 595977;
                goto LABEL_28;
              }
            }
          }
        }
        else
        {
          v5 = -1;
          if ( (bidGblFlags & 2) != 0 )
          {
            v8 = off_383B43218[0];
            if ( off_383B49120[0] )
            {
              v9 = 567;
              v10 = 580617;
              goto LABEL_28;
            }
          }
        }
      }
      else
      {
        v5 = -1;
        if ( (bidGblFlags & 2) != 0 )
        {
          v8 = off_383B43218[0];
          if ( off_383B49120[0] )
          {
            v9 = 552;
            v10 = 565257;
            goto LABEL_28;
          }
        }
      }
    }
    else
    {
      v5 = -1;
      if ( (bidGblFlags & 2) != 0 )
      {
        v8 = off_383B43218[0];
        if ( off_383B49120[0] )
        {
          v9 = 536;
          v10 = 548873;
LABEL_28:
          bidTraceW(v8, v10, off_383B49120[0], v9);
        }
      }
    }
  }
  (*(void (__fastcall **)(__int64))(*(_QWORD *)(g_csSQLPerf + 32LL) + 24LL))(g_csSQLPerf + 32LL);
  if ( (bidGblFlags & 2) != 0 && (v5 || (bidGblFlags & 0x40) != 0) )
  {
    v15 = 601089;
    if ( v5 )
      v15 = 601121;
    bidTraceW(off_383B43218[0], v15, off_383B494E8[0], (unsigned int)v5);
  }
  return (unsigned __int16)v5;
}

```

## disassembly

```asm
0x3839630d0  mov     r11, rsp
0x3839630d3  push    rbp
0x3839630d4  push    rbx
0x3839630d5  lea     rbp, [r11-1D8h]
0x3839630dc  sub     rsp, 2C8h
0x3839630e3  mov     rax, cs:__security_cookie
0x3839630ea  xor     rax, rsp
0x3839630ed  mov     [rbp+1D0h+var_20], rax
0x3839630f4  mov     [r11+10h], rsi
0x3839630f8  mov     rsi, rcx
0x3839630fb  mov     [r11+18h], rdi
0x3839630ff  mov     rdi, cs:?g_hPerfDataFile@@3PEAXEA; void * g_hPerfDataFile
0x383963106  lea     rcx, [rsp+2D0h+Time]; Time
0x38396310b  xor     ebx, ebx
0x38396310d  mov     [rsp+2D0h+NumberOfBytesWritten], ebx
0x383963111  call    cs:__imp__time64
0x383963117  lea     rcx, [rsp+2D0h+Time]; Time
0x38396311c  call    cs:__imp__wctime64
0x383963122  mov     r11, rax
0x383963125  mov     rax, [rax]
0x383963128  mov     [rbp+1D0h+var_250], rax
0x38396312c  mov     rax, [r11+8]
0x383963130  mov     [rbp+1D0h+var_248], rax
0x383963134  mov     rax, [r11+10h]
0x383963138  mov     [rbp+1D0h+var_240], rax
0x38396313c  mov     rax, [r11+18h]
0x383963140  mov     [rbp+1D0h+var_238], rax
0x383963144  mov     rax, [r11+20h]
0x383963148  mov     [rbp+1D0h+var_230], rax
0x38396314c  mov     word ptr [rbp+1D0h+var_230+6], bx
0x383963150  call    ?ReCalcStatistics@@YAXXZ; ReCalcStatistics(void)
0x383963155  mov     rcx, cs:?g_csSQLPerf@@3PEAVCCriticalSection@@EA; CCriticalSection * g_csSQLPerf
0x38396315c  mov     rax, [rcx+20h]
0x383963160  add     rcx, 20h ; ' '
0x383963164  call    qword ptr [rax+8]
0x383963167  cmp     cs:?g_fPerfStatLogEnabled@@3HA, ebx; int g_fPerfStatLogEnabled
0x38396316d  jz      loc_3839634ED
0x383963173  mov     eax, cs:dword_383B25660
0x383963179  lea     r9, [rbp+1D0h+var_250]
0x38396317d  lea     r8, aSLdLdLdLdLdLdL; "%s\t%ld\t%ld\t%ld\t%ld\t%ld\t%ld\t%ld\t"...
0x383963184  mov     [rsp+60h], eax
0x383963188  mov     eax, cs:dword_383B2565C
0x38396318e  lea     rcx, [rbp+1D0h+Buffer]; unsigned __int16 *
0x383963192  mov     [rsp+2D0h+var_278], eax
0x383963196  mov     eax, cs:dword_383B25658
0x38396319c  mov     edx, 0FFh; unsigned __int64
0x3839631a1  mov     dword ptr [rsp+2D0h+var_280], eax
0x3839631a5  mov     eax, cs:dword_383B25654
0x3839631ab  mov     [rsp+2C0h], r14
0x3839631b3  mov     dword ptr [rsp+2D0h+var_288], eax
0x3839631b7  mov     eax, cs:dword_383B25650
0x3839631bd  mov     dword ptr [rsp+2D0h+var_298+8], eax
0x3839631c1  mov     eax, cs:dword_383B2564C
0x3839631c7  mov     dword ptr [rsp+2D0h+var_298], eax
0x3839631cb  mov     eax, cs:dword_383B25648
0x3839631d1  mov     dword ptr [rsp+2D0h+var_2A0], eax
0x3839631d5  mov     eax, cs:dword_383B25644
0x3839631db  mov     dword ptr [rsp+2D0h+var_2A8], eax
0x3839631df  mov     eax, cs:?g_SQLPerfData@@3Usqlperf@@A; sqlperf g_SQLPerfData
0x3839631e5  mov     dword ptr [rsp+2D0h+lpOverlapped], eax
0x3839631e9  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x3839631ee  or      r14, 0FFFFFFFFFFFFFFFFh
0x3839631f2  mov     rax, r14
0x3839631f5  lea     r11, [rbp+1D0h+Buffer]
0x3839631f9  nop     dword ptr [rax+00000000h]
0x383963200  inc     rax
0x383963203  cmp     [r11+rax*2], bx
0x383963208  jnz     short loc_383963200
0x38396320a  lea     r8d, [rax+rax]; nNumberOfBytesToWrite
0x38396320e  lea     r9, [rsp+2D0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x383963213  lea     rdx, [rbp+1D0h+Buffer]; lpBuffer
0x383963217  mov     rcx, rdi; hFile
0x38396321a  mov     [rsp+2D0h+lpOverlapped], rbx; lpOverlapped
0x38396321f  call    cs:__imp_WriteFile
0x383963225  test    eax, eax
0x383963227  jnz     short loc_383963261
0x383963229  test    byte ptr cs:_bidGblFlags, 2
0x383963230  movzx   ebx, r14w
0x383963234  jz      loc_3839634E5
0x38396323a  mov     rcx, cs:off_383B43218; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x383963241  mov     rax, cs:off_383B49120; "<Trace|MARK> line %d\n"
0x383963248  test    rax, rax
0x38396324b  jz      loc_3839634E5
0x383963251  mov     r9d, 218h
0x383963257  mov     edx, 86009h
0x38396325c  jmp     loc_3839634D9
0x383963261  mov     eax, cs:dword_383B25694
0x383963267  movsd   xmm0, qword ptr cs:unk_383B25688
0x38396326f  movsd   xmm1, qword ptr cs:xmmword_383B25678+8
0x383963277  mov     r9d, cs:dword_383B25664
0x38396327e  mov     [rsp+2D0h+var_278], eax
0x383963282  mov     eax, cs:dword_383B25690
0x383963288  mov     dword ptr [rsp+2D0h+var_280], eax
0x38396328c  mov     eax, cs:dword_383B2566C
0x383963292  lea     r8, aLdLdLdFFFFLdLd; "%ld\t%ld\t%ld\t%f\t%f\t%f\t%f\t%ld\t%ld"...
0x383963299  movsd   [rsp+2D0h+var_288], xmm0
0x38396329f  movsd   xmm0, qword ptr cs:xmmword_383B25678
0x3839632a7  movsd   qword ptr [rsp+2D0h+var_298+8], xmm1
0x3839632ad  lea     rcx, [rbp+1D0h+Buffer]; unsigned __int16 *
0x3839632b1  mov     edx, 0FFh; unsigned __int64
0x3839632b6  movsd   xmm1, cs:qword_383B25670
0x3839632be  movsd   qword ptr [rsp+2D0h+var_298], xmm0
0x3839632c4  movsd   [rsp+2D0h+var_2A0], xmm1
0x3839632ca  mov     dword ptr [rsp+2D0h+var_2A8], eax
0x3839632ce  mov     eax, cs:dword_383B25668
0x3839632d4  mov     dword ptr [rsp+2D0h+lpOverlapped], eax
0x3839632d8  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x3839632dd  lea     r11, [rbp+1D0h+Buffer]
0x3839632e1  mov     rax, r14
0x3839632e4  inc     rax
0x3839632e7  cmp     [r11+rax*2], bx
0x3839632ec  jnz     short loc_3839632E4
0x3839632ee  lea     r8d, [rax+rax]; nNumberOfBytesToWrite
0x3839632f2  lea     r9, [rsp+2D0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x3839632f7  lea     rdx, [rbp+1D0h+Buffer]; lpBuffer
0x3839632fb  mov     rcx, rdi; hFile
0x3839632fe  mov     [rsp+2D0h+lpOverlapped], rbx; lpOverlapped
0x383963303  call    cs:__imp_WriteFile
0x383963309  test    eax, eax
0x38396330b  jnz     short loc_383963345
0x38396330d  test    byte ptr cs:_bidGblFlags, 2
0x383963314  movzx   ebx, r14w
0x383963318  jz      loc_3839634E5
0x38396331e  mov     rcx, cs:off_383B43218; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x383963325  mov     rax, cs:off_383B49120; "<Trace|MARK> line %d\n"
0x38396332c  test    rax, rax
0x38396332f  jz      loc_3839634E5
0x383963335  mov     r9d, 228h
0x38396333b  mov     edx, 8A009h
0x383963340  jmp     loc_3839634D9
0x383963345  mov     eax, cs:dword_383B256B0
0x38396334b  movsd   xmm0, cs:qword_383B256B8
0x383963353  mov     r9d, cs:dword_383B25698
0x38396335a  movsd   [rsp+2D0h+var_280], xmm0
0x383963360  mov     dword ptr [rsp+2D0h+var_288], eax
0x383963364  mov     eax, cs:dword_383B256AC
0x38396336a  mov     dword ptr [rsp+2D0h+var_298+8], eax
0x38396336e  mov     eax, cs:dword_383B256A8
0x383963374  lea     r8, aLdLdLdLdLdLdLd_0; "%ld\t%ld\t%ld\t%ld\t%ld\t%ld\t%ld\t%f\t"
0x38396337b  mov     dword ptr [rsp+2D0h+var_298], eax
0x38396337f  mov     eax, cs:dword_383B256A4
0x383963385  lea     rcx, [rbp+1D0h+Buffer]; unsigned __int16 *
0x383963389  mov     dword ptr [rsp+2D0h+var_2A0], eax
0x38396338d  mov     eax, cs:dword_383B256A0
0x383963393  mov     edx, 0FFh; unsigned __int64
0x383963398  mov     dword ptr [rsp+2D0h+var_2A8], eax
0x38396339c  mov     eax, cs:dword_383B2569C
0x3839633a2  mov     dword ptr [rsp+2D0h+lpOverlapped], eax
0x3839633a6  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x3839633ab  lea     r11, [rbp+1D0h+Buffer]
0x3839633af  mov     rax, r14
0x3839633b2  inc     rax
0x3839633b5  cmp     [r11+rax*2], bx
0x3839633ba  jnz     short loc_3839633B2
0x3839633bc  lea     r8d, [rax+rax]; nNumberOfBytesToWrite
0x3839633c0  lea     r9, [rsp+2D0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x3839633c5  lea     rdx, [rbp+1D0h+Buffer]; lpBuffer
0x3839633c9  mov     rcx, rdi; hFile
0x3839633cc  mov     [rsp+2D0h+lpOverlapped], rbx; lpOverlapped
0x3839633d1  call    cs:__imp_WriteFile
0x3839633d7  test    eax, eax
0x3839633d9  jnz     short loc_383963413
0x3839633db  test    byte ptr cs:_bidGblFlags, 2
0x3839633e2  movzx   ebx, r14w
0x3839633e6  jz      loc_3839634E5
0x3839633ec  mov     rcx, cs:off_383B43218; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x3839633f3  mov     rax, cs:off_383B49120; "<Trace|MARK> line %d\n"
0x3839633fa  test    rax, rax
0x3839633fd  jz      loc_3839634E5
0x383963403  mov     r9d, 237h
0x383963409  mov     edx, 8DC09h
0x38396340e  jmp     loc_3839634D9
0x383963413  mov     r9d, cs:dword_383B256C0
0x38396341a  test    rsi, rsi
0x38396341d  lea     rax, WideCharStr
0x383963424  cmovnz  rax, rsi
0x383963428  lea     r8, aLdLdLdLdLdLdLd; "%ld\t%ld\t%ld\t%ld\t%ld\t%ld\t%ld\t%s\r"...
0x38396342f  lea     rcx, [rbp+1D0h+Buffer]; unsigned __int16 *
0x383963433  mov     [rsp+2D0h+var_280], rax
0x383963438  mov     eax, cs:dword_383B256D8
0x38396343e  mov     edx, 0FFh; unsigned __int64
0x383963443  mov     dword ptr [rsp+2D0h+var_288], eax
0x383963447  mov     eax, cs:dword_383B256D4
0x38396344d  mov     dword ptr [rsp+2D0h+var_298+8], eax
0x383963451  mov     eax, cs:dword_383B256D0
0x383963457  mov     dword ptr [rsp+2D0h+var_298], eax
0x38396345b  mov     eax, cs:dword_383B256CC
0x383963461  mov     dword ptr [rsp+2D0h+var_2A0], eax
0x383963465  mov     eax, cs:dword_383B256C8
0x38396346b  mov     dword ptr [rsp+2D0h+var_2A8], eax
0x38396346f  mov     eax, cs:dword_383B256C4
0x383963475  mov     dword ptr [rsp+2D0h+lpOverlapped], eax
0x383963479  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x38396347e  lea     r11, [rbp+1D0h+Buffer]
0x383963482  mov     rax, r14
0x383963485  inc     rax
0x383963488  cmp     [r11+rax*2], bx
0x38396348d  jnz     short loc_383963485
0x38396348f  lea     r8d, [rax+rax]; nNumberOfBytesToWrite
0x383963493  lea     r9, [rsp+2D0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x383963498  lea     rdx, [rbp+1D0h+Buffer]; lpBuffer
0x38396349c  mov     rcx, rdi; hFile
0x38396349f  mov     [rsp+2D0h+lpOverlapped], rbx; lpOverlapped
0x3839634a4  call    cs:__imp_WriteFile
0x3839634aa  test    eax, eax
0x3839634ac  jnz     short loc_3839634E5
0x3839634ae  test    byte ptr cs:_bidGblFlags, 2
0x3839634b5  movzx   ebx, r14w
0x3839634b9  jz      short loc_3839634E5
0x3839634bb  mov     rcx, cs:off_383B43218; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x3839634c2  mov     rax, cs:off_383B49120; "<Trace|MARK> line %d\n"
0x3839634c9  test    rax, rax
0x3839634cc  jz      short loc_3839634E5
0x3839634ce  mov     r9d, 246h
0x3839634d4  mov     edx, 91809h
0x3839634d9  mov     r8, cs:off_383B49120; "<Trace|MARK> line %d\n"
0x3839634e0  call    _bidTraceW
0x3839634e5  mov     r14, [rsp+2C0h]
0x3839634ed  mov     rax, cs:?g_csSQLPerf@@3PEAVCCriticalSection@@EA; CCriticalSection * g_csSQLPerf
0x3839634f4  mov     rdx, [rax+20h]
0x3839634f8  lea     rcx, [rax+20h]
0x3839634fc  call    qword ptr [rdx+18h]
0x3839634ff  test    byte ptr cs:_bidGblFlags, 2
0x383963506  mov     rdi, [rsp+2D0h+arg_10]
0x38396350e  mov     rsi, [rsp+2D0h+arg_8]
0x383963516  jz      short loc_38396354D
0x383963518  mov     rcx, cs:off_383B43218; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x38396351f  mov     r8, cs:off_383B494E8; "<ODBC|DRIVER|RET> %d{SQLRETURN}\n"
0x383963526  test    bx, bx
0x383963529  jnz     short loc_383963534
0x38396352b  test    byte ptr cs:_bidGblFlags, 40h
0x383963532  jz      short loc_38396354D
0x383963534  mov     eax, 92C21h
0x383963539  test    bx, bx
0x38396353c  mov     edx, 92C01h
0x383963541  cmovnz  edx, eax
0x383963544  movsx   r9d, bx
0x383963548  call    _bidTraceW
0x38396354d  movzx   eax, bx
0x383963550  mov     rcx, [rbp+1D0h+var_20]
0x383963557  xor     rcx, rsp; StackCookie
0x38396355a  call    __security_check_cookie
0x38396355f  add     rsp, 2C8h
0x383963566  pop     rbx
0x383963567  pop     rbp
0x383963568  retn
```
