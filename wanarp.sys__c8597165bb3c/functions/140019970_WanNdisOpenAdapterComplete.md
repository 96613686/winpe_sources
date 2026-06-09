# WanNdisOpenAdapterComplete

- ea: `0x140019970`
- end: `0x140019afa`
- name: `WanNdisOpenAdapterComplete`
- size: `394`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140002350`

## callees

- `0x140002d70`
- `0x140019970`
- `0x140019b00`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140019a24`
- `ntoskrnl!ExAllocatePool2` at `0x140019a24`
- `ntoskrnl!ExQueueWorkItem` at `0x140019aa0`
- `ntoskrnl!ExQueueWorkItem` at `0x140019aa0`
- `NDIS!NdisCompleteBindAdapterEx` at `0x1400199ce`
- `NDIS!NdisCompleteBindAdapterEx` at `0x1400199ce`

## pseudocode

```c
void __fastcall WanNdisOpenAdapterComplete(__int64 a1, NDIS_STATUS a2)
{
  int *v2; // rbx
  unsigned __int8 v3; // si
  NDIS_HANDLE v5; // rcx
  __int64 v6; // rdx
  __int64 *v7; // rax
  __int64 OidRequest; // rax
  int *v9; // rax
  int *v10; // rax
  struct _WORK_QUEUE_ITEM *v11; // rcx
  int v12; // [rsp+40h] [rbp-18h] BYREF
  __int16 v13; // [rsp+44h] [rbp-14h]
  int v14; // [rsp+48h] [rbp-10h] BYREF
  __int16 v15; // [rsp+4Ch] [rbp-Ch]

  v14 = 128;
  v2 = &v12;
  v15 = 8;
  v12 = 128;
  v3 = a1 == 212578788;
  v13 = -8826;
  if ( a1 == 212578788 )
    v2 = &v14;
  if ( a2 )
  {
    v5 = (NDIS_HANDLE)qword_140009A10;
    if ( a1 != 212578788 )
      v5 = BindAdapterContext;
    NdisCompleteBindAdapterEx(v5, a2);
    v7 = &qword_140009A10;
    if ( a1 != 212578788 )
      v7 = (__int64 *)&BindAdapterContext;
    *v7 = 0;
    WanpFreeBindResourcesAndReleaseLock(v3, v6);
  }
  else
  {
    OidRequest = ExAllocatePool2(64, 264, 1919971927);
    if ( OidRequest )
    {
      *(_DWORD *)(OidRequest + 256) = *v2;
      *(_WORD *)(OidRequest + 260) = *((_WORD *)v2 + 2);
      WanpDoNdisRequest(
        OidRequest,
        67174660,
        OidRequest + 256,
        6,
        (PNDIS_OID_REQUEST)OidRequest,
        (__int64)&WanpSetProtocolTypeComplete,
        v3);
    }
    else
    {
      v9 = &dword_140009A24;
      if ( a1 != 212578788 )
        v9 = &dword_140009B44;
      *v9 = -1073741670;
      v10 = &dword_140009A20;
      if ( a1 != 212578788 )
        v10 = &Status;
      v11 = (struct _WORK_QUEUE_ITEM *)qword_140009A50;
      *v10 = -1073741670;
      if ( a1 != 212578788 )
        v11 = &stru_140009B70;
      v11->WorkerRoutine = (PWORKER_THREAD_ROUTINE)WanpCloseNdisWan;
      v11->Parameter = (PVOID)v3;
      v11->List.Flink = 0;
      ExQueueWorkItem(v11, DelayedWorkQueue);
    }
  }
}

```

## disassembly

```asm
0x140019970  mov     rax, rsp
0x140019973  mov     [rax+8], rbx
0x140019977  mov     [rax+18h], rsi
0x14001997b  push    rdi
0x14001997c  sub     rsp, 50h
0x140019980  cmp     rcx, 0CABB1E4h
0x140019987  mov     dword ptr [rax-10h], 80h
0x14001998e  lea     rbx, [rax-18h]
0x140019992  mov     word ptr [rax-0Ch], 8
0x140019998  mov     dword ptr [rax-18h], 80h
0x14001999f  setz    sil
0x1400199a3  mov     word ptr [rax-14h], 0DD86h
0x1400199a9  lea     rax, [rax-10h]
0x1400199ad  cmovz   rbx, rax
0x1400199b1  mov     rdi, rcx
0x1400199b4  test    edx, edx
0x1400199b6  jz      short loc_140019A14
0x1400199b8  mov     rcx, cs:qword_140009A10
0x1400199bf  cmp     rdi, 0CABB1E4h
0x1400199c6  cmovnz  rcx, cs:BindAdapterContext; BindAdapterContext
0x1400199ce  call    cs:__imp_NdisCompleteBindAdapterEx
0x1400199d5  nop     dword ptr [rax+rax+00h]
0x1400199da  lea     rcx, BindAdapterContext
0x1400199e1  cmp     rdi, 0CABB1E4h
0x1400199e8  lea     rax, qword_140009A10
0x1400199ef  cmovnz  rax, rcx
0x1400199f3  movzx   ecx, sil
0x1400199f7  mov     qword ptr [rax], 0
0x1400199fe  call    WanpFreeBindResourcesAndReleaseLock
0x140019a03  mov     rbx, [rsp+58h+arg_0]
0x140019a08  mov     rsi, [rsp+58h+arg_10]
0x140019a0d  add     rsp, 50h
0x140019a11  pop     rdi
0x140019a12  retn
0x140019a14  mov     edx, 108h
0x140019a19  mov     ecx, 40h ; '@'
0x140019a1e  mov     r8d, 72707257h
0x140019a24  call    cs:__imp_ExAllocatePool2
0x140019a2b  nop     dword ptr [rax+rax+00h]
0x140019a30  mov     rcx, rax; int
0x140019a33  test    rax, rax
0x140019a36  jnz     short loc_140019AAE
0x140019a38  cmp     rdi, 0CABB1E4h
0x140019a3f  lea     rcx, dword_140009B44
0x140019a46  lea     rax, dword_140009A24
0x140019a4d  mov     edx, 1; QueueType
0x140019a52  cmovnz  rax, rcx
0x140019a56  lea     rcx, Status
0x140019a5d  mov     dword ptr [rax], 0C000009Ah
0x140019a63  lea     rax, dword_140009A20
0x140019a6a  cmovnz  rax, rcx
0x140019a6e  lea     rcx, qword_140009A50
0x140019a75  mov     dword ptr [rax], 0C000009Ah
0x140019a7b  lea     rax, stru_140009B70
0x140019a82  cmovnz  rcx, rax; WorkItem
0x140019a86  lea     rax, WanpCloseNdisWan
0x140019a8d  mov     [rcx+10h], rax
0x140019a91  movzx   eax, sil
0x140019a95  mov     [rcx+18h], rax
0x140019a99  mov     qword ptr [rcx], 0
0x140019aa0  call    cs:__imp_ExQueueWorkItem
0x140019aa7  nop     dword ptr [rax+rax+00h]
0x140019aac  jmp     short loc_140019AE9
0x140019aae  lea     r8, [rax+100h]; int
0x140019ab5  mov     [rsp+58h+var_28], sil; char
0x140019aba  mov     eax, [rbx]
0x140019abc  mov     edx, 4010104h; int
0x140019ac1  mov     [r8], eax
0x140019ac4  mov     r9d, 6; int
0x140019aca  movzx   eax, word ptr [rbx+4]
0x140019ace  mov     [r8+4], ax
0x140019ad3  lea     rax, WanpSetProtocolTypeComplete
0x140019ada  mov     [rsp+58h+var_30], rax; __int64
0x140019adf  mov     [rsp+58h+OidRequest], rcx; OidRequest
0x140019ae4  call    WanpDoNdisRequest
0x140019ae9  mov     rbx, [rsp+58h+arg_0]
0x140019aee  mov     rsi, [rsp+58h+arg_10]
0x140019af3  add     rsp, 50h
0x140019af7  pop     rdi
0x140019af8  retn
```
