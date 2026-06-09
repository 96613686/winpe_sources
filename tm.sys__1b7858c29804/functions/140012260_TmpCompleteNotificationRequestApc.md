# TmpCompleteNotificationRequestApc

- ea: `0x140012260`
- end: `0x1400122af`
- name: `TmpCompleteNotificationRequestApc`
- size: `79`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140012260`
- `0x1400122b8`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14001229c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001229c`
- `ntoskrnl!ObfDereferenceObject` at `0x140012283`
- `ntoskrnl!ObfDereferenceObject` at `0x140012283`

## pseudocode

```c
void __fastcall TmpCompleteNotificationRequestApc(__int64 a1, __int64 a2, __int64 a3, __int64 *a4)
{
  _QWORD *v4; // rbx
  void *v5; // rcx

  v4 = (_QWORD *)*a4;
  TmpCompleteNotificationRequestPacket((char *)(a1 - 64), *a4);
  if ( v4 )
  {
    v5 = (void *)v4[2];
    if ( v5 )
    {
      ObfDereferenceObject(v5);
      v4[2] = 0;
    }
    ExFreePoolWithTag(v4, 0);
  }
}

```

## disassembly

```asm
0x140012260  push    rbx
0x140012262  sub     rsp, 20h
0x140012266  mov     rbx, [r9]
0x140012269  add     rcx, 0FFFFFFFFFFFFFFC0h; P
0x14001226d  mov     rdx, rbx
0x140012270  call    TmpCompleteNotificationRequestPacket
0x140012275  test    rbx, rbx
0x140012278  jz      short loc_1400122A8
0x14001227a  mov     rcx, [rbx+10h]; Object
0x14001227e  test    rcx, rcx
0x140012281  jz      short loc_140012297
0x140012283  call    cs:__imp_ObfDereferenceObject
0x14001228a  nop     dword ptr [rax+rax+00h]
0x14001228f  mov     qword ptr [rbx+10h], 0
0x140012297  xor     edx, edx; Tag
0x140012299  mov     rcx, rbx; P
0x14001229c  call    cs:__imp_ExFreePoolWithTag
0x1400122a3  nop     dword ptr [rax+rax+00h]
0x1400122a8  add     rsp, 20h
0x1400122ac  pop     rbx
0x1400122ad  retn
```
