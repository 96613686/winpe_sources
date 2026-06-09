# HbDrvDeserializeBitmapsInternal

- ea: `0x18009fe7c`
- end: `0x1800a0659`
- name: `HbDrvDeserializeBitmapsInternal`
- size: `2013`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, registry_config, loader_planting, installer_update`

## callers

- `0x18009fe2c`

## callees

- `0x18001bfcc`
- `0x18001c020`
- `0x18009ef80`
- `0x18009efb8`
- `0x18009f0d8`
- `0x18009fe7c`
- `0x1800a0d90`
- `0x1800b57c0`
- `0x1800b605c`
- `0x1800b62c8`
- `0x1800b645a`
- `0x1800b7010`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x1800a02eb`
- `ntdll!RtlNtStatusToDosError` at `0x1800a02eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009ff81`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009ff81`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a0636`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a0636`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18009ff6e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18009ff6e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800a02ce`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800a04f9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800a05a3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800a05bf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800a05ee`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800a0612`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800a02ce`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800a04f9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800a05a3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800a05bf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800a05ee`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800a0612`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18009ffa1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18009ffdd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a0074`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a0158`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a0318`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18009ffa1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18009ffdd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a0074`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a0158`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a0318`

## pseudocode

```c
__int64 __fastcall HbDrvDeserializeBitmapsInternal(__int64 a1, const WCHAR *a2, char **a3, _DWORD *a4, int a5)
{
  __int64 v7; // r9
  unsigned int File; // ebx
  HANDLE v9; // rdi
  struct _OVERLAPPED *v10; // r15
  char *v11; // rsi
  int j; // r13d
  void *v13; // rax
  unsigned int v14; // eax
  unsigned int i; // ebx
  __int64 v16; // rdi
  char *v17; // rsi
  int v18; // eax
  LPVOID v19; // rax
  unsigned int v20; // ecx
  __int64 v21; // r14
  unsigned __int64 v22; // rsi
  char *v23; // rdi
  __int64 ii; // rcx
  __int64 v25; // r9
  __int64 v26; // rdx
  __m128i *v27; // rax
  __m128i v28; // xmm1
  __m128i v29; // xmm0
  __int64 v30; // r8
  unsigned __int64 v31; // rax
  char v32; // cl
  DWORD v33; // ebx
  void *v34; // rax
  void *v35; // r8
  void *v36; // r8
  unsigned int *v37; // r14
  unsigned int jj; // ebx
  int v39; // r9d
  __int64 v40; // rcx
  NTSTATUS updated; // eax
  char *v42; // rsi
  unsigned int v43; // r15d
  unsigned int k; // ebx
  __int64 v45; // r14
  unsigned int v46; // eax
  int m; // edi
  __int64 BitmapForVolume; // rax
  __int64 v49; // rdx
  __int64 v50; // r9
  char v51; // cl
  unsigned __int64 v52; // rdx
  unsigned int v53; // r15d
  unsigned int v54; // r12d
  char *v55; // rcx
  char *v56; // rdi
  __int64 n; // r14
  unsigned int v58; // r15d
  unsigned int v59; // r14d
  char *v60; // r12
  char *v61; // rdi
  __int64 kk; // rsi
  _QWORD *v63; // rdx
  unsigned int v64; // ecx
  __int64 mm; // rdi
  void *v66; // r8
  char *v68; // [rsp+48h] [rbp-A1h]
  __int64 Buffer; // [rsp+50h] [rbp-99h] BYREF
  HANDLE hFile; // [rsp+58h] [rbp-91h]
  __int64 v71; // [rsp+60h] [rbp-89h] BYREF
  __int64 v72; // [rsp+68h] [rbp-81h]
  unsigned int v73; // [rsp+70h] [rbp-79h]
  LPVOID v74; // [rsp+78h] [rbp-71h]
  LPVOID lpMem; // [rsp+80h] [rbp-69h]
  unsigned __int64 v76; // [rsp+88h] [rbp-61h]
  __m128i v77; // [rsp+90h] [rbp-59h] BYREF
  __m128i v78; // [rsp+A0h] [rbp-49h]
  char v79[8]; // [rsp+B8h] [rbp-31h] BYREF
  __int64 v80; // [rsp+C0h] [rbp-29h]

  v76 = 0;
  memset_0(v79, 0, 0x48u);
  LODWORD(v72) = 0;
  v71 = 0;
  Buffer = 0;
  v77 = 0;
  v78 = 0;
  if ( a5 )
  {
    v80 = -1;
    File = PfsBcCreateFile((__int64)v79, a2, 0, v7, 0);
    if ( File )
    {
LABEL_109:
      PfsBcClose(v79);
      return File;
    }
    v9 = 0;
    hFile = 0;
  }
  else
  {
    hFile = CreateFileW(a2, 0x80000000, 0, 0, 3u, 0, 0);
    v9 = hFile;
    if ( !hFile )
      return GetLastError();
  }
  v10 = (struct _OVERLAPPED *)((unsigned __int64)v79 & -(__int64)(a5 != 0));
  File = HbDrvBitmapReadFile(v10, v9, &Buffer, 8u);
  if ( !File )
  {
    if ( (_DWORD)Buffer == 2 )
    {
      v68 = (char *)HeapAlloc(*(HANDLE *)(*(_QWORD *)&PfSvcGlobals + 88LL), 0, (unsigned int)(104 * HIDWORD(Buffer)));
      v11 = v68;
      if ( v68 )
      {
        j = 0;
        lpMem = 0;
        v13 = HeapAlloc(*(HANDLE *)(*(_QWORD *)&PfSvcGlobals + 88LL), 0, 8LL * HIDWORD(Buffer));
        v74 = v13;
        if ( v13 )
        {
          memset_0(v13, 0, 8LL * HIDWORD(Buffer));
          v14 = HIDWORD(Buffer);
          for ( i = 0; i < HIDWORD(Buffer); ++i )
          {
            HbDrvBitmapInitialize(&v68[104 * i]);
            v14 = HIDWORD(Buffer);
          }
          v16 = 0;
          while ( (unsigned int)v16 < v14 )
          {
            v17 = &v11[104 * (unsigned int)v16];
            File = HbDrvBitmapReadFile(v10, hFile, v17, 0x18u);
            if ( File )
              goto LABEL_87;
            v18 = *((_DWORD *)v17 + 5);
            if ( v18 )
            {
              v19 = HeapAlloc(
                      *(HANDLE *)(*(_QWORD *)&PfSvcGlobals + 88LL),
                      0,
                      (unsigned int)(*((_DWORD *)v17 + 4) * v18));
              *((_QWORD *)v74 + v16) = v19;
              if ( !v19 )
              {
                File = 8;
                goto LABEL_87;
              }
            }
            v14 = HIDWORD(Buffer);
            v16 = (unsigned int)(v16 + 1);
            v11 = v68;
          }
          v20 = 0;
          for ( j = 1; ; j = 1 )
          {
            v73 = v20;
            if ( v20 >= v14 )
            {
              v42 = (char *)HeapAlloc(
                              *(HANDLE *)(*(_QWORD *)&PfSvcGlobals + 88LL),
                              0,
                              (unsigned int)(624 * *(_DWORD *)(a1 + 28)));
              if ( v42 )
              {
                v43 = 0;
                for ( k = 0; k < 6 * *(_DWORD *)(a1 + 28); ++k )
                  HbDrvBitmapInitialize(&v42[104 * k]);
                v45 = 0;
LABEL_62:
                v46 = *(_DWORD *)(a1 + 28);
                if ( (unsigned int)v45 < v46 )
                {
                  for ( m = 5; ; --m )
                  {
                    if ( m < 0 )
                    {
                      v45 = (unsigned int)(v45 + 1);
                      goto LABEL_62;
                    }
                    BitmapForVolume = HbDrvFindBitmapForVolume(
                                        *(_QWORD *)(*(_QWORD *)(a1 + 32) + 48 * v45 + 8),
                                        v68,
                                        HIDWORD(Buffer),
                                        (unsigned int)m);
                    if ( BitmapForVolume
                      && *(unsigned int *)(BitmapForVolume + 76)
                       * (unsigned __int64)*(unsigned int *)(BitmapForVolume + 80) )
                    {
                      v49 = 104LL * v43;
                      *(_OWORD *)&v42[v49] = *(_OWORD *)BitmapForVolume;
                      *(_OWORD *)&v42[v49 + 16] = *(_OWORD *)(BitmapForVolume + 16);
                      *(_OWORD *)&v42[v49 + 32] = *(_OWORD *)(BitmapForVolume + 32);
                      *(_OWORD *)&v42[v49 + 48] = *(_OWORD *)(BitmapForVolume + 48);
                      *(_OWORD *)&v42[v49 + 64] = *(_OWORD *)(BitmapForVolume + 64);
                      *(_OWORD *)&v42[v49 + 80] = *(_OWORD *)(BitmapForVolume + 80);
                      *(_QWORD *)&v42[v49 + 96] = *(_QWORD *)(BitmapForVolume + 96);
                      HbDrvBitmapInitialize(BitmapForVolume);
                    }
                    else
                    {
                      v50 = *(_QWORD *)(a1 + 32);
                      v51 = *(_BYTE *)(a1 + 24);
                      v52 = ((unsigned __int64)(unsigned int)(1 << v51) + *(_QWORD *)(v50 + 48 * v45) - 1LL)
                          / (unsigned int)(1 << v51);
                      if ( v52 >= 0xFFFFFFFFLL << v51 )
                        v52 = 0xFFFFFFFFLL << v51;
                      File = HbDrvBitmapStart((unsigned int)v42 + 104 * v43, v52, m, 0, *(_QWORD *)(v50 + 48 * v45 + 8));
                      if ( File )
                      {
                        j = 0;
                        v53 = 0;
                        v54 = 6 * *(_DWORD *)(a1 + 28);
                        if ( v54 )
                        {
                          v55 = v42 + 24;
                          do
                          {
                            v56 = &v55[104 * v53];
                            if ( *((_QWORD *)v56 + 1) )
                            {
                              for ( n = 0; (unsigned int)n < *((_DWORD *)v56 + 13); n = (unsigned int)(n + 1) )
                              {
                                if ( (unsigned __int8)RtlpSparseBitmapCheckRangeArrayPage(v56, (unsigned int)n) )
                                {
                                  if ( *(_QWORD *)(*((_QWORD *)v56 + 1) + 8 * n) )
                                    (*((void (**)(void))v56 + 5))();
                                }
                                else
                                {
                                  LODWORD(n) = n + 511;
                                }
                              }
                              RtlpSparseBitmapRangeArrayCleanup(v56, *((_QWORD *)v56 + 1), *((_QWORD *)v56 + 3));
                              v55 = v42 + 24;
                            }
                            ++v53;
                          }
                          while ( v53 < v54 );
                        }
                        HeapFree(*(HANDLE *)(*(_QWORD *)&PfSvcGlobals + 88LL), 0, v42);
                        goto LABEL_87;
                      }
                    }
                    ++v43;
                  }
                }
                File = 0;
                *a3 = v42;
                *a4 = 6 * v46;
              }
              else
              {
LABEL_57:
                File = 8;
              }
              j = 0;
              goto LABEL_87;
            }
            v21 = v20;
            v22 = 0;
            v23 = &v68[104 * v20];
            for ( ii = 0; (unsigned int)ii < *(_DWORD *)(a1 + 28); ii = (unsigned int)(ii + 1) )
            {
              v25 = *(_QWORD *)(a1 + 32);
              v26 = 6 * ii;
              v27 = *(__m128i **)(v25 + 48 * ii + 8);
              v28 = *v27;
              v29 = v27[1];
              v30 = v27->m128i_i64[0];
              v31 = HIDWORD(v27->m128i_i64[0]);
              v77 = v28;
              v78 = v29;
              if ( __PAIR64__(v30, v31) == *(_QWORD *)v23
                && _mm_cvtsi128_si32(_mm_srli_si128(v28, 8)) == *((_DWORD *)v23 + 2) )
              {
                v32 = *(_BYTE *)(a1 + 24);
                v22 = 0xFFFFFFFFLL << v32;
                if ( ((unsigned __int64)(unsigned int)(1 << v32) + *(_QWORD *)(v25 + 8 * v26) - 1LL)
                   / (unsigned int)(1 << v32) < 0xFFFFFFFFLL << v32 )
                  v22 = ((unsigned __int64)(unsigned int)(1 << v32) + *(_QWORD *)(v25 + 8 * v26) - 1LL)
                      / (unsigned int)(1 << v32);
                break;
              }
            }
            v33 = 24 * *((_DWORD *)v23 + 4);
            v34 = HeapAlloc(*(HANDLE *)(*(_QWORD *)&PfSvcGlobals + 88LL), 0, v33);
            lpMem = v34;
            if ( !v34 )
              goto LABEL_57;
            File = HbDrvBitmapReadFile(v10, hFile, v34, v33);
            if ( File )
              goto LABEL_87;
            v35 = (void *)*((_QWORD *)v74 + v21);
            if ( v35 )
            {
              File = HbDrvBitmapReadFile(v10, hFile, v35, *((_DWORD *)v23 + 4) * *((_DWORD *)v23 + 5));
              if ( File )
                goto LABEL_87;
              LODWORD(v71) = *((_DWORD *)v23 + 5);
            }
            else
            {
              LODWORD(v71) = 0;
            }
            if ( v22 )
              break;
            v36 = lpMem;
LABEL_55:
            HeapFree(*(HANDLE *)(*(_QWORD *)&PfSvcGlobals + 88LL), 0, v36);
            v14 = HIDWORD(Buffer);
            v20 = v73 + 1;
          }
          File = HbDrvBitmapStart((_DWORD)v23, v22, *((_DWORD *)v23 + 3), *((_DWORD *)v23 + 5), (__int64)&v77);
          if ( !File )
          {
            if ( (_DWORD)v71 )
              v72 = *((_QWORD *)v74 + v21);
            else
              v72 = 0;
            v37 = (unsigned int *)lpMem;
            for ( jj = 0; ; ++jj )
            {
              if ( jj >= *((_DWORD *)v23 + 4) )
              {
                v36 = v37;
                goto LABEL_55;
              }
              v39 = *(_QWORD *)&v37[6 * jj];
              v76 = *(_QWORD *)&v37[6 * jj];
              if ( v76 < v22 )
              {
                v40 = v37[6 * jj + 2];
                if ( (_DWORD)v40 )
                {
                  if ( v76 + v40 > v22 )
                  {
                    LODWORD(v40) = v22 - v39;
                    v37[6 * jj + 2] = v22 - v39;
                  }
                  if ( v72 )
                  {
                    updated = RtlpSparseBitmapCtxUpdateBitRanges(
                                (int)v23 + 24,
                                v39,
                                v40,
                                (unsigned int)HbDrvDeserializeBitmapMetadataCallback,
                                (__int64)&v71,
                                1,
                                0);
                    v72 += (unsigned int)v71;
                  }
                  else
                  {
                    updated = RtlpSparseBitmapCtxUpdateBitRanges((int)v23 + 24, v39, v40, 0, 0, 1, 0);
                  }
                  if ( updated < 0 )
                    break;
                }
              }
            }
            File = RtlNtStatusToDosError(updated);
          }
LABEL_87:
          v11 = v68;
        }
        else
        {
          File = 8;
        }
        v58 = HIDWORD(Buffer);
        v59 = 0;
        if ( HIDWORD(Buffer) )
        {
          v60 = v11 + 24;
          do
          {
            v61 = &v60[104 * v59];
            if ( *((_QWORD *)v61 + 1) )
            {
              for ( kk = 0; (unsigned int)kk < *((_DWORD *)v61 + 13); kk = (unsigned int)(kk + 1) )
              {
                if ( (unsigned __int8)RtlpSparseBitmapCheckRangeArrayPage(&v60[104 * v59], (unsigned int)kk) )
                {
                  if ( *(_QWORD *)(*((_QWORD *)v61 + 1) + 8 * kk) )
                    (*((void (**)(void))v61 + 5))();
                }
                else
                {
                  LODWORD(kk) = kk + 511;
                }
              }
              RtlpSparseBitmapRangeArrayCleanup(&v60[104 * v59], *((_QWORD *)v61 + 1), *((_QWORD *)v61 + 3));
            }
            ++v59;
          }
          while ( v59 < v58 );
        }
        HeapFree(*(HANDLE *)(*(_QWORD *)&PfSvcGlobals + 88LL), 0, v68);
        if ( j )
          HeapFree(*(HANDLE *)(*(_QWORD *)&PfSvcGlobals + 88LL), 0, lpMem);
        v63 = v74;
        if ( v74 )
        {
          v64 = HIDWORD(Buffer);
          for ( mm = 0; (unsigned int)mm < v64; mm = (unsigned int)(mm + 1) )
          {
            v66 = (void *)v63[mm];
            if ( v66 )
            {
              HeapFree(*(HANDLE *)(*(_QWORD *)&PfSvcGlobals + 88LL), 0, v66);
              v64 = HIDWORD(Buffer);
              v63 = v74;
            }
          }
          HeapFree(*(HANDLE *)(*(_QWORD *)&PfSvcGlobals + 88LL), 0, v63);
        }
        v9 = hFile;
      }
      else
      {
        File = 8;
      }
    }
    else
    {
      File = 1006;
    }
  }
  if ( a5 )
    goto LABEL_109;
  if ( v9 )
    CloseHandle(v9);
  return File;
}

```

## disassembly

```asm
0x18009fe7c  mov     rax, rsp
0x18009fe7f  mov     [rax+8], rbx
0x18009fe83  mov     [rax+20h], r9
0x18009fe87  mov     [rax+18h], r8
0x18009fe8b  push    rbp
0x18009fe8c  push    rsi
0x18009fe8d  push    rdi
0x18009fe8e  push    r12
0x18009fe90  push    r13
0x18009fe92  push    r14
0x18009fe94  push    r15
0x18009fe96  lea     rbp, [rax-57h]
0x18009fe9a  sub     rsp, 100h
0x18009fea1  mov     rbx, rdx
0x18009fea4  mov     [rbp+4Fh+var_B0], 0
0x18009feac  xor     edx, edx; Val
0x18009feae  mov     r12, rcx
0x18009feb1  lea     rcx, [rbp+4Fh+var_80]; void *
0x18009feb5  lea     r8d, [rdx+48h]; Size
0x18009feb9  call    memset_0
0x18009febe  mov     r15d, [rbp+4Fh+arg_20]
0x18009fec2  xor     eax, eax
0x18009fec4  xorps   xmm0, xmm0
0x18009fec7  mov     [rsp+130h+var_D8+4], rax
0x18009fecc  xor     r8d, r8d; dwShareMode
0x18009fecf  mov     [rsp+130h+var_D8], rax
0x18009fed4  mov     [rsp+130h+Buffer], rax
0x18009fed9  movups  [rbp+4Fh+var_A8], xmm0
0x18009fedd  movups  [rbp+4Fh+var_98], xmm0
0x18009fee1  test    r15d, r15d
0x18009fee4  jz      short loc_18009FF52
0x18009fee6  mov     rdx, rbx
0x18009fee9  mov     [rbp+4Fh+var_78], 0FFFFFFFFFFFFFFFFh
0x18009fef1  lea     rcx, [rbp+4Fh+var_80]
0x18009fef5  mov     [rsp+130h+dwCreationDisposition], eax
0x18009fef9  call    PfsBcCreateFile
0x18009fefe  mov     ebx, eax
0x18009ff00  test    eax, eax
0x18009ff02  jnz     loc_1800A0623
0x18009ff08  xor     edi, edi
0x18009ff0a  mov     [rsp+130h+hFile], rdi
0x18009ff0f  mov     eax, r15d
0x18009ff12  lea     r8, [rsp+130h+Buffer]; lpBuffer
0x18009ff17  neg     eax
0x18009ff19  mov     r14d, 8
0x18009ff1f  lea     rax, [rbp+4Fh+var_80]
0x18009ff23  mov     r9d, r14d; nNumberOfBytesToRead
0x18009ff26  sbb     r15, r15
0x18009ff29  mov     rdx, rdi; hFile
0x18009ff2c  and     r15, rax
0x18009ff2f  mov     rcx, r15; lpOverlapped
0x18009ff32  call    HbDrvBitmapReadFile
0x18009ff37  mov     ebx, eax
0x18009ff39  test    eax, eax
0x18009ff3b  jnz     loc_1800A061D
0x18009ff41  cmp     dword ptr [rsp+130h+Buffer], 2
0x18009ff46  jz      short loc_18009FF8E
0x18009ff48  mov     ebx, 3EEh
0x18009ff4d  jmp     loc_1800A061D
0x18009ff52  mov     [rsp+30h], rax; hTemplateFile
0x18009ff57  xor     r9d, r9d; lpSecurityAttributes
0x18009ff5a  mov     [rsp+130h+dwFlagsAndAttributes], eax; dwFlagsAndAttributes
0x18009ff5e  mov     edx, 80000000h; dwDesiredAccess
0x18009ff63  mov     rcx, rbx; lpFileName
0x18009ff66  mov     [rsp+130h+dwCreationDisposition], 3; dwCreationDisposition
0x18009ff6e  call    cs:__imp_CreateFileW
0x18009ff74  mov     [rsp+130h+hFile], rax
0x18009ff79  mov     rdi, rax
0x18009ff7c  test    rax, rax
0x18009ff7f  jnz     short loc_18009FF0F
0x18009ff81  call    cs:__imp_GetLastError
0x18009ff87  mov     ebx, eax
0x18009ff89  jmp     loc_1800A063C
0x18009ff8e  mov     rcx, cs:PfSvcGlobals
0x18009ff95  xor     edx, edx; dwFlags
0x18009ff97  imul    r8d, dword ptr [rsp+130h+Buffer+4], 68h ; 'h'; dwBytes
0x18009ff9d  mov     rcx, [rcx+58h]; hHeap
0x18009ffa1  call    cs:__imp_HeapAlloc
0x18009ffa7  mov     [rsp+130h+var_F0], rax
0x18009ffac  mov     rsi, rax
0x18009ffaf  test    rax, rax
0x18009ffb2  jnz     short loc_18009FFBC
0x18009ffb4  mov     ebx, r14d
0x18009ffb7  jmp     loc_1800A061D
0x18009ffbc  mov     rcx, cs:PfSvcGlobals
0x18009ffc3  xor     edx, edx; dwFlags
0x18009ffc5  mov     r8d, dword ptr [rsp+130h+Buffer+4]
0x18009ffca  xor     r13d, r13d
0x18009ffcd  shl     r8, 3; dwBytes
0x18009ffd1  mov     [rbp+4Fh+lpMem], 0
0x18009ffd9  mov     rcx, [rcx+58h]; hHeap
0x18009ffdd  call    cs:__imp_HeapAlloc
0x18009ffe3  mov     [rbp+4Fh+var_C0], rax
0x18009ffe7  test    rax, rax
0x18009ffea  jnz     short loc_18009FFF4
0x18009ffec  mov     ebx, r14d
0x18009ffef  jmp     loc_1800A051D
0x18009fff4  mov     r8d, dword ptr [rsp+130h+Buffer+4]
0x18009fff9  xor     edx, edx; Val
0x18009fffb  shl     r8, 3; Size
0x18009ffff  mov     rcx, rax; void *
0x1800a0002  call    memset_0
0x1800a0007  mov     eax, dword ptr [rsp+130h+Buffer+4]
0x1800a000b  xor     ebx, ebx
0x1800a000d  test    eax, eax
0x1800a000f  jz      short loc_1800A0029
0x1800a0011  mov     eax, ebx
0x1800a0013  imul    rcx, rax, 68h ; 'h'
0x1800a0017  add     rcx, rsi
0x1800a001a  call    HbDrvBitmapInitialize
0x1800a001f  mov     eax, dword ptr [rsp+130h+Buffer+4]
0x1800a0023  inc     ebx
0x1800a0025  cmp     ebx, eax
0x1800a0027  jb      short loc_1800A0011
0x1800a0029  xor     edi, edi
0x1800a002b  cmp     edi, eax
0x1800a002d  jnb     short loc_1800A009E
0x1800a002f  mov     rdx, [rsp+130h+hFile]; hFile
0x1800a0034  mov     r9d, 18h; nNumberOfBytesToRead
0x1800a003a  mov     r14d, edi
0x1800a003d  mov     rcx, r15; lpOverlapped
0x1800a0040  imul    rax, r14, 68h ; 'h'
0x1800a0044  add     rsi, rax
0x1800a0047  mov     r8, rsi; lpBuffer
0x1800a004a  call    HbDrvBitmapReadFile
0x1800a004f  mov     ebx, eax
0x1800a0051  test    eax, eax
0x1800a0053  jnz     loc_1800A0518
0x1800a0059  mov     eax, [rsi+14h]
0x1800a005c  test    eax, eax
0x1800a005e  jz      short loc_1800A0087
0x1800a0060  imul    eax, [rsi+10h]
0x1800a0064  xor     edx, edx; dwFlags
0x1800a0066  mov     rcx, cs:PfSvcGlobals
0x1800a006d  mov     rcx, [rcx+58h]; hHeap
0x1800a0071  mov     r8d, eax; dwBytes
0x1800a0074  call    cs:__imp_HeapAlloc
0x1800a007a  mov     rcx, [rbp+4Fh+var_C0]
0x1800a007e  mov     [rcx+rdi*8], rax
0x1800a0082  test    rax, rax
0x1800a0085  jz      short loc_1800A0094
0x1800a0087  mov     eax, dword ptr [rsp+130h+Buffer+4]
0x1800a008b  inc     edi
0x1800a008d  mov     rsi, [rsp+130h+var_F0]
0x1800a0092  jmp     short loc_1800A002B
0x1800a0094  mov     ebx, 8
0x1800a0099  jmp     loc_1800A0518
0x1800a009e  xor     ecx, ecx
0x1800a00a0  lea     r13d, [rcx+1]
0x1800a00a4  mov     [rbp+4Fh+var_C8], ecx
0x1800a00a7  mov     r10d, 0FFFFFFFFh
0x1800a00ad  cmp     ecx, eax
0x1800a00af  jnb     loc_1800A0302
0x1800a00b5  mov     r14d, ecx
0x1800a00b8  xor     esi, esi
0x1800a00ba  imul    rdi, r14, 68h ; 'h'
0x1800a00be  add     rdi, [rsp+130h+var_F0]
0x1800a00c3  xor     ecx, ecx
0x1800a00c5  cmp     ecx, [r12+1Ch]
0x1800a00ca  jnb     short loc_1800A013D
0x1800a00cc  mov     r9, [r12+20h]
0x1800a00d1  lea     rdx, [rcx+rcx*2]
0x1800a00d5  add     rdx, rdx
0x1800a00d8  mov     rax, [r9+rdx*8+8]
0x1800a00dd  movups  xmm1, xmmword ptr [rax]
0x1800a00e0  movups  xmm0, xmmword ptr [rax+10h]
0x1800a00e4  movq    r8, xmm1
0x1800a00e9  mov     rax, r8
0x1800a00ec  shr     rax, 20h
0x1800a00f0  movups  [rbp+4Fh+var_A8], xmm1
0x1800a00f4  movups  [rbp+4Fh+var_98], xmm0
0x1800a00f8  cmp     eax, [rdi]
0x1800a00fa  jnz     short loc_1800A0110
0x1800a00fc  cmp     r8d, [rdi+4]
0x1800a0100  jnz     short loc_1800A0110
0x1800a0102  psrldq  xmm1, 8
0x1800a0107  movd    eax, xmm1
0x1800a010b  cmp     eax, [rdi+8]
0x1800a010e  jz      short loc_1800A0115
0x1800a0110  add     ecx, r13d
0x1800a0113  jmp     short loc_1800A00C5
0x1800a0115  mov     rax, [r9+rdx*8]
0x1800a0119  mov     r8d, r13d
0x1800a011c  movzx   ecx, byte ptr [r12+18h]
0x1800a0122  dec     rax
0x1800a0125  shl     r8d, cl
0x1800a0128  xor     edx, edx
0x1800a012a  add     rax, r8
0x1800a012d  mov     rsi, r10
0x1800a0130  div     r8
0x1800a0133  shl     rsi, cl
0x1800a0136  cmp     rax, rsi
0x1800a0139  cmovb   rsi, rax
0x1800a013d  mov     eax, [rdi+10h]
0x1800a0140  xor     edx, edx; dwFlags
0x1800a0142  lea     ecx, [rax+rax*2]
0x1800a0145  shl     ecx, 3
0x1800a0148  mov     ebx, ecx
0x1800a014a  mov     r8d, ecx; dwBytes
0x1800a014d  mov     rcx, cs:PfSvcGlobals
0x1800a0154  mov     rcx, [rcx+58h]; hHeap
0x1800a0158  call    cs:__imp_HeapAlloc
0x1800a015e  mov     [rbp+4Fh+lpMem], rax
0x1800a0162  test    rax, rax
0x1800a0165  jz      loc_1800A02F8
0x1800a016b  mov     rdx, [rsp+130h+hFile]; hFile
0x1800a0170  mov     r9d, ebx; nNumberOfBytesToRead
0x1800a0173  mov     r8, rax; lpBuffer
0x1800a0176  mov     rcx, r15; lpOverlapped
0x1800a0179  call    HbDrvBitmapReadFile
0x1800a017e  mov     ebx, eax
0x1800a0180  test    eax, eax
0x1800a0182  jnz     loc_1800A0518
0x1800a0188  mov     rax, [rbp+4Fh+var_C0]
0x1800a018c  mov     r8, [rax+r14*8]; lpBuffer
0x1800a0190  test    r8, r8
0x1800a0193  jz      short loc_1800A01BE
0x1800a0195  mov     r9d, [rdi+14h]
0x1800a0199  mov     rcx, r15; lpOverlapped
0x1800a019c  imul    r9d, [rdi+10h]; nNumberOfBytesToRead
0x1800a01a1  mov     rdx, [rsp+130h+hFile]; hFile
0x1800a01a6  call    HbDrvBitmapReadFile
0x1800a01ab  mov     ebx, eax
0x1800a01ad  test    eax, eax
0x1800a01af  jnz     loc_1800A0518
0x1800a01b5  mov     eax, [rdi+14h]
0x1800a01b8  mov     dword ptr [rsp+130h+var_D8], eax
0x1800a01bc  jmp     short loc_1800A01C6
0x1800a01be  mov     dword ptr [rsp+130h+var_D8], 0
0x1800a01c6  test    rsi, rsi
0x1800a01c9  jnz     short loc_1800A01D4
0x1800a01cb  mov     r8, [rbp+4Fh+lpMem]
0x1800a01cf  jmp     loc_1800A02C1
0x1800a01d4  mov     r9d, [rdi+14h]
0x1800a01d8  lea     rax, [rbp+4Fh+var_A8]
0x1800a01dc  mov     r8d, [rdi+0Ch]
0x1800a01e0  mov     rdx, rsi
0x1800a01e3  mov     rcx, rdi
0x1800a01e6  mov     qword ptr [rsp+130h+dwCreationDisposition], rax
0x1800a01eb  call    HbDrvBitmapStart
0x1800a01f0  xor     r10d, r10d
0x1800a01f3  mov     ebx, eax
0x1800a01f5  test    eax, eax
0x1800a01f7  jnz     loc_1800A0518
0x1800a01fd  cmp     dword ptr [rsp+130h+var_D8], r10d
0x1800a0202  jbe     short loc_1800A0213
0x1800a0204  mov     rax, [rbp+4Fh+var_C0]
0x1800a0208  mov     rax, [rax+r14*8]
0x1800a020c  mov     [rsp+130h+var_D0], rax
0x1800a0211  jmp     short loc_1800A0218
0x1800a0213  mov     [rsp+130h+var_D0], r10
0x1800a0218  mov     r14, [rbp+4Fh+lpMem]
0x1800a021c  mov     ebx, r10d
0x1800a021f  cmp     ebx, [rdi+10h]
0x1800a0222  jnb     loc_1800A02BE
0x1800a0228  mov     eax, ebx
0x1800a022a  lea     r8, [rax+rax*2]
0x1800a022e  mov     eax, [r14+r8*8+4]
0x1800a0233  mov     r9d, [r14+r8*8]
0x1800a0237  mov     dword ptr [rbp+4Fh+var_B0+4], eax
0x1800a023a  mov     dword ptr [rbp+4Fh+var_B0], r9d
0x1800a023e  mov     rdx, [rbp+4Fh+var_B0]
0x1800a0242  cmp     rdx, rsi
0x1800a0245  jnb     short loc_1800A02B7
0x1800a0247  mov     ecx, [r14+r8*8+8]
0x1800a024c  test    ecx, ecx
0x1800a024e  jz      short loc_1800A02B7
0x1800a0250  lea     rax, [rdx+rcx]
0x1800a0254  cmp     rax, rsi
0x1800a0257  jbe     short loc_1800A0263
0x1800a0259  mov     ecx, esi
0x1800a025b  sub     ecx, r9d
0x1800a025e  mov     [r14+r8*8+8], ecx
0x1800a0263  mov     [rsp+30h], r10
0x1800a0268  mov     [rsp+130h+dwFlagsAndAttributes], 1
0x1800a0270  mov     r8d, ecx
0x1800a0273  cmp     [rsp+130h+var_D0], r10
0x1800a0278  jz      short loc_1800A029F
0x1800a027a  lea     rcx, [rsp+130h+var_D8]
0x1800a027f  mov     qword ptr [rsp+130h+dwCreationDisposition], rcx
0x1800a0284  lea     r9, HbDrvDeserializeBitmapMetadataCallback
0x1800a028b  lea     rcx, [rdi+18h]
0x1800a028f  call    RtlpSparseBitmapCtxUpdateBitRanges
0x1800a0294  mov     ecx, dword ptr [rsp+130h+var_D8]
0x1800a0298  add     [rsp+130h+var_D0], rcx
0x1800a029d  jmp     short loc_1800A02B0
0x1800a029f  xor     r9d, r9d
0x1800a02a2  mov     qword ptr [rsp+130h+dwCreationDisposition], r10
0x1800a02a7  lea     rcx, [rdi+18h]
0x1800a02ab  call    RtlpSparseBitmapCtxUpdateBitRanges
0x1800a02b0  xor     r10d, r10d
0x1800a02b3  test    eax, eax
0x1800a02b5  js      short loc_1800A02E9
0x1800a02b7  inc     ebx
0x1800a02b9  jmp     loc_1800A021F
0x1800a02be  mov     r8, r14; lpMem
0x1800a02c1  mov     rcx, cs:PfSvcGlobals
0x1800a02c8  xor     edx, edx; dwFlags
0x1800a02ca  mov     rcx, [rcx+58h]; hHeap
0x1800a02ce  call    cs:__imp_HeapFree
  ... truncated ...
```
