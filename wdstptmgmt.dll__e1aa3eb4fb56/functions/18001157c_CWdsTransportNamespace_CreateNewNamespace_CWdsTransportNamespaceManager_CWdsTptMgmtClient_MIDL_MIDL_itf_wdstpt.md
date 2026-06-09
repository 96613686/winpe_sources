# CWdsTransportNamespace::CreateNewNamespace(CWdsTransportNamespaceManager *,CWdsTptMgmtClient *,__MIDL___MIDL_itf_wdstptmgmt_0000_0000_0003,ushort *,ushort *,ushort *,IWdsTransportNamespace * *)

- ea: `0x18001157c`
- end: `0x180011704`
- name: `?CreateNewNamespace@CWdsTransportNamespace@@SAJPEAVCWdsTransportNamespaceManager@@PEAVCWdsTptMgmtClient@@W4__MIDL___MIDL_itf_wdstptmgmt_0000_0000_0003@@PEAG33PEAPEAUIWdsTransportNamespace@@@Z`
- size: `392`
- prototype: `__int64 __fastcall(struct CWdsTransportNamespaceManager *, struct CWdsTptMgmtClient *, enum __MIDL___MIDL_itf_wdstptmgmt_0000_0000_0003, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, struct IWdsTransportNamespace **)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180010160`
- `0x180010e24`

## callees

- `0x180011448`
- `0x18001157c`
- `0x180011db4`
- `0x1800137c4`
- `0x180020010`

## import_xrefs

- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x1800115c1`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x1800116d8`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x1800115c1`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x1800116d8`

## string_xrefs

- `0x1800115a1`: `-> CWdsTransportNamespace::CreateNewNamespace`
- `0x1800116c5`: `<- CWdsTransportNamespace::CreateNewNamespace=%x`

## pseudocode

```c
__int64 __fastcall CWdsTransportNamespace::CreateNewNamespace(
        struct CWdsTransportNamespaceManager *a1,
        struct CWdsTptMgmtClient *a2,
        enum __MIDL___MIDL_itf_wdstptmgmt_0000_0000_0003 a3,
        unsigned __int16 *a4,
        unsigned __int16 *a5,
        unsigned __int16 *a6,
        struct IWdsTransportNamespace **a7)
{
  CWdsTransportNamespace *v10; // rbx
  unsigned __int16 *v12; // rsi
  unsigned __int16 *v13; // r15
  struct IWdsTransportNamespace **v14; // r14
  __int64 v15; // rdi
  __int64 v16; // rdx
  __int64 v17; // r8
  int v18; // eax
  __int64 v19; // rdx
  __int64 v20; // r8
  struct CWdsTransportNamespace *v22; // [rsp+60h] [rbp+8h] BYREF

  v10 = 0;
  v22 = 0;
  CTrace::Trace((CTrace *)qword_18003B770, 0x10000u, L"-> CWdsTransportNamespace::CreateNewNamespace");
  if ( a1 && a2 && a4 && *a4 && (v12 = a5) != 0 && *a5 && (v13 = a6) != 0 && (v14 = a7) != 0 )
  {
    v15 = (unsigned int)CWdsTransportNamespace::CreateNamespace(a3, &v22);
    v18 = ElValidateHr_7(v15, v16, v17, 196);
    v10 = v22;
    if ( v18 >= 0 )
    {
      (*(void (__fastcall **)(struct CWdsTransportNamespace *))(*(_QWORD *)v22 + 8LL))(v22);
      v15 = (unsigned int)CWdsTransportNamespace::InitializeNewNamespace(v10, a1, a2, a4, v12, v13);
      if ( (int)ElValidateHr_7(v15, v19, v20, 208) >= 0 )
        LODWORD(v15) = (**(__int64 (__fastcall ***)(CWdsTransportNamespace *, GUID *, struct IWdsTransportNamespace **))v10)(
                         v10,
                         &IID_IWdsTransportNamespace,
                         v14);
    }
  }
  else
  {
    LODWORD(v15) = -2147024809;
  }
  if ( v10 )
    (*(void (__fastcall **)(CWdsTransportNamespace *))(*(_QWORD *)v10 + 16LL))(v10);
  CTrace::Trace(
    (CTrace *)qword_18003B770,
    0x10000u,
    L"<- CWdsTransportNamespace::CreateNewNamespace=%x",
    (unsigned int)v15);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x18001157c  mov     rax, rsp
0x18001157f  mov     [rax+10h], rbx
0x180011583  mov     [rax+18h], rbp
0x180011587  mov     [rax+20h], rsi
0x18001158b  push    rdi
0x18001158c  push    r12
0x18001158e  push    r13
0x180011590  push    r14
0x180011592  push    r15
0x180011594  sub     rsp, 30h
0x180011598  mov     edi, r8d
0x18001159b  mov     r12, rdx
0x18001159e  mov     r13, rcx
0x1800115a1  lea     r8, aCwdstransportn_37; "-> CWdsTransportNamespace::CreateNewNam"...
0x1800115a8  xor     r14d, r14d
0x1800115ab  lea     rcx, qword_18003B770
0x1800115b2  mov     ebx, r14d
0x1800115b5  mov     edx, 10000h
0x1800115ba  mov     [rax+8], rbx
0x1800115be  mov     rbp, r9
0x1800115c1  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x1800115c8  nop     dword ptr [rax+rax+00h]
0x1800115cd  test    r13, r13
0x1800115d0  jz      loc_1800116A9
0x1800115d6  test    r12, r12
0x1800115d9  jz      loc_1800116A9
0x1800115df  test    rbp, rbp
0x1800115e2  jz      loc_1800116A9
0x1800115e8  cmp     [rbp+0], r14w
0x1800115ed  jz      loc_1800116A9
0x1800115f3  mov     rsi, [rsp+58h+arg_20]
0x1800115fb  test    rsi, rsi
0x1800115fe  jz      loc_1800116A9
0x180011604  cmp     [rsi], r14w
0x180011608  jz      loc_1800116A9
0x18001160e  mov     r15, [rsp+58h+arg_28]
0x180011616  test    r15, r15
0x180011619  jz      loc_1800116A9
0x18001161f  mov     r14, [rsp+58h+arg_30]
0x180011627  test    r14, r14
0x18001162a  jz      short loc_1800116A9
0x18001162c  lea     rdx, [rsp+58h+arg_0]; struct CWdsTransportNamespace **
0x180011631  mov     ecx, edi; enum __MIDL___MIDL_itf_wdstptmgmt_0000_0000_0003
0x180011633  call    ?CreateNamespace@CWdsTransportNamespace@@CAJW4__MIDL___MIDL_itf_wdstptmgmt_0000_0000_0003@@PEAPEAV1@@Z; CWdsTransportNamespace::CreateNamespace(__MIDL___MIDL_itf_wdstptmgmt_0000_0000_0003,CWdsTransportNamespace * *)
0x180011638  mov     r9d, 0C4h
0x18001163e  mov     ecx, eax
0x180011640  mov     edi, eax
0x180011642  call    ElValidateHr_7
0x180011647  mov     rbx, [rsp+58h+arg_0]
0x18001164c  test    eax, eax
0x18001164e  js      short loc_1800116AE
0x180011650  mov     rax, [rbx]
0x180011653  mov     rcx, rbx
0x180011656  mov     rax, [rax+8]
0x18001165a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001165f  mov     r9, rbp; unsigned __int16 *
0x180011662  mov     [rsp+58h+var_30], r15; unsigned __int16 *
0x180011667  mov     r8, r12; struct CWdsTptMgmtClient *
0x18001166a  mov     [rsp+58h+var_38], rsi; unsigned __int16 *
0x18001166f  mov     rdx, r13; struct CWdsTransportNamespaceManager *
0x180011672  mov     rcx, rbx; this
0x180011675  call    ?InitializeNewNamespace@CWdsTransportNamespace@@AEAAJPEAVCWdsTransportNamespaceManager@@PEAVCWdsTptMgmtClient@@PEAG22@Z; CWdsTransportNamespace::InitializeNewNamespace(CWdsTransportNamespaceManager *,CWdsTptMgmtClient *,ushort *,ushort *,ushort *)
0x18001167a  mov     r9d, 0D0h
0x180011680  mov     ecx, eax
0x180011682  mov     edi, eax
0x180011684  call    ElValidateHr_7
0x180011689  test    eax, eax
0x18001168b  js      short loc_1800116AE
0x18001168d  mov     rax, [rbx]
0x180011690  lea     rdx, IID_IWdsTransportNamespace
0x180011697  mov     r8, r14
0x18001169a  mov     rcx, rbx
0x18001169d  mov     rax, [rax]
0x1800116a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800116a5  mov     edi, eax
0x1800116a7  jmp     short loc_1800116AE
0x1800116a9  mov     edi, 80070057h
0x1800116ae  test    rbx, rbx
0x1800116b1  jz      short loc_1800116C2
0x1800116b3  mov     rax, [rbx]
0x1800116b6  mov     rcx, rbx
0x1800116b9  mov     rax, [rax+10h]
0x1800116bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800116c2  mov     r9d, edi
0x1800116c5  lea     r8, aCwdstransportn_73; "<- CWdsTransportNamespace::CreateNewNam"...
0x1800116cc  mov     edx, 10000h
0x1800116d1  lea     rcx, qword_18003B770
0x1800116d8  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x1800116df  nop     dword ptr [rax+rax+00h]
0x1800116e4  mov     rbx, [rsp+58h+arg_8]
0x1800116e9  mov     eax, edi
0x1800116eb  mov     rbp, [rsp+58h+arg_10]
0x1800116f0  mov     rsi, [rsp+58h+arg_18]
0x1800116f5  add     rsp, 30h
0x1800116f9  pop     r15
0x1800116fb  pop     r14
0x1800116fd  pop     r13
0x1800116ff  pop     r12
0x180011701  pop     rdi
0x180011702  retn
```
