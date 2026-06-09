# SQL_SOSGetSPidAndRequestId(SOS_Task *,ulong &,ulong &,long &)

- ea: `0x10041f400`
- end: `0x10041f4a6`
- name: `?SQL_SOSGetSPidAndRequestId@@YAXPEAVSOS_Task@@AEAK1AEAJ@Z`
- size: `166`
- prototype: `void __fastcall(struct SOS_Task *, unsigned int *, unsigned int *, int *)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x10041f400`
- `0x10041f860`

## import_xrefs

- `sqllang!?SessionId@ExecutionContext@@QEBAFXZ` at `0x10041f45e`
- `sqllang!?SessionId@ExecutionContext@@QEBAFXZ` at `0x10041f45e`
- `sqldk!SystemThread_TlsOffset` at `0x10041f443`
- `sqldk!SystemThread_TlsIndex` at `0x10041f439`

## pseudocode

```c
void __fastcall SQL_SOSGetSPidAndRequestId(struct SOS_Task *a1, unsigned int *a2, unsigned int *a3, int *a4)
{
  ExecutionContext *RemoteObject; // rax
  ExecutionContext *v8; // rbp
  __int64 v9; // rbx
  unsigned int v10; // eax

  RemoteObject = (ExecutionContext *)SOS_Task::RetrieveRemoteObject(a1, 1u);
  v8 = RemoteObject;
  v9 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                 + SystemThread_TlsOffset
                 + 80LL);
  if ( RemoteObject )
  {
    *a2 = ExecutionContext::SessionId(RemoteObject);
    v10 = *((_DWORD *)v8 + 4);
  }
  else
  {
    *a2 = 0;
    v10 = 0;
  }
  *a3 = v10;
  if ( v9 )
    *a4 = *(_DWORD *)(v9 + 80);
  else
    *a4 = 0;
}

```

## disassembly

```asm
0x10041f400  mov     [rsp+arg_0], rbx
0x10041f405  mov     [rsp+arg_8], rbp
0x10041f40a  mov     [rsp+arg_10], rsi
0x10041f40f  mov     [rsp+arg_18], rdi
0x10041f414  push    r14
0x10041f416  sub     rsp, 20h
0x10041f41a  mov     rsi, rdx
0x10041f41d  mov     rdi, r9
0x10041f420  mov     edx, 1; unsigned int
0x10041f425  mov     r14, r8
0x10041f428  call    ?RetrieveRemoteObject@SOS_Task@@QEAAPEAXK@Z; SOS_Task::RetrieveRemoteObject(ulong)
0x10041f42d  mov     rbx, gs:58h
0x10041f436  mov     rbp, rax
0x10041f439  mov     rcx, cs:__imp_SystemThread_TlsIndex
0x10041f440  mov     r11d, [rcx]
0x10041f443  mov     rcx, cs:__imp_SystemThread_TlsOffset
0x10041f44a  mov     r10d, [rcx]
0x10041f44d  mov     rcx, [rbx+r11*8]
0x10041f451  mov     rbx, [rcx+r10+50h]
0x10041f456  test    rax, rax
0x10041f459  jz      short loc_10041F46E
0x10041f45b  mov     rcx, rax
0x10041f45e  call    cs:__imp_?SessionId@ExecutionContext@@QEBAFXZ; ExecutionContext::SessionId(void)
0x10041f464  movsx   ecx, ax
0x10041f467  mov     [rsi], ecx
0x10041f469  mov     eax, [rbp+10h]
0x10041f46c  jmp     short loc_10041F476
0x10041f46e  mov     dword ptr [rsi], 0
0x10041f474  xor     eax, eax
0x10041f476  mov     [r14], eax
0x10041f479  test    rbx, rbx
0x10041f47c  jz      short loc_10041F485
0x10041f47e  mov     eax, [rbx+50h]
0x10041f481  mov     [rdi], eax
0x10041f483  jmp     short loc_10041F48B
0x10041f485  mov     dword ptr [rdi], 0
0x10041f48b  mov     rbx, [rsp+28h+arg_0]
0x10041f490  mov     rbp, [rsp+28h+arg_8]
0x10041f495  mov     rsi, [rsp+28h+arg_10]
0x10041f49a  mov     rdi, [rsp+28h+arg_18]
0x10041f49f  add     rsp, 20h
0x10041f4a3  pop     r14
0x10041f4a5  retn
```
