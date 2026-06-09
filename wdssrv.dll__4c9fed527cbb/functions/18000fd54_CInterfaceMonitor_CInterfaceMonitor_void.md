# CInterfaceMonitor::~CInterfaceMonitor(void)

- ea: `0x18000fd54`
- end: `0x18000fd9f`
- name: `??1CInterfaceMonitor@@QEAA@XZ`
- size: `75`
- prototype: `void __fastcall(CInterfaceMonitor *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800135e8`

## callees

- `0x180003944`
- `0x18000fd14`
- `0x1800105f0`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18000fd93`

## pseudocode

```c
void __fastcall CInterfaceMonitor::~CInterfaceMonitor(CInterfaceMonitor *this)
{
  unsigned int v2; // eax
  __int64 v3; // rdx

  v2 = CInterfaceMonitor::Shutdown(this);
  ElValidateWin32(v2, v3, "base\\eco\\wds\\wdssrv\\server\\src\\ifmonitor.cpp", 38);
  CNetworkChangeMonitor<CInterfaceMonitor>::~CNetworkChangeMonitor<CInterfaceMonitor>((struct _RTL_CRITICAL_SECTION *)((char *)this + 352));
  CNetworkChangeMonitor<CInterfaceMonitor>::~CNetworkChangeMonitor<CInterfaceMonitor>((struct _RTL_CRITICAL_SECTION *)this + 1);
  DeleteCriticalSection((LPCRITICAL_SECTION)this);
}

```

## disassembly

```asm
0x18000fd54  push    rbx
0x18000fd56  sub     rsp, 20h
0x18000fd5a  mov     rbx, rcx
0x18000fd5d  call    ?Shutdown@CInterfaceMonitor@@QEAAKXZ; CInterfaceMonitor::Shutdown(void)
0x18000fd62  mov     ecx, eax
0x18000fd64  lea     r8, aBaseEcoWdsWdss_1; "base\\eco\\wds\\wdssrv\\server\\src\\if"...
0x18000fd6b  mov     r9d, 26h ; '&'
0x18000fd71  call    ElValidateWin32
0x18000fd76  lea     rcx, [rbx+160h]
0x18000fd7d  call    ??1?$CNetworkChangeMonitor@VCInterfaceMonitor@@@@QEAA@XZ; CNetworkChangeMonitor<CInterfaceMonitor>::~CNetworkChangeMonitor<CInterfaceMonitor>(void)
0x18000fd82  lea     rcx, [rbx+28h]
0x18000fd86  call    ??1?$CNetworkChangeMonitor@VCInterfaceMonitor@@@@QEAA@XZ; CNetworkChangeMonitor<CInterfaceMonitor>::~CNetworkChangeMonitor<CInterfaceMonitor>(void)
0x18000fd8b  mov     rcx, rbx
0x18000fd8e  add     rsp, 20h
0x18000fd92  pop     rbx
0x18000fd93  jmp     cs:__imp_DeleteCriticalSection
```
