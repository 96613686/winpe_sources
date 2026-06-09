# CNetworkChangeMonitor<CInterfaceMonitor>::~CNetworkChangeMonitor<CInterfaceMonitor>(void)

- ea: `0x18000fd14`
- end: `0x18000fd4b`
- name: `??1?$CNetworkChangeMonitor@VCInterfaceMonitor@@@@QEAA@XZ`
- size: `55`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, loader_planting`

## callers

- `0x18000fd54`

## callees

- `0x180008464`
- `0x18000fc48`
- `0x180010534`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18000fd3f`

## pseudocode

```c
void __fastcall CNetworkChangeMonitor<CInterfaceMonitor>::~CNetworkChangeMonitor<CInterfaceMonitor>(
        struct _RTL_CRITICAL_SECTION *a1)
{
  CNetworkChangeMonitor<CInterfaceMonitor>::Shutdown(a1);
  CChildCount<CUdpSocket<CUdpEndpoint,IoOperation<CUdpEndpoint>>>::~CChildCount<CUdpSocket<CUdpEndpoint,IoOperation<CUdpEndpoint>>>((__int64)&a1[4].OwningThread);
  CTimer<CMadcapHandler>::Delete((__int64)&a1[1].SpinCount);
  DeleteCriticalSection(a1);
}

```

## disassembly

```asm
0x18000fd14  push    rbx
0x18000fd16  sub     rsp, 20h
0x18000fd1a  mov     rbx, rcx
0x18000fd1d  call    ?Shutdown@?$CNetworkChangeMonitor@VCInterfaceMonitor@@@@QEAAKXZ; CNetworkChangeMonitor<CInterfaceMonitor>::Shutdown(void)
0x18000fd22  lea     rcx, [rbx+0B0h]
0x18000fd29  call    ??1?$CChildCount@V?$CUdpSocket@VCUdpEndpoint@@U?$IoOperation@VCUdpEndpoint@@@@@@@@QEAA@XZ; CChildCount<CUdpSocket<CUdpEndpoint,IoOperation<CUdpEndpoint>>>::~CChildCount<CUdpSocket<CUdpEndpoint,IoOperation<CUdpEndpoint>>>(void)
0x18000fd2e  lea     rcx, [rbx+48h]
0x18000fd32  call    ?Delete@?$CTimer@VCMadcapHandler@@@@AEAAXXZ; CTimer<CMadcapHandler>::Delete(void)
0x18000fd37  mov     rcx, rbx
0x18000fd3a  add     rsp, 20h
0x18000fd3e  pop     rbx
0x18000fd3f  jmp     cs:__imp_DeleteCriticalSection
```
