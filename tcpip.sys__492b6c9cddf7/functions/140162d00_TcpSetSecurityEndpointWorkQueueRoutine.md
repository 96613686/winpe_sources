# TcpSetSecurityEndpointWorkQueueRoutine

- ea: `0x140162d00`
- end: `0x140162e53`
- name: `TcpSetSecurityEndpointWorkQueueRoutine`
- size: `339`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140162c18`

## callees

- `0x1400392f0`
- `0x1400b5b10`
- `0x140162d00`
- `0x1401bf5c0`

## import_xrefs

- `ntoskrnl!ObReferenceSecurityDescriptor` at `0x140162d52`
- `ntoskrnl!ObReferenceSecurityDescriptor` at `0x140162d52`
- `ntoskrnl!KeBugCheck` at `0x140162e46`
- `ntoskrnl!KeBugCheck` at `0x140162e46`
- `ntoskrnl!ObDereferenceSecurityDescriptor` at `0x140162d83`
- `ntoskrnl!ObDereferenceSecurityDescriptor` at `0x140162d83`
- `ntoskrnl!KeGetCurrentIrql` at `0x140162de1`
- `ntoskrnl!KeGetCurrentIrql` at `0x140162de1`
- `ntoskrnl!KeWaitForSingleObject` at `0x140162d30`
- `ntoskrnl!KeWaitForSingleObject` at `0x140162d30`
- `ntoskrnl!KeReleaseSemaphore` at `0x140162d6a`
- `ntoskrnl!KeReleaseSemaphore` at `0x140162d6a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140162e20`
- `ntoskrnl!ExFreePoolWithTag` at `0x140162e20`
- `NETIO!NetioInsertWorkQueue` at `0x140162e0c`
- `NETIO!NetioInsertWorkQueue` at `0x140162e0c`

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
      RhAppendHistory(EndpointReferenceHistory, (unsigned int)v7, v6);
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
0x140162d00  push    rbx
0x140162d02  push    rbp
0x140162d03  push    rsi
0x140162d04  push    rdi
0x140162d05  push    r14
0x140162d07  sub     rsp, 30h
0x140162d0b  mov     rdi, rcx
0x140162d0e  mov     rbx, [rdi+8]
0x140162d12  xor     r9d, r9d; Alertable
0x140162d15  mov     r14, [rdi]
0x140162d18  xor     r8d, r8d; WaitMode
0x140162d1b  xor     edx, edx; WaitReason
0x140162d1d  mov     [rsp+58h+Timeout], 0; Timeout
0x140162d26  lea     rbp, [rbx+100h]
0x140162d2d  mov     rcx, rbp; Object
0x140162d30  call    cs:__imp_KeWaitForSingleObject
0x140162d37  nop     dword ptr [rax+rax+00h]
0x140162d3c  mov     rcx, [rdi+20h]
0x140162d40  mov     rsi, [rbx+38h]
0x140162d44  mov     [rbx+38h], rcx
0x140162d48  test    rcx, rcx
0x140162d4b  jz      short loc_140162D5E
0x140162d4d  mov     edx, 1
0x140162d52  call    cs:__imp_ObReferenceSecurityDescriptor
0x140162d59  nop     dword ptr [rax+rax+00h]
0x140162d5e  xor     r9d, r9d; Wait
0x140162d61  xor     edx, edx; Increment
0x140162d63  mov     rcx, rbp; Semaphore
0x140162d66  lea     r8d, [r9+1]; Adjustment
0x140162d6a  call    cs:__imp_KeReleaseSemaphore
0x140162d71  nop     dword ptr [rax+rax+00h]
0x140162d76  test    rsi, rsi
0x140162d79  jz      short loc_140162D8F
0x140162d7b  mov     edx, 1
0x140162d80  mov     rcx, rsi
0x140162d83  call    cs:__imp_ObDereferenceSecurityDescriptor
0x140162d8a  nop     dword ptr [rax+rax+00h]
0x140162d8f  mov     rax, [rdi+10h]
0x140162d93  xor     r8d, r8d
0x140162d96  mov     rcx, [rdi+18h]
0x140162d9a  xor     edx, edx
0x140162d9c  call    _guard_dispatch_icall
0x140162da1  mov     rsi, [rdi+8]
0x140162da5  or      rbx, 0FFFFFFFFFFFFFFFFh
0x140162da9  lock xadd [rsi+8], rbx
0x140162daf  sub     rbx, 1
0x140162db3  js      loc_140162E41
0x140162db9  mov     rcx, cs:EndpointReferenceHistory
0x140162dc0  mov     rbp, rdi
0x140162dc3  mov     rdi, r14
0x140162dc6  test    rcx, rcx
0x140162dc9  jz      short loc_140162DD5
0x140162dcb  mov     edx, ebx
0x140162dcd  mov     r8, rsi
0x140162dd0  call    RhAppendHistory
0x140162dd5  test    rbx, rbx
0x140162dd8  jnz     short loc_140162E18
0x140162dda  lea     rbx, [rsi+90h]
0x140162de1  call    cs:__imp_KeGetCurrentIrql
0x140162de8  nop     dword ptr [rax+rax+00h]
0x140162ded  test    al, al
0x140162def  jnz     short loc_140162E02
0x140162df1  mov     rcx, rbx
0x140162df4  mov     qword ptr [rbx], 0
0x140162dfb  call    TcpCleanupEndpointWorkQueueRoutine
0x140162e00  jmp     short loc_140162E18
0x140162e02  mov     rdx, rbx
0x140162e05  lea     rcx, TcpCleanupEndpointWorkQueue
0x140162e0c  call    cs:__imp_NetioInsertWorkQueue
0x140162e13  nop     dword ptr [rax+rax+00h]
0x140162e18  mov     edx, 57456354h; Tag
0x140162e1d  mov     rcx, rbp; P
0x140162e20  call    cs:__imp_ExFreePoolWithTag
0x140162e27  nop     dword ptr [rax+rax+00h]
0x140162e2c  test    r14, r14
0x140162e2f  jnz     loc_140162D0E
0x140162e35  add     rsp, 30h
0x140162e39  pop     r14
0x140162e3b  pop     rdi
0x140162e3c  pop     rsi
0x140162e3d  pop     rbp
0x140162e3e  pop     rbx
0x140162e3f  retn
0x140162e41  mov     ecx, 1Ch; BugCheckCode
0x140162e46  call    cs:__imp_KeBugCheck
```
