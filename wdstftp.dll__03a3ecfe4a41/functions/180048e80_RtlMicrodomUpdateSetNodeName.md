# RtlMicrodomUpdateSetNodeName

- ea: `0x180048e80`
- end: `0x180048f96`
- name: `RtlMicrodomUpdateSetNodeName`
- size: `278`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180045d80`

## callees

- `0x1800370f4`
- `0x180048e80`
- `0x180060e70`

## string_xrefs

- `0x180048e97`: `onecore\base\xml\udom_modify.cpp`
- `0x180048ec5`: `onecore\base\xml\udom_modify.cpp`
- `0x180048f10`: `onecore\base\xml\udom_modify.cpp`
- `0x180048f4f`: `onecore\base\xml\udom_modify.cpp`
- `0x180048eb4`: `RtlIsMicrodomUpdateContextValid(HostUpdate)`
- `0x180048ea9`: `Windows::uDom::Rtl::RtlMicrodomUpdateSetNodeName`
- `0x180048ed7`: `Windows::uDom::Rtl::RtlMicrodomUpdateSetNodeName`
- `0x180048f22`: `Windows::uDom::Rtl::RtlMicrodomUpdateSetNodeName`
- `0x180048f61`: `Windows::uDom::Rtl::RtlMicrodomUpdateSetNodeName`

## pseudocode

```c
__int64 __fastcall RtlMicrodomUpdateSetNodeName(__int64 a1, __int64 a2, _QWORD *a3)
{
  unsigned int v3; // ebx
  const char *v4; // rax
  __int64 v5; // rcx
  int v6; // eax
  const char *v8; // [rsp+20h] [rbp-20h] BYREF
  const char *v9; // [rsp+28h] [rbp-18h]
  int v10; // [rsp+30h] [rbp-10h]
  const char *v11; // [rsp+38h] [rbp-8h]

  v3 = 0;
  if ( !a1 )
  {
    v10 = 1700;
    v8 = "onecore\\base\\xml\\udom_modify.cpp";
    v9 = "Windows::uDom::Rtl::RtlMicrodomUpdateSetNodeName";
    v4 = "RtlIsMicrodomUpdateContextValid(HostUpdate)";
LABEL_15:
    v11 = v4;
    RtlReportErrorOrigination(&v8, a2, 3221225485LL);
    return 3221225485LL;
  }
  if ( !a2 )
  {
    v10 = 1701;
    v8 = "onecore\\base\\xml\\udom_modify.cpp";
    v9 = "Windows::uDom::Rtl::RtlMicrodomUpdateSetNodeName";
    v4 = "ObjectCookie.Opaque != 0";
    goto LABEL_15;
  }
  if ( !a3 || *a3 > a3[1] || !a3[2] && *a3 )
  {
    v10 = 1702;
    v8 = "onecore\\base\\xml\\udom_modify.cpp";
    v9 = "Windows::uDom::Rtl::RtlMicrodomUpdateSetNodeName";
    v4 = "RtlIsLUtf8StringValid(Name)";
    goto LABEL_15;
  }
  v5 = *(_QWORD *)(a2 + 56);
  if ( !v5 )
  {
    v10 = 1704;
    v8 = "onecore\\base\\xml\\udom_modify.cpp";
    v9 = "Windows::uDom::Rtl::RtlMicrodomUpdateSetNodeName";
    v4 = "pChild->pBasicNode != 0";
    goto LABEL_15;
  }
  v6 = (*(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v5 + 48LL))(v5, a3);
  if ( v6 < 0 )
    return (unsigned int)v6;
  return v3;
}

```

## disassembly

```asm
0x180048e80  mov     [rsp-8+arg_18], rbx
0x180048e85  push    rbp
0x180048e86  mov     rbp, rsp
0x180048e89  sub     rsp, 40h
0x180048e8d  xor     ebx, ebx
0x180048e8f  mov     rax, r8
0x180048e92  test    rcx, rcx
0x180048e95  jnz     short loc_180048EC0
0x180048e97  lea     rax, aOnecoreBaseXml; "onecore\\base\\xml\\udom_modify.cpp"
0x180048e9e  mov     [rbp+var_10], 6A4h
0x180048ea5  mov     [rbp+var_20], rax
0x180048ea9  lea     rax, aWindowsUdomRtl; "Windows::uDom::Rtl::RtlMicrodomUpdateSe"...
0x180048eb0  mov     [rbp+var_18], rax
0x180048eb4  lea     rax, aRtlismicrodomu_0; "RtlIsMicrodomUpdateContextValid(HostUpd"...
0x180048ebb  jmp     loc_180048F73
0x180048ec0  test    rdx, rdx
0x180048ec3  jnz     short loc_180048EEE
0x180048ec5  lea     rax, aOnecoreBaseXml; "onecore\\base\\xml\\udom_modify.cpp"
0x180048ecc  mov     [rbp+var_10], 6A5h
0x180048ed3  mov     [rbp+var_20], rax
0x180048ed7  lea     rax, aWindowsUdomRtl; "Windows::uDom::Rtl::RtlMicrodomUpdateSe"...
0x180048ede  mov     [rbp+var_18], rax
0x180048ee2  lea     rax, aObjectcookieOp; "ObjectCookie.Opaque != 0"
0x180048ee9  jmp     loc_180048F73
0x180048eee  test    rax, rax
0x180048ef1  jz      short loc_180048F4F
0x180048ef3  mov     rcx, [r8]
0x180048ef6  cmp     rcx, [r8+8]
0x180048efa  ja      short loc_180048F4F
0x180048efc  cmp     [r8+10h], rbx
0x180048f00  jnz     short loc_180048F07
0x180048f02  test    rcx, rcx
0x180048f05  jnz     short loc_180048F4F
0x180048f07  mov     rcx, [rdx+38h]
0x180048f0b  test    rcx, rcx
0x180048f0e  jnz     short loc_180048F36
0x180048f10  lea     rax, aOnecoreBaseXml; "onecore\\base\\xml\\udom_modify.cpp"
0x180048f17  mov     [rbp+var_10], 6A8h
0x180048f1e  mov     [rbp+var_20], rax
0x180048f22  lea     rax, aWindowsUdomRtl; "Windows::uDom::Rtl::RtlMicrodomUpdateSe"...
0x180048f29  mov     [rbp+var_18], rax
0x180048f2d  lea     rax, aPchildPbasicno; "pChild->pBasicNode != 0"
0x180048f34  jmp     short loc_180048F73
0x180048f36  mov     r8, [rcx]
0x180048f39  mov     rdx, rax
0x180048f3c  mov     rax, [r8+30h]
0x180048f40  call    cs:__guard_dispatch_icall_fptr
0x180048f46  test    eax, eax
0x180048f48  cmovs   ebx, eax
0x180048f4b  mov     eax, ebx
0x180048f4d  jmp     short loc_180048F8B
0x180048f4f  lea     rax, aOnecoreBaseXml; "onecore\\base\\xml\\udom_modify.cpp"
0x180048f56  mov     [rbp+var_10], 6A6h
0x180048f5d  mov     [rbp+var_20], rax
0x180048f61  lea     rax, aWindowsUdomRtl; "Windows::uDom::Rtl::RtlMicrodomUpdateSe"...
0x180048f68  mov     [rbp+var_18], rax
0x180048f6c  lea     rax, aRtlislutf8stri_10; "RtlIsLUtf8StringValid(Name)"
0x180048f73  mov     r8d, 0C000000Dh
0x180048f79  mov     [rbp+var_8], rax
0x180048f7d  lea     rcx, [rbp+var_20]
0x180048f81  call    RtlReportErrorOrigination
0x180048f86  mov     eax, 0C000000Dh
0x180048f8b  mov     rbx, [rsp+40h+arg_18]
0x180048f90  add     rsp, 40h
0x180048f94  pop     rbp
0x180048f95  retn
```
