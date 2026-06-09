# _ImagingHandler::CreateImagingFactory_::_1_::dtor$0

- ea: `0x18001a65b`
- end: `0x18001a667`
- name: `_ImagingHandler::CreateImagingFactory_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000fec4`

## pseudocode

```c
void __fastcall ImagingHandler::CreateImagingFactory_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  tip2::test_watcher<tip2::details::merged_data<_tip_ImagingHandlerInitTipTest,_tip_ImagingHandlerInitTipTest>>::~test_watcher<tip2::details::merged_data<_tip_ImagingHandlerInitTipTest,_tip_ImagingHandlerInitTipTest>>(a2 + 64);
}

```

## disassembly

```asm
0x18001a65b  lea     rcx, [rdx+40h]
0x18001a662  jmp     ??1?$test_watcher@V?$merged_data@U_tip_ImagingHandlerInitTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_ImagingHandlerInitTipTest,_tip_ImagingHandlerInitTipTest>>::~test_watcher<tip2::details::merged_data<_tip_ImagingHandlerInitTipTest,_tip_ImagingHandlerInitTipTest>>(void)
```
