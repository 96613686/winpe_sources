# CWSHExtension::Initialize(_ITEMIDLIST const *,IDataObject *,HKEY__ *)

- ea: `0x180009fe0`
- end: `0x18000a032`
- name: `?Initialize@CWSHExtension@@UEAAJPEFBU_ITEMIDLIST@@PEAUIDataObject@@PEAUHKEY__@@@Z`
- size: `82`
- prototype: `__int64 __fastcall(CWSHExtension *__hidden this, const struct _ITEMIDLIST *, struct IDataObject *, HKEY)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180009fe0`
- `0x18000e010`

## pseudocode

```c
__int64 __fastcall CWSHExtension::Initialize(
        CWSHExtension *this,
        const struct _ITEMIDLIST *a2,
        struct IDataObject *a3,
        HKEY a4)
{
  __int64 v6; // rcx

  v6 = *((_QWORD *)this + 9);
  if ( v6 )
  {
    (*(void (__fastcall **)(__int64, const struct _ITEMIDLIST *, struct IDataObject *, HKEY))(*(_QWORD *)v6 + 16LL))(
      v6,
      a2,
      a3,
      a4);
    *((_QWORD *)this + 9) = 0;
  }
  if ( a3 )
  {
    *((_QWORD *)this + 9) = a3;
    ((void (__fastcall *)(struct IDataObject *, const struct _ITEMIDLIST *, struct IDataObject *, HKEY))a3->lpVtbl->AddRef)(
      a3,
      a2,
      a3,
      a4);
  }
  return 0;
}

```

## disassembly

```asm
0x180009fe0  mov     [rsp+arg_0], rbx
0x180009fe5  push    rdi
0x180009fe6  sub     rsp, 20h
0x180009fea  mov     rdi, rcx
0x180009fed  mov     rbx, r8
0x180009ff0  mov     rcx, [rcx+48h]
0x180009ff4  test    rcx, rcx
0x180009ff7  jz      short loc_18000A00D
0x180009ff9  mov     rax, [rcx]
0x180009ffc  mov     rax, [rax+10h]
0x18000a000  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a005  mov     qword ptr [rdi+48h], 0
0x18000a00d  test    rbx, rbx
0x18000a010  jz      short loc_18000A025
0x18000a012  mov     [rdi+48h], rbx
0x18000a016  mov     rcx, rbx
0x18000a019  mov     rax, [rbx]
0x18000a01c  mov     rax, [rax+8]
0x18000a020  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a025  mov     rbx, [rsp+28h+arg_0]
0x18000a02a  xor     eax, eax
0x18000a02c  add     rsp, 20h
0x18000a030  pop     rdi
0x18000a031  retn
```
