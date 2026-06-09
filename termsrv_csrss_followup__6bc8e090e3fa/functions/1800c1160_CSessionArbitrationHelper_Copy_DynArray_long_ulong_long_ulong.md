# CSessionArbitrationHelper::Copy(DynArray<long,ulong> &,long * *,ulong *)

- ea: `0x1800c1160`
- end: `0x1800c1425`
- name: `?Copy@CSessionArbitrationHelper@@AEAAJAEAV?$DynArray@JK@@PEAPEAJPEAK@Z`
- size: `709`
- prototype: ``
- caller_count: `4`
- callee_count: `7`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800c2400`
- `0x1800c27b0`
- `0x1800c2bc0`
- `0x1800c2f00`

## callees

- `0x180009940`
- `0x180013948`
- `0x1800139c0`
- `0x180033f44`
- `0x18003444c`
- `0x1800c1160`
- `0x1800ce010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_qsort` at `0x1800c1356`
- `api-ms-win-crt-private-l1-1-0!_o_qsort` at `0x1800c1356`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800c1385`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800c1385`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c13e7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c13e7`

## string_xrefs

- `0x1800c11cf`: `CSessionArbitrationHelper::Copy`

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
        SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v28);
        v5 = v27;
      }
      else
      {
        v11 = 0;
        _DbgPrintMessage(4, "GetSessionList() failed; skipping session list sort..");
        SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v26);
        SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v28);
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
      SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v28);
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
0x1800c1160  mov     [rsp-40h+arg_10], r8
0x1800c1165  mov     [rsp-40h+arg_0], rcx
0x1800c116a  push    rbp
0x1800c116b  push    rbx
0x1800c116c  push    rsi
0x1800c116d  push    rdi
0x1800c116e  push    r12
0x1800c1170  push    r13
0x1800c1172  push    r14
0x1800c1174  push    r15
0x1800c1176  mov     rbp, rsp
0x1800c1179  sub     rsp, 58h
0x1800c117d  mov     qword ptr [r8], 0
0x1800c1184  mov     rcx, rdx
0x1800c1187  mov     dword ptr [r9], 0
0x1800c118e  mov     r13, r9
0x1800c1191  mov     rax, [rdx]
0x1800c1194  mov     r12, r8
0x1800c1197  mov     r15, rdx
0x1800c119a  mov     rax, [rax+18h]
0x1800c119e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c11a3  mov     esi, eax
0x1800c11a5  test    eax, eax
0x1800c11a7  jnz     short loc_1800C11B0
0x1800c11a9  xor     ebx, ebx
0x1800c11ab  jmp     loc_1800C1411
0x1800c11b0  lea     rcx, [rbp+arg_18]; struct ISessionManager **
0x1800c11b4  mov     [rbp+arg_18], 0
0x1800c11bc  mov     [rbp+arg_8], 0
0x1800c11c4  call    ?GetInstanceOfSessionManager@CUtils@@SAJPEAPEAUISessionManager@@@Z; CUtils::GetInstanceOfSessionManager(ISessionManager * *)
0x1800c11c9  mov     ebx, eax
0x1800c11cb  test    eax, eax
0x1800c11cd  jns     short loc_1800C1201
0x1800c11cf  lea     r9, aCsessionarbitr_10; "CSessionArbitrationHelper::Copy"
0x1800c11d6  mov     r8d, eax
0x1800c11d9  lea     rdx, aCutilsGetinsta_2; "CUtils::GetInstanceOfSessionManager fai"...
0x1800c11e0  mov     ecx, 8; int
0x1800c11e5  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800c11ea  lea     rcx, [rbp+arg_8]; void *
0x1800c11ee  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x1800c11f3  lea     rcx, [rbp+arg_18]; void *
0x1800c11f7  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x1800c11fc  jmp     loc_1800C1411
0x1800c1201  mov     rcx, [rbp+arg_18]
0x1800c1205  lea     rdx, [rbp+arg_8]
0x1800c1209  mov     byte ptr [rbp+arg_0], 0
0x1800c120d  mov     rax, [rcx]
0x1800c1210  mov     rax, [rax+18h]
0x1800c1214  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c1219  test    eax, eax
0x1800c121b  jns     short loc_1800C1245
0x1800c121d  xor     edi, edi
0x1800c121f  lea     rdx, aGetsessionlist; "GetSessionList() failed; skipping sessi"...
0x1800c1226  lea     ecx, [rdi+4]; int
0x1800c1229  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800c122e  lea     rcx, [rbp+arg_8]; void *
0x1800c1232  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x1800c1237  lea     rcx, [rbp+arg_18]; void *
0x1800c123b  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x1800c1240  jmp     loc_1800C137C
0x1800c1245  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800c124c  mov     eax, 10h
0x1800c1251  mul     rsi
0x1800c1254  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800c125b  cmovb   rax, rcx
0x1800c125f  mov     rcx, rax; unsigned __int64
0x1800c1262  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800c1267  mov     rdi, rax
0x1800c126a  test    rax, rax
0x1800c126d  jnz     short loc_1800C1283
0x1800c126f  lea     rdx, aMemoryAllocati_1; "memory allocation failed; skipping sess"...
0x1800c1276  lea     ecx, [rax+4]; int
0x1800c1279  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800c127e  jmp     loc_1800C1366
0x1800c1283  xor     ebx, ebx
0x1800c1285  cmp     ebx, esi
0x1800c1287  jnb     loc_1800C1343
0x1800c128d  mov     rax, [r15]
0x1800c1290  mov     edx, ebx
0x1800c1292  mov     r14d, ebx
0x1800c1295  mov     rcx, r15
0x1800c1298  shl     r14, 4
0x1800c129c  add     r14, rdi
0x1800c129f  mov     [rbp+var_28], 0
0x1800c12a7  mov     rax, [rax+28h]
0x1800c12ab  mov     r8, r14
0x1800c12ae  mov     [rbp+var_18], 0
0x1800c12b6  mov     [rbp+var_20], 0
0x1800c12be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c12c3  test    eax, eax
0x1800c12c5  jz      short loc_1800C133A
0x1800c12c7  mov     rcx, [rbp+arg_8]
0x1800c12cb  lea     r8, [rbp+var_28]
0x1800c12cf  mov     edx, [r14]
0x1800c12d2  mov     rax, [rcx]
0x1800c12d5  mov     rax, [rax+18h]
0x1800c12d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c12de  test    eax, eax
0x1800c12e0  js      short loc_1800C1331
0x1800c12e2  mov     rcx, [rbp+var_28]
0x1800c12e6  lea     r9, [r14+8]
0x1800c12ea  lea     r8, [rbp+var_20]
0x1800c12ee  lea     rdx, [rbp+var_18]
0x1800c12f2  mov     rax, [rcx]
0x1800c12f5  mov     rax, [rax+0C8h]
0x1800c12fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c1301  test    eax, eax
0x1800c1303  js      short loc_1800C1315
0x1800c1305  lea     rcx, [rbp+var_28]; void *
0x1800c1309  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x1800c130e  inc     ebx
0x1800c1310  jmp     loc_1800C1285
0x1800c1315  lea     rdx, aGettimesFailed; "GetTimes() failed; skipping session lis"...
0x1800c131c  mov     ecx, 4; int
0x1800c1321  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800c1326  lea     rcx, [rbp+var_28]; void *
0x1800c132a  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x1800c132f  jmp     short loc_1800C1366
0x1800c1331  lea     rdx, aFindsessionbyi_1; "FindSessionById() failed; skipping sess"...
0x1800c1338  jmp     short loc_1800C131C
0x1800c133a  lea     rdx, aGetatFailedSki; "GetAt() failed; skipping session list s"...
0x1800c1341  jmp     short loc_1800C131C
0x1800c1343  lea     r9, ?CompareSessionLogonTime@@YAHPEBX0@Z; CompareFunction
0x1800c134a  mov     r8d, 10h; SizeOfElements
0x1800c1350  mov     rdx, rsi; NumOfElements
0x1800c1353  mov     rcx, rdi; Base
0x1800c1356  call    cs:__imp_qsort
0x1800c135d  nop     dword ptr [rax+rax+00h]
0x1800c1362  mov     byte ptr [rbp+arg_0], 1
0x1800c1366  lea     rcx, [rbp+arg_8]; void *
0x1800c136a  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x1800c136f  lea     rcx, [rbp+arg_18]; void *
0x1800c1373  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x1800c1378  mov     r12, [rbp+arg_10]
0x1800c137c  lea     ebx, ds:0[rsi*4]
0x1800c1383  mov     ecx, ebx; cb
0x1800c1385  call    cs:__imp_CoTaskMemAlloc
0x1800c138c  nop     dword ptr [rax+rax+00h]
0x1800c1391  mov     rsi, rax
0x1800c1394  test    rax, rax
0x1800c1397  jnz     short loc_1800C13A0
0x1800c1399  mov     ebx, 8007000Eh
0x1800c139e  jmp     short loc_1800C1404
0x1800c13a0  shr     ebx, 2
0x1800c13a3  xor     r14d, r14d
0x1800c13a6  cmp     r14d, ebx
0x1800c13a9  jnb     short loc_1800C13FA
0x1800c13ab  cmp     byte ptr [rbp+arg_0], 0
0x1800c13af  jz      short loc_1800C13C5
0x1800c13b1  test    rdi, rdi
0x1800c13b4  jz      short loc_1800C13C5
0x1800c13b6  mov     eax, r14d
0x1800c13b9  add     rax, rax
0x1800c13bc  mov     eax, [rdi+rax*8]
0x1800c13bf  mov     [rsi+r14*4], eax
0x1800c13c3  jmp     short loc_1800C13DF
0x1800c13c5  mov     rcx, [r15]
0x1800c13c8  lea     r8, [rsi+r14*4]
0x1800c13cc  mov     edx, r14d
0x1800c13cf  mov     rax, [rcx+28h]
0x1800c13d3  mov     rcx, r15
0x1800c13d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c13db  test    eax, eax
0x1800c13dd  jz      short loc_1800C13E4
0x1800c13df  inc     r14d
0x1800c13e2  jmp     short loc_1800C13A6
0x1800c13e4  mov     rcx, rsi; pv
0x1800c13e7  call    cs:__imp_CoTaskMemFree
0x1800c13ee  nop     dword ptr [rax+rax+00h]
0x1800c13f3  mov     ebx, 8007000Dh
0x1800c13f8  jmp     short loc_1800C1404
0x1800c13fa  mov     [r12], rsi
0x1800c13fe  mov     [r13+0], ebx
0x1800c1402  xor     ebx, ebx
0x1800c1404  test    rdi, rdi
0x1800c1407  jz      short loc_1800C1411
0x1800c1409  mov     rcx, rdi; Block
0x1800c140c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800c1411  mov     eax, ebx
0x1800c1413  add     rsp, 58h
0x1800c1417  pop     r15
0x1800c1419  pop     r14
0x1800c141b  pop     r13
0x1800c141d  pop     r12
0x1800c141f  pop     rdi
0x1800c1420  pop     rsi
0x1800c1421  pop     rbx
0x1800c1422  pop     rbp
0x1800c1423  retn
```
