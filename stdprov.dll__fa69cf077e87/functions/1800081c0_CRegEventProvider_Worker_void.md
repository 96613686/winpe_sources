# CRegEventProvider::Worker(void *)

- ea: `0x1800081c0`
- end: `0x1800082c9`
- name: `?Worker@CRegEventProvider@@KAKPEAX@Z`
- size: `265`
- prototype: `__int64 __fastcall(char *lpThreadParameter)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800081c0`
- `0x1800082d0`
- `0x180008300`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800081cf`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800081cf`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180008293`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800082b8`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180008293`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800082b8`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800081ec`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800081ec`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008223`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008275`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008223`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008275`
- `wbemcomn!?Dequeue@CFlexQueue@@QEAAPEAXXZ` at `0x180008215`
- `wbemcomn!?Dequeue@CFlexQueue@@QEAAPEAXXZ` at `0x180008215`

## pseudocode

```c
__int64 __fastcall CRegEventProvider::Worker(char *lpThreadParameter)
{
  DWORD v2; // ebx
  char *v3; // rdi
  int v4; // ebx
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+48h] [rbp+10h] BYREF
  LPCRITICAL_SECTION v7; // [rsp+50h] [rbp+18h] BYREF

  CoInitializeEx(0, 0);
  while ( 1 )
  {
    v2 = WaitForSingleObject(*((HANDLE *)lpThreadParameter + 28), 0xFFFFFFFF);
    if ( v2 )
    {
      CoUninitialize();
      return v2;
    }
    CInCritSec::CInCritSec((CInCritSec *)&lpCriticalSection, (struct _RTL_CRITICAL_SECTION *)(lpThreadParameter + 232));
    v3 = (char *)CFlexQueue::Dequeue((CFlexQueue *)(lpThreadParameter + 272));
    LeaveCriticalSection(lpCriticalSection);
    if ( !v3 )
      break;
    CInCritSec::CInCritSec((CInCritSec *)&v7, (struct _RTL_CRITICAL_SECTION *)(v3 + 184));
    if ( *((_DWORD *)v3 + 41) >= (signed int)v2 )
    {
      v4 = *((_DWORD *)v3 + 42);
      CRegistryEventRequest::ResetOnChangeHandle((CRegistryEventRequest *)v3);
      if ( !v4 )
        (*(void (__fastcall **)(char *, _QWORD))(*(_QWORD *)v3 + 8LL))(v3, 0);
    }
    LeaveCriticalSection(v7);
    if ( !_InterlockedDecrement((volatile signed __int32 *)v3 + 2) )
      (**(void (__fastcall ***)(void *, __int64))v3)(v3, 1);
  }
  CoUninitialize();
  return 0;
}

```

## disassembly

```asm
0x1800081c0  push    rbx
0x1800081c2  push    rsi
0x1800081c3  push    rdi
0x1800081c4  sub     rsp, 20h
0x1800081c8  mov     rsi, rcx
0x1800081cb  xor     edx, edx; dwCoInit
0x1800081cd  xor     ecx, ecx; pvReserved
0x1800081cf  call    cs:__imp_CoInitializeEx
0x1800081d5  nop     word ptr [rax+rax+00000000h]
0x1800081e0  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x1800081e5  mov     rcx, [rsi+0E0h]; hHandle
0x1800081ec  call    cs:__imp_WaitForSingleObject
0x1800081f2  mov     ebx, eax
0x1800081f4  test    eax, eax
0x1800081f6  jnz     loc_180008293
0x1800081fc  lea     rdx, [rsi+0E8h]; struct _RTL_CRITICAL_SECTION *
0x180008203  lea     rcx, [rsp+38h+lpCriticalSection]; this
0x180008208  call    ??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z; CInCritSec::CInCritSec(_RTL_CRITICAL_SECTION *)
0x18000820d  nop
0x18000820e  lea     rcx, [rsi+110h]
0x180008215  call    cs:__imp_?Dequeue@CFlexQueue@@QEAAPEAXXZ; CFlexQueue::Dequeue(void)
0x18000821b  mov     rdi, rax
0x18000821e  mov     rcx, [rsp+38h+lpCriticalSection]; lpCriticalSection
0x180008223  call    cs:__imp_LeaveCriticalSection
0x180008229  test    rdi, rdi
0x18000822c  jz      loc_1800082B8
0x180008232  lea     rdx, [rdi+0B8h]; struct _RTL_CRITICAL_SECTION *
0x180008239  lea     rcx, [rsp+38h+arg_10]; this
0x18000823e  call    ??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z; CInCritSec::CInCritSec(_RTL_CRITICAL_SECTION *)
0x180008243  nop
0x180008244  cmp     [rdi+0A4h], ebx
0x18000824a  jl      short loc_180008270
0x18000824c  mov     ebx, [rdi+0A8h]
0x180008252  mov     rcx, rdi; this
0x180008255  call    ?ResetOnChangeHandle@CRegistryEventRequest@@QEAAHXZ; CRegistryEventRequest::ResetOnChangeHandle(void)
0x18000825a  test    ebx, ebx
0x18000825c  jnz     short loc_180008270
0x18000825e  mov     rax, [rdi]
0x180008261  xor     edx, edx
0x180008263  mov     rcx, rdi
0x180008266  mov     rax, [rax+8]
0x18000826a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000826f  nop
0x180008270  mov     rcx, [rsp+38h+arg_10]; lpCriticalSection
0x180008275  call    cs:__imp_LeaveCriticalSection
0x18000827b  mov     eax, 0FFFFFFFFh
0x180008280  lock xadd [rdi+8], eax
0x180008285  sub     eax, 1
0x180008288  mov     [rsp+38h+arg_0], eax
0x18000828c  jz      short loc_1800082A3
0x18000828e  jmp     loc_1800081E0
0x180008293  call    cs:__imp_CoUninitialize
0x180008299  mov     eax, ebx
0x18000829b  add     rsp, 20h
0x18000829f  pop     rdi
0x1800082a0  pop     rsi
0x1800082a1  pop     rbx
0x1800082a2  retn
0x1800082a3  mov     rax, [rdi]
0x1800082a6  mov     edx, 1
0x1800082ab  mov     rcx, rdi
0x1800082ae  mov     rax, [rax]
0x1800082b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800082b6  jmp     short loc_18000828E
0x1800082b8  call    cs:__imp_CoUninitialize
0x1800082be  xor     eax, eax
0x1800082c0  jmp     short loc_18000829B
0x1800082c2  mov     eax, 8
0x1800082c7  jmp     short loc_18000829B
```
