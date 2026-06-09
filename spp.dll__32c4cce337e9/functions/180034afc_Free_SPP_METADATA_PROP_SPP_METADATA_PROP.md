# Free_SPP_METADATA_PROP(_SPP_METADATA_PROP *)

- ea: `0x180034afc`
- end: `0x180034b80`
- name: `?Free_SPP_METADATA_PROP@@YAXPEAU_SPP_METADATA_PROP@@@Z`
- size: `132`
- prototype: `void __fastcall(struct _SPP_METADATA_PROP *)`
- caller_count: `3`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000a6a0`
- `0x18001431c`
- `0x1800206c0`

## callees

- `0x18003475c`
- `0x180034afc`
- `0x180034bd4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034b16`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034b5c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034b16`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034b5c`

## pseudocode

```c
void __fastcall Free_SPP_METADATA_PROP(struct _SPP_METADATA_PROP *a1)
{
  _DWORD *v2; // rdi
  __int64 i; // rsi

  if ( a1 )
  {
    CoTaskMemFree(*(LPVOID *)a1);
    *(_QWORD *)a1 = 0;
    Free_StringArray((unsigned int *)a1 + 2, (LPVOID *)a1 + 2);
    v2 = (_DWORD *)((char *)a1 + 24);
    if ( *((_QWORD *)a1 + 4) )
    {
      for ( i = 0; (unsigned int)i < *v2; i = (unsigned int)(i + 1) )
        Free_SPP_COMPONENT_PROP((LPVOID *)(*((_QWORD *)a1 + 4) + 80 * i));
      CoTaskMemFree(*((LPVOID *)a1 + 4));
      *((_QWORD *)a1 + 4) = 0;
    }
    *v2 = 0;
  }
}

```

## disassembly

```asm
0x180034afc  test    rcx, rcx
0x180034aff  jz      short locret_180034B7F
0x180034b01  mov     [rsp+arg_0], rbx
0x180034b06  mov     [rsp+arg_8], rsi
0x180034b0b  push    rdi
0x180034b0c  sub     rsp, 20h
0x180034b10  mov     rbx, rcx
0x180034b13  mov     rcx, [rcx]; pv
0x180034b16  call    cs:__imp_CoTaskMemFree
0x180034b1c  lea     rdx, [rbx+10h]; unsigned __int16 ***
0x180034b20  mov     qword ptr [rbx], 0
0x180034b27  lea     rcx, [rbx+8]; unsigned int *
0x180034b2b  call    ?Free_StringArray@@YAXPEAKPEAPEAPEAG@Z; Free_StringArray(ulong *,ushort * * *)
0x180034b30  cmp     qword ptr [rbx+20h], 0
0x180034b35  lea     rdi, [rbx+18h]
0x180034b39  jz      short loc_180034B6A
0x180034b3b  xor     esi, esi
0x180034b3d  cmp     [rdi], esi
0x180034b3f  jbe     short loc_180034B58
0x180034b41  lea     rcx, [rsi+rsi*4]
0x180034b45  shl     rcx, 4
0x180034b49  add     rcx, [rbx+20h]; struct _SPP_COMPONENT_PROP *
0x180034b4d  call    ?Free_SPP_COMPONENT_PROP@@YAXPEAU_SPP_COMPONENT_PROP@@@Z; Free_SPP_COMPONENT_PROP(_SPP_COMPONENT_PROP *)
0x180034b52  inc     esi
0x180034b54  cmp     esi, [rdi]
0x180034b56  jb      short loc_180034B41
0x180034b58  mov     rcx, [rbx+20h]; pv
0x180034b5c  call    cs:__imp_CoTaskMemFree
0x180034b62  mov     qword ptr [rbx+20h], 0
0x180034b6a  mov     rbx, [rsp+28h+arg_0]
0x180034b6f  mov     rsi, [rsp+28h+arg_8]
0x180034b74  mov     dword ptr [rdi], 0
0x180034b7a  add     rsp, 20h
0x180034b7e  pop     rdi
0x180034b7f  retn
```
