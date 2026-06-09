# CSWbemServices::Get(ushort *,long,IDispatch *,ISWbemObject * *)

- ea: `0x180002610`
- end: `0x1800028a4`
- name: `?Get@CSWbemServices@@UEAAJPEAGJPEAUIDispatch@@PEAPEAUISWbemObject@@@Z`
- size: `660`
- prototype: `__int64 __usercall@<rax>(CSWbemServices *__hidden this@<rcx>, unsigned __int16 *@<rdx>, int@<r8d>, struct IDispatch *@<r9>, struct ISWbemObject **)`
- caller_count: `0`
- callee_count: `9`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x180002610`
- `0x1800036b0`
- `0x1800036e0`
- `0x1800050dc`
- `0x180006300`
- `0x1800077d0`
- `0x180009320`
- `0x1800184d4`
- `0x180036010`

## import_xrefs

- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800026fb`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800026fb`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CSWbemServices::Get(
        CSWbemServices *this,
        unsigned __int16 *a2,
        unsigned int a3,
        struct IDispatch *a4,
        struct ISWbemObject **a5)
{
  int v9; // ebx
  CSWbemSecurity *v10; // rcx
  struct IUnknown *Proxy; // r15
  __int64 v12; // rcx
  __int64 v13; // r14
  int v14; // eax
  CSWbemSecurity *v15; // rcx
  void *v16; // rax
  CSWbemObject *v17; // rdi
  __int64 v19; // rax
  bool v20[8]; // [rsp+20h] [rbp-50h]
  bool v21; // [rsp+40h] [rbp-30h] BYREF
  __int64 v22; // [rsp+48h] [rbp-28h] BYREF
  __int64 v23; // [rsp+50h] [rbp-20h] BYREF
  struct IWbemClassObject *v24; // [rsp+58h] [rbp-18h] BYREF
  void *v25; // [rsp+60h] [rbp-10h] BYREF

  ResetLastErrors();
  if ( !a5 )
  {
    v9 = -2147217400;
LABEL_27:
    CDispatchHelp::RaiseException((CSWbemServices *)((char *)this + 56), v9);
    return (unsigned int)v9;
  }
  v9 = -2147217407;
  v10 = (CSWbemSecurity *)*((_QWORD *)this + 17);
  if ( !v10 )
    goto LABEL_27;
  Proxy = CSWbemSecurity::GetProxy(v10);
  if ( !Proxy )
    goto LABEL_27;
  v24 = 0;
  v12 = *((_QWORD *)this + 18);
  v22 = 0;
  v23 = 0;
  if ( v12
    && (*(int (__fastcall **)(__int64, GUID *, GUID *, __int64 *))(*(_QWORD *)v12 + 24LL))(
         v12,
         &IID_IWbemContext,
         &IID_IWbemContext,
         &v22) < 0 )
  {
    v22 = 0;
  }
  if ( a4
    && !v22
    && ((__int64 (__fastcall *)(struct IDispatch *, GUID *, __int64 *))a4->lpVtbl->QueryInterface)(
         a4,
         &IID_ISWbemInternalContext,
         &v23) >= 0 )
  {
    (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v23 + 24LL))(v23, &v22);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
  }
  v13 = v22;
  v21 = 0;
  v25 = 0;
  v14 = CSWbemSecurity::SetSecurity(*((CSWbemSecurity **)this + 17), &v21, &v25);
  v15 = 0;
  if ( v14 )
  {
    if ( !a2 )
      goto LABEL_24;
    v19 = -1;
    do
      ++v19;
    while ( a2[v19] );
    if ( !v19 )
LABEL_24:
      a2 = 0;
    v9 = ((__int64 (__fastcall *)(struct IUnknown *, unsigned __int16 *, _QWORD, __int64, struct IWbemClassObject **, _QWORD))Proxy->lpVtbl[2].QueryInterface)(
           Proxy,
           a2,
           a3,
           v13,
           &v24,
           0);
  }
  if ( v21 )
    CSWbemSecurity::ResetSecurity(v15, v25);
  if ( v9 >= 0 )
  {
    v16 = CWin32DefaultArena::WbemMemAlloc(0x78u);
    v25 = v16;
    if ( v16 )
    {
      v20[0] = 0;
      v17 = CSWbemObject::CSWbemObject((CSWbemObject *)v16, this, v24, 0, *(_QWORD *)v20);
    }
    else
    {
      v17 = 0;
    }
    if ( v17 )
    {
      v9 = (**(__int64 (__fastcall ***)(CSWbemObject *, GUID *, struct ISWbemObject **))v17)(v17, &IID_ISWbemObject, a5);
      if ( v9 < 0 )
        (*(void (__fastcall **)(CSWbemObject *, __int64))(*(_QWORD *)v17 + 288LL))(v17, 1);
    }
    else
    {
      v9 = -2147217402;
    }
    ((void (__fastcall *)(struct IWbemClassObject *))v24->lpVtbl->Release)(v24);
  }
  SetWbemError((const OLECHAR **)this);
  if ( v13 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
  ((void (__fastcall *)(struct IUnknown *))Proxy->lpVtbl->Release)(Proxy);
  if ( v9 < 0 )
    goto LABEL_27;
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180002610  push    rbp
0x180002612  push    rbx
0x180002613  push    rsi
0x180002614  push    rdi
0x180002615  push    r13
0x180002617  push    r14
0x180002619  push    r15
0x18000261b  mov     rbp, rsp
0x18000261e  sub     rsp, 70h
0x180002622  mov     r14, r9
0x180002625  mov     r13d, r8d
0x180002628  mov     rdi, rdx
0x18000262b  mov     rsi, rcx
0x18000262e  call    ?ResetLastErrors@@YAXXZ; ResetLastErrors(void)
0x180002633  cmp     [rbp+arg_20], 0
0x180002638  jz      loc_1800027DA
0x18000263e  mov     ebx, 80041001h
0x180002643  mov     rcx, [rsi+88h]; this
0x18000264a  test    rcx, rcx
0x18000264d  jz      loc_1800027DF
0x180002653  call    ?GetProxy@CSWbemSecurity@@QEAAPEAUIUnknown@@XZ; CSWbemSecurity::GetProxy(void)
0x180002658  mov     r15, rax
0x18000265b  test    rax, rax
0x18000265e  jz      loc_1800027DF
0x180002664  mov     [rbp+var_18], 0
0x18000266c  mov     rcx, [rsi+90h]
0x180002673  mov     [rbp+var_28], 0
0x18000267b  mov     [rbp+var_20], 0
0x180002683  test    rcx, rcx
0x180002686  jz      short loc_1800026AE
0x180002688  mov     rax, [rcx]
0x18000268b  lea     r9, [rbp+var_28]
0x18000268f  lea     rdx, IID_IWbemContext
0x180002696  mov     r8, rdx
0x180002699  mov     rax, [rax+18h]
0x18000269d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800026a2  test    eax, eax
0x1800026a4  jns     short loc_1800026AE
0x1800026a6  mov     [rbp+var_28], 0
0x1800026ae  test    r14, r14
0x1800026b1  jnz     loc_1800027EC
0x1800026b7  mov     r14, [rbp+var_28]
0x1800026bb  mov     [rbp+var_30], 0
0x1800026bf  mov     [rbp+var_10], 0
0x1800026c7  lea     r8, [rbp+var_10]; void **
0x1800026cb  lea     rdx, [rbp+var_30]; bool *
0x1800026cf  mov     rcx, [rsi+88h]; this
0x1800026d6  call    ?SetSecurity@CSWbemSecurity@@QEAAHAEA_NAEAPEAX@Z; CSWbemSecurity::SetSecurity(bool &,void * &)
0x1800026db  xor     ecx, ecx; this
0x1800026dd  test    eax, eax
0x1800026df  jnz     loc_18000279E
0x1800026e5  xor     r13d, r13d
0x1800026e8  cmp     [rbp+var_30], r13b
0x1800026ec  jnz     loc_18000285C
0x1800026f2  test    ebx, ebx
0x1800026f4  js      short loc_180002764
0x1800026f6  mov     ecx, 78h ; 'x'
0x1800026fb  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180002701  mov     [rbp+var_10], rax
0x180002705  test    rax, rax
0x180002708  jz      loc_180002799
0x18000270e  mov     [rsp+70h+var_50], r13b; bool
0x180002713  xor     r9d, r9d; struct CSWbemSecurity *
0x180002716  mov     r8, [rbp+var_18]; struct IWbemClassObject *
0x18000271a  mov     rdx, rsi; struct CSWbemServices *
0x18000271d  mov     rcx, rax; this
0x180002720  call    ??0CSWbemObject@@QEAA@PEAVCSWbemServices@@PEAUIWbemClassObject@@PEAVCSWbemSecurity@@_N@Z; CSWbemObject::CSWbemObject(CSWbemServices *,IWbemClassObject *,CSWbemSecurity *,bool)
0x180002725  mov     rdi, rax
0x180002728  test    rdi, rdi
0x18000272b  jz      loc_18000286A
0x180002731  mov     rax, [rdi]
0x180002734  mov     r8, [rbp+arg_20]
0x180002738  lea     rdx, IID_ISWbemObject
0x18000273f  mov     rcx, rdi
0x180002742  mov     rax, [rax]
0x180002745  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000274a  mov     ebx, eax
0x18000274c  test    eax, eax
0x18000274e  js      loc_180002874
0x180002754  mov     rcx, [rbp+var_18]
0x180002758  mov     rax, [rcx]
0x18000275b  mov     rax, [rax+10h]
0x18000275f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002764  mov     rcx, rsi; this
0x180002767  call    ?SetWbemError@@YAXPEAVCSWbemServices@@@Z; SetWbemError(CSWbemServices *)
0x18000276c  test    r14, r14
0x18000276f  jnz     loc_180002890
0x180002775  mov     rax, [r15]
0x180002778  mov     rcx, r15
0x18000277b  mov     rax, [rax+10h]
0x18000277f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002784  test    ebx, ebx
0x180002786  js      short loc_1800027DF
0x180002788  mov     eax, ebx
0x18000278a  add     rsp, 70h
0x18000278e  pop     r15
0x180002790  pop     r14
0x180002792  pop     r13
0x180002794  pop     rdi
0x180002795  pop     rsi
0x180002796  pop     rbx
0x180002797  pop     rbp
0x180002798  retn
0x180002799  mov     rdi, r13
0x18000279c  jmp     short loc_180002728
0x18000279e  mov     rax, [r15]
0x1800027a1  mov     r10, [rax+30h]
0x1800027a5  test    rdi, rdi
0x1800027a8  jnz     loc_180002841
0x1800027ae  mov     rdi, rcx
0x1800027b1  mov     [rsp+70h+var_48], rcx
0x1800027b6  lea     rax, [rbp+var_18]
0x1800027ba  mov     qword ptr [rsp+70h+var_50], rax
0x1800027bf  mov     r9, r14
0x1800027c2  mov     r8d, r13d
0x1800027c5  mov     rdx, rdi
0x1800027c8  mov     rcx, r15
0x1800027cb  mov     rax, r10
0x1800027ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800027d3  mov     ebx, eax
0x1800027d5  jmp     loc_1800026E5
0x1800027da  mov     ebx, 80041008h
0x1800027df  lea     rcx, [rsi+38h]; this
0x1800027e3  mov     edx, ebx; int
0x1800027e5  call    ?RaiseException@CDispatchHelp@@QEAAXJ@Z; CDispatchHelp::RaiseException(long)
0x1800027ea  jmp     short loc_180002788
0x1800027ec  cmp     [rbp+var_28], 0
0x1800027f1  jnz     loc_1800026B7
0x1800027f7  mov     rax, [r14]
0x1800027fa  lea     r8, [rbp+var_20]
0x1800027fe  lea     rdx, IID_ISWbemInternalContext
0x180002805  mov     rcx, r14
0x180002808  mov     rax, [rax]
0x18000280b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002810  test    eax, eax
0x180002812  js      loc_1800026B7
0x180002818  mov     rcx, [rbp+var_20]
0x18000281c  mov     rax, [rcx]
0x18000281f  lea     rdx, [rbp+var_28]
0x180002823  mov     rax, [rax+18h]
0x180002827  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000282c  mov     rcx, [rbp+var_20]
0x180002830  mov     rax, [rcx]
0x180002833  mov     rax, [rax+10h]
0x180002837  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000283c  jmp     loc_1800026B7
0x180002841  or      rax, 0FFFFFFFFFFFFFFFFh
0x180002845  inc     rax
0x180002848  cmp     [rdi+rax*2], cx
0x18000284c  jnz     short loc_180002845
0x18000284e  test    rax, rax
0x180002851  jnz     loc_1800027B1
0x180002857  jmp     loc_1800027AE
0x18000285c  mov     rdx, [rbp+var_10]; void *
0x180002860  call    ?ResetSecurity@CSWbemSecurity@@QEAAXPEAX@Z; CSWbemSecurity::ResetSecurity(void *)
0x180002865  jmp     loc_1800026F2
0x18000286a  mov     ebx, 80041006h
0x18000286f  jmp     loc_180002754
0x180002874  mov     rax, [rdi]
0x180002877  mov     edx, 1
0x18000287c  mov     rcx, rdi
0x18000287f  mov     rax, [rax+120h]
0x180002886  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000288b  jmp     loc_180002754
0x180002890  mov     rax, [r14]
0x180002893  mov     rcx, r14
0x180002896  mov     rax, [rax+10h]
0x18000289a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000289f  jmp     loc_180002775
```
