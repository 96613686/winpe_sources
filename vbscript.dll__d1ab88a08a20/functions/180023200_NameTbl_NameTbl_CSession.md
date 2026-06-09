# NameTbl::NameTbl(CSession *)

- ea: `0x180023200`
- end: `0x18002324a`
- name: `??0NameTbl@@IEAA@PEAVCSession@@@Z`
- size: `74`
- prototype: `NameTbl *__fastcall(NameTbl *__hidden this, struct CSession *)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x1800231a4`
- `0x18005d9dc`
- `0x180077bb0`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180023231`
- `KERNEL32!GetCurrentThreadId` at `0x180023231`

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
0x180023200  push    rbx
0x180023202  sub     rsp, 20h
0x180023206  lea     rax, ??_7NameTbl@@6B@; const NameTbl::`vftable'
0x18002320d  mov     rbx, rcx
0x180023210  mov     [rcx], rax
0x180023213  lock inc cs:?g_cLibRef@@3JA; long g_cLibRef
0x18002321a  mov     qword ptr [rcx+10h], 0
0x180023222  mov     [rcx+18h], rdx
0x180023226  lock inc dword ptr [rdx+8]
0x18002322a  mov     dword ptr [rcx+8], 1
0x180023231  call    cs:__imp_GetCurrentThreadId
0x180023238  nop     dword ptr [rax+rax+00h]
0x18002323d  mov     [rbx+20h], eax
0x180023240  mov     rax, rbx
0x180023243  add     rsp, 20h
0x180023247  pop     rbx
0x180023248  retn
```
