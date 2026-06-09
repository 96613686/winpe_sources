# CSxArrayBuilder<_SPP_COMPONENT_PROP,&Free_SPP_COMPONENT_PROP(_SPP_COMPONENT_PROP *),&SxDefaultInit<_SPP_COMPONENT_PROP>(_SPP_COMPONENT_PROP *),&SxDefaultTransfer<_SPP_COMPONENT_PROP>(_SPP_COMPONENT_PROP *,_SPP_COMPONENT_PROP *)>::~CSxArrayBuilder<_SPP_COMPONENT_PROP,&Free_SPP_COMPONENT_PROP(_SPP_COMPONENT_PROP *),&SxDefaultInit<_SPP_COMPONENT_PROP>(_SPP_COMPONENT_PROP *),&SxDefaultTransfer<_SPP_COMPONENT_PROP>(_SPP_COMPONENT_PROP *,_SPP_COMPONENT_PROP *)>(void)

- ea: `0x180002520`
- end: `0x18000257c`
- name: `??1?$CSxArrayBuilder@U_SPP_COMPONENT_PROP@@$1?Free_SPP_COMPONENT_PROP@@YAXPEAU1@@Z$1??$SxDefaultInit@U_SPP_COMPONENT_PROP@@@@YAX0@Z$1??$SxDefaultTransfer@U_SPP_COMPONENT_PROP@@@@YAX00@Z@@AEAA@XZ`
- size: `92`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000de40`

## callees

- `0x180002520`
- `0x18003475c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180002557`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180002557`

## pseudocode

```c
void __fastcall CSxArrayBuilder<_SPP_COMPONENT_PROP,&void Free_SPP_COMPONENT_PROP(_SPP_COMPONENT_PROP *),&void SxDefaultInit<_SPP_COMPONENT_PROP>(_SPP_COMPONENT_PROP *),&void SxDefaultTransfer<_SPP_COMPONENT_PROP>(_SPP_COMPONENT_PROP *,_SPP_COMPONENT_PROP *)>::~CSxArrayBuilder<_SPP_COMPONENT_PROP,&void Free_SPP_COMPONENT_PROP(_SPP_COMPONENT_PROP *),&void SxDefaultInit<_SPP_COMPONENT_PROP>(_SPP_COMPONENT_PROP *),&void SxDefaultTransfer<_SPP_COMPONENT_PROP>(_SPP_COMPONENT_PROP *,_SPP_COMPONENT_PROP *)>(
        __int64 a1)
{
  __int64 v1; // rsi
  LPVOID *i; // rbx

  v1 = 0;
  for ( i = (LPVOID *)(a1 + 8); (unsigned int)v1 < *(_DWORD *)(a1 + 16); v1 = (unsigned int)(v1 + 1) )
    Free_SPP_COMPONENT_PROP((struct _SPP_COMPONENT_PROP *)((char *)*i + 80 * v1));
  CoTaskMemFree(*i);
  *i = 0;
  *(_QWORD *)(a1 + 16) = 0;
}

```

## disassembly

```asm
0x180002520  mov     [rsp+arg_0], rbx
0x180002525  mov     [rsp+arg_8], rsi
0x18000252a  push    rdi
0x18000252b  sub     rsp, 20h
0x18000252f  xor     esi, esi
0x180002531  lea     rbx, [rcx+8]
0x180002535  mov     rdi, rcx
0x180002538  cmp     [rcx+10h], esi
0x18000253b  jbe     short loc_180002554
0x18000253d  lea     rcx, [rsi+rsi*4]
0x180002541  shl     rcx, 4
0x180002545  add     rcx, [rbx]; struct _SPP_COMPONENT_PROP *
0x180002548  call    ?Free_SPP_COMPONENT_PROP@@YAXPEAU_SPP_COMPONENT_PROP@@@Z; Free_SPP_COMPONENT_PROP(_SPP_COMPONENT_PROP *)
0x18000254d  inc     esi
0x18000254f  cmp     esi, [rdi+10h]
0x180002552  jb      short loc_18000253D
0x180002554  mov     rcx, [rbx]; pv
0x180002557  call    cs:__imp_CoTaskMemFree
0x18000255d  mov     rsi, [rsp+28h+arg_8]
0x180002562  mov     qword ptr [rbx], 0
0x180002569  mov     rbx, [rsp+28h+arg_0]
0x18000256e  mov     qword ptr [rdi+10h], 0
0x180002576  add     rsp, 20h
0x18000257a  pop     rdi
0x18000257b  retn
```
