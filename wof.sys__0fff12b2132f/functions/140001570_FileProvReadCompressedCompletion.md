# FileProvReadCompressedCompletion

- ea: `0x140001570`
- end: `0x1400016db`
- name: `FileProvReadCompressedCompletion`
- size: `363`
- prototype: `void __stdcall(PFLT_CALLBACK_DATA CallbackData, PFLT_CONTEXT Context)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140038710`

## callees

- `0x140001570`
- `0x1400016f0`
- `0x1400022a0`
- `0x14000d3b8`
- `0x14000fb60`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x14000159a`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000159a`
- `FLTMGR!FltFreeGenericWorkItem` at `0x14000164a`
- `FLTMGR!FltFreeGenericWorkItem` at `0x14000164a`
- `FLTMGR!FltQueueGenericWorkItem` at `0x140001607`
- `FLTMGR!FltQueueGenericWorkItem` at `0x140001607`
- `FLTMGR!FltAllocateGenericWorkItem` at `0x1400015d9`
- `FLTMGR!FltAllocateGenericWorkItem` at `0x1400015d9`

## pseudocode

```c
void __fastcall FileProvReadCompressedCompletion(PFLT_CALLBACK_DATA CallbackData, PVOID *Context)
{
  PDEVICE_OBJECT v4; // rcx
  struct _FLT_GENERIC_WORKITEM *GenericWorkItem; // rax
  struct _FLT_GENERIC_WORKITEM *v6; // rdi
  NTSTATUS v7; // esi
  __int64 v8; // rdx
  __int64 v9; // r9

  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 34, WPP_3b099794e4b93327e327da255c047df6_Traceguids);
  *Context = CallbackData;
  if ( KeGetCurrentIrql() < 2u )
  {
    FileProvReadCompressedCompletionWorker(0, 0, Context);
    goto LABEL_4;
  }
  GenericWorkItem = FltAllocateGenericWorkItem();
  v6 = GenericWorkItem;
  if ( GenericWorkItem )
  {
    v7 = FltQueueGenericWorkItem(
           GenericWorkItem,
           Context[5],
           (PFLT_GENERIC_WORKITEM_ROUTINE)FileProvReadCompressedCompletionWorker,
           CriticalWorkQueue,
           Context);
    if ( v7 >= 0 )
    {
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 35, WPP_3b099794e4b93327e327da255c047df6_Traceguids);
LABEL_4:
      v4 = WPP_GLOBAL_Control;
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        v8 = 36;
        v9 = 0;
        goto LABEL_20;
      }
      return;
    }
    FltFreeGenericWorkItem(v6);
  }
  else
  {
    v7 = -1073741670;
  }
  FileProvCompleteRead((char *)Context, 0, v7);
  v4 = WPP_GLOBAL_Control;
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    v8 = 37;
    v9 = (unsigned int)v7;
LABEL_20:
    WPP_SF_d(v4->AttachedDevice, v8, WPP_3b099794e4b93327e327da255c047df6_Traceguids, v9);
  }
}

```

## disassembly

```asm
0x140001570  mov     [rsp+arg_8], rbx
0x140001575  push    rdi
0x140001576  sub     rsp, 30h
0x14000157a  mov     rbx, rdx
0x14000157d  mov     rdi, rcx
0x140001580  mov     rcx, cs:WPP_GLOBAL_Control
0x140001587  mov     eax, [rcx+2Ch]
0x14000158a  test    al, 20h
0x14000158c  jnz     loc_140001689
0x140001592  mov     [rsp+38h+arg_0], rsi
0x140001597  mov     [rbx], rdi
0x14000159a  call    cs:__imp_KeGetCurrentIrql
0x1400015a1  nop     dword ptr [rax+rax+00h]
0x1400015a6  cmp     al, 2
0x1400015a8  jnb     short loc_1400015D9
0x1400015aa  mov     r8, rbx; Context
0x1400015ad  xor     edx, edx; FltObject
0x1400015af  xor     ecx, ecx; FltWorkItem
0x1400015b1  call    FileProvReadCompressedCompletionWorker
0x1400015b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400015bd  mov     eax, [rcx+2Ch]
0x1400015c0  test    al, 20h
0x1400015c2  jnz     loc_1400016B4
0x1400015c8  mov     rsi, [rsp+38h+arg_0]
0x1400015cd  mov     rbx, [rsp+38h+arg_8]
0x1400015d2  add     rsp, 30h
0x1400015d6  pop     rdi
0x1400015d7  retn
0x1400015d9  call    cs:__imp_FltAllocateGenericWorkItem
0x1400015e0  nop     dword ptr [rax+rax+00h]
0x1400015e5  mov     rdi, rax
0x1400015e8  test    rax, rax
0x1400015eb  jz      loc_1400016AD
0x1400015f1  mov     rdx, [rbx+28h]; FltObject
0x1400015f5  lea     r8, FileProvReadCompressedCompletionWorker; WorkerRoutine
0x1400015fc  xor     r9d, r9d; QueueType
0x1400015ff  mov     [rsp+38h+Context], rbx; Context
0x140001604  mov     rcx, rax; FltWorkItem
0x140001607  call    cs:__imp_FltQueueGenericWorkItem
0x14000160e  nop     dword ptr [rax+rax+00h]
0x140001613  mov     esi, eax
0x140001615  test    eax, eax
0x140001617  js      short loc_140001647
0x140001619  mov     rcx, cs:WPP_GLOBAL_Control
0x140001620  mov     eax, [rcx+2Ch]
0x140001623  test    al, 20h
0x140001625  jz      short loc_1400015B6
0x140001627  cmp     byte ptr [rcx+29h], 5
0x14000162b  jb      short loc_1400015B6
0x14000162d  mov     rcx, [rcx+18h]
0x140001631  lea     r8, WPP_3b099794e4b93327e327da255c047df6_Traceguids
0x140001638  mov     edx, 23h ; '#'
0x14000163d  call    WPP_SF_
0x140001642  jmp     loc_1400015B6
0x140001647  mov     rcx, rdi; FltWorkItem
0x14000164a  call    cs:__imp_FltFreeGenericWorkItem
0x140001651  nop     dword ptr [rax+rax+00h]
0x140001656  mov     r8d, esi
0x140001659  xor     edx, edx
0x14000165b  mov     rcx, rbx; Entry
0x14000165e  call    FileProvCompleteRead
0x140001663  mov     rcx, cs:WPP_GLOBAL_Control
0x14000166a  mov     eax, [rcx+2Ch]
0x14000166d  test    al, 20h
0x14000166f  jz      loc_1400015C8
0x140001675  cmp     byte ptr [rcx+29h], 4
0x140001679  jb      loc_1400015C8
0x14000167f  mov     edx, 25h ; '%'
0x140001684  mov     r9d, esi
0x140001687  jmp     short loc_1400016C6
0x140001689  cmp     byte ptr [rcx+29h], 4
0x14000168d  jb      loc_140001592
0x140001693  mov     rcx, [rcx+18h]
0x140001697  lea     r8, WPP_3b099794e4b93327e327da255c047df6_Traceguids
0x14000169e  mov     edx, 22h ; '"'
0x1400016a3  call    WPP_SF_
0x1400016a8  jmp     loc_140001592
0x1400016ad  mov     esi, 0C000009Ah
0x1400016b2  jmp     short loc_140001656
0x1400016b4  cmp     byte ptr [rcx+29h], 4
0x1400016b8  jb      loc_1400015C8
0x1400016be  mov     edx, 24h ; '$'
0x1400016c3  xor     r9d, r9d
0x1400016c6  mov     rcx, [rcx+18h]
0x1400016ca  lea     r8, WPP_3b099794e4b93327e327da255c047df6_Traceguids
0x1400016d1  call    WPP_SF_d
0x1400016d6  jmp     loc_1400015C8
```
