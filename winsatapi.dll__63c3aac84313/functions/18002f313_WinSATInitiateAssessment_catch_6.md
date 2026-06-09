# WinSATInitiateAssessment$catch$6

- ea: `0x18002f313`
- end: `0x18002f348`
- name: `WinSATInitiateAssessment$catch$6`
- size: `53`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180012af0`
- `0x180013128`
- `0x18002f313`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TerminateThread` at `0x18002f32e`
- `api-ms-win-core-processthreads-l1-1-0!TerminateThread` at `0x18002f32e`

## pseudocode

```c
// positive sp value has been detected, the output may be wrong!
void *WinSATInitiateAssessment_catch_6()
{
  if ( hThread )
    TerminateThread(hThread, 0);
  ResetGlobalState();
  return &loc_1800130FA;
}

```

## disassembly

```asm
0x18002f313  mov     [rsp+arg_8], rdx
0x18002f318  push    rbp
0x18002f319  sub     rsp, 30h
0x18002f31d  mov     rbp, rdx
0x18002f320  mov     rcx, cs:hThread; hThread
0x18002f327  test    rcx, rcx
0x18002f32a  jz      short loc_18002F334
0x18002f32c  xor     edx, edx; dwExitCode
0x18002f32e  call    cs:__imp_TerminateThread
0x18002f334  call    ResetGlobalState
0x18002f339  nop
0x18002f33a  lea     rax, loc_1800130FA
0x18002f341  add     rsp, 30h
0x18002f345  pop     rbp
0x18002f346  retn
```
