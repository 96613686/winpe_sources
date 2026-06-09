# CUdpSocket<CUdpEndpoint,IoOperation<CUdpEndpoint>>::~CUdpSocket<CUdpEndpoint,IoOperation<CUdpEndpoint>>(void)

- ea: `0x1800181bc`
- end: `0x180018236`
- name: `??1?$CUdpSocket@VCUdpEndpoint@@U?$IoOperation@VCUdpEndpoint@@@@@@UEAA@XZ`
- size: `122`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001823c`
- `0x180018330`

## callees

- `0x18000fc48`
- `0x18001a1f4`
- `0x18001a250`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x1800181f3`
- `KERNEL32!DeleteCriticalSection` at `0x180018216`
- `KERNEL32!DeleteCriticalSection` at `0x1800181f3`
- `KERNEL32!DeleteCriticalSection` at `0x180018216`
- `WdsServerCommonLib!??1CCompPort@@QEAA@XZ` at `0x180018206`
- `WdsServerCommonLib!??1CCompPort@@QEAA@XZ` at `0x180018206`
- `WdsServerCommonLib!??1ICpRecvRequest@@MEAA@XZ` at `0x18001822a`

## pseudocode

```c
void __fastcall CUdpSocket<CUdpEndpoint,IoOperation<CUdpEndpoint>>::~CUdpSocket<CUdpEndpoint,IoOperation<CUdpEndpoint>>(
        __int64 a1)
{
  *(_QWORD *)a1 = &CUdpSocket<CUdpEndpoint,IoOperation<CUdpEndpoint>>::`vftable';
  CUdpSocket<CUdpEndpoint,IoOperation<CUdpEndpoint>>::Shutdown();
  CChildCount<CUdpSocket<CUdpEndpoint,IoOperation<CUdpEndpoint>>>::~CChildCount<CUdpSocket<CUdpEndpoint,IoOperation<CUdpEndpoint>>>(a1 + 480);
  CPool<IoOperation<CUdpEndpoint>>::Shutdown((PSLIST_HEADER)(a1 + 432));
  DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 376));
  CCompPort::~CCompPort((CCompPort *)(a1 + 288));
  DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
  ICpRecvRequest::~ICpRecvRequest((ICpRecvRequest *)a1);
}

```

## disassembly

```asm
0x1800181bc  push    rbx
0x1800181be  sub     rsp, 20h
0x1800181c2  lea     rax, ??_7?$CUdpSocket@VCUdpEndpoint@@U?$IoOperation@VCUdpEndpoint@@@@@@6B@; const CUdpSocket<CUdpEndpoint,IoOperation<CUdpEndpoint>>::`vftable'
0x1800181c9  mov     rbx, rcx
0x1800181cc  mov     [rcx], rax
0x1800181cf  call    ?Shutdown@?$CUdpSocket@VCUdpEndpoint@@U?$IoOperation@VCUdpEndpoint@@@@@@QEAAKXZ; CUdpSocket<CUdpEndpoint,IoOperation<CUdpEndpoint>>::Shutdown(void)
0x1800181d4  lea     rcx, [rbx+1E0h]
0x1800181db  call    ??1?$CChildCount@V?$CUdpSocket@VCUdpEndpoint@@U?$IoOperation@VCUdpEndpoint@@@@@@@@QEAA@XZ; CChildCount<CUdpSocket<CUdpEndpoint,IoOperation<CUdpEndpoint>>>::~CChildCount<CUdpSocket<CUdpEndpoint,IoOperation<CUdpEndpoint>>>(void)
0x1800181e0  lea     rcx, [rbx+1B0h]; ListHead
0x1800181e7  call    ?Shutdown@?$CPool@U?$IoOperation@VCUdpEndpoint@@@@@@QEAAXXZ; CPool<IoOperation<CUdpEndpoint>>::Shutdown(void)
0x1800181ec  lea     rcx, [rbx+178h]; lpCriticalSection
0x1800181f3  call    cs:__imp_DeleteCriticalSection
0x1800181fa  nop     dword ptr [rax+rax+00h]
0x1800181ff  lea     rcx, [rbx+120h]
0x180018206  call    cs:__imp_??1CCompPort@@QEAA@XZ; CCompPort::~CCompPort(void)
0x18001820d  nop     dword ptr [rax+rax+00h]
0x180018212  lea     rcx, [rbx+8]; lpCriticalSection
0x180018216  call    cs:__imp_DeleteCriticalSection
0x18001821d  nop     dword ptr [rax+rax+00h]
0x180018222  mov     rcx, rbx
0x180018225  add     rsp, 20h
0x180018229  pop     rbx
0x18001822a  jmp     cs:__imp_??1ICpRecvRequest@@MEAA@XZ; ICpRecvRequest::~ICpRecvRequest(void)
```
