# Free_SPP_BAD_WRITER_INFO(_SPP_WRITER_ERROR_INFO *)

- ea: `0x180008d8c`
- end: `0x180008e05`
- name: `?Free_SPP_BAD_WRITER_INFO@@YAXPEAU_SPP_WRITER_ERROR_INFO@@@Z`
- size: `121`
- prototype: `void __fastcall(struct _SPP_WRITER_ERROR_INFO *)`
- caller_count: `3`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800081dc`
- `0x1800123e4`
- `0x180020500`

## callees

- `0x180008d3c`
- `0x180008d8c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008da2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008db4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008dec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008da2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008db4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008dec`

## pseudocode

```c
void __fastcall Free_SPP_BAD_WRITER_INFO(LPVOID *a1)
{
  void *v2; // rcx
  bool v3; // zf
  __int64 i; // rdi

  if ( a1 )
  {
    CoTaskMemFree(a1[4]);
    v2 = a1[7];
    a1[4] = 0;
    CoTaskMemFree(v2);
    v3 = a1[9] == 0;
    a1[7] = 0;
    if ( !v3 )
    {
      for ( i = 0; (unsigned int)i < *((_DWORD *)a1 + 16); i = (unsigned int)(i + 1) )
        Free_SPP_BAD_COMPONENT_INFO((struct _SPP_COMPONENT_ERROR_INFO *)((char *)a1[9] + 40 * i));
      CoTaskMemFree(a1[9]);
      a1[9] = 0;
    }
  }
}

```

## disassembly

```asm
0x180008d8c  test    rcx, rcx
0x180008d8f  jz      short locret_180008E04
0x180008d91  mov     [rsp+arg_0], rbx
0x180008d96  push    rdi
0x180008d97  sub     rsp, 20h
0x180008d9b  mov     rbx, rcx
0x180008d9e  mov     rcx, [rcx+20h]; pv
0x180008da2  call    cs:__imp_CoTaskMemFree
0x180008da8  mov     rcx, [rbx+38h]; pv
0x180008dac  mov     qword ptr [rbx+20h], 0
0x180008db4  call    cs:__imp_CoTaskMemFree
0x180008dba  cmp     qword ptr [rbx+48h], 0
0x180008dbf  mov     qword ptr [rbx+38h], 0
0x180008dc7  jz      short loc_180008DFA
0x180008dc9  xor     edi, edi
0x180008dcb  cmp     [rbx+40h], edi
0x180008dce  jbe     short loc_180008DE8
0x180008dd0  mov     rax, [rbx+48h]
0x180008dd4  lea     rcx, [rdi+rdi*4]
0x180008dd8  lea     rcx, [rax+rcx*8]; struct _SPP_COMPONENT_ERROR_INFO *
0x180008ddc  call    ?Free_SPP_BAD_COMPONENT_INFO@@YAXPEAU_SPP_COMPONENT_ERROR_INFO@@@Z; Free_SPP_BAD_COMPONENT_INFO(_SPP_COMPONENT_ERROR_INFO *)
0x180008de1  inc     edi
0x180008de3  cmp     edi, [rbx+40h]
0x180008de6  jb      short loc_180008DD0
0x180008de8  mov     rcx, [rbx+48h]; pv
0x180008dec  call    cs:__imp_CoTaskMemFree
0x180008df2  mov     qword ptr [rbx+48h], 0
0x180008dfa  mov     rbx, [rsp+28h+arg_0]
0x180008dff  add     rsp, 20h
0x180008e03  pop     rdi
0x180008e04  retn
```
