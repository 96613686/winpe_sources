# LISTENER_CHANNEL::StopListenerChannel(int)

- ea: `0x18000b4ec`
- end: `0x18000b627`
- name: `?StopListenerChannel@LISTENER_CHANNEL@@QEAAJH@Z`
- size: `315`
- prototype: `__int64 __fastcall(LISTENER_CHANNEL *__hidden this, int)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000bc3c`
- `0x18000bdc4`

## callees

- `0x1800069cc`
- `0x18000b2fc`
- `0x18000b4ec`
- `0x18000e010`

## import_xrefs

- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000b5e8`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000b5e8`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000b50d`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000b50d`

## pseudocode

```c
__int64 __fastcall LISTENER_CHANNEL::StopListenerChannel(LISTENER_CHANNEL *this, int a2)
{
  CReaderWriterLock3 *v2; // rbp
  __int64 v5; // rbx
  W3WP_HOST *v6; // rcx
  int v7; // edi
  char *v8; // rdi
  _QWORD *v9; // rax
  __int64 v10; // rcx
  char **v11; // r8

  v2 = (LISTENER_CHANNEL *)((char *)this + 280);
  CReaderWriterLock3::WriteLock((LISTENER_CHANNEL *)((char *)this + 280));
  v5 = *((_QWORD *)this + 39);
  if ( v5 )
  {
    *((_QWORD *)this + 39) = 0;
    if ( !_InterlockedCompareExchange((volatile signed __int32 *)(v5 + 32), 1, 0) )
      _InterlockedAdd(&W3WP_HOST_WORKITEM::sm_OutstandingWorkItemCount, 1u);
    *(_DWORD *)(v5 + 48) = a2;
    if ( ((*((_DWORD *)this + 66) - 2) & 0xFFFFFFFD) != 0 )
    {
      *((_DWORD *)this + 66) = 4;
      LISTENER_CHANNEL_WORKITEM::SetListenerChannel((LISTENER_CHANNEL_WORKITEM *)v5, this);
      v7 = W3WP_HOST::QueueWorkItem(v6, (struct W3WP_HOST_WORKITEM *)v5);
      if ( v7 < 0 )
        goto LABEL_16;
    }
    else
    {
      v8 = (char *)this + 296;
      while ( 1 )
      {
        v9 = *(_QWORD **)v8;
        if ( *(char **)v8 == v8 )
          break;
        if ( (char *)v9[1] != v8 )
          goto LABEL_19;
        v10 = *v9;
        if ( *(_QWORD **)(*v9 + 8LL) != v9 )
          goto LABEL_19;
        *(_QWORD *)v8 = v10;
        *(_QWORD *)(v10 + 8) = v8;
        if ( v9 != (_QWORD *)16 )
          (*(void (__fastcall **)(_QWORD *, __int64))*(v9 - 2))(v9 - 2, 1);
      }
      v11 = (char **)*((_QWORD *)v8 + 1);
      if ( *v11 != v8 )
LABEL_19:
        __fastfail(3u);
      *(_QWORD *)(v5 + 16) = v8;
      *(_QWORD *)(v5 + 24) = v11;
      *v11 = (char *)(v5 + 16);
      *((_QWORD *)v8 + 1) = v5 + 16;
    }
  }
  v5 = 0;
  v7 = 0;
LABEL_16:
  CReaderWriterLock3::WriteUnlock(v2);
  if ( v5 )
    (**(void (__fastcall ***)(__int64, __int64))v5)(v5, 1);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18000b4ec  mov     [rsp+arg_8], rbx
0x18000b4f1  mov     [rsp+arg_10], rbp
0x18000b4f6  push    rsi
0x18000b4f7  push    rdi
0x18000b4f8  push    r14
0x18000b4fa  sub     rsp, 20h
0x18000b4fe  lea     rbp, [rcx+118h]
0x18000b505  mov     rdi, rcx
0x18000b508  mov     rcx, rbp
0x18000b50b  mov     esi, edx
0x18000b50d  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x18000b514  nop     dword ptr [rax+rax+00h]
0x18000b519  mov     rbx, [rdi+138h]
0x18000b520  mov     r14d, 1
0x18000b526  test    rbx, rbx
0x18000b529  jz      loc_18000B5E1
0x18000b52f  mov     qword ptr [rdi+138h], 0
0x18000b53a  xor     eax, eax
0x18000b53c  lock cmpxchg [rbx+20h], r14d
0x18000b542  jnz     short loc_18000B54C
0x18000b544  lock add cs:?sm_OutstandingWorkItemCount@W3WP_HOST_WORKITEM@@0JA, r14d; long W3WP_HOST_WORKITEM::sm_OutstandingWorkItemCount
0x18000b54c  mov     [rbx+30h], esi
0x18000b54f  mov     eax, [rdi+108h]
0x18000b555  sub     eax, 2
0x18000b558  test    eax, 0FFFFFFFDh
0x18000b55d  jz      short loc_18000B584
0x18000b55f  mov     rdx, rdi; struct LISTENER_CHANNEL *
0x18000b562  mov     dword ptr [rdi+108h], 4
0x18000b56c  mov     rcx, rbx; this
0x18000b56f  call    ?SetListenerChannel@LISTENER_CHANNEL_WORKITEM@@QEAAXPEAVLISTENER_CHANNEL@@@Z; LISTENER_CHANNEL_WORKITEM::SetListenerChannel(LISTENER_CHANNEL *)
0x18000b574  mov     rdx, rbx; struct W3WP_HOST_WORKITEM *
0x18000b577  call    ?QueueWorkItem@W3WP_HOST@@QEAAJPEAVW3WP_HOST_WORKITEM@@@Z; W3WP_HOST::QueueWorkItem(W3WP_HOST_WORKITEM *)
0x18000b57c  mov     edi, eax
0x18000b57e  test    eax, eax
0x18000b580  js      short loc_18000B5E5
0x18000b582  jmp     short loc_18000B5E1
0x18000b584  add     rdi, 128h
0x18000b58b  mov     rax, [rdi]
0x18000b58e  cmp     rax, rdi
0x18000b591  jz      short loc_18000B5C6
0x18000b593  cmp     [rax+8], rdi
0x18000b597  jnz     loc_18000B620
0x18000b59d  mov     rcx, [rax]
0x18000b5a0  cmp     [rcx+8], rax
0x18000b5a4  jnz     short loc_18000B620
0x18000b5a6  mov     [rdi], rcx
0x18000b5a9  mov     [rcx+8], rdi
0x18000b5ad  lea     rcx, [rax-10h]
0x18000b5b1  test    rcx, rcx
0x18000b5b4  jz      short loc_18000B58B
0x18000b5b6  mov     rax, [rcx]
0x18000b5b9  mov     edx, r14d
0x18000b5bc  mov     rax, [rax]
0x18000b5bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b5c4  jmp     short loc_18000B58B
0x18000b5c6  mov     r8, [rdi+8]
0x18000b5ca  cmp     [r8], rdi
0x18000b5cd  jnz     short loc_18000B620
0x18000b5cf  lea     rax, [rbx+10h]
0x18000b5d3  mov     [rax], rdi
0x18000b5d6  mov     [rax+8], r8
0x18000b5da  mov     [r8], rax
0x18000b5dd  mov     [rdi+8], rax
0x18000b5e1  xor     ebx, ebx
0x18000b5e3  xor     edi, edi
0x18000b5e5  mov     rcx, rbp
0x18000b5e8  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x18000b5ef  nop     dword ptr [rax+rax+00h]
0x18000b5f4  test    rbx, rbx
0x18000b5f7  jz      short loc_18000B60A
0x18000b5f9  mov     rax, [rbx]
0x18000b5fc  mov     edx, r14d
0x18000b5ff  mov     rcx, rbx
0x18000b602  mov     rax, [rax]
0x18000b605  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b60a  mov     rbx, [rsp+38h+arg_8]
0x18000b60f  mov     eax, edi
0x18000b611  mov     rbp, [rsp+38h+arg_10]
0x18000b616  add     rsp, 20h
0x18000b61a  pop     r14
0x18000b61c  pop     rdi
0x18000b61d  pop     rsi
0x18000b61e  retn
0x18000b620  mov     ecx, 3
0x18000b625  int     29h; Win8: RtlFailFast(ecx)
```
