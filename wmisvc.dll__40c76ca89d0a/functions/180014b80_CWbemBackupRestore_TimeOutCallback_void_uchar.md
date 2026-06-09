# CWbemBackupRestore::TimeOutCallback(void *,uchar)

- ea: `0x180014b80`
- end: `0x180014cd6`
- name: `?TimeOutCallback@CWbemBackupRestore@@SAXPEAXE@Z`
- size: `342`
- prototype: `void __fastcall(PVOID, __int64, __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180009f78`
- `0x180014b80`
- `0x180014d78`
- `0x180014f04`
- `0x180015044`
- `0x180020010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014bce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014bf3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014bce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014bf3`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x180014bc4`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x180014bc4`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180014c35`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180014c35`
- `wbemcomn!GetMemLogObject` at `0x180014c29`
- `wbemcomn!GetMemLogObject` at `0x180014c29`

## pseudocode

```c
void __fastcall CWbemBackupRestore::TimeOutCallback(PVOID a1, __int64 a2, __int64 a3)
{
  __int64 v4; // rsi
  int v5; // ebp
  DWORD LastError; // eax
  __int64 v7; // rdx
  __int64 v8; // r8
  int v9; // r14d
  CMemoryLog *MemLogObject; // rax
  __int64 v11; // rdx
  __int64 v12; // r8

  if ( a1 )
  {
    if ( _InterlockedCompareExchange((volatile signed __int32 *)a1 + 17, 1, 0) )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        WPP_SF_qqqd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          a2,
          a3,
          a1,
          *((_QWORD *)a1 + 7),
          *((_QWORD *)a1 + 5),
          *((_DWORD *)a1 + 17));
      }
    }
    else
    {
      v4 = *((_QWORD *)a1 + 5);
      v5 = 0;
      if ( v4 )
      {
        if ( DeleteTimerQueueTimer(0, *((HANDLE *)a1 + 5), 0) || GetLastError() == 997 )
        {
          *((_QWORD *)a1 + 5) = 0;
          v5 = 1;
        }
        else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
               && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
               && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          LastError = GetLastError();
          WPP_SF_qDq(*((_QWORD *)WPP_GLOBAL_Control + 2), v7, v8, v4, LastError, a1);
        }
      }
      v9 = CWbemBackupRestore::pResume((CWbemBackupRestore *)a1);
      MemLogObject = GetMemLogObject();
      CMemoryLog::Write(MemLogObject, -1);
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_qqDD(*((_QWORD *)WPP_GLOBAL_Control + 2), v11, v12, a1, v4, *((_DWORD *)a1 + 12), v9);
      }
      if ( v5 )
        (*(void (__fastcall **)(PVOID))(*(_QWORD *)a1 + 16LL))(a1);
    }
  }
}

```

## disassembly

```asm
0x180014b80  test    rcx, rcx
0x180014b83  jz      locret_180014CD5
0x180014b89  push    rbx
0x180014b8a  push    rbp
0x180014b8b  push    rsi
0x180014b8c  push    rdi
0x180014b8d  push    r14
0x180014b8f  push    r15
0x180014b91  sub     rsp, 48h
0x180014b95  xor     eax, eax
0x180014b97  mov     rbx, rcx
0x180014b9a  lea     r15d, [rax+1]
0x180014b9e  lock cmpxchg [rcx+44h], r15d
0x180014ba4  jnz     loc_180014C85
0x180014baa  mov     rsi, [rcx+28h]
0x180014bae  lea     rdi, WPP_GLOBAL_Control
0x180014bb5  xor     ebp, ebp
0x180014bb7  test    rsi, rsi
0x180014bba  jz      short loc_180014C1E
0x180014bbc  xor     r8d, r8d; CompletionEvent
0x180014bbf  mov     rdx, rsi; Timer
0x180014bc2  xor     ecx, ecx; TimerQueue
0x180014bc4  call    cs:__imp_DeleteTimerQueueTimer
0x180014bca  test    eax, eax
0x180014bcc  jnz     short loc_180014C17
0x180014bce  call    cs:__imp_GetLastError
0x180014bd4  cmp     eax, 3E5h
0x180014bd9  jz      short loc_180014C17
0x180014bdb  mov     rax, cs:WPP_GLOBAL_Control
0x180014be2  cmp     rax, rdi
0x180014be5  jz      short loc_180014C1E
0x180014be7  test    [rax+1Ch], r15b
0x180014beb  jz      short loc_180014C1E
0x180014bed  cmp     byte ptr [rax+19h], 5
0x180014bf1  jb      short loc_180014C1E
0x180014bf3  call    cs:__imp_GetLastError
0x180014bf9  mov     rcx, cs:WPP_GLOBAL_Control
0x180014c00  mov     r9, rsi
0x180014c03  mov     [rsp+78h+var_50], rbx
0x180014c08  mov     dword ptr [rsp+78h+var_58], eax
0x180014c0c  mov     rcx, [rcx+10h]
0x180014c10  call    WPP_SF_qDq
0x180014c15  jmp     short loc_180014C1E
0x180014c17  mov     [rbx+28h], rbp
0x180014c1b  mov     ebp, r15d
0x180014c1e  mov     rcx, rbx; this
0x180014c21  call    ?pResume@CWbemBackupRestore@@QEAAJXZ; CWbemBackupRestore::pResume(void)
0x180014c26  mov     r14d, eax
0x180014c29  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180014c2f  mov     rcx, rax
0x180014c32  or      edx, 0FFFFFFFFh
0x180014c35  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180014c3b  mov     rcx, cs:WPP_GLOBAL_Control
0x180014c42  cmp     rcx, rdi
0x180014c45  jz      short loc_180014C70
0x180014c47  test    [rcx+1Ch], r15b
0x180014c4b  jz      short loc_180014C70
0x180014c4d  cmp     byte ptr [rcx+19h], 2
0x180014c51  jb      short loc_180014C70
0x180014c53  mov     eax, [rbx+30h]
0x180014c56  mov     r9, rbx
0x180014c59  mov     rcx, [rcx+10h]
0x180014c5d  mov     [rsp+78h+var_48], r14d
0x180014c62  mov     dword ptr [rsp+78h+var_50], eax
0x180014c66  mov     [rsp+78h+var_58], rsi
0x180014c6b  call    WPP_SF_qqDD
0x180014c70  test    ebp, ebp
0x180014c72  jz      short loc_180014CC9
0x180014c74  mov     rax, [rbx]
0x180014c77  mov     rcx, rbx
0x180014c7a  mov     rax, [rax+10h]
0x180014c7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014c83  jmp     short loc_180014CC9
0x180014c85  mov     rcx, cs:WPP_GLOBAL_Control
0x180014c8c  lea     rdi, WPP_GLOBAL_Control
0x180014c93  cmp     rcx, rdi
0x180014c96  jz      short loc_180014CC9
0x180014c98  test    [rcx+1Ch], r15b
0x180014c9c  jz      short loc_180014CC9
0x180014c9e  cmp     byte ptr [rcx+19h], 5
0x180014ca2  jb      short loc_180014CC9
0x180014ca4  mov     eax, [rbx+44h]
0x180014ca7  mov     r9, rbx
0x180014caa  mov     rcx, [rcx+10h]
0x180014cae  mov     [rsp+78h+var_48], eax
0x180014cb2  mov     rax, [rbx+28h]
0x180014cb6  mov     [rsp+78h+var_50], rax
0x180014cbb  mov     rax, [rbx+38h]
0x180014cbf  mov     [rsp+78h+var_58], rax
0x180014cc4  call    WPP_SF_qqqd
0x180014cc9  add     rsp, 48h
0x180014ccd  pop     r15
0x180014ccf  pop     r14
0x180014cd1  pop     rdi
0x180014cd2  pop     rsi
0x180014cd3  pop     rbp
0x180014cd4  pop     rbx
0x180014cd5  retn
```
