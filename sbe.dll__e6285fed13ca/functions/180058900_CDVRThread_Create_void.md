# CDVRThread::Create(void)

- ea: `0x180058900`
- end: `0x180058993`
- name: `?Create@CDVRThread@@QEAAHXZ`
- size: `147`
- prototype: `__int64 __fastcall(CDVRThread *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800443a8`

## callees

- `0x180001c00`
- `0x180058900`

## import_xrefs

- `KERNEL32!CreateThread` at `0x180058958`
- `KERNEL32!CreateThread` at `0x180058958`
- `KERNEL32!LeaveCriticalSection` at `0x180058973`
- `KERNEL32!LeaveCriticalSection` at `0x180058973`
- `KERNEL32!EnterCriticalSection` at `0x18005892b`
- `KERNEL32!EnterCriticalSection` at `0x18005892b`

## pseudocode

```c
_BOOL8 __fastcall CDVRThread::Create(struct _RTL_CRITICAL_SECTION *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rdi
  HANDLE v3; // rax
  BOOL v4; // ebx
  DWORD ThreadId; // [rsp+30h] [rbp-18h] BYREF

  v1 = this + 1;
  ThreadId = 0;
  EnterCriticalSection(this + 1);
  v4 = 0;
  if ( !this->SpinCount )
  {
    v3 = CreateThread(0, 0, CDVRThread::InitialThreadProc, this, 0, &ThreadId);
    this->SpinCount = (ULONG_PTR)v3;
    if ( v3 )
      v4 = 1;
  }
  LeaveCriticalSection(v1);
  return v4;
}

```

## disassembly

```asm
0x180058900  mov     [rsp+arg_8], rbx
0x180058905  push    rdi
0x180058906  sub     rsp, 40h
0x18005890a  mov     rax, cs:__security_cookie
0x180058911  xor     rax, rsp
0x180058914  mov     [rsp+48h+var_10], rax
0x180058919  lea     rdi, [rcx+28h]
0x18005891d  mov     [rsp+48h+ThreadId], 0
0x180058925  mov     rbx, rcx
0x180058928  mov     rcx, rdi; lpCriticalSection
0x18005892b  call    cs:__imp_EnterCriticalSection
0x180058931  cmp     qword ptr [rbx+20h], 0
0x180058936  jnz     short loc_18005896E
0x180058938  lea     rax, [rsp+48h+ThreadId]
0x18005893d  mov     r9, rbx; lpParameter
0x180058940  mov     [rsp+48h+lpThreadId], rax; lpThreadId
0x180058945  lea     r8, ?InitialThreadProc@CDVRThread@@SAKPEAX@Z; lpStartAddress
0x18005894c  xor     edx, edx; dwStackSize
0x18005894e  mov     [rsp+48h+dwCreationFlags], 0; dwCreationFlags
0x180058956  xor     ecx, ecx; lpThreadAttributes
0x180058958  call    cs:__imp_CreateThread
0x18005895e  mov     [rbx+20h], rax
0x180058962  test    rax, rax
0x180058965  jz      short loc_18005896E
0x180058967  mov     ebx, 1
0x18005896c  jmp     short loc_180058970
0x18005896e  xor     ebx, ebx
0x180058970  mov     rcx, rdi; lpCriticalSection
0x180058973  call    cs:__imp_LeaveCriticalSection
0x180058979  mov     eax, ebx
0x18005897b  mov     rcx, [rsp+48h+var_10]
0x180058980  xor     rcx, rsp; StackCookie
0x180058983  call    __security_check_cookie
0x180058988  mov     rbx, [rsp+48h+arg_8]
0x18005898d  add     rsp, 40h
0x180058991  pop     rdi
0x180058992  retn
```
