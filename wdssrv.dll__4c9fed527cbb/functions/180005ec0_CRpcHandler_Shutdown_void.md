# CRpcHandler::Shutdown(void)

- ea: `0x180005ec0`
- end: `0x18000601f`
- name: `?Shutdown@CRpcHandler@@UEAAKXZ`
- size: `351`
- prototype: `unsigned int __fastcall(CRpcHandler *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180003c78`

## callees

- `0x180002358`
- `0x180003fb4`
- `0x180005ec0`
- `0x18001d010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180005f3b`
- `KERNEL32!LeaveCriticalSection` at `0x180005f3b`
- `KERNEL32!EnterCriticalSection` at `0x180005edf`
- `KERNEL32!EnterCriticalSection` at `0x180005f28`
- `KERNEL32!EnterCriticalSection` at `0x180005edf`
- `KERNEL32!EnterCriticalSection` at `0x180005f28`
- `WdsServerCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180005fdb`
- `WdsServerCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180005fdb`
- `WdsServerCommonLib!?WdsAssert@@YAXPEBDK0HH@Z` at `0x180005f18`
- `WdsServerCommonLib!?WdsAssert@@YAXPEBDK0HH@Z` at `0x180005f9a`
- `WdsServerCommonLib!?WdsAssert@@YAXPEBDK0HH@Z` at `0x180005f18`
- `WdsServerCommonLib!?WdsAssert@@YAXPEBDK0HH@Z` at `0x180005f9a`

## string_xrefs

- `0x180005eff`: `m_hServerThread == 0`

## pseudocode

```c
__int64 __fastcall CRpcHandler::Shutdown(CRpcHandler *this)
{
  char *v1; // rsi
  bool v3; // zf
  __int64 v4; // rbx
  __int64 v5; // rbx
  __int64 v6; // rax
  const wchar_t *v7; // r9
  char *v9; // [rsp+30h] [rbp-18h] BYREF
  int v10; // [rsp+38h] [rbp-10h]
  __int64 v11; // [rsp+50h] [rbp+8h] BYREF

  v1 = (char *)this + 96;
  v9 = (char *)this + 96;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 112));
  v3 = *((_QWORD *)this + 10) == 0;
  v10 = 1;
  if ( !v3 )
    WdsAssert("base\\eco\\wds\\wdssrv\\server\\src\\rpchandler.cpp", 0x10Au, "m_hServerThread == 0", 1, 0);
  EnterCriticalSection((LPCRITICAL_SECTION)(v1 + 16));
  v4 = *(_QWORD *)v1;
  LeaveCriticalSection((LPCRITICAL_SECTION)(v1 + 16));
  if ( v4 )
  {
    v11 = *(_QWORD *)v1;
    while ( v11 )
    {
      v5 = CList<CRegRpcEndpoint,CCriticalSection>::DeleteAt(v1, &v11);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v5 + 56), 0) )
        WdsAssert(
          "base\\eco\\wds\\wdssrv\\server\\src\\rpchandler.cpp",
          0x119u,
          "pRegEndpoint->GetPendingRequests() == 0",
          1,
          0);
      v6 = *(_QWORD *)(v5 + 64);
      if ( v6 )
        v7 = *(const wchar_t **)(v6 + 16);
      else
        v7 = L"<Unknown>";
      CTrace::Trace(
        (CTrace *)qword_180039310,
        0x80000u,
        L"[%s][RPC][Ep:%s] Provider did not close Endpoint.",
        v7,
        v5 + 1288);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 8LL))(v5);
    }
  }
  CAutoTypeLock<CList<CRegUdpEndpoint,CCriticalSection>>::~CAutoTypeLock<CList<CRegUdpEndpoint,CCriticalSection>>(&v9);
  return 0;
}

```

## disassembly

```asm
0x180005ec0  mov     [rsp+arg_8], rbx
0x180005ec5  mov     [rsp+arg_10], rsi
0x180005eca  push    rdi
0x180005ecb  sub     rsp, 40h
0x180005ecf  lea     rsi, [rcx+60h]
0x180005ed3  mov     rbx, rcx
0x180005ed6  add     rcx, 70h ; 'p'; lpCriticalSection
0x180005eda  mov     [rsp+48h+var_18], rsi
0x180005edf  call    cs:__imp_EnterCriticalSection
0x180005ee6  nop     dword ptr [rax+rax+00h]
0x180005eeb  cmp     qword ptr [rbx+50h], 0
0x180005ef0  mov     [rsp+48h+var_10], 1
0x180005ef8  jz      short loc_180005F24
0x180005efa  and     dword ptr [rsp+48h+var_28], 0
0x180005eff  lea     r8, aMHserverthread; "m_hServerThread == 0"
0x180005f06  mov     r9d, 1
0x180005f0c  lea     rcx, aBaseEcoWdsWdss_6; "base\\eco\\wds\\wdssrv\\server\\src\\rp"...
0x180005f13  mov     edx, 10Ah
0x180005f18  call    cs:__imp_?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x180005f1f  nop     dword ptr [rax+rax+00h]
0x180005f24  lea     rcx, [rsi+10h]; lpCriticalSection
0x180005f28  call    cs:__imp_EnterCriticalSection
0x180005f2f  nop     dword ptr [rax+rax+00h]
0x180005f34  mov     rbx, [rsi]
0x180005f37  lea     rcx, [rsi+10h]; lpCriticalSection
0x180005f3b  call    cs:__imp_LeaveCriticalSection
0x180005f42  nop     dword ptr [rax+rax+00h]
0x180005f47  test    rbx, rbx
0x180005f4a  jz      loc_180006002
0x180005f50  mov     rax, [rsi]
0x180005f53  mov     [rsp+48h+arg_0], rax
0x180005f58  test    rax, rax
0x180005f5b  jz      loc_180006002
0x180005f61  lea     rdx, [rsp+48h+arg_0]
0x180005f66  mov     rcx, rsi
0x180005f69  call    ?DeleteAt@?$CList@VCRegRpcEndpoint@@VCCriticalSection@@@@QEAAPEAVCRegRpcEndpoint@@AEAPEAX@Z; CList<CRegRpcEndpoint,CCriticalSection>::DeleteAt(void * &)
0x180005f6e  mov     rbx, rax
0x180005f71  xor     ecx, ecx
0x180005f73  lock xadd [rax+38h], ecx
0x180005f78  test    ecx, ecx
0x180005f7a  jz      short loc_180005FA6
0x180005f7c  and     dword ptr [rsp+48h+var_28], 0
0x180005f81  lea     r8, aPregendpointGe; "pRegEndpoint->GetPendingRequests() == 0"
0x180005f88  mov     r9d, 1
0x180005f8e  lea     rcx, aBaseEcoWdsWdss_6; "base\\eco\\wds\\wdssrv\\server\\src\\rp"...
0x180005f95  mov     edx, 119h
0x180005f9a  call    cs:__imp_?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x180005fa1  nop     dword ptr [rax+rax+00h]
0x180005fa6  mov     rax, [rbx+40h]
0x180005faa  lea     rcx, [rbx+508h]
0x180005fb1  test    rax, rax
0x180005fb4  jz      short loc_180005FBC
0x180005fb6  mov     r9, [rax+10h]
0x180005fba  jmp     short loc_180005FC3
0x180005fbc  lea     r9, aUnknown_0; "<Unknown>"
0x180005fc3  mov     [rsp+48h+var_28], rcx
0x180005fc8  lea     r8, aSRpcEpSProvide; "[%s][RPC][Ep:%s] Provider did not close"...
0x180005fcf  lea     rcx, qword_180039310
0x180005fd6  mov     edx, 80000h
0x180005fdb  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x180005fe2  nop     dword ptr [rax+rax+00h]
0x180005fe7  mov     rax, [rbx]
0x180005fea  mov     rcx, rbx
0x180005fed  mov     rax, [rax+8]
0x180005ff1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ff6  cmp     [rsp+48h+arg_0], 0
0x180005ffc  jnz     loc_180005F61
0x180006002  lea     rcx, [rsp+48h+var_18]
0x180006007  call    ??1?$CAutoTypeLock@V?$CList@VCRegUdpEndpoint@@VCCriticalSection@@@@@@QEAA@XZ; CAutoTypeLock<CList<CRegUdpEndpoint,CCriticalSection>>::~CAutoTypeLock<CList<CRegUdpEndpoint,CCriticalSection>>(void)
0x18000600c  mov     rbx, [rsp+48h+arg_8]
0x180006011  xor     eax, eax
0x180006013  mov     rsi, [rsp+48h+arg_10]
0x180006018  add     rsp, 40h
0x18000601c  pop     rdi
0x18000601d  retn
```
