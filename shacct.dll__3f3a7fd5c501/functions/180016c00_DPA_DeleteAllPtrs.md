# DPA_DeleteAllPtrs

- ea: `0x180016c00`
- end: `0x180016c48`
- name: `DPA_DeleteAllPtrs`
- size: `72`
- prototype: `BOOL __stdcall(HDPA hdpa)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180009900`

## callees

- `0x180016bd0`
- `0x180016c00`

## pseudocode

```c
BOOL __stdcall DPA_DeleteAllPtrs(HDPA hdpa)
{
  void *v2; // rdx
  BOOL result; // eax

  if ( !hdpa )
    return 0;
  v2 = (void *)*((_QWORD *)hdpa + 1);
  if ( v2 )
  {
    if ( CCv6s_HeapFree(*((void **)hdpa + 2), v2) < 0 )
      return 0;
  }
  *((_QWORD *)hdpa + 1) = 0;
  result = 1;
  *((_DWORD *)hdpa + 6) = 0;
  *(_DWORD *)hdpa = 0;
  return result;
}

```

## disassembly

```asm
0x180016c00  push    rbx
0x180016c02  sub     rsp, 20h
0x180016c06  mov     rbx, rcx
0x180016c09  test    rcx, rcx
0x180016c0c  jz      short loc_180016C40
0x180016c0e  mov     rdx, [rcx+8]; void *
0x180016c12  test    rdx, rdx
0x180016c15  jz      short loc_180016C24
0x180016c17  mov     rcx, [rcx+10h]; void *
0x180016c1b  call    ?CCv6s_HeapFree@@YAJPEAX0@Z; CCv6s_HeapFree(void *,void *)
0x180016c20  test    eax, eax
0x180016c22  js      short loc_180016C40
0x180016c24  mov     qword ptr [rbx+8], 0
0x180016c2c  mov     eax, 1
0x180016c31  mov     dword ptr [rbx+18h], 0
0x180016c38  mov     dword ptr [rbx], 0
0x180016c3e  jmp     short loc_180016C42
0x180016c40  xor     eax, eax
0x180016c42  add     rsp, 20h
0x180016c46  pop     rbx
0x180016c47  retn
```
