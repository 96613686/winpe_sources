# CWaitEventCollect::CWaitEventCollect(void *,void *)

- ea: `0x180028cdc`
- end: `0x180028d55`
- name: `??0CWaitEventCollect@@QEAA@PEAX0@Z`
- size: `121`
- prototype: `CWaitEventCollect *(CWaitEventCollect *__hidden this, void *, void *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800011c0`

## callees

- `0x1800052bc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180028d36`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180028d36`

## pseudocode

```c
CWaitEventCollect *__fastcall CWaitEventCollect::CWaitEventCollect(CWaitEventCollect *this, void *a2, void *a3)
{
  CWaitItem::CWaitItem(this, a3);
  *((_QWORD *)this + 200) = a2;
  *(_QWORD *)this = &CWaitEventCollect::`vftable';
  *((_DWORD *)this + 398) = 0;
  *((_DWORD *)this + 402) = 0;
  *((_DWORD *)this + 406) = 0;
  *((_QWORD *)this + 202) = a3;
  *((_QWORD *)this + 205) = (char *)this + 1632;
  *((_QWORD *)this + 204) = (char *)this + 1632;
  *((_DWORD *)this + 406) = GetCurrentThreadId();
  return this;
}

```

## disassembly

```asm
0x180028cdc  mov     [rsp+arg_0], rbx
0x180028ce1  mov     [rsp+arg_8], rsi
0x180028ce6  push    rdi
0x180028ce7  sub     rsp, 20h
0x180028ceb  mov     rbx, rdx
0x180028cee  mov     rdi, r8
0x180028cf1  mov     rdx, r8; void *
0x180028cf4  mov     rsi, rcx
0x180028cf7  call    ??0CWaitItem@@QEAA@PEAX@Z; CWaitItem::CWaitItem(void *)
0x180028cfc  lea     rax, ??_7CWaitEventCollect@@6B@; const CWaitEventCollect::`vftable'
0x180028d03  mov     [rsi+640h], rbx
0x180028d0a  mov     [rsi], rax
0x180028d0d  xor     eax, eax
0x180028d0f  mov     [rsi+638h], eax
0x180028d15  mov     [rsi+648h], eax
0x180028d1b  mov     [rsi+658h], eax
0x180028d21  lea     rax, [rsi+660h]
0x180028d28  mov     [rsi+650h], rdi
0x180028d2f  mov     [rax+8], rax
0x180028d33  mov     [rax], rax
0x180028d36  call    cs:__imp_GetCurrentThreadId
0x180028d3c  mov     rbx, [rsp+28h+arg_0]
0x180028d41  mov     [rsi+658h], eax
0x180028d47  mov     rax, rsi
0x180028d4a  mov     rsi, [rsp+28h+arg_8]
0x180028d4f  add     rsp, 20h
0x180028d53  pop     rdi
0x180028d54  retn
```
