# TaDllGetClassObject(_GUID const &,_GUID const &,void * *)

- ea: `0x18000a490`
- end: `0x18000a553`
- name: `?TaDllGetClassObject@@YAJAEBU_GUID@@0PEAPEAX@Z`
- size: `195`
- prototype: `__int64 __fastcall(const struct _GUID *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180006da0`

## callees

- `0x180003200`
- `0x18000a2e0`
- `0x18000a490`
- `0x18000e010`

## pseudocode

```c
__int64 __fastcall TaDllGetClassObject(const struct _GUID *a1, const struct _GUID *a2, void **a3)
{
  struct TaClassTable near **i; // rcx
  const struct TaDescUnknown *v8; // rdi
  __int64 v9; // rax
  CClassFactory *v10; // rax
  CClassFactory *v11; // rax
  CClassFactory *v12; // rdi
  unsigned int v13; // ebx

  if ( !a3 )
    return 2147500035LL;
  for ( i = &g_TaClassTable; ; i += 3 )
  {
    if ( !*(_DWORD *)i )
      return 2147746065LL;
    v8 = i[2];
    v9 = **(_QWORD **)v8 - *(_QWORD *)&a1->Data1;
    if ( !v9 )
      v9 = *(_QWORD *)(*(_QWORD *)v8 + 8LL) - *(_QWORD *)a1->Data4;
    if ( !v9 )
      break;
  }
  v10 = (CClassFactory *)operator new(0x18u);
  if ( v10 && (v11 = CClassFactory::CClassFactory(v10, v8), (v12 = v11) != 0) )
  {
    v13 = (**(__int64 (__fastcall ***)(CClassFactory *, const struct _GUID *, void **))v11)(v11, a2, a3);
    (*(void (__fastcall **)(CClassFactory *))(*(_QWORD *)v12 + 16LL))(v12);
    return v13;
  }
  else
  {
    *a3 = 0;
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x18000a490  mov     [rsp+arg_0], rbx
0x18000a495  mov     [rsp+arg_8], rsi
0x18000a49a  push    rdi
0x18000a49b  sub     rsp, 20h
0x18000a49f  mov     rbx, r8
0x18000a4a2  mov     rsi, rdx
0x18000a4a5  mov     r8, rcx
0x18000a4a8  test    rbx, rbx
0x18000a4ab  jnz     short loc_18000A4B7
0x18000a4ad  mov     eax, 80004003h
0x18000a4b2  jmp     loc_18000A543
0x18000a4b7  lea     rcx, ?g_TaClassTable@@3PAUTaClassTable@@A; TaClassTable near * g_TaClassTable
0x18000a4be  cmp     dword ptr [rcx], 0
0x18000a4c1  jz      short loc_18000A53E
0x18000a4c3  mov     rdi, [rcx+10h]
0x18000a4c7  mov     rdx, [rdi]
0x18000a4ca  mov     rax, [rdx]
0x18000a4cd  sub     rax, [r8]
0x18000a4d0  jnz     short loc_18000A4DA
0x18000a4d2  mov     rax, [rdx+8]
0x18000a4d6  sub     rax, [r8+8]
0x18000a4da  test    rax, rax
0x18000a4dd  jz      short loc_18000A4E5
0x18000a4df  add     rcx, 18h
0x18000a4e3  jmp     short loc_18000A4BE
0x18000a4e5  mov     ecx, 18h; Size
0x18000a4ea  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000a4ef  test    rax, rax
0x18000a4f2  jz      short loc_18000A530
0x18000a4f4  mov     rdx, rdi; struct TaDescUnknown *
0x18000a4f7  mov     rcx, rax; this
0x18000a4fa  call    ??0CClassFactory@@QEAA@PEBUTaDescUnknown@@@Z; CClassFactory::CClassFactory(TaDescUnknown const *)
0x18000a4ff  mov     rdi, rax
0x18000a502  test    rax, rax
0x18000a505  jz      short loc_18000A530
0x18000a507  mov     rcx, [rax]
0x18000a50a  mov     r8, rbx
0x18000a50d  mov     rdx, rsi
0x18000a510  mov     rax, [rcx]
0x18000a513  mov     rcx, rdi
0x18000a516  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a51b  mov     rcx, [rdi]
0x18000a51e  mov     ebx, eax
0x18000a520  mov     rax, [rcx+10h]
0x18000a524  mov     rcx, rdi
0x18000a527  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a52c  mov     eax, ebx
0x18000a52e  jmp     short loc_18000A543
0x18000a530  mov     qword ptr [rbx], 0
0x18000a537  mov     eax, 8007000Eh
0x18000a53c  jmp     short loc_18000A543
0x18000a53e  mov     eax, 80040111h
0x18000a543  mov     rbx, [rsp+28h+arg_0]
0x18000a548  mov     rsi, [rsp+28h+arg_8]
0x18000a54d  add     rsp, 20h
0x18000a551  pop     rdi
0x18000a552  retn
```
