# VidThreadPoolpThreadRoutine

- ea: `0x140025310`
- end: `0x14002549e`
- name: `VidThreadPoolpThreadRoutine`
- size: `398`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x140021c60`
- `0x140025310`
- `0x140030524`
- `0x1400fb404`

## import_xrefs

- `ntoskrnl!ExUnblockOnAddressPushLockEx` at `0x140025438`
- `ntoskrnl!ExUnblockOnAddressPushLockEx` at `0x140025438`
- `ntoskrnl!KeUnstackDetachProcess` at `0x1400253ed`
- `ntoskrnl!KeUnstackDetachProcess` at `0x14002545f`
- `ntoskrnl!KeUnstackDetachProcess` at `0x1400253ed`
- `ntoskrnl!KeUnstackDetachProcess` at `0x14002545f`
- `ntoskrnl!PsTerminateSystemThread` at `0x14002546d`
- `ntoskrnl!PsTerminateSystemThread` at `0x14002546d`
- `ntoskrnl!PsGetCurrentProcess` at `0x14002535d`
- `ntoskrnl!PsGetCurrentProcess` at `0x14002535d`
- `ntoskrnl!KeStackAttachProcess` at `0x14002537d`
- `ntoskrnl!KeStackAttachProcess` at `0x140025413`
- `ntoskrnl!KeStackAttachProcess` at `0x14002537d`
- `ntoskrnl!KeStackAttachProcess` at `0x140025413`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x1400253cf`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x1400253cf`

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
0x140025310  mov     [rsp-8+arg_8], rbx
0x140025315  mov     [rsp-8+arg_10], rsi
0x14002531a  push    rbp
0x14002531b  push    rdi
0x14002531c  push    r14
0x14002531e  lea     rbp, [rsp-47h]
0x140025323  sub     rsp, 90h
0x14002532a  mov     rax, cs:__security_cookie
0x140025331  xor     rax, rsp
0x140025334  mov     [rbp+57h+var_18], rax
0x140025338  mov     rbx, [rcx]
0x14002533b  xorps   xmm0, xmm0
0x14002533e  xor     eax, eax
0x140025340  mov     r14, rcx
0x140025343  movups  xmmword ptr [rbp+57h+ApcState.ApcListHead.Flink], xmm0
0x140025347  mov     [rbp+57h+var_20], rax
0x14002534b  xor     dil, dil
0x14002534e  movups  xmmword ptr [rbp+57h+ApcState.ApcListHead.Flink+10h], xmm0
0x140025352  movups  xmmword ptr [rbp+57h+ApcState.Process], xmm0
0x140025356  movups  xmmword ptr [rbp+57h+Object], xmm0
0x14002535a  mov     rsi, [rbx]
0x14002535d  call    cs:__imp_PsGetCurrentProcess
0x140025364  nop     dword ptr [rax+rax+00h]
0x140025369  cmp     rax, [rsi+2848h]
0x140025370  jz      short loc_14002538C
0x140025372  mov     rcx, [rsi+2800h]; PROCESS
0x140025379  lea     rdx, [rbp+57h+ApcState]; ApcState
0x14002537d  call    cs:__imp_KeStackAttachProcess
0x140025384  nop     dword ptr [rax+rax+00h]
0x140025389  mov     dil, 1
0x14002538c  lea     rax, [rbx+8]
0x140025390  mov     [rbp+57h+Object], rax
0x140025394  lea     rax, [rbx+20h]
0x140025398  mov     [rbp+57h+Object+8], rax
0x14002539c  lea     rax, [r14+10h]
0x1400253a0  mov     [rbp+57h+var_20], rax
0x1400253a4  xor     r9d, r9d; WaitReason
0x1400253a7  mov     [rsp+0A0h+WaitBlockArray], 0; WaitBlockArray
0x1400253b0  mov     [rsp+0A0h+Timeout], 0; Timeout
0x1400253b9  lea     rdx, [rbp+57h+Object]; Object
0x1400253bd  mov     [rsp+0A0h+Alertable], 0; Alertable
0x1400253c2  mov     [rsp+0A0h+WaitMode], 0; WaitMode
0x1400253c7  lea     r8d, [r9+1]; WaitType
0x1400253cb  lea     ecx, [r9+3]; Count
0x1400253cf  call    cs:__imp_KeWaitForMultipleObjects
0x1400253d6  nop     dword ptr [rax+rax+00h]
0x1400253db  test    eax, eax
0x1400253dd  jz      short loc_140025449
0x1400253df  cmp     eax, 1
0x1400253e2  jnz     short loc_140025456
0x1400253e4  test    dil, dil
0x1400253e7  jz      short loc_1400253FE
0x1400253e9  lea     rcx, [rbp+57h+ApcState]; ApcState
0x1400253ed  call    cs:__imp_KeUnstackDetachProcess
0x1400253f4  nop     dword ptr [rax+rax+00h]
0x1400253f9  xor     dil, dil
0x1400253fc  jmp     short loc_140025422
0x1400253fe  cmp     qword ptr [rsi+2848h], 0
0x140025406  jnz     short loc_140025422
0x140025408  mov     rcx, [rsi+2800h]; PROCESS
0x14002540f  lea     rdx, [rbp+57h+ApcState]; ApcState
0x140025413  call    cs:__imp_KeStackAttachProcess
0x14002541a  nop     dword ptr [rax+rax+00h]
0x14002541f  mov     dil, 1
0x140025422  lea     rcx, [rbx+88h]
0x140025429  call    VidOpCtrlUnblock
0x14002542e  lea     rcx, [rbx+40h]
0x140025432  mov     byte ptr [rbx+38h], 0
0x140025436  xor     edx, edx
0x140025438  call    cs:__imp_ExUnblockOnAddressPushLockEx
0x14002543f  nop     dword ptr [rax+rax+00h]
0x140025444  jmp     loc_1400253A4
0x140025449  mov     rcx, rbx
0x14002544c  call    VidThreadPoolpProcessQueue
0x140025451  jmp     loc_1400253A4
0x140025456  test    dil, dil
0x140025459  jz      short loc_14002546B
0x14002545b  lea     rcx, [rbp+57h+ApcState]; ApcState
0x14002545f  call    cs:__imp_KeUnstackDetachProcess
0x140025466  nop     dword ptr [rax+rax+00h]
0x14002546b  xor     ecx, ecx; ExitStatus
0x14002546d  call    cs:__imp_PsTerminateSystemThread
0x140025474  nop     dword ptr [rax+rax+00h]
0x140025479  mov     rcx, [rbp+57h+var_18]
0x14002547d  xor     rcx, rsp; StackCookie
0x140025480  call    __security_check_cookie
0x140025485  lea     r11, [rsp+0A0h+var_10]
0x14002548d  mov     rbx, [r11+28h]
0x140025491  mov     rsi, [r11+30h]
0x140025495  mov     rsp, r11
0x140025498  pop     r14
0x14002549a  pop     rdi
0x14002549b  pop     rbp
0x14002549c  retn
```
