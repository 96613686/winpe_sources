# CSWbemObject::Put_(long,IDispatch *,ISWbemObjectPath * *)

- ea: `0x18002b880`
- end: `0x18002bbf3`
- name: `?Put_@CSWbemObject@@UEAAJJPEAUIDispatch@@PEAPEAUISWbemObjectPath@@@Z`
- size: `883`
- prototype: `int(CSWbemObject *__hidden this, int, struct IDispatch *, struct ISWbemObjectPath **)`
- caller_count: `0`
- callee_count: `12`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x18000311c`
- `0x180003170`
- `0x1800036e0`
- `0x180006300`
- `0x1800077d0`
- `0x180009b14`
- `0x1800112fc`
- `0x180014f20`
- `0x1800184d4`
- `0x180024774`
- `0x18002b880`
- `0x180036010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18002bb5a`
- `OLEAUT32!__imp_SysFreeString` at `0x18002bb5a`
- `OLEAUT32!__imp_VariantInit` at `0x18002b8da`
- `OLEAUT32!__imp_VariantInit` at `0x18002baac`
- `OLEAUT32!__imp_VariantInit` at `0x18002b8da`
- `OLEAUT32!__imp_VariantInit` at `0x18002baac`
- `OLEAUT32!__imp_VariantClear` at `0x18002bb18`
- `OLEAUT32!__imp_VariantClear` at `0x18002bbbf`
- `OLEAUT32!__imp_VariantClear` at `0x18002bb18`
- `OLEAUT32!__imp_VariantClear` at `0x18002bbbf`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18002ba30`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18002ba30`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CSWbemObject::Put_(CSWbemObject *this, int a2, struct IDispatch *a3, struct ISWbemObjectPath **a4)
{
  int v8; // ebx
  struct IWbemContext *IWbemContext; // r12
  struct IWbemServices *IWbemServices; // rsi
  struct IUnknown *v11; // rcx
  CSWbemSecurity *SecurityInfo; // rax
  CSWbemSecurity *v13; // r14
  CSWbemSecurity *v14; // rcx
  struct IWbemServicesVtbl *lpVtbl; // rax
  __int64 v16; // rdx
  __int64 v17; // r8
  int v18; // eax
  CSWbemSecurity *v19; // rax
  struct CSWbemSecurity *v20; // rsi
  OLECHAR *v21; // rax
  CSWbemObjectPath *v22; // rbx
  int v23; // eax
  struct ISWbemObjectPath v24; // r8
  __int64 result; // rax
  CWbemDispatchMgr *v26; // rcx
  int v27; // [rsp+40h] [rbp-39h] BYREF
  struct IUnknown *v28; // [rsp+48h] [rbp-31h] BYREF
  void *v29; // [rsp+50h] [rbp-29h] BYREF
  VARIANTARG v30; // [rsp+58h] [rbp-21h] BYREF
  VARIANTARG pvarg; // [rsp+70h] [rbp-9h] BYREF
  BSTR bstrString; // [rsp+E0h] [rbp+67h] BYREF

  v8 = -2147217407;
  v27 = -2147217407;
  ResetLastErrors();
  if ( *((_QWORD *)this + 7) && *((_QWORD *)this + 8) )
  {
    memset(&pvarg, 0, sizeof(pvarg));
    VariantInit(&pvarg);
    if ( (*(unsigned int (__fastcall **)(_QWORD, const OLECHAR *, _QWORD, VARIANTARG *, _QWORD, _QWORD))(**((_QWORD **)this + 8) + 32LL))(
           *((_QWORD *)this + 8),
           L"__GENUS",
           0,
           &pvarg,
           0,
           0) )
    {
LABEL_43:
      VariantClear(&pvarg);
      goto LABEL_44;
    }
    IWbemContext = CSWbemNamedValueSet::GetIWbemContext(a3, *((struct IServiceProvider **)this + 10));
    IWbemServices = CSWbemServices::GetIWbemServices(*((CSWbemServices **)this + 7));
    v11 = 0;
    v28 = 0;
    if ( IWbemServices )
    {
      SecurityInfo = CSWbemServices::GetSecurityInfo(*((CSWbemServices **)this + 7));
      v13 = SecurityInfo;
      if ( SecurityInfo )
      {
        LOBYTE(bstrString) = 0;
        v29 = 0;
        if ( (unsigned int)CSWbemSecurity::SetSecurity(SecurityInfo, (bool *)&bstrString, &v29) )
        {
          lpVtbl = IWbemServices->lpVtbl;
          v16 = *((_QWORD *)this + 8);
          v17 = a2 | 0x10u;
          if ( pvarg.lVal == 1 )
            v18 = ((__int64 (__fastcall *)(struct IWbemServices *, __int64, __int64, struct IWbemContext *, struct IUnknown **))lpVtbl->PutClass)(
                    IWbemServices,
                    v16,
                    v17,
                    IWbemContext,
                    &v28);
          else
            v18 = ((__int64 (__fastcall *)(struct IWbemServices *, __int64, __int64, struct IWbemContext *, struct IUnknown **))lpVtbl->PutInstance)(
                    IWbemServices,
                    v16,
                    v17,
                    IWbemContext,
                    &v28);
          v8 = v18;
        }
        if ( (_BYTE)bstrString )
          CSWbemSecurity::ResetSecurity(v14, v29);
        (*(void (__fastcall **)(CSWbemSecurity *))(*(_QWORD *)v13 + 16LL))(v13);
      }
      ((void (__fastcall *)(struct IWbemServices *))IWbemServices->lpVtbl->Release)(IWbemServices);
      if ( !v8 )
      {
        v19 = CSWbemServices::GetSecurityInfo(*((CSWbemServices **)this + 7));
        v20 = v19;
        if ( v19 )
          CSWbemSecurity::SecureInterface(v19, v28);
        if ( !((unsigned int (__fastcall *)(struct IUnknown *, __int64, int *))v28->lpVtbl[2].QueryInterface)(
                v28,
                0xFFFFFFFFLL,
                &v27)
          && !v27
          && a4 )
        {
          v21 = (OLECHAR *)CWin32DefaultArena::WbemMemAlloc(0x98u);
          bstrString = v21;
          if ( v21 )
            v22 = CSWbemObjectPath::CSWbemObjectPath(
                    (CSWbemObjectPath *)v21,
                    v20,
                    *(unsigned __int16 **)(*((_QWORD *)this + 7) + 48LL));
          else
            v22 = 0;
          if ( v22 )
          {
            (*(void (__fastcall **)(CSWbemObjectPath *))(*(_QWORD *)v22 + 8LL))(v22);
            (*(void (__fastcall **)(CSWbemObjectPath *, _QWORD))(*(_QWORD *)v22 + 64LL))(
              v22,
              *(_QWORD *)(*((_QWORD *)this + 7) + 40LL));
            if ( pvarg.lVal == 1 )
            {
              memset(&v30, 0, sizeof(v30));
              VariantInit(&v30);
              if ( (*(unsigned int (__fastcall **)(_QWORD, const OLECHAR *, _QWORD, VARIANTARG *, _QWORD, _QWORD))(**((_QWORD **)this + 8) + 32LL))(
                     *((_QWORD *)this + 8),
                     L"__CLASS",
                     0,
                     &v30,
                     0,
                     0)
                || v30.vt != 8 )
              {
                (*(void (__fastcall **)(CSWbemObjectPath *))(*(_QWORD *)v22 + 16LL))(v22);
              }
              else
              {
                (*(void (__fastcall **)(CSWbemObjectPath *, LONGLONG))(*(_QWORD *)v22 + 152LL))(v22, v30.llVal);
                *a4 = (struct ISWbemObjectPath *)v22;
              }
              VariantClear(&v30);
            }
            else
            {
              bstrString = 0;
              v23 = ((__int64 (__fastcall *)(struct IUnknown *, __int64, BSTR *))v28->lpVtbl[1].AddRef)(
                      v28,
                      0xFFFFFFFFLL,
                      &bstrString);
              v24.lpVtbl = *(struct ISWbemObjectPathVtbl **)v22;
              if ( v23 )
              {
                ((void (__fastcall *)(CSWbemObjectPath *))v24.lpVtbl->Release)(v22);
              }
              else
              {
                ((void (__fastcall *)(CSWbemObjectPath *, BSTR))v24.lpVtbl->put_RelPath)(v22, bstrString);
                *a4 = (struct ISWbemObjectPath *)v22;
                SysFreeString(bstrString);
              }
            }
          }
          else
          {
            v27 = -2147217402;
          }
        }
        if ( v20 )
          (*(void (__fastcall **)(struct CSWbemSecurity *))(*(_QWORD *)v20 + 16LL))(v20);
        v11 = v28;
        goto LABEL_39;
      }
      v11 = v28;
    }
    v27 = v8;
LABEL_39:
    if ( v11 )
      ((void (__fastcall *)(struct IUnknown *))v11->lpVtbl->Release)(v11);
    SetWbemError(*((const OLECHAR ***)this + 7));
    if ( IWbemContext )
      ((void (__fastcall *)(struct IWbemContext *))IWbemContext->lpVtbl->Release)(IWbemContext);
    goto LABEL_43;
  }
LABEL_44:
  result = (unsigned int)v27;
  if ( v27 < 0 )
  {
    v26 = (CWbemDispatchMgr *)*((_QWORD *)this + 9);
    if ( v26 )
    {
      CWbemDispatchMgr::RaiseException(v26, v27);
      return (unsigned int)v27;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18002b880  push    rbp
0x18002b882  push    rbx
0x18002b883  push    rsi
0x18002b884  push    rdi
0x18002b885  push    r12
0x18002b887  push    r13
0x18002b889  push    r14
0x18002b88b  push    r15
0x18002b88d  lea     rbp, [rsp-1Fh]
0x18002b892  sub     rsp, 98h
0x18002b899  mov     r13, r9
0x18002b89c  mov     rsi, r8
0x18002b89f  mov     r15d, edx
0x18002b8a2  mov     rdi, rcx
0x18002b8a5  mov     ebx, 80041001h
0x18002b8aa  mov     [rbp+57h+var_90], ebx
0x18002b8ad  call    ?ResetLastErrors@@YAXXZ; ResetLastErrors(void)
0x18002b8b2  xor     r14d, r14d
0x18002b8b5  cmp     [rdi+38h], r14
0x18002b8b9  jz      loc_18002BBC5
0x18002b8bf  cmp     [rdi+40h], r14
0x18002b8c3  jz      loc_18002BBC5
0x18002b8c9  xorps   xmm0, xmm0
0x18002b8cc  xor     eax, eax
0x18002b8ce  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x18002b8d2  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x18002b8d6  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18002b8da  call    cs:__imp_VariantInit
0x18002b8e0  mov     rcx, [rdi+40h]
0x18002b8e4  mov     rax, [rcx]
0x18002b8e7  mov     [rsp+0D0h+var_A8], r14
0x18002b8ec  mov     [rsp+0D0h+var_B0], r14
0x18002b8f1  lea     r9, [rbp+57h+pvarg]
0x18002b8f5  xor     r8d, r8d
0x18002b8f8  lea     rdx, aGenus; "__GENUS"
0x18002b8ff  mov     rax, [rax+20h]
0x18002b903  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b908  test    eax, eax
0x18002b90a  jnz     loc_18002BBBB
0x18002b910  mov     rdx, [rdi+50h]; struct IServiceProvider *
0x18002b914  mov     rcx, rsi; struct IDispatch *
0x18002b917  call    ?GetIWbemContext@CSWbemNamedValueSet@@SAPEAUIWbemContext@@PEAUIDispatch@@PEAUIServiceProvider@@@Z; CSWbemNamedValueSet::GetIWbemContext(IDispatch *,IServiceProvider *)
0x18002b91c  mov     r12, rax
0x18002b91f  mov     rcx, [rdi+38h]; this
0x18002b923  call    ?GetIWbemServices@CSWbemServices@@QEAAPEAUIWbemServices@@XZ; CSWbemServices::GetIWbemServices(void)
0x18002b928  mov     rsi, rax
0x18002b92b  mov     ecx, r14d
0x18002b92e  mov     [rbp+57h+var_88], rcx
0x18002b932  test    rax, rax
0x18002b935  jz      loc_18002BB89
0x18002b93b  mov     rcx, [rdi+38h]; this
0x18002b93f  call    ?GetSecurityInfo@CSWbemServices@@QEAAPEAVCSWbemSecurity@@XZ; CSWbemServices::GetSecurityInfo(void)
0x18002b944  mov     r14, rax
0x18002b947  test    rax, rax
0x18002b94a  jz      short loc_18002B9BE
0x18002b94c  mov     byte ptr [rbp+57h+bstrString], 0
0x18002b950  mov     [rbp+57h+var_80], 0
0x18002b958  lea     r8, [rbp+57h+var_80]; void **
0x18002b95c  lea     rdx, [rbp+57h+bstrString]; bool *
0x18002b960  mov     rcx, rax; this
0x18002b963  call    ?SetSecurity@CSWbemSecurity@@QEAAHAEA_NAEAPEAX@Z; CSWbemSecurity::SetSecurity(bool &,void * &)
0x18002b968  test    eax, eax
0x18002b96a  jz      short loc_18002B9A0
0x18002b96c  mov     rax, [rsi]
0x18002b96f  or      r15d, 10h
0x18002b973  mov     rdx, [rdi+40h]
0x18002b977  lea     rcx, [rbp+57h+var_88]
0x18002b97b  mov     r9, r12
0x18002b97e  mov     r8d, r15d
0x18002b981  mov     [rsp+0D0h+var_B0], rcx
0x18002b986  mov     rcx, rsi
0x18002b989  cmp     dword ptr [rbp+57h+pvarg+8], 1
0x18002b98d  jnz     short loc_18002B995
0x18002b98f  mov     rax, [rax+40h]
0x18002b993  jmp     short loc_18002B999
0x18002b995  mov     rax, [rax+70h]
0x18002b999  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b99e  mov     ebx, eax
0x18002b9a0  cmp     byte ptr [rbp+57h+bstrString], 0
0x18002b9a4  jz      short loc_18002B9AF
0x18002b9a6  mov     rdx, [rbp+57h+var_80]; void *
0x18002b9aa  call    ?ResetSecurity@CSWbemSecurity@@QEAAXPEAX@Z; CSWbemSecurity::ResetSecurity(void *)
0x18002b9af  mov     rax, [r14]
0x18002b9b2  mov     rcx, r14
0x18002b9b5  mov     rax, [rax+10h]
0x18002b9b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b9be  mov     rax, [rsi]
0x18002b9c1  mov     rcx, rsi
0x18002b9c4  mov     rax, [rax+10h]
0x18002b9c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b9cd  xor     r14d, r14d
0x18002b9d0  test    ebx, ebx
0x18002b9d2  jnz     loc_18002BB85
0x18002b9d8  mov     rcx, [rdi+38h]; this
0x18002b9dc  call    ?GetSecurityInfo@CSWbemServices@@QEAAPEAVCSWbemSecurity@@XZ; CSWbemServices::GetSecurityInfo(void)
0x18002b9e1  mov     rsi, rax
0x18002b9e4  test    rax, rax
0x18002b9e7  jz      short loc_18002B9F5
0x18002b9e9  mov     rdx, [rbp+57h+var_88]; struct IUnknown *
0x18002b9ed  mov     rcx, rax; this
0x18002b9f0  call    ?SecureInterface@CSWbemSecurity@@QEAAXPEAUIUnknown@@@Z; CSWbemSecurity::SecureInterface(IUnknown *)
0x18002b9f5  mov     rcx, [rbp+57h+var_88]
0x18002b9f9  mov     rdx, [rcx]
0x18002b9fc  mov     rax, [rdx+30h]
0x18002ba00  lea     r8, [rbp+57h+var_90]
0x18002ba04  or      r15d, 0FFFFFFFFh
0x18002ba08  mov     edx, r15d
0x18002ba0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ba10  test    eax, eax
0x18002ba12  jnz     loc_18002BB6B
0x18002ba18  cmp     [rbp+57h+var_90], r14d
0x18002ba1c  jnz     loc_18002BB6B
0x18002ba22  test    r13, r13
0x18002ba25  jz      loc_18002BB6B
0x18002ba2b  mov     ecx, 98h
0x18002ba30  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18002ba36  mov     [rbp+57h+bstrString], rax
0x18002ba3a  test    rax, rax
0x18002ba3d  jz      short loc_18002BA57
0x18002ba3f  mov     r8, [rdi+38h]
0x18002ba43  mov     r8, [r8+30h]; unsigned __int16 *
0x18002ba47  mov     rdx, rsi; struct CSWbemSecurity *
0x18002ba4a  mov     rcx, rax; this
0x18002ba4d  call    ??0CSWbemObjectPath@@QEAA@PEAVCSWbemSecurity@@PEAG@Z; CSWbemObjectPath::CSWbemObjectPath(CSWbemSecurity *,ushort *)
0x18002ba52  mov     rbx, rax
0x18002ba55  jmp     short loc_18002BA5A
0x18002ba57  mov     rbx, r14
0x18002ba5a  test    rbx, rbx
0x18002ba5d  jnz     short loc_18002BA6B
0x18002ba5f  mov     [rbp+57h+var_90], 80041006h
0x18002ba66  jmp     loc_18002BB6B
0x18002ba6b  mov     rax, [rbx]
0x18002ba6e  mov     rcx, rbx
0x18002ba71  mov     rax, [rax+8]
0x18002ba75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ba7a  mov     rax, [rbx]
0x18002ba7d  mov     rdx, [rdi+38h]
0x18002ba81  mov     rdx, [rdx+28h]
0x18002ba85  mov     rcx, rbx
0x18002ba88  mov     rax, [rax+40h]
0x18002ba8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ba91  cmp     dword ptr [rbp+57h+pvarg+8], 1
0x18002ba95  jnz     loc_18002BB20
0x18002ba9b  xorps   xmm0, xmm0
0x18002ba9e  xor     eax, eax
0x18002baa0  movups  xmmword ptr [rbp+57h+var_78], xmm0
0x18002baa4  mov     qword ptr [rbp+57h+var_78+10h], rax
0x18002baa8  lea     rcx, [rbp+57h+var_78]; pvarg
0x18002baac  call    cs:__imp_VariantInit
0x18002bab2  mov     rcx, [rdi+40h]
0x18002bab6  mov     rax, [rcx]
0x18002bab9  mov     [rsp+0D0h+var_A8], r14
0x18002babe  mov     [rsp+0D0h+var_B0], r14
0x18002bac3  lea     r9, [rbp+57h+var_78]
0x18002bac7  xor     r8d, r8d
0x18002baca  lea     rdx, aClass; "__CLASS"
0x18002bad1  mov     rax, [rax+20h]
0x18002bad5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bada  test    eax, eax
0x18002badc  jnz     short loc_18002BB05
0x18002bade  mov     eax, 8
0x18002bae3  cmp     ax, word ptr [rbp+57h+var_78]
0x18002bae7  jnz     short loc_18002BB05
0x18002bae9  mov     rax, [rbx]
0x18002baec  mov     rdx, qword ptr [rbp+57h+var_78+8]
0x18002baf0  mov     rcx, rbx
0x18002baf3  mov     rax, [rax+98h]
0x18002bafa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002baff  mov     [r13+0], rbx
0x18002bb03  jmp     short loc_18002BB14
0x18002bb05  mov     rax, [rbx]
0x18002bb08  mov     rcx, rbx
0x18002bb0b  mov     rax, [rax+10h]
0x18002bb0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bb14  lea     rcx, [rbp+57h+var_78]; pvarg
0x18002bb18  call    cs:__imp_VariantClear
0x18002bb1e  jmp     short loc_18002BB6B
0x18002bb20  mov     [rbp+57h+bstrString], r14
0x18002bb24  mov     rcx, [rbp+57h+var_88]
0x18002bb28  mov     rax, [rcx]
0x18002bb2b  lea     r8, [rbp+57h+bstrString]
0x18002bb2f  mov     edx, r15d
0x18002bb32  mov     rax, [rax+20h]
0x18002bb36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bb3b  mov     r8, [rbx]
0x18002bb3e  mov     rcx, rbx
0x18002bb41  test    eax, eax
0x18002bb43  jnz     short loc_18002BB62
0x18002bb45  mov     rdx, [rbp+57h+bstrString]
0x18002bb49  mov     rax, [r8+50h]
0x18002bb4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bb52  mov     [r13+0], rbx
0x18002bb56  mov     rcx, [rbp+57h+bstrString]; bstrString
0x18002bb5a  call    cs:__imp_SysFreeString
0x18002bb60  jmp     short loc_18002BB6B
0x18002bb62  mov     rax, [r8+10h]
0x18002bb66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bb6b  test    rsi, rsi
0x18002bb6e  jz      short loc_18002BB7F
0x18002bb70  mov     rax, [rsi]
0x18002bb73  mov     rcx, rsi
0x18002bb76  mov     rax, [rax+10h]
0x18002bb7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bb7f  mov     rcx, [rbp+57h+var_88]
0x18002bb83  jmp     short loc_18002BB8C
0x18002bb85  mov     rcx, [rbp+57h+var_88]
0x18002bb89  mov     [rbp+57h+var_90], ebx
0x18002bb8c  test    rcx, rcx
0x18002bb8f  jz      short loc_18002BB9D
0x18002bb91  mov     rax, [rcx]
0x18002bb94  mov     rax, [rax+10h]
0x18002bb98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bb9d  mov     rcx, [rdi+38h]; this
0x18002bba1  call    ?SetWbemError@@YAXPEAVCSWbemServices@@@Z; SetWbemError(CSWbemServices *)
0x18002bba6  test    r12, r12
0x18002bba9  jz      short loc_18002BBBB
0x18002bbab  mov     rax, [r12]
0x18002bbaf  mov     rcx, r12
0x18002bbb2  mov     rax, [rax+10h]
0x18002bbb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bbbb  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18002bbbf  call    cs:__imp_VariantClear
0x18002bbc5  mov     eax, [rbp+57h+var_90]
0x18002bbc8  test    eax, eax
0x18002bbca  jns     short loc_18002BBDF
0x18002bbcc  mov     rcx, [rdi+48h]; this
0x18002bbd0  test    rcx, rcx
0x18002bbd3  jz      short loc_18002BBDF
0x18002bbd5  mov     edx, eax; int
0x18002bbd7  call    ?RaiseException@CWbemDispatchMgr@@QEAAXJ@Z; CWbemDispatchMgr::RaiseException(long)
0x18002bbdc  mov     eax, [rbp+57h+var_90]
0x18002bbdf  add     rsp, 98h
0x18002bbe6  pop     r15
0x18002bbe8  pop     r14
0x18002bbea  pop     r13
0x18002bbec  pop     r12
0x18002bbee  pop     rdi
0x18002bbef  pop     rsi
0x18002bbf0  pop     rbx
0x18002bbf1  pop     rbp
0x18002bbf2  retn
```
