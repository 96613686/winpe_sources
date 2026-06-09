# CShellPropertyThunk::RefIDThunk(IPropertyStore *,_tagpropertykey const &,long,IHMEMediaContainer *,tagPROPVARIANT *)

- ea: `0x140027860`
- end: `0x1400279e7`
- name: `?RefIDThunk@CShellPropertyThunk@@CAJPEAUIPropertyStore@@AEBU_tagpropertykey@@JPEAUIHMEMediaContainer@@PEAUtagPROPVARIANT@@@Z`
- size: `391`
- prototype: `__int64 __usercall@<rax>(struct IPropertyStore *@<rcx>, const struct _tagpropertykey *@<rdx>, int@<r8d>, struct IHMEMediaContainer *@<r9>, struct tagPROPVARIANT *)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task`

## callees

- `0x140008550`
- `0x140027860`
- `0x1400279f0`
- `0x14009e010`

## import_xrefs

- `ole32!PropVariantClear` at `0x1400279c2`
- `ole32!PropVariantClear` at `0x1400279c2`
- `ole32!CoTaskMemFree` at `0x1400279b1`
- `ole32!CoTaskMemFree` at `0x1400279b1`
- `PROPSYS!PropVariantToStringAlloc` at `0x140027946`
- `PROPSYS!PropVariantToStringAlloc` at `0x140027946`

## pseudocode

```c
__int64 __fastcall CShellPropertyThunk::RefIDThunk(
        struct IPropertyStore *a1,
        const struct _tagpropertykey *a2,
        int a3,
        struct IHMEMediaContainer *a4,
        struct tagPROPVARIANT *a5)
{
  unsigned __int16 *v8; // rax
  int v9; // edx
  unsigned __int16 *v10; // rax
  int v11; // edx
  unsigned __int16 *v12; // rax
  int v13; // edx
  struct IPropertyStoreVtbl *lpVtbl; // rax
  __int64 v15; // rdx
  int UpnpClassForItem; // ebx
  const unsigned __int16 *v17; // rcx
  PWSTR ppszOut; // [rsp+20h] [rbp-28h] BYREF
  PROPVARIANT propvar[2]; // [rsp+28h] [rbp-20h] BYREF
  __int64 v21; // [rsp+38h] [rbp-10h]
  int v22; // [rsp+80h] [rbp+38h] BYREF

  if ( a3 )
    return (unsigned int)-2147023728;
  v8 = (unsigned __int16 *)(*(__int64 (__fastcall **)(struct IHMEMediaContainer *))(*(_QWORD *)a4 + 56LL))(a4);
  v9 = *v8 - 52;
  if ( *v8 == 52 )
    v9 = v8[1];
  if ( !v9 )
    goto LABEL_25;
  v10 = (unsigned __int16 *)(*(__int64 (__fastcall **)(struct IHMEMediaContainer *))(*(_QWORD *)a4 + 56LL))(a4);
  v11 = *v10 - 56;
  if ( *v10 == 56 )
    v11 = v10[1];
  if ( !v11 )
    goto LABEL_25;
  v12 = (unsigned __int16 *)(*(__int64 (__fastcall **)(struct IHMEMediaContainer *))(*(_QWORD *)a4 + 56LL))(a4);
  v13 = *v12 - 66;
  if ( *v12 == 66 )
    v13 = v12[1];
  if ( !v13 )
  {
LABEL_25:
    UpnpClassForItem = 0;
    a5->vt = 0;
    return (unsigned int)UpnpClassForItem;
  }
  v21 = 0;
  lpVtbl = a1->lpVtbl;
  *(_OWORD *)propvar = 0;
  if ( ((int (__fastcall *)(struct IPropertyStore *, const struct _tagpropertykey *, PROPVARIANT *))lpVtbl->GetValue)(
         a1,
         a2,
         propvar) < 0
    || LOWORD(propvar[0]) < 2u )
  {
    UpnpClassForItem = -2147023728;
    goto LABEL_24;
  }
  ppszOut = 0;
  UpnpClassForItem = PropVariantToStringAlloc(propvar, &ppszOut);
  if ( UpnpClassForItem >= 0 )
  {
    v22 = 0;
    UpnpClassForItem = CUpnpClassMapper::GetUpnpClassForItem(a1, v15, (enum CUpnpClassMapper::CdsItemClass *)&v22);
    if ( UpnpClassForItem >= 0 )
    {
      if ( (unsigned int)(v22 - 5) <= 2 )
      {
        v17 = L"4";
LABEL_21:
        UpnpClassForItem = CShellPropertyThunk::MakeItemObjectID(v17, ppszOut, a5);
        goto LABEL_22;
      }
      if ( (unsigned int)(v22 - 1) <= 3 )
      {
        v17 = L"8";
        goto LABEL_21;
      }
      if ( (unsigned int)(v22 - 8) <= 1 )
      {
        v17 = L"B";
        goto LABEL_21;
      }
    }
  }
LABEL_22:
  CoTaskMemFree(ppszOut);
LABEL_24:
  PropVariantClear(propvar);
  return (unsigned int)UpnpClassForItem;
}

```

## disassembly

```asm
0x140027860  push    rbp
0x140027862  push    rbx
0x140027863  push    rsi
0x140027864  push    rdi
0x140027865  mov     rbp, rsp
0x140027868  sub     rsp, 48h
0x14002786c  mov     rbx, r9
0x14002786f  mov     rsi, rdx
0x140027872  mov     rdi, rcx
0x140027875  test    r8d, r8d
0x140027878  jnz     loc_1400279D7
0x14002787e  mov     rax, [r9]
0x140027881  mov     rcx, rbx
0x140027884  mov     rax, [rax+38h]
0x140027888  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002788d  movzx   edx, word ptr [rax]
0x140027890  sub     edx, 34h ; '4'
0x140027893  jnz     short loc_1400278A0
0x140027895  movzx   edx, word ptr [rax+2]
0x140027899  xor     eax, eax
0x14002789b  movzx   ecx, ax
0x14002789e  sub     edx, ecx
0x1400278a0  test    edx, edx
0x1400278a2  jz      loc_1400279CA
0x1400278a8  mov     rax, [rbx]
0x1400278ab  mov     rcx, rbx
0x1400278ae  mov     rax, [rax+38h]
0x1400278b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400278b7  movzx   edx, word ptr [rax]
0x1400278ba  sub     edx, 38h ; '8'
0x1400278bd  jnz     short loc_1400278CA
0x1400278bf  movzx   edx, word ptr [rax+2]
0x1400278c3  xor     eax, eax
0x1400278c5  movzx   ecx, ax
0x1400278c8  sub     edx, ecx
0x1400278ca  test    edx, edx
0x1400278cc  jz      loc_1400279CA
0x1400278d2  mov     rax, [rbx]
0x1400278d5  mov     rcx, rbx
0x1400278d8  mov     rax, [rax+38h]
0x1400278dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400278e1  movzx   edx, word ptr [rax]
0x1400278e4  sub     edx, 42h ; 'B'
0x1400278e7  jnz     short loc_1400278F4
0x1400278e9  movzx   edx, word ptr [rax+2]
0x1400278ed  xor     eax, eax
0x1400278ef  movzx   ecx, ax
0x1400278f2  sub     edx, ecx
0x1400278f4  test    edx, edx
0x1400278f6  jz      loc_1400279CA
0x1400278fc  xor     eax, eax
0x1400278fe  lea     r8, [rbp+propvar]
0x140027902  mov     [rbp+var_10], rax
0x140027906  xorps   xmm0, xmm0
0x140027909  mov     rax, [rdi]
0x14002790c  mov     rdx, rsi
0x14002790f  mov     rcx, rdi
0x140027912  movups  xmmword ptr [rbp+propvar], xmm0
0x140027916  mov     rax, [rax+28h]
0x14002791a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002791f  test    eax, eax
0x140027921  js      loc_1400279B9
0x140027927  mov     esi, 2
0x14002792c  cmp     word ptr [rbp+propvar], si
0x140027930  jb      loc_1400279B9
0x140027936  lea     rdx, [rbp+ppszOut]; ppszOut
0x14002793a  mov     [rbp+ppszOut], 0
0x140027942  lea     rcx, [rbp+propvar]; propvar
0x140027946  call    cs:__imp_PropVariantToStringAlloc
0x14002794c  mov     ebx, eax
0x14002794e  test    eax, eax
0x140027950  js      short loc_1400279AD
0x140027952  lea     r8, [rbp+arg_10]; enum CUpnpClassMapper::CdsItemClass *
0x140027956  mov     [rbp+arg_10], 0
0x14002795d  mov     rcx, rdi; struct IPropertyStore *
0x140027960  call    ?GetUpnpClassForItem@CUpnpClassMapper@@SAJPEAUIPropertyStore@@_NPEAW4CdsItemClass@1@@Z; CUpnpClassMapper::GetUpnpClassForItem(IPropertyStore *,bool,CUpnpClassMapper::CdsItemClass *)
0x140027965  mov     ebx, eax
0x140027967  test    eax, eax
0x140027969  js      short loc_1400279AD
0x14002796b  mov     ecx, [rbp+arg_10]
0x14002796e  lea     eax, [rcx-5]
0x140027971  cmp     eax, esi
0x140027973  ja      short loc_14002797E
0x140027975  lea     rcx, a4; "4"
0x14002797c  jmp     short loc_14002799E
0x14002797e  lea     eax, [rcx-1]
0x140027981  cmp     eax, 3
0x140027984  ja      short loc_14002798F
0x140027986  lea     rcx, a8; "8"
0x14002798d  jmp     short loc_14002799E
0x14002798f  lea     eax, [rcx-8]
0x140027992  cmp     eax, 1
0x140027995  ja      short loc_1400279AD
0x140027997  lea     rcx, aB; "B"
0x14002799e  mov     r8, [rbp+arg_20]; struct tagPROPVARIANT *
0x1400279a2  mov     rdx, [rbp+ppszOut]; unsigned __int16 *
0x1400279a6  call    ?MakeItemObjectID@CShellPropertyThunk@@SAJPEBG0PEAUtagPROPVARIANT@@@Z; CShellPropertyThunk::MakeItemObjectID(ushort const *,ushort const *,tagPROPVARIANT *)
0x1400279ab  mov     ebx, eax
0x1400279ad  mov     rcx, [rbp+ppszOut]; pv
0x1400279b1  call    cs:__imp_CoTaskMemFree
0x1400279b7  jmp     short loc_1400279BE
0x1400279b9  mov     ebx, 80070490h
0x1400279be  lea     rcx, [rbp+propvar]; pvar
0x1400279c2  call    cs:__imp_PropVariantClear
0x1400279c8  jmp     short loc_1400279DC
0x1400279ca  mov     rax, [rbp+arg_20]
0x1400279ce  xor     ebx, ebx
0x1400279d0  xor     ecx, ecx
0x1400279d2  mov     [rax], cx
0x1400279d5  jmp     short loc_1400279DC
0x1400279d7  mov     ebx, 80070490h
0x1400279dc  mov     eax, ebx
0x1400279de  add     rsp, 48h
0x1400279e2  pop     rdi
0x1400279e3  pop     rsi
0x1400279e4  pop     rbx
0x1400279e5  pop     rbp
0x1400279e6  retn
```
