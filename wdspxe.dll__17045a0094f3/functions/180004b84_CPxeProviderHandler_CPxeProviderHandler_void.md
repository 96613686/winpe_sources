# CPxeProviderHandler::~CPxeProviderHandler(void)

- ea: `0x180004b84`
- end: `0x180004c4f`
- name: `??1CPxeProviderHandler@@QEAA@XZ`
- size: `203`
- prototype: `void __fastcall(CPxeProviderHandler *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x1800120a0`

## callees

- `0x180004b84`
- `0x180006adc`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180004bde`
- `msvcrt!??3@YAXPEAX@Z` at `0x180004bde`
- `KERNEL32!DeleteCriticalSection` at `0x180004ba7`
- `KERNEL32!DeleteCriticalSection` at `0x180004c19`
- `KERNEL32!DeleteCriticalSection` at `0x180004c29`
- `KERNEL32!DeleteCriticalSection` at `0x180004ba7`
- `KERNEL32!DeleteCriticalSection` at `0x180004c19`
- `KERNEL32!DeleteCriticalSection` at `0x180004c29`
- `KERNEL32!DeleteCriticalSection` at `0x180004c43`
- `KERNEL32!InterlockedPopEntrySList` at `0x180004bbd`
- `KERNEL32!InterlockedPopEntrySList` at `0x180004bbd`
- `WdsCommonLib!?Shutdown@CBannedDeviceIds@@QEAAKXZ` at `0x180004c09`
- `WdsCommonLib!?Shutdown@CBannedDeviceIds@@QEAAKXZ` at `0x180004c09`
- `WdsCommonLib!??1CMRSWLock@@QEAA@XZ` at `0x180004bf3`
- `WdsCommonLib!??1CMRSWLock@@QEAA@XZ` at `0x180004bf3`

## pseudocode

```c
void __fastcall CPxeProviderHandler::~CPxeProviderHandler(CPxeProviderHandler *this)
{
  PSLIST_ENTRY v2; // rax

  *(_QWORD *)this = &CPxeProviderHandler::`vftable';
  CPxeProviderHandler::Shutdown(this);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 336));
  while ( 1 )
  {
    v2 = InterlockedPopEntrySList((PSLIST_HEADER)this + 24);
    if ( !v2 )
      break;
    _InterlockedDecrement((volatile signed __int32 *)this + 100);
    if ( v2 == (PSLIST_ENTRY)208 )
      break;
    operator delete(&v2[-13]);
  }
  CMRSWLock::~CMRSWLock((CPxeProviderHandler *)((char *)this + 200));
  CBannedDeviceIds::Shutdown((CPxeProviderHandler *)((char *)this + 136));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 152));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
}

```

## disassembly

```asm
0x180004b84  mov     [rsp+arg_0], rbx
0x180004b89  push    rdi
0x180004b8a  sub     rsp, 20h
0x180004b8e  lea     rax, ??_7CPxeProviderHandler@@6B@; const CPxeProviderHandler::`vftable'
0x180004b95  mov     rdi, rcx
0x180004b98  mov     [rcx], rax
0x180004b9b  call    ?Shutdown@CPxeProviderHandler@@QEAAKXZ; CPxeProviderHandler::Shutdown(void)
0x180004ba0  lea     rcx, [rdi+150h]; lpCriticalSection
0x180004ba7  call    cs:__imp_DeleteCriticalSection
0x180004bae  nop     dword ptr [rax+rax+00h]
0x180004bb3  lea     rbx, [rdi+180h]
0x180004bba  mov     rcx, rbx; ListHead
0x180004bbd  call    cs:__imp_InterlockedPopEntrySList
0x180004bc4  nop     dword ptr [rax+rax+00h]
0x180004bc9  test    rax, rax
0x180004bcc  jz      short loc_180004BEC
0x180004bce  lock dec dword ptr [rbx+10h]
0x180004bd2  lea     rcx, [rax-0D0h]
0x180004bd9  test    rcx, rcx
0x180004bdc  jz      short loc_180004BEC
0x180004bde  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180004be5  nop     dword ptr [rax+rax+00h]
0x180004bea  jmp     short loc_180004BBA
0x180004bec  lea     rcx, [rdi+0C8h]
0x180004bf3  call    cs:__imp_??1CMRSWLock@@QEAA@XZ; CMRSWLock::~CMRSWLock(void)
0x180004bfa  nop     dword ptr [rax+rax+00h]
0x180004bff  lea     rbx, [rdi+88h]
0x180004c06  mov     rcx, rbx
0x180004c09  call    cs:__imp_?Shutdown@CBannedDeviceIds@@QEAAKXZ; CBannedDeviceIds::Shutdown(void)
0x180004c10  nop     dword ptr [rax+rax+00h]
0x180004c15  lea     rcx, [rbx+10h]; lpCriticalSection
0x180004c19  call    cs:__imp_DeleteCriticalSection
0x180004c20  nop     dword ptr [rax+rax+00h]
0x180004c25  lea     rcx, [rdi+58h]; lpCriticalSection
0x180004c29  call    cs:__imp_DeleteCriticalSection
0x180004c30  nop     dword ptr [rax+rax+00h]
0x180004c35  lea     rcx, [rdi+18h]
0x180004c39  mov     rbx, [rsp+28h+arg_0]
0x180004c3e  add     rsp, 20h
0x180004c42  pop     rdi
0x180004c43  jmp     cs:__imp_DeleteCriticalSection
```
