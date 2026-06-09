# ??$replace@XU?$generic_delete@XU?$generic_deallocate@$MP6APEAXPEAX@Z1?LocalFree@@YAPEAX0@ZPEAX@tlx@@@tlx@@@utl@@YAPEAPEAXAEAV?$unique_ptr@XU?$generic_delete@XU?$generic_deallocate@$MP6APEAXPEAX@Z1?LocalFree@@YAPEAX0@ZPEAX@tlx@@@tlx@@@0@@Z

- ea: `0x180013f54`
- end: `0x180013f7b`
- name: `??$replace@XU?$generic_delete@XU?$generic_deallocate@$MP6APEAXPEAX@Z1?LocalFree@@YAPEAX0@ZPEAX@tlx@@@tlx@@@utl@@YAPEAPEAXAEAV?$unique_ptr@XU?$generic_delete@XU?$generic_deallocate@$MP6APEAXPEAX@Z1?LocalFree@@YAPEAX0@ZPEAX@tlx@@@tlx@@@0@@Z`
- size: `39`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180016318`
- `0x18001c6b0`
- `0x18001d9e8`
- `0x18001ed68`
- `0x180022108`
- `0x180031000`

## callees

- `0x180013f54`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013f6c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013f6c`

## pseudocode

```c
void **__fastcall ___replace_XU__generic_delete_XU__generic_deallocate__MP6APEAXPEAX_Z1_LocalFree__YAPEAX0_ZPEAX_tlx___tlx___utl__YAPEAPEAXAEAV__unique_ptr_XU__generic_delete_XU__generic_deallocate__MP6APEAXPEAX_Z1_LocalFree__YAPEAX0_ZPEAX_tlx___tlx___0__Z(
        void **a1)
{
  void *v2; // rcx

  v2 = *a1;
  *a1 = 0;
  if ( v2 )
    LocalFree(v2);
  return a1;
}

```

## disassembly

```asm
0x180013f54  push    rbx
0x180013f56  sub     rsp, 20h
0x180013f5a  mov     rbx, rcx
0x180013f5d  mov     rcx, [rcx]; hMem
0x180013f60  mov     qword ptr [rbx], 0
0x180013f67  test    rcx, rcx
0x180013f6a  jz      short loc_180013F72
0x180013f6c  call    cs:__imp_LocalFree
0x180013f72  mov     rax, rbx
0x180013f75  add     rsp, 20h
0x180013f79  pop     rbx
0x180013f7a  retn
```
