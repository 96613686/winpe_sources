# std::filesystem::path::~path(void)

- ea: `0x1800296c0`
- end: `0x1800296c5`
- name: `??1path@filesystem@std@@QEAA@XZ`
- size: `5`
- prototype: `void __fastcall(std::filesystem::path *__hidden this)`
- caller_count: `169`
- callee_count: `1`
- tags: ``

## callers

- `0x180037064`
- `0x1800489be`
- `0x1800489d0`
- `0x180048a18`
- `0x180048a60`
- `0x180048ad0`
- `0x180048ae2`
- `0x180048af4`
- `0x180048b3c`
- `0x180048b84`
- `0x180048b96`
- `0x180048bea`
- `0x180048bfc`
- `0x180048c28`
- `0x180048c54`
- `0x180048c66`
- `0x180048c78`
- `0x180048c8e`
- `0x180048ca0`
- `0x180048d18`
- `0x180048f6d`
- `0x180048f7f`
- `0x180048fb5`
- `0x180048feb`
- `0x180048ffd`
- `0x18004900f`
- `0x180049021`
- `0x180049197`
- `0x1800491df`
- `0x1800491f1`
- `0x180049215`
- `0x180049227`
- `0x1800496c7`
- `0x1800497c5`
- `0x1800497fb`
- `0x18004980d`
- `0x18004981f`
- `0x180049a6c`
- `0x180049a98`
- `0x180049b76`
- `0x180049e5b`
- `0x180049f05`
- `0x180049fad`
- `0x180049fdc`
- `0x18004a02e`
- `0x18004a134`
- `0x18004a14a`
- `0x18004a1ac`
- `0x18004a298`
- `0x18004a2ae`

## callees

- `0x180029644`

## pseudocode

```c
// attributes: thunk
void __fastcall std::filesystem::path::~path(std::filesystem::path *this)
{
  std::wstring::_Tidy_deallocate(this);
}

```

## disassembly

```asm
0x1800296c0  jmp     ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
```
