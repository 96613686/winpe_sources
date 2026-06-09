# tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)

- ea: `0x180005ddc`
- end: `0x180005df8`
- name: `??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ`
- size: `28`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `24`
- callee_count: `1`
- tags: ``

## callers

- `0x180005e00`
- `0x180006ee0`
- `0x18000b1b4`
- `0x18000b334`
- `0x18000b5dc`
- `0x18000cae8`
- `0x18000f6cc`
- `0x180010938`
- `0x1800115c4`
- `0x180011720`
- `0x1800117fc`
- `0x180011af0`
- `0x180012084`
- `0x180012598`
- `0x18001326c`
- `0x18001714e`
- `0x180017167`
- `0x180017180`
- `0x180017199`
- `0x1800171c4`
- `0x1800172f6`
- `0x180017362`
- `0x180017378`
- `0x180017414`

## callees

- `0x180005ddc`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x180005ded`
- `KERNEL32!CloseHandle` at `0x180005ded`

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
0x180005ddc  sub     rsp, 28h
0x180005de0  mov     rcx, [rcx]; hObject
0x180005de3  lea     rax, [rcx+1]
0x180005de7  cmp     rax, 1
0x180005deb  jbe     short loc_180005DF3
0x180005ded  call    cs:__imp_CloseHandle
0x180005df3  add     rsp, 28h
0x180005df7  retn
```
