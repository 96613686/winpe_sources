# CompletionRemoteWakeNotication

- ea: `0x14000f220`
- end: `0x14000f32f`
- name: `CompletionRemoteWakeNotication`
- size: `271`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x1400083c8`
- `0x140008eac`
- `0x14000c4d0`
- `0x14000f220`

## import_xrefs

- `ntoskrnl!IoCancelIrp` at `0x14000f2c6`
- `ntoskrnl!IoCancelIrp` at `0x14000f2c6`
- `ntoskrnl!IoQueueWorkItem` at `0x14000f310`
- `ntoskrnl!IoQueueWorkItem` at `0x14000f310`

## pseudocode

```c
__int64 __fastcall CompletionRemoteWakeNotication(__int64 a1, __int64 a2, _QWORD *a3)
{
  __int64 v3; // rbx
  _QWORD *v5; // rdi
  _QWORD *v6; // rsi
  char v8; // [rsp+30h] [rbp-48h]
  int v9; // [rsp+38h] [rbp-40h]

  v3 = a3[48];
  v5 = a3 + 28;
  v6 = a3 + 49;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v9 = *(_DWORD *)(a2 + 48);
    v8 = a2;
    LOBYTE(a2) = 4;
    WPP_RECORDER_SF_qqd(*v6, a2, 3, 78, (__int64)WPP_6d8a51a08a9b3edb1d37cbc5358a5e6d_Traceguids, *v5, v8, v9);
  }
  if ( *(_BYTE *)(v3 + 58) )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(a2) = 2;
      WPP_RECORDER_SF_qq(
        *v6,
        a2,
        3,
        79,
        (__int64)WPP_6d8a51a08a9b3edb1d37cbc5358a5e6d_Traceguids,
        *v5,
        *(_QWORD *)(v3 + 72));
    }
    IoCancelIrp(*(PIRP *)(v3 + 72));
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(a2) = 4;
    WPP_RECORDER_SF_q(*v6, a2, 3, 80, (__int64)WPP_6d8a51a08a9b3edb1d37cbc5358a5e6d_Traceguids, *v5);
  }
  IoQueueWorkItem(*(PIO_WORKITEM *)(v3 + 80), (PIO_WORKITEM_ROUTINE)ProcessWakeNotificationWorker, DelayedWorkQueue, a3);
  return 3221225494LL;
}

```

## disassembly

```asm
0x14000f220  push    rbx
0x14000f222  push    rbp
0x14000f223  push    rsi
0x14000f224  push    rdi
0x14000f225  push    r12
0x14000f227  push    r14
0x14000f229  sub     rsp, 48h
0x14000f22d  mov     rbx, [r8+180h]
0x14000f234  mov     rbp, r8
0x14000f237  lea     r14, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14000f23e  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14000f245  lea     rdi, [r8+0E0h]
0x14000f24c  lea     rsi, [r8+188h]
0x14000f253  lea     r12, WPP_6d8a51a08a9b3edb1d37cbc5358a5e6d_Traceguids
0x14000f25a  jz      short loc_14000F289
0x14000f25c  mov     eax, [rdx+30h]
0x14000f25f  mov     r9d, 4Eh ; 'N'
0x14000f265  mov     rcx, [rsi]
0x14000f268  mov     [rsp+78h+var_40], eax
0x14000f26c  mov     rax, [rdi]
0x14000f26f  mov     [rsp+78h+var_48], rdx
0x14000f274  lea     r8d, [r9-4Bh]
0x14000f278  mov     [rsp+78h+var_50], rax
0x14000f27d  mov     dl, 4
0x14000f27f  mov     [rsp+78h+var_58], r12
0x14000f284  call    WPP_RECORDER_SF_qqd
0x14000f289  cmp     byte ptr [rbx+3Ah], 0
0x14000f28d  jz      short loc_14000F2D2
0x14000f28f  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x14000f296  jz      short loc_14000F2C2
0x14000f298  mov     rax, [rbx+48h]
0x14000f29c  mov     r9d, 4Fh ; 'O'
0x14000f2a2  mov     rcx, [rsi]
0x14000f2a5  mov     dl, 2
0x14000f2a7  mov     [rsp+78h+var_48], rax
0x14000f2ac  mov     rax, [rdi]
0x14000f2af  mov     [rsp+78h+var_50], rax
0x14000f2b4  lea     r8d, [r9-4Ch]
0x14000f2b8  mov     [rsp+78h+var_58], r12
0x14000f2bd  call    WPP_RECORDER_SF_qq
0x14000f2c2  mov     rcx, [rbx+48h]; Irp
0x14000f2c6  call    cs:__imp_IoCancelIrp
0x14000f2cd  nop     dword ptr [rax+rax+00h]
0x14000f2d2  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x14000f2d9  jz      short loc_14000F2FC
0x14000f2db  mov     rax, [rdi]
0x14000f2de  mov     r9d, 50h ; 'P'
0x14000f2e4  mov     rcx, [rsi]
0x14000f2e7  mov     dl, 4
0x14000f2e9  mov     [rsp+78h+var_50], rax
0x14000f2ee  mov     [rsp+78h+var_58], r12
0x14000f2f3  lea     r8d, [r9-4Dh]
0x14000f2f7  call    WPP_RECORDER_SF_q
0x14000f2fc  mov     rcx, [rbx+50h]; IoWorkItem
0x14000f300  lea     rdx, ProcessWakeNotificationWorker; WorkerRoutine
0x14000f307  mov     r9, rbp; Context
0x14000f30a  mov     r8d, 1; QueueType
0x14000f310  call    cs:__imp_IoQueueWorkItem
0x14000f317  nop     dword ptr [rax+rax+00h]
0x14000f31c  mov     eax, 0C0000016h
0x14000f321  add     rsp, 48h
0x14000f325  pop     r14
0x14000f327  pop     r12
0x14000f329  pop     rdi
0x14000f32a  pop     rsi
0x14000f32b  pop     rbp
0x14000f32c  pop     rbx
0x14000f32d  retn
```
