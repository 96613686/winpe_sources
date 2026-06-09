# CSxArrayBuilder<_SPP_EXTERNAL_VOLUME_PROP,&Free_SPP_EXTERNAL_VOLUME_PROP(_SPP_EXTERNAL_VOLUME_PROP *),&SxDefaultInit<_SPP_EXTERNAL_VOLUME_PROP>(_SPP_EXTERNAL_VOLUME_PROP *),&SxDefaultTransfer<_SPP_EXTERNAL_VOLUME_PROP>(_SPP_EXTERNAL_VOLUME_PROP *,_SPP_EXTERNAL_VOLUME_PROP *)>::Dispose(void)

- ea: `0x180008118`
- end: `0x180008174`
- name: `?Dispose@?$CSxArrayBuilder@U_SPP_EXTERNAL_VOLUME_PROP@@$1?Free_SPP_EXTERNAL_VOLUME_PROP@@YAXPEAU1@@Z$1??$SxDefaultInit@U_SPP_EXTERNAL_VOLUME_PROP@@@@YAX0@Z$1??$SxDefaultTransfer@U_SPP_EXTERNAL_VOLUME_PROP@@@@YAX00@Z@@QEAAXXZ`
- size: `92`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000df00`
- `0x180011b30`

## callees

- `0x180008118`
- `0x180034998`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000814f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000814f`

## pseudocode

```c
void __fastcall CSxArrayBuilder<_SPP_EXTERNAL_VOLUME_PROP,&void Free_SPP_EXTERNAL_VOLUME_PROP(_SPP_EXTERNAL_VOLUME_PROP *),&void SxDefaultInit<_SPP_EXTERNAL_VOLUME_PROP>(_SPP_EXTERNAL_VOLUME_PROP *),&void SxDefaultTransfer<_SPP_EXTERNAL_VOLUME_PROP>(_SPP_EXTERNAL_VOLUME_PROP *,_SPP_EXTERNAL_VOLUME_PROP *)>::Dispose(
        __int64 a1)
{
  __int64 v1; // rsi
  LPVOID *i; // rbx

  v1 = 0;
  for ( i = (LPVOID *)(a1 + 8); (unsigned int)v1 < *(_DWORD *)(a1 + 16); v1 = (unsigned int)(v1 + 1) )
    Free_SPP_EXTERNAL_VOLUME_PROP((struct _SPP_EXTERNAL_VOLUME_PROP *)((char *)*i + 24 * v1));
  CoTaskMemFree(*i);
  *i = 0;
  *(_QWORD *)(a1 + 16) = 0;
}

```

## disassembly

```asm
0x180008118  mov     [rsp+arg_0], rbx
0x18000811d  mov     [rsp+arg_8], rsi
0x180008122  push    rdi
0x180008123  sub     rsp, 20h
0x180008127  xor     esi, esi
0x180008129  lea     rbx, [rcx+8]
0x18000812d  mov     rdi, rcx
0x180008130  cmp     [rcx+10h], esi
0x180008133  jbe     short loc_18000814C
0x180008135  mov     rax, [rbx]
0x180008138  lea     rcx, [rsi+rsi*2]
0x18000813c  lea     rcx, [rax+rcx*8]; struct _SPP_EXTERNAL_VOLUME_PROP *
0x180008140  call    ?Free_SPP_EXTERNAL_VOLUME_PROP@@YAXPEAU_SPP_EXTERNAL_VOLUME_PROP@@@Z; Free_SPP_EXTERNAL_VOLUME_PROP(_SPP_EXTERNAL_VOLUME_PROP *)
0x180008145  inc     esi
0x180008147  cmp     esi, [rdi+10h]
0x18000814a  jb      short loc_180008135
0x18000814c  mov     rcx, [rbx]; pv
0x18000814f  call    cs:__imp_CoTaskMemFree
0x180008155  mov     rsi, [rsp+28h+arg_8]
0x18000815a  mov     qword ptr [rbx], 0
0x180008161  mov     rbx, [rsp+28h+arg_0]
0x180008166  mov     qword ptr [rdi+10h], 0
0x18000816e  add     rsp, 20h
0x180008172  pop     rdi
0x180008173  retn
```
