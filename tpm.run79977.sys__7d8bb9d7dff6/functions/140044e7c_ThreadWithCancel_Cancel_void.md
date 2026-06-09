# ThreadWithCancel::Cancel(void)

- ea: `0x140044e7c`
- end: `0x140044efa`
- name: `?Cancel@ThreadWithCancel@@QEAAJXZ`
- size: `126`
- prototype: `__int64 __fastcall(ThreadWithCancel *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x14001d070`
- `0x14001dc10`

## callees

- `0x140044e50`
- `0x140044e7c`
- `0x140044f00`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x140044ec1`
- `ntoskrnl!KeWaitForSingleObject` at `0x140044ec1`
- `ntoskrnl!KeSetEvent` at `0x140044ea1`
- `ntoskrnl!KeSetEvent` at `0x140044ea1`

## pseudocode

```c
__int64 __fastcall ThreadWithCancel::Cancel(ThreadWithCancel *this)
{
  PVOID *v1; // rbx
  PRKEVENT *v2; // rsi
  NTSTATUS v3; // edi

  v1 = (PVOID *)((char *)this + 16);
  v2 = (PRKEVENT *)((char *)this + 24);
  if ( !*((_QWORD *)this + 2) )
  {
    v3 = 0;
    goto LABEL_5;
  }
  KeSetEvent(*v2, 0, 0);
  v3 = KeWaitForSingleObject(*v1, Executive, 0, 0, 0);
  if ( v3 >= 0 )
  {
    Thread::Cleanup((Thread *)v1);
LABEL_5:
    SyncObject::Cleanup((SyncObject *)v2);
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x140044e7c  mov     [rsp+arg_0], rbx
0x140044e81  mov     [rsp+arg_8], rsi
0x140044e86  push    rdi
0x140044e87  sub     rsp, 30h
0x140044e8b  lea     rbx, [rcx+10h]
0x140044e8f  cmp     qword ptr [rbx], 0
0x140044e93  lea     rsi, [rcx+18h]
0x140044e97  jz      short loc_140044EDD
0x140044e99  mov     rcx, [rsi]; Event
0x140044e9c  xor     r8d, r8d; Wait
0x140044e9f  xor     edx, edx; Increment
0x140044ea1  call    cs:__imp_KeSetEvent
0x140044ea8  nop     dword ptr [rax+rax+00h]
0x140044ead  mov     rcx, [rbx]; Object
0x140044eb0  xor     r9d, r9d; Alertable
0x140044eb3  xor     r8d, r8d; WaitMode
0x140044eb6  mov     [rsp+38h+Timeout], 0; Timeout
0x140044ebf  xor     edx, edx; WaitReason
0x140044ec1  call    cs:__imp_KeWaitForSingleObject
0x140044ec8  nop     dword ptr [rax+rax+00h]
0x140044ecd  mov     edi, eax
0x140044ecf  test    eax, eax
0x140044ed1  js      short loc_140044EE7
0x140044ed3  mov     rcx, rbx; this
0x140044ed6  call    ?Cleanup@Thread@@QEAAXXZ; Thread::Cleanup(void)
0x140044edb  jmp     short loc_140044EDF
0x140044edd  xor     edi, edi
0x140044edf  mov     rcx, rsi; this
0x140044ee2  call    ?Cleanup@SyncObject@@QEAAXXZ; SyncObject::Cleanup(void)
0x140044ee7  mov     rbx, [rsp+38h+arg_0]
0x140044eec  mov     eax, edi
0x140044eee  mov     rsi, [rsp+38h+arg_8]
0x140044ef3  add     rsp, 30h
0x140044ef7  pop     rdi
0x140044ef8  retn
```
