# CWdsTransportTftpManager::CreateInstance(CWdsTransportServer *,ATL::CComObject<CWdsTransportTftpManager> * *)

- ea: `0x180019878`
- end: `0x18001996d`
- name: `?CreateInstance@CWdsTransportTftpManager@@SAJPEAVCWdsTransportServer@@PEAPEAV?$CComObject@VCWdsTransportTftpManager@@@ATL@@@Z`
- size: `245`
- prototype: `__int64 __fastcall(struct CWdsTransportServer *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180009000`

## callees

- `0x180019750`
- `0x180019878`
- `0x180019b14`
- `0x180019ecc`
- `0x180020010`

## import_xrefs

- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x1800198aa`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180019949`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x1800198aa`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180019949`

## string_xrefs

- `0x180019891`: `-> CWdsTransportTftpManager::CreateInstance`
- `0x180019936`: `<- CWdsTransportTftpManager::CreateInstance=%x`

## pseudocode

```c
__int64 __fastcall CWdsTransportTftpManager::CreateInstance(struct CWdsTransportServer *a1, __int64 a2)
{
  __int64 v4; // rdi
  __int64 v5; // rdx
  __int64 v6; // r8
  int v7; // eax
  CWdsTransportTftpManager *v8; // rbx
  __int64 v9; // rdx
  __int64 v10; // r8
  CWdsTransportTftpManager *v12; // [rsp+40h] [rbp+18h] BYREF

  v12 = 0;
  CTrace::Trace((CTrace *)qword_18003B770, 0x10000u, L"-> CWdsTransportTftpManager::CreateInstance");
  v4 = (unsigned int)ATL::CComObject<CWdsTransportTftpManager>::CreateInstance(&v12);
  v7 = ElValidateHr_15(v4, v5, v6, 64);
  v8 = v12;
  if ( v7 >= 0 )
  {
    (*(void (__fastcall **)(CWdsTransportTftpManager *))(*(_QWORD *)v12 + 8LL))(v12);
    v4 = (unsigned int)CWdsTransportTftpManager::Initialize(v8, a1);
    if ( (int)ElValidateHr_15(v4, v9, v10, 72) >= 0 )
      LODWORD(v4) = (**(__int64 (__fastcall ***)(CWdsTransportTftpManager *, GUID *, __int64))v8)(
                      v8,
                      &IID_IWdsTransportTftpManager,
                      a2);
  }
  if ( v8 )
    (*(void (__fastcall **)(CWdsTransportTftpManager *))(*(_QWORD *)v8 + 16LL))(v8);
  CTrace::Trace(
    (CTrace *)qword_18003B770,
    0x10000u,
    L"<- CWdsTransportTftpManager::CreateInstance=%x",
    (unsigned int)v4);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180019878  mov     rax, rsp
0x18001987b  mov     [rax+8], rbx
0x18001987f  mov     [rax+10h], rbp
0x180019883  mov     [rax+20h], rsi
0x180019887  push    rdi
0x180019888  sub     rsp, 20h
0x18001988c  and     qword ptr [rax+18h], 0
0x180019891  lea     r8, aCwdstransportt_12; "-> CWdsTransportTftpManager::CreateInst"...
0x180019898  mov     rsi, rdx
0x18001989b  mov     rbp, rcx
0x18001989e  mov     edx, 10000h
0x1800198a3  lea     rcx, qword_18003B770
0x1800198aa  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x1800198b1  nop     dword ptr [rax+rax+00h]
0x1800198b6  lea     rcx, [rsp+28h+arg_10]
0x1800198bb  call    ?CreateInstance@?$CComObject@VCWdsTransportTftpManager@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CWdsTransportTftpManager>::CreateInstance(ATL::CComObject<CWdsTransportTftpManager> * *)
0x1800198c0  mov     r9d, 40h ; '@'
0x1800198c6  mov     ecx, eax
0x1800198c8  mov     edi, eax
0x1800198ca  call    ElValidateHr_15
0x1800198cf  mov     rbx, [rsp+28h+arg_10]
0x1800198d4  test    eax, eax
0x1800198d6  js      short loc_18001991F
0x1800198d8  mov     rax, [rbx]
0x1800198db  mov     rcx, rbx
0x1800198de  mov     rax, [rax+8]
0x1800198e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800198e7  mov     rdx, rbp; struct CWdsTransportServer *
0x1800198ea  mov     rcx, rbx; this
0x1800198ed  call    ?Initialize@CWdsTransportTftpManager@@AEAAJPEAVCWdsTransportServer@@@Z; CWdsTransportTftpManager::Initialize(CWdsTransportServer *)
0x1800198f2  mov     r9d, 48h ; 'H'
0x1800198f8  mov     ecx, eax
0x1800198fa  mov     edi, eax
0x1800198fc  call    ElValidateHr_15
0x180019901  test    eax, eax
0x180019903  js      short loc_18001991F
0x180019905  mov     rax, [rbx]
0x180019908  lea     rdx, IID_IWdsTransportTftpManager
0x18001990f  mov     r8, rsi
0x180019912  mov     rcx, rbx
0x180019915  mov     rax, [rax]
0x180019918  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001991d  mov     edi, eax
0x18001991f  test    rbx, rbx
0x180019922  jz      short loc_180019933
0x180019924  mov     rax, [rbx]
0x180019927  mov     rcx, rbx
0x18001992a  mov     rax, [rax+10h]
0x18001992e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019933  mov     r9d, edi
0x180019936  lea     r8, aCwdstransportt_10; "<- CWdsTransportTftpManager::CreateInst"...
0x18001993d  mov     edx, 10000h
0x180019942  lea     rcx, qword_18003B770
0x180019949  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x180019950  nop     dword ptr [rax+rax+00h]
0x180019955  mov     rbx, [rsp+28h+arg_0]
0x18001995a  mov     eax, edi
0x18001995c  mov     rbp, [rsp+28h+arg_8]
0x180019961  mov     rsi, [rsp+28h+arg_18]
0x180019966  add     rsp, 20h
0x18001996a  pop     rdi
0x18001996b  retn
```
