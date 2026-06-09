# _dynamic_initializer_for__WM_TASKBARCREATED__

- ea: `0x180001820`
- end: `0x18000183c`
- name: `_dynamic_initializer_for__WM_TASKBARCREATED__`
- size: `28`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## import_xrefs

- `USER32!RegisterWindowMessageW` at `0x18000182b`
- `USER32!RegisterWindowMessageW` at `0x18000182b`

## string_xrefs

- `0x180001824`: `TaskbarCreated`

## pseudocode

```c
UINT dynamic_initializer_for__WM_TASKBARCREATED__()
{
  UINT result; // eax

  result = RegisterWindowMessageW(L"TaskbarCreated");
  WM_TASKBARCREATED = result;
  return result;
}

```

## disassembly

```asm
0x180001820  sub     rsp, 28h
0x180001824  lea     rcx, String; "TaskbarCreated"
0x18000182b  call    cs:__imp_RegisterWindowMessageW
0x180001831  mov     cs:?WM_TASKBARCREATED@@3IB, eax; uint const WM_TASKBARCREATED
0x180001837  add     rsp, 28h
0x18000183b  retn
```
