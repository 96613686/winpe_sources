# ATL::CComPtr<ITypeInfo>::operator=<ITypeInfo2>(ATL::CComPtr<ITypeInfo2> const &)

- ea: `0x180001ff8`
- end: `0x180002100`
- name: `??$?4UITypeInfo2@@@?$CComPtr@UITypeInfo@@@ATL@@QEAAPEAUITypeInfo@@AEBV?$CComPtr@UITypeInfo2@@@1@@Z`
- size: `264`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180005e28`

## callees

- `0x180001ff8`
- `0x180015010`

## pseudocode

```c
void (__fastcall ***__fastcall ATL::CComPtr<ITypeInfo>::operator=<ITypeInfo2>(
        __int64 *a1,
        void (__fastcall ****a2)(_QWORD, GUID *, __int64 *)))(_QWORD, GUID *, __int64 *)
{
  void (__fastcall ***v2)(_QWORD, GUID *, __int64 *); // rdi
  void (__fastcall ***v4)(_QWORD, GUID *, __int64 *); // rcx
  __int64 v6; // rcx
  bool v7; // di
  void (__fastcall ***v8)(_QWORD, GUID *, __int64 *); // rcx
  __int64 v9; // rdi
  __int64 v11; // [rsp+30h] [rbp+8h] BYREF
  __int64 v12; // [rsp+38h] [rbp+10h] BYREF

  v2 = *a2;
  v4 = (void (__fastcall ***)(_QWORD, GUID *, __int64 *))*a1;
  if ( !v4 )
  {
    if ( !v2 )
      return (void (__fastcall ***)(_QWORD, GUID *, __int64 *))*a1;
    goto LABEL_10;
  }
  if ( !v2 )
    goto LABEL_10;
  v11 = 0;
  v12 = 0;
  (**v4)(v4, &GUID_00000000_0000_0000_c000_000000000046, &v11);
  (**v2)(v2, &GUID_00000000_0000_0000_c000_000000000046, &v12);
  v6 = v11;
  v7 = v11 == v12;
  if ( v12 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    v6 = v11;
  }
  if ( v6 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  if ( !v7 )
  {
LABEL_10:
    v8 = *a2;
    v9 = *a1;
    *a1 = 0;
    if ( v8 )
      (**v8)(v8, &GUID_00020401_0000_0000_c000_000000000046, a1);
    if ( v9 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
  }
  return (void (__fastcall ***)(_QWORD, GUID *, __int64 *))*a1;
}

```

## disassembly

```asm
0x180001ff8  mov     [rsp+arg_10], rbx
0x180001ffd  mov     [rsp+arg_18], rsi
0x180002002  push    rdi
0x180002003  sub     rsp, 20h
0x180002007  mov     rdi, [rdx]
0x18000200a  mov     rbx, rcx
0x18000200d  mov     rcx, [rcx]
0x180002010  mov     rsi, rdx
0x180002013  test    rcx, rcx
0x180002016  jnz     short loc_180002026
0x180002018  test    rdi, rdi
0x18000201b  jnz     loc_1800020B2
0x180002021  jmp     loc_1800020ED
0x180002026  test    rdi, rdi
0x180002029  jz      loc_1800020B2
0x18000202f  mov     [rsp+28h+arg_0], 0
0x180002038  lea     r8, [rsp+28h+arg_0]
0x18000203d  mov     [rsp+28h+arg_8], 0
0x180002046  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x18000204d  mov     rax, [rcx]
0x180002050  mov     rax, [rax]
0x180002053  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002058  mov     rax, [rdi]
0x18000205b  lea     r8, [rsp+28h+arg_8]
0x180002060  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x180002067  mov     rcx, rdi
0x18000206a  mov     rax, [rax]
0x18000206d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002072  mov     rdx, [rsp+28h+arg_8]
0x180002077  mov     rcx, [rsp+28h+arg_0]
0x18000207c  cmp     rcx, rdx
0x18000207f  setz    dil
0x180002083  test    rdx, rdx
0x180002086  jz      short loc_18000209C
0x180002088  mov     rax, [rdx]
0x18000208b  mov     rcx, rdx
0x18000208e  mov     rax, [rax+10h]
0x180002092  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002097  mov     rcx, [rsp+28h+arg_0]
0x18000209c  test    rcx, rcx
0x18000209f  jz      short loc_1800020AD
0x1800020a1  mov     rax, [rcx]
0x1800020a4  mov     rax, [rax+10h]
0x1800020a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800020ad  test    dil, dil
0x1800020b0  jnz     short loc_1800020ED
0x1800020b2  mov     rcx, [rsi]
0x1800020b5  mov     rdi, [rbx]
0x1800020b8  mov     qword ptr [rbx], 0
0x1800020bf  test    rcx, rcx
0x1800020c2  jz      short loc_1800020D9
0x1800020c4  mov     rax, [rcx]
0x1800020c7  lea     rdx, _GUID_00020401_0000_0000_c000_000000000046
0x1800020ce  mov     r8, rbx
0x1800020d1  mov     rax, [rax]
0x1800020d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800020d9  test    rdi, rdi
0x1800020dc  jz      short loc_1800020ED
0x1800020de  mov     rax, [rdi]
0x1800020e1  mov     rcx, rdi
0x1800020e4  mov     rax, [rax+10h]
0x1800020e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800020ed  mov     rax, [rbx]
0x1800020f0  mov     rbx, [rsp+28h+arg_10]
0x1800020f5  mov     rsi, [rsp+28h+arg_18]
0x1800020fa  add     rsp, 20h
0x1800020fe  pop     rdi
0x1800020ff  retn
```
