# ATL::CComPtrBase<IPnpInterface>::IsEqualObject(IUnknown *)

- ea: `0x18001c058`
- end: `0x18001c0e6`
- name: `?IsEqualObject@?$CComPtrBase@UIPnpInterface@@@ATL@@QEAA_NPEAUIUnknown@@@Z`
- size: `142`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000d000`

## callees

- `0x18000eb68`
- `0x18001c058`
- `0x180021010`

## pseudocode

```c
bool __fastcall ATL::CComPtrBase<IPnpInterface>::IsEqualObject(
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
0x18001c058  push    rbx
0x18001c05a  sub     rsp, 20h
0x18001c05e  mov     rbx, rdx
0x18001c061  mov     rcx, [rcx]
0x18001c064  test    rcx, rcx
0x18001c067  jnz     short loc_18001C071
0x18001c069  test    rdx, rdx
0x18001c06c  setz    al
0x18001c06f  jmp     short loc_18001C0E0
0x18001c071  test    rbx, rbx
0x18001c074  jz      short loc_18001C0DE
0x18001c076  mov     [rsp+28h+arg_10], 0
0x18001c07f  mov     [rsp+28h+arg_0], 0
0x18001c088  mov     rax, [rcx]
0x18001c08b  lea     r8, [rsp+28h+arg_10]
0x18001c090  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x18001c097  mov     rax, [rax]
0x18001c09a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c09f  mov     rax, [rbx]
0x18001c0a2  lea     r8, [rsp+28h+arg_0]
0x18001c0a7  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x18001c0ae  mov     rcx, rbx
0x18001c0b1  mov     rax, [rax]
0x18001c0b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c0b9  mov     rax, [rsp+28h+arg_0]
0x18001c0be  cmp     [rsp+28h+arg_10], rax
0x18001c0c3  setz    bl
0x18001c0c6  lea     rcx, [rsp+28h+arg_0]
0x18001c0cb  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001c0d0  lea     rcx, [rsp+28h+arg_10]
0x18001c0d5  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001c0da  mov     al, bl
0x18001c0dc  jmp     short loc_18001C0E0
0x18001c0de  xor     al, al
0x18001c0e0  add     rsp, 20h
0x18001c0e4  pop     rbx
0x18001c0e5  retn
```
