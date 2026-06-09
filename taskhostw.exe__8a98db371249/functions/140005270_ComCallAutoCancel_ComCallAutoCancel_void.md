# ComCallAutoCancel::ComCallAutoCancel(void)

- ea: `0x140005270`
- end: `0x14000532c`
- name: `??0ComCallAutoCancel@@QEAA@XZ`
- size: `188`
- prototype: `void **__fastcall(void **Parameter)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140004a30`
- `0x140004ec0`

## callees

- `0x140005270`
- `0x140009e3c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400052b1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400052b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005300`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005300`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x1400052dd`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x1400052dd`
- `api-ms-win-core-com-l1-1-0!CoEnableCallCancellation` at `0x140005287`
- `api-ms-win-core-com-l1-1-0!CoEnableCallCancellation` at `0x140005287`

## pseudocode

```c
void **__fastcall ComCallAutoCancel::ComCallAutoCancel(void **Parameter)
{
  int LastError; // eax
  __int64 v3; // r8
  _QWORD *v4; // rcx
  __int64 v5; // rdx

  *Parameter = 0;
  *((_DWORD *)Parameter + 2) = 0;
  LastError = CoEnableCallCancellation(0);
  if ( LastError >= 0 )
  {
    *((_DWORD *)Parameter + 2) = GetCurrentThreadId();
    if ( !CreateTimerQueueTimer(Parameter, 0, ComCallAutoCancel::TimerCallback, Parameter, 0xEA60u, 0, 8u)
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      LastError = GetLastError();
      v4 = WPP_GLOBAL_Control;
      v5 = 11;
      goto LABEL_9;
    }
  }
  else
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v5 = 10;
LABEL_9:
      WPP_SF_D(v4[2], v5, v3, (unsigned int)LastError);
    }
  }
  return Parameter;
}

```

## disassembly

```asm
0x140005270  mov     [rsp+arg_0], rbx
0x140005275  push    rdi
0x140005276  sub     rsp, 40h
0x14000527a  xor     edi, edi
0x14000527c  mov     rbx, rcx
0x14000527f  mov     [rcx], rdi
0x140005282  mov     [rcx+8], edi
0x140005285  xor     ecx, ecx; pReserved
0x140005287  call    cs:__imp_CoEnableCallCancellation
0x14000528d  test    eax, eax
0x14000528f  jns     short loc_1400052B1
0x140005291  mov     rcx, cs:WPP_GLOBAL_Control
0x140005298  lea     rdx, WPP_GLOBAL_Control
0x14000529f  cmp     rcx, rdx
0x1400052a2  jz      short loc_14000531E
0x1400052a4  test    byte ptr [rcx+1Ch], 1
0x1400052a8  jz      short loc_14000531E
0x1400052aa  mov     edx, 0Ah
0x1400052af  jmp     short loc_140005312
0x1400052b1  call    cs:__imp_GetCurrentThreadId
0x1400052b7  mov     [rsp+48h+Flags], 8; Flags
0x1400052bf  lea     r8, ?TimerCallback@ComCallAutoCancel@@CAXPEAXE@Z; Callback
0x1400052c6  mov     [rsp+48h+Period], edi; Period
0x1400052ca  mov     r9, rbx; Parameter
0x1400052cd  xor     edx, edx; TimerQueue
0x1400052cf  mov     [rbx+8], eax
0x1400052d2  mov     rcx, rbx; phNewTimer
0x1400052d5  mov     [rsp+48h+DueTime], 0EA60h; DueTime
0x1400052dd  call    cs:__imp_CreateTimerQueueTimer
0x1400052e3  test    eax, eax
0x1400052e5  jnz     short loc_14000531E
0x1400052e7  mov     rax, cs:WPP_GLOBAL_Control
0x1400052ee  lea     rdx, WPP_GLOBAL_Control
0x1400052f5  cmp     rax, rdx
0x1400052f8  jz      short loc_14000531E
0x1400052fa  test    byte ptr [rax+1Ch], 1
0x1400052fe  jz      short loc_14000531E
0x140005300  call    cs:__imp_GetLastError
0x140005306  mov     rcx, cs:WPP_GLOBAL_Control
0x14000530d  mov     edx, 0Bh
0x140005312  mov     rcx, [rcx+10h]
0x140005316  mov     r9d, eax
0x140005319  call    WPP_SF_D
0x14000531e  mov     rax, rbx
0x140005321  mov     rbx, [rsp+48h+arg_0]
0x140005326  add     rsp, 40h
0x14000532a  pop     rdi
0x14000532b  retn
```
