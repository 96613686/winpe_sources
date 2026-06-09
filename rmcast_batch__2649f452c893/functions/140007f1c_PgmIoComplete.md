# PgmIoComplete

- ea: `0x140007f1c`
- end: `0x140007f95`
- name: `PgmIoComplete`
- size: `121`
- prototype: `__int64 __fastcall(PIRP Irp)`
- caller_count: `9`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1400023b8`
- `0x140005b30`
- `0x1400067f4`
- `0x14000cf04`
- `0x14001013c`
- `0x140010ae4`
- `0x1400163e4`
- `0x140018020`
- `0x140018b00`

## callees

- `0x1400074c8`
- `0x140007f1c`
- `0x140008004`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x140007f78`
- `ntoskrnl!IofCompleteRequest` at `0x140007f78`

## pseudocode

```c
void __fastcall PgmIoComplete(PIRP Irp, NTSTATUS a2, unsigned int a3)
{
  __int64 v6; // rdx
  __int64 v7; // r8

  Irp->IoStatus.Status = a2;
  if ( a3 != -1 )
    Irp->IoStatus.Information = a3;
  PgmCancelCancelRoutine(Irp);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
    WPP_SF_qDd(WPP_GLOBAL_Control->AttachedDevice, v6, v7, Irp, a2, a3);
  IofCompleteRequest(Irp, 2);
}

```

## disassembly

```asm
0x140007f1c  mov     [rsp+arg_0], rbx
0x140007f21  mov     [rsp+arg_8], rsi
0x140007f26  push    rdi
0x140007f27  sub     rsp, 30h
0x140007f2b  mov     edi, r8d
0x140007f2e  mov     esi, edx
0x140007f30  mov     [rcx+30h], edx
0x140007f33  mov     rbx, rcx
0x140007f36  cmp     r8d, 0FFFFFFFFh
0x140007f3a  jz      short loc_140007F40
0x140007f3c  mov     [rcx+38h], rdi
0x140007f40  call    PgmCancelCancelRoutine
0x140007f45  mov     rcx, cs:WPP_GLOBAL_Control
0x140007f4c  lea     rax, WPP_GLOBAL_Control
0x140007f53  cmp     rcx, rax
0x140007f56  jz      short loc_140007F73
0x140007f58  mov     eax, [rcx+2Ch]
0x140007f5b  test    al, 10h
0x140007f5d  jz      short loc_140007F73
0x140007f5f  mov     rcx, [rcx+18h]
0x140007f63  mov     r9, rbx
0x140007f66  mov     [rsp+38h+var_10], edi
0x140007f6a  mov     [rsp+38h+var_18], esi
0x140007f6e  call    WPP_SF_qDd
0x140007f73  mov     dl, 2; PriorityBoost
0x140007f75  mov     rcx, rbx; Irp
0x140007f78  call    cs:__imp_IofCompleteRequest
0x140007f7f  nop     dword ptr [rax+rax+00h]
0x140007f84  mov     rbx, [rsp+38h+arg_0]
0x140007f89  mov     rsi, [rsp+38h+arg_8]
0x140007f8e  add     rsp, 30h
0x140007f92  pop     rdi
0x140007f93  retn
```
