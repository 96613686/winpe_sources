# CImpDyn::GetAttString(IWbemClassObject *,ushort *,ushort *,ushort * *,CIndexCache *,int)

- ea: `0x1800040c8`
- end: `0x18000424f`
- name: `?GetAttString@CImpDyn@@QEAAJPEAUIWbemClassObject@@PEAG1PEAPEAGPEAVCIndexCache@@H@Z`
- size: `391`
- prototype: `__int64 __fastcall(CImpDyn *__hidden this, struct IWbemClassObject *, unsigned __int16 *, unsigned __int16 *, unsigned __int16 **, struct CIndexCache *, int)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1800038e0`

## callees

- `0x180002e10`
- `0x180003f40`
- `0x1800040c8`
- `0x180004260`
- `0x1800091e0`
- `0x18000abf0`
- `0x18000f770`
- `0x180017010`

## import_xrefs

- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180004103`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180004103`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800041d7`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800041d7`

## pseudocode

```c
__int64 __fastcall CImpDyn::GetAttString(
        CImpDyn *this,
        struct IWbemClassObject *a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        unsigned __int16 **a5,
        struct CIndexCache *a6,
        int a7)
{
  const unsigned __int16 **v10; // rdi
  unsigned __int16 *WString; // rax
  int v12; // ebx
  struct IWbemClassObjectVtbl *lpVtbl; // rax
  int v14; // eax
  __int64 v15; // rax
  unsigned int v16; // ebx
  unsigned __int16 *v17; // rax
  void **v19; // [rsp+30h] [rbp-28h] BYREF
  struct tagVARIANT v20; // [rsp+38h] [rbp-20h] BYREF
  __int64 v21; // [rsp+90h] [rbp+38h] BYREF

  v21 = 0;
  CVariant::CVariant((CVariant *)&v19);
  v10 = (const unsigned __int16 **)a5;
  if ( *a5 )
    CWin32DefaultArena::WbemMemFree(*a5);
  *v10 = 0;
  if ( a6 )
  {
    if ( a7 != -1 )
    {
      WString = CIndexCache::GetWString(a6, a7);
      *v10 = WString;
      if ( WString )
      {
        v12 = 0;
LABEL_14:
        CVariant::~CVariant((CVariant *)&v19);
        return (unsigned int)v12;
      }
    }
  }
  lpVtbl = a2->lpVtbl;
  if ( a3 )
    v14 = ((__int64 (__fastcall *)(struct IWbemClassObject *, unsigned __int16 *, __int64 *))lpVtbl->GetPropertyQualifierSet)(
            a2,
            a3,
            &v21);
  else
    v14 = ((__int64 (__fastcall *)(struct IWbemClassObject *, __int64 *))lpVtbl->GetQualifierSet)(a2, &v21);
  v12 = v14;
  if ( v14 < 0 )
    goto LABEL_14;
  v12 = (*(__int64 (__fastcall **)(__int64, unsigned __int16 *, _QWORD, struct tagVARIANT *, _QWORD))(*(_QWORD *)v21 + 24LL))(
          v21,
          a4,
          0,
          &v20,
          0);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
  if ( v12 < 0 )
    goto LABEL_14;
  if ( v20.vt != 8 )
  {
    v12 = -2147217407;
    goto LABEL_14;
  }
  v15 = -1;
  do
    ++v15;
  while ( *(_WORD *)(v20.llVal + 2 * v15) );
  v16 = v15 + 1;
  v17 = (unsigned __int16 *)CWin32DefaultArena::WbemMemAlloc(saturated_mul((unsigned int)(v15 + 1), 2u));
  *v10 = v17;
  if ( v17 )
  {
    StringCchCopyW(v17, v16, v20.bstrVal);
    v12 = 0;
  }
  else
  {
    v12 = -2147217402;
  }
  if ( a6 && a7 != -1 && *v10 )
    CIndexCache::SetAt(a6, *v10, a7);
  v19 = &CVariant::`vftable';
  OMSVariantClear(&v20);
  v19 = &CObject::`vftable';
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x1800040c8  mov     [rsp-30h+arg_0], rcx
0x1800040cd  push    rbp
0x1800040ce  push    rbx
0x1800040cf  push    rdi
0x1800040d0  push    r12
0x1800040d2  push    r13
0x1800040d4  push    r15
0x1800040d6  mov     rbp, rsp
0x1800040d9  sub     rsp, 58h
0x1800040dd  mov     r12, r9
0x1800040e0  mov     r15, r8
0x1800040e3  mov     rbx, rdx
0x1800040e6  xor     r13d, r13d
0x1800040e9  mov     [rbp+arg_0], r13
0x1800040ed  lea     rcx, [rbp+var_28]; this
0x1800040f1  call    ??0CVariant@@QEAA@XZ; CVariant::CVariant(void)
0x1800040f6  nop
0x1800040f7  mov     rdi, [rbp+arg_20]
0x1800040fb  mov     rcx, [rdi]
0x1800040fe  test    rcx, rcx
0x180004101  jz      short loc_180004109
0x180004103  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180004109  mov     [rdi], r13
0x18000410c  cmp     [rbp+arg_28], r13
0x180004110  jz      short loc_180004131
0x180004112  cmp     [rbp+arg_30], 0FFFFFFFFh
0x180004116  jz      short loc_180004131
0x180004118  mov     edx, [rbp+arg_30]; int
0x18000411b  mov     rcx, [rbp+arg_28]; this
0x18000411f  call    ?GetWString@CIndexCache@@QEAAPEAGH@Z; CIndexCache::GetWString(int)
0x180004124  mov     [rdi], rax
0x180004127  test    rax, rax
0x18000412a  jz      short loc_180004131
0x18000412c  mov     ebx, r13d
0x18000412f  jmp     short loc_1800041A2
0x180004131  mov     rax, [rbx]
0x180004134  mov     rcx, rbx
0x180004137  test    r15, r15
0x18000413a  jnz     short loc_18000414B
0x18000413c  lea     rdx, [rbp+arg_0]
0x180004140  mov     rax, [rax+18h]
0x180004144  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004149  jmp     short loc_18000415B
0x18000414b  lea     r8, [rbp+arg_0]
0x18000414f  mov     rdx, r15
0x180004152  mov     rax, [rax+58h]
0x180004156  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000415b  mov     ebx, eax
0x18000415d  test    eax, eax
0x18000415f  js      short loc_1800041A2
0x180004161  mov     rcx, [rbp+arg_0]
0x180004165  mov     rax, [rcx]
0x180004168  mov     [rsp+58h+var_38], r13
0x18000416d  lea     r9, [rbp+var_20]
0x180004171  xor     r8d, r8d
0x180004174  mov     rdx, r12
0x180004177  mov     rax, [rax+18h]
0x18000417b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004180  mov     ebx, eax
0x180004182  mov     rcx, [rbp+arg_0]
0x180004186  mov     rax, [rcx]
0x180004189  mov     rax, [rax+10h]
0x18000418d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004192  test    ebx, ebx
0x180004194  js      short loc_1800041A2
0x180004196  cmp     word ptr [rbp+var_20], 8
0x18000419b  jz      short loc_1800041B0
0x18000419d  mov     ebx, 80041001h
0x1800041a2  lea     rcx, [rbp+var_28]; this
0x1800041a6  call    ??1CVariant@@UEAA@XZ; CVariant::~CVariant(void)
0x1800041ab  jmp     loc_18000423F
0x1800041b0  mov     rcx, qword ptr [rbp+var_20+8]
0x1800041b4  or      r15, 0FFFFFFFFFFFFFFFFh
0x1800041b8  mov     rax, r15
0x1800041bb  inc     rax
0x1800041be  cmp     [rcx+rax*2], r13w
0x1800041c3  jnz     short loc_1800041BB
0x1800041c5  lea     ebx, [rax+1]
0x1800041c8  mov     eax, 2
0x1800041cd  mul     rbx
0x1800041d0  cmovb   rax, r15
0x1800041d4  mov     rcx, rax
0x1800041d7  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x1800041dd  mov     [rdi], rax
0x1800041e0  test    rax, rax
0x1800041e3  jz      short loc_1800041F8
0x1800041e5  mov     r8, qword ptr [rbp+var_20+8]; unsigned __int16 *
0x1800041e9  mov     edx, ebx; unsigned __int64
0x1800041eb  mov     rcx, rax; unsigned __int16 *
0x1800041ee  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800041f3  mov     ebx, r13d
0x1800041f6  jmp     short loc_1800041FD
0x1800041f8  mov     ebx, 80041006h
0x1800041fd  cmp     [rbp+arg_28], r13
0x180004201  jz      short loc_18000421F
0x180004203  cmp     [rbp+arg_30], r15d
0x180004207  jz      short loc_18000421F
0x180004209  mov     rdx, [rdi]; unsigned __int16 *
0x18000420c  test    rdx, rdx
0x18000420f  jz      short loc_18000421F
0x180004211  mov     r8d, [rbp+arg_30]; int
0x180004215  mov     rcx, [rbp+arg_28]; this
0x180004219  call    ?SetAt@CIndexCache@@QEAAHPEBGH@Z; CIndexCache::SetAt(ushort const *,int)
0x18000421e  nop
0x18000421f  lea     rax, ??_7CVariant@@6B@; const CVariant::`vftable'
0x180004226  mov     [rbp+var_28], rax
0x18000422a  lea     rcx, [rbp+var_20]; struct tagVARIANT *
0x18000422e  call    ?OMSVariantClear@@YAJPEAUtagVARIANT@@@Z; OMSVariantClear(tagVARIANT *)
0x180004233  nop
0x180004234  lea     rax, ??_7CObject@@6B@; const CObject::`vftable'
0x18000423b  mov     [rbp+var_28], rax
0x18000423f  mov     eax, ebx
0x180004241  add     rsp, 58h
0x180004245  pop     r15
0x180004247  pop     r13
0x180004249  pop     r12
0x18000424b  pop     rdi
0x18000424c  pop     rbx
0x18000424d  pop     rbp
0x18000424e  retn
```
