# GetServiceConfigStrings(ushort *,ulong,ushort *,ulong)

- ea: `0x180005480`
- end: `0x180005928`
- name: `?GetServiceConfigStrings@@YAXPEAGK0K@Z`
- size: `1192`
- prototype: `void __fastcall(unsigned __int16 *, __int64, unsigned __int16 *)`
- caller_count: `3`
- callee_count: `9`
- tags: `registry_config, service_task`

## callers

- `0x18000d464`
- `0x180019400`
- `0x180039100`

## callees

- `0x180001730`
- `0x180003ac0`
- `0x180005480`
- `0x180005930`
- `0x1800067b0`
- `0x180018138`
- `0x18001d9a0`
- `0x18003d270`
- `0x18003dd2c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005850`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005888`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800058aa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800058ca`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800058ff`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005915`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180064058`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180064079`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800640af`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800640d0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800640f1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180064104`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005850`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005888`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800058aa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800058ca`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800058ff`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005915`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180064058`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180064079`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800640af`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800640d0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800640f1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180064104`

## string_xrefs

- `0x1800057f9`: `Failed to gather service configuration info for logging purposes`

## pseudocode

```c
void __fastcall GetServiceConfigStrings(unsigned __int16 *a1, __int64 a2, unsigned __int16 *a3)
{
  __int64 v5; // rax
  const unsigned __int16 *v6; // r8
  __int64 v7; // rax
  unsigned __int16 *v8; // rcx
  int v9; // edx
  __int64 v10; // rbx
  __int64 v11; // rdx
  unsigned __int16 *v12; // r8
  __int64 v13; // rcx
  unsigned __int16 *v14; // r9
  __int64 v15; // r10
  unsigned __int16 v16; // ax
  __int64 v17; // rcx
  unsigned __int16 *v18; // rax
  int v19; // edx
  bool v20; // zf
  unsigned __int16 *v21; // rdx
  __int64 v22; // rsi
  unsigned __int16 *v23; // rcx
  __int64 v24; // r8
  unsigned __int16 v25; // ax
  HLOCAL v26; // rdx
  void *v27; // rcx
  void *v28; // rcx
  unsigned int i; // ebx
  void *v30; // rcx
  void *v31; // rcx
  unsigned __int16 * near **v32; // [rsp+20h] [rbp-1D8h]
  __int64 v33; // [rsp+20h] [rbp-1D8h]
  __int64 v34; // [rsp+20h] [rbp-1D8h]
  unsigned __int16 * near *v35; // [rsp+28h] [rbp-1D0h]
  __int64 v36; // [rsp+28h] [rbp-1D0h]
  HLOCAL hMem; // [rsp+30h] [rbp-1C8h] BYREF
  __int64 v38; // [rsp+38h] [rbp-1C0h]
  unsigned __int16 *v39; // [rsp+40h] [rbp-1B8h]
  __int64 v40; // [rsp+48h] [rbp-1B0h]
  __int64 v41; // [rsp+50h] [rbp-1A8h]
  unsigned __int16 *v42; // [rsp+58h] [rbp-1A0h]
  __int64 v43; // [rsp+60h] [rbp-198h]
  unsigned __int16 *v44; // [rsp+68h] [rbp-190h]
  __int64 v45; // [rsp+70h] [rbp-188h]
  unsigned __int16 *v46; // [rsp+78h] [rbp-180h]
  __int64 v47; // [rsp+80h] [rbp-178h]
  __int64 v48; // [rsp+88h] [rbp-170h]
  unsigned __int16 *v49; // [rsp+90h] [rbp-168h]
  __int64 v50; // [rsp+98h] [rbp-160h]
  unsigned __int16 *v51; // [rsp+A0h] [rbp-158h]
  __int64 v52; // [rsp+A8h] [rbp-150h]
  __int64 v53; // [rsp+B0h] [rbp-148h]
  unsigned __int16 v54; // [rsp+C0h] [rbp-138h] BYREF
  char v55[254]; // [rsp+C2h] [rbp-136h] BYREF

  hMem = 0;
  v54 = 0;
  memset_0(v55, 0, sizeof(v55));
  *a1 = 0;
  *a3 = 0;
  if ( (int)s_W32TimeQueryConfiguration(-1, &hMem) >= 0 && hMem )
  {
    v32 = &g_wszConfigFlagPtr;
    W32timeConfigInfoToString(a1);
    v5 = *((unsigned int *)qword_1800A42F0 + 59);
    if ( (unsigned int)v5 >= 5 )
    {
      LODWORD(v35) = *((_DWORD *)qword_1800A42F0 + 59);
      v6 = L"%s: %d (%d)\n";
    }
    else
    {
      v35 = (&g_wszConfigFlagPtr)[v5];
      v6 = L"%s: %d (%s)\n";
    }
    LODWORD(v32) = *((_DWORD *)qword_1800A42F0 + 58);
    if ( (int)StringCchPrintfW(&v54, 0x80u, v6, L"UtilizeSslTimeData", v32, v35) < 0 )
    {
      v10 = 2147483646;
    }
    else
    {
      v38 = 0;
      v7 = 4096;
      v45 = 4096;
      v8 = a1;
      v44 = a1;
      v9 = 0;
      while ( v7 && *v8 )
      {
        v44 = ++v8;
        v45 = --v7;
      }
      if ( !v7 )
        v9 = -2147024809;
      if ( v9 < 0 )
        v38 = 0;
      else
        v38 = 4096 - v7;
      v10 = 2147483646;
      if ( v9 >= 0 )
      {
        v11 = 2147483646;
        v48 = 2147483646;
        v12 = &v54;
        v46 = &v54;
        v13 = 4096 - v38;
        v47 = 4096 - v38;
        v14 = &a1[v38];
        v39 = v14;
        v15 = 0;
        v40 = 0;
        while ( v13 )
        {
          if ( !v11 )
            goto LABEL_20;
          v16 = *v12;
          if ( !*v12 )
            goto LABEL_20;
          v46 = ++v12;
          *v14++ = v16;
          v39 = v14;
          v47 = --v13;
          v48 = --v11;
          v40 = ++v15;
        }
        v39 = --v14;
        v40 = v15 - 1;
LABEL_20:
        *v14 = 0;
      }
    }
    LODWORD(v36) = qword_1800A4738;
    LODWORD(v33) = dword_1800A4720;
    if ( (int)StringCchPrintfW(
                &v54,
                0x80u,
                L"\n"
                 "[Leap Seconds]\n"
                 "Enabled: %d (Local)\n"
                 "Total Leap Seconds (after June 2018): %d (Local)\n"
                 "Current UTC offset: %d (Local)\n",
                (unsigned int)dword_1800A4710,
                v33,
                v36) >= 0 )
    {
      v41 = 0;
      v17 = 4096;
      v50 = 4096;
      v18 = a1;
      v49 = a1;
      v19 = 0;
      while ( 1 )
      {
        v20 = v17 == 0;
        if ( !v17 )
          break;
        if ( !*v18 )
        {
          v20 = v17 == 0;
          break;
        }
        v49 = ++v18;
        v50 = --v17;
      }
      if ( v20 )
        v19 = -2147024809;
      if ( v19 < 0 )
        v41 = 0;
      else
        v41 = 4096 - v17;
      if ( v19 >= 0 )
      {
        v53 = 2147483646;
        v21 = &v54;
        v51 = &v54;
        v22 = 4096 - v41;
        v52 = 4096 - v41;
        v23 = &a1[v41];
        v42 = v23;
        v24 = 0;
        v43 = 0;
        while ( v22 )
        {
          if ( !v10 )
            goto LABEL_37;
          v25 = *v21;
          if ( !*v21 )
            goto LABEL_37;
          v51 = ++v21;
          *v23++ = v25;
          v42 = v23;
          v52 = --v22;
          v53 = --v10;
          v43 = ++v24;
        }
        v42 = --v23;
        v43 = v24 - 1;
LABEL_37:
        *v23 = 0;
      }
    }
    W32timeConfigProviderInfoToString(a3, v34);
  }
  else if ( (unsigned __int8)FileLogAllowEntry(64) )
  {
    FileLogAdd(L"Failed to gather service configuration info for logging purposes");
  }
  v26 = hMem;
  if ( hMem )
  {
    v27 = (void *)*((_QWORD *)hMem + 20);
    if ( v27 )
    {
      LocalFree(v27);
      v26 = hMem;
    }
    v28 = (void *)*((_QWORD *)v26 + 19);
    if ( v28 )
    {
      LocalFree(v28);
      v26 = hMem;
    }
    if ( *((_QWORD *)v26 + 25) )
    {
      for ( i = 0; i < *((_DWORD *)v26 + 48); ++i )
      {
        v30 = *(void **)(*((_QWORD *)v26 + 25) + 8LL * i);
        if ( v30 )
        {
          LocalFree(v30);
          v26 = hMem;
        }
      }
      LocalFree(*((HLOCAL *)v26 + 25));
      v26 = hMem;
    }
    v31 = (void *)*((_QWORD *)v26 + 27);
    if ( v31 )
    {
      LocalFree(v31);
      v26 = hMem;
    }
    LocalFree(v26);
  }
}

```

## disassembly

```asm
0x180005480  mov     [rsp+arg_8], rbx
0x180005485  push    rsi
0x180005486  push    rdi
0x180005487  push    r12
0x180005489  push    r14
0x18000548b  push    r15
0x18000548d  sub     rsp, 1D0h
0x180005494  mov     rax, cs:__security_cookie
0x18000549b  xor     rax, rsp
0x18000549e  mov     [rsp+1F8h+var_38], rax
0x1800054a6  mov     r15, r8
0x1800054a9  mov     r14, rcx
0x1800054ac  xor     r12d, r12d
0x1800054af  mov     [rsp+1F8h+hMem], r12
0x1800054b4  mov     [rsp+1F8h+var_138], r12w
0x1800054bd  xor     edx, edx; Val
0x1800054bf  mov     r8d, 0FEh; Size
0x1800054c5  lea     rcx, [rsp+1F8h+var_136]; void *
0x1800054cd  call    memset_0
0x1800054d2  mov     [r14], r12w
0x1800054d6  mov     [r15], r12w
0x1800054da  lea     rdx, [rsp+1F8h+hMem]
0x1800054df  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800054e6  call    s_W32TimeQueryConfiguration
0x1800054eb  test    eax, eax
0x1800054ed  js      loc_1800057EB
0x1800054f3  mov     r8, [rsp+1F8h+hMem]
0x1800054f8  test    r8, r8
0x1800054fb  jz      loc_1800057EB
0x180005501  lea     rbx, ?g_wszConfigFlagPtr@@3PAPEAGA; ushort * near * g_wszConfigFlagPtr
0x180005508  mov     [rsp+1F8h+var_1D8], rbx
0x18000550d  mov     r9b, 1
0x180005510  mov     esi, 1000h
0x180005515  mov     edx, esi
0x180005517  mov     rcx, r14; unsigned __int16 *
0x18000551a  call    W32timeConfigInfoToString
0x18000551f  mov     rcx, cs:qword_1800A42F0
0x180005526  mov     eax, [rcx+0ECh]
0x18000552c  lea     r9, aUtilizessltime_0; "UtilizeSslTimeData"
0x180005533  mov     edx, 80h; unsigned __int64
0x180005538  cmp     eax, 5
0x18000553b  jnb     loc_1800057DB
0x180005541  mov     rax, [rbx+rax*8]
0x180005545  mov     [rsp+1F8h+var_1D0], rax
0x18000554a  lea     r8, aSDS; "%s: %d (%s)\n"
0x180005551  mov     eax, [rcx+0E8h]
0x180005557  mov     dword ptr [rsp+1F8h+var_1D8], eax
0x18000555b  lea     rcx, [rsp+1F8h+var_138]; unsigned __int16 *
0x180005563  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180005568  test    eax, eax
0x18000556a  js      loc_18000580F
0x180005570  mov     [rsp+1F8h+var_1C0], r12
0x180005575  lea     r8, [rsp+1F8h+var_1C0]
0x18000557a  mov     rax, rsi
0x18000557d  mov     [rsp+1F8h+var_188], rax
0x180005582  mov     rcx, r14
0x180005585  mov     [rsp+1F8h+var_190], rcx
0x18000558a  mov     edx, r12d
0x18000558d  nop     dword ptr [rax]
0x180005590  test    rax, rax
0x180005593  jz      short loc_1800055AD
0x180005595  cmp     [rcx], dx
0x180005598  jz      short loc_1800055AD
0x18000559a  add     rcx, 2
0x18000559e  mov     [rsp+1F8h+var_190], rcx
0x1800055a3  dec     rax
0x1800055a6  mov     [rsp+1F8h+var_188], rax
0x1800055ab  jmp     short loc_180005590
0x1800055ad  mov     edi, 80070057h
0x1800055b2  test    rax, rax
0x1800055b5  cmovz   edx, edi
0x1800055b8  test    edx, edx
0x1800055ba  js      loc_180005807
0x1800055c0  mov     rcx, rsi
0x1800055c3  sub     rcx, rax
0x1800055c6  mov     [r8], rcx
0x1800055c9  mov     ebx, 7FFFFFFEh
0x1800055ce  test    edx, edx
0x1800055d0  js      loc_18000566B
0x1800055d6  mov     edx, ebx
0x1800055d8  mov     [rsp+1F8h+var_170], rbx
0x1800055e0  lea     r8, [rsp+1F8h+var_138]
0x1800055e8  mov     [rsp+1F8h+var_180], r8
0x1800055ed  mov     rcx, rsi
0x1800055f0  mov     rax, [rsp+1F8h+var_1C0]
0x1800055f5  sub     rcx, rax
0x1800055f8  mov     [rsp+1F8h+var_178], rcx
0x180005600  lea     r9, [r14+rax*2]
0x180005604  mov     [rsp+1F8h+var_1B8], r9
0x180005609  mov     r10, r12
0x18000560c  mov     [rsp+1F8h+var_1B0], r12
0x180005611  test    rcx, rcx
0x180005614  jz      loc_1800057B2
0x18000561a  test    rdx, rdx
0x18000561d  jz      short loc_18000565E
0x18000561f  movzx   eax, word ptr [r8]
0x180005623  test    ax, ax
0x180005626  jz      short loc_18000565E
0x180005628  add     r8, 2
0x18000562c  mov     [rsp+1F8h+var_180], r8
0x180005631  mov     [r9], ax
0x180005635  add     r9, 2
0x180005639  mov     [rsp+1F8h+var_1B8], r9
0x18000563e  dec     rcx
0x180005641  mov     [rsp+1F8h+var_178], rcx
0x180005649  dec     rdx
0x18000564c  mov     [rsp+1F8h+var_170], rdx
0x180005654  inc     r10
0x180005657  mov     [rsp+1F8h+var_1B0], r10
0x18000565c  jmp     short loc_180005611
0x18000565e  test    rcx, rcx
0x180005661  jz      loc_1800057B2
0x180005667  mov     [r9], r12w
0x18000566b  mov     rax, cs:qword_1800A4738
0x180005672  mov     dword ptr [rsp+1F8h+var_1D0], eax
0x180005676  mov     eax, cs:dword_1800A4720
0x18000567c  mov     dword ptr [rsp+1F8h+var_1D8], eax; __int64
0x180005680  mov     r9d, cs:dword_1800A4710
0x180005687  lea     r8, aLeapSecondsEna; "\n[Leap Seconds]\nEnabled: %d (Local)\n"...
0x18000568e  mov     edx, 80h; unsigned __int64
0x180005693  lea     rcx, [rsp+1F8h+var_138]; unsigned __int16 *
0x18000569b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800056a0  test    eax, eax
0x1800056a2  js      loc_1800057A3
0x1800056a8  mov     [rsp+1F8h+var_1A8], r12
0x1800056ad  lea     r8, [rsp+1F8h+var_1A8]
0x1800056b2  mov     rcx, rsi
0x1800056b5  mov     [rsp+1F8h+var_160], rcx
0x1800056bd  mov     rax, r14
0x1800056c0  mov     [rsp+1F8h+var_168], rax
0x1800056c8  mov     edx, r12d
0x1800056cb  nop     dword ptr [rax+rax+00h]
0x1800056d0  test    rcx, rcx
0x1800056d3  jz      short loc_1800056F6
0x1800056d5  cmp     [rax], dx
0x1800056d8  jz      short loc_1800056F3
0x1800056da  add     rax, 2
0x1800056de  mov     [rsp+1F8h+var_168], rax
0x1800056e6  dec     rcx
0x1800056e9  mov     [rsp+1F8h+var_160], rcx
0x1800056f1  jmp     short loc_1800056D0
0x1800056f3  test    rcx, rcx
0x1800056f6  cmovz   edx, edi
0x1800056f9  test    edx, edx
0x1800056fb  js      loc_18000581E
0x180005701  mov     rax, rsi
0x180005704  sub     rax, rcx
0x180005707  mov     [r8], rax
0x18000570a  test    edx, edx
0x18000570c  js      loc_1800057A3
0x180005712  mov     [rsp+1F8h+var_148], rbx
0x18000571a  lea     rdx, [rsp+1F8h+var_138]
0x180005722  mov     [rsp+1F8h+var_158], rdx
0x18000572a  mov     rax, [rsp+1F8h+var_1A8]
0x18000572f  sub     rsi, rax
0x180005732  mov     [rsp+1F8h+var_150], rsi
0x18000573a  lea     rcx, [r14+rax*2]
0x18000573e  mov     [rsp+1F8h+var_1A0], rcx
0x180005743  mov     r8, r12
0x180005746  mov     [rsp+1F8h+var_198], r12
0x18000574b  nop     dword ptr [rax+rax+00h]
0x180005750  test    rsi, rsi
0x180005753  jz      short loc_1800057C8
0x180005755  test    rbx, rbx
0x180005758  jz      short loc_18000579A
0x18000575a  movzx   eax, word ptr [rdx]
0x18000575d  test    ax, ax
0x180005760  jz      short loc_18000579A
0x180005762  add     rdx, 2
0x180005766  mov     [rsp+1F8h+var_158], rdx
0x18000576e  mov     [rcx], ax
0x180005771  add     rcx, 2
0x180005775  mov     [rsp+1F8h+var_1A0], rcx
0x18000577a  dec     rsi
0x18000577d  mov     [rsp+1F8h+var_150], rsi
0x180005785  dec     rbx
0x180005788  mov     [rsp+1F8h+var_148], rbx
0x180005790  inc     r8
0x180005793  mov     [rsp+1F8h+var_198], r8
0x180005798  jmp     short loc_180005750
0x18000579a  test    rsi, rsi
0x18000579d  jz      short loc_1800057C8
0x18000579f  mov     [rcx], r12w
0x1800057a3  mov     r8, [rsp+1F8h+hMem]
0x1800057a8  mov     rcx, r15; unsigned __int16 *
0x1800057ab  call    W32timeConfigProviderInfoToString
0x1800057b0  jmp     short loc_180005826
0x1800057b2  sub     r9, 2
0x1800057b6  mov     [rsp+1F8h+var_1B8], r9
0x1800057bb  dec     r10
0x1800057be  mov     [rsp+1F8h+var_1B0], r10
0x1800057c3  jmp     loc_180005667
0x1800057c8  sub     rcx, 2
0x1800057cc  mov     [rsp+1F8h+var_1A0], rcx
0x1800057d1  dec     r8
0x1800057d4  mov     [rsp+1F8h+var_198], r8
0x1800057d9  jmp     short loc_18000579F
0x1800057db  mov     dword ptr [rsp+1F8h+var_1D0], eax
0x1800057df  lea     r8, aSDD; "%s: %d (%d)\n"
0x1800057e6  jmp     loc_180005551
0x1800057eb  mov     ecx, 40h ; '@'
0x1800057f0  call    FileLogAllowEntry
0x1800057f5  test    al, al
0x1800057f7  jz      short loc_180005826
0x1800057f9  lea     rcx, aFailedToGather_0; "Failed to gather service configuration "...
0x180005800  call    FileLogAdd
0x180005805  jmp     short loc_180005826
0x180005807  mov     [r8], r12
0x18000580a  jmp     loc_1800055C9
0x18000580f  mov     edi, 80070057h
0x180005814  mov     ebx, 7FFFFFFEh
0x180005819  jmp     loc_18000566B
0x18000581e  mov     [r8], r12
0x180005821  jmp     loc_18000570A
0x180005826  mov     rdx, [rsp+1F8h+hMem]
0x18000582b  test    rdx, rdx
0x18000582e  jz      loc_1800058D6
0x180005834  mov     rcx, [rdx+0A0h]; hMem
0x18000583b  test    rcx, rcx
0x18000583e  jnz     loc_1800058FF
0x180005844  mov     rcx, [rdx+98h]; hMem
0x18000584b  test    rcx, rcx
0x18000584e  jz      short loc_180005861
0x180005850  call    cs:__imp_LocalFree
0x180005857  nop     dword ptr [rax+rax+00h]
0x18000585c  mov     rdx, [rsp+1F8h+hMem]
0x180005861  cmp     qword ptr [rdx+0C8h], 0
0x180005869  jz      short loc_1800058BB
0x18000586b  mov     ebx, r12d
0x18000586e  cmp     [rdx+0C0h], ebx
0x180005874  jbe     short loc_1800058A3
0x180005876  mov     ecx, ebx
0x180005878  mov     rax, [rdx+0C8h]
0x18000587f  mov     rcx, [rax+rcx*8]; hMem
0x180005883  test    rcx, rcx
0x180005886  jz      short loc_180005899
0x180005888  call    cs:__imp_LocalFree
0x18000588f  nop     dword ptr [rax+rax+00h]
0x180005894  mov     rdx, [rsp+1F8h+hMem]
0x180005899  inc     ebx
0x18000589b  cmp     ebx, [rdx+0C0h]
0x1800058a1  jb      short loc_180005876
0x1800058a3  mov     rcx, [rdx+0C8h]; hMem
0x1800058aa  call    cs:__imp_LocalFree
0x1800058b1  nop     dword ptr [rax+rax+00h]
0x1800058b6  mov     rdx, [rsp+1F8h+hMem]
0x1800058bb  mov     rcx, [rdx+0D8h]; hMem
0x1800058c2  test    rcx, rcx
0x1800058c5  jnz     short loc_180005915
0x1800058c7  mov     rcx, rdx; hMem
0x1800058ca  call    cs:__imp_LocalFree
0x1800058d1  nop     dword ptr [rax+rax+00h]
0x1800058d6  mov     rcx, [rsp+1F8h+var_38]
0x1800058de  xor     rcx, rsp; StackCookie
0x1800058e1  call    __security_check_cookie
0x1800058e6  mov     rbx, [rsp+1F8h+arg_8]
0x1800058ee  add     rsp, 1D0h
0x1800058f5  pop     r15
0x1800058f7  pop     r14
0x1800058f9  pop     r12
0x1800058fb  pop     rdi
0x1800058fc  pop     rsi
0x1800058fd  retn
0x1800058ff  call    cs:__imp_LocalFree
0x180005906  nop     dword ptr [rax+rax+00h]
0x18000590b  mov     rdx, [rsp+1F8h+hMem]
0x180005910  jmp     loc_180005844
0x180005915  call    cs:__imp_LocalFree
0x18000591c  nop     dword ptr [rax+rax+00h]
0x180005921  mov     rdx, [rsp+1F8h+hMem]
0x180005926  jmp     short loc_1800058C7
0x180064030  push    rbx
0x180064032  push    rbp
0x180064033  sub     rsp, 38h
0x180064037  mov     rbp, rdx
0x18006403a  mov     rdx, [rbp+30h]
0x18006403e  test    rdx, rdx
0x180064041  jz      loc_180064111
0x180064047  cmp     qword ptr [rdx+0A0h], 0
0x18006404f  jz      short loc_180064068
0x180064051  mov     rcx, [rdx+0A0h]; hMem
0x180064058  call    cs:__imp_LocalFree
0x18006405f  nop     dword ptr [rax+rax+00h]
0x180064064  mov     rdx, [rbp+30h]
0x180064068  cmp     qword ptr [rdx+98h], 0
0x180064070  jz      short loc_180064089
0x180064072  mov     rcx, [rdx+98h]; hMem
0x180064079  call    cs:__imp_LocalFree
0x180064080  nop     dword ptr [rax+rax+00h]
0x180064085  mov     rdx, [rbp+30h]
0x180064089  cmp     qword ptr [rdx+0C8h], 0
0x180064091  jz      short loc_1800640E0
0x180064093  xor     ebx, ebx
0x180064095  cmp     [rdx+0C0h], ebx
0x18006409b  jbe     short loc_1800640C9
0x18006409d  mov     rax, [rdx+0C8h]
0x1800640a4  cmp     qword ptr [rax+rbx*8], 0
0x1800640a9  jz      short loc_1800640BF
0x1800640ab  mov     rcx, [rax+rbx*8]; hMem
0x1800640af  call    cs:__imp_LocalFree
  ... truncated ...
```
