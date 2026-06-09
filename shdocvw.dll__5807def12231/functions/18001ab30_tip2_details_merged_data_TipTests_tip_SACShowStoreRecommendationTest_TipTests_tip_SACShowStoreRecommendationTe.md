# tip2::details::merged_data<TipTests::_tip_SACShowStoreRecommendationTest,TipTests::_tip_SACShowStoreRecommendationTest>::deserialize(tson::input_archive &)

- ea: `0x18001ab30`
- end: `0x18001ab9f`
- name: `?deserialize@?$merged_data@U_tip_SACShowStoreRecommendationTest@TipTests@@U12@@details@tip2@@EEAAXAEAVinput_archive@tson@@@Z`
- size: `111`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180012acc`
- `0x18001b60c`
- `0x18001cd98`

## string_xrefs

- `0x18001ab57`: `displayRecommendationDialog`

## pseudocode

```c
void __fastcall tip2::details::merged_data<TipTests::_tip_SACShowStoreRecommendationTest,TipTests::_tip_SACShowStoreRecommendationTest>::deserialize(
        __int64 a1,
        __int64 a2)
{
  __int64 v4; // rax
  const char *v5; // [rsp+20h] [rbp-28h] BYREF
  char v6; // [rsp+28h] [rbp-20h]
  __int64 v7; // [rsp+30h] [rbp-18h]

  *(_BYTE *)(a2 + 24) = 4;
  *(_QWORD *)(a2 + 16) = "test";
  tson::input_archive::startNode((tson::input_archive *)a2);
  v6 = 27;
  v5 = "displayRecommendationDialog";
  v4 = a1 + 272;
  if ( !a1 )
    v4 = 16;
  v7 = v4;
  tson::input_archive::operator()<tson::nvp<bool &>>(a2, &v5);
  tson::input_archive::finishNode((tson::input_archive *)a2);
}

```

## disassembly

```asm
0x18001ab30  mov     [rsp+arg_0], rbx
0x18001ab35  push    rdi
0x18001ab36  sub     rsp, 40h
0x18001ab3a  mov     rbx, rcx
0x18001ab3d  mov     byte ptr [rdx+18h], 4
0x18001ab41  lea     rax, aTest; "test"
0x18001ab48  mov     rcx, rdx; this
0x18001ab4b  mov     [rdx+10h], rax
0x18001ab4f  mov     rdi, rdx
0x18001ab52  call    ?startNode@input_archive@tson@@QEAAXXZ; tson::input_archive::startNode(void)
0x18001ab57  lea     rax, aDisplayrecomme; "displayRecommendationDialog"
0x18001ab5e  mov     [rsp+48h+var_20], 1Bh
0x18001ab63  mov     [rsp+48h+var_28], rax
0x18001ab68  lea     rdx, [rsp+48h+var_28]
0x18001ab6d  mov     ecx, 10h
0x18001ab72  lea     rax, [rbx+110h]
0x18001ab79  test    rbx, rbx
0x18001ab7c  cmovz   rax, rcx
0x18001ab80  mov     rcx, rdi
0x18001ab83  mov     [rsp+48h+var_18], rax
0x18001ab88  call    ??$?RV?$nvp@AEA_N@tson@@@input_archive@tson@@QEAAAEAV01@$$QEAV?$nvp@AEA_N@1@@Z; tson::input_archive::operator()<tson::nvp<bool &>>(tson::nvp<bool &> &&)
0x18001ab8d  mov     rcx, rdi; this
0x18001ab90  mov     rbx, [rsp+48h+arg_0]
0x18001ab95  add     rsp, 40h
0x18001ab99  pop     rdi
0x18001ab9a  jmp     ?finishNode@input_archive@tson@@QEAAXXZ; tson::input_archive::finishNode(void)
```
