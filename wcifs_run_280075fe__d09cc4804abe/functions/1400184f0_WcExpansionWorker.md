# WcExpansionWorker

- ea: `0x1400184f0`
- end: `0x14001896a`
- name: `WcExpansionWorker`
- size: `1146`
- prototype: `void __stdcall(PFLT_GENERIC_WORKITEM FltWorkItem, PVOID FltObject, PVOID Context)`
- caller_count: `0`
- callee_count: `14`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140001500`
- `0x1400016f0`
- `0x140001b94`
- `0x140001bc8`
- `0x140001bf8`
- `0x140001ffc`
- `0x1400020c4`
- `0x140007c60`
- `0x140017f64`
- `0x140018254`
- `0x1400184f0`
- `0x14001b0bc`
- `0x14001ef50`
- `0x14002ee54`

## import_xrefs

- `ntoskrnl!IoClearActivityIdThread` at `0x14001884c`
- `ntoskrnl!IoClearActivityIdThread` at `0x14001884c`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x140018704`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x140018704`
- `ntoskrnl!ExRundownCompleted` at `0x140018714`
- `ntoskrnl!ExRundownCompleted` at `0x140018714`
- `ntoskrnl!KeSetEvent` at `0x140018882`
- `ntoskrnl!KeSetEvent` at `0x140018882`
- `ntoskrnl!ObfDereferenceObject` at `0x1400186ab`
- `ntoskrnl!ObfDereferenceObject` at `0x140018906`
- `ntoskrnl!ObfDereferenceObject` at `0x140018929`
- `ntoskrnl!ObfDereferenceObject` at `0x1400186ab`
- `ntoskrnl!ObfDereferenceObject` at `0x140018906`
- `ntoskrnl!ObfDereferenceObject` at `0x140018929`
- `HAL!KeQueryPerformanceCounter` at `0x1400186f1`
- `HAL!KeQueryPerformanceCounter` at `0x140018755`
- `HAL!KeQueryPerformanceCounter` at `0x1400186f1`
- `HAL!KeQueryPerformanceCounter` at `0x140018755`
- `FLTMGR!FltCbdqRemoveNextIo` at `0x1400187a0`
- `FLTMGR!FltCbdqRemoveNextIo` at `0x1400187a0`
- `FLTMGR!FltPropagateActivityIdToThread` at `0x1400187c3`
- `FLTMGR!FltPropagateActivityIdToThread` at `0x1400187c3`
- `FLTMGR!FltCompletePendedPostOperation` at `0x140018815`
- `FLTMGR!FltCompletePendedPostOperation` at `0x140018815`
- `FLTMGR!FltCompletePendedPreOperation` at `0x140018837`
- `FLTMGR!FltCompletePendedPreOperation` at `0x140018837`
- `FLTMGR!FltClose` at `0x140018695`
- `FLTMGR!FltClose` at `0x14001891a`
- `FLTMGR!FltClose` at `0x140018695`
- `FLTMGR!FltClose` at `0x14001891a`
- `FLTMGR!FltCancelFileOpen` at `0x1400187fb`
- `FLTMGR!FltCancelFileOpen` at `0x1400187fb`
- `FLTMGR!FltGetStreamContext` at `0x14001867f`
- `FLTMGR!FltGetStreamContext` at `0x14001867f`
- `FLTMGR!FltFreeGenericWorkItem` at `0x140018576`
- `FLTMGR!FltFreeGenericWorkItem` at `0x140018576`
- `FLTMGR!FltReleaseContext` at `0x1400188e3`
- `FLTMGR!FltReleaseContext` at `0x1400188f2`
- `FLTMGR!FltReleaseContext` at `0x1400188e3`
- `FLTMGR!FltReleaseContext` at `0x1400188f2`

## pseudocode

```c
void __fastcall WcExpansionWorker(
        PFLT_GENERIC_WORKITEM FltWorkItem,
        struct _FLT_INSTANCE *FltObject,
        struct _FILE_OBJECT *Context)
{
  NTSTATUS StreamContext; // edi
  int v6; // edx
  int v7; // eax
  PFILE_OBJECT v8; // rsi
  __int64 v9; // rcx
  LARGE_INTEGER v10; // rbx
  NTSTATUS v11; // eax
  struct _FLT_INSTANCE *v12; // r15
  char v13; // r13
  __int64 v14; // r12
  FLT_PREOP_CALLBACK_STATUS v15; // esi
  PFLT_CALLBACK_DATA v16; // rax
  struct _FLT_CALLBACK_DATA *v17; // rbx
  PFLT_IO_PARAMETER_BLOCK Iopb; // rdx
  PVOID v19; // r15
  int v20; // edx
  PVOID v21; // rsi
  HANDLE v22; // r12
  __int64 v23; // r13
  char v24; // [rsp+50h] [rbp-79h]
  int v25; // [rsp+54h] [rbp-75h]
  PFLT_CONTEXT Contexta; // [rsp+58h] [rbp-71h] BYREF
  int v27; // [rsp+60h] [rbp-69h]
  int v28; // [rsp+64h] [rbp-65h]
  PVOID v29; // [rsp+68h] [rbp-61h]
  HANDLE FileHandle; // [rsp+70h] [rbp-59h]
  HANDLE v31; // [rsp+78h] [rbp-51h]
  int v32; // [rsp+80h] [rbp-49h]
  FLT_PREOP_CALLBACK_STATUS CallbackStatus; // [rsp+84h] [rbp-45h]
  PFILE_OBJECT FileObject; // [rsp+88h] [rbp-41h] BYREF
  PFLT_INSTANCE Instance; // [rsp+90h] [rbp-39h]
  __int64 v36; // [rsp+98h] [rbp-31h]
  PFLT_CONTEXT v37; // [rsp+A0h] [rbp-29h]
  union _LARGE_INTEGER PerformanceFrequency; // [rsp+A8h] [rbp-21h] BYREF
  __int64 v39; // [rsp+B0h] [rbp-19h] BYREF
  LONGLONG v40; // [rsp+B8h] [rbp-11h]
  __int64 UnionContext; // [rsp+C0h] [rbp-9h]
  __int64 v42; // [rsp+C8h] [rbp-1h]
  PVOID Object; // [rsp+D0h] [rbp+7h]
  __int128 v44; // [rsp+D8h] [rbp+Fh] BYREF

  Object = Context;
  Contexta = 0;
  StreamContext = 0;
  v37 = 0;
  UnionContext = 0;
  v31 = 0;
  FileHandle = 0;
  v29 = 0;
  FileObject = 0;
  v44 = 0;
  v39 = 0;
  LOBYTE(v32) = 0;
  v40 = 0;
  v36 = 0;
  v42 = 0;
  v25 = 0;
  PerformanceFrequency.QuadPart = 0;
  v28 = 0;
  v27 = 0;
  Instance = FltObject;
  CallbackStatus = FLT_PREOP_SUCCESS_NO_CALLBACK;
  FltFreeGenericWorkItem(FltWorkItem);
  WcGetContextFileObject(FltObject, Context);
  if ( (unsigned __int8)WcIsExpanded(0) )
  {
    v24 = 1;
  }
  else
  {
    v24 = 0;
    if ( (unsigned __int8)WcIsPlaceHolderStream(0, Contexta)
      || (unsigned __int8)WcIsPlaceHolderDirectory(0, Contexta)
      || !(unsigned __int8)WcIsPlaceHolder(0) )
    {
      v8 = Context;
      v29 = Context;
    }
    else
    {
      UnionContext = WcGetUnionContext(0, FltObject, Context);
      if ( !UnionContext && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v6) = 3;
        WPP_RECORDER_SF_sDd(
          WPP_GLOBAL_Control->DeviceExtension,
          v6,
          10,
          19,
          (__int64)WPP_c8ed118f3d633d749a651abfa78156c7_Traceguids,
          (__int64)"onecore\\base\\fs\\wci\\wcifs\\expansion.c",
          190,
          0);
      }
      v7 = WcOpenDefaultStream(FltObject, Context, (__int64)&FileObject);
      v8 = FileObject;
      StreamContext = v7;
      v29 = FileObject;
      if ( v7 < 0 || (StreamContext = FltGetStreamContext(FltObject, FileObject, &Contexta), StreamContext >= 0) )
      {
        v31 = FileHandle;
      }
      else
      {
        FltClose(FileHandle);
        v31 = 0;
        ObfDereferenceObject(v8);
        v8 = 0;
        v29 = 0;
      }
    }
    if ( v8 )
    {
      v9 = *((_QWORD *)Contexta + 5);
      v28 = *(_DWORD *)(v9 + 28);
      v27 = *(_DWORD *)(v9 + 32);
      v10 = KeQueryPerformanceCounter(&PerformanceFrequency);
      ExWaitForRundownProtectionRelease((PEX_RUNDOWN_REF)0x48);
      ExRundownCompleted((PEX_RUNDOWN_REF)0x48);
      if ( (*((_DWORD *)Contexta + 6) & 0x10) != 0 )
      {
        v11 = WcExpandDirectory(Instance, v8);
        v25 = 2;
      }
      else
      {
        v11 = WcExpandFile(Instance, v8);
        v25 = 1;
      }
      StreamContext = v11;
      v40 = 1000 * (*(_QWORD *)&KeQueryPerformanceCounter(0) - v10.QuadPart) / PerformanceFrequency.QuadPart;
    }
  }
  v12 = Instance;
  v13 = v32;
  v14 = v42;
  v15 = CallbackStatus;
  do
  {
    while ( 1 )
    {
      _InterlockedExchange((volatile __int32 *)(MEMORY[0x50] + 32LL), 1);
      v16 = FltCbdqRemoveNextIo((PFLT_CALLBACK_DATA_QUEUE)(MEMORY[0x50] + 40LL), 0);
      v17 = v16;
      if ( !v16 )
        break;
      if ( (int)FltPropagateActivityIdToThread(v16, &v44, &v39) >= 0 )
        v13 = 1;
      if ( (v17->Flags & 0x80000) != 0 )
      {
        if ( StreamContext < 0 )
        {
          Iopb = v17->Iopb;
          if ( !Iopb->MajorFunction )
          {
            FltCancelFileOpen(v12, Iopb->TargetFileObject);
            v17->IoStatus.Status = StreamContext;
            v17->IoStatus.Information = 0;
          }
        }
        FltCompletePendedPostOperation(v17);
      }
      else
      {
        if ( StreamContext < 0 )
        {
          v17->IoStatus.Status = StreamContext;
          v15 = FLT_PREOP_COMPLETE;
        }
        FltCompletePendedPreOperation(v17, v15, 0);
      }
      if ( v13 )
        IoClearActivityIdThread(v39);
      ++v14;
    }
  }
  while ( _InterlockedExchangeAdd((volatile signed __int32 *)(MEMORY[0x50] + 32LL), 0xFFFFFFFF) != 1 );
  KeSetEvent((PRKEVENT)(MEMORY[0x50] + 8LL), 0, 0);
  v19 = Object;
  LOBYTE(v20) = v24;
  WcTelemetryPostExpansionComplete((_DWORD)Object, v20, v25, MEMORY[0x50], StreamContext, v14, v36, v40, v28, v27);
  v21 = v29;
  v22 = v31;
  v23 = UnionContext;
  if ( Contexta )
    FltReleaseContext(Contexta);
  FltReleaseContext(0);
  if ( v19 )
    ObfDereferenceObject(v19);
  if ( v22 )
  {
    FltClose(v22);
    ObfDereferenceObject(v21);
  }
  if ( v23 )
    WcReleaseUnionContext(v23);
}

```

## disassembly

```asm
0x1400184f0  mov     [rsp-8+arg_18], rbx
0x1400184f5  push    rbp
0x1400184f6  push    rsi
0x1400184f7  push    rdi
0x1400184f8  push    r12
0x1400184fa  push    r13
0x1400184fc  push    r14
0x1400184fe  push    r15
0x140018500  lea     rbp, [rsp-27h]
0x140018505  sub     rsp, 0F0h
0x14001850c  mov     rax, cs:__security_cookie
0x140018513  xor     rax, rsp
0x140018516  mov     [rbp+57h+var_38], rax
0x14001851a  xor     eax, eax
0x14001851c  mov     [rbp+57h+Object], r8
0x140018520  xorps   xmm0, xmm0
0x140018523  mov     [rbp+57h+Context], rax
0x140018527  mov     edi, eax
0x140018529  mov     [rbp+57h+var_80], rax
0x14001852d  mov     [rbp+57h+var_60], rax
0x140018531  mov     r15, r8
0x140018534  mov     [rbp+57h+var_A8], rax
0x140018538  mov     rbx, rdx
0x14001853b  mov     [rbp+57h+FileHandle], rax
0x14001853f  mov     [rbp+57h+var_B8], rax
0x140018543  mov     [rbp+57h+FileObject], rax
0x140018547  movups  [rbp+57h+var_48], xmm0
0x14001854b  mov     [rbp+57h+var_70], rax
0x14001854f  mov     byte ptr [rbp+57h+var_A0], al
0x140018552  mov     [rbp+57h+var_68], rax
0x140018556  mov     [rbp+57h+var_88], rax
0x14001855a  mov     [rbp+57h+var_58], rax
0x14001855e  mov     [rbp+57h+var_CC], eax
0x140018561  mov     qword ptr [rbp+57h+PerformanceFrequency], rax
0x140018565  mov     [rbp+57h+var_BC], eax
0x140018568  mov     [rbp+57h+var_C0], eax
0x14001856b  mov     [rbp+57h+Instance], rdx
0x14001856f  mov     [rbp+57h+CallbackStatus], 1
0x140018576  call    cs:__imp_FltFreeGenericWorkItem
0x14001857d  nop     dword ptr [rax+rax+00h]
0x140018582  lea     r9, [rbp+57h+Context]
0x140018586  mov     rdx, r15; FileObject
0x140018589  lea     r8, [rbp+57h+var_80]
0x14001858d  mov     rcx, rbx; Instance
0x140018590  call    WcGetContextFileObject
0x140018595  mov     r14, [rbp+57h+var_80]
0x140018599  mov     rcx, r14
0x14001859c  call    WcIsExpanded
0x1400185a1  test    al, al
0x1400185a3  jnz     loc_140018777
0x1400185a9  mov     rdx, [rbp+57h+Context]
0x1400185ad  mov     rcx, r14
0x1400185b0  mov     [rbp+57h+var_D0], dil
0x1400185b4  call    WcIsPlaceHolderStream
0x1400185b9  test    al, al
0x1400185bb  jnz     loc_1400186C9
0x1400185c1  mov     rdx, [rbp+57h+Context]
0x1400185c5  mov     rcx, r14
0x1400185c8  call    WcIsPlaceHolderDirectory
0x1400185cd  test    al, al
0x1400185cf  jnz     loc_1400186C9
0x1400185d5  mov     rcx, r14
0x1400185d8  call    WcIsPlaceHolder
0x1400185dd  test    al, al
0x1400185df  jz      loc_1400186C9
0x1400185e5  mov     r8, r15
0x1400185e8  mov     rdx, rbx
0x1400185eb  xor     ecx, ecx
0x1400185ed  call    WcGetUnionContext
0x1400185f2  mov     [rbp+57h+var_60], rax
0x1400185f6  mov     r13, rax
0x1400185f9  test    rax, rax
0x1400185fc  jnz     short loc_14001864C
0x1400185fe  lea     rax, WPP_RECORDER_INITIALIZED
0x140018605  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001860c  jz      short loc_14001864C
0x14001860e  mov     rcx, cs:WPP_GLOBAL_Control
0x140018615  lea     rax, aOnecoreBaseFsW_3; "onecore\\base\\fs\\wci\\wcifs\\expansio"...
0x14001861c  mov     dword ptr [rsp+120h+var_E8], edi
0x140018620  lea     r9d, [r13+13h]
0x140018624  mov     dword ptr [rsp+120h+var_F0], 4BEh
0x14001862c  lea     r8d, [r13+0Ah]
0x140018630  mov     [rsp+120h+var_F8], rax
0x140018635  mov     dl, 3
0x140018637  mov     rcx, [rcx+40h]
0x14001863b  lea     rax, WPP_c8ed118f3d633d749a651abfa78156c7_Traceguids
0x140018642  mov     [rsp+120h+var_100], rax
0x140018647  call    WPP_RECORDER_SF_sDd
0x14001864c  lea     rax, [rbp+57h+FileObject]
0x140018650  mov     r8, r13
0x140018653  lea     r9, [rbp+57h+FileHandle]
0x140018657  mov     [rsp+120h+var_100], rax; __int64
0x14001865c  mov     rdx, r15; FileObject
0x14001865f  mov     rcx, rbx; Instance
0x140018662  call    WcOpenDefaultStream
0x140018667  mov     rsi, [rbp+57h+FileObject]
0x14001866b  mov     edi, eax
0x14001866d  mov     [rbp+57h+var_B8], rsi
0x140018671  test    eax, eax
0x140018673  js      short loc_1400186BF
0x140018675  lea     r8, [rbp+57h+Context]; Context
0x140018679  mov     rdx, rsi; FileObject
0x14001867c  mov     rcx, rbx; Instance
0x14001867f  call    cs:__imp_FltGetStreamContext
0x140018686  nop     dword ptr [rax+rax+00h]
0x14001868b  mov     edi, eax
0x14001868d  test    eax, eax
0x14001868f  jns     short loc_1400186BF
0x140018691  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x140018695  call    cs:__imp_FltClose
0x14001869c  nop     dword ptr [rax+rax+00h]
0x1400186a1  xor     r12d, r12d
0x1400186a4  mov     rcx, rsi; Object
0x1400186a7  mov     [rbp+57h+var_A8], r12
0x1400186ab  call    cs:__imp_ObfDereferenceObject
0x1400186b2  nop     dword ptr [rax+rax+00h]
0x1400186b7  xor     esi, esi
0x1400186b9  mov     [rbp+57h+var_B8], rsi
0x1400186bd  jmp     short loc_1400186D0
0x1400186bf  mov     r12, [rbp+57h+FileHandle]
0x1400186c3  mov     [rbp+57h+var_A8], r12
0x1400186c7  jmp     short loc_1400186D0
0x1400186c9  mov     rsi, r15
0x1400186cc  mov     [rbp+57h+var_B8], r15
0x1400186d0  test    rsi, rsi
0x1400186d3  jz      loc_14001877B
0x1400186d9  mov     rax, [rbp+57h+Context]
0x1400186dd  mov     rcx, [rax+28h]
0x1400186e1  mov     eax, [rcx+1Ch]
0x1400186e4  mov     [rbp+57h+var_BC], eax
0x1400186e7  mov     eax, [rcx+20h]
0x1400186ea  lea     rcx, [rbp+57h+PerformanceFrequency]; PerformanceFrequency
0x1400186ee  mov     [rbp+57h+var_C0], eax
0x1400186f1  call    cs:__imp_KeQueryPerformanceCounter
0x1400186f8  nop     dword ptr [rax+rax+00h]
0x1400186fd  lea     rcx, [r14+48h]; RunRef
0x140018701  mov     rbx, rax
0x140018704  call    cs:__imp_ExWaitForRundownProtectionRelease
0x14001870b  nop     dword ptr [rax+rax+00h]
0x140018710  lea     rcx, [r14+48h]; RunRef
0x140018714  call    cs:__imp_ExRundownCompleted
0x14001871b  nop     dword ptr [rax+rax+00h]
0x140018720  mov     r8, [rbp+57h+Context]
0x140018724  lea     r9, [rbp+57h+var_88]
0x140018728  mov     rcx, [rbp+57h+Instance]; Instance
0x14001872c  mov     rdx, rsi; FileObject
0x14001872f  mov     eax, [r8+18h]
0x140018733  test    al, 10h
0x140018735  jz      short loc_140018745
0x140018737  call    WcExpandDirectory
0x14001873c  mov     [rbp+57h+var_CC], 2
0x140018743  jmp     short loc_140018751
0x140018745  call    WcExpandFile
0x14001874a  mov     [rbp+57h+var_CC], 1
0x140018751  xor     ecx, ecx; PerformanceFrequency
0x140018753  mov     edi, eax
0x140018755  call    cs:__imp_KeQueryPerformanceCounter
0x14001875c  nop     dword ptr [rax+rax+00h]
0x140018761  sub     rax, rbx
0x140018764  imul    rax, 3E8h
0x14001876b  cqo
0x14001876d  idiv    qword ptr [rbp+57h+PerformanceFrequency]
0x140018771  mov     [rbp+57h+var_68], rax
0x140018775  jmp     short loc_14001877B
0x140018777  mov     [rbp+57h+var_D0], 1
0x14001877b  mov     r15, [rbp+57h+Instance]
0x14001877f  mov     r13d, [rbp+57h+var_A0]
0x140018783  mov     r12, [rbp+57h+var_58]
0x140018787  mov     esi, [rbp+57h+CallbackStatus]
0x14001878a  mov     rcx, [r14+50h]
0x14001878e  mov     eax, 1
0x140018793  xor     edx, edx; PeekContext
0x140018795  xchg    eax, [rcx+20h]
0x140018798  mov     rcx, [r14+50h]
0x14001879c  add     rcx, 28h ; '('; Cbdq
0x1400187a0  call    cs:__imp_FltCbdqRemoveNextIo
0x1400187a7  nop     dword ptr [rax+rax+00h]
0x1400187ac  mov     rbx, rax
0x1400187af  test    rax, rax
0x1400187b2  jz      loc_140018860
0x1400187b8  lea     r8, [rbp+57h+var_70]
0x1400187bc  mov     rcx, rax
0x1400187bf  lea     rdx, [rbp+57h+var_48]
0x1400187c3  call    cs:__imp_FltPropagateActivityIdToThread
0x1400187ca  nop     dword ptr [rax+rax+00h]
0x1400187cf  test    eax, eax
0x1400187d1  movzx   r13d, r13b
0x1400187d5  mov     eax, 1
0x1400187da  cmovns  r13d, eax
0x1400187de  test    dword ptr [rbx], 80000h
0x1400187e4  jz      short loc_140018823
0x1400187e6  test    edi, edi
0x1400187e8  jns     short loc_140018812
0x1400187ea  mov     rdx, [rbx+10h]
0x1400187ee  cmp     byte ptr [rdx+4], 0
0x1400187f2  jnz     short loc_140018812
0x1400187f4  mov     rdx, [rdx+8]; FileObject
0x1400187f8  mov     rcx, r15; Instance
0x1400187fb  call    cs:__imp_FltCancelFileOpen
0x140018802  nop     dword ptr [rax+rax+00h]
0x140018807  mov     [rbx+18h], edi
0x14001880a  mov     qword ptr [rbx+20h], 0
0x140018812  mov     rcx, rbx; CallbackData
0x140018815  call    cs:__imp_FltCompletePendedPostOperation
0x14001881c  nop     dword ptr [rax+rax+00h]
0x140018821  jmp     short loc_140018843
0x140018823  test    edi, edi
0x140018825  jns     short loc_14001882F
0x140018827  mov     [rbx+18h], edi
0x14001882a  mov     esi, 4
0x14001882f  xor     r8d, r8d; Context
0x140018832  mov     edx, esi; CallbackStatus
0x140018834  mov     rcx, rbx; CallbackData
0x140018837  call    cs:__imp_FltCompletePendedPreOperation
0x14001883e  nop     dword ptr [rax+rax+00h]
0x140018843  test    r13b, r13b
0x140018846  jz      short loc_140018858
0x140018848  mov     rcx, [rbp+57h+var_70]
0x14001884c  call    cs:__imp_IoClearActivityIdThread
0x140018853  nop     dword ptr [rax+rax+00h]
0x140018858  inc     r12
0x14001885b  jmp     loc_14001878A
0x140018860  mov     rcx, [r14+50h]
0x140018864  or      eax, 0FFFFFFFFh
0x140018867  lock xadd [rcx+20h], eax
0x14001886c  cmp     eax, 1
0x14001886f  jnz     loc_14001878A
0x140018875  mov     rcx, [r14+50h]
0x140018879  xor     r8d, r8d; Wait
0x14001887c  add     rcx, 8; Event
0x140018880  xor     edx, edx; Increment
0x140018882  call    cs:__imp_KeSetEvent
0x140018889  nop     dword ptr [rax+rax+00h]
0x14001888e  mov     eax, [rbp+57h+var_C0]
0x140018891  mov     r15, [rbp+57h+Object]
0x140018895  mov     r9, [r14+50h]
0x140018899  mov     rcx, r15
0x14001889c  mov     r8d, [rbp+57h+var_CC]
0x1400188a0  mov     dl, [rbp+57h+var_D0]
0x1400188a3  mov     [rsp+120h+var_D8], eax
0x1400188a7  mov     eax, [rbp+57h+var_BC]
0x1400188aa  mov     [rsp+120h+var_E0], eax
0x1400188ae  mov     rax, [rbp+57h+var_68]
0x1400188b2  mov     [rsp+120h+var_E8], rax
0x1400188b7  mov     rax, [rbp+57h+var_88]
0x1400188bb  mov     [rsp+120h+var_F0], rax
0x1400188c0  mov     [rsp+120h+var_F8], r12
0x1400188c5  mov     dword ptr [rsp+120h+var_100], edi
0x1400188c9  call    WcTelemetryPostExpansionComplete
0x1400188ce  mov     rcx, [rbp+57h+Context]; Context
0x1400188d2  mov     rsi, [rbp+57h+var_B8]
0x1400188d6  mov     r12, [rbp+57h+var_A8]
0x1400188da  mov     r13, [rbp+57h+var_60]
0x1400188de  test    rcx, rcx
0x1400188e1  jz      short loc_1400188EF
0x1400188e3  call    cs:__imp_FltReleaseContext
0x1400188ea  nop     dword ptr [rax+rax+00h]
0x1400188ef  mov     rcx, r14; Context
0x1400188f2  call    cs:__imp_FltReleaseContext
0x1400188f9  nop     dword ptr [rax+rax+00h]
0x1400188fe  test    r15, r15
0x140018901  jz      short loc_140018912
0x140018903  mov     rcx, r15; Object
0x140018906  call    cs:__imp_ObfDereferenceObject
0x14001890d  nop     dword ptr [rax+rax+00h]
0x140018912  test    r12, r12
0x140018915  jz      short loc_140018935
0x140018917  mov     rcx, r12; FileHandle
0x14001891a  call    cs:__imp_FltClose
0x140018921  nop     dword ptr [rax+rax+00h]
0x140018926  mov     rcx, rsi; Object
0x140018929  call    cs:__imp_ObfDereferenceObject
0x140018930  nop     dword ptr [rax+rax+00h]
0x140018935  test    r13, r13
0x140018938  jz      short loc_140018942
0x14001893a  mov     rcx, r13
0x14001893d  call    WcReleaseUnionContext
0x140018942  mov     rcx, [rbp+57h+var_38]
0x140018946  xor     rcx, rsp; StackCookie
0x140018949  call    __security_check_cookie
0x14001894e  mov     rbx, [rsp+120h+arg_18]
0x140018956  add     rsp, 0F0h
0x14001895d  pop     r15
0x14001895f  pop     r14
0x140018961  pop     r13
0x140018963  pop     r12
0x140018965  pop     rdi
0x140018966  pop     rsi
0x140018967  pop     rbp
0x140018968  retn
```
