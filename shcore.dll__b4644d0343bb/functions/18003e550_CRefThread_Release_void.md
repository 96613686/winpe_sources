# CRefThread::Release(void)

- ea: `0x18003e550`
- end: `0x18003e5c7`
- name: `?Release@CRefThread@@UEAAKXZ`
- size: `119`
- prototype: `unsigned int __fastcall(CRefThread *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18003e550`
- `0x180095010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18003e5bf`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18003e5bf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003e576`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003e576`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!PostThreadMessageW` at `0x18003e5b4`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!PostThreadMessageW` at `0x18003e5b4`

## pseudocode

```c
__int64 __fastcall CRefThread::Release(CRefThread *this)
{
  DWORD v1; // esi
  void *v2; // rdi
  unsigned __int32 v3; // ebx

  v1 = *((_DWORD *)this + 4);
  v2 = (void *)*((_QWORD *)this + 3);
  v3 = _InterlockedDecrement(*((volatile signed __int32 **)this + 1));
  if ( !v3 )
    (*(void (__fastcall **)(CRefThread *, __int64))(*(_QWORD *)this + 32LL))(this, 1);
  if ( v1 != GetCurrentThreadId() )
  {
    if ( v2 )
      SetEvent(v2);
    else
      PostThreadMessageW(v1, 0, 0, 0);
  }
  return v3;
}

```

## disassembly

```asm
0x18003e550  mov     [rsp+arg_0], rbx
0x18003e555  mov     [rsp+arg_8], rsi
0x18003e55a  push    rdi
0x18003e55b  sub     rsp, 20h
0x18003e55f  mov     esi, [rcx+10h]
0x18003e562  or      ebx, 0FFFFFFFFh
0x18003e565  mov     rdi, [rcx+18h]
0x18003e569  mov     rax, [rcx+8]
0x18003e56d  lock xadd [rax], ebx
0x18003e571  sub     ebx, 1
0x18003e574  jz      short loc_18003E592
0x18003e576  call    cs:__imp_GetCurrentThreadId
0x18003e57c  cmp     esi, eax
0x18003e57e  jnz     short loc_18003E5A5
0x18003e580  mov     rsi, [rsp+28h+arg_8]
0x18003e585  mov     eax, ebx
0x18003e587  mov     rbx, [rsp+28h+arg_0]
0x18003e58c  add     rsp, 20h
0x18003e590  pop     rdi
0x18003e591  retn
0x18003e592  mov     rax, [rcx]
0x18003e595  mov     edx, 1
0x18003e59a  mov     rax, [rax+20h]
0x18003e59e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e5a3  jmp     short loc_18003E576
0x18003e5a5  test    rdi, rdi
0x18003e5a8  jnz     short loc_18003E5BC
0x18003e5aa  xor     r9d, r9d; lParam
0x18003e5ad  xor     r8d, r8d; wParam
0x18003e5b0  xor     edx, edx; Msg
0x18003e5b2  mov     ecx, esi; idThread
0x18003e5b4  call    cs:__imp_PostThreadMessageW
0x18003e5ba  jmp     short loc_18003E580
0x18003e5bc  mov     rcx, rdi; hEvent
0x18003e5bf  call    cs:__imp_SetEvent
0x18003e5c5  jmp     short loc_18003E580
```
