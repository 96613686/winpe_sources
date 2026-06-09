# _ImagingHandler::CreateImagingFactory_::_1_::dtor$1

- ea: `0x18001a66d`
- end: `0x18001a679`
- name: `_ImagingHandler::CreateImagingFactory_::_1_::dtor$1`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000fdb4`

## pseudocode

```c
void __fastcall ImagingHandler::CreateImagingFactory_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  tip2::test_data_control<tip2::details::merged_data<_tip_ImagingHandlerInitTipTest,_tip_ImagingHandlerInitTipTest>>::~test_data_control<tip2::details::merged_data<_tip_ImagingHandlerInitTipTest,_tip_ImagingHandlerInitTipTest>>((__int64 *)(a2 + 168));
}

```

## disassembly

```asm
0x18001a66d  lea     rcx, [rdx+0A8h]
0x18001a674  jmp     ??1?$test_data_control@V?$merged_data@U_tip_ImagingHandlerInitTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_ImagingHandlerInitTipTest,_tip_ImagingHandlerInitTipTest>>::~test_data_control<tip2::details::merged_data<_tip_ImagingHandlerInitTipTest,_tip_ImagingHandlerInitTipTest>>(void)
```
