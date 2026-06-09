# RtlMicrodomUpdateSetNodeTextContent

- ea: `0x180048d60`
- end: `0x180048e79`
- name: `RtlMicrodomUpdateSetNodeTextContent`
- size: `281`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180043764`
- `0x180044540`
- `0x180044684`

## callees

- `0x1800370f4`
- `0x180048d60`
- `0x180060e70`

## string_xrefs

- `0x180048d77`: `onecore\base\xml\udom_modify.cpp`
- `0x180048dbd`: `onecore\base\xml\udom_modify.cpp`
- `0x180048dfc`: `onecore\base\xml\udom_modify.cpp`
- `0x180048e2e`: `onecore\base\xml\udom_modify.cpp`
- `0x180048d94`: `RtlIsMicrodomUpdateContextValid(HostUpdate)`
- `0x180048d89`: `Windows::uDom::Rtl::RtlMicrodomUpdateSetNodeTextContent`
- `0x180048dcf`: `Windows::uDom::Rtl::RtlMicrodomUpdateSetNodeTextContent`
- `0x180048e0e`: `Windows::uDom::Rtl::RtlMicrodomUpdateSetNodeTextContent`
- `0x180048e40`: `Windows::uDom::Rtl::RtlMicrodomUpdateSetNodeTextContent`

## pseudocode

```c
__int64 __fastcall RtlMicrodomUpdateSetNodeTextContent(__int64 a1, __int64 a2, _QWORD *a3)
{
  unsigned int v3; // ebx
  const char *v4; // rax
  __int64 v6; // rcx
  int v7; // eax
  const char *v8; // [rsp+20h] [rbp-20h] BYREF
  const char *v9; // [rsp+28h] [rbp-18h]
  int v10; // [rsp+30h] [rbp-10h]
  const char *v11; // [rsp+38h] [rbp-8h]

  v3 = 0;
  if ( !a1 )
  {
    v10 = 1677;
    v8 = "onecore\\base\\xml\\udom_modify.cpp";
    v9 = "Windows::uDom::Rtl::RtlMicrodomUpdateSetNodeTextContent";
    v4 = "RtlIsMicrodomUpdateContextValid(HostUpdate)";
LABEL_3:
    v11 = v4;
    RtlReportErrorOrigination(&v8, a2, 3221225485LL);
    return 3221225485LL;
  }
  if ( !a2 )
  {
    v10 = 1678;
    v8 = "onecore\\base\\xml\\udom_modify.cpp";
    v9 = "Windows::uDom::Rtl::RtlMicrodomUpdateSetNodeTextContent";
    v4 = "ObjectCookie.Opaque != 0";
    goto LABEL_3;
  }
  if ( a3 && (*a3 > a3[1] || !a3[2] && *a3) )
  {
    v10 = 1679;
    v8 = "onecore\\base\\xml\\udom_modify.cpp";
    v9 = "Windows::uDom::Rtl::RtlMicrodomUpdateSetNodeTextContent";
    v4 = "(Value == 0) || RtlIsLUtf8StringValid(Value)";
    goto LABEL_3;
  }
  v6 = *(_QWORD *)(a2 + 56);
  if ( !v6 )
  {
    v10 = 1681;
    v8 = "onecore\\base\\xml\\udom_modify.cpp";
    v9 = "Windows::uDom::Rtl::RtlMicrodomUpdateSetNodeTextContent";
    v4 = "pChild->pBasicNode != 0";
    goto LABEL_3;
  }
  v7 = (*(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v6 + 72LL))(v6, a3);
  if ( v7 < 0 )
    return (unsigned int)v7;
  return v3;
}

```

## disassembly

```asm
0x180048d60  mov     [rsp-8+arg_18], rbx
0x180048d65  push    rbp
0x180048d66  mov     rbp, rsp
0x180048d69  sub     rsp, 40h
0x180048d6d  xor     ebx, ebx
0x180048d6f  mov     rax, r8
0x180048d72  test    rcx, rcx
0x180048d75  jnz     short loc_180048DB8
0x180048d77  lea     rax, aOnecoreBaseXml; "onecore\\base\\xml\\udom_modify.cpp"
0x180048d7e  mov     [rbp+var_10], 68Dh
0x180048d85  mov     [rbp+var_20], rax
0x180048d89  lea     rax, aWindowsUdomRtl_8; "Windows::uDom::Rtl::RtlMicrodomUpdateSe"...
0x180048d90  mov     [rbp+var_18], rax
0x180048d94  lea     rax, aRtlismicrodomu_0; "RtlIsMicrodomUpdateContextValid(HostUpd"...
0x180048d9b  mov     r8d, 0C000000Dh
0x180048da1  mov     [rbp+var_8], rax
0x180048da5  lea     rcx, [rbp+var_20]
0x180048da9  call    RtlReportErrorOrigination
0x180048dae  mov     eax, 0C000000Dh
0x180048db3  jmp     loc_180048E6E
0x180048db8  test    rdx, rdx
0x180048dbb  jnz     short loc_180048DE3
0x180048dbd  lea     rax, aOnecoreBaseXml; "onecore\\base\\xml\\udom_modify.cpp"
0x180048dc4  mov     [rbp+var_10], 68Eh
0x180048dcb  mov     [rbp+var_20], rax
0x180048dcf  lea     rax, aWindowsUdomRtl_8; "Windows::uDom::Rtl::RtlMicrodomUpdateSe"...
0x180048dd6  mov     [rbp+var_18], rax
0x180048dda  lea     rax, aObjectcookieOp; "ObjectCookie.Opaque != 0"
0x180048de1  jmp     short loc_180048D9B
0x180048de3  test    rax, rax
0x180048de6  jz      short loc_180048E25
0x180048de8  mov     rcx, [r8]
0x180048deb  cmp     rcx, [r8+8]
0x180048def  ja      short loc_180048DFC
0x180048df1  cmp     [r8+10h], rbx
0x180048df5  jnz     short loc_180048E25
0x180048df7  test    rcx, rcx
0x180048dfa  jz      short loc_180048E25
0x180048dfc  lea     rax, aOnecoreBaseXml; "onecore\\base\\xml\\udom_modify.cpp"
0x180048e03  mov     [rbp+var_10], 68Fh
0x180048e0a  mov     [rbp+var_20], rax
0x180048e0e  lea     rax, aWindowsUdomRtl_8; "Windows::uDom::Rtl::RtlMicrodomUpdateSe"...
0x180048e15  mov     [rbp+var_18], rax
0x180048e19  lea     rax, aValue0Rtlislut; "(Value == 0) || RtlIsLUtf8StringValid(V"...
0x180048e20  jmp     loc_180048D9B
0x180048e25  mov     rcx, [rdx+38h]
0x180048e29  test    rcx, rcx
0x180048e2c  jnz     short loc_180048E57
0x180048e2e  lea     rax, aOnecoreBaseXml; "onecore\\base\\xml\\udom_modify.cpp"
0x180048e35  mov     [rbp+var_10], 691h
0x180048e3c  mov     [rbp+var_20], rax
0x180048e40  lea     rax, aWindowsUdomRtl_8; "Windows::uDom::Rtl::RtlMicrodomUpdateSe"...
0x180048e47  mov     [rbp+var_18], rax
0x180048e4b  lea     rax, aPchildPbasicno; "pChild->pBasicNode != 0"
0x180048e52  jmp     loc_180048D9B
0x180048e57  mov     r8, [rcx]
0x180048e5a  mov     rdx, rax
0x180048e5d  mov     rax, [r8+48h]
0x180048e61  call    cs:__guard_dispatch_icall_fptr
0x180048e67  test    eax, eax
0x180048e69  cmovs   ebx, eax
0x180048e6c  mov     eax, ebx
0x180048e6e  mov     rbx, [rsp+40h+arg_18]
0x180048e73  add     rsp, 40h
0x180048e77  pop     rbp
0x180048e78  retn
```
