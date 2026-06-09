# NvIoAllocateWorkerQueue

- ea: `0x14006a4ac`
- end: `0x14006a642`
- name: `NvIoAllocateWorkerQueue`
- size: `406`
- prototype: ``
- caller_count: `4`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x1400fb990`
- `0x1400fe920`
- `0x140106248`
- `0x14015b440`

## callees

- `0x14006a4ac`
- `0x14006a648`
- `0x14006a7f8`
- `0x14008ba18`
- `0x14008e6ac`

## import_xrefs

- `ntoskrnl!ExReInitializeRundownProtection` at `0x14006a505`
- `ntoskrnl!ExReInitializeRundownProtection` at `0x14006a523`
- `ntoskrnl!ExReInitializeRundownProtection` at `0x14006a505`
- `ntoskrnl!ExReInitializeRundownProtection` at `0x14006a523`
- `ntoskrnl!ObfReferenceObject` at `0x14006a5df`
- `ntoskrnl!ObfReferenceObject` at `0x14006a5df`
- `ntoskrnl!KeInitializeSemaphore` at `0x14006a59f`
- `ntoskrnl!KeInitializeSemaphore` at `0x14006a59f`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14006a60f`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14006a60f`
- `ntoskrnl!KeInitializeEvent` at `0x14006a53b`
- `ntoskrnl!KeInitializeEvent` at `0x14006a53b`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14006a56d`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14006a56d`
- `ntoskrnl!KeInitializeSpinLock` at `0x14006a584`
- `ntoskrnl!KeInitializeSpinLock` at `0x14006a584`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006a623`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006a623`

## pseudocode

```c
__int64 __fastcall NvIoAllocateWorkerQueue(__int64 a1, __int64 a2, __int64 *a3)
{
  PVOID v3; // rsi
  __int64 v6; // rax
  __int64 v7; // rcx
  __int64 v8; // rdi
  char Thread; // bl
  struct _EX_RUNDOWN_REF *v10; // rbx
  __int64 v11; // rdx

  v3 = VmsDriverObject;
  *a3 = 0;
  v6 = NvIoEnvMemAlloc(320, 1901545806);
  v8 = v6;
  if ( v6 )
  {
    v10 = (struct _EX_RUNDOWN_REF *)(v6 + 128);
    *(_DWORD *)(v6 + 288) = 1;
    NvIoEnvInitializeRundown((PEX_RUNDOWN_REF)(v6 + 128));
    ExReInitializeRundownProtection(v10);
    NvIoEnvInitializeRundown((PEX_RUNDOWN_REF)(v8 + 136));
    ExReInitializeRundownProtection((PEX_RUNDOWN_REF)(v8 + 136));
    KeInitializeEvent((PRKEVENT)(v8 + 168), NotificationEvent, 1u);
    ExInitializeNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)v8, 0, 0, 0x200u, 0x78u, 0x6957494Eu, 0);
    *(_BYTE *)(v8 + 216) = 0;
    KeInitializeSpinLock((PKSPIN_LOCK)(v8 + 208));
    KeInitializeSemaphore((PRKSEMAPHORE)(v8 + 256), 0, 0x7FFFFFFF);
    *(_QWORD *)(v8 + 248) = v8 + 240;
    *(_QWORD *)(v8 + 240) = v8 + 240;
    *(_QWORD *)(v8 + 232) = v8 + 224;
    *(_QWORD *)(v8 + 224) = v8 + 224;
    Thread = NvIoEnvCreateThread((PVOID *)(v8 + 144), v11, (void *)v8);
    if ( Thread )
    {
      ExDeleteNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)v8);
      ExFreePoolWithTag((PVOID)v8, 0x7157494Eu);
    }
    else
    {
      ObfReferenceObject(v3);
      *(_QWORD *)(v8 + 200) = v3;
      *(_QWORD *)(v8 + 296) = VmsNvioWorkItemEventCallBackTable;
      *(_QWORD *)(v8 + 192) = a2;
      *a3 = v8;
    }
  }
  else
  {
    Thread = 24;
  }
  LOBYTE(v7) = Thread;
  return NvIoEnvConvertToResult(v7);
}

```

## disassembly

```asm
0x14006a4ac  push    rbx
0x14006a4ae  push    rbp
0x14006a4af  push    rsi
0x14006a4b0  push    rdi
0x14006a4b1  push    r14
0x14006a4b3  sub     rsp, 40h
0x14006a4b7  mov     rsi, cs:VmsDriverObject
0x14006a4be  mov     rbp, rdx
0x14006a4c1  mov     edx, 7157494Eh
0x14006a4c6  mov     qword ptr [r8], 0
0x14006a4cd  mov     ecx, 140h
0x14006a4d2  mov     r14, r8
0x14006a4d5  call    NvIoEnvMemAlloc
0x14006a4da  mov     rdi, rax
0x14006a4dd  test    rax, rax
0x14006a4e0  jnz     short loc_14006A4E9
0x14006a4e2  mov     bl, 18h
0x14006a4e4  jmp     loc_14006A62F
0x14006a4e9  lea     rbx, [rax+80h]
0x14006a4f0  mov     dword ptr [rax+120h], 1
0x14006a4fa  mov     rcx, rbx; RunRef
0x14006a4fd  call    NvIoEnvInitializeRundown
0x14006a502  mov     rcx, rbx; RunRef
0x14006a505  call    cs:__imp_ExReInitializeRundownProtection
0x14006a50c  nop     dword ptr [rax+rax+00h]
0x14006a511  lea     rbx, [rdi+88h]
0x14006a518  mov     rcx, rbx; RunRef
0x14006a51b  call    NvIoEnvInitializeRundown
0x14006a520  mov     rcx, rbx; RunRef
0x14006a523  call    cs:__imp_ExReInitializeRundownProtection
0x14006a52a  nop     dword ptr [rax+rax+00h]
0x14006a52f  lea     rcx, [rdi+0A8h]; Event
0x14006a536  mov     r8b, 1; State
0x14006a539  xor     edx, edx; Type
0x14006a53b  call    cs:__imp_KeInitializeEvent
0x14006a542  nop     dword ptr [rax+rax+00h]
0x14006a547  xor     eax, eax
0x14006a549  mov     r9d, 200h; Flags
0x14006a54f  mov     [rsp+68h+Depth], ax; Depth
0x14006a554  xor     r8d, r8d; Free
0x14006a557  mov     [rsp+68h+Tag], 6957494Eh; Tag
0x14006a55f  xor     edx, edx; Allocate
0x14006a561  mov     rcx, rdi; Lookaside
0x14006a564  mov     [rsp+68h+Size], 78h ; 'x'; Size
0x14006a56d  call    cs:__imp_ExInitializeNPagedLookasideList
0x14006a574  nop     dword ptr [rax+rax+00h]
0x14006a579  lea     rcx, [rdi+0D0h]; SpinLock
0x14006a580  mov     byte ptr [rcx+8], 0
0x14006a584  call    cs:__imp_KeInitializeSpinLock
0x14006a58b  nop     dword ptr [rax+rax+00h]
0x14006a590  lea     rcx, [rdi+100h]; Semaphore
0x14006a597  xor     edx, edx; Count
0x14006a599  mov     r8d, 7FFFFFFFh; Limit
0x14006a59f  call    cs:__imp_KeInitializeSemaphore
0x14006a5a6  nop     dword ptr [rax+rax+00h]
0x14006a5ab  lea     rax, [rdi+0F0h]
0x14006a5b2  mov     r8, rdi
0x14006a5b5  mov     [rax+8], rax
0x14006a5b9  lea     rcx, [rdi+90h]
0x14006a5c0  mov     [rax], rax
0x14006a5c3  lea     rax, [rdi+0E0h]
0x14006a5ca  mov     [rax+8], rax
0x14006a5ce  mov     [rax], rax
0x14006a5d1  call    NvIoEnvCreateThread
0x14006a5d6  mov     bl, al
0x14006a5d8  test    al, al
0x14006a5da  jnz     short loc_14006A60C
0x14006a5dc  mov     rcx, rsi; Object
0x14006a5df  call    cs:__imp_ObfReferenceObject
0x14006a5e6  nop     dword ptr [rax+rax+00h]
0x14006a5eb  lea     rax, VmsNvioWorkItemEventCallBackTable
0x14006a5f2  mov     [rdi+0C8h], rsi
0x14006a5f9  mov     [rdi+128h], rax
0x14006a600  mov     [rdi+0C0h], rbp
0x14006a607  mov     [r14], rdi
0x14006a60a  jmp     short loc_14006A62F
0x14006a60c  mov     rcx, rdi; Lookaside
0x14006a60f  call    cs:__imp_ExDeleteNPagedLookasideList
0x14006a616  nop     dword ptr [rax+rax+00h]
0x14006a61b  mov     edx, 7157494Eh; Tag
0x14006a620  mov     rcx, rdi; P
0x14006a623  call    cs:__imp_ExFreePoolWithTag
0x14006a62a  nop     dword ptr [rax+rax+00h]
0x14006a62f  mov     cl, bl
0x14006a631  call    NvIoEnvConvertToResult
0x14006a636  add     rsp, 40h
0x14006a63a  pop     r14
0x14006a63c  pop     rdi
0x14006a63d  pop     rsi
0x14006a63e  pop     rbp
0x14006a63f  pop     rbx
0x14006a640  retn
```
