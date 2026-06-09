# CEnumDebugStackFrames::CEnumDebugStackFrames(unsigned __int64,CSession *)

- ea: `0x18005042c`
- end: `0x180050490`
- name: `??0CEnumDebugStackFrames@@QEAA@_KPEAVCSession@@@Z`
- size: `100`
- prototype: `CEnumDebugStackFrames *__fastcall(CEnumDebugStackFrames *__hidden this, unsigned __int64, struct CSession *)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x180050800`
- `0x180052c10`
- `0x180052cd0`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180050455`
- `KERNEL32!GetCurrentThreadId` at `0x180050455`

## pseudocode

```c
CEnumDebugStackFrames *__fastcall CEnumDebugStackFrames::CEnumDebugStackFrames(
        CEnumDebugStackFrames *this,
        __int64 a2,
        struct CSession *a3)
{
  DWORD CurrentThreadId; // eax
  CEnumDebugStackFrames *result; // rax

  *((_DWORD *)this + 2) = 1;
  *(_QWORD *)this = &CEnumDebugStackFrames::`vftable';
  CurrentThreadId = GetCurrentThreadId();
  *((_DWORD *)this + 7) &= 0xFFFFFFFC;
  *((_DWORD *)this + 3) = CurrentThreadId;
  *((_DWORD *)this + 6) = 0;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = a3;
  _InterlockedIncrement((volatile signed __int32 *)a3 + 2);
  result = this;
  *((_QWORD *)this + 2) = a2;
  return result;
}

```

## disassembly

```asm
0x18005042c  mov     [rsp+arg_0], rbx
0x180050431  mov     [rsp+arg_8], rsi
0x180050436  push    rdi
0x180050437  sub     rsp, 20h
0x18005043b  lea     rax, ??_7CEnumDebugStackFrames@@6B@; const CEnumDebugStackFrames::`vftable'
0x180050442  mov     dword ptr [rcx+8], 1
0x180050449  mov     [rcx], rax
0x18005044c  mov     rbx, r8
0x18005044f  mov     rdi, rdx
0x180050452  mov     rsi, rcx
0x180050455  call    cs:__imp_GetCurrentThreadId
0x18005045b  and     dword ptr [rsi+1Ch], 0FFFFFFFCh
0x18005045f  mov     [rsi+0Ch], eax
0x180050462  mov     dword ptr [rsi+18h], 0
0x180050469  mov     qword ptr [rsi+20h], 0
0x180050471  mov     [rsi+28h], rbx
0x180050475  lock inc dword ptr [rbx+8]
0x180050479  mov     rbx, [rsp+28h+arg_0]
0x18005047e  mov     rax, rsi
0x180050481  mov     [rsi+10h], rdi
0x180050485  mov     rsi, [rsp+28h+arg_8]
0x18005048a  add     rsp, 20h
0x18005048e  pop     rdi
0x18005048f  retn
```
