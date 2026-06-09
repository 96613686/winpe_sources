# TpmRequest::Complete(long,uint)

- ea: `0x14000e754`
- end: `0x14000e7b2`
- name: `?Complete@TpmRequest@@QEAAXJI@Z`
- size: `94`
- prototype: `void __fastcall(TpmRequest *__hidden this, int, unsigned int)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1400049b4`
- `0x14000e568`
- `0x1400116fc`

## callees

- `0x14000e7b8`
- `0x14000e854`
- `0x140039780`

## pseudocode

```c
void __fastcall TpmRequest::Complete(TpmRequest *this, unsigned int a2, unsigned int a3)
{
  unsigned int v4; // edx
  unsigned int v5; // [rsp+48h] [rbp+10h] BYREF
  unsigned int v6; // [rsp+50h] [rbp+18h] BYREF

  v6 = a3;
  v5 = a2;
  *((_DWORD *)this + 8) |= 0x4000000u;
  TpmRequest::FilterStatus(this, (int *)&v5, &v6);
  (*((void (__fastcall **)(PKDPC, _QWORD, _QWORD, _QWORD))WPP_MAIN_CB.Queue.Wcb.CurrentIrp + 265))(
    WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc,
    *((_QWORD *)this + 44),
    v5,
    v6);
  TpmRequest::`scalar deleting destructor'(this, v4);
}

```

## disassembly

```asm
0x14000e754  mov     rax, rsp
0x14000e757  mov     [rax+18h], r8d
0x14000e75b  mov     [rax+10h], edx
0x14000e75e  push    rbx
0x14000e75f  sub     rsp, 30h
0x14000e763  bts     dword ptr [rcx+20h], 1Ah
0x14000e768  lea     r8, [rax+18h]; unsigned int *
0x14000e76c  lea     rdx, [rax+10h]; int *
0x14000e770  mov     rbx, rcx
0x14000e773  call    ?FilterStatus@TpmRequest@@QEAAXPEAJPEAI@Z; TpmRequest::FilterStatus(long *,uint *)
0x14000e778  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+38h
0x14000e77f  mov     r9d, [rsp+38h+arg_10]
0x14000e784  mov     r8d, [rsp+38h+arg_8]
0x14000e789  mov     rdx, [rbx+160h]
0x14000e790  mov     rax, [rax+848h]
0x14000e797  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+40h
0x14000e79e  call    _guard_dispatch_icall
0x14000e7a3  mov     rcx, rbx; this
0x14000e7a6  call    ??_GTpmRequest@@QEAAPEAXI@Z; TpmRequest::`scalar deleting destructor'(uint)
0x14000e7ab  add     rsp, 30h
0x14000e7af  pop     rbx
0x14000e7b0  retn
```
