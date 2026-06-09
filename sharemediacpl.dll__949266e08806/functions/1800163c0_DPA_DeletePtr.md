# DPA_DeletePtr

- ea: `0x1800163c0`
- end: `0x18001640e`
- name: `DPA_DeletePtr`
- size: `78`
- prototype: `PVOID __stdcall(HDPA hdpa, int i)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000a130`
- `0x18000d338`

## callees

- `0x1800163c0`
- `0x180016650`
- `0x18001e010`

## pseudocode

```c
PVOID __stdcall DPA_DeletePtr(HDPA hdpa, int i)
{
  PVOID result; // rax

  result = (PVOID)qword_18002A2E8;
  if ( qword_18002A2E8 == -1 )
  {
    GetProcFromComCtl32((FARPROC *)&qword_18002A2E8, (const CHAR *)0x150);
    result = (PVOID)qword_18002A2E8;
  }
  if ( result )
    return (PVOID)((__int64 (__fastcall *)(HDPA, _QWORD))result)(hdpa, (unsigned int)i);
  return result;
}

```

## disassembly

```asm
0x1800163c0  mov     [rsp+arg_0], rbx
0x1800163c5  push    rdi
0x1800163c6  sub     rsp, 20h
0x1800163ca  mov     rax, cs:qword_18002A2E8
0x1800163d1  mov     ebx, edx
0x1800163d3  mov     rdi, rcx
0x1800163d6  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800163da  jnz     short loc_1800163F4
0x1800163dc  mov     edx, 150h
0x1800163e1  lea     rcx, qword_18002A2E8
0x1800163e8  call    _GetProcFromComCtl32
0x1800163ed  mov     rax, cs:qword_18002A2E8
0x1800163f4  test    rax, rax
0x1800163f7  jz      short loc_180016403
0x1800163f9  mov     edx, ebx
0x1800163fb  mov     rcx, rdi
0x1800163fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016403  mov     rbx, [rsp+28h+arg_0]
0x180016408  add     rsp, 20h
0x18001640c  pop     rdi
0x18001640d  retn
```
