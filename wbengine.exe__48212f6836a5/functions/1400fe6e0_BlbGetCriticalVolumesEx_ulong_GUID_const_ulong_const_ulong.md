# BlbGetCriticalVolumesEx(ulong *,_GUID const * *,ulong const * *,ulong)

- ea: `0x1400fe6e0`
- end: `0x1400fea93`
- name: `?BlbGetCriticalVolumesEx@@YAJPEAKPEAPEBU_GUID@@PEAPEBKK@Z`
- size: `947`
- prototype: `__int64 __fastcall(unsigned int *, const struct _GUID **, const unsigned int **, unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x14002ae80`

## callees

- `0x140007ad3`
- `0x14000bb24`
- `0x14000bb4c`
- `0x14003c69c`
- `0x140088aa0`
- `0x14008b940`
- `0x14009026c`
- `0x1400fe6e0`
- `0x140137010`

## import_xrefs

- `KERNEL32!GetSystemTimeAsFileTime` at `0x1400fe875`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1400fe89e`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1400fe875`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1400fe89e`
- `ole32!CoTaskMemAlloc` at `0x1400fe779`
- `ole32!CoTaskMemAlloc` at `0x1400fe787`
- `ole32!CoTaskMemAlloc` at `0x1400fe925`
- `ole32!CoTaskMemAlloc` at `0x1400fe935`
- `ole32!CoTaskMemAlloc` at `0x1400fe779`
- `ole32!CoTaskMemAlloc` at `0x1400fe787`
- `ole32!CoTaskMemAlloc` at `0x1400fe925`
- `ole32!CoTaskMemAlloc` at `0x1400fe935`
- `ole32!CoTaskMemFree` at `0x1400fe9ea`
- `ole32!CoTaskMemFree` at `0x1400fe9f8`
- `ole32!CoTaskMemFree` at `0x1400fe9ea`
- `ole32!CoTaskMemFree` at `0x1400fe9f8`
- `ole32!CoCreateInstance` at `0x1400fe7ff`
- `ole32!CoCreateInstance` at `0x1400fe7ff`

## pseudocode

```c
__int64 __fastcall BlbGetCriticalVolumesEx(
        unsigned int *a1,
        struct _GUID **a2,
        const unsigned int **a3,
        unsigned int a4)
{
  unsigned int v4; // r15d
  HRESULT IsEnvironmentWinPE; // ebx
  struct _GUID *v8; // rdi
  _QWORD *v9; // rax
  _DWORD *v10; // rsi
  unsigned int v11; // r14d
  unsigned int v12; // eax
  PVOID *v13; // rcx
  __int64 v14; // rdx
  _DWORD *v15; // rax
  unsigned __int16 *v16; // rcx
  __int64 v17; // rdx
  unsigned __int16 **v19; // [rsp+30h] [rbp-20h] BYREF
  LPVOID ppv; // [rsp+38h] [rbp-18h] BYREF
  struct _FILETIME v21; // [rsp+40h] [rbp-10h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+48h] [rbp-8h] BYREF
  unsigned int v24; // [rsp+A8h] [rbp+58h] BYREF

  v24 = a4;
  v4 = 0;
  ppv = 0;
  v19 = 0;
  SystemTimeAsFileTime = 0;
  v21 = 0;
  LOBYTE(v24) = 0;
  IsEnvironmentWinPE = BlbutilIsEnvironmentWinPE((unsigned __int8 *)&v24);
  if ( IsEnvironmentWinPE < 0 )
    goto LABEL_46;
  if ( !(_BYTE)v24 )
  {
    v24 = 0;
    IsEnvironmentWinPE = CoCreateInstance(&CLSID_SPP, 0, 1u, &IID_ISharedProtectionPoints, &ppv);
    if ( IsEnvironmentWinPE >= 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, WPP_ac926ebcd8713fa3b2309f2035630ff8_Traceguids);
      }
      GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
      IsEnvironmentWinPE = (*(__int64 (__fastcall **)(LPVOID, __int64, unsigned int *, unsigned __int16 ***))(*(_QWORD *)ppv + 136LL))(
                             ppv,
                             1,
                             &v24,
                             &v19);
      GetSystemTimeAsFileTime(&v21);
      if ( IsEnvironmentWinPE >= 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_q(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            43,
            WPP_ac926ebcd8713fa3b2309f2035630ff8_Traceguids,
            (*(_QWORD *)&v21 - *(_QWORD *)&SystemTimeAsFileTime) / 0x2710uLL);
        }
        v8 = (struct _GUID *)CoTaskMemAlloc(16LL * v24);
        v15 = CoTaskMemAlloc(4LL * v24);
        v10 = v15;
        if ( v8 && v15 )
        {
          memset_0(v8, 0, 16LL * v24);
          memset_0(v10, 0, 4LL * v24);
          v11 = 0;
          while ( v4 < v24 )
          {
            v16 = v19[v4];
            if ( v16 )
            {
              v17 = -1;
              do
                ++v17;
              while ( v16[v17] );
              IsEnvironmentWinPE = BlbutilQueryVolumeId(v16, v17, &v8[v11]);
              if ( IsEnvironmentWinPE < 0 )
                goto LABEL_43;
              ++v11;
            }
            ++v4;
          }
          goto LABEL_39;
        }
        goto LABEL_41;
      }
      v13 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_47;
      }
      v14 = 42;
    }
    else
    {
      v13 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_47;
      }
      v14 = 40;
    }
    WPP_SF_d(v13[2], v14, WPP_ac926ebcd8713fa3b2309f2035630ff8_Traceguids);
LABEL_46:
    v13 = (PVOID *)WPP_GLOBAL_Control;
LABEL_47:
    v11 = 0;
    goto LABEL_48;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, WPP_ac926ebcd8713fa3b2309f2035630ff8_Traceguids);
  }
  v8 = (struct _GUID *)CoTaskMemAlloc(0x20u);
  v9 = CoTaskMemAlloc(8u);
  v10 = v9;
  if ( !v8 || !v9 )
  {
LABEL_41:
    IsEnvironmentWinPE = -2147024882;
    if ( v8 )
LABEL_43:
      CoTaskMemFree(v8);
    if ( v10 )
      CoTaskMemFree(v10);
    goto LABEL_46;
  }
  *v8 = 0;
  v11 = 2;
  v8[1] = 0;
  *v9 = 0;
  v12 = g_dwSystemVolumeFlags;
  *v8 = g_guidBootVolumeId;
  *v10 = 0;
  v8[1] = g_guidSystemVolumeId;
  v10[1] = v12;
LABEL_39:
  *a1 = v11;
  *a2 = v8;
  *a3 = v10;
  v13 = (PVOID *)WPP_GLOBAL_Control;
LABEL_48:
  if ( v19 )
  {
    v24 = v11;
    BlbutilFreeStrings(&v19, &v24);
    v13 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( ppv )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    v13 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( IsEnvironmentWinPE < 0
    && v13 != &WPP_GLOBAL_Control
    && (*((_BYTE *)v13 + 28) & 1) != 0
    && *((_BYTE *)v13 + 25) >= 2u )
  {
    WPP_SF_d(v13[2], 44, WPP_ac926ebcd8713fa3b2309f2035630ff8_Traceguids);
  }
  return (unsigned int)IsEnvironmentWinPE;
}

```

## disassembly

```asm
0x1400fe6e0  mov     [rsp-38h+arg_8], rbx
0x1400fe6e5  mov     [rsp-38h+arg_18], r9d
0x1400fe6ea  mov     [rsp-38h+arg_0], rcx
0x1400fe6ef  push    rbp
0x1400fe6f0  push    rsi
0x1400fe6f1  push    rdi
0x1400fe6f2  push    r12
0x1400fe6f4  push    r13
0x1400fe6f6  push    r14
0x1400fe6f8  push    r15
0x1400fe6fa  mov     rbp, rsp
0x1400fe6fd  sub     rsp, 50h
0x1400fe701  xor     r15d, r15d
0x1400fe704  lea     rcx, [rbp+arg_18]; unsigned __int8 *
0x1400fe708  mov     [rbp+var_18], r15
0x1400fe70c  mov     r12, r8
0x1400fe70f  mov     [rbp+var_20], r15
0x1400fe713  mov     r13, rdx
0x1400fe716  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], r15
0x1400fe71a  mov     qword ptr [rbp+var_10.dwLowDateTime], r15
0x1400fe71e  mov     byte ptr [rbp+arg_18], r15b
0x1400fe722  call    ?BlbutilIsEnvironmentWinPE@@YAJPEAE@Z; BlbutilIsEnvironmentWinPE(uchar *)
0x1400fe727  lea     rsi, WPP_GLOBAL_Control
0x1400fe72e  mov     ebx, eax
0x1400fe730  lea     edi, [r15+1]
0x1400fe734  lea     r14, WPP_ac926ebcd8713fa3b2309f2035630ff8_Traceguids
0x1400fe73b  test    eax, eax
0x1400fe73d  js      loc_1400FE9FE
0x1400fe743  cmp     byte ptr [rbp+arg_18], r15b
0x1400fe747  jz      loc_1400FE7DF
0x1400fe74d  mov     rcx, cs:WPP_GLOBAL_Control
0x1400fe754  cmp     rcx, rsi
0x1400fe757  jz      short loc_1400FE774
0x1400fe759  test    [rcx+1Ch], dil
0x1400fe75d  jz      short loc_1400FE774
0x1400fe75f  cmp     byte ptr [rcx+19h], 4
0x1400fe763  jb      short loc_1400FE774
0x1400fe765  mov     rcx, [rcx+10h]
0x1400fe769  lea     edx, [rdi+26h]
0x1400fe76c  mov     r8, r14
0x1400fe76f  call    WPP_SF_
0x1400fe774  mov     ecx, 20h ; ' '; cb
0x1400fe779  call    cs:__imp_CoTaskMemAlloc
0x1400fe77f  mov     ecx, 8; cb
0x1400fe784  mov     rdi, rax
0x1400fe787  call    cs:__imp_CoTaskMemAlloc
0x1400fe78d  mov     rsi, rax
0x1400fe790  test    rdi, rdi
0x1400fe793  jz      loc_1400FE9D8
0x1400fe799  test    rax, rax
0x1400fe79c  jz      loc_1400FE9D8
0x1400fe7a2  xorps   xmm0, xmm0
0x1400fe7a5  xor     eax, eax
0x1400fe7a7  movups  xmmword ptr [rdi], xmm0
0x1400fe7aa  mov     r14d, 2
0x1400fe7b0  movups  xmmword ptr [rdi+10h], xmm0
0x1400fe7b4  mov     [rsi], rax
0x1400fe7b7  movups  xmm0, xmmword ptr cs:?g_guidBootVolumeId@@3U_GUID@@A.Data1; _GUID g_guidBootVolumeId ...
0x1400fe7be  mov     eax, cs:?g_dwSystemVolumeFlags@@3KA; ulong g_dwSystemVolumeFlags
0x1400fe7c4  movdqu  xmmword ptr [rdi], xmm0
0x1400fe7c8  mov     [rsi], r15d
0x1400fe7cb  movups  xmm1, xmmword ptr cs:?g_guidSystemVolumeId@@3U_GUID@@A.Data1; _GUID g_guidSystemVolumeId ...
0x1400fe7d2  movdqu  xmmword ptr [rdi+10h], xmm1
0x1400fe7d7  mov     [rsi+4], eax
0x1400fe7da  jmp     loc_1400FE9BC
0x1400fe7df  lea     rax, [rbp+var_18]
0x1400fe7e3  mov     [rbp+arg_18], r15d
0x1400fe7e7  lea     r9, IID_ISharedProtectionPoints; riid
0x1400fe7ee  mov     [rsp+50h+ppv], rax; ppv
0x1400fe7f3  mov     r8d, edi; dwClsContext
0x1400fe7f6  lea     rcx, CLSID_SPP; rclsid
0x1400fe7fd  xor     edx, edx; pUnkOuter
0x1400fe7ff  call    cs:__imp_CoCreateInstance
0x1400fe805  mov     ebx, eax
0x1400fe807  test    eax, eax
0x1400fe809  jns     short loc_1400FE848
0x1400fe80b  mov     rcx, cs:WPP_GLOBAL_Control
0x1400fe812  cmp     rcx, rsi
0x1400fe815  jz      loc_1400FEA05
0x1400fe81b  test    [rcx+1Ch], dil
0x1400fe81f  jz      loc_1400FEA05
0x1400fe825  cmp     byte ptr [rcx+19h], 2
0x1400fe829  jb      loc_1400FEA05
0x1400fe82f  mov     edx, 28h ; '('
0x1400fe834  mov     r9d, eax
0x1400fe837  mov     rcx, [rcx+10h]
0x1400fe83b  mov     r8, r14
0x1400fe83e  call    WPP_SF_d
0x1400fe843  jmp     loc_1400FE9FE
0x1400fe848  mov     rcx, cs:WPP_GLOBAL_Control
0x1400fe84f  cmp     rcx, rsi
0x1400fe852  jz      short loc_1400FE871
0x1400fe854  test    [rcx+1Ch], dil
0x1400fe858  jz      short loc_1400FE871
0x1400fe85a  cmp     byte ptr [rcx+19h], 4
0x1400fe85e  jb      short loc_1400FE871
0x1400fe860  mov     rcx, [rcx+10h]
0x1400fe864  mov     edx, 29h ; ')'
0x1400fe869  mov     r8, r14
0x1400fe86c  call    WPP_SF_
0x1400fe871  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1400fe875  call    cs:__imp_GetSystemTimeAsFileTime
0x1400fe87b  mov     rcx, [rbp+var_18]
0x1400fe87f  lea     r9, [rbp+var_20]
0x1400fe883  lea     r8, [rbp+arg_18]
0x1400fe887  mov     edx, edi
0x1400fe889  mov     rax, [rcx]
0x1400fe88c  mov     rax, [rax+88h]
0x1400fe893  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400fe898  lea     rcx, [rbp+var_10]; lpSystemTimeAsFileTime
0x1400fe89c  mov     ebx, eax
0x1400fe89e  call    cs:__imp_GetSystemTimeAsFileTime
0x1400fe8a4  test    ebx, ebx
0x1400fe8a6  jns     short loc_1400FE8D9
0x1400fe8a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400fe8af  cmp     rcx, rsi
0x1400fe8b2  jz      loc_1400FEA05
0x1400fe8b8  test    [rcx+1Ch], dil
0x1400fe8bc  jz      loc_1400FEA05
0x1400fe8c2  cmp     byte ptr [rcx+19h], 2
0x1400fe8c6  jb      loc_1400FEA05
0x1400fe8cc  mov     edx, 2Ah ; '*'
0x1400fe8d1  mov     r9d, ebx
0x1400fe8d4  jmp     loc_1400FE837
0x1400fe8d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400fe8e0  cmp     rcx, rsi
0x1400fe8e3  jz      short loc_1400FE91E
0x1400fe8e5  test    [rcx+1Ch], dil
0x1400fe8e9  jz      short loc_1400FE91E
0x1400fe8eb  cmp     byte ptr [rcx+19h], 4
0x1400fe8ef  jb      short loc_1400FE91E
0x1400fe8f1  mov     rdx, qword ptr [rbp+var_10.dwLowDateTime]
0x1400fe8f5  mov     rax, 346DC5D63886594Bh
0x1400fe8ff  sub     rdx, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1400fe903  mov     r8, r14
0x1400fe906  mov     rcx, [rcx+10h]
0x1400fe90a  mul     rdx
0x1400fe90d  mov     r9, rdx
0x1400fe910  mov     edx, 2Bh ; '+'
0x1400fe915  shr     r9, 0Bh
0x1400fe919  call    WPP_SF_q
0x1400fe91e  mov     ecx, [rbp+arg_18]
0x1400fe921  shl     rcx, 4; cb
0x1400fe925  call    cs:__imp_CoTaskMemAlloc
0x1400fe92b  mov     ecx, [rbp+arg_18]
0x1400fe92e  mov     rdi, rax
0x1400fe931  shl     rcx, 2; cb
0x1400fe935  call    cs:__imp_CoTaskMemAlloc
0x1400fe93b  mov     rsi, rax
0x1400fe93e  test    rdi, rdi
0x1400fe941  jz      loc_1400FE9D8
0x1400fe947  test    rax, rax
0x1400fe94a  jz      loc_1400FE9D8
0x1400fe950  mov     r8d, [rbp+arg_18]
0x1400fe954  xor     edx, edx; Val
0x1400fe956  shl     r8, 4; Size
0x1400fe95a  mov     rcx, rdi; void *
0x1400fe95d  call    memset_0
0x1400fe962  mov     r8d, [rbp+arg_18]
0x1400fe966  xor     edx, edx; Val
0x1400fe968  shl     r8, 2; Size
0x1400fe96c  mov     rcx, rsi; void *
0x1400fe96f  call    memset_0
0x1400fe974  mov     r14d, r15d
0x1400fe977  cmp     r15d, [rbp+arg_18]
0x1400fe97b  jnb     short loc_1400FE9B9
0x1400fe97d  mov     rax, [rbp+var_20]
0x1400fe981  mov     ecx, r15d
0x1400fe984  mov     rcx, [rax+rcx*8]; unsigned __int16 *
0x1400fe988  xor     eax, eax
0x1400fe98a  test    rcx, rcx
0x1400fe98d  jz      short loc_1400FE9B4
0x1400fe98f  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1400fe993  inc     rdx; unsigned int
0x1400fe996  cmp     [rcx+rdx*2], ax
0x1400fe99a  jnz     short loc_1400FE993
0x1400fe99c  mov     r8d, r14d
0x1400fe99f  shl     r8, 4
0x1400fe9a3  add     r8, rdi; struct _GUID *
0x1400fe9a6  call    ?BlbutilQueryVolumeId@@YAJPEAGKPEAU_GUID@@@Z; BlbutilQueryVolumeId(ushort *,ulong,_GUID *)
0x1400fe9ab  mov     ebx, eax
0x1400fe9ad  test    eax, eax
0x1400fe9af  js      short loc_1400FE9E4
0x1400fe9b1  inc     r14d
0x1400fe9b4  inc     r15d
0x1400fe9b7  jmp     short loc_1400FE977
0x1400fe9b9  xor     r15d, r15d
0x1400fe9bc  mov     rax, [rbp+arg_0]
0x1400fe9c0  mov     [rax], r14d
0x1400fe9c3  mov     [r13+0], rdi
0x1400fe9c7  mov     [r12], rsi
0x1400fe9cb  test    ebx, ebx
0x1400fe9cd  js      short loc_1400FE9DD
0x1400fe9cf  mov     rcx, cs:WPP_GLOBAL_Control
0x1400fe9d6  jmp     short loc_1400FEA08
0x1400fe9d8  mov     ebx, 8007000Eh
0x1400fe9dd  test    rdi, rdi
0x1400fe9e0  jz      short loc_1400FE9F0
0x1400fe9e2  jmp     short loc_1400FE9E7
0x1400fe9e4  xor     r15d, r15d
0x1400fe9e7  mov     rcx, rdi; pv
0x1400fe9ea  call    cs:__imp_CoTaskMemFree
0x1400fe9f0  test    rsi, rsi
0x1400fe9f3  jz      short loc_1400FE9FE
0x1400fe9f5  mov     rcx, rsi; pv
0x1400fe9f8  call    cs:__imp_CoTaskMemFree
0x1400fe9fe  mov     rcx, cs:WPP_GLOBAL_Control
0x1400fea05  mov     r14d, r15d
0x1400fea08  cmp     [rbp+var_20], r15
0x1400fea0c  jz      short loc_1400FEA26
0x1400fea0e  lea     rdx, [rbp+arg_18]; unsigned int *
0x1400fea12  mov     [rbp+arg_18], r14d
0x1400fea16  lea     rcx, [rbp+var_20]; unsigned __int16 ***
0x1400fea1a  call    ?BlbutilFreeStrings@@YAXAEAPEAPEAGAEAK@Z; BlbutilFreeStrings(ushort * * &,ulong &)
0x1400fea1f  mov     rcx, cs:WPP_GLOBAL_Control
0x1400fea26  mov     rdx, [rbp+var_18]
0x1400fea2a  test    rdx, rdx
0x1400fea2d  jz      short loc_1400FEA45
0x1400fea2f  mov     rax, [rdx]
0x1400fea32  mov     rcx, rdx
0x1400fea35  mov     rax, [rax+10h]
0x1400fea39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400fea3e  mov     rcx, cs:WPP_GLOBAL_Control
0x1400fea45  test    ebx, ebx
0x1400fea47  jns     short loc_1400FEA79
0x1400fea49  lea     rax, WPP_GLOBAL_Control
0x1400fea50  cmp     rcx, rax
0x1400fea53  jz      short loc_1400FEA79
0x1400fea55  test    byte ptr [rcx+1Ch], 1
0x1400fea59  jz      short loc_1400FEA79
0x1400fea5b  cmp     byte ptr [rcx+19h], 2
0x1400fea5f  jb      short loc_1400FEA79
0x1400fea61  mov     rcx, [rcx+10h]
0x1400fea65  lea     r8, WPP_ac926ebcd8713fa3b2309f2035630ff8_Traceguids
0x1400fea6c  mov     edx, 2Ch ; ','
0x1400fea71  mov     r9d, ebx
0x1400fea74  call    WPP_SF_d
0x1400fea79  mov     eax, ebx
0x1400fea7b  mov     rbx, [rsp+50h+arg_8]
0x1400fea83  add     rsp, 50h
0x1400fea87  pop     r15
0x1400fea89  pop     r14
0x1400fea8b  pop     r13
0x1400fea8d  pop     r12
0x1400fea8f  pop     rdi
0x1400fea90  pop     rsi
0x1400fea91  pop     rbp
0x1400fea92  retn
```
