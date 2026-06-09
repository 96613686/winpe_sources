# CSxArrayBuilder<_SPP_WRITER_ERROR_INFO,&Free_SPP_BAD_WRITER_INFO(_SPP_WRITER_ERROR_INFO *),&SxDefaultInit<_SPP_WRITER_ERROR_INFO>(_SPP_WRITER_ERROR_INFO *),&SxDefaultTransfer<_SPP_WRITER_ERROR_INFO>(_SPP_WRITER_ERROR_INFO *,_SPP_WRITER_ERROR_INFO *)>::Dispose(void)

- ea: `0x1800081dc`
- end: `0x180008238`
- name: `?Dispose@?$CSxArrayBuilder@U_SPP_WRITER_ERROR_INFO@@$1?Free_SPP_BAD_WRITER_INFO@@YAXPEAU1@@Z$1??$SxDefaultInit@U_SPP_WRITER_ERROR_INFO@@@@YAX0@Z$1??$SxDefaultTransfer@U_SPP_WRITER_ERROR_INFO@@@@YAX00@Z@@QEAAXXZ`
- size: `92`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800028c0`
- `0x18000e000`

## callees

- `0x1800081dc`
- `0x180008d8c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008213`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008213`

## pseudocode

```c
void __fastcall CSxArrayBuilder<_SPP_WRITER_ERROR_INFO,&void Free_SPP_BAD_WRITER_INFO(_SPP_WRITER_ERROR_INFO *),&void SxDefaultInit<_SPP_WRITER_ERROR_INFO>(_SPP_WRITER_ERROR_INFO *),&void SxDefaultTransfer<_SPP_WRITER_ERROR_INFO>(_SPP_WRITER_ERROR_INFO *,_SPP_WRITER_ERROR_INFO *)>::Dispose(
        __int64 a1)
{
  __int64 v1; // rsi
  LPVOID *i; // rbx

  v1 = 0;
  for ( i = (LPVOID *)(a1 + 8); (unsigned int)v1 < *(_DWORD *)(a1 + 16); v1 = (unsigned int)(v1 + 1) )
    Free_SPP_BAD_WRITER_INFO((LPVOID *)*i + 10 * v1);
  CoTaskMemFree(*i);
  *i = 0;
  *(_QWORD *)(a1 + 16) = 0;
}

```

## disassembly

```asm
0x1800081dc  mov     [rsp+arg_0], rbx
0x1800081e1  mov     [rsp+arg_8], rsi
0x1800081e6  push    rdi
0x1800081e7  sub     rsp, 20h
0x1800081eb  xor     esi, esi
0x1800081ed  lea     rbx, [rcx+8]
0x1800081f1  mov     rdi, rcx
0x1800081f4  cmp     [rcx+10h], esi
0x1800081f7  jbe     short loc_180008210
0x1800081f9  lea     rcx, [rsi+rsi*4]
0x1800081fd  shl     rcx, 4
0x180008201  add     rcx, [rbx]; struct _SPP_WRITER_ERROR_INFO *
0x180008204  call    ?Free_SPP_BAD_WRITER_INFO@@YAXPEAU_SPP_WRITER_ERROR_INFO@@@Z; Free_SPP_BAD_WRITER_INFO(_SPP_WRITER_ERROR_INFO *)
0x180008209  inc     esi
0x18000820b  cmp     esi, [rdi+10h]
0x18000820e  jb      short loc_1800081F9
0x180008210  mov     rcx, [rbx]; pv
0x180008213  call    cs:__imp_CoTaskMemFree
0x180008219  mov     rsi, [rsp+28h+arg_8]
0x18000821e  mov     qword ptr [rbx], 0
0x180008225  mov     rbx, [rsp+28h+arg_0]
0x18000822a  mov     qword ptr [rdi+10h], 0
0x180008232  add     rsp, 20h
0x180008236  pop     rdi
0x180008237  retn
```
