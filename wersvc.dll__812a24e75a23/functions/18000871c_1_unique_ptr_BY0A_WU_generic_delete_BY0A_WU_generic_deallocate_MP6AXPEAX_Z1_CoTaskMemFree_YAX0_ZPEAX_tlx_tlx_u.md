# ??1?$unique_ptr@$$BY0A@_WU?$generic_delete@$$BY0A@_WU?$generic_deallocate@$MP6AXPEAX@Z1?CoTaskMemFree@@YAX0@ZPEAX@tlx@@@tlx@@@utl@@QEAA@XZ

- ea: `0x18000871c`
- end: `0x180008733`
- name: `??1?$unique_ptr@$$BY0A@_WU?$generic_delete@$$BY0A@_WU?$generic_deallocate@$MP6AXPEAX@Z1?CoTaskMemFree@@YAX0@ZPEAX@tlx@@@tlx@@@utl@@QEAA@XZ`
- size: `23`
- prototype: `void __fastcall(void **)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180035079`

## callees

- `0x18000871c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008728`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008728`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x18000871c  sub     rsp, 28h
0x180008720  mov     rcx, [rcx]; pv
0x180008723  test    rcx, rcx
0x180008726  jz      short loc_18000872E
0x180008728  call    cs:__imp_CoTaskMemFree
0x18000872e  add     rsp, 28h
0x180008732  retn
```
