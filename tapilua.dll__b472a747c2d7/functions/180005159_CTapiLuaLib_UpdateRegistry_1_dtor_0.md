# _CTapiLuaLib::UpdateRegistry_::_1_::dtor$0

- ea: `0x180005159`
- end: `0x180005165`
- name: `_CTapiLuaLib::UpdateRegistry_::_1_::dtor$0`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, installer_update`

## callees

- `0x180001edc`

## pseudocode

```c
void __fastcall CTapiLuaLib::UpdateRegistry_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>((_QWORD **)(a2 + 88));
}

```

## disassembly

```asm
0x180005159  lea     rcx, [rdx+58h]
0x180005160  jmp     ??1?$CAtlSafeAllocBufferManager@V_CCRTAllocator@_ATL_SAFE_ALLOCA_IMPL@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>(void)
```
