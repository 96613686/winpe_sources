# CWdsTransportConfigurationManager::Initialize(CWdsTransportServer *)

- ea: `0x18000b9a4`
- end: `0x18000bacd`
- name: `?Initialize@CWdsTransportConfigurationManager@@AEAAJPEAVCWdsTransportServer@@@Z`
- size: `297`
- prototype: `int(CWdsTransportConfigurationManager *__hidden this, struct CWdsTransportServer *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000b410`

## callees

- `0x18000b9a4`
- `0x18000c478`
- `0x18000cdf0`
- `0x18000f338`
- `0x180017608`

## import_xrefs

- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000b9d9`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000baa3`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000b9d9`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000baa3`

## string_xrefs

- `0x18000b9c0`: `-> CWdsTransportConfigurationManager::Initialize(0x%p)`
- `0x18000ba90`: `<- CWdsTransportConfigurationManager::Initialize(0x%p) =%x`

## pseudocode

```c
__int64 __fastcall CWdsTransportConfigurationManager::Initialize(
        CWdsTransportConfigurationManager *this,
        struct CWdsTransportServer *a2)
{
  __int64 Instance; // rdi
  __int64 v5; // rdx
  __int64 v6; // r8
  __int64 v7; // rdx
  __int64 v8; // r8
  __int64 v9; // rdx
  __int64 v10; // r8
  int v12; // [rsp+20h] [rbp-18h]

  CTrace::Trace((CTrace *)qword_18003B770, 0x10000u, L"-> CWdsTransportConfigurationManager::Initialize(0x%p)", this);
  if ( *((_DWORD *)this + 30) )
  {
    LODWORD(Instance) = -1055915767;
  }
  else
  {
    *((_QWORD *)this + 8) = a2;
    Instance = (unsigned int)CWdsTransportServicePolicy::CreateInstance(a2);
    if ( (int)ElValidateHr_3(Instance, v5, v6, 159) >= 0 )
    {
      Instance = (unsigned int)CWdsTransportDiagnosticsPolicy::CreateInstance(*((struct CWdsTransportServer **)this + 8));
      if ( (int)ElValidateHr_3(Instance, v7, v8, 166) >= 0 )
      {
        Instance = (unsigned int)CWdsTransportMulticastSessionPolicy::CreateInstance(*((struct CWdsTransportServer **)this
                                                                                     + 8));
        if ( (int)ElValidateHr_3(Instance, v9, v10, 173) >= 0 )
        {
          *(_DWORD *)(*((_QWORD *)this + 17) + 72LL) = 1;
          *(_DWORD *)(*((_QWORD *)this + 18) + 72LL) = 1;
          *(_DWORD *)(*((_QWORD *)this + 19) + 72LL) = 1;
          *((_DWORD *)this + 30) = 1;
        }
      }
    }
  }
  v12 = Instance;
  CTrace::Trace(
    (CTrace *)qword_18003B770,
    0x10000u,
    L"<- CWdsTransportConfigurationManager::Initialize(0x%p) =%x",
    this,
    v12);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x18000b9a4  mov     rax, rsp
0x18000b9a7  mov     [rax+8], rbx
0x18000b9ab  mov     [rax+10h], rsi
0x18000b9af  mov     [rax+18h], rdi
0x18000b9b3  mov     [rax+20h], r14
0x18000b9b7  push    r15
0x18000b9b9  sub     rsp, 30h
0x18000b9bd  mov     rdi, rdx
0x18000b9c0  lea     r8, aCwdstransportc_50; "-> CWdsTransportConfigurationManager::I"...
0x18000b9c7  mov     rbx, rcx
0x18000b9ca  mov     r9, rcx
0x18000b9cd  mov     edx, 10000h
0x18000b9d2  lea     rcx, qword_18003B770
0x18000b9d9  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x18000b9e0  nop     dword ptr [rax+rax+00h]
0x18000b9e5  cmp     dword ptr [rbx+78h], 0
0x18000b9e9  jz      short loc_18000B9F5
0x18000b9eb  mov     edi, 0C1100109h
0x18000b9f0  jmp     loc_18000BA89
0x18000b9f5  lea     r15, [rbx+88h]
0x18000b9fc  mov     [rbx+40h], rdi
0x18000ba00  mov     rdx, r15
0x18000ba03  mov     rcx, rdi; struct CWdsTransportServer *
0x18000ba06  call    ?CreateInstance@CWdsTransportServicePolicy@@SAJPEAVCWdsTransportServer@@PEAPEAV?$CComObject@VCWdsTransportServicePolicy@@@ATL@@@Z; CWdsTransportServicePolicy::CreateInstance(CWdsTransportServer *,ATL::CComObject<CWdsTransportServicePolicy> * *)
0x18000ba0b  mov     r9d, 9Fh
0x18000ba11  mov     ecx, eax
0x18000ba13  mov     edi, eax
0x18000ba15  call    ElValidateHr_3
0x18000ba1a  test    eax, eax
0x18000ba1c  js      short loc_18000BA89
0x18000ba1e  mov     rcx, [rbx+40h]; struct CWdsTransportServer *
0x18000ba22  lea     r14, [rbx+90h]
0x18000ba29  mov     rdx, r14
0x18000ba2c  call    ?CreateInstance@CWdsTransportDiagnosticsPolicy@@SAJPEAVCWdsTransportServer@@PEAPEAV?$CComObject@VCWdsTransportDiagnosticsPolicy@@@ATL@@@Z; CWdsTransportDiagnosticsPolicy::CreateInstance(CWdsTransportServer *,ATL::CComObject<CWdsTransportDiagnosticsPolicy> * *)
0x18000ba31  mov     r9d, 0A6h
0x18000ba37  mov     ecx, eax
0x18000ba39  mov     edi, eax
0x18000ba3b  call    ElValidateHr_3
0x18000ba40  test    eax, eax
0x18000ba42  js      short loc_18000BA89
0x18000ba44  mov     rcx, [rbx+40h]; struct CWdsTransportServer *
0x18000ba48  lea     rsi, [rbx+98h]
0x18000ba4f  mov     rdx, rsi
0x18000ba52  call    ?CreateInstance@CWdsTransportMulticastSessionPolicy@@SAJPEAVCWdsTransportServer@@PEAPEAV?$CComObject@VCWdsTransportMulticastSessionPolicy@@@ATL@@@Z; CWdsTransportMulticastSessionPolicy::CreateInstance(CWdsTransportServer *,ATL::CComObject<CWdsTransportMulticastSessionPolicy> * *)
0x18000ba57  mov     r9d, 0ADh
0x18000ba5d  mov     ecx, eax
0x18000ba5f  mov     edi, eax
0x18000ba61  call    ElValidateHr_3
0x18000ba66  test    eax, eax
0x18000ba68  js      short loc_18000BA89
0x18000ba6a  mov     rax, [r15]
0x18000ba6d  mov     r8d, 1
0x18000ba73  mov     [rax+48h], r8d
0x18000ba77  mov     rax, [r14]
0x18000ba7a  mov     [rax+48h], r8d
0x18000ba7e  mov     rax, [rsi]
0x18000ba81  mov     [rax+48h], r8d
0x18000ba85  mov     [rbx+78h], r8d
0x18000ba89  mov     r9, rbx
0x18000ba8c  mov     [rsp+38h+var_18], edi
0x18000ba90  lea     r8, aCwdstransportc_34; "<- CWdsTransportConfigurationManager::I"...
0x18000ba97  mov     edx, 10000h
0x18000ba9c  lea     rcx, qword_18003B770
0x18000baa3  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x18000baaa  nop     dword ptr [rax+rax+00h]
0x18000baaf  mov     rbx, [rsp+38h+arg_0]
0x18000bab4  mov     eax, edi
0x18000bab6  mov     rdi, [rsp+38h+arg_10]
0x18000babb  mov     rsi, [rsp+38h+arg_8]
0x18000bac0  mov     r14, [rsp+38h+arg_18]
0x18000bac5  add     rsp, 30h
0x18000bac9  pop     r15
0x18000bacb  retn
```
