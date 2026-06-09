# Microsoft::WRL::ComPtr<IWICBitmapSource>::InternalAddRef(void)

- ea: `0x18003c864`
- end: `0x18003c882`
- name: `?InternalAddRef@?$ComPtr@UIWICBitmapSource@@@WRL@Microsoft@@IEBAXXZ`
- size: `30`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18003d050`

## callees

- `0x18003c864`
- `0x180044010`

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
0x18003c864  sub     rsp, 28h
0x18003c868  mov     rcx, [rcx]
0x18003c86b  test    rcx, rcx
0x18003c86e  jz      short loc_18003C87D
0x18003c870  mov     rax, [rcx]
0x18003c873  mov     rax, [rax+8]
0x18003c877  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c87c  nop
0x18003c87d  add     rsp, 28h
0x18003c881  retn
```
