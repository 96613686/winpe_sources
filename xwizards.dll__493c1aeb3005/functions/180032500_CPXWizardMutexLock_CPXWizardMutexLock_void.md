# CPXWizardMutexLock::~CPXWizardMutexLock(void)

- ea: `0x180032500`
- end: `0x180032537`
- name: `??1CPXWizardMutexLock@@QEAA@XZ`
- size: `55`
- prototype: `void __fastcall(CPXWizardMutexLock *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180031b70`

## callees

- `0x180032500`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180032512`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180032512`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003252b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003252b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003251c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003251c`

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
0x180032500  push    rbx
0x180032502  sub     rsp, 20h
0x180032506  mov     rbx, rcx
0x180032509  mov     rcx, [rcx+8]; hMutex
0x18003250d  test    rcx, rcx
0x180032510  jz      short loc_180032522
0x180032512  call    cs:__imp_ReleaseMutex
0x180032518  mov     rcx, [rbx+8]; hObject
0x18003251c  call    cs:__imp_CloseHandle
0x180032522  mov     rcx, [rbx+10h]; pv
0x180032526  test    rcx, rcx
0x180032529  jz      short loc_180032531
0x18003252b  call    cs:__imp_CoTaskMemFree
0x180032531  add     rsp, 20h
0x180032535  pop     rbx
0x180032536  retn
```
