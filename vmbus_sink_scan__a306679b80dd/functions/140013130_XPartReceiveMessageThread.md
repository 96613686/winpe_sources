# XPartReceiveMessageThread

- ea: `0x140013130`
- end: `0x1400131e9`
- name: `XPartReceiveMessageThread`
- size: `185`
- prototype: `KSTART_ROUTINE`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x140012f34`
- `0x140013130`
- `0x140017000`

## import_xrefs

- `ntoskrnl!PsTerminateSystemThread` at `0x1400131c4`
- `ntoskrnl!PsTerminateSystemThread` at `0x1400131c4`
- `ntoskrnl!KeWaitForSingleObject` at `0x140013191`
- `ntoskrnl!KeWaitForSingleObject` at `0x140013191`
- `ntoskrnl!KeSetSystemGroupAffinityThread` at `0x14001316e`
- `ntoskrnl!KeSetSystemGroupAffinityThread` at `0x14001316e`
- `ntoskrnl!KeRevertToUserGroupAffinityThread` at `0x1400131b6`
- `ntoskrnl!KeRevertToUserGroupAffinityThread` at `0x1400131b6`

## pseudocode

```c
void __fastcall XPartReceiveMessageThread(char *StartContext)
{
  struct _GROUP_AFFINITY v2; // [rsp+30h] [rbp-38h] BYREF
  struct _GROUP_AFFINITY PreviousAffinity; // [rsp+40h] [rbp-28h] BYREF

  v2 = 0;
  v2.Mask = 1;
  PreviousAffinity = 0;
  KeSetSystemGroupAffinityThread(&v2, &PreviousAffinity);
  while ( !StartContext[112] )
  {
    KeWaitForSingleObject(StartContext + 88, Executive, 0, 0, 0);
    if ( StartContext[112] )
      break;
    XPartPullAndDeliverMessages((__int64)StartContext);
  }
  KeRevertToUserGroupAffinityThread(&PreviousAffinity);
  PsTerminateSystemThread(0);
}

```

## disassembly

```asm
0x140013130  mov     r11, rsp
0x140013133  mov     [r11+10h], rbx
0x140013137  push    rdi
0x140013138  sub     rsp, 60h
0x14001313c  mov     rax, cs:__security_cookie
0x140013143  xor     rax, rsp
0x140013146  mov     [rsp+68h+var_18], rax
0x14001314b  xorps   xmm1, xmm1
0x14001314e  lea     rdx, [r11-28h]; PreviousAffinity
0x140013152  mov     rbx, rcx
0x140013155  xorps   xmm0, xmm0
0x140013158  movups  [rsp+68h+var_38], xmm1
0x14001315d  lea     rcx, [r11-38h]; Affinity
0x140013161  mov     qword ptr [r11-38h], 1
0x140013169  movups  xmmword ptr [rsp+68h+PreviousAffinity.Mask], xmm0
0x14001316e  call    cs:__imp_KeSetSystemGroupAffinityThread
0x140013175  nop     dword ptr [rax+rax+00h]
0x14001317a  jmp     short loc_1400131AB
0x14001317c  xor     r9d, r9d; Alertable
0x14001317f  mov     [rsp+68h+Timeout], 0; Timeout
0x140013188  xor     r8d, r8d; WaitMode
0x14001318b  lea     rcx, [rbx+58h]; Object
0x14001318f  xor     edx, edx; WaitReason
0x140013191  call    cs:__imp_KeWaitForSingleObject
0x140013198  nop     dword ptr [rax+rax+00h]
0x14001319d  cmp     byte ptr [rbx+70h], 0
0x1400131a1  jnz     short loc_1400131B1
0x1400131a3  mov     rcx, rbx
0x1400131a6  call    XPartPullAndDeliverMessages
0x1400131ab  cmp     byte ptr [rbx+70h], 0
0x1400131af  jz      short loc_14001317C
0x1400131b1  lea     rcx, [rsp+68h+PreviousAffinity]; PreviousAffinity
0x1400131b6  call    cs:__imp_KeRevertToUserGroupAffinityThread
0x1400131bd  nop     dword ptr [rax+rax+00h]
0x1400131c2  xor     ecx, ecx; ExitStatus
0x1400131c4  call    cs:__imp_PsTerminateSystemThread
0x1400131cb  nop     dword ptr [rax+rax+00h]
0x1400131d0  mov     rcx, [rsp+68h+var_18]
0x1400131d5  xor     rcx, rsp; StackCookie
0x1400131d8  call    __security_check_cookie
0x1400131dd  mov     rbx, [rsp+68h+arg_8]
0x1400131e2  add     rsp, 60h
0x1400131e6  pop     rdi
0x1400131e7  retn
```
