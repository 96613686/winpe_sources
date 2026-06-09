# XMLScrServProv::QueryInterface(_GUID const &,void * *)

- ea: `0x14000c4e0`
- end: `0x14000c546`
- name: `?QueryInterface@XMLScrServProv@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `102`
- prototype: `__int64 __fastcall(XMLScrServProv *__hidden this, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, service_task`

## callees

- `0x14000c4e0`
- `0x140018010`

## pseudocode

```c
__int64 __fastcall XMLScrServProv::QueryInterface(XMLScrServProv *this, const struct _GUID *a2, void **a3)
{
  if ( !a3 )
    return 2147500035LL;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IUnknown.Data1 && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_IUnknown.Data4
    || *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IServiceProvider.Data1
    && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_IServiceProvider.Data4 )
  {
    *a3 = this;
    (*(void (__fastcall **)(XMLScrServProv *))(*(_QWORD *)this + 8LL))(this);
    return 0;
  }
  else
  {
    *a3 = 0;
    return 2147500034LL;
  }
}

```

## disassembly

```asm
0x14000c4e0  sub     rsp, 28h
0x14000c4e4  test    r8, r8
0x14000c4e7  jnz     short loc_14000C4F0
0x14000c4e9  mov     eax, 80004003h
0x14000c4ee  jmp     short loc_14000C541
0x14000c4f0  mov     rax, [rdx]
0x14000c4f3  cmp     rax, qword ptr cs:IID_IUnknown.Data1
0x14000c4fa  jnz     short loc_14000C509
0x14000c4fc  mov     rax, [rdx+8]
0x14000c500  cmp     rax, qword ptr cs:IID_IUnknown.Data4
0x14000c507  jz      short loc_14000C522
0x14000c509  mov     rax, [rdx]
0x14000c50c  cmp     rax, qword ptr cs:IID_IServiceProvider.Data1
0x14000c513  jnz     short loc_14000C535
0x14000c515  mov     rax, [rdx+8]
0x14000c519  cmp     rax, qword ptr cs:IID_IServiceProvider.Data4
0x14000c520  jnz     short loc_14000C535
0x14000c522  mov     [r8], rcx
0x14000c525  mov     rax, [rcx]
0x14000c528  mov     rax, [rax+8]
0x14000c52c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c531  xor     eax, eax
0x14000c533  jmp     short loc_14000C541
0x14000c535  mov     qword ptr [r8], 0
0x14000c53c  mov     eax, 80004002h
0x14000c541  add     rsp, 28h
0x14000c545  retn
```
