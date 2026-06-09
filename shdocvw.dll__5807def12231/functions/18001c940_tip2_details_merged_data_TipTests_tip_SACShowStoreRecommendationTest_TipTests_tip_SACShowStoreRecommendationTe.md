# tip2::details::merged_data<TipTests::_tip_SACShowStoreRecommendationTest,TipTests::_tip_SACShowStoreRecommendationTest>::serialize(tson::output_archive &,tip2::details::serialize_options)

- ea: `0x18001c940`
- end: `0x18001c9d7`
- name: `?serialize@?$merged_data@U_tip_SACShowStoreRecommendationTest@TipTests@@U12@@details@tip2@@EEAAXAEAVoutput_archive@tson@@W4serialize_options@23@@Z`
- size: `151`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x1800125ac`
- `0x18001b65c`
- `0x18001c940`
- `0x18001ce20`

## string_xrefs

- `0x18001c99e`: `displayRecommendationDialog`

## pseudocode

```c
void __fastcall tip2::details::merged_data<TipTests::_tip_SACShowStoreRecommendationTest,TipTests::_tip_SACShowStoreRecommendationTest>::serialize(
        __int64 a1,
        tson::output_archive *a2,
        char a3)
{
  _BYTE *v3; // rdi
  __int64 v7; // rdx

  v3 = (char *)a2 + 8;
  if ( (a3 & 2) != 0 )
  {
    *v3 = 7;
    *(_QWORD *)a2 = "metrics";
    tson::output_archive::startNode(a2);
    *(_DWORD *)(a1 + 184) = 0;
    tson::output_archive::finishNode(a2);
  }
  if ( (a3 & 1) != 0 )
  {
    *v3 = 4;
    *(_QWORD *)a2 = "test";
    tson::output_archive::startNode(a2);
    *v3 = 27;
    *(_QWORD *)a2 = "displayRecommendationDialog";
    v7 = a1 + 272;
    if ( !a1 )
      v7 = 16;
    tson::output_archive::operator()<bool &>(a2, v7);
    tson::output_archive::finishNode(a2);
  }
}

```

## disassembly

```asm
0x18001c940  push    rbx
0x18001c942  push    rbp
0x18001c943  push    rsi
0x18001c944  push    rdi
0x18001c945  sub     rsp, 28h
0x18001c949  lea     rdi, [rdx+8]
0x18001c94d  mov     esi, r8d
0x18001c950  mov     rbx, rdx
0x18001c953  mov     rbp, rcx
0x18001c956  test    r8b, 2
0x18001c95a  jz      short loc_18001C983
0x18001c95c  lea     rax, aMetrics; "metrics"
0x18001c963  mov     byte ptr [rdi], 7
0x18001c966  mov     rcx, rdx; this
0x18001c969  mov     [rdx], rax
0x18001c96c  call    ?startNode@output_archive@tson@@QEAAXXZ; tson::output_archive::startNode(void)
0x18001c971  mov     rcx, rbx; this
0x18001c974  mov     dword ptr [rbp+0B8h], 0
0x18001c97e  call    ?finishNode@output_archive@tson@@QEAAXXZ; tson::output_archive::finishNode(void)
0x18001c983  test    sil, 1
0x18001c987  jz      short loc_18001C9CE
0x18001c989  lea     rax, aTest; "test"
0x18001c990  mov     byte ptr [rdi], 4
0x18001c993  mov     rcx, rbx; this
0x18001c996  mov     [rbx], rax
0x18001c999  call    ?startNode@output_archive@tson@@QEAAXXZ; tson::output_archive::startNode(void)
0x18001c99e  lea     rax, aDisplayrecomme; "displayRecommendationDialog"
0x18001c9a5  mov     byte ptr [rdi], 1Bh
0x18001c9a8  mov     [rbx], rax
0x18001c9ab  lea     rdx, [rbp+110h]
0x18001c9b2  mov     eax, 10h
0x18001c9b7  test    rbp, rbp
0x18001c9ba  mov     rcx, rbx
0x18001c9bd  cmovz   rdx, rax
0x18001c9c1  call    ??$?RAEA_N@output_archive@tson@@QEAAAEAV01@AEA_N@Z; tson::output_archive::operator()<bool &>(bool &)
0x18001c9c6  mov     rcx, rbx; this
0x18001c9c9  call    ?finishNode@output_archive@tson@@QEAAXXZ; tson::output_archive::finishNode(void)
0x18001c9ce  add     rsp, 28h
0x18001c9d2  pop     rdi
0x18001c9d3  pop     rsi
0x18001c9d4  pop     rbp
0x18001c9d5  pop     rbx
0x18001c9d6  retn
```
