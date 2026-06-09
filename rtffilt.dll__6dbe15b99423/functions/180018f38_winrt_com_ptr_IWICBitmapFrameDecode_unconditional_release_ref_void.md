# winrt::com_ptr<IWICBitmapFrameDecode>::unconditional_release_ref(void)

- ea: `0x180018f38`
- end: `0x180018f5b`
- name: `?unconditional_release_ref@?$com_ptr@UIWICBitmapFrameDecode@@@winrt@@AEAAXXZ`
- size: `35`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `12`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000e22c`
- `0x18000fc20`
- `0x18000ff64`
- `0x18001003c`
- `0x180010464`
- `0x1800108a4`
- `0x180010b80`
- `0x18001153c`
- `0x1800137e8`
- `0x180013a1c`
- `0x180013b90`
- `0x180014030`

## callees

- `0x18001b010`

## pseudocode

```c
__int64 __fastcall winrt::com_ptr<IWICBitmapFrameDecode>::unconditional_release_ref(__int64 *a1)
{
  __int64 v1; // rdx

  v1 = *a1;
  *a1 = 0;
  return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v1 + 16LL))(v1);
}

```

## disassembly

```asm
0x180018f38  sub     rsp, 28h
0x180018f3c  mov     rdx, [rcx]
0x180018f3f  mov     qword ptr [rcx], 0
0x180018f46  mov     rax, [rdx]
0x180018f49  mov     rcx, rdx
0x180018f4c  mov     rax, [rax+10h]
0x180018f50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018f55  nop
0x180018f56  add     rsp, 28h
0x180018f5a  retn
```
