# CWdsTransportContent::CreateInstance(CWdsTransportNamespace *,CWdsTptMgmtClient *,_WDSTPT_CONTENT *,IWdsTransportContent * *)

- ea: `0x1800149f4`
- end: `0x180014b17`
- name: `?CreateInstance@CWdsTransportContent@@SAJPEAVCWdsTransportNamespace@@PEAVCWdsTptMgmtClient@@PEAU_WDSTPT_CONTENT@@PEAPEAUIWdsTransportContent@@@Z`
- size: `291`
- prototype: `__int64 __fastcall(struct CWdsTransportNamespace *, struct CWdsTptMgmtClient *, struct _WDSTPT_CONTENT *, struct IWdsTransportContent **)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180012844`

## callees

- `0x1800148c0`
- `0x1800149f4`
- `0x180014c24`
- `0x180015214`
- `0x180020010`

## import_xrefs

- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180014a31`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180014aef`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180014a31`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180014aef`

## string_xrefs

- `0x180014a15`: `-> CWdsTransportContent::CreateInstance`
- `0x180014adc`: `<- CWdsTransportContent::CreateInstance=%x`

## pseudocode

```c
__int64 __fastcall CWdsTransportContent::CreateInstance(
        struct CWdsTransportNamespace *a1,
        struct CWdsTptMgmtClient *a2,
        struct _WDSTPT_CONTENT *a3,
        struct IWdsTransportContent **a4)
{
  CWdsTransportContent *v7; // rbx
  __int64 v9; // rdi
  __int64 v10; // rdx
  __int64 v11; // r8
  int v12; // eax
  __int64 v13; // rdx
  __int64 v14; // r8
  CWdsTransportContent *v16; // [rsp+40h] [rbp+8h] BYREF

  v7 = 0;
  v16 = 0;
  CTrace::Trace((CTrace *)qword_18003B770, 0x10000u, L"-> CWdsTransportContent::CreateInstance");
  if ( a1 && a2 && a3 && a4 )
  {
    v9 = (unsigned int)ATL::CComObject<CWdsTransportContent>::CreateInstance(&v16);
    v12 = ElValidateHr_9(v9, v10, v11, 89);
    v7 = v16;
    if ( v12 >= 0 )
    {
      (*(void (__fastcall **)(CWdsTransportContent *))(*(_QWORD *)v16 + 8LL))(v16);
      v9 = (unsigned int)CWdsTransportContent::Initialize(v7, a1, a2, a3);
      if ( (int)ElValidateHr_9(v9, v13, v14, 99) >= 0 )
        LODWORD(v9) = (**(__int64 (__fastcall ***)(CWdsTransportContent *, GUID *, struct IWdsTransportContent **))v7)(
                        v7,
                        &IID_IWdsTransportContent,
                        a4);
    }
  }
  else
  {
    LODWORD(v9) = -2147024809;
  }
  if ( v7 )
    (*(void (__fastcall **)(CWdsTransportContent *))(*(_QWORD *)v7 + 16LL))(v7);
  CTrace::Trace((CTrace *)qword_18003B770, 0x10000u, L"<- CWdsTransportContent::CreateInstance=%x", (unsigned int)v9);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800149f4  mov     rax, rsp
0x1800149f7  mov     [rax+10h], rbx
0x1800149fb  mov     [rax+18h], rbp
0x1800149ff  mov     [rax+20h], rsi
0x180014a03  push    rdi
0x180014a04  push    r14
0x180014a06  push    r15
0x180014a08  sub     rsp, 20h
0x180014a0c  mov     rbp, r8
0x180014a0f  mov     r14, rdx
0x180014a12  mov     r15, rcx
0x180014a15  lea     r8, aCwdstransportc_10; "-> CWdsTransportContent::CreateInstance"
0x180014a1c  xor     ebx, ebx
0x180014a1e  lea     rcx, qword_18003B770
0x180014a25  mov     edx, 10000h
0x180014a2a  mov     [rax+8], rbx
0x180014a2e  mov     rsi, r9
0x180014a31  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x180014a38  nop     dword ptr [rax+rax+00h]
0x180014a3d  test    r15, r15
0x180014a40  jz      short loc_180014AC0
0x180014a42  test    r14, r14
0x180014a45  jz      short loc_180014AC0
0x180014a47  test    rbp, rbp
0x180014a4a  jz      short loc_180014AC0
0x180014a4c  test    rsi, rsi
0x180014a4f  jz      short loc_180014AC0
0x180014a51  lea     rcx, [rsp+38h+arg_0]
0x180014a56  call    ?CreateInstance@?$CComObject@VCWdsTransportContent@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CWdsTransportContent>::CreateInstance(ATL::CComObject<CWdsTransportContent> * *)
0x180014a5b  lea     r9d, [rbx+59h]
0x180014a5f  mov     ecx, eax
0x180014a61  mov     edi, eax
0x180014a63  call    ElValidateHr_9
0x180014a68  mov     rbx, [rsp+38h+arg_0]
0x180014a6d  test    eax, eax
0x180014a6f  js      short loc_180014AC5
0x180014a71  mov     rax, [rbx]
0x180014a74  mov     rcx, rbx
0x180014a77  mov     rax, [rax+8]
0x180014a7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014a80  mov     r9, rbp; struct _WDSTPT_CONTENT *
0x180014a83  mov     r8, r14; struct CWdsTptMgmtClient *
0x180014a86  mov     rdx, r15; struct CWdsTransportNamespace *
0x180014a89  mov     rcx, rbx; this
0x180014a8c  call    ?Initialize@CWdsTransportContent@@AEAAJPEAVCWdsTransportNamespace@@PEAVCWdsTptMgmtClient@@PEAU_WDSTPT_CONTENT@@@Z; CWdsTransportContent::Initialize(CWdsTransportNamespace *,CWdsTptMgmtClient *,_WDSTPT_CONTENT *)
0x180014a91  mov     r9d, 63h ; 'c'
0x180014a97  mov     ecx, eax
0x180014a99  mov     edi, eax
0x180014a9b  call    ElValidateHr_9
0x180014aa0  test    eax, eax
0x180014aa2  js      short loc_180014AC5
0x180014aa4  mov     rax, [rbx]
0x180014aa7  lea     rdx, IID_IWdsTransportContent
0x180014aae  mov     r8, rsi
0x180014ab1  mov     rcx, rbx
0x180014ab4  mov     rax, [rax]
0x180014ab7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014abc  mov     edi, eax
0x180014abe  jmp     short loc_180014AC5
0x180014ac0  mov     edi, 80070057h
0x180014ac5  test    rbx, rbx
0x180014ac8  jz      short loc_180014AD9
0x180014aca  mov     rax, [rbx]
0x180014acd  mov     rcx, rbx
0x180014ad0  mov     rax, [rax+10h]
0x180014ad4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014ad9  mov     r9d, edi
0x180014adc  lea     r8, aCwdstransportc_42; "<- CWdsTransportContent::CreateInstance"...
0x180014ae3  mov     edx, 10000h
0x180014ae8  lea     rcx, qword_18003B770
0x180014aef  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x180014af6  nop     dword ptr [rax+rax+00h]
0x180014afb  mov     rbx, [rsp+38h+arg_8]
0x180014b00  mov     eax, edi
0x180014b02  mov     rbp, [rsp+38h+arg_10]
0x180014b07  mov     rsi, [rsp+38h+arg_18]
0x180014b0c  add     rsp, 20h
0x180014b10  pop     r15
0x180014b12  pop     r14
0x180014b14  pop     rdi
0x180014b15  retn
```
