# CSWbemServices::ReferencesTo(ushort *,ushort *,ushort *,short,short,ushort *,long,IDispatch *,ISWbemObjectSet * *)

- ea: `0x18001e010`
- end: `0x18001e21a`
- name: `?ReferencesTo@CSWbemServices@@UEAAJPEAG00FF0JPEAUIDispatch@@PEAPEAUISWbemObjectSet@@@Z`
- size: `522`
- prototype: `__int64 __usercall@<rax>(CSWbemServices *__hidden this@<rcx>, unsigned __int16 *@<rdx>, unsigned __int16 *@<r8>, unsigned __int16 *@<r9>, __int16, __int16, unsigned __int16 *, int, struct IDispatch *, struct ISWbemObjectSet **)`
- caller_count: `0`
- callee_count: `12`
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
- `0x18001e010`
- `0x1800257ec`
- `0x180036010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18001e099`
- `OLEAUT32!__imp_SysAllocString` at `0x18001e099`
- `OLEAUT32!__imp_SysFreeString` at `0x18001e1b7`
- `OLEAUT32!__imp_SysFreeString` at `0x18001e1c0`
- `OLEAUT32!__imp_SysFreeString` at `0x18001e1b7`
- `OLEAUT32!__imp_SysFreeString` at `0x18001e1c0`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18001e13d`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18001e13d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CSWbemServices::ReferencesTo(
        CSWbemServices *this,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        __int16 a5,
        __int16 a6,
        unsigned __int16 *a7,
        unsigned int a8,
        struct IDispatch *a9,
        struct ISWbemObjectSet **a10)
{
  int v12; // ebx
  CSWbemSecurity *v13; // rcx
  struct IUnknown *Proxy; // r14
  struct IWbemContext *IWbemContext; // r15
  OLECHAR *v16; // r13
  OLECHAR *v17; // rdi
  CSWbemSecurity *v18; // rcx
  __int64 v19; // r9
  void *v20; // rax
  CSWbemObjectSet *v21; // rdi
  unsigned int v22; // edx
  bool v24; // [rsp+40h] [rbp-20h] BYREF
  struct IEnumWbemClassObject *v25; // [rsp+48h] [rbp-18h] BYREF
  void *v26; // [rsp+50h] [rbp-10h] BYREF
  OLECHAR *v27; // [rsp+58h] [rbp-8h]

  ResetLastErrors();
  if ( !a10 || !a2 )
  {
    v12 = -2147217400;
LABEL_23:
    CDispatchHelp::RaiseException((CSWbemServices *)((char *)this + 56), v12);
    return (unsigned int)v12;
  }
  v12 = -2147217407;
  v13 = (CSWbemSecurity *)*((_QWORD *)this + 17);
  if ( !v13 )
    goto LABEL_23;
  Proxy = CSWbemSecurity::GetProxy(v13);
  if ( !Proxy )
    goto LABEL_23;
  v25 = 0;
  IWbemContext = CSWbemNamedValueSet::GetIWbemContext(a9, *((struct IServiceProvider **)this + 18));
  v16 = SysAllocString(L"WQL");
  v17 = FormatReferencesQuery(a2, a3, a4, a5, a6, a7);
  v27 = v17;
  v24 = 0;
  v26 = 0;
  if ( (unsigned int)CSWbemSecurity::SetSecurity(*((CSWbemSecurity **)this + 17), &v24, &v26) )
  {
    v19 = a8;
    LODWORD(v19) = a8 | 0x100;
    v12 = ((__int64 (__fastcall *)(struct IUnknown *, OLECHAR *, OLECHAR *, __int64, struct IWbemContext *, struct IEnumWbemClassObject **))Proxy->lpVtbl[6].Release)(
            Proxy,
            v16,
            v17,
            v19,
            IWbemContext,
            &v25);
  }
  if ( v24 )
    CSWbemSecurity::ResetSecurity(v18, v26);
  if ( v12 >= 0 )
  {
    v20 = CWin32DefaultArena::WbemMemAlloc(0x80u);
    v26 = v20;
    if ( v20 )
      v21 = CSWbemObjectSet::CSWbemObjectSet((CSWbemObjectSet *)v20, this, v25, 0);
    else
      v21 = 0;
    if ( v21 )
    {
      v12 = (**(__int64 (__fastcall ***)(CSWbemObjectSet *, GUID *, struct ISWbemObjectSet **))v21)(
              v21,
              &IID_ISWbemObjectSet,
              a10);
      if ( v12 < 0 )
        CSWbemObjectSet::`scalar deleting destructor'(v21, v22);
    }
    else
    {
      v12 = -2147217402;
    }
    ((void (__fastcall *)(struct IEnumWbemClassObject *))v25->lpVtbl->Release)(v25);
    v17 = v27;
  }
  SetWbemError((const OLECHAR **)this);
  SysFreeString(v17);
  SysFreeString(v16);
  if ( IWbemContext )
    ((void (__fastcall *)(struct IWbemContext *))IWbemContext->lpVtbl->Release)(IWbemContext);
  ((void (__fastcall *)(struct IUnknown *))Proxy->lpVtbl->Release)(Proxy);
  if ( v12 < 0 )
    goto LABEL_23;
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18001e010  mov     rax, rsp
0x18001e013  mov     [rax+8], rbx
0x18001e017  mov     [rax+10h], rsi
0x18001e01b  mov     [rax+20h], r9
0x18001e01f  mov     [rax+18h], r8
0x18001e023  push    rbp
0x18001e024  push    rdi
0x18001e025  push    r13
0x18001e027  push    r14
0x18001e029  push    r15
0x18001e02b  mov     rbp, rsp
0x18001e02e  sub     rsp, 60h
0x18001e032  mov     rdi, rdx
0x18001e035  mov     rsi, rcx
0x18001e038  call    ?ResetLastErrors@@YAXXZ; ResetLastErrors(void)
0x18001e03d  cmp     [rbp+arg_48], 0
0x18001e042  jz      loc_18001E1EF
0x18001e048  test    rdi, rdi
0x18001e04b  jz      loc_18001E1EF
0x18001e051  mov     ebx, 80041001h
0x18001e056  mov     rcx, [rsi+88h]; this
0x18001e05d  test    rcx, rcx
0x18001e060  jz      loc_18001E1F4
0x18001e066  call    ?GetProxy@CSWbemSecurity@@QEAAPEAUIUnknown@@XZ; CSWbemSecurity::GetProxy(void)
0x18001e06b  mov     r14, rax
0x18001e06e  test    rax, rax
0x18001e071  jz      loc_18001E1F4
0x18001e077  mov     [rbp+var_18], 0
0x18001e07f  mov     rdx, [rsi+90h]; struct IServiceProvider *
0x18001e086  mov     rcx, [rbp+arg_40]; struct IDispatch *
0x18001e08a  call    ?GetIWbemContext@CSWbemNamedValueSet@@SAPEAUIWbemContext@@PEAUIDispatch@@PEAUIServiceProvider@@@Z; CSWbemNamedValueSet::GetIWbemContext(IDispatch *,IServiceProvider *)
0x18001e08f  mov     r15, rax
0x18001e092  lea     rcx, aWql; "WQL"
0x18001e099  call    cs:__imp_SysAllocString
0x18001e09f  mov     r13, rax
0x18001e0a2  mov     rax, [rbp+arg_30]
0x18001e0a6  mov     [rsp+60h+var_38], rax; unsigned __int16 *
0x18001e0ab  movzx   eax, [rbp+arg_28]
0x18001e0af  mov     [rsp+60h+var_40], ax; __int16
0x18001e0b4  movzx   r9d, [rbp+arg_20]; __int16
0x18001e0b9  mov     r8, [rbp+arg_18]; unsigned __int16 *
0x18001e0bd  mov     rdx, [rbp+arg_10]; unsigned __int16 *
0x18001e0c1  mov     rcx, rdi; unsigned __int16 *
0x18001e0c4  call    ?FormatReferencesQuery@@YAPEAGPEAG00FF0@Z; FormatReferencesQuery(ushort *,ushort *,ushort *,short,short,ushort *)
0x18001e0c9  mov     rdi, rax
0x18001e0cc  mov     [rbp+var_8], rax
0x18001e0d0  mov     [rbp+var_20], 0
0x18001e0d4  mov     [rbp+var_10], 0
0x18001e0dc  lea     r8, [rbp+var_10]; void **
0x18001e0e0  lea     rdx, [rbp+var_20]; bool *
0x18001e0e4  mov     rcx, [rsi+88h]; this
0x18001e0eb  call    ?SetSecurity@CSWbemSecurity@@QEAAHAEA_NAEAPEAX@Z; CSWbemSecurity::SetSecurity(bool &,void * &)
0x18001e0f0  test    eax, eax
0x18001e0f2  jz      short loc_18001E125
0x18001e0f4  mov     rax, [r14]
0x18001e0f7  mov     r9d, [rbp+arg_38]
0x18001e0fb  bts     r9d, 8
0x18001e100  lea     rcx, [rbp+var_18]
0x18001e104  mov     [rsp+60h+var_38], rcx
0x18001e109  mov     qword ptr [rsp+60h+var_40], r15
0x18001e10e  mov     r8, rdi
0x18001e111  mov     rdx, r13
0x18001e114  mov     rcx, r14
0x18001e117  mov     rax, [rax+0A0h]
0x18001e11e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e123  mov     ebx, eax
0x18001e125  cmp     [rbp+var_20], 0
0x18001e129  jz      short loc_18001E134
0x18001e12b  mov     rdx, [rbp+var_10]; void *
0x18001e12f  call    ?ResetSecurity@CSWbemSecurity@@QEAAXPEAX@Z; CSWbemSecurity::ResetSecurity(void *)
0x18001e134  test    ebx, ebx
0x18001e136  js      short loc_18001E1AC
0x18001e138  mov     ecx, 80h
0x18001e13d  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18001e143  mov     [rbp+var_10], rax
0x18001e147  test    rax, rax
0x18001e14a  jz      short loc_18001E163
0x18001e14c  xor     r9d, r9d; struct CSWbemSecurity *
0x18001e14f  mov     r8, [rbp+var_18]; struct IEnumWbemClassObject *
0x18001e153  mov     rdx, rsi; struct CSWbemServices *
0x18001e156  mov     rcx, rax; this
0x18001e159  call    ??0CSWbemObjectSet@@QEAA@PEAVCSWbemServices@@PEAUIEnumWbemClassObject@@PEAVCSWbemSecurity@@@Z; CSWbemObjectSet::CSWbemObjectSet(CSWbemServices *,IEnumWbemClassObject *,CSWbemSecurity *)
0x18001e15e  mov     rdi, rax
0x18001e161  jmp     short loc_18001E165
0x18001e163  xor     edi, edi
0x18001e165  test    rdi, rdi
0x18001e168  jnz     short loc_18001E171
0x18001e16a  mov     ebx, 80041006h
0x18001e16f  jmp     short loc_18001E198
0x18001e171  mov     rax, [rdi]
0x18001e174  mov     r8, [rbp+arg_48]
0x18001e178  lea     rdx, IID_ISWbemObjectSet
0x18001e17f  mov     rcx, rdi
0x18001e182  mov     rax, [rax]
0x18001e185  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e18a  mov     ebx, eax
0x18001e18c  test    eax, eax
0x18001e18e  jns     short loc_18001E198
0x18001e190  mov     rcx, rdi; this
0x18001e193  call    ??_GCSWbemObjectSet@@QEAAPEAXI@Z; CSWbemObjectSet::`scalar deleting destructor'(uint)
0x18001e198  mov     rcx, [rbp+var_18]
0x18001e19c  mov     rax, [rcx]
0x18001e19f  mov     rax, [rax+10h]
0x18001e1a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e1a8  mov     rdi, [rbp+var_8]
0x18001e1ac  mov     rcx, rsi; this
0x18001e1af  call    ?SetWbemError@@YAXPEAVCSWbemServices@@@Z; SetWbemError(CSWbemServices *)
0x18001e1b4  mov     rcx, rdi; bstrString
0x18001e1b7  call    cs:__imp_SysFreeString
0x18001e1bd  mov     rcx, r13; bstrString
0x18001e1c0  call    cs:__imp_SysFreeString
0x18001e1c6  test    r15, r15
0x18001e1c9  jz      short loc_18001E1DA
0x18001e1cb  mov     rax, [r15]
0x18001e1ce  mov     rcx, r15
0x18001e1d1  mov     rax, [rax+10h]
0x18001e1d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e1da  mov     rax, [r14]
0x18001e1dd  mov     rcx, r14
0x18001e1e0  mov     rax, [rax+10h]
0x18001e1e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e1e9  test    ebx, ebx
0x18001e1eb  jns     short loc_18001E1FF
0x18001e1ed  jmp     short loc_18001E1F4
0x18001e1ef  mov     ebx, 80041008h
0x18001e1f4  lea     rcx, [rsi+38h]; this
0x18001e1f8  mov     edx, ebx; int
0x18001e1fa  call    ?RaiseException@CDispatchHelp@@QEAAXJ@Z; CDispatchHelp::RaiseException(long)
0x18001e1ff  mov     eax, ebx
0x18001e201  lea     r11, [rsp+60h+var_s0]
0x18001e206  mov     rbx, [r11+30h]
0x18001e20a  mov     rsi, [r11+38h]
0x18001e20e  mov     rsp, r11
0x18001e211  pop     r15
0x18001e213  pop     r14
0x18001e215  pop     r13
0x18001e217  pop     rdi
0x18001e218  pop     rbp
0x18001e219  retn
```
