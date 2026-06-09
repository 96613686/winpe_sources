# FreeSharableItemDescriptor(SHARABLE_ITEM_DESCRIPTOR *)

- ea: `0x18006109c`
- end: `0x1800610d4`
- name: `?FreeSharableItemDescriptor@@YAXPEAUSHARABLE_ITEM_DESCRIPTOR@@@Z`
- size: `56`
- prototype: `void __fastcall(struct SHARABLE_ITEM_DESCRIPTOR *)`
- caller_count: `5`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x180060f88`
- `0x1800610dc`
- `0x180061210`
- `0x18006a530`
- `0x18006aa20`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800610a8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800610b2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800610bc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800610a8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800610b2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800610bc`

## pseudocode

```c
void __fastcall FreeSharableItemDescriptor(LPVOID *a1)
{
  CoTaskMemFree(*a1);
  CoTaskMemFree(a1[1]);
  CoTaskMemFree(a1[2]);
  *(_OWORD *)a1 = 0;
  a1[2] = 0;
}

```

## disassembly

```asm
0x18006109c  push    rbx
0x18006109e  sub     rsp, 20h
0x1800610a2  mov     rbx, rcx
0x1800610a5  mov     rcx, [rcx]; pv
0x1800610a8  call    cs:__imp_CoTaskMemFree
0x1800610ae  mov     rcx, [rbx+8]; pv
0x1800610b2  call    cs:__imp_CoTaskMemFree
0x1800610b8  mov     rcx, [rbx+10h]; pv
0x1800610bc  call    cs:__imp_CoTaskMemFree
0x1800610c2  xorps   xmm0, xmm0
0x1800610c5  xor     eax, eax
0x1800610c7  movups  xmmword ptr [rbx], xmm0
0x1800610ca  mov     [rbx+10h], rax
0x1800610ce  add     rsp, 20h
0x1800610d2  pop     rbx
0x1800610d3  retn
```
