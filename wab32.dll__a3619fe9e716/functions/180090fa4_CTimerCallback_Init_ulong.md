# CTimerCallback::_Init(ulong)

- ea: `0x180090fa4`
- end: `0x18009106d`
- name: `?_Init@CTimerCallback@@AEAAJK@Z`
- size: `201`
- prototype: `__int64 __fastcall(CTimerCallback *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180090dcc`

## callees

- `0x18000161c`
- `0x18007b01c`
- `0x180090fa4`

## import_xrefs

- `KERNEL32!CreateTimerQueueTimer` at `0x180091035`
- `KERNEL32!CreateTimerQueueTimer` at `0x180091035`
- `KERNEL32!GetCurrentThreadId` at `0x180090fd2`
- `KERNEL32!GetCurrentThreadId` at `0x180090fd2`
- `KERNEL32!GetLastError` at `0x18009103f`
- `KERNEL32!GetLastError` at `0x18009103f`

## pseudocode

```c
signed int __fastcall CTimerCallback::_Init(CTimerCallback *this)
{
  char *v2; // rbx
  signed int result; // eax

  v2 = (char *)operator new(0x20u);
  if ( v2 )
  {
    *(_QWORD *)v2 = &CTimerCallback::CTimerCallbackSink::`vftable';
    *((_DWORD *)v2 + 4) = GetCurrentThreadId();
    *((_QWORD *)v2 + 1) = 0;
    *(_QWORD *)(v2 + 20) = 1;
  }
  else
  {
    v2 = 0;
  }
  *((_QWORD *)this + 1) = v2;
  if ( !v2 )
    return -2147024882;
  result = CThreadCallback::CreateInstance((struct IThreadNotify *)v2, (struct CThreadCallback **)this + 3);
  if ( result >= 0 )
  {
    if ( CreateTimerQueueTimer(
           (PHANDLE)this + 4,
           0,
           CTimerCallback::s_TimerCallbackProc,
           (char *)this + 24,
           0x1D4C0u,
           0x1D4C0u,
           0x20u) )
    {
      *(_QWORD *)(*((_QWORD *)this + 1) + 8LL) = this;
      return 0;
    }
    else
    {
      result = GetLastError();
      if ( result > 0 )
        return (unsigned __int16)result | 0x80070000;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180090fa4  mov     [rsp+arg_0], rbx
0x180090fa9  mov     [rsp+arg_8], rsi
0x180090fae  push    rdi
0x180090faf  sub     rsp, 40h
0x180090fb3  mov     rdi, rcx
0x180090fb6  mov     ecx, 20h ; ' '; Size
0x180090fbb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180090fc0  mov     rbx, rax
0x180090fc3  test    rax, rax
0x180090fc6  jz      short loc_180090FED
0x180090fc8  lea     rax, ??_7CTimerCallbackSink@CTimerCallback@@6B@; const CTimerCallback::CTimerCallbackSink::`vftable'
0x180090fcf  mov     [rbx], rax
0x180090fd2  call    cs:__imp_GetCurrentThreadId
0x180090fd8  mov     [rbx+10h], eax
0x180090fdb  mov     qword ptr [rbx+8], 0
0x180090fe3  mov     qword ptr [rbx+14h], 1
0x180090feb  jmp     short loc_180090FEF
0x180090fed  xor     ebx, ebx
0x180090fef  mov     [rdi+8], rbx
0x180090ff3  test    rbx, rbx
0x180090ff6  jnz     short loc_180090FFF
0x180090ff8  mov     eax, 8007000Eh
0x180090ffd  jmp     short loc_18009105D
0x180090fff  lea     rdx, [rdi+18h]; struct CThreadCallback **
0x180091003  mov     rcx, rbx; struct IThreadNotify *
0x180091006  call    ?CreateInstance@CThreadCallback@@SAJPEAUIThreadNotify@@PEAPEAV1@@Z; CThreadCallback::CreateInstance(IThreadNotify *,CThreadCallback * *)
0x18009100b  test    eax, eax
0x18009100d  js      short loc_18009105D
0x18009100f  mov     eax, 1D4C0h
0x180091014  mov     [rsp+48h+Flags], 20h ; ' '; Flags
0x18009101c  mov     [rsp+48h+Period], eax; Period
0x180091020  lea     rcx, [rdi+20h]; phNewTimer
0x180091024  lea     r9, [rdi+18h]; Parameter
0x180091028  mov     [rsp+48h+DueTime], eax; DueTime
0x18009102c  lea     r8, ?s_TimerCallbackProc@CTimerCallback@@CAXPEAXE@Z; Callback
0x180091033  xor     edx, edx; TimerQueue
0x180091035  call    cs:__imp_CreateTimerQueueTimer
0x18009103b  test    eax, eax
0x18009103d  jnz     short loc_180091053
0x18009103f  call    cs:__imp_GetLastError
0x180091045  test    eax, eax
0x180091047  jle     short loc_18009105D
0x180091049  movzx   eax, ax
0x18009104c  or      eax, 80070000h
0x180091051  jmp     short loc_18009105D
0x180091053  mov     rax, [rdi+8]
0x180091057  mov     [rax+8], rdi
0x18009105b  xor     eax, eax
0x18009105d  mov     rbx, [rsp+48h+arg_0]
0x180091062  mov     rsi, [rsp+48h+arg_8]
0x180091067  add     rsp, 40h
0x18009106b  pop     rdi
0x18009106c  retn
```
