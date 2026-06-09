# CWdsService::~CWdsService(void)

- ea: `0x180007148`
- end: `0x180007244`
- name: `??1CWdsService@@QEAA@XZ`
- size: `252`
- prototype: `void __fastcall(CWdsService *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callers

- `0x18001c700`

## callees

- `0x180007148`
- `0x180008464`
- `0x1800135e8`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180007188`
- `KERNEL32!DeleteCriticalSection` at `0x180007220`
- `KERNEL32!DeleteCriticalSection` at `0x180007188`
- `KERNEL32!DeleteCriticalSection` at `0x180007220`
- `KERNEL32!InterlockedPopEntrySList` at `0x1800071ea`
- `KERNEL32!InterlockedPopEntrySList` at `0x1800071ea`
- `WdsServerCommonLib!?WdsPrivateHpFree@@YAKPEAX@Z` at `0x180007166`
- `WdsServerCommonLib!?WdsPrivateHpFree@@YAKPEAX@Z` at `0x18000720b`
- `WdsServerCommonLib!?WdsPrivateHpFree@@YAKPEAX@Z` at `0x180007166`
- `WdsServerCommonLib!?WdsPrivateHpFree@@YAKPEAX@Z` at `0x18000720b`
- `WdsServerCommonLib!??1CCompPort@@QEAA@XZ` at `0x1800071c5`
- `WdsServerCommonLib!??1CCompPort@@QEAA@XZ` at `0x1800071c5`
- `WdsServerCommonLib!??1ICpRecvRequest@@MEAA@XZ` at `0x1800071d4`
- `WdsServerCommonLib!??1ICpRecvRequest@@MEAA@XZ` at `0x1800071d4`
- `WdsServerCommonLib!?Shutdown@CCompPort@@QEAAKXZ` at `0x1800071b5`
- `WdsServerCommonLib!?Shutdown@CCompPort@@QEAAKXZ` at `0x1800071b5`

## pseudocode

```c
void __fastcall CWdsService::~CWdsService(CWdsService *this)
{
  void *v2; // rcx
  PSLIST_ENTRY v3; // rax

  v2 = (void *)*((_QWORD *)this + 8421);
  if ( v2 )
  {
    WdsPrivateHpFree(v2);
    *((_QWORD *)this + 8421) = 0;
  }
  *((_DWORD *)this + 16840) = 0;
  DeleteCriticalSection((LPCRITICAL_SECTION)this + 1683);
  CTimer<CMadcapHandler>::Delete((char *)this + 67264);
  *((_QWORD *)this + 8396) = &CWorkItemHandler::`vftable';
  CCompPort::Shutdown((CWdsService *)((char *)this + 67176));
  CCompPort::~CCompPort((CWdsService *)((char *)this + 67176));
  ICpRecvRequest::~ICpRecvRequest((CWdsService *)((char *)this + 67168));
  while ( 1 )
  {
    v3 = InterlockedPopEntrySList((PSLIST_HEADER)this + 4195);
    if ( !v3 )
      break;
    _InterlockedDecrement((volatile signed __int32 *)this + 16784);
    if ( v3 == (PSLIST_ENTRY)2176 )
      break;
    WdsPrivateHpFree(&v3[-136]);
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 67072));
  CInterfaceHandler::~CInterfaceHandler((CWdsService *)((char *)this + 48));
}

```

## disassembly

```asm
0x180007148  mov     [rsp+arg_0], rbx
0x18000714d  mov     [rsp+arg_8], rsi
0x180007152  push    rdi
0x180007153  sub     rsp, 20h
0x180007157  mov     rsi, rcx
0x18000715a  mov     rcx, [rcx+10728h]
0x180007161  test    rcx, rcx
0x180007164  jz      short loc_18000717A
0x180007166  call    cs:__imp_?WdsPrivateHpFree@@YAKPEAX@Z; WdsPrivateHpFree(void *)
0x18000716d  nop     dword ptr [rax+rax+00h]
0x180007172  and     qword ptr [rsi+10728h], 0
0x18000717a  and     dword ptr [rsi+10720h], 0
0x180007181  lea     rcx, [rsi+106F8h]; lpCriticalSection
0x180007188  call    cs:__imp_DeleteCriticalSection
0x18000718f  nop     dword ptr [rax+rax+00h]
0x180007194  lea     rcx, [rsi+106C0h]
0x18000719b  call    ?Delete@?$CTimer@VCMadcapHandler@@@@AEAAXXZ; CTimer<CMadcapHandler>::Delete(void)
0x1800071a0  lea     rdi, [rsi+10660h]
0x1800071a7  lea     rax, ??_7CWorkItemHandler@@6B@; const CWorkItemHandler::`vftable'
0x1800071ae  lea     rcx, [rdi+8]
0x1800071b2  mov     [rdi], rax
0x1800071b5  call    cs:__imp_?Shutdown@CCompPort@@QEAAKXZ; CCompPort::Shutdown(void)
0x1800071bc  nop     dword ptr [rax+rax+00h]
0x1800071c1  lea     rcx, [rdi+8]
0x1800071c5  call    cs:__imp_??1CCompPort@@QEAA@XZ; CCompPort::~CCompPort(void)
0x1800071cc  nop     dword ptr [rax+rax+00h]
0x1800071d1  mov     rcx, rdi
0x1800071d4  call    cs:__imp_??1ICpRecvRequest@@MEAA@XZ; ICpRecvRequest::~ICpRecvRequest(void)
0x1800071db  nop     dword ptr [rax+rax+00h]
0x1800071e0  lea     rbx, [rsi+10630h]
0x1800071e7  mov     rcx, rbx; ListHead
0x1800071ea  call    cs:__imp_InterlockedPopEntrySList
0x1800071f1  nop     dword ptr [rax+rax+00h]
0x1800071f6  test    rax, rax
0x1800071f9  jz      short loc_180007219
0x1800071fb  lock dec dword ptr [rbx+10h]
0x1800071ff  lea     rcx, [rax-880h]
0x180007206  test    rcx, rcx
0x180007209  jz      short loc_180007219
0x18000720b  call    cs:__imp_?WdsPrivateHpFree@@YAKPEAX@Z; WdsPrivateHpFree(void *)
0x180007212  nop     dword ptr [rax+rax+00h]
0x180007217  jmp     short loc_1800071E7
0x180007219  lea     rcx, [rsi+10600h]; lpCriticalSection
0x180007220  call    cs:__imp_DeleteCriticalSection
0x180007227  nop     dword ptr [rax+rax+00h]
0x18000722c  lea     rcx, [rsi+30h]; this
0x180007230  mov     rbx, [rsp+28h+arg_0]
0x180007235  mov     rsi, [rsp+28h+arg_8]
0x18000723a  add     rsp, 20h
0x18000723e  pop     rdi
0x18000723f  jmp     ??1CInterfaceHandler@@QEAA@XZ; CInterfaceHandler::~CInterfaceHandler(void)
```
