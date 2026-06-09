# WimFSFReadWimCompletion

- ea: `0x14000afc0`
- end: `0x14000b106`
- name: `WimFSFReadWimCompletion`
- size: `326`
- prototype: `void __stdcall(PFLT_CALLBACK_DATA CallbackData, PFLT_CONTEXT Context)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x14003ccf0`

## callees

- `0x14000a9f0`
- `0x14000afc0`
- `0x14000cae0`
- `0x14000d3b8`
- `0x14000fb60`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x14000b001`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000b001`
- `FLTMGR!FltFreeGenericWorkItem` at `0x14000b054`
- `FLTMGR!FltFreeGenericWorkItem` at `0x14000b054`
- `FLTMGR!FltQueueGenericWorkItem` at `0x14000b03f`
- `FLTMGR!FltQueueGenericWorkItem` at `0x14000b03f`
- `FLTMGR!FltAllocateGenericWorkItem` at `0x14000b015`
- `FLTMGR!FltAllocateGenericWorkItem` at `0x14000b015`

## pseudocode

```c
void __fastcall WimFSFReadWimCompletion(PFLT_CALLBACK_DATA CallbackData, PVOID *Context)
{
  struct _FLT_GENERIC_WORKITEM *GenericWorkItem; // rax
  struct _FLT_GENERIC_WORKITEM *v5; // rsi
  NTSTATUS v6; // edi
  PDEVICE_OBJECT v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // r9

  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 40, WPP_3158cc7d99213f3216ee7f88e8d8f42f_Traceguids);
  *Context = CallbackData;
  if ( KeGetCurrentIrql() < 2u )
  {
    WimFSFReadWimCompletionWorker(0, 0, Context);
  }
  else
  {
    GenericWorkItem = FltAllocateGenericWorkItem();
    v5 = GenericWorkItem;
    if ( !GenericWorkItem )
    {
      v6 = -1073741670;
      goto LABEL_12;
    }
    v6 = FltQueueGenericWorkItem(
           GenericWorkItem,
           Context[5],
           (PFLT_GENERIC_WORKITEM_ROUTINE)WimFSFReadWimCompletionWorker,
           CriticalWorkQueue,
           Context);
    if ( v6 < 0 )
    {
      FltFreeGenericWorkItem(v5);
LABEL_12:
      WimFSFCompleteRead((char *)Context, 0, v6);
      v7 = WPP_GLOBAL_Control;
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        v8 = 43;
        v9 = (unsigned int)v6;
LABEL_19:
        WPP_SF_d(v7->AttachedDevice, v8, WPP_3158cc7d99213f3216ee7f88e8d8f42f_Traceguids, v9);
        return;
      }
      return;
    }
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 41, WPP_3158cc7d99213f3216ee7f88e8d8f42f_Traceguids);
  }
  v7 = WPP_GLOBAL_Control;
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    v8 = 42;
    v9 = 0;
    goto LABEL_19;
  }
}

```

## disassembly

```asm
0x14000afc0  mov     [rsp+arg_0], rbx
0x14000afc5  mov     [rsp+arg_8], rsi
0x14000afca  push    rdi
0x14000afcb  sub     rsp, 30h
0x14000afcf  mov     rbx, rdx
0x14000afd2  mov     rdi, rcx
0x14000afd5  mov     rcx, cs:WPP_GLOBAL_Control
0x14000afdc  mov     eax, [rcx+2Ch]
0x14000afdf  test    al, 20h
0x14000afe1  jz      short loc_14000AFFE
0x14000afe3  cmp     byte ptr [rcx+29h], 4
0x14000afe7  jb      short loc_14000AFFE
0x14000afe9  mov     rcx, [rcx+18h]
0x14000afed  lea     r8, WPP_3158cc7d99213f3216ee7f88e8d8f42f_Traceguids
0x14000aff4  mov     edx, 28h ; '('
0x14000aff9  call    WPP_SF_
0x14000affe  mov     [rbx], rdi
0x14000b001  call    cs:__imp_KeGetCurrentIrql
0x14000b008  nop     dword ptr [rax+rax+00h]
0x14000b00d  cmp     al, 2
0x14000b00f  jb      loc_14000B0BD
0x14000b015  call    cs:__imp_FltAllocateGenericWorkItem
0x14000b01c  nop     dword ptr [rax+rax+00h]
0x14000b021  mov     rsi, rax
0x14000b024  test    rax, rax
0x14000b027  jz      short loc_14000B08D
0x14000b029  mov     rdx, [rbx+28h]; FltObject
0x14000b02d  lea     r8, WimFSFReadWimCompletionWorker; WorkerRoutine
0x14000b034  xor     r9d, r9d; QueueType
0x14000b037  mov     [rsp+38h+Context], rbx; Context
0x14000b03c  mov     rcx, rax; FltWorkItem
0x14000b03f  call    cs:__imp_FltQueueGenericWorkItem
0x14000b046  nop     dword ptr [rax+rax+00h]
0x14000b04b  mov     edi, eax
0x14000b04d  test    eax, eax
0x14000b04f  jns     short loc_14000B062
0x14000b051  mov     rcx, rsi; FltWorkItem
0x14000b054  call    cs:__imp_FltFreeGenericWorkItem
0x14000b05b  nop     dword ptr [rax+rax+00h]
0x14000b060  jmp     short loc_14000B092
0x14000b062  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b069  mov     eax, [rcx+2Ch]
0x14000b06c  test    al, 20h
0x14000b06e  jz      short loc_14000B0C9
0x14000b070  cmp     byte ptr [rcx+29h], 5
0x14000b074  jb      short loc_14000B0C9
0x14000b076  mov     rcx, [rcx+18h]
0x14000b07a  lea     r8, WPP_3158cc7d99213f3216ee7f88e8d8f42f_Traceguids
0x14000b081  mov     edx, 29h ; ')'
0x14000b086  call    WPP_SF_
0x14000b08b  jmp     short loc_14000B0C9
0x14000b08d  mov     edi, 0C000009Ah
0x14000b092  mov     r8d, edi
0x14000b095  xor     edx, edx
0x14000b097  mov     rcx, rbx; Entry
0x14000b09a  call    WimFSFCompleteRead
0x14000b09f  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b0a6  mov     eax, [rcx+2Ch]
0x14000b0a9  test    al, 20h
0x14000b0ab  jz      short loc_14000B0F5
0x14000b0ad  cmp     byte ptr [rcx+29h], 4
0x14000b0b1  jb      short loc_14000B0F5
0x14000b0b3  mov     edx, 2Bh ; '+'
0x14000b0b8  mov     r9d, edi
0x14000b0bb  jmp     short loc_14000B0E5
0x14000b0bd  mov     r8, rbx; Context
0x14000b0c0  xor     edx, edx; FltObject
0x14000b0c2  xor     ecx, ecx; FltWorkItem
0x14000b0c4  call    WimFSFReadWimCompletionWorker
0x14000b0c9  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b0d0  mov     eax, [rcx+2Ch]
0x14000b0d3  test    al, 20h
0x14000b0d5  jz      short loc_14000B0F5
0x14000b0d7  cmp     byte ptr [rcx+29h], 4
0x14000b0db  jb      short loc_14000B0F5
0x14000b0dd  mov     edx, 2Ah ; '*'
0x14000b0e2  xor     r9d, r9d
0x14000b0e5  mov     rcx, [rcx+18h]
0x14000b0e9  lea     r8, WPP_3158cc7d99213f3216ee7f88e8d8f42f_Traceguids
0x14000b0f0  call    WPP_SF_d
0x14000b0f5  mov     rbx, [rsp+38h+arg_0]
0x14000b0fa  mov     rsi, [rsp+38h+arg_8]
0x14000b0ff  add     rsp, 30h
0x14000b103  pop     rdi
0x14000b104  retn
```
