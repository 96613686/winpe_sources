# CThread::Exit(long)

- ea: `0x180005d94`
- end: `0x180005e3b`
- name: `?Exit@CThread@@AEAAXJ@Z`
- size: `167`
- prototype: `void __fastcall __noreturn(CThread *__hidden this, DWORD dwExitCode)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180005d10`

## callees

- `0x180005d94`
- `0x180005e44`
- `0x180013810`
- `0x180014f54`
- `0x1800530c4`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x180005e34`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x180005e34`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180005dac`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180005e21`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180005dac`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180005e21`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall __noreturn CThread::Exit(CThread *this, DWORD dwExitCode)
{
  _QWORD **v4; // rcx
  CSynchLock *v5; // r8
  HMODULE v6; // rsi
  CSynchLock *v7[2]; // [rsp+20h] [rbp-18h] BYREF

  SetEvent(*((HANDLE *)this + 14));
  while ( _InterlockedCompareExchange((volatile signed __int32 *)this + 26, 4, *((_DWORD *)this + 26)) != 4 )
    ;
  *(_OWORD *)v7 = 0;
  CThread::thread_list(v7);
  v4 = (_QWORD **)*((_QWORD *)this + 12);
  v5 = v7[0];
  *v4[1] = *v4;
  (*v4)[1] = v4[1];
  --*((_QWORD *)v5 + 1);
  std::_Deallocate<16>(v4, 0x18u);
  v6 = (HMODULE)*((_QWORD *)this + 11);
  *((_QWORD *)this + 11) = 0;
  if ( v7[1] )
    CSynchLock::Unlock(v7[1]);
  SetEvent(*((HANDLE *)this + 15));
  CThread::Release(this);
  FreeLibraryAndExitThread(v6, dwExitCode);
}

```

## disassembly

```asm
0x180005d94  mov     [rsp+arg_0], rbx
0x180005d99  mov     [rsp+arg_8], rsi
0x180005d9e  push    rdi
0x180005d9f  sub     rsp, 30h
0x180005da3  mov     edi, edx
0x180005da5  mov     rbx, rcx
0x180005da8  mov     rcx, [rcx+70h]; hEvent
0x180005dac  call    cs:__imp_SetEvent
0x180005db2  mov     ecx, 4
0x180005db7  mov     eax, [rbx+68h]
0x180005dba  lock cmpxchg [rbx+68h], ecx
0x180005dbf  cmp     eax, ecx
0x180005dc1  jnz     short loc_180005DB7
0x180005dc3  xorps   xmm0, xmm0
0x180005dc6  movdqu  xmmword ptr [rsp+38h+var_18], xmm0
0x180005dcc  lea     rcx, [rsp+38h+var_18]
0x180005dd1  call    ?thread_list@CThread@@CAJPEAV?$locked_pointer@V?$list@PEAVCThread@@V?$allocator@PEAVCThread@@@std@@@std@@@@@Z; CThread::thread_list(locked_pointer<std::list<CThread *>> *)
0x180005dd6  mov     rcx, [rbx+60h]
0x180005dda  mov     r8, [rsp+38h+var_18]
0x180005ddf  mov     rdx, [rcx+8]
0x180005de3  mov     rax, [rcx]
0x180005de6  mov     [rdx], rax
0x180005de9  mov     rdx, [rcx]
0x180005dec  mov     rax, [rcx+8]
0x180005df0  mov     [rdx+8], rax
0x180005df4  dec     qword ptr [r8+8]
0x180005df8  mov     edx, 18h
0x180005dfd  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180005e02  mov     rsi, [rbx+58h]
0x180005e06  mov     qword ptr [rbx+58h], 0
0x180005e0e  mov     rcx, [rsp+38h+var_18+8]; this
0x180005e13  test    rcx, rcx
0x180005e16  jz      short loc_180005E1D
0x180005e18  call    ?Unlock@CSynchLock@@QEAAXXZ; CSynchLock::Unlock(void)
0x180005e1d  mov     rcx, [rbx+78h]; hEvent
0x180005e21  call    cs:__imp_SetEvent
0x180005e27  mov     rcx, rbx; this
0x180005e2a  call    ?Release@CThread@@AEBAJXZ; CThread::Release(void)
0x180005e2f  mov     edx, edi; dwExitCode
0x180005e31  mov     rcx, rsi; hLibModule
0x180005e34  call    cs:__imp_FreeLibraryAndExitThread
```
