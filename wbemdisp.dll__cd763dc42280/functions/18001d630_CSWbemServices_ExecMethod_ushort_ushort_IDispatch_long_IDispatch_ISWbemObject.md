# CSWbemServices::ExecMethod(ushort *,ushort *,IDispatch *,long,IDispatch *,ISWbemObject * *)

- ea: `0x18001d630`
- end: `0x18001d820`
- name: `?ExecMethod@CSWbemServices@@UEAAJPEAG0PEAUIDispatch@@J1PEAPEAUISWbemObject@@@Z`
- size: `496`
- prototype: `__int64 __fastcall(CSWbemServices *this, unsigned __int16 *, unsigned __int16 *, struct IDispatch *, unsigned int, struct IDispatch *, struct ISWbemObject **)`
- caller_count: `0`
- callee_count: `11`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x1800036b0`
- `0x1800036e0`
- `0x1800050dc`
- `0x180006300`
- `0x1800077d0`
- `0x180009320`
- `0x180014f20`
- `0x1800184d4`
- `0x18001d630`
- `0x18002b4a0`
- `0x180036010`

## import_xrefs

- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18001d72a`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18001d72a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CSWbemServices::ExecMethod(
        CSWbemServices *this,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        struct IDispatch *a4,
        unsigned int a5,
        struct IDispatch *a6,
        struct ISWbemObject **a7)
{
  int v10; // ebx
  CSWbemSecurity *v11; // rcx
  struct IUnknown *Proxy; // r14
  struct IWbemClassObject *IWbemClassObject; // r15
  struct IWbemContext *IWbemContext; // r12
  CSWbemSecurity *v15; // rcx
  struct ISWbemObject **v16; // r13
  void *v17; // rax
  CSWbemObject *v18; // rdi
  struct IWbemClassObject *v20; // [rsp+50h] [rbp-20h] BYREF
  void *v21[3]; // [rsp+58h] [rbp-18h] BYREF
  bool v22; // [rsp+B0h] [rbp+40h] BYREF
  unsigned __int16 *v23; // [rsp+B8h] [rbp+48h]

  v23 = a2;
  v10 = -2147217407;
  ResetLastErrors();
  v11 = (CSWbemSecurity *)*((_QWORD *)this + 17);
  if ( !v11 )
    goto LABEL_22;
  Proxy = CSWbemSecurity::GetProxy(v11);
  if ( !Proxy )
    goto LABEL_22;
  IWbemClassObject = CSWbemObject::GetIWbemClassObject(a4);
  v20 = 0;
  IWbemContext = CSWbemNamedValueSet::GetIWbemContext(a6, *((struct IServiceProvider **)this + 18));
  v22 = 0;
  v21[0] = 0;
  if ( (unsigned int)CSWbemSecurity::SetSecurity(*((CSWbemSecurity **)this + 17), &v22, v21) )
  {
    v10 = ((__int64 (__fastcall *)(struct IUnknown *, unsigned __int16 *, unsigned __int16 *, _QWORD, struct IWbemContext *, struct IWbemClassObject *, struct IWbemClassObject **, _QWORD))Proxy->lpVtbl[8].QueryInterface)(
            Proxy,
            v23,
            a3,
            a5,
            IWbemContext,
            IWbemClassObject,
            &v20,
            0);
    if ( v10 >= 0 )
    {
      if ( v20 )
      {
        v16 = a7;
        if ( a7 )
        {
          v17 = CWin32DefaultArena::WbemMemAlloc(0x78u);
          v21[1] = v17;
          if ( v17 )
            v18 = CSWbemObject::CSWbemObject((CSWbemObject *)v17, this, v20, 0, 0);
          else
            v18 = 0;
          if ( v18 )
          {
            v10 = (**(__int64 (__fastcall ***)(CSWbemObject *, GUID *, struct ISWbemObject **))v18)(
                    v18,
                    &IID_ISWbemObject,
                    v16);
            if ( v10 < 0 )
              (*(void (__fastcall **)(CSWbemObject *, __int64))(*(_QWORD *)v18 + 288LL))(v18, 1);
          }
          else
          {
            v10 = -2147217402;
          }
        }
        ((void (__fastcall *)(struct IWbemClassObject *))v20->lpVtbl->Release)(v20);
      }
    }
  }
  if ( v22 )
    CSWbemSecurity::ResetSecurity(v15, v21[0]);
  SetWbemError(this);
  if ( IWbemContext )
    ((void (__fastcall *)(struct IWbemContext *))IWbemContext->lpVtbl->Release)(IWbemContext);
  if ( IWbemClassObject )
    ((void (__fastcall *)(struct IWbemClassObject *))IWbemClassObject->lpVtbl->Release)(IWbemClassObject);
  ((void (__fastcall *)(struct IUnknown *))Proxy->lpVtbl->Release)(Proxy);
  if ( v10 < 0 )
LABEL_22:
    CDispatchHelp::RaiseException((CSWbemServices *)((char *)this + 56), v10);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18001d630  mov     [rsp-38h+arg_10], rbx
0x18001d635  mov     [rsp-38h+arg_8], rdx
0x18001d63a  push    rbp
0x18001d63b  push    rsi
0x18001d63c  push    rdi
0x18001d63d  push    r12
0x18001d63f  push    r13
0x18001d641  push    r14
0x18001d643  push    r15
0x18001d645  mov     rbp, rsp
0x18001d648  sub     rsp, 70h
0x18001d64c  mov     rdi, r9
0x18001d64f  mov     r13, r8
0x18001d652  mov     rsi, rcx
0x18001d655  mov     ebx, 80041001h
0x18001d65a  call    ?ResetLastErrors@@YAXXZ; ResetLastErrors(void)
0x18001d65f  mov     rcx, [rsi+88h]; this
0x18001d666  test    rcx, rcx
0x18001d669  jz      loc_18001D7FB
0x18001d66f  call    ?GetProxy@CSWbemSecurity@@QEAAPEAUIUnknown@@XZ; CSWbemSecurity::GetProxy(void)
0x18001d674  mov     r14, rax
0x18001d677  test    rax, rax
0x18001d67a  jz      loc_18001D7FB
0x18001d680  mov     rcx, rdi; struct IDispatch *
0x18001d683  call    ?GetIWbemClassObject@CSWbemObject@@SAPEAUIWbemClassObject@@PEAUIDispatch@@@Z; CSWbemObject::GetIWbemClassObject(IDispatch *)
0x18001d688  mov     r15, rax
0x18001d68b  mov     [rbp+var_20], 0
0x18001d693  mov     rdx, [rsi+90h]; struct IServiceProvider *
0x18001d69a  mov     rcx, [rbp+arg_28]; struct IDispatch *
0x18001d69e  call    ?GetIWbemContext@CSWbemNamedValueSet@@SAPEAUIWbemContext@@PEAUIDispatch@@PEAUIServiceProvider@@@Z; CSWbemNamedValueSet::GetIWbemContext(IDispatch *,IServiceProvider *)
0x18001d6a3  mov     r12, rax
0x18001d6a6  mov     [rbp+arg_0], 0
0x18001d6aa  mov     [rbp+var_18], 0
0x18001d6b2  lea     r8, [rbp+var_18]; void **
0x18001d6b6  lea     rdx, [rbp+arg_0]; bool *
0x18001d6ba  mov     rcx, [rsi+88h]; this
0x18001d6c1  call    ?SetSecurity@CSWbemSecurity@@QEAAHAEA_NAEAPEAX@Z; CSWbemSecurity::SetSecurity(bool &,void * &)
0x18001d6c6  test    eax, eax
0x18001d6c8  jz      loc_18001D7A8
0x18001d6ce  mov     rax, [r14]
0x18001d6d1  mov     [rsp+70h+var_38], 0
0x18001d6da  lea     rcx, [rbp+var_20]
0x18001d6de  mov     [rsp+70h+var_40], rcx
0x18001d6e3  mov     [rsp+70h+var_48], r15
0x18001d6e8  mov     qword ptr [rsp+70h+var_50], r12
0x18001d6ed  mov     r9d, [rbp+arg_20]
0x18001d6f1  mov     r8, r13
0x18001d6f4  mov     rdx, [rbp+arg_8]
0x18001d6f8  mov     rcx, r14
0x18001d6fb  mov     rax, [rax+0C0h]
0x18001d702  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d707  mov     ebx, eax
0x18001d709  test    eax, eax
0x18001d70b  js      loc_18001D7A8
0x18001d711  cmp     [rbp+var_20], 0
0x18001d716  jz      loc_18001D7A8
0x18001d71c  mov     r13, [rbp+arg_30]
0x18001d720  test    r13, r13
0x18001d723  jz      short loc_18001D798
0x18001d725  mov     ecx, 78h ; 'x'
0x18001d72a  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18001d730  mov     [rbp+var_10], rax
0x18001d734  test    rax, rax
0x18001d737  jz      short loc_18001D755
0x18001d739  mov     [rsp+70h+var_50], 0; bool
0x18001d73e  xor     r9d, r9d; struct CSWbemSecurity *
0x18001d741  mov     r8, [rbp+var_20]; struct IWbemClassObject *
0x18001d745  mov     rdx, rsi; struct CSWbemServices *
0x18001d748  mov     rcx, rax; this
0x18001d74b  call    ??0CSWbemObject@@QEAA@PEAVCSWbemServices@@PEAUIWbemClassObject@@PEAVCSWbemSecurity@@_N@Z; CSWbemObject::CSWbemObject(CSWbemServices *,IWbemClassObject *,CSWbemSecurity *,bool)
0x18001d750  mov     rdi, rax
0x18001d753  jmp     short loc_18001D757
0x18001d755  xor     edi, edi
0x18001d757  test    rdi, rdi
0x18001d75a  jnz     short loc_18001D763
0x18001d75c  mov     ebx, 80041006h
0x18001d761  jmp     short loc_18001D798
0x18001d763  mov     rax, [rdi]
0x18001d766  mov     r8, r13
0x18001d769  lea     rdx, IID_ISWbemObject
0x18001d770  mov     rcx, rdi
0x18001d773  mov     rax, [rax]
0x18001d776  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d77b  mov     ebx, eax
0x18001d77d  test    eax, eax
0x18001d77f  jns     short loc_18001D798
0x18001d781  mov     rax, [rdi]
0x18001d784  mov     edx, 1
0x18001d789  mov     rcx, rdi
0x18001d78c  mov     rax, [rax+120h]
0x18001d793  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d798  mov     rcx, [rbp+var_20]
0x18001d79c  mov     rax, [rcx]
0x18001d79f  mov     rax, [rax+10h]
0x18001d7a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d7a8  cmp     [rbp+arg_0], 0
0x18001d7ac  jz      short loc_18001D7B7
0x18001d7ae  mov     rdx, [rbp+var_18]; void *
0x18001d7b2  call    ?ResetSecurity@CSWbemSecurity@@QEAAXPEAX@Z; CSWbemSecurity::ResetSecurity(void *)
0x18001d7b7  mov     rcx, rsi; this
0x18001d7ba  call    ?SetWbemError@@YAXPEAVCSWbemServices@@@Z; SetWbemError(CSWbemServices *)
0x18001d7bf  test    r12, r12
0x18001d7c2  jz      short loc_18001D7D4
0x18001d7c4  mov     rax, [r12]
0x18001d7c8  mov     rcx, r12
0x18001d7cb  mov     rax, [rax+10h]
0x18001d7cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d7d4  test    r15, r15
0x18001d7d7  jz      short loc_18001D7E8
0x18001d7d9  mov     rax, [r15]
0x18001d7dc  mov     rcx, r15
0x18001d7df  mov     rax, [rax+10h]
0x18001d7e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d7e8  mov     rax, [r14]
0x18001d7eb  mov     rcx, r14
0x18001d7ee  mov     rax, [rax+10h]
0x18001d7f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d7f7  test    ebx, ebx
0x18001d7f9  jns     short loc_18001D806
0x18001d7fb  lea     rcx, [rsi+38h]; this
0x18001d7ff  mov     edx, ebx; int
0x18001d801  call    ?RaiseException@CDispatchHelp@@QEAAXJ@Z; CDispatchHelp::RaiseException(long)
0x18001d806  mov     eax, ebx
0x18001d808  mov     rbx, [rsp+70h+arg_10]
0x18001d810  add     rsp, 70h
0x18001d814  pop     r15
0x18001d816  pop     r14
0x18001d818  pop     r13
0x18001d81a  pop     r12
0x18001d81c  pop     rdi
0x18001d81d  pop     rsi
0x18001d81e  pop     rbp
0x18001d81f  retn
```
