# UnInitializeThreadFromPool(SThreadFromPoolState)

- ea: `0x180003cc4`
- end: `0x180003ceb`
- name: `?UnInitializeThreadFromPool@@YAXUSThreadFromPoolState@@@Z`
- size: `39`
- prototype: `NTSTATUS __fastcall(CActiveThreadList *)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800053b0`
- `0x18000f150`
- `0x18000f1b0`

## callees

- `0x180003cc4`
- `0x1800047b0`

## import_xrefs

- `ntdll!RtlSetThreadErrorMode` at `0x180003ce4`

## pseudocode

```c
NTSTATUS __fastcall UnInitializeThreadFromPool(CActiveThreadList *a1)
{
  ULONG v1; // ebx

  v1 = (unsigned int)a1;
  if ( g_pActiveThreadList )
    CActiveThreadList::RemoveCurrent(a1);
  return RtlSetThreadErrorMode(v1, 0);
}

```

## disassembly

```asm
0x180003cc4  push    rbx
0x180003cc6  sub     rsp, 20h
0x180003cca  cmp     cs:g_pActiveThreadList, 0
0x180003cd2  mov     ebx, ecx
0x180003cd4  jz      short loc_180003CDB
0x180003cd6  call    ?RemoveCurrent@CActiveThreadList@@QEAAJXZ; CActiveThreadList::RemoveCurrent(void)
0x180003cdb  xor     edx, edx
0x180003cdd  mov     ecx, ebx
0x180003cdf  add     rsp, 20h
0x180003ce3  pop     rbx
0x180003ce4  jmp     cs:__imp_RtlSetThreadErrorMode
```
