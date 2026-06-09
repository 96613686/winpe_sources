# WapGenerateHttpRequestExtraHeaders

- ea: `0x180006290`
- end: `0x1800067cf`
- name: `WapGenerateHttpRequestExtraHeaders`
- size: `1343`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000a268`
- `0x18000a598`

## callees

- `0x1800027d8`
- `0x180003fb0`
- `0x180005c50`
- `0x1800061e4`
- `0x180006290`
- `0x1800067d8`
- `0x1800068a0`
- `0x18000ed38`
- `0x1800391c0`
- `0x18006aea0`
- `0x18006deb8`
- `0x1800722f0`
- `0x180098010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000665f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000665f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000644a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180006529`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000644a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180006529`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180006496`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000653f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180006496`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000653f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800064a5`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800064a5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800064ed`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000651a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800064ed`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000651a`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180006769`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180006769`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006569`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006569`
- `ntdll!RtlCompareUnicodeStrings` at `0x180006475`
- `ntdll!RtlCompareUnicodeStrings` at `0x1800064d0`
- `ntdll!RtlCompareUnicodeStrings` at `0x1800065fb`
- `ntdll!RtlCompareUnicodeStrings` at `0x180006475`
- `ntdll!RtlCompareUnicodeStrings` at `0x1800064d0`
- `ntdll!RtlCompareUnicodeStrings` at `0x1800065fb`

## pseudocode

```c
__int64 __fastcall WapGenerateHttpRequestExtraHeaders(__int64 a1, _OWORD *a2)
{
  __int64 v2; // r14
  _OWORD *v3; // r13
  unsigned __int64 v5; // rdi
  __int64 v6; // rsi
  int v7; // r9d
  unsigned __int64 v8; // rbx
  unsigned int v9; // eax
  unsigned __int64 v10; // rsi
  unsigned __int64 v11; // rdx
  char v12; // r15
  __int64 v13; // r13
  _WORD *v14; // rdi
  _WORD *v15; // r12
  _WORD *v16; // rcx
  char v17; // r8
  unsigned int i; // edx
  __int64 v19; // rax
  RTL_SRWLOCK *v20; // rbx
  RTL_SRWLOCK *v21; // r15
  RTL_SRWLOCK *j; // rdi
  RTL_SRWLOCK *v23; // r14
  __int64 v24; // rcx
  RTL_SRWLOCK *k; // rdi
  void *v26; // r14
  void *v27; // rdi
  int TransformedComponentW; // ebx
  void *v29; // rsi
  __int64 Heap; // rax
  int v32; // r9d
  RTL_SRWLOCK *v33; // r13
  RTL_SRWLOCK *Ptr; // r14
  RTL_SRWLOCK *v35; // rax
  RTL_SRWLOCK *v36; // rsi
  const FILETIME *v37; // r13
  char IsCookieMatch; // dl
  bool v39; // sf
  int v40; // [rsp+20h] [rbp-79h]
  char v41[8]; // [rsp+30h] [rbp-69h] BYREF
  unsigned __int64 v42; // [rsp+38h] [rbp-61h] BYREF
  _WORD *v43; // [rsp+40h] [rbp-59h] BYREF
  void *v44; // [rsp+48h] [rbp-51h]
  _OWORD *v45; // [rsp+50h] [rbp-49h]
  RTL_SRWLOCK *v46; // [rsp+58h] [rbp-41h] BYREF
  unsigned __int64 v47; // [rsp+60h] [rbp-39h] BYREF
  __int64 v48; // [rsp+68h] [rbp-31h]
  _QWORD v49[2]; // [rsp+70h] [rbp-29h] BYREF
  __int64 v50; // [rsp+80h] [rbp-19h]
  int v51; // [rsp+88h] [rbp-11h]
  int v52; // [rsp+8Ch] [rbp-Dh]
  __int128 v53; // [rsp+90h] [rbp-9h] BYREF
  __int128 v54; // [rsp+A0h] [rbp+7h]
  struct _FILETIME SystemTimeAsFileTime; // [rsp+B0h] [rbp+17h] BYREF

  v45 = a2;
  *a2 = 0;
  v2 = 0;
  v3 = a2;
  a2[1] = 0;
  a2[2] = 0;
  if ( !*(_BYTE *)(a1 + 4472) )
    WapGenerateHttpRequestAuthHeaders();
  if ( *(_DWORD *)(a1 + 324) != 3 && !*(_BYTE *)(a1 + 4545) )
  {
    v5 = *(_QWORD *)(*(_QWORD *)(a1 + 72) + 48LL);
    v47 = v5;
    if ( v5 )
    {
      v6 = *(_QWORD *)(a1 + 328);
      v48 = v6;
      v49[1] = 0;
      v50 = 0;
      v52 = 0;
      v53 = 0;
      v54 = 0;
      if ( (unsigned __int8)WaIsValidCookieUri(v6) )
      {
        v49[0] = 0;
        v50 = v6;
        v51 = 32;
        v43 = 0;
        v42 = 0;
        if ( !(unsigned int)WapUriGetTransformedComponentW(v6, 3, 335544324, v7, (__int64)&v43, (__int64)&v42) )
        {
          v8 = v42;
          if ( v42 )
          {
            v9 = *(_DWORD *)(v6 + 64) - 1;
            v44 = 0;
            if ( v9 <= 1 )
            {
              v15 = v43;
              v10 = v42;
            }
            else
            {
              v10 = 0;
              v11 = 0;
              v12 = 0;
              v13 = 2;
              v14 = &v43[v42];
              while ( 1 )
              {
                v15 = v14;
                if ( v10 >= v8 )
                  break;
                v16 = v14--;
                if ( *v14 == 46 )
                {
                  if ( ++v2 == 1 )
                  {
                    if ( v11 > 2
                      || v11 == 2 && (LOBYTE(v40) = 1, !(unsigned int)RtlCompareUnicodeStrings(v16, 2, L"tv", 2, v40)) )
                    {
                      v12 = 1;
                    }
                  }
                  else if ( !v12 )
                  {
                    v12 = 1;
                    if ( (unsigned __int8)WapSecondLevelDomainIsTld(v16, v11) )
                      v13 = 3;
                  }
                  if ( v2 == v13 )
                    break;
                  v11 = 0;
                }
                else
                {
                  ++v11;
                }
                ++v10;
              }
              v3 = v45;
              v5 = v47;
            }
            v17 = 0;
            for ( i = 0; i < 2 * v10; v17 = *((_BYTE *)v15 + v19) + 29 * v17 )
              v19 = i++;
            v20 = (RTL_SRWLOCK *)(v5 + 32LL * (v17 & 0x7F) + 8);
            v21 = v20 + 3;
            while ( 2 )
            {
              AcquireSRWLockShared(v20 + 3);
              for ( j = (RTL_SRWLOCK *)v20->Ptr; ; j = (RTL_SRWLOCK *)j->Ptr )
              {
                if ( j == v20 )
                  goto LABEL_28;
                v23 = j - 1;
                LOBYTE(v40) = 1;
                if ( !(unsigned int)RtlCompareUnicodeStrings(j[2].Ptr, j[3].Ptr, v15, v10, v40) )
                  break;
              }
              if ( j == (RTL_SRWLOCK *)8 )
              {
LABEL_28:
                ReleaseSRWLockShared(v20 + 3);
                AcquireSRWLockExclusive(v20 + 3);
                for ( k = (RTL_SRWLOCK *)v20->Ptr; ; k = (RTL_SRWLOCK *)k->Ptr )
                {
                  if ( k == v20 )
                    goto LABEL_34;
                  LOBYTE(v40) = 1;
                  if ( !(unsigned int)RtlCompareUnicodeStrings(k[2].Ptr, k[3].Ptr, v15, v10, v40) )
                    break;
                }
                if ( k != (RTL_SRWLOCK *)8 )
                {
LABEL_33:
                  ReleaseSRWLockExclusive(v20 + 3);
                  continue;
                }
LABEL_34:
                v26 = 0;
                if ( WapCreateCookieLocationHead(v20, v15, v10) )
                  goto LABEL_33;
                v27 = 0;
                ReleaseSRWLockExclusive(v20 + 3);
                AcquireSRWLockShared(v20 + 3);
                TransformedComponentW = 8;
LABEL_36:
                v29 = v26;
LABEL_37:
                ReleaseSRWLockShared(v21);
                if ( v27 )
                {
                  if ( g_fWxHeapExtensionInitialized )
                    g_WxHeapExtensionInterfaces(v27);
                  else
                    HeapFree(g_hWxProcessHeap, 0, v27);
                }
                if ( !TransformedComponentW )
                {
                  *((_QWORD *)v3 + 4) = v26;
                  *((_QWORD *)v3 + 5) = v29;
                }
                return 0;
              }
              break;
            }
            v29 = 0;
            *((_QWORD *)&v53 + 1) = 5120;
            *(_QWORD *)&v54 = 0;
            DWORD2(v54) = 0;
            Heap = WxAllocateHeapEx(v24, 5120);
            v27 = (void *)Heap;
            if ( Heap )
            {
              *(_QWORD *)&v53 = Heap;
              SystemTimeAsFileTime = 0;
              v47 = 0;
              v41[0] = 0;
              GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
              v46 = 0;
              v43 = 0;
              TransformedComponentW = WapUriGetTransformedComponentW(
                                        v48,
                                        5,
                                        1107427600,
                                        v32,
                                        (__int64)&v46,
                                        (__int64)&v43);
              if ( !TransformedComponentW )
              {
                if ( v43 && LOWORD(v46->Ptr) == 47 )
                {
                  v33 = v23 + 5;
                  Ptr = (RTL_SRWLOCK *)v23[5].Ptr;
                  v46 = v33;
                  if ( Ptr != v33 )
                  {
                    do
                    {
                      TransformedComponentW = WaQueryUriCookiePath(Ptr[2].Ptr, 0, &v47);
                      if ( TransformedComponentW )
                        break;
                      if ( v47 <= (unsigned __int64)v43 )
                      {
                        TransformedComponentW = WapIsCookieUriMatch(v48, Ptr[2].Ptr, v41);
                        if ( TransformedComponentW )
                          break;
                        if ( v41[0] )
                        {
                          v35 = Ptr + 3;
                          v36 = (RTL_SRWLOCK *)Ptr[3].Ptr;
                          while ( v36 != v35 )
                          {
                            v37 = (const FILETIME *)&v36[-1];
                            v36 = (RTL_SRWLOCK *)v36->Ptr;
                            IsCookieMatch = WapIsCookieMatch(v37, v49);
                            if ( (v37[7].dwLowDateTime & 2) != 0 )
                            {
                              v35 = Ptr + 3;
                              if ( **(_DWORD **)(v48 + 56) != 2 )
                                continue;
                            }
                            v35 = Ptr + 3;
                            if ( IsCookieMatch )
                            {
                              v39 = CompareFileTime(v37 + 8, &SystemTimeAsFileTime) < 0;
                              v35 = Ptr + 3;
                              if ( !v39 )
                              {
                                TransformedComponentW = WapCookieCallbackHeader(&v53, v37, &Ptr[-1]);
                                if ( TransformedComponentW )
                                  goto LABEL_67;
                                v35 = Ptr + 3;
                              }
                            }
                          }
                          v33 = v46;
                        }
                      }
                      Ptr = (RTL_SRWLOCK *)Ptr->Ptr;
                    }
                    while ( Ptr != v33 );
LABEL_67:
                    v29 = (void *)v54;
                  }
                  v3 = v45;
                  if ( !TransformedComponentW && v29 )
                  {
                    v26 = v27;
                    v27 = 0;
                    goto LABEL_37;
                  }
                  v26 = v44;
                  goto LABEL_36;
                }
                TransformedComponentW = 13;
              }
            }
            else
            {
              TransformedComponentW = 8;
            }
            v26 = 0;
            goto LABEL_37;
          }
        }
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180006290  mov     [rsp-8+arg_10], rbx
0x180006295  push    rbp
0x180006296  push    rsi
0x180006297  push    rdi
0x180006298  push    r12
0x18000629a  push    r13
0x18000629c  push    r14
0x18000629e  push    r15
0x1800062a0  lea     rbp, [rsp-27h]
0x1800062a5  sub     rsp, 0C0h
0x1800062ac  mov     rax, cs:__security_cookie
0x1800062b3  xor     rax, rsp
0x1800062b6  mov     [rbp+57h+var_38], rax
0x1800062ba  xorps   xmm0, xmm0
0x1800062bd  mov     [rbp+57h+var_A0], rdx
0x1800062c1  movups  xmmword ptr [rdx], xmm0
0x1800062c4  xor     r14d, r14d
0x1800062c7  mov     r13, rdx
0x1800062ca  movups  xmmword ptr [rdx+10h], xmm0
0x1800062ce  mov     rbx, rcx
0x1800062d1  movups  xmmword ptr [rdx+20h], xmm0
0x1800062d5  cmp     [rcx+1178h], r14b
0x1800062dc  jnz     short loc_1800062E3
0x1800062de  call    WapGenerateHttpRequestAuthHeaders
0x1800062e3  mov     r15d, 3
0x1800062e9  cmp     [rbx+144h], r15d
0x1800062f0  jz      loc_180006581
0x1800062f6  cmp     [rbx+11C1h], r14b
0x1800062fd  jnz     loc_180006581
0x180006303  mov     rax, [rbx+48h]
0x180006307  mov     rdi, [rax+30h]
0x18000630b  mov     [rbp+57h+var_90], rdi
0x18000630f  test    rdi, rdi
0x180006312  jz      loc_180006581
0x180006318  mov     rsi, [rbx+148h]
0x18000631f  xorps   xmm0, xmm0
0x180006322  mov     rcx, rsi
0x180006325  mov     [rbp+57h+var_88], rsi
0x180006329  mov     [rbp+57h+var_78], r14
0x18000632d  mov     [rbp+57h+var_70], r14
0x180006331  mov     [rbp+57h+var_64], r14d
0x180006335  movups  [rbp+57h+var_60], xmm0
0x180006339  movups  [rbp+57h+var_50], xmm0
0x18000633d  call    WaIsValidCookieUri
0x180006342  test    al, al
0x180006344  jz      loc_180006581
0x18000634a  lea     rax, [rbp+57h+var_B8]
0x18000634e  mov     [rbp+57h+var_80], r14
0x180006352  mov     [rsp+0F0h+var_C8], rax
0x180006357  mov     r8d, 14000004h
0x18000635d  lea     rax, [rbp+57h+var_B0]
0x180006361  mov     [rbp+57h+var_70], rsi
0x180006365  mov     edx, r15d
0x180006368  mov     [rsp+0F0h+var_D0], rax
0x18000636d  mov     rcx, rsi
0x180006370  mov     [rbp+57h+var_68], 20h ; ' '
0x180006377  mov     [rbp+57h+var_B0], r14
0x18000637b  mov     [rbp+57h+var_B8], r14
0x18000637f  call    WapUriGetTransformedComponentW
0x180006384  test    eax, eax
0x180006386  jnz     loc_180006581
0x18000638c  mov     rbx, [rbp+57h+var_B8]
0x180006390  test    rbx, rbx
0x180006393  jz      loc_180006581
0x180006399  mov     eax, [rsi+40h]
0x18000639c  lea     r10d, [r15-1]
0x1800063a0  dec     eax
0x1800063a2  mov     [rbp+57h+var_A8], r14
0x1800063a6  cmp     eax, 1
0x1800063a9  jbe     loc_1800065D7
0x1800063af  mov     rax, [rbp+57h+var_B0]
0x1800063b3  mov     rsi, r14
0x1800063b6  mov     rdx, r14
0x1800063b9  xor     r15b, r15b
0x1800063bc  mov     r13d, r10d
0x1800063bf  lea     rdi, [rax+rbx*2]
0x1800063c3  mov     r12, rdi
0x1800063c6  cmp     rsi, rbx
0x1800063c9  jnb     short loc_180006401
0x1800063cb  mov     rcx, rdi
0x1800063ce  sub     rdi, r10
0x1800063d1  cmp     word ptr [rdi], 2Eh ; '.'
0x1800063d5  jz      short loc_1800063DF
0x1800063d7  inc     rdx
0x1800063da  inc     rsi
0x1800063dd  jmp     short loc_1800063C3
0x1800063df  inc     r14
0x1800063e2  cmp     r14, 1
0x1800063e6  jnz     loc_1800065AB
0x1800063ec  cmp     rdx, r10
0x1800063ef  jbe     loc_1800065E3
0x1800063f5  mov     r15b, 1
0x1800063f8  cmp     r14, r13
0x1800063fb  jnz     loc_1800065CC
0x180006401  mov     r13, [rbp+57h+var_A0]
0x180006405  xor     r14d, r14d
0x180006408  mov     rdi, [rbp+57h+var_90]
0x18000640c  lea     r9, [rsi+rsi]
0x180006410  mov     r8d, r14d
0x180006413  mov     edx, r14d
0x180006416  test    r9, r9
0x180006419  jz      short loc_180006432
0x18000641b  mov     eax, edx
0x18000641d  inc     edx
0x18000641f  imul    r8d, 1Dh
0x180006423  movzx   ecx, byte ptr [rax+r12]
0x180006428  mov     eax, edx
0x18000642a  add     r8d, ecx
0x18000642d  cmp     rax, r9
0x180006430  jb      short loc_18000641B
0x180006432  mov     ebx, r8d
0x180006435  and     ebx, 7Fh
0x180006438  shl     rbx, 5
0x18000643c  add     rbx, 8
0x180006440  add     rbx, rdi
0x180006443  lea     r15, [rbx+18h]
0x180006447  mov     rcx, r15; SRWLock
0x18000644a  call    cs:__imp_AcquireSRWLockShared
0x180006451  nop     dword ptr [rax+rax+00h]
0x180006456  mov     rdi, [rbx]
0x180006459  cmp     rdi, rbx
0x18000645c  jz      short loc_180006493
0x18000645e  lea     r14, [rdi-8]
0x180006462  mov     byte ptr [rsp+0F0h+var_D0], 1
0x180006467  mov     rdx, [r14+20h]
0x18000646b  mov     r9, rsi
0x18000646e  mov     rcx, [r14+18h]
0x180006472  mov     r8, r12
0x180006475  call    cs:__imp_RtlCompareUnicodeStrings
0x18000647c  nop     dword ptr [rax+rax+00h]
0x180006481  test    eax, eax
0x180006483  jz      short loc_18000648A
0x180006485  mov     rdi, [rdi]
0x180006488  jmp     short loc_180006459
0x18000648a  test    r14, r14
0x18000648d  jnz     loc_180006628
0x180006493  mov     rcx, r15; SRWLock
0x180006496  call    cs:__imp_ReleaseSRWLockShared
0x18000649d  nop     dword ptr [rax+rax+00h]
0x1800064a2  mov     rcx, r15; SRWLock
0x1800064a5  call    cs:__imp_AcquireSRWLockExclusive
0x1800064ac  nop     dword ptr [rax+rax+00h]
0x1800064b1  mov     rdi, [rbx]
0x1800064b4  cmp     rdi, rbx
0x1800064b7  jz      short loc_1800064FE
0x1800064b9  lea     r14, [rdi-8]
0x1800064bd  mov     byte ptr [rsp+0F0h+var_D0], 1
0x1800064c2  mov     rdx, [r14+20h]
0x1800064c6  mov     r9, rsi
0x1800064c9  mov     rcx, [r14+18h]
0x1800064cd  mov     r8, r12
0x1800064d0  call    cs:__imp_RtlCompareUnicodeStrings
0x1800064d7  nop     dword ptr [rax+rax+00h]
0x1800064dc  test    eax, eax
0x1800064de  jz      short loc_1800064E5
0x1800064e0  mov     rdi, [rdi]
0x1800064e3  jmp     short loc_1800064B4
0x1800064e5  test    r14, r14
0x1800064e8  jz      short loc_1800064FE
0x1800064ea  mov     rcx, r15; SRWLock
0x1800064ed  call    cs:__imp_ReleaseSRWLockExclusive
0x1800064f4  nop     dword ptr [rax+rax+00h]
0x1800064f9  jmp     loc_180006447
0x1800064fe  mov     r8, rsi
0x180006501  mov     rdx, r12
0x180006504  mov     rcx, rbx
0x180006507  call    WapCreateCookieLocationHead
0x18000650c  xor     r14d, r14d
0x18000650f  test    rax, rax
0x180006512  jnz     short loc_1800064EA
0x180006514  mov     edi, r14d
0x180006517  mov     rcx, r15; SRWLock
0x18000651a  call    cs:__imp_ReleaseSRWLockExclusive
0x180006521  nop     dword ptr [rax+rax+00h]
0x180006526  mov     rcx, r15; SRWLock
0x180006529  call    cs:__imp_AcquireSRWLockShared
0x180006530  nop     dword ptr [rax+rax+00h]
0x180006535  lea     ebx, [r14+8]
0x180006539  mov     rsi, r14
0x18000653c  mov     rcx, r15; SRWLock
0x18000653f  call    cs:__imp_ReleaseSRWLockShared
0x180006546  nop     dword ptr [rax+rax+00h]
0x18000654b  test    rdi, rdi
0x18000654e  jz      short loc_180006575
0x180006550  cmp     cs:?g_fWxHeapExtensionInitialized@@3HA, 0; int g_fWxHeapExtensionInitialized
0x180006557  jnz     loc_180006614
0x18000655d  mov     rcx, cs:g_hWxProcessHeap; hHeap
0x180006564  mov     r8, rdi; lpMem
0x180006567  xor     edx, edx; dwFlags
0x180006569  call    cs:__imp_HeapFree
0x180006570  nop     dword ptr [rax+rax+00h]
0x180006575  test    ebx, ebx
0x180006577  jnz     short loc_180006581
0x180006579  mov     [r13+20h], r14
0x18000657d  mov     [r13+28h], rsi
0x180006581  xor     eax, eax
0x180006583  mov     rcx, [rbp+57h+var_38]
0x180006587  xor     rcx, rsp; StackCookie
0x18000658a  call    __security_check_cookie
0x18000658f  mov     rbx, [rsp+0F0h+arg_10]
0x180006597  add     rsp, 0C0h
0x18000659e  pop     r15
0x1800065a0  pop     r14
0x1800065a2  pop     r13
0x1800065a4  pop     r12
0x1800065a6  pop     rdi
0x1800065a7  pop     rsi
0x1800065a8  pop     rbp
0x1800065a9  retn
0x1800065ab  test    r15b, r15b
0x1800065ae  jnz     loc_1800063F8
0x1800065b4  mov     r15b, 1
0x1800065b7  call    WapSecondLevelDomainIsTld
0x1800065bc  test    al, al
0x1800065be  mov     eax, 3
0x1800065c3  cmovnz  r13, rax
0x1800065c7  jmp     loc_1800063F8
0x1800065cc  xor     edx, edx
0x1800065ce  lea     r10d, [rdx+2]
0x1800065d2  jmp     loc_1800063DA
0x1800065d7  mov     r12, [rbp+57h+var_B0]
0x1800065db  mov     rsi, rbx
0x1800065de  jmp     loc_18000640C
0x1800065e3  jnz     loc_1800063F8
0x1800065e9  mov     r9, r10
0x1800065ec  mov     byte ptr [rsp+0F0h+var_D0], 1
0x1800065f1  lea     r8, aTv; "tv"
0x1800065f8  mov     rdx, r10
0x1800065fb  call    cs:__imp_RtlCompareUnicodeStrings
0x180006602  nop     dword ptr [rax+rax+00h]
0x180006607  test    eax, eax
0x180006609  jz      loc_1800063F5
0x18000660f  jmp     loc_1800063F8
0x180006614  mov     rax, cs:?g_WxHeapExtensionInterfaces@@3U_WX_HEAP_EXTENSION@@A; _WX_HEAP_EXTENSION g_WxHeapExtensionInterfaces
0x18000661b  mov     rcx, rdi
0x18000661e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006623  jmp     loc_180006575
0x180006628  mov     edx, 1400h
0x18000662d  xor     esi, esi
0x18000662f  mov     qword ptr [rbp+57h+var_60+8], rdx
0x180006633  mov     qword ptr [rbp+57h+var_50], rsi
0x180006637  mov     dword ptr [rbp+57h+var_50+8], esi
0x18000663a  call    WxAllocateHeapEx
0x18000663f  mov     rdi, rax
0x180006642  test    rax, rax
0x180006645  jz      loc_1800067AE
0x18000664b  lea     rcx, [rbp+57h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000664f  mov     qword ptr [rbp+57h+var_60], rax
0x180006653  mov     qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime], rsi
0x180006657  mov     [rbp+57h+var_90], rsi
0x18000665b  mov     [rbp+57h+var_C0], sil
0x18000665f  call    cs:__imp_GetSystemTimeAsFileTime
0x180006666  nop     dword ptr [rax+rax+00h]
0x18000666b  mov     rcx, [rbp+57h+var_88]
0x18000666f  lea     rax, [rbp+57h+var_B0]
0x180006673  mov     [rsp+0F0h+var_C8], rax
0x180006678  lea     edx, [rsi+5]
0x18000667b  lea     rax, [rbp+57h+var_98]
0x18000667f  mov     [rbp+57h+var_98], rsi
0x180006683  mov     r8d, 42020110h
0x180006689  mov     [rsp+0F0h+var_D0], rax
0x18000668e  mov     [rbp+57h+var_B0], rsi
0x180006692  call    WapUriGetTransformedComponentW
0x180006697  mov     ebx, eax
0x180006699  test    eax, eax
0x18000669b  jnz     short loc_1800066B2
0x18000669d  cmp     [rbp+57h+var_B0], rsi
0x1800066a1  jz      short loc_1800066AD
0x1800066a3  mov     rax, [rbp+57h+var_98]
0x1800066a7  cmp     word ptr [rax], 2Fh ; '/'
0x1800066ab  jz      short loc_1800066BA
0x1800066ad  mov     ebx, 0Dh
0x1800066b2  mov     r14, rsi
0x1800066b5  jmp     loc_18000653C
0x1800066ba  lea     r13, [r14+28h]
0x1800066be  mov     r14, [r13+0]
0x1800066c2  mov     [rbp+57h+var_98], r13
0x1800066c6  cmp     r14, r13
0x1800066c9  jnz     short loc_1800066EB
0x1800066cb  mov     r13, [rbp+57h+var_A0]
0x1800066cf  test    ebx, ebx
0x1800066d1  jnz     short loc_1800066D8
0x1800066d3  test    rsi, rsi
0x1800066d6  jnz     short loc_1800066E1
0x1800066d8  mov     r14, [rbp+57h+var_A8]
0x1800066dc  jmp     loc_180006539
0x1800066e1  mov     r14, rdi
0x1800066e4  xor     edi, edi
0x1800066e6  jmp     loc_18000653C
0x1800066eb  mov     rcx, [r14+10h]
0x1800066ef  lea     r8, [rbp+57h+var_90]
0x1800066f3  xor     edx, edx
0x1800066f5  call    WaQueryUriCookiePath
0x1800066fa  mov     ebx, eax
0x1800066fc  test    eax, eax
0x1800066fe  jnz     short loc_180006725
0x180006700  mov     rax, [rbp+57h+var_B0]
0x180006704  cmp     [rbp+57h+var_90], rax
0x180006708  ja      loc_18000679D
0x18000670e  mov     rdx, [r14+10h]
  ... truncated ...
```
