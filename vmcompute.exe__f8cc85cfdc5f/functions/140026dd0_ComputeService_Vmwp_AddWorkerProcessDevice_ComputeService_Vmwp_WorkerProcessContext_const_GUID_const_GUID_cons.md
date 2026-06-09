# ComputeService::Vmwp::AddWorkerProcessDevice(ComputeService::Vmwp::WorkerProcessContext const &,_GUID const &,_GUID const &,ushort const *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,uint,IVmHandleBroker *)

- ea: `0x140026dd0`
- end: `0x140026f82`
- name: `?AddWorkerProcessDevice@Vmwp@ComputeService@@YAXAEBUWorkerProcessContext@12@AEBU_GUID@@1PEBGAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@IPEAUIVmHandleBroker@@@Z`
- size: `434`
- prototype: ``
- caller_count: `5`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x140025774`
- `0x1400942e0`
- `0x140095464`
- `0x140098b98`
- `0x140287908`

## callees

- `0x1400243f0`
- `0x140026dd0`
- `0x14007cb48`
- `0x1400c40e0`
- `0x1400da33c`
- `0x140105824`
- `0x1402c4010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x140026ea1`
- `OLEAUT32!__imp_SysAllocString` at `0x140026ea1`
- `OLEAUT32!__imp_SysFreeString` at `0x140026f3d`
- `OLEAUT32!__imp_SysFreeString` at `0x140026f3d`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x140026e04`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x140026e04`

## string_xrefs

- `0x140026ebc`: `onecore\vm\common\vml\VmBstr.h`
- `0x140026e20`: `onecore\vm\compute\shared\vmwp\lib\workerprocessdevice.cpp`
- `0x140026f22`: `onecore\vm\compute\shared\vmwp\lib\workerprocessdevice.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall ComputeService::Vmwp::AddWorkerProcessDevice(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const OLECHAR *a4,
        __int64 a5,
        char a6,
        __int64 a7)
{
  const BYTE *v11; // rcx
  IStream *v12; // rdi
  int v13; // r8d
  const char *v14; // r9
  __int64 v15; // rcx
  __int64 v16; // rbx
  __int64 *v17; // rax
  __int64 v18; // rdx
  OLECHAR *v19; // rax
  int v20; // eax
  int v22; // [rsp+20h] [rbp-60h]
  int v23; // [rsp+20h] [rbp-60h]
  __int64 v24; // [rsp+50h] [rbp-30h] BYREF
  __int64 v25; // [rsp+58h] [rbp-28h] BYREF
  BSTR bstrString; // [rsp+60h] [rbp-20h] BYREF
  __int64 v27; // [rsp+68h] [rbp-18h] BYREF
  _QWORD v28[2]; // [rsp+70h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+38h]

  v11 = (const BYTE *)a5;
  if ( *(_QWORD *)(a5 + 24) > 7u )
    v11 = *(const BYTE **)a5;
  v12 = SHCreateMemStream(v11, 2 * *(_DWORD *)(a5 + 16));
  v28[1] = v12;
  LODWORD(v15) = (_DWORD)retaddr;
  if ( !v12 )
    wil::details::in1diag3::_Throw_NullAlloc(
      retaddr,
      (void *)0x48,
      (unsigned int)"onecore\\vm\\compute\\shared\\vmwp\\lib\\workerprocessdevice.cpp",
      v14);
  v16 = a7;
  v25 = a7;
  if ( a7 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a7 + 8LL))(a7);
  if ( !v16 )
  {
    v17 = (__int64 *)wil::MakeOrThrow<VmHandleBroker,_GUID &,_GUID const &>(&v24, a3, a2);
    v18 = *v17;
    *v17 = 0;
    wil::com_ptr_t<IVmHandleBroker,wil::err_exception_policy>::attach(&v25, v18);
    v15 = v24;
    if ( v24 )
    {
      v24 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
    }
    v16 = v25;
  }
  v27 = v16;
  v28[0] = v12;
  v19 = 0;
  if ( a4 )
  {
    v19 = SysAllocString(a4);
    if ( !v19 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x254,
        (unsigned int)"onecore\\vm\\common\\vml\\VmBstr.h",
        (const char *)0x8007000ELL,
        v22);
  }
  bstrString = v19;
  LODWORD(v24) = 1;
  v20 = ___InvokeWorkerProcessMethod_UIVmVirtualDeviceAccess__AEBU_GUID__AEBU2_KPEAGPEAUIUnknown__IPEAUIVmHandleBroker____ZAEBU2_AEBU2_W4tagCLSCTX__VVmBstr_Vml__PEAUIStream__AEAIPEAU4__Vmwp_ComputeService__YAJAEBUWorkerProcessContext_01_PEAUIUnknown__P8IVmVirtualDeviceAccess__EAAJAEBU_GUID__2KPEAG1IPEAUIVmHandleBroker___Z22__QEAW4tagCLSCTX____QEAVVmBstr_Vml____QEAPEAUIStream__AEAI__QEAPEAU6__Z(
          v15,
          *(_QWORD *)(a1 + 16),
          v13,
          a3,
          a2,
          (__int64)&v24,
          (__int64)&bstrString,
          (__int64)v28,
          (__int64)&a6,
          (__int64)&v27);
  if ( v20 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x5B,
      (unsigned int)"onecore\\vm\\compute\\shared\\vmwp\\lib\\workerprocessdevice.cpp",
      (const char *)(unsigned int)v20,
      v23);
  if ( bstrString )
    SysFreeString(bstrString);
  if ( v16 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
  return (*(__int64 (__fastcall **)(IStream *))(*(_QWORD *)v12 + 16LL))(v12);
}

```

## disassembly

```asm
0x140026dd0  push    rbp
0x140026dd2  push    rbx
0x140026dd3  push    rsi
0x140026dd4  push    rdi
0x140026dd5  push    r13
0x140026dd7  push    r14
0x140026dd9  push    r15
0x140026ddb  mov     rbp, rsp
0x140026dde  sub     rsp, 80h
0x140026de5  mov     rsi, r9
0x140026de8  mov     r15, r8
0x140026deb  mov     r14, rdx
0x140026dee  mov     r13, rcx
0x140026df1  mov     rcx, [rbp+arg_20]
0x140026df5  mov     edx, [rcx+10h]
0x140026df8  add     edx, edx; cbInit
0x140026dfa  cmp     qword ptr [rcx+18h], 7
0x140026dff  jbe     short loc_140026E04
0x140026e01  mov     rcx, [rcx]; pInit
0x140026e04  call    cs:__imp_SHCreateMemStream
0x140026e0b  nop     dword ptr [rax+rax+00h]
0x140026e10  mov     rdi, rax
0x140026e13  mov     [rbp+var_8], rax
0x140026e17  mov     rcx, [rbp+38h]; this
0x140026e1b  test    rax, rax
0x140026e1e  jnz     short loc_140026E30
0x140026e20  lea     r8, aOnecoreVmCompu_52; "onecore\\vm\\compute\\shared\\vmwp\\lib"...
0x140026e27  lea     edx, [rax+48h]; void *
0x140026e2a  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x140026e30  mov     rbx, [rbp+arg_30]
0x140026e34  mov     [rbp+var_28], rbx
0x140026e38  test    rbx, rbx
0x140026e3b  jz      short loc_140026E4D
0x140026e3d  mov     rax, [rbx]
0x140026e40  mov     rcx, rbx
0x140026e43  mov     rax, [rax+8]
0x140026e47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140026e4c  nop
0x140026e4d  test    rbx, rbx
0x140026e50  jnz     short loc_140026E8F
0x140026e52  mov     r8, r14
0x140026e55  mov     rdx, r15
0x140026e58  lea     rcx, [rbp+var_30]
0x140026e5c  call    ??$MakeOrThrow@VVmHandleBroker@@AEAU_GUID@@AEBU2@@wil@@YA?AV?$ComPtr@VVmHandleBroker@@@WRL@Microsoft@@AEAU_GUID@@AEBU4@@Z; wil::MakeOrThrow<VmHandleBroker,_GUID &,_GUID const &>(_GUID &,_GUID const &)
0x140026e61  mov     rdx, [rax]
0x140026e64  mov     [rax], rbx
0x140026e67  lea     rcx, [rbp+var_28]
0x140026e6b  call    ?attach@?$com_ptr_t@UIVmHandleBroker@@Uerr_exception_policy@wil@@@wil@@QEAAXPEAUIVmHandleBroker@@@Z; wil::com_ptr_t<IVmHandleBroker,wil::err_exception_policy>::attach(IVmHandleBroker *)
0x140026e70  nop
0x140026e71  mov     rcx, [rbp+var_30]
0x140026e75  test    rcx, rcx
0x140026e78  jz      short loc_140026E8B
0x140026e7a  mov     [rbp+var_30], rbx
0x140026e7e  mov     rax, [rcx]
0x140026e81  mov     rax, [rax+10h]
0x140026e85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140026e8a  nop
0x140026e8b  mov     rbx, [rbp+var_28]
0x140026e8f  mov     [rbp+var_18], rbx
0x140026e93  mov     [rbp+var_10], rdi
0x140026e97  xor     eax, eax
0x140026e99  test    rsi, rsi
0x140026e9c  jz      short loc_140026ECE
0x140026e9e  mov     rcx, rsi; psz
0x140026ea1  call    cs:__imp_SysAllocString
0x140026ea8  nop     dword ptr [rax+rax+00h]
0x140026ead  test    rax, rax
0x140026eb0  jnz     short loc_140026ECE
0x140026eb2  mov     rcx, [rbp+38h]; this
0x140026eb6  mov     r9d, 8007000Eh; char *
0x140026ebc  lea     r8, aOnecoreVmCommo_30; "onecore\\vm\\common\\vml\\VmBstr.h"
0x140026ec3  mov     edx, 254h; void *
0x140026ec8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140026ece  mov     [rbp+bstrString], rax
0x140026ed2  mov     dword ptr [rbp+var_30], 1
0x140026ed9  lea     rax, [rbp+var_18]
0x140026edd  mov     [rsp+80h+var_38], rax
0x140026ee2  lea     rax, [rbp+arg_28]
0x140026ee6  mov     [rsp+80h+var_40], rax
0x140026eeb  lea     rax, [rbp+var_10]
0x140026eef  mov     [rsp+80h+var_48], rax
0x140026ef4  lea     rax, [rbp+bstrString]
0x140026ef8  mov     [rsp+80h+var_50], rax
0x140026efd  lea     rax, [rbp+var_30]
0x140026f01  mov     [rsp+80h+var_58], rax
0x140026f06  mov     qword ptr [rsp+80h+var_60], r14; int
0x140026f0b  mov     r9, r15
0x140026f0e  mov     rdx, [r13+10h]
0x140026f12  call    ??$InvokeWorkerProcessMethod@UIVmVirtualDeviceAccess@@AEBU_GUID@@AEBU2@KPEAGPEAUIUnknown@@IPEAUIVmHandleBroker@@$$ZAEBU2@AEBU2@W4tagCLSCTX@@VVmBstr@Vml@@PEAUIStream@@AEAIPEAU4@@Vmwp@ComputeService@@YAJAEBUWorkerProcessContext@01@PEAUIUnknown@@P8IVmVirtualDeviceAccess@@EAAJAEBU_GUID@@2KPEAG1IPEAUIVmHandleBroker@@@Z22$$QEAW4tagCLSCTX@@$$QEAVVmBstr@Vml@@$$QEAPEAUIStream@@AEAI$$QEAPEAU6@@Z
0x140026f17  mov     rcx, [rbp+38h]; this
0x140026f1b  test    eax, eax
0x140026f1d  jns     short loc_140026F34
0x140026f1f  mov     r9d, eax; char *
0x140026f22  lea     r8, aOnecoreVmCompu_52; "onecore\\vm\\compute\\shared\\vmwp\\lib"...
0x140026f29  mov     edx, 5Bh ; '['; void *
0x140026f2e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140026f34  mov     rcx, [rbp+bstrString]; bstrString
0x140026f38  test    rcx, rcx
0x140026f3b  jz      short loc_140026F4A
0x140026f3d  call    cs:__imp_SysFreeString
0x140026f44  nop     dword ptr [rax+rax+00h]
0x140026f49  nop
0x140026f4a  test    rbx, rbx
0x140026f4d  jz      short loc_140026F5F
0x140026f4f  mov     rax, [rbx]
0x140026f52  mov     rcx, rbx
0x140026f55  mov     rax, [rax+10h]
0x140026f59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140026f5e  nop
0x140026f5f  mov     rax, [rdi]
0x140026f62  mov     rcx, rdi
0x140026f65  mov     rax, [rax+10h]
0x140026f69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140026f6e  nop
0x140026f6f  add     rsp, 80h
0x140026f76  pop     r15
0x140026f78  pop     r14
0x140026f7a  pop     r13
0x140026f7c  pop     rdi
0x140026f7d  pop     rsi
0x140026f7e  pop     rbx
0x140026f7f  pop     rbp
0x140026f80  retn
```
