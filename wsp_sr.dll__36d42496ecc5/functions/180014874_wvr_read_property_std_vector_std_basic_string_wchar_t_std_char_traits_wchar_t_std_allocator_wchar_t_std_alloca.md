# wvr::read_property<std::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>>>::get_value(void)

- ea: `0x180014874`
- end: `0x1800148d2`
- name: `?get_value@?$read_property@V?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@@wvr@@QEBA?BV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@XZ`
- size: `94`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x180013c50`
- `0x1800198cc`
- `0x180021dbc`
- `0x1800222d8`

## callees

- `0x1800058f8`
- `0x180006688`
- `0x180013238`
- `0x18001382c`
- `0x18001385c`

## pseudocode

```c
__int64 __fastcall wvr::read_property<std::vector<std::wstring>>::get_value(__int64 a1, __int64 a2)
{
  _QWORD *v3; // r9
  __int64 v4; // rax
  __int64 v5; // rdx
  _QWORD v7[3]; // [rsp+28h] [rbp-40h] BYREF
  _BYTE v8[40]; // [rsp+40h] [rbp-28h] BYREF

  std::vector<srstor::MSFT_StorageNode>::vector<srstor::MSFT_StorageNode>(v7);
  mi::MiInstance::GetElement<std::vector<std::wstring>>(*v3, v3 + 1, v7);
  v4 = std::vector<std::wstring>::vector<std::wstring>(v8, v7);
  std::vector<std::wstring>::vector<std::wstring>(a2, v4);
  std::vector<std::wstring>::_Tidy(v5);
  std::vector<std::wstring>::_Tidy((__int64)v7);
  return a2;
}

```

## disassembly

```asm
0x180014874  push    rbx
0x180014876  sub     rsp, 60h
0x18001487a  mov     rbx, rdx
0x18001487d  mov     r9, rcx
0x180014880  lea     rcx, [rsp+68h+var_40]
0x180014885  call    ??0?$vector@VMSFT_StorageNode@srstor@@V?$allocator@VMSFT_StorageNode@srstor@@@std@@@std@@QEAA@XZ; std::vector<srstor::MSFT_StorageNode>::vector<srstor::MSFT_StorageNode>(void)
0x18001488a  nop
0x18001488b  lea     rdx, [r9+8]
0x18001488f  lea     r8, [rsp+68h+var_40]
0x180014894  mov     rcx, [r9]
0x180014897  call    ??$GetElement@V?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@@MiInstance@mi@@QEBAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@3@@Z; mi::MiInstance::GetElement<std::vector<std::wstring>>(std::wstring const &,std::vector<std::wstring> &)
0x18001489c  lea     rdx, [rsp+68h+var_40]
0x1800148a1  lea     rcx, [rsp+68h+var_28]
0x1800148a6  call    ??0?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAA@AEBV01@@Z; std::vector<std::wstring>::vector<std::wstring>(std::vector<std::wstring> const &)
0x1800148ab  mov     rdx, rax
0x1800148ae  mov     rcx, rbx
0x1800148b1  call    ??0?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAA@$$QEAV01@@Z; std::vector<std::wstring>::vector<std::wstring>(std::vector<std::wstring> &&)
0x1800148b6  mov     rcx, rdx
0x1800148b9  call    ?_Tidy@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x1800148be  nop
0x1800148bf  lea     rcx, [rsp+68h+var_40]
0x1800148c4  call    ?_Tidy@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x1800148c9  mov     rax, rbx
0x1800148cc  add     rsp, 60h
0x1800148d0  pop     rbx
0x1800148d1  retn
```
