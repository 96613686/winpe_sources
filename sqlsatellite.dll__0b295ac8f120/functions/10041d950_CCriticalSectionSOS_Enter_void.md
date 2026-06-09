# CCriticalSectionSOS::Enter(void)

- ea: `0x10041d950`
- end: `0x10041da6f`
- name: `?Enter@CCriticalSectionSOS@@QEAAXXZ`
- size: `287`
- prototype: `void __fastcall(CCriticalSectionSOS *__hidden this)`
- caller_count: `64`
- callee_count: `1`
- tags: ``

## callers

- `0x100426760`
- `0x1004269b0`
- `0x100427e60`
- `0x100428450`
- `0x100428e20`
- `0x10042c7f0`
- `0x10042ca80`
- `0x10042cd20`
- `0x10042cf60`
- `0x10042d3c0`
- `0x10042dd60`
- `0x10042e120`
- `0x10042e690`
- `0x10042eed0`
- `0x10042f890`
- `0x10042fa70`
- `0x10042fdb0`
- `0x100430130`
- `0x100430970`
- `0x100430e50`
- `0x100431170`
- `0x100431af0`
- `0x100431f20`
- `0x100432600`
- `0x100432820`
- `0x100433010`
- `0x100433110`
- `0x100433340`
- `0x100433440`
- `0x100433a70`
- `0x10043a0f0`
- `0x10043ff90`
- `0x100442df0`
- `0x100443700`
- `0x100444130`
- `0x1004447d0`
- `0x100444980`
- `0x1004454b0`
- `0x100445880`
- `0x100445bc0`
- `0x100446500`
- `0x100446730`
- `0x1004490f0`
- `0x1004494a0`
- `0x100449680`
- `0x10044a0a0`
- `0x10044a530`
- `0x10044a720`
- `0x10044a8c0`
- `0x10044c0b0`

## callees

- `0x10041d950`

## import_xrefs

- `sqldk!?LongWait@SOS_UnfairRecursiveMutexExtendedGuarantee@@AEAA?AW4SOS_RESULT@@PEAVWorker@@KQEBVSOS_WaitInfo@@@Z` at `0x10041da3f`
- `sqldk!?LongWait@SOS_UnfairRecursiveMutexExtendedGuarantee@@AEAA?AW4SOS_RESULT@@PEAVWorker@@KQEBVSOS_WaitInfo@@@Z` at `0x10041da3f`
- `sqldk!SystemThread_TlsIndex` at `0x10041d97d`
- `sqldk!SystemThread_TlsIndex` at `0x10041d9f7`
- `sqldk!SystemThread_TlsOffset` at `0x10041d986`
- `sqldk!SystemThread_TlsOffset` at `0x10041da00`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10041d9a1`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10041da1b`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10041d9a1`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10041da1b`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CCriticalSectionSOS::Enter(CCriticalSectionSOS *this)
{
  __int64 v2; // rdi
  __int64 v3; // rbx
  __int64 v4; // rdi
  __int64 v5; // rsi
  __int64 v6; // rdx
  int v7; // [rsp+28h] [rbp-40h]
  int v8; // [rsp+38h] [rbp-30h] BYREF
  __int64 v9; // [rsp+40h] [rbp-28h]
  __int64 v10; // [rsp+48h] [rbp-20h]
  __int64 v11; // [rsp+50h] [rbp-18h]
  __int64 v12; // [rsp+58h] [rbp-10h]

  v2 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v3 = *(_QWORD *)(v2 + 256);
  if ( !v3 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v3 = *(_QWORD *)(v2 + 256);
  }
  v7 = !(*(_BYTE *)(v3 + 616) & 1);
  *(_DWORD *)(v3 + 616) |= 1u;
  v8 = 4194679;
  v9 = 0;
  v11 = 0;
  v10 = 0;
  v12 = 0;
  v4 = *((_QWORD *)this + 1);
  v5 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v6 = *(_QWORD *)(v5 + 256);
  if ( !v6 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v6 = *(_QWORD *)(v5 + 256);
  }
  if ( v6 == *(_QWORD *)(v4 + 32) )
    ++*(_QWORD *)(v4 + 56);
  else
    SOS_UnfairRecursiveMutexExtendedGuarantee::LongWait(v4, v6, 0xFFFFFFFFLL, &v8, -2);
  *(_DWORD *)(v3 + 616) &= ~v7;
}

```

## disassembly

```asm
0x10041d950  mov     rax, rsp
0x10041d953  push    rdi
0x10041d954  sub     rsp, 60h
0x10041d958  mov     qword ptr [rax-48h], 0FFFFFFFFFFFFFFFEh
0x10041d960  mov     [rax+8], rbx
0x10041d964  mov     [rax+10h], rbp
0x10041d968  mov     [rax+18h], rsi
0x10041d96c  mov     rsi, rcx
0x10041d96f  xor     ebp, ebp
0x10041d971  mov     [rax-40h], ebp
0x10041d974  mov     r8, gs:58h
0x10041d97d  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10041d984  mov     edx, [rax]
0x10041d986  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10041d98d  mov     edi, [rax]
0x10041d98f  add     rdi, [r8+rdx*8]
0x10041d993  mov     rbx, [rdi+100h]
0x10041d99a  test    rbx, rbx
0x10041d99d  jnz     short loc_10041D9AE
0x10041d99f  xor     ecx, ecx
0x10041d9a1  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10041d9a7  mov     rbx, [rdi+100h]
0x10041d9ae  mov     [rsp+68h+var_38], rbx
0x10041d9b3  mov     ecx, [rbx+268h]
0x10041d9b9  mov     eax, ecx
0x10041d9bb  and     eax, 1
0x10041d9be  xor     eax, 1
0x10041d9c1  mov     [rsp+68h+var_40], eax
0x10041d9c5  or      ecx, 1
0x10041d9c8  mov     [rbx+268h], ecx
0x10041d9ce  mov     [rsp+68h+var_30], 400177h
0x10041d9d6  mov     [rsp+68h+var_28], rbp
0x10041d9db  mov     [rsp+68h+var_18], rbp
0x10041d9e0  mov     [rsp+68h+var_20], rbp
0x10041d9e5  mov     [rsp+68h+var_10], rbp
0x10041d9ea  mov     rdi, [rsi+8]
0x10041d9ee  mov     rdx, gs:58h
0x10041d9f7  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10041d9fe  mov     ecx, [rax]
0x10041da00  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10041da07  mov     esi, [rax]
0x10041da09  add     rsi, [rdx+rcx*8]
0x10041da0d  mov     rdx, [rsi+100h]
0x10041da14  test    rdx, rdx
0x10041da17  jnz     short loc_10041DA28
0x10041da19  xor     ecx, ecx
0x10041da1b  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10041da21  mov     rdx, [rsi+100h]
0x10041da28  mov     rax, [rdi+20h]
0x10041da2c  cmp     rdx, rax
0x10041da2f  jz      short loc_10041DA47
0x10041da31  lea     r9, [rsp+68h+var_30]
0x10041da36  mov     r8d, 0FFFFFFFFh
0x10041da3c  mov     rcx, rdi
0x10041da3f  call    cs:__imp_?LongWait@SOS_UnfairRecursiveMutexExtendedGuarantee@@AEAA?AW4SOS_RESULT@@PEAVWorker@@KQEBVSOS_WaitInfo@@@Z; SOS_UnfairRecursiveMutexExtendedGuarantee::LongWait(Worker *,ulong,SOS_WaitInfo const * const)
0x10041da45  jmp     short loc_10041DA4B
0x10041da47  inc     qword ptr [rdi+38h]
0x10041da4b  mov     eax, [rsp+68h+var_40]
0x10041da4f  not     eax
0x10041da51  and     [rbx+268h], eax
0x10041da57  mov     rbx, [rsp+68h+arg_0]
0x10041da5c  mov     rbp, [rsp+68h+arg_8]
0x10041da61  mov     rsi, [rsp+68h+arg_10]
0x10041da69  add     rsp, 60h
0x10041da6d  pop     rdi
0x10041da6e  retn
```
