# FileProvReadCompressed

- ea: `0x140038710`
- end: `0x140038ab1`
- name: `FileProvReadCompressed`
- size: `929`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140038260`
- `0x140038ac0`

## callees

- `0x140001570`
- `0x1400078a0`
- `0x140009a50`
- `0x14000d3b8`
- `0x14000fb60`
- `0x14001112c`
- `0x140038710`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x1400388f1`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400388f1`
- `ntoskrnl!KeAreAllApcsDisabled` at `0x140038844`
- `ntoskrnl!KeAreAllApcsDisabled` at `0x140038844`
- `ntoskrnl!KeInitializeEvent` at `0x140038898`
- `ntoskrnl!KeInitializeEvent` at `0x1400389c5`
- `ntoskrnl!KeInitializeEvent` at `0x140038898`
- `ntoskrnl!KeInitializeEvent` at `0x1400389c5`
- `FLTMGR!FltIsOperationSynchronous` at `0x14003893b`
- `FLTMGR!FltIsOperationSynchronous` at `0x14003893b`
- `FLTMGR!FltSetIoPriorityHintIntoCallbackData` at `0x140038838`
- `FLTMGR!FltSetIoPriorityHintIntoCallbackData` at `0x140038838`
- `FLTMGR!FltPerformAsynchronousIo` at `0x140038980`
- `FLTMGR!FltPerformAsynchronousIo` at `0x140038980`
- `FLTMGR!FltPerformSynchronousIo` at `0x1400388a9`
- `FLTMGR!FltPerformSynchronousIo` at `0x1400388a9`
- `FLTMGR!FltAllocateCallbackDataEx` at `0x1400387a4`
- `FLTMGR!FltAllocateCallbackDataEx` at `0x1400387a4`
- `FLTMGR!FltPropagateIrpExtension` at `0x1400387c6`
- `FLTMGR!FltPropagateIrpExtension` at `0x1400387c6`
- `FLTMGR!FltFreeCallbackData` at `0x140038996`
- `FLTMGR!FltFreeCallbackData` at `0x140038996`

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
    FileProvReleaseReadCompletionContext((volatile signed __int32 *)a4);
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
    FileProvReadCompressedCompletion(RetNewCallbackData, (PFLT_CONTEXT)a4);
  }
  else
  {
    v11 = 259;
    RetNewCallbackData->Iopb->IrpFlags |= 0x103u;
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 46, WPP_3b099794e4b93327e327da255c047df6_Traceguids);
    FltPerformAsynchronousIo(RetNewCallbackData, FileProvReadCompressedCompletion, (PVOID)a4);
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
0x140038710  mov     [rsp+arg_8], rbx
0x140038715  mov     [rsp+arg_10], rbp
0x14003871a  push    rsi
0x14003871b  push    rdi
0x14003871c  push    r12
0x14003871e  push    r14
0x140038720  push    r15
0x140038722  sub     rsp, 30h
0x140038726  mov     rdi, [r9+28h]
0x14003872a  xor     r12d, r12d
0x14003872d  mov     r15, [r9+38h]
0x140038731  mov     rbx, r9
0x140038734  mov     [rsp+58h+RetNewCallbackData], r12
0x140038739  mov     esi, r8d
0x14003873c  mov     rbp, rdx
0x14003873f  mov     r14, rcx
0x140038742  mov     rcx, cs:WPP_GLOBAL_Control
0x140038749  mov     eax, [rcx+2Ch]
0x14003874c  test    al, 20h
0x14003874e  jnz     loc_1400389D6
0x140038754  mov     rcx, cs:WPP_GLOBAL_Control
0x14003875b  mov     eax, [rcx+2Ch]
0x14003875e  test    al, 20h
0x140038760  jnz     loc_1400389FA
0x140038766  mov     eax, [rbx+64h]
0x140038769  mov     [rbx+4Ch], r12d
0x14003876d  test    al, 1
0x14003876f  jnz     loc_1400389AF
0x140038775  mov     [rbx+89h], r12b
0x14003877c  mov     rcx, rbx
0x14003877f  mov     [rbx+70h], esi
0x140038782  mov     [rbx+78h], r14
0x140038786  mov     [rbx+80h], rbp
0x14003878d  call    FileProvReferenceReadCompletionContext
0x140038792  mov     rdx, [r15+28h]; FileObject
0x140038796  lea     r9, [rsp+58h+RetNewCallbackData]; RetNewCallbackData
0x14003879b  mov     r8d, 1; Flags
0x1400387a1  mov     rcx, rdi; Instance
0x1400387a4  call    cs:__imp_FltAllocateCallbackDataEx
0x1400387ab  nop     dword ptr [rax+rax+00h]
0x1400387b0  mov     edi, eax
0x1400387b2  test    eax, eax
0x1400387b4  js      loc_1400389A2
0x1400387ba  mov     rdx, [rsp+58h+RetNewCallbackData]
0x1400387bf  xor     r8d, r8d
0x1400387c2  mov     rcx, [rbx+18h]
0x1400387c6  call    cs:__imp_FltPropagateIrpExtension
0x1400387cd  nop     dword ptr [rax+rax+00h]
0x1400387d2  mov     edi, eax
0x1400387d4  test    eax, eax
0x1400387d6  js      loc_140038991
0x1400387dc  mov     rax, [rsp+58h+RetNewCallbackData]
0x1400387e1  mov     byte ptr [rbx+88h], 1
0x1400387e8  mov     rcx, [rax+10h]
0x1400387ec  mov     byte ptr [rcx+4], 3
0x1400387f0  mov     rax, [rsp+58h+RetNewCallbackData]
0x1400387f5  mov     rcx, [rax+10h]
0x1400387f9  mov     [rcx+28h], r14
0x1400387fd  mov     rax, [rsp+58h+RetNewCallbackData]
0x140038802  mov     rcx, [rax+10h]
0x140038806  mov     [rcx+18h], esi
0x140038809  mov     rax, [rsp+58h+RetNewCallbackData]
0x14003880e  mov     rcx, [rax+10h]
0x140038812  mov     [rcx+20h], r12d
0x140038816  mov     rax, [rsp+58h+RetNewCallbackData]
0x14003881b  mov     rcx, [rax+10h]
0x14003881f  mov     [rcx+38h], r12
0x140038823  mov     rax, [rsp+58h+RetNewCallbackData]
0x140038828  mov     rcx, [rax+10h]
0x14003882c  mov     [rcx+30h], rbp
0x140038830  mov     edx, [rbx+58h]; PriorityHint
0x140038833  mov     rcx, [rsp+58h+RetNewCallbackData]; Data
0x140038838  call    cs:__imp_FltSetIoPriorityHintIntoCallbackData
0x14003883f  nop     dword ptr [rax+rax+00h]
0x140038844  call    cs:__imp_KeAreAllApcsDisabled
0x14003884b  nop     dword ptr [rax+rax+00h]
0x140038850  test    al, al
0x140038852  jz      loc_14003892C
0x140038858  mov     rax, [rsp+58h+RetNewCallbackData]
0x14003885d  mov     rcx, [rax+10h]
0x140038861  or      dword ptr [rcx], 143h
0x140038867  mov     rcx, cs:WPP_GLOBAL_Control
0x14003886e  mov     eax, [rcx+2Ch]
0x140038871  test    al, 20h
0x140038873  jnz     loc_140038A42
0x140038879  cmp     [rbx+89h], r12b
0x140038880  jnz     short loc_1400388A4
0x140038882  lea     rcx, [rbx+90h]; Event
0x140038889  mov     byte ptr [rbx+89h], 1
0x140038890  xor     r8d, r8d; State
0x140038893  mov     edx, 1; Type
0x140038898  call    cs:__imp_KeInitializeEvent
0x14003889f  nop     dword ptr [rax+rax+00h]
0x1400388a4  mov     rcx, [rsp+58h+RetNewCallbackData]; CallbackData
0x1400388a9  call    cs:__imp_FltPerformSynchronousIo
0x1400388b0  nop     dword ptr [rax+rax+00h]
0x1400388b5  mov     rcx, [rsp+58h+RetNewCallbackData]; CallbackData
0x1400388ba  mov     rdx, rbx; Context
0x1400388bd  call    FileProvReadCompressedCompletion
0x1400388c2  cmp     [rbx+89h], r12b
0x1400388c9  jz      short loc_140038900
0x1400388cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1400388d2  mov     eax, [rcx+2Ch]
0x1400388d5  test    al, 20h
0x1400388d7  jnz     loc_140038A66
0x1400388dd  lea     rcx, [rbx+90h]; Object
0x1400388e4  mov     [rsp+58h+Timeout], r12; Timeout
0x1400388e9  xor     r9d, r9d; Alertable
0x1400388ec  xor     r8d, r8d; WaitMode
0x1400388ef  xor     edx, edx; WaitReason
0x1400388f1  call    cs:__imp_KeWaitForSingleObject
0x1400388f8  nop     dword ptr [rax+rax+00h]
0x1400388fd  mov     edi, [rbx+8]
0x140038900  mov     rcx, cs:WPP_GLOBAL_Control
0x140038907  mov     eax, [rcx+2Ch]
0x14003890a  test    al, 20h
0x14003890c  jnz     loc_140038A8A
0x140038912  mov     rbx, [rsp+58h+arg_8]
0x140038917  mov     eax, edi
0x140038919  mov     rbp, [rsp+58h+arg_10]
0x14003891e  add     rsp, 30h
0x140038922  pop     r15
0x140038924  pop     r14
0x140038926  pop     r12
0x140038928  pop     rdi
0x140038929  pop     rsi
0x14003892a  retn
0x14003892c  mov     eax, [rbx+64h]
0x14003892f  test    al, 1
0x140038931  jnz     loc_140038858
0x140038937  mov     rcx, [rbx+18h]; CallbackData
0x14003893b  call    cs:__imp_FltIsOperationSynchronous
0x140038942  nop     dword ptr [rax+rax+00h]
0x140038947  test    al, al
0x140038949  jnz     loc_140038858
0x14003894f  mov     rax, [rsp+58h+RetNewCallbackData]
0x140038954  mov     edi, 103h
0x140038959  mov     rcx, [rax+10h]
0x14003895d  or      [rcx], edi
0x14003895f  mov     rcx, cs:WPP_GLOBAL_Control
0x140038966  mov     eax, [rcx+2Ch]
0x140038969  test    al, 20h
0x14003896b  jnz     loc_140038A1E
0x140038971  mov     rcx, [rsp+58h+RetNewCallbackData]; CallbackData
0x140038976  lea     rdx, FileProvReadCompressedCompletion; CallbackRoutine
0x14003897d  mov     r8, rbx; CallbackContext
0x140038980  call    cs:__imp_FltPerformAsynchronousIo
0x140038987  nop     dword ptr [rax+rax+00h]
0x14003898c  jmp     loc_1400388C2
0x140038991  mov     rcx, [rsp+58h+RetNewCallbackData]; CallbackData
0x140038996  call    cs:__imp_FltFreeCallbackData
0x14003899d  nop     dword ptr [rax+rax+00h]
0x1400389a2  mov     rcx, rbx; Entry
0x1400389a5  call    FileProvReleaseReadCompletionContext
0x1400389aa  jmp     loc_140038900
0x1400389af  lea     rcx, [rbx+90h]; Event
0x1400389b6  mov     byte ptr [rbx+89h], 1
0x1400389bd  xor     r8d, r8d; State
0x1400389c0  mov     edx, 1; Type
0x1400389c5  call    cs:__imp_KeInitializeEvent
0x1400389cc  nop     dword ptr [rax+rax+00h]
0x1400389d1  jmp     loc_14003877C
0x1400389d6  cmp     byte ptr [rcx+29h], 4
0x1400389da  jb      loc_140038754
0x1400389e0  mov     rcx, [rcx+18h]
0x1400389e4  lea     r8, WPP_3b099794e4b93327e327da255c047df6_Traceguids
0x1400389eb  mov     edx, 2Bh ; '+'
0x1400389f0  call    WPP_SF_
0x1400389f5  jmp     loc_140038754
0x1400389fa  cmp     byte ptr [rcx+29h], 5
0x1400389fe  jb      loc_140038766
0x140038a04  mov     rcx, [rcx+18h]
0x140038a08  mov     r9, r14
0x140038a0b  mov     [rsp+58h+var_30], esi
0x140038a0f  mov     [rsp+58h+Timeout], rbp
0x140038a14  call    WPP_SF_iqD
0x140038a19  jmp     loc_140038766
0x140038a1e  cmp     byte ptr [rcx+29h], 5
0x140038a22  jb      loc_140038971
0x140038a28  mov     rcx, [rcx+18h]
0x140038a2c  lea     r8, WPP_3b099794e4b93327e327da255c047df6_Traceguids
0x140038a33  mov     edx, 2Eh ; '.'
0x140038a38  call    WPP_SF_
0x140038a3d  jmp     loc_140038971
0x140038a42  cmp     byte ptr [rcx+29h], 5
0x140038a46  jb      loc_140038879
0x140038a4c  mov     rcx, [rcx+18h]
0x140038a50  lea     r8, WPP_3b099794e4b93327e327da255c047df6_Traceguids
0x140038a57  mov     edx, 2Dh ; '-'
0x140038a5c  call    WPP_SF_
0x140038a61  jmp     loc_140038879
0x140038a66  cmp     byte ptr [rcx+29h], 5
0x140038a6a  jb      loc_1400388DD
0x140038a70  mov     rcx, [rcx+18h]
0x140038a74  lea     r8, WPP_3b099794e4b93327e327da255c047df6_Traceguids
0x140038a7b  mov     edx, 2Fh ; '/'
0x140038a80  call    WPP_SF_
0x140038a85  jmp     loc_1400388DD
0x140038a8a  cmp     byte ptr [rcx+29h], 4
0x140038a8e  jb      loc_140038912
0x140038a94  mov     rcx, [rcx+18h]
0x140038a98  lea     r8, WPP_3b099794e4b93327e327da255c047df6_Traceguids
0x140038a9f  mov     edx, 30h ; '0'
0x140038aa4  mov     r9d, edi
0x140038aa7  call    WPP_SF_d
0x140038aac  jmp     loc_140038912
```
