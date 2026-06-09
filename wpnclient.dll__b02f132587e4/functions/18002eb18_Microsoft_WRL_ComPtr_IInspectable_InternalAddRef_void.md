# Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)

- ea: `0x18002eb18`
- end: `0x18002eb35`
- name: `?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ`
- size: `29`
- prototype: ``
- caller_count: `9`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180010a54`
- `0x180010f1c`
- `0x18002ea70`
- `0x18002fdd0`
- `0x18002fe40`
- `0x180030080`
- `0x1800302f0`
- `0x180030360`
- `0x1800303e0`

## callees

- `0x18002eb18`
- `0x180032010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(__int64 *a1)
{
  __int64 v1; // rcx
  __int64 result; // rax

  v1 = *a1;
  if ( v1 )
    return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v1 + 8LL))(v1);
  return result;
}

```

## disassembly

```asm
0x18002eb18  sub     rsp, 28h
0x18002eb1c  mov     rcx, [rcx]
0x18002eb1f  test    rcx, rcx
0x18002eb22  jz      short loc_18002EB30
0x18002eb24  mov     rax, [rcx]
0x18002eb27  mov     rax, [rax+8]
0x18002eb2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002eb30  add     rsp, 28h
0x18002eb34  retn
```
