# MicrodomImplementation::CMicrodom::GetElementsByTagNameCommon(ulong,_LUTF8_STRING const *,_LUTF8_STRING const *,bool,bool,Windows::Auto<Windows::Vector<Windows::Microdom::Rtl::Element>> *,unsigned __int64 *)

- ea: `0x18004b450`
- end: `0x18004b77c`
- name: `?GetElementsByTagNameCommon@CMicrodom@MicrodomImplementation@@AEAAJKPEBU_LUTF8_STRING@@0_N1PEAV?$Auto@U?$Vector@UElement@Rtl@Microdom@Windows@@@Windows@@@Windows@@PEA_K@Z`
- size: `812`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18004b450`
- `0x18004b784`

## callees

- `0x1800370f4`
- `0x18004b3fc`
- `0x18004b450`
- `0x18004b884`
- `0x18004b9d4`
- `0x18004f514`
- `0x180050a2c`
- `0x1800607b0`
- `0x180060e42`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18004b609`
- `ntdll!RtlFreeHeap` at `0x18004b665`
- `ntdll!RtlFreeHeap` at `0x18004b609`
- `ntdll!RtlFreeHeap` at `0x18004b665`

## string_xrefs

- `0x18004b4e4`: `onecore\base\xml\udom_microdom.cpp`
- `0x18004b5ad`: `onecore\base\xml\udom_microdom.cpp`
- `0x18004b73e`: `onecore\base\xml\udom_microdom.cpp`
- `0x18004b5c3`: `MicrodomImplementation::CMicrodom::GetElementsByTagNameCommon`
- `0x18004b754`: `MicrodomImplementation::CMicrodom::GetElementsByTagNameCommon`
- `0x18004b5d4`: `TempElements.Allocate(NewCapacity)`

## pseudocode

```c
int __fastcall MicrodomImplementation::CMicrodom::GetElementsByTagNameCommon(
        __int64 a1,
        unsigned int a2,
        struct _LUTF8_STRING *a3,
        struct _LUTF8_STRING *a4,
        char a5,
        char a6,
        __int64 a7,
        unsigned __int64 *a8)
{
  int v8; // ebx
  int result; // eax
  __int64 v13; // rdx
  unsigned __int64 v14; // rax
  unsigned __int64 v15; // rdx
  __int64 v16; // rdx
  void *v17; // r8
  _QWORD *v18; // r14
  __int64 v19; // r12
  __int64 i; // r15
  bool v21[16]; // [rsp+40h] [rbp-C0h] BYREF
  PVOID P[2]; // [rsp+50h] [rbp-B0h] BYREF
  struct _MICRODOM_DOM_NODE_HEADER *v23; // [rsp+60h] [rbp-A0h] BYREF
  struct _LUTF8_STRING *v24; // [rsp+68h] [rbp-98h]
  _QWORD *v25; // [rsp+70h] [rbp-90h] BYREF
  struct _MICRODOM_DOM_NODE_HEADER *v26; // [rsp+78h] [rbp-88h] BYREF
  struct _LUTF8_STRING *v27; // [rsp+80h] [rbp-80h]
  _QWORD v28[2]; // [rsp+88h] [rbp-78h] BYREF
  int v29; // [rsp+98h] [rbp-68h]
  const char *v30; // [rsp+A0h] [rbp-60h]
  _QWORD v31[2]; // [rsp+A8h] [rbp-58h] BYREF
  int v32; // [rsp+B8h] [rbp-48h]
  const char *v33; // [rsp+C0h] [rbp-40h]
  _QWORD v34[2]; // [rsp+C8h] [rbp-38h] BYREF
  int v35; // [rsp+D8h] [rbp-28h]
  const char *v36; // [rsp+E0h] [rbp-20h]
  int v37; // [rsp+ECh] [rbp-14h]

  v8 = 0;
  v27 = a4;
  v24 = a3;
  v37 = 0;
  if ( !a4 )
    __debugbreak();
  if ( !a7 )
    __debugbreak();
  if ( !a8 )
    __debugbreak();
  if ( *a8 > *(_QWORD *)(a7 + 8) )
    __debugbreak();
  v23 = 0;
  result = MicrodomImplementation::CDomLayoutCache::FindObject(
             (MicrodomImplementation::CDomLayoutCache *)(a1 + 48),
             a2,
             &v23);
  if ( result >= 0 )
  {
    if ( (*(_BYTE *)v23 & 0xF) != 1 )
    {
      v29 = 2371;
      v28[0] = "onecore\\base\\xml\\udom_microdom.cpp";
      v28[1] = "MicrodomImplementation::CMicrodom::FindObject";
      v30 = "ObjectHeader->uElementType == ucObjectType";
      RtlReportErrorOrigination(v28, v13, 3221225508LL);
      return -1073741788;
    }
    if ( a6 )
    {
      if ( a5 )
        result = MicrodomImplementation::CMicrodom::CompareElementByTagNameNS(
                   (MicrodomImplementation::CMicrodom *)a1,
                   v23,
                   v24,
                   a4,
                   v21);
      else
        result = MicrodomImplementation::CMicrodom::CompareElementByTagName(
                   (MicrodomImplementation::CMicrodom *)a1,
                   v23,
                   a4,
                   v21);
      if ( result < 0 )
        return result;
      if ( v21[0] )
      {
        v14 = *a8;
        if ( *(_QWORD *)(a7 + 8) == *a8 )
        {
          P[0] = 0;
          v15 = v14 + 10;
          P[1] = 0;
          if ( v14 + 10 < v14 || v15 < 0xA )
          {
            v35 = 1826;
            v34[0] = "onecore\\base\\xml\\udom_microdom.cpp";
            v34[1] = "MicrodomImplementation::CMicrodom::GetElementsByTagNameCommon";
            v36 = "::BUCL::Rtl::Add<SIZE_T>( *pcElements, 10, NewCapacity)";
            RtlReportErrorOrigination(v34, v15, 3221225621LL);
            return -1073741675;
          }
          if ( !Windows::AutoVectorBase<Windows::Microdom::MicrodomVectorTraits<Windows::Microdom::Rtl::Element>,Windows::Auto<Windows::Vector<Windows::Microdom::Rtl::Element>>>::Allocate(P) )
          {
            v32 = 1828;
            v31[0] = "onecore\\base\\xml\\udom_microdom.cpp";
            v31[1] = "MicrodomImplementation::CMicrodom::GetElementsByTagNameCommon";
            v33 = "TempElements.Allocate(NewCapacity)";
            RtlReportErrorOrigination(v31, v16, 3221225495LL);
            v8 = -1073741801;
            if ( P[0] )
              RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P[0]);
            return v8;
          }
          memcpy_0(P[0], *(const void **)a7, 16 * *a8);
          v17 = *(void **)a7;
          *(_OWORD *)a7 = *(_OWORD *)P;
          if ( v17 )
          {
            RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v17);
            v8 = v37;
          }
        }
        if ( *a8 >= *(_QWORD *)(a7 + 8) )
          __debugbreak();
        *(_DWORD *)(*(_QWORD *)a7 + 16 * (*a8)++ + 8) = a2;
      }
    }
    result = MicrodomImplementation::CMicrodom::GetNodeChildren(a1, a2, &v25, 0);
    if ( result < 0 )
      return result;
    v18 = v25;
    v19 = 0;
    if ( !v25[1] )
      return v8;
    for ( i = 0; ; i += 16 )
    {
      result = MicrodomImplementation::CDomLayoutCache::FindObject(
                 (MicrodomImplementation::CDomLayoutCache *)(a1 + 48),
                 *(_DWORD *)(i + *v18 + 8),
                 &v26);
      if ( result < 0 )
        break;
      if ( (*(_BYTE *)v26 & 0xF) == 1 )
      {
        result = MicrodomImplementation::CMicrodom::GetElementsByTagNameCommon(
                   a1,
                   *(_DWORD *)(i + *v18 + 8),
                   (_DWORD)v24,
                   (_DWORD)v27,
                   a5,
                   1,
                   a7,
                   (__int64)a8);
        if ( result < 0 )
          break;
      }
      if ( (unsigned __int64)++v19 >= v18[1] )
        return v8;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18004b450  push    rbp
0x18004b452  push    rbx
0x18004b453  push    rsi
0x18004b454  push    rdi
0x18004b455  push    r12
0x18004b457  push    r13
0x18004b459  push    r14
0x18004b45b  push    r15
0x18004b45d  lea     rbp, [rsp-8]
0x18004b462  sub     rsp, 108h
0x18004b469  mov     rax, cs:__security_cookie
0x18004b470  xor     rax, rsp
0x18004b473  mov     [rbp+40h+var_50], rax
0x18004b477  mov     rsi, [rbp+40h+arg_30]
0x18004b47e  xor     ebx, ebx
0x18004b480  mov     rdi, [rbp+40h+arg_38]
0x18004b487  mov     r12, r9
0x18004b48a  mov     [rbp+40h+var_C0], r9
0x18004b48e  mov     r15d, edx
0x18004b491  mov     [rsp+140h+var_D8], r8
0x18004b496  mov     r13, rcx
0x18004b499  mov     [rbp+40h+var_54], ebx
0x18004b49c  test    r9, r9
0x18004b49f  jnz     short loc_18004B4A2
0x18004b4a1  int     3; Trap to Debugger
0x18004b4a2  test    rsi, rsi
0x18004b4a5  jnz     short loc_18004B4A8
0x18004b4a7  int     3; Trap to Debugger
0x18004b4a8  test    rdi, rdi
0x18004b4ab  jnz     short loc_18004B4AE
0x18004b4ad  int     3; Trap to Debugger
0x18004b4ae  mov     rax, [rsi+8]
0x18004b4b2  cmp     [rdi], rax
0x18004b4b5  jbe     short loc_18004B4B8
0x18004b4b7  int     3; Trap to Debugger
0x18004b4b8  and     [rsp+140h+var_E0], rbx
0x18004b4bd  lea     r8, [rsp+140h+var_E0]; struct _MICRODOM_DOM_NODE_HEADER **
0x18004b4c2  add     rcx, 30h ; '0'; this
0x18004b4c6  xor     r14d, r14d
0x18004b4c9  call    ?FindObject@CDomLayoutCache@MicrodomImplementation@@QEAAJKAEAPEBU_MICRODOM_DOM_NODE_HEADER@@@Z; MicrodomImplementation::CDomLayoutCache::FindObject(ulong,_MICRODOM_DOM_NODE_HEADER const * &)
0x18004b4ce  test    eax, eax
0x18004b4d0  js      loc_18004B71E
0x18004b4d6  mov     r14, [rsp+140h+var_E0]
0x18004b4db  mov     al, [r14]
0x18004b4de  and     al, 0Fh
0x18004b4e0  cmp     al, 1
0x18004b4e2  jz      short loc_18004B525
0x18004b4e4  lea     rax, aOnecoreBaseXml_0; "onecore\\base\\xml\\udom_microdom.cpp"
0x18004b4eb  mov     [rbp+40h+var_A8], 943h
0x18004b4f2  mov     [rbp+40h+var_B8], rax
0x18004b4f6  lea     rcx, [rbp+40h+var_B8]
0x18004b4fa  lea     rax, aMicrodomimplem_3; "MicrodomImplementation::CMicrodom::Find"...
0x18004b501  mov     r8d, 0C0000024h
0x18004b507  mov     [rbp+40h+var_B0], rax
0x18004b50b  lea     rax, aObjectheaderUe; "ObjectHeader->uElementType == ucObjectT"...
0x18004b512  mov     [rbp+40h+var_A0], rax
0x18004b516  call    RtlReportErrorOrigination
0x18004b51b  mov     eax, 0C0000024h
0x18004b520  jmp     loc_18004B71E
0x18004b525  xor     eax, eax
0x18004b527  test    eax, eax
0x18004b529  js      loc_18004B71E
0x18004b52f  cmp     [rbp+40h+arg_28], bl
0x18004b532  jz      loc_18004B68C
0x18004b538  mov     rdx, r14; struct _MICRODOM_DOM_NODE_ELEMENT *
0x18004b53b  mov     rcx, r13; this
0x18004b53e  cmp     [rbp+40h+arg_20], bl
0x18004b541  jz      loc_18004B61A
0x18004b547  mov     r8, [rsp+140h+var_D8]; struct _LUTF8_STRING *
0x18004b54c  lea     rax, [rsp+140h+var_100]
0x18004b551  mov     r9, r12; struct _LUTF8_STRING *
0x18004b554  mov     [rsp+140h+var_120], rax; bool *
0x18004b559  call    ?CompareElementByTagNameNS@CMicrodom@MicrodomImplementation@@AEAAJPEBU_MICRODOM_DOM_NODE_ELEMENT@@PEBU_LUTF8_STRING@@1PEA_N@Z; MicrodomImplementation::CMicrodom::CompareElementByTagNameNS(_MICRODOM_DOM_NODE_ELEMENT const *,_LUTF8_STRING const *,_LUTF8_STRING const *,bool *)
0x18004b55e  test    eax, eax
0x18004b560  js      loc_18004B71E
0x18004b566  cmp     [rsp+140h+var_100], bl
0x18004b56a  jz      loc_18004B68C
0x18004b570  mov     rax, [rdi]
0x18004b573  cmp     [rsi+8], rax
0x18004b577  jnz     loc_18004B674
0x18004b57d  and     [rsp+140h+P], rbx
0x18004b582  lea     rdx, [rax+0Ah]
0x18004b586  and     [rsp+140h+P+8], rbx
0x18004b58b  cmp     rdx, rax
0x18004b58e  jb      loc_18004B73E
0x18004b594  cmp     rdx, 0Ah
0x18004b598  jb      loc_18004B73E
0x18004b59e  lea     rcx, [rsp+140h+P]
0x18004b5a3  call    ?Allocate@?$AutoVectorBase@V?$MicrodomVectorTraits@UElement@Rtl@Microdom@Windows@@@Microdom@Windows@@V?$Auto@U?$Vector@UElement@Rtl@Microdom@Windows@@@Windows@@@3@@Windows@@QEAAPEAUElement@Rtl@Microdom@2@_K@Z; Windows::AutoVectorBase<Windows::Microdom::MicrodomVectorTraits<Windows::Microdom::Rtl::Element>,Windows::Auto<Windows::Vector<Windows::Microdom::Rtl::Element>>>::Allocate(unsigned __int64)
0x18004b5a8  test    rax, rax
0x18004b5ab  jnz     short loc_18004B62C
0x18004b5ad  lea     rax, aOnecoreBaseXml_0; "onecore\\base\\xml\\udom_microdom.cpp"
0x18004b5b4  mov     [rbp+40h+var_88], 724h
0x18004b5bb  mov     [rbp+40h+var_98], rax
0x18004b5bf  lea     rcx, [rbp+40h+var_98]
0x18004b5c3  lea     rax, aMicrodomimplem_13; "MicrodomImplementation::CMicrodom::GetE"...
0x18004b5ca  mov     r8d, 0C0000017h
0x18004b5d0  mov     [rbp+40h+var_90], rax
0x18004b5d4  lea     rax, aTempelementsAl; "TempElements.Allocate(NewCapacity)"
0x18004b5db  mov     [rbp+40h+var_80], rax
0x18004b5df  call    RtlReportErrorOrigination
0x18004b5e4  cmp     [rsp+140h+P], 0
0x18004b5ea  mov     ebx, 0C0000017h
0x18004b5ef  jz      loc_18004B71C
0x18004b5f5  mov     rcx, gs:60h
0x18004b5fe  xor     edx, edx; Flags
0x18004b600  mov     r8, [rsp+140h+P]; P
0x18004b605  mov     rcx, [rcx+30h]; HeapHandle
0x18004b609  call    cs:__imp_RtlFreeHeap
0x18004b610  nop     dword ptr [rax+rax+00h]
0x18004b615  jmp     loc_18004B71C
0x18004b61a  lea     r9, [rsp+140h+var_100]; bool *
0x18004b61f  mov     r8, r12; struct _LUTF8_STRING *
0x18004b622  call    ?CompareElementByTagName@CMicrodom@MicrodomImplementation@@AEAAJPEBU_MICRODOM_DOM_NODE_ELEMENT@@PEBU_LUTF8_STRING@@PEA_N@Z; MicrodomImplementation::CMicrodom::CompareElementByTagName(_MICRODOM_DOM_NODE_ELEMENT const *,_LUTF8_STRING const *,bool *)
0x18004b627  jmp     loc_18004B55E
0x18004b62c  mov     r8, [rdi]
0x18004b62f  mov     rdx, [rsi]; Src
0x18004b632  mov     rcx, [rsp+140h+P]; void *
0x18004b637  shl     r8, 4; Size
0x18004b63b  call    memcpy_0
0x18004b640  movups  xmm1, xmmword ptr [rsi]
0x18004b643  movaps  xmm0, xmmword ptr [rsp+140h+P]
0x18004b648  movq    r8, xmm1; P
0x18004b64d  movdqu  xmmword ptr [rsi], xmm0
0x18004b651  test    r8, r8
0x18004b654  jz      short loc_18004B674
0x18004b656  mov     rcx, gs:60h
0x18004b65f  xor     edx, edx; Flags
0x18004b661  mov     rcx, [rcx+30h]; HeapHandle
0x18004b665  call    cs:__imp_RtlFreeHeap
0x18004b66c  nop     dword ptr [rax+rax+00h]
0x18004b671  mov     ebx, [rbp+40h+var_54]
0x18004b674  mov     rcx, [rdi]
0x18004b677  cmp     rcx, [rsi+8]
0x18004b67b  jb      short loc_18004B67E
0x18004b67d  int     3; Trap to Debugger
0x18004b67e  mov     rax, [rsi]
0x18004b681  add     rcx, rcx
0x18004b684  mov     [rax+rcx*8+8], r15d
0x18004b689  inc     qword ptr [rdi]
0x18004b68c  xor     r9d, r9d
0x18004b68f  lea     r8, [rsp+140h+var_D0]
0x18004b694  mov     edx, r15d
0x18004b697  mov     rcx, r13
0x18004b69a  call    ?GetNodeChildren@CMicrodom@MicrodomImplementation@@QEAAJKPEAPEAU?$Vector@$$CBUNode@Rtl@Microdom@Windows@@@Windows@@0@Z; MicrodomImplementation::CMicrodom::GetNodeChildren(ulong,Windows::Vector<Windows::Microdom::Rtl::Node const> * *,Windows::Vector<Windows::Microdom::Rtl::Node const> * *)
0x18004b69f  test    eax, eax
0x18004b6a1  js      short loc_18004B71E
0x18004b6a3  mov     r14, [rsp+140h+var_D0]
0x18004b6a8  xor     r12d, r12d
0x18004b6ab  cmp     [r14+8], r12
0x18004b6af  jbe     short loc_18004B71C
0x18004b6b1  xor     r15d, r15d
0x18004b6b4  mov     rax, [r14]
0x18004b6b7  lea     r8, [rsp+140h+var_C8]; struct _MICRODOM_DOM_NODE_HEADER **
0x18004b6bc  lea     rcx, [r13+30h]; this
0x18004b6c0  mov     edx, [r15+rax+8]; unsigned int
0x18004b6c5  call    ?FindObject@CDomLayoutCache@MicrodomImplementation@@QEAAJKAEAPEBU_MICRODOM_DOM_NODE_HEADER@@@Z; MicrodomImplementation::CDomLayoutCache::FindObject(ulong,_MICRODOM_DOM_NODE_HEADER const * &)
0x18004b6ca  test    eax, eax
0x18004b6cc  js      short loc_18004B71E
0x18004b6ce  mov     rax, [rsp+140h+var_C8]
0x18004b6d3  mov     cl, [rax]
0x18004b6d5  and     cl, 0Fh
0x18004b6d8  cmp     cl, 1
0x18004b6db  jnz     short loc_18004B70F
0x18004b6dd  mov     rax, [r14]
0x18004b6e0  mov     r9, [rbp+40h+var_C0]
0x18004b6e4  mov     r8, [rsp+140h+var_D8]
0x18004b6e9  mov     [rsp+140h+var_108], rdi
0x18004b6ee  mov     edx, [r15+rax+8]
0x18004b6f3  mov     [rsp+140h+var_110], rsi
0x18004b6f8  mov     [rsp+140h+var_118], cl
0x18004b6fc  mov     cl, [rbp+40h+arg_20]
0x18004b6ff  mov     byte ptr [rsp+140h+var_120], cl
0x18004b703  mov     rcx, r13
0x18004b706  call    ?GetElementsByTagNameCommon@CMicrodom@MicrodomImplementation@@AEAAJKPEBU_LUTF8_STRING@@0_N1PEAV?$Auto@U?$Vector@UElement@Rtl@Microdom@Windows@@@Windows@@@Windows@@PEA_K@Z; MicrodomImplementation::CMicrodom::GetElementsByTagNameCommon(ulong,_LUTF8_STRING const *,_LUTF8_STRING const *,bool,bool,Windows::Auto<Windows::Vector<Windows::Microdom::Rtl::Element>> *,unsigned __int64 *)
0x18004b70b  test    eax, eax
0x18004b70d  js      short loc_18004B71E
0x18004b70f  inc     r12
0x18004b712  add     r15, 10h
0x18004b716  cmp     r12, [r14+8]
0x18004b71a  jb      short loc_18004B6B4
0x18004b71c  mov     eax, ebx
0x18004b71e  mov     rcx, [rbp+40h+var_50]
0x18004b722  xor     rcx, rsp; StackCookie
0x18004b725  call    __security_check_cookie
0x18004b72a  add     rsp, 108h
0x18004b731  pop     r15
0x18004b733  pop     r14
0x18004b735  pop     r13
0x18004b737  pop     r12
0x18004b739  pop     rdi
0x18004b73a  pop     rsi
0x18004b73b  pop     rbx
0x18004b73c  pop     rbp
0x18004b73d  retn
0x18004b73e  lea     rax, aOnecoreBaseXml_0; "onecore\\base\\xml\\udom_microdom.cpp"
0x18004b745  mov     [rbp+40h+var_68], 722h
0x18004b74c  mov     [rbp+40h+var_78], rax
0x18004b750  lea     rcx, [rbp+40h+var_78]
0x18004b754  lea     rax, aMicrodomimplem_13; "MicrodomImplementation::CMicrodom::GetE"...
0x18004b75b  mov     r8d, 0C0000095h
0x18004b761  mov     [rbp+40h+var_70], rax
0x18004b765  lea     rax, aBuclRtlAddSize_3; "::BUCL::Rtl::Add<SIZE_T>( *pcElements, "...
0x18004b76c  mov     [rbp+40h+var_60], rax
0x18004b770  call    RtlReportErrorOrigination
0x18004b775  mov     ebx, 0C0000095h
0x18004b77a  jmp     short loc_18004B71C
```
