# FastWppTraceMessage

- ea: `0x1400188e8`
- end: `0x140018a79`
- name: `FastWppTraceMessage`
- size: `401`
- prototype: ``
- caller_count: `20`
- callee_count: `3`
- tags: ``

## callers

- `0x14002e008`
- `0x14002e040`
- `0x14002e060`
- `0x14002e0c4`
- `0x14002e108`
- `0x14002e164`
- `0x14002e1b4`
- `0x14002e220`
- `0x14002e2b4`
- `0x14002e304`
- `0x14002e36c`
- `0x14002e3bc`
- `0x14002e400`
- `0x14002e450`
- `0x14002e4b0`
- `0x14002e4e8`
- `0x14002e53c`
- `0x14002e57c`
- `0x14002e5cc`
- `0x14002e62c`

## callees

- `0x14001885c`
- `0x1400188e8`
- `0x14001f320`

## import_xrefs

- `ntoskrnl!ExAllocatePool3` at `0x1400189ca`
- `ntoskrnl!ExAllocatePool3` at `0x1400189ca`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018a51`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018a51`
- `ntoskrnl!EtwWriteEx` at `0x140018a38`
- `ntoskrnl!EtwWriteEx` at `0x140018a38`

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
0x1400188e8  mov     [rsp-8+arg_10], r8
0x1400188ed  mov     [rsp-8+arg_18], r9
0x1400188f2  push    rbp
0x1400188f3  push    rbx
0x1400188f4  push    r15
0x1400188f6  lea     rbp, [rsp-90h]
0x1400188fe  sub     rsp, 190h
0x140018905  mov     rax, cs:__security_cookie
0x14001890c  xor     rax, rsp
0x14001890f  mov     [rbp+0A0h+var_20], rax
0x140018916  mov     eax, cs:FastWppInitState
0x14001891c  xorps   xmm1, xmm1
0x14001891f  mov     [rsp+1A0h+var_160], 0
0x140018928  xorps   xmm0, xmm0
0x14001892b  movups  xmmword ptr [rsp+1A0h+EventDescriptor.Id], xmm0
0x140018930  movups  xmmword ptr [rsp+1A0h+var_148.Ptr], xmm1
0x140018935  movups  [rsp+1A0h+var_138], xmm1
0x14001893a  cmp     eax, 2
0x14001893d  jnz     loc_140018A5D
0x140018943  movzx   eax, cx
0x140018946  mov     [rsp+1A0h+EventDescriptor.Id], dx
0x14001894b  shr     ax, 8
0x14001894f  lea     r15, [rbp+0A0h+arg_18]
0x140018956  mov     [rsp+1A0h+EventDescriptor.Level], al
0x14001895a  lea     r9, [rsp+1A0h+var_138+8]
0x14001895f  xor     ebx, ebx
0x140018961  mov     byte ptr [rsp+1A0h+var_148.0Ch], 4
0x140018966  mov     r8d, 100h
0x14001896c  mov     [rsp+1A0h+var_148.Size], 10h
0x140018974  lea     rdx, [rbp+0A0h+var_120]
0x140018978  mov     byte ptr [rsp+1A0h+var_138+0Ch], bl
0x14001897c  mov     dword ptr [rsp+1A0h+var_138+8], 100h
0x140018984  lea     eax, [rbx+1]
0x140018987  shl     rax, cl
0x14001898a  mov     rcx, r15
0x14001898d  mov     [rsp+1A0h+EventDescriptor.Keyword], rax
0x140018992  mov     rax, [rbp+0A0h+arg_10]
0x140018999  mov     [rsp+1A0h+var_148.Ptr], rax
0x14001899e  lea     rax, [rbp+0A0h+var_120]
0x1400189a2  mov     qword ptr [rsp+1A0h+var_138], rax
0x1400189a7  call    FastWppPackEvent
0x1400189ac  cmp     dword ptr [rsp+1A0h+var_138+8], 100h
0x1400189b4  jbe     short loc_140018A02
0x1400189b6  mov     edx, dword ptr [rsp+1A0h+var_138+8]
0x1400189ba  lea     ecx, [rbx+40h]
0x1400189bd  xor     r9d, r9d
0x1400189c0  mov     dword ptr [rsp+1A0h+ActivityId], ebx
0x1400189c4  mov     r8d, 46575050h
0x1400189ca  call    cs:__imp_ExAllocatePool3
0x1400189d1  nop     dword ptr [rax+rax+00h]
0x1400189d6  mov     rbx, rax
0x1400189d9  test    rax, rax
0x1400189dc  jz      short loc_1400189FA
0x1400189de  mov     r8d, dword ptr [rsp+1A0h+var_138+8]
0x1400189e3  lea     r9, [rsp+1A0h+var_138+8]
0x1400189e8  mov     rdx, rax
0x1400189eb  mov     qword ptr [rsp+1A0h+var_138], rax
0x1400189f0  mov     rcx, r15
0x1400189f3  call    FastWppPackEvent
0x1400189f8  jmp     short loc_140018A02
0x1400189fa  mov     dword ptr [rsp+1A0h+var_138+8], 100h
0x140018a02  mov     rcx, cs:FastWppRegHandle; RegHandle
0x140018a09  lea     rax, [rsp+1A0h+var_148]
0x140018a0e  mov     [rsp+1A0h+UserData], rax; UserData
0x140018a13  lea     rdx, [rsp+1A0h+EventDescriptor]; EventDescriptor
0x140018a18  mov     [rsp+1A0h+UserDataCount], 2; UserDataCount
0x140018a20  xor     r9d, r9d; Flags
0x140018a23  mov     [rsp+1A0h+RelatedActivityId], 0; RelatedActivityId
0x140018a2c  xor     r8d, r8d; Filter
0x140018a2f  mov     [rsp+1A0h+ActivityId], 0; ActivityId
0x140018a38  call    cs:__imp_EtwWriteEx
0x140018a3f  nop     dword ptr [rax+rax+00h]
0x140018a44  test    rbx, rbx
0x140018a47  jz      short loc_140018A5D
0x140018a49  mov     edx, 46575050h; Tag
0x140018a4e  mov     rcx, rbx; P
0x140018a51  call    cs:__imp_ExFreePoolWithTag
0x140018a58  nop     dword ptr [rax+rax+00h]
0x140018a5d  mov     rcx, [rbp+0A0h+var_20]
0x140018a64  xor     rcx, rsp; StackCookie
0x140018a67  call    __security_check_cookie
0x140018a6c  add     rsp, 190h
0x140018a73  pop     r15
0x140018a75  pop     rbx
0x140018a76  pop     rbp
0x140018a77  retn
```
