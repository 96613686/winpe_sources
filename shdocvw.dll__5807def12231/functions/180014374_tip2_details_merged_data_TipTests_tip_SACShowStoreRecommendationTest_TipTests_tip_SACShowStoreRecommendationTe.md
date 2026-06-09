# tip2::details::merged_data<TipTests::_tip_SACShowStoreRecommendationTest,TipTests::_tip_SACShowStoreRecommendationTest>::merged_data<TipTests::_tip_SACShowStoreRecommendationTest,TipTests::_tip_SACShowStoreRecommendationTest>(void)

- ea: `0x180014374`
- end: `0x180014403`
- name: `??0?$merged_data@U_tip_SACShowStoreRecommendationTest@TipTests@@U12@@details@tip2@@QEAA@XZ`
- size: `143`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001b048`

## callees

- `0x18001440c`

## string_xrefs

- `0x18001439f`: `SACShowStoreRecommendationTest`

## pseudocode

```c
__int64 __fastcall tip2::details::merged_data<TipTests::_tip_SACShowStoreRecommendationTest,TipTests::_tip_SACShowStoreRecommendationTest>::merged_data<TipTests::_tip_SACShowStoreRecommendationTest,TipTests::_tip_SACShowStoreRecommendationTest>(
        __int64 a1)
{
  __int64 result; // rax
  _DWORD v3[2]; // [rsp+20h] [rbp-38h] BYREF
  const char *v4; // [rsp+28h] [rbp-30h]
  __int16 v5; // [rsp+30h] [rbp-28h]
  int v6; // [rsp+32h] [rbp-26h]
  __int16 v7; // [rsp+36h] [rbp-22h]
  __int128 v8; // [rsp+38h] [rbp-20h]
  __int64 v9; // [rsp+48h] [rbp-10h]

  v3[0] = 57850325;
  v6 = 0;
  v7 = 0;
  *(_QWORD *)a1 = &tip2::details::test_data_interface::`vftable';
  v9 = 0;
  v4 = "SACShowStoreRecommendationTest";
  v3[1] = 16640;
  v5 = 1;
  v8 = 0;
  tip2::details::shared_data<1,0,0>::shared_data<1,0,0>(a1 + 8, a1, v3);
  *(_BYTE *)(a1 + 272) = 0;
  *(_QWORD *)a1 = &tip2::details::merged_data<TipTests::_tip_SACShowStoreRecommendationTest,TipTests::_tip_SACShowStoreRecommendationTest>::`vftable';
  *(_QWORD *)(a1 + 264) = a1 + 16;
  result = a1;
  *(_DWORD *)(a1 + 280) = 1;
  return result;
}

```

## disassembly

```asm
0x180014374  push    rbx
0x180014376  sub     rsp, 50h
0x18001437a  xor     edx, edx
0x18001437c  mov     [rsp+58h+var_38], 372B9D5h
0x180014384  mov     rbx, rcx
0x180014387  mov     [rsp+58h+var_26], edx
0x18001438b  lea     rax, ??_7test_data_interface@details@tip2@@6B@; const tip2::details::test_data_interface::`vftable'
0x180014392  mov     [rsp+58h+var_22], dx
0x180014397  mov     [rcx], rax
0x18001439a  lea     r8, [rsp+58h+var_38]
0x18001439f  lea     rcx, aSacshowstorere; "SACShowStoreRecommendationTest"
0x1800143a6  mov     [rsp+58h+var_10], rdx
0x1800143ab  mov     [rsp+58h+var_30], rcx
0x1800143b0  xorps   xmm0, xmm0
0x1800143b3  lea     rcx, [rbx+8]
0x1800143b7  mov     [rsp+58h+var_34], 4100h
0x1800143bf  mov     rdx, rbx
0x1800143c2  mov     [rsp+58h+var_28], 1
0x1800143c9  movdqu  [rsp+58h+var_20], xmm0
0x1800143cf  call    ??0?$shared_data@$00$0A@$0A@@details@tip2@@QEAA@AEAUtest_data_interface@12@AEBUtest_info@2@@Z; tip2::details::shared_data<1,0,0>::shared_data<1,0,0>(tip2::details::test_data_interface &,tip2::test_info const &)
0x1800143d4  mov     byte ptr [rbx+110h], 0
0x1800143db  lea     rax, ??_7?$merged_data@U_tip_SACShowStoreRecommendationTest@TipTests@@U12@@details@tip2@@6B@; const tip2::details::merged_data<TipTests::_tip_SACShowStoreRecommendationTest,TipTests::_tip_SACShowStoreRecommendationTest>::`vftable'
0x1800143e2  mov     [rbx], rax
0x1800143e5  lea     rax, [rbx+10h]
0x1800143e9  mov     [rbx+108h], rax
0x1800143f0  mov     rax, rbx
0x1800143f3  mov     dword ptr [rbx+118h], 1
0x1800143fd  add     rsp, 50h
0x180014401  pop     rbx
0x180014402  retn
```
