# CSxArrayBuilder<_SPP_COMPONENT_LOCATION,&Free_SPP_COMPONENT_LOCATION(_SPP_COMPONENT_LOCATION *),&SxDefaultInit<_SPP_COMPONENT_LOCATION>(_SPP_COMPONENT_LOCATION *),&SxDefaultTransfer<_SPP_COMPONENT_LOCATION>(_SPP_COMPONENT_LOCATION *,_SPP_COMPONENT_LOCATION *)>::~CSxArrayBuilder<_SPP_COMPONENT_LOCATION,&Free_SPP_COMPONENT_LOCATION(_SPP_COMPONENT_LOCATION *),&SxDefaultInit<_SPP_COMPONENT_LOCATION>(_SPP_COMPONENT_LOCATION *),&SxDefaultTransfer<_SPP_COMPONENT_LOCATION>(_SPP_COMPONENT_LOCATION *,_SPP_COMPONENT_LOCATION *)>(void)

- ea: `0x1800024bc`
- end: `0x180002518`
- name: `??1?$CSxArrayBuilder@U_SPP_COMPONENT_LOCATION@@$1?Free_SPP_COMPONENT_LOCATION@@YAXPEAU1@@Z$1??$SxDefaultInit@U_SPP_COMPONENT_LOCATION@@@@YAX0@Z$1??$SxDefaultTransfer@U_SPP_COMPONENT_LOCATION@@@@YAX00@Z@@AEAA@XZ`
- size: `92`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000de00`

## callees

- `0x1800024bc`
- `0x1800346fc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800024f3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800024f3`

## pseudocode

```c
void __fastcall CSxArrayBuilder<_SPP_COMPONENT_LOCATION,&void Free_SPP_COMPONENT_LOCATION(_SPP_COMPONENT_LOCATION *),&void SxDefaultInit<_SPP_COMPONENT_LOCATION>(_SPP_COMPONENT_LOCATION *),&void SxDefaultTransfer<_SPP_COMPONENT_LOCATION>(_SPP_COMPONENT_LOCATION *,_SPP_COMPONENT_LOCATION *)>::~CSxArrayBuilder<_SPP_COMPONENT_LOCATION,&void Free_SPP_COMPONENT_LOCATION(_SPP_COMPONENT_LOCATION *),&void SxDefaultInit<_SPP_COMPONENT_LOCATION>(_SPP_COMPONENT_LOCATION *),&void SxDefaultTransfer<_SPP_COMPONENT_LOCATION>(_SPP_COMPONENT_LOCATION *,_SPP_COMPONENT_LOCATION *)>(
        __int64 a1)
{
  __int64 v1; // rsi
  LPVOID *i; // rbx

  v1 = 0;
  for ( i = (LPVOID *)(a1 + 8); (unsigned int)v1 < *(_DWORD *)(a1 + 16); v1 = (unsigned int)(v1 + 1) )
    Free_SPP_COMPONENT_LOCATION((struct _SPP_COMPONENT_LOCATION *)((char *)*i + 40 * v1));
  CoTaskMemFree(*i);
  *i = 0;
  *(_QWORD *)(a1 + 16) = 0;
}

```

## disassembly

```asm
0x1800024bc  mov     [rsp+arg_0], rbx
0x1800024c1  mov     [rsp+arg_8], rsi
0x1800024c6  push    rdi
0x1800024c7  sub     rsp, 20h
0x1800024cb  xor     esi, esi
0x1800024cd  lea     rbx, [rcx+8]
0x1800024d1  mov     rdi, rcx
0x1800024d4  cmp     [rcx+10h], esi
0x1800024d7  jbe     short loc_1800024F0
0x1800024d9  mov     rax, [rbx]
0x1800024dc  lea     rcx, [rsi+rsi*4]
0x1800024e0  lea     rcx, [rax+rcx*8]; struct _SPP_COMPONENT_LOCATION *
0x1800024e4  call    ?Free_SPP_COMPONENT_LOCATION@@YAXPEAU_SPP_COMPONENT_LOCATION@@@Z; Free_SPP_COMPONENT_LOCATION(_SPP_COMPONENT_LOCATION *)
0x1800024e9  inc     esi
0x1800024eb  cmp     esi, [rdi+10h]
0x1800024ee  jb      short loc_1800024D9
0x1800024f0  mov     rcx, [rbx]; pv
0x1800024f3  call    cs:__imp_CoTaskMemFree
0x1800024f9  mov     rsi, [rsp+28h+arg_8]
0x1800024fe  mov     qword ptr [rbx], 0
0x180002505  mov     rbx, [rsp+28h+arg_0]
0x18000250a  mov     qword ptr [rdi+10h], 0
0x180002512  add     rsp, 20h
0x180002516  pop     rdi
0x180002517  retn
```
