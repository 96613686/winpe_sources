# InvalidationCompleteThread

- ea: `0x14004c670`
- end: `0x14004c855`
- name: `InvalidationCompleteThread`
- size: `485`
- prototype: `IO_WORKITEM_ROUTINE`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x14004c860`

## callees

- `0x140007ec0`
- `0x1400146a4`
- `0x140016cc8`
- `0x140024100`
- `0x1400241ac`
- `0x140029724`
- `0x14004c538`
- `0x14004c670`
- `0x14004ca10`

## import_xrefs

- `ntoskrnl!ExAcquireRundownProtection` at `0x14004c75d`
- `ntoskrnl!ExAcquireRundownProtection` at `0x14004c75d`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14004c772`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14004c818`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14004c772`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14004c818`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14004c720`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14004c720`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14004c83f`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14004c83f`
- `ntoskrnl!IoQueueWorkItem` at `0x14004c78f`
- `ntoskrnl!IoQueueWorkItem` at `0x14004c78f`
- `ntoskrnl!IoFreeWorkItem` at `0x14004c7fb`
- `ntoskrnl!IoFreeWorkItem` at `0x14004c7fb`

## pseudocode

```c
void __fastcall InvalidationCompleteThread(PDEVICE_OBJECT DeviceObject, char *Context, int a3)
{
  _DWORD *v3; // rdi
  __int64 v4; // rsi
  unsigned int i; // ebp
  __int64 v7; // r8

  v3 = (_DWORD *)*((_QWORD *)Context + 16);
  v4 = 0;
  for ( i = *((_DWORD *)Context + 28); (unsigned int)v4 < v3[7]; v4 = (unsigned int)(v4 + 1) )
  {
    if ( v3[6] == 1 )
    {
      if ( (WPP_MAIN_CB.Queue.Wcb.NumberOfChannels & 0x1000) != 0 )
        McTemplateK0idddd_EtwWriteTransfer(
          0,
          (_DWORD)Context,
          a3,
          *(_QWORD *)&v3[22 * (unsigned int)v4 + 12],
          v3[22 * (unsigned int)v4 + 15],
          v3[22 * (unsigned int)v4 + 15],
          i,
          i);
    }
    else if ( v3[6] == 2 && (WPP_MAIN_CB.Queue.Wcb.NumberOfChannels & 0x1000) != 0 )
    {
      McTemplateK0jdddd_EtwWriteTransfer(
        1,
        v3[5 * v4 + 15],
        a3,
        (_DWORD)v3 + 4 * (v4 + 11 + 4 * v4),
        v3[5 * v4 + 15],
        v3[5 * v4 + 15],
        i,
        i);
    }
  }
  if ( (int)v3[10] < 0 || *((int *)Context + 28) < 0 )
  {
    InvalidationCompleteAll(Context);
  }
  else
  {
    ExAcquirePushLockExclusiveEx(&NodeInfo, 0);
    if ( RfsHashTableBucketLookupMatchEntry(SrvNodeTasksTable, v3 + 8, v7, Context + 136) )
    {
      *((_QWORD *)Context + 16) = 0;
      ExAcquireRundownProtection(&SrvAdminNodeRundown);
      ExReleasePushLockExclusiveEx(&NodeInfo, 0);
      IoQueueWorkItem(*((PIO_WORKITEM *)Context + 15), InvalidationThread, CriticalWorkQueue, Context);
    }
    else
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_qD(
          WPP_GLOBAL_Control->AttachedDevice,
          21,
          WPP_65854c2b783f3b66712a66400b9887aa_Traceguids,
          Context,
          v3[8]);
      }
      RfsHashTableRemove(SrvNodeActiveTasksTable, Context + 96, v3 + 8, 1);
      IoFreeWorkItem(*((PIO_WORKITEM *)Context + 15));
      SrvNetWskNotifyCleanupProviderContext(Context);
      ExReleasePushLockExclusiveEx(&NodeInfo, 0);
    }
    ReplyToRequestor(v3, i);
  }
  ExReleaseRundownProtection(&SrvAdminNodeRundown);
}

```

## disassembly

```asm
0x14004c670  push    rbx
0x14004c672  push    rbp
0x14004c673  push    rsi
0x14004c674  push    rdi
0x14004c675  sub     rsp, 48h
0x14004c679  mov     rdi, [rdx+80h]
0x14004c680  xor     esi, esi
0x14004c682  mov     ebp, [rdx+70h]
0x14004c685  mov     rbx, rdx
0x14004c688  cmp     [rdi+1Ch], esi
0x14004c68b  jbe     short loc_14004C703
0x14004c68d  mov     ecx, [rdi+18h]
0x14004c690  sub     ecx, 1
0x14004c693  jz      short loc_14004C6CE
0x14004c695  cmp     ecx, 1
0x14004c698  jnz     short loc_14004C6FC
0x14004c69a  test    byte ptr cs:WPP_MAIN_CB.Queue+11h, 10h
0x14004c6a1  jz      short loc_14004C6FC
0x14004c6a3  mov     [rsp+68h+var_30], ebp
0x14004c6a7  lea     rax, [rsi+rsi*4]
0x14004c6ab  mov     edx, [rdi+rax*4+3Ch]
0x14004c6af  lea     rax, [rsi+0Bh]
0x14004c6b3  lea     rax, [rax+rsi*4]
0x14004c6b7  mov     [rsp+68h+var_38], ebp
0x14004c6bb  mov     [rsp+68h+var_40], edx
0x14004c6bf  lea     r9, [rdi+rax*4]
0x14004c6c3  mov     [rsp+68h+var_48], edx
0x14004c6c7  call    McTemplateK0jdddd_EtwWriteTransfer
0x14004c6cc  jmp     short loc_14004C6FC
0x14004c6ce  test    byte ptr cs:WPP_MAIN_CB.Queue+11h, 10h
0x14004c6d5  jz      short loc_14004C6FC
0x14004c6d7  mov     eax, esi
0x14004c6d9  imul    r9, rax, 58h ; 'X'
0x14004c6dd  mov     [rsp+68h+var_30], ebp
0x14004c6e1  mov     [rsp+68h+var_38], ebp
0x14004c6e5  mov     eax, [r9+rdi+3Ch]
0x14004c6ea  mov     r9, [r9+rdi+30h]
0x14004c6ef  mov     [rsp+68h+var_40], eax
0x14004c6f3  mov     [rsp+68h+var_48], eax
0x14004c6f7  call    McTemplateK0idddd_EtwWriteTransfer
0x14004c6fc  inc     esi
0x14004c6fe  cmp     esi, [rdi+1Ch]
0x14004c701  jb      short loc_14004C68D
0x14004c703  cmp     dword ptr [rdi+28h], 0
0x14004c707  jl      loc_14004C830
0x14004c70d  cmp     dword ptr [rbx+70h], 0
0x14004c711  jl      loc_14004C830
0x14004c717  xor     edx, edx
0x14004c719  lea     rcx, NodeInfo
0x14004c720  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14004c727  nop     dword ptr [rax+rax+00h]
0x14004c72c  mov     rcx, cs:SrvNodeTasksTable
0x14004c733  lea     rsi, [rdi+20h]
0x14004c737  mov     rdx, rsi
0x14004c73a  lea     r9, [rbx+88h]
0x14004c741  call    RfsHashTableBucketLookupMatchEntry
0x14004c746  test    rax, rax
0x14004c749  jz      short loc_14004C7A0
0x14004c74b  lea     rcx, SrvAdminNodeRundown; RunRef
0x14004c752  mov     qword ptr [rbx+80h], 0
0x14004c75d  call    cs:__imp_ExAcquireRundownProtection
0x14004c764  nop     dword ptr [rax+rax+00h]
0x14004c769  xor     edx, edx
0x14004c76b  lea     rcx, NodeInfo
0x14004c772  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14004c779  nop     dword ptr [rax+rax+00h]
0x14004c77e  mov     rcx, [rbx+78h]; IoWorkItem
0x14004c782  lea     rdx, InvalidationThread; WorkerRoutine
0x14004c789  mov     r9, rbx; Context
0x14004c78c  xor     r8d, r8d; QueueType
0x14004c78f  call    cs:__imp_IoQueueWorkItem
0x14004c796  nop     dword ptr [rax+rax+00h]
0x14004c79b  jmp     loc_14004C824
0x14004c7a0  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14004c7a7  lea     rax, WPP_GLOBAL_Control
0x14004c7ae  cmp     rcx, rax
0x14004c7b1  jz      short loc_14004C7DE
0x14004c7b3  mov     eax, [rcx+2Ch]
0x14004c7b6  test    al, 20h
0x14004c7b8  jz      short loc_14004C7DE
0x14004c7ba  cmp     byte ptr [rcx+29h], 4
0x14004c7be  jb      short loc_14004C7DE
0x14004c7c0  mov     eax, [rsi]
0x14004c7c2  lea     r8, WPP_65854c2b783f3b66712a66400b9887aa_Traceguids
0x14004c7c9  mov     rcx, [rcx+18h]
0x14004c7cd  mov     edx, 15h
0x14004c7d2  mov     r9, rbx
0x14004c7d5  mov     [rsp+68h+var_48], eax
0x14004c7d9  call    WPP_SF_qD
0x14004c7de  mov     rcx, cs:SrvNodeActiveTasksTable
0x14004c7e5  lea     rdx, [rbx+60h]
0x14004c7e9  mov     r9d, 1
0x14004c7ef  mov     r8, rsi
0x14004c7f2  call    RfsHashTableRemove
0x14004c7f7  mov     rcx, [rbx+78h]; IoWorkItem
0x14004c7fb  call    cs:__imp_IoFreeWorkItem
0x14004c802  nop     dword ptr [rax+rax+00h]
0x14004c807  mov     rcx, rbx
0x14004c80a  call    SrvNetWskNotifyCleanupProviderContext
0x14004c80f  xor     edx, edx
0x14004c811  lea     rcx, NodeInfo
0x14004c818  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14004c81f  nop     dword ptr [rax+rax+00h]
0x14004c824  mov     edx, ebp
0x14004c826  mov     rcx, rdi
0x14004c829  call    ReplyToRequestor
0x14004c82e  jmp     short loc_14004C838
0x14004c830  mov     rcx, rbx
0x14004c833  call    InvalidationCompleteAll
0x14004c838  lea     rcx, SrvAdminNodeRundown; RunRef
0x14004c83f  call    cs:__imp_ExReleaseRundownProtection
0x14004c846  nop     dword ptr [rax+rax+00h]
0x14004c84b  add     rsp, 48h
0x14004c84f  pop     rdi
0x14004c850  pop     rsi
0x14004c851  pop     rbp
0x14004c852  pop     rbx
0x14004c853  retn
```
