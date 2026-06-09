# RtlMicrodomUpdateInsertChild

- ea: `0x180048f9c`
- end: `0x1800490c0`
- name: `RtlMicrodomUpdateInsertChild`
- size: `292`
- prototype: `__int64 __fastcall(int, int, int, int, struct CChildNode *)`
- caller_count: `4`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180043764`
- `0x180043854`
- `0x180043a80`
- `0x180043efc`

## callees

- `0x1800370f4`
- `0x1800478e8`
- `0x1800479b8`
- `0x180048f9c`

## string_xrefs

- `0x180048fb9`: `onecore\base\xml\udom_modify.cpp`
- `0x180048fff`: `onecore\base\xml\udom_modify.cpp`
- `0x18004902a`: `onecore\base\xml\udom_modify.cpp`
- `0x180049059`: `onecore\base\xml\udom_modify.cpp`
- `0x180048fd6`: `RtlIsMicrodomUpdateContextValid(HostUpdate)`
- `0x180048fcb`: `Windows::uDom::Rtl::RtlMicrodomUpdateInsertChild`
- `0x180049011`: `Windows::uDom::Rtl::RtlMicrodomUpdateInsertChild`
- `0x18004903c`: `Windows::uDom::Rtl::RtlMicrodomUpdateInsertChild`
- `0x18004906b`: `Windows::uDom::Rtl::RtlMicrodomUpdateInsertChild`

## pseudocode

```c
__int64 __fastcall RtlMicrodomUpdateInsertChild(__int64 a1, __int64 a2, __int64 a3, __int64 a4, struct CChildNode *a5)
{
  unsigned int v5; // esi
  const char *v7; // rax
  __int64 result; // rax
  CElementModification *v9; // rcx
  __int64 v10; // rax
  int inserted; // eax
  const char *v12; // [rsp+20h] [rbp-20h] BYREF
  const char *v13; // [rsp+28h] [rbp-18h]
  int v14; // [rsp+30h] [rbp-10h]
  const char *v15; // [rsp+38h] [rbp-8h]

  v5 = 0;
  if ( !a1 )
  {
    v14 = 1772;
    v12 = "onecore\\base\\xml\\udom_modify.cpp";
    v13 = "Windows::uDom::Rtl::RtlMicrodomUpdateInsertChild";
    v7 = "RtlIsMicrodomUpdateContextValid(HostUpdate)";
LABEL_3:
    v15 = v7;
    RtlReportErrorOrigination(&v12, a2, 3221225485LL);
    return 3221225485LL;
  }
  if ( !a4 )
  {
    v14 = 1773;
    v12 = "onecore\\base\\xml\\udom_modify.cpp";
    v13 = "Windows::uDom::Rtl::RtlMicrodomUpdateInsertChild";
    v7 = "pToInsertInto != 0";
    goto LABEL_3;
  }
  if ( !a5 )
  {
    v14 = 1774;
    v12 = "onecore\\base\\xml\\udom_modify.cpp";
    v13 = "Windows::uDom::Rtl::RtlMicrodomUpdateInsertChild";
    v7 = "pToInsert != 0";
    goto LABEL_3;
  }
  v9 = *(CElementModification **)(a4 + 40);
  if ( !v9 )
  {
    v14 = 1776;
    v12 = "onecore\\base\\xml\\udom_modify.cpp";
    v13 = "Windows::uDom::Rtl::RtlMicrodomUpdateInsertChild";
    v7 = "pToInsertInto->Element != 0";
    goto LABEL_3;
  }
  v10 = *((_QWORD *)a5 + 7);
  if ( *(_QWORD *)(v10 + 112) )
  {
    result = CElementModification::RemoveChild(*(CElementModification **)(v10 + 112), a5);
    if ( (int)result < 0 )
      return result;
    v9 = *(CElementModification **)(a4 + 40);
  }
  inserted = CElementModification::InsertChild(v9, a5, 0xFFFFFFFF);
  if ( inserted < 0 )
    return (unsigned int)inserted;
  return v5;
}

```

## disassembly

```asm
0x180048f9c  mov     [rsp-18h+arg_8], rbx
0x180048fa1  push    rbp
0x180048fa2  push    rsi
0x180048fa3  push    rdi
0x180048fa4  mov     rbp, rsp
0x180048fa7  sub     rsp, 40h
0x180048fab  mov     rdi, [rbp+arg_20]
0x180048faf  xor     esi, esi
0x180048fb1  mov     rbx, r9
0x180048fb4  test    rcx, rcx
0x180048fb7  jnz     short loc_180048FFA
0x180048fb9  lea     rax, aOnecoreBaseXml; "onecore\\base\\xml\\udom_modify.cpp"
0x180048fc0  mov     [rbp+var_10], 6ECh
0x180048fc7  mov     [rbp+var_20], rax
0x180048fcb  lea     rax, aWindowsUdomRtl_2; "Windows::uDom::Rtl::RtlMicrodomUpdateIn"...
0x180048fd2  mov     [rbp+var_18], rax
0x180048fd6  lea     rax, aRtlismicrodomu_0; "RtlIsMicrodomUpdateContextValid(HostUpd"...
0x180048fdd  mov     r8d, 0C000000Dh
0x180048fe3  mov     [rbp+var_8], rax
0x180048fe7  lea     rcx, [rbp+var_20]
0x180048feb  call    RtlReportErrorOrigination
0x180048ff0  mov     eax, 0C000000Dh
0x180048ff5  jmp     loc_1800490B3
0x180048ffa  test    rbx, rbx
0x180048ffd  jnz     short loc_180049025
0x180048fff  lea     rax, aOnecoreBaseXml; "onecore\\base\\xml\\udom_modify.cpp"
0x180049006  mov     [rbp+var_10], 6EDh
0x18004900d  mov     [rbp+var_20], rax
0x180049011  lea     rax, aWindowsUdomRtl_2; "Windows::uDom::Rtl::RtlMicrodomUpdateIn"...
0x180049018  mov     [rbp+var_18], rax
0x18004901c  lea     rax, aPtoinsertinto0; "pToInsertInto != 0"
0x180049023  jmp     short loc_180048FDD
0x180049025  test    rdi, rdi
0x180049028  jnz     short loc_180049050
0x18004902a  lea     rax, aOnecoreBaseXml; "onecore\\base\\xml\\udom_modify.cpp"
0x180049031  mov     [rbp+var_10], 6EEh
0x180049038  mov     [rbp+var_20], rax
0x18004903c  lea     rax, aWindowsUdomRtl_2; "Windows::uDom::Rtl::RtlMicrodomUpdateIn"...
0x180049043  mov     [rbp+var_18], rax
0x180049047  lea     rax, aPtoinsert0; "pToInsert != 0"
0x18004904e  jmp     short loc_180048FDD
0x180049050  mov     rcx, [r9+28h]
0x180049054  test    rcx, rcx
0x180049057  jnz     short loc_180049082
0x180049059  lea     rax, aOnecoreBaseXml; "onecore\\base\\xml\\udom_modify.cpp"
0x180049060  mov     [rbp+var_10], 6F0h
0x180049067  mov     [rbp+var_20], rax
0x18004906b  lea     rax, aWindowsUdomRtl_2; "Windows::uDom::Rtl::RtlMicrodomUpdateIn"...
0x180049072  mov     [rbp+var_18], rax
0x180049076  lea     rax, aPtoinsertintoE; "pToInsertInto->Element != 0"
0x18004907d  jmp     loc_180048FDD
0x180049082  mov     rax, [rdi+38h]
0x180049086  cmp     [rax+70h], rsi
0x18004908a  jz      short loc_1800490A0
0x18004908c  mov     rcx, [rax+70h]; this
0x180049090  mov     rdx, rdi; struct CChildNode *
0x180049093  call    ?RemoveChild@CElementModification@@QEAAJPEAVCChildNode@@@Z; CElementModification::RemoveChild(CChildNode *)
0x180049098  test    eax, eax
0x18004909a  js      short loc_1800490B3
0x18004909c  mov     rcx, [rbx+28h]; this
0x1800490a0  or      r8d, 0FFFFFFFFh; unsigned int
0x1800490a4  mov     rdx, rdi; struct CChildNode *
0x1800490a7  call    ?InsertChild@CElementModification@@QEAAJPEAVCChildNode@@K@Z; CElementModification::InsertChild(CChildNode *,ulong)
0x1800490ac  test    eax, eax
0x1800490ae  cmovs   esi, eax
0x1800490b1  mov     eax, esi
0x1800490b3  mov     rbx, [rsp+40h+arg_8]
0x1800490b8  add     rsp, 40h
0x1800490bc  pop     rdi
0x1800490bd  pop     rsi
0x1800490be  pop     rbp
0x1800490bf  retn
```
