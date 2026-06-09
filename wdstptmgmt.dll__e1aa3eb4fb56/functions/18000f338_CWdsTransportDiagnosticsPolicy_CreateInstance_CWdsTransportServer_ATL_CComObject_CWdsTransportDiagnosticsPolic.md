# CWdsTransportDiagnosticsPolicy::CreateInstance(CWdsTransportServer *,ATL::CComObject<CWdsTransportDiagnosticsPolicy> * *)

- ea: `0x18000f338`
- end: `0x18000f435`
- name: `?CreateInstance@CWdsTransportDiagnosticsPolicy@@SAJPEAVCWdsTransportServer@@PEAPEAV?$CComObject@VCWdsTransportDiagnosticsPolicy@@@ATL@@@Z`
- size: `253`
- prototype: `__int64 __fastcall(struct CWdsTransportServer *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000b9a4`

## callees

- `0x18000f204`
- `0x18000f338`
- `0x18000f5e4`
- `0x18000fca8`
- `0x180020010`

## import_xrefs

- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000f36b`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000f411`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000f36b`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000f411`

## string_xrefs

- `0x18000f34f`: `-> CWdsTransportDiagnosticsPolicy::CreateInstance`
- `0x18000f3fe`: `<- CWdsTransportDiagnosticsPolicy::CreateInstance=%x`

## pseudocode

```c
__int64 __fastcall CWdsTransportDiagnosticsPolicy::CreateInstance(
        struct CWdsTransportServer *a1,
        CWdsTransportDiagnosticsPolicy **a2)
{
  CWdsTransportDiagnosticsPolicy *v4; // rbx
  __int64 v5; // rdi
  __int64 v6; // rdx
  __int64 v7; // r8
  int v8; // eax
  __int64 v9; // rdx
  __int64 v10; // r8
  CWdsTransportDiagnosticsPolicy *v12; // [rsp+30h] [rbp+8h] BYREF

  v4 = 0;
  v12 = 0;
  CTrace::Trace((CTrace *)qword_18003B770, 0x10000u, L"-> CWdsTransportDiagnosticsPolicy::CreateInstance");
  if ( a1 && a2 )
  {
    v5 = (unsigned int)ATL::CComObject<CWdsTransportDiagnosticsPolicy>::CreateInstance(&v12);
    v8 = ElValidateHr_5(v5, v6, v7, 78);
    v4 = v12;
    if ( v8 >= 0 )
    {
      (*(void (__fastcall **)(CWdsTransportDiagnosticsPolicy *))(*(_QWORD *)v12 + 8LL))(v12);
      v5 = (unsigned int)CWdsTransportDiagnosticsPolicy::Initialize(v4, a1);
      if ( (int)ElValidateHr_5(v5, v9, v10, 86) >= 0 )
      {
        (*(void (__fastcall **)(CWdsTransportDiagnosticsPolicy *))(*(_QWORD *)v4 + 8LL))(v4);
        *a2 = v4;
      }
    }
  }
  else
  {
    LODWORD(v5) = -2147024809;
  }
  if ( v4 )
    (*(void (__fastcall **)(CWdsTransportDiagnosticsPolicy *))(*(_QWORD *)v4 + 16LL))(v4);
  CTrace::Trace(
    (CTrace *)qword_18003B770,
    0x10000u,
    L"<- CWdsTransportDiagnosticsPolicy::CreateInstance=%x",
    (unsigned int)v5);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18000f338  mov     rax, rsp
0x18000f33b  mov     [rax+10h], rbx
0x18000f33f  mov     [rax+18h], rbp
0x18000f343  mov     [rax+20h], rsi
0x18000f347  push    rdi
0x18000f348  sub     rsp, 20h
0x18000f34c  mov     rsi, rdx
0x18000f34f  lea     r8, aCwdstransportd_3; "-> CWdsTransportDiagnosticsPolicy::Crea"...
0x18000f356  mov     rbp, rcx
0x18000f359  xor     ebx, ebx
0x18000f35b  mov     edx, 10000h
0x18000f360  mov     [rax+8], rbx
0x18000f364  lea     rcx, qword_18003B770
0x18000f36b  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x18000f372  nop     dword ptr [rax+rax+00h]
0x18000f377  test    rbp, rbp
0x18000f37a  jz      short loc_18000F3E2
0x18000f37c  test    rsi, rsi
0x18000f37f  jz      short loc_18000F3E2
0x18000f381  lea     rcx, [rsp+28h+arg_0]
0x18000f386  call    ?CreateInstance@?$CComObject@VCWdsTransportDiagnosticsPolicy@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CWdsTransportDiagnosticsPolicy>::CreateInstance(ATL::CComObject<CWdsTransportDiagnosticsPolicy> * *)
0x18000f38b  lea     r9d, [rbx+4Eh]
0x18000f38f  mov     ecx, eax
0x18000f391  mov     edi, eax
0x18000f393  call    ElValidateHr_5
0x18000f398  mov     rbx, [rsp+28h+arg_0]
0x18000f39d  test    eax, eax
0x18000f39f  js      short loc_18000F3E7
0x18000f3a1  mov     rax, [rbx]
0x18000f3a4  mov     rcx, rbx
0x18000f3a7  mov     rax, [rax+8]
0x18000f3ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f3b0  mov     rdx, rbp; struct CWdsTransportServer *
0x18000f3b3  mov     rcx, rbx; this
0x18000f3b6  call    ?Initialize@CWdsTransportDiagnosticsPolicy@@AEAAJPEAVCWdsTransportServer@@@Z; CWdsTransportDiagnosticsPolicy::Initialize(CWdsTransportServer *)
0x18000f3bb  mov     r9d, 56h ; 'V'
0x18000f3c1  mov     ecx, eax
0x18000f3c3  mov     edi, eax
0x18000f3c5  call    ElValidateHr_5
0x18000f3ca  test    eax, eax
0x18000f3cc  js      short loc_18000F3E7
0x18000f3ce  mov     rax, [rbx]
0x18000f3d1  mov     rcx, rbx
0x18000f3d4  mov     rax, [rax+8]
0x18000f3d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f3dd  mov     [rsi], rbx
0x18000f3e0  jmp     short loc_18000F3E7
0x18000f3e2  mov     edi, 80070057h
0x18000f3e7  test    rbx, rbx
0x18000f3ea  jz      short loc_18000F3FB
0x18000f3ec  mov     rax, [rbx]
0x18000f3ef  mov     rcx, rbx
0x18000f3f2  mov     rax, [rax+10h]
0x18000f3f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f3fb  mov     r9d, edi
0x18000f3fe  lea     r8, aCwdstransportd_10; "<- CWdsTransportDiagnosticsPolicy::Crea"...
0x18000f405  mov     edx, 10000h
0x18000f40a  lea     rcx, qword_18003B770
0x18000f411  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x18000f418  nop     dword ptr [rax+rax+00h]
0x18000f41d  mov     rbx, [rsp+28h+arg_8]
0x18000f422  mov     eax, edi
0x18000f424  mov     rbp, [rsp+28h+arg_10]
0x18000f429  mov     rsi, [rsp+28h+arg_18]
0x18000f42e  add     rsp, 20h
0x18000f432  pop     rdi
0x18000f433  retn
```
