# CSxArrayBuilder<_SPP_VOLUME_PROP,&Free_SPP_VOLUME_PROP(_SPP_VOLUME_PROP *),&SxDefaultInit<_SPP_VOLUME_PROP>(_SPP_VOLUME_PROP *),&SxDefaultTransfer<_SPP_VOLUME_PROP>(_SPP_VOLUME_PROP *,_SPP_VOLUME_PROP *)>::Dispose(void)

- ea: `0x18000817c`
- end: `0x1800081d6`
- name: `?Dispose@?$CSxArrayBuilder@U_SPP_VOLUME_PROP@@$1?Free_SPP_VOLUME_PROP@@YAXPEAU1@@Z$1??$SxDefaultInit@U_SPP_VOLUME_PROP@@@@YAX0@Z$1??$SxDefaultTransfer@U_SPP_VOLUME_PROP@@@@YAX00@Z@@QEAAXXZ`
- size: `90`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000dfc0`
- `0x18001ed44`

## callees

- `0x18000817c`
- `0x180034b88`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800081b1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800081b1`

## pseudocode

```c
void __fastcall CSxArrayBuilder<_SPP_VOLUME_PROP,&void Free_SPP_VOLUME_PROP(_SPP_VOLUME_PROP *),&void SxDefaultInit<_SPP_VOLUME_PROP>(_SPP_VOLUME_PROP *),&void SxDefaultTransfer<_SPP_VOLUME_PROP>(_SPP_VOLUME_PROP *,_SPP_VOLUME_PROP *)>::Dispose(
        __int64 a1)
{
  unsigned int v1; // esi
  LPVOID *i; // rbx

  v1 = 0;
  for ( i = (LPVOID *)(a1 + 8); v1 < *(_DWORD *)(a1 + 16); ++v1 )
    Free_SPP_VOLUME_PROP((struct _SPP_VOLUME_PROP *)((char *)*i + 56 * v1));
  CoTaskMemFree(*i);
  *i = 0;
  *(_QWORD *)(a1 + 16) = 0;
}

```

## disassembly

```asm
0x18000817c  mov     [rsp+arg_0], rbx
0x180008181  mov     [rsp+arg_8], rsi
0x180008186  push    rdi
0x180008187  sub     rsp, 20h
0x18000818b  xor     esi, esi
0x18000818d  lea     rbx, [rcx+8]
0x180008191  mov     rdi, rcx
0x180008194  cmp     [rcx+10h], esi
0x180008197  jbe     short loc_1800081AE
0x180008199  mov     eax, esi
0x18000819b  imul    rcx, rax, 38h ; '8'
0x18000819f  add     rcx, [rbx]; struct _SPP_VOLUME_PROP *
0x1800081a2  call    ?Free_SPP_VOLUME_PROP@@YAXPEAU_SPP_VOLUME_PROP@@@Z; Free_SPP_VOLUME_PROP(_SPP_VOLUME_PROP *)
0x1800081a7  inc     esi
0x1800081a9  cmp     esi, [rdi+10h]
0x1800081ac  jb      short loc_180008199
0x1800081ae  mov     rcx, [rbx]; pv
0x1800081b1  call    cs:__imp_CoTaskMemFree
0x1800081b7  mov     rsi, [rsp+28h+arg_8]
0x1800081bc  mov     qword ptr [rbx], 0
0x1800081c3  mov     rbx, [rsp+28h+arg_0]
0x1800081c8  mov     qword ptr [rdi+10h], 0
0x1800081d0  add     rsp, 20h
0x1800081d4  pop     rdi
0x1800081d5  retn
```
