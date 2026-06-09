# CSessionArbitrationHelper::Copy(DynArray<long,ulong> &,long * *,ulong *)

- ea: `0x1800ba760`
- end: `0x1800baa12`
- name: `?Copy@CSessionArbitrationHelper@@AEAAJAEAV?$DynArray@JK@@PEAPEAJPEAK@Z`
- size: `690`
- prototype: ``
- caller_count: `4`
- callee_count: `7`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800bc3e0`
- `0x1800bc790`
- `0x1800bcba0`
- `0x1800bcee0`

## callees

- `0x18000a210`
- `0x1800130d8`
- `0x180013150`
- `0x1800321d4`
- `0x1800326dc`
- `0x1800ba760`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_qsort` at `0x1800ba956`
- `api-ms-win-crt-private-l1-1-0!_o_qsort` at `0x1800ba956`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800ba97f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800ba97f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ba9db`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ba9db`

## string_xrefs

- `0x1800ba7cf`: `CSessionArbitrationHelper::Copy`

## pseudocode

```c
__int64 __fastcall CSessionArbitrationHelper::Copy(__int64 a1, __int64 *a2, _QWORD *a3, unsigned int *a4)
{
  _QWORD *v5; // r12
  unsigned int v7; // eax
  unsigned __int64 v8; // rsi
  unsigned int v9; // ebx
  int InstanceOfSessionManager; // eax
  char *v11; // rdi
  unsigned __int64 v12; // rax
  unsigned int i; // ebx
  __int64 v14; // rax
  char *v15; // r14
  unsigned int (__fastcall *v16)(__int64 *, _QWORD, char *); // rax
  unsigned int v17; // ebx
  _DWORD *v18; // rsi
  unsigned int v19; // ebx
  __int64 j; // r14
  __int64 v22; // [rsp+30h] [rbp-28h] BYREF
  __int64 v23; // [rsp+38h] [rbp-20h] BYREF
  __int64 v24[3]; // [rsp+40h] [rbp-18h] BYREF
  char v25; // [rsp+A0h] [rbp+48h]
  __int64 v26; // [rsp+A8h] [rbp+50h] BYREF
  _QWORD *v27; // [rsp+B0h] [rbp+58h]
  struct ISessionManager *v28; // [rsp+B8h] [rbp+60h] BYREF

  v27 = a3;
  *a3 = 0;
  *a4 = 0;
  v5 = a3;
  v7 = (*(__int64 (__fastcall **)(__int64 *))(*a2 + 24))(a2);
  v8 = v7;
  if ( v7 )
  {
    v28 = 0;
    v26 = 0;
    InstanceOfSessionManager = CUtils::GetInstanceOfSessionManager(&v28);
    v9 = InstanceOfSessionManager;
    if ( InstanceOfSessionManager >= 0 )
    {
      v25 = 0;
      if ( (*(int (__fastcall **)(struct ISessionManager *, __int64 *))(*(_QWORD *)v28 + 24LL))(v28, &v26) >= 0 )
      {
        v12 = 16 * v8;
        if ( !is_mul_ok(v8, 0x10u) )
          v12 = -1;
        v11 = (char *)operator new(v12, (const struct std::nothrow_t *)std::nothrow);
        if ( v11 )
        {
          for ( i = 0; i < (unsigned int)v8; ++i )
          {
            v14 = *a2;
            v15 = &v11[16 * i];
            v22 = 0;
            v16 = *(unsigned int (__fastcall **)(__int64 *, _QWORD, char *))(v14 + 40);
            v24[0] = 0;
            v23 = 0;
            if ( !v16(a2, i, v15) )
            {
              _DbgPrintMessage(4, "GetAt() failed; skipping session list sort..");
              goto LABEL_18;
            }
            if ( (*(int (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v26 + 24LL))(
                   v26,
                   *(unsigned int *)v15,
                   &v22) < 0 )
            {
              _DbgPrintMessage(4, "FindSessionById() failed; skipping session list sort..");
              goto LABEL_18;
            }
            if ( (*(int (__fastcall **)(__int64, __int64 *, __int64 *, unsigned int *))(*(_QWORD *)v22 + 200LL))(
                   v22,
                   v24,
                   &v23,
                   (unsigned int *)v15 + 2) < 0 )
            {
              _DbgPrintMessage(4, "GetTimes() failed; skipping session list sort..");
LABEL_18:
              SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v22);
              goto LABEL_22;
            }
            SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v22);
          }
          qsort(v11, v8, 0x10u, CompareSessionLogonTime);
          v25 = 1;
        }
        else
        {
          _DbgPrintMessage(4, "memory allocation failed; skipping session list sort..");
        }
LABEL_22:
        SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v26);
        SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>((__int64 *)&v28);
        v5 = v27;
      }
      else
      {
        v11 = 0;
        _DbgPrintMessage(4, "GetSessionList() failed; skipping session list sort..");
        SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v26);
        SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>((__int64 *)&v28);
      }
      v17 = 4 * v8;
      v18 = CoTaskMemAlloc((unsigned int)(4 * v8));
      if ( v18 )
      {
        v19 = v17 >> 2;
        for ( j = 0; (unsigned int)j < v19; j = (unsigned int)(j + 1) )
        {
          if ( v25 && v11 )
          {
            v18[j] = *(_DWORD *)&v11[16 * (unsigned int)j];
          }
          else if ( !(*(unsigned int (__fastcall **)(__int64 *, _QWORD, _DWORD *))(*a2 + 40))(
                       a2,
                       (unsigned int)j,
                       &v18[j]) )
          {
            CoTaskMemFree(v18);
            v9 = -2147024883;
            goto LABEL_34;
          }
        }
        *v5 = v18;
        *a4 = v19;
        v9 = 0;
      }
      else
      {
        v9 = -2147024882;
      }
LABEL_34:
      if ( v11 )
        operator delete(v11);
    }
    else
    {
      _DbgPrintMessage(
        8,
        "CUtils::GetInstanceOfSessionManager failed: 0x%x in %s",
        InstanceOfSessionManager,
        "CSessionArbitrationHelper::Copy");
      SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v26);
      SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>((__int64 *)&v28);
    }
  }
  else
  {
    return 0;
  }
  return v9;
}

```

## disassembly

```asm
0x1800ba760  mov     [rsp-40h+arg_10], r8
0x1800ba765  mov     [rsp-40h+arg_0], rcx
0x1800ba76a  push    rbp
0x1800ba76b  push    rbx
0x1800ba76c  push    rsi
0x1800ba76d  push    rdi
0x1800ba76e  push    r12
0x1800ba770  push    r13
0x1800ba772  push    r14
0x1800ba774  push    r15
0x1800ba776  mov     rbp, rsp
0x1800ba779  sub     rsp, 58h
0x1800ba77d  mov     qword ptr [r8], 0
0x1800ba784  mov     rcx, rdx
0x1800ba787  mov     dword ptr [r9], 0
0x1800ba78e  mov     r13, r9
0x1800ba791  mov     rax, [rdx]
0x1800ba794  mov     r12, r8
0x1800ba797  mov     r15, rdx
0x1800ba79a  mov     rax, [rax+18h]
0x1800ba79e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ba7a3  mov     esi, eax
0x1800ba7a5  test    eax, eax
0x1800ba7a7  jnz     short loc_1800BA7B0
0x1800ba7a9  xor     ebx, ebx
0x1800ba7ab  jmp     loc_1800BA9FF
0x1800ba7b0  lea     rcx, [rbp+arg_18]; struct ISessionManager **
0x1800ba7b4  mov     [rbp+arg_18], 0
0x1800ba7bc  mov     [rbp+arg_8], 0
0x1800ba7c4  call    ?GetInstanceOfSessionManager@CUtils@@SAJPEAPEAUISessionManager@@@Z; CUtils::GetInstanceOfSessionManager(ISessionManager * *)
0x1800ba7c9  mov     ebx, eax
0x1800ba7cb  test    eax, eax
0x1800ba7cd  jns     short loc_1800BA801
0x1800ba7cf  lea     r9, aCsessionarbitr_10; "CSessionArbitrationHelper::Copy"
0x1800ba7d6  mov     r8d, eax
0x1800ba7d9  lea     rdx, aCutilsGetinsta_2; "CUtils::GetInstanceOfSessionManager fai"...
0x1800ba7e0  mov     ecx, 8; int
0x1800ba7e5  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800ba7ea  lea     rcx, [rbp+arg_8]; void *
0x1800ba7ee  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x1800ba7f3  lea     rcx, [rbp+arg_18]; void *
0x1800ba7f7  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x1800ba7fc  jmp     loc_1800BA9FF
0x1800ba801  mov     rcx, [rbp+arg_18]
0x1800ba805  lea     rdx, [rbp+arg_8]
0x1800ba809  mov     byte ptr [rbp+arg_0], 0
0x1800ba80d  mov     rax, [rcx]
0x1800ba810  mov     rax, [rax+18h]
0x1800ba814  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ba819  test    eax, eax
0x1800ba81b  jns     short loc_1800BA845
0x1800ba81d  xor     edi, edi
0x1800ba81f  lea     rdx, aGetsessionlist; "GetSessionList() failed; skipping sessi"...
0x1800ba826  lea     ecx, [rdi+4]; int
0x1800ba829  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800ba82e  lea     rcx, [rbp+arg_8]; void *
0x1800ba832  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x1800ba837  lea     rcx, [rbp+arg_18]; void *
0x1800ba83b  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x1800ba840  jmp     loc_1800BA976
0x1800ba845  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800ba84c  mov     eax, 10h
0x1800ba851  mul     rsi
0x1800ba854  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800ba85b  cmovb   rax, rcx
0x1800ba85f  mov     rcx, rax; unsigned __int64
0x1800ba862  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800ba867  mov     rdi, rax
0x1800ba86a  test    rax, rax
0x1800ba86d  jnz     short loc_1800BA883
0x1800ba86f  lea     rdx, aMemoryAllocati_1; "memory allocation failed; skipping sess"...
0x1800ba876  lea     ecx, [rax+4]; int
0x1800ba879  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800ba87e  jmp     loc_1800BA960
0x1800ba883  xor     ebx, ebx
0x1800ba885  cmp     ebx, esi
0x1800ba887  jnb     loc_1800BA943
0x1800ba88d  mov     rax, [r15]
0x1800ba890  mov     edx, ebx
0x1800ba892  mov     r14d, ebx
0x1800ba895  mov     rcx, r15
0x1800ba898  shl     r14, 4
0x1800ba89c  add     r14, rdi
0x1800ba89f  mov     [rbp+var_28], 0
0x1800ba8a7  mov     rax, [rax+28h]
0x1800ba8ab  mov     r8, r14
0x1800ba8ae  mov     [rbp+var_18], 0
0x1800ba8b6  mov     [rbp+var_20], 0
0x1800ba8be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ba8c3  test    eax, eax
0x1800ba8c5  jz      short loc_1800BA93A
0x1800ba8c7  mov     rcx, [rbp+arg_8]
0x1800ba8cb  lea     r8, [rbp+var_28]
0x1800ba8cf  mov     edx, [r14]
0x1800ba8d2  mov     rax, [rcx]
0x1800ba8d5  mov     rax, [rax+18h]
0x1800ba8d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ba8de  test    eax, eax
0x1800ba8e0  js      short loc_1800BA931
0x1800ba8e2  mov     rcx, [rbp+var_28]
0x1800ba8e6  lea     r9, [r14+8]
0x1800ba8ea  lea     r8, [rbp+var_20]
0x1800ba8ee  lea     rdx, [rbp+var_18]
0x1800ba8f2  mov     rax, [rcx]
0x1800ba8f5  mov     rax, [rax+0C8h]
0x1800ba8fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ba901  test    eax, eax
0x1800ba903  js      short loc_1800BA915
0x1800ba905  lea     rcx, [rbp+var_28]; void *
0x1800ba909  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x1800ba90e  inc     ebx
0x1800ba910  jmp     loc_1800BA885
0x1800ba915  lea     rdx, aGettimesFailed; "GetTimes() failed; skipping session lis"...
0x1800ba91c  mov     ecx, 4; int
0x1800ba921  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800ba926  lea     rcx, [rbp+var_28]; void *
0x1800ba92a  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x1800ba92f  jmp     short loc_1800BA960
0x1800ba931  lea     rdx, aFindsessionbyi_1; "FindSessionById() failed; skipping sess"...
0x1800ba938  jmp     short loc_1800BA91C
0x1800ba93a  lea     rdx, aGetatFailedSki; "GetAt() failed; skipping session list s"...
0x1800ba941  jmp     short loc_1800BA91C
0x1800ba943  lea     r9, ?CompareSessionLogonTime@@YAHPEBX0@Z; CompareFunction
0x1800ba94a  mov     r8d, 10h; SizeOfElements
0x1800ba950  mov     rdx, rsi; NumOfElements
0x1800ba953  mov     rcx, rdi; Base
0x1800ba956  call    cs:__imp_qsort
0x1800ba95c  mov     byte ptr [rbp+arg_0], 1
0x1800ba960  lea     rcx, [rbp+arg_8]; void *
0x1800ba964  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x1800ba969  lea     rcx, [rbp+arg_18]; void *
0x1800ba96d  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x1800ba972  mov     r12, [rbp+arg_10]
0x1800ba976  lea     ebx, ds:0[rsi*4]
0x1800ba97d  mov     ecx, ebx; cb
0x1800ba97f  call    cs:__imp_CoTaskMemAlloc
0x1800ba985  mov     rsi, rax
0x1800ba988  test    rax, rax
0x1800ba98b  jnz     short loc_1800BA994
0x1800ba98d  mov     ebx, 8007000Eh
0x1800ba992  jmp     short loc_1800BA9F2
0x1800ba994  shr     ebx, 2
0x1800ba997  xor     r14d, r14d
0x1800ba99a  cmp     r14d, ebx
0x1800ba99d  jnb     short loc_1800BA9E8
0x1800ba99f  cmp     byte ptr [rbp+arg_0], 0
0x1800ba9a3  jz      short loc_1800BA9B9
0x1800ba9a5  test    rdi, rdi
0x1800ba9a8  jz      short loc_1800BA9B9
0x1800ba9aa  mov     eax, r14d
0x1800ba9ad  add     rax, rax
0x1800ba9b0  mov     eax, [rdi+rax*8]
0x1800ba9b3  mov     [rsi+r14*4], eax
0x1800ba9b7  jmp     short loc_1800BA9D3
0x1800ba9b9  mov     rcx, [r15]
0x1800ba9bc  lea     r8, [rsi+r14*4]
0x1800ba9c0  mov     edx, r14d
0x1800ba9c3  mov     rax, [rcx+28h]
0x1800ba9c7  mov     rcx, r15
0x1800ba9ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ba9cf  test    eax, eax
0x1800ba9d1  jz      short loc_1800BA9D8
0x1800ba9d3  inc     r14d
0x1800ba9d6  jmp     short loc_1800BA99A
0x1800ba9d8  mov     rcx, rsi; pv
0x1800ba9db  call    cs:__imp_CoTaskMemFree
0x1800ba9e1  mov     ebx, 8007000Dh
0x1800ba9e6  jmp     short loc_1800BA9F2
0x1800ba9e8  mov     [r12], rsi
0x1800ba9ec  mov     [r13+0], ebx
0x1800ba9f0  xor     ebx, ebx
0x1800ba9f2  test    rdi, rdi
0x1800ba9f5  jz      short loc_1800BA9FF
0x1800ba9f7  mov     rcx, rdi; Block
0x1800ba9fa  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800ba9ff  mov     eax, ebx
0x1800baa01  add     rsp, 58h
0x1800baa05  pop     r15
0x1800baa07  pop     r14
0x1800baa09  pop     r13
0x1800baa0b  pop     r12
0x1800baa0d  pop     rdi
0x1800baa0e  pop     rsi
0x1800baa0f  pop     rbx
0x1800baa10  pop     rbp
0x1800baa11  retn
```
