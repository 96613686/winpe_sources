# CWdsTransportServer::CreateInstance(ushort const *,IWdsTransportServer * *)

- ea: `0x180008afc`
- end: `0x180008c01`
- name: `?CreateInstance@CWdsTransportServer@@SAJPEBGPEAPEAUIWdsTransportServer@@@Z`
- size: `261`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct IWdsTransportServer **)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800084a0`

## callees

- `0x180008a30`
- `0x180008afc`
- `0x180008ee4`
- `0x180009af8`
- `0x180020010`

## import_xrefs

- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180008b2f`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180008bdd`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180008b2f`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180008bdd`

## string_xrefs

- `0x180008b13`: `-> CWdsTransportServer::CreateInstance`
- `0x180008bca`: `<- CWdsTransportServer::CreateInstance=%x`

## pseudocode

```c
__int64 __fastcall CWdsTransportServer::CreateInstance(const unsigned __int16 *a1, struct IWdsTransportServer **a2)
{
  unsigned __int16 **v4; // rbx
  __int64 v5; // rdi
  __int64 v6; // rdx
  __int64 v7; // r8
  int v8; // eax
  __int64 v9; // rdx
  __int64 v10; // r8
  CWdsTransportServer *v12; // [rsp+30h] [rbp+8h] BYREF

  v4 = 0;
  v12 = 0;
  CTrace::Trace((CTrace *)qword_18003B770, 0x10000u, L"-> CWdsTransportServer::CreateInstance");
  if ( a1 && a2 )
  {
    v5 = (unsigned int)ATL::CComObject<CWdsTransportServer>::CreateInstance(&v12);
    v8 = ElValidateHr_1(v5, v6, v7, 80);
    v4 = (unsigned __int16 **)v12;
    if ( v8 >= 0 )
    {
      (*(void (__fastcall **)(CWdsTransportServer *))(*(_QWORD *)v12 + 8LL))(v12);
      v5 = (unsigned int)CWdsTransportServer::Initialize(v4, a1);
      if ( (int)ElValidateHr_1(v5, v9, v10, 88) >= 0 )
        LODWORD(v5) = (*(__int64 (__fastcall **)(unsigned __int16 **, GUID *, struct IWdsTransportServer **))*v4)(
                        v4,
                        &IID_IWdsTransportServer,
                        a2);
    }
  }
  else
  {
    LODWORD(v5) = -2147024809;
  }
  if ( v4 )
    (*((void (__fastcall **)(unsigned __int16 **))*v4 + 2))(v4);
  CTrace::Trace((CTrace *)qword_18003B770, 0x10000u, L"<- CWdsTransportServer::CreateInstance=%x", (unsigned int)v5);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180008afc  mov     rax, rsp
0x180008aff  mov     [rax+10h], rbx
0x180008b03  mov     [rax+18h], rbp
0x180008b07  mov     [rax+20h], rsi
0x180008b0b  push    rdi
0x180008b0c  sub     rsp, 20h
0x180008b10  mov     rsi, rdx
0x180008b13  lea     r8, aCwdstransports_64; "-> CWdsTransportServer::CreateInstance"
0x180008b1a  mov     rbp, rcx
0x180008b1d  xor     ebx, ebx
0x180008b1f  mov     edx, 10000h
0x180008b24  mov     [rax+8], rbx
0x180008b28  lea     rcx, qword_18003B770
0x180008b2f  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x180008b36  nop     dword ptr [rax+rax+00h]
0x180008b3b  test    rbp, rbp
0x180008b3e  jz      short loc_180008BAE
0x180008b40  test    rsi, rsi
0x180008b43  jz      short loc_180008BAE
0x180008b45  lea     rcx, [rsp+28h+arg_0]
0x180008b4a  call    ?CreateInstance@?$CComObject@VCWdsTransportServer@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CWdsTransportServer>::CreateInstance(ATL::CComObject<CWdsTransportServer> * *)
0x180008b4f  lea     r9d, [rbx+50h]
0x180008b53  mov     ecx, eax
0x180008b55  mov     edi, eax
0x180008b57  call    ElValidateHr_1
0x180008b5c  mov     rbx, [rsp+28h+arg_0]
0x180008b61  test    eax, eax
0x180008b63  js      short loc_180008BB3
0x180008b65  mov     rax, [rbx]
0x180008b68  mov     rcx, rbx
0x180008b6b  mov     rax, [rax+8]
0x180008b6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008b74  mov     rdx, rbp; unsigned __int16 *
0x180008b77  mov     rcx, rbx; this
0x180008b7a  call    ?Initialize@CWdsTransportServer@@AEAAJPEBG@Z; CWdsTransportServer::Initialize(ushort const *)
0x180008b7f  mov     r9d, 58h ; 'X'
0x180008b85  mov     ecx, eax
0x180008b87  mov     edi, eax
0x180008b89  call    ElValidateHr_1
0x180008b8e  test    eax, eax
0x180008b90  js      short loc_180008BB3
0x180008b92  mov     rax, [rbx]
0x180008b95  lea     rdx, IID_IWdsTransportServer
0x180008b9c  mov     r8, rsi
0x180008b9f  mov     rcx, rbx
0x180008ba2  mov     rax, [rax]
0x180008ba5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008baa  mov     edi, eax
0x180008bac  jmp     short loc_180008BB3
0x180008bae  mov     edi, 80070057h
0x180008bb3  test    rbx, rbx
0x180008bb6  jz      short loc_180008BC7
0x180008bb8  mov     rax, [rbx]
0x180008bbb  mov     rcx, rbx
0x180008bbe  mov     rax, [rax+10h]
0x180008bc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008bc7  mov     r9d, edi
0x180008bca  lea     r8, aCwdstransports_11; "<- CWdsTransportServer::CreateInstance="...
0x180008bd1  mov     edx, 10000h
0x180008bd6  lea     rcx, qword_18003B770
0x180008bdd  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x180008be4  nop     dword ptr [rax+rax+00h]
0x180008be9  mov     rbx, [rsp+28h+arg_8]
0x180008bee  mov     eax, edi
0x180008bf0  mov     rbp, [rsp+28h+arg_10]
0x180008bf5  mov     rsi, [rsp+28h+arg_18]
0x180008bfa  add     rsp, 20h
0x180008bfe  pop     rdi
0x180008bff  retn
```
