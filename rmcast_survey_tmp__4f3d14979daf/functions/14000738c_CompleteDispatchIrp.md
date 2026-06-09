# CompleteDispatchIrp

- ea: `0x14000738c`
- end: `0x14000740b`
- name: `CompleteDispatchIrp`
- size: `127`
- prototype: `__int64 __fastcall(PIRP Irp)`
- caller_count: `5`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1400075b0`
- `0x140007720`
- `0x1400078e0`
- `0x140007ab0`
- `0x140007d90`

## callees

- `0x140005328`
- `0x14000738c`
- `0x1400074c8`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x1400073ee`
- `ntoskrnl!IofCompleteRequest` at `0x1400073ee`

## pseudocode

```c
void __fastcall CompleteDispatchIrp(PIRP Irp, NTSTATUS a2)
{
  PgmCancelCancelRoutine((__int64)Irp);
  Irp->IoStatus.Status = a2;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
    WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 36, WPP_a24bb4c2db3a31577af78786167edc49_Traceguids, Irp, a2);
  IofCompleteRequest(Irp, a2 == 0 ? 2 : 0);
}

```

## disassembly

```asm
0x14000738c  mov     [rsp+arg_0], rbx
0x140007391  mov     [rsp+arg_8], rsi
0x140007396  push    rdi
0x140007397  sub     rsp, 30h
0x14000739b  mov     esi, edx
0x14000739d  mov     rdi, rcx
0x1400073a0  call    PgmCancelCancelRoutine
0x1400073a5  mov     eax, esi
0x1400073a7  mov     [rdi+30h], esi
0x1400073aa  neg     eax
0x1400073ac  sbb     bl, bl
0x1400073ae  not     bl
0x1400073b0  and     bl, 2
0x1400073b3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400073ba  lea     rax, WPP_GLOBAL_Control
0x1400073c1  cmp     rcx, rax
0x1400073c4  jz      short loc_1400073E9
0x1400073c6  mov     eax, [rcx+2Ch]
0x1400073c9  test    al, 10h
0x1400073cb  jz      short loc_1400073E9
0x1400073cd  mov     rcx, [rcx+18h]
0x1400073d1  lea     r8, WPP_a24bb4c2db3a31577af78786167edc49_Traceguids
0x1400073d8  mov     edx, 24h ; '$'
0x1400073dd  mov     [rsp+38h+var_18], esi
0x1400073e1  mov     r9, rdi
0x1400073e4  call    WPP_SF_qD
0x1400073e9  mov     dl, bl; PriorityBoost
0x1400073eb  mov     rcx, rdi; Irp
0x1400073ee  call    cs:__imp_IofCompleteRequest
0x1400073f5  nop     dword ptr [rax+rax+00h]
0x1400073fa  mov     rbx, [rsp+38h+arg_0]
0x1400073ff  mov     rsi, [rsp+38h+arg_8]
0x140007404  add     rsp, 30h
0x140007408  pop     rdi
0x140007409  retn
```
