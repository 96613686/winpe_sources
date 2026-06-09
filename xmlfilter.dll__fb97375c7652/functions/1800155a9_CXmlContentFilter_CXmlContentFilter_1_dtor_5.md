# _CXmlContentFilter::CXmlContentFilter_::_1_::dtor$5

- ea: `0x1800155a9`
- end: `0x1800155b9`
- name: `_CXmlContentFilter::CXmlContentFilter_::_1_::dtor$5`
- size: `16`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x1800044fc`

## pseudocode

```c
__int64 __fastcall CXmlContentFilter::CXmlContentFilter_::_1_::dtor_5(__int64 a1, __int64 a2)
{
  return TVarString<16>::~TVarString<16>(*(_QWORD *)(a2 + 72) + 48LL);
}

```

## disassembly

```asm
0x1800155a9  mov     rcx, [rdx+48h]
0x1800155b0  add     rcx, 30h ; '0'
0x1800155b4  jmp     ??1?$TVarString@$0BA@@@QEAA@XZ; TVarString<16>::~TVarString<16>(void)
```
