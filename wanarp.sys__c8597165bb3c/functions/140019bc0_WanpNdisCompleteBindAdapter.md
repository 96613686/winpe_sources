# WanpNdisCompleteBindAdapter

- ea: `0x140019bc0`
- end: `0x140019c40`
- name: `WanpNdisCompleteBindAdapter`
- size: `128`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1400024d0`

## import_xrefs

- `NDIS!NdisCompleteBindAdapterEx` at `0x140019bdc`
- `NDIS!NdisCompleteBindAdapterEx` at `0x140019bdc`

## pseudocode

```c
__int64 __fastcall WanpNdisCompleteBindAdapter(char a1)
{
  NDIS_HANDLE v2; // rcx
  __int64 *v3; // rax
  char *v4; // rax
  char *v5; // rax

  v2 = (NDIS_HANDLE)qword_140009A10;
  if ( !a1 )
    v2 = BindAdapterContext;
  NdisCompleteBindAdapterEx(v2, 0);
  v3 = &qword_140009A10;
  if ( !a1 )
    v3 = (__int64 *)&BindAdapterContext;
  *v3 = 0;
  v4 = &byte_1400099E5;
  if ( !a1 )
    v4 = &byte_140009B05;
  *v4 = 1;
  v5 = &byte_1400099E6;
  if ( !a1 )
    v5 = &byte_140009B06;
  *v5 = 1;
  return WanpReleaseResource(&g_wrBindMutex);
}

```

## disassembly

```asm
0x140019bc0  push    rbx
0x140019bc2  sub     rsp, 20h
0x140019bc6  mov     rbx, rcx
0x140019bc9  mov     rcx, cs:qword_140009A10
0x140019bd0  test    bl, bl
0x140019bd2  cmovz   rcx, cs:BindAdapterContext; BindAdapterContext
0x140019bda  xor     edx, edx; Status
0x140019bdc  call    cs:__imp_NdisCompleteBindAdapterEx
0x140019be3  nop     dword ptr [rax+rax+00h]
0x140019be8  test    bl, bl
0x140019bea  lea     rcx, BindAdapterContext
0x140019bf1  lea     rax, qword_140009A10
0x140019bf8  cmovz   rax, rcx
0x140019bfc  lea     rcx, byte_140009B05
0x140019c03  mov     qword ptr [rax], 0
0x140019c0a  lea     rax, byte_1400099E5
0x140019c11  cmovz   rax, rcx
0x140019c15  lea     rcx, byte_140009B06
0x140019c1c  mov     byte ptr [rax], 1
0x140019c1f  lea     rax, byte_1400099E6
0x140019c26  cmovz   rax, rcx
0x140019c2a  lea     rcx, g_wrBindMutex
0x140019c31  mov     byte ptr [rax], 1
0x140019c34  call    WanpReleaseResource
0x140019c39  add     rsp, 20h
0x140019c3d  pop     rbx
0x140019c3e  retn
```
