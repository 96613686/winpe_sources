# SOS_ObjectStore::GetPoolIdForObject(SList *)

- ea: `0x10041e420`
- end: `0x10041e531`
- name: `?GetPoolIdForObject@SOS_ObjectStore@@AEBAKPEAVSList@@@Z`
- size: `273`
- prototype: `unsigned int __fastcall(SOS_ObjectStore *__hidden this, struct SList *)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x100412470`
- `0x100416770`
- `0x10041d870`
- `0x100435700`
- `0x1004369a0`
- `0x10043f6a0`

## callees

- `0x10041e420`

## import_xrefs

- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10041e484`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10041e4f0`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10041e484`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10041e4f0`
- `sqldk!SystemThread_TlsOffset` at `0x10041e469`
- `sqldk!SystemThread_TlsOffset` at `0x10041e4d5`
- `sqldk!SystemThread_TlsIndex` at `0x10041e460`
- `sqldk!SystemThread_TlsIndex` at `0x10041e4cc`
- `sqldk!?IsOwner@SOS_MemoryWorkSpace@@SAHPEAXPEAK@Z` at `0x10041e4b9`
- `sqldk!?IsOwner@SOS_MemoryWorkSpace@@SAHPEAXPEAK@Z` at `0x10041e4b9`

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
0x10041e420  push    rdi
0x10041e422  sub     rsp, 40h
0x10041e426  mov     [rsp+48h+var_28], 0FFFFFFFFFFFFFFFEh
0x10041e42f  mov     [rsp+48h+arg_8], rbx
0x10041e434  mov     [rsp+48h+arg_10], rsi
0x10041e439  mov     rsi, rdx
0x10041e43c  mov     eax, [rcx+5D0h]
0x10041e442  mov     [rsp+48h+arg_0], eax
0x10041e446  cmp     eax, 40h ; '@'
0x10041e449  jnz     loc_10041E521
0x10041e44f  mov     [rsp+48h+var_20], 0
0x10041e457  mov     r8, gs:58h
0x10041e460  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10041e467  mov     ecx, [rax]
0x10041e469  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10041e470  mov     edi, [rax]
0x10041e472  add     rdi, [r8+rcx*8]
0x10041e476  mov     rbx, [rdi+100h]
0x10041e47d  test    rbx, rbx
0x10041e480  jnz     short loc_10041E491
0x10041e482  xor     ecx, ecx
0x10041e484  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10041e48a  mov     rbx, [rdi+100h]
0x10041e491  mov     [rsp+48h+var_18], rbx
0x10041e496  mov     eax, [rbx+268h]
0x10041e49c  mov     edi, eax
0x10041e49e  and     edi, 40h
0x10041e4a1  xor     edi, 40h
0x10041e4a4  mov     [rsp+48h+var_20], edi
0x10041e4a8  or      eax, 40h
0x10041e4ab  mov     [rbx+268h], eax
0x10041e4b1  lea     rdx, [rsp+48h+arg_0]
0x10041e4b6  mov     rcx, rsi
0x10041e4b9  call    cs:__imp_?IsOwner@SOS_MemoryWorkSpace@@SAHPEAXPEAK@Z; SOS_MemoryWorkSpace::IsOwner(void *,ulong *)
0x10041e4bf  test    eax, eax
0x10041e4c1  jnz     short loc_10041E515
0x10041e4c3  mov     rdx, gs:58h
0x10041e4cc  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10041e4d3  mov     ecx, [rax]
0x10041e4d5  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10041e4dc  mov     esi, [rax]
0x10041e4de  add     rsi, [rdx+rcx*8]
0x10041e4e2  mov     rax, [rsi+100h]
0x10041e4e9  test    rax, rax
0x10041e4ec  jnz     short loc_10041E4FD
0x10041e4ee  xor     ecx, ecx
0x10041e4f0  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10041e4f6  mov     rax, [rsi+100h]
0x10041e4fd  mov     rax, [rax+218h]
0x10041e504  mov     rcx, [rax+0D08h]
0x10041e50b  mov     eax, [rcx+0B30h]
0x10041e511  mov     [rsp+48h+arg_0], eax
0x10041e515  not     edi
0x10041e517  and     [rbx+268h], edi
0x10041e51d  mov     eax, [rsp+48h+arg_0]
0x10041e521  mov     rbx, [rsp+48h+arg_8]
0x10041e526  mov     rsi, [rsp+48h+arg_10]
0x10041e52b  add     rsp, 40h
0x10041e52f  pop     rdi
0x10041e530  retn
```
