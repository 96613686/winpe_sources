# TmpGetNotificationResourceManagerAsync

- ea: `0x14001268c`
- end: `0x140012957`
- name: `TmpGetNotificationResourceManagerAsync`
- size: `715`
- prototype: `__int64 __usercall@<rax>(PRKEVENT Event@<rcx>, int, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140014480`

## callees

- `0x140012154`
- `0x14001268c`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x1400126c6`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400126ed`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400126c6`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400126ed`
- `ntoskrnl!KeReleaseMutex` at `0x140012742`
- `ntoskrnl!KeReleaseMutex` at `0x140012850`
- `ntoskrnl!KeReleaseMutex` at `0x140012907`
- `ntoskrnl!KeReleaseMutex` at `0x14001291f`
- `ntoskrnl!KeReleaseMutex` at `0x140012930`
- `ntoskrnl!KeReleaseMutex` at `0x140012742`
- `ntoskrnl!KeReleaseMutex` at `0x140012850`
- `ntoskrnl!KeReleaseMutex` at `0x140012907`
- `ntoskrnl!KeReleaseMutex` at `0x14001291f`
- `ntoskrnl!KeReleaseMutex` at `0x140012930`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012810`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012810`
- `ntoskrnl!ObfDereferenceObject` at `0x1400127fb`
- `ntoskrnl!ObfDereferenceObject` at `0x14001285f`
- `ntoskrnl!ObfDereferenceObject` at `0x1400127fb`
- `ntoskrnl!ObfDereferenceObject` at `0x14001285f`
- `ntoskrnl!ObfReferenceObject` at `0x14001272a`
- `ntoskrnl!ObfReferenceObject` at `0x1400128c0`
- `ntoskrnl!ObfReferenceObject` at `0x14001272a`
- `ntoskrnl!ObfReferenceObject` at `0x1400128c0`
- `ntoskrnl!ExAllocatePoolWithQuotaTag` at `0x140012832`
- `ntoskrnl!ExAllocatePoolWithQuotaTag` at `0x140012832`
- `ntoskrnl!KeResetEvent` at `0x14001279c`
- `ntoskrnl!KeResetEvent` at `0x14001279c`
- `ntoskrnl!KeRemoveQueue` at `0x14001277e`
- `ntoskrnl!KeRemoveQueue` at `0x14001277e`
- `ntoskrnl!PsGetCurrentProcess` at `0x14001270b`
- `ntoskrnl!PsGetCurrentProcess` at `0x14001270b`
- `ntoskrnl!KeReadStateQueue` at `0x140012758`
- `ntoskrnl!KeReadStateQueue` at `0x140012758`

## pseudocode

```c
__int64 __fastcall TmpGetNotificationResourceManagerAsync(
        PRKEVENT Event,
        KPROCESSOR_MODE a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6)
{
  struct _KMUTANT *p_Blink; // rbp
  struct _KMUTANT *v10; // rsi
  struct _LIST_ENTRY *v11; // rbx
  struct _LIST_ENTRY *Blink; // r14
  __int64 v13; // r12
  PLIST_ENTRY v14; // rbx
  int v15; // edi
  struct _LIST_ENTRY *Flink; // rcx
  _QWORD *PoolWithQuotaTag; // rax
  _QWORD *v18; // rbx
  int v20; // eax
  PRKEVENT v21; // rdi
  __int64 v22; // rax
  LARGE_INTEGER v23; // [rsp+70h] [rbp+8h] BYREF
  __int64 v24; // [rsp+80h] [rbp+18h]

  v24 = a3;
  p_Blink = (struct _KMUTANT *)&Event[1].Header.WaitListHead.Blink;
  KeWaitForSingleObject(&Event[1].Header.WaitListHead.Blink, Executive, 0, 0, 0);
  v10 = (struct _KMUTANT *)&Event[9];
  KeWaitForSingleObject(&Event[9], Executive, 0, 0, 0);
  if ( ((__int64)Event[1].Header.WaitListHead.Flink & 0x10) != 0
    && (v11 = Event[24].Header.WaitListHead.Flink, (struct _LIST_ENTRY *)PsGetCurrentProcess() == v11) )
  {
    Blink = Event[23].Header.WaitListHead.Blink;
    ObfReferenceObject(Blink);
    v13 = *(_QWORD *)&Event[24].Header.Lock;
    KeReleaseMutex(p_Blink, 0);
    if ( KeReadStateQueue((PRKQUEUE)&Event[6].Header.WaitListHead) )
    {
      v23.QuadPart = 0;
      v14 = KeRemoveQueue((PRKQUEUE)&Event[6].Header.WaitListHead, a2, &v23);
      if ( Event[7].Header.WaitListHead.Flink == &Event[7].Header.WaitListHead )
        KeResetEvent(Event);
      if ( v14 == (PLIST_ENTRY)258 || v14 == (PLIST_ENTRY)192 || v14 == (PLIST_ENTRY)128 )
      {
        v15 = (int)v14;
      }
      else
      {
        v15 = TmpCaptureOrRequeueNotification(Event, a5, a6);
        if ( v15 >= 0 )
        {
          Flink = v14[1].Flink;
          if ( Flink )
          {
            ObfDereferenceObject(Flink);
            v14[1].Flink = 0;
          }
          ExFreePoolWithTag(v14, 0);
        }
      }
      goto LABEL_16;
    }
    PoolWithQuotaTag = ExAllocatePoolWithQuotaTag((POOL_TYPE)520, 0xB8u, 0x524E6D54u);
    v18 = PoolWithQuotaTag;
    if ( !PoolWithQuotaTag )
    {
      v15 = -1073741670;
LABEL_16:
      KeReleaseMutex(v10, 0);
      ObfDereferenceObject(Blink);
      return (unsigned int)v15;
    }
    PoolWithQuotaTag[20] = v24;
    v20 = a5;
    *((_DWORD *)v18 + 38) = *((unsigned __int8 *)KeGetCurrentThread() + 586);
    *((_DWORD *)v18 + 6) = v20;
    v18[2] = a4;
    *((_BYTE *)v18 + 28) = a2;
    v18[22] = 0;
    v18[21] = v13;
    ObfReferenceObject(KeGetCurrentThread());
    v21 = Event + 23;
    v18[6] = KeGetCurrentThread();
    v18[7] = Blink;
    v22 = *(_QWORD *)&v21->Header.Lock;
    if ( *(PRKEVENT *)(*(_QWORD *)&v21->Header.Lock + 8LL) != v21 )
      __fastfail(3u);
    *v18 = v22;
    v18[1] = v21;
    *(_QWORD *)(v22 + 8) = v18;
    *(_QWORD *)&v21->Header.Lock = v18;
    KeReleaseMutex(v10, 0);
    return 259;
  }
  else
  {
    KeReleaseMutex((PRKMUTEX)&Event[9], 0);
    KeReleaseMutex(p_Blink, 0);
    return 3221225860LL;
  }
}

```

## disassembly

```asm
0x14001268c  mov     [rsp+arg_8], rbx
0x140012691  mov     [rsp+arg_10], r8
0x140012696  push    rbp
0x140012697  push    rsi
0x140012698  push    rdi
0x140012699  push    r12
0x14001269b  push    r13
0x14001269d  push    r14
0x14001269f  push    r15
0x1400126a1  sub     rsp, 30h
0x1400126a5  lea     rbp, [rcx+28h]
0x1400126a9  mov     [rsp+68h+Timeout], 0; Timeout
0x1400126b2  mov     r13, r9
0x1400126b5  mov     r15b, dl
0x1400126b8  mov     rdi, rcx
0x1400126bb  xor     r9d, r9d; Alertable
0x1400126be  mov     rcx, rbp; Object
0x1400126c1  xor     r8d, r8d; WaitMode
0x1400126c4  xor     edx, edx; WaitReason
0x1400126c6  call    cs:__imp_KeWaitForSingleObject
0x1400126cd  nop     dword ptr [rax+rax+00h]
0x1400126d2  lea     rsi, [rdi+0D8h]
0x1400126d9  mov     [rsp+68h+Timeout], 0; Timeout
0x1400126e2  mov     rcx, rsi; Object
0x1400126e5  xor     r9d, r9d; Alertable
0x1400126e8  xor     r8d, r8d; WaitMode
0x1400126eb  xor     edx, edx; WaitReason
0x1400126ed  call    cs:__imp_KeWaitForSingleObject
0x1400126f4  nop     dword ptr [rax+rax+00h]
0x1400126f9  mov     eax, [rdi+20h]
0x1400126fc  test    al, 10h
0x1400126fe  jz      loc_14001291A
0x140012704  mov     rbx, [rdi+248h]
0x14001270b  call    cs:__imp_PsGetCurrentProcess
0x140012712  nop     dword ptr [rax+rax+00h]
0x140012717  cmp     rax, rbx
0x14001271a  jnz     loc_14001291A
0x140012720  mov     r14, [rdi+238h]
0x140012727  mov     rcx, r14; Object
0x14001272a  call    cs:__imp_ObfReferenceObject
0x140012731  nop     dword ptr [rax+rax+00h]
0x140012736  mov     r12, [rdi+240h]
0x14001273d  xor     edx, edx; Wait
0x14001273f  mov     rcx, rbp; Mutex
0x140012742  call    cs:__imp_KeReleaseMutex
0x140012749  nop     dword ptr [rax+rax+00h]
0x14001274e  lea     rbx, [rdi+98h]
0x140012755  mov     rcx, rbx; Queue
0x140012758  call    cs:__imp_KeReadStateQueue
0x14001275f  nop     dword ptr [rax+rax+00h]
0x140012764  xor     ebp, ebp
0x140012766  test    eax, eax
0x140012768  jz      loc_140012822
0x14001276e  lea     r8, [rsp+68h+arg_0]; Timeout
0x140012773  mov     qword ptr [rsp+68h+arg_0], rbp
0x140012778  mov     dl, r15b; WaitMode
0x14001277b  mov     rcx, rbx; Queue
0x14001277e  call    cs:__imp_KeRemoveQueue
0x140012785  nop     dword ptr [rax+rax+00h]
0x14001278a  lea     rcx, [rdi+0B0h]
0x140012791  mov     rbx, rax
0x140012794  cmp     [rcx], rcx
0x140012797  jnz     short loc_1400127A8
0x140012799  mov     rcx, rdi; Event
0x14001279c  call    cs:__imp_KeResetEvent
0x1400127a3  nop     dword ptr [rax+rax+00h]
0x1400127a8  cmp     rbx, 102h
0x1400127af  jz      short loc_14001281E
0x1400127b1  cmp     rbx, 0C0h
0x1400127b8  jz      short loc_14001281E
0x1400127ba  cmp     rbx, 80h
0x1400127c1  jz      short loc_14001281E
0x1400127c3  mov     rax, [rsp+68h+arg_28]
0x1400127cb  mov     r9, r13
0x1400127ce  mov     [rsp+68h+var_40], rax; __int64
0x1400127d3  mov     r8, rbx
0x1400127d6  mov     eax, [rsp+68h+arg_20]
0x1400127dd  mov     dl, r15b
0x1400127e0  mov     rcx, rdi; Event
0x1400127e3  mov     dword ptr [rsp+68h+Timeout], eax; int
0x1400127e7  call    TmpCaptureOrRequeueNotification
0x1400127ec  mov     edi, eax
0x1400127ee  test    eax, eax
0x1400127f0  js      short loc_14001284B
0x1400127f2  mov     rcx, [rbx+10h]; Object
0x1400127f6  test    rcx, rcx
0x1400127f9  jz      short loc_14001280B
0x1400127fb  call    cs:__imp_ObfDereferenceObject
0x140012802  nop     dword ptr [rax+rax+00h]
0x140012807  mov     [rbx+10h], rbp
0x14001280b  xor     edx, edx; Tag
0x14001280d  mov     rcx, rbx; P
0x140012810  call    cs:__imp_ExFreePoolWithTag
0x140012817  nop     dword ptr [rax+rax+00h]
0x14001281c  jmp     short loc_14001284B
0x14001281e  mov     edi, ebx
0x140012820  jmp     short loc_14001284B
0x140012822  mov     edx, 0B8h; NumberOfBytes
0x140012827  mov     ecx, 208h; PoolType
0x14001282c  mov     r8d, 524E6D54h; Tag
0x140012832  call    cs:__imp_ExAllocatePoolWithQuotaTag
0x140012839  nop     dword ptr [rax+rax+00h]
0x14001283e  mov     rbx, rax
0x140012841  test    rax, rax
0x140012844  jnz     short loc_140012872
0x140012846  mov     edi, 0C000009Ah
0x14001284b  xor     edx, edx; Wait
0x14001284d  mov     rcx, rsi; Mutex
0x140012850  call    cs:__imp_KeReleaseMutex
0x140012857  nop     dword ptr [rax+rax+00h]
0x14001285c  mov     rcx, r14; Object
0x14001285f  call    cs:__imp_ObfDereferenceObject
0x140012866  nop     dword ptr [rax+rax+00h]
0x14001286b  mov     eax, edi
0x14001286d  jmp     loc_140012941
0x140012872  mov     rax, [rsp+68h+arg_10]
0x14001287a  mov     [rbx+0A0h], rax
0x140012881  mov     rax, gs:188h
0x14001288a  movzx   ecx, byte ptr [rax+24Ah]
0x140012891  mov     eax, [rsp+68h+arg_20]
0x140012898  mov     [rbx+98h], ecx
0x14001289e  mov     [rbx+18h], eax
0x1400128a1  mov     [rbx+10h], r13
0x1400128a5  mov     [rbx+1Ch], r15b
0x1400128a9  mov     [rbx+0B0h], rbp
0x1400128b0  mov     [rbx+0A8h], r12
0x1400128b7  mov     rcx, gs:188h; Object
0x1400128c0  call    cs:__imp_ObfReferenceObject
0x1400128c7  nop     dword ptr [rax+rax+00h]
0x1400128cc  mov     rax, gs:188h
0x1400128d5  add     rdi, 228h
0x1400128dc  mov     [rbx+30h], rax
0x1400128e0  mov     [rbx+38h], r14
0x1400128e4  mov     rax, [rdi]
0x1400128e7  cmp     [rax+8], rdi
0x1400128eb  jz      short loc_1400128F4
0x1400128ed  mov     ecx, 3
0x1400128f2  int     29h; Win8: RtlFailFast(ecx)
0x1400128f4  mov     [rbx], rax
0x1400128f7  xor     edx, edx; Wait
0x1400128f9  mov     [rbx+8], rdi
0x1400128fd  mov     rcx, rsi; Mutex
0x140012900  mov     [rax+8], rbx
0x140012904  mov     [rdi], rbx
0x140012907  call    cs:__imp_KeReleaseMutex
0x14001290e  nop     dword ptr [rax+rax+00h]
0x140012913  mov     eax, 103h
0x140012918  jmp     short loc_140012941
0x14001291a  xor     edx, edx; Wait
0x14001291c  mov     rcx, rsi; Mutex
0x14001291f  call    cs:__imp_KeReleaseMutex
0x140012926  nop     dword ptr [rax+rax+00h]
0x14001292b  xor     edx, edx; Wait
0x14001292d  mov     rcx, rbp; Mutex
0x140012930  call    cs:__imp_KeReleaseMutex
0x140012937  nop     dword ptr [rax+rax+00h]
0x14001293c  mov     eax, 0C0000184h
0x140012941  mov     rbx, [rsp+68h+arg_8]
0x140012946  add     rsp, 30h
0x14001294a  pop     r15
0x14001294c  pop     r14
0x14001294e  pop     r13
0x140012950  pop     r12
0x140012952  pop     rdi
0x140012953  pop     rsi
0x140012954  pop     rbp
0x140012955  retn
```
