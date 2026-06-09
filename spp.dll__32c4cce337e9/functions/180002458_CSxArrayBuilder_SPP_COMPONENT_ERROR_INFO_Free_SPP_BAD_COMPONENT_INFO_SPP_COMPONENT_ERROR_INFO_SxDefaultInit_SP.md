# CSxArrayBuilder<_SPP_COMPONENT_ERROR_INFO,&Free_SPP_BAD_COMPONENT_INFO(_SPP_COMPONENT_ERROR_INFO *),&SxDefaultInit<_SPP_COMPONENT_ERROR_INFO>(_SPP_COMPONENT_ERROR_INFO *),&SxDefaultTransfer<_SPP_COMPONENT_ERROR_INFO>(_SPP_COMPONENT_ERROR_INFO *,_SPP_COMPONENT_ERROR_INFO *)>::~CSxArrayBuilder<_SPP_COMPONENT_ERROR_INFO,&Free_SPP_BAD_COMPONENT_INFO(_SPP_COMPONENT_ERROR_INFO *),&SxDefaultInit<_SPP_COMPONENT_ERROR_INFO>(_SPP_COMPONENT_ERROR_INFO *),&SxDefaultTransfer<_SPP_COMPONENT_ERROR_INFO>(_SPP_COMPONENT_ERROR_INFO *,_SPP_COMPONENT_ERROR_INFO *)>(void)

- ea: `0x180002458`
- end: `0x1800024b4`
- name: `??1?$CSxArrayBuilder@U_SPP_COMPONENT_ERROR_INFO@@$1?Free_SPP_BAD_COMPONENT_INFO@@YAXPEAU1@@Z$1??$SxDefaultInit@U_SPP_COMPONENT_ERROR_INFO@@@@YAX0@Z$1??$SxDefaultTransfer@U_SPP_COMPONENT_ERROR_INFO@@@@YAX00@Z@@AEAA@XZ`
- size: `92`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000ddc0`

## callees

- `0x180002458`
- `0x180008d3c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000248f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000248f`

## pseudocode

```c
void __fastcall CSxArrayBuilder<_SPP_COMPONENT_ERROR_INFO,&void Free_SPP_BAD_COMPONENT_INFO(_SPP_COMPONENT_ERROR_INFO *),&void SxDefaultInit<_SPP_COMPONENT_ERROR_INFO>(_SPP_COMPONENT_ERROR_INFO *),&void SxDefaultTransfer<_SPP_COMPONENT_ERROR_INFO>(_SPP_COMPONENT_ERROR_INFO *,_SPP_COMPONENT_ERROR_INFO *)>::~CSxArrayBuilder<_SPP_COMPONENT_ERROR_INFO,&void Free_SPP_BAD_COMPONENT_INFO(_SPP_COMPONENT_ERROR_INFO *),&void SxDefaultInit<_SPP_COMPONENT_ERROR_INFO>(_SPP_COMPONENT_ERROR_INFO *),&void SxDefaultTransfer<_SPP_COMPONENT_ERROR_INFO>(_SPP_COMPONENT_ERROR_INFO *,_SPP_COMPONENT_ERROR_INFO *)>(
        __int64 a1)
{
  __int64 v1; // rsi
  LPVOID *i; // rbx

  v1 = 0;
  for ( i = (LPVOID *)(a1 + 8); (unsigned int)v1 < *(_DWORD *)(a1 + 16); v1 = (unsigned int)(v1 + 1) )
    Free_SPP_BAD_COMPONENT_INFO((struct _SPP_COMPONENT_ERROR_INFO *)((char *)*i + 40 * v1));
  CoTaskMemFree(*i);
  *i = 0;
  *(_QWORD *)(a1 + 16) = 0;
}

```

## disassembly

```asm
0x180002458  mov     [rsp+arg_0], rbx
0x18000245d  mov     [rsp+arg_8], rsi
0x180002462  push    rdi
0x180002463  sub     rsp, 20h
0x180002467  xor     esi, esi
0x180002469  lea     rbx, [rcx+8]
0x18000246d  mov     rdi, rcx
0x180002470  cmp     [rcx+10h], esi
0x180002473  jbe     short loc_18000248C
0x180002475  mov     rax, [rbx]
0x180002478  lea     rcx, [rsi+rsi*4]
0x18000247c  lea     rcx, [rax+rcx*8]; struct _SPP_COMPONENT_ERROR_INFO *
0x180002480  call    ?Free_SPP_BAD_COMPONENT_INFO@@YAXPEAU_SPP_COMPONENT_ERROR_INFO@@@Z; Free_SPP_BAD_COMPONENT_INFO(_SPP_COMPONENT_ERROR_INFO *)
0x180002485  inc     esi
0x180002487  cmp     esi, [rdi+10h]
0x18000248a  jb      short loc_180002475
0x18000248c  mov     rcx, [rbx]; pv
0x18000248f  call    cs:__imp_CoTaskMemFree
0x180002495  mov     rsi, [rsp+28h+arg_8]
0x18000249a  mov     qword ptr [rbx], 0
0x1800024a1  mov     rbx, [rsp+28h+arg_0]
0x1800024a6  mov     qword ptr [rdi+10h], 0
0x1800024ae  add     rsp, 20h
0x1800024b2  pop     rdi
0x1800024b3  retn
```
