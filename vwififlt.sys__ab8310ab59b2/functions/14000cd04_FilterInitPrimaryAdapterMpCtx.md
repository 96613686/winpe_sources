# FilterInitPrimaryAdapterMpCtx

- ea: `0x14000cd04`
- end: `0x14000cd8f`
- name: `FilterInitPrimaryAdapterMpCtx`
- size: `139`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140002c90`

## callees

- `0x140006960`

## import_xrefs

- `NDIS!NdisFDirectOidRequestComplete` at `0x14000cd5e`
- `NDIS!NdisFOidRequestComplete` at `0x14000cd53`
- `NDIS!NdisFIndicateStatus` at `0x14000cd48`
- `NDIS!NdisFSendNetBufferListsComplete` at `0x14000cd3d`
- `NDIS!NdisFIndicateReceiveNetBufferLists` at `0x14000cd32`

## pseudocode

```c
void (__stdcall *__fastcall FilterInitPrimaryAdapterMpCtx(
        __int64 a1))(NDIS_HANDLE NdisFilterHandle, PNDIS_OID_REQUEST OidRequest, NDIS_STATUS Status)
{
  __int64 v1; // rdi
  void (__stdcall *result)(NDIS_HANDLE, PNDIS_OID_REQUEST, NDIS_STATUS); // rax
  __int128 v4; // xmm0

  v1 = *(_QWORD *)(a1 + 3120);
  *(_DWORD *)v1 = 16843009;
  FilterAddRef();
  *(_QWORD *)(v1 + 8) = a1;
  *(_QWORD *)(v1 + 56) = *(_QWORD *)(a1 + 128);
  *(_QWORD *)(v1 + 64) = NdisFIndicateReceiveNetBufferLists;
  *(_QWORD *)(v1 + 72) = NdisFSendNetBufferListsComplete;
  *(_QWORD *)(v1 + 96) = NdisFIndicateStatus;
  *(_QWORD *)(v1 + 80) = NdisFOidRequestComplete;
  result = NdisFDirectOidRequestComplete;
  *(_QWORD *)(v1 + 88) = NdisFDirectOidRequestComplete;
  v4 = *(_OWORD *)(a1 + 2248);
  *(_DWORD *)(v1 + 16) = -1;
  *(_OWORD *)(v1 + 20) = v4;
  *(_DWORD *)(v1 + 104) = 0;
  return result;
}

```

## disassembly

```asm
0x14000cd04  mov     [rsp+arg_0], rbx
0x14000cd09  push    rdi
0x14000cd0a  sub     rsp, 20h
0x14000cd0e  mov     rdi, [rcx+0C30h]
0x14000cd15  mov     rbx, rcx
0x14000cd18  mov     dword ptr [rdi], 1010101h
0x14000cd1e  call    FilterAddRef
0x14000cd23  mov     [rdi+8], rbx
0x14000cd27  mov     rax, [rbx+80h]
0x14000cd2e  mov     [rdi+38h], rax
0x14000cd32  mov     rax, cs:__imp_NdisFIndicateReceiveNetBufferLists
0x14000cd39  mov     [rdi+40h], rax
0x14000cd3d  mov     rax, cs:__imp_NdisFSendNetBufferListsComplete
0x14000cd44  mov     [rdi+48h], rax
0x14000cd48  mov     rax, cs:__imp_NdisFIndicateStatus
0x14000cd4f  mov     [rdi+60h], rax
0x14000cd53  mov     rax, cs:__imp_NdisFOidRequestComplete
0x14000cd5a  mov     [rdi+50h], rax
0x14000cd5e  mov     rax, cs:__imp_NdisFDirectOidRequestComplete
0x14000cd65  mov     [rdi+58h], rax
0x14000cd69  movups  xmm0, xmmword ptr [rbx+8C8h]
0x14000cd70  mov     rbx, [rsp+28h+arg_0]
0x14000cd75  mov     dword ptr [rdi+10h], 0FFFFFFFFh
0x14000cd7c  movdqu  xmmword ptr [rdi+14h], xmm0
0x14000cd81  mov     dword ptr [rdi+68h], 0
0x14000cd88  add     rsp, 20h
0x14000cd8c  pop     rdi
0x14000cd8d  retn
```
