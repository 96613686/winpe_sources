# RtlMicrodomUpdateRemoveChild

- ea: `0x1800490c8`
- end: `0x1800491bf`
- name: `RtlMicrodomUpdateRemoveChild`
- size: `247`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180043910`
- `0x180044684`

## callees

- `0x1800370f4`
- `0x1800478e8`
- `0x1800490c8`

## string_xrefs

- `0x1800490dc`: `onecore\base\xml\udom_modify.cpp`
- `0x180049122`: `onecore\base\xml\udom_modify.cpp`
- `0x18004914d`: `onecore\base\xml\udom_modify.cpp`
- `0x18004917c`: `onecore\base\xml\udom_modify.cpp`
- `0x1800490f9`: `RtlIsMicrodomUpdateContextValid(HostUpdate)`
- `0x1800490ee`: `Windows::uDom::Rtl::RtlMicrodomUpdateRemoveChild`
- `0x180049134`: `Windows::uDom::Rtl::RtlMicrodomUpdateRemoveChild`
- `0x18004915f`: `Windows::uDom::Rtl::RtlMicrodomUpdateRemoveChild`
- `0x18004918e`: `Windows::uDom::Rtl::RtlMicrodomUpdateRemoveChild`
- `0x18004913f`: `pToRemoveFrom != 0`
- `0x18004916a`: `pToRemove != 0`
- `0x180049199`: `pToRemoveFrom->Element != 0`

## pseudocode

```c
__int64 __fastcall RtlMicrodomUpdateRemoveChild(__int64 a1, __int64 a2, struct CChildNode *a3)
{
  unsigned int v3; // ebx
  const char *v4; // rax
  CElementModification *v6; // rcx
  int v7; // eax
  const char *v8; // [rsp+20h] [rbp-20h] BYREF
  const char *v9; // [rsp+28h] [rbp-18h]
  int v10; // [rsp+30h] [rbp-10h]
  const char *v11; // [rsp+38h] [rbp-8h]

  v3 = 0;
  if ( !a1 )
  {
    v10 = 1816;
    v8 = "onecore\\base\\xml\\udom_modify.cpp";
    v9 = "Windows::uDom::Rtl::RtlMicrodomUpdateRemoveChild";
    v4 = "RtlIsMicrodomUpdateContextValid(HostUpdate)";
LABEL_3:
    v11 = v4;
    RtlReportErrorOrigination(&v8, a2, 3221225485LL);
    return 3221225485LL;
  }
  if ( !a2 )
  {
    v10 = 1817;
    v8 = "onecore\\base\\xml\\udom_modify.cpp";
    v9 = "Windows::uDom::Rtl::RtlMicrodomUpdateRemoveChild";
    v4 = "pToRemoveFrom != 0";
    goto LABEL_3;
  }
  if ( !a3 )
  {
    v10 = 1818;
    v8 = "onecore\\base\\xml\\udom_modify.cpp";
    v9 = "Windows::uDom::Rtl::RtlMicrodomUpdateRemoveChild";
    v4 = "pToRemove != 0";
    goto LABEL_3;
  }
  v6 = *(CElementModification **)(a2 + 40);
  if ( !v6 )
  {
    v10 = 1819;
    v8 = "onecore\\base\\xml\\udom_modify.cpp";
    v9 = "Windows::uDom::Rtl::RtlMicrodomUpdateRemoveChild";
    v4 = "pToRemoveFrom->Element != 0";
    goto LABEL_3;
  }
  v7 = CElementModification::RemoveChild(v6, a3);
  if ( v7 < 0 )
    return (unsigned int)v7;
  return v3;
}

```

## disassembly

```asm
0x1800490c8  mov     [rsp-8+arg_18], rbx
0x1800490cd  push    rbp
0x1800490ce  mov     rbp, rsp
0x1800490d1  sub     rsp, 40h
0x1800490d5  xor     ebx, ebx
0x1800490d7  test    rcx, rcx
0x1800490da  jnz     short loc_18004911D
0x1800490dc  lea     rax, aOnecoreBaseXml; "onecore\\base\\xml\\udom_modify.cpp"
0x1800490e3  mov     [rbp+var_10], 718h
0x1800490ea  mov     [rbp+var_20], rax
0x1800490ee  lea     rax, aWindowsUdomRtl_9; "Windows::uDom::Rtl::RtlMicrodomUpdateRe"...
0x1800490f5  mov     [rbp+var_18], rax
0x1800490f9  lea     rax, aRtlismicrodomu_0; "RtlIsMicrodomUpdateContextValid(HostUpd"...
0x180049100  mov     r8d, 0C000000Dh
0x180049106  mov     [rbp+var_8], rax
0x18004910a  lea     rcx, [rbp+var_20]
0x18004910e  call    RtlReportErrorOrigination
0x180049113  mov     eax, 0C000000Dh
0x180049118  jmp     loc_1800491B4
0x18004911d  test    rdx, rdx
0x180049120  jnz     short loc_180049148
0x180049122  lea     rax, aOnecoreBaseXml; "onecore\\base\\xml\\udom_modify.cpp"
0x180049129  mov     [rbp+var_10], 719h
0x180049130  mov     [rbp+var_20], rax
0x180049134  lea     rax, aWindowsUdomRtl_9; "Windows::uDom::Rtl::RtlMicrodomUpdateRe"...
0x18004913b  mov     [rbp+var_18], rax
0x18004913f  lea     rax, aPtoremovefrom0; "pToRemoveFrom != 0"
0x180049146  jmp     short loc_180049100
0x180049148  test    r8, r8
0x18004914b  jnz     short loc_180049173
0x18004914d  lea     rax, aOnecoreBaseXml; "onecore\\base\\xml\\udom_modify.cpp"
0x180049154  mov     [rbp+var_10], 71Ah
0x18004915b  mov     [rbp+var_20], rax
0x18004915f  lea     rax, aWindowsUdomRtl_9; "Windows::uDom::Rtl::RtlMicrodomUpdateRe"...
0x180049166  mov     [rbp+var_18], rax
0x18004916a  lea     rax, aPtoremove0; "pToRemove != 0"
0x180049171  jmp     short loc_180049100
0x180049173  mov     rcx, [rdx+28h]; this
0x180049177  test    rcx, rcx
0x18004917a  jnz     short loc_1800491A5
0x18004917c  lea     rax, aOnecoreBaseXml; "onecore\\base\\xml\\udom_modify.cpp"
0x180049183  mov     [rbp+var_10], 71Bh
0x18004918a  mov     [rbp+var_20], rax
0x18004918e  lea     rax, aWindowsUdomRtl_9; "Windows::uDom::Rtl::RtlMicrodomUpdateRe"...
0x180049195  mov     [rbp+var_18], rax
0x180049199  lea     rax, aPtoremovefromE; "pToRemoveFrom->Element != 0"
0x1800491a0  jmp     loc_180049100
0x1800491a5  mov     rdx, r8; struct CChildNode *
0x1800491a8  call    ?RemoveChild@CElementModification@@QEAAJPEAVCChildNode@@@Z; CElementModification::RemoveChild(CChildNode *)
0x1800491ad  test    eax, eax
0x1800491af  cmovs   ebx, eax
0x1800491b2  mov     eax, ebx
0x1800491b4  mov     rbx, [rsp+40h+arg_18]
0x1800491b9  add     rsp, 40h
0x1800491bd  pop     rbp
0x1800491be  retn
```
