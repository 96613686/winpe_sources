# WcEnumerateDirectory

- ea: `0x14002b8fc`
- end: `0x14002b9e9`
- name: `WcEnumerateDirectory`
- size: `237`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x1400154ac`
- `0x140018b9c`
- `0x14001cff0`
- `0x14002b84c`

## callees

- `0x14002b8fc`

## import_xrefs

- `FLTMGR!FltPerformSynchronousIo` at `0x14002b9c8`
- `FLTMGR!FltPerformSynchronousIo` at `0x14002b9c8`
- `FLTMGR!FltFreeCallbackData` at `0x14002b933`
- `FLTMGR!FltFreeCallbackData` at `0x14002b933`
- `FLTMGR!FltAllocateCallbackData` at `0x14002b91a`
- `FLTMGR!FltAllocateCallbackData` at `0x14002b91a`

## pseudocode

```c
__int64 __fastcall WcEnumerateDirectory(
        struct _FLT_INSTANCE *a1,
        struct _FILE_OBJECT *a2,
        DWORD a3,
        void *a4,
        ULONG a5,
        UCHAR a6,
        ULONG a7,
        void *a8,
        _DWORD *a9)
{
  NTSTATUS Status; // ebx
  struct _FLT_CALLBACK_DATA *v12; // rdx
  PFLT_CALLBACK_DATA RetNewCallbackData; // [rsp+20h] [rbp-18h] BYREF

  RetNewCallbackData = 0;
  Status = FltAllocateCallbackData(a1, a2, &RetNewCallbackData);
  if ( Status >= 0 )
  {
    RetNewCallbackData->Iopb->MajorFunction = 12;
    RetNewCallbackData->Iopb->MinorFunction = 1;
    RetNewCallbackData->Iopb->Parameters.Read.Length = a7;
    RetNewCallbackData->Iopb->Parameters.Read.ByteOffset.LowPart = a3;
    RetNewCallbackData->Iopb->Parameters.QueryEa.EaList = a4;
    RetNewCallbackData->Iopb->Parameters.Create.EaLength = a5;
    RetNewCallbackData->Iopb->Parameters.Create.EaBuffer = a8;
    RetNewCallbackData->Iopb->Parameters.Create.AllocationSize.QuadPart = 0;
    RetNewCallbackData->Iopb->OperationFlags = a6;
    FltPerformSynchronousIo(RetNewCallbackData);
    v12 = RetNewCallbackData;
    Status = RetNewCallbackData->IoStatus.Status;
    *a9 = RetNewCallbackData->IoStatus.Information;
  }
  else
  {
    v12 = RetNewCallbackData;
  }
  FltFreeCallbackData(v12);
  return (unsigned int)Status;
}

```

## disassembly

```asm
0x14002b8fc  push    rbp
0x14002b8fe  push    rbx
0x14002b8ff  push    rsi
0x14002b900  push    rdi
0x14002b901  mov     rbp, rsp
0x14002b904  sub     rsp, 38h
0x14002b908  mov     esi, r8d
0x14002b90b  mov     [rbp+RetNewCallbackData], 0
0x14002b913  lea     r8, [rbp+RetNewCallbackData]; RetNewCallbackData
0x14002b917  mov     rdi, r9
0x14002b91a  call    cs:__imp_FltAllocateCallbackData
0x14002b921  nop     dword ptr [rax+rax+00h]
0x14002b926  mov     ebx, eax
0x14002b928  test    eax, eax
0x14002b92a  jns     short loc_14002B94B
0x14002b92c  mov     rdx, [rbp+RetNewCallbackData]
0x14002b930  mov     rcx, rdx; CallbackData
0x14002b933  call    cs:__imp_FltFreeCallbackData
0x14002b93a  nop     dword ptr [rax+rax+00h]
0x14002b93f  mov     eax, ebx
0x14002b941  add     rsp, 38h
0x14002b945  pop     rdi
0x14002b946  pop     rsi
0x14002b947  pop     rbx
0x14002b948  pop     rbp
0x14002b949  retn
0x14002b94b  mov     rax, [rbp+RetNewCallbackData]
0x14002b94f  mov     rcx, [rax+10h]
0x14002b953  mov     byte ptr [rcx+4], 0Ch
0x14002b957  mov     rax, [rbp+RetNewCallbackData]
0x14002b95b  mov     rcx, [rax+10h]
0x14002b95f  mov     byte ptr [rcx+5], 1
0x14002b963  mov     rax, [rbp+RetNewCallbackData]
0x14002b967  mov     rcx, [rax+10h]
0x14002b96b  mov     eax, [rbp+arg_30]
0x14002b96e  mov     [rcx+18h], eax
0x14002b971  mov     rax, [rbp+RetNewCallbackData]
0x14002b975  mov     rcx, [rax+10h]
0x14002b979  mov     [rcx+28h], esi
0x14002b97c  mov     rax, [rbp+RetNewCallbackData]
0x14002b980  mov     rcx, [rax+10h]
0x14002b984  mov     [rcx+20h], rdi
0x14002b988  mov     rax, [rbp+RetNewCallbackData]
0x14002b98c  mov     rcx, [rax+10h]
0x14002b990  mov     eax, [rbp+arg_20]
0x14002b993  mov     [rcx+30h], eax
0x14002b996  mov     rax, [rbp+RetNewCallbackData]
0x14002b99a  mov     rcx, [rax+10h]
0x14002b99e  mov     rax, [rbp+arg_38]
0x14002b9a2  mov     [rcx+38h], rax
0x14002b9a6  mov     rax, [rbp+RetNewCallbackData]
0x14002b9aa  mov     rcx, [rax+10h]
0x14002b9ae  mov     qword ptr [rcx+40h], 0
0x14002b9b6  mov     rax, [rbp+RetNewCallbackData]
0x14002b9ba  mov     rcx, [rax+10h]
0x14002b9be  mov     al, [rbp+arg_28]
0x14002b9c1  mov     [rcx+6], al
0x14002b9c4  mov     rcx, [rbp+RetNewCallbackData]; CallbackData
0x14002b9c8  call    cs:__imp_FltPerformSynchronousIo
0x14002b9cf  nop     dword ptr [rax+rax+00h]
0x14002b9d4  mov     rdx, [rbp+RetNewCallbackData]
0x14002b9d8  mov     rax, [rbp+arg_40]
0x14002b9dc  mov     ebx, [rdx+18h]
0x14002b9df  mov     ecx, [rdx+20h]
0x14002b9e2  mov     [rax], ecx
0x14002b9e4  jmp     loc_14002B930
```
