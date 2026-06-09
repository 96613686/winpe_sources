# MicrodomImplementation::CMicrodom_IRtlMicrodomTearoff::GetElementsByTagName(Windows::Microdom::Rtl::Element,_LUTF8_STRING const *,Windows::Auto<Windows::Vector<Windows::Microdom::Rtl::Element>> *)

- ea: `0x18004e410`
- end: `0x18004e5b0`
- name: `?GetElementsByTagName@CMicrodom_IRtlMicrodomTearoff@MicrodomImplementation@@UEAAJUElement@Rtl@Microdom@Windows@@PEBU_LUTF8_STRING@@PEAV?$Auto@U?$Vector@UElement@Rtl@Microdom@Windows@@@Windows@@@6@@Z`
- size: `416`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800370f4`
- `0x18004b784`
- `0x18004e410`
- `0x1800607b0`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18004e511`
- `ntdll!RtlFreeHeap` at `0x18004e54b`
- `ntdll!RtlFreeHeap` at `0x18004e511`
- `ntdll!RtlFreeHeap` at `0x18004e54b`

## string_xrefs

- `0x18004e443`: `onecore\base\xml\udom_microdom.cpp`
- `0x18004e49f`: `onecore\base\xml\udom_microdom.cpp`
- `0x18004e55b`: `onecore\base\xml\udom_microdom.cpp`

## pseudocode

```c
__int64 __fastcall MicrodomImplementation::CMicrodom_IRtlMicrodomTearoff::GetElementsByTagName(
        __int64 a1,
        __int64 a2,
        _QWORD *a3,
        _OWORD *a4)
{
  __int64 v5; // rdx
  _QWORD *v6; // rcx
  int ElementsByTagName; // ebx
  __int128 v8; // xmm0
  PVOID v9; // rax
  _QWORD v11[2]; // [rsp+30h] [rbp-39h] BYREF
  int v12; // [rsp+40h] [rbp-29h]
  const char *v13; // [rsp+48h] [rbp-21h]
  _QWORD v14[2]; // [rsp+50h] [rbp-19h] BYREF
  int v15; // [rsp+60h] [rbp-9h]
  const char *v16; // [rsp+68h] [rbp-1h]
  _QWORD v17[2]; // [rsp+70h] [rbp+7h] BYREF
  int v18; // [rsp+80h] [rbp+17h]
  const char *v19; // [rsp+88h] [rbp+1Fh]
  PVOID P[2]; // [rsp+90h] [rbp+27h] BYREF

  P[0] = 0;
  P[1] = 0;
  v5 = *(unsigned int *)(a2 + 8);
  if ( (_DWORD)v5 == -1 )
  {
    v12 = 3372;
    v11[0] = "onecore\\base\\xml\\udom_microdom.cpp";
    v6 = v11;
    v11[1] = "MicrodomImplementation::CMicrodom_IRtlMicrodomTearoff::GetElementsByTagName";
    v13 = "TheElement != TheElement.InvalidValue()";
LABEL_16:
    RtlReportErrorOrigination(v6, v5, 3221225485LL);
    return (unsigned int)-1073741811;
  }
  if ( !a3 || *a3 > a3[1] || !a3[2] && *a3 )
  {
    v18 = 3373;
    v17[0] = "onecore\\base\\xml\\udom_microdom.cpp";
    v6 = v17;
    v17[1] = "MicrodomImplementation::CMicrodom_IRtlMicrodomTearoff::GetElementsByTagName";
    v19 = "RtlIsLUtf8StringValid(Name)";
    goto LABEL_16;
  }
  if ( !a4 )
  {
    v15 = 3374;
    v14[0] = "onecore\\base\\xml\\udom_microdom.cpp";
    v6 = v14;
    v14[1] = "MicrodomImplementation::CMicrodom_IRtlMicrodomTearoff::GetElementsByTagName";
    v16 = "Not-null check failed: Matches";
    goto LABEL_16;
  }
  ElementsByTagName = MicrodomImplementation::CMicrodom::GetElementsByTagName(
                        *(_QWORD *)(a1 - 8),
                        v5,
                        0,
                        (_DWORD)a3,
                        0,
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
0x18004e410  push    rbp
0x18004e412  push    rbx
0x18004e413  push    rdi
0x18004e414  lea     rbp, [rsp-47h]
0x18004e419  sub     rsp, 0B0h
0x18004e420  mov     rax, cs:__security_cookie
0x18004e427  xor     rax, rsp
0x18004e42a  mov     [rbp+57h+var_20], rax
0x18004e42e  and     [rbp+57h+P], 0
0x18004e433  mov     rdi, r9
0x18004e436  and     [rbp+57h+P+8], 0
0x18004e43b  mov     edx, [rdx+8]
0x18004e43e  cmp     edx, 0FFFFFFFFh
0x18004e441  jnz     short loc_18004E474
0x18004e443  lea     rax, aOnecoreBaseXml_0; "onecore\\base\\xml\\udom_microdom.cpp"
0x18004e44a  mov     [rbp+57h+var_80], 0D2Ch
0x18004e451  mov     [rbp+57h+var_90], rax
0x18004e455  lea     rcx, [rbp+57h+var_90]
0x18004e459  lea     rax, aMicrodomimplem_26; "MicrodomImplementation::CMicrodom_IRtlM"...
0x18004e460  mov     [rbp+57h+var_88], rax
0x18004e464  lea     rax, aTheelementThee; "TheElement != TheElement.InvalidValue()"
0x18004e46b  mov     [rbp+57h+var_78], rax
0x18004e46f  jmp     loc_18004E587
0x18004e474  test    r8, r8
0x18004e477  jz      loc_18004E55B
0x18004e47d  mov     rax, [r8]
0x18004e480  cmp     rax, [r8+8]
0x18004e484  ja      loc_18004E55B
0x18004e48a  cmp     qword ptr [r8+10h], 0
0x18004e48f  jnz     short loc_18004E49A
0x18004e491  test    rax, rax
0x18004e494  jnz     loc_18004E55B
0x18004e49a  test    rdi, rdi
0x18004e49d  jnz     short loc_18004E4D0
0x18004e49f  lea     rax, aOnecoreBaseXml_0; "onecore\\base\\xml\\udom_microdom.cpp"
0x18004e4a6  mov     [rbp+57h+var_60], 0D2Eh
0x18004e4ad  mov     [rbp+57h+var_70], rax
0x18004e4b1  lea     rcx, [rbp+57h+var_70]
0x18004e4b5  lea     rax, aMicrodomimplem_26; "MicrodomImplementation::CMicrodom_IRtlM"...
0x18004e4bc  mov     [rbp+57h+var_68], rax
0x18004e4c0  lea     rax, aNotNullCheckFa_34; "Not-null check failed: Matches"
0x18004e4c7  mov     [rbp+57h+var_58], rax
0x18004e4cb  jmp     loc_18004E587
0x18004e4d0  mov     rcx, [rcx-8]
0x18004e4d4  lea     rax, [rbp+57h+P]
0x18004e4d8  mov     r9, r8
0x18004e4db  mov     [rsp+0C0h+var_98], rax
0x18004e4e0  xor     r8d, r8d
0x18004e4e3  mov     [rsp+0C0h+var_A0], 0
0x18004e4e8  call    ?GetElementsByTagName@CMicrodom@MicrodomImplementation@@QEAAJKPEBU_LUTF8_STRING@@0_NPEAV?$Auto@U?$Vector@UElement@Rtl@Microdom@Windows@@@Windows@@@Windows@@@Z; MicrodomImplementation::CMicrodom::GetElementsByTagName(ulong,_LUTF8_STRING const *,_LUTF8_STRING const *,bool,Windows::Auto<Windows::Vector<Windows::Microdom::Rtl::Element>> *)
0x18004e4ed  mov     ebx, eax
0x18004e4ef  test    eax, eax
0x18004e4f1  jns     short loc_18004E51F
0x18004e4f3  cmp     [rbp+57h+P], 0
0x18004e4f8  jz      loc_18004E597
0x18004e4fe  mov     rcx, gs:60h
0x18004e507  xor     edx, edx; Flags
0x18004e509  mov     r8, [rbp+57h+P]; P
0x18004e50d  mov     rcx, [rcx+30h]; HeapHandle
0x18004e511  call    cs:__imp_RtlFreeHeap
0x18004e518  nop     dword ptr [rax+rax+00h]
0x18004e51d  jmp     short loc_18004E597
0x18004e51f  movups  xmm1, xmmword ptr [rdi]
0x18004e522  movaps  xmm0, xmmword ptr [rbp+57h+P]
0x18004e526  movq    rax, xmm1
0x18004e52b  movaps  xmmword ptr [rbp+57h+P], xmm1
0x18004e52f  movdqu  xmmword ptr [rdi], xmm0
0x18004e533  test    rax, rax
0x18004e536  jz      short loc_18004E557
0x18004e538  mov     rcx, gs:60h
0x18004e541  xor     edx, edx; Flags
0x18004e543  mov     r8, [rbp+57h+P]; P
0x18004e547  mov     rcx, [rcx+30h]; HeapHandle
0x18004e54b  call    cs:__imp_RtlFreeHeap
0x18004e552  nop     dword ptr [rax+rax+00h]
0x18004e557  xor     eax, eax
0x18004e559  jmp     short loc_18004E599
0x18004e55b  lea     rax, aOnecoreBaseXml_0; "onecore\\base\\xml\\udom_microdom.cpp"
0x18004e562  mov     [rbp+57h+var_40], 0D2Dh
0x18004e569  mov     [rbp+57h+var_50], rax
0x18004e56d  lea     rcx, [rbp+57h+var_50]
0x18004e571  lea     rax, aMicrodomimplem_26; "MicrodomImplementation::CMicrodom_IRtlM"...
0x18004e578  mov     [rbp+57h+var_48], rax
0x18004e57c  lea     rax, aRtlislutf8stri_10; "RtlIsLUtf8StringValid(Name)"
0x18004e583  mov     [rbp+57h+var_38], rax
0x18004e587  mov     r8d, 0C000000Dh
0x18004e58d  call    RtlReportErrorOrigination
0x18004e592  mov     ebx, 0C000000Dh
0x18004e597  mov     eax, ebx
0x18004e599  mov     rcx, [rbp+57h+var_20]
0x18004e59d  xor     rcx, rsp; StackCookie
0x18004e5a0  call    __security_check_cookie
0x18004e5a5  add     rsp, 0B0h
0x18004e5ac  pop     rdi
0x18004e5ad  pop     rbx
0x18004e5ae  pop     rbp
0x18004e5af  retn
```
