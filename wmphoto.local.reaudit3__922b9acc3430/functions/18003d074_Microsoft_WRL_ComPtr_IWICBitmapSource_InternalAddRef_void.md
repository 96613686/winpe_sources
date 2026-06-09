# Microsoft::WRL::ComPtr<IWICBitmapSource>::InternalAddRef(void)

- ea: `0x18003d074`
- end: `0x18003d093`
- name: `?InternalAddRef@?$ComPtr@UIWICBitmapSource@@@WRL@Microsoft@@IEBAXXZ`
- size: `31`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18003d7c0`

## callees

- `0x18003d074`
- `0x180045010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ComPtr<IWICBitmapSource>::InternalAddRef(__int64 *a1)
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
0x18003d074  sub     rsp, 28h
0x18003d078  mov     rcx, [rcx]
0x18003d07b  test    rcx, rcx
0x18003d07e  jz      short loc_18003D08D
0x18003d080  mov     rax, [rcx]
0x18003d083  mov     rax, [rax+8]
0x18003d087  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d08c  nop
0x18003d08d  add     rsp, 28h
0x18003d091  retn
```
