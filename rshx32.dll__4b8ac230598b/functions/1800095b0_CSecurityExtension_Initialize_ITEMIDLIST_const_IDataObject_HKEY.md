# CSecurityExtension::Initialize(_ITEMIDLIST const *,IDataObject *,HKEY__ *)

- ea: `0x1800095b0`
- end: `0x1800095fa`
- name: `?Initialize@CSecurityExtension@@UEAAJPEFBU_ITEMIDLIST@@PEAUIDataObject@@PEAUHKEY__@@@Z`
- size: `74`
- prototype: `__int64 __fastcall(CSecurityExtension *__hidden this, const struct _ITEMIDLIST *, struct IDataObject *, HKEY)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800095b0`
- `0x18001e010`

## pseudocode

```c
__int64 __fastcall CSecurityExtension::Initialize(
        CSecurityExtension *this,
        const struct _ITEMIDLIST *a2,
        struct IDataObject *a3,
        HKEY a4)
{
  __int64 v6; // rcx

  v6 = *((_QWORD *)this + 4);
  if ( v6 )
    (*(void (__fastcall **)(__int64, const struct _ITEMIDLIST *, struct IDataObject *, HKEY))(*(_QWORD *)v6 + 16LL))(
      v6,
      a2,
      a3,
      a4);
  *((_QWORD *)this + 4) = a3;
  if ( a3 )
    ((void (__fastcall *)(struct IDataObject *, const struct _ITEMIDLIST *, struct IDataObject *, HKEY))a3->lpVtbl->AddRef)(
      a3,
      a2,
      a3,
      a4);
  return 0;
}

```

## disassembly

```asm
0x1800095b0  mov     [rsp+arg_0], rbx
0x1800095b5  push    rdi
0x1800095b6  sub     rsp, 20h
0x1800095ba  mov     rdi, rcx
0x1800095bd  mov     rbx, r8
0x1800095c0  mov     rcx, [rcx+20h]
0x1800095c4  test    rcx, rcx
0x1800095c7  jz      short loc_1800095D5
0x1800095c9  mov     rax, [rcx]
0x1800095cc  mov     rax, [rax+10h]
0x1800095d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800095d5  mov     [rdi+20h], rbx
0x1800095d9  test    rbx, rbx
0x1800095dc  jz      short loc_1800095ED
0x1800095de  mov     rax, [rbx]
0x1800095e1  mov     rcx, rbx
0x1800095e4  mov     rax, [rax+8]
0x1800095e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800095ed  mov     rbx, [rsp+28h+arg_0]
0x1800095f2  xor     eax, eax
0x1800095f4  add     rsp, 20h
0x1800095f8  pop     rdi
0x1800095f9  retn
```
