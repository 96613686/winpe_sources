# TcpSetSecurityEndpointWorkQueueRoutine

- ea: `0x140164ac0`
- end: `0x140164c13`
- name: `TcpSetSecurityEndpointWorkQueueRoutine`
- size: `339`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1401649d8`

## callees

- `0x1400491f0`
- `0x1400d7980`
- `0x140164ac0`
- `0x1401c1200`

## import_xrefs

- `ntoskrnl!ObReferenceSecurityDescriptor` at `0x140164b12`
- `ntoskrnl!ObReferenceSecurityDescriptor` at `0x140164b12`
- `ntoskrnl!KeBugCheck` at `0x140164c06`
- `ntoskrnl!KeBugCheck` at `0x140164c06`
- `ntoskrnl!ObDereferenceSecurityDescriptor` at `0x140164b43`
- `ntoskrnl!ObDereferenceSecurityDescriptor` at `0x140164b43`
- `ntoskrnl!KeGetCurrentIrql` at `0x140164ba1`
- `ntoskrnl!KeGetCurrentIrql` at `0x140164ba1`
- `ntoskrnl!KeWaitForSingleObject` at `0x140164af0`
- `ntoskrnl!KeWaitForSingleObject` at `0x140164af0`
- `ntoskrnl!KeReleaseSemaphore` at `0x140164b2a`
- `ntoskrnl!KeReleaseSemaphore` at `0x140164b2a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140164be0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140164be0`
- `NETIO!NetioInsertWorkQueue` at `0x140164bcc`
- `NETIO!NetioInsertWorkQueue` at `0x140164bcc`

## pseudocode

```c
void __fastcall TcpSetSecurityEndpointWorkQueueRoutine(void **P)
{
  struct _KSEMAPHORE *v2; // rbx
  void **v3; // r14
  void *v4; // rcx
  __int64 v5; // rsi
  volatile signed __int64 *v6; // rsi
  __int64 v7; // rbx
  void **v8; // rbp

  do
  {
    v2 = (struct _KSEMAPHORE *)P[1];
    v3 = (void **)*P;
    KeWaitForSingleObject(&v2[8], Executive, 0, 0, 0);
    v4 = P[4];
    v5 = *(_QWORD *)&v2[1].Limit;
    *(_QWORD *)&v2[1].Limit = v4;
    if ( v4 )
      ObReferenceSecurityDescriptor(v4, 1);
    KeReleaseSemaphore(v2 + 8, 0, 1, 0);
    if ( v5 )
      ObDereferenceSecurityDescriptor(v5, 1);
    ((void (__fastcall *)(void *, _QWORD, _QWORD))P[2])(P[3], 0, 0);
    v6 = (volatile signed __int64 *)P[1];
    v7 = _InterlockedDecrement64(v6 + 1);
    if ( v7 < 0 )
      KeBugCheck(0x1Cu);
    v8 = P;
    P = v3;
    if ( EndpointReferenceHistory )
      RhAppendHistory(EndpointReferenceHistory, (unsigned int)v7);
    if ( !v7 )
    {
      if ( KeGetCurrentIrql() )
      {
        NetioInsertWorkQueue(TcpCleanupEndpointWorkQueue, v6 + 18);
      }
      else
      {
        *((_QWORD *)v6 + 18) = 0;
        TcpCleanupEndpointWorkQueueRoutine((_QWORD *)v6 + 18);
      }
    }
    ExFreePoolWithTag(v8, 0x57456354u);
  }
  while ( v3 );
}

```

## disassembly

```asm
0x140164ac0  push    rbx
0x140164ac2  push    rbp
0x140164ac3  push    rsi
0x140164ac4  push    rdi
0x140164ac5  push    r14
0x140164ac7  sub     rsp, 30h
0x140164acb  mov     rdi, rcx
0x140164ace  mov     rbx, [rdi+8]
0x140164ad2  xor     r9d, r9d; Alertable
0x140164ad5  mov     r14, [rdi]
0x140164ad8  xor     r8d, r8d; WaitMode
0x140164adb  xor     edx, edx; WaitReason
0x140164add  mov     [rsp+58h+Timeout], 0; Timeout
0x140164ae6  lea     rbp, [rbx+100h]
0x140164aed  mov     rcx, rbp; Object
0x140164af0  call    cs:__imp_KeWaitForSingleObject
0x140164af7  nop     dword ptr [rax+rax+00h]
0x140164afc  mov     rcx, [rdi+20h]
0x140164b00  mov     rsi, [rbx+38h]
0x140164b04  mov     [rbx+38h], rcx
0x140164b08  test    rcx, rcx
0x140164b0b  jz      short loc_140164B1E
0x140164b0d  mov     edx, 1
0x140164b12  call    cs:__imp_ObReferenceSecurityDescriptor
0x140164b19  nop     dword ptr [rax+rax+00h]
0x140164b1e  xor     r9d, r9d; Wait
0x140164b21  xor     edx, edx; Increment
0x140164b23  mov     rcx, rbp; Semaphore
0x140164b26  lea     r8d, [r9+1]; Adjustment
0x140164b2a  call    cs:__imp_KeReleaseSemaphore
0x140164b31  nop     dword ptr [rax+rax+00h]
0x140164b36  test    rsi, rsi
0x140164b39  jz      short loc_140164B4F
0x140164b3b  mov     edx, 1
0x140164b40  mov     rcx, rsi
0x140164b43  call    cs:__imp_ObDereferenceSecurityDescriptor
0x140164b4a  nop     dword ptr [rax+rax+00h]
0x140164b4f  mov     rax, [rdi+10h]
0x140164b53  xor     r8d, r8d
0x140164b56  mov     rcx, [rdi+18h]
0x140164b5a  xor     edx, edx
0x140164b5c  call    _guard_dispatch_icall
0x140164b61  mov     rsi, [rdi+8]
0x140164b65  or      rbx, 0FFFFFFFFFFFFFFFFh
0x140164b69  lock xadd [rsi+8], rbx
0x140164b6f  sub     rbx, 1
0x140164b73  js      loc_140164C01
0x140164b79  mov     rcx, cs:EndpointReferenceHistory
0x140164b80  mov     rbp, rdi
0x140164b83  mov     rdi, r14
0x140164b86  test    rcx, rcx
0x140164b89  jz      short loc_140164B95
0x140164b8b  mov     edx, ebx
0x140164b8d  mov     r8, rsi
0x140164b90  call    RhAppendHistory
0x140164b95  test    rbx, rbx
0x140164b98  jnz     short loc_140164BD8
0x140164b9a  lea     rbx, [rsi+90h]
0x140164ba1  call    cs:__imp_KeGetCurrentIrql
0x140164ba8  nop     dword ptr [rax+rax+00h]
0x140164bad  test    al, al
0x140164baf  jnz     short loc_140164BC2
0x140164bb1  mov     rcx, rbx
0x140164bb4  mov     qword ptr [rbx], 0
0x140164bbb  call    TcpCleanupEndpointWorkQueueRoutine
0x140164bc0  jmp     short loc_140164BD8
0x140164bc2  mov     rdx, rbx
0x140164bc5  lea     rcx, TcpCleanupEndpointWorkQueue
0x140164bcc  call    cs:__imp_NetioInsertWorkQueue
0x140164bd3  nop     dword ptr [rax+rax+00h]
0x140164bd8  mov     edx, 57456354h; Tag
0x140164bdd  mov     rcx, rbp; P
0x140164be0  call    cs:__imp_ExFreePoolWithTag
0x140164be7  nop     dword ptr [rax+rax+00h]
0x140164bec  test    r14, r14
0x140164bef  jnz     loc_140164ACE
0x140164bf5  add     rsp, 30h
0x140164bf9  pop     r14
0x140164bfb  pop     rdi
0x140164bfc  pop     rsi
0x140164bfd  pop     rbp
0x140164bfe  pop     rbx
0x140164bff  retn
0x140164c01  mov     ecx, 1Ch; BugCheckCode
0x140164c06  call    cs:__imp_KeBugCheck
```
