# ATL::CComPtrBase<ITypeInfo>::IsEqualObject(IUnknown *)

- ea: `0x180017f04`
- end: `0x180017f92`
- name: `?IsEqualObject@?$CComPtrBase@UITypeInfo@@@ATL@@QEAA_NPEAUIUnknown@@@Z`
- size: `142`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001795c`

## callees

- `0x180016668`
- `0x180017f04`
- `0x18001b010`

## pseudocode

```c
bool __fastcall ATL::CComPtrBase<ITypeInfo>::IsEqualObject(
        void (__fastcall ****a1)(_QWORD, GUID *, __int64 *),
        void (__fastcall ***a2)(_QWORD, GUID *, __int64 *))
{
  void (__fastcall ***v3)(_QWORD, GUID *, __int64 *); // rcx
  bool v5; // bl
  __int64 v6; // [rsp+30h] [rbp+8h] BYREF
  __int64 v7; // [rsp+40h] [rbp+18h] BYREF

  v3 = *a1;
  if ( !v3 )
    return a2 == 0;
  if ( !a2 )
    return 0;
  v7 = 0;
  v6 = 0;
  (**v3)(v3, &GUID_00000000_0000_0000_c000_000000000046, &v7);
  (**a2)(a2, &GUID_00000000_0000_0000_c000_000000000046, &v6);
  v5 = v7 == v6;
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v6);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v7);
  return v5;
}

```

## disassembly

```asm
0x180017f04  push    rbx
0x180017f06  sub     rsp, 20h
0x180017f0a  mov     rbx, rdx
0x180017f0d  mov     rcx, [rcx]
0x180017f10  test    rcx, rcx
0x180017f13  jnz     short loc_180017F1D
0x180017f15  test    rdx, rdx
0x180017f18  setz    al
0x180017f1b  jmp     short loc_180017F8C
0x180017f1d  test    rbx, rbx
0x180017f20  jz      short loc_180017F8A
0x180017f22  mov     [rsp+28h+arg_10], 0
0x180017f2b  mov     [rsp+28h+arg_0], 0
0x180017f34  mov     rax, [rcx]
0x180017f37  lea     r8, [rsp+28h+arg_10]
0x180017f3c  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x180017f43  mov     rax, [rax]
0x180017f46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017f4b  mov     rax, [rbx]
0x180017f4e  lea     r8, [rsp+28h+arg_0]
0x180017f53  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x180017f5a  mov     rcx, rbx
0x180017f5d  mov     rax, [rax]
0x180017f60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017f65  mov     rax, [rsp+28h+arg_0]
0x180017f6a  cmp     [rsp+28h+arg_10], rax
0x180017f6f  setz    bl
0x180017f72  lea     rcx, [rsp+28h+arg_0]
0x180017f77  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180017f7c  lea     rcx, [rsp+28h+arg_10]
0x180017f81  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180017f86  mov     al, bl
0x180017f88  jmp     short loc_180017F8C
0x180017f8a  xor     al, al
0x180017f8c  add     rsp, 20h
0x180017f90  pop     rbx
0x180017f91  retn
```
