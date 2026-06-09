# TmInitializeResourceManager

- ea: `0x140011dbc`
- end: `0x140012047`
- name: `TmInitializeResourceManager`
- size: `651`
- prototype: `__int64 __usercall@<rax>(PRKEVENT Event@<rcx>, PCUNICODE_STRING StringIn)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140013ff0`

## callees

- `0x140011dbc`
- `0x14001b390`
- `0x14001e020`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x140011e6b`
- `ntoskrnl!KeWaitForSingleObject` at `0x140011f9b`
- `ntoskrnl!KeWaitForSingleObject` at `0x140011e6b`
- `ntoskrnl!KeWaitForSingleObject` at `0x140011f9b`
- `ntoskrnl!KeReleaseMutex` at `0x140011e94`
- `ntoskrnl!KeReleaseMutex` at `0x140011fe8`
- `ntoskrnl!KeReleaseMutex` at `0x140011e94`
- `ntoskrnl!KeReleaseMutex` at `0x140011fe8`
- `ntoskrnl!KeInitializeMutex` at `0x140011ef4`
- `ntoskrnl!KeInitializeMutex` at `0x140011f06`
- `ntoskrnl!KeInitializeMutex` at `0x140011ef4`
- `ntoskrnl!KeInitializeMutex` at `0x140011f06`
- `ntoskrnl!KeInitializeEvent` at `0x140011eca`
- `ntoskrnl!KeInitializeEvent` at `0x140011eca`
- `ntoskrnl!ExUuidCreate` at `0x140011e43`
- `ntoskrnl!ExUuidCreate` at `0x140011e43`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x140012022`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x140012022`
- `ntoskrnl!KeInitializeQueue` at `0x140011edf`
- `ntoskrnl!KeInitializeQueue` at `0x140011edf`

## pseudocode

```c
__int64 __fastcall TmInitializeResourceManager(
        PRKEVENT Event,
        _OWORD *a2,
        char a3,
        __int64 a4,
        PCUNICODE_STRING StringIn)
{
  __int64 result; // rax
  int v10; // ebx
  struct _LIST_ENTRY *v11; // rcx

  Event[1].Header.LockNV = -1341456382;
  Event[12].Header.WaitListHead.Flink = 0;
  Event[12].Header.WaitListHead.Blink = 0;
  LODWORD(Event[1].Header.WaitListHead.Flink) = 1;
  if ( (a3 & 1) != 0 )
  {
    LODWORD(Event[1].Header.WaitListHead.Flink) = 5;
  }
  else if ( a4 )
  {
    KeWaitForSingleObject((PVOID)(a4 + 8), Executive, 0, 0, 0);
    v10 = *(_DWORD *)(a4 + 128) & 1;
    KeReleaseMutex((PRKMUTEX)(a4 + 8), 0);
    if ( v10 )
      return v10 != 0 ? 0xC019003B : 0;
  }
  *(_QWORD *)&Event[4].Header.Lock = 0;
  LOBYTE(Event[5].Header.WaitListHead.Flink) = 0;
  result = TmpNamespaceInitialize((PRTL_AVL_TABLE)&Event[16]);
  if ( (int)result < 0 )
    return result;
  if ( a2 )
    *(_OWORD *)&Event[5].Header.WaitListHead.Blink = *a2;
  else
    ExUuidCreate((UUID *)&Event[5].Header.WaitListHead.Blink);
  Event[12].Header.LockNV = 0;
  KeInitializeEvent(Event, NotificationEvent, 0);
  KeInitializeQueue((PRKQUEUE)&Event[6].Header.WaitListHead, 0);
  KeInitializeMutex((PRKMUTEX)&Event[9], 0);
  KeInitializeMutex((PRKMUTEX)&Event[1].Header.WaitListHead.Blink, 0);
  Event[11].Header.WaitListHead.Blink = &Event[11].Header.WaitListHead;
  Event[11].Header.WaitListHead.Flink = &Event[11].Header.WaitListHead;
  Event[13].Header.WaitListHead.Flink = (struct _LIST_ENTRY *)&Event[13];
  *(_QWORD *)&Event[13].Header.Lock = Event + 13;
  *(_QWORD *)&Event[14].Header.Lock = (char *)Event + 328;
  Event[13].Header.WaitListHead.Blink = (struct _LIST_ENTRY *)&Event[13].Header.WaitListHead.Blink;
  Event[23].Header.WaitListHead.Flink = (struct _LIST_ENTRY *)&Event[23];
  *(_QWORD *)&Event[23].Header.Lock = Event + 23;
  Event[23].Header.WaitListHead.Blink = 0;
  if ( a4 )
  {
    result = TmpInsertResourceManagerTm(Event, a4);
    if ( (int)result < 0 )
      return result;
  }
  else
  {
    *(_QWORD *)&Event[15].Header.Lock = 0;
  }
  if ( (a3 & 2) != 0 )
  {
    LODWORD(Event[1].Header.WaitListHead.Flink) |= 8u;
    KeWaitForSingleObject(&WPP_MAIN_CB.Dpc.DpcData, Executive, 0, 0, 0);
    v11 = (struct _LIST_ENTRY *)*((_QWORD *)&WPP_MAIN_CB.Reserved + 1);
    if ( **((struct _DEVICE_OBJECT ***)&WPP_MAIN_CB.Reserved + 1) != (struct _DEVICE_OBJECT *)&WPP_MAIN_CB.Reserved )
      __fastfail(3u);
    ++TmpAllCRMListCount;
    Event[14].Header.WaitListHead.Flink = (struct _LIST_ENTRY *)&WPP_MAIN_CB.Reserved;
    Event[14].Header.WaitListHead.Blink = v11;
    v11->Flink = &Event[14].Header.WaitListHead;
    *((_QWORD *)&WPP_MAIN_CB.Reserved + 1) = (char *)Event + 344;
    KeReleaseMutex((PRKMUTEX)&WPP_MAIN_CB.Dpc.DpcData, 0);
  }
  Event[15].Header.WaitListHead.Blink = 0;
  LOWORD(Event[15].Header.WaitListHead.Flink) = 0;
  WORD1(Event[15].Header.WaitListHead.Flink) = 0;
  if ( StringIn )
    RtlDuplicateUnicodeString(0, StringIn, (PUNICODE_STRING)&Event[15].Header.WaitListHead);
  Event[1].Header.SignalState = 2;
  return 0;
}

```

## disassembly

```asm
0x140011dbc  push    rbx
0x140011dbe  push    rbp
0x140011dbf  push    rsi
0x140011dc0  push    rdi
0x140011dc1  push    r12
0x140011dc3  push    r14
0x140011dc5  push    r15
0x140011dc7  sub     rsp, 30h
0x140011dcb  mov     dword ptr [rcx+18h], 0B00B0002h
0x140011dd2  mov     rbp, r9
0x140011dd5  mov     qword ptr [rcx+128h], 0
0x140011de0  mov     r12d, r8d
0x140011de3  mov     qword ptr [rcx+130h], 0
0x140011dee  mov     r15, rdx
0x140011df1  mov     dword ptr [rcx+20h], 1
0x140011df8  mov     rsi, rcx
0x140011dfb  test    r8b, 1
0x140011dff  jz      short loc_140011E51
0x140011e01  mov     dword ptr [rcx+20h], 5
0x140011e08  mov     edx, 8
0x140011e0d  mov     qword ptr [rsi+60h], 0
0x140011e15  lea     rcx, [rsi+180h]; Table
0x140011e1c  mov     byte ptr [rsi+80h], 0
0x140011e23  lea     r8d, [rdx+28h]
0x140011e27  call    TmpNamespaceInitialize
0x140011e2c  test    eax, eax
0x140011e2e  js      loc_140012037
0x140011e34  lea     rax, [rsi+88h]
0x140011e3b  test    r15, r15
0x140011e3e  jnz     short loc_140011EB0
0x140011e40  mov     rcx, rax; Uuid
0x140011e43  call    cs:__imp_ExUuidCreate
0x140011e4a  nop     dword ptr [rax+rax+00h]
0x140011e4f  jmp     short loc_140011EB8
0x140011e51  test    rbp, rbp
0x140011e54  jz      short loc_140011E08
0x140011e56  xor     r9d, r9d; Alertable
0x140011e59  mov     [rsp+68h+Timeout], 0; Timeout
0x140011e62  xor     r8d, r8d; WaitMode
0x140011e65  lea     rcx, [rbp+8]; Object
0x140011e69  xor     edx, edx; WaitReason
0x140011e6b  call    cs:__imp_KeWaitForSingleObject
0x140011e72  nop     dword ptr [rax+rax+00h]
0x140011e77  mov     ebx, [rbp+80h]
0x140011e7d  lea     rcx, [rbp+8]; Mutex
0x140011e81  and     ebx, 1
0x140011e84  mov     eax, ebx
0x140011e86  neg     eax
0x140011e88  sbb     r14d, r14d
0x140011e8b  xor     edx, edx; Wait
0x140011e8d  and     r14d, 0C019003Bh
0x140011e94  call    cs:__imp_KeReleaseMutex
0x140011e9b  nop     dword ptr [rax+rax+00h]
0x140011ea0  test    ebx, ebx
0x140011ea2  jz      loc_140011E08
0x140011ea8  mov     eax, r14d
0x140011eab  jmp     loc_140012037
0x140011eb0  movups  xmm0, xmmword ptr [r15]
0x140011eb4  movdqu  xmmword ptr [rax], xmm0
0x140011eb8  xor     r8d, r8d; State
0x140011ebb  mov     dword ptr [rsi+120h], 0
0x140011ec5  xor     edx, edx; Type
0x140011ec7  mov     rcx, rsi; Event
0x140011eca  call    cs:__imp_KeInitializeEvent
0x140011ed1  nop     dword ptr [rax+rax+00h]
0x140011ed6  lea     rcx, [rsi+98h]; Queue
0x140011edd  xor     edx, edx; Count
0x140011edf  call    cs:__imp_KeInitializeQueue
0x140011ee6  nop     dword ptr [rax+rax+00h]
0x140011eeb  lea     rcx, [rsi+0D8h]; Mutex
0x140011ef2  xor     edx, edx; Level
0x140011ef4  call    cs:__imp_KeInitializeMutex
0x140011efb  nop     dword ptr [rax+rax+00h]
0x140011f00  lea     rcx, [rsi+28h]; Mutex
0x140011f04  xor     edx, edx; Level
0x140011f06  call    cs:__imp_KeInitializeMutex
0x140011f0d  nop     dword ptr [rax+rax+00h]
0x140011f12  lea     rax, [rsi+110h]
0x140011f19  mov     [rax+8], rax
0x140011f1d  mov     [rax], rax
0x140011f20  lea     rax, [rsi+138h]
0x140011f27  mov     [rax+8], rax
0x140011f2b  mov     [rax], rax
0x140011f2e  lea     rax, [rsi+148h]
0x140011f35  mov     [rax+8], rax
0x140011f39  mov     [rax], rax
0x140011f3c  lea     rax, [rsi+228h]
0x140011f43  mov     [rax+8], rax
0x140011f47  mov     [rax], rax
0x140011f4a  mov     qword ptr [rsi+238h], 0
0x140011f55  test    rbp, rbp
0x140011f58  jz      short loc_140011F6E
0x140011f5a  mov     rdx, rbp
0x140011f5d  mov     rcx, rsi
0x140011f60  call    TmpInsertResourceManagerTm
0x140011f65  test    eax, eax
0x140011f67  jns     short loc_140011F79
0x140011f69  jmp     loc_140012037
0x140011f6e  mov     qword ptr [rsi+168h], 0
0x140011f79  test    r12b, 2
0x140011f7d  jz      short loc_140011FF4
0x140011f7f  or      dword ptr [rsi+20h], 8
0x140011f83  lea     rcx, WPP_MAIN_CB.Dpc.DpcData; Object
0x140011f8a  xor     r9d, r9d; Alertable
0x140011f8d  mov     [rsp+68h+Timeout], 0; Timeout
0x140011f96  xor     r8d, r8d; WaitMode
0x140011f99  xor     edx, edx; WaitReason
0x140011f9b  call    cs:__imp_KeWaitForSingleObject
0x140011fa2  nop     dword ptr [rax+rax+00h]
0x140011fa7  mov     rcx, qword ptr cs:WPP_MAIN_CB+148h
0x140011fae  lea     rdx, WPP_MAIN_CB.Reserved
0x140011fb5  cmp     [rcx], rdx
0x140011fb8  jz      short loc_140011FC1
0x140011fba  mov     ecx, 3
0x140011fbf  int     29h; Win8: RtlFailFast(ecx)
0x140011fc1  inc     cs:TmpAllCRMListCount
0x140011fc7  lea     rax, [rsi+158h]
0x140011fce  mov     [rax], rdx
0x140011fd1  xor     edx, edx; Wait
0x140011fd3  mov     [rax+8], rcx
0x140011fd7  mov     [rcx], rax
0x140011fda  lea     rcx, WPP_MAIN_CB.Dpc.DpcData; Mutex
0x140011fe1  mov     qword ptr cs:WPP_MAIN_CB+148h, rax
0x140011fe8  call    cs:__imp_KeReleaseMutex
0x140011fef  nop     dword ptr [rax+rax+00h]
0x140011ff4  mov     rdx, [rsp+68h+StringIn]; StringIn
0x140011ffc  lea     r8, [rsi+170h]; StringOut
0x140012003  xor     eax, eax
0x140012005  mov     qword ptr [rsi+178h], 0
0x140012010  mov     [r8], ax
0x140012014  mov     [rsi+172h], ax
0x14001201b  test    rdx, rdx
0x14001201e  jz      short loc_14001202E
0x140012020  xor     ecx, ecx; Flags
0x140012022  call    cs:__imp_RtlDuplicateUnicodeString
0x140012029  nop     dword ptr [rax+rax+00h]
0x14001202e  mov     dword ptr [rsi+1Ch], 2
0x140012035  xor     eax, eax
0x140012037  add     rsp, 30h
0x14001203b  pop     r15
0x14001203d  pop     r14
0x14001203f  pop     r12
0x140012041  pop     rdi
0x140012042  pop     rsi
0x140012043  pop     rbp
0x140012044  pop     rbx
0x140012045  retn
```
