# MicrodomImplementation::CMicrodom_IRtlMicrodomTearoff::GetElementsByTagName(_LUTF8_STRING const *,Windows::Auto<Windows::Vector<Windows::Microdom::Rtl::Element>> *)

- ea: `0x18004dba0`
- end: `0x18004dcf1`
- name: `?GetElementsByTagName@CMicrodom_IRtlMicrodomTearoff@MicrodomImplementation@@UEAAJPEBU_LUTF8_STRING@@PEAV?$Auto@U?$Vector@UElement@Rtl@Microdom@Windows@@@Windows@@@Windows@@@Z`
- size: `337`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800370f4`
- `0x18004bb10`
- `0x18004dba0`
- `0x1800607b0`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18004dc90`
- `ntdll!RtlFreeHeap` at `0x18004dccc`
- `ntdll!RtlFreeHeap` at `0x18004dc90`
- `ntdll!RtlFreeHeap` at `0x18004dccc`

## string_xrefs

- `0x18004dbe5`: `onecore\base\xml\udom_microdom.cpp`
- `0x18004dc18`: `onecore\base\xml\udom_microdom.cpp`

## pseudocode

```c
__int64 __fastcall MicrodomImplementation::CMicrodom_IRtlMicrodomTearoff::GetElementsByTagName(
        __int64 a1,
        __int64 a2,
        _OWORD *a3)
{
  _QWORD *v4; // rcx
  int ElementsByTagName; // ebx
  __int128 v7; // xmm0
  PVOID v8; // rax
  _QWORD v9[2]; // [rsp+30h] [rbp-19h] BYREF
  int v10; // [rsp+40h] [rbp-9h]
  const char *v11; // [rsp+48h] [rbp-1h]
  _QWORD v12[2]; // [rsp+50h] [rbp+7h] BYREF
  int v13; // [rsp+60h] [rbp+17h]
  const char *v14; // [rsp+68h] [rbp+1Fh]
  PVOID P[2]; // [rsp+70h] [rbp+27h] BYREF

  P[0] = 0;
  P[1] = 0;
  if ( a2 && (*(_QWORD *)a2 > *(_QWORD *)(a2 + 8) || !*(_QWORD *)(a2 + 16) && *(_QWORD *)a2) )
  {
    v10 = 3222;
    v9[0] = "onecore\\base\\xml\\udom_microdom.cpp";
    v4 = v9;
    v9[1] = "MicrodomImplementation::CMicrodom_IRtlMicrodomTearoff::GetElementsByTagName";
    v11 = "RtlIsLUtf8StringValid(TagName) || (TagName == 0)";
LABEL_8:
    RtlReportErrorOrigination(v4, a2, 3221225485LL);
    return (unsigned int)-1073741811;
  }
  if ( !a3 )
  {
    v13 = 3223;
    v12[0] = "onecore\\base\\xml\\udom_microdom.cpp";
    v4 = v12;
    v12[1] = "MicrodomImplementation::CMicrodom_IRtlMicrodomTearoff::GetElementsByTagName";
    v14 = "Not-null check failed: NodeList";
    goto LABEL_8;
  }
  ElementsByTagName = MicrodomImplementation::CMicrodom::GetElementsByTagName(
                        *(MicrodomImplementation::CMicrodom **)(a1 - 8),
                        0,
                        (struct _LUTF8_STRING *)a2,
                        0,
                        (__int128 *)P);
  if ( ElementsByTagName < 0 )
  {
    if ( P[0] )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P[0]);
    return (unsigned int)ElementsByTagName;
  }
  v7 = *(_OWORD *)P;
  *(_OWORD *)P = *a3;
  v8 = P[0];
  *a3 = v7;
  if ( v8 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P[0]);
  return 0;
}

```

## disassembly

```asm
0x18004dba0  push    rbp
0x18004dba2  push    rbx
0x18004dba3  push    rdi
0x18004dba4  lea     rbp, [rsp-47h]
0x18004dba9  sub     rsp, 90h
0x18004dbb0  mov     rax, cs:__security_cookie
0x18004dbb7  xor     rax, rsp
0x18004dbba  mov     [rbp+57h+var_20], rax
0x18004dbbe  and     [rbp+57h+P], 0
0x18004dbc3  mov     rdi, r8
0x18004dbc6  and     [rbp+57h+P+8], 0
0x18004dbcb  test    rdx, rdx
0x18004dbce  jz      short loc_18004DC13
0x18004dbd0  mov     rax, [rdx]
0x18004dbd3  cmp     rax, [rdx+8]
0x18004dbd7  ja      short loc_18004DBE5
0x18004dbd9  cmp     qword ptr [rdx+10h], 0
0x18004dbde  jnz     short loc_18004DC13
0x18004dbe0  test    rax, rax
0x18004dbe3  jz      short loc_18004DC13
0x18004dbe5  lea     rax, aOnecoreBaseXml_0; "onecore\\base\\xml\\udom_microdom.cpp"
0x18004dbec  mov     [rbp+57h+var_60], 0C96h
0x18004dbf3  mov     [rbp+57h+var_70], rax
0x18004dbf7  lea     rcx, [rbp+57h+var_70]
0x18004dbfb  lea     rax, aMicrodomimplem_26; "MicrodomImplementation::CMicrodom_IRtlM"...
0x18004dc02  mov     [rbp+57h+var_68], rax
0x18004dc06  lea     rax, aRtlislutf8stri_6; "RtlIsLUtf8StringValid(TagName) || (TagN"...
0x18004dc0d  mov     [rbp+57h+var_58], rax
0x18004dc11  jmp     short loc_18004DC44
0x18004dc13  test    rdi, rdi
0x18004dc16  jnz     short loc_18004DC56
0x18004dc18  lea     rax, aOnecoreBaseXml_0; "onecore\\base\\xml\\udom_microdom.cpp"
0x18004dc1f  mov     [rbp+57h+var_40], 0C97h
0x18004dc26  mov     [rbp+57h+var_50], rax
0x18004dc2a  lea     rcx, [rbp+57h+var_50]
0x18004dc2e  lea     rax, aMicrodomimplem_26; "MicrodomImplementation::CMicrodom_IRtlM"...
0x18004dc35  mov     [rbp+57h+var_48], rax
0x18004dc39  lea     rax, aNotNullCheckFa_36; "Not-null check failed: NodeList"
0x18004dc40  mov     [rbp+57h+var_38], rax
0x18004dc44  mov     r8d, 0C000000Dh
0x18004dc4a  call    RtlReportErrorOrigination
0x18004dc4f  mov     ebx, 0C000000Dh
0x18004dc54  jmp     short loc_18004DC9C
0x18004dc56  mov     rcx, [rcx-8]; this
0x18004dc5a  lea     rax, [rbp+57h+P]
0x18004dc5e  mov     r8, rdx
0x18004dc61  mov     [rsp+0A0h+var_80], rax; __int64
0x18004dc66  xor     edx, edx
0x18004dc68  xor     r9d, r9d
0x18004dc6b  call    ?GetElementsByTagName@CMicrodom@MicrodomImplementation@@QEAAJPEBU_LUTF8_STRING@@0_NPEAV?$Auto@U?$Vector@UElement@Rtl@Microdom@Windows@@@Windows@@@Windows@@@Z; MicrodomImplementation::CMicrodom::GetElementsByTagName(_LUTF8_STRING const *,_LUTF8_STRING const *,bool,Windows::Auto<Windows::Vector<Windows::Microdom::Rtl::Element>> *)
0x18004dc70  mov     ebx, eax
0x18004dc72  test    eax, eax
0x18004dc74  jns     short loc_18004DCA0
0x18004dc76  cmp     [rbp+57h+P], 0
0x18004dc7b  jz      short loc_18004DC9C
0x18004dc7d  mov     rcx, gs:60h
0x18004dc86  xor     edx, edx; Flags
0x18004dc88  mov     r8, [rbp+57h+P]; P
0x18004dc8c  mov     rcx, [rcx+30h]; HeapHandle
0x18004dc90  call    cs:__imp_RtlFreeHeap
0x18004dc97  nop     dword ptr [rax+rax+00h]
0x18004dc9c  mov     eax, ebx
0x18004dc9e  jmp     short loc_18004DCDA
0x18004dca0  movups  xmm1, xmmword ptr [rdi]
0x18004dca3  movaps  xmm0, xmmword ptr [rbp+57h+P]
0x18004dca7  movq    rax, xmm1
0x18004dcac  movaps  xmmword ptr [rbp+57h+P], xmm1
0x18004dcb0  movdqu  xmmword ptr [rdi], xmm0
0x18004dcb4  test    rax, rax
0x18004dcb7  jz      short loc_18004DCD8
0x18004dcb9  mov     rcx, gs:60h
0x18004dcc2  xor     edx, edx; Flags
0x18004dcc4  mov     r8, [rbp+57h+P]; P
0x18004dcc8  mov     rcx, [rcx+30h]; HeapHandle
0x18004dccc  call    cs:__imp_RtlFreeHeap
0x18004dcd3  nop     dword ptr [rax+rax+00h]
0x18004dcd8  xor     eax, eax
0x18004dcda  mov     rcx, [rbp+57h+var_20]
0x18004dcde  xor     rcx, rsp; StackCookie
0x18004dce1  call    __security_check_cookie
0x18004dce6  add     rsp, 90h
0x18004dced  pop     rdi
0x18004dcee  pop     rbx
0x18004dcef  pop     rbp
0x18004dcf0  retn
```
