# CEnumDebugStackFrames::CEnumDebugStackFrames(unsigned __int64,CSession *)

- ea: `0x180051bf0`
- end: `0x180051c5b`
- name: `??0CEnumDebugStackFrames@@QEAA@_KPEAVCSession@@@Z`
- size: `107`
- prototype: `CEnumDebugStackFrames *__fastcall(CEnumDebugStackFrames *__hidden this, unsigned __int64, struct CSession *)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x180051fe0`
- `0x180054470`
- `0x180054530`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180051c19`
- `KERNEL32!GetCurrentThreadId` at `0x180051c19`

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
0x180051bf0  mov     [rsp+arg_0], rbx
0x180051bf5  mov     [rsp+arg_8], rsi
0x180051bfa  push    rdi
0x180051bfb  sub     rsp, 20h
0x180051bff  lea     rax, ??_7CEnumDebugStackFrames@@6B@; const CEnumDebugStackFrames::`vftable'
0x180051c06  mov     dword ptr [rcx+8], 1
0x180051c0d  mov     [rcx], rax
0x180051c10  mov     rbx, r8
0x180051c13  mov     rdi, rdx
0x180051c16  mov     rsi, rcx
0x180051c19  call    cs:__imp_GetCurrentThreadId
0x180051c20  nop     dword ptr [rax+rax+00h]
0x180051c25  and     dword ptr [rsi+1Ch], 0FFFFFFFCh
0x180051c29  mov     [rsi+0Ch], eax
0x180051c2c  mov     dword ptr [rsi+18h], 0
0x180051c33  mov     qword ptr [rsi+20h], 0
0x180051c3b  mov     [rsi+28h], rbx
0x180051c3f  lock inc dword ptr [rbx+8]
0x180051c43  mov     rbx, [rsp+28h+arg_0]
0x180051c48  mov     rax, rsi
0x180051c4b  mov     [rsi+10h], rdi
0x180051c4f  mov     rsi, [rsp+28h+arg_8]
0x180051c54  add     rsp, 20h
0x180051c58  pop     rdi
0x180051c59  retn
```
