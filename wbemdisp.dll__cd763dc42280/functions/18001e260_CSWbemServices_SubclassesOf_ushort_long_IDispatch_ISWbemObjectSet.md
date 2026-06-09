# CSWbemServices::SubclassesOf(ushort *,long,IDispatch *,ISWbemObjectSet * *)

- ea: `0x18001e260`
- end: `0x18001e3ff`
- name: `?SubclassesOf@CSWbemServices@@UEAAJPEAGJPEAUIDispatch@@PEAPEAUISWbemObjectSet@@@Z`
- size: `415`
- prototype: `__int64 __usercall@<rax>(CSWbemServices *__hidden this@<rcx>, unsigned __int16 *@<rdx>, int@<r8d>, struct IDispatch *@<r9>, struct ISWbemObjectSet **)`
- caller_count: `0`
- callee_count: `11`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x1800036b0`
- `0x1800036e0`
- `0x1800050dc`
- `0x180006300`
- `0x1800077d0`
- `0x180009fd0`
- `0x180013ee0`
- `0x180014f20`
- `0x1800184d4`
- `0x18001e260`
- `0x180036010`

## import_xrefs

- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18001e330`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18001e330`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CSWbemServices::SubclassesOf(
        CSWbemServices *this,
        unsigned __int16 *a2,
        unsigned int a3,
        struct IDispatch *a4,
        struct ISWbemObjectSet **a5)
{
  int v9; // ebx
  CSWbemSecurity *v10; // rcx
  struct IUnknown *Proxy; // r14
  struct IWbemContext *IWbemContext; // r15
  CSWbemSecurity *v13; // rcx
  void *v14; // rax
  CSWbemObjectSet *v15; // rdi
  unsigned int v16; // edx
  bool v18; // [rsp+30h] [rbp-58h] BYREF
  struct IEnumWbemClassObject *v19; // [rsp+38h] [rbp-50h] BYREF
  void *v20[9]; // [rsp+40h] [rbp-48h] BYREF

  ResetLastErrors();
  if ( !a5 )
  {
    v9 = -2147217400;
LABEL_20:
    CDispatchHelp::RaiseException((CSWbemServices *)((char *)this + 56), v9);
    return (unsigned int)v9;
  }
  v9 = -2147217407;
  v10 = (CSWbemSecurity *)*((_QWORD *)this + 17);
  if ( !v10 )
    goto LABEL_20;
  Proxy = CSWbemSecurity::GetProxy(v10);
  if ( !Proxy )
    goto LABEL_20;
  v19 = 0;
  IWbemContext = CSWbemNamedValueSet::GetIWbemContext(a4, *((struct IServiceProvider **)this + 18));
  v18 = 0;
  v20[0] = 0;
  if ( (unsigned int)CSWbemSecurity::SetSecurity(*((CSWbemSecurity **)this + 17), &v18, v20) )
  {
    v9 = ((__int64 (__fastcall *)(struct IUnknown *, unsigned __int16 *, _QWORD, struct IWbemContext *, struct IEnumWbemClassObject **))Proxy->lpVtbl[4].QueryInterface)(
           Proxy,
           a2,
           a3,
           IWbemContext,
           &v19);
    if ( v9 >= 0 )
    {
      v14 = CWin32DefaultArena::WbemMemAlloc(0x80u);
      v20[1] = v14;
      if ( v14 )
        v15 = CSWbemObjectSet::CSWbemObjectSet((CSWbemObjectSet *)v14, this, v19, 0);
      else
        v15 = 0;
      if ( v15 )
      {
        v9 = (**(__int64 (__fastcall ***)(CSWbemObjectSet *, GUID *, struct ISWbemObjectSet **))v15)(
               v15,
               &IID_ISWbemObjectSet,
               a5);
        if ( v9 < 0 )
          CSWbemObjectSet::`scalar deleting destructor'(v15, v16);
      }
      else
      {
        v9 = -2147217402;
      }
      ((void (__fastcall *)(struct IEnumWbemClassObject *))v19->lpVtbl->Release)(v19);
    }
  }
  if ( v18 )
    CSWbemSecurity::ResetSecurity(v13, v20[0]);
  SetWbemError((const OLECHAR **)this);
  if ( IWbemContext )
    ((void (__fastcall *)(struct IWbemContext *))IWbemContext->lpVtbl->Release)(IWbemContext);
  ((void (__fastcall *)(struct IUnknown *))Proxy->lpVtbl->Release)(Proxy);
  if ( v9 < 0 )
    goto LABEL_20;
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18001e260  push    rbx
0x18001e262  push    rsi
0x18001e263  push    rdi
0x18001e264  push    r12
0x18001e266  push    r13
0x18001e268  push    r14
0x18001e26a  push    r15
0x18001e26c  sub     rsp, 50h
0x18001e270  mov     rdi, r9
0x18001e273  mov     r12d, r8d
0x18001e276  mov     r13, rdx
0x18001e279  mov     rsi, rcx
0x18001e27c  call    ?ResetLastErrors@@YAXXZ; ResetLastErrors(void)
0x18001e281  cmp     [rsp+88h+arg_20], 0
0x18001e28a  jnz     short loc_18001E296
0x18001e28c  mov     ebx, 80041008h
0x18001e291  jmp     loc_18001E3E2
0x18001e296  mov     ebx, 80041001h
0x18001e29b  mov     rcx, [rsi+88h]; this
0x18001e2a2  test    rcx, rcx
0x18001e2a5  jz      loc_18001E3E2
0x18001e2ab  call    ?GetProxy@CSWbemSecurity@@QEAAPEAUIUnknown@@XZ; CSWbemSecurity::GetProxy(void)
0x18001e2b0  mov     r14, rax
0x18001e2b3  test    rax, rax
0x18001e2b6  jz      loc_18001E3E2
0x18001e2bc  mov     [rsp+88h+var_50], 0
0x18001e2c5  mov     rdx, [rsi+90h]; struct IServiceProvider *
0x18001e2cc  mov     rcx, rdi; struct IDispatch *
0x18001e2cf  call    ?GetIWbemContext@CSWbemNamedValueSet@@SAPEAUIWbemContext@@PEAUIDispatch@@PEAUIServiceProvider@@@Z; CSWbemNamedValueSet::GetIWbemContext(IDispatch *,IServiceProvider *)
0x18001e2d4  mov     r15, rax
0x18001e2d7  mov     [rsp+88h+var_58], 0
0x18001e2dc  mov     [rsp+88h+var_48], 0
0x18001e2e5  lea     r8, [rsp+88h+var_48]; void **
0x18001e2ea  lea     rdx, [rsp+88h+var_58]; bool *
0x18001e2ef  mov     rcx, [rsi+88h]; this
0x18001e2f6  call    ?SetSecurity@CSWbemSecurity@@QEAAHAEA_NAEAPEAX@Z; CSWbemSecurity::SetSecurity(bool &,void * &)
0x18001e2fb  test    eax, eax
0x18001e2fd  jz      loc_18001E3A2
0x18001e303  mov     rax, [r14]
0x18001e306  lea     rcx, [rsp+88h+var_50]
0x18001e30b  mov     [rsp+88h+var_68], rcx
0x18001e310  mov     r9, r15
0x18001e313  mov     r8d, r12d
0x18001e316  mov     rdx, r13
0x18001e319  mov     rcx, r14
0x18001e31c  mov     rax, [rax+60h]
0x18001e320  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e325  mov     ebx, eax
0x18001e327  test    eax, eax
0x18001e329  js      short loc_18001E3A2
0x18001e32b  mov     ecx, 80h
0x18001e330  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18001e336  mov     [rsp+88h+var_40], rax
0x18001e33b  test    rax, rax
0x18001e33e  jz      short loc_18001E358
0x18001e340  xor     r9d, r9d; struct CSWbemSecurity *
0x18001e343  mov     r8, [rsp+88h+var_50]; struct IEnumWbemClassObject *
0x18001e348  mov     rdx, rsi; struct CSWbemServices *
0x18001e34b  mov     rcx, rax; this
0x18001e34e  call    ??0CSWbemObjectSet@@QEAA@PEAVCSWbemServices@@PEAUIEnumWbemClassObject@@PEAVCSWbemSecurity@@@Z; CSWbemObjectSet::CSWbemObjectSet(CSWbemServices *,IEnumWbemClassObject *,CSWbemSecurity *)
0x18001e353  mov     rdi, rax
0x18001e356  jmp     short loc_18001E35A
0x18001e358  xor     edi, edi
0x18001e35a  test    rdi, rdi
0x18001e35d  jnz     short loc_18001E366
0x18001e35f  mov     ebx, 80041006h
0x18001e364  jmp     short loc_18001E391
0x18001e366  mov     rax, [rdi]
0x18001e369  mov     r8, [rsp+88h+arg_20]
0x18001e371  lea     rdx, IID_ISWbemObjectSet
0x18001e378  mov     rcx, rdi
0x18001e37b  mov     rax, [rax]
0x18001e37e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e383  mov     ebx, eax
0x18001e385  test    eax, eax
0x18001e387  jns     short loc_18001E391
0x18001e389  mov     rcx, rdi; this
0x18001e38c  call    ??_GCSWbemObjectSet@@QEAAPEAXI@Z; CSWbemObjectSet::`scalar deleting destructor'(uint)
0x18001e391  mov     rcx, [rsp+88h+var_50]
0x18001e396  mov     rax, [rcx]
0x18001e399  mov     rax, [rax+10h]
0x18001e39d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e3a2  cmp     [rsp+88h+var_58], 0
0x18001e3a7  jz      short loc_18001E3B3
0x18001e3a9  mov     rdx, [rsp+88h+var_48]; void *
0x18001e3ae  call    ?ResetSecurity@CSWbemSecurity@@QEAAXPEAX@Z; CSWbemSecurity::ResetSecurity(void *)
0x18001e3b3  mov     rcx, rsi; this
0x18001e3b6  call    ?SetWbemError@@YAXPEAVCSWbemServices@@@Z; SetWbemError(CSWbemServices *)
0x18001e3bb  test    r15, r15
0x18001e3be  jz      short loc_18001E3CF
0x18001e3c0  mov     rax, [r15]
0x18001e3c3  mov     rcx, r15
0x18001e3c6  mov     rax, [rax+10h]
0x18001e3ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e3cf  mov     rax, [r14]
0x18001e3d2  mov     rcx, r14
0x18001e3d5  mov     rax, [rax+10h]
0x18001e3d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e3de  test    ebx, ebx
0x18001e3e0  jns     short loc_18001E3ED
0x18001e3e2  lea     rcx, [rsi+38h]; this
0x18001e3e6  mov     edx, ebx; int
0x18001e3e8  call    ?RaiseException@CDispatchHelp@@QEAAXJ@Z; CDispatchHelp::RaiseException(long)
0x18001e3ed  mov     eax, ebx
0x18001e3ef  add     rsp, 50h
0x18001e3f3  pop     r15
0x18001e3f5  pop     r14
0x18001e3f7  pop     r13
0x18001e3f9  pop     r12
0x18001e3fb  pop     rdi
0x18001e3fc  pop     rsi
0x18001e3fd  pop     rbx
0x18001e3fe  retn
```
