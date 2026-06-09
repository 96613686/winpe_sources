# FileProvPerformCompress

- ea: `0x14003a6a8`
- end: `0x14003ac65`
- name: `FileProvPerformCompress`
- size: `1469`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14003a4d8`

## callees

- `0x140008fd0`
- `0x14000d158`
- `0x1400116c0`
- `0x14003a6a8`
- `0x14003ac70`

## import_xrefs

- `ntoskrnl!KeDelayExecutionThread` at `0x14003aaa4`
- `ntoskrnl!KeDelayExecutionThread` at `0x14003aaa4`
- `ntoskrnl!KeSetEvent` at `0x14003aada`
- `ntoskrnl!KeSetEvent` at `0x14003aada`
- `ntoskrnl!KeWaitForSingleObject` at `0x14003a821`
- `ntoskrnl!KeWaitForSingleObject` at `0x14003a821`
- `ntoskrnl!KeInitializeEvent` at `0x14003ab4b`
- `ntoskrnl!KeInitializeEvent` at `0x14003ab4b`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14003ab1a`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14003ab1a`
- `FLTMGR!FltWriteFile` at `0x14003aa7d`
- `FLTMGR!FltWriteFile` at `0x14003aa7d`
- `FLTMGR!FltSetInformationFile` at `0x14003a958`
- `FLTMGR!FltSetInformationFile` at `0x14003a958`

## pseudocode

```c
__int64 __fastcall FileProvPerformCompress(__int64 a1, __int64 a2, int a3, __int64 a4)
{
  void (__stdcall *CallbackRoutine)(PFLT_CALLBACK_DATA, PFLT_CONTEXT); // r13
  int v5; // edi
  unsigned int v6; // esi
  __int64 v8; // r8
  __int64 v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // rax
  int v14; // eax
  __int64 v15; // rax
  __int64 v16; // rdx
  __int64 v17; // rcx
  unsigned int v18; // r8d
  unsigned int v19; // eax
  int v20; // edx
  __int64 v21; // rax
  __int64 v22; // r10
  __int64 v23; // r9
  __int64 v24; // rdx
  __int64 v25; // rax
  __int64 v26; // rcx
  unsigned __int64 v27; // rdx
  unsigned int v28; // r8d
  __int64 v29; // r11
  unsigned __int64 *v30; // rdi
  __int64 v31; // rbp
  __int64 v32; // r14
  __int64 v33; // rcx
  __int64 v34; // r8
  unsigned int v35; // edx
  unsigned __int64 v36; // rcx
  unsigned int v37; // eax
  FLT_IO_OPERATION_FLAGS Flags; // r12d
  unsigned int v39; // edx
  unsigned int v40; // ecx
  void *CallbackContext; // rdx
  NTSTATUS v42; // eax
  __int64 v43; // rdx
  unsigned __int64 v44; // rdi
  int v45; // ebp
  PVOID PoolWithTag; // rax
  int v47; // ecx
  unsigned int v48; // ecx
  __int64 v49; // rax
  unsigned __int64 v50; // rbp
  int v51; // edi
  union _LARGE_INTEGER Interval; // [rsp+50h] [rbp-48h] BYREF
  __int64 v54; // [rsp+A8h] [rbp+10h]
  int v55; // [rsp+B0h] [rbp+18h]
  ULONG BytesWritten; // [rsp+B8h] [rbp+20h] BYREF

  v55 = a3;
  v54 = a2;
  CallbackRoutine = 0;
  v5 = a3;
  v6 = 0;
  BytesWritten = 0;
  v8 = a2;
  while ( 1 )
  {
    do
    {
      while ( v5 )
      {
        if ( *(_QWORD *)(a4 + 32) < *(_QWORD *)(a1 + 8) )
        {
          *(_QWORD *)(*(_QWORD *)(a4 + 240) + 64LL) = v8;
          *(_DWORD *)(*(_QWORD *)(a4 + 240) + 88LL) = **(_DWORD **)(a4 + 8);
          *(_QWORD *)(*(_QWORD *)(a4 + 240) + 56LL) = *(_QWORD *)(a4 + 32);
          *(_QWORD *)(a4 + 32) += **(unsigned int **)(a4 + 8);
          v10 = *(_QWORD *)(a1 + 8);
          if ( *(_QWORD *)(a4 + 32) > v10 )
          {
            v11 = *(_QWORD *)(a4 + 240);
            *(_QWORD *)(a4 + 32) = v10;
            *(_DWORD *)(v11 + 88) = *(_DWORD *)(a1 + 8) - *(_DWORD *)(v11 + 56);
          }
          v12 = *(_QWORD *)(a4 + 240);
          v13 = *(unsigned int *)(v12 + 88);
          v5 -= v13;
          v54 = v13 + v8;
          v55 = v5;
          if ( *(_DWORD *)(a4 + 52) <= 1u )
          {
            *(_QWORD *)(v12 + 72) = *(_QWORD *)(a4 + 24);
          }
          else if ( (unsigned __int8)WofTryQueueWorkItem(v12, (unsigned int)(*(_DWORD *)(a4 + 56) + 32)) )
          {
            goto LABEL_11;
          }
          FileProvCompressWorkItem(*(_QWORD *)(a4 + 240));
LABEL_11:
          v14 = *(_DWORD *)(a4 + 252);
          ++*(_DWORD *)(a4 + 256);
          v8 = v54;
          *(_DWORD *)(a4 + 252) = (unsigned int)(v14 + 1) % *(_DWORD *)(a4 + 52);
        }
        if ( !v5 )
          break;
        if ( *(_QWORD *)(a4 + 32) >= *(_QWORD *)(a1 + 8) )
          break;
        v15 = *(unsigned int *)(a4 + 252);
        if ( (_DWORD)v15 == *(_DWORD *)(a4 + 248) )
          break;
        *(_QWORD *)(a4 + 240) = *(_QWORD *)(a4 + 232) + 136 * v15;
      }
      v16 = *(_QWORD *)(a4 + 232);
      if ( !*(_DWORD *)(a4 + 256) )
      {
        *(_QWORD *)(a4 + 240) = v16 + 136LL * *(unsigned int *)(a4 + 252);
        return v6;
      }
      v17 = v16 + 136LL * *(unsigned int *)(a4 + 248);
      *(_QWORD *)(a4 + 240) = v17;
      KeWaitForSingleObject((PVOID)(v17 + 96), Executive, 0, 0, 0);
      v18 = *(_DWORD *)(a4 + 52);
      v19 = *(_DWORD *)(a4 + 248) + 1;
      --*(_DWORD *)(a4 + 256);
      v20 = v19 % v18;
      v21 = *(_QWORD *)(a4 + 240);
      *(_DWORD *)(a4 + 248) = v20;
      if ( *(int *)(v21 + 128) < 0 )
        return *(unsigned int *)(v21 + 128);
      if ( v18 > 1 )
      {
        memmove(*(void **)(a4 + 24), *(const void **)(v21 + 72), *(unsigned int *)(v21 + 92));
        v21 = *(_QWORD *)(a4 + 240);
      }
      v22 = *(_QWORD *)(a4 + 40);
      if ( v22 > 0 )
      {
        v23 = *(unsigned int *)(a4 + 16);
        v24 = *(_QWORD *)(a4 + 96);
        v25 = v23 * (*(_QWORD *)(v21 + 56) / (__int64)**(unsigned int **)(a4 + 8) - 1);
        if ( (_DWORD)v23 == 4 )
          *(_DWORD *)(v25 + v24) = v22;
        else
          *(_QWORD *)(v25 + v24) = v22;
      }
      v26 = *(_QWORD *)(a4 + 240);
      v27 = (unsigned __int64)*(unsigned int *)(a4 + 224) << 6;
      *(_QWORD *)(a4 + 40) += *(unsigned int *)(v26 + 92);
      *(_DWORD *)(a4 + 48) += *(_DWORD *)(v26 + 92);
      v28 = *(_DWORD *)(a4 + 48);
      v29 = *(_QWORD *)(a4 + 40);
      *(_QWORD *)(a4 + 24) = *(_QWORD *)(v27 + a4 + 96) + v28;
      if ( v28 + **(_DWORD **)(a4 + 8) > *(_DWORD *)(v27 + a4 + 104) )
        break;
      v8 = v54;
    }
    while ( (signed __int64)(*(_QWORD *)(v26 + 56) + *(unsigned int *)(v26 + 88)) < *(_QWORD *)(a1 + 8) );
    v30 = (unsigned __int64 *)(a4 + 296);
    v31 = *(_QWORD *)(v26 + 56) + *(unsigned int *)(v26 + 88);
    v32 = *(_QWORD *)(a1 + 8);
    v33 = v29 + (unsigned int)(*(_DWORD *)(a4 + 16) * *(_DWORD *)(a4 + 20));
    *(_QWORD *)(a4 + 296) = v33;
    if ( v31 < v32 )
      *v30 = v33 & 0xFFFFFFFFFFFFF000uLL;
    v6 = FltSetInformationFile(
           *(PFLT_INSTANCE *)(a4 + 64),
           *(PFILE_OBJECT *)(a4 + 72),
           (PVOID)(a4 + 296),
           8u,
           FileEndOfFileInformation);
    if ( (v6 & 0x80000000) != 0 )
      return v6;
    if ( v31 >= v32 && !*(_DWORD *)(a4 + 224) && (__int64)*v30 < *(unsigned int *)(a4 + 104) )
    {
      *(_BYTE *)(a4 + 60) = 1;
      return v6;
    }
    *(_QWORD *)(((unsigned __int64)*(unsigned int *)(a4 + 224) << 6) + a4 + 144) = *(_QWORD *)(a4 + 40)
                                                                                 + *(unsigned int *)(((unsigned __int64)*(unsigned int *)(a4 + 224) << 6) + a4 + 108)
                                                                                 + (unsigned __int64)(unsigned int)(*(_DWORD *)(a4 + 16) * *(_DWORD *)(a4 + 20))
                                                                                 - *(unsigned int *)(a4 + 48);
    v35 = *(_DWORD *)(a4 + 48);
    v36 = (unsigned __int64)*(unsigned int *)(a4 + 224) << 6;
    v37 = *(_DWORD *)(v36 + a4 + 108);
    if ( v37 < v35 )
    {
      Flags = 7;
      if ( VersionInformation.dwBuildNumber < 0x265C )
        Flags = 15;
      v39 = v35 - v37;
      if ( v31 >= v32 )
        v39 += 4095;
      *(_DWORD *)(v36 + a4 + 152) = v39 & 0xFFFFF000;
      if ( (Flags & 8) == 0 )
        CallbackRoutine = FileProvSimpleCompletionRoutine;
      while ( 1 )
      {
        v40 = *(_DWORD *)(a4 + 224);
        CallbackContext = (Flags & 8) != 0 ? 0LL : (void *)(a4 + ((unsigned __int64)v40 << 6) + 96);
        v42 = FltWriteFile(
                *(PFLT_INSTANCE *)(a4 + 64),
                *(PFILE_OBJECT *)(a4 + 72),
                (PLARGE_INTEGER)(((unsigned __int64)v40 << 6) + a4 + 144),
                *(_DWORD *)(((unsigned __int64)v40 << 6) + a4 + 152),
                (PVOID)(*(_QWORD *)(a4 + ((unsigned __int64)v40 << 6) + 96)
                      + *(unsigned int *)(((unsigned __int64)v40 << 6) + a4 + 108)),
                Flags,
                &BytesWritten,
                CallbackRoutine,
                CallbackContext);
        v6 = v42;
        if ( v42 != -1073741740 )
          break;
        Interval.QuadPart = -100000;
        KeDelayExecutionThread(0, 1u, &Interval);
      }
      CallbackRoutine = 0;
      if ( v42 < 0 )
        return v6;
      if ( (Flags & 8) != 0 )
        KeSetEvent((PRKEVENT)(a4 + ((unsigned __int64)*(unsigned int *)(a4 + 224) << 6) + 120), 0, 0);
    }
    v43 = *(unsigned int *)(a4 + 224);
    if ( v31 >= v32 )
      break;
    v44 = (unsigned __int64)(((_BYTE)v43 - 1) & 1) << 6;
    v45 = ((_BYTE)v43 - 1) & 1;
    if ( *(_QWORD *)(v44 + a4 + 96) )
    {
      LOBYTE(v34) = 1;
      FileProvWaitForWriteComplete(a4, ((_BYTE)v43 - 1) & 1, v34);
      if ( *(int *)(v44 + a4 + 112) < 0 )
      {
        v6 = *(_DWORD *)(v44 + a4 + 112);
        *(_DWORD *)(a4 + 224) = v45;
        return v6;
      }
    }
    else
    {
      PoolWithTag = ExAllocatePoolWithTag(PagedPool, 0x200000u, 0x44527066u);
      *(_QWORD *)(v44 + a4 + 96) = PoolWithTag;
      if ( !PoolWithTag )
        return (unsigned int)-1073741670;
      *(_QWORD *)(v44 + a4 + 104) = 0x200000;
      KeInitializeEvent((PRKEVENT)(v44 + a4 + 120), SynchronizationEvent, 0);
    }
    memmove(
      (void *)(*(_QWORD *)(v44 + a4 + 96) + *(unsigned int *)(v44 + a4 + 108)),
      (const void *)(*(_QWORD *)(((unsigned __int64)*(unsigned int *)(a4 + 224) << 6) + a4 + 96)
                   + (*(_DWORD *)(a4 + 48) & 0xFFFFF000)),
      *(_DWORD *)(a4 + 48) & 0xFFF);
    v8 = v54;
    v47 = *(_DWORD *)(a4 + 48) & 0xFFF;
    *(_DWORD *)(a4 + 224) = v45;
    v48 = *(_DWORD *)(v44 + a4 + 108) + v47;
    *(_DWORD *)(a4 + 48) = v48;
    v49 = *(_QWORD *)(v44 + a4 + 96) + v48;
    v5 = v55;
    *(_QWORD *)(a4 + 24) = v49;
  }
  if ( *(_DWORD *)((v43 << 6) + a4 + 108) < *(_DWORD *)(a4 + 48) )
  {
    v50 = (unsigned __int64)(((_BYTE)v43 - 1) & 1) << 6;
    v51 = ((_BYTE)v43 - 1) & 1;
    if ( *(_QWORD *)(a4 + v50 + 96) )
    {
      LOBYTE(v34) = 1;
      FileProvWaitForWriteComplete(a4, ((_BYTE)v43 - 1) & 1, v34);
      if ( *(int *)(a4 + v50 + 112) < 0 )
        v6 = *(_DWORD *)(a4 + v50 + 112);
    }
    *(_DWORD *)(a4 + 224) = v51;
  }
  return v6;
}

```

## disassembly

```asm
0x14003a6a8  mov     rax, rsp
0x14003a6ab  mov     [rax+8], rbx
0x14003a6af  mov     [rax+18h], r8d
0x14003a6b3  mov     [rax+10h], rdx
0x14003a6b7  push    rbp
0x14003a6b8  push    rsi
0x14003a6b9  push    rdi
0x14003a6ba  push    r12
0x14003a6bc  push    r13
0x14003a6be  push    r14
0x14003a6c0  push    r15
0x14003a6c2  sub     rsp, 60h
0x14003a6c6  xor     r13d, r13d
0x14003a6c9  mov     edi, r8d
0x14003a6cc  mov     esi, r13d
0x14003a6cf  mov     [rax+20h], r13d
0x14003a6d3  mov     rbx, r9
0x14003a6d6  mov     r8, rdx
0x14003a6d9  mov     r15, rcx
0x14003a6dc  test    edi, edi
0x14003a6de  jz      loc_14003A7E5
0x14003a6e4  mov     rax, [r15+8]
0x14003a6e8  cmp     [rbx+20h], rax
0x14003a6ec  jge     loc_14003A7AF
0x14003a6f2  mov     rax, [rbx+0F0h]
0x14003a6f9  mov     [rax+40h], r8
0x14003a6fd  mov     rax, [rbx+8]
0x14003a701  mov     rcx, [rbx+0F0h]
0x14003a708  mov     eax, [rax]
0x14003a70a  mov     [rcx+58h], eax
0x14003a70d  mov     rax, [rbx+20h]
0x14003a711  mov     rcx, [rbx+0F0h]
0x14003a718  mov     [rcx+38h], rax
0x14003a71c  mov     rax, [rbx+8]
0x14003a720  mov     ecx, [rax]
0x14003a722  add     [rbx+20h], rcx
0x14003a726  mov     rcx, [r15+8]
0x14003a72a  cmp     [rbx+20h], rcx
0x14003a72e  jle     short loc_14003A745
0x14003a730  mov     rdx, [rbx+0F0h]
0x14003a737  mov     [rbx+20h], rcx
0x14003a73b  mov     ecx, [r15+8]
0x14003a73f  sub     ecx, [rdx+38h]
0x14003a742  mov     [rdx+58h], ecx
0x14003a745  mov     rcx, [rbx+0F0h]
0x14003a74c  mov     eax, [rcx+58h]
0x14003a74f  add     r8, rax
0x14003a752  sub     edi, eax
0x14003a754  cmp     dword ptr [rbx+34h], 1
0x14003a758  mov     [rsp+98h+arg_8], r8
0x14003a760  mov     [rsp+98h+arg_10], edi
0x14003a767  jbe     short loc_14003A77A
0x14003a769  mov     edx, [rbx+38h]
0x14003a76c  add     edx, 20h ; ' '
0x14003a76f  call    WofTryQueueWorkItem
0x14003a774  test    al, al
0x14003a776  jz      short loc_14003A782
0x14003a778  jmp     short loc_14003A78E
0x14003a77a  mov     rax, [rbx+18h]
0x14003a77e  mov     [rcx+48h], rax
0x14003a782  mov     rcx, [rbx+0F0h]
0x14003a789  call    FileProvCompressWorkItem
0x14003a78e  mov     eax, [rbx+0FCh]
0x14003a794  xor     edx, edx
0x14003a796  inc     dword ptr [rbx+100h]
0x14003a79c  inc     eax
0x14003a79e  div     dword ptr [rbx+34h]
0x14003a7a1  mov     r8, [rsp+98h+arg_8]
0x14003a7a9  mov     [rbx+0FCh], edx
0x14003a7af  test    edi, edi
0x14003a7b1  jz      short loc_14003A7E5
0x14003a7b3  mov     rax, [r15+8]
0x14003a7b7  cmp     [rbx+20h], rax
0x14003a7bb  jge     short loc_14003A7E5
0x14003a7bd  mov     eax, [rbx+0FCh]
0x14003a7c3  cmp     eax, [rbx+0F8h]
0x14003a7c9  jz      short loc_14003A7E5
0x14003a7cb  imul    rcx, rax, 88h
0x14003a7d2  add     rcx, [rbx+0E8h]
0x14003a7d9  mov     [rbx+0F0h], rcx
0x14003a7e0  jmp     loc_14003A6DC
0x14003a7e5  mov     rdx, [rbx+0E8h]
0x14003a7ec  cmp     [rbx+100h], r13d
0x14003a7f3  jz      loc_14003AC33
0x14003a7f9  mov     eax, [rbx+0F8h]
0x14003a7ff  xor     r9d, r9d; Alertable
0x14003a802  imul    rcx, rax, 88h
0x14003a809  xor     r8d, r8d; WaitMode
0x14003a80c  mov     [rsp+98h+Timeout], r13; Timeout
0x14003a811  add     rcx, rdx
0x14003a814  xor     edx, edx; WaitReason
0x14003a816  mov     [rbx+0F0h], rcx
0x14003a81d  add     rcx, 60h ; '`'; Object
0x14003a821  call    cs:__imp_KeWaitForSingleObject
0x14003a828  nop     dword ptr [rax+rax+00h]
0x14003a82d  mov     eax, [rbx+0F8h]
0x14003a833  xor     edx, edx
0x14003a835  mov     r8d, [rbx+34h]
0x14003a839  inc     eax
0x14003a83b  dec     dword ptr [rbx+100h]
0x14003a841  div     r8d
0x14003a844  mov     rax, [rbx+0F0h]
0x14003a84b  mov     [rbx+0F8h], edx
0x14003a851  mov     ecx, [rax+80h]
0x14003a857  test    ecx, ecx
0x14003a859  js      loc_14003AC2F
0x14003a85f  cmp     r8d, 1
0x14003a863  jbe     short loc_14003A87D
0x14003a865  mov     r8d, [rax+5Ch]; Size
0x14003a869  mov     rdx, [rax+48h]; Src
0x14003a86d  mov     rcx, [rbx+18h]; void *
0x14003a871  call    memmove
0x14003a876  mov     rax, [rbx+0F0h]
0x14003a87d  mov     r10, [rbx+28h]
0x14003a881  test    r10, r10
0x14003a884  jle     short loc_14003A8B7
0x14003a886  mov     rax, [rax+38h]
0x14003a88a  mov     rcx, [rbx+8]
0x14003a88e  cqo
0x14003a890  mov     r9d, [rbx+10h]
0x14003a894  mov     r8d, [rcx]
0x14003a897  idiv    r8
0x14003a89a  mov     rdx, [rbx+60h]
0x14003a89e  dec     rax
0x14003a8a1  imul    rax, r9
0x14003a8a5  cmp     r9d, 4
0x14003a8a9  jnz     short loc_14003A8B3
0x14003a8ab  mov     ecx, r10d
0x14003a8ae  mov     [rax+rdx], ecx
0x14003a8b1  jmp     short loc_14003A8B7
0x14003a8b3  mov     [rax+rdx], r10
0x14003a8b7  mov     rcx, [rbx+0F0h]
0x14003a8be  mov     edx, [rbx+0E0h]
0x14003a8c4  shl     rdx, 6
0x14003a8c8  mov     eax, [rcx+5Ch]
0x14003a8cb  add     [rbx+28h], rax
0x14003a8cf  mov     eax, [rcx+5Ch]
0x14003a8d2  add     [rbx+30h], eax
0x14003a8d5  mov     r8d, [rbx+30h]
0x14003a8d9  mov     r11, [rbx+28h]
0x14003a8dd  mov     eax, r8d
0x14003a8e0  add     rax, [rdx+rbx+60h]
0x14003a8e5  mov     [rbx+18h], rax
0x14003a8e9  mov     rax, [rbx+8]
0x14003a8ed  mov     eax, [rax]
0x14003a8ef  add     eax, r8d
0x14003a8f2  cmp     eax, [rdx+rbx+68h]
0x14003a8f6  ja      short loc_14003A911
0x14003a8f8  mov     eax, [rcx+58h]
0x14003a8fb  add     rax, [rcx+38h]
0x14003a8ff  mov     r8, [rsp+98h+arg_8]
0x14003a907  cmp     rax, [r15+8]
0x14003a90b  jl      loc_14003A6DC
0x14003a911  mov     ebp, [rcx+58h]
0x14003a914  lea     rdi, [rbx+128h]
0x14003a91b  add     rbp, [rcx+38h]
0x14003a91f  mov     ecx, [rbx+14h]
0x14003a922  imul    ecx, [rbx+10h]
0x14003a926  mov     r14, [r15+8]
0x14003a92a  add     rcx, r11
0x14003a92d  mov     [rdi], rcx
0x14003a930  cmp     rbp, r14
0x14003a933  jge     short loc_14003A93F
0x14003a935  and     rcx, 0FFFFFFFFFFFFF000h
0x14003a93c  mov     [rdi], rcx
0x14003a93f  mov     rdx, [rbx+48h]; FileObject
0x14003a943  mov     r9d, 8; Length
0x14003a949  mov     rcx, [rbx+40h]; Instance
0x14003a94d  mov     r8, rdi; FileInformation
0x14003a950  mov     dword ptr [rsp+98h+Timeout], 14h; FileInformationClass
0x14003a958  call    cs:__imp_FltSetInformationFile
0x14003a95f  nop     dword ptr [rax+rax+00h]
0x14003a964  mov     esi, eax
0x14003a966  test    eax, eax
0x14003a968  js      loc_14003AC4A
0x14003a96e  cmp     rbp, r14
0x14003a971  jl      short loc_14003A988
0x14003a973  cmp     [rbx+0E0h], r13d
0x14003a97a  jnz     short loc_14003A988
0x14003a97c  mov     ecx, [rbx+68h]
0x14003a97f  cmp     [rdi], rcx
0x14003a982  jl      loc_14003ABD4
0x14003a988  mov     ecx, [rbx+14h]
0x14003a98b  imul    ecx, [rbx+10h]
0x14003a98f  mov     edx, [rbx+0E0h]
0x14003a995  shl     rdx, 6
0x14003a999  mov     eax, [rdx+rbx+6Ch]
0x14003a99d  add     rcx, rax
0x14003a9a0  mov     eax, [rbx+30h]
0x14003a9a3  sub     rcx, rax
0x14003a9a6  add     rcx, [rbx+28h]
0x14003a9aa  mov     [rdx+rbx+90h], rcx
0x14003a9b2  mov     ecx, [rbx+0E0h]
0x14003a9b8  mov     edx, [rbx+30h]
0x14003a9bb  shl     rcx, 6
0x14003a9bf  mov     eax, [rcx+rbx+6Ch]
0x14003a9c3  cmp     eax, edx
0x14003a9c5  jnb     loc_14003AAE6
0x14003a9cb  cmp     cs:VersionInformation.dwBuildNumber, 265Ch
0x14003a9d5  mov     r12d, 7
0x14003a9db  lea     r8d, [r12+8]
0x14003a9e0  cmovb   r12d, r8d
0x14003a9e4  sub     edx, eax
0x14003a9e6  cmp     rbp, r14
0x14003a9e9  mov     edi, r12d
0x14003a9ec  lea     eax, [rdx+0FFFh]
0x14003a9f2  cmovge  edx, eax
0x14003a9f5  lea     rax, FileProvSimpleCompletionRoutine
0x14003a9fc  and     edx, 0FFFFF000h
0x14003aa02  and     edi, 8
0x14003aa05  mov     [rcx+rbx+98h], edx
0x14003aa0c  cmovz   r13, rax
0x14003aa10  test    edi, edi
0x14003aa12  jz      short loc_14003AA1E
0x14003aa14  mov     ecx, [rbx+0E0h]
0x14003aa1a  xor     edx, edx
0x14003aa1c  jmp     short loc_14003AA31
0x14003aa1e  mov     ecx, [rbx+0E0h]
0x14003aa24  mov     edx, ecx
0x14003aa26  shl     rdx, 6
0x14003aa2a  add     rdx, 60h ; '`'
0x14003aa2e  add     rdx, rbx
0x14003aa31  mov     [rsp+98h+CallbackContext], rdx; CallbackContext
0x14003aa36  lea     r8, [rbx+90h]
0x14003aa3d  mov     rdx, [rbx+48h]; FileObject
0x14003aa41  mov     r9d, ecx
0x14003aa44  lea     rcx, [rsp+98h+arg_18]
0x14003aa4c  shl     r9, 6
0x14003aa50  mov     [rsp+98h+CallbackRoutine], r13; CallbackRoutine
0x14003aa55  add     r8, r9; ByteOffset
0x14003aa58  mov     [rsp+98h+BytesWritten], rcx; BytesWritten
0x14003aa5d  mov     rcx, [rbx+40h]; InitiatingInstance
0x14003aa61  mov     eax, [r9+rbx+6Ch]
0x14003aa66  add     rax, [rbx+r9+60h]
0x14003aa6b  mov     r9d, [r9+rbx+98h]; Length
0x14003aa73  mov     [rsp+98h+Flags], r12d; Flags
0x14003aa78  mov     [rsp+98h+Timeout], rax; Buffer
0x14003aa7d  call    cs:__imp_FltWriteFile
0x14003aa84  nop     dword ptr [rax+rax+00h]
0x14003aa89  mov     esi, eax
0x14003aa8b  cmp     eax, 0C0000054h
0x14003aa90  jnz     short loc_14003AAB5
0x14003aa92  lea     r8, [rsp+98h+Interval]; Interval
0x14003aa97  mov     qword ptr [rsp+98h+Interval], 0FFFFFFFFFFFE7960h
0x14003aaa0  mov     dl, 1; Alertable
0x14003aaa2  xor     ecx, ecx; WaitMode
0x14003aaa4  call    cs:__imp_KeDelayExecutionThread
0x14003aaab  nop     dword ptr [rax+rax+00h]
0x14003aab0  jmp     loc_14003AA10
0x14003aab5  xor     r13d, r13d
0x14003aab8  test    eax, eax
0x14003aaba  js      loc_14003AC4A
0x14003aac0  test    edi, edi
0x14003aac2  jz      short loc_14003AAE6
0x14003aac4  mov     ecx, [rbx+0E0h]
0x14003aaca  xor     r8d, r8d; Wait
0x14003aacd  shl     rcx, 6
0x14003aad1  xor     edx, edx; Increment
0x14003aad3  add     rcx, 78h ; 'x'
0x14003aad7  add     rcx, rbx; Event
0x14003aada  call    cs:__imp_KeSetEvent
0x14003aae1  nop     dword ptr [rax+rax+00h]
0x14003aae6  mov     edx, [rbx+0E0h]
0x14003aaec  cmp     rbp, r14
0x14003aaef  jge     loc_14003ABEB
0x14003aaf5  lea     eax, [rdx-1]
0x14003aaf8  and     eax, 1
0x14003aafb  mov     edi, eax
0x14003aafd  shl     rdi, 6
0x14003ab01  mov     ebp, eax
0x14003ab03  cmp     [rdi+rbx+60h], r13
0x14003ab08  jnz     short loc_14003AB59
0x14003ab0a  mov     edx, 200000h; NumberOfBytes
0x14003ab0f  mov     ecx, 1; PoolType
0x14003ab14  mov     r8d, 44527066h; Tag
0x14003ab1a  call    cs:__imp_ExAllocatePoolWithTag
0x14003ab21  nop     dword ptr [rax+rax+00h]
0x14003ab26  mov     [rdi+rbx+60h], rax
0x14003ab2b  test    rax, rax
0x14003ab2e  jz      loc_14003ABDA
0x14003ab34  xor     r8d, r8d; State
0x14003ab37  mov     qword ptr [rdi+rbx+68h], 200000h
0x14003ab40  lea     rcx, [rbx+78h]
0x14003ab44  add     rcx, rdi; Event
0x14003ab47  lea     edx, [r8+1]; Type
0x14003ab4b  call    cs:__imp_KeInitializeEvent
0x14003ab52  nop     dword ptr [rax+rax+00h]
0x14003ab57  jmp     short loc_14003AB6E
0x14003ab59  mov     r8b, 1
0x14003ab5c  mov     edx, ebp
0x14003ab5e  mov     rcx, rbx
0x14003ab61  call    FileProvWaitForWriteComplete
0x14003ab66  mov     eax, [rdi+rbx+70h]
0x14003ab6a  test    eax, eax
0x14003ab6c  js      short loc_14003ABE1
0x14003ab6e  mov     edx, [rbx+30h]
0x14003ab71  mov     eax, [rbx+0E0h]
0x14003ab77  mov     r8d, edx
0x14003ab7a  mov     ecx, [rdi+rbx+6Ch]
0x14003ab7e  and     rdx, 0FFFFFFFFFFFFF000h
  ... truncated ...
```
