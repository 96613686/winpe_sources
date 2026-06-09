# CSxArrayBuilder<_SPP_EXTERNAL_GROUP_PROP,&Free_SPP_EXTERNAL_GROUP_PROP(_SPP_EXTERNAL_GROUP_PROP *),&SxDefaultInit<_SPP_EXTERNAL_GROUP_PROP>(_SPP_EXTERNAL_GROUP_PROP *),&SxDefaultTransfer<_SPP_EXTERNAL_GROUP_PROP>(_SPP_EXTERNAL_GROUP_PROP *,_SPP_EXTERNAL_GROUP_PROP *)>::~CSxArrayBuilder<_SPP_EXTERNAL_GROUP_PROP,&Free_SPP_EXTERNAL_GROUP_PROP(_SPP_EXTERNAL_GROUP_PROP *),&SxDefaultInit<_SPP_EXTERNAL_GROUP_PROP>(_SPP_EXTERNAL_GROUP_PROP *),&SxDefaultTransfer<_SPP_EXTERNAL_GROUP_PROP>(_SPP_EXTERNAL_GROUP_PROP *,_SPP_EXTERNAL_GROUP_PROP *)>(void)

- ea: `0x1800025e4`
- end: `0x180002641`
- name: `??1?$CSxArrayBuilder@U_SPP_EXTERNAL_GROUP_PROP@@$1?Free_SPP_EXTERNAL_GROUP_PROP@@YAXPEAU1@@Z$1??$SxDefaultInit@U_SPP_EXTERNAL_GROUP_PROP@@@@YAX0@Z$1??$SxDefaultTransfer@U_SPP_EXTERNAL_GROUP_PROP@@@@YAX00@Z@@AEAA@XZ`
- size: `93`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000dec0`

## callees

- `0x1800025e4`
- `0x180034840`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000261c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000261c`

## pseudocode

```c
void __fastcall CSxArrayBuilder<_SPP_EXTERNAL_GROUP_PROP,&void Free_SPP_EXTERNAL_GROUP_PROP(_SPP_EXTERNAL_GROUP_PROP *),&void SxDefaultInit<_SPP_EXTERNAL_GROUP_PROP>(_SPP_EXTERNAL_GROUP_PROP *),&void SxDefaultTransfer<_SPP_EXTERNAL_GROUP_PROP>(_SPP_EXTERNAL_GROUP_PROP *,_SPP_EXTERNAL_GROUP_PROP *)>::~CSxArrayBuilder<_SPP_EXTERNAL_GROUP_PROP,&void Free_SPP_EXTERNAL_GROUP_PROP(_SPP_EXTERNAL_GROUP_PROP *),&void SxDefaultInit<_SPP_EXTERNAL_GROUP_PROP>(_SPP_EXTERNAL_GROUP_PROP *),&void SxDefaultTransfer<_SPP_EXTERNAL_GROUP_PROP>(_SPP_EXTERNAL_GROUP_PROP *,_SPP_EXTERNAL_GROUP_PROP *)>(
        __int64 a1)
{
  unsigned int v1; // esi
  LPVOID *i; // rbx

  v1 = 0;
  for ( i = (LPVOID *)(a1 + 8); v1 < *(_DWORD *)(a1 + 16); ++v1 )
    Free_SPP_EXTERNAL_GROUP_PROP((struct _SPP_EXTERNAL_GROUP_PROP *)((char *)*i + 176 * v1));
  CoTaskMemFree(*i);
  *i = 0;
  *(_QWORD *)(a1 + 16) = 0;
}

```

## disassembly

```asm
0x1800025e4  mov     [rsp+arg_0], rbx
0x1800025e9  mov     [rsp+arg_8], rsi
0x1800025ee  push    rdi
0x1800025ef  sub     rsp, 20h
0x1800025f3  xor     esi, esi
0x1800025f5  lea     rbx, [rcx+8]
0x1800025f9  mov     rdi, rcx
0x1800025fc  cmp     [rcx+10h], esi
0x1800025ff  jbe     short loc_180002619
0x180002601  mov     eax, esi
0x180002603  imul    rcx, rax, 0B0h
0x18000260a  add     rcx, [rbx]; struct _SPP_EXTERNAL_GROUP_PROP *
0x18000260d  call    ?Free_SPP_EXTERNAL_GROUP_PROP@@YAXPEAU_SPP_EXTERNAL_GROUP_PROP@@@Z; Free_SPP_EXTERNAL_GROUP_PROP(_SPP_EXTERNAL_GROUP_PROP *)
0x180002612  inc     esi
0x180002614  cmp     esi, [rdi+10h]
0x180002617  jb      short loc_180002601
0x180002619  mov     rcx, [rbx]; pv
0x18000261c  call    cs:__imp_CoTaskMemFree
0x180002622  mov     rsi, [rsp+28h+arg_8]
0x180002627  mov     qword ptr [rbx], 0
0x18000262e  mov     rbx, [rsp+28h+arg_0]
0x180002633  mov     qword ptr [rdi+10h], 0
0x18000263b  add     rsp, 20h
0x18000263f  pop     rdi
0x180002640  retn
```
