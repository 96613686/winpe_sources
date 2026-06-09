# wsl::util::DeleteProcThreadAttributeList(_PROC_THREAD_ATTRIBUTE_LIST *)

- ea: `0x180009f94`
- end: `0x180009fb2`
- name: `?DeleteProcThreadAttributeList@util@wsl@@YAXPEAU_PROC_THREAD_ATTRIBUTE_LIST@@@Z`
- size: `30`
- prototype: `void __fastcall(wsl::util *__hidden this, struct _PROC_THREAD_ATTRIBUTE_LIST *)`
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x180009df4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!DeleteProcThreadAttributeList` at `0x180009f9d`
- `api-ms-win-core-processthreads-l1-1-0!DeleteProcThreadAttributeList` at `0x180009f9d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009fab`

## pseudocode

```c
void __fastcall wsl::util::DeleteProcThreadAttributeList(wsl::util *this, struct _PROC_THREAD_ATTRIBUTE_LIST *a2)
{
  DeleteProcThreadAttributeList(this);
  CoTaskMemFree(this);
}

```

## disassembly

```asm
0x180009f94  push    rbx
0x180009f96  sub     rsp, 20h
0x180009f9a  mov     rbx, rcx
0x180009f9d  call    cs:__imp_DeleteProcThreadAttributeList
0x180009fa3  mov     rcx, rbx
0x180009fa6  add     rsp, 20h
0x180009faa  pop     rbx
0x180009fab  jmp     cs:__imp_CoTaskMemFree
```
