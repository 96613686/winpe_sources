# ATL::CAxHostWindow::QueryService(_GUID const &,_GUID const &,void * *)

- ea: `0x1400077c0`
- end: `0x1400077e6`
- name: `?QueryService@CAxHostWindow@ATL@@UEAAJAEBU_GUID@@0PEAPEAX@Z`
- size: `38`
- prototype: `__int64 __fastcall(ATL::CAxHostWindow *__hidden this, const struct _GUID *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x1400077c0`
- `0x14000f010`

## pseudocode

```c
__int64 __fastcall ATL::CAxHostWindow::QueryService(
        ATL::CAxHostWindow *this,
        const struct _GUID *a2,
        const struct _GUID *a3,
        void **a4)
{
  __int64 v4; // rcx
  __int64 result; // rax

  v4 = *((_QWORD *)this + 25);
  result = 2147500034LL;
  if ( v4 )
    return (*(__int64 (__fastcall **)(__int64, const struct _GUID *, const struct _GUID *, void **))(*(_QWORD *)v4 + 24LL))(
             v4,
             a2,
             a3,
             a4);
  return result;
}

```

## disassembly

```asm
0x1400077c0  sub     rsp, 38h
0x1400077c4  mov     rcx, [rcx+0C8h]
0x1400077cb  mov     eax, 80004002h
0x1400077d0  test    rcx, rcx
0x1400077d3  jz      short loc_1400077E1
0x1400077d5  mov     rax, [rcx]
0x1400077d8  mov     rax, [rax+18h]
0x1400077dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400077e1  add     rsp, 38h
0x1400077e5  retn
```
