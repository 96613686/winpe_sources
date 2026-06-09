# CUdpSocket<CClientLibrary,IoOperation<CClientLibrary>>::~CUdpSocket<CClientLibrary,IoOperation<CClientLibrary>>(void)

- ea: `0x18000342c`
- end: `0x1800034a6`
- name: `??1?$CUdpSocket@VCClientLibrary@@U?$IoOperation@VCClientLibrary@@@@@@UEAA@XZ`
- size: `122`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180003ac0`

## callees

- `0x180003360`
- `0x18000a7fc`
- `0x18000a858`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180003463`
- `KERNEL32!DeleteCriticalSection` at `0x180003486`
- `KERNEL32!DeleteCriticalSection` at `0x180003463`
- `KERNEL32!DeleteCriticalSection` at `0x180003486`
- `WdsCommonLib!??1CCompPort@@QEAA@XZ` at `0x180003476`
- `WdsCommonLib!??1CCompPort@@QEAA@XZ` at `0x180003476`
- `WdsCommonLib!??1ICpRecvRequest@@MEAA@XZ` at `0x18000349a`

## pseudocode

```c
void __fastcall CUdpSocket<CClientLibrary,IoOperation<CClientLibrary>>::~CUdpSocket<CClientLibrary,IoOperation<CClientLibrary>>(
        __int64 a1)
{
  *(_QWORD *)a1 = &CUdpSocket<CClientLibrary,IoOperation<CClientLibrary>>::`vftable';
  CUdpSocket<CClientLibrary,IoOperation<CClientLibrary>>::Shutdown();
  CChildCount<CUdpSocket<CClientLibrary,IoOperation<CClientLibrary>>>::~CChildCount<CUdpSocket<CClientLibrary,IoOperation<CClientLibrary>>>(a1 + 480);
  CPool<IoOperation<CClientLibrary>>::Shutdown((PSLIST_HEADER)(a1 + 432));
  DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 376));
  CCompPort::~CCompPort((CCompPort *)(a1 + 288));
  DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
  ICpRecvRequest::~ICpRecvRequest((ICpRecvRequest *)a1);
}

```

## disassembly

```asm
0x18000342c  push    rbx
0x18000342e  sub     rsp, 20h
0x180003432  lea     rax, ??_7?$CUdpSocket@VCClientLibrary@@U?$IoOperation@VCClientLibrary@@@@@@6B@; const CUdpSocket<CClientLibrary,IoOperation<CClientLibrary>>::`vftable'
0x180003439  mov     rbx, rcx
0x18000343c  mov     [rcx], rax
0x18000343f  call    ?Shutdown@?$CUdpSocket@VCClientLibrary@@U?$IoOperation@VCClientLibrary@@@@@@QEAAKXZ; CUdpSocket<CClientLibrary,IoOperation<CClientLibrary>>::Shutdown(void)
0x180003444  lea     rcx, [rbx+1E0h]
0x18000344b  call    ??1?$CChildCount@V?$CUdpSocket@VCClientLibrary@@U?$IoOperation@VCClientLibrary@@@@@@@@QEAA@XZ; CChildCount<CUdpSocket<CClientLibrary,IoOperation<CClientLibrary>>>::~CChildCount<CUdpSocket<CClientLibrary,IoOperation<CClientLibrary>>>(void)
0x180003450  lea     rcx, [rbx+1B0h]; ListHead
0x180003457  call    ?Shutdown@?$CPool@U?$IoOperation@VCClientLibrary@@@@@@QEAAXXZ; CPool<IoOperation<CClientLibrary>>::Shutdown(void)
0x18000345c  lea     rcx, [rbx+178h]; lpCriticalSection
0x180003463  call    cs:__imp_DeleteCriticalSection
0x18000346a  nop     dword ptr [rax+rax+00h]
0x18000346f  lea     rcx, [rbx+120h]
0x180003476  call    cs:__imp_??1CCompPort@@QEAA@XZ; CCompPort::~CCompPort(void)
0x18000347d  nop     dword ptr [rax+rax+00h]
0x180003482  lea     rcx, [rbx+8]; lpCriticalSection
0x180003486  call    cs:__imp_DeleteCriticalSection
0x18000348d  nop     dword ptr [rax+rax+00h]
0x180003492  mov     rcx, rbx
0x180003495  add     rsp, 20h
0x180003499  pop     rbx
0x18000349a  jmp     cs:__imp_??1ICpRecvRequest@@MEAA@XZ; ICpRecvRequest::~ICpRecvRequest(void)
```
