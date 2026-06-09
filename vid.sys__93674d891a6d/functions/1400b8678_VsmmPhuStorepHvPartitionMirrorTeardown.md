# VsmmPhuStorepHvPartitionMirrorTeardown

- ea: `0x1400b8678`
- end: `0x1400b881c`
- name: `VsmmPhuStorepHvPartitionMirrorTeardown`
- size: `420`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1400b4168`

## callees

- `0x1400029c0`
- `0x140006b68`
- `0x140008cd0`
- `0x14000a010`
- `0x140021c60`
- `0x1400248f4`
- `0x1400b8678`

## import_xrefs

- `ntoskrnl!KeRemoveQueueDpcEx` at `0x1400b87c3`
- `ntoskrnl!KeRemoveQueueDpcEx` at `0x1400b87c3`
- `ntoskrnl!KeClearEvent` at `0x1400b87d2`
- `ntoskrnl!KeClearEvent` at `0x1400b87d2`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400b877d`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400b877d`

## pseudocode

```c
NTSTATUS __fastcall VsmmPhuStorepHvPartitionMirrorTeardown(__int64 a1, __int64 a2)
{
  NTSTATUS result; // eax
  struct _KEVENT *v4; // rdi
  int v5; // r9d
  int v6; // [rsp+30h] [rbp-29h] BYREF
  __int64 v7; // [rsp+38h] [rbp-21h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v8; // [rsp+40h] [rbp-19h] BYREF
  _BYTE v9[16]; // [rsp+60h] [rbp+7h] BYREF
  _BYTE v10[16]; // [rsp+70h] [rbp+17h] BYREF
  int *v11; // [rsp+80h] [rbp+27h]
  __int64 v12; // [rsp+88h] [rbp+2Fh]
  __int64 *v13; // [rsp+90h] [rbp+37h]
  __int64 v14; // [rsp+98h] [rbp+3Fh]

  if ( *(_DWORD *)(a1 + 8660) )
  {
    v4 = (struct _KEVENT *)(a1 + 8728);
    if ( *(_DWORD *)(a1 + 8660) != 3 )
      KeWaitForSingleObject((PVOID)(a1 + 8728), Executive, 0, 0, 0);
    v5 = *(_DWORD *)(a1 + 8752);
    if ( v5 < 0 )
      VidTraceErrorStatusPartitionInternal0(
        (unsigned int)"VsmmPhuStorepHvPartitionMirrorTeardown",
        (unsigned int)"onecore\\vm\\vid\\sys\\vsmm\\vsmmphustore.c",
        4134,
        v5,
        a1 + 656);
    LOBYTE(a2) = 1;
    KeRemoveQueueDpcEx(a1 + 8664, a2);
    KeClearEvent(v4);
    _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 8660), 0, 3);
    return VidMessagePoolRequiredCountDec(a1, 1, 0);
  }
  else
  {
    result = dword_140065110;
    if ( (unsigned int)dword_140065110 > 4 )
    {
      result = tlgKeywordOn(&dword_140065110, 256);
      if ( (_BYTE)result )
      {
        tlgCreate1Sz_char(v9, "VsmmPhuStorepHvPartitionMirrorTeardown");
        tlgCreate1Sz_char(v10, "onecore\\vm\\vid\\sys\\vsmm\\vsmmphustore.c");
        v6 = 4114;
        v11 = &v6;
        v7 = *(_QWORD *)(a1 + 648);
        v12 = 4;
        v13 = &v7;
        v14 = 8;
        return tlgWriteTransfer_EtwWriteTransfer(
                 (__int64)&dword_140065110,
                 (unsigned __int8 *)byte_14004FD41,
                 0,
                 0,
                 6u,
                 &v8);
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x1400b8678  mov     [rsp-8+arg_8], rbx
0x1400b867d  mov     [rsp-8+arg_10], rdi
0x1400b8682  push    rbp
0x1400b8683  lea     rbp, [rsp-57h]
0x1400b8688  sub     rsp, 0B0h
0x1400b868f  mov     rax, cs:__security_cookie
0x1400b8696  xor     rax, rsp
0x1400b8699  mov     [rbp+57h+var_10], rax
0x1400b869d  mov     eax, [rcx+21D4h]
0x1400b86a3  mov     rbx, rcx
0x1400b86a6  test    eax, eax
0x1400b86a8  jnz     loc_1400B8757
0x1400b86ae  mov     eax, cs:dword_140065110
0x1400b86b4  cmp     eax, 4
0x1400b86b7  jbe     loc_1400B87FA
0x1400b86bd  mov     edx, 100h
0x1400b86c2  lea     rcx, dword_140065110
0x1400b86c9  call    _tlgKeywordOn
0x1400b86ce  test    al, al
0x1400b86d0  jz      loc_1400B87FA
0x1400b86d6  lea     rdx, aVsmmphustoreph_2; "VsmmPhuStorepHvPartitionMirrorTeardown"
0x1400b86dd  lea     rcx, [rbp+57h+var_50]
0x1400b86e1  call    _tlgCreate1Sz_char
0x1400b86e6  lea     rdx, aOnecoreVmVidSy_55; "onecore\\vm\\vid\\sys\\vsmm\\vsmmphusto"...
0x1400b86ed  lea     rcx, [rbp+57h+var_40]
0x1400b86f1  call    _tlgCreate1Sz_char
0x1400b86f6  lea     rax, [rbp+57h+var_80]
0x1400b86fa  mov     [rbp+57h+var_80], 1012h
0x1400b8701  mov     [rbp+57h+var_30], rax
0x1400b8705  lea     rdx, byte_14004FD41
0x1400b870c  mov     rax, [rbx+288h]
0x1400b8713  lea     rcx, dword_140065110
0x1400b871a  mov     [rbp+57h+var_78], rax
0x1400b871e  xor     r9d, r9d
0x1400b8721  lea     rax, [rbp+57h+var_78]
0x1400b8725  mov     [rbp+57h+var_28], 4
0x1400b872d  mov     [rbp+57h+var_20], rax
0x1400b8731  xor     r8d, r8d
0x1400b8734  lea     rax, [rbp+57h+var_70]
0x1400b8738  mov     [rbp+57h+var_18], 8
0x1400b8740  mov     [rsp+0B0h+var_88], rax
0x1400b8745  mov     dword ptr [rsp+0B0h+Timeout], 6
0x1400b874d  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400b8752  jmp     loc_1400B87FA
0x1400b8757  mov     eax, [rcx+21D4h]
0x1400b875d  lea     rdi, [rcx+2218h]
0x1400b8764  cmp     eax, 3
0x1400b8767  jz      short loc_1400B8789
0x1400b8769  xor     r9d, r9d; Alertable
0x1400b876c  mov     [rsp+0B0h+Timeout], 0; Timeout
0x1400b8775  xor     r8d, r8d; WaitMode
0x1400b8778  xor     edx, edx; WaitReason
0x1400b877a  mov     rcx, rdi; Object
0x1400b877d  call    cs:__imp_KeWaitForSingleObject
0x1400b8784  nop     dword ptr [rax+rax+00h]
0x1400b8789  mov     r9d, [rbx+2230h]
0x1400b8790  test    r9d, r9d
0x1400b8793  jns     short loc_1400B87BA
0x1400b8795  lea     rax, [rbx+290h]
0x1400b879c  mov     r8d, 1026h
0x1400b87a2  lea     rdx, aOnecoreVmVidSy_55; "onecore\\vm\\vid\\sys\\vsmm\\vsmmphusto"...
0x1400b87a9  mov     [rsp+0B0h+Timeout], rax
0x1400b87ae  lea     rcx, aVsmmphustoreph_2; "VsmmPhuStorepHvPartitionMirrorTeardown"
0x1400b87b5  call    VidTraceErrorStatusPartitionInternal0
0x1400b87ba  lea     rcx, [rbx+21D8h]
0x1400b87c1  mov     dl, 1
0x1400b87c3  call    cs:__imp_KeRemoveQueueDpcEx
0x1400b87ca  nop     dword ptr [rax+rax+00h]
0x1400b87cf  mov     rcx, rdi; Event
0x1400b87d2  call    cs:__imp_KeClearEvent
0x1400b87d9  nop     dword ptr [rax+rax+00h]
0x1400b87de  xor     r8d, r8d
0x1400b87e1  lea     eax, [r8+3]
0x1400b87e5  lock cmpxchg [rbx+21D4h], r8d
0x1400b87ee  lea     edx, [r8+1]
0x1400b87f2  mov     rcx, rbx
0x1400b87f5  call    VidMessagePoolRequiredCountDec
0x1400b87fa  mov     rcx, [rbp+57h+var_10]
0x1400b87fe  xor     rcx, rsp; StackCookie
0x1400b8801  call    __security_check_cookie
0x1400b8806  lea     r11, [rsp+0B0h+var_s0]
0x1400b880e  mov     rbx, [r11+18h]
0x1400b8812  mov     rdi, [r11+20h]
0x1400b8816  mov     rsp, r11
0x1400b8819  pop     rbp
0x1400b881a  retn
```
