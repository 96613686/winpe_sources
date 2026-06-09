# CScopePicker::_CheckChildren(_ITEMIDLIST_ABSOLUTE *)

- ea: `0x180024f0c`
- end: `0x180025065`
- name: `?_CheckChildren@CScopePicker@@AEAAJPEAU_ITEMIDLIST_ABSOLUTE@@@Z`
- size: `345`
- prototype: `int(CScopePicker *__hidden this, struct _ITEMIDLIST_ABSOLUTE *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180024950`

## callees

- `0x1800038ac`
- `0x180024f0c`
- `0x18002cc10`
- `0x18002cd24`
- `0x18002d2f0`
- `0x18002d918`
- `0x180032010`

## import_xrefs

- `SHELL32!__imp_ILCombine` at `0x180024fdb`
- `SHELL32!__imp_ILCombine` at `0x180024fdb`
- `SHELL32!__imp_ILFree` at `0x180025005`
- `SHELL32!__imp_ILFree` at `0x18002501c`
- `SHELL32!__imp_ILFree` at `0x18002502b`
- `SHELL32!__imp_ILFree` at `0x180025005`
- `SHELL32!__imp_ILFree` at `0x18002501c`
- `SHELL32!__imp_ILFree` at `0x18002502b`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CScopePicker::_CheckChildren(CScopePicker *this, struct _ITEMIDLIST_ABSOLUTE *a2)
{
  CShellWrappers *v3; // r14
  int ContentEnumFromAbsPidl; // ebx
  CShellWrappers *v5; // rcx
  CShellWrappers *v6; // rcx
  const struct _ITEMIDLIST_ABSOLUTE *v7; // rax
  ITEMIDLIST *v8; // rdi
  struct IShellFolder *v10; // [rsp+30h] [rbp-20h] BYREF
  struct IEnumIDList *v11; // [rsp+38h] [rbp-18h] BYREF
  struct IEnumIDList *v12[2]; // [rsp+40h] [rbp-10h] BYREF
  unsigned int v13; // [rsp+90h] [rbp+40h] BYREF
  LPCITEMIDLIST pidl2; // [rsp+98h] [rbp+48h] BYREF

  v12[0] = 0;
  v3 = (CScopePicker *)((char *)this + 1744);
  ContentEnumFromAbsPidl = CShellWrappers::GetContentEnumFromAbsPidl((CScopePicker *)((char *)this + 1744), a2, v12);
  if ( ContentEnumFromAbsPidl == -2147467263 )
    ContentEnumFromAbsPidl = 1;
  v10 = 0;
  if ( !ContentEnumFromAbsPidl )
    ContentEnumFromAbsPidl = CShellWrappers::GetParentFolderFromAbsPidl(v3, a2, &v10);
  pidl2 = 0;
  if ( !ContentEnumFromAbsPidl )
  {
    while ( 1 )
    {
      ContentEnumFromAbsPidl = ((__int64 (__fastcall *)(struct IEnumIDList *, __int64, LPCITEMIDLIST *, _QWORD))v12[0]->lpVtbl->Next)(
                                 v12[0],
                                 1,
                                 &pidl2,
                                 0);
      if ( ContentEnumFromAbsPidl )
        break;
      v13 = 0;
      if ( !(unsigned int)CShellWrappers::GetAttribsFromChildPidl(v5, v10, (const struct _ITEMID_CHILD *)pidl2, 0, &v13)
        && !(unsigned int)CShellWrappers::IsDisplayableObject(v6, v10, (const struct _ITEMID_CHILD *)pidl2, v13) )
      {
        v7 = (const struct _ITEMIDLIST_ABSOLUTE *)ILCombine((LPCITEMIDLIST)a2, pidl2);
        v8 = (ITEMIDLIST *)v7;
        if ( v7 )
        {
          v11 = 0;
          ContentEnumFromAbsPidl = CShellWrappers::GetContentEnumFromAbsPidl(v3, v7, &v11);
          ILFree(v8);
          if ( ContentEnumFromAbsPidl >= 0 )
          {
            ILFree((LPITEMIDLIST)pidl2);
            ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v11);
            break;
          }
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v11);
        }
      }
      ILFree((LPITEMIDLIST)pidl2);
    }
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v10);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v12);
  return (unsigned int)ContentEnumFromAbsPidl;
}

```

## disassembly

```asm
0x180024f0c  mov     [rsp-28h+arg_0], rbx
0x180024f11  push    rbp
0x180024f12  push    rsi
0x180024f13  push    rdi
0x180024f14  push    r12
0x180024f16  push    r14
0x180024f18  mov     rbp, rsp
0x180024f1b  sub     rsp, 50h
0x180024f1f  mov     rsi, rdx
0x180024f22  mov     [rbp+var_10], 0
0x180024f2a  lea     r14, [rcx+6D0h]
0x180024f31  lea     r8, [rbp+var_10]; struct IEnumIDList **
0x180024f35  mov     rcx, r14; this
0x180024f38  call    ?GetContentEnumFromAbsPidl@CShellWrappers@@QEAAJPEBU_ITEMIDLIST_ABSOLUTE@@PEAPEAUIEnumIDList@@@Z; CShellWrappers::GetContentEnumFromAbsPidl(_ITEMIDLIST_ABSOLUTE const *,IEnumIDList * *)
0x180024f3d  mov     ebx, eax
0x180024f3f  mov     r12d, 1
0x180024f45  cmp     eax, 80004001h
0x180024f4a  cmovz   ebx, r12d
0x180024f4e  mov     [rbp+var_20], 0
0x180024f56  test    ebx, ebx
0x180024f58  jnz     short loc_180024F6B
0x180024f5a  lea     r8, [rbp+var_20]; struct IShellFolder **
0x180024f5e  mov     rdx, rsi; struct _ITEMIDLIST_ABSOLUTE *
0x180024f61  mov     rcx, r14; this
0x180024f64  call    ?GetParentFolderFromAbsPidl@CShellWrappers@@QEAAJPEBU_ITEMIDLIST_ABSOLUTE@@PEAPEAUIShellFolder@@@Z; CShellWrappers::GetParentFolderFromAbsPidl(_ITEMIDLIST_ABSOLUTE const *,IShellFolder * *)
0x180024f69  mov     ebx, eax
0x180024f6b  mov     [rbp+pidl2], 0
0x180024f73  test    ebx, ebx
0x180024f75  jnz     loc_18002503C
0x180024f7b  mov     rcx, [rbp+var_10]
0x180024f7f  mov     rax, [rcx]
0x180024f82  xor     r9d, r9d
0x180024f85  lea     r8, [rbp+pidl2]
0x180024f89  mov     edx, r12d
0x180024f8c  mov     rax, [rax+18h]
0x180024f90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024f95  mov     ebx, eax
0x180024f97  test    eax, eax
0x180024f99  jnz     loc_18002503C
0x180024f9f  mov     [rbp+arg_10], eax
0x180024fa2  lea     rax, [rbp+arg_10]
0x180024fa6  mov     [rsp+50h+var_30], rax; unsigned int *
0x180024fab  xor     r9d, r9d; unsigned int *
0x180024fae  mov     r8, [rbp+pidl2]; struct _ITEMID_CHILD *
0x180024fb2  mov     rdx, [rbp+var_20]; struct IShellFolder *
0x180024fb6  call    ?GetAttribsFromChildPidl@CShellWrappers@@QEAAJPEAUIShellFolder@@PEBU_ITEMID_CHILD@@PEAK2@Z; CShellWrappers::GetAttribsFromChildPidl(IShellFolder *,_ITEMID_CHILD const *,ulong *,ulong *)
0x180024fbb  test    eax, eax
0x180024fbd  jnz     short loc_180025018
0x180024fbf  mov     r9d, [rbp+arg_10]; unsigned int
0x180024fc3  mov     r8, [rbp+pidl2]; struct _ITEMID_CHILD *
0x180024fc7  mov     rdx, [rbp+var_20]; struct IShellFolder *
0x180024fcb  call    ?IsDisplayableObject@CShellWrappers@@QEAAJPEAUIShellFolder@@PEBU_ITEMID_CHILD@@K@Z; CShellWrappers::IsDisplayableObject(IShellFolder *,_ITEMID_CHILD const *,ulong)
0x180024fd0  test    eax, eax
0x180024fd2  jnz     short loc_180025018
0x180024fd4  mov     rdx, [rbp+pidl2]; pidl2
0x180024fd8  mov     rcx, rsi; pidl1
0x180024fdb  call    cs:__imp_ILCombine
0x180024fe1  mov     rdi, rax
0x180024fe4  test    rax, rax
0x180024fe7  jz      short loc_180025018
0x180024fe9  mov     [rbp+var_18], 0
0x180024ff1  lea     r8, [rbp+var_18]; struct IEnumIDList **
0x180024ff5  mov     rdx, rax; struct _ITEMIDLIST_ABSOLUTE *
0x180024ff8  mov     rcx, r14; this
0x180024ffb  call    ?GetContentEnumFromAbsPidl@CShellWrappers@@QEAAJPEBU_ITEMIDLIST_ABSOLUTE@@PEAPEAUIEnumIDList@@@Z; CShellWrappers::GetContentEnumFromAbsPidl(_ITEMIDLIST_ABSOLUTE const *,IEnumIDList * *)
0x180025000  mov     ebx, eax
0x180025002  mov     rcx, rdi; pidl
0x180025005  call    cs:__imp_ILFree
0x18002500b  test    ebx, ebx
0x18002500d  jns     short loc_180025027
0x18002500f  lea     rcx, [rbp+var_18]
0x180025013  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180025018  mov     rcx, [rbp+pidl2]; pidl
0x18002501c  call    cs:__imp_ILFree
0x180025022  jmp     loc_180024F7B
0x180025027  mov     rcx, [rbp+pidl2]; pidl
0x18002502b  call    cs:__imp_ILFree
0x180025031  nop
0x180025032  lea     rcx, [rbp+var_18]
0x180025036  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18002503b  nop
0x18002503c  lea     rcx, [rbp+var_20]
0x180025040  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180025045  nop
0x180025046  lea     rcx, [rbp+var_10]
0x18002504a  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18002504f  mov     eax, ebx
0x180025051  mov     rbx, [rsp+50h+arg_0]
0x180025059  add     rsp, 50h
0x18002505d  pop     r14
0x18002505f  pop     r12
0x180025061  pop     rdi
0x180025062  pop     rsi
0x180025063  pop     rbp
0x180025064  retn
```
