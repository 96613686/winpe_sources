# std::default_delete<PIN_MAPS_MEM>::operator()(PIN_MAPS_MEM *)

- ea: `0x18000f3a4`
- end: `0x18000f3e0`
- name: `??R?$default_delete@UPIN_MAPS_MEM@@@std@@QEBAXPEAUPIN_MAPS_MEM@@@Z`
- size: `60`
- prototype: `void __fastcall(__int64, void *)`
- caller_count: `4`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18000c7e8`
- `0x18000dc78`
- `0x180016954`
- `0x180029000`

## callees

- `0x180001ee4`
- `0x180002360`
- `0x18000f3a4`

## pseudocode

```c
void __fastcall std::default_delete<PIN_MAPS_MEM>::operator()(__int64 a1, void *a2)
{
  if ( a2 )
  {
    `eh vector destructor iterator'(a2, 0x98u, 2u, (void (*)(void *))PIN_MAP_RECORD_MEM::~PIN_MAP_RECORD_MEM);
    operator delete(a2);
  }
}

```

## disassembly

```asm
0x18000f3a4  test    rdx, rdx
0x18000f3a7  jz      short locret_18000F3DF
0x18000f3a9  push    rbx
0x18000f3aa  sub     rsp, 20h
0x18000f3ae  mov     rbx, rdx
0x18000f3b1  lea     r9, ??1PIN_MAP_RECORD_MEM@@QEAA@XZ; void (*)(void *)
0x18000f3b8  mov     edx, 98h; unsigned __int64
0x18000f3bd  mov     r8d, 2; unsigned __int64
0x18000f3c3  mov     rcx, rbx; void *
0x18000f3c6  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x18000f3cb  nop
0x18000f3cc  mov     edx, 130h
0x18000f3d1  mov     rcx, rbx; Block
0x18000f3d4  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000f3d9  nop
0x18000f3da  add     rsp, 20h
0x18000f3de  pop     rbx
0x18000f3df  retn
```
