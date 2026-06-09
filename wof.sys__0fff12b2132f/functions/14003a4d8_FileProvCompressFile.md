# FileProvCompressFile

- ea: `0x14003a4d8`
- end: `0x14003a6a1`
- name: `FileProvCompressFile`
- size: `457`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x14003a3c0`

## callees

- `0x140010ef8`
- `0x140011064`
- `0x14003a4d8`
- `0x14003a6a8`
- `0x14003addc`
- `0x14003b078`

## import_xrefs

- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14003a67e`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14003a67e`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x14003a5a0`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x14003a5a0`
- `FLTMGR!FltReadFile` at `0x14003a617`
- `FLTMGR!FltReadFile` at `0x14003a617`

## pseudocode

```c
__int64 __fastcall FileProvCompressFile(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v3; // rdi
  void *Buffer; // rsi
  NTSTATUS v7; // ebx
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
  v7 = FileProvInitializeCompress(a1, a2, *(_QWORD *)(a2 + 32), a3, &v13);
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
        v7 = FileProvPerformCompress(a1, Buffer, BytesRead, v3);
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
0x14003a4d8  mov     rax, rsp
0x14003a4db  mov     [rax+10h], rbx
0x14003a4df  push    rbp
0x14003a4e0  push    rsi
0x14003a4e1  push    rdi
0x14003a4e2  push    r12
0x14003a4e4  push    r14
0x14003a4e6  sub     rsp, 50h
0x14003a4ea  xor     edi, edi
0x14003a4ec  xor     esi, esi
0x14003a4ee  mov     r14, rdx
0x14003a4f1  mov     rbp, rcx
0x14003a4f4  mov     [rax+20h], rdi
0x14003a4f8  mov     [rax+8], esi
0x14003a4fb  cmp     [rcx+8], rsi
0x14003a4ff  jnz     short loc_14003A50B
0x14003a501  mov     ebx, 0C000046Fh
0x14003a506  jmp     loc_14003A65F
0x14003a50b  mov     eax, cs:dword_14001A4A4
0x14003a511  mov     rcx, [rcx+18h]
0x14003a515  sub     rcx, rax
0x14003a518  cmp     dword ptr [rcx+90h], 1Ch
0x14003a51f  jnz     short loc_14003A573
0x14003a521  mov     ecx, cs:Feature_ReFS_WOF_Support__private_featureState
0x14003a527  mov     [rsp+78h+arg_18], rsi
0x14003a52f  mov     dword ptr [rsp+78h+arg_18], ecx
0x14003a536  test    cl, 10h
0x14003a539  jnz     short loc_14003A501
0x14003a53b  mov     rax, [rsp+78h+arg_18]
0x14003a543  or      ecx, 1
0x14003a546  mov     [rsp+78h+arg_18], rax
0x14003a54e  mov     ebx, 3
0x14003a553  mov     dword ptr [rsp+78h+arg_18], ecx
0x14003a55a  mov     r8d, ebx
0x14003a55d  mov     rdx, [rsp+78h+arg_18]
0x14003a565  call    wil_details_FeatureReporting_ReportUsageToService
0x14003a56a  mov     edx, ebx
0x14003a56c  call    wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath
0x14003a571  jmp     short loc_14003A501
0x14003a573  lea     rax, [rsp+78h+arg_18]
0x14003a57b  mov     r9, r8
0x14003a57e  mov     r8, [rdx+20h]
0x14003a582  mov     rcx, rbp
0x14003a585  mov     [rsp+78h+Buffer], rax
0x14003a58a  call    FileProvInitializeCompress
0x14003a58f  mov     ebx, eax
0x14003a591  test    eax, eax
0x14003a593  js      loc_14003A657
0x14003a599  lea     rcx, FileProvCompressReadLookaside; Lookaside
0x14003a5a0  call    cs:__imp_ExAllocateFromPagedLookasideList
0x14003a5a7  nop     dword ptr [rax+rax+00h]
0x14003a5ac  mov     rdi, [rsp+78h+arg_18]
0x14003a5b4  mov     rsi, rax
0x14003a5b7  test    rax, rax
0x14003a5ba  jnz     short loc_14003A5C6
0x14003a5bc  mov     ebx, 0C000009Ah
0x14003a5c1  jmp     loc_14003A65F
0x14003a5c6  mov     r12d, 80000000h
0x14003a5cc  mov     rax, [rbp+8]
0x14003a5d0  lea     r8, [rdi+20h]; ByteOffset
0x14003a5d4  cmp     [r8], rax
0x14003a5d7  jge     loc_14003A65F
0x14003a5dd  mov     rdx, [r14+20h]; FileObject
0x14003a5e1  lea     rax, [rsp+78h+arg_0]
0x14003a5e9  mov     rcx, [rdi+40h]; InitiatingInstance
0x14003a5ed  mov     r9d, 40000h; Length
0x14003a5f3  mov     [rsp+78h+CallbackContext], 0; CallbackContext
0x14003a5fc  mov     [rsp+78h+CallbackRoutine], 0; CallbackRoutine
0x14003a605  mov     [rsp+78h+BytesRead], rax; BytesRead
0x14003a60a  mov     [rsp+78h+Flags], 4; Flags
0x14003a612  mov     [rsp+78h+Buffer], rsi; Buffer
0x14003a617  call    cs:__imp_FltReadFile
0x14003a61e  nop     dword ptr [rax+rax+00h]
0x14003a623  mov     ebx, eax
0x14003a625  add     eax, r12d
0x14003a628  test    r12d, eax
0x14003a62b  jnz     short loc_14003A635
0x14003a62d  cmp     ebx, 0C0000011h
0x14003a633  jnz     short loc_14003A65F
0x14003a635  mov     r8d, [rsp+78h+arg_0]
0x14003a63d  mov     r9, rdi
0x14003a640  mov     rdx, rsi
0x14003a643  mov     rcx, rbp
0x14003a646  call    FileProvPerformCompress
0x14003a64b  mov     ebx, eax
0x14003a64d  test    eax, eax
0x14003a64f  jns     loc_14003A5CC
0x14003a655  jmp     short loc_14003A65F
0x14003a657  mov     rdi, [rsp+78h+arg_18]
0x14003a65f  mov     r8d, ebx
0x14003a662  mov     rdx, rdi
0x14003a665  mov     rcx, rbp
0x14003a668  call    FileProvFinalizeCompress
0x14003a66d  mov     ebx, eax
0x14003a66f  test    rsi, rsi
0x14003a672  jz      short loc_14003A68A
0x14003a674  mov     rdx, rsi; Entry
0x14003a677  lea     rcx, FileProvCompressReadLookaside; Lookaside
0x14003a67e  call    cs:__imp_ExFreeToPagedLookasideList
0x14003a685  nop     dword ptr [rax+rax+00h]
0x14003a68a  mov     eax, ebx
0x14003a68c  mov     rbx, [rsp+78h+arg_8]
0x14003a694  add     rsp, 50h
0x14003a698  pop     r14
0x14003a69a  pop     r12
0x14003a69c  pop     rdi
0x14003a69d  pop     rsi
0x14003a69e  pop     rbp
0x14003a69f  retn
```
