# FileProvReadCompressed

- ea: `0x140038760`
- end: `0x140038b01`
- name: `FileProvReadCompressed`
- size: `929`
- prototype: `__int64 __fastcall(LARGE_INTEGER, void *, __int64, __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400382b0`
- `0x140038b10`

## callees

- `0x140001570`
- `0x1400078a0`
- `0x140009a50`
- `0x14000d3b8`
- `0x14000fb60`
- `0x14001112c`
- `0x140038760`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x140038941`
- `ntoskrnl!KeWaitForSingleObject` at `0x140038941`
- `ntoskrnl!KeAreAllApcsDisabled` at `0x140038894`
- `ntoskrnl!KeAreAllApcsDisabled` at `0x140038894`
- `ntoskrnl!KeInitializeEvent` at `0x1400388e8`
- `ntoskrnl!KeInitializeEvent` at `0x140038a15`
- `ntoskrnl!KeInitializeEvent` at `0x1400388e8`
- `ntoskrnl!KeInitializeEvent` at `0x140038a15`
- `FLTMGR!FltIsOperationSynchronous` at `0x14003898b`
- `FLTMGR!FltIsOperationSynchronous` at `0x14003898b`
- `FLTMGR!FltSetIoPriorityHintIntoCallbackData` at `0x140038888`
- `FLTMGR!FltSetIoPriorityHintIntoCallbackData` at `0x140038888`
- `FLTMGR!FltPerformAsynchronousIo` at `0x1400389d0`
- `FLTMGR!FltPerformAsynchronousIo` at `0x1400389d0`
- `FLTMGR!FltPerformSynchronousIo` at `0x1400388f9`
- `FLTMGR!FltPerformSynchronousIo` at `0x1400388f9`
- `FLTMGR!FltAllocateCallbackDataEx` at `0x1400387f4`
- `FLTMGR!FltAllocateCallbackDataEx` at `0x1400387f4`
- `FLTMGR!FltPropagateIrpExtension` at `0x140038816`
- `FLTMGR!FltPropagateIrpExtension` at `0x140038816`
- `FLTMGR!FltFreeCallbackData` at `0x1400389e6`
- `FLTMGR!FltFreeCallbackData` at `0x1400389e6`

## pseudocode

```c
__int64 __fastcall FileProvReadCompressed(LARGE_INTEGER a1, void *a2, __int64 a3, __int64 a4)
{
  struct _FLT_INSTANCE *v4; // rdi
  __int64 v5; // r15
  ULONG v7; // esi
  int v10; // eax
  NTSTATUS v11; // edi
  PFLT_CALLBACK_DATA v12; // rax
  PFLT_CALLBACK_DATA RetNewCallbackData; // [rsp+60h] [rbp+8h] BYREF

  v4 = *(struct _FLT_INSTANCE **)(a4 + 40);
  v5 = *(_QWORD *)(a4 + 56);
  RetNewCallbackData = 0;
  v7 = a3;
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 43, WPP_3b099794e4b93327e327da255c047df6_Traceguids);
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD))WPP_SF_iqD)(
      WPP_GLOBAL_Control->AttachedDevice,
      a2,
      a3,
      (LARGE_INTEGER)a1.QuadPart,
      a2,
      v7);
  v10 = *(_DWORD *)(a4 + 100);
  *(_DWORD *)(a4 + 76) = 0;
  if ( (v10 & 1) != 0 )
  {
    *(_BYTE *)(a4 + 137) = 1;
    KeInitializeEvent((PRKEVENT)(a4 + 144), SynchronizationEvent, 0);
  }
  else
  {
    *(_BYTE *)(a4 + 137) = 0;
  }
  *(_DWORD *)(a4 + 112) = v7;
  *(LARGE_INTEGER *)(a4 + 120) = a1;
  *(_QWORD *)(a4 + 128) = a2;
  FileProvReferenceReadCompletionContext(a4);
  v11 = FltAllocateCallbackDataEx(v4, *(PFILE_OBJECT *)(v5 + 40), 1u, &RetNewCallbackData);
  if ( v11 < 0 )
    goto LABEL_22;
  v11 = FltPropagateIrpExtension(*(_QWORD *)(a4 + 24), RetNewCallbackData, 0);
  if ( v11 < 0 )
  {
    FltFreeCallbackData(RetNewCallbackData);
LABEL_22:
    FileProvReleaseReadCompletionContext((PVOID)a4);
    goto LABEL_15;
  }
  v12 = RetNewCallbackData;
  *(_BYTE *)(a4 + 136) = 1;
  v12->Iopb->MajorFunction = 3;
  RetNewCallbackData->Iopb->Parameters.Read.ByteOffset = a1;
  RetNewCallbackData->Iopb->Parameters.Read.Length = v7;
  RetNewCallbackData->Iopb->Parameters.Create.Options = 0;
  RetNewCallbackData->Iopb->Parameters.Create.EaBuffer = 0;
  RetNewCallbackData->Iopb->Parameters.CreatePipe.Parameters = a2;
  FltSetIoPriorityHintIntoCallbackData(RetNewCallbackData, *(IO_PRIORITY_HINT *)(a4 + 88));
  if ( KeAreAllApcsDisabled()
    || (*(_DWORD *)(a4 + 100) & 1) != 0
    || FltIsOperationSynchronous(*(PFLT_CALLBACK_DATA *)(a4 + 24)) )
  {
    RetNewCallbackData->Iopb->IrpFlags |= 0x143u;
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 45, WPP_3b099794e4b93327e327da255c047df6_Traceguids);
    if ( !*(_BYTE *)(a4 + 137) )
    {
      *(_BYTE *)(a4 + 137) = 1;
      KeInitializeEvent((PRKEVENT)(a4 + 144), SynchronizationEvent, 0);
    }
    FltPerformSynchronousIo(RetNewCallbackData);
    FileProvReadCompressedCompletion(RetNewCallbackData, (PVOID *)a4);
  }
  else
  {
    v11 = 259;
    RetNewCallbackData->Iopb->IrpFlags |= 0x103u;
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 46, WPP_3b099794e4b93327e327da255c047df6_Traceguids);
    FltPerformAsynchronousIo(
      RetNewCallbackData,
      (PFLT_COMPLETED_ASYNC_IO_CALLBACK)FileProvReadCompressedCompletion,
      (PVOID)a4);
  }
  if ( *(_BYTE *)(a4 + 137) )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 47, WPP_3b099794e4b93327e327da255c047df6_Traceguids);
    KeWaitForSingleObject((PVOID)(a4 + 144), Executive, 0, 0, 0);
    v11 = *(_DWORD *)(a4 + 8);
  }
LABEL_15:
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 48, WPP_3b099794e4b93327e327da255c047df6_Traceguids, (unsigned int)v11);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x140038760  mov     [rsp+arg_8], rbx
0x140038765  mov     [rsp+arg_10], rbp
0x14003876a  push    rsi
0x14003876b  push    rdi
0x14003876c  push    r12
0x14003876e  push    r14
0x140038770  push    r15
0x140038772  sub     rsp, 30h
0x140038776  mov     rdi, [r9+28h]
0x14003877a  xor     r12d, r12d
0x14003877d  mov     r15, [r9+38h]
0x140038781  mov     rbx, r9
0x140038784  mov     [rsp+58h+RetNewCallbackData], r12
0x140038789  mov     esi, r8d
0x14003878c  mov     rbp, rdx
0x14003878f  mov     r14, rcx
0x140038792  mov     rcx, cs:WPP_GLOBAL_Control
0x140038799  mov     eax, [rcx+2Ch]
0x14003879c  test    al, 20h
0x14003879e  jnz     loc_140038A26
0x1400387a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400387ab  mov     eax, [rcx+2Ch]
0x1400387ae  test    al, 20h
0x1400387b0  jnz     loc_140038A4A
0x1400387b6  mov     eax, [rbx+64h]
0x1400387b9  mov     [rbx+4Ch], r12d
0x1400387bd  test    al, 1
0x1400387bf  jnz     loc_1400389FF
0x1400387c5  mov     [rbx+89h], r12b
0x1400387cc  mov     rcx, rbx
0x1400387cf  mov     [rbx+70h], esi
0x1400387d2  mov     [rbx+78h], r14
0x1400387d6  mov     [rbx+80h], rbp
0x1400387dd  call    FileProvReferenceReadCompletionContext
0x1400387e2  mov     rdx, [r15+28h]; FileObject
0x1400387e6  lea     r9, [rsp+58h+RetNewCallbackData]; RetNewCallbackData
0x1400387eb  mov     r8d, 1; Flags
0x1400387f1  mov     rcx, rdi; Instance
0x1400387f4  call    cs:__imp_FltAllocateCallbackDataEx
0x1400387fb  nop     dword ptr [rax+rax+00h]
0x140038800  mov     edi, eax
0x140038802  test    eax, eax
0x140038804  js      loc_1400389F2
0x14003880a  mov     rdx, [rsp+58h+RetNewCallbackData]
0x14003880f  xor     r8d, r8d
0x140038812  mov     rcx, [rbx+18h]
0x140038816  call    cs:__imp_FltPropagateIrpExtension
0x14003881d  nop     dword ptr [rax+rax+00h]
0x140038822  mov     edi, eax
0x140038824  test    eax, eax
0x140038826  js      loc_1400389E1
0x14003882c  mov     rax, [rsp+58h+RetNewCallbackData]
0x140038831  mov     byte ptr [rbx+88h], 1
0x140038838  mov     rcx, [rax+10h]
0x14003883c  mov     byte ptr [rcx+4], 3
0x140038840  mov     rax, [rsp+58h+RetNewCallbackData]
0x140038845  mov     rcx, [rax+10h]
0x140038849  mov     [rcx+28h], r14
0x14003884d  mov     rax, [rsp+58h+RetNewCallbackData]
0x140038852  mov     rcx, [rax+10h]
0x140038856  mov     [rcx+18h], esi
0x140038859  mov     rax, [rsp+58h+RetNewCallbackData]
0x14003885e  mov     rcx, [rax+10h]
0x140038862  mov     [rcx+20h], r12d
0x140038866  mov     rax, [rsp+58h+RetNewCallbackData]
0x14003886b  mov     rcx, [rax+10h]
0x14003886f  mov     [rcx+38h], r12
0x140038873  mov     rax, [rsp+58h+RetNewCallbackData]
0x140038878  mov     rcx, [rax+10h]
0x14003887c  mov     [rcx+30h], rbp
0x140038880  mov     edx, [rbx+58h]; PriorityHint
0x140038883  mov     rcx, [rsp+58h+RetNewCallbackData]; Data
0x140038888  call    cs:__imp_FltSetIoPriorityHintIntoCallbackData
0x14003888f  nop     dword ptr [rax+rax+00h]
0x140038894  call    cs:__imp_KeAreAllApcsDisabled
0x14003889b  nop     dword ptr [rax+rax+00h]
0x1400388a0  test    al, al
0x1400388a2  jz      loc_14003897C
0x1400388a8  mov     rax, [rsp+58h+RetNewCallbackData]
0x1400388ad  mov     rcx, [rax+10h]
0x1400388b1  or      dword ptr [rcx], 143h
0x1400388b7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400388be  mov     eax, [rcx+2Ch]
0x1400388c1  test    al, 20h
0x1400388c3  jnz     loc_140038A92
0x1400388c9  cmp     [rbx+89h], r12b
0x1400388d0  jnz     short loc_1400388F4
0x1400388d2  lea     rcx, [rbx+90h]; Event
0x1400388d9  mov     byte ptr [rbx+89h], 1
0x1400388e0  xor     r8d, r8d; State
0x1400388e3  mov     edx, 1; Type
0x1400388e8  call    cs:__imp_KeInitializeEvent
0x1400388ef  nop     dword ptr [rax+rax+00h]
0x1400388f4  mov     rcx, [rsp+58h+RetNewCallbackData]; CallbackData
0x1400388f9  call    cs:__imp_FltPerformSynchronousIo
0x140038900  nop     dword ptr [rax+rax+00h]
0x140038905  mov     rcx, [rsp+58h+RetNewCallbackData]; CallbackData
0x14003890a  mov     rdx, rbx; Context
0x14003890d  call    FileProvReadCompressedCompletion
0x140038912  cmp     [rbx+89h], r12b
0x140038919  jz      short loc_140038950
0x14003891b  mov     rcx, cs:WPP_GLOBAL_Control
0x140038922  mov     eax, [rcx+2Ch]
0x140038925  test    al, 20h
0x140038927  jnz     loc_140038AB6
0x14003892d  lea     rcx, [rbx+90h]; Object
0x140038934  mov     [rsp+58h+Timeout], r12; Timeout
0x140038939  xor     r9d, r9d; Alertable
0x14003893c  xor     r8d, r8d; WaitMode
0x14003893f  xor     edx, edx; WaitReason
0x140038941  call    cs:__imp_KeWaitForSingleObject
0x140038948  nop     dword ptr [rax+rax+00h]
0x14003894d  mov     edi, [rbx+8]
0x140038950  mov     rcx, cs:WPP_GLOBAL_Control
0x140038957  mov     eax, [rcx+2Ch]
0x14003895a  test    al, 20h
0x14003895c  jnz     loc_140038ADA
0x140038962  mov     rbx, [rsp+58h+arg_8]
0x140038967  mov     eax, edi
0x140038969  mov     rbp, [rsp+58h+arg_10]
0x14003896e  add     rsp, 30h
0x140038972  pop     r15
0x140038974  pop     r14
0x140038976  pop     r12
0x140038978  pop     rdi
0x140038979  pop     rsi
0x14003897a  retn
0x14003897c  mov     eax, [rbx+64h]
0x14003897f  test    al, 1
0x140038981  jnz     loc_1400388A8
0x140038987  mov     rcx, [rbx+18h]; CallbackData
0x14003898b  call    cs:__imp_FltIsOperationSynchronous
0x140038992  nop     dword ptr [rax+rax+00h]
0x140038997  test    al, al
0x140038999  jnz     loc_1400388A8
0x14003899f  mov     rax, [rsp+58h+RetNewCallbackData]
0x1400389a4  mov     edi, 103h
0x1400389a9  mov     rcx, [rax+10h]
0x1400389ad  or      [rcx], edi
0x1400389af  mov     rcx, cs:WPP_GLOBAL_Control
0x1400389b6  mov     eax, [rcx+2Ch]
0x1400389b9  test    al, 20h
0x1400389bb  jnz     loc_140038A6E
0x1400389c1  mov     rcx, [rsp+58h+RetNewCallbackData]; CallbackData
0x1400389c6  lea     rdx, FileProvReadCompressedCompletion; CallbackRoutine
0x1400389cd  mov     r8, rbx; CallbackContext
0x1400389d0  call    cs:__imp_FltPerformAsynchronousIo
0x1400389d7  nop     dword ptr [rax+rax+00h]
0x1400389dc  jmp     loc_140038912
0x1400389e1  mov     rcx, [rsp+58h+RetNewCallbackData]; CallbackData
0x1400389e6  call    cs:__imp_FltFreeCallbackData
0x1400389ed  nop     dword ptr [rax+rax+00h]
0x1400389f2  mov     rcx, rbx; Entry
0x1400389f5  call    FileProvReleaseReadCompletionContext
0x1400389fa  jmp     loc_140038950
0x1400389ff  lea     rcx, [rbx+90h]; Event
0x140038a06  mov     byte ptr [rbx+89h], 1
0x140038a0d  xor     r8d, r8d; State
0x140038a10  mov     edx, 1; Type
0x140038a15  call    cs:__imp_KeInitializeEvent
0x140038a1c  nop     dword ptr [rax+rax+00h]
0x140038a21  jmp     loc_1400387CC
0x140038a26  cmp     byte ptr [rcx+29h], 4
0x140038a2a  jb      loc_1400387A4
0x140038a30  mov     rcx, [rcx+18h]
0x140038a34  lea     r8, WPP_3b099794e4b93327e327da255c047df6_Traceguids
0x140038a3b  mov     edx, 2Bh ; '+'
0x140038a40  call    WPP_SF_
0x140038a45  jmp     loc_1400387A4
0x140038a4a  cmp     byte ptr [rcx+29h], 5
0x140038a4e  jb      loc_1400387B6
0x140038a54  mov     rcx, [rcx+18h]
0x140038a58  mov     r9, r14
0x140038a5b  mov     [rsp+58h+var_30], esi
0x140038a5f  mov     [rsp+58h+Timeout], rbp
0x140038a64  call    WPP_SF_iqD
0x140038a69  jmp     loc_1400387B6
0x140038a6e  cmp     byte ptr [rcx+29h], 5
0x140038a72  jb      loc_1400389C1
0x140038a78  mov     rcx, [rcx+18h]
0x140038a7c  lea     r8, WPP_3b099794e4b93327e327da255c047df6_Traceguids
0x140038a83  mov     edx, 2Eh ; '.'
0x140038a88  call    WPP_SF_
0x140038a8d  jmp     loc_1400389C1
0x140038a92  cmp     byte ptr [rcx+29h], 5
0x140038a96  jb      loc_1400388C9
0x140038a9c  mov     rcx, [rcx+18h]
0x140038aa0  lea     r8, WPP_3b099794e4b93327e327da255c047df6_Traceguids
0x140038aa7  mov     edx, 2Dh ; '-'
0x140038aac  call    WPP_SF_
0x140038ab1  jmp     loc_1400388C9
0x140038ab6  cmp     byte ptr [rcx+29h], 5
0x140038aba  jb      loc_14003892D
0x140038ac0  mov     rcx, [rcx+18h]
0x140038ac4  lea     r8, WPP_3b099794e4b93327e327da255c047df6_Traceguids
0x140038acb  mov     edx, 2Fh ; '/'
0x140038ad0  call    WPP_SF_
0x140038ad5  jmp     loc_14003892D
0x140038ada  cmp     byte ptr [rcx+29h], 4
0x140038ade  jb      loc_140038962
0x140038ae4  mov     rcx, [rcx+18h]
0x140038ae8  lea     r8, WPP_3b099794e4b93327e327da255c047df6_Traceguids
0x140038aef  mov     edx, 30h ; '0'
0x140038af4  mov     r9d, edi
0x140038af7  call    WPP_SF_d
0x140038afc  jmp     loc_140038962
```
