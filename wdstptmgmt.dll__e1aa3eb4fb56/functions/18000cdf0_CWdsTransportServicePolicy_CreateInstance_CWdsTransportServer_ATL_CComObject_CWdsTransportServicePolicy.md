# CWdsTransportServicePolicy::CreateInstance(CWdsTransportServer *,ATL::CComObject<CWdsTransportServicePolicy> * *)

- ea: `0x18000cdf0`
- end: `0x18000ceed`
- name: `?CreateInstance@CWdsTransportServicePolicy@@SAJPEAVCWdsTransportServer@@PEAPEAV?$CComObject@VCWdsTransportServicePolicy@@@ATL@@@Z`
- size: `253`
- prototype: `__int64 __fastcall(struct CWdsTransportServer *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000b9a4`

## callees

- `0x18000cd08`
- `0x18000cdf0`
- `0x18000d194`
- `0x18000eb74`
- `0x180020010`

## import_xrefs

- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000ce23`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000cec9`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000ce23`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000cec9`

## string_xrefs

- `0x18000ce07`: `-> CWdsTransportServicePolicy::CreateInstance`
- `0x18000ceb6`: `<- CWdsTransportServicePolicy::CreateInstance=%x`

## pseudocode

```c
__int64 __fastcall CWdsTransportServicePolicy::CreateInstance(
        struct CWdsTransportServer *a1,
        CWdsTransportServicePolicy **a2)
{
  CWdsTransportServicePolicy *v4; // rbx
  __int64 v5; // rdi
  __int64 v6; // rdx
  __int64 v7; // r8
  int v8; // eax
  __int64 v9; // rdx
  __int64 v10; // r8
  CWdsTransportServicePolicy *v12; // [rsp+30h] [rbp+8h] BYREF

  v4 = 0;
  v12 = 0;
  CTrace::Trace((CTrace *)qword_18003B770, 0x10000u, L"-> CWdsTransportServicePolicy::CreateInstance");
  if ( a1 && a2 )
  {
    v5 = (unsigned int)ATL::CComObject<CWdsTransportServicePolicy>::CreateInstance(&v12);
    v8 = ElValidateHr_4(v5, v6, v7, 78);
    v4 = v12;
    if ( v8 >= 0 )
    {
      (*(void (__fastcall **)(CWdsTransportServicePolicy *))(*(_QWORD *)v12 + 8LL))(v12);
      v5 = (unsigned int)CWdsTransportServicePolicy::Initialize(v4, a1);
      if ( (int)ElValidateHr_4(v5, v9, v10, 86) >= 0 )
      {
        (*(void (__fastcall **)(CWdsTransportServicePolicy *))(*(_QWORD *)v4 + 8LL))(v4);
        *a2 = v4;
      }
    }
  }
  else
  {
    LODWORD(v5) = -2147024809;
  }
  if ( v4 )
    (*(void (__fastcall **)(CWdsTransportServicePolicy *))(*(_QWORD *)v4 + 16LL))(v4);
  CTrace::Trace(
    (CTrace *)qword_18003B770,
    0x10000u,
    L"<- CWdsTransportServicePolicy::CreateInstance=%x",
    (unsigned int)v5);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18000cdf0  mov     rax, rsp
0x18000cdf3  mov     [rax+10h], rbx
0x18000cdf7  mov     [rax+18h], rbp
0x18000cdfb  mov     [rax+20h], rsi
0x18000cdff  push    rdi
0x18000ce00  sub     rsp, 20h
0x18000ce04  mov     rsi, rdx
0x18000ce07  lea     r8, aCwdstransports_18; "-> CWdsTransportServicePolicy::CreateIn"...
0x18000ce0e  mov     rbp, rcx
0x18000ce11  xor     ebx, ebx
0x18000ce13  mov     edx, 10000h
0x18000ce18  mov     [rax+8], rbx
0x18000ce1c  lea     rcx, qword_18003B770
0x18000ce23  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x18000ce2a  nop     dword ptr [rax+rax+00h]
0x18000ce2f  test    rbp, rbp
0x18000ce32  jz      short loc_18000CE9A
0x18000ce34  test    rsi, rsi
0x18000ce37  jz      short loc_18000CE9A
0x18000ce39  lea     rcx, [rsp+28h+arg_0]
0x18000ce3e  call    ?CreateInstance@?$CComObject@VCWdsTransportServicePolicy@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CWdsTransportServicePolicy>::CreateInstance(ATL::CComObject<CWdsTransportServicePolicy> * *)
0x18000ce43  lea     r9d, [rbx+4Eh]
0x18000ce47  mov     ecx, eax
0x18000ce49  mov     edi, eax
0x18000ce4b  call    ElValidateHr_4
0x18000ce50  mov     rbx, [rsp+28h+arg_0]
0x18000ce55  test    eax, eax
0x18000ce57  js      short loc_18000CE9F
0x18000ce59  mov     rax, [rbx]
0x18000ce5c  mov     rcx, rbx
0x18000ce5f  mov     rax, [rax+8]
0x18000ce63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ce68  mov     rdx, rbp; struct CWdsTransportServer *
0x18000ce6b  mov     rcx, rbx; this
0x18000ce6e  call    ?Initialize@CWdsTransportServicePolicy@@AEAAJPEAVCWdsTransportServer@@@Z; CWdsTransportServicePolicy::Initialize(CWdsTransportServer *)
0x18000ce73  mov     r9d, 56h ; 'V'
0x18000ce79  mov     ecx, eax
0x18000ce7b  mov     edi, eax
0x18000ce7d  call    ElValidateHr_4
0x18000ce82  test    eax, eax
0x18000ce84  js      short loc_18000CE9F
0x18000ce86  mov     rax, [rbx]
0x18000ce89  mov     rcx, rbx
0x18000ce8c  mov     rax, [rax+8]
0x18000ce90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ce95  mov     [rsi], rbx
0x18000ce98  jmp     short loc_18000CE9F
0x18000ce9a  mov     edi, 80070057h
0x18000ce9f  test    rbx, rbx
0x18000cea2  jz      short loc_18000CEB3
0x18000cea4  mov     rax, [rbx]
0x18000cea7  mov     rcx, rbx
0x18000ceaa  mov     rax, [rax+10h]
0x18000ceae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ceb3  mov     r9d, edi
0x18000ceb6  lea     r8, aCwdstransports_62; "<- CWdsTransportServicePolicy::CreateIn"...
0x18000cebd  mov     edx, 10000h
0x18000cec2  lea     rcx, qword_18003B770
0x18000cec9  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x18000ced0  nop     dword ptr [rax+rax+00h]
0x18000ced5  mov     rbx, [rsp+28h+arg_8]
0x18000ceda  mov     eax, edi
0x18000cedc  mov     rbp, [rsp+28h+arg_10]
0x18000cee1  mov     rsi, [rsp+28h+arg_18]
0x18000cee6  add     rsp, 20h
0x18000ceea  pop     rdi
0x18000ceeb  retn
```
