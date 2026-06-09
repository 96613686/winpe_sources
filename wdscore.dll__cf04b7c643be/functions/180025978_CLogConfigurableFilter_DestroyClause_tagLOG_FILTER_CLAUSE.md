# CLogConfigurableFilter::DestroyClause(tagLOG_FILTER_CLAUSE *)

- ea: `0x180025978`
- end: `0x1800259a2`
- name: `?DestroyClause@CLogConfigurableFilter@@IEAAXPEAUtagLOG_FILTER_CLAUSE@@@Z`
- size: `42`
- prototype: `void(CLogConfigurableFilter *__hidden this, struct tagLOG_FILTER_CLAUSE *)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, registry_config`

## callers

- `0x180025630`
- `0x1800259d8`

## callees

- `0x180001184`
- `0x180021ebc`
- `0x180025978`

## pseudocode

```c
void __fastcall CLogConfigurableFilter::DestroyClause(CLogConfigurableFilter *this, struct tagLOG_FILTER_CLAUSE *a2)
{
  if ( !*((_DWORD *)a2 + 2) && *((_QWORD *)a2 + 2) )
    DestroyParsedPatternW();
  operator delete(a2);
}

```

## disassembly

```asm
0x180025978  push    rbx
0x18002597a  sub     rsp, 20h
0x18002597e  cmp     dword ptr [rdx+8], 0
0x180025982  mov     rbx, rdx
0x180025985  jnz     short loc_180025995
0x180025987  mov     rcx, [rdx+10h]
0x18002598b  test    rcx, rcx
0x18002598e  jz      short loc_180025995
0x180025990  call    DestroyParsedPatternW
0x180025995  mov     rcx, rbx; Block
0x180025998  add     rsp, 20h
0x18002599c  pop     rbx
0x18002599d  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
