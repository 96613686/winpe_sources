# CPXWizardMutexLock::~CPXWizardMutexLock(void)

- ea: `0x180011de8`
- end: `0x180011e1f`
- name: `??1CPXWizardMutexLock@@QEAA@XZ`
- size: `55`
- prototype: `void __fastcall(CPXWizardMutexLock *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000d26c`

## callees

- `0x180011de8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180011dfa`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180011dfa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011e13`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011e13`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011e04`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011e04`

## pseudocode

```c
void __fastcall CPXWizardMutexLock::~CPXWizardMutexLock(CPXWizardMutexLock *this)
{
  void *v2; // rcx
  void *v3; // rcx

  v2 = (void *)*((_QWORD *)this + 1);
  if ( v2 )
  {
    ReleaseMutex(v2);
    CloseHandle(*((HANDLE *)this + 1));
  }
  v3 = (void *)*((_QWORD *)this + 2);
  if ( v3 )
    CoTaskMemFree(v3);
}

```

## disassembly

```asm
0x180011de8  push    rbx
0x180011dea  sub     rsp, 20h
0x180011dee  mov     rbx, rcx
0x180011df1  mov     rcx, [rcx+8]; hMutex
0x180011df5  test    rcx, rcx
0x180011df8  jz      short loc_180011E0A
0x180011dfa  call    cs:__imp_ReleaseMutex
0x180011e00  mov     rcx, [rbx+8]; hObject
0x180011e04  call    cs:__imp_CloseHandle
0x180011e0a  mov     rcx, [rbx+10h]; pv
0x180011e0e  test    rcx, rcx
0x180011e11  jz      short loc_180011E19
0x180011e13  call    cs:__imp_CoTaskMemFree
0x180011e19  add     rsp, 20h
0x180011e1d  pop     rbx
0x180011e1e  retn
```
