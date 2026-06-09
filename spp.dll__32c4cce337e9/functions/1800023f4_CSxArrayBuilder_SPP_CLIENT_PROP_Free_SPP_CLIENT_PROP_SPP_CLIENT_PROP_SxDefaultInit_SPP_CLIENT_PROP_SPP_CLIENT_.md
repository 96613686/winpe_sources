# CSxArrayBuilder<_SPP_CLIENT_PROP,&Free_SPP_CLIENT_PROP(_SPP_CLIENT_PROP *),&SxDefaultInit<_SPP_CLIENT_PROP>(_SPP_CLIENT_PROP *),&SxDefaultTransfer<_SPP_CLIENT_PROP>(_SPP_CLIENT_PROP *,_SPP_CLIENT_PROP *)>::~CSxArrayBuilder<_SPP_CLIENT_PROP,&Free_SPP_CLIENT_PROP(_SPP_CLIENT_PROP *),&SxDefaultInit<_SPP_CLIENT_PROP>(_SPP_CLIENT_PROP *),&SxDefaultTransfer<_SPP_CLIENT_PROP>(_SPP_CLIENT_PROP *,_SPP_CLIENT_PROP *)>(void)

- ea: `0x1800023f4`
- end: `0x180002450`
- name: `??1?$CSxArrayBuilder@U_SPP_CLIENT_PROP@@$1?Free_SPP_CLIENT_PROP@@YAXPEAU1@@Z$1??$SxDefaultInit@U_SPP_CLIENT_PROP@@@@YAX0@Z$1??$SxDefaultTransfer@U_SPP_CLIENT_PROP@@@@YAX00@Z@@AEAA@XZ`
- size: `92`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000dd80`

## callees

- `0x1800023f4`
- `0x1800346c0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000242b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000242b`

## pseudocode

```c
void __fastcall CSxArrayBuilder<_SPP_CLIENT_PROP,&void Free_SPP_CLIENT_PROP(_SPP_CLIENT_PROP *),&void SxDefaultInit<_SPP_CLIENT_PROP>(_SPP_CLIENT_PROP *),&void SxDefaultTransfer<_SPP_CLIENT_PROP>(_SPP_CLIENT_PROP *,_SPP_CLIENT_PROP *)>::~CSxArrayBuilder<_SPP_CLIENT_PROP,&void Free_SPP_CLIENT_PROP(_SPP_CLIENT_PROP *),&void SxDefaultInit<_SPP_CLIENT_PROP>(_SPP_CLIENT_PROP *),&void SxDefaultTransfer<_SPP_CLIENT_PROP>(_SPP_CLIENT_PROP *,_SPP_CLIENT_PROP *)>(
        __int64 a1)
{
  __int64 v1; // rsi
  LPVOID *i; // rbx

  v1 = 0;
  for ( i = (LPVOID *)(a1 + 8); (unsigned int)v1 < *(_DWORD *)(a1 + 16); v1 = (unsigned int)(v1 + 1) )
    Free_SPP_CLIENT_PROP((struct _SPP_CLIENT_PROP *)((char *)*i + 48 * v1));
  CoTaskMemFree(*i);
  *i = 0;
  *(_QWORD *)(a1 + 16) = 0;
}

```

## disassembly

```asm
0x1800023f4  mov     [rsp+arg_0], rbx
0x1800023f9  mov     [rsp+arg_8], rsi
0x1800023fe  push    rdi
0x1800023ff  sub     rsp, 20h
0x180002403  xor     esi, esi
0x180002405  lea     rbx, [rcx+8]
0x180002409  mov     rdi, rcx
0x18000240c  cmp     [rcx+10h], esi
0x18000240f  jbe     short loc_180002428
0x180002411  lea     rcx, [rsi+rsi*2]
0x180002415  shl     rcx, 4
0x180002419  add     rcx, [rbx]; struct _SPP_CLIENT_PROP *
0x18000241c  call    ?Free_SPP_CLIENT_PROP@@YAXPEAU_SPP_CLIENT_PROP@@@Z; Free_SPP_CLIENT_PROP(_SPP_CLIENT_PROP *)
0x180002421  inc     esi
0x180002423  cmp     esi, [rdi+10h]
0x180002426  jb      short loc_180002411
0x180002428  mov     rcx, [rbx]; pv
0x18000242b  call    cs:__imp_CoTaskMemFree
0x180002431  mov     rsi, [rsp+28h+arg_8]
0x180002436  mov     qword ptr [rbx], 0
0x18000243d  mov     rbx, [rsp+28h+arg_0]
0x180002442  mov     qword ptr [rdi+10h], 0
0x18000244a  add     rsp, 20h
0x18000244e  pop     rdi
0x18000244f  retn
```
