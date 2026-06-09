# Free_SPP_EXTERNAL_VOLUME_PROP(_SPP_EXTERNAL_VOLUME_PROP *)

- ea: `0x180034998`
- end: `0x1800349c8`
- name: `?Free_SPP_EXTERNAL_VOLUME_PROP@@YAXPEAU_SPP_EXTERNAL_VOLUME_PROP@@@Z`
- size: `48`
- prototype: `void __fastcall(struct _SPP_EXTERNAL_VOLUME_PROP *)`
- caller_count: `3`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180008118`
- `0x180011b30`
- `0x180034840`

## callees

- `0x180034998`
- `0x180034bd4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800349a8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800349a8`

## pseudocode

```c
void __fastcall Free_SPP_EXTERNAL_VOLUME_PROP(struct _SPP_EXTERNAL_VOLUME_PROP *a1)
{
  if ( a1 )
  {
    CoTaskMemFree(*(LPVOID *)a1);
    *(_QWORD *)a1 = 0;
    Free_StringArray((unsigned int *)a1 + 2, (LPVOID *)a1 + 2);
  }
}

```

## disassembly

```asm
0x180034998  test    rcx, rcx
0x18003499b  jz      short locret_1800349C7
0x18003499d  push    rbx
0x18003499e  sub     rsp, 20h
0x1800349a2  mov     rbx, rcx
0x1800349a5  mov     rcx, [rcx]; pv
0x1800349a8  call    cs:__imp_CoTaskMemFree
0x1800349ae  lea     rdx, [rbx+10h]; unsigned __int16 ***
0x1800349b2  mov     qword ptr [rbx], 0
0x1800349b9  lea     rcx, [rbx+8]; unsigned int *
0x1800349bd  call    ?Free_StringArray@@YAXPEAKPEAPEAPEAG@Z; Free_StringArray(ulong *,ushort * * *)
0x1800349c2  add     rsp, 20h
0x1800349c6  pop     rbx
0x1800349c7  retn
```
