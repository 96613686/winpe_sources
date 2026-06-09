# CShellResultsListenerEvent::~CShellResultsListenerEvent(void)

- ea: `0x140082f54`
- end: `0x140082fc0`
- name: `??1CShellResultsListenerEvent@@UEAA@XZ`
- size: `108`
- prototype: `void __fastcall(CShellResultsListenerEvent *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140082c68`
- `0x140083210`

## callees

- `0x140024688`
- `0x140039ca8`
- `0x140082f54`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140082f79`
- `KERNEL32!GetCurrentThreadId` at `0x140082f79`
- `KERNEL32!WaitForSingleObject` at `0x140082f8a`
- `KERNEL32!WaitForSingleObject` at `0x140082f8a`
- `KERNEL32!CloseHandle` at `0x140082f94`
- `KERNEL32!CloseHandle` at `0x140082f94`

## pseudocode

```c
void __fastcall CShellResultsListenerEvent::~CShellResultsListenerEvent(CShellResultsListenerEvent *this)
{
  bool v1; // zf
  int v3; // ebx

  v1 = *((_QWORD *)this + 12) == 0;
  *(_QWORD *)this = &CShellResultsListenerEvent::`vftable';
  *((_BYTE *)this + 89) = 1;
  if ( !v1 )
  {
    v3 = *((_DWORD *)this + 26);
    if ( v3 != GetCurrentThreadId() )
      WaitForSingleObject(*((HANDLE *)this + 12), 0xFFFFFFFF);
    CloseHandle(*((HANDLE *)this + 12));
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)this + 10);
  *(_QWORD *)this = &CShellResultsListener::`vftable';
  ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection((CShellResultsListenerEvent *)((char *)this + 24));
}

```

## disassembly

```asm
0x140082f54  mov     [rsp+arg_0], rbx
0x140082f59  push    rdi
0x140082f5a  sub     rsp, 20h
0x140082f5e  cmp     qword ptr [rcx+60h], 0
0x140082f63  lea     rax, ??_7CShellResultsListenerEvent@@6B@; const CShellResultsListenerEvent::`vftable'
0x140082f6a  mov     [rcx], rax
0x140082f6d  mov     rdi, rcx
0x140082f70  mov     byte ptr [rcx+59h], 1
0x140082f74  jz      short loc_140082F9A
0x140082f76  mov     ebx, [rcx+68h]
0x140082f79  call    cs:__imp_GetCurrentThreadId
0x140082f7f  cmp     ebx, eax
0x140082f81  jz      short loc_140082F90
0x140082f83  mov     rcx, [rdi+60h]; hHandle
0x140082f87  or      edx, 0FFFFFFFFh; dwMilliseconds
0x140082f8a  call    cs:__imp_WaitForSingleObject
0x140082f90  mov     rcx, [rdi+60h]; hObject
0x140082f94  call    cs:__imp_CloseHandle
0x140082f9a  lea     rcx, [rdi+50h]
0x140082f9e  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x140082fa3  lea     rax, ??_7CShellResultsListener@@6B@; const CShellResultsListener::`vftable'
0x140082faa  lea     rcx, [rdi+18h]; this
0x140082fae  mov     [rdi], rax
0x140082fb1  mov     rbx, [rsp+28h+arg_0]
0x140082fb6  add     rsp, 20h
0x140082fba  pop     rdi
0x140082fbb  jmp     ??1CComSafeDeleteCriticalSection@ATL@@QEAA@XZ; ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection(void)
```
