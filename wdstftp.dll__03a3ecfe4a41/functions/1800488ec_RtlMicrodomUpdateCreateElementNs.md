# RtlMicrodomUpdateCreateElementNs

- ea: `0x1800488ec`
- end: `0x180048a16`
- name: `RtlMicrodomUpdateCreateElementNs`
- size: `298`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180043a80`
- `0x180043efc`

## callees

- `0x1800370f4`
- `0x18004632c`
- `0x180048104`
- `0x1800488ec`

## string_xrefs

- `0x180048921`: `onecore\base\xml\udom_modify.cpp`
- `0x180048969`: `onecore\base\xml\udom_modify.cpp`
- `0x1800489c5`: `onecore\base\xml\udom_modify.cpp`
- `0x180048933`: `Windows::uDom::Rtl::RtlMicrodomUpdateCreateElementNs`
- `0x18004897b`: `Windows::uDom::Rtl::RtlMicrodomUpdateCreateElementNs`
- `0x1800489d7`: `Windows::uDom::Rtl::RtlMicrodomUpdateCreateElementNs`
- `0x18004893e`: `RtlIsMicrodomUpdateContextValid(HostUpdate)`
- `0x180048986`: `Not-null check failed: pUpdateCookie`

## pseudocode

```c
__int64 __fastcall RtlMicrodomUpdateCreateElementNs(
        __int64 a1,
        CMicrodomUpdateContext *a2,
        __int64 a3,
        __int64 a4,
        struct _LUTF8_STRING *a5,
        struct CChildNode **a6)
{
  const char *v6; // rax
  __int64 result; // rax
  struct CChildNode *v8; // rdi
  const char *v9; // [rsp+20h] [rbp-30h] BYREF
  const char *v10; // [rsp+28h] [rbp-28h]
  int v11; // [rsp+30h] [rbp-20h]
  const char *v12; // [rsp+38h] [rbp-18h]
  struct CChildNode *v13; // [rsp+40h] [rbp-10h] BYREF

  v13 = 0;
  if ( a6 )
    *a6 = 0;
  if ( !a2 )
  {
    v11 = 1477;
    v9 = "onecore\\base\\xml\\udom_modify.cpp";
    v10 = "Windows::uDom::Rtl::RtlMicrodomUpdateCreateElementNs";
    v6 = "RtlIsMicrodomUpdateContextValid(HostUpdate)";
LABEL_17:
    v12 = v6;
    RtlReportErrorOrigination(&v9, a2, 3221225485LL);
    return 3221225485LL;
  }
  if ( !a5 || *(_QWORD *)a5 > *((_QWORD *)a5 + 1) || !*((_QWORD *)a5 + 2) && *(_QWORD *)a5 )
  {
    v11 = 1481;
    v9 = "onecore\\base\\xml\\udom_modify.cpp";
    v10 = "Windows::uDom::Rtl::RtlMicrodomUpdateCreateElementNs";
    v6 = "RtlIsLUtf8StringValid(LocalName)";
    goto LABEL_17;
  }
  if ( !a6 )
  {
    v11 = 1482;
    v9 = "onecore\\base\\xml\\udom_modify.cpp";
    v10 = "Windows::uDom::Rtl::RtlMicrodomUpdateCreateElementNs";
    v6 = "Not-null check failed: pUpdateCookie";
    goto LABEL_17;
  }
  result = CMicrodomUpdateContext::CreateVirtualElement(a2, &v13);
  if ( (int)result >= 0 )
  {
    v8 = v13;
    if ( !v13 )
      __debugbreak();
    result = CBasicNodeType::ForceNameSetting(*((CBasicNodeType **)v13 + 7), 0, 0, a5);
    if ( (int)result >= 0 )
    {
      *a6 = v8;
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800488ec  mov     [rsp-8+arg_0], rbx
0x1800488f1  mov     [rsp-8+arg_10], rsi
0x1800488f6  mov     [rsp-8+arg_18], rdi
0x1800488fb  push    rbp
0x1800488fc  mov     rbp, rsp
0x1800488ff  sub     rsp, 50h
0x180048903  mov     rsi, [rbp+arg_28]
0x180048907  mov     rax, rdx
0x18004890a  and     [rbp+var_10], 0
0x18004890f  mov     rbx, [rbp+arg_20]
0x180048913  test    rsi, rsi
0x180048916  jz      short loc_18004891C
0x180048918  and     qword ptr [rsi], 0
0x18004891c  test    rax, rax
0x18004891f  jnz     short loc_18004894A
0x180048921  lea     rax, aOnecoreBaseXml; "onecore\\base\\xml\\udom_modify.cpp"
0x180048928  mov     [rbp+var_20], 5C5h
0x18004892f  mov     [rbp+var_30], rax
0x180048933  lea     rax, aWindowsUdomRtl_10; "Windows::uDom::Rtl::RtlMicrodomUpdateCr"...
0x18004893a  mov     [rbp+var_28], rax
0x18004893e  lea     rax, aRtlismicrodomu_0; "RtlIsMicrodomUpdateContextValid(HostUpd"...
0x180048945  jmp     loc_1800489E9
0x18004894a  test    rbx, rbx
0x18004894d  jz      short loc_1800489C5
0x18004894f  mov     rcx, [rbx]
0x180048952  cmp     rcx, [rbx+8]
0x180048956  ja      short loc_1800489C5
0x180048958  cmp     qword ptr [rbx+10h], 0
0x18004895d  jnz     short loc_180048964
0x18004895f  test    rcx, rcx
0x180048962  jnz     short loc_1800489C5
0x180048964  test    rsi, rsi
0x180048967  jnz     short loc_18004898F
0x180048969  lea     rax, aOnecoreBaseXml; "onecore\\base\\xml\\udom_modify.cpp"
0x180048970  mov     [rbp+var_20], 5CAh
0x180048977  mov     [rbp+var_30], rax
0x18004897b  lea     rax, aWindowsUdomRtl_10; "Windows::uDom::Rtl::RtlMicrodomUpdateCr"...
0x180048982  mov     [rbp+var_28], rax
0x180048986  lea     rax, aNotNullCheckFa_14; "Not-null check failed: pUpdateCookie"
0x18004898d  jmp     short loc_1800489E9
0x18004898f  lea     rdx, [rbp+var_10]; struct CChildNode **
0x180048993  mov     rcx, rax; this
0x180048996  call    ?CreateVirtualElement@CMicrodomUpdateContext@@QEAAJAEAPEAVCChildNode@@@Z; CMicrodomUpdateContext::CreateVirtualElement(CChildNode * &)
0x18004899b  test    eax, eax
0x18004899d  js      short loc_180048A01
0x18004899f  mov     rdi, [rbp+var_10]
0x1800489a3  test    rdi, rdi
0x1800489a6  jnz     short loc_1800489A9
0x1800489a8  int     3; Trap to Debugger
0x1800489a9  mov     rcx, [rdi+38h]; this
0x1800489ad  mov     r9, rbx; struct _LUTF8_STRING *
0x1800489b0  xor     r8d, r8d; struct _LUTF8_STRING *
0x1800489b3  xor     edx, edx; struct _LUTF8_STRING *
0x1800489b5  call    ?ForceNameSetting@CBasicNodeType@@QEAAJPEBU_LUTF8_STRING@@00@Z; CBasicNodeType::ForceNameSetting(_LUTF8_STRING const *,_LUTF8_STRING const *,_LUTF8_STRING const *)
0x1800489ba  test    eax, eax
0x1800489bc  js      short loc_180048A01
0x1800489be  mov     [rsi], rdi
0x1800489c1  xor     eax, eax
0x1800489c3  jmp     short loc_180048A01
0x1800489c5  lea     rax, aOnecoreBaseXml; "onecore\\base\\xml\\udom_modify.cpp"
0x1800489cc  mov     [rbp+var_20], 5C9h
0x1800489d3  mov     [rbp+var_30], rax
0x1800489d7  lea     rax, aWindowsUdomRtl_10; "Windows::uDom::Rtl::RtlMicrodomUpdateCr"...
0x1800489de  mov     [rbp+var_28], rax
0x1800489e2  lea     rax, aRtlislutf8stri; "RtlIsLUtf8StringValid(LocalName)"
0x1800489e9  mov     r8d, 0C000000Dh
0x1800489ef  mov     [rbp+var_18], rax
0x1800489f3  lea     rcx, [rbp+var_30]
0x1800489f7  call    RtlReportErrorOrigination
0x1800489fc  mov     eax, 0C000000Dh
0x180048a01  mov     rbx, [rsp+50h+arg_0]
0x180048a06  mov     rsi, [rsp+50h+arg_10]
0x180048a0b  mov     rdi, [rsp+50h+arg_18]
0x180048a10  add     rsp, 50h
0x180048a14  pop     rbp
0x180048a15  retn
```
