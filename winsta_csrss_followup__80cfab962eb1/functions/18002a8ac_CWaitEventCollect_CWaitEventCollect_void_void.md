# CWaitEventCollect::CWaitEventCollect(void *,void *)

- ea: `0x18002a8ac`
- end: `0x18002a92c`
- name: `??0CWaitEventCollect@@QEAA@PEAX0@Z`
- size: `128`
- prototype: `CWaitEventCollect *(CWaitEventCollect *__hidden this, void *, void *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000d360`

## callees

- `0x180002d34`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002a906`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002a906`

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
0x18002a8ac  mov     [rsp+arg_0], rbx
0x18002a8b1  mov     [rsp+arg_8], rsi
0x18002a8b6  push    rdi
0x18002a8b7  sub     rsp, 20h
0x18002a8bb  mov     rbx, rdx
0x18002a8be  mov     rdi, r8
0x18002a8c1  mov     rdx, r8; void *
0x18002a8c4  mov     rsi, rcx
0x18002a8c7  call    ??0CWaitItem@@QEAA@PEAX@Z; CWaitItem::CWaitItem(void *)
0x18002a8cc  lea     rax, ??_7CWaitEventCollect@@6B@; const CWaitEventCollect::`vftable'
0x18002a8d3  mov     [rsi+640h], rbx
0x18002a8da  mov     [rsi], rax
0x18002a8dd  xor     eax, eax
0x18002a8df  mov     [rsi+638h], eax
0x18002a8e5  mov     [rsi+648h], eax
0x18002a8eb  mov     [rsi+658h], eax
0x18002a8f1  lea     rax, [rsi+660h]
0x18002a8f8  mov     [rsi+650h], rdi
0x18002a8ff  mov     [rax+8], rax
0x18002a903  mov     [rax], rax
0x18002a906  call    cs:__imp_GetCurrentThreadId
0x18002a90d  nop     dword ptr [rax+rax+00h]
0x18002a912  mov     rbx, [rsp+28h+arg_0]
0x18002a917  mov     [rsi+658h], eax
0x18002a91d  mov     rax, rsi
0x18002a920  mov     rsi, [rsp+28h+arg_8]
0x18002a925  add     rsp, 20h
0x18002a929  pop     rdi
0x18002a92a  retn
```
