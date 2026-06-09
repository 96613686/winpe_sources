# CVdsPack::MigrateGetSourceInfo(_VDS_PROVIDER_PROP *,IVdsMigrateDisks * *,ulong,_GUID *,IUnknown * * *)

- ea: `0x1400405a0`
- end: `0x1400407ff`
- name: `?MigrateGetSourceInfo@CVdsPack@@QEAAJPEAU_VDS_PROVIDER_PROP@@PEAPEAUIVdsMigrateDisks@@KPEAU_GUID@@PEAPEAPEAUIUnknown@@@Z`
- size: `607`
- prototype: `int(CVdsPack *__hidden this, struct _VDS_PROVIDER_PROP *, struct IVdsMigrateDisks **, unsigned int, struct _GUID *, struct IUnknown ***)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x140017250`

## callees

- `0x140012c48`
- `0x14002e123`
- `0x1400405a0`
- `0x140056010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400407a2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400407b9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400407a2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400407b9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400406b2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400406b2`
- `vdsutil!VdsHeapAlloc` at `0x1400406c3`
- `vdsutil!VdsHeapAlloc` at `0x1400406c3`
- `vdsutil!VdsTraceEx` at `0x140040793`
- `vdsutil!VdsTraceEx` at `0x140040793`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x1400405ea`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x1400405ea`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x1400407cb`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x1400407cb`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CVdsPack::MigrateGetSourceInfo(
        CVdsPack *this,
        struct _VDS_PROVIDER_PROP *a2,
        struct IVdsMigrateDisks **a3,
        unsigned int a4,
        struct _GUID *a5,
        struct IUnknown ***a6)
{
  __int64 v6; // r13
  int v10; // eax
  int v11; // ebx
  int v12; // eax
  int v13; // eax
  HANDLE ProcessHeap; // rax
  struct IUnknown **v15; // rax
  __int64 i; // rsi
  int v17; // eax
  LPWSTR pwszName; // rcx
  LPWSTR pwszVersion; // rcx
  __int64 v21; // [rsp+30h] [rbp-30h] BYREF
  __int64 v22; // [rsp+38h] [rbp-28h] BYREF
  struct _GUID v23; // [rsp+40h] [rbp-20h] BYREF
  _BYTE v24[16]; // [rsp+50h] [rbp-10h] BYREF
  struct IUnknown **v26; // [rsp+A8h] [rbp+48h]

  v6 = a4;
  v22 = 0;
  v21 = 0;
  CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v24, 0x5Eu, "CVdsPack::MigrateGetSourceInfo()");
  memset_0(a2, 0, sizeof(struct _VDS_PROVIDER_PROP));
  if ( a2 && a3 && a5 && a6 )
  {
    v10 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**((_QWORD **)this + 11) + 32LL))(*((_QWORD *)this + 11), &v22);
    v11 = v10;
    if ( v10 >= 0 )
    {
      v12 = (*(__int64 (__fastcall **)(__int64, struct _VDS_PROVIDER_PROP *))(*(_QWORD *)v22 + 24LL))(v22, a2);
      v11 = v12;
      if ( v12 >= 0 )
      {
        v13 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v22)(v22, &IID_IVdsProviderPrivate, &v21);
        v11 = v13;
        if ( v13 >= 0 && v21 )
        {
          ProcessHeap = GetProcessHeap();
          v15 = (struct IUnknown **)VdsHeapAlloc(ProcessHeap, 8, 8 * v6);
          *a6 = v15;
          if ( v15 )
          {
            for ( i = 0; (unsigned int)i < (unsigned int)v6; i = (unsigned int)(i + 1) )
            {
              v26 = &(*a6)[i];
              v23 = a5[(unsigned int)i];
              v11 = (*(__int64 (__fastcall **)(__int64, struct _GUID *, __int64, struct IUnknown **))(*(_QWORD *)v21 + 24LL))(
                      v21,
                      &v23,
                      13,
                      v26);
              if ( v11 < 0 || !*v26 )
              {
                VdsTraceEx(94, 0, "CVdsPack::MigrateGetSourceInfo, 6, hr=%lX", (unsigned int)v11);
                goto LABEL_24;
              }
            }
            v17 = (***((__int64 (__fastcall ****)(_QWORD, GUID *, struct IVdsMigrateDisks **))this + 11))(
                    *((_QWORD *)this + 11),
                    &IID_IVdsMigrateDisks,
                    a3);
            v11 = v17;
            if ( v17 < 0 )
              VdsTraceEx(94, 0, "CVdsPack::MigrateGetSourceInfo, 7, hr=%lX", (unsigned int)v17);
          }
          else
          {
            v11 = -2147024882;
            VdsTraceEx(94, 0, "CVdsPack::MigrateGetSourceInfo, 5, hr=%lX", 2147942414LL);
          }
        }
        else
        {
          VdsTraceEx(94, 0, "CVdsPack::MigrateGetSourceInfo, 4, hr=%lX", (unsigned int)v13);
        }
      }
      else
      {
        VdsTraceEx(94, 0, "CVdsPack::MigrateGetSourceInfo, 3, hr=%lX", (unsigned int)v12);
      }
    }
    else
    {
      VdsTraceEx(94, 0, "CVdsPack::MigrateGetSourceInfo, 2, hr=%lX", (unsigned int)v10);
    }
  }
  else
  {
    v11 = -2147024809;
    VdsTraceEx(94, 0, "CVdsPack::MigrateGetSourceInfo, 1, hr=%lX", 2147942487LL);
  }
LABEL_24:
  pwszName = a2->pwszName;
  if ( pwszName )
  {
    CoTaskMemFree(pwszName);
    a2->pwszName = 0;
  }
  pwszVersion = a2->pwszVersion;
  if ( pwszVersion )
  {
    CoTaskMemFree(pwszVersion);
    a2->pwszVersion = 0;
  }
  CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v24);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v21);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v22);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1400405a0  mov     [rsp-38h+arg_10], rbx
0x1400405a5  mov     [rsp-38h+arg_0], rcx
0x1400405aa  push    rbp
0x1400405ab  push    rsi
0x1400405ac  push    rdi
0x1400405ad  push    r12
0x1400405af  push    r13
0x1400405b1  push    r14
0x1400405b3  push    r15
0x1400405b5  mov     rbp, rsp
0x1400405b8  sub     rsp, 60h
0x1400405bc  mov     r13d, r9d
0x1400405bf  mov     r12, r8
0x1400405c2  mov     rdi, rdx
0x1400405c5  mov     rbx, rcx
0x1400405c8  mov     [rbp+var_28], 0
0x1400405d0  mov     [rbp+var_30], 0
0x1400405d8  lea     r8, aCvdspackMigrat_18; "CVdsPack::MigrateGetSourceInfo()"
0x1400405df  mov     esi, 5Eh ; '^'
0x1400405e4  mov     edx, esi
0x1400405e6  lea     rcx, [rbp+var_10]
0x1400405ea  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x1400405f0  nop
0x1400405f1  xor     edx, edx; Val
0x1400405f3  lea     r8d, [rsi-1Eh]; Size
0x1400405f7  mov     rcx, rdi; void *
0x1400405fa  call    memset_0
0x1400405ff  test    rdi, rdi
0x140040602  jz      loc_140040780
0x140040608  test    r12, r12
0x14004060b  jz      loc_140040780
0x140040611  mov     r15, [rbp+arg_20]
0x140040615  test    r15, r15
0x140040618  jz      loc_140040780
0x14004061e  mov     r14, [rbp+arg_28]
0x140040622  test    r14, r14
0x140040625  jz      loc_140040780
0x14004062b  mov     rcx, [rbx+58h]
0x14004062f  mov     rax, [rcx]
0x140040632  lea     rdx, [rbp+var_28]
0x140040636  mov     rax, [rax+20h]
0x14004063a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004063f  mov     ebx, eax
0x140040641  test    eax, eax
0x140040643  jns     short loc_140040654
0x140040645  mov     r9d, eax
0x140040648  lea     r8, aCvdspackMigrat_0; "CVdsPack::MigrateGetSourceInfo, 2, hr=%"...
0x14004064f  jmp     loc_14004078F
0x140040654  mov     rcx, [rbp+var_28]
0x140040658  mov     rax, [rcx]
0x14004065b  mov     rdx, rdi
0x14004065e  mov     rax, [rax+18h]
0x140040662  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140040667  mov     ebx, eax
0x140040669  test    eax, eax
0x14004066b  jns     short loc_14004067C
0x14004066d  mov     r9d, eax
0x140040670  lea     r8, aCvdspackMigrat_16; "CVdsPack::MigrateGetSourceInfo, 3, hr=%"...
0x140040677  jmp     loc_14004078F
0x14004067c  mov     rcx, [rbp+var_28]
0x140040680  mov     rax, [rcx]
0x140040683  lea     r8, [rbp+var_30]
0x140040687  lea     rdx, IID_IVdsProviderPrivate
0x14004068e  mov     rax, [rax]
0x140040691  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140040696  mov     ebx, eax
0x140040698  test    eax, eax
0x14004069a  js      loc_140040774
0x1400406a0  cmp     [rbp+var_30], 0
0x1400406a5  jz      loc_140040774
0x1400406ab  mov     rbx, r13
0x1400406ae  shl     rbx, 3
0x1400406b2  call    cs:__imp_GetProcessHeap
0x1400406b8  mov     rcx, rax
0x1400406bb  mov     r8, rbx
0x1400406be  mov     edx, 8
0x1400406c3  call    cs:__imp_VdsHeapAlloc
0x1400406c9  mov     [r14], rax
0x1400406cc  test    rax, rax
0x1400406cf  jnz     short loc_1400406E2
0x1400406d1  mov     ebx, 8007000Eh
0x1400406d6  lea     r8, aCvdspackMigrat; "CVdsPack::MigrateGetSourceInfo, 5, hr=%"...
0x1400406dd  jmp     loc_14004078C
0x1400406e2  xor     esi, esi
0x1400406e4  cmp     esi, r13d
0x1400406e7  jnb     short loc_140040745
0x1400406e9  mov     edx, esi
0x1400406eb  mov     rax, [r14]
0x1400406ee  lea     r8, [rax+rsi*8]
0x1400406f2  mov     [rbp+arg_8], r8
0x1400406f6  mov     rcx, [rbp+var_30]
0x1400406fa  add     rdx, rdx
0x1400406fd  movups  xmm0, xmmword ptr [r15+rdx*8]
0x140040702  movdqu  [rbp+var_20], xmm0
0x140040707  mov     rax, [rcx]
0x14004070a  mov     r9, r8
0x14004070d  mov     r8d, 0Dh
0x140040713  lea     rdx, [rbp+var_20]
0x140040717  mov     rax, [rax+18h]
0x14004071b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140040720  mov     ebx, eax
0x140040722  test    eax, eax
0x140040724  js      short loc_140040734
0x140040726  mov     rax, [rbp+arg_8]
0x14004072a  cmp     qword ptr [rax], 0
0x14004072e  jz      short loc_140040734
0x140040730  inc     esi
0x140040732  jmp     short loc_1400406E4
0x140040734  mov     r9d, ebx
0x140040737  lea     r8, aCvdspackMigrat_6; "CVdsPack::MigrateGetSourceInfo, 6, hr=%"...
0x14004073e  mov     ecx, 5Eh ; '^'
0x140040743  jmp     short loc_140040791
0x140040745  mov     rcx, [rbp+arg_0]
0x140040749  mov     rcx, [rcx+58h]
0x14004074d  mov     rax, [rcx]
0x140040750  mov     r8, r12
0x140040753  lea     rdx, IID_IVdsMigrateDisks
0x14004075a  mov     rax, [rax]
0x14004075d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140040762  mov     ebx, eax
0x140040764  test    eax, eax
0x140040766  jns     short loc_140040799
0x140040768  mov     r9d, eax
0x14004076b  lea     r8, aCvdspackMigrat_2; "CVdsPack::MigrateGetSourceInfo, 7, hr=%"...
0x140040772  jmp     short loc_14004073E
0x140040774  mov     r9d, eax
0x140040777  lea     r8, aCvdspackMigrat_10; "CVdsPack::MigrateGetSourceInfo, 4, hr=%"...
0x14004077e  jmp     short loc_14004078F
0x140040780  mov     ebx, 80070057h
0x140040785  lea     r8, aCvdspackMigrat_34; "CVdsPack::MigrateGetSourceInfo, 1, hr=%"...
0x14004078c  mov     r9d, ebx
0x14004078f  mov     ecx, esi
0x140040791  xor     edx, edx
0x140040793  call    cs:__imp_VdsTraceEx
0x140040799  mov     rcx, [rdi+10h]; pv
0x14004079d  test    rcx, rcx
0x1400407a0  jz      short loc_1400407B0
0x1400407a2  call    cs:__imp_CoTaskMemFree
0x1400407a8  mov     qword ptr [rdi+10h], 0
0x1400407b0  mov     rcx, [rdi+28h]; pv
0x1400407b4  test    rcx, rcx
0x1400407b7  jz      short loc_1400407C7
0x1400407b9  call    cs:__imp_CoTaskMemFree
0x1400407bf  mov     qword ptr [rdi+28h], 0
0x1400407c7  lea     rcx, [rbp+var_10]
0x1400407cb  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x1400407d1  nop
0x1400407d2  lea     rcx, [rbp+var_30]
0x1400407d6  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1400407db  nop
0x1400407dc  lea     rcx, [rbp+var_28]
0x1400407e0  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1400407e5  mov     eax, ebx
0x1400407e7  mov     rbx, [rsp+60h+arg_10]
0x1400407ef  add     rsp, 60h
0x1400407f3  pop     r15
0x1400407f5  pop     r14
0x1400407f7  pop     r13
0x1400407f9  pop     r12
0x1400407fb  pop     rdi
0x1400407fc  pop     rsi
0x1400407fd  pop     rbp
0x1400407fe  retn
```
