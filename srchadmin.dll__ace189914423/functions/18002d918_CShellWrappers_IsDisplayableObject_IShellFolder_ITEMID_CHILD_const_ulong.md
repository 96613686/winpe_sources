# CShellWrappers::IsDisplayableObject(IShellFolder *,_ITEMID_CHILD const *,ulong)

- ea: `0x18002d918`
- end: `0x18002da33`
- name: `?IsDisplayableObject@CShellWrappers@@QEAAJPEAUIShellFolder@@PEBU_ITEMID_CHILD@@K@Z`
- size: `283`
- prototype: `__int64 __fastcall(CShellWrappers *__hidden this, struct IShellFolder *, const struct _ITEMID_CHILD *, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180024f0c`
- `0x180025b24`

## callees

- `0x1800038ac`
- `0x18002d918`
- `0x180032010`

## import_xrefs

- `SHELL32!SHCreateShellItem` at `0x18002d939`
- `SHELL32!SHCreateShellItem` at `0x18002d939`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CShellWrappers::IsDisplayableObject(
        CShellWrappers *this,
        struct IShellFolder *a2,
        const ITEMIDLIST *a3,
        int a4)
{
  HRESULT v5; // edi
  __int64 (__fastcall ***v6)(_QWORD, GUID *, CShellWrappers **); // rcx
  unsigned int v7; // ebx
  __int64 v9; // [rsp+30h] [rbp-28h] BYREF
  __int64 (__fastcall ***v10)(_QWORD, GUID *, CShellWrappers **); // [rsp+38h] [rbp-20h] BYREF
  IShellItem *ppsi[3]; // [rsp+40h] [rbp-18h] BYREF
  CShellWrappers *v12; // [rsp+80h] [rbp+28h] BYREF

  v12 = this;
  ppsi[0] = 0;
  v5 = SHCreateShellItem(0, a2, a3, ppsi);
  v6 = 0;
  v10 = 0;
  if ( v5 >= 0 )
  {
    v5 = ((__int64 (__fastcall *)(IShellItem *, _QWORD, const GUID *, GUID *, __int64 (__fastcall ****)(_QWORD, GUID *, CShellWrappers **)))ppsi[0]->lpVtbl->BindToHandler)(
           ppsi[0],
           0,
           &BHID_SFObject,
           &GUID_000214e6_0000_0000_c000_000000000046,
           &v10);
    v6 = v10;
  }
  v9 = 0;
  if ( v5 >= 0 )
  {
    v5 = -2147467262;
    v9 = 0;
    if ( v6 )
    {
      v12 = 0;
      v5 = (**v6)(v6, &GUID_a6087428_3be3_4d73_b308_7c04a540bf1a, &v12);
      if ( v5 >= 0 )
      {
        v5 = (*(__int64 (__fastcall **)(CShellWrappers *, GUID *, GUID *, __int64 *))(*(_QWORD *)v12 + 24LL))(
               v12,
               &GUID_c3be0d61_c82a_4abe_bf10_330f84a45c82,
               &GUID_607c87f7_0696_4558_a368_de5e59cfe456,
               &v9);
        (*(void (__fastcall **)(CShellWrappers *))(*(_QWORD *)v12 + 16LL))(v12);
      }
    }
  }
  v7 = 0;
  if ( v5 >= 0 )
    v7 = v5;
  if ( (a4 & 0x60400000) == 0x60400000 )
    v7 = 1;
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v9);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v10);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(ppsi);
  return v7;
}

```

## disassembly

```asm
0x18002d918  mov     [rsp-20h+arg_0], rcx
0x18002d91d  push    rbp
0x18002d91e  push    rbx
0x18002d91f  push    rsi
0x18002d920  push    rdi
0x18002d921  mov     rbp, rsp
0x18002d924  sub     rsp, 58h
0x18002d928  mov     esi, r9d
0x18002d92b  mov     [rbp+ppsi], 0
0x18002d933  lea     r9, [rbp+ppsi]; ppsi
0x18002d937  xor     ecx, ecx; pidlParent
0x18002d939  call    cs:__imp_SHCreateShellItem
0x18002d93f  mov     edi, eax
0x18002d941  xor     ecx, ecx
0x18002d943  mov     [rbp+var_20], rcx
0x18002d947  test    eax, eax
0x18002d949  js      short loc_18002D97A
0x18002d94b  mov     rcx, [rbp+ppsi]
0x18002d94f  mov     rax, [rcx]
0x18002d952  lea     rdx, [rbp+var_20]
0x18002d956  mov     [rsp+58h+var_38], rdx
0x18002d95b  lea     r9, _GUID_000214e6_0000_0000_c000_000000000046
0x18002d962  lea     r8, BHID_SFObject
0x18002d969  xor     edx, edx
0x18002d96b  mov     rax, [rax+18h]
0x18002d96f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d974  mov     edi, eax
0x18002d976  mov     rcx, [rbp+var_20]
0x18002d97a  mov     [rbp+var_28], 0
0x18002d982  test    edi, edi
0x18002d984  js      short loc_18002D9F0
0x18002d986  mov     edi, 80004002h
0x18002d98b  mov     [rbp+var_28], 0
0x18002d993  test    rcx, rcx
0x18002d996  jz      short loc_18002D9F0
0x18002d998  mov     [rbp+arg_0], 0
0x18002d9a0  mov     rax, [rcx]
0x18002d9a3  lea     r8, [rbp+arg_0]
0x18002d9a7  lea     rdx, _GUID_a6087428_3be3_4d73_b308_7c04a540bf1a
0x18002d9ae  mov     rax, [rax]
0x18002d9b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d9b6  mov     edi, eax
0x18002d9b8  test    eax, eax
0x18002d9ba  js      short loc_18002D9F0
0x18002d9bc  mov     rcx, [rbp+arg_0]
0x18002d9c0  mov     rax, [rcx]
0x18002d9c3  lea     r9, [rbp+var_28]
0x18002d9c7  lea     r8, _GUID_607c87f7_0696_4558_a368_de5e59cfe456
0x18002d9ce  lea     rdx, _GUID_c3be0d61_c82a_4abe_bf10_330f84a45c82
0x18002d9d5  mov     rax, [rax+18h]
0x18002d9d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d9de  mov     edi, eax
0x18002d9e0  mov     rcx, [rbp+arg_0]
0x18002d9e4  mov     rax, [rcx]
0x18002d9e7  mov     rax, [rax+10h]
0x18002d9eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d9f0  xor     ebx, ebx
0x18002d9f2  test    edi, edi
0x18002d9f4  cmovns  ebx, edi
0x18002d9f7  test    ebx, ebx
0x18002d9f9  js      short loc_18002DA0B
0x18002d9fb  mov     eax, 60400000h
0x18002da00  and     esi, eax
0x18002da02  cmp     esi, eax
0x18002da04  jnz     short loc_18002DA0B
0x18002da06  mov     ebx, 1
0x18002da0b  lea     rcx, [rbp+var_28]
0x18002da0f  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18002da14  nop
0x18002da15  lea     rcx, [rbp+var_20]
0x18002da19  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18002da1e  nop
0x18002da1f  lea     rcx, [rbp+ppsi]
0x18002da23  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18002da28  mov     eax, ebx
0x18002da2a  add     rsp, 58h
0x18002da2e  pop     rdi
0x18002da2f  pop     rsi
0x18002da30  pop     rbx
0x18002da31  pop     rbp
0x18002da32  retn
```
