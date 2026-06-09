# InvalidationThread

- ea: `0x14004c860`
- end: `0x14004ca07`
- name: `InvalidationThread`
- size: `423`
- prototype: `IO_WORKITEM_ROUTINE`
- caller_count: `0`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callees

- `0x140007ec0`
- `0x1400146a4`
- `0x140016cc8`
- `0x1400189b4`
- `0x140029724`
- `0x14004894c`
- `0x14004c670`
- `0x14004c860`

## import_xrefs

- `ntoskrnl!ExAcquireRundownProtection` at `0x14004c95c`
- `ntoskrnl!ExAcquireRundownProtection` at `0x14004c95c`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14004c924`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14004c971`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14004c924`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14004c971`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14004c878`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14004c878`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14004c9f1`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14004c9f1`
- `ntoskrnl!IoFreeWorkItem` at `0x14004c907`
- `ntoskrnl!IoFreeWorkItem` at `0x14004c907`

## pseudocode

```c
void __fastcall InvalidationThread(PDEVICE_OBJECT DeviceObject, char *Context)
{
  __int64 v4; // r8
  __int64 matched; // rax
  _DWORD *v6; // rdi
  int v7; // eax
  int v8; // r8d

  ExAcquirePushLockExclusiveEx(&NodeInfo, 0);
  matched = RfsHashTableBucketLookupMatchEntry(SrvNodeTasksTable, Context + 140, v4, Context + 136);
  v6 = (_DWORD *)matched;
  if ( matched )
  {
    *((_QWORD *)Context + 16) = matched;
    RfsHashTableRemove(SrvNodeTasksTable, matched, matched + 32, 1);
    ExAcquireRundownProtection(&SrvAdminNodeRundown);
    ExReleasePushLockExclusiveEx(&NodeInfo, 0);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_DDD(
        WPP_GLOBAL_Control->AttachedDevice,
        20,
        WPP_65854c2b783f3b66712a66400b9887aa_Traceguids,
        (unsigned int)v6[7],
        v6[8],
        v6[6]);
    }
    v7 = SrvIdSegRequestNodeInvalidation(Context, v6 + 6, (unsigned int)v6[9], Context + 112);
    if ( v7 < 0 )
    {
      *((_DWORD *)Context + 28) = v7;
      InvalidationCompleteThread(DeviceObject, Context, v8);
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_qD(
        WPP_GLOBAL_Control->AttachedDevice,
        19,
        WPP_65854c2b783f3b66712a66400b9887aa_Traceguids,
        Context,
        (unsigned __int8)Context[140]);
    }
    RfsHashTableRemove(SrvNodeActiveTasksTable, Context + 96, Context + 140, 1);
    IoFreeWorkItem(*((PIO_WORKITEM *)Context + 15));
    SrvNetWskNotifyCleanupProviderContext(Context);
    ExReleasePushLockExclusiveEx(&NodeInfo, 0);
  }
  ExReleaseRundownProtection(&SrvAdminNodeRundown);
}

```

## disassembly

```asm
0x14004c860  push    rbx
0x14004c862  push    rbp
0x14004c863  push    rsi
0x14004c864  push    rdi
0x14004c865  sub     rsp, 38h
0x14004c869  mov     rbx, rdx
0x14004c86c  mov     rbp, rcx
0x14004c86f  xor     edx, edx
0x14004c871  lea     rcx, NodeInfo
0x14004c878  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14004c87f  nop     dword ptr [rax+rax+00h]
0x14004c884  mov     rcx, cs:SrvNodeTasksTable
0x14004c88b  lea     rsi, [rbx+8Ch]
0x14004c892  mov     rdx, rsi
0x14004c895  lea     r9, [rbx+88h]
0x14004c89c  call    RfsHashTableBucketLookupMatchEntry
0x14004c8a1  mov     rdi, rax
0x14004c8a4  test    rax, rax
0x14004c8a7  jnz     loc_14004C935
0x14004c8ad  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14004c8b4  lea     rax, WPP_GLOBAL_Control
0x14004c8bb  cmp     rcx, rax
0x14004c8be  jz      short loc_14004C8EA
0x14004c8c0  mov     eax, [rcx+2Ch]
0x14004c8c3  test    al, 20h
0x14004c8c5  jz      short loc_14004C8EA
0x14004c8c7  cmp     byte ptr [rcx+29h], 4
0x14004c8cb  jb      short loc_14004C8EA
0x14004c8cd  movzx   eax, byte ptr [rsi]
0x14004c8d0  lea     edx, [rdi+13h]
0x14004c8d3  mov     rcx, [rcx+18h]
0x14004c8d7  lea     r8, WPP_65854c2b783f3b66712a66400b9887aa_Traceguids
0x14004c8de  mov     r9, rbx
0x14004c8e1  mov     [rsp+58h+var_38], eax
0x14004c8e5  call    WPP_SF_qD
0x14004c8ea  mov     rcx, cs:SrvNodeActiveTasksTable
0x14004c8f1  lea     rdx, [rbx+60h]
0x14004c8f5  mov     r9d, 1
0x14004c8fb  mov     r8, rsi
0x14004c8fe  call    RfsHashTableRemove
0x14004c903  mov     rcx, [rbx+78h]; IoWorkItem
0x14004c907  call    cs:__imp_IoFreeWorkItem
0x14004c90e  nop     dword ptr [rax+rax+00h]
0x14004c913  mov     rcx, rbx
0x14004c916  call    SrvNetWskNotifyCleanupProviderContext
0x14004c91b  xor     edx, edx
0x14004c91d  lea     rcx, NodeInfo
0x14004c924  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14004c92b  nop     dword ptr [rax+rax+00h]
0x14004c930  jmp     loc_14004C9EA
0x14004c935  mov     [rbx+80h], rdi
0x14004c93c  lea     r8, [rax+20h]
0x14004c940  mov     rcx, cs:SrvNodeTasksTable
0x14004c947  mov     r9d, 1
0x14004c94d  mov     rdx, rdi
0x14004c950  call    RfsHashTableRemove
0x14004c955  lea     rcx, SrvAdminNodeRundown; RunRef
0x14004c95c  call    cs:__imp_ExAcquireRundownProtection
0x14004c963  nop     dword ptr [rax+rax+00h]
0x14004c968  xor     edx, edx
0x14004c96a  lea     rcx, NodeInfo
0x14004c971  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14004c978  nop     dword ptr [rax+rax+00h]
0x14004c97d  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14004c984  lea     rax, WPP_GLOBAL_Control
0x14004c98b  cmp     rcx, rax
0x14004c98e  jz      short loc_14004C9C4
0x14004c990  mov     eax, [rcx+2Ch]
0x14004c993  test    al, 20h
0x14004c995  jz      short loc_14004C9C4
0x14004c997  cmp     byte ptr [rcx+29h], 4
0x14004c99b  jb      short loc_14004C9C4
0x14004c99d  mov     eax, [rdi+18h]
0x14004c9a0  lea     r8, WPP_65854c2b783f3b66712a66400b9887aa_Traceguids
0x14004c9a7  mov     r9d, [rdi+1Ch]
0x14004c9ab  mov     edx, 14h
0x14004c9b0  mov     rcx, [rcx+18h]
0x14004c9b4  mov     [rsp+58h+var_30], eax
0x14004c9b8  mov     eax, [rdi+20h]
0x14004c9bb  mov     [rsp+58h+var_38], eax
0x14004c9bf  call    WPP_SF_DDD
0x14004c9c4  mov     r8d, [rdi+24h]
0x14004c9c8  lea     rdx, [rdi+18h]
0x14004c9cc  lea     r9, [rbx+70h]
0x14004c9d0  mov     rcx, rbx
0x14004c9d3  call    SrvIdSegRequestNodeInvalidation
0x14004c9d8  test    eax, eax
0x14004c9da  jns     short loc_14004C9EA
0x14004c9dc  mov     rdx, rbx; Context
0x14004c9df  mov     [rbx+70h], eax
0x14004c9e2  mov     rcx, rbp; DeviceObject
0x14004c9e5  call    InvalidationCompleteThread
0x14004c9ea  lea     rcx, SrvAdminNodeRundown; RunRef
0x14004c9f1  call    cs:__imp_ExReleaseRundownProtection
0x14004c9f8  nop     dword ptr [rax+rax+00h]
0x14004c9fd  add     rsp, 38h
0x14004ca01  pop     rdi
0x14004ca02  pop     rsi
0x14004ca03  pop     rbp
0x14004ca04  pop     rbx
0x14004ca05  retn
```
