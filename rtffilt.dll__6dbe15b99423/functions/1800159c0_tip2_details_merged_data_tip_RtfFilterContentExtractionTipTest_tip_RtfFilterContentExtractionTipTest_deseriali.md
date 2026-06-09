# tip2::details::merged_data<_tip_RtfFilterContentExtractionTipTest,_tip_RtfFilterContentExtractionTipTest>::deserialize(tson::input_archive &)

- ea: `0x1800159c0`
- end: `0x180015a62`
- name: `?deserialize@?$merged_data@U_tip_RtfFilterContentExtractionTipTest@@U1@@details@tip2@@EEAAXAEAVinput_archive@tson@@@Z`
- size: `162`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x18000f4e0`
- `0x1800166dc`
- `0x180018eac`

## pseudocode

```c
void __fastcall tip2::details::merged_data<_tip_RtfFilterContentExtractionTipTest,_tip_RtfFilterContentExtractionTipTest>::deserialize(
        __int64 a1,
        __int64 a2)
{
  __int64 v4; // rax
  __int64 v5; // rax
  const char *v6; // [rsp+20h] [rbp-38h] BYREF
  char v7; // [rsp+28h] [rbp-30h]
  __int64 v8; // [rsp+30h] [rbp-28h]
  const char *v9; // [rsp+38h] [rbp-20h] BYREF
  char v10; // [rsp+40h] [rbp-18h]
  __int64 v11; // [rsp+48h] [rbp-10h]

  *(_BYTE *)(a2 + 24) = 4;
  *(_QWORD *)(a2 + 16) = "test";
  tson::input_archive::startNode((tson::input_archive *)a2);
  v10 = 34;
  v9 = "failedToExtractImagesFromTextRange";
  v7 = 20;
  v4 = a1 + 273;
  if ( !a1 )
    v4 = 17;
  v11 = v4;
  v6 = "fileContentExtracted";
  v5 = a1 + 272;
  if ( !a1 )
    v5 = 16;
  v8 = v5;
  tson::input_archive::process<tson::nvp<bool &>>(a2, &v6);
  tson::input_archive::process<tson::nvp<bool &>>(a2, &v9);
  tson::input_archive::finishNode((tson::input_archive *)a2);
}

```

## disassembly

```asm
0x1800159c0  mov     [rsp+arg_0], rbx
0x1800159c5  push    rdi
0x1800159c6  sub     rsp, 50h
0x1800159ca  mov     rbx, rcx
0x1800159cd  mov     byte ptr [rdx+18h], 4
0x1800159d1  lea     rax, aTest; "test"
0x1800159d8  mov     rcx, rdx; this
0x1800159db  mov     [rdx+10h], rax
0x1800159df  mov     rdi, rdx
0x1800159e2  call    ?startNode@input_archive@tson@@QEAAXXZ; tson::input_archive::startNode(void)
0x1800159e7  lea     rax, aFailedtoextrac; "failedToExtractImagesFromTextRange"
0x1800159ee  mov     [rsp+58h+var_18], 22h ; '"'
0x1800159f3  mov     [rsp+58h+var_20], rax
0x1800159f8  lea     rdx, [rsp+58h+var_38]
0x1800159fd  test    rbx, rbx
0x180015a00  mov     [rsp+58h+var_30], 14h
0x180015a05  mov     ecx, 11h
0x180015a0a  lea     rax, [rbx+111h]
0x180015a11  cmovz   rax, rcx
0x180015a15  mov     ecx, 10h
0x180015a1a  mov     [rsp+58h+var_10], rax
0x180015a1f  lea     rax, aFilecontentext; "fileContentExtracted"
0x180015a26  mov     [rsp+58h+var_38], rax
0x180015a2b  lea     rax, [rbx+110h]
0x180015a32  cmovz   rax, rcx
0x180015a36  mov     rcx, rdi
0x180015a39  mov     [rsp+58h+var_28], rax
0x180015a3e  call    ??$process@V?$nvp@AEA_N@tson@@@input_archive@tson@@AEAAX$$QEAV?$nvp@AEA_N@1@@Z; tson::input_archive::process<tson::nvp<bool &>>(tson::nvp<bool &> &&)
0x180015a43  lea     rdx, [rsp+58h+var_20]
0x180015a48  mov     rcx, rdi
0x180015a4b  call    ??$process@V?$nvp@AEA_N@tson@@@input_archive@tson@@AEAAX$$QEAV?$nvp@AEA_N@1@@Z; tson::input_archive::process<tson::nvp<bool &>>(tson::nvp<bool &> &&)
0x180015a50  mov     rcx, rdi; this
0x180015a53  mov     rbx, [rsp+58h+arg_0]
0x180015a58  add     rsp, 50h
0x180015a5c  pop     rdi
0x180015a5d  jmp     ?finishNode@input_archive@tson@@QEAAXXZ; tson::input_archive::finishNode(void)
```
