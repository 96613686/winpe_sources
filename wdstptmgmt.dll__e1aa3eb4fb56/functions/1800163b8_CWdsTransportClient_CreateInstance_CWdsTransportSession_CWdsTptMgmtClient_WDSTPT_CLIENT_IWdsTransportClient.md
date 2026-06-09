# CWdsTransportClient::CreateInstance(CWdsTransportSession *,CWdsTptMgmtClient *,_WDSTPT_CLIENT *,IWdsTransportClient * *)

- ea: `0x1800163b8`
- end: `0x1800164db`
- name: `?CreateInstance@CWdsTransportClient@@SAJPEAVCWdsTransportSession@@PEAVCWdsTptMgmtClient@@PEAU_WDSTPT_CLIENT@@PEAPEAUIWdsTransportClient@@@Z`
- size: `291`
- prototype: `__int64 __fastcall(struct CWdsTransportSession *, struct CWdsTptMgmtClient *, struct _WDSTPT_CLIENT *, struct IWdsTransportClient **)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180015ae0`

## callees

- `0x1800162d0`
- `0x1800163b8`
- `0x1800167b4`
- `0x180016f20`
- `0x180020010`

## import_xrefs

- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x1800163f5`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x1800164b3`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x1800163f5`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x1800164b3`

## string_xrefs

- `0x1800163d9`: `-> CWdsTransportClient::CreateInstance`
- `0x1800164a0`: `<- CWdsTransportClient::CreateInstance=%x`

## pseudocode

```c
__int64 __fastcall CWdsTransportClient::CreateInstance(
        struct CWdsTransportSession *a1,
        struct CWdsTptMgmtClient *a2,
        struct _WDSTPT_CLIENT *a3,
        struct IWdsTransportClient **a4)
{
  CWdsTransportClient *v7; // rbx
  __int64 v9; // rdi
  __int64 v10; // rdx
  __int64 v11; // r8
  int v12; // eax
  __int64 v13; // rdx
  __int64 v14; // r8
  CWdsTransportClient *v16; // [rsp+40h] [rbp+8h] BYREF

  v7 = 0;
  v16 = 0;
  CTrace::Trace((CTrace *)qword_18003B770, 0x10000u, L"-> CWdsTransportClient::CreateInstance");
  if ( a1 && a2 && a3 && a4 )
  {
    v9 = (unsigned int)ATL::CComObject<CWdsTransportClient>::CreateInstance(&v16);
    v12 = ElValidateHr_11(v9, v10, v11, 86);
    v7 = v16;
    if ( v12 >= 0 )
    {
      (*(void (__fastcall **)(CWdsTransportClient *))(*(_QWORD *)v16 + 8LL))(v16);
      v9 = (unsigned int)CWdsTransportClient::Initialize(v7, a1, a2, a3);
      if ( (int)ElValidateHr_11(v9, v13, v14, 96) >= 0 )
        LODWORD(v9) = (**(__int64 (__fastcall ***)(CWdsTransportClient *, GUID *, struct IWdsTransportClient **))v7)(
                        v7,
                        &IID_IWdsTransportClient,
                        a4);
    }
  }
  else
  {
    LODWORD(v9) = -2147024809;
  }
  if ( v7 )
    (*(void (__fastcall **)(CWdsTransportClient *))(*(_QWORD *)v7 + 16LL))(v7);
  CTrace::Trace((CTrace *)qword_18003B770, 0x10000u, L"<- CWdsTransportClient::CreateInstance=%x", (unsigned int)v9);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800163b8  mov     rax, rsp
0x1800163bb  mov     [rax+10h], rbx
0x1800163bf  mov     [rax+18h], rbp
0x1800163c3  mov     [rax+20h], rsi
0x1800163c7  push    rdi
0x1800163c8  push    r14
0x1800163ca  push    r15
0x1800163cc  sub     rsp, 20h
0x1800163d0  mov     rbp, r8
0x1800163d3  mov     r14, rdx
0x1800163d6  mov     r15, rcx
0x1800163d9  lea     r8, aCwdstransportc_20; "-> CWdsTransportClient::CreateInstance"
0x1800163e0  xor     ebx, ebx
0x1800163e2  lea     rcx, qword_18003B770
0x1800163e9  mov     edx, 10000h
0x1800163ee  mov     [rax+8], rbx
0x1800163f2  mov     rsi, r9
0x1800163f5  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x1800163fc  nop     dword ptr [rax+rax+00h]
0x180016401  test    r15, r15
0x180016404  jz      short loc_180016484
0x180016406  test    r14, r14
0x180016409  jz      short loc_180016484
0x18001640b  test    rbp, rbp
0x18001640e  jz      short loc_180016484
0x180016410  test    rsi, rsi
0x180016413  jz      short loc_180016484
0x180016415  lea     rcx, [rsp+38h+arg_0]
0x18001641a  call    ?CreateInstance@?$CComObject@VCWdsTransportClient@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CWdsTransportClient>::CreateInstance(ATL::CComObject<CWdsTransportClient> * *)
0x18001641f  lea     r9d, [rbx+56h]
0x180016423  mov     ecx, eax
0x180016425  mov     edi, eax
0x180016427  call    ElValidateHr_11
0x18001642c  mov     rbx, [rsp+38h+arg_0]
0x180016431  test    eax, eax
0x180016433  js      short loc_180016489
0x180016435  mov     rax, [rbx]
0x180016438  mov     rcx, rbx
0x18001643b  mov     rax, [rax+8]
0x18001643f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016444  mov     r9, rbp; struct _WDSTPT_CLIENT *
0x180016447  mov     r8, r14; struct CWdsTptMgmtClient *
0x18001644a  mov     rdx, r15; struct CWdsTransportSession *
0x18001644d  mov     rcx, rbx; this
0x180016450  call    ?Initialize@CWdsTransportClient@@AEAAJPEAVCWdsTransportSession@@PEAVCWdsTptMgmtClient@@PEAU_WDSTPT_CLIENT@@@Z; CWdsTransportClient::Initialize(CWdsTransportSession *,CWdsTptMgmtClient *,_WDSTPT_CLIENT *)
0x180016455  mov     r9d, 60h ; '`'
0x18001645b  mov     ecx, eax
0x18001645d  mov     edi, eax
0x18001645f  call    ElValidateHr_11
0x180016464  test    eax, eax
0x180016466  js      short loc_180016489
0x180016468  mov     rax, [rbx]
0x18001646b  lea     rdx, IID_IWdsTransportClient
0x180016472  mov     r8, rsi
0x180016475  mov     rcx, rbx
0x180016478  mov     rax, [rax]
0x18001647b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016480  mov     edi, eax
0x180016482  jmp     short loc_180016489
0x180016484  mov     edi, 80070057h
0x180016489  test    rbx, rbx
0x18001648c  jz      short loc_18001649D
0x18001648e  mov     rax, [rbx]
0x180016491  mov     rcx, rbx
0x180016494  mov     rax, [rax+10h]
0x180016498  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001649d  mov     r9d, edi
0x1800164a0  lea     r8, aCwdstransportc_48; "<- CWdsTransportClient::CreateInstance="...
0x1800164a7  mov     edx, 10000h
0x1800164ac  lea     rcx, qword_18003B770
0x1800164b3  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x1800164ba  nop     dword ptr [rax+rax+00h]
0x1800164bf  mov     rbx, [rsp+38h+arg_8]
0x1800164c4  mov     eax, edi
0x1800164c6  mov     rbp, [rsp+38h+arg_10]
0x1800164cb  mov     rsi, [rsp+38h+arg_18]
0x1800164d0  add     rsp, 20h
0x1800164d4  pop     r15
0x1800164d6  pop     r14
0x1800164d8  pop     rdi
0x1800164d9  retn
```
