# CPXWizardTask::FreeTaskDataElement(tag_WIZARD_TASK_DATA * *)

- ea: `0x18001d854`
- end: `0x18001d8ba`
- name: `?FreeTaskDataElement@CPXWizardTask@@CAXPEAPEAUtag_WIZARD_TASK_DATA@@@Z`
- size: `102`
- prototype: `void __fastcall(struct tag_WIZARD_TASK_DATA **)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001e180`
- `0x18001eb00`

## callees

- `0x18001d854`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d89e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d8a7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d89e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d8a7`

## pseudocode

```c
void __fastcall CPXWizardTask::FreeTaskDataElement(LPVOID *a1)
{
  __int64 v2; // rcx
  __int64 v3; // rcx
  void *v4; // rcx

  if ( *a1 )
  {
    v2 = *((_QWORD *)*a1 + 10);
    if ( v2 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
    v3 = *((_QWORD *)*a1 + 9);
    if ( v3 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
    v4 = (void *)*((_QWORD *)*a1 + 6);
    if ( v4 )
      CoTaskMemFree(v4);
    CoTaskMemFree(*a1);
    *a1 = 0;
  }
}

```

## disassembly

```asm
0x18001d854  push    rbx
0x18001d856  sub     rsp, 20h
0x18001d85a  mov     rax, [rcx]
0x18001d85d  mov     rbx, rcx
0x18001d860  test    rax, rax
0x18001d863  jz      short loc_18001D8B4
0x18001d865  mov     rcx, [rax+50h]
0x18001d869  test    rcx, rcx
0x18001d86c  jz      short loc_18001D87A
0x18001d86e  mov     rax, [rcx]
0x18001d871  mov     rax, [rax+10h]
0x18001d875  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d87a  mov     rax, [rbx]
0x18001d87d  mov     rcx, [rax+48h]
0x18001d881  test    rcx, rcx
0x18001d884  jz      short loc_18001D892
0x18001d886  mov     rax, [rcx]
0x18001d889  mov     rax, [rax+10h]
0x18001d88d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d892  mov     rax, [rbx]
0x18001d895  mov     rcx, [rax+30h]; pv
0x18001d899  test    rcx, rcx
0x18001d89c  jz      short loc_18001D8A4
0x18001d89e  call    cs:__imp_CoTaskMemFree
0x18001d8a4  mov     rcx, [rbx]; pv
0x18001d8a7  call    cs:__imp_CoTaskMemFree
0x18001d8ad  mov     qword ptr [rbx], 0
0x18001d8b4  add     rsp, 20h
0x18001d8b8  pop     rbx
0x18001d8b9  retn
```
