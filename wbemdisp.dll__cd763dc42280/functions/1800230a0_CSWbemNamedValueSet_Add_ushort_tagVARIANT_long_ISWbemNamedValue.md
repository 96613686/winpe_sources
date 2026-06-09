# CSWbemNamedValueSet::Add(ushort *,tagVARIANT *,long,ISWbemNamedValue * *)

- ea: `0x1800230a0`
- end: `0x1800232d0`
- name: `?Add@CSWbemNamedValueSet@@UEAAJPEAGPEAUtagVARIANT@@JPEAPEAUISWbemNamedValue@@@Z`
- size: `560`
- prototype: `__int64 __usercall@<rax>(CSWbemNamedValueSet *__hidden this@<rcx>, unsigned __int16 *@<rdx>, struct tagVARIANT *@<r8>, int@<r9d>, struct ISWbemNamedValue **)`
- caller_count: `0`
- callee_count: `8`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x1800050dc`
- `0x180006300`
- `0x180022314`
- `0x180022900`
- `0x1800230a0`
- `0x180025c74`
- `0x180033834`
- `0x180036010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1800231fc`
- `OLEAUT32!__imp_SysAllocString` at `0x1800231fc`
- `OLEAUT32!__imp_SysFreeString` at `0x180023229`
- `OLEAUT32!__imp_SysFreeString` at `0x180023229`
- `OLEAUT32!__imp_VariantInit` at `0x18002312f`
- `OLEAUT32!__imp_VariantInit` at `0x18002312f`
- `OLEAUT32!__imp_VariantClear` at `0x18002319f`
- `OLEAUT32!__imp_VariantClear` at `0x18002319f`
- `OLEAUT32!__imp_VariantChangeType` at `0x180023171`
- `OLEAUT32!__imp_VariantChangeType` at `0x180023171`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x18002315e`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x18002315e`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180023256`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180023256`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18002329f`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18002329f`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CSWbemNamedValueSet::Add(
        CSWbemNamedValueSet *this,
        unsigned __int16 *a2,
        struct tagVARIANT *a3,
        unsigned int a4,
        struct ISWbemNamedValue **a5)
{
  void **v9; // r14
  int v10; // ebx
  HRESULT v11; // eax
  int v12; // edx
  enum WbemCimtypeEnum v13; // r12d
  CWbemPathCracker *v14; // r15
  struct ISWbemNamedValue **v15; // rbx
  bool v16; // di
  struct ISWbemNamedValue **v17; // rax
  VARIANTARG pvarg; // [rsp+30h] [rbp-58h] BYREF

  ResetLastErrors();
  v9 = (void **)a5;
  if ( !a5 || !a2 || !a3 )
  {
    v10 = -2147217400;
    goto LABEL_29;
  }
  if ( !*((_BYTE *)this + 144) )
  {
    v10 = -2147217373;
LABEL_29:
    CDispatchHelp::RaiseException((CSWbemNamedValueSet *)((char *)this + 56), v10);
    return (unsigned int)v10;
  }
  v10 = -2147217407;
  if ( !*((_QWORD *)this + 6) )
    goto LABEL_29;
  *a5 = 0;
  if ( (a3->vt & 0x4000) != 0 )
  {
    memset(&pvarg, 0, sizeof(pvarg));
    VariantInit(&pvarg);
    if ( (a3->vt & 0x2000) != 0 )
    {
      pvarg.vt = a3->vt & 0xBFFF;
      v11 = SafeArrayCopy(*a3->pparray, &pvarg.parray);
    }
    else
    {
      v11 = VariantChangeType(&pvarg, a3, 0, a3->vt & 0xBFFF);
    }
    v10 = v11;
    if ( v11 >= 0 )
      v10 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int16 *, _QWORD, VARIANTARG *))(**((_QWORD **)this + 6) + 64LL))(
              *((_QWORD *)this + 6),
              a2,
              a4,
              &pvarg);
    VariantClear(&pvarg);
  }
  else
  {
    if ( a3->vt == 10 && a3->lVal == -2147352572 )
      a3->vt = 1;
    v10 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int16 *, _QWORD, struct tagVARIANT *))(**((_QWORD **)this + 6)
                                                                                             + 64LL))(
            *((_QWORD *)this + 6),
            a2,
            a4,
            a3);
  }
  if ( v10 < 0 )
    goto LABEL_29;
  v13 = MapVariantTypeToCimType(a3, v12);
  v14 = (CWbemPathCracker *)*((_QWORD *)this + 17);
  if ( v14 )
  {
    v15 = (struct ISWbemNamedValue **)SysAllocString(a2);
    a5 = v15;
    v16 = CWbemPathCracker::SetKey(v14, (const struct ATL::CComBSTR *)&a5, v13, a3);
    SysFreeString((BSTR)v15);
    if ( !v16 )
    {
      (*(void (__fastcall **)(_QWORD, unsigned __int16 *, _QWORD))(**((_QWORD **)this + 6) + 80LL))(
        *((_QWORD *)this + 6),
        a2,
        0);
      v10 = -2147217407;
      goto LABEL_29;
    }
  }
  v17 = (struct ISWbemNamedValue **)CWin32DefaultArena::WbemMemAlloc(0x88u);
  a5 = v17;
  if ( v17 )
    v17 = (struct ISWbemNamedValue **)CSWbemNamedValue::CSWbemNamedValue(
                                        (struct IDispatch *)v17,
                                        *((struct CSWbemServices **)this + 5),
                                        this,
                                        1);
  *v9 = v17;
  if ( !v17 )
  {
    v10 = -2147217402;
    goto LABEL_29;
  }
  v10 = CSWbemNamedValue::SetName((CSWbemNamedValue *)v17, a2);
  if ( v10 < 0 )
  {
    CWin32DefaultArena::WbemMemFree(*v9);
    *v9 = 0;
    goto LABEL_29;
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1800230a0  push    rbx
0x1800230a2  push    rbp
0x1800230a3  push    rsi
0x1800230a4  push    rdi
0x1800230a5  push    r12
0x1800230a7  push    r14
0x1800230a9  push    r15
0x1800230ab  sub     rsp, 50h
0x1800230af  mov     r15d, r9d
0x1800230b2  mov     rdi, r8
0x1800230b5  mov     rbp, rdx
0x1800230b8  mov     rsi, rcx
0x1800230bb  call    ?ResetLastErrors@@YAXXZ; ResetLastErrors(void)
0x1800230c0  mov     r14, [rsp+88h+arg_20]
0x1800230c8  test    r14, r14
0x1800230cb  jz      loc_1800232AF
0x1800230d1  test    rbp, rbp
0x1800230d4  jz      loc_1800232AF
0x1800230da  test    rdi, rdi
0x1800230dd  jz      loc_1800232AF
0x1800230e3  cmp     byte ptr [rsi+90h], 0
0x1800230ea  jnz     short loc_1800230F6
0x1800230ec  mov     ebx, 80041023h
0x1800230f1  jmp     loc_1800232B4
0x1800230f6  mov     ebx, 80041001h
0x1800230fb  cmp     qword ptr [rsi+30h], 0
0x180023100  jz      loc_1800232B4
0x180023106  mov     qword ptr [r14], 0
0x18002310d  mov     eax, 4000h
0x180023112  test    [rdi], ax
0x180023115  jz      loc_1800231A7
0x18002311b  xorps   xmm0, xmm0
0x18002311e  xor     eax, eax
0x180023120  movups  xmmword ptr [rsp+88h+pvarg], xmm0
0x180023125  mov     qword ptr [rsp+88h+pvarg+10h], rax
0x18002312a  lea     rcx, [rsp+88h+pvarg]; pvarg
0x18002312f  call    cs:__imp_VariantInit
0x180023135  mov     eax, 0BFFFh
0x18002313a  movzx   r9d, word ptr [rdi]
0x18002313e  and     r9w, ax; vt
0x180023142  mov     eax, 2000h
0x180023147  test    [rdi], ax
0x18002314a  jz      short loc_180023166
0x18002314c  mov     word ptr [rsp+88h+pvarg], r9w
0x180023152  mov     rcx, [rdi+8]
0x180023156  lea     rdx, [rsp+88h+pvarg+8]; ppsaOut
0x18002315b  mov     rcx, [rcx]; psa
0x18002315e  call    cs:__imp_SafeArrayCopy
0x180023164  jmp     short loc_180023177
0x180023166  xor     r8d, r8d; wFlags
0x180023169  mov     rdx, rdi; pvarSrc
0x18002316c  lea     rcx, [rsp+88h+pvarg]; pvargDest
0x180023171  call    cs:__imp_VariantChangeType
0x180023177  mov     ebx, eax
0x180023179  test    eax, eax
0x18002317b  js      short loc_18002319A
0x18002317d  mov     rcx, [rsi+30h]
0x180023181  mov     rax, [rcx]
0x180023184  lea     r9, [rsp+88h+pvarg]
0x180023189  mov     r8d, r15d
0x18002318c  mov     rdx, rbp
0x18002318f  mov     rax, [rax+40h]
0x180023193  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023198  mov     ebx, eax
0x18002319a  lea     rcx, [rsp+88h+pvarg]; pvarg
0x18002319f  call    cs:__imp_VariantClear
0x1800231a5  jmp     short loc_1800231DA
0x1800231a7  mov     eax, 0Ah
0x1800231ac  cmp     ax, [rdi]
0x1800231af  jnz     short loc_1800231BF
0x1800231b1  cmp     dword ptr [rdi+8], 80020004h
0x1800231b8  jnz     short loc_1800231BF
0x1800231ba  mov     word ptr [rdi], 1
0x1800231bf  mov     rcx, [rsi+30h]
0x1800231c3  mov     rax, [rcx]
0x1800231c6  mov     r9, rdi
0x1800231c9  mov     r8d, r15d
0x1800231cc  mov     rdx, rbp
0x1800231cf  mov     rax, [rax+40h]
0x1800231d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800231d8  mov     ebx, eax
0x1800231da  test    ebx, ebx
0x1800231dc  js      loc_1800232B4
0x1800231e2  mov     rcx, rdi; struct tagVARIANT *
0x1800231e5  call    ?MapVariantTypeToCimType@@YA?AW4WbemCimtypeEnum@@PEAUtagVARIANT@@J@Z; MapVariantTypeToCimType(tagVARIANT *,long)
0x1800231ea  mov     r12d, eax
0x1800231ed  mov     r15, [rsi+88h]
0x1800231f4  test    r15, r15
0x1800231f7  jz      short loc_180023251
0x1800231f9  mov     rcx, rbp; psz
0x1800231fc  call    cs:__imp_SysAllocString
0x180023202  mov     rbx, rax
0x180023205  mov     [rsp+88h+arg_20], rax
0x18002320d  mov     r9, rdi; struct tagVARIANT *
0x180023210  mov     r8d, r12d; enum WbemCimtypeEnum
0x180023213  lea     rdx, [rsp+88h+arg_20]; struct ATL::CComBSTR *
0x18002321b  mov     rcx, r15; this
0x18002321e  call    ?SetKey@CWbemPathCracker@@QEAA_NAEBVCComBSTR@ATL@@W4WbemCimtypeEnum@@AEAUtagVARIANT@@@Z; CWbemPathCracker::SetKey(ATL::CComBSTR const &,WbemCimtypeEnum,tagVARIANT &)
0x180023223  mov     dil, al
0x180023226  mov     rcx, rbx; bstrString
0x180023229  call    cs:__imp_SysFreeString
0x18002322f  test    dil, dil
0x180023232  jnz     short loc_180023251
0x180023234  mov     rcx, [rsi+30h]
0x180023238  mov     rax, [rcx]
0x18002323b  xor     r8d, r8d
0x18002323e  mov     rdx, rbp
0x180023241  mov     rax, [rax+50h]
0x180023245  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002324a  mov     ebx, 80041001h
0x18002324f  jmp     short loc_1800232B4
0x180023251  mov     ecx, 88h
0x180023256  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18002325c  mov     [rsp+88h+arg_20], rax
0x180023264  test    rax, rax
0x180023267  jz      short loc_18002327C
0x180023269  mov     r9b, 1; bool
0x18002326c  mov     r8, rsi; struct CSWbemNamedValueSet *
0x18002326f  mov     rdx, [rsi+28h]; struct CSWbemServices *
0x180023273  mov     rcx, rax; this
0x180023276  call    ??0CSWbemNamedValue@@QEAA@PEAVCSWbemServices@@PEAVCSWbemNamedValueSet@@_N@Z; CSWbemNamedValue::CSWbemNamedValue(CSWbemServices *,CSWbemNamedValueSet *,bool)
0x18002327b  nop
0x18002327c  mov     [r14], rax
0x18002327f  test    rax, rax
0x180023282  jnz     short loc_18002328B
0x180023284  mov     ebx, 80041006h
0x180023289  jmp     short loc_1800232B4
0x18002328b  mov     rdx, rbp; unsigned __int16 *
0x18002328e  mov     rcx, rax; this
0x180023291  call    ?SetName@CSWbemNamedValue@@QEAAJPEAG@Z; CSWbemNamedValue::SetName(ushort *)
0x180023296  mov     ebx, eax
0x180023298  test    eax, eax
0x18002329a  jns     short loc_1800232BF
0x18002329c  mov     rcx, [r14]
0x18002329f  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x1800232a5  nop
0x1800232a6  mov     qword ptr [r14], 0
0x1800232ad  jmp     short loc_1800232B4
0x1800232af  mov     ebx, 80041008h
0x1800232b4  lea     rcx, [rsi+38h]; this
0x1800232b8  mov     edx, ebx; int
0x1800232ba  call    ?RaiseException@CDispatchHelp@@QEAAXJ@Z; CDispatchHelp::RaiseException(long)
0x1800232bf  mov     eax, ebx
0x1800232c1  add     rsp, 50h
0x1800232c5  pop     r15
0x1800232c7  pop     r14
0x1800232c9  pop     r12
0x1800232cb  pop     rdi
0x1800232cc  pop     rsi
0x1800232cd  pop     rbp
0x1800232ce  pop     rbx
0x1800232cf  retn
```
