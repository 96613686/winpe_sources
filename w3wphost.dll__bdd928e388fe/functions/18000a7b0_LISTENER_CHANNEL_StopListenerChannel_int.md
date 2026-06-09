# LISTENER_CHANNEL::StopListenerChannel(int)

- ea: `0x18000a7b0`
- end: `0x18000a8da`
- name: `?StopListenerChannel@LISTENER_CHANNEL@@QEAAJH@Z`
- size: `298`
- prototype: `__int64 __fastcall(LISTENER_CHANNEL *__hidden this, int)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000aea8`
- `0x18000affc`

## callees

- `0x1800063a0`
- `0x18000a5e8`
- `0x18000a7b0`
- `0x18000d010`

## import_xrefs

- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000a8a2`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000a8a2`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000a7d1`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000a7d1`

## pseudocode

```c
__int64 __fastcall LISTENER_CHANNEL::StopListenerChannel(LISTENER_CHANNEL *this, int a2)
{
  CReaderWriterLock3 *v2; // rbp
  __int64 v5; // rbx
  W3WP_HOST *v6; // rcx
  signed int v7; // edi
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
0x18000a7b0  mov     [rsp+arg_8], rbx
0x18000a7b5  mov     [rsp+arg_10], rbp
0x18000a7ba  push    rsi
0x18000a7bb  push    rdi
0x18000a7bc  push    r14
0x18000a7be  sub     rsp, 20h
0x18000a7c2  lea     rbp, [rcx+118h]
0x18000a7c9  mov     rdi, rcx
0x18000a7cc  mov     rcx, rbp
0x18000a7cf  mov     esi, edx
0x18000a7d1  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x18000a7d7  mov     rbx, [rdi+138h]
0x18000a7de  mov     r14d, 1
0x18000a7e4  test    rbx, rbx
0x18000a7e7  jz      loc_18000A89B
0x18000a7ed  mov     qword ptr [rdi+138h], 0
0x18000a7f8  xor     eax, eax
0x18000a7fa  lock cmpxchg [rbx+20h], r14d
0x18000a800  jnz     short loc_18000A80A
0x18000a802  lock add cs:?sm_OutstandingWorkItemCount@W3WP_HOST_WORKITEM@@0JA, r14d; long W3WP_HOST_WORKITEM::sm_OutstandingWorkItemCount
0x18000a80a  mov     [rbx+30h], esi
0x18000a80d  mov     eax, [rdi+108h]
0x18000a813  sub     eax, 2
0x18000a816  test    eax, 0FFFFFFFDh
0x18000a81b  jz      short loc_18000A842
0x18000a81d  mov     rdx, rdi; struct LISTENER_CHANNEL *
0x18000a820  mov     dword ptr [rdi+108h], 4
0x18000a82a  mov     rcx, rbx; this
0x18000a82d  call    ?SetListenerChannel@LISTENER_CHANNEL_WORKITEM@@QEAAXPEAVLISTENER_CHANNEL@@@Z; LISTENER_CHANNEL_WORKITEM::SetListenerChannel(LISTENER_CHANNEL *)
0x18000a832  mov     rdx, rbx; struct W3WP_HOST_WORKITEM *
0x18000a835  call    ?QueueWorkItem@W3WP_HOST@@QEAAJPEAVW3WP_HOST_WORKITEM@@@Z; W3WP_HOST::QueueWorkItem(W3WP_HOST_WORKITEM *)
0x18000a83a  mov     edi, eax
0x18000a83c  test    eax, eax
0x18000a83e  js      short loc_18000A89F
0x18000a840  jmp     short loc_18000A89B
0x18000a842  add     rdi, 128h
0x18000a849  mov     rax, [rdi]
0x18000a84c  cmp     rax, rdi
0x18000a84f  jz      short loc_18000A880
0x18000a851  cmp     [rax+8], rdi
0x18000a855  jnz     short loc_18000A8D3
0x18000a857  mov     rcx, [rax]
0x18000a85a  cmp     [rcx+8], rax
0x18000a85e  jnz     short loc_18000A8D3
0x18000a860  mov     [rdi], rcx
0x18000a863  mov     [rcx+8], rdi
0x18000a867  lea     rcx, [rax-10h]
0x18000a86b  test    rcx, rcx
0x18000a86e  jz      short loc_18000A849
0x18000a870  mov     rax, [rcx]
0x18000a873  mov     edx, r14d
0x18000a876  mov     rax, [rax]
0x18000a879  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a87e  jmp     short loc_18000A849
0x18000a880  mov     r8, [rdi+8]
0x18000a884  cmp     [r8], rdi
0x18000a887  jnz     short loc_18000A8D3
0x18000a889  lea     rax, [rbx+10h]
0x18000a88d  mov     [rax], rdi
0x18000a890  mov     [rax+8], r8
0x18000a894  mov     [r8], rax
0x18000a897  mov     [rdi+8], rax
0x18000a89b  xor     ebx, ebx
0x18000a89d  xor     edi, edi
0x18000a89f  mov     rcx, rbp
0x18000a8a2  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x18000a8a8  test    rbx, rbx
0x18000a8ab  jz      short loc_18000A8BE
0x18000a8ad  mov     rax, [rbx]
0x18000a8b0  mov     edx, r14d
0x18000a8b3  mov     rcx, rbx
0x18000a8b6  mov     rax, [rax]
0x18000a8b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a8be  mov     rbx, [rsp+38h+arg_8]
0x18000a8c3  mov     eax, edi
0x18000a8c5  mov     rbp, [rsp+38h+arg_10]
0x18000a8ca  add     rsp, 20h
0x18000a8ce  pop     r14
0x18000a8d0  pop     rdi
0x18000a8d1  pop     rsi
0x18000a8d2  retn
0x18000a8d3  mov     ecx, 3
0x18000a8d8  int     29h; Win8: RtlFailFast(ecx)
```
