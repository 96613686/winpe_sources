# CWdsTransportConfigurationManager::CreateInstance(CWdsTransportServer *,ATL::CComObject<CWdsTransportConfigurationManager> * *)

- ea: `0x18000b410`
- end: `0x18000b50d`
- name: `?CreateInstance@CWdsTransportConfigurationManager@@SAJPEAVCWdsTransportServer@@PEAPEAV?$CComObject@VCWdsTransportConfigurationManager@@@ATL@@@Z`
- size: `253`
- prototype: `__int64 __fastcall(struct CWdsTransportServer *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180009000`

## callees

- `0x18000b2d0`
- `0x18000b410`
- `0x18000b9a4`
- `0x18000c478`
- `0x180020010`

## import_xrefs

- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000b443`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000b4e9`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000b443`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000b4e9`

## string_xrefs

- `0x18000b427`: `-> CWdsTransportConfigurationManager::CreateInstance`
- `0x18000b4d6`: `<- CWdsTransportConfigurationManager::CreateInstance=%x`

## pseudocode

```c
__int64 __fastcall CWdsTransportConfigurationManager::CreateInstance(
        struct CWdsTransportServer *a1,
        CWdsTransportConfigurationManager **a2)
{
  CWdsTransportConfigurationManager *v4; // rbx
  __int64 v5; // rdi
  __int64 v6; // rdx
  __int64 v7; // r8
  int v8; // eax
  __int64 v9; // rdx
  __int64 v10; // r8
  CWdsTransportConfigurationManager *v12; // [rsp+30h] [rbp+8h] BYREF

  v4 = 0;
  v12 = 0;
  CTrace::Trace((CTrace *)qword_18003B770, 0x10000u, L"-> CWdsTransportConfigurationManager::CreateInstance");
  if ( a1 && a2 )
  {
    v5 = (unsigned int)ATL::CComObject<CWdsTransportConfigurationManager>::CreateInstance(&v12);
    v8 = ElValidateHr_3(v5, v6, v7, 81);
    v4 = v12;
    if ( v8 >= 0 )
    {
      (*(void (__fastcall **)(CWdsTransportConfigurationManager *))(*(_QWORD *)v12 + 8LL))(v12);
      v5 = (unsigned int)CWdsTransportConfigurationManager::Initialize(v4, a1);
      if ( (int)ElValidateHr_3(v5, v9, v10, 89) >= 0 )
      {
        (*(void (__fastcall **)(CWdsTransportConfigurationManager *))(*(_QWORD *)v4 + 8LL))(v4);
        *a2 = v4;
      }
    }
  }
  else
  {
    LODWORD(v5) = -2147024809;
  }
  if ( v4 )
    (*(void (__fastcall **)(CWdsTransportConfigurationManager *))(*(_QWORD *)v4 + 16LL))(v4);
  CTrace::Trace(
    (CTrace *)qword_18003B770,
    0x10000u,
    L"<- CWdsTransportConfigurationManager::CreateInstance=%x",
    (unsigned int)v5);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18000b410  mov     rax, rsp
0x18000b413  mov     [rax+10h], rbx
0x18000b417  mov     [rax+18h], rbp
0x18000b41b  mov     [rax+20h], rsi
0x18000b41f  push    rdi
0x18000b420  sub     rsp, 20h
0x18000b424  mov     rsi, rdx
0x18000b427  lea     r8, aCwdstransportc_40; "-> CWdsTransportConfigurationManager::C"...
0x18000b42e  mov     rbp, rcx
0x18000b431  xor     ebx, ebx
0x18000b433  mov     edx, 10000h
0x18000b438  mov     [rax+8], rbx
0x18000b43c  lea     rcx, qword_18003B770
0x18000b443  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x18000b44a  nop     dword ptr [rax+rax+00h]
0x18000b44f  test    rbp, rbp
0x18000b452  jz      short loc_18000B4BA
0x18000b454  test    rsi, rsi
0x18000b457  jz      short loc_18000B4BA
0x18000b459  lea     rcx, [rsp+28h+arg_0]
0x18000b45e  call    ?CreateInstance@?$CComObject@VCWdsTransportConfigurationManager@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CWdsTransportConfigurationManager>::CreateInstance(ATL::CComObject<CWdsTransportConfigurationManager> * *)
0x18000b463  lea     r9d, [rbx+51h]
0x18000b467  mov     ecx, eax
0x18000b469  mov     edi, eax
0x18000b46b  call    ElValidateHr_3
0x18000b470  mov     rbx, [rsp+28h+arg_0]
0x18000b475  test    eax, eax
0x18000b477  js      short loc_18000B4BF
0x18000b479  mov     rax, [rbx]
0x18000b47c  mov     rcx, rbx
0x18000b47f  mov     rax, [rax+8]
0x18000b483  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b488  mov     rdx, rbp; struct CWdsTransportServer *
0x18000b48b  mov     rcx, rbx; this
0x18000b48e  call    ?Initialize@CWdsTransportConfigurationManager@@AEAAJPEAVCWdsTransportServer@@@Z; CWdsTransportConfigurationManager::Initialize(CWdsTransportServer *)
0x18000b493  mov     r9d, 59h ; 'Y'
0x18000b499  mov     ecx, eax
0x18000b49b  mov     edi, eax
0x18000b49d  call    ElValidateHr_3
0x18000b4a2  test    eax, eax
0x18000b4a4  js      short loc_18000B4BF
0x18000b4a6  mov     rax, [rbx]
0x18000b4a9  mov     rcx, rbx
0x18000b4ac  mov     rax, [rax+8]
0x18000b4b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b4b5  mov     [rsi], rbx
0x18000b4b8  jmp     short loc_18000B4BF
0x18000b4ba  mov     edi, 80070057h
0x18000b4bf  test    rbx, rbx
0x18000b4c2  jz      short loc_18000B4D3
0x18000b4c4  mov     rax, [rbx]
0x18000b4c7  mov     rcx, rbx
0x18000b4ca  mov     rax, [rax+10h]
0x18000b4ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b4d3  mov     r9d, edi
0x18000b4d6  lea     r8, aCwdstransportc_18; "<- CWdsTransportConfigurationManager::C"...
0x18000b4dd  mov     edx, 10000h
0x18000b4e2  lea     rcx, qword_18003B770
0x18000b4e9  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x18000b4f0  nop     dword ptr [rax+rax+00h]
0x18000b4f5  mov     rbx, [rsp+28h+arg_8]
0x18000b4fa  mov     eax, edi
0x18000b4fc  mov     rbp, [rsp+28h+arg_10]
0x18000b501  mov     rsi, [rsp+28h+arg_18]
0x18000b506  add     rsp, 20h
0x18000b50a  pop     rdi
0x18000b50b  retn
```
