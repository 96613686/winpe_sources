# ??1?$unique_ptr@$$BY0A@_WU?$generic_delete@$$BY0A@_WU?$generic_deallocate@$MP6AXPEAX@Z1?CoTaskMemFree@@YAX0@ZPEAX@tlx@@@tlx@@@utl@@QEAA@XZ

- ea: `0x140017278`
- end: `0x14001728f`
- name: `??1?$unique_ptr@$$BY0A@_WU?$generic_delete@$$BY0A@_WU?$generic_deallocate@$MP6AXPEAX@Z1?CoTaskMemFree@@YAX0@ZPEAX@tlx@@@tlx@@@utl@@QEAA@XZ`
- size: `23`
- prototype: `void __fastcall(void **)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x14001ce6b`
- `0x14001ce7d`

## callees

- `0x140017278`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140017284`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140017284`

## pseudocode

```c
void __fastcall __1__unique_ptr___BY0A__WU__generic_delete___BY0A__WU__generic_deallocate__MP6AXPEAX_Z1_CoTaskMemFree__YAX0_ZPEAX_tlx___tlx___utl__QEAA_XZ(
        void **a1)
{
  void *v1; // rcx

  v1 = *a1;
  if ( v1 )
    CoTaskMemFree(v1);
}

```

## disassembly

```asm
0x140017278  sub     rsp, 28h
0x14001727c  mov     rcx, [rcx]; pv
0x14001727f  test    rcx, rcx
0x140017282  jz      short loc_14001728A
0x140017284  call    cs:__imp_CoTaskMemFree
0x14001728a  add     rsp, 28h
0x14001728e  retn
```
