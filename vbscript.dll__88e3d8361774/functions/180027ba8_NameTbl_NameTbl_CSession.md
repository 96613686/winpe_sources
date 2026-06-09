# NameTbl::NameTbl(CSession *)

- ea: `0x180027ba8`
- end: `0x180027beb`
- name: `??0NameTbl@@IEAA@PEAVCSession@@@Z`
- size: `67`
- prototype: `NameTbl *__fastcall(NameTbl *__hidden this, struct CSession *)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x180027b50`
- `0x18005be54`
- `0x180074fe0`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180027bd9`
- `KERNEL32!GetCurrentThreadId` at `0x180027bd9`

## pseudocode

```c
NameTbl *__fastcall NameTbl::NameTbl(NameTbl *this, struct CSession *a2)
{
  *(_QWORD *)this = &NameTbl::`vftable';
  _InterlockedIncrement(&g_cLibRef);
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 3) = a2;
  _InterlockedIncrement((volatile signed __int32 *)a2 + 2);
  *((_DWORD *)this + 2) = 1;
  *((_DWORD *)this + 8) = GetCurrentThreadId();
  return this;
}

```

## disassembly

```asm
0x180027ba8  push    rbx
0x180027baa  sub     rsp, 20h
0x180027bae  lea     rax, ??_7NameTbl@@6B@; const NameTbl::`vftable'
0x180027bb5  mov     rbx, rcx
0x180027bb8  mov     [rcx], rax
0x180027bbb  lock inc cs:?g_cLibRef@@3JA; long g_cLibRef
0x180027bc2  mov     qword ptr [rcx+10h], 0
0x180027bca  mov     [rcx+18h], rdx
0x180027bce  lock inc dword ptr [rdx+8]
0x180027bd2  mov     dword ptr [rcx+8], 1
0x180027bd9  call    cs:__imp_GetCurrentThreadId
0x180027bdf  mov     [rbx+20h], eax
0x180027be2  mov     rax, rbx
0x180027be5  add     rsp, 20h
0x180027be9  pop     rbx
0x180027bea  retn
```
