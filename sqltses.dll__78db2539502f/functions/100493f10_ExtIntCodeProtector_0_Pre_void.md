# ExtIntCodeProtector<0>::Pre(void)

- ea: `0x100493f10`
- end: `0x100493fb6`
- name: `?Pre@?$ExtIntCodeProtector@$0A@@@QEAAJXZ`
- size: `166`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1004923f0`
- `0x100492530`
- `0x100492700`

## callees

- `0x100493f10`

## import_xrefs

- `sqldk!SystemThread_TlsIndex` at `0x100493f26`
- `sqldk!SystemThread_TlsIndex` at `0x100493f6e`
- `sqldk!SystemThread_TlsOffset` at `0x100493f2f`
- `sqldk!SystemThread_TlsOffset` at `0x100493f77`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100493f4a`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100493f92`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100493f4a`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100493f92`

## pseudocode

```c
__int64 __fastcall ExtIntCodeProtector<0>::Pre(int *a1)
{
  __int64 v2; // rbx
  __int64 v3; // rax
  __int64 v4; // rbx
  __int64 v5; // rax

  v2 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v3 = *(_QWORD *)(v2 + 256);
  if ( !v3 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v3 = *(_QWORD *)(v2 + 256);
  }
  *a1 = (*(_DWORD *)(v3 + 616) >> 9) & 1;
  v4 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v5 = *(_QWORD *)(v4 + 256);
  if ( !v5 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v5 = *(_QWORD *)(v4 + 256);
  }
  *(_DWORD *)(v5 + 616) &= ~0x200u;
  return 0;
}

```

## disassembly

```asm
0x100493f10  mov     [rsp+arg_0], rbx
0x100493f15  push    rdi
0x100493f16  sub     rsp, 20h
0x100493f1a  mov     r8, gs:58h
0x100493f23  mov     rdi, rcx
0x100493f26  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100493f2d  mov     edx, [rax]
0x100493f2f  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100493f36  mov     ebx, [rax]
0x100493f38  add     rbx, [r8+rdx*8]
0x100493f3c  mov     rax, [rbx+100h]
0x100493f43  test    rax, rax
0x100493f46  jnz     short loc_100493F57
0x100493f48  xor     ecx, ecx
0x100493f4a  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x100493f50  mov     rax, [rbx+100h]
0x100493f57  mov     eax, [rax+268h]
0x100493f5d  shr     eax, 9
0x100493f60  and     eax, 1
0x100493f63  mov     [rdi], eax
0x100493f65  mov     rdx, gs:58h
0x100493f6e  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100493f75  mov     ecx, [rax]
0x100493f77  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100493f7e  mov     ebx, [rax]
0x100493f80  add     rbx, [rdx+rcx*8]
0x100493f84  mov     rax, [rbx+100h]
0x100493f8b  test    rax, rax
0x100493f8e  jnz     short loc_100493F9F
0x100493f90  xor     ecx, ecx
0x100493f92  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x100493f98  mov     rax, [rbx+100h]
0x100493f9f  and     dword ptr [rax+268h], 0FFFFFDFFh
0x100493fa9  mov     rbx, [rsp+28h+arg_0]
0x100493fae  xor     eax, eax
0x100493fb0  add     rsp, 20h
0x100493fb4  pop     rdi
0x100493fb5  retn
```
