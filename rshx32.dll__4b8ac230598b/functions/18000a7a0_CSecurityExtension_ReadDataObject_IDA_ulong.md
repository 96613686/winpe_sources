# CSecurityExtension::_ReadDataObject(_IDA *,ulong *)

- ea: `0x18000a7a0`
- end: `0x18000a986`
- name: `?_ReadDataObject@CSecurityExtension@@AEAAJPEAU_IDA@@PEAK@Z`
- size: `486`
- prototype: `__int64 __fastcall(CSecurityExtension *__hidden this, struct _IDA *, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180008d90`

## callees

- `0x18000907c`
- `0x18000a7a0`
- `0x18001e010`

## import_xrefs

- `SHELL32!SHBindToObject` at `0x18000a7f8`
- `SHELL32!SHBindToObject` at `0x18000a7f8`
- `SHELL32!SHBindToFolderIDListParentEx` at `0x18000a8bc`
- `SHELL32!SHBindToFolderIDListParentEx` at `0x18000a8bc`
- `SHELL32!SHBindToFolderIDListParent` at `0x18000a82e`
- `SHELL32!SHBindToFolderIDListParent` at `0x18000a82e`

## pseudocode

```c
__int64 __fastcall CSecurityExtension::_ReadDataObject(CSecurityExtension *this, struct _IDA *a2, unsigned int *a3)
{
  bool v3; // zf
  HRESULT v7; // ebx
  const ITEMIDLIST *v8; // rdx
  int v9; // edi
  IShellFolder *v10; // rcx
  LPCITEMIDLIST ppidlLast; // [rsp+30h] [rbp-20h] BYREF
  void *ppv; // [rsp+38h] [rbp-18h] BYREF
  LPCITEMIDLIST v14[2]; // [rsp+40h] [rbp-10h] BYREF
  int v15; // [rsp+88h] [rbp+38h] BYREF
  IShellFolder *v16; // [rsp+90h] [rbp+40h] BYREF
  IShellFolder *psfRoot; // [rsp+98h] [rbp+48h] BYREF

  v3 = a2->cidl == 1;
  psfRoot = 0;
  v16 = 0;
  *a3 = 0;
  if ( v3 )
  {
    v7 = SHBindToObject(
           0,
           (LPCITEMIDLIST)((char *)a2 + a2->aoffset[0]),
           0,
           &GUID_93f2f68c_1d1b_11d3_a30e_00c04f79abd1,
           (void **)&psfRoot);
    if ( v7 < 0
      || (v8 = (const ITEMIDLIST *)((char *)a2 + a2[1].cidl),
          ppidlLast = 0,
          v7 = SHBindToFolderIDListParent(
                 psfRoot,
                 v8,
                 &GUID_93f2f68c_1d1b_11d3_a30e_00c04f79abd1,
                 (void **)&v16,
                 &ppidlLast),
          v7 < 0)
      || (v7 = DisplayNameOfAsLocalAlloc(
                 v16,
                 ppidlLast,
                 32769 - (*((_DWORD *)this + 7) != 3),
                 (unsigned __int16 **)this + 8),
          v7 < 0)
      || (v7 = DisplayNameOfAsLocalAlloc(
                 psfRoot,
                 (const struct _ITEMIDLIST *)((char *)a2 + a2[1].cidl),
                 0,
                 (unsigned __int16 **)this + 7),
          v7 < 0) )
    {
      v10 = v16;
    }
    else
    {
      v9 = 0;
      v14[0] = 0;
      ppv = 0;
      if ( SHBindToFolderIDListParentEx(v16, ppidlLast, 0, &GUID_000214e6_0000_0000_c000_000000000046, &ppv, v14) >= 0 )
      {
        v15 = 1614807040;
        if ( (*(int (__fastcall **)(void *, __int64, LPCITEMIDLIST *, int *))(*(_QWORD *)ppv + 72LL))(ppv, 1, v14, &v15) >= 0 )
          v9 = v15 & 0x60400000;
        (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
      }
      v10 = v16;
      if ( v16 )
      {
        ((void (__fastcall *)(IShellFolder *))v16->lpVtbl->Release)(v16);
        v10 = 0;
        v16 = 0;
      }
      if ( *((_DWORD *)this + 7) != 1 || (v9 & 0x40000000) != 0 )
      {
        if ( (v9 & 0x20400000) == 0x20000000 )
          *a3 |= 1u;
      }
      else
      {
        v7 = -2147467259;
      }
    }
    if ( v10 )
    {
      ((void (__fastcall *)(IShellFolder *))v10->lpVtbl->Release)(v10);
      v16 = 0;
    }
    if ( psfRoot )
      ((void (__fastcall *)(IShellFolder *))psfRoot->lpVtbl->Release)(psfRoot);
  }
  else
  {
    return (unsigned int)-2147467259;
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18000a7a0  push    rbp
0x18000a7a2  push    rbx
0x18000a7a3  push    rsi
0x18000a7a4  push    rdi
0x18000a7a5  push    r14
0x18000a7a7  mov     rbp, rsp
0x18000a7aa  sub     rsp, 50h
0x18000a7ae  cmp     dword ptr [rdx], 1
0x18000a7b1  mov     rsi, r8
0x18000a7b4  mov     rdi, rdx
0x18000a7b7  mov     [rbp+psfRoot], 0
0x18000a7bf  mov     r14, rcx
0x18000a7c2  mov     [rbp+arg_10], 0
0x18000a7ca  mov     dword ptr [r8], 0
0x18000a7d1  jz      short loc_18000A7DD
0x18000a7d3  mov     ebx, 80004005h
0x18000a7d8  jmp     loc_18000A979
0x18000a7dd  mov     edx, [rdx+4]
0x18000a7e0  lea     rax, [rbp+psfRoot]
0x18000a7e4  add     rdx, rdi; pidl
0x18000a7e7  mov     [rsp+50h+ppv], rax; ppv
0x18000a7ec  lea     r9, _GUID_93f2f68c_1d1b_11d3_a30e_00c04f79abd1; riid
0x18000a7f3  xor     r8d, r8d; pbc
0x18000a7f6  xor     ecx, ecx; psf
0x18000a7f8  call    cs:__imp_SHBindToObject
0x18000a7fe  mov     ebx, eax
0x18000a800  test    eax, eax
0x18000a802  js      loc_18000A947
0x18000a808  mov     edx, [rdi+8]
0x18000a80b  lea     rax, [rbp+ppidlLast]
0x18000a80f  mov     rcx, [rbp+psfRoot]; psfRoot
0x18000a813  lea     r9, [rbp+arg_10]; ppv
0x18000a817  add     rdx, rdi; pidl
0x18000a81a  mov     [rbp+ppidlLast], 0
0x18000a822  lea     r8, _GUID_93f2f68c_1d1b_11d3_a30e_00c04f79abd1; riid
0x18000a829  mov     [rsp+50h+ppv], rax; ppidlLast
0x18000a82e  call    cs:__imp_SHBindToFolderIDListParent
0x18000a834  mov     ebx, eax
0x18000a836  test    eax, eax
0x18000a838  js      loc_18000A947
0x18000a83e  mov     rdx, [rbp+ppidlLast]; struct _ITEMIDLIST *
0x18000a842  lea     r9, [r14+40h]; unsigned __int16 **
0x18000a846  mov     rcx, [rbp+arg_10]; struct IShellFolder *
0x18000a84a  mov     eax, 3
0x18000a84f  sub     eax, [r14+1Ch]
0x18000a853  neg     eax
0x18000a855  sbb     r8d, r8d
0x18000a858  add     r8d, 8001h; unsigned int
0x18000a85f  call    ?DisplayNameOfAsLocalAlloc@@YAJPEAUIShellFolder@@PEFBU_ITEMIDLIST@@KPEAPEAG@Z; DisplayNameOfAsLocalAlloc(IShellFolder *,_ITEMIDLIST const *,ulong,ushort * *)
0x18000a864  mov     ebx, eax
0x18000a866  test    eax, eax
0x18000a868  js      loc_18000A947
0x18000a86e  mov     edx, [rdi+8]
0x18000a871  lea     r9, [r14+38h]; unsigned __int16 **
0x18000a875  mov     rcx, [rbp+psfRoot]; struct IShellFolder *
0x18000a879  add     rdx, rdi; struct _ITEMIDLIST *
0x18000a87c  xor     r8d, r8d; unsigned int
0x18000a87f  call    ?DisplayNameOfAsLocalAlloc@@YAJPEAUIShellFolder@@PEFBU_ITEMIDLIST@@KPEAPEAG@Z; DisplayNameOfAsLocalAlloc(IShellFolder *,_ITEMIDLIST const *,ulong,ushort * *)
0x18000a884  mov     ebx, eax
0x18000a886  test    eax, eax
0x18000a888  js      loc_18000A947
0x18000a88e  mov     rdx, [rbp+ppidlLast]; pidl
0x18000a892  lea     rax, [rbp+var_10]
0x18000a896  mov     rcx, [rbp+arg_10]; psfRoot
0x18000a89a  lea     r9, _GUID_000214e6_0000_0000_c000_000000000046; riid
0x18000a8a1  mov     [rsp+50h+var_28], rax; ppidlLast
0x18000a8a6  xor     edi, edi
0x18000a8a8  lea     rax, [rbp+var_18]
0x18000a8ac  mov     [rbp+var_10], rdi
0x18000a8b0  xor     r8d, r8d; ppbc
0x18000a8b3  mov     [rsp+50h+ppv], rax; ppv
0x18000a8b8  mov     [rbp+var_18], rdi
0x18000a8bc  call    cs:__imp_SHBindToFolderIDListParentEx
0x18000a8c2  test    eax, eax
0x18000a8c4  js      short loc_18000A905
0x18000a8c6  mov     rcx, [rbp+var_18]
0x18000a8ca  lea     r9, [rbp+arg_8]
0x18000a8ce  mov     [rbp+arg_8], 60400000h
0x18000a8d5  lea     r8, [rbp+var_10]
0x18000a8d9  lea     edx, [rdi+1]
0x18000a8dc  mov     rax, [rcx]
0x18000a8df  mov     rax, [rax+48h]
0x18000a8e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a8e8  test    eax, eax
0x18000a8ea  js      short loc_18000A8F5
0x18000a8ec  mov     edi, [rbp+arg_8]
0x18000a8ef  and     edi, 60400000h
0x18000a8f5  mov     rcx, [rbp+var_18]
0x18000a8f9  mov     rax, [rcx]
0x18000a8fc  mov     rax, [rax+10h]
0x18000a900  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a905  mov     rcx, [rbp+arg_10]
0x18000a909  test    rcx, rcx
0x18000a90c  jz      short loc_18000A920
0x18000a90e  mov     rax, [rcx]
0x18000a911  mov     rax, [rax+10h]
0x18000a915  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a91a  xor     ecx, ecx
0x18000a91c  mov     [rbp+arg_10], rcx
0x18000a920  cmp     dword ptr [r14+1Ch], 1
0x18000a925  jnz     short loc_18000A934
0x18000a927  bt      edi, 1Eh
0x18000a92b  jb      short loc_18000A934
0x18000a92d  mov     ebx, 80004005h
0x18000a932  jmp     short loc_18000A94B
0x18000a934  and     edi, 20400000h
0x18000a93a  cmp     edi, 20000000h
0x18000a940  jnz     short loc_18000A94B
0x18000a942  or      dword ptr [rsi], 1
0x18000a945  jmp     short loc_18000A94B
0x18000a947  mov     rcx, [rbp+arg_10]
0x18000a94b  test    rcx, rcx
0x18000a94e  jz      short loc_18000A964
0x18000a950  mov     rax, [rcx]
0x18000a953  mov     rax, [rax+10h]
0x18000a957  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a95c  mov     [rbp+arg_10], 0
0x18000a964  mov     rcx, [rbp+psfRoot]
0x18000a968  test    rcx, rcx
0x18000a96b  jz      short loc_18000A979
0x18000a96d  mov     rax, [rcx]
0x18000a970  mov     rax, [rax+10h]
0x18000a974  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a979  mov     eax, ebx
0x18000a97b  add     rsp, 50h
0x18000a97f  pop     r14
0x18000a981  pop     rdi
0x18000a982  pop     rsi
0x18000a983  pop     rbx
0x18000a984  pop     rbp
0x18000a985  retn
```
