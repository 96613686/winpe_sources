# Microsoft::WRL::ComPtr<Windows::Foundation::ITypedEventHandler<Windows::Graphics::Holographic::Internal::HolographicDisplayWatcher *,Windows::Graphics::Holographic::HolographicDisplay *>>::~ComPtr<Windows::Foundation::ITypedEventHandler<Windows::Graphics::Holographic::Internal::HolographicDisplayWatcher *,Windows::Graphics::Holographic::HolographicDisplay *>>(void)

- ea: `0x18000457c`
- end: `0x1800045a4`
- name: `??1?$ComPtr@U?$ITypedEventHandler@PEAVHolographicDisplayWatcher@Internal@Holographic@Graphics@Windows@@PEAVHolographicDisplay@345@@Foundation@Windows@@@WRL@Microsoft@@QEAA@XZ`
- size: `40`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000eec1`
- `0x18000ef2f`
- `0x18000f7ad`
- `0x18000fb60`
- `0x18000fb8c`
- `0x18000fb9e`
- `0x18000fbb0`

## callees

- `0x18000457c`
- `0x180010010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall Microsoft::WRL::ComPtr<Windows::Foundation::ITypedEventHandler<Windows::Graphics::Holographic::Internal::HolographicDisplayWatcher *,Windows::Graphics::Holographic::HolographicDisplay *>>::~ComPtr<Windows::Foundation::ITypedEventHandler<Windows::Graphics::Holographic::Internal::HolographicDisplayWatcher *,Windows::Graphics::Holographic::HolographicDisplay *>>(
        _QWORD *a1)
{
  _QWORD *result; // rax
  __int64 v2; // rcx

  result = a1;
  v2 = *a1;
  if ( v2 )
  {
    *result = 0;
    return (_QWORD *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  }
  return result;
}

```

## disassembly

```asm
0x18000457c  sub     rsp, 28h
0x180004580  mov     rax, rcx
0x180004583  mov     rcx, [rcx]
0x180004586  test    rcx, rcx
0x180004589  jz      short loc_18000459F
0x18000458b  mov     qword ptr [rax], 0
0x180004592  mov     rax, [rcx]
0x180004595  mov     rax, [rax+10h]
0x180004599  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000459e  nop
0x18000459f  add     rsp, 28h
0x1800045a3  retn
```
