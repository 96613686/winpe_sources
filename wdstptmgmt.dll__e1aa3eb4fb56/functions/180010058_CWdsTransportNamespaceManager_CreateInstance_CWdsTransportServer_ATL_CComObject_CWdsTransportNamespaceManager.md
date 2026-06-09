# CWdsTransportNamespaceManager::CreateInstance(CWdsTransportServer *,ATL::CComObject<CWdsTransportNamespaceManager> * *)

- ea: `0x180010058`
- end: `0x180010155`
- name: `?CreateInstance@CWdsTransportNamespaceManager@@SAJPEAVCWdsTransportServer@@PEAPEAV?$CComObject@VCWdsTransportNamespaceManager@@@ATL@@@Z`
- size: `253`
- prototype: `__int64 __fastcall(struct CWdsTransportServer *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180009000`

## callees

- `0x18000ff30`
- `0x180010058`
- `0x180010444`
- `0x180010984`
- `0x180020010`

## import_xrefs

- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18001008b`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180010131`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18001008b`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180010131`

## string_xrefs

- `0x18001006f`: `-> CWdsTransportNamespaceManager::CreateInstance`
- `0x18001011e`: `<- CWdsTransportNamespaceManager::CreateInstance=%x`

## pseudocode

```c
__int64 __fastcall CWdsTransportNamespaceManager::CreateInstance(
        struct CWdsTransportServer *a1,
        CWdsTransportNamespaceManager **a2)
{
  CWdsTransportNamespaceManager *v4; // rbx
  __int64 v5; // rdi
  __int64 v6; // rdx
  __int64 v7; // r8
  int v8; // eax
  __int64 v9; // rdx
  __int64 v10; // r8
  CWdsTransportNamespaceManager *v12; // [rsp+30h] [rbp+8h] BYREF

  v4 = 0;
  v12 = 0;
  CTrace::Trace((CTrace *)qword_18003B770, 0x10000u, L"-> CWdsTransportNamespaceManager::CreateInstance");
  if ( a1 && a2 )
  {
    v5 = (unsigned int)ATL::CComObject<CWdsTransportNamespaceManager>::CreateInstance(&v12);
    v8 = ElValidateHr_6(v5, v6, v7, 82);
    v4 = v12;
    if ( v8 >= 0 )
    {
      (*(void (__fastcall **)(CWdsTransportNamespaceManager *))(*(_QWORD *)v12 + 8LL))(v12);
      v5 = (unsigned int)CWdsTransportNamespaceManager::Initialize(v4, a1);
      if ( (int)ElValidateHr_6(v5, v9, v10, 90) >= 0 )
      {
        (*(void (__fastcall **)(CWdsTransportNamespaceManager *))(*(_QWORD *)v4 + 8LL))(v4);
        *a2 = v4;
      }
    }
  }
  else
  {
    LODWORD(v5) = -2147024809;
  }
  if ( v4 )
    (*(void (__fastcall **)(CWdsTransportNamespaceManager *))(*(_QWORD *)v4 + 16LL))(v4);
  CTrace::Trace(
    (CTrace *)qword_18003B770,
    0x10000u,
    L"<- CWdsTransportNamespaceManager::CreateInstance=%x",
    (unsigned int)v5);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180010058  mov     rax, rsp
0x18001005b  mov     [rax+10h], rbx
0x18001005f  mov     [rax+18h], rbp
0x180010063  mov     [rax+20h], rsi
0x180010067  push    rdi
0x180010068  sub     rsp, 20h
0x18001006c  mov     rsi, rdx
0x18001006f  lea     r8, aCwdstransportn_23; "-> CWdsTransportNamespaceManager::Creat"...
0x180010076  mov     rbp, rcx
0x180010079  xor     ebx, ebx
0x18001007b  mov     edx, 10000h
0x180010080  mov     [rax+8], rbx
0x180010084  lea     rcx, qword_18003B770
0x18001008b  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x180010092  nop     dword ptr [rax+rax+00h]
0x180010097  test    rbp, rbp
0x18001009a  jz      short loc_180010102
0x18001009c  test    rsi, rsi
0x18001009f  jz      short loc_180010102
0x1800100a1  lea     rcx, [rsp+28h+arg_0]
0x1800100a6  call    ?CreateInstance@?$CComObject@VCWdsTransportNamespaceManager@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CWdsTransportNamespaceManager>::CreateInstance(ATL::CComObject<CWdsTransportNamespaceManager> * *)
0x1800100ab  lea     r9d, [rbx+52h]
0x1800100af  mov     ecx, eax
0x1800100b1  mov     edi, eax
0x1800100b3  call    ElValidateHr_6
0x1800100b8  mov     rbx, [rsp+28h+arg_0]
0x1800100bd  test    eax, eax
0x1800100bf  js      short loc_180010107
0x1800100c1  mov     rax, [rbx]
0x1800100c4  mov     rcx, rbx
0x1800100c7  mov     rax, [rax+8]
0x1800100cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800100d0  mov     rdx, rbp; struct CWdsTransportServer *
0x1800100d3  mov     rcx, rbx; this
0x1800100d6  call    ?Initialize@CWdsTransportNamespaceManager@@AEAAJPEAVCWdsTransportServer@@@Z; CWdsTransportNamespaceManager::Initialize(CWdsTransportServer *)
0x1800100db  mov     r9d, 5Ah ; 'Z'
0x1800100e1  mov     ecx, eax
0x1800100e3  mov     edi, eax
0x1800100e5  call    ElValidateHr_6
0x1800100ea  test    eax, eax
0x1800100ec  js      short loc_180010107
0x1800100ee  mov     rax, [rbx]
0x1800100f1  mov     rcx, rbx
0x1800100f4  mov     rax, [rax+8]
0x1800100f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800100fd  mov     [rsi], rbx
0x180010100  jmp     short loc_180010107
0x180010102  mov     edi, 80070057h
0x180010107  test    rbx, rbx
0x18001010a  jz      short loc_18001011B
0x18001010c  mov     rax, [rbx]
0x18001010f  mov     rcx, rbx
0x180010112  mov     rax, [rax+10h]
0x180010116  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001011b  mov     r9d, edi
0x18001011e  lea     r8, aCwdstransportn_61; "<- CWdsTransportNamespaceManager::Creat"...
0x180010125  mov     edx, 10000h
0x18001012a  lea     rcx, qword_18003B770
0x180010131  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x180010138  nop     dword ptr [rax+rax+00h]
0x18001013d  mov     rbx, [rsp+28h+arg_8]
0x180010142  mov     eax, edi
0x180010144  mov     rbp, [rsp+28h+arg_10]
0x180010149  mov     rsi, [rsp+28h+arg_18]
0x18001014e  add     rsp, 20h
0x180010152  pop     rdi
0x180010153  retn
```
