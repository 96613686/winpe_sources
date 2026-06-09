# wvr::read_property<std::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>>>::get_value(void)

- ea: `0x180014724`
- end: `0x180014783`
- name: `?get_value@?$read_property@V?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@@wvr@@QEBA?BV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@XZ`
- size: `95`
- prototype: ``
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x180013b60`
- `0x180019904`
- `0x180021f64`
- `0x180022490`

## callees

- `0x180005930`
- `0x1800066d0`
- `0x180013108`
- `0x180013730`
- `0x180013760`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall wvr::read_property<std::vector<std::wstring>>::get_value(__int64 a1, __int64 a2)
{
  _QWORD *v3; // r9
  __int64 v4; // rax
  __int64 v5; // rdx
  _BYTE v7[24]; // [rsp+28h] [rbp-40h] BYREF
  _BYTE v8[40]; // [rsp+40h] [rbp-28h] BYREF

  std::vector<srstor::MSFT_StorageNode>::vector<srstor::MSFT_StorageNode>(v7);
  mi::MiInstance::GetElement<std::vector<std::wstring>>(*v3, v3 + 1, v7);
  v4 = std::vector<std::wstring>::vector<std::wstring>(v8, v7);
  std::vector<std::wstring>::vector<std::wstring>(a2, v4);
  std::vector<std::wstring>::_Tidy(v5);
  std::vector<std::wstring>::_Tidy(v7);
  return a2;
}

```

## disassembly

```asm
0x180014724  push    rbx
0x180014726  sub     rsp, 60h
0x18001472a  mov     rbx, rdx
0x18001472d  mov     r9, rcx
0x180014730  lea     rcx, [rsp+68h+var_40]
0x180014735  call    ??0?$vector@VMSFT_StorageNode@srstor@@V?$allocator@VMSFT_StorageNode@srstor@@@std@@@std@@QEAA@XZ; std::vector<srstor::MSFT_StorageNode>::vector<srstor::MSFT_StorageNode>(void)
0x18001473a  nop
0x18001473b  lea     rdx, [r9+8]
0x18001473f  lea     r8, [rsp+68h+var_40]
0x180014744  mov     rcx, [r9]
0x180014747  call    ??$GetElement@V?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@@MiInstance@mi@@QEBAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@3@@Z; mi::MiInstance::GetElement<std::vector<std::wstring>>(std::wstring const &,std::vector<std::wstring> &)
0x18001474c  lea     rdx, [rsp+68h+var_40]
0x180014751  lea     rcx, [rsp+68h+var_28]
0x180014756  call    ??0?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAA@AEBV01@@Z; std::vector<std::wstring>::vector<std::wstring>(std::vector<std::wstring> const &)
0x18001475b  mov     rdx, rax
0x18001475e  mov     rcx, rbx
0x180014761  call    ??0?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAA@$$QEAV01@@Z; std::vector<std::wstring>::vector<std::wstring>(std::vector<std::wstring> &&)
0x180014766  mov     rcx, rdx
0x180014769  call    ?_Tidy@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18001476e  nop
0x18001476f  lea     rcx, [rsp+68h+var_40]
0x180014774  call    ?_Tidy@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180014779  mov     rax, rbx
0x18001477c  add     rsp, 60h
0x180014780  pop     rbx
0x180014781  retn
```
