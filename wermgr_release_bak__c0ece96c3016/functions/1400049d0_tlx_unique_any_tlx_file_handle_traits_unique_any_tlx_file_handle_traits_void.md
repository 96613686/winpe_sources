# tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)

- ea: `0x1400049d0`
- end: `0x1400049ec`
- name: `??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ`
- size: `28`
- prototype: ``
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x14001cc05`
- `0x14001cc5f`
- `0x14001cc71`
- `0x14001cccb`
- `0x14001ccdd`
- `0x14001cdb5`
- `0x14001cdd9`
- `0x14001ce21`
- `0x14001cf1f`

## callees

- `0x1400049d0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400049e1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400049e1`

## pseudocode

```c
int __fastcall tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void **a1)
{
  void *v1; // rcx
  int result; // eax

  v1 = *a1;
  result = (_DWORD)v1 + 1;
  if ( (unsigned __int64)v1 + 1 > 1 )
    return CloseHandle(v1);
  return result;
}

```

## disassembly

```asm
0x1400049d0  sub     rsp, 28h
0x1400049d4  mov     rcx, [rcx]; hObject
0x1400049d7  lea     rax, [rcx+1]
0x1400049db  cmp     rax, 1
0x1400049df  jbe     short loc_1400049E7
0x1400049e1  call    cs:__imp_CloseHandle
0x1400049e7  add     rsp, 28h
0x1400049eb  retn
```
