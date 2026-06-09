# tip2::details::merged_data<_tip_ImagingHandlerInitTipTest,_tip_ImagingHandlerInitTipTest>::deserialize(tson::input_archive &)

- ea: `0x180015950`
- end: `0x1800159b3`
- name: `?deserialize@?$merged_data@U_tip_ImagingHandlerInitTipTest@@U1@@details@tip2@@EEAAXAEAVinput_archive@tson@@@Z`
- size: `99`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callees

- `0x1800166dc`
- `0x180017410`
- `0x180018eac`

## pseudocode

```c
void __fastcall tip2::details::merged_data<_tip_ImagingHandlerInitTipTest,_tip_ImagingHandlerInitTipTest>::deserialize(
        __int64 a1,
        __int64 a2)
{
  __int64 v4; // rdx

  *(_BYTE *)(a2 + 24) = 4;
  *(_QWORD *)(a2 + 16) = "test";
  tson::input_archive::startNode((tson::input_archive *)a2);
  *(_BYTE *)(a2 + 24) = 14;
  *(_QWORD *)(a2 + 16) = "consumerFilter";
  v4 = a1 + 272;
  if ( !a1 )
    v4 = 16;
  tson::load_nothrow((tson::input_archive *)a2, (void *)v4);
  tson::input_archive::finishNode((tson::input_archive *)a2);
}

```

## disassembly

```asm
0x180015950  mov     [rsp+arg_0], rbx
0x180015955  push    rdi
0x180015956  sub     rsp, 20h
0x18001595a  mov     rbx, rcx
0x18001595d  mov     byte ptr [rdx+18h], 4
0x180015961  lea     rax, aTest; "test"
0x180015968  mov     rcx, rdx; this
0x18001596b  mov     [rdx+10h], rax
0x18001596f  mov     rdi, rdx
0x180015972  call    ?startNode@input_archive@tson@@QEAAXXZ; tson::input_archive::startNode(void)
0x180015977  lea     rax, aConsumerfilter; "consumerFilter"
0x18001597e  mov     byte ptr [rdi+18h], 0Eh
0x180015982  mov     [rdi+10h], rax
0x180015986  lea     rdx, [rbx+110h]
0x18001598d  mov     eax, 10h
0x180015992  test    rbx, rbx
0x180015995  mov     rcx, rdi; this
0x180015998  cmovz   rdx, rax; Src
0x18001599c  call    ?load_nothrow@tson@@YAXAEAVinput_archive@1@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; tson::load_nothrow(tson::input_archive &,std::wstring &)
0x1800159a1  mov     rcx, rdi; this
0x1800159a4  mov     rbx, [rsp+28h+arg_0]
0x1800159a9  add     rsp, 20h
0x1800159ad  pop     rdi
0x1800159ae  jmp     ?finishNode@input_archive@tson@@QEAAXXZ; tson::input_archive::finishNode(void)
```
