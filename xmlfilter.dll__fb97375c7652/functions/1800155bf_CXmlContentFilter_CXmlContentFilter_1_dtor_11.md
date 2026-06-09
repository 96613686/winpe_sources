# _CXmlContentFilter::CXmlContentFilter_::_1_::dtor$11

- ea: `0x1800155bf`
- end: `0x1800155cb`
- name: `_CXmlContentFilter::CXmlContentFilter_::_1_::dtor$11`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x18000ed70`

## pseudocode

```c
__int64 __fastcall CXmlContentFilter::CXmlContentFilter_::_1_::dtor_11(__int64 a1, __int64 a2)
{
  return CVarBuffer<CElement,64>::~CVarBuffer<CElement,64>(*(_QWORD *)(a2 + 32));
}

```

## disassembly

```asm
0x1800155bf  mov     rcx, [rdx+20h]
0x1800155c6  jmp     ??1?$CVarBuffer@VCElement@@$0EA@@@QEAA@XZ; CVarBuffer<CElement,64>::~CVarBuffer<CElement,64>(void)
```
