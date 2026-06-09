# CSWbemServices::Put(ISWbemObjectEx *,long,IDispatch *,ISWbemObjectPath * *)

- ea: `0x18001dc50`
- end: `0x18001dfbd`
- name: `?Put@CSWbemServices@@UEAAJPEAUISWbemObjectEx@@JPEAUIDispatch@@PEAPEAUISWbemObjectPath@@@Z`
- size: `877`
- prototype: `__int64 __usercall@<rax>(CSWbemServices *__hidden this@<rcx>, struct ISWbemObjectEx *@<rdx>, int@<r8d>, struct IDispatch *@<r9>, struct ISWbemObjectPath **)`
- caller_count: `0`
- callee_count: `12`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x1800036b0`
- `0x1800036e0`
- `0x1800050dc`
- `0x180006300`
- `0x1800077d0`
- `0x180009b14`
- `0x1800112fc`
- `0x180014f20`
- `0x1800184d4`
- `0x18001dc50`
- `0x18002b4a0`
- `0x180036010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18001df1c`
- `OLEAUT32!__imp_SysFreeString` at `0x18001df1c`
- `OLEAUT32!__imp_VariantInit` at `0x18001dcef`
- `OLEAUT32!__imp_VariantInit` at `0x18001de65`
- `OLEAUT32!__imp_VariantInit` at `0x18001dcef`
- `OLEAUT32!__imp_VariantInit` at `0x18001de65`
- `OLEAUT32!__imp_VariantClear` at `0x18001ded7`
- `OLEAUT32!__imp_VariantClear` at `0x18001df6f`
- `OLEAUT32!__imp_VariantClear` at `0x18001ded7`
- `OLEAUT32!__imp_VariantClear` at `0x18001df6f`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18001ddee`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18001ddee`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CSWbemServices::Put(
        CSWbemServices *this,
        struct IDispatch *a2,
        int a3,
        struct IDispatch *a4,
        struct ISWbemObjectPath **a5)
{
  int v9; // ebx
  __int64 result; // rax
  CSWbemSecurity *v11; // rcx
  struct IUnknown *Proxy; // r15
  struct IWbemClassObject *IWbemClassObject; // r14
  struct IWbemContext *IWbemContext; // r12
  struct IUnknownVtbl *lpVtbl; // rax
  __int64 v16; // r8
  int v17; // eax
  CSWbemSecurity *v18; // rcx
  struct ISWbemObjectPath **v19; // rsi
  OLECHAR *v20; // rax
  CSWbemObjectPath *v21; // rbx
  int v22; // eax
  __int64 v23; // r8
  int v24; // [rsp+40h] [rbp-21h] BYREF
  struct IUnknown *v25; // [rsp+48h] [rbp-19h] BYREF
  void *v26; // [rsp+50h] [rbp-11h] BYREF
  VARIANTARG v27; // [rsp+58h] [rbp-9h] BYREF
  VARIANTARG pvarg; // [rsp+70h] [rbp+Fh] BYREF
  BSTR bstrString; // [rsp+C8h] [rbp+67h] BYREF

  v9 = -2147217407;
  v24 = -2147217407;
  ResetLastErrors();
  if ( !a2 )
  {
    LODWORD(result) = -2147217400;
    v24 = -2147217400;
LABEL_39:
    CDispatchHelp::RaiseException((CSWbemServices *)((char *)this + 56), result);
    return (unsigned int)v24;
  }
  v11 = (CSWbemSecurity *)*((_QWORD *)this + 17);
  if ( v11 )
  {
    Proxy = CSWbemSecurity::GetProxy(v11);
    if ( Proxy )
    {
      IWbemClassObject = CSWbemObject::GetIWbemClassObject(a2);
      IWbemContext = CSWbemNamedValueSet::GetIWbemContext(a4, *((struct IServiceProvider **)this + 18));
      if ( IWbemClassObject )
      {
        memset(&pvarg, 0, sizeof(pvarg));
        VariantInit(&pvarg);
        if ( !((unsigned int (__fastcall *)(struct IWbemClassObject *, const OLECHAR *, _QWORD, VARIANTARG *, _QWORD, _QWORD))IWbemClassObject->lpVtbl->Get)(
                IWbemClassObject,
                L"__GENUS",
                0,
                &pvarg,
                0,
                0) )
        {
          v25 = 0;
          LOBYTE(bstrString) = 0;
          v26 = 0;
          if ( !(unsigned int)CSWbemSecurity::SetSecurity(*((CSWbemSecurity **)this + 17), (bool *)&bstrString, &v26) )
            goto LABEL_31;
          lpVtbl = Proxy->lpVtbl;
          v16 = a3 | 0x10u;
          if ( pvarg.lVal == 1 )
            v17 = ((__int64 (__fastcall *)(struct IUnknown *, struct IWbemClassObject *, __int64, struct IWbemContext *, struct IUnknown **))lpVtbl[2].Release)(
                    Proxy,
                    IWbemClassObject,
                    v16,
                    IWbemContext,
                    &v25);
          else
            v17 = ((__int64 (__fastcall *)(struct IUnknown *, struct IWbemClassObject *, __int64, struct IWbemContext *, struct IUnknown **))lpVtbl[4].Release)(
                    Proxy,
                    IWbemClassObject,
                    v16,
                    IWbemContext,
                    &v25);
          v9 = v17;
          if ( (_BYTE)bstrString )
            CSWbemSecurity::ResetSecurity(v18, v26);
          if ( v9 )
          {
LABEL_31:
            v24 = v9;
          }
          else
          {
            CSWbemSecurity::SecureInterface(*((CSWbemSecurity **)this + 17), v25);
            if ( !((unsigned int (__fastcall *)(struct IUnknown *, __int64, int *))v25->lpVtbl[2].QueryInterface)(
                    v25,
                    0xFFFFFFFFLL,
                    &v24)
              && !v24 )
            {
              v19 = a5;
              if ( a5 )
              {
                v20 = (OLECHAR *)CWin32DefaultArena::WbemMemAlloc(0x98u);
                bstrString = v20;
                if ( v20 )
                  v21 = CSWbemObjectPath::CSWbemObjectPath(
                          (CSWbemObjectPath *)v20,
                          *((struct CSWbemSecurity **)this + 17),
                          *((unsigned __int16 **)this + 6));
                else
                  v21 = 0;
                if ( v21 )
                {
                  (*(void (__fastcall **)(CSWbemObjectPath *))(*(_QWORD *)v21 + 8LL))(v21);
                  (*(void (__fastcall **)(CSWbemObjectPath *, _QWORD))(*(_QWORD *)v21 + 64LL))(
                    v21,
                    *((_QWORD *)this + 5));
                  if ( pvarg.lVal == 1 )
                  {
                    memset(&v27, 0, sizeof(v27));
                    VariantInit(&v27);
                    if ( ((unsigned int (__fastcall *)(struct IWbemClassObject *, const OLECHAR *, _QWORD, VARIANTARG *, _QWORD, _QWORD))IWbemClassObject->lpVtbl->Get)(
                           IWbemClassObject,
                           L"__CLASS",
                           0,
                           &v27,
                           0,
                           0)
                      || v27.vt != 8 )
                    {
                      (*(void (__fastcall **)(CSWbemObjectPath *))(*(_QWORD *)v21 + 16LL))(v21);
                    }
                    else
                    {
                      (*(void (__fastcall **)(CSWbemObjectPath *, LONGLONG))(*(_QWORD *)v21 + 152LL))(v21, v27.llVal);
                      *v19 = (struct ISWbemObjectPath *)v21;
                    }
                    VariantClear(&v27);
                  }
                  else
                  {
                    bstrString = 0;
                    v22 = ((__int64 (__fastcall *)(struct IUnknown *, __int64, BSTR *))v25->lpVtbl[1].AddRef)(
                            v25,
                            0xFFFFFFFFLL,
                            &bstrString);
                    v23 = *(_QWORD *)v21;
                    if ( v22 )
                    {
                      (*(void (__fastcall **)(CSWbemObjectPath *))(v23 + 16))(v21);
                    }
                    else
                    {
                      (*(void (__fastcall **)(CSWbemObjectPath *, BSTR))(v23 + 80))(v21, bstrString);
                      *v19 = (struct ISWbemObjectPath *)v21;
                      SysFreeString(bstrString);
                    }
                  }
                }
                else
                {
                  v24 = -2147217402;
                }
              }
            }
          }
          if ( v25 )
            ((void (__fastcall *)(struct IUnknown *))v25->lpVtbl->Release)(v25);
        }
        if ( IWbemContext )
          ((void (__fastcall *)(struct IWbemContext *))IWbemContext->lpVtbl->Release)(IWbemContext);
        ((void (__fastcall *)(struct IWbemClassObject *))IWbemClassObject->lpVtbl->Release)(IWbemClassObject);
        VariantClear(&pvarg);
      }
      SetWbemError((const OLECHAR **)this);
      ((void (__fastcall *)(struct IUnknown *))Proxy->lpVtbl->Release)(Proxy);
    }
  }
  result = (unsigned int)v24;
  if ( v24 < 0 )
    goto LABEL_39;
  return result;
}

```

## disassembly

```asm
0x18001dc50  mov     [rsp-8+arg_0], rbx
0x18001dc55  mov     [rsp-8+arg_10], rsi
0x18001dc5a  push    rbp
0x18001dc5b  push    rdi
0x18001dc5c  push    r12
0x18001dc5e  push    r14
0x18001dc60  push    r15
0x18001dc62  lea     rbp, [rsp-2Fh]
0x18001dc67  sub     rsp, 90h
0x18001dc6e  mov     r12, r9
0x18001dc71  mov     esi, r8d
0x18001dc74  mov     r14, rdx
0x18001dc77  mov     rdi, rcx
0x18001dc7a  mov     ebx, 80041001h
0x18001dc7f  mov     [rbp+4Fh+var_70], ebx
0x18001dc82  call    ?ResetLastErrors@@YAXXZ; ResetLastErrors(void)
0x18001dc87  test    r14, r14
0x18001dc8a  jnz     short loc_18001DC97
0x18001dc8c  lea     eax, [rbx+7]
0x18001dc8f  mov     [rbp+4Fh+var_70], eax
0x18001dc92  jmp     loc_18001DF93
0x18001dc97  mov     rcx, [rdi+88h]; this
0x18001dc9e  test    rcx, rcx
0x18001dca1  jz      loc_18001DF8C
0x18001dca7  call    ?GetProxy@CSWbemSecurity@@QEAAPEAUIUnknown@@XZ; CSWbemSecurity::GetProxy(void)
0x18001dcac  mov     r15, rax
0x18001dcaf  test    rax, rax
0x18001dcb2  jz      loc_18001DF8C
0x18001dcb8  mov     rcx, r14; struct IDispatch *
0x18001dcbb  call    ?GetIWbemClassObject@CSWbemObject@@SAPEAUIWbemClassObject@@PEAUIDispatch@@@Z; CSWbemObject::GetIWbemClassObject(IDispatch *)
0x18001dcc0  mov     r14, rax
0x18001dcc3  mov     rdx, [rdi+90h]; struct IServiceProvider *
0x18001dcca  mov     rcx, r12; struct IDispatch *
0x18001dccd  call    ?GetIWbemContext@CSWbemNamedValueSet@@SAPEAUIWbemContext@@PEAUIDispatch@@PEAUIServiceProvider@@@Z; CSWbemNamedValueSet::GetIWbemContext(IDispatch *,IServiceProvider *)
0x18001dcd2  mov     r12, rax
0x18001dcd5  test    r14, r14
0x18001dcd8  jz      loc_18001DF75
0x18001dcde  xorps   xmm0, xmm0
0x18001dce1  xor     eax, eax
0x18001dce3  movups  xmmword ptr [rbp+4Fh+pvarg], xmm0
0x18001dce7  mov     qword ptr [rbp+4Fh+pvarg+10h], rax
0x18001dceb  lea     rcx, [rbp+4Fh+pvarg]; pvarg
0x18001dcef  call    cs:__imp_VariantInit
0x18001dcf5  mov     rcx, [r14]
0x18001dcf8  mov     rax, [rcx+20h]
0x18001dcfc  mov     [rsp+0B0h+var_88], 0
0x18001dd05  mov     [rsp+0B0h+var_90], 0
0x18001dd0e  lea     r9, [rbp+4Fh+pvarg]
0x18001dd12  xor     r8d, r8d
0x18001dd15  lea     rdx, aGenus; "__GENUS"
0x18001dd1c  mov     rcx, r14
0x18001dd1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dd24  test    eax, eax
0x18001dd26  jnz     loc_18001DF47
0x18001dd2c  mov     [rbp+4Fh+var_68], 0
0x18001dd34  mov     byte ptr [rbp+4Fh+bstrString], al
0x18001dd37  mov     [rbp+4Fh+var_60], 0
0x18001dd3f  lea     r8, [rbp+4Fh+var_60]; void **
0x18001dd43  lea     rdx, [rbp+4Fh+bstrString]; bool *
0x18001dd47  mov     rcx, [rdi+88h]; this
0x18001dd4e  call    ?SetSecurity@CSWbemSecurity@@QEAAHAEA_NAEAPEAX@Z; CSWbemSecurity::SetSecurity(bool &,void * &)
0x18001dd53  test    eax, eax
0x18001dd55  jz      loc_18001DF2F
0x18001dd5b  mov     rax, [r15]
0x18001dd5e  or      esi, 10h
0x18001dd61  lea     rcx, [rbp+4Fh+var_68]
0x18001dd65  mov     r9, r12
0x18001dd68  mov     r8d, esi
0x18001dd6b  mov     rdx, r14
0x18001dd6e  mov     [rsp+0B0h+var_90], rcx
0x18001dd73  mov     rcx, r15
0x18001dd76  cmp     dword ptr [rbp+4Fh+pvarg+8], 1
0x18001dd7a  jnz     short loc_18001DD82
0x18001dd7c  mov     rax, [rax+40h]
0x18001dd80  jmp     short loc_18001DD86
0x18001dd82  mov     rax, [rax+70h]
0x18001dd86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dd8b  mov     ebx, eax
0x18001dd8d  cmp     byte ptr [rbp+4Fh+bstrString], 0
0x18001dd91  jz      short loc_18001DD9C
0x18001dd93  mov     rdx, [rbp+4Fh+var_60]; void *
0x18001dd97  call    ?ResetSecurity@CSWbemSecurity@@QEAAXPEAX@Z; CSWbemSecurity::ResetSecurity(void *)
0x18001dd9c  test    ebx, ebx
0x18001dd9e  jnz     loc_18001DF2F
0x18001dda4  mov     rdx, [rbp+4Fh+var_68]; struct IUnknown *
0x18001dda8  mov     rcx, [rdi+88h]; this
0x18001ddaf  call    ?SecureInterface@CSWbemSecurity@@QEAAXPEAUIUnknown@@@Z; CSWbemSecurity::SecureInterface(IUnknown *)
0x18001ddb4  mov     rcx, [rbp+4Fh+var_68]
0x18001ddb8  mov     rax, [rcx]
0x18001ddbb  lea     r8, [rbp+4Fh+var_70]
0x18001ddbf  or      edx, 0FFFFFFFFh
0x18001ddc2  mov     rax, [rax+30h]
0x18001ddc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ddcb  test    eax, eax
0x18001ddcd  jnz     loc_18001DF32
0x18001ddd3  cmp     [rbp+4Fh+var_70], eax
0x18001ddd6  jnz     loc_18001DF32
0x18001dddc  mov     rsi, [rbp+4Fh+arg_20]
0x18001dde0  test    rsi, rsi
0x18001dde3  jz      loc_18001DF32
0x18001dde9  mov     ecx, 98h
0x18001ddee  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18001ddf4  mov     [rbp+4Fh+bstrString], rax
0x18001ddf8  test    rax, rax
0x18001ddfb  jz      short loc_18001DE15
0x18001ddfd  mov     r8, [rdi+30h]; unsigned __int16 *
0x18001de01  mov     rdx, [rdi+88h]; struct CSWbemSecurity *
0x18001de08  mov     rcx, rax; this
0x18001de0b  call    ??0CSWbemObjectPath@@QEAA@PEAVCSWbemSecurity@@PEAG@Z; CSWbemObjectPath::CSWbemObjectPath(CSWbemSecurity *,ushort *)
0x18001de10  mov     rbx, rax
0x18001de13  jmp     short loc_18001DE17
0x18001de15  xor     ebx, ebx
0x18001de17  test    rbx, rbx
0x18001de1a  jnz     short loc_18001DE28
0x18001de1c  mov     [rbp+4Fh+var_70], 80041006h
0x18001de23  jmp     loc_18001DF32
0x18001de28  mov     rax, [rbx]
0x18001de2b  mov     rcx, rbx
0x18001de2e  mov     rax, [rax+8]
0x18001de32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001de37  mov     rax, [rbx]
0x18001de3a  mov     rdx, [rdi+28h]
0x18001de3e  mov     rcx, rbx
0x18001de41  mov     rax, [rax+40h]
0x18001de45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001de4a  cmp     dword ptr [rbp+4Fh+pvarg+8], 1
0x18001de4e  jnz     loc_18001DEDF
0x18001de54  xorps   xmm0, xmm0
0x18001de57  xor     eax, eax
0x18001de59  movups  xmmword ptr [rbp+4Fh+var_58], xmm0
0x18001de5d  mov     qword ptr [rbp+4Fh+var_58+10h], rax
0x18001de61  lea     rcx, [rbp+4Fh+var_58]; pvarg
0x18001de65  call    cs:__imp_VariantInit
0x18001de6b  mov     rax, [r14]
0x18001de6e  mov     [rsp+0B0h+var_88], 0
0x18001de77  mov     [rsp+0B0h+var_90], 0
0x18001de80  lea     r9, [rbp+4Fh+var_58]
0x18001de84  xor     r8d, r8d
0x18001de87  lea     rdx, aClass; "__CLASS"
0x18001de8e  mov     rcx, r14
0x18001de91  mov     rax, [rax+20h]
0x18001de95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001de9a  test    eax, eax
0x18001de9c  jnz     short loc_18001DEC4
0x18001de9e  mov     eax, 8
0x18001dea3  cmp     ax, word ptr [rbp+4Fh+var_58]
0x18001dea7  jnz     short loc_18001DEC4
0x18001dea9  mov     rax, [rbx]
0x18001deac  mov     rdx, qword ptr [rbp+4Fh+var_58+8]
0x18001deb0  mov     rcx, rbx
0x18001deb3  mov     rax, [rax+98h]
0x18001deba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001debf  mov     [rsi], rbx
0x18001dec2  jmp     short loc_18001DED3
0x18001dec4  mov     rax, [rbx]
0x18001dec7  mov     rcx, rbx
0x18001deca  mov     rax, [rax+10h]
0x18001dece  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ded3  lea     rcx, [rbp+4Fh+var_58]; pvarg
0x18001ded7  call    cs:__imp_VariantClear
0x18001dedd  jmp     short loc_18001DF32
0x18001dedf  mov     [rbp+4Fh+bstrString], 0
0x18001dee7  mov     rcx, [rbp+4Fh+var_68]
0x18001deeb  mov     rax, [rcx]
0x18001deee  lea     r8, [rbp+4Fh+bstrString]
0x18001def2  or      edx, 0FFFFFFFFh
0x18001def5  mov     rax, [rax+20h]
0x18001def9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001defe  mov     r8, [rbx]
0x18001df01  mov     rcx, rbx
0x18001df04  test    eax, eax
0x18001df06  jnz     short loc_18001DF24
0x18001df08  mov     rdx, [rbp+4Fh+bstrString]
0x18001df0c  mov     rax, [r8+50h]
0x18001df10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001df15  mov     [rsi], rbx
0x18001df18  mov     rcx, [rbp+4Fh+bstrString]; bstrString
0x18001df1c  call    cs:__imp_SysFreeString
0x18001df22  jmp     short loc_18001DF32
0x18001df24  mov     rax, [r8+10h]
0x18001df28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001df2d  jmp     short loc_18001DF32
0x18001df2f  mov     [rbp+4Fh+var_70], ebx
0x18001df32  mov     rcx, [rbp+4Fh+var_68]
0x18001df36  test    rcx, rcx
0x18001df39  jz      short loc_18001DF47
0x18001df3b  mov     rax, [rcx]
0x18001df3e  mov     rax, [rax+10h]
0x18001df42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001df47  test    r12, r12
0x18001df4a  jz      short loc_18001DF5C
0x18001df4c  mov     rax, [r12]
0x18001df50  mov     rcx, r12
0x18001df53  mov     rax, [rax+10h]
0x18001df57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001df5c  mov     rax, [r14]
0x18001df5f  mov     rcx, r14
0x18001df62  mov     rax, [rax+10h]
0x18001df66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001df6b  lea     rcx, [rbp+4Fh+pvarg]; pvarg
0x18001df6f  call    cs:__imp_VariantClear
0x18001df75  mov     rcx, rdi; this
0x18001df78  call    ?SetWbemError@@YAXPEAVCSWbemServices@@@Z; SetWbemError(CSWbemServices *)
0x18001df7d  mov     rax, [r15]
0x18001df80  mov     rcx, r15
0x18001df83  mov     rax, [rax+10h]
0x18001df87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001df8c  mov     eax, [rbp+4Fh+var_70]
0x18001df8f  test    eax, eax
0x18001df91  jns     short loc_18001DFA1
0x18001df93  lea     rcx, [rdi+38h]; this
0x18001df97  mov     edx, eax; int
0x18001df99  call    ?RaiseException@CDispatchHelp@@QEAAXJ@Z; CDispatchHelp::RaiseException(long)
0x18001df9e  mov     eax, [rbp+4Fh+var_70]
0x18001dfa1  lea     r11, [rsp+0B0h+var_20]
0x18001dfa9  mov     rbx, [r11+30h]
0x18001dfad  mov     rsi, [r11+40h]
0x18001dfb1  mov     rsp, r11
0x18001dfb4  pop     r15
0x18001dfb6  pop     r14
0x18001dfb8  pop     r12
0x18001dfba  pop     rdi
0x18001dfbb  pop     rbp
0x18001dfbc  retn
```
