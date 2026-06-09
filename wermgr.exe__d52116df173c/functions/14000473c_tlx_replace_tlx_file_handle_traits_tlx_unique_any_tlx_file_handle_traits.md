# tlx::replace<tlx::file_handle_traits>(tlx::unique_any<tlx::file_handle_traits> &)

- ea: `0x14000473c`
- end: `0x140004768`
- name: `??$replace@Ufile_handle_traits@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@Ufile_handle_traits@tlx@@@0@@Z`
- size: `44`
- prototype: `void **__fastcall(void **)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x14000a804`
- `0x14000c798`
- `0x14000e49c`
- `0x14001628c`

## callees

- `0x14000473c`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140004759`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140004759`

## pseudocode

```c
void **__fastcall tlx::replace<tlx::file_handle_traits>(void **a1)
{
  void *v2; // rcx

  v2 = *a1;
  *a1 = 0;
  if ( (unsigned __int64)v2 + 1 > 1 )
    CloseHandle(v2);
  return a1;
}

```

## disassembly

```asm
0x14000473c  push    rbx
0x14000473e  sub     rsp, 20h
0x140004742  mov     rbx, rcx
0x140004745  mov     rcx, [rcx]; hObject
0x140004748  lea     rax, [rcx+1]
0x14000474c  mov     qword ptr [rbx], 0
0x140004753  cmp     rax, 1
0x140004757  jbe     short loc_14000475F
0x140004759  call    cs:__imp_CloseHandle
0x14000475f  mov     rax, rbx
0x140004762  add     rsp, 20h
0x140004766  pop     rbx
0x140004767  retn
```
