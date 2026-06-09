# CMicrodomUpdateContext::Construct(Windows::Microdom::Rtl::IRtlMicrodom *)

- ea: `0x180047be0`
- end: `0x180047df6`
- name: `?Construct@CMicrodomUpdateContext@@QEAAJPEAUIRtlMicrodom@Rtl@Microdom@Windows@@@Z`
- size: `534`
- prototype: `__int64 __fastcall(CMicrodomUpdateContext *__hidden this, struct Windows::Microdom::Rtl::IRtlMicrodom *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180048734`

## callees

- `0x1800370f4`
- `0x180047be0`
- `0x180048534`
- `0x1800495c4`
- `0x1800607b0`
- `0x180060e70`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180047d94`
- `ntdll!RtlFreeHeap` at `0x180047dc7`
- `ntdll!RtlFreeHeap` at `0x180047d94`
- `ntdll!RtlFreeHeap` at `0x180047dc7`

## string_xrefs

- `0x180047c10`: `onecore\base\xml\udom_modify.cpp`
- `0x180047c26`: `CMicrodomUpdateContext::Construct`

## pseudocode

```c
__int64 __fastcall CMicrodomUpdateContext::Construct(
        CMicrodomUpdateContext *this,
        struct Windows::Microdom::Rtl::IRtlMicrodom *a2)
{
  __int64 v4; // rax
  int NodeUpdatePtr; // ebx
  void (__fastcall ***v6)(_QWORD); // rdx
  void (__fastcall ***v7)(_QWORD); // rcx
  void (__fastcall ***v8)(_QWORD); // rcx
  void (__fastcall ***v9)(_QWORD); // rcx
  PVOID v10; // r8
  PVOID v11; // r8
  _BYTE v12[8]; // [rsp+20h] [rbp-59h] BYREF
  struct CChildNode *v13; // [rsp+28h] [rbp-51h] BYREF
  _QWORD v14[2]; // [rsp+30h] [rbp-49h] BYREF
  int v15; // [rsp+40h] [rbp-39h]
  const char *v16; // [rsp+48h] [rbp-31h]
  __int128 v17; // [rsp+50h] [rbp-29h] BYREF
  __int128 v18; // [rsp+60h] [rbp-19h] BYREF
  struct Node v19[2]; // [rsp+70h] [rbp-9h] BYREF
  void (__fastcall ***v20)(_QWORD); // [rsp+80h] [rbp+7h] BYREF
  PVOID P; // [rsp+88h] [rbp+Fh] BYREF
  __int64 v22; // [rsp+90h] [rbp+17h]
  __int128 v23; // [rsp+A0h] [rbp+27h] BYREF
  __int128 v24; // [rsp+B0h] [rbp+37h] BYREF

  if ( !a2 )
  {
    v15 = 1157;
    v14[0] = "onecore\\base\\xml\\udom_modify.cpp";
    v14[1] = "CMicrodomUpdateContext::Construct";
    v16 = "SourceDom != 0";
    RtlReportErrorOrigination(v14, 0, 3221225485LL);
    return 3221225485LL;
  }
  v4 = *(_QWORD *)a2;
  v20 = 0;
  NodeUpdatePtr = (*(__int64 (__fastcall **)(struct Windows::Microdom::Rtl::IRtlMicrodom *, GUID *, void (__fastcall ****)(_QWORD)))(v4 + 8))(
                    a2,
                    &GUID_a72b16a7_01e0_49dd_9eb3_f0d75af8d9bd,
                    &v20);
  if ( NodeUpdatePtr < 0 )
  {
    v6 = v20;
  }
  else
  {
    if ( !v20 )
      return (unsigned int)-1073741127;
    v6 = *(void (__fastcall ****)(_QWORD))this;
    *(_QWORD *)this = v20;
  }
  if ( v6 )
  {
    v20 = 0;
    (**v6)(v6);
  }
  if ( NodeUpdatePtr < 0 )
    return (unsigned int)NodeUpdatePtr;
  v7 = *(void (__fastcall ****)(_QWORD))this;
  P = 0;
  v22 = 0;
  NodeUpdatePtr = ((__int64 (__fastcall *)(void (__fastcall ***)(_QWORD), __int128 *))(*v7)[3])(v7, &v23);
  if ( NodeUpdatePtr < 0 )
    goto LABEL_17;
  v8 = *(void (__fastcall ****)(_QWORD))this;
  v17 = v23;
  NodeUpdatePtr = ((__int64 (__fastcall *)(void (__fastcall ***)(_QWORD), __int128 *, __int128 *))(*v8)[2])(
                    v8,
                    &v17,
                    &v24);
  if ( NodeUpdatePtr < 0
    || (v9 = *(void (__fastcall ****)(_QWORD))this,
        v18 = v23,
        NodeUpdatePtr = ((__int64 (__fastcall *)(void (__fastcall ***)(_QWORD), __int128 *, PVOID *))(*v9)[40])(
                          v9,
                          &v18,
                          &P),
        NodeUpdatePtr < 0)
    || (NodeUpdatePtr = *(_DWORD *)BUCL::CVector<NullableChildNodePtr,BUCL::Rtl::CCallDisposition>::Resize(
                                     (char *)this + 40,
                                     v12,
                                     v22),
        NodeUpdatePtr < 0)
    || (v13 = 0,
        *(_OWORD *)&v19[0].lpVtbl = v24,
        NodeUpdatePtr = CMicrodomUpdateContext::GetNodeUpdatePtr(this, (struct Node)v19, 0, &v13),
        NodeUpdatePtr < 0) )
  {
LABEL_17:
    v10 = P;
    if ( P )
    {
      P = 0;
      v22 = 0;
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v10);
    }
    return (unsigned int)NodeUpdatePtr;
  }
  v11 = P;
  if ( P )
  {
    P = 0;
    v22 = 0;
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v11);
  }
  return 0;
}

```

## disassembly

```asm
0x180047be0  mov     [rsp-8+arg_10], rbx
0x180047be5  mov     [rsp-8+arg_18], rdi
0x180047bea  push    rbp
0x180047beb  lea     rbp, [rsp-57h]
0x180047bf0  sub     rsp, 0D0h
0x180047bf7  mov     rax, cs:__security_cookie
0x180047bfe  xor     rax, rsp
0x180047c01  mov     [rbp+57h+var_10], rax
0x180047c05  mov     r9, rdx
0x180047c08  mov     rdi, rcx
0x180047c0b  test    rdx, rdx
0x180047c0e  jnz     short loc_180047C51
0x180047c10  lea     rax, aOnecoreBaseXml; "onecore\\base\\xml\\udom_modify.cpp"
0x180047c17  mov     [rbp+57h+var_90], 485h
0x180047c1e  mov     [rbp+57h+var_A0], rax
0x180047c22  lea     rcx, [rbp+57h+var_A0]
0x180047c26  lea     rax, aCmicrodomupdat_4; "CMicrodomUpdateContext::Construct"
0x180047c2d  mov     r8d, 0C000000Dh
0x180047c33  mov     [rbp+57h+var_98], rax
0x180047c37  lea     rax, aSourcedom0; "SourceDom != 0"
0x180047c3e  mov     [rbp+57h+var_88], rax
0x180047c42  call    RtlReportErrorOrigination
0x180047c47  mov     eax, 0C000000Dh
0x180047c4c  jmp     loc_180047DD5
0x180047c51  mov     rax, [rdx]
0x180047c54  lea     r8, [rbp+57h+var_50]
0x180047c58  and     [rbp+57h+var_50], 0
0x180047c5d  lea     rdx, _GUID_a72b16a7_01e0_49dd_9eb3_f0d75af8d9bd
0x180047c64  mov     rcx, r9
0x180047c67  mov     rax, [rax+8]
0x180047c6b  call    cs:__guard_dispatch_icall_fptr
0x180047c71  mov     ebx, eax
0x180047c73  test    eax, eax
0x180047c75  js      short loc_180047C8F
0x180047c77  mov     rcx, [rbp+57h+var_50]
0x180047c7b  test    rcx, rcx
0x180047c7e  jnz     short loc_180047C87
0x180047c80  mov     ebx, 0C00002B9h
0x180047c85  jmp     short loc_180047CB0
0x180047c87  mov     rdx, [rdi]
0x180047c8a  mov     [rdi], rcx
0x180047c8d  jmp     short loc_180047C93
0x180047c8f  mov     rdx, [rbp+57h+var_50]
0x180047c93  test    rdx, rdx
0x180047c96  jz      short loc_180047CAC
0x180047c98  and     [rbp+57h+var_50], 0
0x180047c9d  mov     rcx, rdx
0x180047ca0  mov     rax, [rdx]
0x180047ca3  mov     rax, [rax]
0x180047ca6  call    cs:__guard_dispatch_icall_fptr
0x180047cac  test    ebx, ebx
0x180047cae  jns     short loc_180047CB7
0x180047cb0  mov     eax, ebx
0x180047cb2  jmp     loc_180047DD5
0x180047cb7  mov     rcx, [rdi]
0x180047cba  lea     rdx, [rbp+57h+var_30]
0x180047cbe  and     [rbp+57h+P], 0
0x180047cc3  and     [rbp+57h+var_40], 0
0x180047cc8  mov     rax, [rcx]
0x180047ccb  mov     rax, [rax+18h]
0x180047ccf  call    cs:__guard_dispatch_icall_fptr
0x180047cd5  mov     ebx, eax
0x180047cd7  test    eax, eax
0x180047cd9  js      loc_180047D6E
0x180047cdf  mov     rcx, [rdi]
0x180047ce2  lea     r8, [rbp+57h+var_20]
0x180047ce6  movaps  xmm0, [rbp+57h+var_30]
0x180047cea  lea     rdx, [rbp+57h+var_80]
0x180047cee  movdqa  [rbp+57h+var_80], xmm0
0x180047cf3  mov     rax, [rcx]
0x180047cf6  mov     rax, [rax+10h]
0x180047cfa  call    cs:__guard_dispatch_icall_fptr
0x180047d00  mov     ebx, eax
0x180047d02  test    eax, eax
0x180047d04  js      short loc_180047D6E
0x180047d06  mov     rcx, [rdi]
0x180047d09  lea     r8, [rbp+57h+P]
0x180047d0d  movaps  xmm0, [rbp+57h+var_30]
0x180047d11  lea     rdx, [rbp+57h+var_70]
0x180047d15  movdqa  [rbp+57h+var_70], xmm0
0x180047d1a  mov     rax, [rcx]
0x180047d1d  mov     rax, [rax+140h]
0x180047d24  call    cs:__guard_dispatch_icall_fptr
0x180047d2a  mov     ebx, eax
0x180047d2c  test    eax, eax
0x180047d2e  js      short loc_180047D6E
0x180047d30  mov     r8, [rbp+57h+var_40]
0x180047d34  lea     rcx, [rdi+28h]
0x180047d38  lea     rdx, [rbp+57h+var_B0]
0x180047d3c  call    ?Resize@?$CVector@UNullableChildNodePtr@@VCCallDisposition@Rtl@BUCL@@@BUCL@@QEAA?AVCCallDisposition@Rtl@2@_K@Z; BUCL::CVector<NullableChildNodePtr,BUCL::Rtl::CCallDisposition>::Resize(unsigned __int64)
0x180047d41  mov     ebx, [rax]
0x180047d43  test    ebx, ebx
0x180047d45  js      short loc_180047D6E
0x180047d47  movaps  xmm0, [rbp+57h+var_20]
0x180047d4b  lea     r9, [rbp+57h+var_A8]; struct CChildNode **
0x180047d4f  and     [rbp+57h+var_A8], 0
0x180047d54  lea     rdx, [rbp+57h+var_60]; struct Node
0x180047d58  xor     r8d, r8d; struct CElementModification *
0x180047d5b  movdqa  xmmword ptr [rbp+57h+var_60.lpVtbl], xmm0
0x180047d60  mov     rcx, rdi; this
0x180047d63  call    ?GetNodeUpdatePtr@CMicrodomUpdateContext@@QEAAJUNode@Rtl@Microdom@Windows@@PEAVCElementModification@@AEAPEAVCChildNode@@@Z; CMicrodomUpdateContext::GetNodeUpdatePtr(Windows::Microdom::Rtl::Node,CElementModification *,CChildNode * &)
0x180047d68  mov     ebx, eax
0x180047d6a  test    eax, eax
0x180047d6c  jns     short loc_180047DA5
0x180047d6e  mov     r8, [rbp+57h+P]; P
0x180047d72  test    r8, r8
0x180047d75  jz      loc_180047CB0
0x180047d7b  and     [rbp+57h+P], 0
0x180047d80  xor     edx, edx; Flags
0x180047d82  and     [rbp+57h+var_40], 0
0x180047d87  mov     rcx, gs:60h
0x180047d90  mov     rcx, [rcx+30h]; HeapHandle
0x180047d94  call    cs:__imp_RtlFreeHeap
0x180047d9b  nop     dword ptr [rax+rax+00h]
0x180047da0  jmp     loc_180047CB0
0x180047da5  mov     r8, [rbp+57h+P]; P
0x180047da9  test    r8, r8
0x180047dac  jz      short loc_180047DD3
0x180047dae  and     [rbp+57h+P], 0
0x180047db3  xor     edx, edx; Flags
0x180047db5  and     [rbp+57h+var_40], 0
0x180047dba  mov     rcx, gs:60h
0x180047dc3  mov     rcx, [rcx+30h]; HeapHandle
0x180047dc7  call    cs:__imp_RtlFreeHeap
0x180047dce  nop     dword ptr [rax+rax+00h]
0x180047dd3  xor     eax, eax
0x180047dd5  mov     rcx, [rbp+57h+var_10]
0x180047dd9  xor     rcx, rsp; StackCookie
0x180047ddc  call    __security_check_cookie
0x180047de1  lea     r11, [rsp+0D0h+var_s0]
0x180047de9  mov     rbx, [r11+20h]
0x180047ded  mov     rdi, [r11+28h]
0x180047df1  mov     rsp, r11
0x180047df4  pop     rbp
0x180047df5  retn
```
