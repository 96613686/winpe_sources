# CRpcHandler::~CRpcHandler(void)

- ea: `0x180003c78`
- end: `0x180003d17`
- name: `??1CRpcHandler@@UEAA@XZ`
- size: `159`
- prototype: `void __fastcall(CRpcHandler *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180003d20`
- `0x1800135e8`

## callees

- `0x180003c78`
- `0x180005ec0`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180003cc2`
- `KERNEL32!DeleteCriticalSection` at `0x180003cc2`
- `KERNEL32!InterlockedPopEntrySList` at `0x180003cd2`
- `KERNEL32!InterlockedPopEntrySList` at `0x180003cd2`
- `WdsServerCommonLib!?WdsPrivateHpFree@@YAKPEAX@Z` at `0x180003cf3`
- `WdsServerCommonLib!?WdsPrivateHpFree@@YAKPEAX@Z` at `0x180003cf3`
- `WdsServerCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180003cb2`
- `WdsServerCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180003cb2`

## string_xrefs

- `0x180003c9f`: `[RPC] Deleted.`

## pseudocode

```c
void __fastcall CRpcHandler::~CRpcHandler(CRpcHandler *this)
{
  PSLIST_ENTRY v2; // rax

  *(_QWORD *)this = &CRpcHandler::`vftable'{for `IEndpointHandler'};
  *((_QWORD *)this + 2) = &CRpcHandler::`vftable'{for `IWdsWorkItem'};
  CRpcHandler::Shutdown(this);
  CTrace::Trace((CTrace *)qword_180039310, 0x20000u, L"[RPC] Deleted.");
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 112));
  while ( 1 )
  {
    v2 = InterlockedPopEntrySList((PSLIST_HEADER)this + 2);
    if ( !v2 )
      break;
    _InterlockedDecrement((volatile signed __int32 *)this + 12);
    if ( v2 == (PSLIST_ENTRY)2288 )
      break;
    WdsPrivateHpFree(&v2[-143]);
  }
  *(_QWORD *)this = &CRefCount::`vftable';
}

```

## disassembly

```asm
0x180003c78  mov     [rsp+arg_0], rbx
0x180003c7d  push    rdi
0x180003c7e  sub     rsp, 20h
0x180003c82  lea     rax, ??_7CRpcHandler@@6BIEndpointHandler@@@; const CRpcHandler::`vftable'{for `IEndpointHandler'}
0x180003c89  mov     rbx, rcx
0x180003c8c  mov     [rcx], rax
0x180003c8f  lea     rax, ??_7CRpcHandler@@6BIWdsWorkItem@@@; const CRpcHandler::`vftable'{for `IWdsWorkItem'}
0x180003c96  mov     [rcx+10h], rax
0x180003c9a  call    ?Shutdown@CRpcHandler@@UEAAKXZ; CRpcHandler::Shutdown(void)
0x180003c9f  lea     r8, aRpcDeleted; "[RPC] Deleted."
0x180003ca6  mov     edx, 20000h
0x180003cab  lea     rcx, qword_180039310
0x180003cb2  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x180003cb9  nop     dword ptr [rax+rax+00h]
0x180003cbe  lea     rcx, [rbx+70h]; lpCriticalSection
0x180003cc2  call    cs:__imp_DeleteCriticalSection
0x180003cc9  nop     dword ptr [rax+rax+00h]
0x180003cce  lea     rcx, [rbx+20h]; ListHead
0x180003cd2  call    cs:__imp_InterlockedPopEntrySList
0x180003cd9  nop     dword ptr [rax+rax+00h]
0x180003cde  test    rax, rax
0x180003ce1  jz      short loc_180003D01
0x180003ce3  lock dec dword ptr [rbx+30h]
0x180003ce7  lea     rcx, [rax-8F0h]
0x180003cee  test    rcx, rcx
0x180003cf1  jz      short loc_180003D01
0x180003cf3  call    cs:__imp_?WdsPrivateHpFree@@YAKPEAX@Z; WdsPrivateHpFree(void *)
0x180003cfa  nop     dword ptr [rax+rax+00h]
0x180003cff  jmp     short loc_180003CCE
0x180003d01  lea     rax, ??_7CRefCount@@6B@; const CRefCount::`vftable'
0x180003d08  mov     [rbx], rax
0x180003d0b  mov     rbx, [rsp+28h+arg_0]
0x180003d10  add     rsp, 20h
0x180003d14  pop     rdi
0x180003d15  retn
```
