# CWdsTransportSetupManager::CreateInstance(CWdsTransportServer *,ATL::CComObject<CWdsTransportSetupManager> * *)

- ea: `0x180009f8c`
- end: `0x18000a0d5`
- name: `?CreateInstance@CWdsTransportSetupManager@@SAJPEAVCWdsTransportServer@@PEAPEAV?$CComObject@VCWdsTransportSetupManager@@@ATL@@@Z`
- size: `329`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180009000`

## callees

- `0x180009e50`
- `0x180009f8c`
- `0x18000b048`
- `0x180020010`

## import_xrefs

- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180009fbf`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000a026`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000a051`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000a0b1`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180009fbf`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000a026`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000a051`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000a0b1`

## string_xrefs

- `0x180009fa3`: `-> CWdsTransportSetupManager::CreateInstance`
- `0x18000a09e`: `<- CWdsTransportSetupManager::CreateInstance=%x`

## pseudocode

```c
__int64 __fastcall CWdsTransportSetupManager::CreateInstance(__int64 a1, _QWORD *a2)
{
  _QWORD *v4; // rbx
  __int64 v5; // rdi
  __int64 v6; // rdx
  __int64 v7; // r8
  int v8; // eax
  __int64 v9; // rdx
  __int64 v10; // r8
  int v12; // [rsp+20h] [rbp-18h]
  _QWORD *v13; // [rsp+40h] [rbp+8h] BYREF

  v4 = 0;
  v13 = 0;
  CTrace::Trace((CTrace *)qword_18003B770, 0x10000u, L"-> CWdsTransportSetupManager::CreateInstance");
  if ( a1 && a2 )
  {
    v5 = (unsigned int)ATL::CComObject<CWdsTransportSetupManager>::CreateInstance(&v13);
    v8 = ElValidateHr_2(v5, v6, v7, 79);
    v4 = v13;
    if ( v8 >= 0 )
    {
      (*(void (__fastcall **)(_QWORD *))(*v13 + 8LL))(v13);
      CTrace::Trace((CTrace *)qword_18003B770, 0x10000u, L"-> CWdsTransportSetupManager::Initialize(0x%p)", v4);
      v12 = 0;
      v4[8] = a1;
      CTrace::Trace((CTrace *)qword_18003B770, 0x10000u, L"<- CWdsTransportSetupManager::Initialize(0x%p) =%x", v4, v12);
      LODWORD(v5) = 0;
      if ( (int)ElValidateHr_2(0, v9, v10, 87) >= 0 )
      {
        (*(void (__fastcall **)(_QWORD *))(*v4 + 8LL))(v4);
        *a2 = v4;
      }
    }
  }
  else
  {
    LODWORD(v5) = -2147024809;
  }
  if ( v4 )
    (*(void (__fastcall **)(_QWORD *))(*v4 + 16LL))(v4);
  CTrace::Trace(
    (CTrace *)qword_18003B770,
    0x10000u,
    L"<- CWdsTransportSetupManager::CreateInstance=%x",
    (unsigned int)v5);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180009f8c  mov     rax, rsp
0x180009f8f  mov     [rax+10h], rbx
0x180009f93  mov     [rax+18h], rbp
0x180009f97  mov     [rax+20h], rsi
0x180009f9b  push    rdi
0x180009f9c  sub     rsp, 30h
0x180009fa0  mov     rsi, rdx
0x180009fa3  lea     r8, aCwdstransports_21; "-> CWdsTransportSetupManager::CreateIns"...
0x180009faa  mov     rbp, rcx
0x180009fad  xor     ebx, ebx
0x180009faf  mov     edx, 10000h
0x180009fb4  mov     [rax+8], rbx
0x180009fb8  lea     rcx, qword_18003B770
0x180009fbf  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x180009fc6  nop     dword ptr [rax+rax+00h]
0x180009fcb  test    rbp, rbp
0x180009fce  jz      loc_18000A082
0x180009fd4  test    rsi, rsi
0x180009fd7  jz      loc_18000A082
0x180009fdd  lea     rcx, [rsp+38h+arg_0]
0x180009fe2  call    ?CreateInstance@?$CComObject@VCWdsTransportSetupManager@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CWdsTransportSetupManager>::CreateInstance(ATL::CComObject<CWdsTransportSetupManager> * *)
0x180009fe7  lea     r9d, [rbx+4Fh]
0x180009feb  mov     ecx, eax
0x180009fed  mov     edi, eax
0x180009fef  call    ElValidateHr_2
0x180009ff4  mov     rbx, [rsp+38h+arg_0]
0x180009ff9  test    eax, eax
0x180009ffb  js      loc_18000A087
0x18000a001  mov     rax, [rbx]
0x18000a004  mov     rcx, rbx
0x18000a007  mov     rax, [rax+8]
0x18000a00b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a010  mov     r9, rbx
0x18000a013  lea     r8, aCwdstransports_59; "-> CWdsTransportSetupManager::Initializ"...
0x18000a01a  mov     edx, 10000h
0x18000a01f  lea     rcx, qword_18003B770
0x18000a026  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x18000a02d  nop     dword ptr [rax+rax+00h]
0x18000a032  and     [rsp+38h+var_18], 0
0x18000a037  lea     r8, aCwdstransports_13; "<- CWdsTransportSetupManager::Initializ"...
0x18000a03e  mov     r9, rbx
0x18000a041  mov     [rbx+40h], rbp
0x18000a045  mov     edx, 10000h
0x18000a04a  lea     rcx, qword_18003B770
0x18000a051  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x18000a058  nop     dword ptr [rax+rax+00h]
0x18000a05d  xor     edi, edi
0x18000a05f  xor     ecx, ecx
0x18000a061  lea     r9d, [rdi+57h]
0x18000a065  call    ElValidateHr_2
0x18000a06a  test    eax, eax
0x18000a06c  js      short loc_18000A087
0x18000a06e  mov     rax, [rbx]
0x18000a071  mov     rcx, rbx
0x18000a074  mov     rax, [rax+8]
0x18000a078  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a07d  mov     [rsi], rbx
0x18000a080  jmp     short loc_18000A087
0x18000a082  mov     edi, 80070057h
0x18000a087  test    rbx, rbx
0x18000a08a  jz      short loc_18000A09B
0x18000a08c  mov     rax, [rbx]
0x18000a08f  mov     rcx, rbx
0x18000a092  mov     rax, [rax+10h]
0x18000a096  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a09b  mov     r9d, edi
0x18000a09e  lea     r8, aCwdstransports_3; "<- CWdsTransportSetupManager::CreateIns"...
0x18000a0a5  mov     edx, 10000h
0x18000a0aa  lea     rcx, qword_18003B770
0x18000a0b1  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x18000a0b8  nop     dword ptr [rax+rax+00h]
0x18000a0bd  mov     rbx, [rsp+38h+arg_8]
0x18000a0c2  mov     eax, edi
0x18000a0c4  mov     rbp, [rsp+38h+arg_10]
0x18000a0c9  mov     rsi, [rsp+38h+arg_18]
0x18000a0ce  add     rsp, 30h
0x18000a0d2  pop     rdi
0x18000a0d3  retn
```
