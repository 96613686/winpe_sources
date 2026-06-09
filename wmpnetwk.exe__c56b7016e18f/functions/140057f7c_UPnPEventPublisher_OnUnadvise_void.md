# UPnPEventPublisher::OnUnadvise(void)

- ea: `0x140057f7c`
- end: `0x140058068`
- name: `?OnUnadvise@UPnPEventPublisher@@QEAAJXZ`
- size: `236`
- prototype: `__int64 __fastcall(UPnPEventPublisher *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x140058930`
- `0x14005b670`
- `0x14005f910`

## callees

- `0x140057f7c`
- `0x14009e010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x140057f95`
- `KERNEL32!EnterCriticalSection` at `0x140057f95`
- `KERNEL32!LeaveCriticalSection` at `0x140058056`
- `KERNEL32!LeaveCriticalSection` at `0x140058056`
- `KERNEL32!DeleteTimerQueueTimer` at `0x140058044`
- `KERNEL32!DeleteTimerQueueTimer` at `0x140058044`
- `ole32!CoReleaseMarshalData` at `0x140057fde`
- `ole32!CoReleaseMarshalData` at `0x140057fde`

## pseudocode

```c
__int64 __fastcall UPnPEventPublisher::OnUnadvise(UPnPEventPublisher *this)
{
  BOOL v2; // edi
  volatile __int64 *v3; // rcx
  __int64 v4; // rcx
  unsigned int v5; // ecx
  void *v6; // rdx

  v2 = 0;
  *((_DWORD *)this + 36) = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  v3 = (volatile __int64 *)*((_QWORD *)this + 17);
  *((_DWORD *)this + 36) = 0;
  if ( v3 )
    v2 = _InterlockedExchange64(v3, 0) != 0;
  v4 = *((_QWORD *)this + 2);
  if ( v4 )
  {
    (*(void (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v4 + 40LL))(v4, 0, 0, 0);
    CoReleaseMarshalData(*((LPSTREAM *)this + 2));
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 2) + 16LL))(*((_QWORD *)this + 2));
    *((_QWORD *)this + 2) = 0;
  }
  v5 = 0;
  *((_DWORD *)this + 26) = 0;
  for ( *((_DWORD *)this + 32) = 0; v5 < *((_DWORD *)this + 14); ++v5 )
  {
    if ( !*((_DWORD *)this + 4 * v5 + 6) )
      *((_WORD *)this + 8 * v5 + 18) = 0;
  }
  if ( v2 )
  {
    v6 = (void *)*((_QWORD *)this + 15);
    if ( v6 )
    {
      DeleteTimerQueueTimer(*((HANDLE *)this + 14), v6, 0);
      *((_QWORD *)this + 15) = 0;
    }
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  return 0;
}

```

## disassembly

```asm
0x140057f7c  push    rbx
0x140057f7e  push    rsi
0x140057f7f  push    rdi
0x140057f80  push    r14
0x140057f82  sub     rsp, 38h
0x140057f86  mov     rbx, rcx
0x140057f89  xor     edi, edi
0x140057f8b  mov     [rcx+90h], edi
0x140057f91  add     rcx, 40h ; '@'; lpCriticalSection
0x140057f95  call    cs:__imp_EnterCriticalSection
0x140057f9b  mov     rcx, [rbx+88h]
0x140057fa2  lea     r14d, [rdi+1]
0x140057fa6  mov     [rbx+90h], edi
0x140057fac  test    rcx, rcx
0x140057faf  jz      short loc_140057FBD
0x140057fb1  xor     eax, eax
0x140057fb3  xchg    rax, [rcx]
0x140057fb6  test    rax, rax
0x140057fb9  cmovnz  edi, r14d
0x140057fbd  mov     rcx, [rbx+10h]
0x140057fc1  test    rcx, rcx
0x140057fc4  jz      short loc_140057FFC
0x140057fc6  mov     rax, [rcx]
0x140057fc9  xor     edx, edx
0x140057fcb  xor     r9d, r9d
0x140057fce  xor     r8d, r8d
0x140057fd1  mov     rax, [rax+28h]
0x140057fd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140057fda  mov     rcx, [rbx+10h]; pStm
0x140057fde  call    cs:__imp_CoReleaseMarshalData
0x140057fe4  mov     rcx, [rbx+10h]
0x140057fe8  mov     rax, [rcx]
0x140057feb  mov     rax, [rax+10h]
0x140057fef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140057ff4  mov     qword ptr [rbx+10h], 0
0x140057ffc  xor     ecx, ecx
0x140057ffe  mov     dword ptr [rbx+68h], 0
0x140058005  mov     dword ptr [rbx+80h], 0
0x14005800f  cmp     [rbx+38h], ecx
0x140058012  jbe     short loc_14005802F
0x140058014  mov     eax, ecx
0x140058016  add     rax, rax
0x140058019  cmp     dword ptr [rbx+rax*8+18h], 0
0x14005801e  jnz     short loc_140058027
0x140058020  mov     word ptr [rbx+rax*8+24h], 0
0x140058027  add     ecx, r14d
0x14005802a  cmp     ecx, [rbx+38h]
0x14005802d  jb      short loc_140058014
0x14005802f  cmp     edi, r14d
0x140058032  jnz     short loc_140058052
0x140058034  mov     rdx, [rbx+78h]; Timer
0x140058038  test    rdx, rdx
0x14005803b  jz      short loc_140058052
0x14005803d  mov     rcx, [rbx+70h]; TimerQueue
0x140058041  xor     r8d, r8d; CompletionEvent
0x140058044  call    cs:__imp_DeleteTimerQueueTimer
0x14005804a  mov     qword ptr [rbx+78h], 0
0x140058052  lea     rcx, [rbx+40h]; lpCriticalSection
0x140058056  call    cs:__imp_LeaveCriticalSection
0x14005805c  xor     eax, eax
0x14005805e  add     rsp, 38h
0x140058062  pop     r14
0x140058064  pop     rdi
0x140058065  pop     rsi
0x140058066  pop     rbx
0x140058067  retn
```
