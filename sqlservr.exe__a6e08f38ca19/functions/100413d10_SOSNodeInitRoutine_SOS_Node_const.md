# SOSNodeInitRoutine(SOS_Node * const)

- ea: `0x100413d10`
- end: `0x100413d7f`
- name: `?SOSNodeInitRoutine@@YA?AW4SOS_RESULT@@QEAVSOS_Node@@@Z`
- size: `111`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x100413d10`

## import_xrefs

- `sqlmin!?SQLMinNodeInitRoutine@@YA?AW4SOS_RESULT@@QEAVSOS_Node@@@Z` at `0x100413d6c`
- `sqllang!?SQLLangNodeInitRoutine@@YA?AW4SOS_RESULT@@QEAVSOS_Node@@@Z` at `0x100413d5a`
- `sqllang!?SQLLangNodeInitRoutine@@YA?AW4SOS_RESULT@@QEAVSOS_Node@@@Z` at `0x100413d5a`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100413d43`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100413d43`
- `sqldk!SystemThread_TlsOffset` at `0x100413d28`
- `sqldk!SystemThread_TlsIndex` at `0x100413d1f`

## pseudocode

```c
__int64 SOSNodeInitRoutine()
{
  __int64 v0; // rbx
  __int64 v1; // rax
  __int64 v2; // rbx
  __int64 result; // rax

  v0 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v1 = *(_QWORD *)(v0 + 256);
  if ( !v1 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v1 = *(_QWORD *)(v0 + 256);
  }
  v2 = *(_QWORD *)(v1 + 992);
  result = SQLLangNodeInitRoutine(v2);
  if ( !(_DWORD)result )
    return SQLMinNodeInitRoutine(v2);
  return result;
}

```

## disassembly

```asm
0x100413d10  push    rbx
0x100413d12  sub     rsp, 20h
0x100413d16  mov     rdx, gs:58h
0x100413d1f  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100413d26  mov     ecx, [rax]
0x100413d28  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100413d2f  mov     ebx, [rax]
0x100413d31  add     rbx, [rdx+rcx*8]
0x100413d35  mov     rax, [rbx+100h]
0x100413d3c  test    rax, rax
0x100413d3f  jnz     short loc_100413D50
0x100413d41  xor     ecx, ecx
0x100413d43  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x100413d49  mov     rax, [rbx+100h]
0x100413d50  mov     rbx, [rax+3E0h]
0x100413d57  mov     rcx, rbx
0x100413d5a  call    cs:__imp_?SQLLangNodeInitRoutine@@YA?AW4SOS_RESULT@@QEAVSOS_Node@@@Z; SQLLangNodeInitRoutine(SOS_Node * const)
0x100413d60  test    eax, eax
0x100413d62  jnz     short loc_100413D79
0x100413d64  mov     rcx, rbx
0x100413d67  add     rsp, 20h
0x100413d6b  pop     rbx
0x100413d6c  jmp     cs:__imp_?SQLMinNodeInitRoutine@@YA?AW4SOS_RESULT@@QEAVSOS_Node@@@Z; SQLMinNodeInitRoutine(SOS_Node * const)
0x100413d79  add     rsp, 20h
0x100413d7d  pop     rbx
0x100413d7e  retn
```
