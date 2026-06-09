# SOS_RWLock::GetLock(RWLockMode,ulong,SOS_WaitInfo const *)

- ea: `0x10041d750`
- end: `0x10041d85b`
- name: `?GetLock@SOS_RWLock@@QEAA?AW4SOS_RESULT@@W4RWLockMode@@KPEBVSOS_WaitInfo@@@Z`
- size: `267`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x1004447d0`
- `0x100471080`
- `0x100471ab0`
- `0x100471d80`
- `0x1004723b0`
- `0x100473630`

## callees

- `0x10041d750`

## import_xrefs

- `sqldk!?GetLongWait@SOS_RWLock@@AEAA?AW4SOS_RESULT@@W4RWLockMode@@KPEBVSOS_WaitInfo@@@Z` at `0x10041d82f`
- `sqldk!?GetLongWait@SOS_RWLock@@AEAA?AW4SOS_RESULT@@W4RWLockMode@@KPEBVSOS_WaitInfo@@@Z` at `0x10041d82f`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10041d7d6`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10041d7d6`
- `sqldk!SystemThread_TlsIndex` at `0x10041d774`
- `sqldk!SystemThread_TlsOffset` at `0x10041d786`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10041d7a1`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10041d7a1`

## string_xrefs

- `0x10041d7c3`: `Sql\DkTemp\sos\include\sossync.inl`

## pseudocode

```c
__int64 __fastcall SOS_RWLock::GetLock(__int64 a1, unsigned int a2, unsigned int a3, __int64 a4)
{
  __int64 v8; // rsi
  __int64 v9; // rbx
  __int64 v10; // rcx
  __int64 v11; // rax
  __int64 result; // rax

  v8 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v9 = *(_QWORD *)(v8 + 256);
  if ( !v9 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v9 = *(_QWORD *)(v8 + 256);
  }
  if ( *(_QWORD *)(a1 + 24) == v9 )
    utassert_fail(1u, "m_pExclusiveOwner != pWorker", "Sql\\DkTemp\\sos\\include\\sossync.inl", 1833, 0);
  if ( a3 )
  {
    v10 = *(_QWORD *)(v9 + 600);
    if ( v10 )
    {
      if ( *(_QWORD *)(v10 + 152) )
      {
        if ( (*(_DWORD *)(v10 + 188) & 4) != 0 )
        {
          v11 = *(_QWORD *)(v10 + 152);
          if ( (*(_BYTE *)(v11 + 616) & 1) == 0 && (*(_DWORD *)(v11 + 800) & 0x180) == 0 )
            return 2;
        }
      }
    }
  }
  result = SOS_RWLock::GetLongWait(a1, a2, a3, a4);
  if ( !(_DWORD)result && a2 == 2 )
    *(_QWORD *)(a1 + 24) = v9;
  return result;
}

```

## disassembly

```asm
0x10041d750  mov     [rsp+arg_0], rbx
0x10041d755  mov     [rsp+arg_8], rbp
0x10041d75a  mov     [rsp+arg_10], rsi
0x10041d75f  push    rdi
0x10041d760  push    r14
0x10041d762  push    r15
0x10041d764  sub     rsp, 30h
0x10041d768  mov     r11, gs:58h
0x10041d771  mov     r15, r9
0x10041d774  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10041d77b  mov     r14d, r8d
0x10041d77e  mov     ebp, edx
0x10041d780  mov     rdi, rcx
0x10041d783  mov     r10d, [rax]
0x10041d786  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10041d78d  mov     esi, [rax]
0x10041d78f  add     rsi, [r11+r10*8]
0x10041d793  mov     rbx, [rsi+100h]
0x10041d79a  test    rbx, rbx
0x10041d79d  jnz     short loc_10041D7AE
0x10041d79f  xor     ecx, ecx
0x10041d7a1  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10041d7a7  mov     rbx, [rsi+100h]
0x10041d7ae  cmp     [rdi+18h], rbx
0x10041d7b2  jnz     short loc_10041D7DC
0x10041d7b4  mov     r9d, 729h
0x10041d7ba  mov     [rsp+48h+var_28], 0
0x10041d7c3  lea     r8, ?szFileName@?6??GetLock@SOS_RWLock@@QEAA?AW4SOS_RESULT@@W4RWLockMode@@KPEBVSOS_WaitInfo@@@Z@4QBDB; "Sql\\DkTemp\\sos\\include\\sossync.inl"
0x10041d7ca  mov     ecx, 1
0x10041d7cf  lea     rdx, ?szExpression@?6??GetLock@SOS_RWLock@@QEAA?AW4SOS_RESULT@@W4RWLockMode@@KPEBVSOS_WaitInfo@@@Z@4QBDB; "m_pExclusiveOwner != pWorker"
0x10041d7d6  call    cs:__imp_?utassert_fail@@YAXIPEBD0H0ZZ; utassert_fail(uint,char const *,char const *,int,char const *,...)
0x10041d7dc  test    r14d, r14d
0x10041d7df  jz      short loc_10041D824
0x10041d7e1  mov     rcx, [rbx+258h]
0x10041d7e8  test    rcx, rcx
0x10041d7eb  jz      short loc_10041D824
0x10041d7ed  cmp     qword ptr [rcx+98h], 0
0x10041d7f5  jz      short loc_10041D824
0x10041d7f7  mov     eax, [rcx+0BCh]
0x10041d7fd  test    al, 4
0x10041d7ff  jz      short loc_10041D824
0x10041d801  mov     rax, [rcx+98h]
0x10041d808  test    byte ptr [rax+268h], 1
0x10041d80f  jnz     short loc_10041D824
0x10041d811  test    dword ptr [rax+320h], 180h
0x10041d81b  jnz     short loc_10041D824
0x10041d81d  mov     eax, 2
0x10041d822  jmp     short loc_10041D842
0x10041d824  mov     r9, r15
0x10041d827  mov     r8d, r14d
0x10041d82a  mov     edx, ebp
0x10041d82c  mov     rcx, rdi
0x10041d82f  call    cs:__imp_?GetLongWait@SOS_RWLock@@AEAA?AW4SOS_RESULT@@W4RWLockMode@@KPEBVSOS_WaitInfo@@@Z; SOS_RWLock::GetLongWait(RWLockMode,ulong,SOS_WaitInfo const *)
0x10041d835  test    eax, eax
0x10041d837  jnz     short loc_10041D842
0x10041d839  cmp     ebp, 2
0x10041d83c  jnz     short loc_10041D842
0x10041d83e  mov     [rdi+18h], rbx
0x10041d842  mov     rbx, [rsp+48h+arg_0]
0x10041d847  mov     rbp, [rsp+48h+arg_8]
0x10041d84c  mov     rsi, [rsp+48h+arg_10]
0x10041d851  add     rsp, 30h
0x10041d855  pop     r15
0x10041d857  pop     r14
0x10041d859  pop     rdi
0x10041d85a  retn
```
