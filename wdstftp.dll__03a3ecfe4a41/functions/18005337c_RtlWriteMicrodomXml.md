# RtlWriteMicrodomXml

- ea: `0x18005337c`
- end: `0x180053509`
- name: `RtlWriteMicrodomXml`
- size: `397`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180044c00`
- `0x18004d360`

## callees

- `0x1800370f4`
- `0x180052c80`
- `0x180052f08`
- `0x18005337c`
- `0x1800607b0`
- `0x180060e70`

## string_xrefs

- `0x1800533ad`: `onecore\base\xml\udom_writer.cpp`
- `0x1800533f3`: `onecore\base\xml\udom_writer.cpp`
- `0x18005341e`: `onecore\base\xml\udom_writer.cpp`
- `0x1800534be`: `onecore\base\xml\udom_writer.cpp`
- `0x1800533bf`: `RtlWriteMicrodomXml`
- `0x180053405`: `RtlWriteMicrodomXml`
- `0x180053430`: `RtlWriteMicrodomXml`
- `0x1800534d0`: `RtlWriteMicrodomXml`
- `0x1800533ca`: `Not-null check failed: pWriter`

## pseudocode

```c
__int64 __fastcall RtlWriteMicrodomXml(
        __int64 a1,
        __int64 a2,
        struct Windows::Microdom::Rtl::IRtlMicrodomXmlWriter *a3,
        __int128 *a4,
        struct Windows::Microdom::Rtl::IRtlMicrodom *a5)
{
  const char *v8; // rax
  __int64 result; // rax
  MicrodomWriterImplementation *v10; // rcx
  __int64 v11; // rax
  __int64 v12; // rcx
  struct Windows::Rtl::IRtlWOFOStream *v13; // [rsp+20h] [rbp-60h]
  __int128 v14; // [rsp+30h] [rbp-50h] BYREF
  int v15; // [rsp+40h] [rbp-40h]
  const char *v16; // [rsp+48h] [rbp-38h]
  __int128 v17; // [rsp+50h] [rbp-30h] BYREF
  _BYTE v18[8]; // [rsp+60h] [rbp-20h] BYREF
  int v19; // [rsp+68h] [rbp-18h]

  if ( !a2 )
  {
    v15 = 987;
    *(_QWORD *)&v14 = "onecore\\base\\xml\\udom_writer.cpp";
    *((_QWORD *)&v14 + 1) = "RtlWriteMicrodomXml";
    v8 = "Not-null check failed: pWriter";
LABEL_3:
    v16 = v8;
    RtlReportErrorOrigination(&v14, a2, 3221225485LL);
    return 3221225485LL;
  }
  if ( !a3 )
  {
    v15 = 988;
    *(_QWORD *)&v14 = "onecore\\base\\xml\\udom_writer.cpp";
    *((_QWORD *)&v14 + 1) = "RtlWriteMicrodomXml";
    v8 = "Not-null check failed: pDocument";
    goto LABEL_3;
  }
  if ( !a5 )
  {
    v15 = 989;
    *(_QWORD *)&v14 = "onecore\\base\\xml\\udom_writer.cpp";
    *((_QWORD *)&v14 + 1) = "RtlWriteMicrodomXml";
    v8 = "Not-null check failed: pOutputStream";
    goto LABEL_3;
  }
  result = (*(__int64 (__fastcall **)(struct Windows::Microdom::Rtl::IRtlMicrodomXmlWriter *, _BYTE *))(*(_QWORD *)a3 + 24LL))(
             a3,
             v18);
  if ( (int)result >= 0 )
  {
    if ( v19 == *((_DWORD *)a4 + 2) )
    {
      result = MicrodomWriterImplementation::WalkDocumentNodes(v10, a2, a3, a5, v13);
    }
    else
    {
      v11 = *(_QWORD *)a3;
      v14 = *a4;
      result = (*(__int64 (__fastcall **)(struct Windows::Microdom::Rtl::IRtlMicrodomXmlWriter *, __int128 *, __int128 *))(v11 + 88))(
                 a3,
                 &v14,
                 &v17);
      if ( (int)result < 0 )
        return result;
      if ( DWORD2(v17) == -1 )
      {
        v15 = 1003;
        *(_QWORD *)&v14 = "onecore\\base\\xml\\udom_writer.cpp";
        *((_QWORD *)&v14 + 1) = "RtlWriteMicrodomXml";
        v8 = "TheElement != TheElement.InvalidValue()";
        goto LABEL_3;
      }
      v14 = v17;
      result = MicrodomWriterImplementation::WalkAndWriteElement(v12, a2, a3, &v14, a5);
    }
    if ( (int)result >= 0 )
      return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18005337c  push    rbp
0x18005337e  push    rbx
0x18005337f  push    rsi
0x180053380  push    rdi
0x180053381  push    r14
0x180053383  mov     rbp, rsp
0x180053386  sub     rsp, 80h
0x18005338d  mov     rax, cs:__security_cookie
0x180053394  xor     rax, rsp
0x180053397  mov     [rbp+var_10], rax
0x18005339b  mov     rdi, [rbp+arg_20]
0x18005339f  mov     r14, r9
0x1800533a2  mov     rbx, r8
0x1800533a5  mov     rsi, rdx
0x1800533a8  test    rdx, rdx
0x1800533ab  jnz     short loc_1800533EE
0x1800533ad  lea     rax, aOnecoreBaseXml_2; "onecore\\base\\xml\\udom_writer.cpp"
0x1800533b4  mov     [rbp+var_40], 3DBh
0x1800533bb  mov     qword ptr [rbp+var_50], rax
0x1800533bf  lea     rax, aRtlwritemicrod; "RtlWriteMicrodomXml"
0x1800533c6  mov     qword ptr [rbp+var_50+8], rax
0x1800533ca  lea     rax, aNotNullCheckFa_16; "Not-null check failed: pWriter"
0x1800533d1  mov     r8d, 0C000000Dh
0x1800533d7  mov     [rbp+var_38], rax
0x1800533db  lea     rcx, [rbp+var_50]
0x1800533df  call    RtlReportErrorOrigination
0x1800533e4  mov     eax, 0C000000Dh
0x1800533e9  jmp     loc_180053479
0x1800533ee  test    rbx, rbx
0x1800533f1  jnz     short loc_180053419
0x1800533f3  lea     rax, aOnecoreBaseXml_2; "onecore\\base\\xml\\udom_writer.cpp"
0x1800533fa  mov     [rbp+var_40], 3DCh
0x180053401  mov     qword ptr [rbp+var_50], rax
0x180053405  lea     rax, aRtlwritemicrod; "RtlWriteMicrodomXml"
0x18005340c  mov     qword ptr [rbp+var_50+8], rax
0x180053410  lea     rax, aNotNullCheckFa_20; "Not-null check failed: pDocument"
0x180053417  jmp     short loc_1800533D1
0x180053419  test    rdi, rdi
0x18005341c  jnz     short loc_180053444
0x18005341e  lea     rax, aOnecoreBaseXml_2; "onecore\\base\\xml\\udom_writer.cpp"
0x180053425  mov     [rbp+var_40], 3DDh
0x18005342c  mov     qword ptr [rbp+var_50], rax
0x180053430  lea     rax, aRtlwritemicrod; "RtlWriteMicrodomXml"
0x180053437  mov     qword ptr [rbp+var_50+8], rax
0x18005343b  lea     rax, aNotNullCheckFa_33; "Not-null check failed: pOutputStream"
0x180053442  jmp     short loc_1800533D1
0x180053444  mov     rax, [r8]
0x180053447  lea     rdx, [rbp+var_20]
0x18005344b  mov     rcx, rbx
0x18005344e  mov     rax, [rax+18h]
0x180053452  call    cs:__guard_dispatch_icall_fptr
0x180053458  test    eax, eax
0x18005345a  js      short loc_180053479
0x18005345c  mov     eax, [r14+8]
0x180053460  cmp     [rbp+var_18], eax
0x180053463  jnz     short loc_180053493
0x180053465  mov     r9, rdi; struct Windows::Microdom::Rtl::IRtlMicrodom *
0x180053468  mov     r8, rbx; struct Windows::Microdom::Rtl::IRtlMicrodomXmlWriter *
0x18005346b  mov     rdx, rsi; unsigned int
0x18005346e  call    ?WalkDocumentNodes@MicrodomWriterImplementation@@YAJKPEAUIRtlMicrodomXmlWriter@Rtl@Microdom@Windows@@PEAUIRtlMicrodom@345@PEAUIRtlWOFOStream@35@@Z; MicrodomWriterImplementation::WalkDocumentNodes(ulong,Windows::Microdom::Rtl::IRtlMicrodomXmlWriter *,Windows::Microdom::Rtl::IRtlMicrodom *,Windows::Rtl::IRtlWOFOStream *)
0x180053473  test    eax, eax
0x180053475  js      short loc_180053479
0x180053477  xor     eax, eax
0x180053479  mov     rcx, [rbp+var_10]
0x18005347d  xor     rcx, rsp; StackCookie
0x180053480  call    __security_check_cookie
0x180053485  add     rsp, 80h
0x18005348c  pop     r14
0x18005348e  pop     rdi
0x18005348f  pop     rsi
0x180053490  pop     rbx
0x180053491  pop     rbp
0x180053492  retn
0x180053493  mov     rax, [rbx]
0x180053496  lea     r8, [rbp+var_30]
0x18005349a  movaps  xmm0, xmmword ptr [r14]
0x18005349e  lea     rdx, [rbp+var_50]
0x1800534a2  mov     rcx, rbx
0x1800534a5  movdqa  [rbp+var_50], xmm0
0x1800534aa  mov     rax, [rax+58h]
0x1800534ae  call    cs:__guard_dispatch_icall_fptr
0x1800534b4  test    eax, eax
0x1800534b6  js      short loc_180053479
0x1800534b8  cmp     dword ptr [rbp+var_30+8], 0FFFFFFFFh
0x1800534bc  jnz     short loc_1800534E7
0x1800534be  lea     rax, aOnecoreBaseXml_2; "onecore\\base\\xml\\udom_writer.cpp"
0x1800534c5  mov     [rbp+var_40], 3EBh
0x1800534cc  mov     qword ptr [rbp+var_50], rax
0x1800534d0  lea     rax, aRtlwritemicrod; "RtlWriteMicrodomXml"
0x1800534d7  mov     qword ptr [rbp+var_50+8], rax
0x1800534db  lea     rax, aTheelementThee; "TheElement != TheElement.InvalidValue()"
0x1800534e2  jmp     loc_1800533D1
0x1800534e7  movaps  xmm0, [rbp+var_30]
0x1800534eb  lea     r9, [rbp+var_50]
0x1800534ef  mov     r8, rbx
0x1800534f2  movdqa  [rbp+var_50], xmm0
0x1800534f7  mov     rdx, rsi
0x1800534fa  mov     [rsp+80h+var_60], rdi
0x1800534ff  call    ?WalkAndWriteElement@MicrodomWriterImplementation@@YAJKPEAUIRtlMicrodomXmlWriter@Rtl@Microdom@Windows@@PEAUIRtlMicrodom@345@UElement@345@PEAUIRtlWOFOStream@35@@Z; MicrodomWriterImplementation::WalkAndWriteElement(ulong,Windows::Microdom::Rtl::IRtlMicrodomXmlWriter *,Windows::Microdom::Rtl::IRtlMicrodom *,Windows::Microdom::Rtl::Element,Windows::Rtl::IRtlWOFOStream *)
0x180053504  jmp     loc_180053473
```
