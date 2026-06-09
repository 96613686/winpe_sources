# CSxArrayBuilder<_SPP_GROUP_PROP,&Free_SPP_GROUP_PROP(_SPP_GROUP_PROP *),&SxDefaultInit<_SPP_GROUP_PROP>(_SPP_GROUP_PROP *),&SxDefaultTransfer<_SPP_GROUP_PROP>(_SPP_GROUP_PROP *,_SPP_GROUP_PROP *)>::~CSxArrayBuilder<_SPP_GROUP_PROP,&Free_SPP_GROUP_PROP(_SPP_GROUP_PROP *),&SxDefaultInit<_SPP_GROUP_PROP>(_SPP_GROUP_PROP *),&SxDefaultTransfer<_SPP_GROUP_PROP>(_SPP_GROUP_PROP *,_SPP_GROUP_PROP *)>(void)

- ea: `0x180002648`
- end: `0x1800026a4`
- name: `??1?$CSxArrayBuilder@U_SPP_GROUP_PROP@@$1?Free_SPP_GROUP_PROP@@YAXPEAU1@@Z$1??$SxDefaultInit@U_SPP_GROUP_PROP@@@@YAX0@Z$1??$SxDefaultTransfer@U_SPP_GROUP_PROP@@@@YAX00@Z@@AEAA@XZ`
- size: `92`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000df40`

## callees

- `0x180002648`
- `0x1800349d0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000267f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000267f`

## pseudocode

```c
void __fastcall CSxArrayBuilder<_SPP_GROUP_PROP,&void Free_SPP_GROUP_PROP(_SPP_GROUP_PROP *),&void SxDefaultInit<_SPP_GROUP_PROP>(_SPP_GROUP_PROP *),&void SxDefaultTransfer<_SPP_GROUP_PROP>(_SPP_GROUP_PROP *,_SPP_GROUP_PROP *)>::~CSxArrayBuilder<_SPP_GROUP_PROP,&void Free_SPP_GROUP_PROP(_SPP_GROUP_PROP *),&void SxDefaultInit<_SPP_GROUP_PROP>(_SPP_GROUP_PROP *),&void SxDefaultTransfer<_SPP_GROUP_PROP>(_SPP_GROUP_PROP *,_SPP_GROUP_PROP *)>(
        __int64 a1)
{
  __int64 v1; // rsi
  LPVOID *i; // rbx

  v1 = 0;
  for ( i = (LPVOID *)(a1 + 8); (unsigned int)v1 < *(_DWORD *)(a1 + 16); v1 = (unsigned int)(v1 + 1) )
    Free_SPP_GROUP_PROP((struct _SPP_GROUP_PROP *)((char *)*i + 144 * v1));
  CoTaskMemFree(*i);
  *i = 0;
  *(_QWORD *)(a1 + 16) = 0;
}

```

## disassembly

```asm
0x180002648  mov     [rsp+arg_0], rbx
0x18000264d  mov     [rsp+arg_8], rsi
0x180002652  push    rdi
0x180002653  sub     rsp, 20h
0x180002657  xor     esi, esi
0x180002659  lea     rbx, [rcx+8]
0x18000265d  mov     rdi, rcx
0x180002660  cmp     [rcx+10h], esi
0x180002663  jbe     short loc_18000267C
0x180002665  lea     rcx, [rsi+rsi*8]
0x180002669  shl     rcx, 4
0x18000266d  add     rcx, [rbx]; struct _SPP_GROUP_PROP *
0x180002670  call    ?Free_SPP_GROUP_PROP@@YAXPEAU_SPP_GROUP_PROP@@@Z; Free_SPP_GROUP_PROP(_SPP_GROUP_PROP *)
0x180002675  inc     esi
0x180002677  cmp     esi, [rdi+10h]
0x18000267a  jb      short loc_180002665
0x18000267c  mov     rcx, [rbx]; pv
0x18000267f  call    cs:__imp_CoTaskMemFree
0x180002685  mov     rsi, [rsp+28h+arg_8]
0x18000268a  mov     qword ptr [rbx], 0
0x180002691  mov     rbx, [rsp+28h+arg_0]
0x180002696  mov     qword ptr [rdi+10h], 0
0x18000269e  add     rsp, 20h
0x1800026a2  pop     rdi
0x1800026a3  retn
```
