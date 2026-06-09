# CWdsTransportSession::CreateInstance(CWdsTransportContent *,CWdsTptMgmtClient *,_WDSTPT_SESSION *,IWdsTransportSession * *)

- ea: `0x1800155fc`
- end: `0x18001571f`
- name: `?CreateInstance@CWdsTransportSession@@SAJPEAVCWdsTransportContent@@PEAVCWdsTptMgmtClient@@PEAU_WDSTPT_SESSION@@PEAPEAUIWdsTransportSession@@@Z`
- size: `291`
- prototype: `__int64 __fastcall(struct CWdsTransportContent *, struct CWdsTptMgmtClient *, struct _WDSTPT_SESSION *, struct IWdsTransportSession **)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180014e40`

## callees

- `0x180015530`
- `0x1800155fc`
- `0x180015854`
- `0x180015fac`
- `0x180020010`

## import_xrefs

- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180015639`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x1800156f7`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180015639`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x1800156f7`

## string_xrefs

- `0x18001561d`: `-> CWdsTransportSession::CreateInstance`
- `0x1800156e4`: `<- CWdsTransportSession::CreateInstance=%x`

## pseudocode

```c
__int64 __fastcall CWdsTransportSession::CreateInstance(
        struct CWdsTransportContent *a1,
        struct CWdsTptMgmtClient *a2,
        struct _WDSTPT_SESSION *a3,
        struct IWdsTransportSession **a4)
{
  CWdsTransportSession *v7; // rbx
  __int64 v9; // rdi
  __int64 v10; // rdx
  __int64 v11; // r8
  int v12; // eax
  __int64 v13; // rdx
  __int64 v14; // r8
  CWdsTransportSession *v16; // [rsp+40h] [rbp+8h] BYREF

  v7 = 0;
  v16 = 0;
  CTrace::Trace((CTrace *)qword_18003B770, 0x10000u, L"-> CWdsTransportSession::CreateInstance");
  if ( a1 && a2 && a3 && a4 )
  {
    v9 = (unsigned int)ATL::CComObject<CWdsTransportSession>::CreateInstance(&v16);
    v12 = ElValidateHr_10(v9, v10, v11, 88);
    v7 = v16;
    if ( v12 >= 0 )
    {
      (*(void (__fastcall **)(CWdsTransportSession *))(*(_QWORD *)v16 + 8LL))(v16);
      v9 = (unsigned int)CWdsTransportSession::Initialize(v7, a1, a2, a3);
      if ( (int)ElValidateHr_10(v9, v13, v14, 98) >= 0 )
        LODWORD(v9) = (**(__int64 (__fastcall ***)(CWdsTransportSession *, GUID *, struct IWdsTransportSession **))v7)(
                        v7,
                        &IID_IWdsTransportSession,
                        a4);
    }
  }
  else
  {
    LODWORD(v9) = -2147024809;
  }
  if ( v7 )
    (*(void (__fastcall **)(CWdsTransportSession *))(*(_QWORD *)v7 + 16LL))(v7);
  CTrace::Trace((CTrace *)qword_18003B770, 0x10000u, L"<- CWdsTransportSession::CreateInstance=%x", (unsigned int)v9);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800155fc  mov     rax, rsp
0x1800155ff  mov     [rax+10h], rbx
0x180015603  mov     [rax+18h], rbp
0x180015607  mov     [rax+20h], rsi
0x18001560b  push    rdi
0x18001560c  push    r14
0x18001560e  push    r15
0x180015610  sub     rsp, 20h
0x180015614  mov     rbp, r8
0x180015617  mov     r14, rdx
0x18001561a  mov     r15, rcx
0x18001561d  lea     r8, aCwdstransports_29; "-> CWdsTransportSession::CreateInstance"
0x180015624  xor     ebx, ebx
0x180015626  lea     rcx, qword_18003B770
0x18001562d  mov     edx, 10000h
0x180015632  mov     [rax+8], rbx
0x180015636  mov     rsi, r9
0x180015639  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x180015640  nop     dword ptr [rax+rax+00h]
0x180015645  test    r15, r15
0x180015648  jz      short loc_1800156C8
0x18001564a  test    r14, r14
0x18001564d  jz      short loc_1800156C8
0x18001564f  test    rbp, rbp
0x180015652  jz      short loc_1800156C8
0x180015654  test    rsi, rsi
0x180015657  jz      short loc_1800156C8
0x180015659  lea     rcx, [rsp+38h+arg_0]
0x18001565e  call    ?CreateInstance@?$CComObject@VCWdsTransportSession@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CWdsTransportSession>::CreateInstance(ATL::CComObject<CWdsTransportSession> * *)
0x180015663  lea     r9d, [rbx+58h]
0x180015667  mov     ecx, eax
0x180015669  mov     edi, eax
0x18001566b  call    ElValidateHr_10
0x180015670  mov     rbx, [rsp+38h+arg_0]
0x180015675  test    eax, eax
0x180015677  js      short loc_1800156CD
0x180015679  mov     rax, [rbx]
0x18001567c  mov     rcx, rbx
0x18001567f  mov     rax, [rax+8]
0x180015683  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015688  mov     r9, rbp; struct _WDSTPT_SESSION *
0x18001568b  mov     r8, r14; struct CWdsTptMgmtClient *
0x18001568e  mov     rdx, r15; struct CWdsTransportContent *
0x180015691  mov     rcx, rbx; this
0x180015694  call    ?Initialize@CWdsTransportSession@@AEAAJPEAVCWdsTransportContent@@PEAVCWdsTptMgmtClient@@PEAU_WDSTPT_SESSION@@@Z; CWdsTransportSession::Initialize(CWdsTransportContent *,CWdsTptMgmtClient *,_WDSTPT_SESSION *)
0x180015699  mov     r9d, 62h ; 'b'
0x18001569f  mov     ecx, eax
0x1800156a1  mov     edi, eax
0x1800156a3  call    ElValidateHr_10
0x1800156a8  test    eax, eax
0x1800156aa  js      short loc_1800156CD
0x1800156ac  mov     rax, [rbx]
0x1800156af  lea     rdx, IID_IWdsTransportSession
0x1800156b6  mov     r8, rsi
0x1800156b9  mov     rcx, rbx
0x1800156bc  mov     rax, [rax]
0x1800156bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800156c4  mov     edi, eax
0x1800156c6  jmp     short loc_1800156CD
0x1800156c8  mov     edi, 80070057h
0x1800156cd  test    rbx, rbx
0x1800156d0  jz      short loc_1800156E1
0x1800156d2  mov     rax, [rbx]
0x1800156d5  mov     rcx, rbx
0x1800156d8  mov     rax, [rax+10h]
0x1800156dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800156e1  mov     r9d, edi
0x1800156e4  lea     r8, aCwdstransports_31; "<- CWdsTransportSession::CreateInstance"...
0x1800156eb  mov     edx, 10000h
0x1800156f0  lea     rcx, qword_18003B770
0x1800156f7  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x1800156fe  nop     dword ptr [rax+rax+00h]
0x180015703  mov     rbx, [rsp+38h+arg_8]
0x180015708  mov     eax, edi
0x18001570a  mov     rbp, [rsp+38h+arg_10]
0x18001570f  mov     rsi, [rsp+38h+arg_18]
0x180015714  add     rsp, 20h
0x180015718  pop     r15
0x18001571a  pop     r14
0x18001571c  pop     rdi
0x18001571d  retn
```
