# CShellPropertyThunk::ObjectIDThunk(IPropertyStore *,_tagpropertykey const &,long,IHMEMediaContainer *,tagPROPVARIANT *)

- ea: `0x140027710`
- end: `0x14002784b`
- name: `?ObjectIDThunk@CShellPropertyThunk@@CAJPEAUIPropertyStore@@AEBU_tagpropertykey@@JPEAUIHMEMediaContainer@@PEAUtagPROPVARIANT@@@Z`
- size: `315`
- prototype: `__int64 __fastcall(struct IPropertyStore *, const struct _tagpropertykey *, int, struct IHMEMediaContainer *, struct tagPROPVARIANT *)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x140027710`
- `0x1400282b0`
- `0x14009e010`

## import_xrefs

- `ole32!PropVariantClear` at `0x1400277eb`
- `ole32!PropVariantClear` at `0x1400277eb`
- `ole32!CoTaskMemFree` at `0x1400277e0`
- `ole32!CoTaskMemFree` at `0x1400277e0`
- `ole32!CoTaskMemAlloc` at `0x1400277c7`
- `ole32!CoTaskMemAlloc` at `0x1400277c7`
- `PROPSYS!PropVariantToStringAlloc` at `0x14002776f`
- `PROPSYS!PropVariantToStringAlloc` at `0x14002776f`

## pseudocode

```c
__int64 __fastcall CShellPropertyThunk::ObjectIDThunk(
        struct IPropertyStore *a1,
        const struct _tagpropertykey *a2,
        int a3,
        struct IHMEMediaContainer *a4,
        struct tagPROPVARIANT *a5)
{
  struct IPropertyStoreVtbl *lpVtbl; // rax
  HRESULT v7; // ebx
  const unsigned __int16 *v8; // rbp
  __int64 v9; // rax
  __int64 v10; // rcx
  const unsigned __int16 *v11; // rbx
  __int64 v12; // rdi
  unsigned __int64 v13; // rsi
  unsigned __int16 *v14; // rax
  PWSTR ppszOut; // [rsp+20h] [rbp-58h] BYREF
  PROPVARIANT propvar[2]; // [rsp+28h] [rbp-50h] BYREF
  __int64 v18; // [rsp+38h] [rbp-40h]

  if ( a3 )
  {
    return (unsigned int)-2147023728;
  }
  else
  {
    v18 = 0;
    lpVtbl = a1->lpVtbl;
    *(_OWORD *)propvar = 0;
    if ( ((int (__fastcall *)(struct IPropertyStore *, const struct _tagpropertykey *, PROPVARIANT *))lpVtbl->GetValue)(
           a1,
           a2,
           propvar) < 0
      || LOWORD(propvar[0]) < 2u )
    {
      v7 = -2147023728;
    }
    else
    {
      ppszOut = 0;
      v7 = PropVariantToStringAlloc(propvar, &ppszOut);
      if ( v7 >= 0 )
      {
        v8 = ppszOut;
        v9 = (*(__int64 (__fastcall **)(struct IHMEMediaContainer *))(*(_QWORD *)a4 + 56LL))(a4);
        v10 = -1;
        v11 = (const unsigned __int16 *)v9;
        v12 = -1;
        do
          ++v12;
        while ( *(_WORD *)(v9 + 2 * v12) );
        do
          ++v10;
        while ( v8[v10] );
        v13 = v12 + v10 + 2;
        a5->vt = 31;
        v14 = (unsigned __int16 *)CoTaskMemAlloc(2 * v13);
        a5->hVal.QuadPart = (LONGLONG)v14;
        if ( v14 )
        {
          v7 = StringCchCopyW(v14, v13, v11);
          if ( v7 >= 0 )
          {
            *(_WORD *)(a5->hVal.QuadPart + 2 * v12) = 45;
            v7 = StringCchCopyW((unsigned __int16 *)(a5->hVal.QuadPart + 2 + 2 * v12), v13 - v12 - 1, v8);
          }
        }
        else
        {
          v7 = -2147024882;
        }
      }
      CoTaskMemFree(ppszOut);
    }
    PropVariantClear(propvar);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x140027710  push    rbx
0x140027712  push    rbp
0x140027713  push    rsi
0x140027714  push    rdi
0x140027715  push    r14
0x140027717  push    r15
0x140027719  sub     rsp, 48h
0x14002771d  xor     r15d, r15d
0x140027720  mov     rdi, r9
0x140027723  test    r8d, r8d
0x140027726  jnz     loc_140027844
0x14002772c  xor     eax, eax
0x14002772e  lea     r8, [rsp+78h+propvar]
0x140027733  mov     [rsp+78h+var_40], rax
0x140027738  xorps   xmm0, xmm0
0x14002773b  mov     rax, [rcx]
0x14002773e  movups  xmmword ptr [rsp+78h+propvar], xmm0
0x140027743  mov     rax, [rax+28h]
0x140027747  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002774c  test    eax, eax
0x14002774e  js      loc_14002783D
0x140027754  cmp     word ptr [rsp+78h+propvar], 2
0x14002775a  jb      loc_14002783D
0x140027760  lea     rdx, [rsp+78h+ppszOut]; ppszOut
0x140027765  mov     [rsp+78h+ppszOut], r15
0x14002776a  lea     rcx, [rsp+78h+propvar]; propvar
0x14002776f  call    cs:__imp_PropVariantToStringAlloc
0x140027775  mov     ebx, eax
0x140027777  test    eax, eax
0x140027779  js      short loc_1400277DB
0x14002777b  mov     rax, [rdi]
0x14002777e  mov     rcx, rdi
0x140027781  mov     rbp, [rsp+78h+ppszOut]
0x140027786  mov     rax, [rax+38h]
0x14002778a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002778f  or      rcx, 0FFFFFFFFFFFFFFFFh
0x140027793  mov     rbx, rax
0x140027796  mov     rdi, rcx
0x140027799  inc     rdi
0x14002779c  cmp     [rax+rdi*2], r15w
0x1400277a1  jnz     short loc_140027799
0x1400277a3  inc     rcx
0x1400277a6  cmp     [rbp+rcx*2+0], r15w
0x1400277ac  jnz     short loc_1400277A3
0x1400277ae  mov     r14, [rsp+78h+arg_20]
0x1400277b6  lea     rsi, [rcx+2]
0x1400277ba  add     rsi, rdi
0x1400277bd  mov     word ptr [r14], 1Fh
0x1400277c3  lea     rcx, [rsi+rsi]; cb
0x1400277c7  call    cs:__imp_CoTaskMemAlloc
0x1400277cd  mov     [r14+8], rax
0x1400277d1  test    rax, rax
0x1400277d4  jnz     short loc_140027800
0x1400277d6  mov     ebx, 8007000Eh
0x1400277db  mov     rcx, [rsp+78h+ppszOut]; pv
0x1400277e0  call    cs:__imp_CoTaskMemFree
0x1400277e6  lea     rcx, [rsp+78h+propvar]; pvar
0x1400277eb  call    cs:__imp_PropVariantClear
0x1400277f1  mov     eax, ebx
0x1400277f3  add     rsp, 48h
0x1400277f7  pop     r15
0x1400277f9  pop     r14
0x1400277fb  pop     rdi
0x1400277fc  pop     rsi
0x1400277fd  pop     rbp
0x1400277fe  pop     rbx
0x1400277ff  retn
0x140027800  mov     r8, rbx; unsigned __int16 *
0x140027803  mov     rdx, rsi; unsigned __int64
0x140027806  mov     rcx, rax; unsigned __int16 *
0x140027809  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x14002780e  mov     ebx, eax
0x140027810  test    eax, eax
0x140027812  js      short loc_1400277DB
0x140027814  mov     rax, [r14+8]
0x140027818  sub     rsi, rdi
0x14002781b  mov     r8, rbp; unsigned __int16 *
0x14002781e  mov     word ptr [rax+rdi*2], 2Dh ; '-'
0x140027824  lea     rdx, [rsi-1]; unsigned __int64
0x140027828  mov     rcx, [r14+8]
0x14002782c  add     rcx, 2
0x140027830  lea     rcx, [rcx+rdi*2]; unsigned __int16 *
0x140027834  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x140027839  mov     ebx, eax
0x14002783b  jmp     short loc_1400277DB
0x14002783d  mov     ebx, 80070490h
0x140027842  jmp     short loc_1400277E6
0x140027844  mov     ebx, 80070490h
0x140027849  jmp     short loc_1400277F1
```
