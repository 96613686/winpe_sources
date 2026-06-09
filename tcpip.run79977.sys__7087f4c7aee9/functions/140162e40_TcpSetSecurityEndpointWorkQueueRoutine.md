# TcpSetSecurityEndpointWorkQueueRoutine

- ea: `0x140162e40`
- end: `0x140162f93`
- name: `TcpSetSecurityEndpointWorkQueueRoutine`
- size: `339`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140162d58`

## callees

- `0x140039590`
- `0x1400b5730`
- `0x140162e40`
- `0x1401bf700`

## import_xrefs

- `ntoskrnl!ObReferenceSecurityDescriptor` at `0x140162e92`
- `ntoskrnl!ObReferenceSecurityDescriptor` at `0x140162e92`
- `ntoskrnl!KeBugCheck` at `0x140162f86`
- `ntoskrnl!KeBugCheck` at `0x140162f86`
- `ntoskrnl!ObDereferenceSecurityDescriptor` at `0x140162ec3`
- `ntoskrnl!ObDereferenceSecurityDescriptor` at `0x140162ec3`
- `ntoskrnl!KeGetCurrentIrql` at `0x140162f21`
- `ntoskrnl!KeGetCurrentIrql` at `0x140162f21`
- `ntoskrnl!KeWaitForSingleObject` at `0x140162e70`
- `ntoskrnl!KeWaitForSingleObject` at `0x140162e70`
- `ntoskrnl!KeReleaseSemaphore` at `0x140162eaa`
- `ntoskrnl!KeReleaseSemaphore` at `0x140162eaa`
- `ntoskrnl!ExFreePoolWithTag` at `0x140162f60`
- `ntoskrnl!ExFreePoolWithTag` at `0x140162f60`
- `NETIO!NetioInsertWorkQueue` at `0x140162f4c`
- `NETIO!NetioInsertWorkQueue` at `0x140162f4c`

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
        NetioInsertWorkQueue(&TcpCleanupEndpointWorkQueue, v6 + 18);
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
0x140162e40  push    rbx
0x140162e42  push    rbp
0x140162e43  push    rsi
0x140162e44  push    rdi
0x140162e45  push    r14
0x140162e47  sub     rsp, 30h
0x140162e4b  mov     rdi, rcx
0x140162e4e  mov     rbx, [rdi+8]
0x140162e52  xor     r9d, r9d; Alertable
0x140162e55  mov     r14, [rdi]
0x140162e58  xor     r8d, r8d; WaitMode
0x140162e5b  xor     edx, edx; WaitReason
0x140162e5d  mov     [rsp+58h+Timeout], 0; Timeout
0x140162e66  lea     rbp, [rbx+100h]
0x140162e6d  mov     rcx, rbp; Object
0x140162e70  call    cs:__imp_KeWaitForSingleObject
0x140162e77  nop     dword ptr [rax+rax+00h]
0x140162e7c  mov     rcx, [rdi+20h]
0x140162e80  mov     rsi, [rbx+38h]
0x140162e84  mov     [rbx+38h], rcx
0x140162e88  test    rcx, rcx
0x140162e8b  jz      short loc_140162E9E
0x140162e8d  mov     edx, 1
0x140162e92  call    cs:__imp_ObReferenceSecurityDescriptor
0x140162e99  nop     dword ptr [rax+rax+00h]
0x140162e9e  xor     r9d, r9d; Wait
0x140162ea1  xor     edx, edx; Increment
0x140162ea3  mov     rcx, rbp; Semaphore
0x140162ea6  lea     r8d, [r9+1]; Adjustment
0x140162eaa  call    cs:__imp_KeReleaseSemaphore
0x140162eb1  nop     dword ptr [rax+rax+00h]
0x140162eb6  test    rsi, rsi
0x140162eb9  jz      short loc_140162ECF
0x140162ebb  mov     edx, 1
0x140162ec0  mov     rcx, rsi
0x140162ec3  call    cs:__imp_ObDereferenceSecurityDescriptor
0x140162eca  nop     dword ptr [rax+rax+00h]
0x140162ecf  mov     rax, [rdi+10h]
0x140162ed3  xor     r8d, r8d
0x140162ed6  mov     rcx, [rdi+18h]
0x140162eda  xor     edx, edx
0x140162edc  call    _guard_dispatch_icall
0x140162ee1  mov     rsi, [rdi+8]
0x140162ee5  or      rbx, 0FFFFFFFFFFFFFFFFh
0x140162ee9  lock xadd [rsi+8], rbx
0x140162eef  sub     rbx, 1
0x140162ef3  js      loc_140162F81
0x140162ef9  mov     rcx, cs:EndpointReferenceHistory
0x140162f00  mov     rbp, rdi
0x140162f03  mov     rdi, r14
0x140162f06  test    rcx, rcx
0x140162f09  jz      short loc_140162F15
0x140162f0b  mov     edx, ebx
0x140162f0d  mov     r8, rsi
0x140162f10  call    RhAppendHistory
0x140162f15  test    rbx, rbx
0x140162f18  jnz     short loc_140162F58
0x140162f1a  lea     rbx, [rsi+90h]
0x140162f21  call    cs:__imp_KeGetCurrentIrql
0x140162f28  nop     dword ptr [rax+rax+00h]
0x140162f2d  test    al, al
0x140162f2f  jnz     short loc_140162F42
0x140162f31  mov     rcx, rbx
0x140162f34  mov     qword ptr [rbx], 0
0x140162f3b  call    TcpCleanupEndpointWorkQueueRoutine
0x140162f40  jmp     short loc_140162F58
0x140162f42  mov     rdx, rbx
0x140162f45  lea     rcx, TcpCleanupEndpointWorkQueue
0x140162f4c  call    cs:__imp_NetioInsertWorkQueue
0x140162f53  nop     dword ptr [rax+rax+00h]
0x140162f58  mov     edx, 57456354h; Tag
0x140162f5d  mov     rcx, rbp; P
0x140162f60  call    cs:__imp_ExFreePoolWithTag
0x140162f67  nop     dword ptr [rax+rax+00h]
0x140162f6c  test    r14, r14
0x140162f6f  jnz     loc_140162E4E
0x140162f75  add     rsp, 30h
0x140162f79  pop     r14
0x140162f7b  pop     rdi
0x140162f7c  pop     rsi
0x140162f7d  pop     rbp
0x140162f7e  pop     rbx
0x140162f7f  retn
0x140162f81  mov     ecx, 1Ch; BugCheckCode
0x140162f86  call    cs:__imp_KeBugCheck
```
