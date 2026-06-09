# tlx::unique_any<tlx::file_handle_traits>::reset(void *)

- ea: `0x18000983c`
- end: `0x18000985e`
- name: `?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z`
- size: `34`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `16`
- callee_count: `1`
- tags: ``

## callers

- `0x180005c58`
- `0x180005e00`
- `0x180006990`
- `0x180007a70`
- `0x180008b90`
- `0x18000b334`
- `0x18000b5dc`
- `0x18000daa0`
- `0x180010938`
- `0x1800111c0`
- `0x1800115c4`
- `0x180011720`
- `0x1800117fc`
- `0x180011af0`
- `0x180012084`
- `0x18001326c`

## callees

- `0x18000983c`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x180009853`
- `KERNEL32!CloseHandle` at `0x180009853`

## pseudocode

```c
int __fastcall tlx::unique_any<tlx::file_handle_traits>::reset(void **a1, void *a2)
{
  void *v2; // r8
  int result; // eax

  v2 = *a1;
  *a1 = a2;
  result = (_DWORD)v2 + 1;
  if ( (unsigned __int64)v2 + 1 > 1 )
    return CloseHandle(v2);
  return result;
}

```

## disassembly

```asm
0x18000983c  sub     rsp, 28h
0x180009840  mov     r8, [rcx]
0x180009843  mov     [rcx], rdx
0x180009846  lea     rax, [r8+1]
0x18000984a  cmp     rax, 1
0x18000984e  jbe     short loc_180009859
0x180009850  mov     rcx, r8; hObject
0x180009853  call    cs:__imp_CloseHandle
0x180009859  add     rsp, 28h
0x18000985d  retn
```
