# CVdsVolume::ShrinkRoutine(void *)

- ea: `0x140043ec0`
- end: `0x140044167`
- name: `?ShrinkRoutine@CVdsVolume@@SAKPEAX@Z`
- size: `679`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x14000f930`
- `0x14000f98c`
- `0x140010b04`
- `0x140012c48`
- `0x140012c9c`
- `0x1400439b0`
- `0x140043ec0`
- `0x140056010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1400440ec`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1400440ec`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x140043fb4`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x140043fb4`
- `vdsutil!?SetCompletionStatus@CVdsAsyncObjectBase@@QEAAXJK@Z` at `0x140043f55`
- `vdsutil!?SetCompletionStatus@CVdsAsyncObjectBase@@QEAAXJK@Z` at `0x140044022`
- `vdsutil!?SetCompletionStatus@CVdsAsyncObjectBase@@QEAAXJK@Z` at `0x140044073`
- `vdsutil!?SetCompletionStatus@CVdsAsyncObjectBase@@QEAAXJK@Z` at `0x1400440cc`
- `vdsutil!?SetCompletionStatus@CVdsAsyncObjectBase@@QEAAXJK@Z` at `0x140043f55`
- `vdsutil!?SetCompletionStatus@CVdsAsyncObjectBase@@QEAAXJK@Z` at `0x140044022`
- `vdsutil!?SetCompletionStatus@CVdsAsyncObjectBase@@QEAAXJK@Z` at `0x140044073`
- `vdsutil!?SetCompletionStatus@CVdsAsyncObjectBase@@QEAAXJK@Z` at `0x1400440cc`
- `vdsutil!?Signal@CVdsAsyncObjectBase@@QEAAXXZ` at `0x1400440f5`
- `vdsutil!?Signal@CVdsAsyncObjectBase@@QEAAXXZ` at `0x1400440f5`
- `vdsutil!VdsTraceEx` at `0x140043f45`
- `vdsutil!VdsTraceEx` at `0x140043fcf`
- `vdsutil!VdsTraceEx` at `0x140044014`
- `vdsutil!VdsTraceEx` at `0x140044065`
- `vdsutil!VdsTraceEx` at `0x1400440b8`
- `vdsutil!VdsTraceEx` at `0x140043f45`
- `vdsutil!VdsTraceEx` at `0x140043fcf`
- `vdsutil!VdsTraceEx` at `0x140044014`
- `vdsutil!VdsTraceEx` at `0x140044065`
- `vdsutil!VdsTraceEx` at `0x1400440b8`
- `vdsutil!AcquireRundownProtection` at `0x140043f2b`
- `vdsutil!AcquireRundownProtection` at `0x140043f2b`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140043f1d`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140043f1d`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140044112`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140044112`
- `vdsutil!ReleaseRundownProtection` at `0x140044107`
- `vdsutil!ReleaseRundownProtection` at `0x140044107`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall CVdsVolume::ShrinkRoutine(_QWORD *Parameter)
{
  struct CVdsServiceAsyncObject *v2; // rdi
  CVdsVolume *v3; // rbx
  char v4; // r13
  int v5; // edx
  CVdsAsyncObjectBase *v6; // rcx
  int v7; // r15d
  __int64 v8; // r14
  __int64 v9; // r12
  __int64 v10; // rdx
  __int64 v11; // rax
  HRESULT v12; // eax
  HRESULT v13; // esi
  int v14; // r15d
  int v15; // eax
  int v16; // esi
  int v17; // ebx
  int v18; // edx
  struct CVdsServiceAsyncObject *v20; // [rsp+30h] [rbp-50h] BYREF
  unsigned __int64 v21; // [rsp+38h] [rbp-48h] BYREF
  __int64 v22; // [rsp+40h] [rbp-40h] BYREF
  _QWORD *v23; // [rsp+48h] [rbp-38h] BYREF
  _BYTE v24[16]; // [rsp+50h] [rbp-30h] BYREF
  _OWORD v25[2]; // [rsp+60h] [rbp-20h] BYREF
  int v26; // [rsp+C8h] [rbp+48h] BYREF
  __int64 v27; // [rsp+D0h] [rbp+50h] BYREF
  CVdsVolume *v28; // [rsp+D8h] [rbp+58h] BYREF

  v23 = 0;
  v2 = 0;
  v20 = 0;
  v3 = 0;
  v28 = 0;
  v21 = 0;
  v26 = 0;
  memset(v25, 0, sizeof(v25));
  v27 = 0;
  v22 = 0;
  CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v24, 0x5Eu, "CVdsVolume::ShrinkRoutine()");
  v4 = AcquireRundownProtection(&g_RundownRef);
  if ( !v4 )
  {
    VdsTraceEx(94, 3, "CVdsVolume::ShrinkRoutine exiting due to shutdown");
    v5 = -2146959352;
    v6 = 0;
LABEL_3:
    CVdsAsyncObjectBase::SetCompletionStatus(v6, v5, 0);
    goto LABEL_27;
  }
  v23 = Parameter;
  ATL::CComPtrBase<CVdsEnumObject>::Attach((__int64 *)&v20, Parameter[3]);
  v7 = *((_DWORD *)Parameter + 8);
  v8 = *Parameter;
  v9 = Parameter[1];
  v10 = Parameter[2];
  if ( v10 )
  {
    ATL::CComPtrBase<CVdsEnumObject>::Attach((__int64 *)&v28, v10);
    v3 = v28;
  }
  v11 = Parameter[5];
  if ( v11 )
    v22 = v11 + 2;
  v2 = v20;
  if ( !v7 )
  {
    v14 = 0;
LABEL_15:
    v17 = (*(__int64 (__fastcall **)(_QWORD *, __int64, __int64 *))(**((_QWORD **)v3 + 16) + 56LL))(
            *((_QWORD **)v3 + 16),
            v8,
            &v27);
    if ( v17 >= 0 )
    {
      v17 = (*(__int64 (__fastcall **)(__int64, int *, _OWORD *))(*(_QWORD *)v27 + 32LL))(v27, &v26, v25);
      if ( v17 >= 0 )
      {
        if ( v26 >= 0 )
        {
          CVdsAsyncObjectBase::SetCompletionStatus(v2, v26, 0x64u);
          LODWORD(v25[0]) = 3;
          *((_QWORD *)&v25[0] + 1) = v8;
          if ( *((_DWORD *)v2 + 20) == 3 )
            *((_QWORD *)v2 + 11) = v8;
LABEL_25:
          if ( !v14 )
            goto LABEL_27;
          goto LABEL_26;
        }
        VdsTraceEx(94, 0, "CVdsVolume::ShrinkRoutine: IVdsVolume::Shrink provider pAsync->Wait returned error: %X", v26);
        v18 = v26;
LABEL_18:
        CVdsAsyncObjectBase::SetCompletionStatus(v2, v18, 0);
        goto LABEL_25;
      }
      VdsTraceEx(
        94,
        0,
        "CVdsVolume::ShrinkRoutine: IVdsVolume::Shrink provider pAsync->Wait failed: %X",
        (unsigned int)v17);
    }
    else
    {
      VdsTraceEx(94, 0, "CVdsVolume::ShrinkRoutine: IVdsVolume::Shrink provider call failed: %X", (unsigned int)v17);
    }
    v18 = v17;
    goto LABEL_18;
  }
  v12 = CoInitializeEx(0, 0);
  v13 = v12;
  if ( v12 < 0 )
  {
    VdsTraceEx(94, 0, "CVdsVolume::ShrinkRoutine: CoInitializeEx failed: %X", v12);
    v5 = v13;
    v6 = v2;
    goto LABEL_3;
  }
  v14 = 1;
  v15 = CVdsVolume::ShrinkFileSystem(v3, v8, v9, &v21, v2);
  v16 = v15;
  if ( v15 >= 0 )
  {
    v8 = v21;
    goto LABEL_15;
  }
  VdsTraceEx(94, 0, "CVdsVolume::ShrinkRoutine: ShrinkFileSystem failed: %X", v15);
  CVdsAsyncObjectBase::SetCompletionStatus(v2, v16, 0);
LABEL_26:
  CoUninitialize();
LABEL_27:
  CVdsAsyncObjectBase::Signal(v2);
  if ( v4 )
    ReleaseRundownProtection(&g_RundownRef);
  CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v24);
  CVolumeLock::~CVolumeLock((CVolumeLock *)&v22);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v27);
  ATL::CComPtrBase<CVdsEnumObject>::~CComPtrBase<CVdsEnumObject>((__int64 *)&v28);
  ATL::CComPtrBase<CVdsEnumObject>::~CComPtrBase<CVdsEnumObject>((__int64 *)&v20);
  CVdsHeapPtr<_EXTEND_VOLUME_HANDLER_PARAMETER>::~CVdsHeapPtr<_EXTEND_VOLUME_HANDLER_PARAMETER>((__int64 *)&v23);
  return 0;
}

```

## disassembly

```asm
0x140043ec0  mov     [rsp-38h+arg_0], rbx
0x140043ec5  push    rbp
0x140043ec6  push    rsi
0x140043ec7  push    rdi
0x140043ec8  push    r12
0x140043eca  push    r13
0x140043ecc  push    r14
0x140043ece  push    r15
0x140043ed0  mov     rbp, rsp
0x140043ed3  sub     rsp, 80h
0x140043eda  mov     rsi, rcx
0x140043edd  mov     [rbp+var_38], 0
0x140043ee5  xor     edi, edi
0x140043ee7  mov     [rbp+var_50], rdi
0x140043eeb  xor     ebx, ebx
0x140043eed  mov     [rbp+arg_18], rbx
0x140043ef1  mov     [rbp+var_48], rbx
0x140043ef5  mov     [rbp+arg_8], ebx
0x140043ef8  xorps   xmm0, xmm0
0x140043efb  movups  [rbp+var_20], xmm0
0x140043eff  movups  [rbp+var_10], xmm0
0x140043f03  mov     [rbp+arg_10], rbx
0x140043f07  mov     [rbp+var_40], rbx
0x140043f0b  lea     r8, aCvdsvolumeShri_6; "CVdsVolume::ShrinkRoutine()"
0x140043f12  lea     r14d, [rdi+5Eh]
0x140043f16  mov     edx, r14d
0x140043f19  lea     rcx, [rbp+var_30]
0x140043f1d  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x140043f23  nop
0x140043f24  lea     rcx, ?g_RundownRef@@3U_RUNDOWN_REF@@A; _RUNDOWN_REF g_RundownRef
0x140043f2b  call    cs:__imp_AcquireRundownProtection
0x140043f31  mov     r13b, al
0x140043f34  test    al, al
0x140043f36  jnz     short loc_140043F60
0x140043f38  lea     r8, aCvdsvolumeShri_15; "CVdsVolume::ShrinkRoutine exiting due t"...
0x140043f3f  lea     edx, [rdi+3]
0x140043f42  mov     ecx, r14d
0x140043f45  call    cs:__imp_VdsTraceEx
0x140043f4b  xor     r8d, r8d
0x140043f4e  mov     edx, 80080008h
0x140043f53  xor     ecx, ecx
0x140043f55  call    cs:__imp_?SetCompletionStatus@CVdsAsyncObjectBase@@QEAAXJK@Z; CVdsAsyncObjectBase::SetCompletionStatus(long,ulong)
0x140043f5b  jmp     loc_1400440F2
0x140043f60  mov     [rbp+var_38], rsi
0x140043f64  mov     rdx, [rsi+18h]
0x140043f68  lea     rcx, [rbp+var_50]
0x140043f6c  call    ?Attach@?$CComPtrBase@VCVdsEnumObject@@@ATL@@QEAAXPEAVCVdsEnumObject@@@Z; ATL::CComPtrBase<CVdsEnumObject>::Attach(CVdsEnumObject *)
0x140043f71  mov     r15d, [rsi+20h]
0x140043f75  mov     r14, [rsi]
0x140043f78  mov     r12, [rsi+8]
0x140043f7c  mov     rdx, [rsi+10h]
0x140043f80  test    rdx, rdx
0x140043f83  jz      short loc_140043F92
0x140043f85  lea     rcx, [rbp+arg_18]
0x140043f89  call    ?Attach@?$CComPtrBase@VCVdsEnumObject@@@ATL@@QEAAXPEAVCVdsEnumObject@@@Z; ATL::CComPtrBase<CVdsEnumObject>::Attach(CVdsEnumObject *)
0x140043f8e  mov     rbx, [rbp+arg_18]
0x140043f92  mov     rax, [rsi+28h]
0x140043f96  test    rax, rax
0x140043f99  jz      short loc_140043FA3
0x140043f9b  add     rax, 2
0x140043f9f  mov     [rbp+var_40], rax
0x140043fa3  mov     rdi, [rbp+var_50]
0x140043fa7  test    r15d, r15d
0x140043faa  jz      loc_140044033
0x140043fb0  xor     edx, edx; dwCoInit
0x140043fb2  xor     ecx, ecx; pvReserved
0x140043fb4  call    cs:__imp_CoInitializeEx
0x140043fba  mov     esi, eax
0x140043fbc  test    eax, eax
0x140043fbe  jns     short loc_140043FE2
0x140043fc0  mov     r9d, eax
0x140043fc3  lea     r8, aCvdsvolumeShri_8; "CVdsVolume::ShrinkRoutine: CoInitialize"...
0x140043fca  xor     edx, edx
0x140043fcc  lea     ecx, [rdx+5Eh]
0x140043fcf  call    cs:__imp_VdsTraceEx
0x140043fd5  xor     r8d, r8d
0x140043fd8  mov     edx, esi
0x140043fda  mov     rcx, rdi
0x140043fdd  jmp     loc_140043F55
0x140043fe2  mov     r15d, 1
0x140043fe8  mov     [rsp+80h+var_60], rdi; struct CVdsServiceAsyncObject *
0x140043fed  lea     r9, [rbp+var_48]; unsigned __int64 *
0x140043ff1  mov     r8, r12; unsigned __int64
0x140043ff4  mov     rdx, r14; unsigned __int64
0x140043ff7  mov     rcx, rbx; this
0x140043ffa  call    ?ShrinkFileSystem@CVdsVolume@@QEAAJ_K0PEA_KPEAVCVdsServiceAsyncObject@@@Z; CVdsVolume::ShrinkFileSystem(unsigned __int64,unsigned __int64,unsigned __int64 *,CVdsServiceAsyncObject *)
0x140043fff  mov     esi, eax
0x140044001  test    eax, eax
0x140044003  jns     short loc_14004402D
0x140044005  mov     r9d, eax
0x140044008  lea     r8, aCvdsvolumeShri_3; "CVdsVolume::ShrinkRoutine: ShrinkFileSy"...
0x14004400f  xor     edx, edx
0x140044011  lea     ecx, [rdx+5Eh]
0x140044014  call    cs:__imp_VdsTraceEx
0x14004401a  xor     r8d, r8d
0x14004401d  mov     edx, esi
0x14004401f  mov     rcx, rdi
0x140044022  call    cs:__imp_?SetCompletionStatus@CVdsAsyncObjectBase@@QEAAXJK@Z; CVdsAsyncObjectBase::SetCompletionStatus(long,ulong)
0x140044028  jmp     loc_1400440EC
0x14004402d  mov     r14, [rbp+var_48]
0x140044031  jmp     short loc_140044036
0x140044033  xor     r15d, r15d
0x140044036  mov     rcx, [rbx+80h]
0x14004403d  mov     rax, [rcx]
0x140044040  lea     r8, [rbp+arg_10]
0x140044044  mov     rdx, r14
0x140044047  mov     rax, [rax+38h]
0x14004404b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140044050  mov     ebx, eax
0x140044052  test    eax, eax
0x140044054  jns     short loc_14004407B
0x140044056  lea     r8, aCvdsvolumeShri_21; "CVdsVolume::ShrinkRoutine: IVdsVolume::"...
0x14004405d  mov     r9d, ebx
0x140044060  xor     edx, edx
0x140044062  lea     ecx, [rdx+5Eh]
0x140044065  call    cs:__imp_VdsTraceEx
0x14004406b  mov     edx, ebx
0x14004406d  xor     r8d, r8d
0x140044070  mov     rcx, rdi
0x140044073  call    cs:__imp_?SetCompletionStatus@CVdsAsyncObjectBase@@QEAAXJK@Z; CVdsAsyncObjectBase::SetCompletionStatus(long,ulong)
0x140044079  jmp     short loc_1400440E7
0x14004407b  mov     rcx, [rbp+arg_10]
0x14004407f  mov     rax, [rcx]
0x140044082  lea     r8, [rbp+var_20]
0x140044086  lea     rdx, [rbp+arg_8]
0x14004408a  mov     rax, [rax+20h]
0x14004408e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140044093  mov     ebx, eax
0x140044095  test    eax, eax
0x140044097  jns     short loc_1400440A2
0x140044099  lea     r8, aCvdsvolumeShri_0; "CVdsVolume::ShrinkRoutine: IVdsVolume::"...
0x1400440a0  jmp     short loc_14004405D
0x1400440a2  mov     edx, [rbp+arg_8]
0x1400440a5  test    edx, edx
0x1400440a7  jns     short loc_1400440C3
0x1400440a9  mov     r9d, edx
0x1400440ac  lea     r8, aCvdsvolumeShri_18; "CVdsVolume::ShrinkRoutine: IVdsVolume::"...
0x1400440b3  xor     edx, edx
0x1400440b5  lea     ecx, [rdx+5Eh]
0x1400440b8  call    cs:__imp_VdsTraceEx
0x1400440be  mov     edx, [rbp+arg_8]
0x1400440c1  jmp     short loc_14004406D
0x1400440c3  mov     r8d, 64h ; 'd'
0x1400440c9  mov     rcx, rdi
0x1400440cc  call    cs:__imp_?SetCompletionStatus@CVdsAsyncObjectBase@@QEAAXJK@Z; CVdsAsyncObjectBase::SetCompletionStatus(long,ulong)
0x1400440d2  mov     dword ptr [rbp+var_20], 3
0x1400440d9  mov     qword ptr [rbp+var_20+8], r14
0x1400440dd  cmp     dword ptr [rdi+50h], 3
0x1400440e1  jnz     short loc_1400440E7
0x1400440e3  mov     [rdi+58h], r14
0x1400440e7  test    r15d, r15d
0x1400440ea  jz      short loc_1400440F2
0x1400440ec  call    cs:__imp_CoUninitialize
0x1400440f2  mov     rcx, rdi
0x1400440f5  call    cs:__imp_?Signal@CVdsAsyncObjectBase@@QEAAXXZ; CVdsAsyncObjectBase::Signal(void)
0x1400440fb  test    r13b, r13b
0x1400440fe  jz      short loc_14004410E
0x140044100  lea     rcx, ?g_RundownRef@@3U_RUNDOWN_REF@@A; _RUNDOWN_REF g_RundownRef
0x140044107  call    cs:__imp_ReleaseRundownProtection
0x14004410d  nop
0x14004410e  lea     rcx, [rbp+var_30]
0x140044112  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x140044118  nop
0x140044119  lea     rcx, [rbp+var_40]; this
0x14004411d  call    ??1CVolumeLock@@QEAA@XZ; CVolumeLock::~CVolumeLock(void)
0x140044122  nop
0x140044123  lea     rcx, [rbp+arg_10]
0x140044127  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14004412c  nop
0x14004412d  lea     rcx, [rbp+arg_18]
0x140044131  call    ??1?$CComPtrBase@VCVdsEnumObject@@@ATL@@QEAA@XZ; ATL::CComPtrBase<CVdsEnumObject>::~CComPtrBase<CVdsEnumObject>(void)
0x140044136  nop
0x140044137  lea     rcx, [rbp+var_50]
0x14004413b  call    ??1?$CComPtrBase@VCVdsEnumObject@@@ATL@@QEAA@XZ; ATL::CComPtrBase<CVdsEnumObject>::~CComPtrBase<CVdsEnumObject>(void)
0x140044140  nop
0x140044141  lea     rcx, [rbp+var_38]
0x140044145  call    ??1?$CVdsHeapPtr@U_EXTEND_VOLUME_HANDLER_PARAMETER@@@@QEAA@XZ; CVdsHeapPtr<_EXTEND_VOLUME_HANDLER_PARAMETER>::~CVdsHeapPtr<_EXTEND_VOLUME_HANDLER_PARAMETER>(void)
0x14004414a  xor     eax, eax
0x14004414c  mov     rbx, [rsp+80h+arg_0]
0x140044154  add     rsp, 80h
0x14004415b  pop     r15
0x14004415d  pop     r14
0x14004415f  pop     r13
0x140044161  pop     r12
0x140044163  pop     rdi
0x140044164  pop     rsi
0x140044165  pop     rbp
0x140044166  retn
```
