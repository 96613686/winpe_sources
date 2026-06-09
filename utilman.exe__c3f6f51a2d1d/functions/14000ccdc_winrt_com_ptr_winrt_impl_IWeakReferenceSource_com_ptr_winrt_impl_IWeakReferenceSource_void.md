# winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)

- ea: `0x14000ccdc`
- end: `0x14000ccf1`
- name: `??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ`
- size: `21`
- prototype: ``
- caller_count: `63`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14000cd18`
- `0x14000cd74`
- `0x14000cdd0`
- `0x14000ce2c`
- `0x14000d06c`
- `0x14000d1e8`
- `0x14000d6b0`
- `0x14000e72c`
- `0x14001d2fc`
- `0x14001d730`
- `0x14001e66c`
- `0x14001ed0c`
- `0x14001f880`
- `0x14001fd40`
- `0x1400206e8`
- `0x140021000`
- `0x1400212ec`
- `0x140021360`
- `0x1400213e4`
- `0x140021538`
- `0x140021fdc`
- `0x140022168`
- `0x14002227c`
- `0x1400223d8`
- `0x140022930`
- `0x1400229ec`
- `0x140022b10`
- `0x1400237c4`
- `0x1400238dc`
- `0x1400239f4`
- `0x140023b0c`
- `0x140023c24`
- `0x140023d44`
- `0x140024118`
- `0x140024284`
- `0x14002471c`
- `0x1400247dc`
- `0x140024aa8`
- `0x140024c70`
- `0x140024de4`
- `0x140024f10`
- `0x14002556c`
- `0x140025604`
- `0x1400257e8`
- `0x14002712c`
- `0x1400271fe`
- `0x1400276b2`
- `0x1400276fe`
- `0x140027784`
- `0x140027980`

## callees

- `0x140009ee0`
- `0x14000ccdc`

## pseudocode

```c
__int64 __fastcall winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(
        _QWORD *a1)
{
  __int64 result; // rax

  if ( *a1 )
    return winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1);
  return result;
}

```

## disassembly

```asm
0x14000ccdc  sub     rsp, 28h
0x14000cce0  cmp     qword ptr [rcx], 0
0x14000cce4  jz      short loc_14000CCEB
0x14000cce6  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x14000cceb  add     rsp, 28h
0x14000ccef  retn
```
