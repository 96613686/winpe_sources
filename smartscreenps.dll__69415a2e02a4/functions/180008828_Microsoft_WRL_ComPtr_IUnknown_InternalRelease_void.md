# Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)

- ea: `0x180008828`
- end: `0x18000884f`
- name: `?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ`
- size: `39`
- prototype: ``
- caller_count: `9`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000a3a4`
- `0x18000a4ec`
- `0x18000a634`
- `0x18000a8dc`
- `0x18000a98c`
- `0x18000aad0`
- `0x18000abc8`
- `0x18000ac90`
- `0x18000ae90`

## callees

- `0x180008828`
- `0x18000e010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(__int64 *a1)
{
  __int64 result; // rax
  __int64 v3; // rcx

  result = 0;
  v3 = *a1;
  if ( v3 )
  {
    *a1 = 0;
    return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  }
  return result;
}

```

## disassembly

```asm
0x180008828  sub     rsp, 28h
0x18000882c  mov     rdx, rcx
0x18000882f  xor     eax, eax
0x180008831  mov     rcx, [rcx]
0x180008834  test    rcx, rcx
0x180008837  jz      short loc_180008849
0x180008839  mov     [rdx], rax
0x18000883c  mov     rax, [rcx]
0x18000883f  mov     rax, [rax+10h]
0x180008843  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008848  nop
0x180008849  add     rsp, 28h
0x18000884d  retn
```
