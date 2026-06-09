# NameTbl::FBaseThread(void)

- ea: `0x18003670c`
- end: `0x180036732`
- name: `?FBaseThread@NameTbl@@IEAAHXZ`
- size: `38`
- prototype: `__int64 __fastcall(NameTbl *__hidden this)`
- caller_count: `11`
- callee_count: `0`
- tags: ``

## callers

- `0x180036560`
- `0x1800365d0`
- `0x180036a20`
- `0x18005da50`
- `0x18005dab0`
- `0x18005dcd0`
- `0x18005dd90`
- `0x18005de60`
- `0x18005df20`
- `0x180077dd0`
- `0x180077f90`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180036715`
- `KERNEL32!GetCurrentThreadId` at `0x180036715`

## pseudocode

```c
_BOOL8 __fastcall NameTbl::FBaseThread(NameTbl *this)
{
  return GetCurrentThreadId() == *((_DWORD *)this + 8);
}

```

## disassembly

```asm
0x18003670c  push    rbx
0x18003670e  sub     rsp, 20h
0x180036712  mov     rbx, rcx
0x180036715  call    cs:__imp_GetCurrentThreadId
0x18003671c  nop     dword ptr [rax+rax+00h]
0x180036721  xor     edx, edx
0x180036723  cmp     eax, [rbx+20h]
0x180036726  setz    dl
0x180036729  mov     eax, edx
0x18003672b  add     rsp, 20h
0x18003672f  pop     rbx
0x180036730  retn
```
