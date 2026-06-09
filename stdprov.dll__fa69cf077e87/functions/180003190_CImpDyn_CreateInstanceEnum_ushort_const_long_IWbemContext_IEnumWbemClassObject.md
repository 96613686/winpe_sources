# CImpDyn::CreateInstanceEnum(ushort * const,long,IWbemContext *,IEnumWbemClassObject * *)

- ea: `0x180003190`
- end: `0x18000342b`
- name: `?CreateInstanceEnum@CImpDyn@@UEAAJQEAGJPEAUIWbemContext@@PEAPEAUIEnumWbemClassObject@@@Z`
- size: `667`
- prototype: `__int64 __fastcall(CImpDyn *__hidden this, unsigned __int16 *const, int, struct IWbemContext *, struct IEnumWbemClassObject **)`
- caller_count: `0`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callees

- `0x180001490`
- `0x180002e10`
- `0x180002e90`
- `0x180003190`
- `0x180003f40`
- `0x180003f64`
- `0x1800091e0`
- `0x18000a0c8`
- `0x180017010`

## import_xrefs

- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18000336e`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18000336e`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800032c4`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180003381`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800032c4`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180003381`
- `OLEAUT32!__imp_VariantInit` at `0x180003212`
- `OLEAUT32!__imp_VariantInit` at `0x180003212`

## pseudocode

```c
__int64 __fastcall CImpDyn::CreateInstanceEnum(
        CImpDyn *this,
        unsigned __int16 *const a2,
        int a3,
        struct IWbemContext *a4,
        struct IEnumWbemClassObject **a5)
{
  __int64 result; // rax
  unsigned __int16 *v10; // rsi
  int v11; // ebx
  __int64 v12; // rax
  unsigned int v13; // ebx
  unsigned __int16 *v14; // rax
  char v15; // al
  CEnumInst *v16; // rax
  CEnumInst *v17; // rbx
  unsigned int v18; // edx
  int v19; // edi
  CEnumInst *v20; // [rsp+40h] [rbp-91h] BYREF
  struct CEnumInfo *v21; // [rsp+48h] [rbp-89h] BYREF
  void **v22; // [rsp+50h] [rbp-81h] BYREF
  VARIANTARG pvarg; // [rsp+58h] [rbp-79h] BYREF
  _BYTE v24[176]; // [rsp+70h] [rbp-61h] BYREF

  v21 = 0;
  result = (*(__int64 (__fastcall **)(_QWORD, unsigned __int16 *const, _QWORD))(**((_QWORD **)this + 3) + 48LL))(
             *((_QWORD *)this + 3),
             a2,
             0);
  if ( !(_DWORD)result )
  {
    v20 = 0;
    v22 = &CVariant::`vftable';
    VariantInit(&pvarg);
    pvarg.llVal = 0;
    v10 = 0;
    v11 = (*(__int64 (__fastcall **)(_QWORD, CEnumInst **))(MEMORY[0] + 24LL))(0, &v20);
    if ( v11 < 0
      || (v11 = (*(__int64 (__fastcall **)(CEnumInst *, const wchar_t *, _QWORD, VARIANTARG *, _QWORD))(*(_QWORD *)v20 + 24LL))(
                  v20,
                  L"classcontext",
                  0,
                  &pvarg,
                  0),
          (*(void (__fastcall **)(CEnumInst *))(*(_QWORD *)v20 + 16LL))(v20),
          v11 < 0) )
    {
      CVariant::~CVariant((CVariant *)&v22);
    }
    else if ( pvarg.vt == 8 )
    {
      v12 = -1;
      do
        ++v12;
      while ( *(_WORD *)(pvarg.llVal + 2 * v12) );
      v13 = v12 + 1;
      v14 = (unsigned __int16 *)CWin32DefaultArena::WbemMemAlloc(saturated_mul((unsigned int)(v12 + 1), 2u));
      v10 = v14;
      if ( v14 )
      {
        StringCchCopyW(v14, v13, pvarg.bstrVal);
        v11 = 0;
      }
      else
      {
        v11 = -2147217402;
      }
      v22 = &CVariant::`vftable';
      OMSVariantClear(&pvarg);
      v22 = &CObject::`vftable';
    }
    else
    {
      CVariant::~CVariant((CVariant *)&v22);
      v11 = -2147217407;
    }
    (*(void (__fastcall **)(_QWORD))(MEMORY[0] + 16LL))(0);
    if ( !v11 )
    {
      v15 = (*(__int64 (__fastcall **)(CImpDyn *))(*(_QWORD *)this + 288LL))(this);
      CProvObj::CProvObj((CProvObj *)v24, v10, 0x7Cu, v15);
      v11 = (*(__int64 (__fastcall **)(CImpDyn *, _QWORD, _BYTE *, struct CEnumInfo **))(*(_QWORD *)this + 216LL))(
              this,
              0,
              v24,
              &v21);
      CWin32DefaultArena::WbemMemFree(v10);
      if ( !v11 )
      {
        v16 = (CEnumInst *)CWin32DefaultArena::WbemMemAlloc(0xB0u);
        v20 = v16;
        if ( v16 )
          v17 = CEnumInst::CEnumInst(v16, v21, a3, a2, *((struct IWbemServices **)this + 3), this, a4);
        else
          v17 = 0;
        if ( v17 )
        {
          v19 = (**(__int64 (__fastcall ***)(CEnumInst *, GUID *, struct IEnumWbemClassObject **))v17)(
                  v17,
                  &IID_IEnumWbemClassObject,
                  a5);
          if ( v19 < 0 )
            CEnumInst::`scalar deleting destructor'(v17, v18);
          v11 = v19;
        }
        else
        {
          if ( v21 )
            (**(void (__fastcall ***)(struct CEnumInfo *, __int64))v21)(v21, 1);
          v11 = -2147217402;
        }
      }
      CProvObj::~CProvObj((CProvObj *)v24);
    }
    return (unsigned int)v11;
  }
  return result;
}

```

## disassembly

```asm
0x180003190  push    rbp
0x180003192  push    rbx
0x180003193  push    rsi
0x180003194  push    rdi
0x180003195  push    r12
0x180003197  push    r13
0x180003199  push    r14
0x18000319b  push    r15
0x18000319d  lea     rbp, [rsp-17h]
0x1800031a2  sub     rsp, 0E8h
0x1800031a9  mov     r14, r9
0x1800031ac  mov     r12d, r8d
0x1800031af  mov     r15, rdx
0x1800031b2  mov     rdi, rcx
0x1800031b5  xor     r13d, r13d
0x1800031b8  mov     [rbp+4Fh+arg_0], r13
0x1800031bc  mov     [rsp+120h+var_D8], r13
0x1800031c1  mov     rcx, [rcx+18h]
0x1800031c5  mov     rax, [rcx]
0x1800031c8  mov     [rsp+120h+var_F8], r13
0x1800031cd  lea     rdx, [rbp+4Fh+arg_0]
0x1800031d1  mov     [rsp+120h+var_100], rdx
0x1800031d6  xor     r8d, r8d
0x1800031d9  mov     rdx, r15
0x1800031dc  mov     rax, [rax+30h]
0x1800031e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800031e5  test    eax, eax
0x1800031e7  jnz     loc_180003417
0x1800031ed  mov     rbx, [rbp+4Fh+arg_0]
0x1800031f1  mov     [rsp+120h+var_E0], r13
0x1800031f6  lea     rax, ??_7CObject@@6B@; const CObject::`vftable'
0x1800031fd  mov     [rsp+120h+var_D0], rax
0x180003202  lea     rax, ??_7CVariant@@6B@; const CVariant::`vftable'
0x180003209  mov     [rsp+120h+var_D0], rax
0x18000320e  lea     rcx, [rbp+4Fh+pvarg]; pvarg
0x180003212  call    cs:__imp_VariantInit
0x180003218  xor     eax, eax
0x18000321a  mov     qword ptr [rbp+4Fh+pvarg+8], rax
0x18000321e  mov     esi, r13d
0x180003221  mov     rax, [rbx]
0x180003224  lea     rdx, [rsp+120h+var_E0]
0x180003229  mov     rcx, rbx
0x18000322c  mov     rax, [rax+18h]
0x180003230  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003235  mov     ebx, eax
0x180003237  test    eax, eax
0x180003239  jns     short loc_18000324A
0x18000323b  lea     rcx, [rsp+120h+var_D0]; this
0x180003240  call    ??1CVariant@@UEAA@XZ; CVariant::~CVariant(void)
0x180003245  jmp     loc_18000330C
0x18000324a  mov     rcx, [rsp+120h+var_E0]
0x18000324f  mov     rax, [rcx]
0x180003252  mov     [rsp+120h+var_100], r13
0x180003257  lea     r9, [rbp+4Fh+pvarg]
0x18000325b  xor     r8d, r8d
0x18000325e  lea     rdx, aClasscontext; "classcontext"
0x180003265  mov     rax, [rax+18h]
0x180003269  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000326e  mov     ebx, eax
0x180003270  mov     rcx, [rsp+120h+var_E0]
0x180003275  mov     rax, [rcx]
0x180003278  mov     rax, [rax+10h]
0x18000327c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003281  test    ebx, ebx
0x180003283  js      short loc_18000323B
0x180003285  cmp     word ptr [rbp+4Fh+pvarg], 8
0x18000328a  jz      short loc_18000329D
0x18000328c  lea     rcx, [rsp+120h+var_D0]; this
0x180003291  call    ??1CVariant@@UEAA@XZ; CVariant::~CVariant(void)
0x180003296  mov     ebx, 80041001h
0x18000329b  jmp     short loc_18000330C
0x18000329d  mov     rcx, qword ptr [rbp+4Fh+pvarg+8]
0x1800032a1  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800032a5  mov     rax, r8
0x1800032a8  inc     rax
0x1800032ab  cmp     [rcx+rax*2], r13w
0x1800032b0  jnz     short loc_1800032A8
0x1800032b2  lea     ebx, [rax+1]
0x1800032b5  mov     eax, 2
0x1800032ba  mul     rbx
0x1800032bd  cmovb   rax, r8
0x1800032c1  mov     rcx, rax
0x1800032c4  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x1800032ca  mov     rsi, rax
0x1800032cd  test    rax, rax
0x1800032d0  jz      short loc_1800032E5
0x1800032d2  mov     r8, qword ptr [rbp+4Fh+pvarg+8]; unsigned __int16 *
0x1800032d6  mov     edx, ebx; unsigned __int64
0x1800032d8  mov     rcx, rax; unsigned __int16 *
0x1800032db  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800032e0  mov     ebx, r13d
0x1800032e3  jmp     short loc_1800032EA
0x1800032e5  mov     ebx, 80041006h
0x1800032ea  lea     rax, ??_7CVariant@@6B@; const CVariant::`vftable'
0x1800032f1  mov     [rsp+120h+var_D0], rax
0x1800032f6  lea     rcx, [rbp+4Fh+pvarg]; struct tagVARIANT *
0x1800032fa  call    ?OMSVariantClear@@YAJPEAUtagVARIANT@@@Z; OMSVariantClear(tagVARIANT *)
0x1800032ff  nop
0x180003300  lea     rax, ??_7CObject@@6B@; const CObject::`vftable'
0x180003307  mov     [rsp+120h+var_D0], rax
0x18000330c  mov     rcx, [rbp+4Fh+arg_0]
0x180003310  mov     rdx, [rcx]
0x180003313  mov     rax, [rdx+10h]
0x180003317  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000331c  test    ebx, ebx
0x18000331e  jnz     loc_180003415
0x180003324  mov     rax, [rdi]
0x180003327  mov     rcx, rdi
0x18000332a  mov     rax, [rax+120h]
0x180003331  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003336  lea     r8d, [rbx+7Ch]; unsigned __int16
0x18000333a  mov     r9b, al; bool
0x18000333d  mov     rdx, rsi; unsigned __int16 *
0x180003340  lea     rcx, [rbp+4Fh+var_B0]; this
0x180003344  call    ??0CProvObj@@QEAA@PEBGG_N@Z; CProvObj::CProvObj(ushort const *,ushort,bool)
0x180003349  nop
0x18000334a  mov     rax, [rdi]
0x18000334d  lea     r9, [rsp+120h+var_D8]
0x180003352  lea     r8, [rbp+4Fh+var_B0]
0x180003356  mov     rdx, [rbp+4Fh+arg_0]
0x18000335a  mov     rcx, rdi
0x18000335d  mov     rax, [rax+0D8h]
0x180003364  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003369  mov     ebx, eax
0x18000336b  mov     rcx, rsi
0x18000336e  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180003374  test    ebx, ebx
0x180003376  jnz     loc_18000340C
0x18000337c  mov     ecx, 0B0h
0x180003381  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180003387  mov     [rsp+120h+var_E0], rax
0x18000338c  test    rax, rax
0x18000338f  jz      short loc_1800033BC
0x180003391  mov     [rsp+120h+var_F0], r14; struct IWbemContext *
0x180003396  mov     [rsp+120h+var_F8], rdi; struct CImpDyn *
0x18000339b  mov     rcx, [rdi+18h]
0x18000339f  mov     [rsp+120h+var_100], rcx; struct IWbemServices *
0x1800033a4  mov     r9, r15; unsigned __int16 *
0x1800033a7  mov     r8d, r12d; int
0x1800033aa  mov     rdx, [rsp+120h+var_D8]; struct CEnumInfo *
0x1800033af  mov     rcx, rax; this
0x1800033b2  call    ??0CEnumInst@@QEAA@PEAVCEnumInfo@@JPEAGPEAUIWbemServices@@PEAVCImpDyn@@PEAUIWbemContext@@@Z; CEnumInst::CEnumInst(CEnumInfo *,long,ushort *,IWbemServices *,CImpDyn *,IWbemContext *)
0x1800033b7  mov     rbx, rax
0x1800033ba  jmp     short loc_1800033BF
0x1800033bc  mov     rbx, r13
0x1800033bf  test    rbx, rbx
0x1800033c2  jnz     short loc_1800033E3
0x1800033c4  mov     rcx, [rsp+120h+var_D8]
0x1800033c9  test    rcx, rcx
0x1800033cc  jz      short loc_1800033DC
0x1800033ce  mov     rax, [rcx]
0x1800033d1  lea     edx, [rbx+1]
0x1800033d4  mov     rax, [rax]
0x1800033d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800033dc  mov     ebx, 80041006h
0x1800033e1  jmp     short loc_18000340C
0x1800033e3  mov     rax, [rbx]
0x1800033e6  mov     r8, [rbp+4Fh+arg_20]
0x1800033ea  lea     rdx, IID_IEnumWbemClassObject
0x1800033f1  mov     rcx, rbx
0x1800033f4  mov     rax, [rax]
0x1800033f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800033fc  mov     edi, eax
0x1800033fe  test    eax, eax
0x180003400  jns     short loc_18000340A
0x180003402  mov     rcx, rbx; this
0x180003405  call    ??_GCEnumInst@@QEAAPEAXI@Z; CEnumInst::`scalar deleting destructor'(uint)
0x18000340a  mov     ebx, edi
0x18000340c  lea     rcx, [rbp+4Fh+var_B0]; this
0x180003410  call    ??1CProvObj@@UEAA@XZ; CProvObj::~CProvObj(void)
0x180003415  mov     eax, ebx
0x180003417  add     rsp, 0E8h
0x18000341e  pop     r15
0x180003420  pop     r14
0x180003422  pop     r13
0x180003424  pop     r12
0x180003426  pop     rdi
0x180003427  pop     rsi
0x180003428  pop     rbx
0x180003429  pop     rbp
0x18000342a  retn
```
