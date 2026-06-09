# CPreflistDropTarget::CreateTarget(_ITEMIDLIST const *,CSingletonPtr<CWlanProfileStore> &,CProfile const &,ATL::CComPtr<CPreflistDropTarget> &)

- ea: `0x18001369c`
- end: `0x180013730`
- name: `?CreateTarget@CPreflistDropTarget@@SAJPEFBU_ITEMIDLIST@@AEAV?$CSingletonPtr@VCWlanProfileStore@@@@AEBVCProfile@@AEAV?$CComPtr@VCPreflistDropTarget@@@ATL@@@Z`
- size: `148`
- prototype: `__int64 __fastcall(LPCITEMIDLIST pidl, struct IUnknown *, const struct CProfile *, struct IUnknown **)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000f770`

## callees

- `0x18000d578`
- `0x1800135c8`
- `0x18001369c`
- `0x180027648`

## import_xrefs

- `SHELL32!__imp_ILClone` at `0x1800136e1`
- `SHELL32!__imp_ILClone` at `0x1800136e1`

## pseudocode

```c
__int64 __fastcall CPreflistDropTarget::CreateTarget(
        LPCITEMIDLIST pidl,
        struct IUnknown *a2,
        const struct CProfile *a3,
        struct IUnknown **a4)
{
  __int64 result; // rax
  LPITEMIDLIST v8; // rdi
  struct IUnknown *v9; // [rsp+38h] [rbp+10h] BYREF

  v9 = a2;
  if ( *((_BYTE *)a3 + 81) )
    return 2147942487LL;
  v9 = 0;
  result = ATL::CComObject<CPreflistDropTarget>::CreateInstance(&v9);
  if ( (int)result >= 0 )
  {
    v8 = ILClone(pidl);
    if ( v8 )
    {
      if ( *a4 != v9 )
        ATL::AtlComPtrAssign(a4, v9);
      (*a4)[8].lpVtbl = (struct IUnknownVtbl *)v8;
      CProfile::Clone((CProfile *)&(*a4)[10], a3);
      return 0;
    }
    else
    {
      return 2147942414LL;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18001369c  mov     [rsp+arg_0], rbx
0x1800136a1  mov     [rsp+arg_10], rsi
0x1800136a6  mov     [rsp+arg_8], rdx
0x1800136ab  push    rdi
0x1800136ac  sub     rsp, 20h
0x1800136b0  cmp     byte ptr [r8+51h], 0
0x1800136b5  mov     rbx, r9
0x1800136b8  mov     rsi, r8
0x1800136bb  mov     rdi, rcx
0x1800136be  jz      short loc_1800136C7
0x1800136c0  mov     eax, 80070057h
0x1800136c5  jmp     short loc_180013720
0x1800136c7  lea     rcx, [rsp+28h+arg_8]
0x1800136cc  mov     [rsp+28h+arg_8], 0
0x1800136d5  call    ?CreateInstance@?$CComObject@VCPreflistDropTarget@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CPreflistDropTarget>::CreateInstance(ATL::CComObject<CPreflistDropTarget> * *)
0x1800136da  test    eax, eax
0x1800136dc  js      short loc_180013720
0x1800136de  mov     rcx, rdi; pidl
0x1800136e1  call    cs:__imp_ILClone
0x1800136e7  mov     rdi, rax
0x1800136ea  test    rax, rax
0x1800136ed  jnz     short loc_1800136F6
0x1800136ef  mov     eax, 8007000Eh
0x1800136f4  jmp     short loc_180013720
0x1800136f6  mov     rdx, [rsp+28h+arg_8]; struct IUnknown *
0x1800136fb  cmp     [rbx], rdx
0x1800136fe  jz      short loc_180013708
0x180013700  mov     rcx, rbx; struct IUnknown **
0x180013703  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x180013708  mov     rax, [rbx]
0x18001370b  mov     rdx, rsi; struct CProfile *
0x18001370e  mov     [rax+40h], rdi
0x180013712  mov     rcx, [rbx]
0x180013715  add     rcx, 50h ; 'P'; this
0x180013719  call    ?Clone@CProfile@@IEAAXAEBV1@@Z; CProfile::Clone(CProfile const &)
0x18001371e  xor     eax, eax
0x180013720  mov     rbx, [rsp+28h+arg_0]
0x180013725  mov     rsi, [rsp+28h+arg_10]
0x18001372a  add     rsp, 20h
0x18001372e  pop     rdi
0x18001372f  retn
```
