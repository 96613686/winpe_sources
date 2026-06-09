# CTPolicyHandler<CExpandSZRegValue>::~CTPolicyHandler<CExpandSZRegValue>(void)

- ea: `0x180012430`
- end: `0x180012467`
- name: `??1?$CTPolicyHandler@VCExpandSZRegValue@@@@UEAA@XZ`
- size: `55`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180012580`
- `0x180012600`
- `0x180012690`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012447`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012451`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012447`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012451`

## pseudocode

```c
void **__fastcall CTPolicyHandler<CExpandSZRegValue>::~CTPolicyHandler<CExpandSZRegValue>(__int64 a1)
{
  void **result; // rax

  *(_QWORD *)a1 = &CTPolicyHandler<CTRegValue<unsigned short *>>::`vftable';
  CoTaskMemFree(*(LPVOID *)(a1 + 88));
  CoTaskMemFree(*(LPVOID *)(a1 + 48));
  result = &CPolicyHandlerBase::`vftable';
  *(_QWORD *)a1 = &CPolicyHandlerBase::`vftable';
  return result;
}

```

## disassembly

```asm
0x180012430  push    rbx
0x180012432  sub     rsp, 20h
0x180012436  lea     rax, ??_7?$CTPolicyHandler@V?$CTRegValue@PEAG@@@@6B@; const CTPolicyHandler<CTRegValue<ushort *>>::`vftable'
0x18001243d  mov     rbx, rcx
0x180012440  mov     [rcx], rax
0x180012443  mov     rcx, [rcx+58h]; pv
0x180012447  call    cs:__imp_CoTaskMemFree
0x18001244d  mov     rcx, [rbx+30h]; pv
0x180012451  call    cs:__imp_CoTaskMemFree
0x180012457  lea     rax, ??_7CPolicyHandlerBase@@6B@; const CPolicyHandlerBase::`vftable'
0x18001245e  mov     [rbx], rax
0x180012461  add     rsp, 20h
0x180012465  pop     rbx
0x180012466  retn
```
