# CWdsTransportTftpClient::CreateInstance(_WDSTFTP_CLIENT *,IWdsTransportTftpClient * *)

- ea: `0x180018ec8`
- end: `0x180018fbd`
- name: `?CreateInstance@CWdsTransportTftpClient@@SAJPEAU_WDSTFTP_CLIENT@@PEAPEAUIWdsTransportTftpClient@@@Z`
- size: `245`
- prototype: `__int64 __fastcall(struct _WDSTFTP_CLIENT *, struct IWdsTransportTftpClient **)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180019cb0`

## callees

- `0x180018db0`
- `0x180018ec8`
- `0x180019094`
- `0x18001959c`
- `0x180020010`

## import_xrefs

- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180018efa`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180018f99`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180018efa`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180018f99`

## string_xrefs

- `0x180018ee1`: `-> CWdsTransportTftpClient::CreateInstance`
- `0x180018f86`: `<- CWdsTransportTftpClient::CreateInstance=%x`

## pseudocode

```c
__int64 __fastcall CWdsTransportTftpClient::CreateInstance(
        struct _WDSTFTP_CLIENT *a1,
        struct IWdsTransportTftpClient **a2)
{
  __int64 v4; // rdi
  __int64 v5; // rdx
  __int64 v6; // r8
  int v7; // eax
  CWdsTransportTftpClient *v8; // rbx
  __int64 v9; // rdx
  __int64 v10; // r8
  CWdsTransportTftpClient *v12; // [rsp+40h] [rbp+18h] BYREF

  v12 = 0;
  CTrace::Trace((CTrace *)qword_18003B770, 0x10000u, L"-> CWdsTransportTftpClient::CreateInstance");
  v4 = (unsigned int)ATL::CComObject<CWdsTransportTftpClient>::CreateInstance(&v12);
  v7 = ElValidateHr_14(v4, v5, v6, 69);
  v8 = v12;
  if ( v7 >= 0 )
  {
    (*(void (__fastcall **)(CWdsTransportTftpClient *))(*(_QWORD *)v12 + 8LL))(v12);
    v4 = (unsigned int)CWdsTransportTftpClient::Initialize(v8, a1);
    if ( (int)ElValidateHr_14(v4, v9, v10, 77) >= 0 )
      LODWORD(v4) = (**(__int64 (__fastcall ***)(CWdsTransportTftpClient *, GUID *, struct IWdsTransportTftpClient **))v8)(
                      v8,
                      &IID_IWdsTransportTftpClient,
                      a2);
  }
  if ( v8 )
    (*(void (__fastcall **)(CWdsTransportTftpClient *))(*(_QWORD *)v8 + 16LL))(v8);
  CTrace::Trace((CTrace *)qword_18003B770, 0x10000u, L"<- CWdsTransportTftpClient::CreateInstance=%x", (unsigned int)v4);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180018ec8  mov     rax, rsp
0x180018ecb  mov     [rax+8], rbx
0x180018ecf  mov     [rax+10h], rbp
0x180018ed3  mov     [rax+20h], rsi
0x180018ed7  push    rdi
0x180018ed8  sub     rsp, 20h
0x180018edc  and     qword ptr [rax+18h], 0
0x180018ee1  lea     r8, aCwdstransportt; "-> CWdsTransportTftpClient::CreateInsta"...
0x180018ee8  mov     rsi, rdx
0x180018eeb  mov     rbp, rcx
0x180018eee  mov     edx, 10000h
0x180018ef3  lea     rcx, qword_18003B770
0x180018efa  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x180018f01  nop     dword ptr [rax+rax+00h]
0x180018f06  lea     rcx, [rsp+28h+arg_10]
0x180018f0b  call    ?CreateInstance@?$CComObject@VCWdsTransportTftpClient@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CWdsTransportTftpClient>::CreateInstance(ATL::CComObject<CWdsTransportTftpClient> * *)
0x180018f10  mov     r9d, 45h ; 'E'
0x180018f16  mov     ecx, eax
0x180018f18  mov     edi, eax
0x180018f1a  call    ElValidateHr_14
0x180018f1f  mov     rbx, [rsp+28h+arg_10]
0x180018f24  test    eax, eax
0x180018f26  js      short loc_180018F6F
0x180018f28  mov     rax, [rbx]
0x180018f2b  mov     rcx, rbx
0x180018f2e  mov     rax, [rax+8]
0x180018f32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018f37  mov     rdx, rbp; struct _WDSTFTP_CLIENT *
0x180018f3a  mov     rcx, rbx; this
0x180018f3d  call    ?Initialize@CWdsTransportTftpClient@@AEAAJPEAU_WDSTFTP_CLIENT@@@Z; CWdsTransportTftpClient::Initialize(_WDSTFTP_CLIENT *)
0x180018f42  mov     r9d, 4Dh ; 'M'
0x180018f48  mov     ecx, eax
0x180018f4a  mov     edi, eax
0x180018f4c  call    ElValidateHr_14
0x180018f51  test    eax, eax
0x180018f53  js      short loc_180018F6F
0x180018f55  mov     rax, [rbx]
0x180018f58  lea     rdx, IID_IWdsTransportTftpClient
0x180018f5f  mov     r8, rsi
0x180018f62  mov     rcx, rbx
0x180018f65  mov     rax, [rax]
0x180018f68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018f6d  mov     edi, eax
0x180018f6f  test    rbx, rbx
0x180018f72  jz      short loc_180018F83
0x180018f74  mov     rax, [rbx]
0x180018f77  mov     rcx, rbx
0x180018f7a  mov     rax, [rax+10h]
0x180018f7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018f83  mov     r9d, edi
0x180018f86  lea     r8, aCwdstransportt_8; "<- CWdsTransportTftpClient::CreateInsta"...
0x180018f8d  mov     edx, 10000h
0x180018f92  lea     rcx, qword_18003B770
0x180018f99  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x180018fa0  nop     dword ptr [rax+rax+00h]
0x180018fa5  mov     rbx, [rsp+28h+arg_0]
0x180018faa  mov     eax, edi
0x180018fac  mov     rbp, [rsp+28h+arg_8]
0x180018fb1  mov     rsi, [rsp+28h+arg_18]
0x180018fb6  add     rsp, 20h
0x180018fba  pop     rdi
0x180018fbb  retn
```
