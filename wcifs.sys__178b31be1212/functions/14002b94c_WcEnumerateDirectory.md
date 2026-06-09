# WcEnumerateDirectory

- ea: `0x14002b94c`
- end: `0x14002ba39`
- name: `WcEnumerateDirectory`
- size: `237`
- prototype: `__int64 __fastcall(struct _FLT_INSTANCE *, struct _FILE_OBJECT *, DWORD, void *, ULONG, UCHAR, ULONG, void *, _DWORD *)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x1400154ac`
- `0x140018b9c`
- `0x14001cff0`
- `0x14002b89c`

## callees

- `0x14002b94c`

## import_xrefs

- `FLTMGR!FltPerformSynchronousIo` at `0x14002ba18`
- `FLTMGR!FltPerformSynchronousIo` at `0x14002ba18`
- `FLTMGR!FltFreeCallbackData` at `0x14002b983`
- `FLTMGR!FltFreeCallbackData` at `0x14002b983`
- `FLTMGR!FltAllocateCallbackData` at `0x14002b96a`
- `FLTMGR!FltAllocateCallbackData` at `0x14002b96a`

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
0x14002b94c  push    rbp
0x14002b94e  push    rbx
0x14002b94f  push    rsi
0x14002b950  push    rdi
0x14002b951  mov     rbp, rsp
0x14002b954  sub     rsp, 38h
0x14002b958  mov     esi, r8d
0x14002b95b  mov     [rbp+RetNewCallbackData], 0
0x14002b963  lea     r8, [rbp+RetNewCallbackData]; RetNewCallbackData
0x14002b967  mov     rdi, r9
0x14002b96a  call    cs:__imp_FltAllocateCallbackData
0x14002b971  nop     dword ptr [rax+rax+00h]
0x14002b976  mov     ebx, eax
0x14002b978  test    eax, eax
0x14002b97a  jns     short loc_14002B99B
0x14002b97c  mov     rdx, [rbp+RetNewCallbackData]
0x14002b980  mov     rcx, rdx; CallbackData
0x14002b983  call    cs:__imp_FltFreeCallbackData
0x14002b98a  nop     dword ptr [rax+rax+00h]
0x14002b98f  mov     eax, ebx
0x14002b991  add     rsp, 38h
0x14002b995  pop     rdi
0x14002b996  pop     rsi
0x14002b997  pop     rbx
0x14002b998  pop     rbp
0x14002b999  retn
0x14002b99b  mov     rax, [rbp+RetNewCallbackData]
0x14002b99f  mov     rcx, [rax+10h]
0x14002b9a3  mov     byte ptr [rcx+4], 0Ch
0x14002b9a7  mov     rax, [rbp+RetNewCallbackData]
0x14002b9ab  mov     rcx, [rax+10h]
0x14002b9af  mov     byte ptr [rcx+5], 1
0x14002b9b3  mov     rax, [rbp+RetNewCallbackData]
0x14002b9b7  mov     rcx, [rax+10h]
0x14002b9bb  mov     eax, [rbp+arg_30]
0x14002b9be  mov     [rcx+18h], eax
0x14002b9c1  mov     rax, [rbp+RetNewCallbackData]
0x14002b9c5  mov     rcx, [rax+10h]
0x14002b9c9  mov     [rcx+28h], esi
0x14002b9cc  mov     rax, [rbp+RetNewCallbackData]
0x14002b9d0  mov     rcx, [rax+10h]
0x14002b9d4  mov     [rcx+20h], rdi
0x14002b9d8  mov     rax, [rbp+RetNewCallbackData]
0x14002b9dc  mov     rcx, [rax+10h]
0x14002b9e0  mov     eax, [rbp+arg_20]
0x14002b9e3  mov     [rcx+30h], eax
0x14002b9e6  mov     rax, [rbp+RetNewCallbackData]
0x14002b9ea  mov     rcx, [rax+10h]
0x14002b9ee  mov     rax, [rbp+arg_38]
0x14002b9f2  mov     [rcx+38h], rax
0x14002b9f6  mov     rax, [rbp+RetNewCallbackData]
0x14002b9fa  mov     rcx, [rax+10h]
0x14002b9fe  mov     qword ptr [rcx+40h], 0
0x14002ba06  mov     rax, [rbp+RetNewCallbackData]
0x14002ba0a  mov     rcx, [rax+10h]
0x14002ba0e  mov     al, [rbp+arg_28]
0x14002ba11  mov     [rcx+6], al
0x14002ba14  mov     rcx, [rbp+RetNewCallbackData]; CallbackData
0x14002ba18  call    cs:__imp_FltPerformSynchronousIo
0x14002ba1f  nop     dword ptr [rax+rax+00h]
0x14002ba24  mov     rdx, [rbp+RetNewCallbackData]
0x14002ba28  mov     rax, [rbp+arg_40]
0x14002ba2c  mov     ebx, [rdx+18h]
0x14002ba2f  mov     ecx, [rdx+20h]
0x14002ba32  mov     [rax], ecx
0x14002ba34  jmp     loc_14002B980
```
