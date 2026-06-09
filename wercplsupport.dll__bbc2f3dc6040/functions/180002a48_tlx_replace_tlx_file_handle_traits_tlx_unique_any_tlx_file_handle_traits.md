# tlx::replace<tlx::file_handle_traits>(tlx::unique_any<tlx::file_handle_traits> &)

- ea: `0x180002a48`
- end: `0x180002a74`
- name: `??$replace@Ufile_handle_traits@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@Ufile_handle_traits@tlx@@@0@@Z`
- size: `44`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180005e04`
- `0x180007dd8`
- `0x18000e520`
- `0x18000e700`

## callees

- `0x180002a48`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002a65`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002a65`

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
0x180002a48  push    rbx
0x180002a4a  sub     rsp, 20h
0x180002a4e  mov     rbx, rcx
0x180002a51  mov     rcx, [rcx]; hObject
0x180002a54  lea     rax, [rcx+1]
0x180002a58  mov     qword ptr [rbx], 0
0x180002a5f  cmp     rax, 1
0x180002a63  jbe     short loc_180002A6B
0x180002a65  call    cs:__imp_CloseHandle
0x180002a6b  mov     rax, rbx
0x180002a6e  add     rsp, 20h
0x180002a72  pop     rbx
0x180002a73  retn
```
