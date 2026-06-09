# __std_fs_open_handle

- ea: `0x1800021ac`
- end: `0x1800021ff`
- name: `__std_fs_open_handle`
- size: `83`
- prototype: `DWORD __fastcall(__int64 *, int, int, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180001e20`

## callees

- `0x180001cc8`
- `0x1800021ac`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800021f8`

## pseudocode

```c
DWORD __fastcall _std_fs_open_handle(__int64 *a1, int a2, int a3, int a4)
{
  __int64 File; // rax

  File = anonymous_namespace_::__vcp_CreateFile(a2, a3, 7, 0, 3, a4, 0);
  *a1 = File;
  if ( File == -1 )
    return GetLastError();
  else
    return 0;
}

```

## disassembly

```asm
0x1800021ac  push    rbx
0x1800021ae  sub     rsp, 40h
0x1800021b2  mov     eax, r8d
0x1800021b5  mov     [rsp+48h+var_18], 0
0x1800021be  mov     [rsp+48h+var_20], r9d
0x1800021c3  mov     r10, rdx
0x1800021c6  xor     r9d, r9d
0x1800021c9  mov     [rsp+48h+var_28], 3
0x1800021d1  mov     rbx, rcx
0x1800021d4  mov     edx, eax
0x1800021d6  mov     rcx, r10
0x1800021d9  lea     r8d, [r9+7]
0x1800021dd  call    _anonymous_namespace_____vcp_CreateFile
0x1800021e2  mov     [rbx], rax
0x1800021e5  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800021e9  jz      short loc_1800021F3
0x1800021eb  xor     eax, eax
0x1800021ed  add     rsp, 40h
0x1800021f1  pop     rbx
0x1800021f2  retn
0x1800021f3  add     rsp, 40h
0x1800021f7  pop     rbx
0x1800021f8  jmp     cs:__imp_GetLastError
```
