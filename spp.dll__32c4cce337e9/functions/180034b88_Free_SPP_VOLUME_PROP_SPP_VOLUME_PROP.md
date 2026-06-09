# Free_SPP_VOLUME_PROP(_SPP_VOLUME_PROP *)

- ea: `0x180034b88`
- end: `0x180034bcc`
- name: `?Free_SPP_VOLUME_PROP@@YAXPEAU_SPP_VOLUME_PROP@@@Z`
- size: `68`
- prototype: `void __fastcall(struct _SPP_VOLUME_PROP *)`
- caller_count: `3`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000817c`
- `0x18001ed44`
- `0x1800349d0`

## callees

- `0x180034b88`
- `0x180034bd4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034b99`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034bab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034b99`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034bab`

## pseudocode

```c
void __fastcall Free_SPP_VOLUME_PROP(struct _SPP_VOLUME_PROP *a1)
{
  void *v2; // rcx

  if ( a1 )
  {
    CoTaskMemFree(*((LPVOID *)a1 + 2));
    v2 = (void *)*((_QWORD *)a1 + 3);
    *((_QWORD *)a1 + 2) = 0;
    CoTaskMemFree(v2);
    *((_QWORD *)a1 + 3) = 0;
    Free_StringArray((unsigned int *)a1 + 8, (LPVOID *)a1 + 5);
  }
}

```

## disassembly

```asm
0x180034b88  test    rcx, rcx
0x180034b8b  jz      short locret_180034BCB
0x180034b8d  push    rbx
0x180034b8e  sub     rsp, 20h
0x180034b92  mov     rbx, rcx
0x180034b95  mov     rcx, [rcx+10h]; pv
0x180034b99  call    cs:__imp_CoTaskMemFree
0x180034b9f  mov     rcx, [rbx+18h]; pv
0x180034ba3  mov     qword ptr [rbx+10h], 0
0x180034bab  call    cs:__imp_CoTaskMemFree
0x180034bb1  lea     rdx, [rbx+28h]; unsigned __int16 ***
0x180034bb5  mov     qword ptr [rbx+18h], 0
0x180034bbd  lea     rcx, [rbx+20h]; unsigned int *
0x180034bc1  call    ?Free_StringArray@@YAXPEAKPEAPEAPEAG@Z; Free_StringArray(ulong *,ushort * * *)
0x180034bc6  add     rsp, 20h
0x180034bca  pop     rbx
0x180034bcb  retn
```
