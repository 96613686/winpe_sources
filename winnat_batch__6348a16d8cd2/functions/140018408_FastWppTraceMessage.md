# FastWppTraceMessage

- ea: `0x140018408`
- end: `0x140018599`
- name: `FastWppTraceMessage`
- size: `401`
- prototype: ``
- caller_count: `20`
- callee_count: `3`
- tags: ``

## callers

- `0x14002d008`
- `0x14002d040`
- `0x14002d060`
- `0x14002d0c4`
- `0x14002d108`
- `0x14002d164`
- `0x14002d1b4`
- `0x14002d220`
- `0x14002d2b4`
- `0x14002d304`
- `0x14002d36c`
- `0x14002d3bc`
- `0x14002d400`
- `0x14002d450`
- `0x14002d4b0`
- `0x14002d4e8`
- `0x14002d53c`
- `0x14002d57c`
- `0x14002d5cc`
- `0x14002d62c`

## callees

- `0x14001837c`
- `0x140018408`
- `0x14001ede0`

## import_xrefs

- `ntoskrnl!ExAllocatePool3` at `0x1400184ea`
- `ntoskrnl!ExAllocatePool3` at `0x1400184ea`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018571`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018571`
- `ntoskrnl!EtwWriteEx` at `0x140018558`
- `ntoskrnl!EtwWriteEx` at `0x140018558`

## pseudocode

```c
void FastWppTraceMessage(__int16 a1, USHORT a2, ULONGLONG a3, ...)
{
  void *v3; // rbx
  __int64 Pool3; // rax
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+48h] [rbp-B8h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v7; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v8[256]; // [rsp+80h] [rbp-80h] BYREF
  va_list va; // [rsp+1C8h] [rbp+C8h] BYREF

  va_start(va, a3);
  EventDescriptor = 0;
  UserData = 0;
  v7 = 0;
  if ( FastWppInitState == 2 )
  {
    EventDescriptor.Id = a2;
    EventDescriptor.Level = HIBYTE(a1);
    v3 = 0;
    UserData.Type = 4;
    UserData.Size = 16;
    BYTE12(v7) = 0;
    DWORD2(v7) = 256;
    EventDescriptor.Keyword = 1LL << a1;
    UserData.Ptr = a3;
    *(_QWORD *)&v7 = v8;
    FastWppPackEvent((__int64 *)va, v8, 256, (char *)&v7 + 8);
    if ( DWORD2(v7) > 0x100 )
    {
      Pool3 = ExAllocatePool3(64, DWORD2(v7), 1180127312, 0, 0);
      v3 = (void *)Pool3;
      if ( Pool3 )
      {
        *(_QWORD *)&v7 = Pool3;
        FastWppPackEvent((__int64 *)va, Pool3, DWORD2(v7), (char *)&v7 + 8);
      }
      else
      {
        DWORD2(v7) = 256;
      }
    }
    EtwWriteEx(FastWppRegHandle, &EventDescriptor, 0, 0, 0, 0, 2u, &UserData);
    if ( v3 )
      ExFreePoolWithTag(v3, 0x46575050u);
  }
}

```

## disassembly

```asm
0x140018408  mov     [rsp-8+arg_10], r8
0x14001840d  mov     [rsp-8+arg_18], r9
0x140018412  push    rbp
0x140018413  push    rbx
0x140018414  push    r15
0x140018416  lea     rbp, [rsp-90h]
0x14001841e  sub     rsp, 190h
0x140018425  mov     rax, cs:__security_cookie
0x14001842c  xor     rax, rsp
0x14001842f  mov     [rbp+0A0h+var_20], rax
0x140018436  mov     eax, cs:FastWppInitState
0x14001843c  xorps   xmm1, xmm1
0x14001843f  mov     [rsp+1A0h+var_160], 0
0x140018448  xorps   xmm0, xmm0
0x14001844b  movups  xmmword ptr [rsp+1A0h+EventDescriptor.Id], xmm0
0x140018450  movups  xmmword ptr [rsp+1A0h+var_148.Ptr], xmm1
0x140018455  movups  [rsp+1A0h+var_138], xmm1
0x14001845a  cmp     eax, 2
0x14001845d  jnz     loc_14001857D
0x140018463  movzx   eax, cx
0x140018466  mov     [rsp+1A0h+EventDescriptor.Id], dx
0x14001846b  shr     ax, 8
0x14001846f  lea     r15, [rbp+0A0h+arg_18]
0x140018476  mov     [rsp+1A0h+EventDescriptor.Level], al
0x14001847a  lea     r9, [rsp+1A0h+var_138+8]
0x14001847f  xor     ebx, ebx
0x140018481  mov     byte ptr [rsp+1A0h+var_148.0Ch], 4
0x140018486  mov     r8d, 100h
0x14001848c  mov     [rsp+1A0h+var_148.Size], 10h
0x140018494  lea     rdx, [rbp+0A0h+var_120]
0x140018498  mov     byte ptr [rsp+1A0h+var_138+0Ch], bl
0x14001849c  mov     dword ptr [rsp+1A0h+var_138+8], 100h
0x1400184a4  lea     eax, [rbx+1]
0x1400184a7  shl     rax, cl
0x1400184aa  mov     rcx, r15
0x1400184ad  mov     [rsp+1A0h+EventDescriptor.Keyword], rax
0x1400184b2  mov     rax, [rbp+0A0h+arg_10]
0x1400184b9  mov     [rsp+1A0h+var_148.Ptr], rax
0x1400184be  lea     rax, [rbp+0A0h+var_120]
0x1400184c2  mov     qword ptr [rsp+1A0h+var_138], rax
0x1400184c7  call    FastWppPackEvent
0x1400184cc  cmp     dword ptr [rsp+1A0h+var_138+8], 100h
0x1400184d4  jbe     short loc_140018522
0x1400184d6  mov     edx, dword ptr [rsp+1A0h+var_138+8]
0x1400184da  lea     ecx, [rbx+40h]
0x1400184dd  xor     r9d, r9d
0x1400184e0  mov     dword ptr [rsp+1A0h+ActivityId], ebx
0x1400184e4  mov     r8d, 46575050h
0x1400184ea  call    cs:__imp_ExAllocatePool3
0x1400184f1  nop     dword ptr [rax+rax+00h]
0x1400184f6  mov     rbx, rax
0x1400184f9  test    rax, rax
0x1400184fc  jz      short loc_14001851A
0x1400184fe  mov     r8d, dword ptr [rsp+1A0h+var_138+8]
0x140018503  lea     r9, [rsp+1A0h+var_138+8]
0x140018508  mov     rdx, rax
0x14001850b  mov     qword ptr [rsp+1A0h+var_138], rax
0x140018510  mov     rcx, r15
0x140018513  call    FastWppPackEvent
0x140018518  jmp     short loc_140018522
0x14001851a  mov     dword ptr [rsp+1A0h+var_138+8], 100h
0x140018522  mov     rcx, cs:FastWppRegHandle; RegHandle
0x140018529  lea     rax, [rsp+1A0h+var_148]
0x14001852e  mov     [rsp+1A0h+UserData], rax; UserData
0x140018533  lea     rdx, [rsp+1A0h+EventDescriptor]; EventDescriptor
0x140018538  mov     [rsp+1A0h+UserDataCount], 2; UserDataCount
0x140018540  xor     r9d, r9d; Flags
0x140018543  mov     [rsp+1A0h+RelatedActivityId], 0; RelatedActivityId
0x14001854c  xor     r8d, r8d; Filter
0x14001854f  mov     [rsp+1A0h+ActivityId], 0; ActivityId
0x140018558  call    cs:__imp_EtwWriteEx
0x14001855f  nop     dword ptr [rax+rax+00h]
0x140018564  test    rbx, rbx
0x140018567  jz      short loc_14001857D
0x140018569  mov     edx, 46575050h; Tag
0x14001856e  mov     rcx, rbx; P
0x140018571  call    cs:__imp_ExFreePoolWithTag
0x140018578  nop     dword ptr [rax+rax+00h]
0x14001857d  mov     rcx, [rbp+0A0h+var_20]
0x140018584  xor     rcx, rsp; StackCookie
0x140018587  call    __security_check_cookie
0x14001858c  add     rsp, 190h
0x140018593  pop     r15
0x140018595  pop     rbx
0x140018596  pop     rbp
0x140018597  retn
```
