# SOS_Mutex::Wait(ulong,SOS_WaitInfo const *,SOS_SYNC_WAIT_OPTIONS)

- ea: `0x10049f3d0`
- end: `0x10049f4cd`
- name: `?Wait@SOS_Mutex@@QEAA?AW4SOS_RESULT@@KPEBVSOS_WaitInfo@@W4SOS_SYNC_WAIT_OPTIONS@@@Z`
- size: `253`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1004a01d0`
- `0x1008109c0`

## callees

- `0x10049f3d0`

## import_xrefs

- `sqldk!?Wait@WaitableBase@@QEAA?AW4SOS_RESULT@@KPEBVSOS_WaitInfo@@W4SOS_SYNC_WAIT_OPTIONS@@_N@Z` at `0x10049f451`
- `sqldk!?Wait@WaitableBase@@QEAA?AW4SOS_RESULT@@KPEBVSOS_WaitInfo@@W4SOS_SYNC_WAIT_OPTIONS@@_N@Z` at `0x10049f451`
- `sqldk!SystemThread_TlsIndex` at `0x10049f3fa`
- `sqldk!SystemThread_TlsIndex` at `0x10049f466`
- `sqldk!SystemThread_TlsOffset` at `0x10049f40d`
- `sqldk!SystemThread_TlsOffset` at `0x10049f46f`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10049f428`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10049f48a`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10049f428`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10049f48a`

## pseudocode

```c
__int64 __fastcall SOS_Mutex::Wait(__int64 a1, unsigned int a2, __int64 a3, unsigned int a4)
{
  __int64 v8; // rdi
  __int64 v9; // rbx
  __int64 result; // rax
  __int64 v11; // rdi
  __int64 v12; // rax

  v8 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v9 = *(_QWORD *)(v8 + 256);
  if ( !v9 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v9 = *(_QWORD *)(v8 + 256);
  }
  *(_QWORD *)(v9 + 168) = a1 + 48;
  result = WaitableBase::Wait(a1, a2, a3, a4, 0);
  if ( !(_DWORD)result )
  {
    v11 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v12 = *(_QWORD *)(v11 + 256);
    if ( !v12 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v12 = *(_QWORD *)(v11 + 256);
    }
    *(_QWORD *)(a1 + 48) = *(_QWORD *)(v12 + 600);
    result = 0;
  }
  *(_QWORD *)(v9 + 168) = 0;
  return result;
}

```

## disassembly

```asm
0x10049f3d0  mov     [rsp+arg_0], rbx
0x10049f3d5  mov     [rsp+arg_8], rbp
0x10049f3da  mov     [rsp+arg_10], rsi
0x10049f3df  mov     [rsp+arg_18], rdi
0x10049f3e4  push    r12
0x10049f3e6  push    r14
0x10049f3e8  push    r15
0x10049f3ea  sub     rsp, 30h
0x10049f3ee  mov     r11, gs:58h
0x10049f3f7  mov     ebp, r9d
0x10049f3fa  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10049f401  mov     r15, r8
0x10049f404  mov     r12d, edx
0x10049f407  mov     rsi, rcx
0x10049f40a  mov     r10d, [rax]
0x10049f40d  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10049f414  mov     edi, [rax]
0x10049f416  add     rdi, [r11+r10*8]
0x10049f41a  mov     rbx, [rdi+100h]
0x10049f421  test    rbx, rbx
0x10049f424  jnz     short loc_10049F435
0x10049f426  xor     ecx, ecx
0x10049f428  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10049f42e  mov     rbx, [rdi+100h]
0x10049f435  lea     r14, [rsi+30h]
0x10049f439  mov     [rsp+48h+var_28], 0
0x10049f43e  mov     r9d, ebp
0x10049f441  mov     [rbx+0A8h], r14
0x10049f448  mov     r8, r15
0x10049f44b  mov     edx, r12d
0x10049f44e  mov     rcx, rsi
0x10049f451  call    cs:__imp_?Wait@WaitableBase@@QEAA?AW4SOS_RESULT@@KPEBVSOS_WaitInfo@@W4SOS_SYNC_WAIT_OPTIONS@@_N@Z; WaitableBase::Wait(ulong,SOS_WaitInfo const *,SOS_SYNC_WAIT_OPTIONS,bool)
0x10049f457  mov     esi, eax
0x10049f459  test    eax, eax
0x10049f45b  jnz     short loc_10049F4A3
0x10049f45d  mov     r8, gs:58h
0x10049f466  mov     rcx, cs:__imp_SystemThread_TlsIndex
0x10049f46d  mov     edx, [rcx]
0x10049f46f  mov     rcx, cs:__imp_SystemThread_TlsOffset
0x10049f476  mov     edi, [rcx]
0x10049f478  add     rdi, [r8+rdx*8]
0x10049f47c  mov     rax, [rdi+100h]
0x10049f483  test    rax, rax
0x10049f486  jnz     short loc_10049F497
0x10049f488  xor     ecx, ecx
0x10049f48a  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10049f490  mov     rax, [rdi+100h]
0x10049f497  mov     rax, [rax+258h]
0x10049f49e  mov     [r14], rax
0x10049f4a1  mov     eax, esi
0x10049f4a3  mov     rbp, [rsp+48h+arg_8]
0x10049f4a8  mov     rsi, [rsp+48h+arg_10]
0x10049f4ad  mov     rdi, [rsp+48h+arg_18]
0x10049f4b2  mov     qword ptr [rbx+0A8h], 0
0x10049f4bd  mov     rbx, [rsp+48h+arg_0]
0x10049f4c2  add     rsp, 30h
0x10049f4c6  pop     r15
0x10049f4c8  pop     r14
0x10049f4ca  pop     r12
0x10049f4cc  retn
```
