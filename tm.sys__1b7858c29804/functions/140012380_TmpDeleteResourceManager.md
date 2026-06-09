# TmpDeleteResourceManager

- ea: `0x140012380`
- end: `0x140012558`
- name: `TmpDeleteResourceManager`
- size: `472`
- prototype: `__int64 __fastcall(PRKEVENT Event)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x14000c664`
- `0x140012380`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x1400123ad`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400123d8`
- `ntoskrnl!KeWaitForSingleObject` at `0x140012447`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400123ad`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400123d8`
- `ntoskrnl!KeWaitForSingleObject` at `0x140012447`
- `ntoskrnl!KeReleaseMutex` at `0x14001241b`
- `ntoskrnl!KeReleaseMutex` at `0x140012491`
- `ntoskrnl!KeReleaseMutex` at `0x1400124e8`
- `ntoskrnl!KeReleaseMutex` at `0x14001241b`
- `ntoskrnl!KeReleaseMutex` at `0x140012491`
- `ntoskrnl!KeReleaseMutex` at `0x1400124e8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001253b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001253b`
- `ntoskrnl!ObfDereferenceObject` at `0x14001251f`
- `ntoskrnl!ObfDereferenceObject` at `0x14001251f`
- `ntoskrnl!KeResetEvent` at `0x140012480`
- `ntoskrnl!KeResetEvent` at `0x140012480`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1400124d6`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1400124d6`
- `ntoskrnl!KeInitializeQueue` at `0x140012471`
- `ntoskrnl!KeInitializeQueue` at `0x140012471`
- `ntoskrnl!KeRundownQueue` at `0x14001245d`
- `ntoskrnl!KeRundownQueue` at `0x14001245d`

## pseudocode

```c
void __fastcall TmpDeleteResourceManager(PRKEVENT Event)
{
  struct _LIST_ENTRY *Flink; // r8
  struct _LIST_ENTRY *Blink; // rdx
  PLIST_ENTRY v4; // rbp
  __int64 v5; // rbx
  char v6; // di
  _QWORD *p_Flink; // rbx
  void *v8; // rcx
  void *v9; // rdi

  if ( Event[1].Header.SignalState )
  {
    KeWaitForSingleObject(&Event[1].Header.WaitListHead.Blink, Executive, 0, 0, 0);
    if ( ((__int64)Event[1].Header.WaitListHead.Flink & 8) != 0 )
    {
      KeWaitForSingleObject(&WPP_MAIN_CB.Dpc.DpcData, Executive, 0, 0, 0);
      Flink = Event[14].Header.WaitListHead.Flink;
      if ( Flink->Blink != &Event[14].Header.WaitListHead
        || (Blink = Event[14].Header.WaitListHead.Blink, Blink->Flink != &Event[14].Header.WaitListHead) )
      {
        __fastfail(3u);
      }
      --TmpAllCRMListCount;
      Blink->Flink = Flink;
      Flink->Blink = Blink;
      KeReleaseMutex((PRKMUTEX)&WPP_MAIN_CB.Dpc.DpcData, 0);
      _InterlockedAnd((volatile signed __int32 *)&Event[1].Header.WaitListHead, 0xFFFFFFF7);
    }
    KeWaitForSingleObject(&Event[9], Executive, 0, 0, 0);
    v4 = KeRundownQueue((PRKQUEUE)&Event[6].Header.WaitListHead);
    KeInitializeQueue((PRKQUEUE)&Event[6].Header.WaitListHead, 0);
    KeResetEvent(Event);
    KeReleaseMutex((PRKMUTEX)&Event[9], 0);
    v5 = *(_QWORD *)&Event[15].Header.Lock;
    if ( v5 )
    {
      v6 = 1;
      *(_QWORD *)&Event[15].Header.Lock = 0;
    }
    else
    {
      v6 = 0;
      v5 = 0;
    }
    if ( Event[15].Header.WaitListHead.Blink )
      RtlFreeUnicodeString((PUNICODE_STRING)&Event[15].Header.WaitListHead);
    KeReleaseMutex((PRKMUTEX)&Event[1].Header.WaitListHead.Blink, 0);
    if ( v6 )
      TmpNamespaceRemove((PRTL_AVL_TABLE)(v5 + 344), (PVOID)v5, (__int64)Event);
    if ( v4 )
    {
      p_Flink = &v4->Flink;
      do
      {
        v8 = (void *)p_Flink[2];
        v9 = p_Flink;
        if ( v8 )
        {
          ObfDereferenceObject(v8);
          p_Flink[2] = 0;
        }
        p_Flink = (_QWORD *)*p_Flink;
        ExFreePoolWithTag(v9, 0);
      }
      while ( v4 != (PLIST_ENTRY)p_Flink );
    }
  }
}

```

## disassembly

```asm
0x140012380  push    rbx
0x140012382  push    rbp
0x140012383  push    rsi
0x140012384  push    rdi
0x140012385  push    r14
0x140012387  sub     rsp, 30h
0x14001238b  cmp     dword ptr [rcx+1Ch], 0
0x14001238f  mov     rsi, rcx
0x140012392  jz      loc_14001254C
0x140012398  xor     r9d, r9d; Alertable
0x14001239b  mov     [rsp+58h+Timeout], 0; Timeout
0x1400123a4  xor     r8d, r8d; WaitMode
0x1400123a7  xor     edx, edx; WaitReason
0x1400123a9  add     rcx, 28h ; '('; Object
0x1400123ad  call    cs:__imp_KeWaitForSingleObject
0x1400123b4  nop     dword ptr [rax+rax+00h]
0x1400123b9  mov     eax, [rsi+20h]
0x1400123bc  test    al, 8
0x1400123be  jz      short loc_14001242C
0x1400123c0  xor     r9d, r9d; Alertable
0x1400123c3  mov     [rsp+58h+Timeout], 0; Timeout
0x1400123cc  xor     r8d, r8d; WaitMode
0x1400123cf  lea     rcx, WPP_MAIN_CB.Dpc.DpcData; Object
0x1400123d6  xor     edx, edx; WaitReason
0x1400123d8  call    cs:__imp_KeWaitForSingleObject
0x1400123df  nop     dword ptr [rax+rax+00h]
0x1400123e4  lea     rax, [rsi+158h]
0x1400123eb  mov     r8, [rax]
0x1400123ee  cmp     [r8+8], rax
0x1400123f2  jnz     loc_1400124B9
0x1400123f8  mov     rdx, [rax+8]
0x1400123fc  cmp     [rdx], rax
0x1400123ff  jnz     loc_1400124B9
0x140012405  dec     cs:TmpAllCRMListCount
0x14001240b  lea     rcx, WPP_MAIN_CB.Dpc.DpcData; Mutex
0x140012412  mov     [rdx], r8
0x140012415  mov     [r8+8], rdx
0x140012419  xor     edx, edx; Wait
0x14001241b  call    cs:__imp_KeReleaseMutex
0x140012422  nop     dword ptr [rax+rax+00h]
0x140012427  lock and dword ptr [rsi+20h], 0FFFFFFF7h
0x14001242c  lea     rdi, [rsi+0D8h]
0x140012433  mov     [rsp+58h+Timeout], 0; Timeout
0x14001243c  mov     rcx, rdi; Object
0x14001243f  xor     r9d, r9d; Alertable
0x140012442  xor     r8d, r8d; WaitMode
0x140012445  xor     edx, edx; WaitReason
0x140012447  call    cs:__imp_KeWaitForSingleObject
0x14001244e  nop     dword ptr [rax+rax+00h]
0x140012453  lea     rbx, [rsi+98h]
0x14001245a  mov     rcx, rbx; Queue
0x14001245d  call    cs:__imp_KeRundownQueue
0x140012464  nop     dword ptr [rax+rax+00h]
0x140012469  xor     edx, edx; Count
0x14001246b  mov     rcx, rbx; Queue
0x14001246e  mov     rbp, rax
0x140012471  call    cs:__imp_KeInitializeQueue
0x140012478  nop     dword ptr [rax+rax+00h]
0x14001247d  mov     rcx, rsi; Event
0x140012480  call    cs:__imp_KeResetEvent
0x140012487  nop     dword ptr [rax+rax+00h]
0x14001248c  xor     edx, edx; Wait
0x14001248e  mov     rcx, rdi; Mutex
0x140012491  call    cs:__imp_KeReleaseMutex
0x140012498  nop     dword ptr [rax+rax+00h]
0x14001249d  mov     rbx, [rsi+168h]
0x1400124a4  test    rbx, rbx
0x1400124a7  jz      short loc_1400124C0
0x1400124a9  mov     dil, 1
0x1400124ac  mov     qword ptr [rsi+168h], 0
0x1400124b7  jmp     short loc_1400124C5
0x1400124b9  mov     ecx, 3
0x1400124be  int     29h; Win8: RtlFailFast(ecx)
0x1400124c0  xor     dil, dil
0x1400124c3  xor     ebx, ebx
0x1400124c5  cmp     qword ptr [rsi+178h], 0
0x1400124cd  jz      short loc_1400124E2
0x1400124cf  lea     rcx, [rsi+170h]; UnicodeString
0x1400124d6  call    cs:__imp_RtlFreeUnicodeString
0x1400124dd  nop     dword ptr [rax+rax+00h]
0x1400124e2  xor     edx, edx; Wait
0x1400124e4  lea     rcx, [rsi+28h]; Mutex
0x1400124e8  call    cs:__imp_KeReleaseMutex
0x1400124ef  nop     dword ptr [rax+rax+00h]
0x1400124f4  test    dil, dil
0x1400124f7  jz      short loc_14001250B
0x1400124f9  lea     rcx, [rbx+158h]; Table
0x140012500  mov     r8, rsi
0x140012503  mov     rdx, rbx; Object
0x140012506  call    TmpNamespaceRemove
0x14001250b  test    rbp, rbp
0x14001250e  jz      short loc_14001254C
0x140012510  mov     rbx, rbp
0x140012513  mov     rcx, [rbx+10h]; Object
0x140012517  mov     rdi, rbx
0x14001251a  test    rcx, rcx
0x14001251d  jz      short loc_140012533
0x14001251f  call    cs:__imp_ObfDereferenceObject
0x140012526  nop     dword ptr [rax+rax+00h]
0x14001252b  mov     qword ptr [rbx+10h], 0
0x140012533  mov     rbx, [rbx]
0x140012536  xor     edx, edx; Tag
0x140012538  mov     rcx, rdi; P
0x14001253b  call    cs:__imp_ExFreePoolWithTag
0x140012542  nop     dword ptr [rax+rax+00h]
0x140012547  cmp     rbp, rbx
0x14001254a  jnz     short loc_140012513
0x14001254c  add     rsp, 30h
0x140012550  pop     r14
0x140012552  pop     rdi
0x140012553  pop     rsi
0x140012554  pop     rbp
0x140012555  pop     rbx
0x140012556  retn
```
