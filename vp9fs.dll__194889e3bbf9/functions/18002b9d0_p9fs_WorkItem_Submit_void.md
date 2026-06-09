# p9fs::WorkItem::Submit(void)

- ea: `0x18002b9d0`
- end: `0x18002b9db`
- name: `?Submit@WorkItem@p9fs@@UEAAXXZ`
- size: `11`
- prototype: `void __fastcall(p9fs::WorkItem *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18002b9d4`

## pseudocode

```c
void __fastcall p9fs::WorkItem::Submit(PTP_WORK *this)
{
  SubmitThreadpoolWork(this[1]);
}

```

## disassembly

```asm
0x18002b9d0  mov     rcx, [rcx+8]
0x18002b9d4  jmp     cs:__imp_SubmitThreadpoolWork
```
