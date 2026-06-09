# MicrodomImplementation::CMicrodom::GetElementNodeSet(Windows::Microdom::Rtl::Element,Windows::Auto<Windows::Vector<Windows::Microdom::Rtl::Node>> *)

- ea: `0x18004ab3c`
- end: `0x18004ad12`
- name: `?GetElementNodeSet@CMicrodom@MicrodomImplementation@@QEAAJUElement@Rtl@Microdom@Windows@@PEAV?$Auto@U?$Vector@UNode@Rtl@Microdom@Windows@@@Windows@@@6@@Z`
- size: `470`
- prototype: `__int64 __fastcall(MicrodomImplementation::CMicrodom *this)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18004ed00`

## callees

- `0x1800370f4`
- `0x18004ab3c`
- `0x18004afac`
- `0x18004f514`
- `0x180050a2c`
- `0x1800607b0`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18004aca6`
- `ntdll!RtlFreeHeap` at `0x18004ad02`
- `ntdll!RtlFreeHeap` at `0x18004aca6`
- `ntdll!RtlFreeHeap` at `0x18004ad02`

## string_xrefs

- `0x18004ac08`: `onecore\base\xml\udom_microdom.cpp`
- `0x18004ac2f`: `TempNodes.Allocate(UpperIndex - TheElement.Reserved)`

## pseudocode

```c
__int64 __fastcall MicrodomImplementation::CMicrodom::GetElementNodeSet(
        MicrodomImplementation::CMicrodom *this,
        __int64 a2,
        _OWORD *a3)
{
  __int64 v5; // rdx
  unsigned int v7; // ebx
  __int64 result; // rax
  unsigned int v9; // edx
  unsigned int v10; // eax
  unsigned __int64 v11; // r14
  unsigned __int64 v12; // rax
  unsigned __int64 v13; // rdi
  __int64 v14; // rdx
  PVOID v15; // rsi
  unsigned int v16; // edi
  _DWORD *v17; // rcx
  __int128 v18; // xmm0
  PVOID v19; // rax
  PVOID P[2]; // [rsp+30h] [rbp-39h] BYREF
  struct _MICRODOM_DOM_NODE_HEADER *v21; // [rsp+40h] [rbp-29h] BYREF
  unsigned int v22; // [rsp+58h] [rbp-11h] BYREF
  _QWORD v23[2]; // [rsp+60h] [rbp-9h] BYREF
  int v24; // [rsp+70h] [rbp+7h]
  const char *v25; // [rsp+78h] [rbp+Fh]
  unsigned int v26; // [rsp+80h] [rbp+17h]

  v5 = *(unsigned int *)(a2 + 8);
  v7 = 0;
  v26 = 0;
  v21 = 0;
  result = MicrodomImplementation::CDomLayoutCache::FindObject(
             (MicrodomImplementation::CMicrodom *)((char *)this + 48),
             v5,
             &v21);
  if ( (int)result < 0 )
    return result;
  v9 = *(_DWORD *)(a2 + 8);
  v22 = -1;
  result = MicrodomImplementation::CMicrodom::GetSibling(this, v9, v21, 1, &v22);
  if ( (int)result < 0 )
    return result;
  v10 = v22;
  if ( v22 == -1 )
    v10 = *(_DWORD *)(*((_QWORD *)this + 12) + 8LL);
  v11 = v10;
  v12 = *(unsigned int *)(a2 + 8);
  P[0] = 0;
  P[1] = 0;
  if ( v11 < v12 )
    __debugbreak();
  v13 = *(unsigned int *)(a2 + 8);
  if ( !Windows::AutoVectorBase<Windows::Microdom::MicrodomVectorTraits<Windows::Microdom::Rtl::Element>,Windows::Auto<Windows::Vector<Windows::Microdom::Rtl::Element>>>::Allocate(P) )
  {
    v15 = P[0];
    v23[0] = "onecore\\base\\xml\\udom_microdom.cpp";
    v24 = 1295;
    v23[1] = "MicrodomImplementation::CMicrodom::GetElementNodeSet";
    v25 = "TempNodes.Allocate(UpperIndex - TheElement.Reserved)";
    RtlReportErrorOrigination(v23, v14, 3221225495LL);
    v16 = -1073741801;
LABEL_20:
    if ( v15 )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P[0]);
    return v16;
  }
  if ( v13 < v11 )
  {
    v15 = P[0];
    v17 = (char *)P[0] + 8;
    while ( v13 <= 0xFFFFFFFF )
    {
      *v17 = v13;
      if ( v13 != (unsigned int)v13 )
      {
        v16 = -1073741595;
        goto LABEL_20;
      }
      ++v13;
      v17 += 4;
      if ( v13 >= v11 )
        goto LABEL_14;
    }
    v16 = -1073741675;
    goto LABEL_20;
  }
LABEL_14:
  v18 = *(_OWORD *)P;
  *(_OWORD *)P = *a3;
  v19 = P[0];
  *a3 = v18;
  if ( v19 )
  {
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P[0]);
    return v26;
  }
  return v7;
}

```

## disassembly

```asm
0x18004ab3c  mov     [rsp-8+arg_18], rbx
0x18004ab41  push    rbp
0x18004ab42  push    rsi
0x18004ab43  push    rdi
0x18004ab44  push    r12
0x18004ab46  push    r13
0x18004ab48  push    r14
0x18004ab4a  push    r15
0x18004ab4c  lea     rbp, [rsp-27h]
0x18004ab51  sub     rsp, 90h
0x18004ab58  mov     rax, cs:__security_cookie
0x18004ab5f  xor     rax, rsp
0x18004ab62  mov     [rbp+57h+var_38], rax
0x18004ab66  mov     r15, r8
0x18004ab69  mov     r13, rdx
0x18004ab6c  mov     edx, [rdx+8]; unsigned int
0x18004ab6f  lea     r8, [rbp+57h+var_80]; struct _MICRODOM_DOM_NODE_HEADER **
0x18004ab73  mov     rdi, rcx
0x18004ab76  xor     ebx, ebx
0x18004ab78  add     rcx, 30h ; '0'; this
0x18004ab7c  mov     [rbp+57h+var_40], ebx
0x18004ab7f  mov     [rbp+57h+var_80], rbx
0x18004ab83  call    ?FindObject@CDomLayoutCache@MicrodomImplementation@@QEAAJKAEAPEBU_MICRODOM_DOM_NODE_HEADER@@@Z; MicrodomImplementation::CDomLayoutCache::FindObject(ulong,_MICRODOM_DOM_NODE_HEADER const * &)
0x18004ab88  test    eax, eax
0x18004ab8a  js      loc_18004ACB7
0x18004ab90  mov     r8, [rbp+57h+var_80]; struct _MICRODOM_DOM_NODE_HEADER *
0x18004ab94  lea     rax, [rbp+57h+var_68]
0x18004ab98  mov     edx, [r13+8]; unsigned int
0x18004ab9c  lea     r9d, [rbx+1]; int
0x18004aba0  mov     r12d, 0FFFFFFFFh
0x18004aba6  mov     [rsp+0C0h+var_A0], rax; unsigned int *
0x18004abab  mov     [rbp+57h+var_68], r12d
0x18004abaf  mov     rcx, rdi; this
0x18004abb2  movaps  xmm0, xmmword ptr [rbp-19h]
0x18004abb6  movdqa  xmmword ptr [rbp-19h], xmm0
0x18004abbb  call    ?GetSibling@CMicrodom@MicrodomImplementation@@QEAAJKPEBU_MICRODOM_DOM_NODE_HEADER@@HPEAK@Z; MicrodomImplementation::CMicrodom::GetSibling(ulong,_MICRODOM_DOM_NODE_HEADER const *,int,ulong *)
0x18004abc0  test    eax, eax
0x18004abc2  js      loc_18004ACB7
0x18004abc8  mov     eax, [rbp+57h+var_68]
0x18004abcb  cmp     eax, r12d
0x18004abce  jnz     short loc_18004ABD7
0x18004abd0  mov     rax, [rdi+60h]
0x18004abd4  mov     eax, [rax+8]
0x18004abd7  mov     r14d, eax
0x18004abda  mov     eax, [r13+8]
0x18004abde  mov     [rbp+57h+P], rbx
0x18004abe2  mov     [rbp+57h+P+8], rbx
0x18004abe6  cmp     r14, rax
0x18004abe9  jnb     short loc_18004ABEC
0x18004abeb  int     3; Trap to Debugger
0x18004abec  mov     edi, [r13+8]
0x18004abf0  lea     rcx, [rbp+57h+P]
0x18004abf4  mov     rdx, r14
0x18004abf7  sub     rdx, rdi
0x18004abfa  call    ?Allocate@?$AutoVectorBase@V?$MicrodomVectorTraits@UElement@Rtl@Microdom@Windows@@@Microdom@Windows@@V?$Auto@U?$Vector@UElement@Rtl@Microdom@Windows@@@Windows@@@3@@Windows@@QEAAPEAUElement@Rtl@Microdom@2@_K@Z; Windows::AutoVectorBase<Windows::Microdom::MicrodomVectorTraits<Windows::Microdom::Rtl::Element>,Windows::Auto<Windows::Vector<Windows::Microdom::Rtl::Element>>>::Allocate(unsigned __int64)
0x18004abff  test    rax, rax
0x18004ac02  jnz     short loc_18004AC49
0x18004ac04  mov     rsi, [rbp+57h+P]
0x18004ac08  lea     rax, aOnecoreBaseXml_0; "onecore\\base\\xml\\udom_microdom.cpp"
0x18004ac0f  mov     [rbp+57h+var_60], rax
0x18004ac13  lea     rcx, [rbp+57h+var_60]
0x18004ac17  lea     rax, aMicrodomimplem_23; "MicrodomImplementation::CMicrodom::GetE"...
0x18004ac1e  mov     [rbp+57h+var_50], 50Fh
0x18004ac25  mov     [rbp+57h+var_58], rax
0x18004ac29  mov     r8d, 0C0000017h
0x18004ac2f  lea     rax, aTempnodesAlloc; "TempNodes.Allocate(UpperIndex - TheElem"...
0x18004ac36  mov     [rbp+57h+var_48], rax
0x18004ac3a  call    RtlReportErrorOrigination
0x18004ac3f  mov     edi, 0C0000017h
0x18004ac44  jmp     loc_18004ACEA
0x18004ac49  cmp     rdi, r14
0x18004ac4c  jnb     short loc_18004AC74
0x18004ac4e  mov     rsi, [rbp+57h+P]
0x18004ac52  lea     rcx, [rsi+8]
0x18004ac56  cmp     rdi, r12
0x18004ac59  ja      loc_18004ACE5
0x18004ac5f  mov     eax, edi
0x18004ac61  mov     [rcx], eax
0x18004ac63  cmp     rdi, rax
0x18004ac66  jnz     short loc_18004ACDE
0x18004ac68  inc     rdi
0x18004ac6b  add     rcx, 10h
0x18004ac6f  cmp     rdi, r14
0x18004ac72  jb      short loc_18004AC56
0x18004ac74  movups  xmm1, xmmword ptr [r15]
0x18004ac78  movaps  xmm0, xmmword ptr [rbp+57h+P]
0x18004ac7c  movq    rax, xmm1
0x18004ac81  movaps  xmmword ptr [rbp+57h+P], xmm1
0x18004ac85  mov     [rbp+57h+P], rax
0x18004ac89  movdqu  xmmword ptr [r15], xmm0
0x18004ac8e  test    rax, rax
0x18004ac91  jz      short loc_18004ACB5
0x18004ac93  mov     rcx, gs:60h
0x18004ac9c  xor     edx, edx; Flags
0x18004ac9e  mov     r8, [rbp+57h+P]; P
0x18004aca2  mov     rcx, [rcx+30h]; HeapHandle
0x18004aca6  call    cs:__imp_RtlFreeHeap
0x18004acad  nop     dword ptr [rax+rax+00h]
0x18004acb2  mov     ebx, [rbp+57h+var_40]
0x18004acb5  mov     eax, ebx
0x18004acb7  mov     rcx, [rbp+57h+var_38]
0x18004acbb  xor     rcx, rsp; StackCookie
0x18004acbe  call    __security_check_cookie
0x18004acc3  mov     rbx, [rsp+0C0h+arg_18]
0x18004accb  add     rsp, 90h
0x18004acd2  pop     r15
0x18004acd4  pop     r14
0x18004acd6  pop     r13
0x18004acd8  pop     r12
0x18004acda  pop     rdi
0x18004acdb  pop     rsi
0x18004acdc  pop     rbp
0x18004acdd  retn
0x18004acde  mov     edi, 0C00000E5h
0x18004ace3  jmp     short loc_18004ACEA
0x18004ace5  mov     edi, 0C0000095h
0x18004acea  test    rsi, rsi
0x18004aced  jz      short loc_18004AD0E
0x18004acef  mov     rcx, gs:60h
0x18004acf8  xor     edx, edx; Flags
0x18004acfa  mov     r8, [rbp+57h+P]; P
0x18004acfe  mov     rcx, [rcx+30h]; HeapHandle
0x18004ad02  call    cs:__imp_RtlFreeHeap
0x18004ad09  nop     dword ptr [rax+rax+00h]
0x18004ad0e  mov     eax, edi
0x18004ad10  jmp     short loc_18004ACB7
```
