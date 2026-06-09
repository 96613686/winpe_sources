# UnionFs::UfsPersistenceManager::StartPersistenceWorker(UnionFs::StackEventTracer &)

- ea: `0x140053b80`
- end: `0x140053d88`
- name: `?StartPersistenceWorker@UfsPersistenceManager@UnionFs@@IEAAJAEAVStackEventTracer@2@@Z`
- size: `520`
- prototype: `__int64 __fastcall(PVOID StartContext, struct UnionFs::StackEventTracer *)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x14001f978`
- `0x14005b298`

## callees

- `0x140001008`
- `0x140050414`
- `0x140053b80`
- `0x140056a50`

## import_xrefs

- `ntoskrnl!PsCreateSystemThread` at `0x140053c4f`
- `ntoskrnl!PsCreateSystemThread` at `0x140053c4f`
- `ntoskrnl!ZwClose` at `0x140053d0c`
- `ntoskrnl!ZwClose` at `0x140053d5d`
- `ntoskrnl!ZwClose` at `0x140053d0c`
- `ntoskrnl!ZwClose` at `0x140053d5d`
- `ntoskrnl!KeWaitForSingleObject` at `0x140053d2f`
- `ntoskrnl!KeWaitForSingleObject` at `0x140053d2f`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140053ca9`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140053ca9`
- `ntoskrnl!ObfDereferenceObject` at `0x140053cd0`
- `ntoskrnl!ObfDereferenceObject` at `0x140053cd0`

## string_xrefs

- `0x140053c61`: `API: Starting persistence worker thread`
- `0x140053ce0`: `API: Referencing thread object`

## pseudocode

```c
__int64 __fastcall UnionFs::UfsPersistenceManager::StartPersistenceWorker(
        void **StartContext,
        struct UnionFs::StackEventTracer *a2,
        __int64 a3,
        int a4)
{
  int v4; // edi
  NTSTATUS v6; // ebx
  const char *v7; // rax
  __int64 v8; // r8
  void *v9; // rcx
  const char *StartRoutine; // [rsp+28h] [rbp-48h]
  const char *v12; // [rsp+40h] [rbp-30h] BYREF
  const char *v13; // [rsp+48h] [rbp-28h] BYREF
  const char *v14; // [rsp+50h] [rbp-20h] BYREF
  void **v15; // [rsp+58h] [rbp-18h]
  PVOID Object; // [rsp+60h] [rbp-10h] BYREF
  char v17; // [rsp+68h] [rbp-8h]
  int v18; // [rsp+A0h] [rbp+30h] BYREF
  void *ThreadHandle; // [rsp+A8h] [rbp+38h] BYREF

  v4 = (int)a2;
  if ( (unsigned int)dword_14009E178 > 5
    && (qword_14009E188 & 0x8000) != 0
    && (qword_14009E190 & 0x8000) == qword_14009E190 )
  {
    v18 = 676;
    v12 = "onecore\\base\\fs\\unionfs\\sys\\persistencemanager.cpp";
    v13 = "UnionFs::UfsPersistenceManager::StartPersistenceWorker";
    v14 = "ENTER";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      0x8000,
      (unsigned int)byte_140097E6B,
      qword_14009E190,
      a4,
      (__int64)&v14,
      (__int64)&v13,
      (__int64)&v12,
      (__int64)&v18);
  }
  ThreadHandle = 0;
  v6 = PsCreateSystemThread(
         &ThreadHandle,
         0x1FFFFFu,
         0,
         0,
         0,
         UnionFs::UfsPersistenceManager::PersistPayloadsWorker,
         StartContext);
  if ( v6 < 0 )
  {
    v7 = "API: Starting persistence worker thread";
    v8 = 0x2B9001702B5LL;
    goto LABEL_12;
  }
  v15 = StartContext + 14;
  Object = 0;
  v17 = 1;
  v6 = ObReferenceObjectByHandle(ThreadHandle, 0x1FFFFFu, 0, 0, &Object, 0);
  if ( v17 )
  {
    v9 = *v15;
    *v15 = Object;
    if ( v9 )
      ObfDereferenceObject(v9);
  }
  if ( v6 < 0 )
  {
    v7 = "API: Referencing thread object";
    v8 = 0x2BA001702C0LL;
    goto LABEL_12;
  }
  v6 = KeWaitForSingleObject(StartContext + 8, Executive, 0, 0, 0);
  if ( v6 < 0 )
  {
    v7 = "API: Waiting for worker to start";
    v8 = 0x2BB001702CALL;
LABEL_12:
    UnionFs::ProcessTraceStatusFromApi(
      (UnionFs *)(unsigned int)v6,
      v4,
      (struct UnionFs::StackEventTracer *)v8,
      (unsigned __int64)"UnionFs::UfsPersistenceManager::StartPersistenceWorker",
      v7,
      StartRoutine);
    if ( ThreadHandle )
      ZwClose(ThreadHandle);
    goto LABEL_19;
  }
  if ( ThreadHandle )
    ZwClose(ThreadHandle);
  v6 = 0;
LABEL_19:
  lambda_93a48e1e1df64eb08a002aa2c4b5f5d5_::operator()();
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140053b80  mov     r11, rsp
0x140053b83  mov     [r11+8], rbx
0x140053b87  mov     [r11+10h], rsi
0x140053b8b  push    rbp
0x140053b8c  push    rdi
0x140053b8d  push    r15
0x140053b8f  mov     rbp, rsp
0x140053b92  sub     rsp, 70h
0x140053b96  mov     eax, cs:dword_14009E178
0x140053b9c  lea     r15, aUnionfsUfspers_1; "UnionFs::UfsPersistenceManager::StartPe"...
0x140053ba3  mov     rdi, rdx
0x140053ba6  mov     rsi, rcx
0x140053ba9  cmp     eax, 5
0x140053bac  jbe     short loc_140053C1E
0x140053bae  mov     r8, cs:qword_14009E190
0x140053bb5  mov     ecx, 8000h
0x140053bba  mov     rax, cs:qword_14009E188
0x140053bc1  test    rcx, rax
0x140053bc4  jz      short loc_140053C1E
0x140053bc6  mov     rax, r8
0x140053bc9  and     rax, rcx
0x140053bcc  cmp     rax, r8
0x140053bcf  jnz     short loc_140053C1E
0x140053bd1  lea     rax, aOnecoreBaseFsU_1; "onecore\\base\\fs\\unionfs\\sys\\persis"...
0x140053bd8  mov     [rbp+arg_10], 2A4h
0x140053bdf  mov     [rbp+var_30], rax
0x140053be3  lea     rdx, byte_140097E6B
0x140053bea  lea     rax, aEnter; "ENTER"
0x140053bf1  mov     [rbp+var_28], r15
0x140053bf5  mov     [rbp+var_20], rax
0x140053bf9  lea     rax, [rbp+arg_10]
0x140053bfd  mov     [r11-50h], rax
0x140053c01  lea     rax, [rbp+var_30]
0x140053c05  mov     [r11-58h], rax
0x140053c09  lea     rax, [rbp+var_28]
0x140053c0d  mov     [r11-60h], rax
0x140053c11  lea     rax, [rbp+var_20]
0x140053c15  mov     [r11-68h], rax
0x140053c19  call    ??$Write@U?$_tlgWrapSz@D@@U1@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@33AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x140053c1e  lea     rax, ?PersistPayloadsWorker@UfsPersistenceManager@UnionFs@@KAXPEAX@Z; UnionFs::UfsPersistenceManager::PersistPayloadsWorker(void *)
0x140053c25  mov     [rsp+70h+StartContext], rsi; StartContext
0x140053c2a  mov     [rsp+70h+StartRoutine], rax; StartRoutine
0x140053c2f  lea     rcx, [rbp+ThreadHandle]; ThreadHandle
0x140053c33  xor     r9d, r9d; ProcessHandle
0x140053c36  mov     [rsp+70h+ClientId], 0; ClientId
0x140053c3f  xor     r8d, r8d; ObjectAttributes
0x140053c42  mov     [rbp+ThreadHandle], 0
0x140053c4a  mov     edx, 1FFFFFh; DesiredAccess
0x140053c4f  call    cs:__imp_PsCreateSystemThread
0x140053c56  nop     dword ptr [rax+rax+00h]
0x140053c5b  mov     ebx, eax
0x140053c5d  test    eax, eax
0x140053c5f  jns     short loc_140053C74
0x140053c61  lea     rax, aApiStartingPer; "API: Starting persistence worker thread"
0x140053c68  mov     r8, 2B9001702B5h
0x140053c72  jmp     short loc_140053CF1
0x140053c74  mov     rcx, [rbp+ThreadHandle]; Handle
0x140053c78  lea     rax, [rsi+70h]
0x140053c7c  mov     [rbp+var_18], rax
0x140053c80  xor     r9d, r9d; AccessMode
0x140053c83  lea     rax, [rbp+Object]
0x140053c87  mov     [rsp+70h+StartRoutine], 0; char *
0x140053c90  xor     r8d, r8d; ObjectType
0x140053c93  mov     [rsp+70h+ClientId], rax; Object
0x140053c98  mov     edx, 1FFFFFh; DesiredAccess
0x140053c9d  mov     [rbp+Object], 0
0x140053ca5  mov     [rbp+var_8], 1
0x140053ca9  call    cs:__imp_ObReferenceObjectByHandle
0x140053cb0  nop     dword ptr [rax+rax+00h]
0x140053cb5  cmp     [rbp+var_8], 0
0x140053cb9  mov     ebx, eax
0x140053cbb  jz      short loc_140053CDC
0x140053cbd  mov     r8, [rbp+var_18]
0x140053cc1  mov     rdx, [rbp+Object]
0x140053cc5  mov     rcx, [r8]; Object
0x140053cc8  mov     [r8], rdx
0x140053ccb  test    rcx, rcx
0x140053cce  jz      short loc_140053CDC
0x140053cd0  call    cs:__imp_ObfDereferenceObject
0x140053cd7  nop     dword ptr [rax+rax+00h]
0x140053cdc  test    ebx, ebx
0x140053cde  jns     short loc_140053D1A
0x140053ce0  lea     rax, aApiReferencing_0; "API: Referencing thread object"
0x140053ce7  mov     r8, 2BA001702C0h; struct UnionFs::StackEventTracer *
0x140053cf1  mov     r9, r15; unsigned __int64
0x140053cf4  mov     [rsp+70h+ClientId], rax; char *
0x140053cf9  mov     rdx, rdi; int
0x140053cfc  mov     ecx, ebx; this
0x140053cfe  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140053d03  mov     rcx, [rbp+ThreadHandle]; Handle
0x140053d07  test    rcx, rcx
0x140053d0a  jz      short loc_140053D6B
0x140053d0c  call    cs:__imp_ZwClose
0x140053d13  nop     dword ptr [rax+rax+00h]
0x140053d18  jmp     short loc_140053D6B
0x140053d1a  lea     rcx, [rsi+40h]; Object
0x140053d1e  mov     [rsp+70h+ClientId], 0; Timeout
0x140053d27  xor     r9d, r9d; Alertable
0x140053d2a  xor     r8d, r8d; WaitMode
0x140053d2d  xor     edx, edx; WaitReason
0x140053d2f  call    cs:__imp_KeWaitForSingleObject
0x140053d36  nop     dword ptr [rax+rax+00h]
0x140053d3b  mov     ebx, eax
0x140053d3d  test    eax, eax
0x140053d3f  jns     short loc_140053D54
0x140053d41  lea     rax, aApiWaitingForW; "API: Waiting for worker to start"
0x140053d48  mov     r8, 2BB001702CAh
0x140053d52  jmp     short loc_140053CF1
0x140053d54  mov     rcx, [rbp+ThreadHandle]; Handle
0x140053d58  test    rcx, rcx
0x140053d5b  jz      short loc_140053D69
0x140053d5d  call    cs:__imp_ZwClose
0x140053d64  nop     dword ptr [rax+rax+00h]
0x140053d69  xor     ebx, ebx
0x140053d6b  call    _lambda_93a48e1e1df64eb08a002aa2c4b5f5d5___operator__
0x140053d70  lea     r11, [rsp+70h+var_s0]
0x140053d75  mov     eax, ebx
0x140053d77  mov     rbx, [r11+20h]
0x140053d7b  mov     rsi, [r11+28h]
0x140053d7f  mov     rsp, r11
0x140053d82  pop     r15
0x140053d84  pop     rdi
0x140053d85  pop     rbp
0x140053d86  retn
```
