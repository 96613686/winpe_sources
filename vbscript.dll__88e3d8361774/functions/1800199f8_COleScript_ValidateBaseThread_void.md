# COleScript::ValidateBaseThread(void)

- ea: `0x1800199f8`
- end: `0x180019a1c`
- name: `?ValidateBaseThread@COleScript@@AEAAJXZ`
- size: `36`
- prototype: `__int64 __fastcall(COleScript *__hidden this)`
- caller_count: `14`
- callee_count: `0`
- tags: ``

## callers

- `0x1800192c0`
- `0x180019430`
- `0x180019670`
- `0x180019950`
- `0x18003a5b0`
- `0x18003fbf0`
- `0x180051f0c`
- `0x180052370`
- `0x180052520`
- `0x180054390`
- `0x180054d74`
- `0x1800553e0`
- `0x180055540`
- `0x180055c60`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180019a01`
- `KERNEL32!GetCurrentThreadId` at `0x180019a01`

## pseudocode

```c
__int64 __fastcall COleScript::ValidateBaseThread(COleScript *this)
{
  return *((_DWORD *)this + 61) != GetCurrentThreadId() ? 0x8000FFFF : 0;
}

```

## disassembly

```asm
0x1800199f8  push    rbx
0x1800199fa  sub     rsp, 20h
0x1800199fe  mov     rbx, rcx
0x180019a01  call    cs:__imp_GetCurrentThreadId
0x180019a07  sub     eax, [rbx+0F4h]
0x180019a0d  neg     eax
0x180019a0f  sbb     eax, eax
0x180019a11  and     eax, 8000FFFFh
0x180019a16  add     rsp, 20h
0x180019a1a  pop     rbx
0x180019a1b  retn
```
