# MicrodomImplementation::CMicrodom_IRtlMicrodomTearoff::GetElementsByTagNameNS(Windows::Microdom::Rtl::Element,_LUTF8_STRING const *,_LUTF8_STRING const *,Windows::Auto<Windows::Vector<Windows::Microdom::Rtl::Element>> *)

- ea: `0x18004e5c0`
- end: `0x18004e7b2`
- name: `?GetElementsByTagNameNS@CMicrodom_IRtlMicrodomTearoff@MicrodomImplementation@@UEAAJUElement@Rtl@Microdom@Windows@@PEBU_LUTF8_STRING@@1PEAV?$Auto@U?$Vector@UElement@Rtl@Microdom@Windows@@@Windows@@@6@@Z`
- size: `498`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800370f4`
- `0x18004b784`
- `0x18004e5c0`
- `0x1800607b0`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18004e6e2`
- `ntdll!RtlFreeHeap` at `0x18004e71f`
- `ntdll!RtlFreeHeap` at `0x18004e6e2`
- `ntdll!RtlFreeHeap` at `0x18004e71f`

## string_xrefs

- `0x18004e5f4`: `onecore\base\xml\udom_microdom.cpp`
- `0x18004e676`: `onecore\base\xml\udom_microdom.cpp`
- `0x18004e72f`: `onecore\base\xml\udom_microdom.cpp`
- `0x18004e75d`: `onecore\base\xml\udom_microdom.cpp`
- `0x18004e77e`: `RtlIsLUtf8StringValid(NamespaceURI)`

## pseudocode

```c
__int64 __fastcall MicrodomImplementation::CMicrodom_IRtlMicrodomTearoff::GetElementsByTagNameNS(
        __int64 a1,
        __int64 a2,
        _QWORD *a3,
        _QWORD *a4,
        _OWORD *a5)
{
  __int64 v5; // rdx
  _QWORD *v6; // rcx
  int ElementsByTagName; // ebx
  __int128 v8; // xmm0
  PVOID v9; // rax
  _QWORD v11[2]; // [rsp+30h] [rbp-61h] BYREF
  int v12; // [rsp+40h] [rbp-51h]
  const char *v13; // [rsp+48h] [rbp-49h]
  _QWORD v14[2]; // [rsp+50h] [rbp-41h] BYREF
  int v15; // [rsp+60h] [rbp-31h]
  const char *v16; // [rsp+68h] [rbp-29h]
  _QWORD v17[2]; // [rsp+70h] [rbp-21h] BYREF
  int v18; // [rsp+80h] [rbp-11h]
  const char *v19; // [rsp+88h] [rbp-9h]
  _QWORD v20[2]; // [rsp+90h] [rbp-1h] BYREF
  int v21; // [rsp+A0h] [rbp+Fh]
  const char *v22; // [rsp+A8h] [rbp+17h]
  PVOID P[2]; // [rsp+B0h] [rbp+1Fh] BYREF

  P[0] = 0;
  P[1] = 0;
  v5 = *(unsigned int *)(a2 + 8);
  if ( (_DWORD)v5 == -1 )
  {
    v12 = 3393;
    v11[0] = "onecore\\base\\xml\\udom_microdom.cpp";
    v6 = v11;
    v11[1] = "MicrodomImplementation::CMicrodom_IRtlMicrodomTearoff::GetElementsByTagNameNS";
    v13 = "TheElement != TheElement.InvalidValue()";
LABEL_21:
    RtlReportErrorOrigination(v6, v5, 3221225485LL);
    return (unsigned int)-1073741811;
  }
  if ( !a3 || *a3 > a3[1] || !a3[2] && *a3 )
  {
    v21 = 3394;
    v20[0] = "onecore\\base\\xml\\udom_microdom.cpp";
    v6 = v20;
    v20[1] = "MicrodomImplementation::CMicrodom_IRtlMicrodomTearoff::GetElementsByTagNameNS";
    v22 = "RtlIsLUtf8StringValid(NamespaceURI)";
    goto LABEL_21;
  }
  if ( !a4 || *a4 > a4[1] || !a4[2] && *a4 )
  {
    v18 = 3395;
    v17[0] = "onecore\\base\\xml\\udom_microdom.cpp";
    v6 = v17;
    v17[1] = "MicrodomImplementation::CMicrodom_IRtlMicrodomTearoff::GetElementsByTagNameNS";
    v19 = "RtlIsLUtf8StringValid(LocalName)";
    goto LABEL_21;
  }
  if ( !a5 )
  {
    v15 = 3396;
    v14[0] = "onecore\\base\\xml\\udom_microdom.cpp";
    v6 = v14;
    v14[1] = "MicrodomImplementation::CMicrodom_IRtlMicrodomTearoff::GetElementsByTagNameNS";
    v16 = "Not-null check failed: Matches";
    goto LABEL_21;
  }
  ElementsByTagName = MicrodomImplementation::CMicrodom::GetElementsByTagName(
                        *(_QWORD *)(a1 - 8),
                        v5,
                        (_DWORD)a3,
                        (_DWORD)a4,
                        1,
                        (__int64)P);
  if ( ElementsByTagName < 0 )
  {
    if ( P[0] )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P[0]);
    return (unsigned int)ElementsByTagName;
  }
  v8 = *(_OWORD *)P;
  *(_OWORD *)P = *a5;
  v9 = P[0];
  *a5 = v8;
  if ( v9 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P[0]);
  return 0;
}

```

## disassembly

```asm
0x18004e5c0  push    rbp
0x18004e5c2  push    rbx
0x18004e5c3  push    rdi
0x18004e5c4  lea     rbp, [rsp-3Fh]
0x18004e5c9  sub     rsp, 0D0h
0x18004e5d0  mov     rax, cs:__security_cookie
0x18004e5d7  xor     rax, rsp
0x18004e5da  mov     [rbp+4Fh+var_20], rax
0x18004e5de  and     [rbp+4Fh+P], 0
0x18004e5e3  and     [rbp+4Fh+P+8], 0
0x18004e5e8  mov     edx, [rdx+8]
0x18004e5eb  mov     rdi, [rbp+4Fh+arg_20]
0x18004e5ef  cmp     edx, 0FFFFFFFFh
0x18004e5f2  jnz     short loc_18004E625
0x18004e5f4  lea     rax, aOnecoreBaseXml_0; "onecore\\base\\xml\\udom_microdom.cpp"
0x18004e5fb  mov     [rbp+4Fh+var_A0], 0D41h
0x18004e602  mov     [rbp+4Fh+var_B0], rax
0x18004e606  lea     rcx, [rbp+4Fh+var_B0]
0x18004e60a  lea     rax, aMicrodomimplem_33; "MicrodomImplementation::CMicrodom_IRtlM"...
0x18004e611  mov     [rbp+4Fh+var_A8], rax
0x18004e615  lea     rax, aTheelementThee; "TheElement != TheElement.InvalidValue()"
0x18004e61c  mov     [rbp+4Fh+var_98], rax
0x18004e620  jmp     loc_18004E789
0x18004e625  test    r8, r8
0x18004e628  jz      loc_18004E75D
0x18004e62e  mov     rax, [r8]
0x18004e631  cmp     rax, [r8+8]
0x18004e635  ja      loc_18004E75D
0x18004e63b  cmp     qword ptr [r8+10h], 0
0x18004e640  jnz     short loc_18004E64B
0x18004e642  test    rax, rax
0x18004e645  jnz     loc_18004E75D
0x18004e64b  test    r9, r9
0x18004e64e  jz      loc_18004E72F
0x18004e654  mov     rax, [r9]
0x18004e657  cmp     rax, [r9+8]
0x18004e65b  ja      loc_18004E72F
0x18004e661  cmp     qword ptr [r9+10h], 0
0x18004e666  jnz     short loc_18004E671
0x18004e668  test    rax, rax
0x18004e66b  jnz     loc_18004E72F
0x18004e671  test    rdi, rdi
0x18004e674  jnz     short loc_18004E6A7
0x18004e676  lea     rax, aOnecoreBaseXml_0; "onecore\\base\\xml\\udom_microdom.cpp"
0x18004e67d  mov     [rbp+4Fh+var_80], 0D44h
0x18004e684  mov     [rbp+4Fh+var_90], rax
0x18004e688  lea     rcx, [rbp+4Fh+var_90]
0x18004e68c  lea     rax, aMicrodomimplem_33; "MicrodomImplementation::CMicrodom_IRtlM"...
0x18004e693  mov     [rbp+4Fh+var_88], rax
0x18004e697  lea     rax, aNotNullCheckFa_34; "Not-null check failed: Matches"
0x18004e69e  mov     [rbp+4Fh+var_78], rax
0x18004e6a2  jmp     loc_18004E789
0x18004e6a7  mov     rcx, [rcx-8]
0x18004e6ab  lea     rax, [rbp+4Fh+P]
0x18004e6af  mov     [rsp+0E0h+var_B8], rax
0x18004e6b4  mov     [rsp+0E0h+var_C0], 1
0x18004e6b9  call    ?GetElementsByTagName@CMicrodom@MicrodomImplementation@@QEAAJKPEBU_LUTF8_STRING@@0_NPEAV?$Auto@U?$Vector@UElement@Rtl@Microdom@Windows@@@Windows@@@Windows@@@Z; MicrodomImplementation::CMicrodom::GetElementsByTagName(ulong,_LUTF8_STRING const *,_LUTF8_STRING const *,bool,Windows::Auto<Windows::Vector<Windows::Microdom::Rtl::Element>> *)
0x18004e6be  mov     ebx, eax
0x18004e6c0  test    eax, eax
0x18004e6c2  jns     short loc_18004E6F3
0x18004e6c4  cmp     [rbp+4Fh+P], 0
0x18004e6c9  jz      loc_18004E799
0x18004e6cf  mov     rcx, gs:60h
0x18004e6d8  xor     edx, edx; Flags
0x18004e6da  mov     r8, [rbp+4Fh+P]; P
0x18004e6de  mov     rcx, [rcx+30h]; HeapHandle
0x18004e6e2  call    cs:__imp_RtlFreeHeap
0x18004e6e9  nop     dword ptr [rax+rax+00h]
0x18004e6ee  jmp     loc_18004E799
0x18004e6f3  movups  xmm1, xmmword ptr [rdi]
0x18004e6f6  movaps  xmm0, xmmword ptr [rbp+4Fh+P]
0x18004e6fa  movq    rax, xmm1
0x18004e6ff  movaps  xmmword ptr [rbp+4Fh+P], xmm1
0x18004e703  movdqu  xmmword ptr [rdi], xmm0
0x18004e707  test    rax, rax
0x18004e70a  jz      short loc_18004E72B
0x18004e70c  mov     rcx, gs:60h
0x18004e715  xor     edx, edx; Flags
0x18004e717  mov     r8, [rbp+4Fh+P]; P
0x18004e71b  mov     rcx, [rcx+30h]; HeapHandle
0x18004e71f  call    cs:__imp_RtlFreeHeap
0x18004e726  nop     dword ptr [rax+rax+00h]
0x18004e72b  xor     eax, eax
0x18004e72d  jmp     short loc_18004E79B
0x18004e72f  lea     rax, aOnecoreBaseXml_0; "onecore\\base\\xml\\udom_microdom.cpp"
0x18004e736  mov     [rbp+4Fh+var_60], 0D43h
0x18004e73d  mov     [rbp+4Fh+var_70], rax
0x18004e741  lea     rcx, [rbp+4Fh+var_70]
0x18004e745  lea     rax, aMicrodomimplem_33; "MicrodomImplementation::CMicrodom_IRtlM"...
0x18004e74c  mov     [rbp+4Fh+var_68], rax
0x18004e750  lea     rax, aRtlislutf8stri; "RtlIsLUtf8StringValid(LocalName)"
0x18004e757  mov     [rbp+4Fh+var_58], rax
0x18004e75b  jmp     short loc_18004E789
0x18004e75d  lea     rax, aOnecoreBaseXml_0; "onecore\\base\\xml\\udom_microdom.cpp"
0x18004e764  mov     [rbp+4Fh+var_40], 0D42h
0x18004e76b  mov     [rbp+4Fh+var_50], rax
0x18004e76f  lea     rcx, [rbp+4Fh+var_50]
0x18004e773  lea     rax, aMicrodomimplem_33; "MicrodomImplementation::CMicrodom_IRtlM"...
0x18004e77a  mov     [rbp+4Fh+var_48], rax
0x18004e77e  lea     rax, aRtlislutf8stri_9; "RtlIsLUtf8StringValid(NamespaceURI)"
0x18004e785  mov     [rbp+4Fh+var_38], rax
0x18004e789  mov     r8d, 0C000000Dh
0x18004e78f  call    RtlReportErrorOrigination
0x18004e794  mov     ebx, 0C000000Dh
0x18004e799  mov     eax, ebx
0x18004e79b  mov     rcx, [rbp+4Fh+var_20]
0x18004e79f  xor     rcx, rsp; StackCookie
0x18004e7a2  call    __security_check_cookie
0x18004e7a7  add     rsp, 0D0h
0x18004e7ae  pop     rdi
0x18004e7af  pop     rbx
0x18004e7b0  pop     rbp
0x18004e7b1  retn
```
