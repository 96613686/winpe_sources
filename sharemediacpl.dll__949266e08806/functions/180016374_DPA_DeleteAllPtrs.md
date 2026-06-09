# DPA_DeleteAllPtrs

- ea: `0x180016374`
- end: `0x1800163ba`
- name: `DPA_DeleteAllPtrs`
- size: `70`
- prototype: `BOOL __stdcall(HDPA hdpa)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000d1e4`

## callees

- `0x180016374`
- `0x180016650`
- `0x18001e010`

## pseudocode

```c
BOOL __stdcall DPA_DeleteAllPtrs(HDPA hdpa)
{
  __int64 (__fastcall *v1)(HDPA); // rax

  v1 = (__int64 (__fastcall *)(HDPA))qword_18002A2E0;
  if ( qword_18002A2E0 == -1 )
  {
    GetProcFromComCtl32((FARPROC *)&qword_18002A2E0, (const CHAR *)0x151);
    v1 = (__int64 (__fastcall *)(HDPA))qword_18002A2E0;
  }
  if ( v1 )
    LODWORD(v1) = v1(hdpa);
  return (int)v1;
}

```

## disassembly

```asm
0x180016374  push    rbx
0x180016376  sub     rsp, 20h
0x18001637a  mov     rax, cs:qword_18002A2E0
0x180016381  mov     rbx, rcx
0x180016384  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180016388  jnz     short loc_1800163A2
0x18001638a  mov     edx, 151h
0x18001638f  lea     rcx, qword_18002A2E0
0x180016396  call    _GetProcFromComCtl32
0x18001639b  mov     rax, cs:qword_18002A2E0
0x1800163a2  test    rax, rax
0x1800163a5  jz      short loc_1800163B4
0x1800163a7  mov     rcx, rbx
0x1800163aa  add     rsp, 20h
0x1800163ae  pop     rbx
0x1800163af  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x1800163b4  add     rsp, 20h
0x1800163b8  pop     rbx
0x1800163b9  retn
```
