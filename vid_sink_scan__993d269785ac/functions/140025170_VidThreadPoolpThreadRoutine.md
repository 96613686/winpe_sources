# VidThreadPoolpThreadRoutine

- ea: `0x140025170`
- end: `0x1400252fe`
- name: `VidThreadPoolpThreadRoutine`
- size: `398`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x140021650`
- `0x140025170`
- `0x140030324`
- `0x1400f8c40`

## import_xrefs

- `ntoskrnl!ExUnblockOnAddressPushLockEx` at `0x140025298`
- `ntoskrnl!ExUnblockOnAddressPushLockEx` at `0x140025298`
- `ntoskrnl!KeUnstackDetachProcess` at `0x14002524d`
- `ntoskrnl!KeUnstackDetachProcess` at `0x1400252bf`
- `ntoskrnl!KeUnstackDetachProcess` at `0x14002524d`
- `ntoskrnl!KeUnstackDetachProcess` at `0x1400252bf`
- `ntoskrnl!PsTerminateSystemThread` at `0x1400252cd`
- `ntoskrnl!PsTerminateSystemThread` at `0x1400252cd`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400251bd`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400251bd`
- `ntoskrnl!KeStackAttachProcess` at `0x1400251dd`
- `ntoskrnl!KeStackAttachProcess` at `0x140025273`
- `ntoskrnl!KeStackAttachProcess` at `0x1400251dd`
- `ntoskrnl!KeStackAttachProcess` at `0x140025273`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x14002522f`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x14002522f`

## pseudocode

```c
NTSTATUS __fastcall VidThreadPoolpThreadRoutine(_QWORD *a1)
{
  __int64 *v1; // rbx
  char v3; // di
  __int64 v4; // rsi
  NTSTATUS v5; // eax
  struct _KAPC_STATE ApcState; // [rsp+40h] [rbp-9h] BYREF
  PVOID Object[2]; // [rsp+70h] [rbp+27h] BYREF
  _QWORD *v9; // [rsp+80h] [rbp+37h]

  v1 = (__int64 *)*a1;
  memset(&ApcState, 0, sizeof(ApcState));
  v9 = 0;
  v3 = 0;
  *(_OWORD *)Object = 0;
  v4 = *v1;
  if ( PsGetCurrentProcess() != *(_QWORD *)(v4 + 10312) )
  {
    KeStackAttachProcess(*(PRKPROCESS *)(v4 + 10240), &ApcState);
    v3 = 1;
  }
  Object[0] = v1 + 1;
  Object[1] = v1 + 4;
  v9 = a1 + 2;
  while ( 1 )
  {
    while ( 1 )
    {
      v5 = KeWaitForMultipleObjects(3u, Object, WaitAny, Executive, 0, 0, 0, 0);
      if ( v5 )
        break;
      VidThreadPoolpProcessQueue(v1);
    }
    if ( v5 != 1 )
      break;
    if ( v3 )
    {
      KeUnstackDetachProcess(&ApcState);
      v3 = 0;
    }
    else if ( !*(_QWORD *)(v4 + 10312) )
    {
      KeStackAttachProcess(*(PRKPROCESS *)(v4 + 10240), &ApcState);
      v3 = 1;
    }
    VidOpCtrlUnblock(v1 + 17);
    *((_BYTE *)v1 + 56) = 0;
    ExUnblockOnAddressPushLockEx(v1 + 8, 0);
  }
  if ( v3 )
    KeUnstackDetachProcess(&ApcState);
  return PsTerminateSystemThread(0);
}

```

## disassembly

```asm
0x140025170  mov     [rsp-8+arg_8], rbx
0x140025175  mov     [rsp-8+arg_10], rsi
0x14002517a  push    rbp
0x14002517b  push    rdi
0x14002517c  push    r14
0x14002517e  lea     rbp, [rsp-47h]
0x140025183  sub     rsp, 90h
0x14002518a  mov     rax, cs:__security_cookie
0x140025191  xor     rax, rsp
0x140025194  mov     [rbp+57h+var_18], rax
0x140025198  mov     rbx, [rcx]
0x14002519b  xorps   xmm0, xmm0
0x14002519e  xor     eax, eax
0x1400251a0  mov     r14, rcx
0x1400251a3  movups  xmmword ptr [rbp+57h+ApcState.ApcListHead.Flink], xmm0
0x1400251a7  mov     [rbp+57h+var_20], rax
0x1400251ab  xor     dil, dil
0x1400251ae  movups  xmmword ptr [rbp+57h+ApcState.ApcListHead.Flink+10h], xmm0
0x1400251b2  movups  xmmword ptr [rbp+57h+ApcState.Process], xmm0
0x1400251b6  movups  xmmword ptr [rbp+57h+Object], xmm0
0x1400251ba  mov     rsi, [rbx]
0x1400251bd  call    cs:__imp_PsGetCurrentProcess
0x1400251c4  nop     dword ptr [rax+rax+00h]
0x1400251c9  cmp     rax, [rsi+2848h]
0x1400251d0  jz      short loc_1400251EC
0x1400251d2  mov     rcx, [rsi+2800h]; PROCESS
0x1400251d9  lea     rdx, [rbp+57h+ApcState]; ApcState
0x1400251dd  call    cs:__imp_KeStackAttachProcess
0x1400251e4  nop     dword ptr [rax+rax+00h]
0x1400251e9  mov     dil, 1
0x1400251ec  lea     rax, [rbx+8]
0x1400251f0  mov     [rbp+57h+Object], rax
0x1400251f4  lea     rax, [rbx+20h]
0x1400251f8  mov     [rbp+57h+Object+8], rax
0x1400251fc  lea     rax, [r14+10h]
0x140025200  mov     [rbp+57h+var_20], rax
0x140025204  xor     r9d, r9d; WaitReason
0x140025207  mov     [rsp+0A0h+WaitBlockArray], 0; WaitBlockArray
0x140025210  mov     [rsp+0A0h+Timeout], 0; Timeout
0x140025219  lea     rdx, [rbp+57h+Object]; Object
0x14002521d  mov     [rsp+0A0h+Alertable], 0; Alertable
0x140025222  mov     [rsp+0A0h+WaitMode], 0; WaitMode
0x140025227  lea     r8d, [r9+1]; WaitType
0x14002522b  lea     ecx, [r9+3]; Count
0x14002522f  call    cs:__imp_KeWaitForMultipleObjects
0x140025236  nop     dword ptr [rax+rax+00h]
0x14002523b  test    eax, eax
0x14002523d  jz      short loc_1400252A9
0x14002523f  cmp     eax, 1
0x140025242  jnz     short loc_1400252B6
0x140025244  test    dil, dil
0x140025247  jz      short loc_14002525E
0x140025249  lea     rcx, [rbp+57h+ApcState]; ApcState
0x14002524d  call    cs:__imp_KeUnstackDetachProcess
0x140025254  nop     dword ptr [rax+rax+00h]
0x140025259  xor     dil, dil
0x14002525c  jmp     short loc_140025282
0x14002525e  cmp     qword ptr [rsi+2848h], 0
0x140025266  jnz     short loc_140025282
0x140025268  mov     rcx, [rsi+2800h]; PROCESS
0x14002526f  lea     rdx, [rbp+57h+ApcState]; ApcState
0x140025273  call    cs:__imp_KeStackAttachProcess
0x14002527a  nop     dword ptr [rax+rax+00h]
0x14002527f  mov     dil, 1
0x140025282  lea     rcx, [rbx+88h]
0x140025289  call    VidOpCtrlUnblock
0x14002528e  lea     rcx, [rbx+40h]
0x140025292  mov     byte ptr [rbx+38h], 0
0x140025296  xor     edx, edx
0x140025298  call    cs:__imp_ExUnblockOnAddressPushLockEx
0x14002529f  nop     dword ptr [rax+rax+00h]
0x1400252a4  jmp     loc_140025204
0x1400252a9  mov     rcx, rbx
0x1400252ac  call    VidThreadPoolpProcessQueue
0x1400252b1  jmp     loc_140025204
0x1400252b6  test    dil, dil
0x1400252b9  jz      short loc_1400252CB
0x1400252bb  lea     rcx, [rbp+57h+ApcState]; ApcState
0x1400252bf  call    cs:__imp_KeUnstackDetachProcess
0x1400252c6  nop     dword ptr [rax+rax+00h]
0x1400252cb  xor     ecx, ecx; ExitStatus
0x1400252cd  call    cs:__imp_PsTerminateSystemThread
0x1400252d4  nop     dword ptr [rax+rax+00h]
0x1400252d9  mov     rcx, [rbp+57h+var_18]
0x1400252dd  xor     rcx, rsp; StackCookie
0x1400252e0  call    __security_check_cookie
0x1400252e5  lea     r11, [rsp+0A0h+var_10]
0x1400252ed  mov     rbx, [r11+28h]
0x1400252f1  mov     rsi, [r11+30h]
0x1400252f5  mov     rsp, r11
0x1400252f8  pop     r14
0x1400252fa  pop     rdi
0x1400252fb  pop     rbp
0x1400252fc  retn
```
