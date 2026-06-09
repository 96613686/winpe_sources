# FileProvCompressFile

- ea: `0x14003a528`
- end: `0x14003a6f1`
- name: `FileProvCompressFile`
- size: `457`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x14003a410`

## callees

- `0x140010ef8`
- `0x140011064`
- `0x14003a528`
- `0x14003a6f8`
- `0x14003ae2c`
- `0x14003b0c8`

## import_xrefs

- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14003a6ce`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14003a6ce`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x14003a5f0`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x14003a5f0`
- `FLTMGR!FltReadFile` at `0x14003a667`
- `FLTMGR!FltReadFile` at `0x14003a667`

## pseudocode

```c
__int64 __fastcall FileProvCompressFile(__int64 a1, __int64 a2, void *a3)
{
  __int64 v3; // rdi
  void *Buffer; // rsi
  int v7; // ebx
  __int64 v8; // rcx
  PVOID v9; // rax
  unsigned int v10; // ebx
  ULONG BytesRead; // [rsp+80h] [rbp+8h] BYREF
  __int64 v13; // [rsp+98h] [rbp+20h] BYREF

  v3 = 0;
  Buffer = 0;
  v13 = 0;
  BytesRead = 0;
  if ( !*(_QWORD *)(a1 + 8) )
  {
LABEL_2:
    v7 = -1073740689;
    goto LABEL_15;
  }
  if ( *(_DWORD *)(*(_QWORD *)(a1 + 24) - (unsigned int)dword_14001A4A4 + 144LL) == 28 )
  {
    v13 = (unsigned int)Feature_ReFS_WOF_Support__private_featureState;
    if ( (Feature_ReFS_WOF_Support__private_featureState & 0x10) == 0 )
    {
      LODWORD(v13) = Feature_ReFS_WOF_Support__private_featureState | 1;
      wil_details_FeatureReporting_ReportUsageToService(Feature_ReFS_WOF_Support__private_featureState | 1u, v13, 3);
      wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath(v8, 3);
    }
    goto LABEL_2;
  }
  v7 = FileProvInitializeCompress(a1, a2, *(void **)(a2 + 32), a3, &v13);
  if ( v7 < 0 )
  {
    v3 = v13;
  }
  else
  {
    v9 = ExAllocateFromPagedLookasideList(&FileProvCompressReadLookaside);
    v3 = v13;
    Buffer = v9;
    if ( v9 )
    {
      do
      {
        if ( *(_QWORD *)(v3 + 32) >= *(_QWORD *)(a1 + 8) )
          break;
        v7 = FltReadFile(
               *(PFLT_INSTANCE *)(v3 + 64),
               *(PFILE_OBJECT *)(a2 + 32),
               (PLARGE_INTEGER)(v3 + 32),
               0x40000u,
               Buffer,
               4u,
               &BytesRead,
               0,
               0);
        if ( ((v7 + 0x80000000) & 0x80000000) == 0 && v7 != -1073741807 )
          break;
        v7 = FileProvPerformCompress(a1, (__int64)Buffer, BytesRead, v3);
      }
      while ( v7 >= 0 );
    }
    else
    {
      v7 = -1073741670;
    }
  }
LABEL_15:
  v10 = FileProvFinalizeCompress(a1, v3, (unsigned int)v7);
  if ( Buffer )
    ExFreeToPagedLookasideList(&FileProvCompressReadLookaside, Buffer);
  return v10;
}

```

## disassembly

```asm
0x14003a528  mov     rax, rsp
0x14003a52b  mov     [rax+10h], rbx
0x14003a52f  push    rbp
0x14003a530  push    rsi
0x14003a531  push    rdi
0x14003a532  push    r12
0x14003a534  push    r14
0x14003a536  sub     rsp, 50h
0x14003a53a  xor     edi, edi
0x14003a53c  xor     esi, esi
0x14003a53e  mov     r14, rdx
0x14003a541  mov     rbp, rcx
0x14003a544  mov     [rax+20h], rdi
0x14003a548  mov     [rax+8], esi
0x14003a54b  cmp     [rcx+8], rsi
0x14003a54f  jnz     short loc_14003A55B
0x14003a551  mov     ebx, 0C000046Fh
0x14003a556  jmp     loc_14003A6AF
0x14003a55b  mov     eax, cs:dword_14001A4A4
0x14003a561  mov     rcx, [rcx+18h]
0x14003a565  sub     rcx, rax
0x14003a568  cmp     dword ptr [rcx+90h], 1Ch
0x14003a56f  jnz     short loc_14003A5C3
0x14003a571  mov     ecx, cs:Feature_ReFS_WOF_Support__private_featureState
0x14003a577  mov     [rsp+78h+arg_18], rsi
0x14003a57f  mov     dword ptr [rsp+78h+arg_18], ecx
0x14003a586  test    cl, 10h
0x14003a589  jnz     short loc_14003A551
0x14003a58b  mov     rax, [rsp+78h+arg_18]
0x14003a593  or      ecx, 1
0x14003a596  mov     [rsp+78h+arg_18], rax
0x14003a59e  mov     ebx, 3
0x14003a5a3  mov     dword ptr [rsp+78h+arg_18], ecx
0x14003a5aa  mov     r8d, ebx
0x14003a5ad  mov     rdx, [rsp+78h+arg_18]
0x14003a5b5  call    wil_details_FeatureReporting_ReportUsageToService
0x14003a5ba  mov     edx, ebx
0x14003a5bc  call    wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath
0x14003a5c1  jmp     short loc_14003A551
0x14003a5c3  lea     rax, [rsp+78h+arg_18]
0x14003a5cb  mov     r9, r8
0x14003a5ce  mov     r8, [rdx+20h]
0x14003a5d2  mov     rcx, rbp
0x14003a5d5  mov     [rsp+78h+Buffer], rax
0x14003a5da  call    FileProvInitializeCompress
0x14003a5df  mov     ebx, eax
0x14003a5e1  test    eax, eax
0x14003a5e3  js      loc_14003A6A7
0x14003a5e9  lea     rcx, FileProvCompressReadLookaside; Lookaside
0x14003a5f0  call    cs:__imp_ExAllocateFromPagedLookasideList
0x14003a5f7  nop     dword ptr [rax+rax+00h]
0x14003a5fc  mov     rdi, [rsp+78h+arg_18]
0x14003a604  mov     rsi, rax
0x14003a607  test    rax, rax
0x14003a60a  jnz     short loc_14003A616
0x14003a60c  mov     ebx, 0C000009Ah
0x14003a611  jmp     loc_14003A6AF
0x14003a616  mov     r12d, 80000000h
0x14003a61c  mov     rax, [rbp+8]
0x14003a620  lea     r8, [rdi+20h]; ByteOffset
0x14003a624  cmp     [r8], rax
0x14003a627  jge     loc_14003A6AF
0x14003a62d  mov     rdx, [r14+20h]; FileObject
0x14003a631  lea     rax, [rsp+78h+arg_0]
0x14003a639  mov     rcx, [rdi+40h]; InitiatingInstance
0x14003a63d  mov     r9d, 40000h; Length
0x14003a643  mov     [rsp+78h+CallbackContext], 0; CallbackContext
0x14003a64c  mov     [rsp+78h+CallbackRoutine], 0; CallbackRoutine
0x14003a655  mov     [rsp+78h+BytesRead], rax; BytesRead
0x14003a65a  mov     [rsp+78h+Flags], 4; Flags
0x14003a662  mov     [rsp+78h+Buffer], rsi; Buffer
0x14003a667  call    cs:__imp_FltReadFile
0x14003a66e  nop     dword ptr [rax+rax+00h]
0x14003a673  mov     ebx, eax
0x14003a675  add     eax, r12d
0x14003a678  test    r12d, eax
0x14003a67b  jnz     short loc_14003A685
0x14003a67d  cmp     ebx, 0C0000011h
0x14003a683  jnz     short loc_14003A6AF
0x14003a685  mov     r8d, [rsp+78h+arg_0]
0x14003a68d  mov     r9, rdi
0x14003a690  mov     rdx, rsi
0x14003a693  mov     rcx, rbp
0x14003a696  call    FileProvPerformCompress
0x14003a69b  mov     ebx, eax
0x14003a69d  test    eax, eax
0x14003a69f  jns     loc_14003A61C
0x14003a6a5  jmp     short loc_14003A6AF
0x14003a6a7  mov     rdi, [rsp+78h+arg_18]
0x14003a6af  mov     r8d, ebx
0x14003a6b2  mov     rdx, rdi
0x14003a6b5  mov     rcx, rbp
0x14003a6b8  call    FileProvFinalizeCompress
0x14003a6bd  mov     ebx, eax
0x14003a6bf  test    rsi, rsi
0x14003a6c2  jz      short loc_14003A6DA
0x14003a6c4  mov     rdx, rsi; Entry
0x14003a6c7  lea     rcx, FileProvCompressReadLookaside; Lookaside
0x14003a6ce  call    cs:__imp_ExFreeToPagedLookasideList
0x14003a6d5  nop     dword ptr [rax+rax+00h]
0x14003a6da  mov     eax, ebx
0x14003a6dc  mov     rbx, [rsp+78h+arg_8]
0x14003a6e4  add     rsp, 50h
0x14003a6e8  pop     r14
0x14003a6ea  pop     r12
0x14003a6ec  pop     rdi
0x14003a6ed  pop     rsi
0x14003a6ee  pop     rbp
0x14003a6ef  retn
```
