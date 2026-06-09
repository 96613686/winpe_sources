# CWebCrawler::~CWebCrawler(void)

- ea: `0x18001df44`
- end: `0x18001dfc1`
- name: `??1CWebCrawler@@EEAA@XZ`
- size: `125`
- prototype: `void __fastcall(CWebCrawler *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001dfd0`

## callees

- `0x180004bd0`
- `0x18001df44`
- `0x1800225d8`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18001dfae`
- `KERNEL32!DeleteCriticalSection` at `0x18001dfae`

## pseudocode

```c
void __fastcall CWebCrawler::~CWebCrawler(struct _RTL_CRITICAL_SECTION *this)
{
  this->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&CWebCrawler::`vftable'{for `ISubscriptionAgentControl'};
  *(_QWORD *)&this->LockCount = &CCDLAgent::`vftable'{for `IShellPropSheetExt'};
  this->OwningThread = &CWebCrawler::`vftable'{for `IExtractIconA'};
  this->LockSemaphore = &CWebCrawler::`vftable'{for `IExtractIconW'};
  this->SpinCount = (ULONG_PTR)&CWebCrawler::`vftable'{for `ISubscriptionAgentShellExt'};
  this[2].SpinCount = (ULONG_PTR)&CWebCrawler::`vftable'{for `CUrlDownloadSink'};
  this[3].DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&CWebCrawler::`vftable'{for `CRunDeliveryAgentSink'};
  CWebCrawler::_CleanUp((CWebCrawler *)this);
  if ( SLODWORD(this[6].DebugInfo) >= 0 )
    DeleteCriticalSection(this + 5);
  CDeliveryAgent::~CDeliveryAgent((CDeliveryAgent *)this);
}

```

## disassembly

```asm
0x18001df44  push    rbx
0x18001df46  sub     rsp, 20h
0x18001df4a  lea     rax, ??_7CWebCrawler@@6BISubscriptionAgentControl@@@; const CWebCrawler::`vftable'{for `ISubscriptionAgentControl'}
0x18001df51  mov     rbx, rcx
0x18001df54  mov     [rcx], rax
0x18001df57  lea     rax, ??_7CCDLAgent@@6BIShellPropSheetExt@@@; const CCDLAgent::`vftable'{for `IShellPropSheetExt'}
0x18001df5e  mov     [rcx+8], rax
0x18001df62  lea     rax, ??_7CWebCrawler@@6BIExtractIconA@@@; const CWebCrawler::`vftable'{for `IExtractIconA'}
0x18001df69  mov     [rcx+10h], rax
0x18001df6d  lea     rax, ??_7CWebCrawler@@6BIExtractIconW@@@; const CWebCrawler::`vftable'{for `IExtractIconW'}
0x18001df74  mov     [rcx+18h], rax
0x18001df78  lea     rax, ??_7CWebCrawler@@6BISubscriptionAgentShellExt@@@; const CWebCrawler::`vftable'{for `ISubscriptionAgentShellExt'}
0x18001df7f  mov     [rcx+20h], rax
0x18001df83  lea     rax, ??_7CWebCrawler@@6BCUrlDownloadSink@@@; const CWebCrawler::`vftable'{for `CUrlDownloadSink'}
0x18001df8a  mov     [rcx+70h], rax
0x18001df8e  lea     rax, ??_7CWebCrawler@@6BCRunDeliveryAgentSink@@@; const CWebCrawler::`vftable'{for `CRunDeliveryAgentSink'}
0x18001df95  mov     [rcx+78h], rax
0x18001df99  call    ?_CleanUp@CWebCrawler@@IEAAXXZ; CWebCrawler::_CleanUp(void)
0x18001df9e  cmp     dword ptr [rbx+0F0h], 0
0x18001dfa5  jl      short loc_18001DFB4
0x18001dfa7  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x18001dfae  call    cs:__imp_DeleteCriticalSection
0x18001dfb4  mov     rcx, rbx; this
0x18001dfb7  add     rsp, 20h
0x18001dfbb  pop     rbx
0x18001dfbc  jmp     ??1CDeliveryAgent@@MEAA@XZ; CDeliveryAgent::~CDeliveryAgent(void)
```
