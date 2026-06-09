# Srv2PostOnCompletionAndClearCancel

- ea: `0x140004f00`
- end: `0x140005069`
- name: `Srv2PostOnCompletionAndClearCancel`
- size: `361`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140004f00`
- `0x1400051dc`

## import_xrefs

- `ntoskrnl!KeGetCurrentNodeNumber` at `0x140004f4f`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x140004f4f`
- `ntoskrnl!KeSetEvent` at `0x140005058`
- `ntoskrnl!KeSetEvent` at `0x140005058`
- `ntoskrnl!KeReadStateEvent` at `0x140004f89`
- `ntoskrnl!KeReadStateEvent` at `0x140004f89`
- `ntoskrnl!RtlInitAnsiString` at `0x140005007`
- `ntoskrnl!RtlInitAnsiString` at `0x140005007`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140004f6b`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140004f6b`
- `HAL!KeQueryPerformanceCounter` at `0x140004fb0`
- `HAL!KeQueryPerformanceCounter` at `0x140004fb0`

## string_xrefs

- `0x140004fed`: `Srv2PostToThreadPool`

## pseudocode

```c
__int64 __fastcall Srv2PostOnCompletionAndClearCancel(__int64 a1, __int64 a2, __int64 a3)
{
  bool v3; // zf
  __int64 v5; // rdi
  __int64 v6; // rdi
  __int64 v7; // rdi
  LARGE_INTEGER PerformanceCounter; // rax
  __int64 v10; // r8
  __int64 v11; // r9
  int v12; // edx
  int v13; // ecx
  struct _STRING DestinationString; // [rsp+40h] [rbp-18h] BYREF

  v3 = *(_DWORD *)(a3 + 8) == 5;
  *(_QWORD *)(a3 + 88) = *(_QWORD *)(a3 + 48);
  *(_QWORD *)(a3 + 48) = Srv2PostOnCompletionAndClearCancelCallback;
  *(_DWORD *)(a3 + 72) = 0;
  if ( v3 )
  {
    v5 = a3 + 584;
    v3 = *(_BYTE *)(a3 + 600) == 0;
    DestinationString = 0;
    if ( !v3 )
    {
      PerformanceCounter = KeQueryPerformanceCounter(0);
      v10 = *(unsigned __int8 *)(v5 + 128);
      if ( (((_BYTE)v10 + 1) & 0xFD) != 0 )
      {
        v11 = *(_QWORD *)(v5 + 136);
        if ( PerformanceCounter.QuadPart > v11 )
          *(_QWORD *)(v5 + 8 * v10 + 40) += PerformanceCounter.QuadPart - v11;
        ++*(_WORD *)(v5 + 2 * v10 + 18);
      }
      *(_BYTE *)(v5 + 128) = 1;
      *(LARGE_INTEGER *)(v5 + 136) = PerformanceCounter;
      RtlInitAnsiString(&DestinationString, "Srv2PostToThreadPool");
      if ( (Microsoft_Windows_SMBServerEnableBits & 4) != 0 )
        McTemplateK0qqhsr2_EtwWriteTransfer(
          v13,
          v12,
          v5,
          1,
          135,
          DestinationString.Length,
          (__int64)DestinationString.Buffer);
    }
  }
  v6 = *(_QWORD *)(*(_QWORD *)(a3 + 64) + 136LL);
  v7 = *(_QWORD *)(v6 + 8LL * KeGetCurrentNodeNumber() + 8);
  if ( !ExpInterlockedPushEntrySList((PSLIST_HEADER)(v7 + 16), (PSLIST_ENTRY)(a3 + 32))
    && *(_WORD *)(v7 + 66)
    && !KeReadStateEvent((PRKEVENT)(v7 + 72)) )
  {
    KeSetEvent((PRKEVENT)(v7 + 72), 0, 0);
  }
  return 3221225494LL;
}

```

## disassembly

```asm
0x140004f00  mov     [rsp+arg_0], rbx
0x140004f05  push    rdi
0x140004f06  sub     rsp, 50h
0x140004f0a  cmp     dword ptr [r8+8], 5
0x140004f0f  mov     rbx, r8
0x140004f12  mov     rax, [r8+30h]
0x140004f16  mov     [r8+58h], rax
0x140004f1a  lea     rax, Srv2PostOnCompletionAndClearCancelCallback
0x140004f21  mov     [r8+30h], rax
0x140004f25  mov     dword ptr [r8+48h], 0
0x140004f2d  jnz     short loc_140004F44
0x140004f2f  lea     rdi, [r8+248h]
0x140004f36  xorps   xmm0, xmm0
0x140004f39  cmp     byte ptr [rdi+10h], 0
0x140004f3d  movups  xmmword ptr [rsp+58h+DestinationString.Length], xmm0
0x140004f42  jnz     short loc_140004FAE
0x140004f44  mov     rax, [rbx+40h]
0x140004f48  mov     rdi, [rax+88h]
0x140004f4f  call    cs:__imp_KeGetCurrentNodeNumber
0x140004f56  nop     dword ptr [rax+rax+00h]
0x140004f5b  movzx   eax, ax
0x140004f5e  lea     rdx, [rbx+20h]; ListEntry
0x140004f62  mov     rdi, [rdi+rax*8+8]
0x140004f67  lea     rcx, [rdi+10h]; ListHead
0x140004f6b  call    cs:__imp_ExpInterlockedPushEntrySList
0x140004f72  nop     dword ptr [rax+rax+00h]
0x140004f77  test    rax, rax
0x140004f7a  jnz     short loc_140004F9D
0x140004f7c  movzx   ecx, word ptr [rdi+42h]
0x140004f80  cmp     ax, cx
0x140004f83  jz      short loc_140004F9D
0x140004f85  lea     rcx, [rdi+48h]; Event
0x140004f89  call    cs:__imp_KeReadStateEvent
0x140004f90  nop     dword ptr [rax+rax+00h]
0x140004f95  test    eax, eax
0x140004f97  jz      loc_14000504F
0x140004f9d  mov     rbx, [rsp+58h+arg_0]
0x140004fa2  mov     eax, 0C0000016h
0x140004fa7  add     rsp, 50h
0x140004fab  pop     rdi
0x140004fac  retn
0x140004fae  xor     ecx, ecx; PerformanceFrequency
0x140004fb0  call    cs:__imp_KeQueryPerformanceCounter
0x140004fb7  nop     dword ptr [rax+rax+00h]
0x140004fbc  movzx   r8d, byte ptr [rdi+80h]
0x140004fc4  lea     ecx, [r8+1]
0x140004fc8  test    cl, 0FDh
0x140004fcb  jz      short loc_140004FED
0x140004fcd  mov     r9, [rdi+88h]
0x140004fd4  cmp     rax, r9
0x140004fd7  jle     short loc_140004FE7
0x140004fd9  mov     rcx, rax
0x140004fdc  lea     rdx, [rdi+r8*8]
0x140004fe0  sub     rcx, r9
0x140004fe3  add     [rdx+28h], rcx
0x140004fe7  inc     word ptr [rdi+r8*2+12h]
0x140004fed  lea     rdx, SourceString; "Srv2PostToThreadPool"
0x140004ff4  mov     byte ptr [rdi+80h], 1
0x140004ffb  lea     rcx, [rsp+58h+DestinationString]; DestinationString
0x140005000  mov     [rdi+88h], rax
0x140005007  call    cs:__imp_RtlInitAnsiString
0x14000500e  nop     dword ptr [rax+rax+00h]
0x140005013  test    cs:Microsoft_Windows_SMBServerEnableBits, 4
0x14000501a  jz      loc_140004F44
0x140005020  mov     rax, [rsp+58h+DestinationString.Buffer]
0x140005025  mov     r9d, 1
0x14000502b  mov     [rsp+58h+var_28], rax
0x140005030  mov     r8, rdi
0x140005033  movzx   eax, [rsp+58h+DestinationString.Length]
0x140005038  mov     [rsp+58h+var_30], ax
0x14000503d  mov     [rsp+58h+var_38], 187h
0x140005045  call    McTemplateK0qqhsr2_EtwWriteTransfer
0x14000504a  jmp     loc_140004F44
0x14000504f  xor     r8d, r8d; Wait
0x140005052  lea     rcx, [rdi+48h]; Event
0x140005056  xor     edx, edx; Increment
0x140005058  call    cs:__imp_KeSetEvent
0x14000505f  nop     dword ptr [rax+rax+00h]
0x140005064  jmp     loc_140004F9D
```
