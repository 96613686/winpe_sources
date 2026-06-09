# MicrodomImplementation::CMicrodom_IRtlMicrodomTearoff::GetElementsByTagNameNS(_LUTF8_STRING const *,_LUTF8_STRING const *,Windows::Auto<Windows::Vector<Windows::Microdom::Rtl::Element>> *)

- ea: `0x18004dd00`
- end: `0x18004de94`
- name: `?GetElementsByTagNameNS@CMicrodom_IRtlMicrodomTearoff@MicrodomImplementation@@UEAAJPEBU_LUTF8_STRING@@0PEAV?$Auto@U?$Vector@UElement@Rtl@Microdom@Windows@@@Windows@@@Windows@@@Z`
- size: `404`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800370f4`
- `0x18004bb10`
- `0x18004dd00`
- `0x1800607b0`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18004de33`
- `ntdll!RtlFreeHeap` at `0x18004de6f`
- `ntdll!RtlFreeHeap` at `0x18004de33`
- `ntdll!RtlFreeHeap` at `0x18004de6f`

## string_xrefs

- `0x18004dd45`: `onecore\base\xml\udom_microdom.cpp`
- `0x18004dd8d`: `onecore\base\xml\udom_microdom.cpp`
- `0x18004ddc0`: `onecore\base\xml\udom_microdom.cpp`
- `0x18004dd66`: `RtlIsLUtf8StringValid(NamespaceURI) || (NamespaceURI == 0)`

## pseudocode

```c
__int64 __fastcall MicrodomImplementation::CMicrodom_IRtlMicrodomTearoff::GetElementsByTagNameNS(
        __int64 a1,
        _QWORD *a2,
        _QWORD *a3,
        _OWORD *a4)
{
  _QWORD *v5; // rcx
  int ElementsByTagName; // ebx
  __int128 v8; // xmm0
  PVOID v9; // rax
  _QWORD v10[2]; // [rsp+30h] [rbp-39h] BYREF
  int v11; // [rsp+40h] [rbp-29h]
  const char *v12; // [rsp+48h] [rbp-21h]
  _QWORD v13[2]; // [rsp+50h] [rbp-19h] BYREF
  int v14; // [rsp+60h] [rbp-9h]
  const char *v15; // [rsp+68h] [rbp-1h]
  _QWORD v16[2]; // [rsp+70h] [rbp+7h] BYREF
  int v17; // [rsp+80h] [rbp+17h]
  const char *v18; // [rsp+88h] [rbp+1Fh]
  PVOID P[2]; // [rsp+90h] [rbp+27h] BYREF

  P[0] = 0;
  P[1] = 0;
  if ( a2 && (*a2 > a2[1] || !a2[2] && *a2) )
  {
    v11 = 3241;
    v10[0] = "onecore\\base\\xml\\udom_microdom.cpp";
    v5 = v10;
    v10[1] = "MicrodomImplementation::CMicrodom_IRtlMicrodomTearoff::GetElementsByTagNameNS";
    v12 = "RtlIsLUtf8StringValid(NamespaceURI) || (NamespaceURI == 0)";
LABEL_13:
    RtlReportErrorOrigination(v5, a2, 3221225485LL);
    return (unsigned int)-1073741811;
  }
  if ( a3 && (*a3 > a3[1] || !a3[2] && *a3) )
  {
    v14 = 3242;
    v13[0] = "onecore\\base\\xml\\udom_microdom.cpp";
    v5 = v13;
    v13[1] = "MicrodomImplementation::CMicrodom_IRtlMicrodomTearoff::GetElementsByTagNameNS";
    v15 = "RtlIsLUtf8StringValid(LocalName) || (LocalName == 0)";
    goto LABEL_13;
  }
  if ( !a4 )
  {
    v17 = 3243;
    v16[0] = "onecore\\base\\xml\\udom_microdom.cpp";
    v5 = v16;
    v16[1] = "MicrodomImplementation::CMicrodom_IRtlMicrodomTearoff::GetElementsByTagNameNS";
    v18 = "Not-null check failed: NodeList";
    goto LABEL_13;
  }
  ElementsByTagName = MicrodomImplementation::CMicrodom::GetElementsByTagName(
                        *(MicrodomImplementation::CMicrodom **)(a1 - 8),
                        (__int64)P);
  if ( ElementsByTagName < 0 )
  {
    if ( P[0] )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P[0]);
    return (unsigned int)ElementsByTagName;
  }
  v8 = *(_OWORD *)P;
  *(_OWORD *)P = *a4;
  v9 = P[0];
  *a4 = v8;
  if ( v9 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P[0]);
  return 0;
}

```

## disassembly

```asm
0x18004dd00  push    rbp
0x18004dd02  push    rbx
0x18004dd03  push    rdi
0x18004dd04  lea     rbp, [rsp-47h]
0x18004dd09  sub     rsp, 0B0h
0x18004dd10  mov     rax, cs:__security_cookie
0x18004dd17  xor     rax, rsp
0x18004dd1a  mov     [rbp+57h+var_20], rax
0x18004dd1e  and     [rbp+57h+P], 0
0x18004dd23  mov     rdi, r9
0x18004dd26  and     [rbp+57h+P+8], 0
0x18004dd2b  test    rdx, rdx
0x18004dd2e  jz      short loc_18004DD73
0x18004dd30  mov     rax, [rdx]
0x18004dd33  cmp     rax, [rdx+8]
0x18004dd37  ja      short loc_18004DD45
0x18004dd39  cmp     qword ptr [rdx+10h], 0
0x18004dd3e  jnz     short loc_18004DD73
0x18004dd40  test    rax, rax
0x18004dd43  jz      short loc_18004DD73
0x18004dd45  lea     rax, aOnecoreBaseXml_0; "onecore\\base\\xml\\udom_microdom.cpp"
0x18004dd4c  mov     [rbp+57h+var_80], 0CA9h
0x18004dd53  mov     [rbp+57h+var_90], rax
0x18004dd57  lea     rcx, [rbp+57h+var_90]
0x18004dd5b  lea     rax, aMicrodomimplem_33; "MicrodomImplementation::CMicrodom_IRtlM"...
0x18004dd62  mov     [rbp+57h+var_88], rax
0x18004dd66  lea     rax, aRtlislutf8stri_2; "RtlIsLUtf8StringValid(NamespaceURI) || "...
0x18004dd6d  mov     [rbp+57h+var_78], rax
0x18004dd71  jmp     short loc_18004DDEC
0x18004dd73  test    r8, r8
0x18004dd76  jz      short loc_18004DDBB
0x18004dd78  mov     rax, [r8]
0x18004dd7b  cmp     rax, [r8+8]
0x18004dd7f  ja      short loc_18004DD8D
0x18004dd81  cmp     qword ptr [r8+10h], 0
0x18004dd86  jnz     short loc_18004DDBB
0x18004dd88  test    rax, rax
0x18004dd8b  jz      short loc_18004DDBB
0x18004dd8d  lea     rax, aOnecoreBaseXml_0; "onecore\\base\\xml\\udom_microdom.cpp"
0x18004dd94  mov     [rbp+57h+var_60], 0CAAh
0x18004dd9b  mov     [rbp+57h+var_70], rax
0x18004dd9f  lea     rcx, [rbp+57h+var_70]
0x18004dda3  lea     rax, aMicrodomimplem_33; "MicrodomImplementation::CMicrodom_IRtlM"...
0x18004ddaa  mov     [rbp+57h+var_68], rax
0x18004ddae  lea     rax, aRtlislutf8stri_11; "RtlIsLUtf8StringValid(LocalName) || (Lo"...
0x18004ddb5  mov     [rbp+57h+var_58], rax
0x18004ddb9  jmp     short loc_18004DDEC
0x18004ddbb  test    rdi, rdi
0x18004ddbe  jnz     short loc_18004DDFE
0x18004ddc0  lea     rax, aOnecoreBaseXml_0; "onecore\\base\\xml\\udom_microdom.cpp"
0x18004ddc7  mov     [rbp+57h+var_40], 0CABh
0x18004ddce  mov     [rbp+57h+var_50], rax
0x18004ddd2  lea     rcx, [rbp+57h+var_50]
0x18004ddd6  lea     rax, aMicrodomimplem_33; "MicrodomImplementation::CMicrodom_IRtlM"...
0x18004dddd  mov     [rbp+57h+var_48], rax
0x18004dde1  lea     rax, aNotNullCheckFa_36; "Not-null check failed: NodeList"
0x18004dde8  mov     [rbp+57h+var_38], rax
0x18004ddec  mov     r8d, 0C000000Dh
0x18004ddf2  call    RtlReportErrorOrigination
0x18004ddf7  mov     ebx, 0C000000Dh
0x18004ddfc  jmp     short loc_18004DE3F
0x18004ddfe  mov     rcx, [rcx-8]; this
0x18004de02  lea     rax, [rbp+57h+P]
0x18004de06  mov     r9b, 1
0x18004de09  mov     [rsp+0C0h+var_A0], rax; __int64
0x18004de0e  call    ?GetElementsByTagName@CMicrodom@MicrodomImplementation@@QEAAJPEBU_LUTF8_STRING@@0_NPEAV?$Auto@U?$Vector@UElement@Rtl@Microdom@Windows@@@Windows@@@Windows@@@Z; MicrodomImplementation::CMicrodom::GetElementsByTagName(_LUTF8_STRING const *,_LUTF8_STRING const *,bool,Windows::Auto<Windows::Vector<Windows::Microdom::Rtl::Element>> *)
0x18004de13  mov     ebx, eax
0x18004de15  test    eax, eax
0x18004de17  jns     short loc_18004DE43
0x18004de19  cmp     [rbp+57h+P], 0
0x18004de1e  jz      short loc_18004DE3F
0x18004de20  mov     rcx, gs:60h
0x18004de29  xor     edx, edx; Flags
0x18004de2b  mov     r8, [rbp+57h+P]; P
0x18004de2f  mov     rcx, [rcx+30h]; HeapHandle
0x18004de33  call    cs:__imp_RtlFreeHeap
0x18004de3a  nop     dword ptr [rax+rax+00h]
0x18004de3f  mov     eax, ebx
0x18004de41  jmp     short loc_18004DE7D
0x18004de43  movups  xmm1, xmmword ptr [rdi]
0x18004de46  movaps  xmm0, xmmword ptr [rbp+57h+P]
0x18004de4a  movq    rax, xmm1
0x18004de4f  movaps  xmmword ptr [rbp+57h+P], xmm1
0x18004de53  movdqu  xmmword ptr [rdi], xmm0
0x18004de57  test    rax, rax
0x18004de5a  jz      short loc_18004DE7B
0x18004de5c  mov     rcx, gs:60h
0x18004de65  xor     edx, edx; Flags
0x18004de67  mov     r8, [rbp+57h+P]; P
0x18004de6b  mov     rcx, [rcx+30h]; HeapHandle
0x18004de6f  call    cs:__imp_RtlFreeHeap
0x18004de76  nop     dword ptr [rax+rax+00h]
0x18004de7b  xor     eax, eax
0x18004de7d  mov     rcx, [rbp+57h+var_20]
0x18004de81  xor     rcx, rsp; StackCookie
0x18004de84  call    __security_check_cookie
0x18004de89  add     rsp, 0B0h
0x18004de90  pop     rdi
0x18004de91  pop     rbx
0x18004de92  pop     rbp
0x18004de93  retn
```
