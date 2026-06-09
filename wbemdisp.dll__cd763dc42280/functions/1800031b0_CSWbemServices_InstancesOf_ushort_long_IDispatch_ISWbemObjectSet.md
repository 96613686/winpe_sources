# CSWbemServices::InstancesOf(ushort *,long,IDispatch *,ISWbemObjectSet * *)

- ea: `0x1800031b0`
- end: `0x18000341a`
- name: `?InstancesOf@CSWbemServices@@UEAAJPEAGJPEAUIDispatch@@PEAPEAUISWbemObjectSet@@@Z`
- size: `618`
- prototype: `__int64 __usercall@<rax>(CSWbemServices *__hidden this@<rcx>, unsigned __int16 *@<rdx>, int@<r8d>, struct IDispatch *@<r9>, struct ISWbemObjectSet **)`
- caller_count: `0`
- callee_count: `10`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x1800031b0`
- `0x1800036b0`
- `0x1800036e0`
- `0x1800050dc`
- `0x180006300`
- `0x1800077d0`
- `0x180009fd0`
- `0x180013ee0`
- `0x1800184d4`
- `0x180036010`

## import_xrefs

- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800032ee`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800032ee`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CSWbemServices::InstancesOf(
        CSWbemServices *this,
        unsigned __int16 *a2,
        unsigned int a3,
        struct IDispatch *a4,
        struct ISWbemObjectSet **a5)
{
  int v8; // ebx
  CSWbemSecurity *v9; // rcx
  __int64 v10; // r14
  CSWbemSecurity *v11; // rcx
  struct IUnknown *Proxy; // r15
  __int64 v14; // rcx
  void *v15; // rax
  CSWbemObjectSet *v16; // rdi
  unsigned int v17; // edx
  bool v18; // [rsp+30h] [rbp-30h] BYREF
  __int64 v19; // [rsp+38h] [rbp-28h] BYREF
  __int64 v20; // [rsp+40h] [rbp-20h] BYREF
  struct IEnumWbemClassObject *v21; // [rsp+48h] [rbp-18h] BYREF
  void *v22; // [rsp+50h] [rbp-10h] BYREF

  ResetLastErrors();
  if ( !a5 )
  {
    v8 = -2147217400;
LABEL_3:
    CDispatchHelp::RaiseException((CSWbemServices *)((char *)this + 56), v8);
    return (unsigned int)v8;
  }
  v8 = -2147217407;
  v9 = (CSWbemSecurity *)*((_QWORD *)this + 17);
  if ( !v9 )
    goto LABEL_3;
  Proxy = CSWbemSecurity::GetProxy(v9);
  if ( !Proxy )
    goto LABEL_3;
  v21 = 0;
  v14 = *((_QWORD *)this + 18);
  v19 = 0;
  v20 = 0;
  if ( v14
    && (*(int (__fastcall **)(__int64, GUID *, GUID *, __int64 *))(*(_QWORD *)v14 + 24LL))(
         v14,
         &IID_IWbemContext,
         &IID_IWbemContext,
         &v19) < 0 )
  {
    v19 = 0;
  }
  if ( a4
    && !v19
    && ((__int64 (__fastcall *)(struct IDispatch *, GUID *, __int64 *))a4->lpVtbl->QueryInterface)(
         a4,
         &IID_ISWbemInternalContext,
         &v20) >= 0 )
  {
    (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v20 + 24LL))(v20, &v19);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
  }
  v10 = v19;
  v18 = 0;
  v22 = 0;
  if ( (unsigned int)CSWbemSecurity::SetSecurity(*((CSWbemSecurity **)this + 17), &v18, &v22) )
    v8 = ((__int64 (__fastcall *)(struct IUnknown *, unsigned __int16 *, _QWORD, __int64, struct IEnumWbemClassObject **))Proxy->lpVtbl[6].QueryInterface)(
           Proxy,
           a2,
           a3,
           v10,
           &v21);
  if ( v18 )
    CSWbemSecurity::ResetSecurity(v11, v22);
  if ( v8 >= 0 )
  {
    v15 = CWin32DefaultArena::WbemMemAlloc(0x80u);
    v22 = v15;
    if ( v15 )
      v16 = CSWbemObjectSet::CSWbemObjectSet((CSWbemObjectSet *)v15, this, v21, 0);
    else
      v16 = 0;
    if ( v16 )
    {
      v8 = (**(__int64 (__fastcall ***)(CSWbemObjectSet *, GUID *, struct ISWbemObjectSet **))v16)(
             v16,
             &IID_ISWbemObjectSet,
             a5);
      if ( v8 < 0 )
        CSWbemObjectSet::`scalar deleting destructor'(v16, v17);
    }
    else
    {
      v8 = -2147217402;
    }
    ((void (__fastcall *)(struct IEnumWbemClassObject *))v21->lpVtbl->Release)(v21);
  }
  SetWbemError((const OLECHAR **)this);
  if ( v10 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
  ((void (__fastcall *)(struct IUnknown *))Proxy->lpVtbl->Release)(Proxy);
  if ( v8 < 0 )
    goto LABEL_3;
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800031b0  mov     [rsp-28h+arg_0], rbx
0x1800031b5  mov     [rsp-28h+arg_10], rsi
0x1800031ba  mov     [rsp-28h+arg_8], rdx
0x1800031bf  push    rbp
0x1800031c0  push    rdi
0x1800031c1  push    r13
0x1800031c3  push    r14
0x1800031c5  push    r15
0x1800031c7  mov     rbp, rsp
0x1800031ca  sub     rsp, 60h
0x1800031ce  mov     rdi, r9
0x1800031d1  mov     r13d, r8d
0x1800031d4  mov     rsi, rcx
0x1800031d7  call    ?ResetLastErrors@@YAXXZ; ResetLastErrors(void)
0x1800031dc  xor     r14d, r14d
0x1800031df  cmp     [rbp+arg_20], r14
0x1800031e3  jz      loc_180003383
0x1800031e9  mov     ebx, 80041001h
0x1800031ee  mov     rcx, [rsi+88h]; this
0x1800031f5  test    rcx, rcx
0x1800031f8  jnz     loc_180003291
0x1800031fe  lea     rcx, [rsi+38h]; this
0x180003202  mov     edx, ebx; int
0x180003204  call    ?RaiseException@CDispatchHelp@@QEAAXJ@Z; CDispatchHelp::RaiseException(long)
0x180003209  jmp     short loc_180003276
0x18000320b  test    rdi, rdi
0x18000320e  jnz     loc_18000338D
0x180003214  mov     r14, [rbp+var_28]
0x180003218  mov     [rbp+var_30], 0
0x18000321c  mov     [rbp+var_10], 0
0x180003224  lea     r8, [rbp+var_10]; void **
0x180003228  lea     rdx, [rbp+var_30]; bool *
0x18000322c  mov     rcx, [rsi+88h]; this
0x180003233  call    ?SetSecurity@CSWbemSecurity@@QEAAHAEA_NAEAPEAX@Z; CSWbemSecurity::SetSecurity(bool &,void * &)
0x180003238  test    eax, eax
0x18000323a  jnz     loc_180003357
0x180003240  cmp     [rbp+var_30], 0
0x180003244  jnz     loc_1800033E1
0x18000324a  test    ebx, ebx
0x18000324c  jns     loc_1800032E9
0x180003252  mov     rcx, rsi; this
0x180003255  call    ?SetWbemError@@YAXPEAVCSWbemServices@@@Z; SetWbemError(CSWbemServices *)
0x18000325a  test    r14, r14
0x18000325d  jnz     loc_180003406
0x180003263  mov     rax, [r15]
0x180003266  mov     rcx, r15
0x180003269  mov     rax, [rax+10h]
0x18000326d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003272  test    ebx, ebx
0x180003274  js      short loc_1800031FE
0x180003276  mov     eax, ebx
0x180003278  lea     r11, [rsp+60h+var_s0]
0x18000327d  mov     rbx, [r11+30h]
0x180003281  mov     rsi, [r11+40h]
0x180003285  mov     rsp, r11
0x180003288  pop     r15
0x18000328a  pop     r14
0x18000328c  pop     r13
0x18000328e  pop     rdi
0x18000328f  pop     rbp
0x180003290  retn
0x180003291  call    ?GetProxy@CSWbemSecurity@@QEAAPEAUIUnknown@@XZ; CSWbemSecurity::GetProxy(void)
0x180003296  mov     r15, rax
0x180003299  test    rax, rax
0x18000329c  jz      loc_1800031FE
0x1800032a2  mov     [rbp+var_18], r14
0x1800032a6  mov     rcx, [rsi+90h]
0x1800032ad  mov     [rbp+var_28], r14
0x1800032b1  mov     [rbp+var_20], r14
0x1800032b5  test    rcx, rcx
0x1800032b8  jz      loc_18000320B
0x1800032be  mov     rax, [rcx]
0x1800032c1  lea     r9, [rbp+var_28]
0x1800032c5  lea     rdx, IID_IWbemContext
0x1800032cc  mov     r8, rdx
0x1800032cf  mov     rax, [rax+18h]
0x1800032d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800032d8  test    eax, eax
0x1800032da  jns     loc_18000320B
0x1800032e0  mov     [rbp+var_28], r14
0x1800032e4  jmp     loc_18000320B
0x1800032e9  mov     ecx, 80h
0x1800032ee  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x1800032f4  mov     [rbp+var_10], rax
0x1800032f8  test    rax, rax
0x1800032fb  jz      short loc_180003353
0x1800032fd  xor     r9d, r9d; struct CSWbemSecurity *
0x180003300  mov     r8, [rbp+var_18]; struct IEnumWbemClassObject *
0x180003304  mov     rdx, rsi; struct CSWbemServices *
0x180003307  mov     rcx, rax; this
0x18000330a  call    ??0CSWbemObjectSet@@QEAA@PEAVCSWbemServices@@PEAUIEnumWbemClassObject@@PEAVCSWbemSecurity@@@Z; CSWbemObjectSet::CSWbemObjectSet(CSWbemServices *,IEnumWbemClassObject *,CSWbemSecurity *)
0x18000330f  mov     rdi, rax
0x180003312  test    rdi, rdi
0x180003315  jz      loc_1800033EF
0x18000331b  mov     rax, [rdi]
0x18000331e  mov     r8, [rbp+arg_20]
0x180003322  lea     rdx, IID_ISWbemObjectSet
0x180003329  mov     rcx, rdi
0x18000332c  mov     rax, [rax]
0x18000332f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003334  mov     ebx, eax
0x180003336  test    eax, eax
0x180003338  js      loc_1800033F9
0x18000333e  mov     rcx, [rbp+var_18]
0x180003342  mov     rax, [rcx]
0x180003345  mov     rax, [rax+10h]
0x180003349  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000334e  jmp     loc_180003252
0x180003353  xor     edi, edi
0x180003355  jmp     short loc_180003312
0x180003357  mov     rax, [r15]
0x18000335a  lea     rcx, [rbp+var_18]
0x18000335e  mov     [rsp+60h+var_40], rcx
0x180003363  mov     r9, r14
0x180003366  mov     r8d, r13d
0x180003369  mov     rdx, [rbp+arg_8]
0x18000336d  mov     rcx, r15
0x180003370  mov     rax, [rax+90h]
0x180003377  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000337c  mov     ebx, eax
0x18000337e  jmp     loc_180003240
0x180003383  mov     ebx, 80041008h
0x180003388  jmp     loc_1800031FE
0x18000338d  cmp     [rbp+var_28], r14
0x180003391  jnz     loc_180003214
0x180003397  mov     rax, [rdi]
0x18000339a  lea     r8, [rbp+var_20]
0x18000339e  lea     rdx, IID_ISWbemInternalContext
0x1800033a5  mov     rcx, rdi
0x1800033a8  mov     rax, [rax]
0x1800033ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800033b0  test    eax, eax
0x1800033b2  js      loc_180003214
0x1800033b8  mov     rcx, [rbp+var_20]
0x1800033bc  mov     rax, [rcx]
0x1800033bf  lea     rdx, [rbp+var_28]
0x1800033c3  mov     rax, [rax+18h]
0x1800033c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800033cc  mov     rcx, [rbp+var_20]
0x1800033d0  mov     rax, [rcx]
0x1800033d3  mov     rax, [rax+10h]
0x1800033d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800033dc  jmp     loc_180003214
0x1800033e1  mov     rdx, [rbp+var_10]; void *
0x1800033e5  call    ?ResetSecurity@CSWbemSecurity@@QEAAXPEAX@Z; CSWbemSecurity::ResetSecurity(void *)
0x1800033ea  jmp     loc_18000324A
0x1800033ef  mov     ebx, 80041006h
0x1800033f4  jmp     loc_18000333E
0x1800033f9  mov     rcx, rdi; this
0x1800033fc  call    ??_GCSWbemObjectSet@@QEAAPEAXI@Z; CSWbemObjectSet::`scalar deleting destructor'(uint)
0x180003401  jmp     loc_18000333E
0x180003406  mov     rax, [r14]
0x180003409  mov     rcx, r14
0x18000340c  mov     rax, [rax+10h]
0x180003410  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003415  jmp     loc_180003263
```
