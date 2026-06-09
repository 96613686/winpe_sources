# CSxArrayBuilder<_SPP_ENVIRONMENT_PROP,&Free_SPP_ENVIRONMENT_PROP(_SPP_ENVIRONMENT_PROP *),&SxDefaultInit<_SPP_ENVIRONMENT_PROP>(_SPP_ENVIRONMENT_PROP *),&SxDefaultTransfer<_SPP_ENVIRONMENT_PROP>(_SPP_ENVIRONMENT_PROP *,_SPP_ENVIRONMENT_PROP *)>::~CSxArrayBuilder<_SPP_ENVIRONMENT_PROP,&Free_SPP_ENVIRONMENT_PROP(_SPP_ENVIRONMENT_PROP *),&SxDefaultInit<_SPP_ENVIRONMENT_PROP>(_SPP_ENVIRONMENT_PROP *),&SxDefaultTransfer<_SPP_ENVIRONMENT_PROP>(_SPP_ENVIRONMENT_PROP *,_SPP_ENVIRONMENT_PROP *)>(void)

- ea: `0x180002584`
- end: `0x1800025de`
- name: `??1?$CSxArrayBuilder@U_SPP_ENVIRONMENT_PROP@@$1?Free_SPP_ENVIRONMENT_PROP@@YAXPEAU1@@Z$1??$SxDefaultInit@U_SPP_ENVIRONMENT_PROP@@@@YAX0@Z$1??$SxDefaultTransfer@U_SPP_ENVIRONMENT_PROP@@@@YAX00@Z@@AEAA@XZ`
- size: `90`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000de80`

## callees

- `0x180002584`
- `0x180034804`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800025b9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800025b9`

## pseudocode

```c
void __fastcall CSxArrayBuilder<_SPP_ENVIRONMENT_PROP,&void Free_SPP_ENVIRONMENT_PROP(_SPP_ENVIRONMENT_PROP *),&void SxDefaultInit<_SPP_ENVIRONMENT_PROP>(_SPP_ENVIRONMENT_PROP *),&void SxDefaultTransfer<_SPP_ENVIRONMENT_PROP>(_SPP_ENVIRONMENT_PROP *,_SPP_ENVIRONMENT_PROP *)>::~CSxArrayBuilder<_SPP_ENVIRONMENT_PROP,&void Free_SPP_ENVIRONMENT_PROP(_SPP_ENVIRONMENT_PROP *),&void SxDefaultInit<_SPP_ENVIRONMENT_PROP>(_SPP_ENVIRONMENT_PROP *),&void SxDefaultTransfer<_SPP_ENVIRONMENT_PROP>(_SPP_ENVIRONMENT_PROP *,_SPP_ENVIRONMENT_PROP *)>(
        __int64 a1)
{
  unsigned int v1; // esi
  LPVOID *i; // rbx

  v1 = 0;
  for ( i = (LPVOID *)(a1 + 8); v1 < *(_DWORD *)(a1 + 16); ++v1 )
    Free_SPP_ENVIRONMENT_PROP((struct _SPP_ENVIRONMENT_PROP *)((char *)*i + 16 * v1));
  CoTaskMemFree(*i);
  *i = 0;
  *(_QWORD *)(a1 + 16) = 0;
}

```

## disassembly

```asm
0x180002584  mov     [rsp+arg_0], rbx
0x180002589  mov     [rsp+arg_8], rsi
0x18000258e  push    rdi
0x18000258f  sub     rsp, 20h
0x180002593  xor     esi, esi
0x180002595  lea     rbx, [rcx+8]
0x180002599  mov     rdi, rcx
0x18000259c  cmp     [rcx+10h], esi
0x18000259f  jbe     short loc_1800025B6
0x1800025a1  mov     ecx, esi
0x1800025a3  shl     rcx, 4
0x1800025a7  add     rcx, [rbx]; struct _SPP_ENVIRONMENT_PROP *
0x1800025aa  call    ?Free_SPP_ENVIRONMENT_PROP@@YAXPEAU_SPP_ENVIRONMENT_PROP@@@Z; Free_SPP_ENVIRONMENT_PROP(_SPP_ENVIRONMENT_PROP *)
0x1800025af  inc     esi
0x1800025b1  cmp     esi, [rdi+10h]
0x1800025b4  jb      short loc_1800025A1
0x1800025b6  mov     rcx, [rbx]; pv
0x1800025b9  call    cs:__imp_CoTaskMemFree
0x1800025bf  mov     rsi, [rsp+28h+arg_8]
0x1800025c4  mov     qword ptr [rbx], 0
0x1800025cb  mov     rbx, [rsp+28h+arg_0]
0x1800025d0  mov     qword ptr [rdi+10h], 0
0x1800025d8  add     rsp, 20h
0x1800025dc  pop     rdi
0x1800025dd  retn
```
