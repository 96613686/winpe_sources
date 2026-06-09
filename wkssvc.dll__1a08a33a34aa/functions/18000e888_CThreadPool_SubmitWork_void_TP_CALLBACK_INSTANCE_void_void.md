# CThreadPool::SubmitWork(void (*)(_TP_CALLBACK_INSTANCE *,void *),void *)

- ea: `0x18000e888`
- end: `0x18000e8c7`
- name: `?SubmitWork@CThreadPool@@QEAAKP6AXPEAU_TP_CALLBACK_INSTANCE@@PEAX@Z1@Z`
- size: `63`
- prototype: `unsigned int(CThreadPool *__hidden this, void (*)(struct _TP_CALLBACK_INSTANCE *, void *), void *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18001089c`
- `0x180033f30`

## callees

- `0x18000e888`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e8b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e8b0`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x18000e8a0`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x18000e8a0`

## pseudocode

```c
__int64 __fastcall CThreadPool::SubmitWork(
        CThreadPool *this,
        void (*a2)(struct _TP_CALLBACK_INSTANCE *, void *),
        void *a3)
{
  unsigned int v3; // ebx

  v3 = 0;
  if ( !TrySubmitThreadpoolCallback(a2, a3, (PTP_CALLBACK_ENVIRON)((char *)this + 8)) )
    return GetLastError();
  return v3;
}

```

## disassembly

```asm
0x18000e888  push    rbx
0x18000e88a  sub     rsp, 20h
0x18000e88e  mov     rax, r8
0x18000e891  mov     r9, rdx
0x18000e894  lea     r8, [rcx+8]; pcbe
0x18000e898  mov     rdx, rax; pv
0x18000e89b  mov     rcx, r9; pfns
0x18000e89e  xor     ebx, ebx
0x18000e8a0  call    cs:__imp_TrySubmitThreadpoolCallback
0x18000e8a7  nop     dword ptr [rax+rax+00h]
0x18000e8ac  test    eax, eax
0x18000e8ae  jnz     short loc_18000E8BE
0x18000e8b0  call    cs:__imp_GetLastError
0x18000e8b7  nop     dword ptr [rax+rax+00h]
0x18000e8bc  mov     ebx, eax
0x18000e8be  mov     eax, ebx
0x18000e8c0  add     rsp, 20h
0x18000e8c4  pop     rbx
0x18000e8c5  retn
```
