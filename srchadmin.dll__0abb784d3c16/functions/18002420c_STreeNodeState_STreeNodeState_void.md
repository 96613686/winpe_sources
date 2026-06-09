# STreeNodeState::~STreeNodeState(void)

- ea: `0x18002420c`
- end: `0x18002422e`
- name: `??1STreeNodeState@@QEAA@XZ`
- size: `34`
- prototype: `void __fastcall(STreeNodeState *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x180024234`

## import_xrefs

- `SHELL32!__imp_ILFree` at `0x180024218`
- `SHELL32!__imp_ILFree` at `0x180024218`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180024227`

## pseudocode

```c
void __fastcall STreeNodeState::~STreeNodeState(STreeNodeState *this)
{
  ILFree(*(LPITEMIDLIST *)this);
  CoTaskMemFree(*((LPVOID *)this + 1));
}

```

## disassembly

```asm
0x18002420c  push    rbx
0x18002420e  sub     rsp, 20h
0x180024212  mov     rbx, rcx
0x180024215  mov     rcx, [rcx]; pidl
0x180024218  call    cs:__imp_ILFree
0x18002421e  mov     rcx, [rbx+8]
0x180024222  add     rsp, 20h
0x180024226  pop     rbx
0x180024227  jmp     cs:__imp_CoTaskMemFree
```
