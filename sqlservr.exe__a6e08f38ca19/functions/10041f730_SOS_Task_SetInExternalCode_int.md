# SOS_Task::SetInExternalCode(int)

- ea: `0x10041f730`
- end: `0x10041f7a4`
- name: `?SetInExternalCode@SOS_Task@@SAXH@Z`
- size: `116`
- prototype: `void __fastcall(int)`
- caller_count: `5`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x10041ed30`
- `0x10041ee70`
- `0x10041f6b0`
- `0x10041f6e0`
- `0x10041f700`

## callees

- `0x10041f730`

## import_xrefs

- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10041f769`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10041f769`
- `sqldk!SystemThread_TlsOffset` at `0x10041f74e`
- `sqldk!SystemThread_TlsIndex` at `0x10041f745`

## pseudocode

```c
void __fastcall SOS_Task::SetInExternalCode(int a1)
{
  __int64 v2; // rbx
  __int64 v3; // rax

  v2 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v3 = *(_QWORD *)(v2 + 256);
  if ( !v3 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v3 = *(_QWORD *)(v2 + 256);
  }
  if ( a1 )
    *(_DWORD *)(v3 + 616) |= 0x200u;
  else
    *(_DWORD *)(v3 + 616) &= ~0x200u;
}

```

## disassembly

```asm
0x10041f730  mov     [rsp+arg_0], rbx
0x10041f735  push    rdi
0x10041f736  sub     rsp, 20h
0x10041f73a  mov     r8, gs:58h
0x10041f743  mov     edi, ecx
0x10041f745  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10041f74c  mov     edx, [rax]
0x10041f74e  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10041f755  mov     ebx, [rax]
0x10041f757  add     rbx, [r8+rdx*8]
0x10041f75b  mov     rax, [rbx+100h]
0x10041f762  test    rax, rax
0x10041f765  jnz     short loc_10041F776
0x10041f767  xor     ecx, ecx
0x10041f769  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10041f76f  mov     rax, [rbx+100h]
0x10041f776  test    edi, edi
0x10041f778  jz      short loc_10041F78F
0x10041f77a  or      dword ptr [rax+268h], 200h
0x10041f784  mov     rbx, [rsp+28h+arg_0]
0x10041f789  add     rsp, 20h
0x10041f78d  pop     rdi
0x10041f78e  retn
0x10041f78f  and     dword ptr [rax+268h], 0FFFFFDFFh
0x10041f799  mov     rbx, [rsp+28h+arg_0]
0x10041f79e  add     rsp, 20h
0x10041f7a2  pop     rdi
0x10041f7a3  retn
```
