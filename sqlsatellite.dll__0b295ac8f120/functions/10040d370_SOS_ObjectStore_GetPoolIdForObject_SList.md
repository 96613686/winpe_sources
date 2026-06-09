# SOS_ObjectStore::GetPoolIdForObject(SList *)

- ea: `0x10040d370`
- end: `0x10040d481`
- name: `?GetPoolIdForObject@SOS_ObjectStore@@AEBAKPEAVSList@@@Z`
- size: `273`
- prototype: `unsigned int __fastcall(SOS_ObjectStore *__hidden this, struct SList *)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x100409790`
- `0x10040af40`
- `0x10040c0e0`
- `0x10041e0a0`
- `0x100446b10`
- `0x1004704c0`
- `0x100477b20`

## callees

- `0x10040d370`

## import_xrefs

- `sqldk!?IsOwner@SOS_MemoryWorkSpace@@SAHPEAXPEAK@Z` at `0x10040d409`
- `sqldk!?IsOwner@SOS_MemoryWorkSpace@@SAHPEAXPEAK@Z` at `0x10040d409`
- `sqldk!SystemThread_TlsIndex` at `0x10040d3b0`
- `sqldk!SystemThread_TlsIndex` at `0x10040d41c`
- `sqldk!SystemThread_TlsOffset` at `0x10040d3b9`
- `sqldk!SystemThread_TlsOffset` at `0x10040d425`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10040d3d4`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10040d440`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10040d3d4`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10040d440`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SOS_ObjectStore::GetPoolIdForObject(SOS_ObjectStore *this, struct SList *a2)
{
  __int64 result; // rax
  __int64 v4; // rdi
  __int64 v5; // rbx
  int v6; // edi
  __int64 v7; // rsi
  __int64 v8; // rax
  unsigned int v9; // [rsp+50h] [rbp+8h] BYREF

  result = *((unsigned int *)this + 372);
  v9 = result;
  if ( (_DWORD)result == 64 )
  {
    v4 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v5 = *(_QWORD *)(v4 + 256);
    if ( !v5 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v5 = *(_QWORD *)(v4 + 256);
    }
    v6 = *(_DWORD *)(v5 + 616) & 0x40 ^ 0x40;
    *(_DWORD *)(v5 + 616) |= 0x40u;
    if ( !SOS_MemoryWorkSpace::IsOwner(a2, &v9) )
    {
      v7 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
      v8 = *(_QWORD *)(v7 + 256);
      if ( !v8 )
      {
        SystemThread::MakeMiniSOSThread(0);
        v8 = *(_QWORD *)(v7 + 256);
      }
      v9 = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v8 + 536) + 3336LL) + 2864LL);
    }
    *(_DWORD *)(v5 + 616) &= ~v6;
    return v9;
  }
  return result;
}

```

## disassembly

```asm
0x10040d370  push    rdi
0x10040d372  sub     rsp, 40h
0x10040d376  mov     [rsp+48h+var_28], 0FFFFFFFFFFFFFFFEh
0x10040d37f  mov     [rsp+48h+arg_8], rbx
0x10040d384  mov     [rsp+48h+arg_10], rsi
0x10040d389  mov     rsi, rdx
0x10040d38c  mov     eax, [rcx+5D0h]
0x10040d392  mov     [rsp+48h+arg_0], eax
0x10040d396  cmp     eax, 40h ; '@'
0x10040d399  jnz     loc_10040D471
0x10040d39f  mov     [rsp+48h+var_20], 0
0x10040d3a7  mov     r8, gs:58h
0x10040d3b0  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10040d3b7  mov     ecx, [rax]
0x10040d3b9  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10040d3c0  mov     edi, [rax]
0x10040d3c2  add     rdi, [r8+rcx*8]
0x10040d3c6  mov     rbx, [rdi+100h]
0x10040d3cd  test    rbx, rbx
0x10040d3d0  jnz     short loc_10040D3E1
0x10040d3d2  xor     ecx, ecx
0x10040d3d4  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10040d3da  mov     rbx, [rdi+100h]
0x10040d3e1  mov     [rsp+48h+var_18], rbx
0x10040d3e6  mov     eax, [rbx+268h]
0x10040d3ec  mov     edi, eax
0x10040d3ee  and     edi, 40h
0x10040d3f1  xor     edi, 40h
0x10040d3f4  mov     [rsp+48h+var_20], edi
0x10040d3f8  or      eax, 40h
0x10040d3fb  mov     [rbx+268h], eax
0x10040d401  lea     rdx, [rsp+48h+arg_0]
0x10040d406  mov     rcx, rsi
0x10040d409  call    cs:__imp_?IsOwner@SOS_MemoryWorkSpace@@SAHPEAXPEAK@Z; SOS_MemoryWorkSpace::IsOwner(void *,ulong *)
0x10040d40f  test    eax, eax
0x10040d411  jnz     short loc_10040D465
0x10040d413  mov     rdx, gs:58h
0x10040d41c  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10040d423  mov     ecx, [rax]
0x10040d425  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10040d42c  mov     esi, [rax]
0x10040d42e  add     rsi, [rdx+rcx*8]
0x10040d432  mov     rax, [rsi+100h]
0x10040d439  test    rax, rax
0x10040d43c  jnz     short loc_10040D44D
0x10040d43e  xor     ecx, ecx
0x10040d440  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10040d446  mov     rax, [rsi+100h]
0x10040d44d  mov     rax, [rax+218h]
0x10040d454  mov     rcx, [rax+0D08h]
0x10040d45b  mov     eax, [rcx+0B30h]
0x10040d461  mov     [rsp+48h+arg_0], eax
0x10040d465  not     edi
0x10040d467  and     [rbx+268h], edi
0x10040d46d  mov     eax, [rsp+48h+arg_0]
0x10040d471  mov     rbx, [rsp+48h+arg_8]
0x10040d476  mov     rsi, [rsp+48h+arg_10]
0x10040d47b  add     rsp, 40h
0x10040d47f  pop     rdi
0x10040d480  retn
```
