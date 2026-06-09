# MicrodomImplementation::CMicrodom::GetElementsByTagName(_LUTF8_STRING const *,_LUTF8_STRING const *,bool,Windows::Auto<Windows::Vector<Windows::Microdom::Rtl::Element>> *)

- ea: `0x18004bb10`
- end: `0x18004be01`
- name: `?GetElementsByTagName@CMicrodom@MicrodomImplementation@@QEAAJPEBU_LUTF8_STRING@@0_NPEAV?$Auto@U?$Vector@UElement@Rtl@Microdom@Windows@@@Windows@@@Windows@@@Z`
- size: `753`
- prototype: `__int64 __usercall@<rax>(MicrodomImplementation::CMicrodom *this@<rcx>, __int64)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18004dba0`
- `0x18004dd00`

## callees

- `0x1800370f4`
- `0x18004b884`
- `0x18004b9d4`
- `0x18004bb10`
- `0x18004f514`
- `0x180050a2c`
- `0x1800607b0`
- `0x180060e42`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18004bc7a`
- `ntdll!RtlFreeHeap` at `0x18004bd1d`
- `ntdll!RtlFreeHeap` at `0x18004bd83`
- `ntdll!RtlFreeHeap` at `0x18004bdcb`
- `ntdll!RtlFreeHeap` at `0x18004bc7a`
- `ntdll!RtlFreeHeap` at `0x18004bd1d`
- `ntdll!RtlFreeHeap` at `0x18004bd83`
- `ntdll!RtlFreeHeap` at `0x18004bdcb`

## string_xrefs

- `0x18004bcc7`: `onecore\base\xml\udom_microdom.cpp`
- `0x18004bd2f`: `onecore\base\xml\udom_microdom.cpp`
- `0x18004bcee`: `TempTempElements.Allocate(NewCapacity)`

## pseudocode

```c
__int64 __fastcall MicrodomImplementation::CMicrodom::GetElementsByTagName(
        MicrodomImplementation::CMicrodom *this,
        struct _LUTF8_STRING *a2,
        struct _LUTF8_STRING *a3,
        char a4,
        __int128 *a5)
{
  char *v5; // rsi
  char *v6; // r14
  char *v7; // rdi
  unsigned int v9; // r15d
  MicrodomImplementation::CDomLayoutCache *i; // rax
  int Object; // ebx
  int v12; // eax
  unsigned __int64 v13; // rdx
  __int64 v14; // rdx
  size_t v15; // rbx
  __int128 v16; // xmm0
  PVOID v17; // r8
  __int128 v19; // xmm1
  __int128 v20; // xmm0
  bool v21; // [rsp+30h] [rbp-81h] BYREF
  char v22; // [rsp+31h] [rbp-80h]
  PVOID v23[2]; // [rsp+40h] [rbp-71h] BYREF
  size_t Size; // [rsp+50h] [rbp-61h]
  struct _MICRODOM_DOM_NODE_HEADER *v25; // [rsp+58h] [rbp-59h] BYREF
  struct _LUTF8_STRING *v26; // [rsp+60h] [rbp-51h]
  struct _LUTF8_STRING *v27; // [rsp+68h] [rbp-49h]
  _QWORD v28[2]; // [rsp+70h] [rbp-41h] BYREF
  int v29; // [rsp+80h] [rbp-31h]
  const char *v30; // [rsp+88h] [rbp-29h]
  _QWORD v31[2]; // [rsp+90h] [rbp-21h] BYREF
  int v32; // [rsp+A0h] [rbp-11h]
  const char *v33; // [rsp+A8h] [rbp-9h]
  PVOID P[2]; // [rsp+B0h] [rbp-1h]
  unsigned int v35; // [rsp+C0h] [rbp+Fh]

  v35 = 0;
  v5 = 0;
  v6 = 0;
  v7 = 0;
  v22 = a4;
  v26 = a3;
  v27 = a2;
  P[0] = 0;
  P[1] = 0;
  if ( !a3 )
    __debugbreak();
  if ( !a5 )
    __debugbreak();
  v9 = 0;
  if ( *(_DWORD *)(*((_QWORD *)this + 12) + 8LL) )
  {
    Size = 0;
    for ( i = (MicrodomImplementation::CMicrodom *)((char *)this + 48);
          ;
          i = (MicrodomImplementation::CMicrodom *)((char *)this + 48) )
    {
      v25 = 0;
      Object = MicrodomImplementation::CDomLayoutCache::FindObject(i, v9, &v25);
      if ( Object < 0 )
        break;
      if ( (*(_BYTE *)v25 & 0xF) == 1 )
      {
        if ( v22 )
          v12 = MicrodomImplementation::CMicrodom::CompareElementByTagNameNS(this, v25, v27, v26, &v21);
        else
          v12 = MicrodomImplementation::CMicrodom::CompareElementByTagName(this, v25, v26, &v21);
        Object = v12;
        if ( v12 < 0 )
          break;
        if ( v21 )
        {
          if ( v6 == v7 )
          {
            v23[0] = 0;
            v13 = (unsigned __int64)(v7 + 10);
            v23[1] = 0;
            if ( v7 + 10 < v7 || v13 < 0xA )
            {
              v32 = 2142;
              v31[0] = "onecore\\base\\xml\\udom_microdom.cpp";
              v31[1] = "MicrodomImplementation::CMicrodom::GetElementsByTagName";
              v33 = "::BUCL::Rtl::Add<SIZE_T>( cElements, 10, NewCapacity)";
              RtlReportErrorOrigination(v31, v13, 3221225621LL);
              Object = -1073741675;
              break;
            }
            if ( !Windows::AutoVectorBase<Windows::Microdom::MicrodomVectorTraits<Windows::Microdom::Rtl::Element>,Windows::Auto<Windows::Vector<Windows::Microdom::Rtl::Element>>>::Allocate(v23) )
            {
              v29 = 2144;
              v28[0] = "onecore\\base\\xml\\udom_microdom.cpp";
              v28[1] = "MicrodomImplementation::CMicrodom::GetElementsByTagName";
              v30 = "TempTempElements.Allocate(NewCapacity)";
              RtlReportErrorOrigination(v28, v14, 3221225495LL);
              Object = -1073741801;
              if ( v23[0] )
              {
                RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v23[0]);
                v5 = (char *)P[0];
              }
              break;
            }
            v15 = Size;
            memcpy_0(v23[0], v5, Size);
            v16 = *(_OWORD *)v23;
            v17 = P[0];
            *(_OWORD *)v23 = *(_OWORD *)P;
            *(_OWORD *)P = v16;
            if ( v17 )
            {
              v23[0] = 0;
              v23[1] = 0;
              RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v17);
            }
            v6 = (char *)P[1];
            v5 = (char *)P[0];
          }
          else
          {
            v15 = Size;
          }
          if ( v7 >= v6 )
            __debugbreak();
          ++v7;
          *(_DWORD *)&v5[v15 + 8] = v9;
          Size = v15 + 16;
        }
      }
      if ( ++v9 == *(_DWORD *)(*((_QWORD *)this + 12) + 8LL) )
        goto LABEL_33;
    }
    if ( v5 )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P[0]);
    return (unsigned int)Object;
  }
  else
  {
LABEL_33:
    v19 = *a5;
    P[1] = v7;
    v20 = *(_OWORD *)P;
    *(_OWORD *)P = v19;
    *a5 = v20;
    if ( (_QWORD)v19 )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P[0]);
    return v35;
  }
}

```

## disassembly

```asm
0x18004bb10  mov     [rsp-8+arg_8], rbx
0x18004bb15  push    rbp
0x18004bb16  push    rsi
0x18004bb17  push    rdi
0x18004bb18  push    r12
0x18004bb1a  push    r13
0x18004bb1c  push    r14
0x18004bb1e  push    r15
0x18004bb20  lea     rbp, [rsp-1Fh]
0x18004bb25  sub     rsp, 0D0h
0x18004bb2c  mov     rax, cs:__security_cookie
0x18004bb33  xor     rax, rsp
0x18004bb36  mov     [rbp+4Fh+var_38], rax
0x18004bb3a  and     [rbp+4Fh+var_40], 0
0x18004bb3e  xor     esi, esi
0x18004bb40  mov     r12, [rbp+4Fh+arg_20]
0x18004bb44  xor     r14d, r14d
0x18004bb47  xor     edi, edi
0x18004bb49  mov     [rbp+4Fh+var_CF], r9b
0x18004bb4d  mov     [rbp+4Fh+var_A0], r8
0x18004bb51  mov     r13, rcx
0x18004bb54  mov     [rbp+4Fh+var_98], rdx
0x18004bb58  mov     [rbp+4Fh+P], rsi
0x18004bb5c  mov     [rbp+4Fh+P+8], r14
0x18004bb60  test    r8, r8
0x18004bb63  jnz     short loc_18004BB66
0x18004bb65  int     3; Trap to Debugger
0x18004bb66  test    r12, r12
0x18004bb69  jnz     short loc_18004BB6C
0x18004bb6b  int     3; Trap to Debugger
0x18004bb6c  mov     rax, [rcx+60h]
0x18004bb70  xor     r15d, r15d
0x18004bb73  cmp     [rax+8], esi
0x18004bb76  jz      loc_18004BD93
0x18004bb7c  and     [rbp+4Fh+Size], rsi
0x18004bb80  lea     rax, [rcx+30h]
0x18004bb84  and     [rbp+4Fh+var_A8], 0
0x18004bb89  lea     r8, [rbp+4Fh+var_A8]; struct _MICRODOM_DOM_NODE_HEADER **
0x18004bb8d  mov     edx, r15d; unsigned int
0x18004bb90  mov     rcx, rax; this
0x18004bb93  call    ?FindObject@CDomLayoutCache@MicrodomImplementation@@QEAAJKAEAPEBU_MICRODOM_DOM_NODE_HEADER@@@Z; MicrodomImplementation::CDomLayoutCache::FindObject(ulong,_MICRODOM_DOM_NODE_HEADER const * &)
0x18004bb98  mov     ebx, eax
0x18004bb9a  test    eax, eax
0x18004bb9c  js      loc_18004BD6B
0x18004bba2  mov     rdx, [rbp+4Fh+var_A8]; struct _MICRODOM_DOM_NODE_ELEMENT *
0x18004bba6  mov     al, [rdx]
0x18004bba8  and     al, 0Fh
0x18004bbaa  cmp     al, 1
0x18004bbac  jnz     loc_18004BCAD
0x18004bbb2  cmp     [rbp+4Fh+var_CF], 0
0x18004bbb6  mov     rcx, r13; this
0x18004bbb9  jz      short loc_18004BBD4
0x18004bbbb  mov     r9, [rbp+4Fh+var_A0]; struct _LUTF8_STRING *
0x18004bbbf  lea     rax, [rsp+100h+var_D0]
0x18004bbc4  mov     r8, [rbp+4Fh+var_98]; struct _LUTF8_STRING *
0x18004bbc8  mov     [rsp+100h+var_E0], rax; bool *
0x18004bbcd  call    ?CompareElementByTagNameNS@CMicrodom@MicrodomImplementation@@AEAAJPEBU_MICRODOM_DOM_NODE_ELEMENT@@PEBU_LUTF8_STRING@@1PEA_N@Z; MicrodomImplementation::CMicrodom::CompareElementByTagNameNS(_MICRODOM_DOM_NODE_ELEMENT const *,_LUTF8_STRING const *,_LUTF8_STRING const *,bool *)
0x18004bbd2  jmp     short loc_18004BBE2
0x18004bbd4  mov     r8, [rbp+4Fh+var_A0]; struct _LUTF8_STRING *
0x18004bbd8  lea     r9, [rsp+100h+var_D0]; bool *
0x18004bbdd  call    ?CompareElementByTagName@CMicrodom@MicrodomImplementation@@AEAAJPEBU_MICRODOM_DOM_NODE_ELEMENT@@PEBU_LUTF8_STRING@@PEA_N@Z; MicrodomImplementation::CMicrodom::CompareElementByTagName(_MICRODOM_DOM_NODE_ELEMENT const *,_LUTF8_STRING const *,bool *)
0x18004bbe2  mov     ebx, eax
0x18004bbe4  test    eax, eax
0x18004bbe6  js      loc_18004BD6B
0x18004bbec  cmp     [rsp+100h+var_D0], 0
0x18004bbf1  jz      loc_18004BCAD
0x18004bbf7  cmp     r14, rdi
0x18004bbfa  jnz     loc_18004BC90
0x18004bc00  and     [rbp+4Fh+var_C0], 0
0x18004bc05  lea     rdx, [rdi+0Ah]
0x18004bc09  and     [rbp+4Fh+var_C0+8], 0
0x18004bc0e  cmp     rdx, rdi
0x18004bc11  jb      loc_18004BD2F
0x18004bc17  cmp     rdx, 0Ah
0x18004bc1b  jb      loc_18004BD2F
0x18004bc21  lea     rcx, [rbp+4Fh+var_C0]
0x18004bc25  call    ?Allocate@?$AutoVectorBase@V?$MicrodomVectorTraits@UElement@Rtl@Microdom@Windows@@@Microdom@Windows@@V?$Auto@U?$Vector@UElement@Rtl@Microdom@Windows@@@Windows@@@3@@Windows@@QEAAPEAUElement@Rtl@Microdom@2@_K@Z; Windows::AutoVectorBase<Windows::Microdom::MicrodomVectorTraits<Windows::Microdom::Rtl::Element>,Windows::Auto<Windows::Vector<Windows::Microdom::Rtl::Element>>>::Allocate(unsigned __int64)
0x18004bc2a  test    rax, rax
0x18004bc2d  jz      loc_18004BCC7
0x18004bc33  mov     rbx, [rbp+4Fh+Size]
0x18004bc37  mov     rdx, rsi; Src
0x18004bc3a  mov     rcx, [rbp+4Fh+var_C0]; void *
0x18004bc3e  mov     r8, rbx; Size
0x18004bc41  call    memcpy_0
0x18004bc46  movaps  xmm1, xmmword ptr [rbp+4Fh+P]
0x18004bc4a  movaps  xmm0, xmmword ptr [rbp+4Fh+var_C0]
0x18004bc4e  movq    r8, xmm1; P
0x18004bc53  movaps  xmmword ptr [rbp+4Fh+var_C0], xmm1
0x18004bc57  movdqa  xmmword ptr [rbp+4Fh+P], xmm0
0x18004bc5c  test    r8, r8
0x18004bc5f  jz      short loc_18004BC86
0x18004bc61  mov     rcx, gs:60h
0x18004bc6a  xor     edx, edx; Flags
0x18004bc6c  and     [rbp+4Fh+var_C0], 0
0x18004bc71  and     [rbp+4Fh+var_C0+8], 0
0x18004bc76  mov     rcx, [rcx+30h]; HeapHandle
0x18004bc7a  call    cs:__imp_RtlFreeHeap
0x18004bc81  nop     dword ptr [rax+rax+00h]
0x18004bc86  mov     r14, [rbp+4Fh+P+8]
0x18004bc8a  mov     rsi, [rbp+4Fh+P]
0x18004bc8e  jmp     short loc_18004BC94
0x18004bc90  mov     rbx, [rbp+4Fh+Size]
0x18004bc94  cmp     rdi, r14
0x18004bc97  jb      short loc_18004BC9A
0x18004bc99  int     3; Trap to Debugger
0x18004bc9a  lea     rax, [rsi+rbx]
0x18004bc9e  inc     rdi
0x18004bca1  add     rbx, 10h
0x18004bca5  mov     [rax+8], r15d
0x18004bca9  mov     [rbp+4Fh+Size], rbx
0x18004bcad  mov     rax, [r13+60h]
0x18004bcb1  inc     r15d
0x18004bcb4  cmp     r15d, [rax+8]
0x18004bcb8  jz      loc_18004BD93
0x18004bcbe  lea     rax, [r13+30h]
0x18004bcc2  jmp     loc_18004BB84
0x18004bcc7  lea     rax, aOnecoreBaseXml_0; "onecore\\base\\xml\\udom_microdom.cpp"
0x18004bcce  mov     [rbp+4Fh+var_80], 860h
0x18004bcd5  mov     [rbp+4Fh+var_90], rax
0x18004bcd9  lea     rcx, [rbp+4Fh+var_90]
0x18004bcdd  lea     rax, aMicrodomimplem_41; "MicrodomImplementation::CMicrodom::GetE"...
0x18004bce4  mov     r8d, 0C0000017h
0x18004bcea  mov     [rbp+4Fh+var_88], rax
0x18004bcee  lea     rax, aTemptempelemen; "TempTempElements.Allocate(NewCapacity)"
0x18004bcf5  mov     [rbp+4Fh+var_78], rax
0x18004bcf9  call    RtlReportErrorOrigination
0x18004bcfe  cmp     [rbp+4Fh+var_C0], 0
0x18004bd03  mov     ebx, 0C0000017h
0x18004bd08  jz      short loc_18004BD6B
0x18004bd0a  mov     rcx, gs:60h
0x18004bd13  xor     edx, edx; Flags
0x18004bd15  mov     r8, [rbp+4Fh+var_C0]; P
0x18004bd19  mov     rcx, [rcx+30h]; HeapHandle
0x18004bd1d  call    cs:__imp_RtlFreeHeap
0x18004bd24  nop     dword ptr [rax+rax+00h]
0x18004bd29  mov     rsi, [rbp+4Fh+P]
0x18004bd2d  jmp     short loc_18004BD6B
0x18004bd2f  lea     rax, aOnecoreBaseXml_0; "onecore\\base\\xml\\udom_microdom.cpp"
0x18004bd36  mov     [rbp+4Fh+var_60], 85Eh
0x18004bd3d  mov     [rbp+4Fh+var_70], rax
0x18004bd41  lea     rcx, [rbp+4Fh+var_70]
0x18004bd45  lea     rax, aMicrodomimplem_41; "MicrodomImplementation::CMicrodom::GetE"...
0x18004bd4c  mov     r8d, 0C0000095h
0x18004bd52  mov     [rbp+4Fh+var_68], rax
0x18004bd56  lea     rax, aBuclRtlAddSize_1; "::BUCL::Rtl::Add<SIZE_T>( cElements, 10"...
0x18004bd5d  mov     [rbp+4Fh+var_58], rax
0x18004bd61  call    RtlReportErrorOrigination
0x18004bd66  mov     ebx, 0C0000095h
0x18004bd6b  test    rsi, rsi
0x18004bd6e  jz      short loc_18004BD8F
0x18004bd70  mov     rcx, gs:60h
0x18004bd79  xor     edx, edx; Flags
0x18004bd7b  mov     r8, [rbp+4Fh+P]; P
0x18004bd7f  mov     rcx, [rcx+30h]; HeapHandle
0x18004bd83  call    cs:__imp_RtlFreeHeap
0x18004bd8a  nop     dword ptr [rax+rax+00h]
0x18004bd8f  mov     eax, ebx
0x18004bd91  jmp     short loc_18004BDDA
0x18004bd93  movups  xmm1, xmmword ptr [r12]
0x18004bd98  mov     [rbp+4Fh+P+8], rdi
0x18004bd9c  movaps  xmm0, xmmword ptr [rbp+4Fh+P]
0x18004bda0  movq    rax, xmm1
0x18004bda5  movaps  xmmword ptr [rbp+4Fh+P], xmm1
0x18004bda9  mov     [rbp+4Fh+P], rax
0x18004bdad  movdqu  xmmword ptr [r12], xmm0
0x18004bdb3  test    rax, rax
0x18004bdb6  jz      short loc_18004BDD7
0x18004bdb8  mov     rcx, gs:60h
0x18004bdc1  xor     edx, edx; Flags
0x18004bdc3  mov     r8, [rbp+4Fh+P]; P
0x18004bdc7  mov     rcx, [rcx+30h]; HeapHandle
0x18004bdcb  call    cs:__imp_RtlFreeHeap
0x18004bdd2  nop     dword ptr [rax+rax+00h]
0x18004bdd7  mov     eax, [rbp+4Fh+var_40]
0x18004bdda  mov     rcx, [rbp+4Fh+var_38]
0x18004bdde  xor     rcx, rsp; StackCookie
0x18004bde1  call    __security_check_cookie
0x18004bde6  mov     rbx, [rsp+100h+arg_8]
0x18004bdee  add     rsp, 0D0h
0x18004bdf5  pop     r15
0x18004bdf7  pop     r14
0x18004bdf9  pop     r13
0x18004bdfb  pop     r12
0x18004bdfd  pop     rdi
0x18004bdfe  pop     rsi
0x18004bdff  pop     rbp
0x18004be00  retn
```
