# BlbGetCriticalVolumes(ulong *,_GUID const * *,ulong const * *,uchar)

- ea: `0x1400fe15c`
- end: `0x1400fe6da`
- name: `?BlbGetCriticalVolumes@@YAJPEAKPEAPEBU_GUID@@PEAPEBKE@Z`
- size: `1406`
- prototype: `__int64 __fastcall(unsigned int *, const struct _GUID **, const unsigned int **, unsigned __int8)`
- caller_count: `3`
- callee_count: `9`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x140013a10`
- `0x1400fdb78`
- `0x1400fdd50`

## callees

- `0x140007ad3`
- `0x14000bb24`
- `0x14000bb4c`
- `0x14003c69c`
- `0x140088aa0`
- `0x14008b940`
- `0x14009026c`
- `0x1400fe15c`
- `0x140137010`

## import_xrefs

- `KERNEL32!GetSystemTimeAsFileTime` at `0x1400fe41e`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1400fe447`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1400fe41e`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1400fe447`
- `ole32!CoTaskMemAlloc` at `0x1400fe2e2`
- `ole32!CoTaskMemAlloc` at `0x1400fe2f9`
- `ole32!CoTaskMemAlloc` at `0x1400fe4ce`
- `ole32!CoTaskMemAlloc` at `0x1400fe4e2`
- `ole32!CoTaskMemAlloc` at `0x1400fe2e2`
- `ole32!CoTaskMemAlloc` at `0x1400fe2f9`
- `ole32!CoTaskMemAlloc` at `0x1400fe4ce`
- `ole32!CoTaskMemAlloc` at `0x1400fe4e2`
- `ole32!CoTaskMemFree` at `0x1400fe1e4`
- `ole32!CoTaskMemFree` at `0x1400fe20a`
- `ole32!CoTaskMemFree` at `0x1400fe60f`
- `ole32!CoTaskMemFree` at `0x1400fe62b`
- `ole32!CoTaskMemFree` at `0x1400fe1e4`
- `ole32!CoTaskMemFree` at `0x1400fe20a`
- `ole32!CoTaskMemFree` at `0x1400fe60f`
- `ole32!CoTaskMemFree` at `0x1400fe62b`
- `ole32!CoCreateInstance` at `0x1400fe39e`
- `ole32!CoCreateInstance` at `0x1400fe39e`

## pseudocode

```c
__int64 __fastcall BlbGetCriticalVolumes(unsigned int *a1, struct _GUID **a2, const unsigned int **a3, char a4)
{
  PVOID *v6; // rcx
  struct _GUID *v7; // rdi
  __int64 v8; // r14
  HRESULT IsEnvironmentWinPE; // esi
  _DWORD *v10; // rax
  _DWORD *v11; // r15
  unsigned int v12; // eax
  __int64 v13; // rdx
  void *v14; // rax
  void *v15; // rbx
  unsigned int i; // ebx
  unsigned __int16 *v17; // rcx
  __int64 v18; // rdx
  unsigned __int16 **v20; // [rsp+30h] [rbp-20h] BYREF
  LPVOID ppv; // [rsp+38h] [rbp-18h] BYREF
  struct _FILETIME v22; // [rsp+40h] [rbp-10h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+48h] [rbp-8h] BYREF
  unsigned int v25; // [rsp+A8h] [rbp+58h] BYREF

  ppv = 0;
  v20 = 0;
  SystemTimeAsFileTime = 0;
  v22 = 0;
  if ( a4 )
  {
    v6 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_ac926ebcd8713fa3b2309f2035630ff8_Traceguids);
      v6 = (PVOID *)WPP_GLOBAL_Control;
    }
    v7 = (struct _GUID *)pv;
    if ( pv )
    {
      CoTaskMemFree(pv);
      v6 = (PVOID *)WPP_GLOBAL_Control;
      v7 = 0;
      pv = 0;
    }
    if ( qword_1401607B0 )
    {
      CoTaskMemFree(qword_1401607B0);
      v6 = (PVOID *)WPP_GLOBAL_Control;
      v7 = (struct _GUID *)pv;
      qword_1401607B0 = 0;
    }
    LODWORD(v8) = 0;
    dword_1401607A8 = 0;
  }
  else
  {
    v6 = (PVOID *)WPP_GLOBAL_Control;
    v7 = (struct _GUID *)pv;
    LODWORD(v8) = dword_1401607A8;
  }
  if ( v7 )
  {
    IsEnvironmentWinPE = 0;
    if ( v6 == &WPP_GLOBAL_Control || (*((_DWORD *)v6 + 7) & 0x200) == 0 || *((_BYTE *)v6 + 25) < 4u )
      goto LABEL_66;
    WPP_SF_(v6[2], 37, WPP_ac926ebcd8713fa3b2309f2035630ff8_Traceguids);
    v7 = (struct _GUID *)pv;
    LODWORD(v8) = dword_1401607A8;
LABEL_65:
    v6 = (PVOID *)WPP_GLOBAL_Control;
LABEL_66:
    *a2 = v7;
    *a1 = v8;
    *a3 = (const unsigned int *)qword_1401607B0;
    goto LABEL_72;
  }
  if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 1) != 0 && *((_BYTE *)v6 + 25) >= 4u )
    WPP_SF_(v6[2], 31, WPP_ac926ebcd8713fa3b2309f2035630ff8_Traceguids);
  LOBYTE(v25) = 0;
  IsEnvironmentWinPE = BlbutilIsEnvironmentWinPE((unsigned __int8 *)&v25);
  if ( IsEnvironmentWinPE < 0 )
    goto LABEL_33;
  if ( !(_BYTE)v25 )
  {
    v25 = 0;
    IsEnvironmentWinPE = CoCreateInstance(&CLSID_SPP, 0, 1u, &IID_ISharedProtectionPoints, &ppv);
    if ( IsEnvironmentWinPE >= 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, WPP_ac926ebcd8713fa3b2309f2035630ff8_Traceguids);
      }
      GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
      IsEnvironmentWinPE = (*(__int64 (__fastcall **)(LPVOID, _QWORD, unsigned int *, unsigned __int16 ***))(*(_QWORD *)ppv + 136LL))(
                             ppv,
                             0,
                             &v25,
                             &v20);
      GetSystemTimeAsFileTime(&v22);
      if ( IsEnvironmentWinPE >= 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_q(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            36,
            WPP_ac926ebcd8713fa3b2309f2035630ff8_Traceguids,
            (*(_QWORD *)&v22 - *(_QWORD *)&SystemTimeAsFileTime) / 0x2710uLL);
        }
        pv = CoTaskMemAlloc(16LL * v25);
        v14 = CoTaskMemAlloc(4LL * v25);
        v7 = (struct _GUID *)pv;
        qword_1401607B0 = v14;
        v15 = v14;
        if ( pv && v14 )
        {
          memset_0(pv, 0, 16LL * v25);
          memset_0(v15, 0, 4LL * v25);
          LODWORD(v8) = 0;
          dword_1401607A8 = 0;
          for ( i = 0; i < v25; ++i )
          {
            v17 = v20[i];
            if ( v17 )
            {
              v18 = -1;
              do
                ++v18;
              while ( v17[v18] );
              IsEnvironmentWinPE = BlbutilQueryVolumeId(v17, v18, &v7[(unsigned int)v8]);
              if ( IsEnvironmentWinPE < 0 )
                goto LABEL_33;
              v7 = (struct _GUID *)pv;
              LODWORD(v8) = ++dword_1401607A8;
            }
          }
          goto LABEL_65;
        }
        v6 = (PVOID *)WPP_GLOBAL_Control;
        IsEnvironmentWinPE = -2147024882;
        goto LABEL_67;
      }
      v6 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
LABEL_34:
        v7 = (struct _GUID *)pv;
        goto LABEL_67;
      }
      v13 = 35;
    }
    else
    {
      v6 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_34;
      }
      v13 = 33;
    }
    WPP_SF_d(v6[2], v13, WPP_ac926ebcd8713fa3b2309f2035630ff8_Traceguids);
LABEL_33:
    v6 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_34;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, WPP_ac926ebcd8713fa3b2309f2035630ff8_Traceguids);
  }
  dword_1401607A8 = 2;
  pv = CoTaskMemAlloc(0x20u);
  v10 = CoTaskMemAlloc(4LL * (unsigned int)dword_1401607A8);
  v7 = (struct _GUID *)pv;
  v11 = v10;
  qword_1401607B0 = v10;
  if ( pv && v10 )
  {
    v8 = (unsigned int)dword_1401607A8;
    memset_0(pv, 0, 16LL * (unsigned int)dword_1401607A8);
    memset_0(v11, 0, 4 * v8);
    v12 = g_dwSystemVolumeFlags;
    *v7 = g_guidBootVolumeId;
    *v11 = 0;
    v7[1] = g_guidSystemVolumeId;
    v11[1] = v12;
    goto LABEL_65;
  }
  v6 = (PVOID *)WPP_GLOBAL_Control;
  IsEnvironmentWinPE = -2147024882;
LABEL_67:
  if ( v7 )
  {
    CoTaskMemFree(v7);
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( qword_1401607B0 )
  {
    CoTaskMemFree(qword_1401607B0);
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
  pv = 0;
  LODWORD(v8) = 0;
  qword_1401607B0 = 0;
  dword_1401607A8 = 0;
LABEL_72:
  if ( v20 )
  {
    v25 = v8;
    BlbutilFreeStrings(&v20, &v25);
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( ppv )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( IsEnvironmentWinPE < 0
    && v6 != &WPP_GLOBAL_Control
    && (*((_BYTE *)v6 + 28) & 1) != 0
    && *((_BYTE *)v6 + 25) >= 2u )
  {
    WPP_SF_d(v6[2], 38, WPP_ac926ebcd8713fa3b2309f2035630ff8_Traceguids);
  }
  return (unsigned int)IsEnvironmentWinPE;
}

```

## disassembly

```asm
0x1400fe15c  mov     [rsp-38h+arg_8], rbx
0x1400fe161  mov     [rsp-38h+arg_0], rcx
0x1400fe166  push    rbp
0x1400fe167  push    rsi
0x1400fe168  push    rdi
0x1400fe169  push    r12
0x1400fe16b  push    r13
0x1400fe16d  push    r14
0x1400fe16f  push    r15
0x1400fe171  mov     rbp, rsp
0x1400fe174  sub     rsp, 50h
0x1400fe178  xor     ebx, ebx
0x1400fe17a  lea     rax, WPP_GLOBAL_Control
0x1400fe181  mov     [rbp+var_18], rbx
0x1400fe185  mov     r12, r8
0x1400fe188  mov     [rbp+var_20], rbx
0x1400fe18c  mov     r13, rdx
0x1400fe18f  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rbx
0x1400fe193  mov     r15b, 4
0x1400fe196  mov     qword ptr [rbp+var_10.dwLowDateTime], rbx
0x1400fe19a  test    r9b, r9b
0x1400fe19d  jz      loc_1400FE23A
0x1400fe1a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400fe1aa  cmp     rcx, rax
0x1400fe1ad  jz      short loc_1400FE1D5
0x1400fe1af  test    byte ptr [rcx+1Ch], 1
0x1400fe1b3  jz      short loc_1400FE1D5
0x1400fe1b5  cmp     [rcx+19h], r15b
0x1400fe1b9  jb      short loc_1400FE1D5
0x1400fe1bb  mov     rcx, [rcx+10h]
0x1400fe1bf  lea     edx, [rbx+1Eh]
0x1400fe1c2  lea     r8, WPP_ac926ebcd8713fa3b2309f2035630ff8_Traceguids
0x1400fe1c9  call    WPP_SF_
0x1400fe1ce  mov     rcx, cs:WPP_GLOBAL_Control
0x1400fe1d5  mov     rdi, cs:pv
0x1400fe1dc  test    rdi, rdi
0x1400fe1df  jz      short loc_1400FE1FB
0x1400fe1e1  mov     rcx, rdi; pv
0x1400fe1e4  call    cs:__imp_CoTaskMemFree
0x1400fe1ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1400fe1f1  mov     rdi, rbx
0x1400fe1f4  mov     cs:pv, rbx
0x1400fe1fb  mov     r15, cs:qword_1401607B0
0x1400fe202  test    r15, r15
0x1400fe205  jz      short loc_1400FE225
0x1400fe207  mov     rcx, r15; pv
0x1400fe20a  call    cs:__imp_CoTaskMemFree
0x1400fe210  mov     rcx, cs:WPP_GLOBAL_Control
0x1400fe217  mov     rdi, cs:pv
0x1400fe21e  mov     cs:qword_1401607B0, rbx
0x1400fe225  mov     r14d, ebx
0x1400fe228  mov     cs:dword_1401607A8, ebx
0x1400fe22e  mov     r15b, 4
0x1400fe231  lea     rax, WPP_GLOBAL_Control
0x1400fe238  jmp     short loc_1400FE24F
0x1400fe23a  mov     rcx, cs:WPP_GLOBAL_Control
0x1400fe241  mov     rdi, cs:pv
0x1400fe248  mov     r14d, cs:dword_1401607A8
0x1400fe24f  test    rdi, rdi
0x1400fe252  jnz     loc_1400FE5AD
0x1400fe258  lea     rdi, WPP_GLOBAL_Control
0x1400fe25f  cmp     rcx, rdi
0x1400fe262  jz      short loc_1400FE285
0x1400fe264  test    byte ptr [rcx+1Ch], 1
0x1400fe268  jz      short loc_1400FE285
0x1400fe26a  cmp     [rcx+19h], r15b
0x1400fe26e  jb      short loc_1400FE285
0x1400fe270  mov     rcx, [rcx+10h]
0x1400fe274  lea     r8, WPP_ac926ebcd8713fa3b2309f2035630ff8_Traceguids
0x1400fe27b  mov     edx, 1Fh
0x1400fe280  call    WPP_SF_
0x1400fe285  lea     rcx, [rbp+arg_18]; unsigned __int8 *
0x1400fe289  mov     byte ptr [rbp+arg_18], bl
0x1400fe28c  call    ?BlbutilIsEnvironmentWinPE@@YAJPEAE@Z; BlbutilIsEnvironmentWinPE(uchar *)
0x1400fe291  mov     esi, eax
0x1400fe293  test    eax, eax
0x1400fe295  js      loc_1400FE3DA
0x1400fe29b  cmp     byte ptr [rbp+arg_18], bl
0x1400fe29e  jz      loc_1400FE37E
0x1400fe2a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400fe2ab  mov     r14d, 20h ; ' '
0x1400fe2b1  cmp     rcx, rdi
0x1400fe2b4  jz      short loc_1400FE2D5
0x1400fe2b6  test    byte ptr [rcx+1Ch], 1
0x1400fe2ba  jz      short loc_1400FE2D5
0x1400fe2bc  cmp     [rcx+19h], r15b
0x1400fe2c0  jb      short loc_1400FE2D5
0x1400fe2c2  mov     rcx, [rcx+10h]
0x1400fe2c6  lea     r8, WPP_ac926ebcd8713fa3b2309f2035630ff8_Traceguids
0x1400fe2cd  mov     edx, r14d
0x1400fe2d0  call    WPP_SF_
0x1400fe2d5  mov     rcx, r14; cb
0x1400fe2d8  mov     cs:dword_1401607A8, 2
0x1400fe2e2  call    cs:__imp_CoTaskMemAlloc
0x1400fe2e8  mov     ecx, cs:dword_1401607A8
0x1400fe2ee  shl     rcx, 2; cb
0x1400fe2f2  mov     cs:pv, rax
0x1400fe2f9  call    cs:__imp_CoTaskMemAlloc
0x1400fe2ff  mov     rdi, cs:pv
0x1400fe306  mov     r15, rax
0x1400fe309  mov     cs:qword_1401607B0, rax
0x1400fe310  test    rdi, rdi
0x1400fe313  jz      short loc_1400FE36D
0x1400fe315  test    rax, rax
0x1400fe318  jz      short loc_1400FE36D
0x1400fe31a  mov     r14d, cs:dword_1401607A8
0x1400fe321  xor     edx, edx; Val
0x1400fe323  mov     r8d, r14d
0x1400fe326  mov     rcx, rdi; void *
0x1400fe329  shl     r8, 4; Size
0x1400fe32d  call    memset_0
0x1400fe332  lea     r8, ds:0[r14*4]; Size
0x1400fe33a  xor     edx, edx; Val
0x1400fe33c  mov     rcx, r15; void *
0x1400fe33f  call    memset_0
0x1400fe344  movups  xmm0, xmmword ptr cs:?g_guidBootVolumeId@@3U_GUID@@A.Data1; _GUID g_guidBootVolumeId ...
0x1400fe34b  mov     eax, cs:?g_dwSystemVolumeFlags@@3KA; ulong g_dwSystemVolumeFlags
0x1400fe351  movdqu  xmmword ptr [rdi], xmm0
0x1400fe355  mov     [r15], ebx
0x1400fe358  movups  xmm1, xmmword ptr cs:?g_guidSystemVolumeId@@3U_GUID@@A.Data1; _GUID g_guidSystemVolumeId ...
0x1400fe35f  movdqu  xmmword ptr [rdi+10h], xmm1
0x1400fe364  mov     [r15+4], eax
0x1400fe368  jmp     loc_1400FE5E6
0x1400fe36d  mov     rcx, cs:WPP_GLOBAL_Control
0x1400fe374  mov     esi, 8007000Eh
0x1400fe379  jmp     loc_1400FE607
0x1400fe37e  xor     edx, edx; pUnkOuter
0x1400fe380  mov     [rbp+arg_18], ebx
0x1400fe383  lea     rax, [rbp+var_18]
0x1400fe387  lea     r9, IID_ISharedProtectionPoints; riid
0x1400fe38e  mov     [rsp+50h+ppv], rax; ppv
0x1400fe393  lea     rcx, CLSID_SPP; rclsid
0x1400fe39a  lea     r8d, [rdx+1]; dwClsContext
0x1400fe39e  call    cs:__imp_CoCreateInstance
0x1400fe3a4  mov     esi, eax
0x1400fe3a6  test    eax, eax
0x1400fe3a8  jns     short loc_1400FE3ED
0x1400fe3aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1400fe3b1  cmp     rcx, rdi
0x1400fe3b4  jz      short loc_1400FE3E1
0x1400fe3b6  test    byte ptr [rcx+1Ch], 1
0x1400fe3ba  jz      short loc_1400FE3E1
0x1400fe3bc  cmp     byte ptr [rcx+19h], 2
0x1400fe3c0  jb      short loc_1400FE3E1
0x1400fe3c2  mov     edx, 21h ; '!'
0x1400fe3c7  mov     r9d, eax
0x1400fe3ca  mov     rcx, [rcx+10h]
0x1400fe3ce  lea     r8, WPP_ac926ebcd8713fa3b2309f2035630ff8_Traceguids
0x1400fe3d5  call    WPP_SF_d
0x1400fe3da  mov     rcx, cs:WPP_GLOBAL_Control
0x1400fe3e1  mov     rdi, cs:pv
0x1400fe3e8  jmp     loc_1400FE607
0x1400fe3ed  mov     rcx, cs:WPP_GLOBAL_Control
0x1400fe3f4  cmp     rcx, rdi
0x1400fe3f7  jz      short loc_1400FE41A
0x1400fe3f9  test    byte ptr [rcx+1Ch], 1
0x1400fe3fd  jz      short loc_1400FE41A
0x1400fe3ff  cmp     [rcx+19h], r15b
0x1400fe403  jb      short loc_1400FE41A
0x1400fe405  mov     rcx, [rcx+10h]
0x1400fe409  lea     r8, WPP_ac926ebcd8713fa3b2309f2035630ff8_Traceguids
0x1400fe410  mov     edx, 22h ; '"'
0x1400fe415  call    WPP_SF_
0x1400fe41a  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1400fe41e  call    cs:__imp_GetSystemTimeAsFileTime
0x1400fe424  mov     rcx, [rbp+var_18]
0x1400fe428  lea     r9, [rbp+var_20]
0x1400fe42c  lea     r8, [rbp+arg_18]
0x1400fe430  xor     edx, edx
0x1400fe432  mov     rax, [rcx]
0x1400fe435  mov     rax, [rax+88h]
0x1400fe43c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400fe441  lea     rcx, [rbp+var_10]; lpSystemTimeAsFileTime
0x1400fe445  mov     esi, eax
0x1400fe447  call    cs:__imp_GetSystemTimeAsFileTime
0x1400fe44d  test    esi, esi
0x1400fe44f  jns     short loc_1400FE47E
0x1400fe451  mov     rcx, cs:WPP_GLOBAL_Control
0x1400fe458  cmp     rcx, rdi
0x1400fe45b  jz      short loc_1400FE3E1
0x1400fe45d  test    byte ptr [rcx+1Ch], 1
0x1400fe461  jz      loc_1400FE3E1
0x1400fe467  cmp     byte ptr [rcx+19h], 2
0x1400fe46b  jb      loc_1400FE3E1
0x1400fe471  mov     edx, 23h ; '#'
0x1400fe476  mov     r9d, esi
0x1400fe479  jmp     loc_1400FE3CA
0x1400fe47e  mov     rcx, cs:WPP_GLOBAL_Control
0x1400fe485  cmp     rcx, rdi
0x1400fe488  jz      short loc_1400FE4C7
0x1400fe48a  test    byte ptr [rcx+1Ch], 1
0x1400fe48e  jz      short loc_1400FE4C7
0x1400fe490  cmp     [rcx+19h], r15b
0x1400fe494  jb      short loc_1400FE4C7
0x1400fe496  mov     rdx, qword ptr [rbp+var_10.dwLowDateTime]
0x1400fe49a  lea     r8, WPP_ac926ebcd8713fa3b2309f2035630ff8_Traceguids
0x1400fe4a1  sub     rdx, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1400fe4a5  mov     rax, 346DC5D63886594Bh
0x1400fe4af  mov     rcx, [rcx+10h]
0x1400fe4b3  mul     rdx
0x1400fe4b6  mov     r9, rdx
0x1400fe4b9  mov     edx, 24h ; '$'
0x1400fe4be  shr     r9, 0Bh
0x1400fe4c2  call    WPP_SF_q
0x1400fe4c7  mov     ecx, [rbp+arg_18]
0x1400fe4ca  shl     rcx, 4; cb
0x1400fe4ce  call    cs:__imp_CoTaskMemAlloc
0x1400fe4d4  mov     ecx, [rbp+arg_18]
0x1400fe4d7  shl     rcx, 2; cb
0x1400fe4db  mov     cs:pv, rax
0x1400fe4e2  call    cs:__imp_CoTaskMemAlloc
0x1400fe4e8  mov     rdi, cs:pv
0x1400fe4ef  xor     r15d, r15d
0x1400fe4f2  mov     cs:qword_1401607B0, rax
0x1400fe4f9  mov     rbx, rax
0x1400fe4fc  test    rdi, rdi
0x1400fe4ff  jz      loc_1400FE596
0x1400fe505  test    rax, rax
0x1400fe508  jz      loc_1400FE596
0x1400fe50e  mov     r8d, [rbp+arg_18]
0x1400fe512  xor     edx, edx; Val
0x1400fe514  shl     r8, 4; Size
0x1400fe518  mov     rcx, rdi; void *
0x1400fe51b  call    memset_0
0x1400fe520  mov     r8d, [rbp+arg_18]
0x1400fe524  xor     edx, edx; Val
0x1400fe526  shl     r8, 2; Size
0x1400fe52a  mov     rcx, rbx; void *
0x1400fe52d  call    memset_0
0x1400fe532  mov     r14d, r15d
0x1400fe535  mov     cs:dword_1401607A8, r15d
0x1400fe53c  mov     ebx, r15d
0x1400fe53f  cmp     ebx, [rbp+arg_18]
0x1400fe542  jnb     short loc_1400FE592
0x1400fe544  mov     rax, [rbp+var_20]
0x1400fe548  mov     ecx, ebx
0x1400fe54a  mov     rcx, [rax+rcx*8]; unsigned __int16 *
0x1400fe54e  test    rcx, rcx
0x1400fe551  jz      short loc_1400FE58E
0x1400fe553  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1400fe557  inc     rdx; unsigned int
0x1400fe55a  cmp     [rcx+rdx*2], r15w
0x1400fe55f  jnz     short loc_1400FE557
0x1400fe561  mov     r8d, r14d
0x1400fe564  shl     r8, 4
0x1400fe568  add     r8, rdi; struct _GUID *
0x1400fe56b  call    ?BlbutilQueryVolumeId@@YAJPEAGKPEAU_GUID@@@Z; BlbutilQueryVolumeId(ushort *,ulong,_GUID *)
0x1400fe570  mov     esi, eax
0x1400fe572  test    eax, eax
0x1400fe574  js      short loc_1400FE5A6
0x1400fe576  mov     r14d, cs:dword_1401607A8
0x1400fe57d  mov     rdi, cs:pv
0x1400fe584  inc     r14d
0x1400fe587  mov     cs:dword_1401607A8, r14d
0x1400fe58e  inc     ebx
0x1400fe590  jmp     short loc_1400FE53F
0x1400fe592  xor     ebx, ebx
0x1400fe594  jmp     short loc_1400FE5E6
0x1400fe596  mov     rcx, cs:WPP_GLOBAL_Control
0x1400fe59d  mov     esi, 8007000Eh
0x1400fe5a2  xor     ebx, ebx
0x1400fe5a4  jmp     short loc_1400FE607
0x1400fe5a6  xor     ebx, ebx
0x1400fe5a8  jmp     loc_1400FE3DA
0x1400fe5ad  mov     esi, ebx
0x1400fe5af  cmp     rcx, rax
0x1400fe5b2  jz      short loc_1400FE5ED
0x1400fe5b4  test    dword ptr [rcx+1Ch], 200h
0x1400fe5bb  jz      short loc_1400FE5ED
0x1400fe5bd  cmp     [rcx+19h], r15b
0x1400fe5c1  jb      short loc_1400FE5ED
0x1400fe5c3  mov     rcx, [rcx+10h]
0x1400fe5c7  lea     r8, WPP_ac926ebcd8713fa3b2309f2035630ff8_Traceguids
0x1400fe5ce  mov     edx, 25h ; '%'
0x1400fe5d3  call    WPP_SF_
0x1400fe5d8  mov     rdi, cs:pv
0x1400fe5df  mov     r14d, cs:dword_1401607A8
0x1400fe5e6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400fe5ed  mov     rax, [rbp+arg_0]
0x1400fe5f1  mov     [r13+0], rdi
0x1400fe5f5  mov     [rax], r14d
0x1400fe5f8  mov     rax, cs:qword_1401607B0
0x1400fe5ff  mov     [r12], rax
0x1400fe603  test    esi, esi
0x1400fe605  jns     short loc_1400FE64F
0x1400fe607  test    rdi, rdi
0x1400fe60a  jz      short loc_1400FE61C
0x1400fe60c  mov     rcx, rdi; pv
0x1400fe60f  call    cs:__imp_CoTaskMemFree
0x1400fe615  mov     rcx, cs:WPP_GLOBAL_Control
0x1400fe61c  mov     r15, cs:qword_1401607B0
0x1400fe623  test    r15, r15
0x1400fe626  jz      short loc_1400FE638
0x1400fe628  mov     rcx, r15; pv
0x1400fe62b  call    cs:__imp_CoTaskMemFree
0x1400fe631  mov     rcx, cs:WPP_GLOBAL_Control
0x1400fe638  mov     cs:pv, rbx
0x1400fe63f  mov     r14d, ebx
0x1400fe642  mov     cs:qword_1401607B0, rbx
0x1400fe649  mov     cs:dword_1401607A8, ebx
  ... truncated ...
```
