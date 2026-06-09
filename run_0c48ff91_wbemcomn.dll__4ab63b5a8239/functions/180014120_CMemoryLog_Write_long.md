# CMemoryLog::Write(long)

- ea: `0x180014120`
- end: `0x1800141d0`
- name: `?Write@CMemoryLog@@QEAAXJ@Z`
- size: `176`
- prototype: `void __fastcall(CMemoryLog *__hidden this, int)`
- caller_count: `205`
- callee_count: `2`
- tags: ``

## callers

- `0x1800016f0`
- `0x180001f50`
- `0x1800029a0`
- `0x180002cb0`
- `0x180002f90`
- `0x180003130`
- `0x180003270`
- `0x180003480`
- `0x180003550`
- `0x180003990`
- `0x1800044c0`
- `0x180004b60`
- `0x180004c70`
- `0x180004d60`
- `0x180004ef0`
- `0x1800056c0`
- `0x1800057d0`
- `0x180005880`
- `0x180005a80`
- `0x180005ec0`
- `0x1800061e0`
- `0x1800073e0`
- `0x180007990`
- `0x180007f80`
- `0x1800083e0`
- `0x180008540`
- `0x180008650`
- `0x180008930`
- `0x180008b50`
- `0x180008cc0`
- `0x1800095a0`
- `0x180009780`
- `0x1800099b0`
- `0x180009c40`
- `0x180009e20`
- `0x18000a420`
- `0x18000a8f0`
- `0x18000b660`
- `0x18000ce10`
- `0x18000d650`
- `0x18000d730`
- `0x18000e640`
- `0x18000eed4`
- `0x180010240`
- `0x180010460`
- `0x180010770`
- `0x180011480`
- `0x180011580`
- `0x180011600`
- `0x180011870`

## callees

- `0x180014120`
- `0x1800442d3`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001416f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001416f`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800141c8`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800141c8`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureStackBackTrace` at `0x18001419b`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureStackBackTrace` at `0x18001419b`

## pseudocode

```c
void __fastcall CMemoryLog::Write(CMemoryLog *this, unsigned int a2)
{
  __int64 v4; // rbx

  if ( *((_BYTE *)this + 20488) )
  {
    v4 = 80LL * (unsigned __int8)_InterlockedExchangeAdd((volatile signed __int32 *)this + 5120, 1u);
    *(_QWORD *)((char *)this + v4 + 8) = a2;
    *(_DWORD *)((char *)this + v4) = GetCurrentThreadId();
    memset_0((char *)this + v4 + 16, 0, 0x40u);
    RtlCaptureStackBackTrace(1u, 8u, (PVOID *)((char *)this + v4 + 16), 0);
    if ( dword_18007007C )
    {
      if ( a2 && (a2 == dword_18007007C || dword_18007007C == -1) )
        DebugBreak();
    }
  }
}

```

## disassembly

```asm
0x180014120  mov     [rsp+arg_8], rbx
0x180014125  mov     [rsp+arg_10], rsi
0x18001412a  push    rdi
0x18001412b  sub     rsp, 20h
0x18001412f  cmp     byte ptr [rcx+5008h], 0
0x180014136  mov     edi, edx
0x180014138  mov     rsi, rcx
0x18001413b  jz      short loc_1800141AB
0x18001413d  mov     eax, 1
0x180014142  lock xadd [rcx+5000h], eax
0x18001414a  mov     eax, eax
0x18001414c  movzx   r8d, al
0x180014150  mov     [rsp+28h+arg_0], 0
0x180014159  mov     dword ptr [rsp+28h+arg_0], edx
0x18001415d  mov     rax, [rsp+28h+arg_0]
0x180014162  lea     rbx, [r8+r8*4]
0x180014166  shl     rbx, 4
0x18001416a  mov     [rbx+rcx+8], rax
0x18001416f  call    cs:__imp_GetCurrentThreadId
0x180014175  xor     edx, edx; Val
0x180014177  lea     rcx, [rsi+10h]
0x18001417b  add     rcx, rbx; void *
0x18001417e  mov     [rbx+rsi], eax
0x180014181  lea     r8d, [rdx+40h]; Size
0x180014185  call    memset_0
0x18001418a  xor     r9d, r9d; BackTraceHash
0x18001418d  lea     r8, [rsi+10h]
0x180014191  add     r8, rbx; BackTrace
0x180014194  lea     edx, [r9+8]; FramesToCapture
0x180014198  lea     ecx, [rdx-7]; FramesToSkip
0x18001419b  call    cs:__imp_RtlCaptureStackBackTrace
0x1800141a1  mov     eax, cs:dword_18007007C
0x1800141a7  test    eax, eax
0x1800141a9  jnz     short loc_1800141BB
0x1800141ab  mov     rbx, [rsp+28h+arg_8]
0x1800141b0  mov     rsi, [rsp+28h+arg_10]
0x1800141b5  add     rsp, 20h
0x1800141b9  pop     rdi
0x1800141ba  retn
0x1800141bb  test    edi, edi
0x1800141bd  jz      short loc_1800141AB
0x1800141bf  cmp     edi, eax
0x1800141c1  jz      short loc_1800141C8
0x1800141c3  cmp     eax, 0FFFFFFFFh
0x1800141c6  jnz     short loc_1800141AB
0x1800141c8  call    cs:__imp_DebugBreak
0x1800141ce  jmp     short loc_1800141AB
```
