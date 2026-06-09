# CPxeProviderHandler::WdsRequestCompletion(_WDSOVERLAPPED *)

- ea: `0x180007060`
- end: `0x1800070c2`
- name: `?WdsRequestCompletion@CPxeProviderHandler@@UEAAXPEAU_WDSOVERLAPPED@@@Z`
- size: `98`
- prototype: `void __fastcall(CPxeProviderHandler *this, struct _WDSOVERLAPPED *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180005aa4`
- `0x180006368`
- `0x180007060`

## import_xrefs

- `WDSSRV!WdsAsyncRecvDone` at `0x1800070a9`
- `WDSSRV!WdsAsyncRecvDone` at `0x1800070a9`

## pseudocode

```c
void __fastcall CPxeProviderHandler::WdsRequestCompletion(CPxeProviderHandler *this, struct _WDSOVERLAPPED *a2)
{
  if ( (unsigned int)CPxeProviderHandler::RecvRequest(
                       this,
                       *((void **)a2 + 17),
                       (struct tagPXE_ADDRESS *)((char *)a2 + 100),
                       (struct tagPXE_ADDRESS *)((char *)a2 + 72),
                       *((PVOID *)a2 + 8),
                       *((_DWORD *)a2 + 14),
                       *((_DWORD *)a2 + 32) + 1) != 997 )
    WdsAsyncRecvDone(*((_QWORD *)a2 + 17), 0);
  PxeRequest::Release(a2);
}

```

## disassembly

```asm
0x180007060  push    rbx
0x180007062  sub     rsp, 40h
0x180007066  mov     eax, [rdx+80h]
0x18000706c  lea     r9, [rdx+48h]; struct tagPXE_ADDRESS *
0x180007070  inc     eax
0x180007072  lea     r8, [rdx+64h]; struct tagPXE_ADDRESS *
0x180007076  mov     [rsp+48h+var_18], eax; unsigned int
0x18000707a  mov     rbx, rdx
0x18000707d  mov     eax, [rdx+38h]
0x180007080  mov     [rsp+48h+var_20], eax; unsigned int
0x180007084  mov     rax, [rdx+40h]
0x180007088  mov     rdx, [rdx+88h]; void *
0x18000708f  mov     [rsp+48h+var_28], rax; void *
0x180007094  call    ?RecvRequest@CPxeProviderHandler@@QEAAKPEAXPEAUtagPXE_ADDRESS@@10KK@Z; CPxeProviderHandler::RecvRequest(void *,tagPXE_ADDRESS *,tagPXE_ADDRESS *,void *,ulong,ulong)
0x180007099  cmp     eax, 3E5h
0x18000709e  jz      short loc_1800070B5
0x1800070a0  mov     rcx, [rbx+88h]
0x1800070a7  xor     edx, edx
0x1800070a9  call    cs:__imp_WdsAsyncRecvDone
0x1800070b0  nop     dword ptr [rax+rax+00h]
0x1800070b5  mov     rcx, rbx; this
0x1800070b8  add     rsp, 40h
0x1800070bc  pop     rbx
0x1800070bd  jmp     ?Release@PxeRequest@@QEAAKXZ; PxeRequest::Release(void)
```
