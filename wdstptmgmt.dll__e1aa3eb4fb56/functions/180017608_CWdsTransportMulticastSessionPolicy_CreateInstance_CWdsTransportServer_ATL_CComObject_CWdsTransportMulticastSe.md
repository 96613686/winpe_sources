# CWdsTransportMulticastSessionPolicy::CreateInstance(CWdsTransportServer *,ATL::CComObject<CWdsTransportMulticastSessionPolicy> * *)

- ea: `0x180017608`
- end: `0x180017705`
- name: `?CreateInstance@CWdsTransportMulticastSessionPolicy@@SAJPEAVCWdsTransportServer@@PEAPEAV?$CComObject@VCWdsTransportMulticastSessionPolicy@@@ATL@@@Z`
- size: `253`
- prototype: `__int64 __fastcall(struct CWdsTransportServer *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000b9a4`

## callees

- `0x1800174c4`
- `0x180017608`
- `0x1800178e4`
- `0x18001811c`
- `0x180020010`

## import_xrefs

- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18001763b`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x1800176e1`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18001763b`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x1800176e1`

## string_xrefs

- `0x18001761f`: `-> CWdsTransportMulticastSessionPolicy::CreateInstance`
- `0x1800176ce`: `<- CWdsTransportMulticastSessionPolicy::CreateInstance=%x`

## pseudocode

```c
__int64 __fastcall CWdsTransportMulticastSessionPolicy::CreateInstance(
        struct CWdsTransportServer *a1,
        CWdsTransportMulticastSessionPolicy **a2)
{
  CWdsTransportMulticastSessionPolicy *v4; // rbx
  __int64 v5; // rdi
  __int64 v6; // rdx
  __int64 v7; // r8
  int v8; // eax
  __int64 v9; // rdx
  __int64 v10; // r8
  CWdsTransportMulticastSessionPolicy *v12; // [rsp+30h] [rbp+8h] BYREF

  v4 = 0;
  v12 = 0;
  CTrace::Trace((CTrace *)qword_18003B770, 0x10000u, L"-> CWdsTransportMulticastSessionPolicy::CreateInstance");
  if ( a1 && a2 )
  {
    v5 = (unsigned int)ATL::CComObject<CWdsTransportMulticastSessionPolicy>::CreateInstance(&v12);
    v8 = ElValidateHr_12(v5, v6, v7, 78);
    v4 = v12;
    if ( v8 >= 0 )
    {
      (*(void (__fastcall **)(CWdsTransportMulticastSessionPolicy *))(*(_QWORD *)v12 + 8LL))(v12);
      v5 = (unsigned int)CWdsTransportMulticastSessionPolicy::Initialize(v4, a1);
      if ( (int)ElValidateHr_12(v5, v9, v10, 86) >= 0 )
      {
        (*(void (__fastcall **)(CWdsTransportMulticastSessionPolicy *))(*(_QWORD *)v4 + 8LL))(v4);
        *a2 = v4;
      }
    }
  }
  else
  {
    LODWORD(v5) = -2147024809;
  }
  if ( v4 )
    (*(void (__fastcall **)(CWdsTransportMulticastSessionPolicy *))(*(_QWORD *)v4 + 16LL))(v4);
  CTrace::Trace(
    (CTrace *)qword_18003B770,
    0x10000u,
    L"<- CWdsTransportMulticastSessionPolicy::CreateInstance=%x",
    (unsigned int)v5);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180017608  mov     rax, rsp
0x18001760b  mov     [rax+10h], rbx
0x18001760f  mov     [rax+18h], rbp
0x180017613  mov     [rax+20h], rsi
0x180017617  push    rdi
0x180017618  sub     rsp, 20h
0x18001761c  mov     rsi, rdx
0x18001761f  lea     r8, aCwdstransportm_2; "-> CWdsTransportMulticastSessionPolicy:"...
0x180017626  mov     rbp, rcx
0x180017629  xor     ebx, ebx
0x18001762b  mov     edx, 10000h
0x180017630  mov     [rax+8], rbx
0x180017634  lea     rcx, qword_18003B770
0x18001763b  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x180017642  nop     dword ptr [rax+rax+00h]
0x180017647  test    rbp, rbp
0x18001764a  jz      short loc_1800176B2
0x18001764c  test    rsi, rsi
0x18001764f  jz      short loc_1800176B2
0x180017651  lea     rcx, [rsp+28h+arg_0]
0x180017656  call    ?CreateInstance@?$CComObject@VCWdsTransportMulticastSessionPolicy@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CWdsTransportMulticastSessionPolicy>::CreateInstance(ATL::CComObject<CWdsTransportMulticastSessionPolicy> * *)
0x18001765b  lea     r9d, [rbx+4Eh]
0x18001765f  mov     ecx, eax
0x180017661  mov     edi, eax
0x180017663  call    ElValidateHr_12
0x180017668  mov     rbx, [rsp+28h+arg_0]
0x18001766d  test    eax, eax
0x18001766f  js      short loc_1800176B7
0x180017671  mov     rax, [rbx]
0x180017674  mov     rcx, rbx
0x180017677  mov     rax, [rax+8]
0x18001767b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017680  mov     rdx, rbp; struct CWdsTransportServer *
0x180017683  mov     rcx, rbx; this
0x180017686  call    ?Initialize@CWdsTransportMulticastSessionPolicy@@AEAAJPEAVCWdsTransportServer@@@Z; CWdsTransportMulticastSessionPolicy::Initialize(CWdsTransportServer *)
0x18001768b  mov     r9d, 56h ; 'V'
0x180017691  mov     ecx, eax
0x180017693  mov     edi, eax
0x180017695  call    ElValidateHr_12
0x18001769a  test    eax, eax
0x18001769c  js      short loc_1800176B7
0x18001769e  mov     rax, [rbx]
0x1800176a1  mov     rcx, rbx
0x1800176a4  mov     rax, [rax+8]
0x1800176a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800176ad  mov     [rsi], rbx
0x1800176b0  jmp     short loc_1800176B7
0x1800176b2  mov     edi, 80070057h
0x1800176b7  test    rbx, rbx
0x1800176ba  jz      short loc_1800176CB
0x1800176bc  mov     rax, [rbx]
0x1800176bf  mov     rcx, rbx
0x1800176c2  mov     rax, [rax+10h]
0x1800176c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800176cb  mov     r9d, edi
0x1800176ce  lea     r8, aCwdstransportm_17; "<- CWdsTransportMulticastSessionPolicy:"...
0x1800176d5  mov     edx, 10000h
0x1800176da  lea     rcx, qword_18003B770
0x1800176e1  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x1800176e8  nop     dword ptr [rax+rax+00h]
0x1800176ed  mov     rbx, [rsp+28h+arg_8]
0x1800176f2  mov     eax, edi
0x1800176f4  mov     rbp, [rsp+28h+arg_10]
0x1800176f9  mov     rsi, [rsp+28h+arg_18]
0x1800176fe  add     rsp, 20h
0x180017702  pop     rdi
0x180017703  retn
```
