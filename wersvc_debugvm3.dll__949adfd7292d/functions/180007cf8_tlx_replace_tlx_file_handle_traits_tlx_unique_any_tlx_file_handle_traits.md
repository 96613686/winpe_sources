# tlx::replace<tlx::file_handle_traits>(tlx::unique_any<tlx::file_handle_traits> &)

- ea: `0x180007cf8`
- end: `0x180007d24`
- name: `??$replace@Ufile_handle_traits@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@Ufile_handle_traits@tlx@@@0@@Z`
- size: `44`
- prototype: ``
- caller_count: `33`
- callee_count: `1`
- tags: ``

## callers

- `0x1800106f4`
- `0x180014200`
- `0x180014378`
- `0x180014934`
- `0x180015aa8`
- `0x180017578`
- `0x1800181f8`
- `0x18001a6d8`
- `0x18001b3f8`
- `0x18001caf4`
- `0x18001e81c`
- `0x18001ed68`
- `0x180020468`
- `0x18002091c`
- `0x180020dc4`
- `0x180021b88`
- `0x180022108`
- `0x180022d54`
- `0x180023d0c`
- `0x1800243ac`
- `0x180024784`
- `0x1800248f4`
- `0x180025568`
- `0x1800261f8`
- `0x180027008`
- `0x180027260`
- `0x180027460`
- `0x18002df50`
- `0x18002ff0c`
- `0x1800300c0`
- `0x180030590`
- `0x1800307b0`
- `0x180030a58`

## callees

- `0x180007cf8`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007d15`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007d15`

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
0x180007cf8  push    rbx
0x180007cfa  sub     rsp, 20h
0x180007cfe  mov     rbx, rcx
0x180007d01  mov     rcx, [rcx]; hObject
0x180007d04  lea     rax, [rcx+1]
0x180007d08  mov     qword ptr [rbx], 0
0x180007d0f  cmp     rax, 1
0x180007d13  jbe     short loc_180007D1B
0x180007d15  call    cs:__imp_CloseHandle
0x180007d1b  mov     rax, rbx
0x180007d1e  add     rsp, 20h
0x180007d22  pop     rbx
0x180007d23  retn
```
