# ClearInterfaceFn(IUnknown * *)

- ea: `0x180003f70`
- end: `0x180003f97`
- name: `?ClearInterfaceFn@@YAXPEAPEAUIUnknown@@@Z`
- size: `39`
- prototype: `void __fastcall(struct IUnknown **)`
- caller_count: `10`
- callee_count: `2`
- tags: ``

## callers

- `0x180002970`
- `0x1800046d0`
- `0x180007280`
- `0x1800089d0`
- `0x180009d50`
- `0x18000af64`
- `0x18000e700`
- `0x18000e990`
- `0x18000e9e0`
- `0x18000ea30`

## callees

- `0x180003f70`
- `0x180015010`

## pseudocode

```c
void __fastcall ClearInterfaceFn(struct IUnknown **a1)
{
  __int64 v1; // rdx

  v1 = (__int64)*a1;
  *a1 = 0;
  if ( v1 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v1 + 16LL))(v1);
}

```

## disassembly

```asm
0x180003f70  sub     rsp, 28h
0x180003f74  mov     rdx, [rcx]
0x180003f77  mov     qword ptr [rcx], 0
0x180003f7e  test    rdx, rdx
0x180003f81  jz      short loc_180003F92
0x180003f83  mov     rax, [rdx]
0x180003f86  mov     rcx, rdx
0x180003f89  mov     rax, [rax+10h]
0x180003f8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003f92  add     rsp, 28h
0x180003f96  retn
```
