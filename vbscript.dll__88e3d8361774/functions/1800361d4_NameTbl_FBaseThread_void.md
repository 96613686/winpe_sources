# NameTbl::FBaseThread(void)

- ea: `0x1800361d4`
- end: `0x1800361f3`
- name: `?FBaseThread@NameTbl@@IEAAHXZ`
- size: `31`
- prototype: `__int64 __fastcall(NameTbl *__hidden this)`
- caller_count: `10`
- callee_count: `0`
- tags: ``

## callers

- `0x180035530`
- `0x180036170`
- `0x18005bed0`
- `0x18005bf30`
- `0x18005c150`
- `0x18005c210`
- `0x18005c2d0`
- `0x18005c380`
- `0x180075210`
- `0x1800753c0`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1800361dd`
- `KERNEL32!GetCurrentThreadId` at `0x1800361dd`

## pseudocode

```c
_BOOL8 __fastcall NameTbl::FBaseThread(NameTbl *this)
{
  return GetCurrentThreadId() == *((_DWORD *)this + 8);
}

```

## disassembly

```asm
0x1800361d4  push    rbx
0x1800361d6  sub     rsp, 20h
0x1800361da  mov     rbx, rcx
0x1800361dd  call    cs:__imp_GetCurrentThreadId
0x1800361e3  xor     edx, edx
0x1800361e5  cmp     eax, [rbx+20h]
0x1800361e8  setz    dl
0x1800361eb  mov     eax, edx
0x1800361ed  add     rsp, 20h
0x1800361f1  pop     rbx
0x1800361f2  retn
```
