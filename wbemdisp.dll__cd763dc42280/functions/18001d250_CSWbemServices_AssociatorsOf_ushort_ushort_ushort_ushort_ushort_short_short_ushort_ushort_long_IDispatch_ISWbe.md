# CSWbemServices::AssociatorsOf(ushort *,ushort *,ushort *,ushort *,ushort *,short,short,ushort *,ushort *,long,IDispatch *,ISWbemObjectSet * *)

- ea: `0x18001d250`
- end: `0x18001d480`
- name: `?AssociatorsOf@CSWbemServices@@UEAAJPEAG0000FF00JPEAUIDispatch@@PEAPEAUISWbemObjectSet@@@Z`
- size: `560`
- prototype: `__int64 __usercall@<rax>(CSWbemServices *__hidden this@<rcx>, unsigned __int16 *@<rdx>, unsigned __int16 *@<r8>, unsigned __int16 *@<r9>, unsigned __int16 *, unsigned __int16 *, __int16, __int16, unsigned __int16 *, unsigned __int16 *, int, struct IDispatch *, struct ISWbemObjectSet **)`
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
- `0x18000cd1c`
- `0x180013ee0`
- `0x180014f20`
- `0x1800184d4`
- `0x18001d250`
- `0x180036010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18001d2df`
- `OLEAUT32!__imp_SysAllocString` at `0x18001d2df`
- `OLEAUT32!__imp_SysFreeString` at `0x18001d41d`
- `OLEAUT32!__imp_SysFreeString` at `0x18001d426`
- `OLEAUT32!__imp_SysFreeString` at `0x18001d41d`
- `OLEAUT32!__imp_SysFreeString` at `0x18001d426`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18001d3a0`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18001d3a0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CSWbemServices::AssociatorsOf(
        CSWbemServices *this,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        unsigned __int16 *a5,
        unsigned __int16 *a6,
        __int16 a7,
        __int16 a8,
        unsigned __int16 *a9,
        unsigned __int16 *a10,
        unsigned int a11,
        struct IDispatch *a12,
        struct ISWbemObjectSet **a13)
{
  int v15; // ebx
  CSWbemSecurity *v16; // rcx
  struct IUnknown *Proxy; // r14
  struct IWbemContext *IWbemContext; // r15
  OLECHAR *v19; // r13
  OLECHAR *v20; // rdi
  CSWbemSecurity *v21; // rcx
  __int64 v22; // r9
  void *v23; // rax
  CSWbemObjectSet *v24; // rdi
  unsigned int v25; // edx
  bool v27; // [rsp+50h] [rbp-20h] BYREF
  struct IEnumWbemClassObject *v28; // [rsp+58h] [rbp-18h] BYREF
  void *v29; // [rsp+60h] [rbp-10h] BYREF
  OLECHAR *v30; // [rsp+68h] [rbp-8h]

  ResetLastErrors();
  if ( !a13 || !a2 )
  {
    v15 = -2147217400;
LABEL_23:
    CDispatchHelp::RaiseException((CSWbemServices *)((char *)this + 56), v15);
    return (unsigned int)v15;
  }
  v15 = -2147217407;
  v16 = (CSWbemSecurity *)*((_QWORD *)this + 17);
  if ( !v16 )
    goto LABEL_23;
  Proxy = CSWbemSecurity::GetProxy(v16);
  if ( !Proxy )
    goto LABEL_23;
  v28 = 0;
  IWbemContext = CSWbemNamedValueSet::GetIWbemContext(a12, *((struct IServiceProvider **)this + 18));
  v19 = SysAllocString(L"WQL");
  v20 = FormatAssociatorsQuery(a2, a3, a4, a5, a6, a7, a8, a9, a10);
  v30 = v20;
  v27 = 0;
  v29 = 0;
  if ( (unsigned int)CSWbemSecurity::SetSecurity(*((CSWbemSecurity **)this + 17), &v27, &v29) )
  {
    v22 = a11;
    LODWORD(v22) = a11 | 0x100;
    v15 = ((__int64 (__fastcall *)(struct IUnknown *, OLECHAR *, OLECHAR *, __int64, struct IWbemContext *, struct IEnumWbemClassObject **))Proxy->lpVtbl[6].Release)(
            Proxy,
            v19,
            v20,
            v22,
            IWbemContext,
            &v28);
  }
  if ( v27 )
    CSWbemSecurity::ResetSecurity(v21, v29);
  if ( v15 >= 0 )
  {
    v23 = CWin32DefaultArena::WbemMemAlloc(0x80u);
    v29 = v23;
    if ( v23 )
      v24 = CSWbemObjectSet::CSWbemObjectSet((CSWbemObjectSet *)v23, this, v28, 0);
    else
      v24 = 0;
    if ( v24 )
    {
      v15 = (**(__int64 (__fastcall ***)(CSWbemObjectSet *, GUID *, struct ISWbemObjectSet **))v24)(
              v24,
              &IID_ISWbemObjectSet,
              a13);
      if ( v15 < 0 )
        CSWbemObjectSet::`scalar deleting destructor'(v24, v25);
    }
    else
    {
      v15 = -2147217402;
    }
    ((void (__fastcall *)(struct IEnumWbemClassObject *))v28->lpVtbl->Release)(v28);
    v20 = v30;
  }
  SetWbemError((const OLECHAR **)this);
  SysFreeString(v20);
  SysFreeString(v19);
  if ( IWbemContext )
    ((void (__fastcall *)(struct IWbemContext *))IWbemContext->lpVtbl->Release)(IWbemContext);
  ((void (__fastcall *)(struct IUnknown *))Proxy->lpVtbl->Release)(Proxy);
  if ( v15 < 0 )
    goto LABEL_23;
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x18001d250  mov     rax, rsp
0x18001d253  mov     [rax+8], rbx
0x18001d257  mov     [rax+10h], rsi
0x18001d25b  mov     [rax+20h], r9
0x18001d25f  mov     [rax+18h], r8
0x18001d263  push    rbp
0x18001d264  push    rdi
0x18001d265  push    r13
0x18001d267  push    r14
0x18001d269  push    r15
0x18001d26b  mov     rbp, rsp
0x18001d26e  sub     rsp, 70h
0x18001d272  mov     rdi, rdx
0x18001d275  mov     rsi, rcx
0x18001d278  call    ?ResetLastErrors@@YAXXZ; ResetLastErrors(void)
0x18001d27d  cmp     [rbp+arg_60], 0
0x18001d285  jz      loc_18001D455
0x18001d28b  test    rdi, rdi
0x18001d28e  jz      loc_18001D455
0x18001d294  mov     ebx, 80041001h
0x18001d299  mov     rcx, [rsi+88h]; this
0x18001d2a0  test    rcx, rcx
0x18001d2a3  jz      loc_18001D45A
0x18001d2a9  call    ?GetProxy@CSWbemSecurity@@QEAAPEAUIUnknown@@XZ; CSWbemSecurity::GetProxy(void)
0x18001d2ae  mov     r14, rax
0x18001d2b1  test    rax, rax
0x18001d2b4  jz      loc_18001D45A
0x18001d2ba  mov     [rbp+var_18], 0
0x18001d2c2  mov     rdx, [rsi+90h]; struct IServiceProvider *
0x18001d2c9  mov     rcx, [rbp+arg_58]; struct IDispatch *
0x18001d2d0  call    ?GetIWbemContext@CSWbemNamedValueSet@@SAPEAUIWbemContext@@PEAUIDispatch@@PEAUIServiceProvider@@@Z; CSWbemNamedValueSet::GetIWbemContext(IDispatch *,IServiceProvider *)
0x18001d2d5  mov     r15, rax
0x18001d2d8  lea     rcx, aWql; "WQL"
0x18001d2df  call    cs:__imp_SysAllocString
0x18001d2e5  mov     r13, rax
0x18001d2e8  mov     rax, [rbp+arg_48]
0x18001d2ec  mov     [rsp+70h+var_30], rax; unsigned __int16 *
0x18001d2f1  mov     rax, [rbp+arg_40]
0x18001d2f5  mov     [rsp+70h+var_38], rax; unsigned __int16 *
0x18001d2fa  movzx   eax, [rbp+arg_38]
0x18001d2fe  mov     [rsp+70h+var_40], ax; __int16
0x18001d303  movzx   eax, [rbp+arg_30]
0x18001d307  mov     [rsp+70h+var_48], ax; __int16
0x18001d30c  mov     rax, [rbp+arg_28]
0x18001d310  mov     [rsp+70h+var_50], rax; unsigned __int16 *
0x18001d315  mov     r9, [rbp+arg_20]; unsigned __int16 *
0x18001d319  mov     r8, [rbp+arg_18]; unsigned __int16 *
0x18001d31d  mov     rdx, [rbp+arg_10]; unsigned __int16 *
0x18001d321  mov     rcx, rdi; unsigned __int16 *
0x18001d324  call    ?FormatAssociatorsQuery@@YAPEAGPEAG0000FF00@Z; FormatAssociatorsQuery(ushort *,ushort *,ushort *,ushort *,ushort *,short,short,ushort *,ushort *)
0x18001d329  mov     rdi, rax
0x18001d32c  mov     [rbp+var_8], rax
0x18001d330  mov     [rbp+var_20], 0
0x18001d334  mov     [rbp+var_10], 0
0x18001d33c  lea     r8, [rbp+var_10]; void **
0x18001d340  lea     rdx, [rbp+var_20]; bool *
0x18001d344  mov     rcx, [rsi+88h]; this
0x18001d34b  call    ?SetSecurity@CSWbemSecurity@@QEAAHAEA_NAEAPEAX@Z; CSWbemSecurity::SetSecurity(bool &,void * &)
0x18001d350  test    eax, eax
0x18001d352  jz      short loc_18001D388
0x18001d354  mov     rax, [r14]
0x18001d357  mov     r9d, [rbp+arg_50]
0x18001d35e  bts     r9d, 8
0x18001d363  lea     rcx, [rbp+var_18]
0x18001d367  mov     qword ptr [rsp+70h+var_48], rcx
0x18001d36c  mov     [rsp+70h+var_50], r15
0x18001d371  mov     r8, rdi
0x18001d374  mov     rdx, r13
0x18001d377  mov     rcx, r14
0x18001d37a  mov     rax, [rax+0A0h]
0x18001d381  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d386  mov     ebx, eax
0x18001d388  cmp     [rbp+var_20], 0
0x18001d38c  jz      short loc_18001D397
0x18001d38e  mov     rdx, [rbp+var_10]; void *
0x18001d392  call    ?ResetSecurity@CSWbemSecurity@@QEAAXPEAX@Z; CSWbemSecurity::ResetSecurity(void *)
0x18001d397  test    ebx, ebx
0x18001d399  js      short loc_18001D412
0x18001d39b  mov     ecx, 80h
0x18001d3a0  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18001d3a6  mov     [rbp+var_10], rax
0x18001d3aa  test    rax, rax
0x18001d3ad  jz      short loc_18001D3C6
0x18001d3af  xor     r9d, r9d; struct CSWbemSecurity *
0x18001d3b2  mov     r8, [rbp+var_18]; struct IEnumWbemClassObject *
0x18001d3b6  mov     rdx, rsi; struct CSWbemServices *
0x18001d3b9  mov     rcx, rax; this
0x18001d3bc  call    ??0CSWbemObjectSet@@QEAA@PEAVCSWbemServices@@PEAUIEnumWbemClassObject@@PEAVCSWbemSecurity@@@Z; CSWbemObjectSet::CSWbemObjectSet(CSWbemServices *,IEnumWbemClassObject *,CSWbemSecurity *)
0x18001d3c1  mov     rdi, rax
0x18001d3c4  jmp     short loc_18001D3C8
0x18001d3c6  xor     edi, edi
0x18001d3c8  test    rdi, rdi
0x18001d3cb  jnz     short loc_18001D3D4
0x18001d3cd  mov     ebx, 80041006h
0x18001d3d2  jmp     short loc_18001D3FE
0x18001d3d4  mov     rax, [rdi]
0x18001d3d7  mov     r8, [rbp+arg_60]
0x18001d3de  lea     rdx, IID_ISWbemObjectSet
0x18001d3e5  mov     rcx, rdi
0x18001d3e8  mov     rax, [rax]
0x18001d3eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d3f0  mov     ebx, eax
0x18001d3f2  test    eax, eax
0x18001d3f4  jns     short loc_18001D3FE
0x18001d3f6  mov     rcx, rdi; this
0x18001d3f9  call    ??_GCSWbemObjectSet@@QEAAPEAXI@Z; CSWbemObjectSet::`scalar deleting destructor'(uint)
0x18001d3fe  mov     rcx, [rbp+var_18]
0x18001d402  mov     rax, [rcx]
0x18001d405  mov     rax, [rax+10h]
0x18001d409  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d40e  mov     rdi, [rbp+var_8]
0x18001d412  mov     rcx, rsi; this
0x18001d415  call    ?SetWbemError@@YAXPEAVCSWbemServices@@@Z; SetWbemError(CSWbemServices *)
0x18001d41a  mov     rcx, rdi; bstrString
0x18001d41d  call    cs:__imp_SysFreeString
0x18001d423  mov     rcx, r13; bstrString
0x18001d426  call    cs:__imp_SysFreeString
0x18001d42c  test    r15, r15
0x18001d42f  jz      short loc_18001D440
0x18001d431  mov     rax, [r15]
0x18001d434  mov     rcx, r15
0x18001d437  mov     rax, [rax+10h]
0x18001d43b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d440  mov     rax, [r14]
0x18001d443  mov     rcx, r14
0x18001d446  mov     rax, [rax+10h]
0x18001d44a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d44f  test    ebx, ebx
0x18001d451  jns     short loc_18001D465
0x18001d453  jmp     short loc_18001D45A
0x18001d455  mov     ebx, 80041008h
0x18001d45a  lea     rcx, [rsi+38h]; this
0x18001d45e  mov     edx, ebx; int
0x18001d460  call    ?RaiseException@CDispatchHelp@@QEAAXJ@Z; CDispatchHelp::RaiseException(long)
0x18001d465  mov     eax, ebx
0x18001d467  lea     r11, [rsp+70h+var_s0]
0x18001d46c  mov     rbx, [r11+30h]
0x18001d470  mov     rsi, [r11+38h]
0x18001d474  mov     rsp, r11
0x18001d477  pop     r15
0x18001d479  pop     r14
0x18001d47b  pop     r13
0x18001d47d  pop     rdi
0x18001d47e  pop     rbp
0x18001d47f  retn
```
