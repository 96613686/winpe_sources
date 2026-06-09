# WanpDeinitializeNdis

- ea: `0x140017738`
- end: `0x140017824`
- name: `WanpDeinitializeNdis`
- size: `236`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140004680`

## callees

- `0x1400024d0`
- `0x140002b6c`
- `0x140017738`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x1400177d4`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400177d4`
- `NDIS!NdisDeregisterProtocolDriver` at `0x14001779e`
- `NDIS!NdisDeregisterProtocolDriver` at `0x14001779e`

## pseudocode

```c
__int64 __fastcall WanpDeinitializeNdis(char a1)
{
  NDIS_HANDLE v2; // rdi
  char *v3; // rax
  NDIS_HANDLE v4; // rsi
  __int64 *v5; // rcx
  __int64 *v6; // rax

  WanpAcquireResource(&g_wrBindMutex);
  v2 = (NDIS_HANDLE)qword_140009160;
  v3 = &byte_1400099E6;
  if ( !a1 )
  {
    v2 = NdisProtocolHandle;
    v3 = &byte_140009B06;
  }
  *v3 = 0;
  v4 = (NDIS_HANDLE)qword_1400099E8;
  if ( !a1 )
    v4 = NdisBindingHandle;
  WanpReleaseResource(&g_wrBindMutex);
  if ( v2 )
    NdisDeregisterProtocolDriver(v2);
  if ( v4 )
  {
    v5 = qword_140009AB8;
    if ( !a1 )
      v5 = (__int64 *)&stru_140009BD8;
    KeWaitForSingleObject(v5, Executive, 0, 0, 0);
  }
  WanpAcquireResource(&g_wrBindMutex);
  v6 = &qword_140009160;
  if ( !a1 )
    v6 = (__int64 *)&NdisProtocolHandle;
  *v6 = 0;
  return WanpReleaseResource(&g_wrBindMutex);
}

```

## disassembly

```asm
0x140017738  mov     [rsp+arg_0], rbx
0x14001773d  mov     [rsp+arg_8], rsi
0x140017742  push    rdi
0x140017743  sub     rsp, 30h
0x140017747  mov     bl, cl
0x140017749  lea     rcx, g_wrBindMutex
0x140017750  call    WanpAcquireResource
0x140017755  mov     rdi, cs:qword_140009160
0x14001775c  lea     rcx, byte_140009B06
0x140017763  test    bl, bl
0x140017765  lea     rax, byte_1400099E6
0x14001776c  cmovz   rdi, cs:NdisProtocolHandle
0x140017774  cmovz   rax, rcx
0x140017778  lea     rcx, g_wrBindMutex
0x14001777f  mov     byte ptr [rax], 0
0x140017782  mov     rsi, cs:qword_1400099E8
0x140017789  cmovz   rsi, cs:NdisBindingHandle
0x140017791  call    WanpReleaseResource
0x140017796  test    rdi, rdi
0x140017799  jz      short loc_1400177AA
0x14001779b  mov     rcx, rdi; NdisProtocolHandle
0x14001779e  call    cs:__imp_NdisDeregisterProtocolDriver
0x1400177a5  nop     dword ptr [rax+rax+00h]
0x1400177aa  test    rsi, rsi
0x1400177ad  jz      short loc_1400177E0
0x1400177af  test    bl, bl
0x1400177b1  mov     [rsp+38h+Timeout], 0; Timeout
0x1400177ba  lea     rax, stru_140009BD8
0x1400177c1  lea     rcx, qword_140009AB8
0x1400177c8  cmovz   rcx, rax; Object
0x1400177cc  xor     r9d, r9d; Alertable
0x1400177cf  xor     r8d, r8d; WaitMode
0x1400177d2  xor     edx, edx; WaitReason
0x1400177d4  call    cs:__imp_KeWaitForSingleObject
0x1400177db  nop     dword ptr [rax+rax+00h]
0x1400177e0  lea     rcx, g_wrBindMutex
0x1400177e7  call    WanpAcquireResource
0x1400177ec  test    bl, bl
0x1400177ee  lea     rdx, NdisProtocolHandle
0x1400177f5  lea     rax, qword_140009160
0x1400177fc  cmovz   rax, rdx
0x140017800  lea     rcx, g_wrBindMutex
0x140017807  mov     qword ptr [rax], 0
0x14001780e  call    WanpReleaseResource
0x140017813  mov     rbx, [rsp+38h+arg_0]
0x140017818  mov     rsi, [rsp+38h+arg_8]
0x14001781d  add     rsp, 30h
0x140017821  pop     rdi
0x140017822  retn
```
