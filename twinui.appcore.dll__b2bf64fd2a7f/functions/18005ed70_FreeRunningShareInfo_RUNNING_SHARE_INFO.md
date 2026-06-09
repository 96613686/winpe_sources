# FreeRunningShareInfo(RUNNING_SHARE_INFO *)

- ea: `0x18005ed70`
- end: `0x18005edb4`
- name: `?FreeRunningShareInfo@@YAXPEAURUNNING_SHARE_INFO@@@Z`
- size: `68`
- prototype: `void __fastcall(struct RUNNING_SHARE_INFO *)`
- caller_count: `4`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18005e808`
- `0x18005eb10`
- `0x18005f750`
- `0x180064680`

## callees

- `0x18002bc68`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005ed7d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005ed87`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005ed91`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005ed9b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005ed7d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005ed87`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005ed91`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005ed9b`

## pseudocode

```c
void __fastcall FreeRunningShareInfo(LPVOID *a1)
{
  CoTaskMemFree(a1[3]);
  CoTaskMemFree(a1[4]);
  CoTaskMemFree(a1[5]);
  CoTaskMemFree(a1[6]);
  memset_0(a1, 0, 0x48u);
}

```

## disassembly

```asm
0x18005ed70  push    rbx
0x18005ed72  sub     rsp, 20h
0x18005ed76  mov     rbx, rcx
0x18005ed79  mov     rcx, [rcx+18h]; pv
0x18005ed7d  call    cs:__imp_CoTaskMemFree
0x18005ed83  mov     rcx, [rbx+20h]; pv
0x18005ed87  call    cs:__imp_CoTaskMemFree
0x18005ed8d  mov     rcx, [rbx+28h]; pv
0x18005ed91  call    cs:__imp_CoTaskMemFree
0x18005ed97  mov     rcx, [rbx+30h]; pv
0x18005ed9b  call    cs:__imp_CoTaskMemFree
0x18005eda1  xor     edx, edx; Val
0x18005eda3  mov     rcx, rbx; void *
0x18005eda6  lea     r8d, [rdx+48h]; Size
0x18005edaa  add     rsp, 20h
0x18005edae  pop     rbx
0x18005edaf  jmp     memset_0
```
