# Free_SR_ENVIRONMENT_PROP(_SR_ENVIRONMENT_PROP *)

- ea: `0x14000d168`
- end: `0x14000d19d`
- name: `?Free_SR_ENVIRONMENT_PROP@@YAXPEAU_SR_ENVIRONMENT_PROP@@@Z`
- size: `53`
- prototype: `void __fastcall(LPVOID *)`
- caller_count: `3`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x14000d1a4`
- `0x14000d3b4`
- `0x14000d688`

## callees

- `0x14000d168`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x14000d178`
- `ole32!CoTaskMemFree` at `0x14000d189`
- `ole32!CoTaskMemFree` at `0x14000d178`
- `ole32!CoTaskMemFree` at `0x14000d189`

## pseudocode

```c
void __fastcall Free_SR_ENVIRONMENT_PROP(LPVOID *a1)
{
  void *v2; // rcx

  if ( a1 )
  {
    CoTaskMemFree(*a1);
    v2 = a1[1];
    *a1 = 0;
    CoTaskMemFree(v2);
    a1[1] = 0;
  }
}

```

## disassembly

```asm
0x14000d168  test    rcx, rcx
0x14000d16b  jz      short locret_14000D19C
0x14000d16d  push    rbx
0x14000d16e  sub     rsp, 20h
0x14000d172  mov     rbx, rcx
0x14000d175  mov     rcx, [rcx]; pv
0x14000d178  call    cs:__imp_CoTaskMemFree
0x14000d17e  mov     rcx, [rbx+8]; pv
0x14000d182  mov     qword ptr [rbx], 0
0x14000d189  call    cs:__imp_CoTaskMemFree
0x14000d18f  mov     qword ptr [rbx+8], 0
0x14000d197  add     rsp, 20h
0x14000d19b  pop     rbx
0x14000d19c  retn
```
