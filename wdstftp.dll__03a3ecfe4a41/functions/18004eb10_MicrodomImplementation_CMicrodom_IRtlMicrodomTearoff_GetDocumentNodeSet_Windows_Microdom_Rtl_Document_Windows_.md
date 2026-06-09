# MicrodomImplementation::CMicrodom_IRtlMicrodomTearoff::GetDocumentNodeSet(Windows::Microdom::Rtl::Document,Windows::Auto<Windows::Vector<Windows::Microdom::Rtl::Node>> *)

- ea: `0x18004eb10`
- end: `0x18004ecf2`
- name: `?GetDocumentNodeSet@CMicrodom_IRtlMicrodomTearoff@MicrodomImplementation@@UEAAJUDocument@Rtl@Microdom@Windows@@PEAV?$Auto@U?$Vector@UNode@Rtl@Microdom@Windows@@@Windows@@@6@@Z`
- size: `482`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800370f4`
- `0x18004eb10`
- `0x180050a2c`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18004ec1a`
- `ntdll!RtlFreeHeap` at `0x18004ec93`
- `ntdll!RtlFreeHeap` at `0x18004eccd`
- `ntdll!RtlFreeHeap` at `0x18004ec1a`
- `ntdll!RtlFreeHeap` at `0x18004ec93`
- `ntdll!RtlFreeHeap` at `0x18004eccd`

## string_xrefs

- `0x18004eb3a`: `onecore\base\xml\udom_microdom.cpp`
- `0x18004eb80`: `onecore\base\xml\udom_microdom.cpp`
- `0x18004ebc9`: `onecore\base\xml\udom_microdom.cpp`
- `0x18004ebf0`: `TempNodes.Allocate(this->m_LayoutCache.TotalObjectCount())`
- `0x18004eb5b`: `whichDoc.Reserved == m_pTargetObject->m_LayoutCache.DocumentId()`

## pseudocode

```c
__int64 __fastcall MicrodomImplementation::CMicrodom_IRtlMicrodomTearoff::GetDocumentNodeSet(
        __int64 a1,
        __int64 a2,
        _OWORD *a3)
{
  __int64 v3; // rdi
  _QWORD *v5; // rcx
  __int64 v7; // rdx
  int v8; // ebx
  unsigned __int64 v9; // rdx
  PVOID v10; // r9
  _DWORD *v11; // r8
  __int128 v12; // xmm0
  PVOID v13; // rax
  PVOID P[2]; // [rsp+20h] [rbp-19h] BYREF
  _QWORD v15[2]; // [rsp+30h] [rbp-9h] BYREF
  int v16; // [rsp+40h] [rbp+7h]
  const char *v17; // [rsp+48h] [rbp+Fh]
  _QWORD v18[2]; // [rsp+50h] [rbp+17h] BYREF
  int v19; // [rsp+60h] [rbp+27h]
  const char *v20; // [rsp+68h] [rbp+2Fh]
  _QWORD v21[2]; // [rsp+70h] [rbp+37h] BYREF
  int v22; // [rsp+80h] [rbp+47h]
  const char *v23; // [rsp+88h] [rbp+4Fh]

  v3 = *(_QWORD *)(a1 - 8);
  if ( *(_DWORD *)(a2 + 8) != *(_DWORD *)(*(_QWORD *)(v3 + 96) + 16LL) )
  {
    v16 = 3486;
    v15[0] = "onecore\\base\\xml\\udom_microdom.cpp";
    v5 = v15;
    v15[1] = "MicrodomImplementation::CMicrodom_IRtlMicrodomTearoff::GetDocumentNodeSet";
    v17 = "whichDoc.Reserved == m_pTargetObject->m_LayoutCache.DocumentId()";
LABEL_3:
    RtlReportErrorOrigination(v5, a2, 3221225485LL);
    return 3221225485LL;
  }
  if ( !a3 )
  {
    v19 = 3487;
    v18[0] = "onecore\\base\\xml\\udom_microdom.cpp";
    v5 = v18;
    v18[1] = "MicrodomImplementation::CMicrodom_IRtlMicrodomTearoff::GetDocumentNodeSet";
    v20 = "Not-null check failed: NodeSet";
    goto LABEL_3;
  }
  P[0] = 0;
  P[1] = 0;
  if ( !Windows::AutoVectorBase<Windows::Microdom::MicrodomVectorTraits<Windows::Microdom::Rtl::Element>,Windows::Auto<Windows::Vector<Windows::Microdom::Rtl::Element>>>::Allocate(P) )
  {
    v22 = 1074;
    v21[0] = "onecore\\base\\xml\\udom_microdom.cpp";
    v21[1] = "MicrodomImplementation::CMicrodom::GetDocumentNodeSet";
    v23 = "TempNodes.Allocate(this->m_LayoutCache.TotalObjectCount())";
    RtlReportErrorOrigination(v21, v7, 3221225495LL);
    if ( P[0] )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P[0]);
    return (unsigned int)-1073741801;
  }
  v9 = 0;
  if ( *(_DWORD *)(*(_QWORD *)(v3 + 96) + 8LL) )
  {
    v10 = P[0];
    v11 = (char *)P[0] + 8;
    while ( v9 <= 0xFFFFFFFF )
    {
      *v11 = v9;
      if ( v9 != (unsigned int)v9 )
      {
        v8 = -1073741595;
        goto LABEL_22;
      }
      ++v9;
      v11 += 4;
      if ( v9 == *(_DWORD *)(*(_QWORD *)(v3 + 96) + 8LL) )
        goto LABEL_15;
    }
    v8 = -1073741675;
LABEL_22:
    if ( v10 )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P[0]);
  }
  else
  {
LABEL_15:
    v12 = *(_OWORD *)P;
    *(_OWORD *)P = *a3;
    v13 = P[0];
    *a3 = v12;
    if ( v13 )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P[0]);
    v8 = 0;
  }
  if ( v8 < 0 )
    return (unsigned int)v8;
  return 0;
}

```

## disassembly

```asm
0x18004eb10  mov     [rsp-8+arg_8], rbx
0x18004eb15  mov     [rsp-8+arg_18], rdi
0x18004eb1a  push    rbp
0x18004eb1b  lea     rbp, [rsp-57h]
0x18004eb20  sub     rsp, 90h
0x18004eb27  mov     rdi, [rcx-8]
0x18004eb2b  mov     rbx, r8
0x18004eb2e  mov     rcx, [rdi+60h]
0x18004eb32  mov     eax, [rcx+10h]
0x18004eb35  cmp     [rdx+8], eax
0x18004eb38  jz      short loc_18004EB7B
0x18004eb3a  lea     rax, aOnecoreBaseXml_0; "onecore\\base\\xml\\udom_microdom.cpp"
0x18004eb41  mov     [rbp+57h+var_50], 0D9Eh
0x18004eb48  mov     [rbp+57h+var_60], rax
0x18004eb4c  lea     rcx, [rbp+57h+var_60]
0x18004eb50  lea     rax, aMicrodomimplem_38; "MicrodomImplementation::CMicrodom_IRtlM"...
0x18004eb57  mov     [rbp+57h+var_58], rax
0x18004eb5b  lea     rax, aWhichdocReserv; "whichDoc.Reserved == m_pTargetObject->m"...
0x18004eb62  mov     [rbp+57h+var_48], rax
0x18004eb66  mov     r8d, 0C000000Dh
0x18004eb6c  call    RtlReportErrorOrigination
0x18004eb71  mov     eax, 0C000000Dh
0x18004eb76  jmp     loc_18004ECDD
0x18004eb7b  test    rbx, rbx
0x18004eb7e  jnz     short loc_18004EBAE
0x18004eb80  lea     rax, aOnecoreBaseXml_0; "onecore\\base\\xml\\udom_microdom.cpp"
0x18004eb87  mov     [rbp+57h+var_30], 0D9Fh
0x18004eb8e  mov     [rbp+57h+var_40], rax
0x18004eb92  lea     rcx, [rbp+57h+var_40]
0x18004eb96  lea     rax, aMicrodomimplem_38; "MicrodomImplementation::CMicrodom_IRtlM"...
0x18004eb9d  mov     [rbp+57h+var_38], rax
0x18004eba1  lea     rax, aNotNullCheckFa_12; "Not-null check failed: NodeSet"
0x18004eba8  mov     [rbp+57h+var_28], rax
0x18004ebac  jmp     short loc_18004EB66
0x18004ebae  mov     edx, [rcx+8]
0x18004ebb1  lea     rcx, [rbp+57h+P]
0x18004ebb5  and     [rbp+57h+P], 0
0x18004ebba  and     [rbp+57h+P+8], 0
0x18004ebbf  call    ?Allocate@?$AutoVectorBase@V?$MicrodomVectorTraits@UElement@Rtl@Microdom@Windows@@@Microdom@Windows@@V?$Auto@U?$Vector@UElement@Rtl@Microdom@Windows@@@Windows@@@3@@Windows@@QEAAPEAUElement@Rtl@Microdom@2@_K@Z; Windows::AutoVectorBase<Windows::Microdom::MicrodomVectorTraits<Windows::Microdom::Rtl::Element>,Windows::Auto<Windows::Vector<Windows::Microdom::Rtl::Element>>>::Allocate(unsigned __int64)
0x18004ebc4  test    rax, rax
0x18004ebc7  jnz     short loc_18004EC2D
0x18004ebc9  lea     rax, aOnecoreBaseXml_0; "onecore\\base\\xml\\udom_microdom.cpp"
0x18004ebd0  mov     [rbp+57h+var_10], 432h
0x18004ebd7  mov     [rbp+57h+var_20], rax
0x18004ebdb  lea     rcx, [rbp+57h+var_20]
0x18004ebdf  lea     rax, aMicrodomimplem_8; "MicrodomImplementation::CMicrodom::GetD"...
0x18004ebe6  mov     r8d, 0C0000017h
0x18004ebec  mov     [rbp+57h+var_18], rax
0x18004ebf0  lea     rax, aTempnodesAlloc_0; "TempNodes.Allocate(this->m_LayoutCache."...
0x18004ebf7  mov     [rbp+57h+var_8], rax
0x18004ebfb  call    RtlReportErrorOrigination
0x18004ec00  cmp     [rbp+57h+P], 0
0x18004ec05  jz      short loc_18004EC26
0x18004ec07  mov     rcx, gs:60h
0x18004ec10  xor     edx, edx; Flags
0x18004ec12  mov     r8, [rbp+57h+P]; P
0x18004ec16  mov     rcx, [rcx+30h]; HeapHandle
0x18004ec1a  call    cs:__imp_RtlFreeHeap
0x18004ec21  nop     dword ptr [rax+rax+00h]
0x18004ec26  mov     ebx, 0C0000017h
0x18004ec2b  jmp     short loc_18004ECA5
0x18004ec2d  mov     rax, [rdi+60h]
0x18004ec31  xor     edx, edx
0x18004ec33  cmp     [rax+8], edx
0x18004ec36  jz      short loc_18004EC67
0x18004ec38  mov     r9, [rbp+57h+P]
0x18004ec3c  lea     r8, [r9+8]
0x18004ec40  mov     eax, 0FFFFFFFFh
0x18004ec45  cmp     rdx, rax
0x18004ec48  ja      short loc_18004ECB0
0x18004ec4a  mov     eax, edx
0x18004ec4c  mov     [r8], eax
0x18004ec4f  cmp     rdx, rax
0x18004ec52  jnz     short loc_18004ECA9
0x18004ec54  mov     rax, [rdi+60h]
0x18004ec58  inc     rdx
0x18004ec5b  add     r8, 10h
0x18004ec5f  mov     ecx, [rax+8]
0x18004ec62  cmp     rdx, rcx
0x18004ec65  jnz     short loc_18004EC40
0x18004ec67  movups  xmm1, xmmword ptr [rbx]
0x18004ec6a  movaps  xmm0, xmmword ptr [rbp+57h+P]
0x18004ec6e  movq    rax, xmm1
0x18004ec73  movaps  xmmword ptr [rbp+57h+P], xmm1
0x18004ec77  movdqu  xmmword ptr [rbx], xmm0
0x18004ec7b  test    rax, rax
0x18004ec7e  jz      short loc_18004EC9F
0x18004ec80  mov     rcx, gs:60h
0x18004ec89  xor     edx, edx; Flags
0x18004ec8b  mov     r8, [rbp+57h+P]; P
0x18004ec8f  mov     rcx, [rcx+30h]; HeapHandle
0x18004ec93  call    cs:__imp_RtlFreeHeap
0x18004ec9a  nop     dword ptr [rax+rax+00h]
0x18004ec9f  xor     ebx, ebx
0x18004eca1  test    ebx, ebx
0x18004eca3  jns     short loc_18004ECDB
0x18004eca5  mov     eax, ebx
0x18004eca7  jmp     short loc_18004ECDD
0x18004eca9  mov     ebx, 0C00000E5h
0x18004ecae  jmp     short loc_18004ECB5
0x18004ecb0  mov     ebx, 0C0000095h
0x18004ecb5  test    r9, r9
0x18004ecb8  jz      short loc_18004ECA1
0x18004ecba  mov     rcx, gs:60h
0x18004ecc3  xor     edx, edx; Flags
0x18004ecc5  mov     r8, [rbp+57h+P]; P
0x18004ecc9  mov     rcx, [rcx+30h]; HeapHandle
0x18004eccd  call    cs:__imp_RtlFreeHeap
0x18004ecd4  nop     dword ptr [rax+rax+00h]
0x18004ecd9  jmp     short loc_18004ECA1
0x18004ecdb  xor     eax, eax
0x18004ecdd  lea     r11, [rsp+90h+var_s0]
0x18004ece5  mov     rbx, [r11+18h]
0x18004ece9  mov     rdi, [r11+28h]
0x18004eced  mov     rsp, r11
0x18004ecf0  pop     rbp
0x18004ecf1  retn
```
