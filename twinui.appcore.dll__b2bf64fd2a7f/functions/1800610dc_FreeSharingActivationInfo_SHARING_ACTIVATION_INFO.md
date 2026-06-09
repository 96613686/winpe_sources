# FreeSharingActivationInfo(SHARING_ACTIVATION_INFO *)

- ea: `0x1800610dc`
- end: `0x180061128`
- name: `?FreeSharingActivationInfo@@YAXPEAUSHARING_ACTIVATION_INFO@@@Z`
- size: `76`
- prototype: `void __fastcall(struct SHARING_ACTIVATION_INFO *)`
- caller_count: `3`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180060f88`
- `0x180061210`
- `0x18006b250`

## callees

- `0x18002bc68`
- `0x18006109c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800610f1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800610fb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180061105`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006110f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800610f1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800610fb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180061105`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006110f`

## pseudocode

```c
void __fastcall FreeSharingActivationInfo(struct SHARING_ACTIVATION_INFO *a1)
{
  FreeSharableItemDescriptor((struct SHARING_ACTIVATION_INFO *)((char *)a1 + 48));
  CoTaskMemFree(*(LPVOID *)a1);
  CoTaskMemFree(*((LPVOID *)a1 + 2));
  CoTaskMemFree(*((LPVOID *)a1 + 3));
  CoTaskMemFree(*((LPVOID *)a1 + 4));
  memset_0(a1, 0, 0x48u);
}

```

## disassembly

```asm
0x1800610dc  push    rbx
0x1800610de  sub     rsp, 20h
0x1800610e2  mov     rbx, rcx
0x1800610e5  add     rcx, 30h ; '0'; struct SHARABLE_ITEM_DESCRIPTOR *
0x1800610e9  call    ?FreeSharableItemDescriptor@@YAXPEAUSHARABLE_ITEM_DESCRIPTOR@@@Z; FreeSharableItemDescriptor(SHARABLE_ITEM_DESCRIPTOR *)
0x1800610ee  mov     rcx, [rbx]; pv
0x1800610f1  call    cs:__imp_CoTaskMemFree
0x1800610f7  mov     rcx, [rbx+10h]; pv
0x1800610fb  call    cs:__imp_CoTaskMemFree
0x180061101  mov     rcx, [rbx+18h]; pv
0x180061105  call    cs:__imp_CoTaskMemFree
0x18006110b  mov     rcx, [rbx+20h]; pv
0x18006110f  call    cs:__imp_CoTaskMemFree
0x180061115  xor     edx, edx; Val
0x180061117  mov     rcx, rbx; void *
0x18006111a  lea     r8d, [rdx+48h]; Size
0x18006111e  add     rsp, 20h
0x180061122  pop     rbx
0x180061123  jmp     memset_0
```
