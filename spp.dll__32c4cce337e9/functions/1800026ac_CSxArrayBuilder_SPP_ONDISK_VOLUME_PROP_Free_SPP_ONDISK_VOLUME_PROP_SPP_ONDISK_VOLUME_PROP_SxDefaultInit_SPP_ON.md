# CSxArrayBuilder<_SPP_ONDISK_VOLUME_PROP,&Free_SPP_ONDISK_VOLUME_PROP(_SPP_ONDISK_VOLUME_PROP *),&SxDefaultInit<_SPP_ONDISK_VOLUME_PROP>(_SPP_ONDISK_VOLUME_PROP *),&SxDefaultTransfer<_SPP_ONDISK_VOLUME_PROP>(_SPP_ONDISK_VOLUME_PROP *,_SPP_ONDISK_VOLUME_PROP *)>::~CSxArrayBuilder<_SPP_ONDISK_VOLUME_PROP,&Free_SPP_ONDISK_VOLUME_PROP(_SPP_ONDISK_VOLUME_PROP *),&SxDefaultInit<_SPP_ONDISK_VOLUME_PROP>(_SPP_ONDISK_VOLUME_PROP *),&SxDefaultTransfer<_SPP_ONDISK_VOLUME_PROP>(_SPP_ONDISK_VOLUME_PROP *,_SPP_ONDISK_VOLUME_PROP *)>(void)

- ea: `0x1800026ac`
- end: `0x180002708`
- name: `??1?$CSxArrayBuilder@U_SPP_ONDISK_VOLUME_PROP@@$1?Free_SPP_ONDISK_VOLUME_PROP@@YAXPEAU1@@Z$1??$SxDefaultInit@U_SPP_ONDISK_VOLUME_PROP@@@@YAX0@Z$1??$SxDefaultTransfer@U_SPP_ONDISK_VOLUME_PROP@@@@YAX00@Z@@AEAA@XZ`
- size: `92`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000df80`

## callees

- `0x1800026ac`
- `0x180008ffc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800026e3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800026e3`

## pseudocode

```c
void __fastcall CSxArrayBuilder<_SPP_ONDISK_VOLUME_PROP,&void Free_SPP_ONDISK_VOLUME_PROP(_SPP_ONDISK_VOLUME_PROP *),&void SxDefaultInit<_SPP_ONDISK_VOLUME_PROP>(_SPP_ONDISK_VOLUME_PROP *),&void SxDefaultTransfer<_SPP_ONDISK_VOLUME_PROP>(_SPP_ONDISK_VOLUME_PROP *,_SPP_ONDISK_VOLUME_PROP *)>::~CSxArrayBuilder<_SPP_ONDISK_VOLUME_PROP,&void Free_SPP_ONDISK_VOLUME_PROP(_SPP_ONDISK_VOLUME_PROP *),&void SxDefaultInit<_SPP_ONDISK_VOLUME_PROP>(_SPP_ONDISK_VOLUME_PROP *),&void SxDefaultTransfer<_SPP_ONDISK_VOLUME_PROP>(_SPP_ONDISK_VOLUME_PROP *,_SPP_ONDISK_VOLUME_PROP *)>(
        __int64 a1)
{
  __int64 v1; // rsi
  LPVOID *i; // rbx

  v1 = 0;
  for ( i = (LPVOID *)(a1 + 8); (unsigned int)v1 < *(_DWORD *)(a1 + 16); v1 = (unsigned int)(v1 + 1) )
    Free_SPP_ONDISK_VOLUME_PROP((LPVOID *)*i + 6 * v1);
  CoTaskMemFree(*i);
  *i = 0;
  *(_QWORD *)(a1 + 16) = 0;
}

```

## disassembly

```asm
0x1800026ac  mov     [rsp+arg_0], rbx
0x1800026b1  mov     [rsp+arg_8], rsi
0x1800026b6  push    rdi
0x1800026b7  sub     rsp, 20h
0x1800026bb  xor     esi, esi
0x1800026bd  lea     rbx, [rcx+8]
0x1800026c1  mov     rdi, rcx
0x1800026c4  cmp     [rcx+10h], esi
0x1800026c7  jbe     short loc_1800026E0
0x1800026c9  lea     rcx, [rsi+rsi*2]
0x1800026cd  shl     rcx, 4
0x1800026d1  add     rcx, [rbx]; struct _SPP_ONDISK_VOLUME_PROP *
0x1800026d4  call    ?Free_SPP_ONDISK_VOLUME_PROP@@YAXPEAU_SPP_ONDISK_VOLUME_PROP@@@Z; Free_SPP_ONDISK_VOLUME_PROP(_SPP_ONDISK_VOLUME_PROP *)
0x1800026d9  inc     esi
0x1800026db  cmp     esi, [rdi+10h]
0x1800026de  jb      short loc_1800026C9
0x1800026e0  mov     rcx, [rbx]; pv
0x1800026e3  call    cs:__imp_CoTaskMemFree
0x1800026e9  mov     rsi, [rsp+28h+arg_8]
0x1800026ee  mov     qword ptr [rbx], 0
0x1800026f5  mov     rbx, [rsp+28h+arg_0]
0x1800026fa  mov     qword ptr [rdi+10h], 0
0x180002702  add     rsp, 20h
0x180002706  pop     rdi
0x180002707  retn
```
