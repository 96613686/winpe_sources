# NonPreemptiveSetter::Pre(void)

- ea: `0x100493fc0`
- end: `0x100494083`
- name: `?Pre@NonPreemptiveSetter@@QEAAJXZ`
- size: `195`
- prototype: `__int64 __fastcall(NonPreemptiveSetter *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1004923f0`
- `0x100492530`
- `0x100492700`

## callees

- `0x100493fc0`

## import_xrefs

- `sqldk!SystemThread_TlsIndex` at `0x100493fd6`
- `sqldk!SystemThread_TlsIndex` at `0x100494019`
- `sqldk!SystemThread_TlsOffset` at `0x100493fdf`
- `sqldk!SystemThread_TlsOffset` at `0x100494022`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100493ffa`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10049403d`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100493ffa`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10049403d`

## pseudocode

```c
__int64 __fastcall NonPreemptiveSetter::Pre(NonPreemptiveSetter *this)
{
  __int64 v2; // rbx
  __int64 v3; // rax
  __int64 v4; // rbx
  __int64 v5; // rdx
  __int64 result; // rax

  v2 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v3 = *(_QWORD *)(v2 + 256);
  if ( !v3 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v3 = *(_QWORD *)(v2 + 256);
  }
  if ( (*(_BYTE *)(v3 + 800) & 4) != 0 )
  {
    v4 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v5 = *(_QWORD *)(v4 + 256);
    if ( !v5 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v5 = *(_QWORD *)(v4 + 256);
    }
    (*(void (__fastcall **)(_QWORD, __int64, __int64))(**(_QWORD **)(v5 + 608) + 16LL))(*(_QWORD *)(v5 + 608), v5, 1);
    result = 0;
    *(_DWORD *)this = 1;
  }
  else
  {
    *(_DWORD *)this = 0;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x100493fc0  mov     [rsp+arg_0], rbx
0x100493fc5  push    rdi
0x100493fc6  sub     rsp, 20h
0x100493fca  mov     r8, gs:58h
0x100493fd3  mov     rdi, rcx
0x100493fd6  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100493fdd  mov     edx, [rax]
0x100493fdf  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100493fe6  mov     ebx, [rax]
0x100493fe8  add     rbx, [r8+rdx*8]
0x100493fec  mov     rax, [rbx+100h]
0x100493ff3  test    rax, rax
0x100493ff6  jnz     short loc_100494007
0x100493ff8  xor     ecx, ecx
0x100493ffa  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x100494000  mov     rax, [rbx+100h]
0x100494007  test    byte ptr [rax+320h], 4
0x10049400e  jz      short loc_100494070
0x100494010  mov     rdx, gs:58h
0x100494019  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100494020  mov     ecx, [rax]
0x100494022  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100494029  mov     ebx, [rax]
0x10049402b  add     rbx, [rdx+rcx*8]
0x10049402f  mov     rdx, [rbx+100h]
0x100494036  test    rdx, rdx
0x100494039  jnz     short loc_10049404A
0x10049403b  xor     ecx, ecx
0x10049403d  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x100494043  mov     rdx, [rbx+100h]
0x10049404a  mov     rcx, [rdx+260h]
0x100494051  mov     r8d, 1
0x100494057  mov     rax, [rcx]
0x10049405a  call    qword ptr [rax+10h]
0x10049405d  xor     eax, eax
0x10049405f  mov     dword ptr [rdi], 1
0x100494065  mov     rbx, [rsp+28h+arg_0]
0x10049406a  add     rsp, 20h
0x10049406e  pop     rdi
0x10049406f  retn
0x100494070  mov     dword ptr [rdi], 0
0x100494076  xor     eax, eax
0x100494078  mov     rbx, [rsp+28h+arg_0]
0x10049407d  add     rsp, 20h
0x100494081  pop     rdi
0x100494082  retn
```
